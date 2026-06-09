# ATL::CRegParser::CanForceRemoveKey(ushort const *)

- ea: `0x1800067c4`
- end: `0x18000680b`
- name: `?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z`
- size: `71`
- prototype: `__int64 __fastcall(ATL::CRegParser *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004fb8`

## callees

- `0x1800067c4`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x1800067e9`
- `KERNEL32!lstrcmpiW` at `0x1800067e9`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::CanForceRemoveKey(ATL::CRegParser *this, const unsigned __int16 *a2)
{
  int i; // ebx

  for ( i = 0; i < 12; ++i )
  {
    if ( !lstrcmpiW(a2, (LPCWSTR)(&ATL::CRegParser::rgszNeverDelete)[i]) )
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1800067c4  mov     [rsp+arg_0], rbx
0x1800067c9  push    rdi
0x1800067ca  sub     rsp, 20h
0x1800067ce  mov     rdi, rdx
0x1800067d1  xor     ebx, ebx
0x1800067d3  cmp     ebx, 0Ch
0x1800067d6  jge     short loc_1800067FB
0x1800067d8  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x1800067df  movsxd  rdx, ebx
0x1800067e2  mov     rcx, rdi; lpString1
0x1800067e5  mov     rdx, [rax+rdx*8]; lpString2
0x1800067e9  call    cs:__imp_lstrcmpiW
0x1800067ef  test    eax, eax
0x1800067f1  jz      short loc_1800067F7
0x1800067f3  inc     ebx
0x1800067f5  jmp     short loc_1800067D3
0x1800067f7  xor     eax, eax
0x1800067f9  jmp     short loc_180006800
0x1800067fb  mov     eax, 1
0x180006800  mov     rbx, [rsp+28h+arg_0]
0x180006805  add     rsp, 20h
0x180006809  pop     rdi
0x18000680a  retn
```
