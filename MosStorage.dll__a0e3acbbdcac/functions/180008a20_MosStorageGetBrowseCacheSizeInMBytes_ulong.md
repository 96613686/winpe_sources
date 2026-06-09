# MosStorageGetBrowseCacheSizeInMBytes(ulong *)

- ea: `0x180008a20`
- end: `0x180008aa0`
- name: `?MosStorageGetBrowseCacheSizeInMBytes@@YAJPEAK@Z`
- size: `128`
- prototype: `__int64 __fastcall(unsigned int *, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800083e0`

## callees

- `0x180008a20`
- `0x18000ca6c`

## import_xrefs

- `ZTrace_Maps!ZTraceReportIgnoreNoThis` at `0x180008a7a`
- `ZTrace_Maps!ZTraceReportIgnoreNoThis` at `0x180008a7a`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180008a44`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180008a44`

## string_xrefs

- `0x180008a73`: `IsSmallBrowseCacheEnabled`
- `0x180008a38`: `MosStorageGetBrowseCacheSizeInMBytes`
- `0x180008a55`: `UseSmallerCache`

## pseudocode

```c
__int64 __fastcall MosStorageGetBrowseCacheSizeInMBytes(unsigned int *a1, __int64 a2, __int64 a3)
{
  unsigned int v4; // edi
  int MapsPersistedRegBoolean; // eax
  bool v7; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    v4 = 0;
    v7 = 0;
    MapsPersistedRegBoolean = RegUtils::GetMapsPersistedRegBoolean(1, L"UseSmallerCache", a3, &v7);
    if ( MapsPersistedRegBoolean < 0 )
      ZTraceReportIgnoreNoThis(MapsPersistedRegBoolean, "IsSmallBrowseCacheEnabled", 84);
    *a1 = v7 ? 80 : 160;
  }
  else
  {
    return (unsigned int)ZTraceReportOriginationNoThis(-2147467261, "MosStorageGetBrowseCacheSizeInMBytes", 999);
  }
  return v4;
}

```

## disassembly

```asm
0x180008a20  mov     [rsp+arg_8], rbx
0x180008a25  push    rdi
0x180008a26  sub     rsp, 20h
0x180008a2a  mov     rbx, rcx
0x180008a2d  test    rcx, rcx
0x180008a30  jnz     short loc_180008A4E
0x180008a32  mov     r8d, 3E7h
0x180008a38  lea     rdx, aMosstoragegetb_0; "MosStorageGetBrowseCacheSizeInMBytes"
0x180008a3f  mov     ecx, 80004003h
0x180008a44  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180008a4a  mov     edi, eax
0x180008a4c  jmp     short loc_180008A93
0x180008a4e  xor     edi, edi
0x180008a50  lea     r9, [rsp+28h+arg_0]
0x180008a55  lea     rdx, aUsesmallercach; "UseSmallerCache"
0x180008a5c  mov     [rsp+28h+arg_0], dil
0x180008a61  lea     ecx, [rdi+1]
0x180008a64  call    ?GetMapsPersistedRegBoolean@RegUtils@@SAJW4MapsRegKeys@@PEBG_NPEA_N@Z; RegUtils::GetMapsPersistedRegBoolean(MapsRegKeys,ushort const *,bool,bool *)
0x180008a69  test    eax, eax
0x180008a6b  jns     short loc_180008A80
0x180008a6d  lea     r8d, [rdi+54h]
0x180008a71  mov     ecx, eax
0x180008a73  lea     rdx, aIssmallbrowsec; "IsSmallBrowseCacheEnabled"
0x180008a7a  call    cs:__imp_?ZTraceReportIgnoreNoThis@@YAXHPEBDH@Z; ZTraceReportIgnoreNoThis(int,char const *,int)
0x180008a80  mov     al, [rsp+28h+arg_0]
0x180008a84  neg     al
0x180008a86  sbb     ecx, ecx
0x180008a88  and     ecx, 0FFFFFFB0h
0x180008a8b  add     ecx, 0A0h
0x180008a91  mov     [rbx], ecx
0x180008a93  mov     rbx, [rsp+28h+arg_8]
0x180008a98  mov     eax, edi
0x180008a9a  add     rsp, 20h
0x180008a9e  pop     rdi
0x180008a9f  retn
```
