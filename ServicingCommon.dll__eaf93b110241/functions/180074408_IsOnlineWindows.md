# IsOnlineWindows

- ea: `0x180074408`
- end: `0x18007454d`
- name: `IsOnlineWindows`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180074040`

## callees

- `0x180022ef0`
- `0x1800293a0`
- `0x18004d3a0`
- `0x18004d850`
- `0x180074408`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180074499`
- `KERNEL32!GetLastError` at `0x180074499`
- `KERNEL32!GetWindowsDirectoryW` at `0x180074489`
- `KERNEL32!GetWindowsDirectoryW` at `0x180074489`
- `KERNEL32!lstrcmpiW` at `0x1800744e8`
- `KERNEL32!lstrcmpiW` at `0x1800744e8`

## pseudocode

```c
__int64 __fastcall IsOnlineWindows(__int64 a1, _DWORD *a2)
{
  LPCWSTR v2; // rdi
  signed int v4; // ebx
  const struct std::nothrow_t *v5; // rdx
  signed int LastError; // eax
  LPCWSTR lpString2; // [rsp+20h] [rbp-E0h] BYREF
  LPCWSTR lpString1; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-D0h] BYREF

  v2 = 0;
  lpString1 = 0;
  lpString2 = 0;
  if ( a2 )
  {
    *a2 = 0;
    v4 = SczAllocFromSz(&lpString1, a1);
    if ( v4 >= 0 )
    {
      v4 = SczEnsureBackslashTerminated(&lpString1);
      if ( v4 >= 0 )
      {
        if ( GetWindowsDirectoryW(Buffer, 0x104u) )
        {
          v4 = SczAllocFromSz(&lpString2, Buffer);
          if ( v4 < 0 || (v4 = SczEnsureBackslashTerminated(&lpString2), v4 < 0) )
          {
            v2 = lpString2;
          }
          else
          {
            v2 = lpString2;
            if ( !lstrcmpiW(lpString1, lpString2) )
              *a2 = 1;
            v4 = 0;
          }
        }
        else
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
    if ( lpString1 )
      operator delete((void *)(lpString1 - 4), v5);
    if ( v2 )
      operator delete((void *)(v2 - 4), v5);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180074408  mov     [rsp-8+arg_10], rbx
0x18007440d  push    rbp
0x18007440e  push    rsi
0x18007440f  push    rdi
0x180074410  lea     rbp, [rsp-150h]
0x180074418  sub     rsp, 250h
0x18007441f  mov     rax, cs:__security_cookie
0x180074426  xor     rax, rsp
0x180074429  mov     [rbp+160h+var_20], rax
0x180074430  xor     edi, edi
0x180074432  mov     [rsp+260h+lpString1], 0
0x18007443b  mov     [rsp+260h+lpString2], rdi
0x180074440  mov     rsi, rdx
0x180074443  test    rdx, rdx
0x180074446  jnz     short loc_180074452
0x180074448  mov     ebx, 80070057h
0x18007444d  jmp     loc_180074528
0x180074452  mov     [rdx], edi
0x180074454  mov     rdx, rcx
0x180074457  lea     rcx, [rsp+260h+lpString1]
0x18007445c  call    SczAllocFromSz
0x180074461  mov     ebx, eax
0x180074463  test    eax, eax
0x180074465  js      loc_180074507
0x18007446b  lea     rcx, [rsp+260h+lpString1]
0x180074470  call    SczEnsureBackslashTerminated
0x180074475  mov     ebx, eax
0x180074477  test    eax, eax
0x180074479  js      loc_180074507
0x18007447f  mov     edx, 104h; uSize
0x180074484  lea     rcx, [rsp+260h+Buffer]; lpBuffer
0x180074489  call    cs:__imp_GetWindowsDirectoryW
0x180074490  nop     dword ptr [rax+rax+00h]
0x180074495  test    eax, eax
0x180074497  jnz     short loc_1800744B6
0x180074499  call    cs:__imp_GetLastError
0x1800744a0  nop     dword ptr [rax+rax+00h]
0x1800744a5  mov     ebx, eax
0x1800744a7  test    eax, eax
0x1800744a9  jle     short loc_180074507
0x1800744ab  movzx   ebx, ax
0x1800744ae  or      ebx, 80070000h
0x1800744b4  jmp     short loc_180074507
0x1800744b6  lea     rdx, [rsp+260h+Buffer]
0x1800744bb  lea     rcx, [rsp+260h+lpString2]
0x1800744c0  call    SczAllocFromSz
0x1800744c5  mov     ebx, eax
0x1800744c7  test    eax, eax
0x1800744c9  js      short loc_180074502
0x1800744cb  lea     rcx, [rsp+260h+lpString2]
0x1800744d0  call    SczEnsureBackslashTerminated
0x1800744d5  mov     ebx, eax
0x1800744d7  test    eax, eax
0x1800744d9  js      short loc_180074502
0x1800744db  mov     rdi, [rsp+260h+lpString2]
0x1800744e0  mov     rcx, [rsp+260h+lpString1]; lpString1
0x1800744e5  mov     rdx, rdi; lpString2
0x1800744e8  call    cs:__imp_lstrcmpiW
0x1800744ef  nop     dword ptr [rax+rax+00h]
0x1800744f4  test    eax, eax
0x1800744f6  jnz     short loc_1800744FE
0x1800744f8  mov     dword ptr [rsi], 1
0x1800744fe  xor     ebx, ebx
0x180074500  jmp     short loc_180074507
0x180074502  mov     rdi, [rsp+260h+lpString2]
0x180074507  mov     rcx, [rsp+260h+lpString1]
0x18007450c  test    rcx, rcx
0x18007450f  jz      short loc_18007451A
0x180074511  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x180074515  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007451a  test    rdi, rdi
0x18007451d  jz      short loc_180074528
0x18007451f  lea     rcx, [rdi-8]; void *
0x180074523  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180074528  mov     eax, ebx
0x18007452a  mov     rcx, [rbp+160h+var_20]
0x180074531  xor     rcx, rsp; StackCookie
0x180074534  call    __security_check_cookie
0x180074539  mov     rbx, [rsp+260h+arg_10]
0x180074541  add     rsp, 250h
0x180074548  pop     rdi
0x180074549  pop     rsi
0x18007454a  pop     rbp
0x18007454b  retn
```
