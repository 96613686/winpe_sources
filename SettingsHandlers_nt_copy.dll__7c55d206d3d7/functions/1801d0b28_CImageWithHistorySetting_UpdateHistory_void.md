# CImageWithHistorySetting::UpdateHistory(void)

- ea: `0x1801d0b28`
- end: `0x1801d0e9f`
- name: `?UpdateHistory@CImageWithHistorySetting@@IEAAXXZ`
- size: `887`
- prototype: `void __fastcall(CImageWithHistorySetting *__hidden this)`
- caller_count: `4`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180129c00`
- `0x180139ec0`
- `0x18013a1d8`
- `0x1801cd190`

## callees

- `0x180011bb0`
- `0x180021640`
- `0x18002242c`
- `0x180033590`
- `0x18003cdf0`
- `0x18003d280`
- `0x180040000`
- `0x180046850`
- `0x18009efa8`
- `0x1800ac518`
- `0x1801d0b28`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d0c31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d0cb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d0cea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d0d12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d0d41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d0d7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d0c31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d0cb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d0cea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d0d12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d0d41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d0d7c`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall CImageWithHistorySetting::UpdateHistory(CImageWithHistorySetting *this)
{
  int (__fastcall *v2)(CImageWithHistorySetting *, __int64 *); // rbx
  __int64 v3; // rbx
  volatile int *v4; // rdx
  __int64 v5; // rcx
  unsigned int v6; // r14d
  __int64 v7; // rbx
  int v8; // ebx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  __int64 v11; // rbx
  __int64 v12; // rdi
  int (__fastcall *v13)(__int64, HSTRING *); // rbx
  HSTRING v14; // r8
  int v15; // eax
  int v16; // edi
  __int64 v17; // rbx
  unsigned int v18; // eax
  __int64 v19; // r10
  signed __int64 v20; // rax
  signed __int64 v21; // rtt
  __int64 v22; // [rsp+20h] [rbp-38h] BYREF
  __int64 v23; // [rsp+28h] [rbp-30h] BYREF
  __int64 v24; // [rsp+30h] [rbp-28h] BYREF
  __int64 v25; // [rsp+38h] [rbp-20h] BYREF
  _QWORD v26[3]; // [rsp+40h] [rbp-18h] BYREF
  __int64 v27; // [rsp+90h] [rbp+38h] BYREF
  HSTRING string; // [rsp+98h] [rbp+40h] BYREF
  __int64 v29; // [rsp+A0h] [rbp+48h] BYREF
  HSTRING v30; // [rsp+A8h] [rbp+50h] BYREF

  v29 = 0;
  v2 = *(int (__fastcall **)(CImageWithHistorySetting *, __int64 *))(*(_QWORD *)this + 264LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(&v29);
  if ( v2(this, &v29) < 0 )
    goto LABEL_36;
  v26[0] = 0;
  v3 = v29;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v26);
  if ( (int)Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::GetAt(
              v3,
              0,
              v26) < 0 )
    goto LABEL_35;
  v5 = *((_QWORD *)this + 27);
  if ( !v5
    || (int)Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(
              v5,
              0,
              v26[0],
              0) < 0 )
  {
    goto LABEL_25;
  }
  LODWORD(v27) = 0;
  Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>>::get_Size(
    v29,
    &v27);
  v6 = 1;
  while ( v6 < (unsigned int)v27 )
  {
    v23 = 0;
    v7 = v29;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
    v8 = Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::GetAt(
           v7,
           v6,
           &v23);
    if ( v8 < 0 )
    {
LABEL_20:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
      ++v6;
      if ( v8 < 0 )
        goto LABEL_25;
    }
    else
    {
      v25 = 0;
      v8 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&v23, &v25);
      if ( v8 < 0 )
        goto LABEL_19;
      v30 = 0;
      v9 = v25;
      v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v25 + 152LL);
      WindowsDeleteString(0);
      v30 = 0;
      v8 = v10(v9, &v30);
      if ( v8 < 0 )
        goto LABEL_18;
      v22 = 0;
      v11 = *((_QWORD *)this + 27);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
      if ( (int)Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::GetAt(
                  v11,
                  v6,
                  &v22) < 0 )
        goto LABEL_17;
      v24 = 0;
      if ( (int)Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&v22, &v24) < 0 )
        goto LABEL_16;
      string = 0;
      v12 = v24;
      v13 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v24 + 152LL);
      WindowsDeleteString(0);
      string = 0;
      if ( v13(v12, &string) < 0
        || (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                           (Microsoft::WRL::Wrappers::Details *)v30,
                           string,
                           v14) )
      {
        WindowsDeleteString(string);
LABEL_16:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
LABEL_17:
        v8 = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::RemoveAtInternal(
               *((_QWORD *)this + 27),
               v6--,
               0);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
LABEL_18:
        WindowsDeleteString(v30);
LABEL_19:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
        goto LABEL_20;
      }
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
      WindowsDeleteString(v30);
      v30 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
      ++v6;
    }
  }
  LODWORD(v27) = 0;
  LODWORD(string) = 0;
  Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>>::get_Size(
    *((_QWORD *)this + 27),
    &v27);
  Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>>::get_Size(
    v29,
    &string);
  v15 = (*(__int64 (__fastcall **)(CImageWithHistorySetting *))(*(_QWORD *)this + 272LL))(this);
  v16 = v27;
  if ( (_DWORD)v27 == v15 + 1 )
  {
    v17 = *((_QWORD *)this + 27);
    v18 = (*(__int64 (__fastcall **)(CImageWithHistorySetting *))(*(_QWORD *)this + 272LL))(this);
    Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::RemoveAtInternal(
      v17,
      v18,
      0);
    --v16;
  }
  if ( v16 != (_DWORD)string )
  {
LABEL_25:
    v19 = v29;
    if ( *((_QWORD *)this + 27) != v29 )
    {
      if ( v29 )
      {
        v20 = *(_QWORD *)(v29 + 88);
        while ( v20 >= 0 )
        {
          if ( (_DWORD)v20 != 0x7FFFFFFF )
          {
            v21 = v20;
            v20 = _InterlockedCompareExchange64((volatile signed __int64 *)(v19 + 88), v20 + 1, v20);
            if ( v21 != v20 )
              continue;
          }
          goto LABEL_33;
        }
        Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(2 * v20 + 16), v4);
      }
LABEL_33:
      v27 = *((_QWORD *)this + 27);
      *((_QWORD *)this + 27) = v19;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(&v27);
    }
    SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_180322520);
  }
