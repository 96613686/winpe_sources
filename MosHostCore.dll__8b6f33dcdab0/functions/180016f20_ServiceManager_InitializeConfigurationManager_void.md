# ServiceManager::InitializeConfigurationManager(void)

- ea: `0x180016f20`
- end: `0x180016fd6`
- name: `?InitializeConfigurationManager@ServiceManager@@AEAAJXZ`
- size: `182`
- prototype: `int __fastcall(ServiceManager *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016b60`

## callees

- `0x180003410`
- `0x180016f20`
- `0x1800171d0`

## import_xrefs

- `MosStorage!MosStorageGetDataDirectory` at `0x180016f5b`
- `MosStorage!MosStorageGetDataDirectory` at `0x180016f5b`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180016f77`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180016f77`
- `MapConfiguration!ConfigurationManager_SetCustomStorageFolder` at `0x180016f84`
- `MapConfiguration!ConfigurationManager_SetCustomStorageFolder` at `0x180016f84`
- `MapConfiguration!ConfigurationManager_Create` at `0x180016fa1`
- `MapConfiguration!ConfigurationManager_Create` at `0x180016fa1`

## string_xrefs

- `0x180016f6e`: `ServiceManager::InitializeConfigurationManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
int __fastcall ServiceManager::InitializeConfigurationManager(ServiceManager *this)
{
  char *v1; // rbx
  int DataDirectory; // eax
  int v4; // r8d
  unsigned __int16 v6[264]; // [rsp+20h] [rbp-228h] BYREF

  v1 = (char *)this + 4368;
  if ( *((_QWORD *)this + 546) )
    __int2c();
  DataDirectory = MosStorageGetDataDirectory(v6, 0x104u);
  if ( DataDirectory < 0 )
  {
    v4 = 2795;
    return ZTraceReportPropagation(DataDirectory, "ServiceManager::InitializeConfigurationManager", v4, this);
  }
  DataDirectory = ConfigurationManager_SetCustomStorageFolder(v6);
  if ( DataDirectory < 0 )
  {
    v4 = 2796;
    return ZTraceReportPropagation(DataDirectory, "ServiceManager::InitializeConfigurationManager", v4, this);
  }
  Microsoft::WRL::ComPtr<IClientProxyResolver>::InternalRelease(v1);
  DataDirectory = ConfigurationManager_Create(v1);
  if ( DataDirectory < 0 )
  {
    v4 = 2798;
    return ZTraceReportPropagation(DataDirectory, "ServiceManager::InitializeConfigurationManager", v4, this);
  }
  return 0;
}

```

## disassembly

```asm
0x180016f20  mov     [rsp+arg_8], rbx
0x180016f25  push    rdi
0x180016f26  sub     rsp, 240h
0x180016f2d  mov     rax, cs:__security_cookie
0x180016f34  xor     rax, rsp
0x180016f37  mov     [rsp+248h+var_18], rax
0x180016f3f  lea     rbx, [rcx+1110h]
0x180016f46  mov     rdi, rcx
0x180016f49  cmp     qword ptr [rbx], 0
0x180016f4d  jz      short loc_180016F51
0x180016f4f  int     2Ch; Windows NT - assertion failure
0x180016f51  mov     edx, 104h
0x180016f56  lea     rcx, [rsp+248h+var_228]
0x180016f5b  call    cs:__imp_?MosStorageGetDataDirectory@@YAJPEAGK@Z; MosStorageGetDataDirectory(ushort *,ulong)
0x180016f61  test    eax, eax
0x180016f63  jns     short loc_180016F7F
0x180016f65  mov     r8d, 0AEBh
0x180016f6b  mov     r9, rdi
0x180016f6e  lea     rdx, aServicemanager_72; "ServiceManager::InitializeConfiguration"...
0x180016f75  mov     ecx, eax
0x180016f77  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180016f7d  jmp     short loc_180016FB5
0x180016f7f  lea     rcx, [rsp+248h+var_228]
0x180016f84  call    cs:__imp_ConfigurationManager_SetCustomStorageFolder
0x180016f8a  test    eax, eax
0x180016f8c  jns     short loc_180016F96
0x180016f8e  mov     r8d, 0AECh
0x180016f94  jmp     short loc_180016F6B
0x180016f96  mov     rcx, rbx
0x180016f99  call    ?InternalRelease@?$ComPtr@UIClientProxyResolver@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IClientProxyResolver>::InternalRelease(void)
0x180016f9e  mov     rcx, rbx
0x180016fa1  call    cs:__imp_ConfigurationManager_Create
0x180016fa7  test    eax, eax
0x180016fa9  jns     short loc_180016FB3
0x180016fab  mov     r8d, 0AEEh
0x180016fb1  jmp     short loc_180016F6B
0x180016fb3  xor     eax, eax
0x180016fb5  mov     rcx, [rsp+248h+var_18]
0x180016fbd  xor     rcx, rsp; StackCookie
0x180016fc0  call    __security_check_cookie
0x180016fc5  mov     rbx, [rsp+248h+arg_8]
0x180016fcd  add     rsp, 240h
0x180016fd4  pop     rdi
0x180016fd5  retn
```
