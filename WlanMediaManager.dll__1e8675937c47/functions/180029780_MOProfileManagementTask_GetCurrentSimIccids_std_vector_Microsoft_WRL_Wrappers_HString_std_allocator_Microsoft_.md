# MOProfileManagementTask::GetCurrentSimIccids(std::vector<Microsoft::WRL::Wrappers::HString,std::allocator<Microsoft::WRL::Wrappers::HString>> &)

- ea: `0x180029780`
- end: `0x1800299f5`
- name: `?GetCurrentSimIccids@MOProfileManagementTask@@AEAAJAEAV?$vector@VHString@Wrappers@WRL@Microsoft@@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@std@@@Z`
- size: `629`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180029148`

## callees

- `0x18001668c`
- `0x18001dc6c`
- `0x18001de54`
- `0x180028e1c`
- `0x180028e7c`
- `0x180029038`
- `0x18002909c`
- `0x180029780`
- `0x180029d00`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002999c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002999c`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x1800297cb`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x1800297cb`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18002986c`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800299b9`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800299d0`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18002986c`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800299b9`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800299d0`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x1800298dc`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x1800298dc`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanEnumerateInterfaces` at `0x180029829`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanEnumerateInterfaces` at `0x180029829`

## string_xrefs

- `0x1800297e0`: `onecoreuap\net\ux\wlanmediamanager\lib\moprofilemanagementtask.cpp`
- `0x18002984a`: `onecoreuap\net\ux\wlanmediamanager\lib\moprofilemanagementtask.cpp`
- `0x1800298f1`: `onecoreuap\net\ux\wlanmediamanager\lib\moprofilemanagementtask.cpp`

## pseudocode

