# FaceDetectionEffectDefnImpl::RuntimeClassInitialize(void)

- ea: `0x18000b760`
- end: `0x18000ba07`
- name: `?RuntimeClassInitialize@FaceDetectionEffectDefnImpl@@QEAAJXZ`
- size: `679`
- prototype: `__int64 __fastcall(FaceDetectionEffectDefnImpl *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180007d4c`

## callees

- `0x180002420`
- `0x180005660`
- `0x18000ad70`
- `0x18000adbc`
- `0x18000ae08`
- `0x18000ae54`
- `0x18000aef4`
- `0x18000b490`
- `0x18000b760`
- `0x18000c0f8`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b86b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b86b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b852`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b852`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b79c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b79c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000b7b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000b7b8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000b883`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000b883`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FaceDetectionEffectDefnImpl::RuntimeClassInitialize(HSTRING *this)
{
  HSTRING *v2; // rbx
  HRESULT ActivationFactory; // ebx
  __int64 v4; // rdx
  _QWORD *v5; // rax
  char *v6; // r15
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, __int64 *); // rbx
  const unsigned __int16 *v9; // rdx
  __int64 v10; // rsi
  __int64 (__fastcall *v11)(__int64, _QWORD, __int64, _BYTE *); // rdi
  __int64 v12; // rbx
  _QWORD *v13; // rax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64 *); // rbx
  const unsigned __int16 *v16; // rdx
  __int64 v17; // rsi
  __int64 (__fastcall *v18)(__int64, _QWORD, __int64, _BYTE *); // rdi
  __int64 v19; // rbx
  _QWORD *v20; // rax
  _BYTE v22[8]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v23; // [rsp+38h] [rbp-40h] BYREF
  __int64 v24; // [rsp+40h] [rbp-38h] BYREF
  HSTRING string; // [rsp+48h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-28h] BYREF

  v24 = 0;
  v23 = 0;
  v22[0] = 0;
  v2 = this + 10;
  WindowsDeleteString(this[10]);
  *v2 = 0;
  ActivationFactory = WindowsCreateString(L"Windows.Media.Core.FaceDetectionEffect", 0x26u, v2);
  if ( ActivationFactory >= 0 )
  {
    v5 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                     &string,
                     L"Windows.Foundation.Collections.PropertySet");
    ActivationFactory = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
                          *v5,
                          this + 12);
    if ( ActivationFactory >= 0 )
    {
      ActivationFactory = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
                            this + 12,
                            &v24);
      if ( ActivationFactory >= 0 )
      {
        if ( WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &hstringHeader, &string) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        v6 = (char *)(this + 13);
        ActivationFactory = RoGetActivationFactory(string, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, this + 13);
        if ( ActivationFactory >= 0 )
        {
          v7 = *(_QWORD *)v6;
          v8 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(**(_QWORD **)v6 + 136LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
          ActivationFactory = v8(v7, 0, &v23);
          if ( ActivationFactory >= 0 )
          {
            v10 = v24;
            v11 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v24 + 80LL);
            v12 = v23;
            v13 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                              &string,
                              (const unsigned __int16 (*)[21])v9);
            ActivationFactory = v11(v10, *v13, v12, v22);
            if ( ActivationFactory >= 0 )
            {
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
              v14 = *(_QWORD *)v6;
              v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(**(_QWORD **)v6 + 88LL);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
              ActivationFactory = v15(v14, *((unsigned int *)this + 22), &v23);
              if ( ActivationFactory >= 0 )
              {
                v17 = v24;
                v18 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v24 + 80LL);
                v19 = v23;
                v20 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                                  &string,
                                  (const unsigned __int16 (*)[14])v16);
                ActivationFactory = v18(v17, *v20, v19, v22);
                if ( ActivationFactory < 0 && _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                {
                  v4 = 19;
                  goto LABEL_27;
                }
              }
              else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v4 = 18;
                goto LABEL_27;
              }
            }
            else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v4 = 17;
              goto LABEL_27;
            }
          }
          else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v4 = 16;
            goto LABEL_27;
          }
        }
        else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v4 = 15;
          goto LABEL_27;
        }
      }
      else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v4 = 14;
        goto LABEL_27;
      }
    }
    else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v4 = 13;
      goto LABEL_27;
    }
  }
  else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v4 = 12;
LABEL_27:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      WPP_309d84805ff9309032e4a9a4f72506c8_Traceguids,
      this,
      ActivationFactory);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18000b760  push    rbp
