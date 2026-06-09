# ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::Append(ushort const *)

- ea: `0x18002a618`
- end: `0x18002a67b`
- name: `?Append@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z`
- size: `99`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180013f6c`

## callees

- `0x180011280`
- `0x18002a618`
- `0x18002a690`
- `0x18002a6b4`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x18002a65e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x18002a65e`

## pseudocode

```c
__int64 __fastcall ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Append(
        __int64 *a1,
        const WCHAR *a2,
        __int64 a3)
{
  int v5; // eax
  __int64 v6; // r9
  int v7; // edx
  unsigned int v8; // ebx

  v5 = ATL::CSimpleStringT<unsigned short,0>::StringLength(a2, a2, a3, *a1);
  v7 = v5 + 1 + *(_DWORD *)(v6 - 16);
  if ( ((*(_DWORD *)(v6 - 12) - v7) | (1 - *(_DWORD *)(v6 - 8))) < 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, v7);
  v8 = PathAppendW((LPWSTR)*a1, a2);
  ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(a1);
  return v8;
}

```

## disassembly

```asm
0x18002a618  mov     [rsp+arg_0], rbx
0x18002a61d  push    rdi
0x18002a61e  sub     rsp, 20h
0x18002a622  mov     r9, [rcx]
0x18002a625  mov     rdi, rcx
0x18002a628  mov     rcx, rdx
0x18002a62b  mov     rbx, rdx
0x18002a62e  call    ?StringLength@?$CSimpleStringT@G$0A@@ATL@@SAHPEBG@Z; ATL::CSimpleStringT<ushort,0>::StringLength(ushort const *)
0x18002a633  mov     edx, [r9-10h]
0x18002a637  inc     eax
0x18002a639  add     edx, eax
0x18002a63b  mov     r8d, 1
0x18002a641  mov     eax, [r9-0Ch]
0x18002a645  sub     r8d, [r9-8]
0x18002a649  sub     eax, edx
0x18002a64b  or      r8d, eax
0x18002a64e  jge     short loc_18002A658
0x18002a650  mov     rcx, rdi
0x18002a653  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18002a658  mov     rcx, [rdi]; pszPath
0x18002a65b  mov     rdx, rbx; pszMore
0x18002a65e  call    cs:__imp_PathAppendW
0x18002a664  mov     rcx, rdi
0x18002a667  mov     ebx, eax
0x18002a669  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x18002a66e  mov     eax, ebx
0x18002a670  mov     rbx, [rsp+28h+arg_0]
0x18002a675  add     rsp, 20h
0x18002a679  pop     rdi
0x18002a67a  retn
```
