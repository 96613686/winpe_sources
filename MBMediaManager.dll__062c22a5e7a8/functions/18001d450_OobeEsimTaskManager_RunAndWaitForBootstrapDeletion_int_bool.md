# OobeEsimTaskManager::RunAndWaitForBootstrapDeletion(int,bool *)

- ea: `0x18001d450`
- end: `0x18001d911`
- name: `?RunAndWaitForBootstrapDeletion@OobeEsimTaskManager@@AEAAJHPEA_N@Z`
- size: `1217`
- prototype: `__int64 __fastcall(OobeEsimTaskManager *this, __int64, bool *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180036640`

## callees

- `0x180009150`
- `0x18000ad20`
- `0x18000fe58`
- `0x180016758`
- `0x180016bb0`
- `0x180017ac4`
- `0x18001b1d4`
- `0x18001bd80`
- `0x18001bdb8`
- `0x18001d450`
- `0x180023018`
- `0x18002cd20`
- `0x180034560`
- `0x180034a3c`
- `0x180034aac`
- `0x180034be8`
- `0x180035c60`
- `0x180036380`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001d5e0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001d5e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d75f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d75f`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001d72e`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001d72e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18001d55e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18001d801`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18001d8da`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18001d55e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18001d801`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18001d8da`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18001d4ae`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18001d4ae`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanEnumerateInterfaces` at `0x18001d518`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanEnumerateInterfaces` at `0x18001d518`

## string_xrefs

