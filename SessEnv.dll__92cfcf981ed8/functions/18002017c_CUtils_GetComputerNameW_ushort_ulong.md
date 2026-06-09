# CUtils::GetComputerNameW(ushort *,ulong *)

- ea: `0x18002017c`
- end: `0x18002023f`
- name: `?GetComputerNameW@CUtils@@SAJPEAGPEAK@Z`
- size: `195`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18005acdc`

## callees

- `0x180003f30`
- `0x180004e00`
- `0x18002017c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800201ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800201ad`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800201a3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800201a3`

## string_xrefs

- `0x18002020b`: `CUtils::GetComputerNameW`
- `0x1800201cc`: `GetComputerName failed: 0x%x in %s`
- `0x180020204`: `StringCchCopy failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUtils::GetComputerNameW(unsigned __int16 *a1, unsigned int *a2)
{
  signed int LastError; // eax
  unsigned int v3; // ebx

  if ( dword_180084640 < 0 )
  {
    nSize = 16;
    if ( GetComputerNameW(&Buffer, &nSize) )
    {
      ++nSize;
      dword_180084640 = 0;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      dword_180084640 = v3;
      if ( (v3 & 0x80000000) != 0 )
      {
        _DbgPrintMessage(8, "GetComputerName failed: 0x%x in %s", v3, "CUtils::GetComputerNameW");
        goto LABEL_10;
      }
    }
  }
  v3 = StringCchCopyW(&word_180087DF8, (unsigned int)dword_180087E18, &Buffer);
  if ( (v3 & 0x80000000) == 0 )
  {
    LODWORD(dword_180087E18) = nSize;
    return v3;
  }
  _DbgPrintMessage(8, "StringCchCopy failed: 0x%x in %s", v3, "CUtils::GetComputerNameW");
LABEL_10:
  LODWORD(dword_180087E18) = 0;
  return v3;
}

```

## disassembly

```asm
0x18002017c  push    rbx
0x18002017e  sub     rsp, 20h
0x180020182  cmp     cs:dword_180084640, 0
0x180020189  jge     short loc_1800201E5
0x18002018b  lea     rdx, nSize; nSize
0x180020192  mov     cs:nSize, 10h
0x18002019c  lea     rcx, Buffer; lpBuffer
0x1800201a3  call    cs:__imp_GetComputerNameW
0x1800201a9  test    eax, eax
0x1800201ab  jnz     short loc_1800201D5
0x1800201ad  call    cs:__imp_GetLastError
0x1800201b3  mov     ebx, eax
0x1800201b5  test    eax, eax
0x1800201b7  jle     short loc_1800201C2
0x1800201b9  movzx   ebx, ax
0x1800201bc  or      ebx, 80070000h
0x1800201c2  mov     cs:dword_180084640, ebx
0x1800201c8  test    ebx, ebx
0x1800201ca  jns     short loc_1800201E5
0x1800201cc  lea     rdx, aGetcomputernam; "GetComputerName failed: 0x%x in %s"
0x1800201d3  jmp     short loc_18002020B
0x1800201d5  inc     cs:nSize
0x1800201db  mov     cs:dword_180084640, 0
0x1800201e5  mov     edx, cs:dword_180087E18; unsigned __int64
0x1800201eb  lea     r8, Buffer; unsigned __int16 *
0x1800201f2  lea     rcx, word_180087DF8; unsigned __int16 *
0x1800201f9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800201fe  mov     ebx, eax
0x180020200  test    eax, eax
0x180020202  jns     short loc_18002022B
0x180020204  lea     rdx, aStringcchcopyF_1; "StringCchCopy failed: 0x%x in %s"
0x18002020b  lea     r9, aCutilsGetcompu; "CUtils::GetComputerNameW"
0x180020212  mov     r8d, ebx
0x180020215  mov     ecx, 8; int
0x18002021a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002021f  mov     cs:dword_180087E18, 0
0x180020229  jmp     short loc_180020237
0x18002022b  mov     eax, cs:nSize
0x180020231  mov     cs:dword_180087E18, eax
0x180020237  mov     eax, ebx
0x180020239  add     rsp, 20h
0x18002023d  pop     rbx
0x18002023e  retn
```
