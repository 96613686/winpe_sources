# AnsiStringToUnicodeString

- ea: `0x18002bc50`
- end: `0x18002bcef`
- name: `AnsiStringToUnicodeString`
- size: `159`
- prototype: `WCHAR *__fastcall(LPCCH lpMultiByteStr)`
- caller_count: `30`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b4f0`
- `0x18000b960`
- `0x180010650`
- `0x180010b20`
- `0x180010f80`
- `0x180011640`
- `0x180011b60`
- `0x180012260`
- `0x180012760`
- `0x180012e20`
- `0x1800133d0`
- `0x180013d30`
- `0x180014fb0`
- `0x180016424`
- `0x1800190d0`
- `0x18001e590`
- `0x18001f640`
- `0x1800206d0`
- `0x1800216f0`
- `0x180022fb0`
- `0x180023c20`
- `0x180024030`
- `0x180024300`
- `0x180024520`
- `0x180024b00`
- `0x1800251c0`
- `0x1800259ec`
- `0x180029bd0`
- `0x18002a070`
- `0x18002a2d0`

## callees

- `0x18002bab8`
- `0x18002bb58`
- `0x18002bc50`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x18002bc84`
- `KERNEL32!MultiByteToWideChar` at `0x18002bcbf`
- `KERNEL32!MultiByteToWideChar` at `0x18002bc84`
- `KERNEL32!MultiByteToWideChar` at `0x18002bcbf`

## pseudocode

```c
WCHAR *__fastcall AnsiStringToUnicodeString(LPCCH lpMultiByteStr)
{
  int v2; // eax
  int cchWideChar; // esi
  WCHAR *lpWideCharStr; // rax
  WCHAR *v5; // rbx

  if ( !lpMultiByteStr )
    return 0;
  v2 = MultiByteToWideChar(0, 9u, lpMultiByteStr, -1, 0, 0);
  if ( !v2 )
    return 0;
  cchWideChar = v2 + 1;
  lpWideCharStr = (WCHAR *)pMemAlloc(2LL * (unsigned int)(v2 + 1));
  v5 = lpWideCharStr;
  if ( !lpWideCharStr )
    return 0;
  if ( !MultiByteToWideChar(0, 9u, lpMultiByteStr, -1, lpWideCharStr, cchWideChar) )
  {
    pMemFree(v5);
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x18002bc50  mov     rax, rsp
0x18002bc53  mov     [rax+8], rbx
0x18002bc57  mov     [rax+10h], rsi
0x18002bc5b  push    rdi
0x18002bc5c  sub     rsp, 30h
0x18002bc60  mov     rdi, rcx
0x18002bc63  test    rcx, rcx
0x18002bc66  jz      short loc_18002BCD7
0x18002bc68  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18002bc6c  mov     dword ptr [rax-10h], 0
0x18002bc73  mov     r8, rcx; lpMultiByteStr
0x18002bc76  mov     qword ptr [rax-18h], 0
0x18002bc7e  xor     ecx, ecx; CodePage
0x18002bc80  lea     edx, [r9+0Ah]; dwFlags
0x18002bc84  call    cs:__imp_MultiByteToWideChar
0x18002bc8b  nop     dword ptr [rax+rax+00h]
0x18002bc90  test    eax, eax
0x18002bc92  jz      short loc_18002BCD7
0x18002bc94  lea     esi, [rax+1]
0x18002bc97  mov     ecx, esi
0x18002bc99  add     rcx, rcx; dwBytes
0x18002bc9c  call    pMemAlloc
0x18002bca1  mov     rbx, rax
0x18002bca4  test    rax, rax
0x18002bca7  jz      short loc_18002BCD7
0x18002bca9  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18002bcad  mov     [rsp+38h+cchWideChar], esi; cchWideChar
0x18002bcb1  mov     r8, rdi; lpMultiByteStr
0x18002bcb4  mov     [rsp+38h+lpWideCharStr], rax; lpWideCharStr
0x18002bcb9  xor     ecx, ecx; CodePage
0x18002bcbb  lea     edx, [r9+0Ah]; dwFlags
0x18002bcbf  call    cs:__imp_MultiByteToWideChar
0x18002bcc6  nop     dword ptr [rax+rax+00h]
0x18002bccb  test    eax, eax
0x18002bccd  jnz     short loc_18002BCEA
0x18002bccf  mov     rcx, rbx; lpMem
0x18002bcd2  call    pMemFree
0x18002bcd7  xor     eax, eax
0x18002bcd9  mov     rbx, [rsp+38h+arg_0]
0x18002bcde  mov     rsi, [rsp+38h+arg_8]
0x18002bce3  add     rsp, 30h
0x18002bce7  pop     rdi
0x18002bce8  retn
0x18002bcea  mov     rax, rbx
0x18002bced  jmp     short loc_18002BCD9
```
