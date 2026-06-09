# SystemSettings::PenSettings::DevicesPenSetActionBase::GetCustomDesktopAppDisplayName(void)

- ea: `0x18002674c`
- end: `0x180026998`
- name: `?GetCustomDesktopAppDisplayName@DevicesPenSetActionBase@PenSettings@SystemSettings@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `588`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180027350`
- `0x180028910`
- `0x18002faf0`

## callees

- `0x1800030e0`
- `0x180008128`
- `0x18001033c`
- `0x18001a378`
- `0x18001b4a0`
- `0x18001f3e8`
- `0x180020740`
- `0x18002674c`
- `0x180027dcc`
- `0x18002ee30`
- `0x180031514`
- `0x18005d010`

## import_xrefs

- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x1800267e8`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x1800267e8`

## string_xrefs

- `0x1800267ab`: `CustomAppPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall SystemSettings::PenSettings::DevicesPenSetActionBase::GetCustomDesktopAppDisplayName(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // r9
  __int64 v4; // rax
  int v5; // eax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  unsigned __int16 *v13; // [rsp+30h] [rbp-59h] BYREF
  void *ppv; // [rsp+38h] [rbp-51h] BYREF
  __int64 v15; // [rsp+40h] [rbp-49h] BYREF
  PCWSTR pszPath[2]; // [rsp+48h] [rbp-41h] BYREF
  _BYTE v17[32]; // [rsp+58h] [rbp-31h] BYREF
  _BYTE v18[32]; // [rsp+78h] [rbp-11h] BYREF
  _BYTE v19[32]; // [rsp+98h] [rbp+Fh] BYREF
  _BYTE v20[32]; // [rsp+B8h] [rbp+2Fh] BYREF

  pszPath[0] = (PCWSTR)a2;
  v13 = 0;
  SystemSettings::PenSettings::ActionTypeOptionManager::GetPrimitiveSpecificParameters(
    *(_DWORD *)(a1 + 272),
    (unsigned int)&v13,
    0,
    0,
    0,
    0);
  pszPath[0] = 0;
  if ( (int)SHRegAllocData(HKEY_CURRENT_USER, v13, L"CustomAppPath", v3, (void **)pszPath) < 0 )
    goto LABEL_14;
  ppv = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  if ( SHCreateItemFromParsingName(pszPath[0], 0, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv) < 0 )
  {
LABEL_13:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
LABEL_14:
    *(_OWORD *)a2 = 0;
    *(_QWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 24) = 7;
    *(_WORD *)a2 = 0;
    goto LABEL_15;
  }
  v15 = 0;
  v4 = *(_QWORD *)ppv;
  v15 = 0;
  v5 = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, __int64 *))(v4 + 136))(ppv, &PKEY_FileDescription, &v15);
  v13 = 0;
  if ( v5 >= 0 )
  {
    v7 = *(_QWORD *)ppv;
    v13 = 0;
    if ( (*(int (__fastcall **)(void *, _QWORD, unsigned __int16 **))(v7 + 40))(ppv, 0, &v13) >= 0 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::GetImpl'::`2'::impl) )
      {
        std::wstring::wstring(a2, v15);
      }
      else
      {
        v8 = std::wstring::wstring(v20, v13);
        v9 = std::wstring::wstring(v19, v15);
        v10 = std::operator+<unsigned short>(v18, v9, L" (");
        std::wstring::wstring(v17, v11, v10, v8);
        std::operator+<unsigned short>(a2, v17, L")");
        std::wstring::_Tidy_deallocate(v17);
        std::wstring::_Tidy_deallocate(v18);
        std::wstring::_Tidy_deallocate(v19);
        std::wstring::_Tidy_deallocate(v20);
      }
      goto LABEL_6;
    }
    goto LABEL_12;
  }
  v6 = *(_QWORD *)ppv;
  v13 = 0;
  if ( (*(int (__fastcall **)(void *, _QWORD, unsigned __int16 **))(v6 + 40))(ppv, 0, &v13) < 0 )
  {
LABEL_12:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v13);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v15);
    goto LABEL_13;
  }
  std::wstring::wstring(a2, v13);
