# MapsStoreManager::OnLoadCatalogAsyncOperationComplete(MapControl::RegionAsyncOperation const &)

- ea: `0x18001a280`
- end: `0x18001a4e4`
- name: `?OnLoadCatalogAsyncOperationComplete@MapsStoreManager@@AEAAXAEBVRegionAsyncOperation@MapControl@@@Z`
- size: `612`
- prototype: `void __fastcall(MapsStoreManager *__hidden this, const struct MapControl::RegionAsyncOperation *)`
- caller_count: `0`
- callee_count: `20`
- tags: `broker_com_uri`

## callees

- `0x180011d28`
- `0x180014178`
- `0x180014b64`
- `0x180014bf0`
- `0x180014fd0`
- `0x1800172f4`
- `0x180017aa8`
- `0x1800185b0`
- `0x18001a280`
- `0x18001a6e0`
- `0x18001afdc`
- `0x18001b9e0`
- `0x18001ccb8`
- `0x18001cd08`
- `0x18001d5a0`
- `0x18001d828`
- `0x18001eefc`
- `0x18002e2dc`
- `0x18004a9dc`
- `0x180098010`

## import_xrefs

- `MosStorage!MosQueryCatalogExists` at `0x18001a2f3`
- `MosStorage!MosQueryCatalogExists` at `0x18001a2f3`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001a30f`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001a30f`

## string_xrefs

