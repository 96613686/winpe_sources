# AIFabricResourceManagerImpl::AIFabricResourceManagerImpl(void)

- ea: `0x18006e878`
- end: `0x18006ecb3`
- name: `??0AIFabricResourceManagerImpl@@QEAA@XZ`
- size: `1083`
- prototype: `AIFabricResourceManagerImpl *__fastcall(AIFabricResourceManagerImpl *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180012d2c`

## callees

- `0x1800017dc`
- `0x180004ca0`
- `0x180007ad0`
- `0x180013930`
- `0x18001899c`
- `0x180018f0c`
- `0x18004c5f4`
- `0x180065380`
- `0x18006cdf0`
- `0x18006cf1c`
- `0x18006cf9c`
- `0x18006d2e8`
- `0x18006e488`
- `0x18006e878`
- `0x1800732d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18006ebf7`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18006ebf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e9ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e9ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006ea01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006ea01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006e9f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006e9f9`
- `msvcp_win!_Thrd_detach` at `0x18006ec19`
- `msvcp_win!_Thrd_detach` at `0x18006ec19`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18006ec63`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18006ec73`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18006ec63`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18006ec73`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006ea65`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006ea65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ec34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ec34`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006eaae`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006eaae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006eb96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006eb96`
- `api-ms-win-core-memory-l1-1-1!CreateMemoryResourceNotification` at `0x18006e9d7`
- `api-ms-win-core-memory-l1-1-1!CreateMemoryResourceNotification` at `0x18006e9d7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18006eb44`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18006eb44`

## string_xrefs

