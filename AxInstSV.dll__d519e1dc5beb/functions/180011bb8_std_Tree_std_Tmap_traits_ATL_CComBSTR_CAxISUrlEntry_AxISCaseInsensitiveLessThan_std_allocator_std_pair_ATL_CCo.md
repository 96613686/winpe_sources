# std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CAxISUrlEntry *,AxISCaseInsensitiveLessThan,std::allocator<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>,0>>::_Lower_bound_duplicate<ATL::CComBSTR>(std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *> * const,ATL::CComBSTR const &)

- ea: `0x180011bb8`
- end: `0x180011bde`
- name: `??$_Lower_bound_duplicate@VCComBSTR@ATL@@@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@PEAVCAxISUrlEntry@@UAxISCaseInsensitiveLessThan@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@1@AEBVCComBSTR@ATL@@@Z`
- size: `38`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800119a4`
- `0x180011ee0`

## callees

- `0x180011bb8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011bc9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011bc9`

## pseudocode

```c
bool __fastcall std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CAxISUrlEntry *,AxISCaseInsensitiveLessThan,std::allocator<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>,0>>::_Lower_bound_duplicate<ATL::CComBSTR>(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  return !*(_BYTE *)(a2 + 25) && (int)_o__wcsicmp(*a3, *(_QWORD *)(a2 + 32)) >= 0;
}

```

## disassembly

```asm
0x180011bb8  sub     rsp, 28h
0x180011bbc  cmp     byte ptr [rdx+19h], 0
0x180011bc0  jnz     short loc_180011BD7
0x180011bc2  mov     rdx, [rdx+20h]
0x180011bc6  mov     rcx, [r8]
0x180011bc9  call    cs:__imp__o__wcsicmp
0x180011bcf  test    eax, eax
0x180011bd1  js      short loc_180011BD7
0x180011bd3  mov     al, 1
0x180011bd5  jmp     short loc_180011BD9
0x180011bd7  xor     al, al
0x180011bd9  add     rsp, 28h
0x180011bdd  retn
```
