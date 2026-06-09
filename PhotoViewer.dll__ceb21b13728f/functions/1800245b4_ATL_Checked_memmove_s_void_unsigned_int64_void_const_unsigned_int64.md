# ATL::Checked::memmove_s(void *,unsigned __int64,void const *,unsigned __int64)

- ea: `0x1800245b4`
- end: `0x1800245ff`
- name: `?memmove_s@Checked@ATL@@YAXPEAX_KPEBX1@Z`
- size: `75`
- prototype: `void __fastcall(ATL::Checked *__hidden this, void *, unsigned __int64, const void *, unsigned __int64)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x1800368a4`
- `0x180037528`
- `0x180039910`
- `0x18003a7e8`
- `0x180046cd8`
- `0x180049110`
- `0x180049398`
- `0x18005ca3c`
- `0x180069d60`
- `0x18006c548`
- `0x180074480`

## callees

- `0x1800245b4`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x1800245b8`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x1800245b8`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x1800245db`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x1800245e7`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x1800245f3`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x1800245db`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x1800245e7`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x1800245f3`

## pseudocode

```c
void __fastcall ATL::Checked::memmove_s(ATL::Checked *this, rsize_t a2, const void *a3, rsize_t a4)
{
  errno_t v4; // eax

  v4 = memmove_s(this, a2, a3, a4);
  if ( v4 && v4 != 80 )
  {
    if ( v4 != 12 )
    {
      if ( v4 != 22 && v4 != 34 )
      {
        ATL::BaseAtlThrow(-2147467259);
        __debugbreak();
      }
      ATL::BaseAtlThrow(-2147024809);
      __debugbreak();
    }
    ATL::BaseAtlThrow(-2147024882);
    __debugbreak();
  }
}

```

## disassembly

```asm
0x1800245b4  sub     rsp, 28h
0x1800245b8  call    cs:__imp_memmove_s
0x1800245be  test    eax, eax
0x1800245c0  jz      short loc_1800245FA
0x1800245c2  cmp     eax, 50h ; 'P'
0x1800245c5  jz      short loc_1800245FA
0x1800245c7  cmp     eax, 0Ch
0x1800245ca  jz      short loc_1800245EE
0x1800245cc  cmp     eax, 16h
0x1800245cf  jz      short loc_1800245E2
0x1800245d1  cmp     eax, 22h ; '"'
0x1800245d4  jz      short loc_1800245E2
0x1800245d6  mov     ecx, 80004005h
0x1800245db  call    cs:__imp_?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1800245e1  int     3; Trap to Debugger
0x1800245e2  mov     ecx, 80070057h
0x1800245e7  call    cs:__imp_?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1800245ed  int     3; Trap to Debugger
0x1800245ee  mov     ecx, 8007000Eh
0x1800245f3  call    cs:__imp_?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1800245f9  int     3; Trap to Debugger
0x1800245fa  add     rsp, 28h
0x1800245fe  retn
```