0x18000b762  push    rbx
0x18000b763  push    rsi
0x18000b764  push    rdi
0x18000b765  push    r14
0x18000b767  push    r15
0x18000b769  mov     rbp, rsp
0x18000b76c  sub     rsp, 78h
0x18000b770  mov     rax, cs:__security_cookie
0x18000b777  xor     rax, rsp
0x18000b77a  mov     [rbp+var_10], rax
0x18000b77e  mov     r14, rcx
0x18000b781  mov     [rbp+var_38], 0
0x18000b789  mov     [rbp+var_40], 0
0x18000b791  mov     [rbp+var_48], 0
0x18000b795  lea     rbx, [rcx+50h]
0x18000b799  mov     rcx, [rbx]; string
0x18000b79c  call    cs:__imp_WindowsDeleteString
0x18000b7a2  mov     qword ptr [rbx], 0
0x18000b7a9  mov     r8, rbx; string
0x18000b7ac  mov     edx, 26h ; '&'; length
0x18000b7b1  lea     rcx, ?RuntimeClass_Windows_Media_Core_FaceDetectionEffect@@3QBGB; "Windows.Media.Core.FaceDetectionEffect"
0x18000b7b8  call    cs:__imp_WindowsCreateString
0x18000b7be  mov     ebx, eax
0x18000b7c0  test    eax, eax
0x18000b7c2  jns     short loc_18000B7DB
0x18000b7c4  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000b7c9  cmp     al, 1
0x18000b7cb  jb      loc_18000B9D9
0x18000b7d1  mov     edx, 0Ch
0x18000b7d6  jmp     loc_18000B9BA
0x18000b7db  lea     rdx, ?RuntimeClass_Windows_Foundation_Collections_PropertySet@@3QBGB; "Windows.Foundation.Collections.Property"...
0x18000b7e2  lea     rcx, [rbp+string]; string
0x18000b7e6  call    ??$?0$0CL@@StringReference@Internal@Windows@@QEAA@AEAY0CL@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[43])
0x18000b7eb  lea     rdx, [r14+60h]
0x18000b7ef  mov     rcx, [rax]
0x18000b7f2  call    ??$ActivateInstance@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>)
0x18000b7f7  mov     ebx, eax
0x18000b7f9  test    eax, eax
0x18000b7fb  jns     short loc_18000B814
0x18000b7fd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000b802  cmp     al, 1
0x18000b804  jb      loc_18000B9D9
0x18000b80a  mov     edx, 0Dh
0x18000b80f  jmp     loc_18000B9BA
0x18000b814  lea     rdx, [rbp+var_38]
0x18000b818  lea     rcx, [r14+60h]
0x18000b81c  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x18000b821  mov     ebx, eax
0x18000b823  test    eax, eax
0x18000b825  jns     short loc_18000B83E
0x18000b827  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000b82c  cmp     al, 1
0x18000b82e  jb      loc_18000B9D9
0x18000b834  mov     edx, 0Eh
0x18000b839  jmp     loc_18000B9BA
0x18000b83e  lea     r9, [rbp+string]; string
0x18000b842  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000b846  mov     edx, 20h ; ' '; length
0x18000b84b  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x18000b852  call    cs:__imp_WindowsCreateStringReference
0x18000b858  test    eax, eax
0x18000b85a  jns     short loc_18000B871
0x18000b85c  xor     r9d, r9d; lpArguments
0x18000b85f  xor     r8d, r8d; nNumberOfArguments
0x18000b862  lea     edx, [r9+1]; dwExceptionFlags
0x18000b866  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000b86b  call    cs:__imp_RaiseException
0x18000b871  lea     r15, [r14+68h]
0x18000b875  mov     r8, r15
0x18000b878  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x18000b87f  mov     rcx, [rbp+string]
0x18000b883  call    cs:__imp_RoGetActivationFactory
0x18000b889  mov     ebx, eax
0x18000b88b  test    eax, eax
0x18000b88d  jns     short loc_18000B8A6
0x18000b88f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000b894  cmp     al, 1
0x18000b896  jb      loc_18000B9D9
0x18000b89c  mov     edx, 0Fh
0x18000b8a1  jmp     loc_18000B9BA
0x18000b8a6  mov     rdi, [r15]
0x18000b8a9  mov     rax, [rdi]
0x18000b8ac  mov     rbx, [rax+88h]
0x18000b8b3  lea     rcx, [rbp+var_40]
0x18000b8b7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000b8bc  lea     r8, [rbp+var_40]
0x18000b8c0  xor     edx, edx
0x18000b8c2  mov     rcx, rdi
0x18000b8c5  mov     rax, rbx
0x18000b8c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8cd  mov     ebx, eax
0x18000b8cf  test    eax, eax
0x18000b8d1  jns     short loc_18000B8EA
0x18000b8d3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000b8d8  cmp     al, 1
0x18000b8da  jb      loc_18000B9D9
0x18000b8e0  mov     edx, 10h
0x18000b8e5  jmp     loc_18000B9BA
0x18000b8ea  mov     rsi, [rbp+var_38]
0x18000b8ee  mov     rax, [rsi]
0x18000b8f1  mov     rdi, [rax+50h]
0x18000b8f5  mov     rbx, [rbp+var_40]
0x18000b8f9  lea     rcx, [rbp+string]; string
0x18000b8fd  call    ??$?0$0BF@@StringReference@Internal@Windows@@QEAA@AEAY0BF@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[21])
0x18000b902  lea     r9, [rbp+var_48]
0x18000b906  mov     r8, rbx
0x18000b909  mov     rdx, [rax]
0x18000b90c  mov     rcx, rsi
0x18000b90f  mov     rax, rdi
0x18000b912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b917  mov     ebx, eax
0x18000b919  test    eax, eax
0x18000b91b  jns     short loc_18000B934
0x18000b91d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000b922  cmp     al, 1
0x18000b924  jb      loc_18000B9D9
0x18000b92a  mov     edx, 11h
0x18000b92f  jmp     loc_18000B9BA
0x18000b934  lea     rcx, [rbp+var_40]
0x18000b938  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000b93d  mov     rdi, [r15]
0x18000b940  mov     rax, [rdi]
0x18000b943  mov     rbx, [rax+58h]
0x18000b947  lea     rcx, [rbp+var_40]
0x18000b94b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000b950  lea     r8, [rbp+var_40]
0x18000b954  mov     edx, [r14+58h]
0x18000b958  mov     rcx, rdi
0x18000b95b  mov     rax, rbx
0x18000b95e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b963  mov     ebx, eax
0x18000b965  test    eax, eax
0x18000b967  jns     short loc_18000B979
0x18000b969  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000b96e  cmp     al, 1
0x18000b970  jb      short loc_18000B9D9
0x18000b972  mov     edx, 12h
0x18000b977  jmp     short loc_18000B9BA
0x18000b979  mov     rsi, [rbp+var_38]
0x18000b97d  mov     rax, [rsi]
0x18000b980  mov     rdi, [rax+50h]
0x18000b984  mov     rbx, [rbp+var_40]
0x18000b988  lea     rcx, [rbp+string]; string
0x18000b98c  call    ??$?0$0O@@StringReference@Internal@Windows@@QEAA@AEAY0O@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[14])
0x18000b991  lea     r9, [rbp+var_48]
0x18000b995  mov     r8, rbx
0x18000b998  mov     rdx, [rax]
0x18000b99b  mov     rcx, rsi
0x18000b99e  mov     rax, rdi
0x18000b9a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9a6  mov     ebx, eax
0x18000b9a8  test    eax, eax
0x18000b9aa  jns     short loc_18000B9D9
0x18000b9ac  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000b9b1  cmp     al, 1
0x18000b9b3  jb      short loc_18000B9D9
0x18000b9b5  mov     edx, 13h
0x18000b9ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b9c1  mov     [rsp+78h+var_58], ebx
0x18000b9c5  mov     r9, r14
0x18000b9c8  lea     r8, WPP_309d84805ff9309032e4a9a4f72506c8_Traceguids
0x18000b9cf  mov     rcx, [rcx+10h]
0x18000b9d3  call    WPP_SF_qD
0x18000b9d8  nop
0x18000b9d9  lea     rcx, [rbp+var_40]
0x18000b9dd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000b9e2  nop
0x18000b9e3  lea     rcx, [rbp+var_38]
0x18000b9e7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000b9ec  mov     eax, ebx
0x18000b9ee  mov     rcx, [rbp+var_10]
0x18000b9f2  xor     rcx, rsp; StackCookie
0x18000b9f5  call    __security_check_cookie
0x18000b9fa  add     rsp, 78h
0x18000b9fe  pop     r15
0x18000ba00  pop     r14
0x18000ba02  pop     rdi
0x18000ba03  pop     rsi
0x18000ba04  pop     rbx
0x18000ba05  pop     rbp
0x18000ba06  retn
```
