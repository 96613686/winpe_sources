# WskTdiWQRoutineEndpointBind

- ea: `0x1400660d0`
- end: `0x14006631a`
- name: `WskTdiWQRoutineEndpointBind`
- size: `586`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140064720`
- `0x140064ef0`
- `0x140065730`

## callees

- `0x140005b60`
- `0x140013030`
- `0x14003ffdc`
- `0x140043ac4`
- `0x140063948`
- `0x140063a5c`
- `0x140063c44`
- `0x140063e04`
- `0x14006404c`
- `0x1400660d0`
- `0x140072920`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1400660e5`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400660e5`
- `ntoskrnl!KeAttachProcess` at `0x14006625e`
- `ntoskrnl!KeAttachProcess` at `0x14006625e`
- `ntoskrnl!KeDetachProcess` at `0x1400662f1`
- `ntoskrnl!KeDetachProcess` at `0x1400662f1`
- `ntoskrnl!KeDelayExecutionThread` at `0x14006617f`
- `ntoskrnl!KeDelayExecutionThread` at `0x14006617f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140066116`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140066116`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006612d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006612d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400662c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400662c1`

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
0x1400660d0  mov     [rsp+arg_8], rbx
0x1400660d5  mov     [rsp+arg_10], rbp
0x1400660da  push    rsi
0x1400660db  push    rdi
0x1400660dc  push    r14
0x1400660de  sub     rsp, 30h
0x1400660e2  mov     rsi, rcx
0x1400660e5  call    cs:__imp_PsGetCurrentProcess
0x1400660ec  nop     dword ptr [rax+rax+00h]
0x1400660f1  mov     r14, rax
0x1400660f4  lea     rdi, [rsi-128h]
0x1400660fb  mov     rsi, [rsi]
0x1400660fe  mov     ecx, [rdi+10h]
0x140066101  test    cl, 40h
0x140066104  jz      loc_14006624D
0x14006610a  test    cl, cl
0x14006610c  jns     loc_1400661AD
0x140066112  lea     rcx, [rdi+8]; SpinLock
0x140066116  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14006611d  nop     dword ptr [rax+rax+00h]
0x140066122  btr     dword ptr [rdi+10h], 7
0x140066127  lea     rcx, [rdi+8]; SpinLock
0x14006612b  mov     dl, al; NewIrql
0x14006612d  call    cs:__imp_KeReleaseSpinLock
0x140066134  nop     dword ptr [rax+rax+00h]
0x140066139  mov     rcx, rdi
0x14006613c  call    WskTdiPopulateReadyEndpoints
0x140066141  cmp     byte ptr [rdi+2], 0
0x140066145  jnz     short loc_1400661A0
0x140066147  test    dword ptr [rdi+10h], 20000h
0x14006614e  jz      short loc_1400661A0
0x140066150  mov     eax, [rdi+0B0h]
0x140066156  cmp     eax, 64h ; 'd'
0x140066159  jge     short loc_14006616D
0x14006615b  mov     eax, [rdi+10h]
0x14006615e  test    al, 20h
0x140066160  jz      short loc_1400661A0
0x140066162  mov     eax, [rdi+0B4h]
0x140066168  cmp     eax, 64h ; 'd'
0x14006616b  jl      short loc_1400661A0
0x14006616d  lea     r8, [rsp+48h+Interval]; Interval
0x140066172  mov     qword ptr [rsp+48h+Interval], 0FFFFFFFFFFF85EE0h
0x14006617b  xor     edx, edx; Alertable
0x14006617d  xor     ecx, ecx; WaitMode
0x14006617f  call    cs:__imp_KeDelayExecutionThread
0x140066186  nop     dword ptr [rax+rax+00h]
0x14006618b  mov     r8d, 64h ; 'd'
0x140066191  mov     dl, 1
0x140066193  mov     rcx, rdi
0x140066196  call    WskTdiInitiatePopulate
0x14006619b  jmp     loc_1400662FD
0x1400661a0  mov     rcx, rdi
0x1400661a3  call    WskTdiReleaseTDIEndpoint
0x1400661a8  jmp     loc_1400662FD
0x1400661ad  mov     eax, [rdi+10h]
0x1400661b0  mov     dword ptr [rdi+0B0h], 64h ; 'd'
0x1400661ba  test    al, 20h
0x1400661bc  jz      short loc_1400661C8
0x1400661be  mov     dword ptr [rdi+0B4h], 64h ; 'd'
0x1400661c8  mov     rcx, rdi
0x1400661cb  call    WskTdiPopulateReadyEndpoints
0x1400661d0  mov     ebx, eax
0x1400661d2  test    eax, eax
0x1400661d4  js      short loc_140066225
0x1400661d6  lock inc dword ptr [rdi+18h]
0x1400661da  mov     rax, [rdi+138h]
0x1400661e1  lea     r9, WskTdiTLProviderListenDispatch
0x1400661e8  mov     rcx, [rdi+130h]
0x1400661ef  mov     r8, rdi
0x1400661f2  mov     edx, ebx
0x1400661f4  call    _guard_dispatch_icall
0x1400661f9  lea     rax, WskProTLClientListenDispatch
0x140066200  xchg    rax, [rdi+120h]
0x140066207  or      eax, 0FFFFFFFFh
0x14006620a  lock xadd [rdi+18h], eax
0x14006620f  cmp     eax, 1
0x140066212  jnz     loc_1400662FD
0x140066218  mov     rcx, rdi
0x14006621b  call    WskTdiFreeEndpoint
0x140066220  jmp     loc_1400662FD
0x140066225  mov     rcx, rdi
0x140066228  call    WskTdiFlushReadyEndpoints
0x14006622d  mov     rax, [rdi+138h]
0x140066234  xor     r9d, r9d
0x140066237  mov     rcx, [rdi+130h]
0x14006623e  xor     r8d, r8d
0x140066241  mov     edx, ebx
0x140066243  call    _guard_dispatch_icall
0x140066248  jmp     loc_1400662FD
0x14006624d  mov     rcx, [rdi+110h]; Process
0x140066254  test    rcx, rcx
0x140066257  jz      short loc_14006626E
0x140066259  cmp     r14, rcx
0x14006625c  jz      short loc_14006626E
0x14006625e  call    cs:__imp_KeAttachProcess
0x140066265  nop     dword ptr [rax+rax+00h]
0x14006626a  mov     bl, 1
0x14006626c  jmp     short loc_140066270
0x14006626e  xor     bl, bl
0x140066270  test    dword ptr [rdi+10h], 200h
0x140066277  mov     rcx, rdi; __int64
0x14006627a  jz      short loc_140066283
0x14006627c  call    WskTdiConnectCore
0x140066281  jmp     short loc_1400662ED
0x140066283  call    WskTdiResolveFamilyAndCreateAO
0x140066288  mov     ebp, eax
0x14006628a  test    eax, eax
0x14006628c  jns     short loc_1400662D5
0x14006628e  mov     r9, [rdi+30h]
0x140066292  movzx   ecx, word ptr [r9]; af
0x140066296  call    SOCKADDR_SIZE
0x14006629b  movzx   r8d, al
0x14006629f  cmp     r8d, cs:AfdStandardAddressLength
0x1400662a6  ja      short loc_1400662B9
0x1400662a8  mov     rcx, cs:PplAddressPool
0x1400662af  mov     rdx, r9
0x1400662b2  call    PplFreeToLookasideList
0x1400662b7  jmp     short loc_1400662CD
0x1400662b9  mov     edx, 52646641h; Tag
0x1400662be  mov     rcx, r9; P
0x1400662c1  call    cs:__imp_ExFreePoolWithTag
0x1400662c8  nop     dword ptr [rax+rax+00h]
0x1400662cd  mov     qword ptr [rdi+30h], 0
0x1400662d5  mov     rax, [rdi+138h]
0x1400662dc  xor     r8d, r8d
0x1400662df  mov     rcx, [rdi+130h]
0x1400662e6  mov     edx, ebp
0x1400662e8  call    _guard_dispatch_icall
0x1400662ed  test    bl, bl
0x1400662ef  jz      short loc_1400662FD
0x1400662f1  call    cs:__imp_KeDetachProcess
0x1400662f8  nop     dword ptr [rax+rax+00h]
0x1400662fd  test    rsi, rsi
0x140066300  jnz     loc_1400660F4
0x140066306  mov     rbx, [rsp+48h+arg_8]
0x14006630b  mov     rbp, [rsp+48h+arg_10]
0x140066310  add     rsp, 30h
0x140066314  pop     r14
0x140066316  pop     rdi
0x140066317  pop     rsi
0x140066318  retn
```
