# Windows::UI::Input::Inking::CInkRecognizerContainer::GetResultsSeparatedBySpace(IInkRecognitionResult *,Windows::Foundation::Collections::IVector<Windows::UI::Input::Inking::InkRecognitionResult *> * *)

- ea: `0x18003a470`
- end: `0x18003a8a4`
- name: `?GetResultsSeparatedBySpace@CInkRecognizerContainer@Inking@Input@UI@Windows@@AEAAJPEAUIInkRecognitionResult@@PEAPEAU?$IVector@PEAVInkRecognitionResult@Inking@Input@UI@Windows@@@Collections@Foundation@5@@Z`
- size: `1076`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18003b2a0`

## callees

- `0x1800101bc`
- `0x1800205a0`
- `0x180038154`
- `0x18003849c`
- `0x180038584`
- `0x180039d20`
- `0x18003a470`
- `0x18005802c`
- `0x1800fb010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18003a79d`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a85f`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a79d`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a85f`
- `OLEAUT32!__imp_SysStringLen` at `0x18003a4fa`
- `OLEAUT32!__imp_SysStringLen` at `0x18003a758`
- `OLEAUT32!__imp_SysStringLen` at `0x18003a4fa`
- `OLEAUT32!__imp_SysStringLen` at `0x18003a758`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a793`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a793`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003a768`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003a768`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Windows::UI::Input::Inking::CInkRecognizerContainer::GetResultsSeparatedBySpace(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  HRESULT NextSegment; // ebx
  __int64 v6; // rcx
  UINT v7; // r14d
  UINT v8; // r15d
  __int64 (__fastcall *v9)(__int64, _QWORD, _QWORD, __int64); // rbx
  __int64 v10; // rdi
  void (__fastcall *v11)(__int64, __int64 *); // rbx
  __int64 v12; // rcx
  int i; // esi
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, BSTR *); // rbx
  void **v16; // r8
  __int64 v17; // rcx
  unsigned int v18; // esi
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, _QWORD, __int64 *); // rbx
  UINT v21; // eax
  _QWORD *v22; // rdi
  __int64 v23; // rax
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // rax
  int *v28; // [rsp+20h] [rbp-49h]
  BSTR bstrString; // [rsp+30h] [rbp-39h] BYREF
  __int64 v30; // [rsp+38h] [rbp-31h] BYREF
  __int64 v31; // [rsp+40h] [rbp-29h] BYREF
  __int64 v32; // [rsp+48h] [rbp-21h] BYREF
  __int64 v33; // [rsp+50h] [rbp-19h] BYREF
  HSTRING string; // [rsp+58h] [rbp-11h] BYREF
  __int64 v35; // [rsp+60h] [rbp-9h] BYREF
  BSTR pbstr; // [rsp+68h] [rbp-1h] BYREF
  __int64 v37; // [rsp+70h] [rbp+7h] BYREF
  _QWORD *v38; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v39; // [rsp+D0h] [rbp+67h] BYREF
  int v40; // [rsp+D8h] [rbp+6Fh] BYREF
  int v41; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v42; // [rsp+E8h] [rbp+7Fh] BYREF

  v39 = a1;
  *a3 = 0;
  v33 = 0;
  v37 = 0;
  NextSegment = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 64LL))(a2, &v37);
  if ( NextSegment >= 0 )
  {
    pbstr = 0;
    NextSegment = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v37 + 56LL))(v37, &pbstr);
    if ( NextSegment >= 0 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
      NextSegment = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::UI::Input::Inking::InkRecognitionResult,Windows::Foundation::Collections::Internal::Vector<Windows::UI::Input::Inking::InkRecognitionResult *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Input::Inking::InkRecognitionResult *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Input::Inking::InkRecognitionResult *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Input::Inking::InkRecognitionResult *>>>(
                      v6,
                      &v33);
      v7 = 0;
      v8 = SysStringLen(pbstr);
      if ( v8 )
      {
        do
        {
          if ( NextSegment < 0 )
            break;
          LODWORD(v39) = v7;
          v40 = -1;
          NextSegment = Windows::UI::Input::Inking::GetNextSegment(
                          (Windows::UI::Input::Inking *)pbstr,
                          (const unsigned __int16 *)v8,
                          (int)&v39,
                          &v40,
                          v28);
          if ( NextSegment >= 0 )
          {
            v7 = v39 + v40;
            v31 = 0;
            v9 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)a2 + 88LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
            v28 = (int *)&v31;
            NextSegment = v9(a2, (unsigned int)v39, (unsigned int)v40, 5);
            if ( NextSegment >= 0 )
            {
              v30 = 0;
              v42 = 0;
              v10 = v31;
              v11 = *(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 72LL);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
              v11(v10, &v42);
              NextSegment = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v37 + 152LL))(
                              v37,
                              v42,
                              &v39,
                              &v40);
              if ( NextSegment < 0 )
                goto LABEL_20;
              if ( v7 != (_DWORD)v39 + v40 )
                v7 = v39 + v40;
              v41 = 0;
              NextSegment = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v42 + 56LL))(v42, &v41);
              if ( NextSegment < 0 || v41 <= 0 )
                goto LABEL_20;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
              NextSegment = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::UI::Input::Inking::InkStroke,Windows::Foundation::Collections::Internal::AgileVector<Windows::UI::Input::Inking::InkStroke *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Input::Inking::InkStroke *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Input::Inking::InkStroke *>,0>>(
                              v12,
                              &v30);
              for ( i = 0; i < v41; ++i )
              {
                if ( NextSegment < 0 )
                  break;
                bstrString = 0;
                v14 = v42;
                v15 = *(__int64 (__fastcall **)(__int64, _QWORD, BSTR *))(*(_QWORD *)v42 + 96LL);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&bstrString);
                NextSegment = v15(v14, (unsigned int)i, &bstrString);
                if ( NextSegment >= 0 )
                {
                  string = 0;
                  NextSegment = Windows::UI::Input::Inking::GetValueFromIInkStrokeDisp(
                                  (Windows::UI::Input::Inking *)bstrString,
                                  (struct IInkStrokeDisp *)&string,
                                  v16);
                  if ( NextSegment >= 0 )
                    NextSegment = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v30 + 104LL))(v30, string);
                }
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&bstrString);
              }
              if ( NextSegment == -2147220958 )
              {
                NextSegment = 0;
              }
              else
              {
LABEL_20:
                v32 = 0;
                if ( NextSegment >= 0 )
                {
                  v41 = 0;
                  NextSegment = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v31 + 56LL))(v31, &v41);
                  if ( NextSegment >= 0 )
                  {
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
                    NextSegment = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(
                                    v17,
                                    &v32);
                    v18 = 0;
                    if ( v41 <= 0 )
                    {
LABEL_31:
                      if ( NextSegment >= 0 )
                      {
                        Microsoft::WRL::Details::Make<Windows::UI::Input::Inking::CInkRecognitionResult,>(&v38);
                        v22 = v38;
                        if ( v38 )
                        {
                          v23 = *v38;
                          v24 = v30;
                          v30 = 0;
                          v25 = v32;
                          v32 = 0;
                          NextSegment = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64))(v23 + 80))(
                                          v38,
                                          v25,
                                          v24);
                          if ( NextSegment >= 0 )
                            (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v33 + 104LL))(v33, v22);
                        }
                        else
                        {
                          NextSegment = -2147024882;
                        }
                        if ( v22 )
                        {
                          v38 = 0;
                          (*(void (__fastcall **)(_QWORD *))(*v22 + 16LL))(v22);
                        }
                      }
                    }
                    else
                    {
                      while ( NextSegment >= 0 )
                      {
                        v35 = 0;
                        v19 = v31;
                        v20 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v31 + 80LL);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
                        NextSegment = v20(v19, v18, &v35);
                        if ( NextSegment >= 0 )
                        {
                          bstrString = 0;
                          NextSegment = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v35 + 56LL))(
                                          v35,
                                          &bstrString);
                          if ( NextSegment >= 0 )
                          {
                            string = 0;
                            v21 = SysStringLen(bstrString);
                            NextSegment = WindowsCreateString(bstrString, v21, &string);
                            if ( NextSegment >= 0 && string )
                            {
                              NextSegment = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 104LL))(v32);
                              WindowsDeleteString(string);
                            }
                            SysFreeString(bstrString);
                          }
                        }
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
                        if ( (int)++v18 >= v41 )
                          goto LABEL_31;
                      }
                    }
                  }
                }
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
          }
        }
        while ( v7 < v8 );
      }
      SysFreeString(pbstr);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    if ( NextSegment >= 0 )
    {
      v26 = v33;
      v33 = 0;
      *a3 = v26;
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
  return (unsigned int)NextSegment;
}

