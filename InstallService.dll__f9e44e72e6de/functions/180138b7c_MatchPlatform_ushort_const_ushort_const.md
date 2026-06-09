# MatchPlatform(ushort const *,ushort const *)

- ea: `0x180138b7c`
- end: `0x180138cd6`
- name: `?MatchPlatform@@YA_NPEBG0@Z`
- size: `346`
- prototype: `bool __fastcall(LPCWCH lpString1, LPCWCH)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180138348`
- `0x180138ae8`

## callees

- `0x180138b7c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180138ba2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180138bc4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180138be6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180138c04`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180138c22`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180138c40`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180138c5e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180138c7c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180138c9a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180138cb8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180138ba2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180138bc4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180138be6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180138c04`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180138c22`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180138c40`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180138c5e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180138c7c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180138c9a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180138cb8`

## pseudocode

```c
bool __fastcall MatchPlatform(LPCWCH lpString1, LPCWCH a2)
{
  if ( CompareStringOrdinal(a2, -1, lpString1, -1, 1) == 2
    || CompareStringOrdinal(a2, -1, L"Windows.Universal", -1, 1) == 2
    || (CompareStringOrdinal(lpString1, -1, L"Windows.8828080", -1, 1) == 2
     || CompareStringOrdinal(lpString1, -1, L"Windows.Core", -1, 1) == 2)
    && CompareStringOrdinal(a2, -1, L"Windows.WindowsPhone8x", -1, 1) != 2
    && CompareStringOrdinal(a2, -1, L"Windows.Windows8x", -1, 1) != 2
    || CompareStringOrdinal(lpString1, -1, L"Windows.Mobile", -1, 1) == 2
    && CompareStringOrdinal(a2, -1, L"Windows.WindowsPhone8x", -1, 1) == 2 )
  {
    return 1;
  }
  if ( CompareStringOrdinal(lpString1, -1, L"Windows.Desktop", -1, 1) == 2 )
    return CompareStringOrdinal(a2, -1, L"Windows.Windows8x", -1, 1) == 2;
  return 0;
}

```

## disassembly

```asm
0x180138b7c  push    rbx
0x180138b7e  push    rbp
0x180138b7f  push    rsi
0x180138b80  push    rdi
0x180138b81  sub     rsp, 38h
0x180138b85  mov     rbx, rdx
0x180138b88  or      esi, 0FFFFFFFFh
0x180138b8b  mov     rdi, rcx
0x180138b8e  mov     r8, rcx; lpString2
0x180138b91  mov     ebp, 1
0x180138b96  mov     r9d, esi; cchCount2
0x180138b99  mov     edx, esi; cchCount1
0x180138b9b  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x180138b9f  mov     rcx, rbx; lpString1
0x180138ba2  call    cs:__imp_CompareStringOrdinal
0x180138ba8  cmp     eax, 2
0x180138bab  jz      loc_180138CCA
0x180138bb1  mov     r9d, esi; cchCount2
0x180138bb4  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x180138bb8  lea     r8, aWindowsUnivers; "Windows.Universal"
0x180138bbf  mov     edx, esi; cchCount1
0x180138bc1  mov     rcx, rbx; lpString1
0x180138bc4  call    cs:__imp_CompareStringOrdinal
0x180138bca  cmp     eax, 2
0x180138bcd  jz      loc_180138CCA
0x180138bd3  mov     r9d, esi; cchCount2
0x180138bd6  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x180138bda  lea     r8, aWindows8828080; "Windows.8828080"
0x180138be1  mov     edx, esi; cchCount1
0x180138be3  mov     rcx, rdi; lpString1
0x180138be6  call    cs:__imp_CompareStringOrdinal
0x180138bec  cmp     eax, 2
0x180138bef  jz      short loc_180138C0F
0x180138bf1  mov     r9d, esi; cchCount2
0x180138bf4  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x180138bf8  lea     r8, aWindowsCore; "Windows.Core"
0x180138bff  mov     edx, esi; cchCount1
0x180138c01  mov     rcx, rdi; lpString1
0x180138c04  call    cs:__imp_CompareStringOrdinal
0x180138c0a  cmp     eax, 2
0x180138c0d  jnz     short loc_180138C4B
0x180138c0f  mov     r9d, esi; cchCount2
0x180138c12  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x180138c16  lea     r8, aWindowsWindows_0; "Windows.WindowsPhone8x"
0x180138c1d  mov     edx, esi; cchCount1
0x180138c1f  mov     rcx, rbx; lpString1
0x180138c22  call    cs:__imp_CompareStringOrdinal
0x180138c28  cmp     eax, 2
0x180138c2b  jz      short loc_180138C4B
0x180138c2d  mov     r9d, esi; cchCount2
0x180138c30  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x180138c34  lea     r8, aWindowsWindows; "Windows.Windows8x"
0x180138c3b  mov     edx, esi; cchCount1
0x180138c3d  mov     rcx, rbx; lpString1
0x180138c40  call    cs:__imp_CompareStringOrdinal
0x180138c46  cmp     eax, 2
0x180138c49  jnz     short loc_180138CCA
0x180138c4b  mov     r9d, esi; cchCount2
0x180138c4e  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x180138c52  lea     r8, aWindowsMobile; "Windows.Mobile"
0x180138c59  mov     edx, esi; cchCount1
0x180138c5b  mov     rcx, rdi; lpString1
0x180138c5e  call    cs:__imp_CompareStringOrdinal
0x180138c64  cmp     eax, 2
0x180138c67  jnz     short loc_180138C87
0x180138c69  mov     r9d, esi; cchCount2
0x180138c6c  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x180138c70  lea     r8, aWindowsWindows_0; "Windows.WindowsPhone8x"
0x180138c77  mov     edx, esi; cchCount1
0x180138c79  mov     rcx, rbx; lpString1
0x180138c7c  call    cs:__imp_CompareStringOrdinal
0x180138c82  cmp     eax, 2
0x180138c85  jz      short loc_180138CCA
0x180138c87  mov     r9d, esi; cchCount2
0x180138c8a  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x180138c8e  lea     r8, aWindowsDesktop; "Windows.Desktop"
0x180138c95  mov     edx, esi; cchCount1
0x180138c97  mov     rcx, rdi; lpString1
0x180138c9a  call    cs:__imp_CompareStringOrdinal
0x180138ca0  cmp     eax, 2
0x180138ca3  jnz     short loc_180138CC6
0x180138ca5  mov     r9d, esi; cchCount2
0x180138ca8  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x180138cac  lea     r8, aWindowsWindows; "Windows.Windows8x"
0x180138cb3  mov     edx, esi; cchCount1
0x180138cb5  mov     rcx, rbx; lpString1
0x180138cb8  call    cs:__imp_CompareStringOrdinal
0x180138cbe  cmp     eax, 2
0x180138cc1  setz    al
0x180138cc4  jmp     short loc_180138CCD
0x180138cc6  xor     al, al
0x180138cc8  jmp     short loc_180138CCD
0x180138cca  mov     al, bpl
0x180138ccd  add     rsp, 38h
0x180138cd1  pop     rdi
0x180138cd2  pop     rsi
0x180138cd3  pop     rbp
0x180138cd4  pop     rbx
0x180138cd5  retn
```
