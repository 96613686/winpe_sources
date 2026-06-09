# ClientsTracker::GetClientAppPackageFamilyName(ulong,MapsClientType)

- ea: `0x1800098a4`
- end: `0x180009930`
- name: `?GetClientAppPackageFamilyName@ClientsTracker@@QEAAPEBGKW4MapsClientType@@@Z`
- size: `140`
- prototype: `__int64 __fastcall(__int64, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014c00`

## callees

- `0x180008110`
- `0x1800098a4`
- `0x18000af6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800098e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800098e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009917`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009917`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800098bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800098bb`

## pseudocode

```c
__int64 __fastcall ClientsTracker::GetClientAppPackageFamilyName(__int64 a1, int a2, int a3)
{
  __int64 v6; // rdx
  __int64 v7; // rbx
  int v9; // [rsp+30h] [rbp+8h] BYREF
  int v10; // [rsp+34h] [rbp+Ch]
  __int64 v11; // [rsp+48h] [rbp+20h] BYREF

  if ( a2 == GetCurrentProcessId() || !a2 )
    __int2c();
  if ( (a3 & 0xFFFFFFFA) != 0 )
    __int2c();
  v9 = a2;
  v10 = a3;
  EnterCriticalSection((LPCRITICAL_SECTION)a1);
  std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::find(
    a1 + 40,
    &v11,
    &v9);
  if ( v11 == *(_QWORD *)(a1 + 48) )
    v7 = 0;
  else
    v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11 + 40, v6);
  LeaveCriticalSection((LPCRITICAL_SECTION)a1);
  return v7;
}

```

## disassembly

```asm
0x1800098a4  mov     [rsp+arg_8], rbx
0x1800098a9  mov     [rsp+arg_10], rsi
0x1800098ae  push    rdi
0x1800098af  sub     rsp, 20h
0x1800098b3  mov     esi, r8d
0x1800098b6  mov     ebx, edx
0x1800098b8  mov     rdi, rcx
0x1800098bb  call    cs:__imp_GetCurrentProcessId
0x1800098c1  cmp     ebx, eax
0x1800098c3  jz      short loc_1800098C9
0x1800098c5  test    ebx, ebx
0x1800098c7  jnz     short loc_1800098CB
0x1800098c9  int     2Ch; Windows NT - assertion failure
0x1800098cb  test    esi, 0FFFFFFFAh
0x1800098d1  jz      short loc_1800098D5
0x1800098d3  int     2Ch; Windows NT - assertion failure
0x1800098d5  mov     rcx, rdi; lpCriticalSection
0x1800098d8  mov     [rsp+28h+arg_0], ebx
0x1800098dc  mov     [rsp+28h+arg_4], esi
0x1800098e0  call    cs:__imp_EnterCriticalSection
0x1800098e6  lea     rcx, [rdi+28h]
0x1800098ea  lea     r8, [rsp+28h+arg_0]
0x1800098ef  lea     rdx, [rsp+28h+arg_18]
0x1800098f4  call    ?find@?$_Hash@V?$_Umap_traits@UClientKey@ClientsTracker@@UClientValue@2@V?$_Uhash_compare@UClientKey@ClientsTracker@@UClientKeyHasher@2@U?$equal_to@UClientKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@@std@@@std@@@2@AEBUClientKey@ClientsTracker@@@Z; std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::find(ClientsTracker::ClientKey const &)
0x1800098f9  mov     rcx, [rsp+28h+arg_18]
0x1800098fe  cmp     rcx, [rdi+30h]
0x180009902  jz      short loc_180009912
0x180009904  add     rcx, 28h ; '('
0x180009908  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000990d  mov     rbx, rax
0x180009910  jmp     short loc_180009914
0x180009912  xor     ebx, ebx
0x180009914  mov     rcx, rdi; lpCriticalSection
0x180009917  call    cs:__imp_LeaveCriticalSection
0x18000991d  mov     rsi, [rsp+28h+arg_10]
0x180009922  mov     rax, rbx
0x180009925  mov     rbx, [rsp+28h+arg_8]
0x18000992a  add     rsp, 20h
0x18000992e  pop     rdi
0x18000992f  retn
```
