# ImpersonationHelper::GetThreadImpersonationToken(void)

- ea: `0x18001b3c0`
- end: `0x18001b49b`
- name: `?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ`
- size: `219`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `18`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800617d0`
- `0x18006d100`
- `0x18022ee90`
- `0x18022f4d0`
- `0x18022ffa0`
- `0x180230600`
- `0x180232b40`
- `0x180239660`
- `0x180239c10`
- `0x18023a270`
- `0x18023c450`
- `0x18023ea50`
- `0x18023ef80`
- `0x18023fd60`
- `0x1802402c0`
- `0x180240850`
- `0x1802411f0`
- `0x180241780`

## callees

- `0x18001b3c0`
- `0x180047120`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001b454`
- `KERNEL32!SetLastError` at `0x18001b454`
- `KERNEL32!GetLastError` at `0x18001b441`
- `KERNEL32!GetLastError` at `0x18001b462`
- `KERNEL32!GetLastError` at `0x18001b441`
- `KERNEL32!GetLastError` at `0x18001b462`
- `KERNEL32!CloseHandle` at `0x18001b44c`
- `KERNEL32!CloseHandle` at `0x18001b44c`
- `KERNEL32!GetCurrentThread` at `0x18001b400`
- `KERNEL32!GetCurrentThread` at `0x18001b400`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001b419`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001b419`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void **__fastcall ImpersonationHelper::GetThreadImpersonationToken(void **a1)
{
  HANDLE CurrentThread; // rax
  BOOL v3; // r15d
  HANDLE v4; // rbp
  void *v5; // rdi
  DWORD LastError; // ebx
  unsigned int v7; // r8d
  const char *v8; // r9
  HANDLE TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  char v12; // [rsp+38h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *a1 = 0;
  TokenHandle = 0;
  v12 = 1;
  CurrentThread = GetCurrentThread();
  v3 = OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle);
  if ( v12 )
  {
    v4 = TokenHandle;
    v5 = *a1;
    if ( *a1 && v5 != (void *)-1LL )
    {
      LastError = GetLastError();
      CloseHandle(v5);
      SetLastError(LastError);
    }
    *a1 = v4;
  }
  if ( !v3 && GetLastError() != 1008 )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0xC, v7, v8);
  return a1;
}

```

## disassembly

```asm
0x18001b3c0  mov     [rsp+arg_8], rbx
0x18001b3c5  mov     [rsp+arg_10], rbp
0x18001b3ca  mov     [rsp+arg_18], rsi
0x18001b3cf  mov     [rsp+arg_0], rcx
0x18001b3d4  push    rdi
0x18001b3d5  push    r14
0x18001b3d7  push    r15
0x18001b3d9  sub     rsp, 40h
0x18001b3dd  mov     r14, rcx
0x18001b3e0  xor     eax, eax
0x18001b3e2  mov     [rsp+58h+var_38], eax
0x18001b3e6  mov     [rcx], rax
0x18001b3e9  mov     [rsp+58h+var_38], 1
0x18001b3f1  mov     [rsp+58h+var_30], rcx
0x18001b3f6  mov     [rsp+58h+TokenHandle], rax
0x18001b3fb  mov     [rsp+58h+var_20], 1
0x18001b400  call    cs:__imp_GetCurrentThread
0x18001b406  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x18001b40b  mov     edx, 0F01FFh; DesiredAccess
0x18001b410  mov     r8d, 1; OpenAsSelf
0x18001b416  mov     rcx, rax; ThreadHandle
0x18001b419  call    cs:__imp_OpenThreadToken
0x18001b41f  mov     r15d, eax
0x18001b422  cmp     [rsp+58h+var_20], 0
0x18001b427  jz      short loc_18001B45D
0x18001b429  mov     rbp, [rsp+58h+TokenHandle]
0x18001b42e  mov     rsi, [rsp+58h+var_30]
0x18001b433  mov     rdi, [rsi]
0x18001b436  test    rdi, rdi
0x18001b439  jz      short loc_18001B45A
0x18001b43b  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001b43f  jz      short loc_18001B45A
0x18001b441  call    cs:__imp_GetLastError
0x18001b447  mov     ebx, eax
0x18001b449  mov     rcx, rdi; hObject
0x18001b44c  call    cs:__imp_CloseHandle
0x18001b452  mov     ecx, ebx; dwErrCode
0x18001b454  call    cs:__imp_SetLastError
0x18001b45a  mov     [rsi], rbp
0x18001b45d  test    r15d, r15d
0x18001b460  jnz     short loc_18001B46F
0x18001b462  call    cs:__imp_GetLastError
0x18001b468  cmp     eax, 3F0h
0x18001b46d  jnz     short loc_18001B48B
0x18001b46f  mov     rax, r14
0x18001b472  mov     rbx, [rsp+58h+arg_8]
0x18001b477  mov     rbp, [rsp+58h+arg_10]
0x18001b47c  mov     rsi, [rsp+58h+arg_18]
0x18001b481  add     rsp, 40h
0x18001b485  pop     r15
0x18001b487  pop     r14
0x18001b489  pop     rdi
0x18001b48a  retn
0x18001b48b  mov     rcx, [rsp+58h]; this
0x18001b490  mov     edx, 0Ch; void *
0x18001b495  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
