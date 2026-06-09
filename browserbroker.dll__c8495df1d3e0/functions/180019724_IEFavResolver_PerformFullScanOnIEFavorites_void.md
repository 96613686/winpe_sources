# IEFavResolver::PerformFullScanOnIEFavorites(void)

- ea: `0x180019724`
- end: `0x180019841`
- name: `?PerformFullScanOnIEFavorites@IEFavResolver@@AEAAJXZ`
- size: `285`
- prototype: `__int64 __fastcall(IEFavResolver *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180019b8c`

## callees

- `0x180006cc4`
- `0x180019724`
- `0x18001aaf4`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Reset` at `0x1800197cc`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Reset` at `0x1800197cc`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x1800197e2`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x1800197e2`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Size` at `0x180019799`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Size` at `0x180019799`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180019745`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180019745`
- `edgeIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x180019818`
- `edgeIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x180019818`
- `edgeIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x1800197bc`
- `edgeIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x1800197bc`
- `edgeIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x180019827`
- `edgeIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x180019827`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IEFavResolver::PerformFullScanOnIEFavorites(IEFavResolver *this)
{
  int v2; // ebx
  struct _IsoMessage *v4; // [rsp+30h] [rbp-10h] BYREF
  ULARGE_INTEGER pui; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v6; // [rsp+68h] [rbp+28h] BYREF
  unsigned int v7; // [rsp+70h] [rbp+30h] BYREF
  LPSTREAM ppstm; // [rsp+78h] [rbp+38h] BYREF

  ppstm = 0;
  v2 = CreateStreamOnHGlobal(0, 1, &ppstm);
  if ( v2 >= 0 )
  {
    v6 = 0;
    v4 = 0;
    v7 = 0;
    v2 = IEFavResolver::WriteFavoriteToStreamRecursively(this, (unsigned __int16 *)this + 24, &ppstm, &v7);
    if ( v2 >= 0 )
    {
      pui.QuadPart = 0;
      v2 = IStream_Size(ppstm, &pui);
      if ( v2 >= 0 )
      {
        v2 = IsoAllocMessageBuffer(*((_DWORD *)this + 2), &v6, pui.LowPart + 44, &v4);
        if ( v2 >= 0 )
        {
          IStream_Reset(ppstm);
          v2 = IStream_Read(ppstm, (char *)v4 + 40, pui.LowPart);
          if ( v2 < 0
            || (*((_DWORD *)v4 + 8) = v7,
                *((_DWORD *)v4 + 9) = pui.LowPart,
                v2 = LCIEPostMessage(*((_DWORD *)this + 2), *((_DWORD *)this + 1), 0xDC1u, 0, v6),
                v2 < 0) )
          {
            IsoFreeMessageBuffer(v6);
          }
        }
      }
    }
  }
  ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>((__int64 *)&ppstm);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180019724  push    rbp
0x180019726  push    rbx
0x180019727  push    rdi
0x180019728  mov     rbp, rsp
0x18001972b  sub     rsp, 40h
0x18001972f  mov     rdi, rcx
0x180019732  mov     [rbp+ppstm], 0
0x18001973a  lea     r8, [rbp+ppstm]; ppstm
0x18001973e  mov     edx, 1; fDeleteOnRelease
0x180019743  xor     ecx, ecx; hGlobal
0x180019745  call    cs:__imp_CreateStreamOnHGlobal
0x18001974b  mov     ebx, eax
0x18001974d  test    eax, eax
0x18001974f  js      loc_18001982E
0x180019755  mov     [rbp+arg_8], 0
0x18001975c  mov     [rbp+var_10], 0
0x180019764  mov     [rbp+arg_10], 0
0x18001976b  lea     rdx, [rdi+30h]; unsigned __int16 *
0x18001976f  lea     r9, [rbp+arg_10]; unsigned int *
0x180019773  lea     r8, [rbp+ppstm]; struct IStream **
0x180019777  mov     rcx, rdi; this
0x18001977a  call    ?WriteFavoriteToStreamRecursively@IEFavResolver@@AEAAJPEBGPEAPEAUIStream@@PEAK@Z; IEFavResolver::WriteFavoriteToStreamRecursively(ushort const *,IStream * *,ulong *)
0x18001977f  mov     ebx, eax
0x180019781  test    eax, eax
0x180019783  js      loc_18001982E
0x180019789  mov     qword ptr [rbp+pui], 0
0x180019791  lea     rdx, [rbp+pui]; pui
0x180019795  mov     rcx, [rbp+ppstm]; pstm
0x180019799  call    cs:__imp_IStream_Size
0x18001979f  mov     ebx, eax
0x1800197a1  test    eax, eax
0x1800197a3  js      loc_18001982E
0x1800197a9  mov     r8d, dword ptr [rbp+pui]
0x1800197ad  add     r8d, 2Ch ; ','
0x1800197b1  lea     r9, [rbp+var_10]
0x1800197b5  lea     rdx, [rbp+arg_8]
0x1800197b9  mov     ecx, [rdi+8]
0x1800197bc  call    cs:__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z; IsoAllocMessageBuffer(ulong,ulong *,ulong,_IsoMessage * *)
0x1800197c2  mov     ebx, eax
0x1800197c4  test    eax, eax
0x1800197c6  js      short loc_18001982E
0x1800197c8  mov     rcx, [rbp+ppstm]; pstm
0x1800197cc  call    cs:__imp_IStream_Reset
0x1800197d2  mov     rdx, [rbp+var_10]
0x1800197d6  add     rdx, 28h ; '('; pv
0x1800197da  mov     r8d, dword ptr [rbp+pui]; cb
0x1800197de  mov     rcx, [rbp+ppstm]; pstm
0x1800197e2  call    cs:__imp_IStream_Read
0x1800197e8  mov     ebx, eax
0x1800197ea  test    eax, eax
0x1800197ec  js      short loc_180019824
0x1800197ee  mov     rcx, [rbp+var_10]
0x1800197f2  mov     eax, [rbp+arg_10]
0x1800197f5  mov     [rcx+20h], eax
0x1800197f8  mov     rcx, [rbp+var_10]
0x1800197fc  mov     eax, dword ptr [rbp+pui]
0x1800197ff  mov     [rcx+24h], eax
0x180019802  mov     eax, [rbp+arg_8]
0x180019805  mov     [rsp+40h+var_20], eax
0x180019809  xor     r9d, r9d
0x18001980c  mov     r8d, 0DC1h
0x180019812  mov     edx, [rdi+4]
0x180019815  mov     ecx, [rdi+8]
0x180019818  call    cs:__imp_?LCIEPostMessage@@YAJKKKKK@Z; LCIEPostMessage(ulong,ulong,ulong,ulong,ulong)
0x18001981e  mov     ebx, eax
0x180019820  test    eax, eax
0x180019822  jns     short loc_18001982E
0x180019824  mov     ecx, [rbp+arg_8]
0x180019827  call    cs:__imp_?IsoFreeMessageBuffer@@YAJK@Z; IsoFreeMessageBuffer(ulong)
0x18001982d  nop
0x18001982e  lea     rcx, [rbp+ppstm]
0x180019832  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x180019837  mov     eax, ebx
0x180019839  add     rsp, 40h
0x18001983d  pop     rdi
0x18001983e  pop     rbx
0x18001983f  pop     rbp
0x180019840  retn
```
