# ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::AddExtension(ushort const *)

- ea: `0x180044e24`
- end: `0x180044e8a`
- name: `?AddExtension@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z`
- size: `102`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180013f6c`

## callees

- `0x180011280`
- `0x18002a690`
- `0x18002a6b4`
- `0x180044e24`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAddExtensionW` at `0x180044e6d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAddExtensionW` at `0x180044e6d`

## pseudocode

```c
__int64 __fastcall ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::AddExtension(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  int v4; // eax
  __int64 v5; // r9
  int v6; // edx
  unsigned int v7; // ebx

  v4 = ATL::CSimpleStringT<unsigned short,0>::StringLength(L".etl", a2, a3, *a1);
  v6 = v4 + *(_DWORD *)(v5 - 16);
  if ( ((*(_DWORD *)(v5 - 12) - v6) | (1 - *(_DWORD *)(v5 - 8))) < 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, v6);
  v7 = PathAddExtensionW((LPWSTR)*a1, L".etl");
  ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(a1);
  return v7;
}

```

## disassembly

```asm
0x180044e24  mov     [rsp+arg_0], rbx
0x180044e29  push    rdi
0x180044e2a  sub     rsp, 20h
0x180044e2e  mov     r9, [rcx]
0x180044e31  mov     rdi, rcx
0x180044e34  lea     rcx, pszExt; ".etl"
0x180044e3b  call    ?StringLength@?$CSimpleStringT@G$0A@@ATL@@SAHPEBG@Z; ATL::CSimpleStringT<ushort,0>::StringLength(ushort const *)
0x180044e40  mov     edx, [r9-10h]
0x180044e44  mov     r8d, 1
0x180044e4a  sub     r8d, [r9-8]
0x180044e4e  add     edx, eax
0x180044e50  mov     eax, [r9-0Ch]
0x180044e54  sub     eax, edx
0x180044e56  or      r8d, eax
0x180044e59  jge     short loc_180044E63
0x180044e5b  mov     rcx, rdi
0x180044e5e  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180044e63  mov     rcx, [rdi]; pszPath
0x180044e66  lea     rdx, pszExt; ".etl"
0x180044e6d  call    cs:__imp_PathAddExtensionW
0x180044e73  mov     rcx, rdi
0x180044e76  mov     ebx, eax
0x180044e78  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x180044e7d  mov     eax, ebx
0x180044e7f  mov     rbx, [rsp+28h+arg_0]
0x180044e84  add     rsp, 20h
0x180044e88  pop     rdi
0x180044e89  retn
```
