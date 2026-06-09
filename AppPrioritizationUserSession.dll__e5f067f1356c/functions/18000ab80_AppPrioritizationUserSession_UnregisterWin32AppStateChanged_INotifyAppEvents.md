# AppPrioritizationUserSession::UnregisterWin32AppStateChanged(INotifyAppEvents *)

- ea: `0x18000ab80`
- end: `0x18000acec`
- name: `?UnregisterWin32AppStateChanged@AppPrioritizationUserSession@@UEAAJPEAUINotifyAppEvents@@@Z`
- size: `364`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, struct INotifyAppEvents *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800088e8`
- `0x18000ad00`

## callees

- `0x180002650`
- `0x1800078a8`
- `0x18000ab08`
- `0x18000ab80`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000abaf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000abaf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000acbb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000acbb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ac90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ac90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac7d`
- `USER32!UnhookWinEvent` at `0x18000ac88`
- `USER32!UnhookWinEvent` at `0x18000ac88`

## pseudocode

```c
__int64 __fastcall AppPrioritizationUserSession::UnregisterWin32AppStateChanged(
        RTL_SRWLOCK *this,
        struct INotifyAppEvents *a2)
{
  RTL_SRWLOCK *v3; // rbx
  AppPrioritizationUserSession *v4; // rcx
  unsigned int v5; // r8d
  const char *v6; // r9
  _QWORD *Ptr; // r14
  _QWORD *v8; // rdi
  _BYTE *v10; // r15
  char v11; // r12
  char *i; // r14
  __int64 v13; // rax
  __int64 v14; // rcx
  _QWORD *v15; // rax
  RTL_SRWLOCK *v16; // rsi
  RTL_SRWLOCK *v17; // r14
  HWINEVENTHOOK v18; // r15
  DWORD LastError; // edi
  __int64 result; // rax
  char v21; // [rsp+20h] [rbp-48h] BYREF
  struct INotifyAppEvents **v22; // [rsp+28h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  struct INotifyAppEvents *v24; // [rsp+78h] [rbp+10h] BYREF

  v24 = a2;
  v3 = this + 9;
  AcquireSRWLockExclusive(this + 9);
  Ptr = this[11].Ptr;
  v8 = this[10].Ptr;
  v22 = &v24;
  while ( v8 != Ptr )
  {
    if ( (unsigned __int8)AppPrioritizationUserSession::UnregisterWin32AppStateChanged_::_3_::_lambda_1_::operator()_Microsoft::WRL::AgileRef_(
                            &v22,
                            v8) )
      break;
    ++v8;
  }
  try
  {
    v10 = this[11].Ptr;
    if ( v8 == (_QWORD *)v10 )
    {
      v11 = 0;
    }
    else
    {
      v11 = 1;
      for ( i = (char *)(v8 + 1); i != v10; i += 8 )
      {
        v13 = 0;
        if ( &v21 != i )
        {
          v13 = *(_QWORD *)i;
          *(_QWORD *)i = 0;
        }
        v14 = *v8;
        *v8 = v13;
        if ( v14 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        ++v8;
      }
      v15 = this[11].Ptr;
      v4 = (AppPrioritizationUserSession *)*(v15 - 1);
      if ( v4 )
      {
        *(v15 - 1) = 0;
        (*(void (__fastcall **)(AppPrioritizationUserSession *))(*(_QWORD *)v4 + 16LL))(v4);
      }
      this[11].Ptr = (char *)this[11].Ptr - 8;
      v10 = this[11].Ptr;
    }
    if ( this[10].Ptr == v10 )
    {
      AppPrioritizationUserSession::StopWin32MessageLoopAsync(v4);
      v16 = this + 4;
      v17 = v16 + 5;
      while ( v16 != v17 )
      {
        v18 = (HWINEVENTHOOK)v16->Ptr;
        if ( v16->Ptr )
        {
          LastError = GetLastError();
          UnhookWinEvent(v18);
          SetLastError(LastError);
        }
        v16->Ptr = 0;
        ++v16;
      }
    }
    if ( v3 )
      ReleaseSRWLockExclusive(v3);
    result = v11 == 0 ? 0x80070057 : 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0xF4, v5, v6);
  }
  return result;
}

```

## disassembly

