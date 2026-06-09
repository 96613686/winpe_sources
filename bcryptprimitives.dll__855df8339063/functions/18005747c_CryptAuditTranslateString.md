# CryptAuditTranslateString

- ea: `0x18005747c`
- end: `0x1800574d9`
- name: `CryptAuditTranslateString`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800215e4`

## callees

- `0x18000ecb0`
- `0x180053d50`
- `0x18005747c`

## string_xrefs

- `0x1800574a8`: `onecore\ds\security\cryptoapi\ncrypt\common\audit.c`

## pseudocode

```c
__int64 __fastcall CryptAuditTranslateString(unsigned int a1, wchar_t *a2)
{
  HRESULT v2; // eax
  HRESULT v3; // ebx
  __int64 result; // rax

  v2 = StringCchPrintfW(a2, 0x10u, L"%%%%%d", a1);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  DebugTraceError((unsigned int)v2, "hr", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\audit.c", 56);
  result = 3221225507LL;
  if ( v3 != -2147024774 )
    return 3221225473LL;
  return result;
}

```

## disassembly

```asm
0x18005747c  push    rbx
0x18005747e  sub     rsp, 20h
0x180057482  mov     rax, rdx
0x180057485  lea     r8, aD; "%%%%%d"
0x18005748c  mov     r9d, ecx
0x18005748f  mov     edx, 10h; cchDest
0x180057494  mov     rcx, rax; pszDest
0x180057497  call    StringCchPrintfW
0x18005749c  mov     ebx, eax
0x18005749e  test    eax, eax
0x1800574a0  jns     short loc_1800574D0
0x1800574a2  mov     r9d, 38h ; '8'
0x1800574a8  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800574af  lea     rdx, aHr; "hr"
0x1800574b6  mov     ecx, eax
0x1800574b8  call    DebugTraceError
0x1800574bd  mov     eax, 0C0000023h
0x1800574c2  cmp     ebx, 8007007Ah
0x1800574c8  lea     ecx, [rax-22h]
0x1800574cb  cmovnz  eax, ecx
0x1800574ce  jmp     short loc_1800574D2
0x1800574d0  xor     eax, eax
0x1800574d2  add     rsp, 20h
0x1800574d6  pop     rbx
0x1800574d7  retn
```