- `0x18001a306`: `MapsStoreManager::OnLoadCatalogAsyncOperationComplete`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall MapsStoreManager::OnLoadCatalogAsyncOperationComplete(
        MapsStoreManager *this,
        const struct MapControl::RegionAsyncOperation *a2)
{
  _BYTE *v3; // rcx
  int v4; // ebx
  int v5; // eax
  wil *v6; // rcx
  __int64 v7; // rax
  Pal::UntypedAsyncOperation *v8; // rbx
  _QWORD *OdvsDataTypes; // rax
  __int64 *v10; // rax
  _QWORD *v11; // rdi
  _QWORD *i; // rbx
  __int64 v13; // rcx
  int v14; // eax
  int v15; // edi
  _QWORD *v16; // [rsp+30h] [rbp-58h] BYREF
  __int64 v17; // [rsp+38h] [rbp-50h]
  _BYTE v18[8]; // [rsp+40h] [rbp-48h] BYREF
  std::_Ref_count_base *v19; // [rsp+48h] [rbp-40h]
  __int128 v20; // [rsp+50h] [rbp-38h] BYREF
  __int64 v21; // [rsp+60h] [rbp-28h]
  __int128 v22; // [rsp+68h] [rbp-20h] BYREF
  __int64 v23; // [rsp+78h] [rbp-10h]
  int v25; // [rsp+A0h] [rbp+18h] BYREF

  try
  {
    v3 = (_BYTE *)*((_QWORD *)this + 48);
    if ( v3[150] )
    {
      v7 = (*(__int64 (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v3 + 56LL))(v3, v18);
      std::shared_ptr<MapControl::LocalIndex>::operator=((char *)this + 568, v7);
      if ( v19 )
        std::_Ref_count_base::_Decref(v19);
      v8 = (Pal::UntypedAsyncOperation *)*((_QWORD *)this + 48);
      Pal::UntypedAsyncOperation::ensureSucceeded(v8);
      v22 = 0;
      v23 = 0;
      std::vector<std::shared_ptr<MapControl::RegionDefinition>>::_Construct_n<std::shared_ptr<MapControl::RegionDefinition> * const &,std::shared_ptr<MapControl::RegionDefinition> * const &>(
        &v22,
        (__int64)(*((_QWORD *)v8 + 37) - *((_QWORD *)v8 + 36)) >> 4);
      OdvsDataTypes = (_QWORD *)MapControl::OdvsDataType::getOdvsDataTypes();
      v20 = 0;
      v21 = 0;
      std::vector<MapControl::PersistentDataKey>::_Construct_n<MapControl::PersistentDataKey * const &,MapControl::PersistentDataKey * const &>(
        &v20,
        0xAAAAAAAAAAAAAAABuLL * ((__int64)(OdvsDataTypes[1] - *OdvsDataTypes) >> 2),
        OdvsDataTypes);
      v16 = 0;
      v17 = 0;
      std::list<std::pair<unsigned short const,unsigned short>>::_Alloc_sentinel_and_proxy(&v16);
      v10 = (__int64 *)MapsRegionCatalogHelper::PrepareRegionCatalog(
                         (unsigned int)&v25,
                         (int)this + 568,
                         (int)this + 336,
                         (unsigned int)&v22,
                         (__int64)&v20,
                         (__int64)&v16);
      std::unique_ptr<MapRegionNode>::operator=<std::default_delete<MapRegionNode>,0>((__int64)this + 584, v10);
      std::unique_ptr<MapRegionNode>::~unique_ptr<MapRegionNode>(&v25);
      if ( v17 )
      {
        v11 = v16;
        for ( i = (_QWORD *)*v16; i != v11; i = (_QWORD *)*i )
        {
          v25 = i[2];
          std::list<unsigned int>::push_back((char *)this + 504, &v25);
        }
        *((_DWORD *)this + 121) = 6;
      }
      MapsStoreManager::ProcessNextOperation(this);
      std::_List_node<MapControl::RegionId,void *>::_Free_non_head<std::allocator<std::_List_node<MapControl::RegionId,void *>>>(
        v13,
        v16);
      std::_Deallocate<16>(v16, 0x18u);
      std::vector<MapControl::PersistentDataKey>::_Tidy(&v20);
      std::vector<std::shared_ptr<MapControl::RegionDefinition>>::_Tidy(&v22);
    }
    else
    {
      if ( (unsigned __int8)std::_Atomic_storage<bool,1>::load((char *)this + 480) )
      {
        v4 = -2080309241;
      }
      else
      {
        v4 = -2080309237;
        if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 14) + 88LL))(*((_QWORD *)this + 14)) )
        {
          LOBYTE(v25) = 0;
          v5 = MosQueryCatalogExists(&v25, 3);
          if ( v5 < 0 )
            ZTraceReportIgnore(v5, "MapsStoreManager::OnLoadCatalogAsyncOperationComplete", 683, this);
          if ( !(_BYTE)v25 )
            v4 = -2080309236;
        }
      }
      MapsStoreManager::CompleteStoreOperation(this, v4);
    }
  }
  catch ( ... )
  {
    v14 = wil::ResultFromCaughtException(v6);
    v15 = v14;
    if ( v14 < 0 )
      ZTraceReportIgnore(v14, "MapsStoreManager::OnLoadCatalogAsyncOperationComplete", 724, this);
    if ( *((_QWORD *)this + 48) )
      MapsStoreManager::CompleteStoreOperation(this, v15);
  }
}

