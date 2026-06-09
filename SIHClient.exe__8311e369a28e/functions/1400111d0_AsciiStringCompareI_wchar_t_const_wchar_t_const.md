# AsciiStringCompareI(wchar_t const *,wchar_t const *)

- ea: `0x1400111d0`
- end: `0x140011287`
- name: `?AsciiStringCompareI@@YAJPEB_W0@Z`
- size: `183`
- prototype: `int __fastcall(PCNZWCH lpString1, PCNZWCH lpString2, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14003af00`

## callees

- `0x140008de4`
- `0x140008e08`
- `0x14000e4d0`
- `0x1400111d0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140011223`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140011223`

## pseudocode

```c
int __fastcall AsciiStringCompareI(PCNZWCH lpString1, PCNZWCH lpString2, __int64 a3, __int64 a4, unsigned int a5)
{
  __int64 v5; // rdx
  int v7; // eax
  const char *v8; // r9
  int v9; // eax
  int v10; // eax
  int lpString2a; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !lpString1 )
  {
    v5 = 162;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\StringUtil.cpp",
      (const char *)0x80070057LL,
      lpString2a);
    return -2147024809;
  }
  if ( !lpString2 )
  {
    v5 = 163;
    goto LABEL_3;
  }
  v7 = CompareStringW(0x7Fu, 1u, lpString1, -1, lpString2, -1);
  if ( !v7 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xAA,
             (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\StringUtil.cpp",
             v8);
  v9 = v7 - 1;
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( !v10 )
      return 0;
    if ( v10 != 1 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xB1,
               (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\StringUtil.cpp",
               (const char *)0xD,
               a5);
  }
  return 1;
}

```

## disassembly

```asm
0x1400111d0  sub     rsp, 38h
0x1400111d4  test    rcx, rcx
0x1400111d7  jnz     short loc_1400111FF
0x1400111d9  mov     edx, 0A2h; void *
0x1400111de  mov     rcx, [rsp+38h]; this
0x1400111e3  lea     r8, aCW1SSrcClientL_4; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1400111ea  mov     r9d, 80070057h; char *
0x1400111f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400111f5  mov     eax, 80070057h
0x1400111fa  add     rsp, 38h
0x1400111fe  retn
0x1400111ff  test    rdx, rdx
0x140011202  jnz     short loc_14001120B
0x140011204  mov     edx, 0A3h
0x140011209  jmp     short loc_1400111DE
0x14001120b  or      r9d, 0FFFFFFFFh; cchCount1
0x14001120f  mov     r8, rcx; lpString1
0x140011212  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x140011217  mov     [rsp+38h+lpString2], rdx; lpString2
0x14001121c  lea     edx, [r9+2]; dwCmpFlags
0x140011220  lea     ecx, [rdx+7Eh]; Locale
0x140011223  call    cs:__imp_CompareStringW
0x140011229  test    eax, eax
0x14001122b  jz      short loc_14001126D
0x14001122d  sub     eax, 1
0x140011230  jz      short loc_140011263
0x140011232  sub     eax, 1
0x140011235  jz      short loc_14001125C
0x140011237  cmp     eax, 1
0x14001123a  jz      short loc_140011263
0x14001123c  mov     rcx, [rsp+38h]; this
0x140011241  lea     r8, aCW1SSrcClientL_4; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140011248  mov     r9d, 0Dh; char *
0x14001124e  mov     edx, 0B1h; void *
0x140011253  add     rsp, 38h
0x140011257  jmp     ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14001125c  xor     eax, eax
0x14001125e  add     rsp, 38h
0x140011262  retn
0x140011263  mov     eax, 1
0x140011268  add     rsp, 38h
0x14001126c  retn
0x14001126d  mov     rcx, [rsp+38h]; this
0x140011272  lea     r8, aCW1SSrcClientL_4; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140011279  mov     edx, 0AAh; void *
0x14001127e  add     rsp, 38h
0x140011282  jmp     ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
```
