# WskTdiWQRoutineEndpointBind

- ea: `0x140065f30`
- end: `0x14006617a`
- name: `WskTdiWQRoutineEndpointBind`
- size: `586`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140064580`
- `0x140064d50`
- `0x140065590`

## callees

- `0x140005b60`
- `0x140013030`
- `0x14003ffbc`
- `0x140043aa4`
- `0x1400637a8`
- `0x1400638bc`
- `0x140063aa4`
- `0x140063c64`
- `0x140063eac`
- `0x140065f30`
- `0x140072780`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140065f45`
- `ntoskrnl!PsGetCurrentProcess` at `0x140065f45`
- `ntoskrnl!KeAttachProcess` at `0x1400660be`
- `ntoskrnl!KeAttachProcess` at `0x1400660be`
- `ntoskrnl!KeDetachProcess` at `0x140066151`
- `ntoskrnl!KeDetachProcess` at `0x140066151`
- `ntoskrnl!KeDelayExecutionThread` at `0x140065fdf`
- `ntoskrnl!KeDelayExecutionThread` at `0x140065fdf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140065f76`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140065f76`
- `ntoskrnl!KeReleaseSpinLock` at `0x140065f8d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140065f8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066121`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066121`

## pseudocode

```c
void __fastcall WskTdiWQRoutineEndpointBind(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  _QWORD *v4; // rsi
  __int64 CurrentProcess; // r14
  __int64 v6; // rdi
  int v7; // ecx
  KIRQL v8; // al
  __int64 v9; // rdx
  int v10; // eax
  int ready; // ebx
  struct _KPROCESS *v12; // rcx
  char v13; // bl
  int AO; // ebp
  void *v15; // r9
  union _LARGE_INTEGER Interval; // [rsp+50h] [rbp+8h] BYREF

  v4 = a1;
  CurrentProcess = PsGetCurrentProcess(a1, a2, a3, a4);
  do
  {
    v6 = (__int64)(v4 - 37);
    v4 = (_QWORD *)*v4;
    v7 = *(_DWORD *)(v6 + 16);
    if ( (v7 & 0x40) != 0 )
    {
      if ( (v7 & 0x80u) == 0 )
      {
        v10 = *(_DWORD *)(v6 + 16);
        *(_DWORD *)(v6 + 176) = 100;
        if ( (v10 & 0x20) != 0 )
          *(_DWORD *)(v6 + 180) = 100;
        ready = WskTdiPopulateReadyEndpoints(v6);
        if ( ready < 0 )
        {
          WskTdiFlushReadyEndpoints(v6);
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(v6 + 312))(
            *(_QWORD *)(v6 + 304),
            (unsigned int)ready,
            0,
            0);
        }
        else
        {
          _InterlockedIncrement((volatile signed __int32 *)(v6 + 24));
          (*(void (__fastcall **)(_QWORD, _QWORD, __int64, __int64 (__fastcall **)()))(v6 + 312))(
            *(_QWORD *)(v6 + 304),
            (unsigned int)ready,
            v6,
            WskTdiTLProviderListenDispatch);
          _InterlockedExchange64((volatile __int64 *)(v6 + 288), (__int64)WskProTLClientListenDispatch);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 24), 0xFFFFFFFF) == 1 )
            WskTdiFreeEndpoint(v6);
        }
      }
      else
      {
        v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v6 + 8));
        *(_DWORD *)(v6 + 16) &= ~0x80u;
        KeReleaseSpinLock((PKSPIN_LOCK)(v6 + 8), v8);
        WskTdiPopulateReadyEndpoints(v6);
        if ( !*(_BYTE *)(v6 + 2)
          && (*(_DWORD *)(v6 + 16) & 0x20000) != 0
          && (*(int *)(v6 + 176) >= 100 || (*(_DWORD *)(v6 + 16) & 0x20) != 0 && *(int *)(v6 + 180) >= 100) )
        {
          Interval.QuadPart = -500000;
          KeDelayExecutionThread(0, 0, &Interval);
          LOBYTE(v9) = 1;
          WskTdiInitiatePopulate(v6, v9, 100);
        }
        else
        {
          WskTdiReleaseTDIEndpoint(v6);
        }
      }
    }
    else
    {
      v12 = *(struct _KPROCESS **)(v6 + 272);
      if ( !v12 || (struct _KPROCESS *)CurrentProcess == v12 )
      {
        v13 = 0;
      }
      else
      {
        KeAttachProcess(v12);
        v13 = 1;
      }
      if ( (*(_DWORD *)(v6 + 16) & 0x200) != 0 )
      {
        WskTdiConnectCore(v6);
      }
      else
      {
        AO = WskTdiResolveFamilyAndCreateAO(v6);
        if ( AO < 0 )
        {
          if ( SOCKADDR_SIZE(**(_WORD **)(v6 + 48)) > (unsigned int)AfdStandardAddressLength )
            ExFreePoolWithTag(v15, 0x52646641u);
          else
            PplFreeToLookasideList((__int64)PplAddressPool, v15);
          *(_QWORD *)(v6 + 48) = 0;
        }
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(v6 + 312))(*(_QWORD *)(v6 + 304), (unsigned int)AO, 0);
      }
      if ( v13 )
        KeDetachProcess();
    }
  }
  while ( v4 );
}

```

