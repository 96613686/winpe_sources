# ATL::AtlCrtErrorCheck(int)

- ea: `0x180008570`
- end: `0x1800085b4`
- name: `?AtlCrtErrorCheck@ATL@@YAHH@Z`
- size: `68`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180004fb8`
- `0x180006260`
- `0x180007cdc`
- `0x1800084a8`
- `0x180008ad8`

## callees

- `0x180005a10`
- `0x180008570`

## pseudocode

```c
__int64 __fastcall ATL::AtlCrtErrorCheck(unsigned int a1)
{
  if ( a1 )
  {
    if ( a1 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( a1 == 22 || a1 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( a1 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  return a1;
}

```

## disassembly

```asm
0x180008570  sub     rsp, 28h
0x180008574  test    ecx, ecx
0x180008576  jz      short loc_1800085AD
0x180008578  cmp     ecx, 0Ch
0x18000857b  jz      short loc_1800085A2
0x18000857d  cmp     ecx, 16h
0x180008580  jz      short loc_180008597
0x180008582  cmp     ecx, 22h ; '"'
0x180008585  jz      short loc_180008597
0x180008587  cmp     ecx, 50h ; 'P'
0x18000858a  jz      short loc_1800085AD
0x18000858c  mov     ecx, 80004005h; int
0x180008591  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180008597  mov     ecx, 80070057h; int
0x18000859c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800085a2  mov     ecx, 8007000Eh; int
0x1800085a7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800085ad  mov     eax, ecx
0x1800085af  add     rsp, 28h
0x1800085b3  retn
```