- `0x18006ec7a`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\aifabricresourcemanagerimpl.cpp`
- `0x18006ec8c`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\aifabricresourcemanagerimpl.cpp`
- `0x18006ec9e`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\aifabricresourcemanagerimpl.cpp`

## pseudocode

```c
AIFabricResourceManagerImpl *__fastcall AIFabricResourceManagerImpl::AIFabricResourceManagerImpl(
        AIFabricResourceManagerImpl *this)
{
  _QWORD *v2; // rax
  const struct _tlgProvider_t *v3; // rcx
  HANDLE MemoryResourceNotification; // r15
  char *v5; // r14
  DWORD LastError; // ebx
  char IsEnabled; // al
  const char *v8; // r9
  LSTATUS v9; // eax
  bool v10; // sf
  LSTATUS ValueW; // eax
  bool v12; // sf
  const char *v13; // r9
  const char *v14; // r9
  wil::details::in1diag3 *v15; // rcx
  _QWORD *v16; // rax
  int v18; // [rsp+40h] [rbp-59h] BYREF
  int v19; // [rsp+44h] [rbp-55h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-51h] BYREF
  _DWORD v21[4]; // [rsp+50h] [rbp-49h] BYREF
  DWORD pcbData[4]; // [rsp+60h] [rbp-39h] BYREF
  __int128 v23; // [rsp+70h] [rbp-29h] BYREF
  AIFabricResourceManagerImpl *v24; // [rsp+80h] [rbp-19h]
  _QWORD v25[4]; // [rsp+88h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v24 = this;
  *(_QWORD *)this = &winrt::impl::producers_base<SemanticTextRegionStream,std::tuple<ISemanticTextRegionStream>>::`vftable';
  winrt::impl::module_lock_updater<1>::module_lock_updater<1>((__int64)this + 16);
  *((_QWORD *)this + 2) = 1;
  *(_QWORD *)this = &AIFabricResourceManagerImpl::`vftable'{for `winrt::impl::producers_base<AIFabricResourceManagerImpl,std::tuple<IAIFabricResourceManager>>'};
  *((_QWORD *)this + 1) = &winrt::impl::heap_implements<AIFabricResourceManagerImpl>::`vftable'{for `winrt::impl::root_implements<AIFabricResourceManagerImpl,IAIFabricResourceManager,winrt::non_agile>'};
  *(_QWORD *)pcbData = (char *)this + 24;
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  v2 = operator new(0x50u);
  *v2 = v2;
  v2[1] = v2;
  *((_QWORD *)this + 4) = v2;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 7;
  *((_QWORD *)this + 10) = 8;
  *((_DWORD *)this + 6) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<enum AIFabric_Component const,std::unique_ptr<wil::srwlock>>>>>>>::_Assign_grow(
    (char *)this + 48,
    16,
    *((_QWORD *)this + 4));
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 2;
  *(_OWORD *)((char *)this + 136) = 0;
  *(_OWORD *)((char *)this + 152) = 0;
  *(_OWORD *)((char *)this + 168) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_DWORD *)this + 46) = -1;
  *((_DWORD *)this + 47) = 0;
  *((_DWORD *)this + 48) = 120;
  *((_DWORD *)this + 49) = 734003200;
  *((_BYTE *)this + 200) = 0;
  v3 = AIFabricTraceLogger::Provider();
  if ( *(_DWORD *)v3 > 5u )
    tlgWriteTransfer_EventWriteTransfer(v3, byte_18009E401, 0, 0, 2, v25);
  MemoryResourceNotification = CreateMemoryResourceNotification(LowMemoryResourceNotification);
  v5 = (char *)*((_QWORD *)this + 11);
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    CloseHandle(v5);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 11) = MemoryResourceNotification;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_59780494>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59780494>::GetImpl'::`2'::impl);
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (char *)this + 96,
    IsEnabled != 0,
    0);
  if ( !*((_QWORD *)this + 12) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1F,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\aifabricresourcemanagerimpl.cpp",
      v8);
  hkey = 0;
  v9 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AIFabricResourceManager",
         0,
         0x20019u,
         &hkey);
  v10 = v9 < 0;
  if ( v9 > 0 )
    v10 = 1;
  if ( !v10 )
  {
    pcbData[0] = 4;
    ValueW = RegGetValueW(hkey, 0, L"ClientInactiveThreshold", 0x10u, 0, (char *)this + 192, pcbData);
    v12 = ValueW < 0;
    if ( ValueW > 0 )
      v12 = 1;
    if ( !v12 )
      AIFabricTraceLogger::OverrideClientInactiveThreshold<unsigned int &>((char *)this + 192);
    v18 = 0;
    if ( (int)wil::reg::get_value_dword_nothrow<unsigned long,0>(hkey, L"IgnoreSystemLowMemoryNotification", &v18) >= 0 )
    {
      AIFabricTraceLogger::SkipSystemLowMemoryNotification<unsigned long &>(&v18);
      *((_BYTE *)this + 200) = v18 != 0;
    }
    v19 = 0;
    if ( (int)wil::reg::get_value_dword_nothrow<unsigned long,0>(hkey, L"EnableTestLowMemoryNotification", &v19) >= 0 )
    {
      AIFabricTraceLogger::EnableTestLowMemoryNotification<unsigned long &>(&v19);
      if ( v19 )
      {
        *(_QWORD *)pcbData = 0;
        if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
                L"D:(A;;GA;;;WD)",
                1u,
                (PSECURITY_DESCRIPTOR *)pcbData,
                0) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x3A,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\aifabricresourcemanagerimpl.cpp",
            v13);
        v25[0] = 24;
        v25[2] = 0;
        v25[1] = *(_QWORD *)pcbData;
        _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
          (char *)this + 104,
          1,
          L"Global\\AIFabricResourceManager_Low_Memory");
        v15 = retaddr;
        if ( !*((_QWORD *)this + 13) )
LABEL_31:
          wil::details::in1diag3::_Throw_GetLastError(
            v15,
            (void *)0x41,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\aifabricresourcemanagerimpl.cpp",
            v14);
        if ( *(_QWORD *)pcbData )
          LocalFree(*(HLOCAL *)pcbData);
      }
    }
    v21[0] = 0;
    if ( (int)wil::reg::get_value_dword_nothrow<unsigned long,0>(hkey, L"ClientMemoryThresholdMB", v21) >= 0 )
    {
      *((_DWORD *)this + 49) = v21[0] << 20;
      AIFabricTraceLogger::OverrideClientMemoryThreshold<unsigned long &>((char *)this + 196);
    }
  }
  v16 = operator new(8u);
  *v16 = this;
  *(_QWORD *)pcbData = v16;
  *(_QWORD *)&v23 = _o__beginthreadex(
                      0,
                      0,
                      std::thread::_Invoke_std::tuple__lambda_4a1196af0e87de351fed9b73ad08653f____0_,
                      v16,
                      0,
                      (char *)&v23 + 8);
  if ( !(_QWORD)v23 )
  {
LABEL_30:
    DWORD2(v23) = 0;
    std::_Throw_Cpp_error(6);
    goto LABEL_31;
  }
  if ( !DWORD2(v23) || (*(_OWORD *)pcbData = v23, _Thrd_detach((_Thrd_t *)pcbData)) )
  {
    std::_Throw_Cpp_error(1);
    goto LABEL_30;
  }
  v23 = 0;
  if ( hkey )
    RegCloseKey(hkey);
  return this;
}

