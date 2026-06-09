# ShouldSkipParsingConfidenceFile(ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18002f498`
- end: `0x18002f75b`
- name: `?ShouldSkipParsingConfidenceFile@@YAHKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `707`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18002edc8`

## callees

- `0x1800078b0`
- `0x1800095cc`
- `0x18000bcc4`
- `0x18000cbd4`
- `0x18000cd34`
- `0x18000ce04`
- `0x18000d524`
- `0x18000e410`
- `0x18000e48c`
- `0x180023634`
- `0x18002386c`
- `0x1800243e8`
- `0x1800248b4`
- `0x18002e178`
- `0x18002e1e8`
- `0x18002e3d0`
- `0x18002e438`
- `0x18002e4ac`
- `0x18002f498`
- `0x18003c0b8`

## import_xrefs

- `ntdll!RtlGetCurrentServiceSessionId` at `0x18002f602`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18002f602`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18002f6c0`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18002f6c0`

## string_xrefs

- `0x18002f60e`: `IsRunningInContainer: Detected container environment (ServiceSessionId=%lu)`
- `0x18002f5c4`: `Version %d is same and BucketId %ls is already scanned`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ShouldSkipParsingConfidenceFile(__int64 a1, __int64 a2)
{
  unsigned int v3; // r14d
  int v4; // esi
  HKEY v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // r8
  __int64 v11; // rax
  unsigned int v12; // ebx
  unsigned int CurrentServiceSessionId; // eax
  wil::reg::reg_view_details *v15; // [rsp+20h] [rbp-49h]
  _WORD *v16; // [rsp+30h] [rbp-39h] BYREF
  HKEY v17; // [rsp+38h] [rbp-31h] BYREF
  HKEY v18[2]; // [rsp+40h] [rbp-29h] BYREF
  __int128 v19; // [rsp+50h] [rbp-19h] BYREF
  __int64 v20; // [rsp+60h] [rbp-9h]
  __int64 v21; // [rsp+68h] [rbp-1h]
  _BYTE v22[32]; // [rsp+70h] [rbp+7h] BYREF
  int v23; // [rsp+90h] [rbp+27h]

  v3 = a1;
  v19 = 0;
  v20 = 0;
  v21 = 7;
  LOWORD(v19) = 0;
  v17 = 0;
  v4 = 0;
  if ( (int)wil::reg::open_unique_key_nothrow(a1, L"SYSTEM\\CurrentControlSet\\Control\\SecureBoot\\Servicing", &v17, 0) >= 0 )
  {
    v4 = IsSameVersion(&v17, v3);
    v16 = 0;
    v5 = v17;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v16,
      0);
    v18[0] = v5;
    LODWORD(v15) = 268435462;
    if ( (int)wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::err_returncode_policy>(
                v18,
                v6,
                L"BucketHash",
                (PVOID *)&v16,
                v15) >= 0 )
    {
      v7 = -1;
      do
        ++v7;
      while ( v16[v7] );
      std::wstring::_Assign<unsigned short>(&v19, v16);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v16);
  }
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v19);
  SBServicingLogMessage((wchar_t *)L"Saved BucketId: %ls, Current BucketId: %ls", v8);
  if ( v4
    && (std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2),
        v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v19),
        (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v9, v20, v10, *(_QWORD *)(a2 + 16))) )
  {
    v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    SBServicingLogMessage((wchar_t *)L"Version %d is same and BucketId %ls is already scanned", v3, v11);
    std::wstring::wstring((__int64)v22, (__int64)L"SkipBCFVersionSameAndBucketIdScanned");
    v12 = 1;
    v23 = 1;
    std::_Tree<std::_Tmap_traits<std::wstring,long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,long>>,0>>::insert<0,0>(
      &g_HrAll,
      v18,
      v22);
  }
  else
  {
    CurrentServiceSessionId = RtlGetCurrentServiceSessionId();
    if ( !CurrentServiceSessionId
      || (SBServicingLogMessage(
            (wchar_t *)L"IsRunningInContainer: Detected container environment (ServiceSessionId=%lu)",
            CurrentServiceSessionId),
          (unsigned int)IsAllowOnContainerRegistrySet()) )
    {
      if ( !(unsigned int)IsHyperVGuest() || (unsigned int)IsAllowOnHyperVRegistrySet() )
      {
        LODWORD(v16) = 0;
        RtlGetDeviceFamilyInfoEnum(0, &v16, 0);
        if ( (((_DWORD)v16 - 9) & 0xFFFFFFFB) != 0 || !(unsigned int)IsSkipOnServerRegistrySet() )
        {
          v12 = 0;
          goto LABEL_21;
        }
        SBServicingLogMessage((wchar_t *)L"Skipping on Server");
        std::wstring::wstring((__int64)v22, (__int64)L"SkipBCFIsServer");
        v12 = 1;
        v23 = 1;
        std::_Tree<std::_Tmap_traits<std::wstring,long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,long>>,0>>::insert<0,0>(
          &g_HrAll,
          v18,
          v22);
      }
      else
      {
        SBServicingLogMessage((wchar_t *)L"Skipping confidence DB parsing: IsHyperVGuest");
        v12 = 1;
        LODWORD(v16) = 1;
        std::pair<std::wstring const,long>::pair<std::wstring const,long>(v22, L"SkipBCFIsHyperVGuest", &v16);
        std::_Tree<std::_Tmap_traits<std::wstring,long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,long>>,0>>::insert<0,0>(
          &g_HrAll,
          v18,
          v22);
      }
    }
    else
    {
      SBServicingLogMessage((wchar_t *)L"Skipping confidence DB parsing: Running in container");
      std::wstring::wstring((__int64)v22, (__int64)L"SkipBCFRunningInContainer");
      v12 = 1;
      v23 = 1;
      std::_Tree<std::_Tmap_traits<std::wstring,long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,long>>,0>>::insert<0,0>(
        &g_HrAll,
        v18,
        v22);
    }
  }
  std::wstring::_Tidy_deallocate(v22);
LABEL_21:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v17);
  std::wstring::_Tidy_deallocate(&v19);
  return v12;
}

```

