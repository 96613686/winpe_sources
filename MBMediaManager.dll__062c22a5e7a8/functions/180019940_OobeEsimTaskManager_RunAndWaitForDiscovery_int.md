# OobeEsimTaskManager::RunAndWaitForDiscovery(int)

- ea: `0x180019940`
- end: `0x180019d4c`
- name: `?RunAndWaitForDiscovery@OobeEsimTaskManager@@AEAAJH@Z`
- size: `1036`
- prototype: `__int64 __fastcall(OobeEsimTaskManager *this)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180036690`

## callees

- `0x180007330`
- `0x180009150`
- `0x18000ad20`
- `0x18000fe58`
- `0x180016bb0`
- `0x180017ac4`
- `0x180019940`
- `0x180019d54`
- `0x180019d78`
- `0x18001b1d4`
- `0x18001bdb8`
- `0x180023018`
- `0x18002cd20`
- `0x180034a74`
- `0x180034d2c`
- `0x180035c60`
- `0x180036a68`
- `0x180049f70`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180019c7e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180019c7e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180019a47`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180019d12`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180019a47`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180019d12`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18001998b`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18001998b`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanEnumerateInterfaces` at `0x1800199fd`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanEnumerateInterfaces` at `0x1800199fd`

## string_xrefs

- `0x1800199a0`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x180019a21`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x180019aed`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x180019cae`: `Task Complete`
- `0x180019a76`: `OobeEsimTaskManager::RunAndWaitForDiscovery`
- `0x180019b3e`: `Created task for interface. guidId=%hs`
- `0x180019c4d`: `Removing task due to Complete/ExitEarly/Error state. easyConnectTasks left=%d`
- `0x180019c22`: `Removing task due maxDiscoveryWait exceeded. easyConnectTasks left=%d`

## pseudocode

```c
__int64 __fastcall OobeEsimTaskManager::RunAndWaitForDiscovery(OobeEsimTaskManager *this)
{
  unsigned int v1; // eax
  unsigned int v2; // ebx
  unsigned int v4; // ebx
  unsigned int v5; // ebx
  unsigned int *v6; // rcx
  unsigned int v7; // r14d
  volatile int *v8; // rdx
  unsigned int i; // ebx
  int v10; // eax
  __int64 v11; // rax
  volatile int *v12; // rdx
  __int64 v13; // rcx
  char v14; // si
  int v15; // edi
  volatile int *v16; // rbx
  volatile int *v17; // rax
  _DWORD *v18; // r8
  int v19; // ecx
  unsigned int *v20; // rcx
  int v21[2]; // [rsp+20h] [rbp-D8h] BYREF
  int v22; // [rsp+28h] [rbp-D0h] BYREF
  unsigned int *v23; // [rsp+30h] [rbp-C8h] BYREF
  __int64 v24; // [rsp+38h] [rbp-C0h] BYREF
  volatile int *v25[2]; // [rsp+40h] [rbp-B8h] BYREF
  volatile int *v26; // [rsp+50h] [rbp-A8h]
  _BYTE v27[8]; // [rsp+58h] [rbp-A0h] BYREF
  char v28[40]; // [rsp+60h] [rbp-98h] BYREF
  __int128 v29; // [rsp+88h] [rbp-70h] BYREF
  char v30; // [rsp+98h] [rbp-60h]
  __int128 v31; // [rsp+A0h] [rbp-58h] BYREF
  _BYTE v32[19]; // [rsp+B0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v24 = -1;
  v22 = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::reset(&v24);
  v1 = WwanOpenHandle(1, 0, &v22, &v24);
  if ( v1 )
  {
    v2 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x9D,
           (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
           (const char *)v1,
           v21[0]);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(&v24);
    return v2;
  }
  else
  {
    v23 = 0;
    v29 = (unsigned __int64)&v23;
    v30 = 1;
    v4 = WwanEnumerateInterfaces(v24, 0, (char *)&v29 + 8);
    wil::details::out_param_ptr_t<WWAN_INTERFACE_INFO_LIST * *,wistd::unique_ptr<WWAN_INTERFACE_INFO_LIST,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>::~out_param_ptr_t<WWAN_INTERFACE_INFO_LIST * *,wistd::unique_ptr<WWAN_INTERFACE_INFO_LIST,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>(&v29);
    if ( v4 )
    {
      v5 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xA0,
             (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
             (const char *)v4,
             v21[0]);
      v6 = v23;
      v23 = 0;
      if ( v6 )
        WwanFreeMemory(v6);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(&v24);
      return v5;
    }
    else
    {
      v7 = 0;
      MBSettingUXLogging::Info("OobeEsimTaskManager::RunAndWaitForDiscovery", 0xA1u, "interfaces found=%d", *v23);
      std::vector<Microsoft::WRL::ComPtr<OobeBootstrapTask>>::vector<Microsoft::WRL::ComPtr<OobeBootstrapTask>>(v25);
      for ( i = 0; i < *v23; ++i )
      {
        v29 = *(_OWORD *)&v23[147 * i + 1];
        *(_QWORD *)v21 = 0;
        Microsoft::WRL::ComPtr<OobeEasyConnectTask>::InternalRelease(v21);
        v10 = Microsoft::WRL::Details::MakeAndInitialize<OobeEasyConnectTask,OobeEasyConnectTask,_GUID const &>(
                v21,
                &v29);
        v7 = v10;
        if ( v10 >= 0 )
        {
          v11 = MbLoggingHelperGuidToString(v28);
          v31 = *(_OWORD *)v11;
          *(_OWORD *)v32 = *(_OWORD *)(v11 + 16);
          *(_DWORD *)&v32[15] = *(_DWORD *)(v11 + 31);
          MBSettingUXLogging::Info(
            "OobeEsimTaskManager::RunAndWaitForDiscovery",
            0xB0u,
            "Created task for interface. guidId=%hs",
            (const char *)&v31);
          v12 = v25[1];
          if ( v25[1] == v26 )
          {
            std::vector<Microsoft::WRL::ComPtr<OobeEasyConnectTask>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<OobeEasyConnectTask> const &>(
              v25,
              v25[1],
              v21);
          }
          else
          {
            v13 = *(_QWORD *)v21;
            *(_QWORD *)v25[1] = *(_QWORD *)v21;
            if ( v13 )
              Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(v13 + 20), v12);
            v25[1] += 2;
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xAB,
            (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
            (const char *)(unsigned int)v10,
            v21[0]);
        }
        Microsoft::WRL::ComPtr<OobeEasyConnectTask>::InternalRelease(v21);
      }
      v14 = 0;
      v15 = 0;
      while ( 1 )
      {
        v16 = v25[0];
        v17 = v25[1];
        if ( v25[0] == v25[1] )
          break;
        while ( v16 != v17 )
        {
          v18 = *(_DWORD **)v16;
          *(_QWORD *)v21 = v18;
          if ( v18 )
            Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(v18 + 5), v8);
          v19 = v18[24];
          if ( (unsigned int)(v19 - 5) <= 2 )
          {
            OobeEasyConnectTask::Uninitialize((OobeEasyConnectTask *)v18);
            std::vector<Microsoft::WRL::ComPtr<OobeEasyConnectTask>>::erase(v25, &v29, v16);
            MBSettingUXLogging::Info(
              "OobeEsimTaskManager::RunAndWaitForDiscovery",
              0xC3u,
              "Removing task due to Complete/ExitEarly/Error state. easyConnectTasks left=%d",
              ((char *)v25[1] - (char *)v25[0]) >> 3);
            goto LABEL_29;
          }
          if ( (unsigned int)(v19 - 1) <= 3 )
          {
            if ( v15 > 3600 )
            {
              OobeEasyConnectTask::Uninitialize((OobeEasyConnectTask *)v18);
              std::vector<Microsoft::WRL::ComPtr<OobeEasyConnectTask>>::erase(v25, v27, v16);
              MBSettingUXLogging::Info(
                "OobeEsimTaskManager::RunAndWaitForDiscovery",
                0xD1u,
                "Removing task due maxDiscoveryWait exceeded. easyConnectTasks left=%d",
                ((char *)v25[1] - (char *)v25[0]) >> 3);
LABEL_29:
              Microsoft::WRL::ComPtr<OobeEasyConnectTask>::InternalRelease(v21);
              break;
            }
            v14 = 1;
          }
          Microsoft::WRL::ComPtr<OobeEasyConnectTask>::InternalRelease(v21);
          v16 += 2;
          v17 = v25[1];
        }
        Sleep(0x3E8u);
        if ( v14 )
        {
          ++v15;
          v14 = 0;
          MBSettingUXLogging::Info(
            "OobeEsimTaskManager::RunAndWaitForDiscovery",
            0xE2u,
            "discoveryWaitTimeInSeconds increased to: %d",
            v15);
        }
      }
      MBSettingUXLogging::Info("OobeEsimTaskManager::RunAndWaitForDiscovery", 0xE6u, "Task Complete");
      if ( v25[0] )
      {
        std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<OobeEasyConnectTask>>>(v25[0], v25[1]);
        std::_Deallocate<16>(v25[0], ((char *)v26 - (char *)v25[0]) & 0xFFFFFFFFFFFFFFF8uLL);
        *(_OWORD *)v25 = 0;
        v26 = 0;
      }
      v20 = v23;
      v23 = 0;
      if ( v20 )
        WwanFreeMemory(v20);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(&v24);
      return v7;
    }
  }
}