```

## disassembly

```asm
0x18006e878  push    rbp
0x18006e87a  push    rbx
0x18006e87b  push    rsi
0x18006e87c  push    rdi
0x18006e87d  push    r12
0x18006e87f  push    r13
0x18006e881  push    r14
0x18006e883  push    r15
0x18006e885  lea     rbp, [rsp-1Fh]
0x18006e88a  sub     rsp, 0B8h
0x18006e891  mov     rax, cs:__security_cookie
0x18006e898  xor     rax, rsp
0x18006e89b  mov     [rbp+57h+var_48], rax
0x18006e89f  mov     rdi, rcx
0x18006e8a2  mov     [rbp+57h+var_70], rcx
0x18006e8a6  xor     r14d, r14d
0x18006e8a9  lea     rax, ??_7?$producers_base@USemanticTextRegionStream@@V?$tuple@UISemanticTextRegionStream@@@std@@@impl@winrt@@6B@; const winrt::impl::producers_base<SemanticTextRegionStream,std::tuple<ISemanticTextRegionStream>>::`vftable'
0x18006e8b0  mov     [rcx], rax
0x18006e8b3  add     rcx, 10h
0x18006e8b7  call    ??0?$module_lock_updater@$00@impl@winrt@@QEAA@XZ; winrt::impl::module_lock_updater<1>::module_lock_updater<1>(void)
0x18006e8bc  mov     qword ptr [rdi+10h], 1
0x18006e8c4  lea     rax, ??_7AIFabricResourceManagerImpl@@6B?$producers_base@UAIFabricResourceManagerImpl@@V?$tuple@UIAIFabricResourceManager@@@std@@@impl@winrt@@@; const AIFabricResourceManagerImpl::`vftable'{for `winrt::impl::producers_base<AIFabricResourceManagerImpl,std::tuple<IAIFabricResourceManager>>'}
0x18006e8cb  mov     [rdi], rax
0x18006e8ce  lea     rax, ??_7?$heap_implements@UAIFabricResourceManagerImpl@@@impl@winrt@@6B?$root_implements@UAIFabricResourceManagerImpl@@UIAIFabricResourceManager@@Unon_agile@winrt@@@12@@; const winrt::impl::heap_implements<AIFabricResourceManagerImpl>::`vftable'{for `winrt::impl::root_implements<AIFabricResourceManagerImpl,IAIFabricResourceManager,winrt::non_agile>'}
0x18006e8d5  mov     [rdi+8], rax
0x18006e8d9  lea     rbx, [rdi+18h]
0x18006e8dd  mov     qword ptr [rbp+57h+var_90], rbx
0x18006e8e1  mov     [rbx], r14d
0x18006e8e4  mov     [rbx+8], r14
0x18006e8e8  mov     [rbx+10h], r14
0x18006e8ec  lea     ecx, [r14+50h]; Size
0x18006e8f0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006e8f5  mov     [rax], rax
0x18006e8f8  mov     [rax+8], rax
0x18006e8fc  mov     [rbx+8], rax
0x18006e900  lea     rcx, [rbx+18h]
0x18006e904  mov     [rcx], r14
0x18006e907  mov     [rcx+8], r14
0x18006e90b  mov     [rcx+10h], r14
0x18006e90f  mov     qword ptr [rbx+30h], 7
0x18006e917  mov     qword ptr [rbx+38h], 8
0x18006e91f  mov     dword ptr [rbx], 3F800000h
0x18006e925  mov     r8, [rbx+8]
0x18006e929  lea     edx, [r14+10h]
0x18006e92d  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4AIFabric_Component@@V?$unique_ptr@Vsrwlock@wil@@U?$default_delete@Vsrwlock@wil@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4AIFabric_Component@@V?$unique_ptr@Vsrwlock@wil@@U?$default_delete@Vsrwlock@wil@@@std@@@std@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<AIFabric_Component const,std::unique_ptr<wil::srwlock>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<AIFabric_Component const,std::unique_ptr<wil::srwlock>>>>>)
0x18006e932  nop
0x18006e933  mov     [rdi+58h], r14
0x18006e937  lea     rsi, [rdi+60h]
0x18006e93b  mov     [rsi], r14
0x18006e93e  mov     [rdi+68h], r14
0x18006e942  mov     qword ptr [rdi+70h], 2
0x18006e94a  xorps   xmm0, xmm0
0x18006e94d  movups  xmmword ptr [rdi+88h], xmm0
0x18006e954  movups  xmmword ptr [rdi+98h], xmm0
0x18006e95b  movups  xmmword ptr [rdi+0A8h], xmm0
0x18006e962  mov     [rdi+78h], r14
0x18006e966  mov     [rdi+80h], r14
0x18006e96d  mov     dword ptr [rdi+0B8h], 0FFFFFFFFh
0x18006e977  lea     ebx, [r14+2]
0x18006e97b  mov     [rdi+0BCh], r14d
0x18006e982  lea     r12, [rdi+0C0h]
0x18006e989  mov     dword ptr [r12], 78h ; 'x'
0x18006e991  lea     r13, [rdi+0C4h]
0x18006e998  mov     dword ptr [r13+0], 2BC00000h
0x18006e9a0  mov     [rdi+0C8h], r14b
0x18006e9a7  call    ?Provider@AIFabricTraceLogger@@SAPEBU_tlgProvider_t@@XZ; AIFabricTraceLogger::Provider(void)
0x18006e9ac  mov     rcx, rax
0x18006e9af  mov     eax, [rax]
0x18006e9b1  cmp     eax, 5
0x18006e9b4  jbe     short loc_18006E9D5
0x18006e9b6  lea     rax, [rbp+57h+var_68]
0x18006e9ba  mov     [rsp+0F0h+pvData], rax
0x18006e9bf  mov     dword ptr [rsp+0F0h+phkResult], ebx
0x18006e9c3  xor     r9d, r9d
0x18006e9c6  xor     r8d, r8d
0x18006e9c9  lea     rdx, byte_18009E401
0x18006e9d0  call    _tlgWriteTransfer_EventWriteTransfer
0x18006e9d5  xor     ecx, ecx; NotificationType
0x18006e9d7  call    cs:__imp_CreateMemoryResourceNotification
0x18006e9dd  mov     r15, rax
0x18006e9e0  mov     r14, [rdi+58h]
0x18006e9e4  lea     rax, [r14-1]
0x18006e9e8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006e9ec  ja      short loc_18006EA07
0x18006e9ee  call    cs:__imp_GetLastError
0x18006e9f4  mov     ebx, eax
0x18006e9f6  mov     rcx, r14; hObject
0x18006e9f9  call    cs:__imp_CloseHandle
0x18006e9ff  mov     ecx, ebx; dwErrCode
0x18006ea01  call    cs:__imp_SetLastError
0x18006ea07  mov     [rdi+58h], r15
0x18006ea0b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59780494@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59780494@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59780494> `wil::Feature<__WilFeatureTraits_Feature_59780494>::GetImpl(void)'::`2'::impl
0x18006ea12  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59780494@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59780494>::__private_IsEnabled(void)
0x18006ea17  xor     r14d, r14d
0x18006ea1a  xor     r9d, r9d
0x18006ea1d  xor     r8d, r8d
0x18006ea20  mov     rcx, rsi
0x18006ea23  test    al, al
0x18006ea25  jz      short loc_18006EA2D
0x18006ea27  lea     edx, [r14+1]
0x18006ea2b  jmp     short loc_18006EA2F
0x18006ea2d  xor     edx, edx
0x18006ea2f  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18006ea34  mov     rcx, [rbp+5Fh]; this
0x18006ea38  cmp     [rsi], r14
0x18006ea3b  jz      loc_18006EC8C
0x18006ea41  mov     [rbp+57h+hkey], r14
0x18006ea45  lea     rax, [rbp+57h+hkey]
0x18006ea49  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18006ea4e  mov     r9d, 20019h; samDesired
0x18006ea54  xor     r8d, r8d; ulOptions
0x18006ea57  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x18006ea5e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006ea65  call    cs:__imp_RegOpenKeyExW
0x18006ea6b  mov     ebx, 80070000h
0x18006ea70  test    eax, eax
0x18006ea72  jle     short loc_18006EA7B
0x18006ea74  movzx   eax, ax
0x18006ea77  or      eax, ebx
0x18006ea79  test    eax, eax
0x18006ea7b  js      loc_18006EBCA
0x18006ea81  mov     [rbp+57h+var_90], 4
0x18006ea88  lea     rax, [rbp+57h+var_90]
0x18006ea8c  mov     [rsp+0F0h+pcbData], rax; pcbData
0x18006ea91  mov     [rsp+0F0h+pvData], r12; pvData
0x18006ea96  mov     [rsp+0F0h+phkResult], r14; pdwType
0x18006ea9b  mov     r9d, 10h; dwFlags
0x18006eaa1  lea     r8, aClientinactive; "ClientInactiveThreshold"
0x18006eaa8  xor     edx, edx; lpSubKey
0x18006eaaa  mov     rcx, [rbp+57h+hkey]; hkey
0x18006eaae  call    cs:__imp_RegGetValueW
0x18006eab4  test    eax, eax
0x18006eab6  jle     short loc_18006EABF
0x18006eab8  movzx   eax, ax
0x18006eabb  or      eax, ebx
0x18006eabd  test    eax, eax
0x18006eabf  js      short loc_18006EAC9
0x18006eac1  mov     rcx, r12
0x18006eac4  call    ??$OverrideClientInactiveThreshold@AEAI@AIFabricTraceLogger@@SAXAEAI@Z; AIFabricTraceLogger::OverrideClientInactiveThreshold<uint &>(uint &)
0x18006eac9  mov     [rbp+57h+var_B0], r14d
0x18006eacd  lea     r8, [rbp+57h+var_B0]
0x18006ead1  lea     rdx, aIgnoresystemlo; "IgnoreSystemLowMemoryNotification"
0x18006ead8  mov     rcx, [rbp+57h+hkey]
0x18006eadc  call    ??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEB_WPEAK@Z; wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,wchar_t const *,ulong *)
0x18006eae1  test    eax, eax
0x18006eae3  js      short loc_18006EAFB
0x18006eae5  lea     rcx, [rbp+57h+var_B0]
0x18006eae9  call    ??$SkipSystemLowMemoryNotification@AEAK@AIFabricTraceLogger@@SAXAEAK@Z; AIFabricTraceLogger::SkipSystemLowMemoryNotification<ulong &>(ulong &)
0x18006eaee  cmp     [rbp+57h+var_B0], r14d
0x18006eaf2  setnz   al
0x18006eaf5  mov     [rdi+0C8h], al
0x18006eafb  mov     [rbp+57h+var_AC], r14d
0x18006eaff  lea     r8, [rbp+57h+var_AC]
0x18006eb03  lea     rdx, aEnabletestlowm; "EnableTestLowMemoryNotification"
0x18006eb0a  mov     rcx, [rbp+57h+hkey]
0x18006eb0e  call    ??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEB_WPEAK@Z; wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,wchar_t const *,ulong *)
0x18006eb13  test    eax, eax
0x18006eb15  js      loc_18006EB9C
0x18006eb1b  lea     rcx, [rbp+57h+var_AC]
0x18006eb1f  call    ??$EnableTestLowMemoryNotification@AEAK@AIFabricTraceLogger@@SAXAEAK@Z; AIFabricTraceLogger::EnableTestLowMemoryNotification<ulong &>(ulong &)
0x18006eb24  cmp     [rbp+57h+var_AC], r14d
0x18006eb28  jz      short loc_18006EB9C
0x18006eb2a  mov     qword ptr [rbp+57h+var_90], r14
0x18006eb2e  mov     rbx, [rbp+5Fh]
0x18006eb32  xor     r9d, r9d; SecurityDescriptorSize
0x18006eb35  lea     r8, [rbp+57h+var_90]; SecurityDescriptor
0x18006eb39  lea     edx, [r9+1]; StringSDRevision
0x18006eb3d  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;WD)"
0x18006eb44  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18006eb4a  test    eax, eax
0x18006eb4c  jz      loc_18006EC9E
0x18006eb52  mov     [rbp+57h+var_68], 18h
0x18006eb5a  mov     [rbp+57h+var_58], r14
0x18006eb5e  mov     rax, qword ptr [rbp+57h+var_90]
0x18006eb62  mov     [rbp+57h+var_60], rax
0x18006eb66  lea     r9, [rbp+57h+var_68]
0x18006eb6a  lea     r8, aGlobalAifabric; "Global\\AIFabricResourceManager_Low_Mem"...
0x18006eb71  mov     edx, 1
0x18006eb76  lea     rcx, [rdi+68h]
0x18006eb7a  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18006eb7f  mov     rcx, [rbp+5Fh]
0x18006eb83  cmp     [rdi+68h], r14
0x18006eb87  jz      loc_18006EC7A
0x18006eb8d  mov     rcx, qword ptr [rbp+57h+var_90]; hMem
0x18006eb91  test    rcx, rcx
0x18006eb94  jz      short loc_18006EB9C
0x18006eb96  call    cs:__imp_LocalFree
0x18006eb9c  mov     [rbp+57h+var_A0], r14d
0x18006eba0  lea     r8, [rbp+57h+var_A0]
0x18006eba4  lea     rdx, aClientmemoryth; "ClientMemoryThresholdMB"
0x18006ebab  mov     rcx, [rbp+57h+hkey]
0x18006ebaf  call    ??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEB_WPEAK@Z; wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,wchar_t const *,ulong *)
0x18006ebb4  test    eax, eax
0x18006ebb6  js      short loc_18006EBCA
0x18006ebb8  mov     eax, [rbp+57h+var_A0]
0x18006ebbb  shl     eax, 14h
0x18006ebbe  mov     [r13+0], eax
0x18006ebc2  mov     rcx, r13
0x18006ebc5  call    ??$OverrideClientMemoryThreshold@AEAK@AIFabricTraceLogger@@SAXAEAK@Z; AIFabricTraceLogger::OverrideClientMemoryThreshold<ulong &>(ulong &)
0x18006ebca  mov     ecx, 8; Size
0x18006ebcf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006ebd4  mov     [rax], rdi
0x18006ebd7  mov     qword ptr [rbp+57h+var_90], rax
0x18006ebdb  lea     rcx, [rbp+57h+var_80+8]
0x18006ebdf  mov     [rsp+0F0h+pvData], rcx
0x18006ebe4  mov     dword ptr [rsp+0F0h+phkResult], r14d
0x18006ebe9  mov     r9, rax
0x18006ebec  lea     r8, std__thread___Invoke_std__tuple__lambda_4a1196af0e87de351fed9b73ad08653f____0_
0x18006ebf3  xor     edx, edx
0x18006ebf5  xor     ecx, ecx
0x18006ebf7  call    cs:__imp__o__beginthreadex
0x18006ebfd  mov     qword ptr [rbp+57h+var_80], rax
0x18006ec01  test    rax, rax
0x18006ec04  jz      short loc_18006EC6A
0x18006ec06  cmp     dword ptr [rbp+57h+var_80+8], r14d
0x18006ec0a  jz      short loc_18006EC5E
0x18006ec0c  movaps  xmm0, [rbp+57h+var_80]
0x18006ec10  movdqa  xmmword ptr [rbp+57h+var_90], xmm0
0x18006ec15  lea     rcx, [rbp+57h+var_90]; _Thrd_t
0x18006ec19  call    cs:__imp__Thrd_detach
0x18006ec1f  test    eax, eax
0x18006ec21  jnz     short loc_18006EC5E
0x18006ec23  xorps   xmm0, xmm0
0x18006ec26  movdqa  [rbp+57h+var_80], xmm0
0x18006ec2b  mov     rcx, [rbp+57h+hkey]; hKey
0x18006ec2f  test    rcx, rcx
0x18006ec32  jz      short loc_18006EC3B
0x18006ec34  call    cs:__imp_RegCloseKey
0x18006ec3a  nop
0x18006ec3b  mov     rax, rdi
0x18006ec3e  mov     rcx, [rbp+57h+var_48]
0x18006ec42  xor     rcx, rsp; StackCookie
0x18006ec45  call    __security_check_cookie
0x18006ec4a  add     rsp, 0B8h
0x18006ec51  pop     r15
0x18006ec53  pop     r14
0x18006ec55  pop     r13
0x18006ec57  pop     r12
0x18006ec59  pop     rdi
0x18006ec5a  pop     rsi
0x18006ec5b  pop     rbx
0x18006ec5c  pop     rbp
0x18006ec5d  retn
0x18006ec5e  mov     ecx, 1
0x18006ec63  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18006ec69  nop
0x18006ec6a  mov     dword ptr [rbp+57h+var_80+8], r14d
0x18006ec6e  mov     ecx, 6
0x18006ec73  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18006ec79  nop
0x18006ec7a  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\search\\com"...
0x18006ec81  mov     edx, 41h ; 'A'; void *
0x18006ec86  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18006ec8c  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\search\\com"...
0x18006ec93  mov     edx, 1Fh; void *
0x18006ec98  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18006ec9e  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\search\\com"...
0x18006eca5  mov     edx, 3Ah ; ':'; void *
0x18006ecaa  mov     rcx, rbx; this
0x18006ecad  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
