# IPxlatInterfaceMgr::Cleanup(void)

- ea: `0x18000f4f8`
- end: `0x18000f662`
- name: `?Cleanup@IPxlatInterfaceMgr@@AEAAXXZ`
- size: `362`
- prototype: `void __fastcall(IPxlatInterfaceMgr *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000ea3c`
- `0x18000f41c`
- `0x180011400`

## callees

- `0x180002110`
- `0x18000b12c`
- `0x18000df7c`
- `0x18000e734`
- `0x18000f4f8`
- `0x1800132ac`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f596`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f5ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f596`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f5ad`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f64f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f64f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f646`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f646`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f5d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f5d4`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x18000f58c`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x18000f58c`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18000f539`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18000f55e`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18000f539`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18000f55e`
- `WINNSI!NsiDisconnectFromServer` at `0x18000f575`
- `WINNSI!NsiDisconnectFromServer` at `0x18000f575`

## pseudocode

```c
void __fastcall IPxlatInterfaceMgr::Cleanup(IPxlatInterfaceMgr *this)
{
  void *v2; // rcx
  void *v3; // rcx
  struct _RTL_CRITICAL_SECTION *v4; // rbp
  char *v5; // rsi
  _QWORD *v6; // rbx
  _QWORD *v7; // rdi
  IPxlatInterface *v8; // r14
  void *v9; // r15

  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::GetImpl'::`2'::impl) )
    IPxlatPolicyMgrUninitialize();
  if ( *((_QWORD *)this + 3) )
  {
    NsiRpcDeregisterChangeNotification(*((_QWORD *)this + 1), &NPI_MS_IPV6_MODULEID, 10);
    *((_QWORD *)this + 3) = 0;
  }
  if ( *((_QWORD *)this + 2) )
  {
    NsiRpcDeregisterChangeNotification(*((_QWORD *)this + 1), &NPI_MS_IPV4_MODULEID, 10);
    *((_QWORD *)this + 2) = 0;
  }
  if ( *((_QWORD *)this + 1) )
  {
    NsiDisconnectFromServer();
    *((_QWORD *)this + 1) = 0;
  }
  v2 = (void *)*((_QWORD *)this + 6);
  if ( v2 )
  {
    CancelWaitableTimer(v2);
    CloseHandle(*((HANDLE *)this + 6));
    *((_QWORD *)this + 6) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 5);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 5) = 0;
  }
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 1, 0, 1) )
  {
    v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 56);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
    v5 = (char *)this + 128;
    v6 = (_QWORD *)*((_QWORD *)this + 16);
    v7 = (_QWORD *)v6[1];
    while ( !*((_BYTE *)v7 + 25) )
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>,void *>>>(
        (__int64)v5,
        (__int64)v5,
        v7[2]);
      v8 = (IPxlatInterface *)v7[5];
      v9 = v7;
      v7 = (_QWORD *)*v7;
      if ( v8 )
      {
        IPxlatInterface::~IPxlatInterface(v8);
        operator delete(v8);
      }
      operator delete(v9);
    }
    v6[1] = v6;
    *v6 = v6;
    v6[2] = v6;
    *((_QWORD *)v5 + 1) = 0;
    LeaveCriticalSection(v4);
    DeleteCriticalSection(v4);
  }
}