- `0x18001d4c3`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x18001d53c`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x18001d62c`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x18001d77f`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x18001d851`: `Task Complete`
- `0x18001d58d`: `OobeEsimTaskManager::RunAndWaitForBootstrapDeletion`
- `0x18001d68c`: `OobeEsimTaskManager::RunAndWaitForBootstrapDeletion`
- `0x18001d745`: `OobeEsimTaskManager::RunAndWaitForBootstrapDeletion`
- `0x18001d85d`: `OobeEsimTaskManager::RunAndWaitForBootstrapDeletion`
- `0x18001d680`: `Created task for interface. guidId=%hs`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OobeEsimTaskManager::RunAndWaitForBootstrapDeletion(OobeEsimTaskManager *this, __int64 a2, bool *a3)
{
  unsigned int v5; // eax
  unsigned int v6; // ebx
  unsigned int v7; // ebx
  unsigned int v8; // ebx
  _DWORD *v9; // rcx
  unsigned int v10; // esi
  unsigned int i; // ebx
  int v12; // eax
  __int64 v13; // rax
  __int64 v14; // rdx
  signed __int64 v15; // rcx
  DWORD v16; // eax
  signed int LastError; // eax
  _DWORD *v18; // rcx
  HANDLE *j; // rbx
  __int64 v20; // r9
  _DWORD *v21; // rcx
  unsigned int v22[2]; // [rsp+20h] [rbp-F8h] BYREF
  int v23; // [rsp+28h] [rbp-F0h] BYREF
  __int64 v24; // [rsp+30h] [rbp-E8h] BYREF
  HANDLE EventW; // [rsp+38h] [rbp-E0h] BYREF
  __int128 v26; // [rsp+40h] [rbp-D8h] BYREF
  __int64 v27; // [rsp+50h] [rbp-C8h]
  __int64 v28; // [rsp+58h] [rbp-C0h] BYREF
  HANDLE *lpHandles[2]; // [rsp+60h] [rbp-B8h] BYREF
  HANDLE *v30; // [rsp+70h] [rbp-A8h]
  HANDLE *p_EventW; // [rsp+78h] [rbp-A0h] BYREF
  char v32[40]; // [rsp+80h] [rbp-98h] BYREF
  __int128 v33; // [rsp+A8h] [rbp-70h] BYREF
  char v34; // [rsp+B8h] [rbp-60h]
  __int128 v35; // [rsp+C0h] [rbp-58h] BYREF
  _BYTE v36[19]; // [rsp+D0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  if ( !a3 )
    return 2147942487LL;
  *a3 = 0;
  v24 = -1;
  v23 = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::reset(&v24);
  v5 = WwanOpenHandle(1, 0, &v23, &v24);
  if ( v5 )
  {
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xF9,
           (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
           (const char *)v5,
           v22[0]);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(&v24);
    return v6;
  }
  *(_QWORD *)v22 = 0;
  *(_QWORD *)&v33 = v22;
  *((_QWORD *)&v33 + 1) = 0;
  v34 = 1;
  v7 = WwanEnumerateInterfaces(v24, 0, (char *)&v33 + 8);
  wil::details::out_param_ptr_t<WWAN_INTERFACE_INFO_LIST * *,wistd::unique_ptr<WWAN_INTERFACE_INFO_LIST,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>::~out_param_ptr_t<WWAN_INTERFACE_INFO_LIST * *,wistd::unique_ptr<WWAN_INTERFACE_INFO_LIST,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>(&v33);
  if ( v7 )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xFC,
           (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
           (const char *)v7,
           v22[0]);
    v9 = *(_DWORD **)v22;
    *(_QWORD *)v22 = 0;
    if ( v9 )
      WwanFreeMemory(v9);
LABEL_8:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(&v24);
    return v8;
  }
  v10 = 0;
  MBSettingUXLogging::Info(
    "OobeEsimTaskManager::RunAndWaitForBootstrapDeletion",
    0xFDu,
    "interfaces found=%d",
    **(_DWORD **)v22);
  std::vector<Microsoft::WRL::ComPtr<OobeBootstrapTask>>::vector<Microsoft::WRL::ComPtr<OobeBootstrapTask>>(&v26);
  std::vector<Microsoft::WRL::ComPtr<OobeBootstrapTask>>::vector<Microsoft::WRL::ComPtr<OobeBootstrapTask>>(lpHandles);
  for ( i = 0; i < **(_DWORD **)v22; ++i )
  {
    v33 = *(_OWORD *)(588LL * i + *(_QWORD *)v22 + 4);
    EventW = CreateEventW(0, 0, 0, 0);
    v28 = 0;
    p_EventW = &EventW;
    Microsoft::WRL::ComPtr<OobeBootstrapTask>::InternalRelease(&v28);
    v12 = Microsoft::WRL::Details::MakeAndInitialize<OobeBootstrapTask,OobeBootstrapTask,_GUID const &,void * *>(
            &v28,
            &v33,
            &p_EventW);
    v10 = v12;
    if ( v12 >= 0 )
    {
      v13 = MbLoggingHelperGuidToString(v32);
      v35 = *(_OWORD *)v13;
      *(_OWORD *)v36 = *(_OWORD *)(v13 + 16);
      *(_DWORD *)&v36[15] = *(_DWORD *)(v13 + 31);
      MBSettingUXLogging::Info(
        "OobeEsimTaskManager::RunAndWaitForBootstrapDeletion",
        0x10Eu,
        "Created task for interface. guidId=%hs",
        (const char *)&v35);
      v14 = *((_QWORD *)&v26 + 1);
      if ( *((_QWORD *)&v26 + 1) == v27 )
      {
        std::vector<Microsoft::WRL::ComPtr<OobeBootstrapTask>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<OobeBootstrapTask> const &>(
          &v26,
          *((_QWORD *)&v26 + 1),
          &v28);
      }
      else
      {
        **((_QWORD **)&v26 + 1) = v28;
        Microsoft::WRL::ComPtr<OobeBootstrapTask>::InternalAddRef(v14);
        *((_QWORD *)&v26 + 1) += 8LL;
      }
      if ( lpHandles[1] == v30 )
        std::vector<void *>::_Emplace_reallocate<void * const &>(lpHandles, lpHandles[1], &EventW);
      else
        *lpHandles[1]++ = EventW;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x109,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
        (const char *)(unsigned int)v12,
        v22[0]);
    }
    Microsoft::WRL::ComPtr<OobeBootstrapTask>::InternalRelease(&v28);
  }
  v15 = lpHandles[1] - lpHandles[0];
  if ( v15 )
  {
    v16 = WaitForMultipleObjects(v15, lpHandles[0], 1, 0x15F90u);
    if ( v16 == 258 )
    {
      MBSettingUXLogging::Info(
        "OobeEsimTaskManager::RunAndWaitForBootstrapDeletion",
        0x11Bu,
        "WaitForMultipleObjects Timed Out");
    }
    else if ( v16 == -1 )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x121,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
        (const char *)v8,
        v22[0]);
      if ( lpHandles[0] )
      {
        std::_Deallocate<16>(lpHandles[0], ((char *)v30 - (char *)lpHandles[0]) & 0xFFFFFFFFFFFFFFF8uLL);
        *(_OWORD *)lpHandles = 0;
        v30 = 0;
      }
      if ( (_QWORD)v26 )
      {
        std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<OobeBootstrapTask>>>(v26, *((_QWORD *)&v26 + 1));
        std::_Deallocate<16>(v26, (v27 - v26) & 0xFFFFFFFFFFFFFFF8uLL);
        v26 = 0;
        v27 = 0;
      }
      v18 = *(_DWORD **)v22;
      *(_QWORD *)v22 = 0;
      if ( v18 )
        WwanFreeMemory(v18);
      goto LABEL_8;
    }
  }
  for ( j = (HANDLE *)v26; j != *((HANDLE **)&v26 + 1); ++j )
  {
    EventW = *j;
    Microsoft::WRL::ComPtr<OobeBootstrapTask>::InternalAddRef(&EventW);
    if ( *(_DWORD *)(v20 + 96) == 3 )
      *a3 = 1;
    Microsoft::WRL::ComPtr<OobeBootstrapTask>::InternalRelease(&EventW);
  }
  MBSettingUXLogging::Info("OobeEsimTaskManager::RunAndWaitForBootstrapDeletion", 0x12Fu, "Task Complete");
  if ( lpHandles[0] )
  {
    std::_Deallocate<16>(lpHandles[0], ((char *)v30 - (char *)lpHandles[0]) & 0xFFFFFFFFFFFFFFF8uLL);
    *(_OWORD *)lpHandles = 0;
    v30 = 0;
  }
  if ( (_QWORD)v26 )
  {
    std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<OobeBootstrapTask>>>(v26, *((_QWORD *)&v26 + 1));
    std::_Deallocate<16>(v26, (v27 - v26) & 0xFFFFFFFFFFFFFFF8uLL);
    v26 = 0;
    v27 = 0;
  }
  v21 = *(_DWORD **)v22;
  *(_QWORD *)v22 = 0;
  if ( v21 )
    WwanFreeMemory(v21);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(&v24);
  return v10;
}

