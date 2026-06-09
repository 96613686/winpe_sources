# ATL::CRegParser::CanForceRemoveKey(ushort const *)

- ea: `0x180009f24`
- end: `0x180009f6b`
- name: `?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z`
- size: `71`
- prototype: `__int64 __fastcall(ATL::CRegParser *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e810`

## callees

- `0x180009f24`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009f49`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009f49`

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
0x180009f24  mov     [rsp+arg_0], rbx
0x180009f29  push    rdi
0x180009f2a  sub     rsp, 20h
0x180009f2e  mov     rdi, rdx
0x180009f31  xor     ebx, ebx
0x180009f33  cmp     ebx, 0Ch
0x180009f36  jge     short loc_180009F5B
0x180009f38  lea     rax, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x180009f3f  movsxd  rdx, ebx
0x180009f42  mov     rcx, rdi; lpString1
0x180009f45  mov     rdx, [rax+rdx*8]; lpString2
0x180009f49  call    cs:__imp_lstrcmpiW
0x180009f4f  test    eax, eax
0x180009f51  jz      short loc_180009F57
0x180009f53  inc     ebx
0x180009f55  jmp     short loc_180009F33
0x180009f57  xor     eax, eax
0x180009f59  jmp     short loc_180009F60
0x180009f5b  mov     eax, 1
0x180009f60  mov     rbx, [rsp+28h+arg_0]
0x180009f65  add     rsp, 20h
0x180009f69  pop     rdi
0x180009f6a  retn
```