```c
__int64 __fastcall MOProfileManagementTask::GetCurrentSimIccids(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rdx
  unsigned int v4; // eax
  unsigned int v5; // ebx
  unsigned int v7; // edi
  unsigned int v8; // ebx
  unsigned int *v9; // rcx
  unsigned int i; // edi
  unsigned int *v11; // rcx
  unsigned int Interface; // eax
  unsigned __int64 v13; // rcx
  HSTRING v14; // r9
  __int64 v15; // r10
  HSTRING *v16; // rdx
  HSTRING v17; // rcx
  const char *v18; // r9
  unsigned int v19; // [rsp+20h] [rbp-68h]
  __int64 v20; // [rsp+48h] [rbp-40h] BYREF
  unsigned int *v21; // [rsp+50h] [rbp-38h] BYREF
  unsigned int **v22; // [rsp+58h] [rbp-30h] BYREF
  __int64 v23; // [rsp+60h] [rbp-28h] BYREF
  char v24; // [rsp+68h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  __int64 v26; // [rsp+90h] [rbp+8h] BYREF
  int v27; // [rsp+98h] [rbp+10h] BYREF
  unsigned int v28; // [rsp+A0h] [rbp+18h] BYREF
  HSTRING string; // [rsp+A8h] [rbp+20h] BYREF

  v26 = a1;
  v3 = a2[1];
  if ( *a2 != v3 )
  {
    std::_Destroy_range<std::allocator<Microsoft::WRL::Wrappers::HString>>(*a2, v3);
    a2[1] = *a2;
  }
  v27 = 0;
  v20 = -1;
  v4 = WwanOpenHandle(1, 0, &v27, &v20);
  if ( v4 )
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xA5,
           (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\moprofilemanagementtask.cpp",
           (const char *)v4,
           v19);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(&v20);
    return v5;
  }
  else
  {
    v21 = 0;
    v22 = &v21;
    v23 = 0;
    v24 = 1;
    v7 = WwanEnumerateInterfaces(v20, 0, &v23);
    wil::details::out_param_ptr_t<WWAN_INTERFACE_INFO_LIST * *,wistd::unique_ptr<WWAN_INTERFACE_INFO_LIST,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>::~out_param_ptr_t<WWAN_INTERFACE_INFO_LIST * *,wistd::unique_ptr<WWAN_INTERFACE_INFO_LIST,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>(&v22);
    if ( v7 )
    {
      v8 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xA8,
             (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\moprofilemanagementtask.cpp",
             (const char *)v7,
             v19);
      v9 = v21;
      v21 = 0;
      if ( v9 )
        WwanFreeMemory();
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(&v20);
      return v8;
    }
    else
    {
      for ( i = 0; ; ++i )
      {
        v11 = v21;
        if ( i >= *v21 )
          break;
        v28 = 0;
        Interface = WwanQueryInterface(v20, &v21[147 * i + 1], 7);
        if ( Interface )
        {
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0xAF,
            (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\moprofilemanagementtask.cpp",
            (const char *)Interface,
            (unsigned int)&v28);
        }
        else
        {
          string = 0;
          LODWORD(v26) = 0;
          v13 = -1;
          do
            ++v13;
          while ( *(_WORD *)(2 * v13 + 0x3B8) );
          if ( (int)ULongLongToUInt(v13, (unsigned int *)&v26) >= 0 )
          {
            Microsoft::WRL::Wrappers::HString::Set(
              (Microsoft::WRL::Wrappers::HString *)&string,
              (const unsigned __int16 *)(v15 + 952),
              v26);
            v14 = string;
          }
          v16 = (HSTRING *)a2[1];
          if ( v16 == (HSTRING *)a2[2] )
          {
            try
            {
              std::vector<Microsoft::WRL::Wrappers::HString>::_Emplace_reallocate<Microsoft::WRL::Wrappers::HString>(
                a2,
                v16,
                &string);
              v17 = string;
            }
            catch ( ... )
            {
              return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                                     retaddr,
                                     (void *)0xBB,
                                     (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\moprofilemanagementtask.cpp",
                                     v18);
            }
          }
          else
          {
            *v16 = v14;
            v17 = 0;
            string = 0;
            a2[1] += 8LL;
          }
          WindowsDeleteString(v17);
          string = 0;
        }
      }
      v21 = 0;
      if ( v11 )
        WwanFreeMemory();
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(&v20);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x180029780  mov     [rsp+arg_0], rcx
0x180029785  push    rbx
0x180029786  push    rsi
0x180029787  push    rdi
0x180029788  sub     rsp, 70h
0x18002978c  mov     rbx, rdx
0x18002978f  mov     rdx, [rdx+8]
0x180029793  cmp     [rbx], rdx
0x180029796  jz      short loc_1800297A7
0x180029798  mov     rcx, [rbx]
0x18002979b  call    ??$_Destroy_range@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@std@@YAXPEAVHString@Wrappers@WRL@Microsoft@@QEAV1234@AEAV?$allocator@VHString@Wrappers@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::Wrappers::HString>>(Microsoft::WRL::Wrappers::HString *,Microsoft::WRL::Wrappers::HString * const,std::allocator<Microsoft::WRL::Wrappers::HString> &)
0x1800297a0  mov     rax, [rbx]
0x1800297a3  mov     [rbx+8], rax
0x1800297a7  xor     esi, esi
0x1800297a9  mov     [rsp+88h+arg_8], esi
0x1800297b0  mov     [rsp+88h+var_40], 0FFFFFFFFFFFFFFFFh
0x1800297b9  lea     r9, [rsp+88h+var_40]
0x1800297be  lea     r8, [rsp+88h+arg_8]
0x1800297c6  xor     edx, edx
0x1800297c8  lea     ecx, [rsi+1]
0x1800297cb  call    cs:__imp_WwanOpenHandle
0x1800297d1  test    eax, eax
0x1800297d3  jz      short loc_180029804
0x1800297d5  mov     rcx, [rsp+88h]; this
0x1800297dd  mov     r9d, eax; char *
0x1800297e0  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x1800297e7  mov     edx, 0A5h; void *
0x1800297ec  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800297f1  mov     ebx, eax
0x1800297f3  lea     rcx, [rsp+88h+var_40]
0x1800297f8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWwanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(void)
0x1800297fd  mov     eax, ebx
0x1800297ff  jmp     loc_1800299EC
0x180029804  mov     [rsp+88h+var_38], rsi
0x180029809  lea     rax, [rsp+88h+var_38]
0x18002980e  mov     [rsp+88h+var_30], rax
0x180029813  mov     [rsp+88h+var_28], rsi
0x180029818  mov     [rsp+88h+var_20], 1
0x18002981d  lea     r8, [rsp+88h+var_28]
0x180029822  xor     edx, edx
0x180029824  mov     rcx, [rsp+88h+var_40]
0x180029829  call    cs:__imp_WwanEnumerateInterfaces
0x18002982f  mov     edi, eax
0x180029831  lea     rcx, [rsp+88h+var_30]
0x180029836  call    ??1?$out_param_ptr_t@PEAPEAUWWAN_INTERFACE_INFO_LIST@@V?$unique_ptr@UWWAN_INTERFACE_INFO_LIST@@U?$function_deleter@P6AXPEAX@Z$1?WwanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<WWAN_INTERFACE_INFO_LIST * *,wistd::unique_ptr<WWAN_INTERFACE_INFO_LIST,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>::~out_param_ptr_t<WWAN_INTERFACE_INFO_LIST * *,wistd::unique_ptr<WWAN_INTERFACE_INFO_LIST,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>(void)
0x18002983b  test    edi, edi
0x18002983d  jz      short loc_180029884
0x18002983f  mov     rcx, [rsp+88h]; this
0x180029847  mov     r9d, edi; char *
0x18002984a  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180029851  mov     edx, 0A8h; void *
0x180029856  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002985b  mov     ebx, eax
0x18002985d  mov     rcx, [rsp+88h+var_38]
0x180029862  mov     [rsp+88h+var_38], rsi
0x180029867  test    rcx, rcx
0x18002986a  jz      short loc_180029873
0x18002986c  call    cs:__imp_WwanFreeMemory
0x180029872  nop
0x180029873  lea     rcx, [rsp+88h+var_40]
0x180029878  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWwanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(void)
0x18002987d  mov     eax, ebx
0x18002987f  jmp     loc_1800299EC
0x180029884  mov     edi, esi
0x180029886  mov     rcx, [rsp+88h+var_38]
0x18002988b  cmp     edi, [rcx]
0x18002988d  jnb     loc_1800299C6
0x180029893  mov     [rsp+88h+var_48], rsi
0x180029898  mov     [rsp+88h+arg_10], esi
0x18002989f  mov     eax, edi
0x1800298a1  imul    rdx, rax, 24Ch
0x1800298a8  add     rcx, 4
0x1800298ac  add     rdx, rcx
0x1800298af  mov     [rsp+88h+var_50], rsi
0x1800298b4  mov     [rsp+88h+var_58], rsi
0x1800298b9  lea     rax, [rsp+88h+var_48]
0x1800298be  mov     [rsp+88h+var_60], rax
0x1800298c3  lea     rax, [rsp+88h+arg_10]
0x1800298cb  mov     qword ptr [rsp+88h+var_68], rax; unsigned int
0x1800298d0  xor     r9d, r9d
0x1800298d3  lea     r8d, [r9+7]
0x1800298d7  mov     rcx, [rsp+88h+var_40]
0x1800298dc  call    cs:__imp_WwanQueryInterface
0x1800298e2  mov     rcx, [rsp+88h]; this
0x1800298ea  test    eax, eax
0x1800298ec  jz      short loc_180029907
0x1800298ee  mov     r9d, eax; char *
0x1800298f1  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x1800298f8  mov     edx, 0AFh; void *
0x1800298fd  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180029902  jmp     loc_1800299AA
0x180029907  mov     r9, rsi
0x18002990a  mov     [rsp+88h+string], rsi
0x180029912  mov     r10, [rsp+88h+var_48]
0x180029917  mov     dword ptr [rsp+88h+arg_0], esi
0x18002991e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180029922  inc     rcx; unsigned __int64
0x180029925  cmp     [r10+rcx*2+3B8h], si
0x18002992e  jnz     short loc_180029922
0x180029930  lea     rdx, [rsp+88h+arg_0]; unsigned int *
0x180029938  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18002993d  test    eax, eax
0x18002993f  js      short loc_180029965
0x180029941  mov     r8d, dword ptr [rsp+88h+arg_0]; unsigned int
0x180029949  lea     rdx, [r10+3B8h]; unsigned __int16 *
0x180029950  lea     rcx, [rsp+88h+string]; this
0x180029958  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18002995d  mov     r9, [rsp+88h+string]
0x180029965  mov     rdx, [rbx+8]
0x180029969  cmp     rdx, [rbx+10h]
0x18002996d  jz      short loc_180029984
0x18002996f  mov     [rdx], r9
0x180029972  mov     rcx, rsi
0x180029975  mov     [rsp+88h+string], rcx
0x18002997d  add     qword ptr [rbx+8], 8
0x180029982  jmp     short loc_18002999C
0x180029984  lea     r8, [rsp+88h+string]
0x18002998c  mov     rcx, rbx
0x18002998f  call    ??$_Emplace_reallocate@VHString@Wrappers@WRL@Microsoft@@@?$vector@VHString@Wrappers@WRL@Microsoft@@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@std@@AEAAPEAVHString@Wrappers@WRL@Microsoft@@QEAV2345@$$QEAV2345@@Z; std::vector<Microsoft::WRL::Wrappers::HString>::_Emplace_reallocate<Microsoft::WRL::Wrappers::HString>(Microsoft::WRL::Wrappers::HString * const,Microsoft::WRL::Wrappers::HString &&)
0x180029994  mov     rcx, [rsp+88h+string]; string
0x18002999c  call    cs:__imp_WindowsDeleteString
0x1800299a2  mov     [rsp+88h+string], rsi
0x1800299aa  mov     rcx, [rsp+88h+var_48]
0x1800299af  test    rcx, rcx
0x1800299b2  mov     [rsp+88h+var_48], rsi
0x1800299b7  jz      short loc_1800299BF
0x1800299b9  call    cs:__imp_WwanFreeMemory
0x1800299bf  inc     edi
0x1800299c1  jmp     loc_180029886
0x1800299c6  mov     [rsp+88h+var_38], rsi
0x1800299cb  test    rcx, rcx
0x1800299ce  jz      short loc_1800299D7
0x1800299d0  call    cs:__imp_WwanFreeMemory
0x1800299d6  nop
0x1800299d7  lea     rcx, [rsp+88h+var_40]
0x1800299dc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWwanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(void)
0x1800299e1  xor     eax, eax
0x1800299e3  jmp     short loc_1800299EC
0x1800299e5  mov     eax, dword ptr [rsp+88h+arg_0]
0x1800299ec  add     rsp, 70h
0x1800299f0  pop     rdi
0x1800299f1  pop     rsi
0x1800299f2  pop     rbx
0x1800299f3  retn
```