```

## disassembly

```asm
0x180019940  push    rbx
0x180019942  push    rsi
0x180019943  push    rdi
0x180019944  push    r12
0x180019946  push    r14
0x180019948  sub     rsp, 0D0h
0x18001994f  mov     rax, cs:__security_cookie
0x180019956  xor     rax, rsp
0x180019959  mov     [rsp+0F8h+var_30], rax
0x180019961  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180019965  mov     [rsp+0F8h+var_C0], rdx
0x18001996a  mov     [rsp+0F8h+var_D0], 0
0x180019972  lea     rcx, [rsp+0F8h+var_C0]
0x180019977  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWwanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::reset(void *)
0x18001997c  lea     r9, [rsp+0F8h+var_C0]
0x180019981  lea     r8, [rsp+0F8h+var_D0]
0x180019986  xor     edx, edx
0x180019988  lea     ecx, [rdx+1]
0x18001998b  call    cs:__imp_WwanOpenHandle
0x180019991  test    eax, eax
0x180019993  jz      short loc_1800199C4
0x180019995  mov     rcx, [rsp+0F8h]; this
0x18001999d  mov     r9d, eax; char *
0x1800199a0  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x1800199a7  mov     edx, 9Dh; void *
0x1800199ac  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800199b1  mov     ebx, eax
0x1800199b3  lea     rcx, [rsp+0F8h+var_C0]
0x1800199b8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWwanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(void)
0x1800199bd  mov     eax, ebx
0x1800199bf  jmp     loc_180019D2C
0x1800199c4  mov     [rsp+0F8h+var_C8], 0
0x1800199cd  lea     rax, [rsp+0F8h+var_C8]
0x1800199d2  mov     qword ptr [rsp+0F8h+var_70], rax
0x1800199da  mov     qword ptr [rsp+0F8h+var_70+8], 0
0x1800199e6  mov     [rsp+0F8h+var_60], 1
0x1800199ee  lea     r8, [rsp+0F8h+var_70+8]
0x1800199f6  xor     edx, edx
0x1800199f8  mov     rcx, [rsp+0F8h+var_C0]
0x1800199fd  call    cs:__imp_WwanEnumerateInterfaces
0x180019a03  mov     ebx, eax
0x180019a05  lea     rcx, [rsp+0F8h+var_70]
0x180019a0d  call    ??1?$out_param_ptr_t@PEAPEAUWWAN_INTERFACE_INFO_LIST@@V?$unique_ptr@UWWAN_INTERFACE_INFO_LIST@@U?$function_deleter@P6AXPEAX@Z$1?WwanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<WWAN_INTERFACE_INFO_LIST * *,wistd::unique_ptr<WWAN_INTERFACE_INFO_LIST,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>::~out_param_ptr_t<WWAN_INTERFACE_INFO_LIST * *,wistd::unique_ptr<WWAN_INTERFACE_INFO_LIST,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>(void)
0x180019a12  test    ebx, ebx
0x180019a14  jz      short loc_180019A5F
0x180019a16  mov     rcx, [rsp+0F8h]; this
0x180019a1e  mov     r9d, ebx; char *
0x180019a21  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x180019a28  mov     edx, 0A0h; void *
0x180019a2d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180019a32  mov     ebx, eax
0x180019a34  mov     rcx, [rsp+0F8h+var_C8]
0x180019a39  mov     [rsp+0F8h+var_C8], 0
0x180019a42  test    rcx, rcx
0x180019a45  jz      short loc_180019A4E
0x180019a47  call    cs:__imp_WwanFreeMemory
0x180019a4d  nop
0x180019a4e  lea     rcx, [rsp+0F8h+var_C0]
0x180019a53  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWwanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(void)
0x180019a58  mov     eax, ebx
0x180019a5a  jmp     loc_180019D2C
0x180019a5f  xor     r14d, r14d
0x180019a62  mov     r9, [rsp+0F8h+var_C8]
0x180019a67  mov     r9d, [r9]
0x180019a6a  lea     r8, aInterfacesFoun; "interfaces found=%d"
0x180019a71  mov     edx, 0A1h; unsigned int
0x180019a76  lea     r12, aOobeesimtaskma_0; "OobeEsimTaskManager::RunAndWaitForDisco"...
0x180019a7d  mov     rcx, r12; char *
0x180019a80  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180019a85  lea     rcx, [rsp+0F8h+var_B8]
0x180019a8a  call    ??0?$vector@V?$ComPtr@VOobeBootstrapTask@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VOobeBootstrapTask@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<OobeBootstrapTask>>::vector<Microsoft::WRL::ComPtr<OobeBootstrapTask>>(void)
0x180019a8f  nop
0x180019a90  xor     ebx, ebx
0x180019a92  mov     rax, [rsp+0F8h+var_C8]
0x180019a97  cmp     ebx, [rax]
0x180019a99  jnb     loc_180019B9D
0x180019a9f  mov     ecx, ebx
0x180019aa1  imul    rdx, rcx, 24Ch
0x180019aa8  movups  xmm0, xmmword ptr [rdx+rax+4]
0x180019aad  movdqu  [rsp+0F8h+var_70], xmm0
0x180019ab6  mov     qword ptr [rsp+0F8h+var_D8], 0; int
0x180019abf  lea     rcx, [rsp+0F8h+var_D8]
0x180019ac4  call    ?InternalRelease@?$ComPtr@VOobeEasyConnectTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OobeEasyConnectTask>::InternalRelease(void)
0x180019ac9  lea     rdx, [rsp+0F8h+var_70]
0x180019ad1  lea     rcx, [rsp+0F8h+var_D8]
0x180019ad6  call    ??$MakeAndInitialize@VOobeEasyConnectTask@@V1@AEBU_GUID@@@Details@WRL@Microsoft@@YAJPEAPEAVOobeEasyConnectTask@@AEBU_GUID@@@Z; Microsoft::WRL::Details::MakeAndInitialize<OobeEasyConnectTask,OobeEasyConnectTask,_GUID const &>(OobeEasyConnectTask * *,_GUID const &)
0x180019adb  mov     r14d, eax
0x180019ade  mov     rcx, [rsp+0F8h]; this
0x180019ae6  test    eax, eax
0x180019ae8  jns     short loc_180019B03
0x180019aea  mov     r9d, eax; char *
0x180019aed  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x180019af4  mov     edx, 0ABh; void *
0x180019af9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180019afe  jmp     loc_180019B8C
0x180019b03  lea     rdx, [rsp+0F8h+var_70]
0x180019b0b  lea     rcx, [rsp+0F8h+var_98]; char *
0x180019b10  call    ?MbLoggingHelperGuidToString@@YA?AV?$array@D$0CD@@std@@AEBU_GUID@@@Z; MbLoggingHelperGuidToString(_GUID const &)
0x180019b15  movups  xmm0, xmmword ptr [rax]
0x180019b18  movups  [rsp+0F8h+var_58], xmm0
0x180019b20  movups  xmm1, xmmword ptr [rax+10h]
0x180019b24  movups  xmmword ptr [rsp+0F8h+var_48], xmm1
0x180019b2c  mov     eax, [rax+1Fh]
0x180019b2f  mov     dword ptr [rsp+0F8h+var_48+0Fh], eax
0x180019b36  lea     r9, [rsp+0F8h+var_58]
0x180019b3e  lea     r8, aCreatedTaskFor; "Created task for interface. guidId=%hs"
0x180019b45  mov     edx, 0B0h; unsigned int
0x180019b4a  mov     rcx, r12; char *
0x180019b4d  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180019b52  mov     rdx, [rsp+0F8h+var_B8+8]; volatile int *
0x180019b57  cmp     rdx, [rsp+0F8h+var_A8]
0x180019b5c  jz      short loc_180019B7C
0x180019b5e  mov     rcx, qword ptr [rsp+0F8h+var_D8]
0x180019b63  mov     [rdx], rcx
0x180019b66  test    rcx, rcx
0x180019b69  jz      short loc_180019B74
0x180019b6b  add     rcx, 14h; this
0x180019b6f  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x180019b74  add     [rsp+0F8h+var_B8+8], 8
0x180019b7a  jmp     short loc_180019B8C
0x180019b7c  lea     r8, [rsp+0F8h+var_D8]
0x180019b81  lea     rcx, [rsp+0F8h+var_B8]
0x180019b86  call    ??$_Emplace_reallocate@AEBV?$ComPtr@VOobeEasyConnectTask@@@WRL@Microsoft@@@?$vector@V?$ComPtr@VOobeEasyConnectTask@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VOobeEasyConnectTask@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@VOobeEasyConnectTask@@@WRL@Microsoft@@QEAV234@AEBV234@@Z; std::vector<Microsoft::WRL::ComPtr<OobeEasyConnectTask>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<OobeEasyConnectTask> const &>(Microsoft::WRL::ComPtr<OobeEasyConnectTask> * const,Microsoft::WRL::ComPtr<OobeEasyConnectTask> const &)
0x180019b8b  nop
0x180019b8c  lea     rcx, [rsp+0F8h+var_D8]
0x180019b91  call    ?InternalRelease@?$ComPtr@VOobeEasyConnectTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OobeEasyConnectTask>::InternalRelease(void)
0x180019b96  inc     ebx
0x180019b98  jmp     loc_180019A92
0x180019b9d  xor     sil, sil
0x180019ba0  xor     edi, edi
0x180019ba2  mov     rbx, [rsp+0F8h+var_B8]
0x180019ba7  mov     rax, [rsp+0F8h+var_B8+8]
0x180019bac  cmp     rbx, rax
0x180019baf  jz      loc_180019CAE
0x180019bb5  cmp     rbx, rax
0x180019bb8  jz      loc_180019C79
0x180019bbe  mov     r8, [rbx]
0x180019bc1  mov     qword ptr [rsp+0F8h+var_D8], r8
0x180019bc6  test    r8, r8
0x180019bc9  jz      short loc_180019BD4
0x180019bcb  lea     rcx, [r8+14h]; this
0x180019bcf  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x180019bd4  mov     ecx, [r8+60h]
0x180019bd8  lea     eax, [rcx-5]
0x180019bdb  cmp     eax, 2
0x180019bde  jbe     short loc_180019C30
0x180019be0  lea     eax, [rcx-1]
0x180019be3  cmp     eax, 3
0x180019be6  ja      short loc_180019BF3
0x180019be8  cmp     edi, 0E10h
0x180019bee  jg      short loc_180019C08
0x180019bf0  mov     sil, 1
0x180019bf3  lea     rcx, [rsp+0F8h+var_D8]
0x180019bf8  call    ?InternalRelease@?$ComPtr@VOobeEasyConnectTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OobeEasyConnectTask>::InternalRelease(void)
0x180019bfd  add     rbx, 8
0x180019c01  mov     rax, [rsp+0F8h+var_B8+8]
0x180019c06  jmp     short loc_180019BB5
0x180019c08  mov     rcx, r8; this
0x180019c0b  call    ?Uninitialize@OobeEasyConnectTask@@QEAAJXZ; OobeEasyConnectTask::Uninitialize(void)
0x180019c10  mov     r8, rbx
0x180019c13  lea     rdx, [rsp+0F8h+var_A0]
0x180019c18  lea     rcx, [rsp+0F8h+var_B8]
0x180019c1d  call    ?erase@?$vector@V?$ComPtr@VOobeEasyConnectTask@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VOobeEasyConnectTask@@@WRL@Microsoft@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$ComPtr@VOobeEasyConnectTask@@@WRL@Microsoft@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$ComPtr@VOobeEasyConnectTask@@@WRL@Microsoft@@@std@@@std@@@2@@Z; std::vector<Microsoft::WRL::ComPtr<OobeEasyConnectTask>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<Microsoft::WRL::ComPtr<OobeEasyConnectTask>>>>)
0x180019c22  lea     r8, aRemovingTaskDu; "Removing task due maxDiscoveryWait exce"...
0x180019c29  mov     edx, 0D1h
0x180019c2e  jmp     short loc_180019C59
0x180019c30  mov     rcx, r8; this
0x180019c33  call    ?Uninitialize@OobeEasyConnectTask@@QEAAJXZ; OobeEasyConnectTask::Uninitialize(void)
0x180019c38  mov     r8, rbx
0x180019c3b  lea     rdx, [rsp+0F8h+var_70]
0x180019c43  lea     rcx, [rsp+0F8h+var_B8]
0x180019c48  call    ?erase@?$vector@V?$ComPtr@VOobeEasyConnectTask@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VOobeEasyConnectTask@@@WRL@Microsoft@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$ComPtr@VOobeEasyConnectTask@@@WRL@Microsoft@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$ComPtr@VOobeEasyConnectTask@@@WRL@Microsoft@@@std@@@std@@@2@@Z; std::vector<Microsoft::WRL::ComPtr<OobeEasyConnectTask>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<Microsoft::WRL::ComPtr<OobeEasyConnectTask>>>>)
0x180019c4d  lea     r8, aRemovingTaskDu_0; "Removing task due to Complete/ExitEarly"...
0x180019c54  mov     edx, 0C3h; unsigned int
0x180019c59  mov     r9, [rsp+0F8h+var_B8+8]
0x180019c5e  sub     r9, [rsp+0F8h+var_B8]
0x180019c63  sar     r9, 3
0x180019c67  mov     rcx, r12; char *
0x180019c6a  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180019c6f  lea     rcx, [rsp+0F8h+var_D8]
0x180019c74  call    ?InternalRelease@?$ComPtr@VOobeEasyConnectTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OobeEasyConnectTask>::InternalRelease(void)
0x180019c79  mov     ecx, 3E8h; dwMilliseconds
0x180019c7e  call    cs:__imp_Sleep
0x180019c84  test    sil, sil
0x180019c87  jz      loc_180019BA2
0x180019c8d  inc     edi
0x180019c8f  xor     sil, sil
0x180019c92  mov     r9d, edi
0x180019c95  lea     r8, aDiscoverywaitt; "discoveryWaitTimeInSeconds increased to"...
0x180019c9c  mov     edx, 0E2h; unsigned int
0x180019ca1  mov     rcx, r12; char *
0x180019ca4  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180019ca9  jmp     loc_180019BA2
0x180019cae  lea     r8, aTaskComplete; "Task Complete"
0x180019cb5  mov     edx, 0E6h; unsigned int
0x180019cba  mov     rcx, r12; char *
0x180019cbd  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180019cc2  nop
0x180019cc3  mov     rcx, [rsp+0F8h+var_B8]
0x180019cc8  test    rcx, rcx
0x180019ccb  jz      short loc_180019CFF
0x180019ccd  mov     rdx, [rsp+0F8h+var_B8+8]
0x180019cd2  call    ??$_Destroy_range@V?$allocator@V?$ComPtr@VOobeEasyConnectTask@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@VOobeEasyConnectTask@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@VOobeEasyConnectTask@@@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<OobeEasyConnectTask>>>(Microsoft::WRL::ComPtr<OobeEasyConnectTask> *,Microsoft::WRL::ComPtr<OobeEasyConnectTask> * const,std::allocator<Microsoft::WRL::ComPtr<OobeEasyConnectTask>> &)
0x180019cd7  mov     rcx, [rsp+0F8h+var_B8]
0x180019cdc  mov     rdx, [rsp+0F8h+var_A8]
0x180019ce1  sub     rdx, rcx
0x180019ce4  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180019ce8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180019ced  xorps   xmm0, xmm0
0x180019cf0  movdqu  xmmword ptr [rsp+0F8h+var_B8], xmm0
0x180019cf6  mov     [rsp+0F8h+var_A8], 0
0x180019cff  mov     rcx, [rsp+0F8h+var_C8]
0x180019d04  mov     [rsp+0F8h+var_C8], 0
0x180019d0d  test    rcx, rcx
0x180019d10  jz      short loc_180019D19
0x180019d12  call    cs:__imp_WwanFreeMemory
0x180019d18  nop
0x180019d19  lea     rcx, [rsp+0F8h+var_C0]
0x180019d1e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWwanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(void)
0x180019d23  mov     eax, r14d
0x180019d26  jmp     short loc_180019D2C
0x180019d28  mov     eax, [rsp+0F8h+var_D0]
0x180019d2c  mov     rcx, [rsp+0F8h+var_30]
0x180019d34  xor     rcx, rsp; StackCookie
0x180019d37  call    __security_check_cookie
0x180019d3c  add     rsp, 0D0h
0x180019d43  pop     r14
0x180019d45  pop     r12
0x180019d47  pop     rdi
0x180019d48  pop     rsi
0x180019d49  pop     rbx
0x180019d4a  retn
```