## disassembly

```asm
0x18002f498  mov     [rsp-8+arg_10], rbx
0x18002f49d  push    rbp
0x18002f49e  push    rsi
0x18002f49f  push    rdi
0x18002f4a0  push    r14
0x18002f4a2  push    r15
0x18002f4a4  lea     rbp, [rsp-37h]
0x18002f4a9  sub     rsp, 0A0h
0x18002f4b0  mov     rax, cs:__security_cookie
0x18002f4b7  xor     rax, rsp
0x18002f4ba  mov     [rbp+57h+var_28], rax
0x18002f4be  mov     rdi, rdx
0x18002f4c1  mov     r14d, ecx
0x18002f4c4  xorps   xmm0, xmm0
0x18002f4c7  movups  [rbp+57h+var_70], xmm0
0x18002f4cb  xor     r15d, r15d
0x18002f4ce  mov     [rbp+57h+var_60], r15
0x18002f4d2  mov     [rbp+57h+var_58], 7
0x18002f4da  mov     word ptr [rbp+57h+var_70], r15w
0x18002f4df  mov     [rbp+57h+var_88], r15
0x18002f4e3  mov     esi, r15d
0x18002f4e6  xor     r9d, r9d
0x18002f4e9  lea     r8, [rbp+57h+var_88]
0x18002f4ed  lea     rdx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Control\\Sec"...
0x18002f4f4  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18002f4f9  test    eax, eax
0x18002f4fb  js      short loc_18002F567
0x18002f4fd  mov     edx, r14d
0x18002f500  lea     rcx, [rbp+57h+var_88]
0x18002f504  call    ?IsSameVersion@@YAHAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z; IsSameVersion(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,ulong)
0x18002f509  mov     esi, eax
0x18002f50b  mov     [rbp+57h+var_90], r15
0x18002f50f  mov     rbx, [rbp+57h+var_88]
0x18002f513  xor     edx, edx
0x18002f515  lea     rcx, [rbp+57h+var_90]
0x18002f519  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002f51e  mov     [rbp+57h+var_80], rbx
0x18002f522  mov     [rsp+0C0h+var_A0], 10000006h
0x18002f52a  lea     r9, [rbp+57h+var_90]
0x18002f52e  lea     r8, aBuckethash; "BucketHash"
0x18002f535  lea     rcx, [rbp+57h+var_80]
0x18002f539  call    ??$get_value_with_type@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@Uerr_returncode_policy@2@@?$reg_view_t@Uerr_returncode_policy@wil@@@reg_view_details@reg@wil@@AEBAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@3@K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::err_returncode_policy>(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong)
0x18002f53e  test    eax, eax
0x18002f540  js      short loc_18002F55E
0x18002f542  mov     rdx, [rbp+57h+var_90]
0x18002f546  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002f54a  inc     r8
0x18002f54d  cmp     [rdx+r8*2], r15w
0x18002f552  jnz     short loc_18002F54A
0x18002f554  lea     rcx, [rbp+57h+var_70]
0x18002f558  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002f55d  nop
0x18002f55e  lea     rcx, [rbp+57h+var_90]
0x18002f562  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002f567  mov     rcx, rdi
0x18002f56a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002f56f  mov     r8, rax
0x18002f572  lea     rcx, [rbp+57h+var_70]
0x18002f576  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002f57b  mov     rdx, rax
0x18002f57e  lea     rcx, aSavedBucketidL; "Saved BucketId: %ls, Current BucketId: "...
0x18002f585  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002f58a  test    esi, esi
0x18002f58c  jz      short loc_18002F602
0x18002f58e  mov     rcx, rdi
0x18002f591  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002f596  mov     r8, rax
0x18002f599  lea     rcx, [rbp+57h+var_70]
0x18002f59d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002f5a2  mov     rcx, rax
0x18002f5a5  mov     r9, [rdi+10h]
0x18002f5a9  mov     rdx, [rbp+57h+var_60]
0x18002f5ad  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18002f5b2  test    al, al
0x18002f5b4  jz      short loc_18002F602
0x18002f5b6  mov     rcx, rdi
0x18002f5b9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002f5be  mov     r8, rax
0x18002f5c1  mov     edx, r14d
0x18002f5c4  lea     rcx, aVersionDIsSame; "Version %d is same and BucketId %ls is "...
0x18002f5cb  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002f5d0  lea     rdx, aSkipbcfversion; "SkipBCFVersionSameAndBucketIdScanned"
0x18002f5d7  lea     rcx, [rbp+57h+var_50]
0x18002f5db  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002f5e0  mov     ebx, 1
0x18002f5e5  mov     [rbp+57h+var_30], ebx
0x18002f5e8  lea     r8, [rbp+57h+var_50]
0x18002f5ec  lea     rdx, [rbp+57h+var_80]
0x18002f5f0  lea     rcx, ?g_HrAll@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@2@@std@@A; std::map<std::wstring,long> g_HrAll
0x18002f5f7  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,long>>,0>>::insert<0,0>(std::pair<std::wstring const,long> &&)
0x18002f5fc  nop
0x18002f5fd  jmp     loc_18002F715
0x18002f602  call    cs:__imp_RtlGetCurrentServiceSessionId
0x18002f608  test    eax, eax
0x18002f60a  jz      short loc_18002F661
0x18002f60c  mov     edx, eax
0x18002f60e  lea     rcx, aIsrunningincon; "IsRunningInContainer: Detected containe"...
0x18002f615  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002f61a  call    ?IsAllowOnContainerRegistrySet@@YAHXZ; IsAllowOnContainerRegistrySet(void)
0x18002f61f  test    eax, eax
0x18002f621  jnz     short loc_18002F661
0x18002f623  lea     rcx, aSkippingConfid_0; "Skipping confidence DB parsing: Running"...
0x18002f62a  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002f62f  lea     rdx, aSkipbcfrunning; "SkipBCFRunningInContainer"
0x18002f636  lea     rcx, [rbp+57h+var_50]
0x18002f63a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002f63f  mov     ebx, 1
0x18002f644  mov     [rbp+57h+var_30], ebx
0x18002f647  lea     r8, [rbp+57h+var_50]
0x18002f64b  lea     rdx, [rbp+57h+var_80]
0x18002f64f  lea     rcx, ?g_HrAll@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@2@@std@@A; std::map<std::wstring,long> g_HrAll
0x18002f656  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,long>>,0>>::insert<0,0>(std::pair<std::wstring const,long> &&)
0x18002f65b  nop
0x18002f65c  jmp     loc_18002F715
0x18002f661  call    ?IsHyperVGuest@@YAHXZ; IsHyperVGuest(void)
0x18002f666  test    eax, eax
0x18002f668  jz      short loc_18002F6B3
0x18002f66a  call    ?IsAllowOnHyperVRegistrySet@@YAHXZ; IsAllowOnHyperVRegistrySet(void)
0x18002f66f  test    eax, eax
0x18002f671  jnz     short loc_18002F6B3
0x18002f673  lea     rcx, aSkippingConfid; "Skipping confidence DB parsing: IsHyper"...
0x18002f67a  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002f67f  mov     ebx, 1
0x18002f684  mov     dword ptr [rbp+57h+var_90], ebx
0x18002f687  lea     r8, [rbp+57h+var_90]
0x18002f68b  lea     rdx, aSkipbcfishyper; "SkipBCFIsHyperVGuest"
0x18002f692  lea     rcx, [rbp+57h+var_50]
0x18002f696  call    ??$?0AEAY0BE@$$CBGAEAJ$0A@@?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@QEAA@AEAY0BE@$$CBGAEAJ@Z; std::pair<std::wstring const,long>::pair<std::wstring const,long>(ushort const (&)[20],long &)
0x18002f69b  nop
0x18002f69c  lea     r8, [rbp+57h+var_50]
0x18002f6a0  lea     rdx, [rbp+57h+var_80]
0x18002f6a4  lea     rcx, ?g_HrAll@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@2@@std@@A; std::map<std::wstring,long> g_HrAll
0x18002f6ab  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,long>>,0>>::insert<0,0>(std::pair<std::wstring const,long> &&)
0x18002f6b0  nop
0x18002f6b1  jmp     short loc_18002F715
0x18002f6b3  mov     dword ptr [rbp+57h+var_90], r15d
0x18002f6b7  xor     r8d, r8d
0x18002f6ba  lea     rdx, [rbp+57h+var_90]
0x18002f6be  xor     ecx, ecx
0x18002f6c0  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18002f6c6  mov     eax, dword ptr [rbp+57h+var_90]
0x18002f6c9  add     eax, 0FFFFFFF7h
0x18002f6cc  test    eax, 0FFFFFFFBh
0x18002f6d1  jnz     short loc_18002F720
0x18002f6d3  call    ?IsSkipOnServerRegistrySet@@YAHXZ; IsSkipOnServerRegistrySet(void)
0x18002f6d8  test    eax, eax
0x18002f6da  jz      short loc_18002F720
0x18002f6dc  lea     rcx, aSkippingOnServ; "Skipping on Server"
0x18002f6e3  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002f6e8  lea     rdx, aSkipbcfisserve; "SkipBCFIsServer"
0x18002f6ef  lea     rcx, [rbp+57h+var_50]
0x18002f6f3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002f6f8  mov     ebx, 1
0x18002f6fd  mov     [rbp+57h+var_30], ebx
0x18002f700  lea     r8, [rbp+57h+var_50]
0x18002f704  lea     rdx, [rbp+57h+var_80]
0x18002f708  lea     rcx, ?g_HrAll@@3V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@2@@std@@A; std::map<std::wstring,long> g_HrAll
0x18002f70f  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,long>>,0>>::insert<0,0>(std::pair<std::wstring const,long> &&)
0x18002f714  nop
0x18002f715  lea     rcx, [rbp+57h+var_50]
0x18002f719  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002f71e  jmp     short loc_18002F723
0x18002f720  mov     ebx, r15d
0x18002f723  lea     rcx, [rbp+57h+var_88]
0x18002f727  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002f72c  nop
0x18002f72d  lea     rcx, [rbp+57h+var_70]
0x18002f731  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002f736  mov     eax, ebx
0x18002f738  mov     rcx, [rbp+57h+var_28]
0x18002f73c  xor     rcx, rsp; StackCookie
0x18002f73f  call    __security_check_cookie
0x18002f744  mov     rbx, [rsp+0C0h+arg_10]
0x18002f74c  add     rsp, 0A0h
0x18002f753  pop     r15
0x18002f755  pop     r14
0x18002f757  pop     rdi
0x18002f758  pop     rsi
0x18002f759  pop     rbp
0x18002f75a  retn
```
