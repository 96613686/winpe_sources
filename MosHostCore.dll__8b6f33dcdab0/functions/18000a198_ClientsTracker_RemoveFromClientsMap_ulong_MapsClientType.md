# ClientsTracker::RemoveFromClientsMap(ulong,MapsClientType)

- ea: `0x18000a198`
- end: `0x18000a257`
- name: `?RemoveFromClientsMap@ClientsTracker@@AEAAXKW4MapsClientType@@@Z`
- size: `191`
- prototype: `void __high(unsigned int, enum MapsClientType)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000a538`

## callees

- `0x1800082e4`
- `0x1800084d4`
- `0x180009310`
- `0x180009d0c`
- `0x180009db4`
- `0x18000a198`
- `0x18000af6c`

## pseudocode

```c
void __fastcall ClientsTracker::RemoveFromClientsMap(__int64 a1, int a2, int a3)
{
  _QWORD *v3; // rdi
  __int64 v6; // rax
  OfflineMapsTelemetry *v7; // rax
  _BYTE v8[40]; // [rsp+20h] [rbp-28h] BYREF
  int v9; // [rsp+50h] [rbp+8h] BYREF
  int v10; // [rsp+54h] [rbp+Ch]
  __int64 v11; // [rsp+68h] [rbp+20h] BYREF

  v3 = (_QWORD *)(a1 + 40);
  v9 = a2;
  v10 = a3;
  if ( *std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::find(
          (_QWORD *)(a1 + 40),
          &v11,
          (unsigned int *)&v9) == *(_QWORD *)(a1 + 48)
    || !*(_DWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Try_emplace<ClientsTracker::ClientKey const &,>(
                                 v3,
                                 (__int64)v8,
                                 (unsigned int *)&v9)
                  + 32LL) )
  {
    __int2c();
  }
  v6 = std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Try_emplace<ClientsTracker::ClientKey const &,>(
         v3,
         (__int64)v8,
         (unsigned int *)&v9);
  --*(_DWORD *)(*(_QWORD *)v6 + 32LL);
  if ( !*(_DWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Try_emplace<ClientsTracker::ClientKey const &,>(
                                 v3,
                                 (__int64)v8,
                                 (unsigned int *)&v9)
                  + 32LL) )
  {
    std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Erase<ClientsTracker::ClientKey>(
      v3,
      (unsigned int *)&v9);
    if ( OfflineMapsTelemetry::IsEnabled() )
    {
      v7 = OfflineMapsTelemetry::Instance();
      OfflineMapsTelemetry::ClientTrackerRemoveClient_(v7, a3, a2);
    }
  }
}

```

## disassembly

