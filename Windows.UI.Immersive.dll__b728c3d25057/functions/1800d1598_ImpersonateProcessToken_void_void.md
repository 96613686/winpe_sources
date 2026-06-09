# _ImpersonateProcessToken(void *,void * *)

- ea: `0x1800d1598`
- end: `0x1800d1682`
- name: `?_ImpersonateProcessToken@@YAJPEAXPEAPEAX@Z`
- size: `234`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800d1688`
- `0x1800d18a8`

## callees

- `0x18003aa84`
- `0x1800d1598`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d15d4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d15d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d15bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d15bd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800d1611`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800d1611`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d165a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d166a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d165a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d166a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800d162b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800d162b`

## pseudocode

```c
__int64 __fastcall _ImpersonateProcessToken(HANDLE ProcessHandle, void **a2)
{
  HANDLE CurrentThread; // rax
  int Error; // eax
  int v6; // ebx
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF
  HANDLE hToken; // [rsp+40h] [rbp+18h] BYREF

  *a2 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
  {
    Error = ResultFromKnownLastError();
    v6 = Error;
    if ( Error == -2147023888 )
    {
      TokenHandle = 0;
    }
    else if ( Error < 0 )
    {
      return (unsigned int)v6;
    }
  }
  hToken = 0;
  if ( OpenProcessToken(ProcessHandle, 0xEu, &hToken) || (v6 = ResultFromKnownLastError(), v6 >= 0) )
  {
    if ( ImpersonateLoggedOnUser(hToken) )
    {
      v6 = 0;
    }
    else
    {
      v6 = ResultFromKnownLastError();
      if ( v6 < 0 )
      {
LABEL_11:
        CloseHandle(hToken);
        goto LABEL_12;
      }
    }
    *a2 = TokenHandle;
    TokenHandle = 0;
    goto LABEL_11;
  }
LABEL_12:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800d1598  mov     [rsp+arg_0], rbx
0x1800d159d  mov     [rsp+arg_18], rsi
0x1800d15a2  push    rdi
0x1800d15a3  sub     rsp, 20h
0x1800d15a7  mov     rdi, rdx
0x1800d15aa  mov     qword ptr [rdx], 0
0x1800d15b1  mov     rsi, rcx
0x1800d15b4  mov     [rsp+28h+TokenHandle], 0
0x1800d15bd  call    cs:__imp_GetCurrentThread
0x1800d15c3  mov     edx, 0Eh; DesiredAccess
0x1800d15c8  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800d15cd  mov     rcx, rax; ThreadHandle
0x1800d15d0  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x1800d15d4  call    cs:__imp_OpenThreadToken
0x1800d15da  test    eax, eax
0x1800d15dc  jnz     short loc_1800D15FB
0x1800d15de  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d15e3  mov     ebx, eax
0x1800d15e5  cmp     eax, 800703F0h
0x1800d15ea  jnz     short loc_1800D15F7
0x1800d15ec  mov     [rsp+28h+TokenHandle], 0
0x1800d15f5  jmp     short loc_1800D15FB
0x1800d15f7  test    eax, eax
0x1800d15f9  js      short loc_1800D1670
0x1800d15fb  lea     r8, [rsp+28h+hToken]; TokenHandle
0x1800d1600  mov     [rsp+28h+hToken], 0
0x1800d1609  mov     edx, 0Eh; DesiredAccess
0x1800d160e  mov     rcx, rsi; ProcessHandle
0x1800d1611  call    cs:__imp_OpenProcessToken
0x1800d1617  test    eax, eax
0x1800d1619  jnz     short loc_1800D1626
0x1800d161b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d1620  mov     ebx, eax
0x1800d1622  test    eax, eax
0x1800d1624  js      short loc_1800D1660
0x1800d1626  mov     rcx, [rsp+28h+hToken]; hToken
0x1800d162b  call    cs:__imp_ImpersonateLoggedOnUser
0x1800d1631  test    eax, eax
0x1800d1633  jz      short loc_1800D1639
0x1800d1635  xor     ebx, ebx
0x1800d1637  jmp     short loc_1800D1644
0x1800d1639  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d163e  mov     ebx, eax
0x1800d1640  test    eax, eax
0x1800d1642  js      short loc_1800D1655
0x1800d1644  mov     rax, [rsp+28h+TokenHandle]
0x1800d1649  mov     [rdi], rax
0x1800d164c  mov     [rsp+28h+TokenHandle], 0
0x1800d1655  mov     rcx, [rsp+28h+hToken]; hObject
0x1800d165a  call    cs:__imp_CloseHandle
0x1800d1660  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x1800d1665  test    rcx, rcx
0x1800d1668  jz      short loc_1800D1670
0x1800d166a  call    cs:__imp_CloseHandle
0x1800d1670  mov     rsi, [rsp+28h+arg_18]
0x1800d1675  mov     eax, ebx
0x1800d1677  mov     rbx, [rsp+28h+arg_0]
0x1800d167c  add     rsp, 20h
0x1800d1680  pop     rdi
0x1800d1681  retn
```
