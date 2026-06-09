# RcsGroupChatAdapterImpl::AddParticipants(utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> const &)

- ea: `0x1800c1e90`
- end: `0x1800c21c4`
- name: `?AddParticipants@RcsGroupChatAdapterImpl@@UEAAJAEBV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z`
- size: `820`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008870`
- `0x18000a754`
- `0x180030bd0`
- `0x18006b108`
- `0x180084738`
- `0x1800bbc88`
- `0x1800bdf9c`
- `0x1800c0aac`
- `0x1800c0c50`
- `0x1800c19f0`
- `0x1800c1e90`
- `0x1800c4e60`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c20d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c20d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c20c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c20c0`

## string_xrefs

- `0x1800c1ed8`: `Windows.Foundation.Uri`
- `0x1800c1f05`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcschatadapterimpl.cpp`
- `0x1800c1f4b`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcschatadapterimpl.cpp`
- `0x1800c2058`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcschatadapterimpl.cpp`
- `0x1800c207d`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcschatadapterimpl.cpp`
- `0x1800c216a`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcschatadapterimpl.cpp`

## pseudocode

```c
__int64 __fastcall RcsGroupChatAdapterImpl::AddParticipants(__int64 a1, const unsigned __int16 ***a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rcx
  char v7; // r8
  int v8; // eax
  __int64 v9; // r9
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v11)(_QWORD, GUID *, __int64 *); // rbx
  const unsigned __int16 **v12; // rbx
  const unsigned __int16 **v13; // rsi
  int UriStringFromDialString; // eax
  int v15; // r14d
  __int64 v16; // r15
  __int64 (__fastcall *v17)(__int64, PVOID, __int64 *); // r14
  char v18; // r8
  HSTRING_HEADER *v19; // rax
  __int64 v20; // r9
  int v21; // eax
  __int64 v22; // r9
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v26; // [rsp+30h] [rbp-59h] BYREF
  __int64 (__fastcall ***v27)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-51h] BYREF
  const WCHAR *Reserved1; // [rsp+40h] [rbp-49h] BYREF
  __int64 v29; // [rsp+48h] [rbp-41h] BYREF
  __int64 v30; // [rsp+50h] [rbp-39h] BYREF
  const WCHAR *v31; // [rsp+58h] [rbp-31h] BYREF
  __int64 (__fastcall *v32)(); // [rsp+60h] [rbp-29h] BYREF
  __int64 v33; // [rsp+68h] [rbp-21h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-19h] BYREF
  __int64 v35; // [rsp+88h] [rbp-1h]
  HSTRING_HEADER v36; // [rsp+90h] [rbp+7h] BYREF

  v30 = 0;
  v35 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Foundation.Uri", 0x17u, 0x16u);
  v4 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
         v35,
         (__int64)&v30);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v27 = 0;
    v26 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
    v8 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Foundation::Uri,Windows::Foundation::Collections::Internal::AgileVector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,0>>(
           v6,
           &v27,
           v7);
    v5 = v8;
    if ( v8 >= 0 )
    {
      v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v27;
      v11 = **v27;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
      v8 = v11(v10, &GUID_b0d63b78_78ad_5e31_b6d8_e32a0e16c447, &v26);
      v5 = v8;
      if ( v8 >= 0 )
      {
        v12 = *a2;
        v13 = a2[1];
        while ( v12 != v13 )
        {
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(&hstringHeader);
          UriStringFromDialString = GetUriStringFromDialString(*v12, (__int64)&hstringHeader);
          v15 = UriStringFromDialString;
          if ( UriStringFromDialString < 0 )
          {
            Log_HREvent_102(
              (unsigned int)UriStringFromDialString,
              1,
              "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcschatadapterimpl.cpp",
              368);
            goto LABEL_18;
          }
          v16 = v30;
          v29 = 0;
          v17 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v30 + 48LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
          Reserved1 = (const WCHAR *)hstringHeader.Reserved.Reserved1;
          v19 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v36, &Reserved1, v18);
          v15 = v17(v16, v19[1].Reserved.Reserved1, &v29);
          if ( v15 < 0 )
          {
            v20 = 371;
LABEL_16:
            Log_HREvent_102(
              (unsigned int)v15,
              1,
              "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcschatadapterimpl.cpp",
              v20);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
LABEL_18:
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&hstringHeader);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
            v5 = v15;
            goto LABEL_26;
          }
          v15 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), __int64))(*v10)[13])(
                  v10,
                  v29);
          if ( v15 < 0 )
          {
            v20 = 372;
            goto LABEL_16;
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&hstringHeader);
          v12 += 4;
        }
        Reserved1 = 0;
        EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
        Microsoft::WRL::ComPtr<Windows::Phone::Restricted::Cellular::Rcs::IRcsChat>::operator=(&Reserved1, a1 + 24);
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
        if ( Reserved1 )
        {
          v31 = Reserved1;
          v36.Reserved.Reserved1 = &v31;
          v33 = v26;
          *(_QWORD *)&v36.Reserved.Reserved2[8] = &v32;
          v32 =  MessagingMultiSimConverter::`vcall'{184,{flat}};
          *(_QWORD *)&v36.Reserved.Reserved2[16] = &v33;
          v21 = AwaitActionHelper<_lambda_a43b19fa30d67ba7e5c4c665a95489cb_>(&v36);
          v5 = v21;
          if ( v21 >= 0 )
          {
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&Reserved1);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
            return 0;
          }
          v22 = 382;
          v23 = 1;
          v24 = (unsigned int)v21;
        }
        else
        {
          v5 = -2147467262;
          v22 = 381;
          v24 = 2147500034LL;
          v23 = 0;
        }
        Log_HREvent_102(
          v24,
          v23,
          "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcschatadapterimpl.cpp",
          v22);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&Reserved1);
        goto LABEL_25;
      }
      v9 = 363;
    }
    else
    {
      v9 = 362;
    }
    Log_HREvent_102(
      (unsigned int)v8,
      1,
      "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcschatadapterimpl.cpp",
      v9);
LABEL_25:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
    goto LABEL_26;
  }
  Log_HREvent_102(
    (unsigned int)v4,
    1,
    "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcschatadapterimpl.cpp",
    358);
LABEL_26:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  return v5;
}

```

## disassembly

```asm
0x1800c1e90  mov     [rsp-8+arg_8], rbx
0x1800c1e95  mov     [rsp-8+arg_10], rsi
0x1800c1e9a  push    rbp
0x1800c1e9b  push    rdi
0x1800c1e9c  push    r13
0x1800c1e9e  push    r14
0x1800c1ea0  push    r15
0x1800c1ea2  lea     rbp, [rsp-37h]
0x1800c1ea7  sub     rsp, 0C0h
0x1800c1eae  mov     rax, cs:__security_cookie
0x1800c1eb5  xor     rax, rsp
0x1800c1eb8  mov     [rbp+57h+var_30], rax
0x1800c1ebc  mov     r9d, 16h; unsigned int
0x1800c1ec2  mov     [rbp+57h+var_90], 0
0x1800c1eca  mov     rsi, rdx
0x1800c1ecd  mov     [rbp+57h+var_58], 0
0x1800c1ed5  mov     r13, rcx
0x1800c1ed8  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x1800c1edf  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800c1ee3  lea     r8d, [r9+1]; unsigned int
0x1800c1ee7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800c1eec  mov     rcx, [rbp+57h+var_58]
0x1800c1ef0  lea     rdx, [rbp+57h+var_90]
0x1800c1ef4  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x1800c1ef9  mov     ebx, eax
0x1800c1efb  test    eax, eax
0x1800c1efd  jns     short loc_1800C1F1D
0x1800c1eff  mov     r9d, 166h
0x1800c1f05  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800c1f0c  mov     edx, 1
0x1800c1f11  mov     ecx, eax
0x1800c1f13  call    Log_HREvent_102
0x1800c1f18  jmp     loc_1800C2191
0x1800c1f1d  lea     rcx, [rbp+57h+var_A8]
0x1800c1f21  mov     [rbp+57h+var_A8], 0
0x1800c1f29  mov     [rbp+57h+var_B0], 0
0x1800c1f31  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c1f36  lea     rdx, [rbp+57h+var_A8]
0x1800c1f3a  call    ??$CreateExternalObjectVector@VUri@Foundation@Windows@@V?$AgileVector@PEAVUri@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAVUri@Foundation@Windows@@@Internal@Collections@23@U?$DefaultLifetimeTraits@PEAVUri@Foundation@Windows@@@5623@$0A@@Internal@Collections@23@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVUri@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAVUri@Foundation@Windows@@@Internal@Collections@23@U?$DefaultLifetimeTraits@PEAVUri@Foundation@Windows@@@5623@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Foundation::Uri,Windows::Foundation::Collections::Internal::AgileVector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,0> * *)
0x1800c1f3f  mov     ebx, eax
0x1800c1f41  test    eax, eax
0x1800c1f43  jns     short loc_1800C1F63
0x1800c1f45  mov     r9d, 16Ah
0x1800c1f4b  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800c1f52  mov     edx, 1
0x1800c1f57  mov     ecx, eax
0x1800c1f59  call    Log_HREvent_102
0x1800c1f5e  jmp     loc_1800C217F
0x1800c1f63  mov     rdi, [rbp+57h+var_A8]
0x1800c1f67  lea     rcx, [rbp+57h+var_B0]
0x1800c1f6b  mov     rax, [rdi]
0x1800c1f6e  mov     rbx, [rax]
0x1800c1f71  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c1f76  lea     r8, [rbp+57h+var_B0]
0x1800c1f7a  mov     rcx, rdi
0x1800c1f7d  lea     rdx, _GUID_b0d63b78_78ad_5e31_b6d8_e32a0e16c447
0x1800c1f84  mov     rax, rbx
0x1800c1f87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1f8c  mov     ebx, eax
0x1800c1f8e  test    eax, eax
0x1800c1f90  jns     short loc_1800C1F9A
0x1800c1f92  mov     r9d, 16Bh
0x1800c1f98  jmp     short loc_1800C1F4B
0x1800c1f9a  mov     rbx, [rsi]
0x1800c1f9d  mov     rsi, [rsi+8]
0x1800c1fa1  cmp     rbx, rsi
0x1800c1fa4  jz      loc_1800C20B4
0x1800c1faa  lea     rcx, [rbp+57h+hstringHeader]
0x1800c1fae  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800c1fb3  mov     rcx, [rbx]
0x1800c1fb6  lea     rdx, [rbp+57h+hstringHeader]
0x1800c1fba  call    ?GetUriStringFromDialString@@YAJPEBGPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; GetUriStringFromDialString(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x1800c1fbf  mov     r14d, eax
0x1800c1fc2  test    eax, eax
0x1800c1fc4  js      loc_1800C2077
0x1800c1fca  mov     r15, [rbp+57h+var_90]
0x1800c1fce  lea     rcx, [rbp+57h+var_98]
0x1800c1fd2  mov     [rbp+57h+var_98], 0
0x1800c1fda  mov     rax, [r15]
0x1800c1fdd  mov     r14, [rax+30h]
0x1800c1fe1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c1fe6  mov     rdx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x1800c1fea  lea     rcx, [rbp+57h+var_50]
0x1800c1fee  mov     [rbp+57h+var_A0], rdx
0x1800c1ff2  lea     rdx, [rbp+57h+var_A0]
0x1800c1ff6  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800c1ffb  lea     r8, [rbp+57h+var_98]
0x1800c1fff  mov     rcx, r15
0x1800c2002  mov     rdx, [rax+18h]
0x1800c2006  mov     rax, r14
0x1800c2009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c200e  mov     r14d, eax
0x1800c2011  test    eax, eax
0x1800c2013  js      short loc_1800C2052
0x1800c2015  mov     rax, [rdi]
0x1800c2018  mov     rcx, rdi
0x1800c201b  mov     rdx, [rbp+57h+var_98]
0x1800c201f  mov     rax, [rax+68h]
0x1800c2023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2028  mov     r14d, eax
0x1800c202b  test    eax, eax
0x1800c202d  js      short loc_1800C204A
0x1800c202f  lea     rcx, [rbp+57h+var_98]
0x1800c2033  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c2038  lea     rcx, [rbp+57h+hstringHeader]
0x1800c203c  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800c2041  add     rbx, 20h ; ' '
0x1800c2045  jmp     loc_1800C1FA1
0x1800c204a  mov     r9d, 174h
0x1800c2050  jmp     short loc_1800C2058
0x1800c2052  mov     r9d, 173h
0x1800c2058  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800c205f  mov     edx, 1
0x1800c2064  mov     ecx, r14d
0x1800c2067  call    Log_HREvent_102
0x1800c206c  lea     rcx, [rbp+57h+var_98]
0x1800c2070  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c2075  jmp     short loc_1800C2091
0x1800c2077  mov     r9d, 170h
0x1800c207d  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800c2084  mov     edx, 1
0x1800c2089  mov     ecx, r14d
0x1800c208c  call    Log_HREvent_102
0x1800c2091  lea     rcx, [rbp+57h+hstringHeader]
0x1800c2095  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800c209a  lea     rcx, [rbp+57h+var_B0]
0x1800c209e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c20a3  lea     rcx, [rbp+57h+var_A8]
0x1800c20a7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c20ac  mov     ebx, r14d
0x1800c20af  jmp     loc_1800C2191
0x1800c20b4  lea     rcx, [r13+40h]; lpCriticalSection
0x1800c20b8  mov     [rbp+57h+var_A0], 0
0x1800c20c0  call    cs:__imp_EnterCriticalSection
0x1800c20c6  lea     rdx, [r13+18h]
0x1800c20ca  lea     rcx, [rbp+57h+var_A0]
0x1800c20ce  call    ??4?$ComPtr@UIRcsChat@Rcs@Cellular@Restricted@Phone@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Phone::Restricted::Cellular::Rcs::IRcsChat>::operator=(Microsoft::WRL::ComPtr<Windows::Phone::Restricted::Cellular::Rcs::IRcsChat> const &)
0x1800c20d3  lea     rcx, [r13+40h]; lpCriticalSection
0x1800c20d7  call    cs:__imp_LeaveCriticalSection
0x1800c20dd  mov     rax, [rbp+57h+var_A0]
0x1800c20e1  test    rax, rax
0x1800c20e4  jz      short loc_1800C215B
0x1800c20e6  mov     rcx, [rbp+57h+var_B0]
0x1800c20ea  mov     [rbp+57h+var_88], rax
0x1800c20ee  lea     rax, [rbp+57h+var_88]
0x1800c20f2  mov     [rbp+57h+var_50], rax
0x1800c20f6  lea     rax, [rbp+57h+var_80]
0x1800c20fa  mov     [rbp+57h+var_78], rcx
0x1800c20fe  lea     rcx, ??_9MessagingMultiSimConverter@@$BLI@AA; [thunk]: MessagingMultiSimConverter::`vcall'{184,{flat}}
0x1800c2105  mov     [rbp+57h+var_48], rax
0x1800c2109  lea     rax, [rbp+57h+var_78]
0x1800c210d  mov     [rbp+57h+var_80], rcx
0x1800c2111  lea     rcx, [rbp+57h+var_50]
0x1800c2115  mov     [rbp+57h+var_40], rax
0x1800c2119  call    ??$AwaitActionHelper@V_lambda_a43b19fa30d67ba7e5c4c665a95489cb_@@@@YAJAEBV_lambda_a43b19fa30d67ba7e5c4c665a95489cb_@@@Z; AwaitActionHelper<_lambda_a43b19fa30d67ba7e5c4c665a95489cb_>(_lambda_a43b19fa30d67ba7e5c4c665a95489cb_ const &)
0x1800c211e  mov     ebx, eax
0x1800c2120  test    eax, eax
0x1800c2122  jns     short loc_1800C2133
0x1800c2124  mov     r9d, 17Eh
0x1800c212a  mov     edx, 1
0x1800c212f  mov     ecx, eax
0x1800c2131  jmp     short loc_1800C216A
0x1800c2133  lea     rcx, [rbp+57h+var_A0]
0x1800c2137  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c213c  lea     rcx, [rbp+57h+var_B0]
0x1800c2140  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c2145  lea     rcx, [rbp+57h+var_A8]
0x1800c2149  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c214e  lea     rcx, [rbp+57h+var_90]
0x1800c2152  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c2157  xor     eax, eax
0x1800c2159  jmp     short loc_1800C219C
0x1800c215b  mov     ebx, 80004002h
0x1800c2160  mov     r9d, 17Dh
0x1800c2166  mov     ecx, ebx
0x1800c2168  xor     edx, edx
0x1800c216a  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800c2171  call    Log_HREvent_102
0x1800c2176  lea     rcx, [rbp+57h+var_A0]
0x1800c217a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c217f  lea     rcx, [rbp+57h+var_B0]
0x1800c2183  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c2188  lea     rcx, [rbp+57h+var_A8]
0x1800c218c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c2191  lea     rcx, [rbp+57h+var_90]
0x1800c2195  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c219a  mov     eax, ebx
0x1800c219c  mov     rcx, [rbp+57h+var_30]
0x1800c21a0  xor     rcx, rsp; StackCookie
0x1800c21a3  call    __security_check_cookie
0x1800c21a8  lea     r11, [rsp+0E0h+var_20]
0x1800c21b0  mov     rbx, [r11+38h]
0x1800c21b4  mov     rsi, [r11+40h]
0x1800c21b8  mov     rsp, r11
0x1800c21bb  pop     r15
0x1800c21bd  pop     r14
0x1800c21bf  pop     r13
0x1800c21c1  pop     rdi
0x1800c21c2  pop     rbp
0x1800c21c3  retn
```
