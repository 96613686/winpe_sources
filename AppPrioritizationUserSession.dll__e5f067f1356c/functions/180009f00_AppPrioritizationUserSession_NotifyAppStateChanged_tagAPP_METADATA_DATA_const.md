# AppPrioritizationUserSession::NotifyAppStateChanged(tagAPP_METADATA_DATA const &)

- ea: `0x180009f00`
- end: `0x18000a078`
- name: `?NotifyAppStateChanged@AppPrioritizationUserSession@@EEAAXAEBUtagAPP_METADATA_DATA@@@Z`
- size: `376`
- prototype: `void __fastcall(RTL_SRWLOCK *this, struct _EVENT_DATA_DESCRIPTOR *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001304`
- `0x180002650`
- `0x180009f00`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009f34`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009f34`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a04d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a04d`

## pseudocode

```c
void __fastcall AppPrioritizationUserSession::NotifyAppStateChanged(
        RTL_SRWLOCK *this,
        struct _EVENT_DATA_DESCRIPTOR *a2)
{
  RTL_SRWLOCK *v4; // rbx
  unsigned int v5; // r8d
  const char *v6; // r9
  const char **Ptr; // rdi
  const char **v8; // rsi
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // [rsp+50h] [rbp-58h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+60h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v4 = this + 9;
  AcquireSRWLockExclusive(this + 9);
  Ptr = (const char **)this[10].Ptr;
  v8 = (const char **)this[11].Ptr;
  try
  {
    while ( Ptr != v8 )
    {
      v9 = 0;
      v13 = 0;
      v6 = *Ptr;
      if ( *Ptr )
      {
        v10 = (*(__int64 (__fastcall **)(const char *, GUID *, __int64 *))(*(_QWORD *)v6 + 24LL))(
                *Ptr,
                &GUID_62b620b7_cedf_42b6_9cce_312fae152147,
                &v13);
        v9 = v13;
      }
      else
      {
        v10 = 0;
      }
      if ( v10 >= 0 )
      {
        v14 = *a2;
        (*(void (__fastcall **)(__int64, struct _EVENT_DATA_DESCRIPTOR *))(*(_QWORD *)v9 + 48LL))(v9, &v14);
        v12 = v13;
        if ( v13 )
        {
          v13 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        }
      }
      else
      {
        if ( (unsigned int)dword_180014000 > 2 )
          tlgWriteTransfer_EventWriteTransfer((int)&dword_180014000, (int)&byte_18000FBCD, 0, 0, 2u, &v14);
        v11 = v13;
        if ( v13 )
        {
          v13 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        }
      }
      ++Ptr;
    }
    if ( v4 )
      ReleaseSRWLockExclusive(v4);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0x185, v5, v6);
  }
}