LABEL_35:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v26);
LABEL_36:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(&v29);
}

```

## disassembly

```asm
0x1801d0b28  push    rbp
0x1801d0b2a  push    rbx
0x1801d0b2b  push    rsi
0x1801d0b2c  push    rdi
0x1801d0b2d  push    r14
0x1801d0b2f  push    r15
0x1801d0b31  mov     rbp, rsp
0x1801d0b34  sub     rsp, 58h
0x1801d0b38  mov     rsi, rcx
0x1801d0b3b  xor     r15d, r15d
0x1801d0b3e  mov     [rbp+arg_10], r15
0x1801d0b42  mov     rax, [rcx]
0x1801d0b45  mov     rbx, [rax+108h]
0x1801d0b4c  lea     rcx, [rbp+arg_10]
0x1801d0b50  call    ?InternalRelease@?$ComPtr@V?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(void)
0x1801d0b55  lea     rdx, [rbp+arg_10]
0x1801d0b59  mov     rcx, rsi
0x1801d0b5c  mov     rax, rbx
0x1801d0b5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d0b64  test    eax, eax
0x1801d0b66  js      loc_1801D0E88
0x1801d0b6c  mov     [rbp+var_18], r15
0x1801d0b70  mov     rbx, [rbp+arg_10]
0x1801d0b74  lea     rcx, [rbp+var_18]
0x1801d0b78  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801d0b7d  lea     r8, [rbp+var_18]
0x1801d0b81  xor     edx, edx
0x1801d0b83  mov     rcx, rbx
0x1801d0b86  call    ?GetAt@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@UEAAJIPEAPEAUIInspectable@@@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::GetAt(uint,IInspectable * *)
0x1801d0b8b  test    eax, eax
0x1801d0b8d  js      loc_1801D0E7E
0x1801d0b93  mov     rcx, [rsi+0D8h]
0x1801d0b9a  test    rcx, rcx
0x1801d0b9d  jz      loc_1801D0E16
0x1801d0ba3  xor     r9d, r9d
0x1801d0ba6  mov     r8, [rbp+var_18]
0x1801d0baa  xor     edx, edx
0x1801d0bac  call    ?InsertAtInternal@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUIInspectable@@_N@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(uint,IInspectable *,bool)
0x1801d0bb1  test    eax, eax
0x1801d0bb3  js      loc_1801D0E16
0x1801d0bb9  mov     dword ptr [rbp+arg_0], r15d
0x1801d0bbd  lea     rdx, [rbp+arg_0]
0x1801d0bc1  mov     rcx, [rbp+arg_10]
0x1801d0bc5  call    ?get_Size@?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$VectorOptions@PEAUHSTRING__@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAI@Z; Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>>::get_Size(uint *)
0x1801d0bca  lea     r14d, [r15+1]
0x1801d0bce  cmp     r14d, dword ptr [rbp+arg_0]
0x1801d0bd2  jnb     loc_1801D0DA9
0x1801d0bd8  mov     [rbp+var_30], r15
0x1801d0bdc  mov     rbx, [rbp+arg_10]
0x1801d0be0  lea     rcx, [rbp+var_30]
0x1801d0be4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801d0be9  lea     r8, [rbp+var_30]
0x1801d0bed  mov     edx, r14d
0x1801d0bf0  mov     rcx, rbx
0x1801d0bf3  call    ?GetAt@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@UEAAJIPEAPEAUIInspectable@@@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::GetAt(uint,IInspectable * *)
0x1801d0bf8  mov     ebx, eax
0x1801d0bfa  test    eax, eax
0x1801d0bfc  js      loc_1801D0D93
0x1801d0c02  mov     [rbp+var_20], r15
0x1801d0c06  lea     rdx, [rbp+var_20]
0x1801d0c0a  lea     rcx, [rbp+var_30]
0x1801d0c0e  call    ??$As@UIPropertyValue@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>>)
0x1801d0c13  mov     ebx, eax
0x1801d0c15  test    eax, eax
0x1801d0c17  js      loc_1801D0D89
0x1801d0c1d  mov     [rbp+arg_18], r15
0x1801d0c21  mov     rdi, [rbp+var_20]
0x1801d0c25  mov     rax, [rdi]
0x1801d0c28  mov     rbx, [rax+98h]
0x1801d0c2f  xor     ecx, ecx; string
0x1801d0c31  call    cs:__imp_WindowsDeleteString
0x1801d0c38  nop     dword ptr [rax+rax+00h]
0x1801d0c3d  mov     [rbp+arg_18], r15
0x1801d0c41  lea     rdx, [rbp+arg_18]
0x1801d0c45  mov     rcx, rdi
0x1801d0c48  mov     rax, rbx
0x1801d0c4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d0c50  mov     ebx, eax
0x1801d0c52  test    eax, eax
0x1801d0c54  js      loc_1801D0D78
0x1801d0c5a  mov     [rbp+var_38], r15
0x1801d0c5e  mov     rbx, [rsi+0D8h]
0x1801d0c65  lea     rcx, [rbp+var_38]
0x1801d0c69  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801d0c6e  lea     r8, [rbp+var_38]
0x1801d0c72  mov     edx, r14d
0x1801d0c75  mov     rcx, rbx
0x1801d0c78  call    ?GetAt@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@UEAAJIPEAPEAUIInspectable@@@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::GetAt(uint,IInspectable * *)
0x1801d0c7d  test    eax, eax
0x1801d0c7f  js      loc_1801D0D57
0x1801d0c85  mov     [rbp+var_28], r15
0x1801d0c89  lea     rdx, [rbp+var_28]
0x1801d0c8d  lea     rcx, [rbp+var_38]
0x1801d0c91  call    ??$As@UIPropertyValue@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>>)
0x1801d0c96  test    eax, eax
0x1801d0c98  js      loc_1801D0D4E
0x1801d0c9e  mov     [rbp+string], r15
0x1801d0ca2  mov     rdi, [rbp+var_28]
0x1801d0ca6  mov     rax, [rdi]
0x1801d0ca9  mov     rbx, [rax+98h]
0x1801d0cb0  xor     ecx, ecx; string
0x1801d0cb2  call    cs:__imp_WindowsDeleteString
0x1801d0cb9  nop     dword ptr [rax+rax+00h]
0x1801d0cbe  mov     [rbp+string], r15
0x1801d0cc2  lea     rdx, [rbp+string]
0x1801d0cc6  mov     rcx, rdi
0x1801d0cc9  mov     rax, rbx
0x1801d0ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d0cd1  test    eax, eax
0x1801d0cd3  js      short loc_1801D0D3D
0x1801d0cd5  mov     rdx, [rbp+string]; HSTRING
0x1801d0cd9  mov     rcx, [rbp+arg_18]; this
0x1801d0cdd  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x1801d0ce2  test    eax, eax
0x1801d0ce4  jnz     short loc_1801D0D3D
0x1801d0ce6  mov     rcx, [rbp+string]; string
0x1801d0cea  call    cs:__imp_WindowsDeleteString
0x1801d0cf1  nop     dword ptr [rax+rax+00h]
0x1801d0cf6  mov     [rbp+string], r15
0x1801d0cfa  lea     rcx, [rbp+var_28]
0x1801d0cfe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801d0d03  nop
0x1801d0d04  lea     rcx, [rbp+var_38]
0x1801d0d08  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801d0d0d  nop
0x1801d0d0e  mov     rcx, [rbp+arg_18]; string
0x1801d0d12  call    cs:__imp_WindowsDeleteString
0x1801d0d19  nop     dword ptr [rax+rax+00h]
0x1801d0d1e  mov     [rbp+arg_18], r15
0x1801d0d22  lea     rcx, [rbp+var_20]
0x1801d0d26  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801d0d2b  nop
0x1801d0d2c  lea     rcx, [rbp+var_30]
0x1801d0d30  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801d0d35  inc     r14d
0x1801d0d38  jmp     loc_1801D0BCE
0x1801d0d3d  mov     rcx, [rbp+string]; string
0x1801d0d41  call    cs:__imp_WindowsDeleteString
0x1801d0d48  nop     dword ptr [rax+rax+00h]
0x1801d0d4d  nop
0x1801d0d4e  lea     rcx, [rbp+var_28]
0x1801d0d52  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801d0d57  xor     r8d, r8d
0x1801d0d5a  mov     edx, r14d
0x1801d0d5d  mov     rcx, [rsi+0D8h]
0x1801d0d64  call    ?RemoveAtInternal@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@AEAAJI_N@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::RemoveAtInternal(uint,bool)
0x1801d0d69  mov     ebx, eax
0x1801d0d6b  dec     r14d
0x1801d0d6e  lea     rcx, [rbp+var_38]
0x1801d0d72  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801d0d77  nop
0x1801d0d78  mov     rcx, [rbp+arg_18]; string
0x1801d0d7c  call    cs:__imp_WindowsDeleteString
0x1801d0d83  nop     dword ptr [rax+rax+00h]
0x1801d0d88  nop
0x1801d0d89  lea     rcx, [rbp+var_20]
0x1801d0d8d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801d0d92  nop
0x1801d0d93  lea     rcx, [rbp+var_30]
0x1801d0d97  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801d0d9c  inc     r14d
0x1801d0d9f  test    ebx, ebx
0x1801d0da1  jns     loc_1801D0BCE
0x1801d0da7  jmp     short loc_1801D0E16
0x1801d0da9  mov     dword ptr [rbp+arg_0], r15d
0x1801d0dad  mov     dword ptr [rbp+string], r15d
0x1801d0db1  lea     rdx, [rbp+arg_0]
0x1801d0db5  mov     rcx, [rsi+0D8h]
0x1801d0dbc  call    ?get_Size@?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$VectorOptions@PEAUHSTRING__@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAI@Z; Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>>::get_Size(uint *)
0x1801d0dc1  lea     rdx, [rbp+string]
0x1801d0dc5  mov     rcx, [rbp+arg_10]
0x1801d0dc9  call    ?get_Size@?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$VectorOptions@PEAUHSTRING__@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAI@Z; Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>>::get_Size(uint *)
0x1801d0dce  mov     rax, [rsi]
0x1801d0dd1  mov     rcx, rsi
0x1801d0dd4  mov     rax, [rax+110h]
0x1801d0ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d0de0  inc     eax
0x1801d0de2  mov     edi, dword ptr [rbp+arg_0]
0x1801d0de5  cmp     edi, eax
0x1801d0de7  jnz     short loc_1801D0E11
0x1801d0de9  mov     rbx, [rsi+0D8h]
0x1801d0df0  mov     rax, [rsi]
0x1801d0df3  mov     rcx, rsi
0x1801d0df6  mov     rax, [rax+110h]
0x1801d0dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d0e02  xor     r8d, r8d
0x1801d0e05  mov     edx, eax
0x1801d0e07  mov     rcx, rbx
0x1801d0e0a  call    ?RemoveAtInternal@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@AEAAJI_N@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::RemoveAtInternal(uint,bool)
0x1801d0e0f  dec     edi
0x1801d0e11  cmp     edi, dword ptr [rbp+string]
0x1801d0e14  jz      short loc_1801D0E7E
0x1801d0e16  mov     r10, [rbp+arg_10]
0x1801d0e1a  cmp     [rsi+0D8h], r10
0x1801d0e21  jz      short loc_1801D0E6E
0x1801d0e23  test    r10, r10
0x1801d0e26  jz      short loc_1801D0E53
0x1801d0e28  mov     rax, [r10+58h]
0x1801d0e2c  test    rax, rax
0x1801d0e2f  js      short loc_1801D0E46
0x1801d0e31  cmp     eax, 7FFFFFFFh
0x1801d0e36  jz      short loc_1801D0E53
0x1801d0e38  lea     rcx, [rax+1]
0x1801d0e3c  lock cmpxchg [r10+58h], rcx
0x1801d0e42  jnz     short loc_1801D0E2C
0x1801d0e44  jmp     short loc_1801D0E53
0x1801d0e46  lea     rcx, ds:10h[rax*2]; this
0x1801d0e4e  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x1801d0e53  mov     rax, [rsi+0D8h]
0x1801d0e5a  mov     [rbp+arg_0], rax
0x1801d0e5e  mov     [rsi+0D8h], r10
0x1801d0e65  lea     rcx, [rbp+arg_0]
0x1801d0e69  call    ?InternalRelease@?$ComPtr@V?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(void)
0x1801d0e6e  lea     rdx, stru_180322520; unsigned __int16 *
0x1801d0e75  mov     rcx, rsi; this
0x1801d0e78  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x1801d0e7d  nop
0x1801d0e7e  lea     rcx, [rbp+var_18]
0x1801d0e82  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801d0e87  nop
0x1801d0e88  lea     rcx, [rbp+arg_10]
0x1801d0e8c  call    ?InternalRelease@?$ComPtr@V?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(void)
0x1801d0e91  add     rsp, 58h
0x1801d0e95  pop     r15
0x1801d0e97  pop     r14
0x1801d0e99  pop     rdi
0x1801d0e9a  pop     rsi
0x1801d0e9b  pop     rbx
0x1801d0e9c  pop     rbp
0x1801d0e9d  retn
```