```

## disassembly

```asm
0x18001a280  mov     [rsp+arg_8], rbx
0x18001a285  mov     [rsp+arg_18], rsi
0x18001a28a  mov     [rsp+arg_0], rcx
0x18001a28f  push    rdi
0x18001a290  sub     rsp, 80h
0x18001a297  mov     rsi, rcx
0x18001a29a  mov     rcx, [rcx+180h]
0x18001a2a1  cmp     byte ptr [rcx+96h], 0
0x18001a2a8  jnz     loc_18001A334
0x18001a2ae  lea     rcx, [rsi+1E0h]
0x18001a2b5  call    ?load@?$_Atomic_storage@_N$00@std@@QEBA_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::load(std::memory_order)
0x18001a2ba  test    al, al
0x18001a2bc  jz      short loc_18001A2C5
0x18001a2be  mov     ebx, 84010007h
0x18001a2c3  jmp     short loc_18001A325
0x18001a2c5  mov     ebx, 8401000Bh
0x18001a2ca  mov     rcx, [rsi+70h]
0x18001a2ce  mov     rax, [rcx]
0x18001a2d1  mov     rax, [rax+58h]
0x18001a2d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2da  test    al, al
0x18001a2dc  jz      short loc_18001A325
0x18001a2de  mov     byte ptr [rsp+88h+arg_10], 0
0x18001a2e6  mov     edx, 3
0x18001a2eb  lea     rcx, [rsp+88h+arg_10]
0x18001a2f3  call    cs:__imp_?MosQueryCatalogExists@@YAJPEA_NW4StackMode@@@Z; MosQueryCatalogExists(bool *,StackMode)
0x18001a2f9  test    eax, eax
0x18001a2fb  jns     short loc_18001A315
0x18001a2fd  mov     r9, rsi
0x18001a300  mov     r8d, 2ABh
0x18001a306  lea     rdx, aMapsstoremanag_2; "MapsStoreManager::OnLoadCatalogAsyncOpe"...
0x18001a30d  mov     ecx, eax
0x18001a30f  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001a315  mov     eax, 8401000Ch
0x18001a31a  cmp     byte ptr [rsp+88h+arg_10], 0
0x18001a322  cmovz   ebx, eax
0x18001a325  mov     edx, ebx; int
0x18001a327  mov     rcx, rsi; this
0x18001a32a  call    ?CompleteStoreOperation@MapsStoreManager@@AEAAXJ@Z; MapsStoreManager::CompleteStoreOperation(long)
0x18001a32f  jmp     loc_18001A4A9
0x18001a334  mov     rax, [rcx]
0x18001a337  lea     rdx, [rsp+88h+var_48]
0x18001a33c  mov     rax, [rax+38h]
0x18001a340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a345  lea     rdi, [rsi+238h]
0x18001a34c  mov     rdx, rax
0x18001a34f  mov     rcx, rdi
0x18001a352  call    ??4?$shared_ptr@VLocalIndex@MapControl@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<MapControl::LocalIndex>::operator=(std::shared_ptr<MapControl::LocalIndex> &&)
0x18001a357  mov     rcx, [rsp+88h+var_40]; this
0x18001a35c  test    rcx, rcx
0x18001a35f  jz      short loc_18001A366
0x18001a361  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001a366  mov     rbx, [rsi+180h]
0x18001a36d  mov     rcx, rbx; this
0x18001a370  call    ?ensureSucceeded@UntypedAsyncOperation@Pal@@IEBAXXZ; Pal::UntypedAsyncOperation::ensureSucceeded(void)
0x18001a375  xorps   xmm0, xmm0
0x18001a378  movdqu  [rsp+88h+var_20], xmm0
0x18001a37e  mov     [rsp+88h+var_10], 0
0x18001a387  lea     r8, [rbx+120h]
0x18001a38e  lea     r9, [r8+8]
0x18001a392  mov     rdx, [r9]
0x18001a395  sub     rdx, [r8]
0x18001a398  sar     rdx, 4
0x18001a39c  lea     rcx, [rsp+88h+var_20]
0x18001a3a1  call    ??$_Construct_n@AEBQEAV?$shared_ptr@VRegionDefinition@MapControl@@@std@@AEBQEAV12@@?$vector@V?$shared_ptr@VRegionDefinition@MapControl@@@std@@V?$allocator@V?$shared_ptr@VRegionDefinition@MapControl@@@std@@@2@@std@@AEAAX_KAEBQEAV?$shared_ptr@VRegionDefinition@MapControl@@@1@1@Z; std::vector<std::shared_ptr<MapControl::RegionDefinition>>::_Construct_n<std::shared_ptr<MapControl::RegionDefinition> * const &,std::shared_ptr<MapControl::RegionDefinition> * const &>(unsigned __int64,std::shared_ptr<MapControl::RegionDefinition> * const &,std::shared_ptr<MapControl::RegionDefinition> * const &)
0x18001a3a6  nop
0x18001a3a7  call    ?getOdvsDataTypes@OdvsDataType@MapControl@@SAAEBV?$vector@VOdvsDataType@MapControl@@V?$allocator@VOdvsDataType@MapControl@@@std@@@std@@XZ; MapControl::OdvsDataType::getOdvsDataTypes(void)
0x18001a3ac  xorps   xmm0, xmm0
0x18001a3af  movdqu  [rsp+88h+var_38], xmm0
0x18001a3b5  mov     [rsp+88h+var_28], 0
0x18001a3be  lea     r9, [rax+8]
0x18001a3c2  mov     rdx, [r9]
0x18001a3c5  sub     rdx, [rax]
0x18001a3c8  sar     rdx, 2
0x18001a3cc  mov     rcx, 0AAAAAAAAAAAAAAABh
0x18001a3d6  imul    rdx, rcx
0x18001a3da  mov     r8, rax
0x18001a3dd  lea     rcx, [rsp+88h+var_38]
0x18001a3e2  call    ??$_Construct_n@AEBQEAUPersistentDataKey@MapControl@@AEBQEAU12@@?$vector@UPersistentDataKey@MapControl@@V?$allocator@UPersistentDataKey@MapControl@@@std@@@std@@AEAAX_KAEBQEAUPersistentDataKey@MapControl@@1@Z; std::vector<MapControl::PersistentDataKey>::_Construct_n<MapControl::PersistentDataKey * const &,MapControl::PersistentDataKey * const &>(unsigned __int64,MapControl::PersistentDataKey * const &,MapControl::PersistentDataKey * const &)
0x18001a3e7  nop
0x18001a3e8  mov     [rsp+88h+var_58], 0
0x18001a3f1  mov     [rsp+88h+var_50], 0
0x18001a3fa  lea     rcx, [rsp+88h+var_58]
0x18001a3ff  call    ?_Alloc_sentinel_and_proxy@?$list@U?$pair@$$CBGG@std@@V?$allocator@U?$pair@$$CBGG@std@@@2@@std@@AEAAXXZ; std::list<std::pair<ushort const,ushort>>::_Alloc_sentinel_and_proxy(void)
0x18001a404  nop
0x18001a405  lea     r8, [rsi+150h]
0x18001a40c  lea     rax, [rsp+88h+var_58]
0x18001a411  mov     [rsp+88h+var_60], rax
0x18001a416  lea     rax, [rsp+88h+var_38]
0x18001a41b  mov     [rsp+88h+var_68], rax
0x18001a420  lea     r9, [rsp+88h+var_20]
0x18001a425  mov     rdx, rdi
0x18001a428  lea     rcx, [rsp+88h+arg_10]
0x18001a430  call    ?PrepareRegionCatalog@MapsRegionCatalogHelper@@SA?AV?$unique_ptr@VMapRegionNode@@U?$default_delete@VMapRegionNode@@@std@@@std@@AEBV?$shared_ptr@VOdvsRegionCatalogIndex@MapControl@@@3@AEBV?$shared_ptr@VPersistentCache@MapControl@@@3@AEBV?$vector@V?$shared_ptr@VRegionDefinition@MapControl@@@std@@V?$allocator@V?$shared_ptr@VRegionDefinition@MapControl@@@std@@@2@@3@AEBV?$vector@VOdvsDataType@MapControl@@V?$allocator@VOdvsDataType@MapControl@@@std@@@3@AEAV?$list@VRegionId@MapControl@@V?$allocator@VRegionId@MapControl@@@std@@@3@@Z; MapsRegionCatalogHelper::PrepareRegionCatalog(std::shared_ptr<MapControl::OdvsRegionCatalogIndex> const &,std::shared_ptr<MapControl::PersistentCache> const &,std::vector<std::shared_ptr<MapControl::RegionDefinition>> const &,std::vector<MapControl::OdvsDataType> const &,std::list<MapControl::RegionId> &)
0x18001a435  lea     rcx, [rsi+248h]
0x18001a43c  mov     rdx, rax
0x18001a43f  call    ??$?4U?$default_delete@VMapRegionNode@@@std@@$0A@@?$unique_ptr@VMapRegionNode@@U?$default_delete@VMapRegionNode@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<MapRegionNode>::operator=<std::default_delete<MapRegionNode>,0>(std::unique_ptr<MapRegionNode> &&)
0x18001a444  lea     rcx, [rsp+88h+arg_10]
0x18001a44c  call    ??1?$unique_ptr@VMapRegionNode@@U?$default_delete@VMapRegionNode@@@std@@@std@@QEAA@XZ; std::unique_ptr<MapRegionNode>::~unique_ptr<MapRegionNode>(void)
0x18001a451  cmp     [rsp+88h+var_50], 0
0x18001a457  jz      short loc_18001A470
0x18001a459  mov     rdi, [rsp+88h+var_58]
0x18001a45e  mov     rbx, [rdi]
0x18001a461  cmp     rbx, rdi
0x18001a464  jnz     short loc_18001A4AB
0x18001a466  mov     dword ptr [rsi+1E4h], 6
0x18001a470  mov     rcx, rsi; this
0x18001a473  call    ?ProcessNextOperation@MapsStoreManager@@AEAAXXZ; MapsStoreManager::ProcessNextOperation(void)
0x18001a478  nop
0x18001a479  mov     rdx, [rsp+88h+var_58]
0x18001a47e  call    ??$_Free_non_head@V?$allocator@U?$_List_node@VRegionId@MapControl@@PEAX@std@@@std@@@?$_List_node@VRegionId@MapControl@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@VRegionId@MapControl@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<MapControl::RegionId,void *>::_Free_non_head<std::allocator<std::_List_node<MapControl::RegionId,void *>>>(std::allocator<std::_List_node<MapControl::RegionId,void *>> &,std::_List_node<MapControl::RegionId,void *> *)
0x18001a483  mov     edx, 18h
0x18001a488  mov     rcx, [rsp+88h+var_58]
0x18001a48d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001a492  nop
0x18001a493  lea     rcx, [rsp+88h+var_38]
0x18001a498  call    ?_Tidy@?$vector@UPersistentDataKey@MapControl@@V?$allocator@UPersistentDataKey@MapControl@@@std@@@std@@AEAAXXZ; std::vector<MapControl::PersistentDataKey>::_Tidy(void)
0x18001a49d  nop
0x18001a49e  lea     rcx, [rsp+88h+var_20]
0x18001a4a3  call    ?_Tidy@?$vector@V?$shared_ptr@VRegionDefinition@MapControl@@@std@@V?$allocator@V?$shared_ptr@VRegionDefinition@MapControl@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<MapControl::RegionDefinition>>::_Tidy(void)
0x18001a4a8  nop
0x18001a4a9  jmp     short loc_18001A4CF
0x18001a4ab  mov     rax, [rbx+10h]
0x18001a4af  mov     [rsp+88h+arg_10], eax
0x18001a4b6  lea     rcx, [rsi+1F8h]
0x18001a4bd  lea     rdx, [rsp+88h+arg_10]
0x18001a4c5  call    ?push_back@?$list@IV?$allocator@I@std@@@std@@QEAAX$$QEAI@Z; std::list<uint>::push_back(uint &&)
0x18001a4ca  mov     rbx, [rbx]
0x18001a4cd  jmp     short loc_18001A461
0x18001a4cf  lea     r11, [rsp+88h+var_8]
0x18001a4d7  mov     rbx, [r11+18h]
0x18001a4db  mov     rsi, [r11+28h]
0x18001a4df  mov     rsp, r11
0x18001a4e2  pop     rdi
0x18001a4e3  retn
```