```

## disassembly

```asm
0x180009f00  mov     [rsp+arg_10], rbx
0x180009f05  push    rsi
0x180009f06  push    rdi
0x180009f07  push    r14
0x180009f09  sub     rsp, 90h
0x180009f10  mov     rax, cs:__security_cookie
0x180009f17  xor     rax, rsp
0x180009f1a  mov     [rsp+0A8h+var_28], rax
0x180009f22  mov     r14, rdx
0x180009f25  mov     rsi, rcx
0x180009f28  mov     [rsp+0A8h+var_60], rdx
0x180009f2d  lea     rbx, [rcx+48h]
0x180009f31  mov     rcx, rbx; SRWLock
0x180009f34  call    cs:__imp_AcquireSRWLockExclusive
0x180009f3a  mov     [rsp+0A8h+var_70], rbx
0x180009f3f  mov     rdi, [rsi+50h]
0x180009f43  mov     rsi, [rsi+58h]
0x180009f47  mov     [rsp+0A8h+var_68], rsi
0x180009f4c  mov     [rsp+0A8h+var_78], rdi
0x180009f51  cmp     rdi, rsi
0x180009f54  jz      loc_18000A045
0x180009f5a  xor     ecx, ecx
0x180009f5c  mov     [rsp+0A8h+var_58], rcx
0x180009f61  mov     r9, [rdi]
0x180009f64  test    r9, r9
0x180009f67  jnz     short loc_180009F6D
0x180009f69  xor     eax, eax
0x180009f6b  jmp     short loc_180009F8D
0x180009f6d  mov     rax, [r9]
0x180009f70  lea     r8, [rsp+0A8h+var_58]
0x180009f75  lea     rdx, _GUID_62b620b7_cedf_42b6_9cce_312fae152147
0x180009f7c  mov     rcx, r9
0x180009f7f  mov     rax, [rax+18h]
0x180009f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f88  mov     rcx, [rsp+0A8h+var_58]
0x180009f8d  test    eax, eax
0x180009f8f  jns     short loc_180009FEA
0x180009f91  mov     eax, cs:dword_180014000
0x180009f97  cmp     eax, 2
0x180009f9a  jbe     short loc_180009FC8
0x180009f9c  lea     rax, [rsp+0A8h+var_48]
0x180009fa1  mov     [rsp+0A8h+var_80], rax; PEVENT_DATA_DESCRIPTOR
0x180009fa6  mov     [rsp+0A8h+var_88], 2; ULONG
0x180009fae  xor     r9d, r9d; int
0x180009fb1  xor     r8d, r8d; int
0x180009fb4  lea     rdx, byte_18000FBCD; int
0x180009fbb  lea     rcx, dword_180014000; int
0x180009fc2  call    _tlgWriteTransfer_EventWriteTransfer
0x180009fc7  nop
0x180009fc8  mov     rcx, [rsp+0A8h+var_58]
0x180009fcd  test    rcx, rcx
0x180009fd0  jz      short loc_180009FE8
0x180009fd2  mov     [rsp+0A8h+var_58], 0
0x180009fdb  mov     rax, [rcx]
0x180009fde  mov     rax, [rax+10h]
0x180009fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fe7  nop
0x180009fe8  jmp     short loc_18000A026
0x180009fea  movups  xmm0, xmmword ptr [r14]
0x180009fee  movdqu  xmmword ptr [rsp+0A8h+var_48.Ptr], xmm0
0x180009ff4  mov     rax, [rcx]
0x180009ff7  lea     rdx, [rsp+0A8h+var_48]
0x180009ffc  mov     rax, [rax+30h]
0x18000a000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a005  nop
0x18000a006  mov     rcx, [rsp+0A8h+var_58]
0x18000a00b  test    rcx, rcx
0x18000a00e  jz      short loc_18000A026
0x18000a010  mov     [rsp+0A8h+var_58], 0
0x18000a019  mov     rax, [rcx]
0x18000a01c  mov     rax, [rax+10h]
0x18000a020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a025  nop
0x18000a026  jmp     short loc_18000A03C
0x18000a028  mov     rbx, [rsp+0A8h+var_70]
0x18000a02d  mov     rdi, [rsp+0A8h+var_78]
0x18000a032  mov     rsi, [rsp+0A8h+var_68]
0x18000a037  mov     r14, [rsp+0A8h+var_60]
0x18000a03c  add     rdi, 8
0x18000a040  jmp     loc_180009F4C
0x18000a045  test    rbx, rbx
0x18000a048  jz      short loc_18000A054
0x18000a04a  mov     rcx, rbx; SRWLock
0x18000a04d  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a053  nop
0x18000a054  mov     rcx, [rsp+0A8h+var_28]
0x18000a05c  xor     rcx, rsp; StackCookie
0x18000a05f  call    __security_check_cookie
0x18000a064  mov     rbx, [rsp+0A8h+arg_10]
0x18000a06c  add     rsp, 90h
0x18000a073  pop     r14
0x18000a075  pop     rdi
0x18000a076  pop     rsi
0x18000a077  retn
```
