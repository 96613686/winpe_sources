# ValidateSIDKeyID(uchar * const,ulong)

- ea: `0x180010cf8`
- end: `0x180010d53`
- name: `?ValidateSIDKeyID@@YAPEAU_SID_KEY_ID_HEADER@@QEAEK@Z`
- size: `91`
- prototype: `struct _SID_KEY_ID_HEADER *__fastcall(unsigned __int8 *const, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010980`
- `0x180017310`

## callees

- `0x180010cf8`
- `0x18001a450`

## string_xrefs

- `0x180010d34`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyutil.cxx`

## pseudocode

```c
struct _SID_KEY_ID_HEADER *__fastcall ValidateSIDKeyID(unsigned __int8 *const a1, unsigned int a2)
{
  if ( a1 && a2 >= 0x28 )
  {
    if ( *((_DWORD *)a1 + 1) == 1263748171
      && *(_DWORD *)a1 == 1
      && *((_DWORD *)a1 + 4) <= 0x1Fu
      && *((_DWORD *)a1 + 5) <= 0x1Fu
      && (*((_DWORD *)a1 + 2) & 0xFFFFFFFC) == 0 )
    {
      return (struct _SID_KEY_ID_HEADER *)a1;
    }
    SidKeyDebugTraceError(
      0x80090003,
      "NTE_BAD_KEY",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyutil.cxx",
      0x1ECu);
  }
  return 0;
}

```

## disassembly

```asm
0x180010cf8  sub     rsp, 28h
0x180010cfc  test    rcx, rcx
0x180010cff  jz      short loc_180010D4C
0x180010d01  cmp     edx, 28h ; '('
0x180010d04  jb      short loc_180010D4C
0x180010d06  cmp     dword ptr [rcx+4], 4B53444Bh
0x180010d0d  jnz     short loc_180010D2E
0x180010d0f  cmp     dword ptr [rcx], 1
0x180010d12  jnz     short loc_180010D2E
0x180010d14  cmp     dword ptr [rcx+10h], 1Fh
0x180010d18  ja      short loc_180010D2E
0x180010d1a  cmp     dword ptr [rcx+14h], 1Fh
0x180010d1e  ja      short loc_180010D2E
0x180010d20  test    dword ptr [rcx+8], 0FFFFFFFCh
0x180010d27  jnz     short loc_180010D2E
0x180010d29  mov     rax, rcx
0x180010d2c  jmp     short loc_180010D4E
0x180010d2e  mov     r9d, 1ECh; unsigned int
0x180010d34  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180010d3b  lea     rdx, aNteBadKey; "NTE_BAD_KEY"
0x180010d42  mov     ecx, 80090003h; unsigned int
0x180010d47  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180010d4c  xor     eax, eax
0x180010d4e  add     rsp, 28h
0x180010d52  retn
```