LABEL_6:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v13);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v15);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
LABEL_15:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(pszPath);
  return a2;
}

```

## disassembly

```asm
0x18002674c  mov     [rsp-8+arg_0], rbx
0x180026751  mov     [rsp-8+arg_10], rdi
0x180026756  push    rbp
0x180026757  lea     rbp, [rsp-57h]
0x18002675c  sub     rsp, 0E0h
0x180026763  mov     rax, cs:__security_cookie
0x18002676a  xor     rax, rsp
0x18002676d  mov     [rbp+57h+var_8], rax
0x180026771  mov     rdi, rdx
0x180026774  mov     [rbp+57h+pszPath], rdx
0x180026778  xor     ebx, ebx
0x18002677a  mov     [rbp+57h+var_B0], rbx
0x18002677e  mov     [rsp+0E0h+var_B8], rbx; unsigned int *
0x180026783  mov     [rsp+0E0h+var_C0], rbx
0x180026788  xor     r9d, r9d
0x18002678b  xor     r8d, r8d
0x18002678e  lea     rdx, [rbp+57h+var_B0]
0x180026792  mov     ecx, [rcx+110h]
0x180026798  call    ?GetPrimitiveSpecificParameters@ActionTypeOptionManager@PenSettings@SystemSettings@@SAXW4PenClickType@@PEAPEBG1PEAPEAV?$vector@UPenActionTypeResourceMapping_@PenSettings@SystemSettings@@V?$allocator@UPenActionTypeResourceMapping_@PenSettings@SystemSettings@@@std@@@std@@11@Z; SystemSettings::PenSettings::ActionTypeOptionManager::GetPrimitiveSpecificParameters(PenClickType,ushort const * *,ushort const * *,std::vector<SystemSettings::PenSettings::PenActionTypeResourceMapping_> * *,ushort const * *,ushort const * *)
0x18002679d  nop
0x18002679e  mov     [rbp+57h+pszPath], rbx
0x1800267a2  lea     rax, [rbp+57h+pszPath]
0x1800267a6  mov     [rsp+0E0h+var_C0], rax; void **
0x1800267ab  lea     r8, aCustomapppath; "CustomAppPath"
0x1800267b2  mov     rdx, [rbp+57h+var_B0]; unsigned __int16 *
0x1800267b6  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1800267bd  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x1800267c2  test    eax, eax
0x1800267c4  js      loc_180026956
0x1800267ca  mov     [rbp+57h+ppv], rbx
0x1800267ce  lea     rcx, [rbp+57h+ppv]
0x1800267d2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800267d7  lea     r9, [rbp+57h+ppv]; ppv
0x1800267db  lea     r8, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x1800267e2  xor     edx, edx; pbc
0x1800267e4  mov     rcx, [rbp+57h+pszPath]; pszPath
0x1800267e8  call    cs:__imp_SHCreateItemFromParsingName
0x1800267ee  test    eax, eax
0x1800267f0  js      loc_18002694D
0x1800267f6  mov     [rbp+57h+var_A0], rbx
0x1800267fa  mov     rcx, [rbp+57h+ppv]
0x1800267fe  mov     rax, [rcx]
0x180026801  mov     [rbp+57h+var_A0], rbx
0x180026805  lea     r8, [rbp+57h+var_A0]
0x180026809  lea     rdx, PKEY_FileDescription
0x180026810  mov     rax, [rax+88h]
0x180026817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002681c  mov     [rbp+57h+var_B0], rbx
0x180026820  test    eax, eax
0x180026822  jns     short loc_180026876
0x180026824  mov     rcx, [rbp+57h+ppv]
0x180026828  mov     rax, [rcx]
0x18002682b  mov     [rbp+57h+var_B0], rbx
0x18002682f  lea     r8, [rbp+57h+var_B0]
0x180026833  xor     edx, edx
0x180026835  mov     rax, [rax+28h]
0x180026839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002683e  test    eax, eax
0x180026840  js      short loc_180026871
0x180026842  mov     rdx, [rbp+57h+var_B0]
0x180026846  mov     rcx, rdi
0x180026849  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002684e  nop
0x18002684f  lea     rcx, [rbp+57h+var_B0]
0x180026853  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180026858  nop
0x180026859  lea     rcx, [rbp+57h+var_A0]
0x18002685d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180026862  nop
0x180026863  lea     rcx, [rbp+57h+ppv]
0x180026867  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002686c  jmp     loc_18002696B
0x180026871  jmp     loc_180026939
0x180026876  mov     rcx, [rbp+57h+ppv]
0x18002687a  mov     rax, [rcx]
0x18002687d  mov     [rbp+57h+var_B0], rbx
0x180026881  lea     r8, [rbp+57h+var_B0]
0x180026885  xor     edx, edx
0x180026887  mov     rax, [rax+28h]
0x18002688b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026890  test    eax, eax
0x180026892  js      loc_180026939
0x180026898  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PenButtonSettingsModernization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PenButtonSettingsModernization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization> `wil::Feature<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::GetImpl(void)'::`2'::impl
0x18002689f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PenButtonSettingsModernization@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(void)
0x1800268a4  test    al, al
0x1800268a6  jz      short loc_1800268B7
0x1800268a8  mov     rdx, [rbp+57h+var_A0]
0x1800268ac  mov     rcx, rdi
0x1800268af  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800268b4  nop
0x1800268b5  jmp     short loc_18002684F
0x1800268b7  mov     rdx, [rbp+57h+var_B0]
0x1800268bb  lea     rcx, [rbp+57h+var_28]
0x1800268bf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800268c4  mov     rbx, rax
0x1800268c7  mov     rdx, [rbp+57h+var_A0]
0x1800268cb  lea     rcx, [rbp+57h+var_48]
0x1800268cf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800268d4  nop
0x1800268d5  lea     r8, asc_18006A600; " ("
0x1800268dc  mov     rdx, rax
0x1800268df  lea     rcx, [rbp+57h+var_68]
0x1800268e3  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800268e8  nop
0x1800268e9  mov     r9, rbx
0x1800268ec  mov     r8, rax
0x1800268ef  lea     rcx, [rbp+57h+var_88]
0x1800268f3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x1800268f8  nop
0x1800268f9  lea     r8, asc_18006A608; ")"
0x180026900  lea     rdx, [rbp+57h+var_88]
0x180026904  mov     rcx, rdi
0x180026907  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18002690c  nop
0x18002690d  lea     rcx, [rbp+57h+var_88]
0x180026911  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026916  nop
0x180026917  lea     rcx, [rbp+57h+var_68]
0x18002691b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026920  nop
0x180026921  lea     rcx, [rbp+57h+var_48]
0x180026925  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002692a  nop
0x18002692b  lea     rcx, [rbp+57h+var_28]
0x18002692f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026934  jmp     loc_1800268B5
0x180026939  lea     rcx, [rbp+57h+var_B0]
0x18002693d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180026942  nop
0x180026943  lea     rcx, [rbp+57h+var_A0]
0x180026947  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002694c  nop
0x18002694d  lea     rcx, [rbp+57h+ppv]
0x180026951  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026956  xorps   xmm0, xmm0
0x180026959  movups  xmmword ptr [rdi], xmm0
0x18002695c  mov     [rdi+10h], rbx
0x180026960  mov     qword ptr [rdi+18h], 7
0x180026968  mov     [rdi], bx
0x18002696b  lea     rcx, [rbp+57h+pszPath]
0x18002696f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180026974  mov     rax, rdi
0x180026977  mov     rcx, [rbp+57h+var_8]
0x18002697b  xor     rcx, rsp; StackCookie
0x18002697e  call    __security_check_cookie
0x180026983  lea     r11, [rsp+0E0h+var_s0]
0x18002698b  mov     rbx, [r11+10h]
0x18002698f  mov     rdi, [r11+20h]
0x180026993  mov     rsp, r11
0x180026996  pop     rbp
0x180026997  retn
```
