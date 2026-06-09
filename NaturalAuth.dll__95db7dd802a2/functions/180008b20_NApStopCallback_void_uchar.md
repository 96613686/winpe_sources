# NApStopCallback(void *,uchar)

- ea: `0x180008b20`
- end: `0x180008c92`
- name: `?NApStopCallback@@YAXPEAXE@Z`
- size: `370`
- prototype: `void __fastcall(void *, unsigned __int8)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000584c`
- `0x180007430`
- `0x180008b20`
- `0x180009c20`
- `0x18000a03c`
- `0x18000a7d0`
- `0x18000a838`
- `0x18000ad04`
- `0x18000b5b0`
- `0x18001e730`
- `0x18001ec98`
- `0x180021710`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180008c8b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008bf3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008bf3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180008b60`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180008b60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008b72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008b72`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180008c64`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180008c64`
- `RPCRT4!RpcBindingVectorFree` at `0x180008bad`
- `RPCRT4!RpcBindingVectorFree` at `0x180008bad`
- `ext-ms-win-ntuser-misc-l1-1-0!UnregisterDeviceNotification` at `0x180008bd8`
- `ext-ms-win-ntuser-misc-l1-1-0!UnregisterDeviceNotification` at `0x180008bd8`

## pseudocode

```c
void __fastcall NApStopCallback(HANDLE *a1, char a2)
{
  Microsoft::WRL::Details *v4; // rax
  struct Microsoft::WRL::Details::ModuleBase *v5; // rdx
  const unsigned __int16 *v6; // r8
  Microsoft::WRL::Details *v7; // rax
  struct Microsoft::WRL::Details::ModuleBase *v8; // rdx
  bool v9; // r9
  _QWORD *v10; // rbx
  unsigned int v11; // r8d
  RTL_SRWLOCK *v12; // [rsp+30h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_2da9a8550d1e32063426f0effd98d727_Traceguids);
  UnregisterWait(*a1);
  if ( !a2 )
  {
    CloseHandle(a1[1]);
    NADisableRpcInterface(qword_1800481A0);
    v4 = (Microsoft::WRL::Details *)Microsoft::WRL::Details::OutOfProcModuleBase<NaturalAuthServiceModule>::Create();
    Microsoft::WRL::Details::UnregisterObjects(v4, v5, v6);
    v7 = (Microsoft::WRL::Details *)Microsoft::WRL::Details::OutOfProcModuleBase<NaturalAuthServiceModule>::Create();
    Microsoft::WRL::Details::TerminateMap(v7, v8, 0, v9);
    NAPluginManagerUninitialize();
    RpcBindingVectorFree(&g_pBindingVector);
    g_pBindingVector = 0;
    if ( g_hDeviceNotification && (unsigned __int8)IsUnregisterDeviceNotificationPresent() )
    {
      UnregisterDeviceNotification(g_hDeviceNotification);
      g_hDeviceNotification = 0;
    }
    AcquireSRWLockExclusive(&SRWLock);
    v12 = &SRWLock;
    v10 = (_QWORD *)qword_18005F740;
    std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::unique_ptr<SignalInfo>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<SignalInfo>>,void *>>>(
      (__int64)&qword_18005F740,
      (__int64)&qword_18005F740,
      *(__int64 **)(qword_18005F740 + 8));
    v10[1] = v10;
    *v10 = v10;
    v10[2] = v10;
    qword_18005F748 = 0;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
    NaturalAuthTraceLogging::Cleanup(0, 0, v11);
    g_ssService.dwCurrentState = 1;
    *(_QWORD *)&g_ssService.dwCheckPoint = 0;
    SetServiceStatus(g_hssService, &g_ssService);
  }
  WppCleanupUm();
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x180008b20  mov     [rsp+arg_8], rbx
0x180008b25  push    rdi
0x180008b26  sub     rsp, 20h
0x180008b2a  mov     bl, dl
0x180008b2c  mov     rdi, rcx
0x180008b2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b36  lea     rax, WPP_GLOBAL_Control
0x180008b3d  cmp     rcx, rax
0x180008b40  jz      short loc_180008B5D
0x180008b42  test    byte ptr [rcx+1Ch], 4
0x180008b46  jz      short loc_180008B5D
0x180008b48  mov     rcx, [rcx+10h]
0x180008b4c  lea     r8, WPP_2da9a8550d1e32063426f0effd98d727_Traceguids
0x180008b53  mov     edx, 0Dh
0x180008b58  call    WPP_SF_
0x180008b5d  mov     rcx, [rdi]; WaitHandle
0x180008b60  call    cs:__imp_UnregisterWait
0x180008b66  test    bl, bl
0x180008b68  jnz     loc_180008C6A
0x180008b6e  mov     rcx, [rdi+8]; hObject
0x180008b72  call    cs:__imp_CloseHandle
0x180008b78  lea     rcx, qword_1800481A0; void *
0x180008b7f  call    ?NADisableRpcInterface@@YAXPEAX@Z; NADisableRpcInterface(void *)
0x180008b84  call    ?Create@?$OutOfProcModuleBase@VNaturalAuthServiceModule@@@Details@WRL@Microsoft@@SAAEAVNaturalAuthServiceModule@@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<NaturalAuthServiceModule>::Create(void)
0x180008b89  mov     rcx, rax; this
0x180008b8c  call    ?UnregisterObjects@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEBG@Z; Microsoft::WRL::Details::UnregisterObjects(Microsoft::WRL::Details::ModuleBase *,ushort const *)
0x180008b91  call    ?Create@?$OutOfProcModuleBase@VNaturalAuthServiceModule@@@Details@WRL@Microsoft@@SAAEAVNaturalAuthServiceModule@@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<NaturalAuthServiceModule>::Create(void)
0x180008b96  xor     r8d, r8d; unsigned __int16 *
0x180008b99  mov     rcx, rax; this
0x180008b9c  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x180008ba1  call    ?NAPluginManagerUninitialize@@YAXXZ; NAPluginManagerUninitialize(void)
0x180008ba6  lea     rcx, ?g_pBindingVector@@3PEAU_RPC_BINDING_VECTOR@@EA; BindingVector
0x180008bad  call    cs:__imp_RpcBindingVectorFree
0x180008bb3  cmp     cs:?g_hDeviceNotification@@3PEAXEA, 0; void * g_hDeviceNotification
0x180008bbb  mov     cs:?g_pBindingVector@@3PEAU_RPC_BINDING_VECTOR@@EA, 0; _RPC_BINDING_VECTOR * g_pBindingVector
0x180008bc6  jz      short loc_180008BE9
0x180008bc8  call    IsUnregisterDeviceNotificationPresent
0x180008bcd  test    al, al
0x180008bcf  jz      short loc_180008BE9
0x180008bd1  mov     rcx, cs:?g_hDeviceNotification@@3PEAXEA; Handle
0x180008bd8  call    cs:__imp_UnregisterDeviceNotification
0x180008bde  mov     cs:?g_hDeviceNotification@@3PEAXEA, 0; void * g_hDeviceNotification
0x180008be9  lea     rbx, SRWLock
0x180008bf0  mov     rcx, rbx; SRWLock
0x180008bf3  call    cs:__imp_AcquireSRWLockExclusive
0x180008bf9  lea     rcx, qword_18005F740
0x180008c00  mov     [rsp+28h+arg_0], rbx
0x180008c05  mov     rbx, cs:qword_18005F740
0x180008c0c  mov     rdx, rcx
0x180008c0f  mov     r8, [rbx+8]
0x180008c13  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignalInfo@@U?$default_delete@VSignalInfo@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$unique_ptr@VSignalInfo@@U?$default_delete@VSignalInfo@@@std@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignalInfo@@U?$default_delete@VSignalInfo@@@std@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignalInfo@@U?$default_delete@VSignalInfo@@@std@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::unique_ptr<SignalInfo>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<SignalInfo>>,void *>>>(std::allocator<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<SignalInfo>>,void *>> &,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<SignalInfo>>,void *> *)
0x180008c18  mov     [rbx+8], rbx
0x180008c1c  lea     rcx, [rsp+28h+arg_0]
0x180008c21  mov     [rbx], rbx
0x180008c24  mov     [rbx+10h], rbx
0x180008c28  mov     cs:qword_18005F748, 0
0x180008c33  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180008c38  xor     edx, edx; int
0x180008c3a  xor     ecx, ecx; this
0x180008c3c  call    ?Cleanup@NaturalAuthTraceLogging@@YAXJK@Z; NaturalAuthTraceLogging::Cleanup(long,ulong)
0x180008c41  mov     rcx, cs:?g_hssService@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180008c48  lea     rdx, ?g_ssService@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180008c4f  mov     cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwCurrentState, 1; _SERVICE_STATUS g_ssService ...
0x180008c59  mov     qword ptr cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS g_ssService ...
0x180008c64  call    cs:__imp_SetServiceStatus
0x180008c6a  call    WppCleanupUm
0x180008c6f  mov     rcx, gs:60h
0x180008c78  mov     r8, rdi
0x180008c7b  xor     edx, edx
0x180008c7d  mov     rcx, [rcx+30h]
0x180008c81  mov     rbx, [rsp+28h+arg_8]
0x180008c86  add     rsp, 20h
0x180008c8a  pop     rdi
0x180008c8b  jmp     cs:__imp_RtlFreeHeap
```