```asm
0x18000ab80  mov     [rsp+arg_10], rbx
0x18000ab85  mov     [rsp+arg_8], rdx
0x18000ab8a  push    rsi
0x18000ab8b  push    rdi
0x18000ab8c  push    r12
0x18000ab8e  push    r14
0x18000ab90  push    r15
0x18000ab92  sub     rsp, 40h
0x18000ab96  mov     rax, cs:__security_cookie
0x18000ab9d  xor     rax, rsp
0x18000aba0  mov     [rsp+68h+var_38], rax
0x18000aba5  mov     rsi, rcx
0x18000aba8  lea     rbx, [rcx+48h]
0x18000abac  mov     rcx, rbx; SRWLock
0x18000abaf  call    cs:__imp_AcquireSRWLockExclusive
0x18000abb5  mov     r14, [rsi+58h]
0x18000abb9  mov     rdi, [rsi+50h]
0x18000abbd  lea     rax, [rsp+68h+arg_8]
0x18000abc2  mov     [rsp+68h+var_40], rax
0x18000abc7  jmp     short loc_18000ABDE
0x18000abc9  mov     rdx, rdi
0x18000abcc  lea     rcx, [rsp+68h+var_40]
0x18000abd1  call    _AppPrioritizationUserSession__UnregisterWin32AppStateChanged____3____lambda_1___operator___Microsoft__WRL__AgileRef_
0x18000abd6  test    al, al
0x18000abd8  jnz     short loc_18000ABE3
0x18000abda  add     rdi, 8
0x18000abde  cmp     rdi, r14
0x18000abe1  jnz     short loc_18000ABC9
0x18000abe3  mov     r15, [rsi+58h]
0x18000abe7  cmp     rdi, r15
0x18000abea  jnz     short loc_18000ABF1
0x18000abec  xor     r12d, r12d
0x18000abef  jmp     short loc_18000AC60
0x18000abf1  mov     r12b, 1
0x18000abf4  lea     r14, [rdi+8]
0x18000abf8  jmp     short loc_18000AC30
0x18000abfa  xor     eax, eax
0x18000abfc  lea     rcx, [rsp+68h+var_48]
0x18000ac01  cmp     rcx, r14
0x18000ac04  jz      short loc_18000AC10
0x18000ac06  mov     rax, [r14]
0x18000ac09  mov     qword ptr [r14], 0
0x18000ac10  mov     rcx, [rdi]
0x18000ac13  mov     [rdi], rax
0x18000ac16  test    rcx, rcx
0x18000ac19  jz      short loc_18000AC28
0x18000ac1b  mov     rax, [rcx]
0x18000ac1e  mov     rax, [rax+10h]
0x18000ac22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac27  nop
0x18000ac28  add     rdi, 8
0x18000ac2c  add     r14, 8
0x18000ac30  cmp     r14, r15
0x18000ac33  jnz     short loc_18000ABFA
0x18000ac35  mov     rax, [rsi+58h]
0x18000ac39  mov     rcx, [rax-8]
0x18000ac3d  test    rcx, rcx
0x18000ac40  jz      short loc_18000AC57
0x18000ac42  mov     qword ptr [rax-8], 0
0x18000ac4a  mov     rax, [rcx]
0x18000ac4d  mov     rax, [rax+10h]
0x18000ac51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac56  nop
0x18000ac57  add     qword ptr [rsi+58h], 0FFFFFFFFFFFFFFF8h
0x18000ac5c  mov     r15, [rsi+58h]
0x18000ac60  cmp     [rsi+50h], r15
0x18000ac64  jnz     short loc_18000ACA6
0x18000ac66  call    ?StopWin32MessageLoopAsync@AppPrioritizationUserSession@@AEAAXXZ; AppPrioritizationUserSession::StopWin32MessageLoopAsync(void)
0x18000ac6b  add     rsi, 20h ; ' '
0x18000ac6f  lea     r14, [rsi+28h]
0x18000ac73  jmp     short loc_18000ACA1
0x18000ac75  mov     r15, [rsi]
0x18000ac78  test    r15, r15
0x18000ac7b  jz      short loc_18000AC96
0x18000ac7d  call    cs:__imp_GetLastError
0x18000ac83  mov     edi, eax
0x18000ac85  mov     rcx, r15; hWinEventHook
0x18000ac88  call    cs:__imp_UnhookWinEvent
0x18000ac8e  mov     ecx, edi; dwErrCode
0x18000ac90  call    cs:__imp_SetLastError
0x18000ac96  mov     qword ptr [rsi], 0
0x18000ac9d  add     rsi, 8
0x18000aca1  cmp     rsi, r14
0x18000aca4  jnz     short loc_18000AC75
0x18000aca6  neg     r12b
0x18000aca9  sbb     edi, edi
0x18000acab  not     edi
0x18000acad  and     edi, 80070057h
0x18000acb3  test    rbx, rbx
0x18000acb6  jz      short loc_18000ACC1
0x18000acb8  mov     rcx, rbx; SRWLock
0x18000acbb  call    cs:__imp_ReleaseSRWLockExclusive
0x18000acc1  mov     eax, edi
0x18000acc3  jmp     short loc_18000ACC9
0x18000acc5  mov     eax, dword ptr [rsp+68h+var_40]
0x18000acc9  mov     rcx, [rsp+68h+var_38]
0x18000acce  xor     rcx, rsp; StackCookie
0x18000acd1  call    __security_check_cookie
0x18000acd6  mov     rbx, [rsp+68h+arg_10]
0x18000acde  add     rsp, 40h
0x18000ace2  pop     r15
0x18000ace4  pop     r14
0x18000ace6  pop     r12
0x18000ace8  pop     rdi
0x18000ace9  pop     rsi
0x18000acea  retn
```
