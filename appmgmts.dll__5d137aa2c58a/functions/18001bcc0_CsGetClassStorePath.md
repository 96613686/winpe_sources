# CsGetClassStorePath

- ea: `0x18001bcc0`
- end: `0x18001bd68`
- name: `CsGetClassStorePath`
- size: `168`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000ca60`
- `0x18000fe58`

## callees

- `0x18001b944`
- `0x18001bcc0`
- `0x180024458`
- `0x18002ad84`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bd50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bd50`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001bd10`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001bd10`

## pseudocode

```c
__int64 __fastcall CsGetClassStorePath(const wchar_t *a1, HLOCAL *a2)
{
  int v4; // ebx
  __int64 v5; // rax
  SIZE_T v6; // rsi
  unsigned __int16 *v7; // rax

  *a2 = 0;
  if ( a1 && !wcsncmp_0(a1, L"LDAP://", 7u) )
  {
    v5 = -1;
    do
      ++v5;
    while ( a1[v5] );
    v6 = (unsigned int)(2 * v5 + 32);
    v7 = (unsigned __int16 *)LocalAlloc(0, v6);
    *a2 = v7;
    if ( v7 )
    {
      v4 = StringCbPrintfW(v7, v6, L"%s%s", L"LDAP://CN=Class Store,", a1 + 7);
      if ( v4 < 0 )
      {
        LocalFree(*a2);
        *a2 = 0;
      }
    }
    else
    {
      v4 = -2147024882;
    }
  }
  else
  {
    v4 = -2147024809;
  }
  return RemapErrorCode(v4, (const unsigned __int16 *)a2);
}

```

## disassembly

```asm
0x18001bcc0  push    rbx
0x18001bcc2  push    rbp
0x18001bcc3  push    rsi
0x18001bcc4  push    rdi
0x18001bcc5  sub     rsp, 38h
0x18001bcc9  xor     ebp, ebp
0x18001bccb  mov     rdi, rdx
0x18001bcce  mov     [rdx], rbp
0x18001bcd1  mov     rbx, rcx
0x18001bcd4  test    rcx, rcx
0x18001bcd7  jnz     short loc_18001BCE0
0x18001bcd9  mov     ebx, 80070057h
0x18001bcde  jmp     short loc_18001BD59
0x18001bce0  mov     r8d, 7; MaxCount
0x18001bce6  lea     rdx, aLdap; "LDAP://"
0x18001bced  call    wcsncmp_0
0x18001bcf2  test    eax, eax
0x18001bcf4  jnz     short loc_18001BCD9
0x18001bcf6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001bcfa  inc     rax
0x18001bcfd  cmp     [rbx+rax*2], bp
0x18001bd01  jnz     short loc_18001BCFA
0x18001bd03  lea     eax, ds:20h[rax*2]
0x18001bd0a  xor     ecx, ecx; uFlags
0x18001bd0c  mov     edx, eax; uBytes
0x18001bd0e  mov     esi, eax
0x18001bd10  call    cs:__imp_LocalAlloc
0x18001bd16  mov     [rdi], rax
0x18001bd19  mov     rcx, rax; unsigned __int16 *
0x18001bd1c  test    rax, rax
0x18001bd1f  jnz     short loc_18001BD28
0x18001bd21  mov     ebx, 8007000Eh
0x18001bd26  jmp     short loc_18001BD59
0x18001bd28  lea     rax, [rbx+0Eh]
0x18001bd2c  mov     rdx, rsi; unsigned __int64
0x18001bd2f  lea     r9, aLdapCnClassSto; "LDAP://CN=Class Store,"
0x18001bd36  mov     [rsp+58h+var_38], rax
0x18001bd3b  lea     r8, aSS_2; "%s%s"
0x18001bd42  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001bd47  mov     ebx, eax
0x18001bd49  test    eax, eax
0x18001bd4b  jns     short loc_18001BD59
0x18001bd4d  mov     rcx, [rdi]; hMem
0x18001bd50  call    cs:__imp_LocalFree
0x18001bd56  mov     [rdi], rbp
0x18001bd59  mov     ecx, ebx; int
0x18001bd5b  add     rsp, 38h
0x18001bd5f  pop     rdi
0x18001bd60  pop     rsi
0x18001bd61  pop     rbp
0x18001bd62  pop     rbx
0x18001bd63  jmp     ?RemapErrorCode@@YAJJPEBG@Z; RemapErrorCode(long,ushort const *)
```
