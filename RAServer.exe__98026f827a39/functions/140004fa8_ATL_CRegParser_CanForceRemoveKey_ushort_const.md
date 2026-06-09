# ATL::CRegParser::CanForceRemoveKey(ushort const *)

- ea: `0x140004fa8`
- end: `0x140004fef`
- name: `?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z`
- size: `71`
- prototype: `__int64 __fastcall(ATL::CRegParser *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140009754`

## callees

- `0x140004fa8`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x140004fcd`
- `KERNEL32!lstrcmpiW` at `0x140004fcd`

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
0x140004fa8  mov     [rsp+arg_0], rbx
0x140004fad  push    rdi
0x140004fae  sub     rsp, 20h
0x140004fb2  mov     rdi, rdx
0x140004fb5  xor     ebx, ebx
0x140004fb7  cmp     ebx, 0Ch
0x140004fba  jge     short loc_140004FDF
0x140004fbc  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x140004fc3  movsxd  rdx, ebx
0x140004fc6  mov     rcx, rdi; lpString1
0x140004fc9  mov     rdx, [rax+rdx*8]; lpString2
0x140004fcd  call    cs:__imp_lstrcmpiW
0x140004fd3  test    eax, eax
0x140004fd5  jz      short loc_140004FDB
0x140004fd7  inc     ebx
0x140004fd9  jmp     short loc_140004FB7
0x140004fdb  xor     eax, eax
0x140004fdd  jmp     short loc_140004FE4
0x140004fdf  mov     eax, 1
0x140004fe4  mov     rbx, [rsp+28h+arg_0]
0x140004fe9  add     rsp, 20h
0x140004fed  pop     rdi
0x140004fee  retn
```