```

## disassembly

```asm
0x18003a470  mov     [rsp-8+arg_0], rcx
0x18003a475  push    rbp
0x18003a476  push    rbx
0x18003a477  push    rsi
0x18003a478  push    rdi
0x18003a479  push    r12
0x18003a47b  push    r13
0x18003a47d  push    r14
0x18003a47f  push    r15
0x18003a481  lea     rbp, [rsp-1Fh]
0x18003a486  sub     rsp, 88h
0x18003a48d  mov     r13, r8
0x18003a490  mov     r12, rdx
0x18003a493  xor     edi, edi
0x18003a495  mov     [r8], rdi
0x18003a498  mov     [rbp+57h+var_70], rdi
0x18003a49c  mov     [rbp+57h+var_50], rdi
0x18003a4a0  mov     rax, [rdx]
0x18003a4a3  lea     rdx, [rbp+57h+var_50]
0x18003a4a7  mov     rcx, r12
0x18003a4aa  mov     rax, [rax+40h]
0x18003a4ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a4b3  mov     ebx, eax
0x18003a4b5  test    eax, eax
0x18003a4b7  js      loc_18003A885
0x18003a4bd  mov     [rbp+57h+pbstr], rdi
0x18003a4c1  mov     rcx, [rbp+57h+var_50]
0x18003a4c5  mov     rax, [rcx]
0x18003a4c8  lea     rdx, [rbp+57h+pbstr]
0x18003a4cc  mov     rax, [rax+38h]
0x18003a4d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a4d5  mov     ebx, eax
0x18003a4d7  test    eax, eax
0x18003a4d9  js      loc_18003A865
0x18003a4df  lea     rcx, [rbp+57h+var_70]
0x18003a4e3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a4e8  lea     rdx, [rbp+57h+var_70]
0x18003a4ec  call    ??$CreateExternalObjectVector@VInkRecognitionResult@Inking@Input@UI@Windows@@V?$Vector@PEAVInkRecognitionResult@Inking@Input@UI@Windows@@U?$DefaultEqualityPredicate@PEAVInkRecognitionResult@Inking@Input@UI@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVInkRecognitionResult@Inking@Input@UI@Windows@@@7895@U?$DefaultVectorOptions@PEAVInkRecognitionResult@Inking@Input@UI@Windows@@@7895@@Internal@Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAVInkRecognitionResult@Inking@Input@UI@Windows@@U?$DefaultEqualityPredicate@PEAVInkRecognitionResult@Inking@Input@UI@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVInkRecognitionResult@Inking@Input@UI@Windows@@@7895@U?$DefaultVectorOptions@PEAVInkRecognitionResult@Inking@Input@UI@Windows@@@7895@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::UI::Input::Inking::InkRecognitionResult,Windows::Foundation::Collections::Internal::Vector<Windows::UI::Input::Inking::InkRecognitionResult *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Input::Inking::InkRecognitionResult *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Input::Inking::InkRecognitionResult *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Input::Inking::InkRecognitionResult *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::UI::Input::Inking::InkRecognitionResult *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Input::Inking::InkRecognitionResult *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Input::Inking::InkRecognitionResult *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Input::Inking::InkRecognitionResult *>> * *)
0x18003a4f1  mov     ebx, eax
0x18003a4f3  mov     r14d, edi
0x18003a4f6  mov     rcx, [rbp+57h+pbstr]; pbstr
0x18003a4fa  call    cs:__imp_SysStringLen
0x18003a500  mov     r15d, eax
0x18003a503  test    eax, eax
0x18003a505  jz      loc_18003A85B
0x18003a50b  test    ebx, ebx
0x18003a50d  js      loc_18003A85B
0x18003a513  mov     dword ptr [rbp+57h+arg_0], r14d
0x18003a517  mov     [rbp+57h+arg_8], 0FFFFFFFFh
0x18003a51e  lea     r9, [rbp+57h+arg_8]; int *
0x18003a522  lea     r8, [rbp+57h+arg_0]; int
0x18003a526  mov     edx, r15d; unsigned __int16 *
0x18003a529  mov     rcx, [rbp+57h+pbstr]; this
0x18003a52d  call    ?GetNextSegment@Inking@Input@UI@Windows@@YAJPEBGJPEAJ1@Z; Windows::UI::Input::Inking::GetNextSegment(ushort const *,long,long *,long *)
0x18003a532  mov     ebx, eax
0x18003a534  test    eax, eax
0x18003a536  js      loc_18003A852
0x18003a53c  mov     r14d, [rbp+57h+arg_8]
0x18003a540  add     r14d, dword ptr [rbp+57h+arg_0]
0x18003a544  mov     [rbp+57h+var_80], rdi
0x18003a548  mov     rax, [r12]
0x18003a54c  mov     rbx, [rax+58h]
0x18003a550  lea     rcx, [rbp+57h+var_80]
0x18003a554  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a559  lea     rax, [rbp+57h+var_80]
0x18003a55d  mov     [rsp+0C0h+var_A0], rax
0x18003a562  mov     r9d, 5
0x18003a568  mov     r8d, [rbp+57h+arg_8]
0x18003a56c  mov     edx, dword ptr [rbp+57h+arg_0]
0x18003a56f  mov     rcx, r12
0x18003a572  mov     rax, rbx
0x18003a575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a57a  mov     ebx, eax
0x18003a57c  test    eax, eax
0x18003a57e  js      loc_18003A849
0x18003a584  mov     [rbp+57h+var_88], rdi
0x18003a588  mov     [rbp+57h+arg_18], rdi
0x18003a58c  mov     rdi, [rbp+57h+var_80]
0x18003a590  mov     rax, [rdi]
0x18003a593  mov     rbx, [rax+48h]
0x18003a597  lea     rcx, [rbp+57h+arg_18]
0x18003a59b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a5a0  lea     rdx, [rbp+57h+arg_18]
0x18003a5a4  mov     rcx, rdi
0x18003a5a7  mov     rax, rbx
0x18003a5aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a5af  mov     rcx, [rbp+57h+var_50]
0x18003a5b3  mov     rax, [rcx]
0x18003a5b6  lea     r9, [rbp+57h+arg_8]
0x18003a5ba  lea     r8, [rbp+57h+arg_0]
0x18003a5be  mov     rdx, [rbp+57h+arg_18]
0x18003a5c2  mov     rax, [rax+98h]
0x18003a5c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a5ce  mov     ebx, eax
0x18003a5d0  xor     edi, edi
0x18003a5d2  test    eax, eax
0x18003a5d4  js      loc_18003A6AD
0x18003a5da  mov     edx, [rbp+57h+arg_8]
0x18003a5dd  add     edx, dword ptr [rbp+57h+arg_0]
0x18003a5e0  cmp     r14d, edx
0x18003a5e3  cmovnz  r14d, edx
0x18003a5e7  mov     [rbp+57h+arg_10], edi
0x18003a5ea  mov     rcx, [rbp+57h+arg_18]
0x18003a5ee  mov     rax, [rcx]
0x18003a5f1  lea     rdx, [rbp+57h+arg_10]
0x18003a5f5  mov     rax, [rax+38h]
0x18003a5f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a5fe  mov     ebx, eax
0x18003a600  test    eax, eax
0x18003a602  js      loc_18003A6AD
0x18003a608  cmp     [rbp+57h+arg_10], edi
0x18003a60b  jle     loc_18003A6AD
0x18003a611  lea     rcx, [rbp+57h+var_88]
0x18003a615  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a61a  lea     rdx, [rbp+57h+var_88]
0x18003a61e  call    ??$CreateExternalObjectVector@VInkStroke@Inking@Input@UI@Windows@@V?$AgileVector@PEAVInkStroke@Inking@Input@UI@Windows@@U?$DefaultEqualityPredicate@PEAVInkStroke@Inking@Input@UI@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVInkStroke@Inking@Input@UI@Windows@@@7895@$0A@@Internal@Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVInkStroke@Inking@Input@UI@Windows@@U?$DefaultEqualityPredicate@PEAVInkStroke@Inking@Input@UI@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVInkStroke@Inking@Input@UI@Windows@@@7895@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::UI::Input::Inking::InkStroke,Windows::Foundation::Collections::Internal::AgileVector<Windows::UI::Input::Inking::InkStroke *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Input::Inking::InkStroke *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Input::Inking::InkStroke *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::UI::Input::Inking::InkStroke *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Input::Inking::InkStroke *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Input::Inking::InkStroke *>,0> * *)
0x18003a623  mov     ebx, eax
0x18003a625  mov     esi, edi
0x18003a627  cmp     [rbp+57h+arg_10], edi
0x18003a62a  jle     short loc_18003A69E
0x18003a62c  test    ebx, ebx
0x18003a62e  js      short loc_18003A69E
0x18003a630  mov     [rbp+57h+bstrString], rdi
0x18003a634  mov     rdi, [rbp+57h+arg_18]
0x18003a638  mov     rax, [rdi]
0x18003a63b  mov     rbx, [rax+60h]
0x18003a63f  lea     rcx, [rbp+57h+bstrString]
0x18003a643  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a648  lea     r8, [rbp+57h+bstrString]
0x18003a64c  mov     edx, esi
0x18003a64e  mov     rcx, rdi
0x18003a651  mov     rax, rbx
0x18003a654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a659  mov     ebx, eax
0x18003a65b  xor     edi, edi
0x18003a65d  test    eax, eax
0x18003a65f  js      short loc_18003A68E
0x18003a661  mov     [rbp+57h+string], rdi
0x18003a665  lea     rdx, [rbp+57h+string]; struct IInkStrokeDisp *
0x18003a669  mov     rcx, [rbp+57h+bstrString]; this
0x18003a66d  call    ?GetValueFromIInkStrokeDisp@Inking@Input@UI@Windows@@YAJPEAUIInkStrokeDisp@@PEAPEAX@Z; Windows::UI::Input::Inking::GetValueFromIInkStrokeDisp(IInkStrokeDisp *,void * *)
0x18003a672  mov     ebx, eax
0x18003a674  test    eax, eax
0x18003a676  js      short loc_18003A68E
0x18003a678  mov     rcx, [rbp+57h+var_88]
0x18003a67c  mov     rax, [rcx]
0x18003a67f  mov     rdx, [rbp+57h+string]
0x18003a683  mov     rax, [rax+68h]
0x18003a687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a68c  mov     ebx, eax
0x18003a68e  lea     rcx, [rbp+57h+bstrString]
0x18003a692  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a697  inc     esi
0x18003a699  cmp     esi, [rbp+57h+arg_10]
0x18003a69c  jl      short loc_18003A62C
0x18003a69e  cmp     ebx, 80040222h
0x18003a6a4  jnz     short loc_18003A6AD
0x18003a6a6  mov     ebx, edi
0x18003a6a8  jmp     loc_18003A835
0x18003a6ad  mov     [rbp+57h+var_78], rdi
0x18003a6b1  test    ebx, ebx
0x18003a6b3  js      loc_18003A82B
0x18003a6b9  mov     [rbp+57h+arg_10], edi
0x18003a6bc  mov     rcx, [rbp+57h+var_80]
0x18003a6c0  mov     rax, [rcx]
0x18003a6c3  lea     rdx, [rbp+57h+arg_10]
0x18003a6c7  mov     rax, [rax+38h]
0x18003a6cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a6d0  mov     ebx, eax
0x18003a6d2  test    eax, eax
0x18003a6d4  js      loc_18003A82B
0x18003a6da  lea     rcx, [rbp+57h+var_78]
0x18003a6de  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a6e3  lea     rdx, [rbp+57h+var_78]
0x18003a6e7  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0> * *)
0x18003a6ec  mov     ebx, eax
0x18003a6ee  mov     esi, edi
0x18003a6f0  cmp     [rbp+57h+arg_10], edi
0x18003a6f3  jle     loc_18003A7B8
0x18003a6f9  test    ebx, ebx
0x18003a6fb  js      loc_18003A82B
0x18003a701  mov     [rbp+57h+var_60], rdi
0x18003a705  mov     rdi, [rbp+57h+var_80]
0x18003a709  mov     rax, [rdi]
0x18003a70c  mov     rbx, [rax+50h]
0x18003a710  lea     rcx, [rbp+57h+var_60]
0x18003a714  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a719  lea     r8, [rbp+57h+var_60]
0x18003a71d  mov     edx, esi
0x18003a71f  mov     rcx, rdi
0x18003a722  mov     rax, rbx
0x18003a725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a72a  mov     ebx, eax
0x18003a72c  xor     edi, edi
0x18003a72e  test    eax, eax
0x18003a730  js      short loc_18003A7A4
0x18003a732  mov     [rbp+57h+bstrString], rdi
0x18003a736  mov     rcx, [rbp+57h+var_60]
0x18003a73a  mov     rax, [rcx]
0x18003a73d  lea     rdx, [rbp+57h+bstrString]
0x18003a741  mov     rax, [rax+38h]
0x18003a745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a74a  mov     ebx, eax
0x18003a74c  test    eax, eax
0x18003a74e  js      short loc_18003A7A4
0x18003a750  mov     [rbp+57h+string], rdi
0x18003a754  mov     rcx, [rbp+57h+bstrString]; pbstr
0x18003a758  call    cs:__imp_SysStringLen
0x18003a75e  lea     r8, [rbp+57h+string]; string
0x18003a762  mov     edx, eax; length
0x18003a764  mov     rcx, [rbp+57h+bstrString]; sourceString
0x18003a768  call    cs:__imp_WindowsCreateString
0x18003a76e  mov     ebx, eax
0x18003a770  test    eax, eax
0x18003a772  js      short loc_18003A799
0x18003a774  mov     rdx, [rbp+57h+string]
0x18003a778  test    rdx, rdx
0x18003a77b  jz      short loc_18003A799
0x18003a77d  mov     rcx, [rbp+57h+var_78]
0x18003a781  mov     rax, [rcx]
0x18003a784  mov     rax, [rax+68h]
0x18003a788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a78d  mov     ebx, eax
0x18003a78f  mov     rcx, [rbp+57h+string]; string
0x18003a793  call    cs:__imp_WindowsDeleteString
0x18003a799  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18003a79d  call    cs:__imp_SysFreeString
0x18003a7a3  nop
0x18003a7a4  lea     rcx, [rbp+57h+var_60]
0x18003a7a8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a7ad  inc     esi
0x18003a7af  cmp     esi, [rbp+57h+arg_10]
0x18003a7b2  jl      loc_18003A6F9
0x18003a7b8  test    ebx, ebx
0x18003a7ba  js      short loc_18003A82B
0x18003a7bc  lea     rcx, [rbp+57h+var_48]
0x18003a7c0  call    ??$Make@VCInkRecognitionResult@Inking@Input@UI@Windows@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCInkRecognitionResult@Inking@Input@UI@Windows@@@12@XZ; Microsoft::WRL::Details::Make<Windows::UI::Input::Inking::CInkRecognitionResult,>(void)
0x18003a7c5  nop
0x18003a7c6  mov     rdi, [rbp+57h+var_48]
0x18003a7ca  xor     esi, esi
0x18003a7cc  test    rdi, rdi
0x18003a7cf  jz      short loc_18003A80B
0x18003a7d1  mov     rax, [rdi]
0x18003a7d4  mov     r8, [rbp+57h+var_88]
0x18003a7d8  mov     [rbp+57h+var_88], rsi
0x18003a7dc  mov     rdx, [rbp+57h+var_78]
0x18003a7e0  mov     [rbp+57h+var_78], rsi
0x18003a7e4  mov     rcx, rdi
0x18003a7e7  mov     rax, [rax+50h]
0x18003a7eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a7f0  mov     ebx, eax
0x18003a7f2  test    eax, eax
0x18003a7f4  js      short loc_18003A810
0x18003a7f6  mov     rcx, [rbp+57h+var_70]
0x18003a7fa  mov     rax, [rcx]
0x18003a7fd  mov     rdx, rdi
0x18003a800  mov     rax, [rax+68h]
0x18003a804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a809  jmp     short loc_18003A810
0x18003a80b  mov     ebx, 8007000Eh
0x18003a810  test    rdi, rdi
0x18003a813  jz      short loc_18003A829
0x18003a815  mov     [rbp+57h+var_48], rsi
0x18003a819  mov     rax, [rdi]
0x18003a81c  mov     rcx, rdi
0x18003a81f  mov     rax, [rax+10h]
0x18003a823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a828  nop
0x18003a829  xor     edi, edi
0x18003a82b  lea     rcx, [rbp+57h+var_78]
0x18003a82f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a834  nop
0x18003a835  lea     rcx, [rbp+57h+arg_18]
0x18003a839  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a83e  nop
0x18003a83f  lea     rcx, [rbp+57h+var_88]
0x18003a843  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a848  nop
0x18003a849  lea     rcx, [rbp+57h+var_80]
0x18003a84d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a852  cmp     r14d, r15d
0x18003a855  jb      loc_18003A50B
0x18003a85b  mov     rcx, [rbp+57h+pbstr]; bstrString
0x18003a85f  call    cs:__imp_SysFreeString
0x18003a865  mov     rcx, [rbp+57h+var_50]
0x18003a869  mov     rax, [rcx]
0x18003a86c  mov     rax, [rax+10h]
0x18003a870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a875  test    ebx, ebx
0x18003a877  js      short loc_18003A885
0x18003a879  mov     rax, [rbp+57h+var_70]
0x18003a87d  mov     [rbp+57h+var_70], rdi
0x18003a881  mov     [r13+0], rax
0x18003a885  lea     rcx, [rbp+57h+var_70]
0x18003a889  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a88e  mov     eax, ebx
0x18003a890  add     rsp, 88h
0x18003a897  pop     r15
0x18003a899  pop     r14
0x18003a89b  pop     r13
  ... truncated ...
```