## disassembly

```asm
0x140065f30  mov     [rsp+arg_8], rbx
0x140065f35  mov     [rsp+arg_10], rbp
0x140065f3a  push    rsi
0x140065f3b  push    rdi
0x140065f3c  push    r14
0x140065f3e  sub     rsp, 30h
0x140065f42  mov     rsi, rcx
0x140065f45  call    cs:__imp_PsGetCurrentProcess
0x140065f4c  nop     dword ptr [rax+rax+00h]
0x140065f51  mov     r14, rax
0x140065f54  lea     rdi, [rsi-128h]
0x140065f5b  mov     rsi, [rsi]
0x140065f5e  mov     ecx, [rdi+10h]
0x140065f61  test    cl, 40h
0x140065f64  jz      loc_1400660AD
0x140065f6a  test    cl, cl
0x140065f6c  jns     loc_14006600D
0x140065f72  lea     rcx, [rdi+8]; SpinLock
0x140065f76  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140065f7d  nop     dword ptr [rax+rax+00h]
0x140065f82  btr     dword ptr [rdi+10h], 7
0x140065f87  lea     rcx, [rdi+8]; SpinLock
0x140065f8b  mov     dl, al; NewIrql
0x140065f8d  call    cs:__imp_KeReleaseSpinLock
0x140065f94  nop     dword ptr [rax+rax+00h]
0x140065f99  mov     rcx, rdi
0x140065f9c  call    WskTdiPopulateReadyEndpoints
0x140065fa1  cmp     byte ptr [rdi+2], 0
0x140065fa5  jnz     short loc_140066000
0x140065fa7  test    dword ptr [rdi+10h], 20000h
0x140065fae  jz      short loc_140066000
0x140065fb0  mov     eax, [rdi+0B0h]
0x140065fb6  cmp     eax, 64h ; 'd'
0x140065fb9  jge     short loc_140065FCD
0x140065fbb  mov     eax, [rdi+10h]
0x140065fbe  test    al, 20h
0x140065fc0  jz      short loc_140066000
0x140065fc2  mov     eax, [rdi+0B4h]
0x140065fc8  cmp     eax, 64h ; 'd'
0x140065fcb  jl      short loc_140066000
0x140065fcd  lea     r8, [rsp+48h+Interval]; Interval
0x140065fd2  mov     qword ptr [rsp+48h+Interval], 0FFFFFFFFFFF85EE0h
0x140065fdb  xor     edx, edx; Alertable
0x140065fdd  xor     ecx, ecx; WaitMode
0x140065fdf  call    cs:__imp_KeDelayExecutionThread
0x140065fe6  nop     dword ptr [rax+rax+00h]
0x140065feb  mov     r8d, 64h ; 'd'
0x140065ff1  mov     dl, 1
0x140065ff3  mov     rcx, rdi
0x140065ff6  call    WskTdiInitiatePopulate
0x140065ffb  jmp     loc_14006615D
0x140066000  mov     rcx, rdi
0x140066003  call    WskTdiReleaseTDIEndpoint
0x140066008  jmp     loc_14006615D
0x14006600d  mov     eax, [rdi+10h]
0x140066010  mov     dword ptr [rdi+0B0h], 64h ; 'd'
0x14006601a  test    al, 20h
0x14006601c  jz      short loc_140066028
0x14006601e  mov     dword ptr [rdi+0B4h], 64h ; 'd'
0x140066028  mov     rcx, rdi
0x14006602b  call    WskTdiPopulateReadyEndpoints
0x140066030  mov     ebx, eax
0x140066032  test    eax, eax
0x140066034  js      short loc_140066085
0x140066036  lock inc dword ptr [rdi+18h]
0x14006603a  mov     rax, [rdi+138h]
0x140066041  lea     r9, WskTdiTLProviderListenDispatch
0x140066048  mov     rcx, [rdi+130h]
0x14006604f  mov     r8, rdi
0x140066052  mov     edx, ebx
0x140066054  call    _guard_dispatch_icall
0x140066059  lea     rax, WskProTLClientListenDispatch
0x140066060  xchg    rax, [rdi+120h]
0x140066067  or      eax, 0FFFFFFFFh
0x14006606a  lock xadd [rdi+18h], eax
0x14006606f  cmp     eax, 1
0x140066072  jnz     loc_14006615D
0x140066078  mov     rcx, rdi
0x14006607b  call    WskTdiFreeEndpoint
0x140066080  jmp     loc_14006615D
0x140066085  mov     rcx, rdi
0x140066088  call    WskTdiFlushReadyEndpoints
0x14006608d  mov     rax, [rdi+138h]
0x140066094  xor     r9d, r9d
0x140066097  mov     rcx, [rdi+130h]
0x14006609e  xor     r8d, r8d
0x1400660a1  mov     edx, ebx
0x1400660a3  call    _guard_dispatch_icall
0x1400660a8  jmp     loc_14006615D
0x1400660ad  mov     rcx, [rdi+110h]; Process
0x1400660b4  test    rcx, rcx
0x1400660b7  jz      short loc_1400660CE
0x1400660b9  cmp     r14, rcx
0x1400660bc  jz      short loc_1400660CE
0x1400660be  call    cs:__imp_KeAttachProcess
0x1400660c5  nop     dword ptr [rax+rax+00h]
0x1400660ca  mov     bl, 1
0x1400660cc  jmp     short loc_1400660D0
0x1400660ce  xor     bl, bl
0x1400660d0  test    dword ptr [rdi+10h], 200h
0x1400660d7  mov     rcx, rdi; __int64
0x1400660da  jz      short loc_1400660E3
0x1400660dc  call    WskTdiConnectCore
0x1400660e1  jmp     short loc_14006614D
0x1400660e3  call    WskTdiResolveFamilyAndCreateAO
0x1400660e8  mov     ebp, eax
0x1400660ea  test    eax, eax
0x1400660ec  jns     short loc_140066135
0x1400660ee  mov     r9, [rdi+30h]
0x1400660f2  movzx   ecx, word ptr [r9]; af
0x1400660f6  call    SOCKADDR_SIZE
0x1400660fb  movzx   r8d, al
0x1400660ff  cmp     r8d, cs:AfdStandardAddressLength
0x140066106  ja      short loc_140066119
0x140066108  mov     rcx, cs:PplAddressPool
0x14006610f  mov     rdx, r9
0x140066112  call    PplFreeToLookasideList
0x140066117  jmp     short loc_14006612D
0x140066119  mov     edx, 52646641h; Tag
0x14006611e  mov     rcx, r9; P
0x140066121  call    cs:__imp_ExFreePoolWithTag
0x140066128  nop     dword ptr [rax+rax+00h]
0x14006612d  mov     qword ptr [rdi+30h], 0
0x140066135  mov     rax, [rdi+138h]
0x14006613c  xor     r8d, r8d
0x14006613f  mov     rcx, [rdi+130h]
0x140066146  mov     edx, ebp
0x140066148  call    _guard_dispatch_icall
0x14006614d  test    bl, bl
0x14006614f  jz      short loc_14006615D
0x140066151  call    cs:__imp_KeDetachProcess
0x140066158  nop     dword ptr [rax+rax+00h]
0x14006615d  test    rsi, rsi
0x140066160  jnz     loc_140065F54
0x140066166  mov     rbx, [rsp+48h+arg_8]
0x14006616b  mov     rbp, [rsp+48h+arg_10]
0x140066170  add     rsp, 30h
0x140066174  pop     r14
0x140066176  pop     rdi
0x140066177  pop     rsi
0x140066178  retn
```