```

## disassembly

```asm
0x18001d450  push    rbx
0x18001d452  push    rsi
0x18001d453  push    rdi
0x18001d454  push    r14
0x18001d456  sub     rsp, 0F8h
0x18001d45d  mov     rax, cs:__security_cookie
0x18001d464  xor     rax, rsp
0x18001d467  mov     [rsp+118h+var_30], rax
0x18001d46f  mov     rdi, r8
0x18001d472  xor     r14d, r14d
0x18001d475  test    r8, r8
0x18001d478  jnz     short loc_18001D484
0x18001d47a  mov     eax, 80070057h
0x18001d47f  jmp     loc_18001D8F3
0x18001d484  mov     [r8], r14b
0x18001d487  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001d48b  mov     [rsp+118h+var_E8], rdx
0x18001d490  mov     [rsp+118h+var_F0], r14d
0x18001d495  lea     rcx, [rsp+118h+var_E8]
0x18001d49a  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWwanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::reset(void *)
0x18001d49f  lea     r9, [rsp+118h+var_E8]
0x18001d4a4  lea     r8, [rsp+118h+var_F0]
0x18001d4a9  xor     edx, edx
0x18001d4ab  lea     ecx, [rdx+1]
0x18001d4ae  call    cs:__imp_WwanOpenHandle
0x18001d4b4  test    eax, eax
0x18001d4b6  jz      short loc_18001D4E7
0x18001d4b8  mov     rcx, [rsp+118h]; this
0x18001d4c0  mov     r9d, eax; char *
0x18001d4c3  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18001d4ca  mov     edx, 0F9h; void *
0x18001d4cf  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001d4d4  mov     ebx, eax
0x18001d4d6  lea     rcx, [rsp+118h+var_E8]
0x18001d4db  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWwanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(void)
0x18001d4e0  mov     eax, ebx
0x18001d4e2  jmp     loc_18001D8F3
0x18001d4e7  mov     qword ptr [rsp+118h+var_F8], r14; int
0x18001d4ec  lea     rax, [rsp+118h+var_F8]
0x18001d4f1  mov     qword ptr [rsp+118h+var_70], rax
0x18001d4f9  mov     qword ptr [rsp+118h+var_70+8], r14
0x18001d501  mov     [rsp+118h+var_60], 1
0x18001d509  lea     r8, [rsp+118h+var_70+8]
0x18001d511  xor     edx, edx
0x18001d513  mov     rcx, [rsp+118h+var_E8]
0x18001d518  call    cs:__imp_WwanEnumerateInterfaces
0x18001d51e  mov     ebx, eax
0x18001d520  lea     rcx, [rsp+118h+var_70]
0x18001d528  call    ??1?$out_param_ptr_t@PEAPEAUWWAN_INTERFACE_INFO_LIST@@V?$unique_ptr@UWWAN_INTERFACE_INFO_LIST@@U?$function_deleter@P6AXPEAX@Z$1?WwanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<WWAN_INTERFACE_INFO_LIST * *,wistd::unique_ptr<WWAN_INTERFACE_INFO_LIST,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>::~out_param_ptr_t<WWAN_INTERFACE_INFO_LIST * *,wistd::unique_ptr<WWAN_INTERFACE_INFO_LIST,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>(void)
0x18001d52d  test    ebx, ebx
0x18001d52f  jz      short loc_18001D576
0x18001d531  mov     rcx, [rsp+118h]; this
0x18001d539  mov     r9d, ebx; char *
0x18001d53c  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18001d543  mov     edx, 0FCh; void *
0x18001d548  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001d54d  mov     ebx, eax
0x18001d54f  mov     rcx, qword ptr [rsp+118h+var_F8]
0x18001d554  mov     qword ptr [rsp+118h+var_F8], r14
0x18001d559  test    rcx, rcx
0x18001d55c  jz      short loc_18001D565
0x18001d55e  call    cs:__imp_WwanFreeMemory
0x18001d564  nop
0x18001d565  lea     rcx, [rsp+118h+var_E8]
0x18001d56a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWwanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(void)
0x18001d56f  mov     eax, ebx
0x18001d571  jmp     loc_18001D8F3
0x18001d576  mov     esi, r14d
0x18001d579  mov     r9, qword ptr [rsp+118h+var_F8]
0x18001d57e  mov     r9d, [r9]
0x18001d581  lea     r8, aInterfacesFoun; "interfaces found=%d"
0x18001d588  mov     edx, 0FDh; unsigned int
0x18001d58d  lea     rcx, aOobeesimtaskma_1; "OobeEsimTaskManager::RunAndWaitForBoots"...
0x18001d594  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18001d599  lea     rcx, [rsp+118h+var_D8]
0x18001d59e  call    ??0?$vector@V?$ComPtr@VOobeBootstrapTask@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VOobeBootstrapTask@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<OobeBootstrapTask>>::vector<Microsoft::WRL::ComPtr<OobeBootstrapTask>>(void)
0x18001d5a3  nop
0x18001d5a4  lea     rcx, [rsp+118h+lpHandles]
0x18001d5a9  call    ??0?$vector@V?$ComPtr@VOobeBootstrapTask@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VOobeBootstrapTask@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<OobeBootstrapTask>>::vector<Microsoft::WRL::ComPtr<OobeBootstrapTask>>(void)
0x18001d5ae  nop
0x18001d5af  mov     ebx, r14d
0x18001d5b2  mov     rax, qword ptr [rsp+118h+var_F8]
0x18001d5b7  cmp     ebx, [rax]
0x18001d5b9  jnb     loc_18001D708
0x18001d5bf  mov     ecx, ebx
0x18001d5c1  imul    rdx, rcx, 24Ch
0x18001d5c8  movups  xmm0, xmmword ptr [rdx+rax+4]
0x18001d5cd  movdqu  [rsp+118h+var_70], xmm0
0x18001d5d6  xor     r9d, r9d; lpName
0x18001d5d9  xor     r8d, r8d; bInitialState
0x18001d5dc  xor     edx, edx; bManualReset
0x18001d5de  xor     ecx, ecx; lpEventAttributes
0x18001d5e0  call    cs:__imp_CreateEventW
0x18001d5e6  mov     [rsp+118h+var_E0], rax
0x18001d5eb  mov     [rsp+118h+var_C0], r14
0x18001d5f0  lea     rax, [rsp+118h+var_E0]
0x18001d5f5  mov     [rsp+118h+var_A0], rax
0x18001d5fa  lea     rcx, [rsp+118h+var_C0]
0x18001d5ff  call    ?InternalRelease@?$ComPtr@VOobeBootstrapTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OobeBootstrapTask>::InternalRelease(void)
0x18001d604  lea     r8, [rsp+118h+var_A0]
0x18001d609  lea     rdx, [rsp+118h+var_70]
0x18001d611  lea     rcx, [rsp+118h+var_C0]
0x18001d616  call    ??$MakeAndInitialize@VOobeBootstrapTask@@V1@AEBU_GUID@@PEAPEAX@Details@WRL@Microsoft@@YAJPEAPEAVOobeBootstrapTask@@AEBU_GUID@@$$QEAPEAPEAX@Z; Microsoft::WRL::Details::MakeAndInitialize<OobeBootstrapTask,OobeBootstrapTask,_GUID const &,void * *>(OobeBootstrapTask * *,_GUID const &,void * * &&)
0x18001d61b  mov     esi, eax
0x18001d61d  mov     rcx, [rsp+118h]; this
0x18001d625  test    eax, eax
0x18001d627  jns     short loc_18001D642
0x18001d629  mov     r9d, eax; char *
0x18001d62c  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18001d633  mov     edx, 109h; void *
0x18001d638  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d63d  jmp     loc_18001D6F7
0x18001d642  lea     rdx, [rsp+118h+var_70]
0x18001d64a  lea     rcx, [rsp+118h+var_98]; char *
0x18001d652  call    ?MbLoggingHelperGuidToString@@YA?AV?$array@D$0CD@@std@@AEBU_GUID@@@Z; MbLoggingHelperGuidToString(_GUID const &)
0x18001d657  movups  xmm0, xmmword ptr [rax]
0x18001d65a  movups  [rsp+118h+var_58], xmm0
0x18001d662  movups  xmm1, xmmword ptr [rax+10h]
0x18001d666  movups  xmmword ptr [rsp+118h+var_48], xmm1
0x18001d66e  mov     eax, [rax+1Fh]
0x18001d671  mov     dword ptr [rsp+118h+var_48+0Fh], eax
0x18001d678  lea     r9, [rsp+118h+var_58]
0x18001d680  lea     r8, aCreatedTaskFor; "Created task for interface. guidId=%hs"
0x18001d687  mov     edx, 10Eh; unsigned int
0x18001d68c  lea     rcx, aOobeesimtaskma_1; "OobeEsimTaskManager::RunAndWaitForBoots"...
0x18001d693  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18001d698  mov     rdx, qword ptr [rsp+118h+var_D8+8]
0x18001d69d  cmp     rdx, [rsp+118h+var_C8]
0x18001d6a2  jz      short loc_18001D6BC
0x18001d6a4  mov     rax, [rsp+118h+var_C0]
0x18001d6a9  mov     [rdx], rax
0x18001d6ac  mov     rcx, rdx
0x18001d6af  call    ?InternalAddRef@?$ComPtr@VOobeBootstrapTask@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<OobeBootstrapTask>::InternalAddRef(void)
0x18001d6b4  add     qword ptr [rsp+118h+var_D8+8], 8
0x18001d6ba  jmp     short loc_18001D6CB
0x18001d6bc  lea     r8, [rsp+118h+var_C0]
0x18001d6c1  lea     rcx, [rsp+118h+var_D8]
0x18001d6c6  call    ??$_Emplace_reallocate@AEBV?$ComPtr@VOobeBootstrapTask@@@WRL@Microsoft@@@?$vector@V?$ComPtr@VOobeBootstrapTask@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VOobeBootstrapTask@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@VOobeBootstrapTask@@@WRL@Microsoft@@QEAV234@AEBV234@@Z; std::vector<Microsoft::WRL::ComPtr<OobeBootstrapTask>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<OobeBootstrapTask> const &>(Microsoft::WRL::ComPtr<OobeBootstrapTask> * const,Microsoft::WRL::ComPtr<OobeBootstrapTask> const &)
0x18001d6cb  mov     rdx, [rsp+118h+lpHandles+8]
0x18001d6d0  cmp     rdx, [rsp+118h+var_A8]
0x18001d6d5  jz      short loc_18001D6E7
0x18001d6d7  mov     rax, [rsp+118h+var_E0]
0x18001d6dc  mov     [rdx], rax
0x18001d6df  add     [rsp+118h+lpHandles+8], 8
0x18001d6e5  jmp     short loc_18001D6F7
0x18001d6e7  lea     r8, [rsp+118h+var_E0]
0x18001d6ec  lea     rcx, [rsp+118h+lpHandles]
0x18001d6f1  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x18001d6f6  nop
0x18001d6f7  lea     rcx, [rsp+118h+var_C0]
0x18001d6fc  call    ?InternalRelease@?$ComPtr@VOobeBootstrapTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OobeBootstrapTask>::InternalRelease(void)
0x18001d701  inc     ebx
0x18001d703  jmp     loc_18001D5B2
0x18001d708  mov     rdx, [rsp+118h+lpHandles]; lpHandles
0x18001d70d  mov     rcx, [rsp+118h+lpHandles+8]
0x18001d712  sub     rcx, rdx
0x18001d715  sar     rcx, 3; nCount
0x18001d719  test    rcx, rcx
0x18001d71c  jz      loc_18001D819
0x18001d722  mov     r9d, 15F90h; dwMilliseconds
0x18001d728  mov     r8d, 1; bWaitAll
0x18001d72e  call    cs:__imp_WaitForMultipleObjects
0x18001d734  cmp     eax, 102h
0x18001d739  jnz     short loc_18001D756
0x18001d73b  lea     r8, aWaitformultipl; "WaitForMultipleObjects Timed Out"
0x18001d742  lea     edx, [rax+19h]; unsigned int
0x18001d745  lea     rcx, aOobeesimtaskma_1; "OobeEsimTaskManager::RunAndWaitForBoots"...
0x18001d74c  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18001d751  jmp     loc_18001D819
0x18001d756  cmp     eax, 0FFFFFFFFh
0x18001d759  jnz     loc_18001D819
0x18001d75f  call    cs:__imp_GetLastError
0x18001d765  mov     ebx, eax
0x18001d767  test    eax, eax
0x18001d769  jle     short loc_18001D774
0x18001d76b  movzx   ebx, ax
0x18001d76e  or      ebx, 80070000h
0x18001d774  mov     rcx, [rsp+118h]; this
0x18001d77c  mov     r9d, ebx; char *
0x18001d77f  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18001d786  mov     edx, 121h; void *
0x18001d78b  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001d790  nop
0x18001d791  mov     rcx, [rsp+118h+lpHandles]
0x18001d796  test    rcx, rcx
0x18001d799  jz      short loc_18001D7BA
0x18001d79b  mov     rdx, [rsp+118h+var_A8]
0x18001d7a0  sub     rdx, rcx
0x18001d7a3  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001d7a7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001d7ac  xorps   xmm0, xmm0
0x18001d7af  movdqu  xmmword ptr [rsp+118h+lpHandles], xmm0
0x18001d7b5  mov     [rsp+118h+var_A8], r14
0x18001d7ba  mov     rcx, qword ptr [rsp+118h+var_D8]
0x18001d7bf  test    rcx, rcx
0x18001d7c2  jz      short loc_18001D7F2
0x18001d7c4  mov     rdx, qword ptr [rsp+118h+var_D8+8]
0x18001d7c9  call    ??$_Destroy_range@V?$allocator@V?$ComPtr@VOobeBootstrapTask@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@VOobeBootstrapTask@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@VOobeBootstrapTask@@@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<OobeBootstrapTask>>>(Microsoft::WRL::ComPtr<OobeBootstrapTask> *,Microsoft::WRL::ComPtr<OobeBootstrapTask> * const,std::allocator<Microsoft::WRL::ComPtr<OobeBootstrapTask>> &)
0x18001d7ce  mov     rcx, qword ptr [rsp+118h+var_D8]
0x18001d7d3  mov     rdx, [rsp+118h+var_C8]
0x18001d7d8  sub     rdx, rcx
0x18001d7db  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001d7df  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001d7e4  xorps   xmm0, xmm0
0x18001d7e7  movdqu  [rsp+118h+var_D8], xmm0
0x18001d7ed  mov     [rsp+118h+var_C8], r14
0x18001d7f2  mov     rcx, qword ptr [rsp+118h+var_F8]
0x18001d7f7  mov     qword ptr [rsp+118h+var_F8], r14
0x18001d7fc  test    rcx, rcx
0x18001d7ff  jz      short loc_18001D808
0x18001d801  call    cs:__imp_WwanFreeMemory
0x18001d807  nop
0x18001d808  lea     rcx, [rsp+118h+var_E8]
0x18001d80d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWwanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(void)
0x18001d812  mov     eax, ebx
0x18001d814  jmp     loc_18001D8F3
0x18001d819  mov     rbx, qword ptr [rsp+118h+var_D8]
0x18001d81e  cmp     rbx, qword ptr [rsp+118h+var_D8+8]
0x18001d823  jz      short loc_18001D851
0x18001d825  mov     r9, [rbx]
0x18001d828  mov     [rsp+118h+var_E0], r9
0x18001d82d  lea     rcx, [rsp+118h+var_E0]
0x18001d832  call    ?InternalAddRef@?$ComPtr@VOobeBootstrapTask@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<OobeBootstrapTask>::InternalAddRef(void)
0x18001d837  cmp     dword ptr [r9+60h], 3
0x18001d83c  jnz     short loc_18001D841
0x18001d83e  mov     byte ptr [rdi], 1
0x18001d841  lea     rcx, [rsp+118h+var_E0]
0x18001d846  call    ?InternalRelease@?$ComPtr@VOobeBootstrapTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OobeBootstrapTask>::InternalRelease(void)
0x18001d84b  add     rbx, 8
0x18001d84f  jmp     short loc_18001D81E
0x18001d851  lea     r8, aTaskComplete; "Task Complete"
0x18001d858  mov     edx, 12Fh; unsigned int
0x18001d85d  lea     rcx, aOobeesimtaskma_1; "OobeEsimTaskManager::RunAndWaitForBoots"...
0x18001d864  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18001d869  nop
0x18001d86a  mov     rcx, [rsp+118h+lpHandles]
0x18001d86f  test    rcx, rcx
0x18001d872  jz      short loc_18001D893
0x18001d874  mov     rdx, [rsp+118h+var_A8]
0x18001d879  sub     rdx, rcx
0x18001d87c  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001d880  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001d885  xorps   xmm0, xmm0
0x18001d888  movdqu  xmmword ptr [rsp+118h+lpHandles], xmm0
0x18001d88e  mov     [rsp+118h+var_A8], r14
0x18001d893  mov     rcx, qword ptr [rsp+118h+var_D8]
0x18001d898  test    rcx, rcx
0x18001d89b  jz      short loc_18001D8CB
0x18001d89d  mov     rdx, qword ptr [rsp+118h+var_D8+8]
0x18001d8a2  call    ??$_Destroy_range@V?$allocator@V?$ComPtr@VOobeBootstrapTask@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@VOobeBootstrapTask@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@VOobeBootstrapTask@@@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<OobeBootstrapTask>>>(Microsoft::WRL::ComPtr<OobeBootstrapTask> *,Microsoft::WRL::ComPtr<OobeBootstrapTask> * const,std::allocator<Microsoft::WRL::ComPtr<OobeBootstrapTask>> &)
0x18001d8a7  mov     rcx, qword ptr [rsp+118h+var_D8]
0x18001d8ac  mov     rdx, [rsp+118h+var_C8]
0x18001d8b1  sub     rdx, rcx
0x18001d8b4  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001d8b8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001d8bd  xorps   xmm0, xmm0
0x18001d8c0  movdqu  [rsp+118h+var_D8], xmm0
0x18001d8c6  mov     [rsp+118h+var_C8], r14
0x18001d8cb  mov     rcx, qword ptr [rsp+118h+var_F8]
0x18001d8d0  mov     qword ptr [rsp+118h+var_F8], r14
0x18001d8d5  test    rcx, rcx
0x18001d8d8  jz      short loc_18001D8E1
0x18001d8da  call    cs:__imp_WwanFreeMemory
0x18001d8e0  nop
0x18001d8e1  lea     rcx, [rsp+118h+var_E8]
0x18001d8e6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWwanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(void)
0x18001d8eb  mov     eax, esi
0x18001d8ed  jmp     short loc_18001D8F3
0x18001d8ef  mov     eax, [rsp+118h+var_F0]
0x18001d8f3  mov     rcx, [rsp+118h+var_30]
0x18001d8fb  xor     rcx, rsp; StackCookie
0x18001d8fe  call    __security_check_cookie
0x18001d903  add     rsp, 0F8h
0x18001d90a  pop     r14
0x18001d90c  pop     rdi
0x18001d90d  pop     rsi
0x18001d90e  pop     rbx
0x18001d90f  retn
```