```asm
0x18000a198  mov     rax, rsp
0x18000a19b  mov     [rax+10h], rbx
0x18000a19f  push    rbp
0x18000a1a0  push    rsi
0x18000a1a1  push    rdi
0x18000a1a2  sub     rsp, 30h
0x18000a1a6  lea     rdi, [rcx+28h]
0x18000a1aa  mov     [rax+8], edx
0x18000a1ad  mov     esi, r8d
0x18000a1b0  mov     [rax+0Ch], r8d
0x18000a1b4  mov     ebp, edx
0x18000a1b6  lea     r8, [rax+8]
0x18000a1ba  mov     rbx, rcx
0x18000a1bd  lea     rdx, [rax+20h]
0x18000a1c1  mov     rcx, rdi
0x18000a1c4  call    ?find@?$_Hash@V?$_Umap_traits@UClientKey@ClientsTracker@@UClientValue@2@V?$_Uhash_compare@UClientKey@ClientsTracker@@UClientKeyHasher@2@U?$equal_to@UClientKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@@std@@@std@@@2@AEBUClientKey@ClientsTracker@@@Z; std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::find(ClientsTracker::ClientKey const &)
0x18000a1c9  mov     rcx, [rbx+30h]
0x18000a1cd  cmp     [rax], rcx
0x18000a1d0  jz      short loc_18000A1ED
0x18000a1d2  lea     r8, [rsp+48h+arg_0]
0x18000a1d7  mov     rcx, rdi
0x18000a1da  lea     rdx, [rsp+48h+var_28]
0x18000a1df  call    ??$_Try_emplace@AEBUClientKey@ClientsTracker@@$$V@?$_Hash@V?$_Umap_traits@UClientKey@ClientsTracker@@UClientValue@2@V?$_Uhash_compare@UClientKey@ClientsTracker@@UClientKeyHasher@2@U?$equal_to@UClientKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@PEAX@std@@_N@1@AEBUClientKey@ClientsTracker@@@Z; std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Try_emplace<ClientsTracker::ClientKey const &,>(ClientsTracker::ClientKey const &)
0x18000a1e4  mov     rcx, [rax]
0x18000a1e7  cmp     dword ptr [rcx+20h], 1
0x18000a1eb  jnb     short loc_18000A1EF
0x18000a1ed  int     2Ch; Windows NT - assertion failure
0x18000a1ef  lea     r8, [rsp+48h+arg_0]
0x18000a1f4  mov     rcx, rdi
0x18000a1f7  lea     rdx, [rsp+48h+var_28]
0x18000a1fc  call    ??$_Try_emplace@AEBUClientKey@ClientsTracker@@$$V@?$_Hash@V?$_Umap_traits@UClientKey@ClientsTracker@@UClientValue@2@V?$_Uhash_compare@UClientKey@ClientsTracker@@UClientKeyHasher@2@U?$equal_to@UClientKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@PEAX@std@@_N@1@AEBUClientKey@ClientsTracker@@@Z; std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Try_emplace<ClientsTracker::ClientKey const &,>(ClientsTracker::ClientKey const &)
0x18000a201  lea     r8, [rsp+48h+arg_0]
0x18000a206  mov     rcx, rdi
0x18000a209  mov     rdx, [rax]
0x18000a20c  dec     dword ptr [rdx+20h]
0x18000a20f  lea     rdx, [rsp+48h+var_28]
0x18000a214  call    ??$_Try_emplace@AEBUClientKey@ClientsTracker@@$$V@?$_Hash@V?$_Umap_traits@UClientKey@ClientsTracker@@UClientValue@2@V?$_Uhash_compare@UClientKey@ClientsTracker@@UClientKeyHasher@2@U?$equal_to@UClientKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@PEAX@std@@_N@1@AEBUClientKey@ClientsTracker@@@Z; std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Try_emplace<ClientsTracker::ClientKey const &,>(ClientsTracker::ClientKey const &)
0x18000a219  mov     rdx, [rax]
0x18000a21c  cmp     dword ptr [rdx+20h], 0
0x18000a220  jnz     short loc_18000A24A
0x18000a222  lea     rdx, [rsp+48h+arg_0]
0x18000a227  mov     rcx, rdi
0x18000a22a  call    ??$_Erase@UClientKey@ClientsTracker@@@?$_Hash@V?$_Umap_traits@UClientKey@ClientsTracker@@UClientValue@2@V?$_Uhash_compare@UClientKey@ClientsTracker@@UClientKeyHasher@2@U?$equal_to@UClientKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@@5@$0A@@std@@@std@@AEAA_KAEBUClientKey@ClientsTracker@@@Z; std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Erase<ClientsTracker::ClientKey>(ClientsTracker::ClientKey const &)
0x18000a22f  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x18000a234  test    al, al
0x18000a236  jz      short loc_18000A24A
0x18000a238  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x18000a23d  mov     r8d, ebp; int
0x18000a240  mov     edx, esi; int
0x18000a242  mov     rcx, rax; this
0x18000a245  call    ?ClientTrackerRemoveClient_@OfflineMapsTelemetry@@QEAAXHH@Z; OfflineMapsTelemetry::ClientTrackerRemoveClient_(int,int)
0x18000a24a  mov     rbx, [rsp+48h+arg_8]
0x18000a24f  add     rsp, 30h
0x18000a253  pop     rdi
0x18000a254  pop     rsi
0x18000a255  pop     rbp
0x18000a256  retn
```
