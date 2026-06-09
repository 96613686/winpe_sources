# IsOnlineWindows

- ea: `0x1800741a8`
- end: `0x1800742ed`
- name: `IsOnlineWindows`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180073de0`

## callees

- `0x180026e00`
- `0x18002d2b0`
- `0x1800504d0`
- `0x180050980`
- `0x1800741a8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180074239`
- `KERNEL32!GetLastError` at `0x180074239`
- `KERNEL32!GetWindowsDirectoryW` at `0x180074229`
- `KERNEL32!GetWindowsDirectoryW` at `0x180074229`
- `KERNEL32!lstrcmpiW` at `0x180074288`
- `KERNEL32!lstrcmpiW` at `0x180074288`

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
0x1800741a8  mov     [rsp-8+arg_10], rbx
0x1800741ad  push    rbp
0x1800741ae  push    rsi
0x1800741af  push    rdi
0x1800741b0  lea     rbp, [rsp-150h]
0x1800741b8  sub     rsp, 250h
0x1800741bf  mov     rax, cs:__security_cookie
0x1800741c6  xor     rax, rsp
0x1800741c9  mov     [rbp+160h+var_20], rax
0x1800741d0  xor     edi, edi
0x1800741d2  mov     [rsp+260h+lpString1], 0
0x1800741db  mov     [rsp+260h+lpString2], rdi
0x1800741e0  mov     rsi, rdx
0x1800741e3  test    rdx, rdx
0x1800741e6  jnz     short loc_1800741F2
0x1800741e8  mov     ebx, 80070057h
0x1800741ed  jmp     loc_1800742C8
0x1800741f2  mov     [rdx], edi
0x1800741f4  mov     rdx, rcx
0x1800741f7  lea     rcx, [rsp+260h+lpString1]
0x1800741fc  call    SczAllocFromSz
0x180074201  mov     ebx, eax
0x180074203  test    eax, eax
0x180074205  js      loc_1800742A7
0x18007420b  lea     rcx, [rsp+260h+lpString1]
0x180074210  call    SczEnsureBackslashTerminated
0x180074215  mov     ebx, eax
0x180074217  test    eax, eax
0x180074219  js      loc_1800742A7
0x18007421f  mov     edx, 104h; uSize
0x180074224  lea     rcx, [rsp+260h+Buffer]; lpBuffer
0x180074229  call    cs:__imp_GetWindowsDirectoryW
0x180074230  nop     dword ptr [rax+rax+00h]
0x180074235  test    eax, eax
0x180074237  jnz     short loc_180074256
0x180074239  call    cs:__imp_GetLastError
0x180074240  nop     dword ptr [rax+rax+00h]
0x180074245  mov     ebx, eax
0x180074247  test    eax, eax
0x180074249  jle     short loc_1800742A7
0x18007424b  movzx   ebx, ax
0x18007424e  or      ebx, 80070000h
0x180074254  jmp     short loc_1800742A7
0x180074256  lea     rdx, [rsp+260h+Buffer]
0x18007425b  lea     rcx, [rsp+260h+lpString2]
0x180074260  call    SczAllocFromSz
0x180074265  mov     ebx, eax
0x180074267  test    eax, eax
0x180074269  js      short loc_1800742A2
0x18007426b  lea     rcx, [rsp+260h+lpString2]
0x180074270  call    SczEnsureBackslashTerminated
0x180074275  mov     ebx, eax
0x180074277  test    eax, eax
0x180074279  js      short loc_1800742A2
0x18007427b  mov     rdi, [rsp+260h+lpString2]
0x180074280  mov     rcx, [rsp+260h+lpString1]; lpString1
0x180074285  mov     rdx, rdi; lpString2
0x180074288  call    cs:__imp_lstrcmpiW
0x18007428f  nop     dword ptr [rax+rax+00h]
0x180074294  test    eax, eax
0x180074296  jnz     short loc_18007429E
0x180074298  mov     dword ptr [rsi], 1
0x18007429e  xor     ebx, ebx
0x1800742a0  jmp     short loc_1800742A7
0x1800742a2  mov     rdi, [rsp+260h+lpString2]
0x1800742a7  mov     rcx, [rsp+260h+lpString1]
0x1800742ac  test    rcx, rcx
0x1800742af  jz      short loc_1800742BA
0x1800742b1  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x1800742b5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800742ba  test    rdi, rdi
0x1800742bd  jz      short loc_1800742C8
0x1800742bf  lea     rcx, [rdi-8]; void *
0x1800742c3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800742c8  mov     eax, ebx
0x1800742ca  mov     rcx, [rbp+160h+var_20]
0x1800742d1  xor     rcx, rsp; StackCookie
0x1800742d4  call    __security_check_cookie
0x1800742d9  mov     rbx, [rsp+260h+arg_10]
0x1800742e1  add     rsp, 250h
0x1800742e8  pop     rdi
0x1800742e9  pop     rsi
0x1800742ea  pop     rbp
0x1800742eb  retn
```
