# ClientsTracker::UpdateLastAccess(ulong,MapsClientType)

- ea: `0x18000a838`
- end: `0x18000a8d9`
- name: `?UpdateLastAccess@ClientsTracker@@QEAAXKW4MapsClientType@@@Z`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001dab0`

## callees

- `0x1800084d4`
- `0x18000a838`
- `0x18000af6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a874`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a874`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a8c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a8c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a84f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a84f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000a89d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000a89d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ClientsTracker::UpdateLastAccess(__int64 a1, unsigned int a2, int a3)
{
  ULONGLONG TickCount64; // rbx
  _QWORD v7[3]; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v8; // [rsp+40h] [rbp+8h] BYREF
  int v9; // [rsp+44h] [rbp+Ch]
  __int64 v10; // [rsp+58h] [rbp+20h]

  if ( a2 == GetCurrentProcessId() || !a2 )
    __int2c();
  if ( (a3 & 0xFFFFFFFA) != 0 )
    __int2c();
  v8 = a2;
  v9 = a3;
  EnterCriticalSection((LPCRITICAL_SECTION)a1);
  v10 = a1;
  if ( *std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::find(
          (_QWORD *)(a1 + 40),
          v7,
          &v8) == *(_QWORD *)(a1 + 48) )
    __int2c();
  TickCount64 = GetTickCount64();
  *(_QWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Try_emplace<ClientsTracker::ClientKey const &,>(
                           (_QWORD *)(a1 + 40),
                           (__int64)v7,
                           &v8)
            + 24LL) = TickCount64;
  LeaveCriticalSection((LPCRITICAL_SECTION)a1);
}

```

## disassembly

```asm
0x18000a838  mov     [rsp+arg_8], rbx
0x18000a83d  mov     [rsp+arg_10], rsi
0x18000a842  push    rdi
0x18000a843  sub     rsp, 30h
0x18000a847  mov     esi, r8d
0x18000a84a  mov     ebx, edx
0x18000a84c  mov     rdi, rcx
0x18000a84f  call    cs:__imp_GetCurrentProcessId
0x18000a855  cmp     ebx, eax
0x18000a857  jz      short loc_18000A85D
0x18000a859  test    ebx, ebx
0x18000a85b  jnz     short loc_18000A85F
0x18000a85d  int     2Ch; Windows NT - assertion failure
0x18000a85f  test    esi, 0FFFFFFFAh
0x18000a865  jz      short loc_18000A869
0x18000a867  int     2Ch; Windows NT - assertion failure
0x18000a869  mov     [rsp+38h+arg_0], ebx
0x18000a86d  mov     [rsp+38h+arg_4], esi
0x18000a871  mov     rcx, rdi; lpCriticalSection
0x18000a874  call    cs:__imp_EnterCriticalSection
0x18000a87a  mov     [rsp+38h+arg_18], rdi
0x18000a87f  lea     r8, [rsp+38h+arg_0]
0x18000a884  lea     rdx, [rsp+38h+var_18]
0x18000a889  lea     rcx, [rdi+28h]
0x18000a88d  call    ?find@?$_Hash@V?$_Umap_traits@UClientKey@ClientsTracker@@UClientValue@2@V?$_Uhash_compare@UClientKey@ClientsTracker@@UClientKeyHasher@2@U?$equal_to@UClientKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@@std@@@std@@@2@AEBUClientKey@ClientsTracker@@@Z; std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::find(ClientsTracker::ClientKey const &)
0x18000a892  mov     rdx, [rdi+30h]
0x18000a896  cmp     [rax], rdx
0x18000a899  jnz     short loc_18000A89D
0x18000a89b  int     2Ch; Windows NT - assertion failure
0x18000a89d  call    cs:__imp_GetTickCount64
0x18000a8a3  mov     rbx, rax
0x18000a8a6  lea     r8, [rsp+38h+arg_0]
0x18000a8ab  lea     rdx, [rsp+38h+var_18]
0x18000a8b0  lea     rcx, [rdi+28h]
0x18000a8b4  call    ??$_Try_emplace@AEBUClientKey@ClientsTracker@@$$V@?$_Hash@V?$_Umap_traits@UClientKey@ClientsTracker@@UClientValue@2@V?$_Uhash_compare@UClientKey@ClientsTracker@@UClientKeyHasher@2@U?$equal_to@UClientKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@PEAX@std@@_N@1@AEBUClientKey@ClientsTracker@@@Z; std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::_Try_emplace<ClientsTracker::ClientKey const &,>(ClientsTracker::ClientKey const &)
0x18000a8b9  mov     rcx, [rax]
0x18000a8bc  mov     [rcx+18h], rbx
0x18000a8c0  mov     rcx, rdi; lpCriticalSection
0x18000a8c3  call    cs:__imp_LeaveCriticalSection
0x18000a8c9  mov     rbx, [rsp+38h+arg_8]
0x18000a8ce  mov     rsi, [rsp+38h+arg_10]
0x18000a8d3  add     rsp, 30h
0x18000a8d7  pop     rdi
0x18000a8d8  retn
```