```

## disassembly

```asm
0x18000f4f8  push    rbx
0x18000f4fa  push    rbp
0x18000f4fb  push    rsi
0x18000f4fc  push    rdi
0x18000f4fd  push    r14
0x18000f4ff  push    r15
0x18000f501  sub     rsp, 28h
0x18000f505  mov     rbx, rcx
0x18000f508  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Preview2_GPO@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_GPO@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_GPO> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::GetImpl(void)'::`2'::impl
0x18000f50f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_GPO@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::__private_IsEnabled(void)
0x18000f514  test    al, al
0x18000f516  jz      short loc_18000F51D
0x18000f518  call    IPxlatPolicyMgrUninitialize
0x18000f51d  mov     r9, [rbx+18h]
0x18000f521  mov     edi, 0Ah
0x18000f526  test    r9, r9
0x18000f529  jz      short loc_18000F547
0x18000f52b  mov     rcx, [rbx+8]
0x18000f52f  lea     rdx, NPI_MS_IPV6_MODULEID
0x18000f536  mov     r8d, edi
0x18000f539  call    cs:__imp_NsiRpcDeregisterChangeNotification
0x18000f53f  mov     qword ptr [rbx+18h], 0
0x18000f547  mov     r9, [rbx+10h]
0x18000f54b  test    r9, r9
0x18000f54e  jz      short loc_18000F56C
0x18000f550  mov     rcx, [rbx+8]
0x18000f554  lea     rdx, NPI_MS_IPV4_MODULEID
0x18000f55b  mov     r8d, edi
0x18000f55e  call    cs:__imp_NsiRpcDeregisterChangeNotification
0x18000f564  mov     qword ptr [rbx+10h], 0
0x18000f56c  mov     rcx, [rbx+8]
0x18000f570  test    rcx, rcx
0x18000f573  jz      short loc_18000F583
0x18000f575  call    cs:__imp_NsiDisconnectFromServer
0x18000f57b  mov     qword ptr [rbx+8], 0
0x18000f583  mov     rcx, [rbx+30h]; hTimer
0x18000f587  test    rcx, rcx
0x18000f58a  jz      short loc_18000F5A4
0x18000f58c  call    cs:__imp_CancelWaitableTimer
0x18000f592  mov     rcx, [rbx+30h]; hObject
0x18000f596  call    cs:__imp_CloseHandle
0x18000f59c  mov     qword ptr [rbx+30h], 0
0x18000f5a4  mov     rcx, [rbx+28h]; hObject
0x18000f5a8  test    rcx, rcx
0x18000f5ab  jz      short loc_18000F5BB
0x18000f5ad  call    cs:__imp_CloseHandle
0x18000f5b3  mov     qword ptr [rbx+28h], 0
0x18000f5bb  xor     ecx, ecx
0x18000f5bd  lea     eax, [rcx+1]
0x18000f5c0  lock cmpxchg [rbx+4], ecx
0x18000f5c5  test    eax, eax
0x18000f5c7  jz      loc_18000F655
0x18000f5cd  lea     rbp, [rbx+38h]
0x18000f5d1  mov     rcx, rbp; lpCriticalSection
0x18000f5d4  call    cs:__imp_EnterCriticalSection
0x18000f5da  lea     rsi, [rbx+80h]
0x18000f5e1  mov     rbx, [rsi]
0x18000f5e4  mov     rdi, [rbx+8]
0x18000f5e8  jmp     short loc_18000F62A
0x18000f5ea  mov     r8, [rdi+10h]
0x18000f5ee  mov     rdx, rsi
0x18000f5f1  mov     rcx, rsi
0x18000f5f4  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>,void *>>>(std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>,void *>> &,std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>,void *> *)
0x18000f5f9  mov     r14, [rdi+28h]
0x18000f5fd  mov     r15, rdi
0x18000f600  mov     rdi, [rdi]
0x18000f603  test    r14, r14
0x18000f606  jz      short loc_18000F61D
0x18000f608  mov     rcx, r14; this
0x18000f60b  call    ??1IPxlatInterface@@QEAA@XZ; IPxlatInterface::~IPxlatInterface(void)
0x18000f610  mov     edx, 0E8h; unsigned __int64
0x18000f615  mov     rcx, r14; void *
0x18000f618  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f61d  mov     edx, 30h ; '0'; unsigned __int64
0x18000f622  mov     rcx, r15; void *
0x18000f625  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f62a  cmp     byte ptr [rdi+19h], 0
0x18000f62e  jz      short loc_18000F5EA
0x18000f630  mov     [rbx+8], rbx
0x18000f634  mov     rcx, rbp; lpCriticalSection
0x18000f637  mov     [rbx], rbx
0x18000f63a  mov     [rbx+10h], rbx
0x18000f63e  mov     qword ptr [rsi+8], 0
0x18000f646  call    cs:__imp_LeaveCriticalSection
0x18000f64c  mov     rcx, rbp; lpCriticalSection
0x18000f64f  call    cs:__imp_DeleteCriticalSection
0x18000f655  add     rsp, 28h
0x18000f659  pop     r15
0x18000f65b  pop     r14
0x18000f65d  pop     rdi
0x18000f65e  pop     rsi
0x18000f65f  pop     rbp
0x18000f660  pop     rbx
0x18000f661  retn
```
