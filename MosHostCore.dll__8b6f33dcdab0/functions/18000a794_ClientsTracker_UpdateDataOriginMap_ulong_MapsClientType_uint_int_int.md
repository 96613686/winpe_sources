# ClientsTracker::UpdateDataOriginMap(ulong,MapsClientType,uint,int,int)

- ea: `0x18000a794`
- end: `0x18000a832`
- name: `?UpdateDataOriginMap@ClientsTracker@@QEAAXKW4MapsClientType@@IHH@Z`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001da90`

## callees

- `0x1800085ec`
- `0x18000a794`
- `0x18000af6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a7c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a7c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a82b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a7a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a7a8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ClientsTracker::UpdateDataOriginMap(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        int a6)
{
  __int64 v10; // rax
  _QWORD v11[9]; // [rsp+20h] [rbp-48h] BYREF
  unsigned int v12; // [rsp+70h] [rbp+8h] BYREF
  unsigned int v13; // [rsp+74h] [rbp+Ch]

  if ( a2 == GetCurrentProcessId() || !a2 )
    __int2c();
  v12 = a2;
  v13 = a3;
  EnterCriticalSection((LPCRITICAL_SECTION)a1);
  v11[2] = a1;
  std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::find(
    (_QWORD *)(a1 + 40),
    v11,
    &v12);
  if ( v11[0] != *(_QWORD *)(a1 + 48) && a5 <= 1 )
  {
    v12 = a4;
    v13 = a5;
    v10 = std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,enum MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>,0>>::_Try_emplace<ClientsTracker::DataOriginKey const &,>(
            (float *)(v11[0] + 88LL),
            (__int64)v11,
            &v12);
    *(_DWORD *)(*(_QWORD *)v10 + 24LL) = a6;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)a1);
}

```

## disassembly

```asm
0x18000a794  push    rbx
0x18000a796  push    rbp
0x18000a797  push    rsi
0x18000a798  push    rdi
0x18000a799  sub     rsp, 48h
0x18000a79d  mov     ebp, r9d
0x18000a7a0  mov     esi, r8d
0x18000a7a3  mov     edi, edx
0x18000a7a5  mov     rbx, rcx
0x18000a7a8  call    cs:__imp_GetCurrentProcessId
0x18000a7ae  cmp     edi, eax
0x18000a7b0  jz      short loc_18000A7B6
0x18000a7b2  test    edi, edi
0x18000a7b4  jnz     short loc_18000A7B8
0x18000a7b6  int     2Ch; Windows NT - assertion failure
0x18000a7b8  mov     [rsp+68h+arg_0], edi
0x18000a7bc  mov     [rsp+68h+arg_4], esi
0x18000a7c0  mov     rcx, rbx; lpCriticalSection
0x18000a7c3  call    cs:__imp_EnterCriticalSection
0x18000a7c9  mov     [rsp+68h+var_38], rbx
0x18000a7ce  lea     rcx, [rbx+28h]
0x18000a7d2  lea     r8, [rsp+68h+arg_0]
0x18000a7d7  lea     rdx, [rsp+68h+var_48]
0x18000a7dc  call    ?find@?$_Hash@V?$_Umap_traits@UClientKey@ClientsTracker@@UClientValue@2@V?$_Uhash_compare@UClientKey@ClientsTracker@@UClientKeyHasher@2@U?$equal_to@UClientKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@@std@@@std@@@2@AEBUClientKey@ClientsTracker@@@Z; std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::find(ClientsTracker::ClientKey const &)
0x18000a7e1  mov     rcx, [rsp+68h+var_48]
0x18000a7e6  cmp     rcx, [rbx+30h]
0x18000a7ea  jz      short loc_18000A820
0x18000a7ec  mov     eax, [rsp+68h+arg_20]
0x18000a7f3  cmp     eax, 1
0x18000a7f6  ja      short loc_18000A820
0x18000a7f8  mov     [rsp+68h+arg_0], ebp
0x18000a7fc  mov     [rsp+68h+arg_4], eax
0x18000a800  add     rcx, 58h ; 'X'
0x18000a804  lea     r8, [rsp+68h+arg_0]
0x18000a809  lea     rdx, [rsp+68h+var_48]
0x18000a80e  call    ??$_Try_emplace@AEBUDataOriginKey@ClientsTracker@@$$V@?$_Hash@V?$_Umap_traits@UDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@V?$_Uhash_compare@UDataOriginKey@ClientsTracker@@UDataOriginKeyHasher@2@U?$equal_to@UDataOriginKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@6@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@PEAX@std@@_N@1@AEBUDataOriginKey@ClientsTracker@@@Z; std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>,0>>::_Try_emplace<ClientsTracker::DataOriginKey const &,>(ClientsTracker::DataOriginKey const &)
0x18000a813  mov     rcx, [rax]
0x18000a816  mov     eax, [rsp+68h+arg_28]
0x18000a81d  mov     [rcx+18h], eax
0x18000a820  mov     rcx, rbx
0x18000a823  add     rsp, 48h
0x18000a827  pop     rdi
0x18000a828  pop     rsi
0x18000a829  pop     rbp
0x18000a82a  pop     rbx
0x18000a82b  jmp     cs:__imp_LeaveCriticalSection
```
