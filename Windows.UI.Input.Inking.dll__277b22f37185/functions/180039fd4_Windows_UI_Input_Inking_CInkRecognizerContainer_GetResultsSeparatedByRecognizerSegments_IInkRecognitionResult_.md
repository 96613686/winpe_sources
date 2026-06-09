# Windows::UI::Input::Inking::CInkRecognizerContainer::GetResultsSeparatedByRecognizerSegments(IInkRecognitionResult *,Windows::Foundation::Collections::IVector<Windows::UI::Input::Inking::InkRecognitionResult *> * *)

- ea: `0x180039fd4`
- end: `0x18003a467`
- name: `?GetResultsSeparatedByRecognizerSegments@CInkRecognizerContainer@Inking@Input@UI@Windows@@AEAAJPEAUIInkRecognitionResult@@PEAPEAU?$IVector@PEAVInkRecognitionResult@Inking@Input@UI@Windows@@@Collections@Foundation@5@@Z`
- size: `1171`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18003b2a0`

## callees

- `0x1800101bc`
- `0x1800205a0`
- `0x180038154`
- `0x18003849c`
- `0x180038584`
- `0x180039fd4`
- `0x18005802c`
- `0x1800fb010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18003a04d`
- `OLEAUT32!__imp_SysAllocString` at `0x18003a04d`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a08d`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a35d`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a08d`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a35d`
- `OLEAUT32!__imp_SysStringLen` at `0x18003a318`
- `OLEAUT32!__imp_SysStringLen` at `0x18003a318`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a353`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a353`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003a328`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003a328`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall Windows::UI::Input::Inking::CInkRecognizerContainer::GetResultsSeparatedByRecognizerSegments(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 (__fastcall *v5)(__int64, __int64 *); // rbx
  HRESULT ValueFromIInkStrokeDisp; // ebx
  __int64 v7; // rcx
  OLECHAR *v8; // rsi
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, OLECHAR *, __int64 *); // rbx
  int v11; // eax
  unsigned int v12; // r14d
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, __int64 *); // rbx
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64 *); // rbx
  __int64 (__fastcall *v17)(__int64, _QWORD, _QWORD, __int64, __int64 *); // rbx
  __int64 v18; // rcx
  int i; // esi
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, _QWORD, Windows::UI::Input::Inking **); // rbx
  void **v22; // r8
  __int64 v23; // rcx
  unsigned int v24; // esi
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, _QWORD, __int64 *); // rbx
  UINT v27; // eax
  _QWORD *v28; // rdi
  __int64 v29; // rax
  __int64 v30; // r8
  __int64 v31; // rdx
  __int64 v32; // rax
  __int64 v34; // [rsp+30h] [rbp-59h] BYREF
  __int64 v35; // [rsp+38h] [rbp-51h] BYREF
  __int64 v36; // [rsp+40h] [rbp-49h] BYREF
  __int64 v37; // [rsp+48h] [rbp-41h] BYREF
  __int64 v38; // [rsp+50h] [rbp-39h] BYREF
  HSTRING string; // [rsp+58h] [rbp-31h] BYREF
  unsigned int v40; // [rsp+60h] [rbp-29h] BYREF
  __int64 v41; // [rsp+68h] [rbp-21h] BYREF
  __int64 v42; // [rsp+70h] [rbp-19h] BYREF
  BSTR pbstr; // [rsp+78h] [rbp-11h] BYREF
  __int64 v44; // [rsp+80h] [rbp-9h] BYREF
  __int64 v45; // [rsp+88h] [rbp-1h] BYREF
  _QWORD *v46; // [rsp+90h] [rbp+7h] BYREF
  __int64 v47; // [rsp+F0h] [rbp+67h] BYREF
  int v48; // [rsp+F8h] [rbp+6Fh] BYREF
  Windows::UI::Input::Inking *v49; // [rsp+100h] [rbp+77h] BYREF
  unsigned int v50; // [rsp+108h] [rbp+7Fh] BYREF

  v47 = a1;
  *a3 = 0;
  v38 = 0;
  v42 = 0;
  v5 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 64LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  ValueFromIInkStrokeDisp = v5(a2, &v42);
  if ( ValueFromIInkStrokeDisp >= 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
    ValueFromIInkStrokeDisp = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::UI::Input::Inking::InkRecognitionResult,Windows::Foundation::Collections::Internal::Vector<Windows::UI::Input::Inking::InkRecognitionResult *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Input::Inking::InkRecognitionResult *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Input::Inking::InkRecognitionResult *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Input::Inking::InkRecognitionResult *>>>(
                                v7,
                                &v38);
  }
  v41 = 0;
  if ( ValueFromIInkStrokeDisp >= 0 )
  {
    v8 = SysAllocString(L"{B3C0FE6C-FB51-4164-BA2F-844AF8F983DA}");
    if ( !v8 )
    {
      ValueFromIInkStrokeDisp = -2147024882;
      v11 = 0;
      v48 = 0;
      goto LABEL_8;
    }
    v9 = v42;
    v10 = *(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)v42 + 160LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
    ValueFromIInkStrokeDisp = v10(v9, v8, &v41);
    SysFreeString(v8);
  }
  v11 = 0;
  v48 = 0;
  if ( ValueFromIInkStrokeDisp >= 0 )
  {
    ValueFromIInkStrokeDisp = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v41 + 56LL))(v41, &v48);
    v11 = v48;
  }
LABEL_8:
  v12 = 0;
  if ( v11 <= 0 )
  {
LABEL_49:
    if ( ValueFromIInkStrokeDisp >= 0 )
    {
      v32 = v38;
      v38 = 0;
      *a3 = v32;
    }
  }
  else
  {
    while ( ValueFromIInkStrokeDisp >= 0 )
    {
      v45 = 0;
      v34 = 0;
      LODWORD(v47) = 0;
      v13 = v41;
      v14 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v41 + 80LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
      ValueFromIInkStrokeDisp = v14(v13, v12, &v45);
      if ( ValueFromIInkStrokeDisp >= 0 )
      {
        v15 = v45;
        v16 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 112LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
        ValueFromIInkStrokeDisp = v16(v15, &v34);
        if ( ValueFromIInkStrokeDisp >= 0 )
          ValueFromIInkStrokeDisp = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v34 + 56LL))(v34, &v47);
      }
      if ( (_DWORD)v47 )
      {
        v40 = 0;
        v50 = 0;
        if ( ValueFromIInkStrokeDisp >= 0 )
          ValueFromIInkStrokeDisp = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *, unsigned int *))(*(_QWORD *)v42 + 152LL))(
                                      v42,
                                      v34,
                                      &v40,
                                      &v50);
        v37 = 0;
        if ( ValueFromIInkStrokeDisp >= 0 )
        {
          v17 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, __int64 *))(*(_QWORD *)a2 + 88LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
          ValueFromIInkStrokeDisp = v17(a2, v40, v50, 5, &v37);
        }
        v35 = 0;
        if ( ValueFromIInkStrokeDisp < 0 )
          goto LABEL_28;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
        ValueFromIInkStrokeDisp = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::UI::Input::Inking::InkStroke,Windows::Foundation::Collections::Internal::AgileVector<Windows::UI::Input::Inking::InkStroke *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Input::Inking::InkStroke *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Input::Inking::InkStroke *>,0>>(
                                    v18,
                                    &v35);
        for ( i = 0; i < (int)v47; ++i )
        {
          if ( ValueFromIInkStrokeDisp < 0 )
            break;
          v49 = 0;
          v20 = v34;
          v21 = *(__int64 (__fastcall **)(__int64, _QWORD, Windows::UI::Input::Inking **))(*(_QWORD *)v34 + 96LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
          ValueFromIInkStrokeDisp = v21(v20, (unsigned int)i, &v49);
          if ( ValueFromIInkStrokeDisp >= 0 )
          {
            string = 0;
            ValueFromIInkStrokeDisp = Windows::UI::Input::Inking::GetValueFromIInkStrokeDisp(
                                        v49,
                                        (struct IInkStrokeDisp *)&string,
                                        v22);
            if ( ValueFromIInkStrokeDisp >= 0 )
              ValueFromIInkStrokeDisp = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v35 + 104LL))(
                                          v35,
                                          string);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
        }
        if ( ValueFromIInkStrokeDisp == -2147220958 )
        {
          ValueFromIInkStrokeDisp = 0;
        }
        else
        {
LABEL_28:
          v36 = 0;
          if ( ValueFromIInkStrokeDisp >= 0 )
          {
            LODWORD(v49) = 0;
            ValueFromIInkStrokeDisp = (*(__int64 (__fastcall **)(__int64, Windows::UI::Input::Inking **))(*(_QWORD *)v37 + 56LL))(
                                        v37,
                                        &v49);
            if ( ValueFromIInkStrokeDisp >= 0 )
            {
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
              ValueFromIInkStrokeDisp = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(
                                          v23,
                                          &v36);
              v24 = 0;
              if ( (int)v49 <= 0 )
              {
LABEL_39:
                if ( ValueFromIInkStrokeDisp >= 0 )
                {
                  Microsoft::WRL::Details::Make<Windows::UI::Input::Inking::CInkRecognitionResult,>(&v46);
                  v28 = v46;
                  if ( v46 )
                  {
                    v29 = *v46;
                    v30 = v35;
                    v35 = 0;
                    v31 = v36;
                    v36 = 0;
                    ValueFromIInkStrokeDisp = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64))(v29 + 80))(
                                                v46,
                                                v31,
                                                v30);
                    if ( ValueFromIInkStrokeDisp >= 0 )
                      (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v38 + 104LL))(v38, v28);
                  }
                  else
                  {
                    ValueFromIInkStrokeDisp = -2147024882;
                  }
                  if ( v28 )
                  {
                    v46 = 0;
                    (*(void (__fastcall **)(_QWORD *))(*v28 + 16LL))(v28);
                  }
                }
              }
              else
              {
                while ( ValueFromIInkStrokeDisp >= 0 )
                {
                  v44 = 0;
                  v25 = v37;
                  v26 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v37 + 80LL);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
                  ValueFromIInkStrokeDisp = v26(v25, v24, &v44);
                  if ( ValueFromIInkStrokeDisp >= 0 )
                  {
                    pbstr = 0;
                    ValueFromIInkStrokeDisp = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v44 + 56LL))(
                                                v44,
                                                &pbstr);
                    if ( ValueFromIInkStrokeDisp >= 0 )
                    {
                      string = 0;
                      v27 = SysStringLen(pbstr);
                      ValueFromIInkStrokeDisp = WindowsCreateString(pbstr, v27, &string);
                      if ( ValueFromIInkStrokeDisp >= 0 && string )
                      {
                        ValueFromIInkStrokeDisp = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 104LL))(v36);
                        WindowsDeleteString(string);
                      }
                      SysFreeString(pbstr);
                    }
                  }
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
                  if ( (int)++v24 >= (int)v49 )
                    goto LABEL_39;
                }
              }
            }
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
      if ( (int)++v12 >= v48 )
        goto LABEL_49;
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
  return (unsigned int)ValueFromIInkStrokeDisp;
}

```

## disassembly

```asm
0x180039fd4  mov     [rsp-8+arg_0], rcx
0x180039fd9  push    rbp
0x180039fda  push    rbx
0x180039fdb  push    rsi
0x180039fdc  push    rdi
0x180039fdd  push    r12
0x180039fdf  push    r13
0x180039fe1  push    r14
0x180039fe3  push    r15
0x180039fe5  lea     rbp, [rsp-1Fh]
0x180039fea  sub     rsp, 0A8h
0x180039ff1  mov     r15, r8
0x180039ff4  mov     r12, rdx
0x180039ff7  xor     r13d, r13d
0x180039ffa  mov     [r8], r13
0x180039ffd  mov     [rbp+57h+var_90], r13
0x18003a001  mov     [rbp+57h+var_70], r13
0x18003a005  mov     rax, [rdx]
0x18003a008  mov     rbx, [rax+40h]
0x18003a00c  lea     rcx, [rbp+57h+var_70]
0x18003a010  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a015  lea     rdx, [rbp+57h+var_70]
0x18003a019  mov     rcx, r12
0x18003a01c  mov     rax, rbx
0x18003a01f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a024  mov     ebx, eax
0x18003a026  test    eax, eax
0x18003a028  js      short loc_18003A03E
0x18003a02a  lea     rcx, [rbp+57h+var_90]
0x18003a02e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a033  lea     rdx, [rbp+57h+var_90]
0x18003a037  call    ??$CreateExternalObjectVector@VInkRecognitionResult@Inking@Input@UI@Windows@@V?$Vector@PEAVInkRecognitionResult@Inking@Input@UI@Windows@@U?$DefaultEqualityPredicate@PEAVInkRecognitionResult@Inking@Input@UI@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVInkRecognitionResult@Inking@Input@UI@Windows@@@7895@U?$DefaultVectorOptions@PEAVInkRecognitionResult@Inking@Input@UI@Windows@@@7895@@Internal@Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAVInkRecognitionResult@Inking@Input@UI@Windows@@U?$DefaultEqualityPredicate@PEAVInkRecognitionResult@Inking@Input@UI@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVInkRecognitionResult@Inking@Input@UI@Windows@@@7895@U?$DefaultVectorOptions@PEAVInkRecognitionResult@Inking@Input@UI@Windows@@@7895@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::UI::Input::Inking::InkRecognitionResult,Windows::Foundation::Collections::Internal::Vector<Windows::UI::Input::Inking::InkRecognitionResult *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Input::Inking::InkRecognitionResult *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Input::Inking::InkRecognitionResult *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Input::Inking::InkRecognitionResult *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::UI::Input::Inking::InkRecognitionResult *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Input::Inking::InkRecognitionResult *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Input::Inking::InkRecognitionResult *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Input::Inking::InkRecognitionResult *>> * *)
0x18003a03c  mov     ebx, eax
0x18003a03e  mov     [rbp+57h+var_78], r13
0x18003a042  test    ebx, ebx
0x18003a044  js      short loc_18003A093
0x18003a046  lea     rcx, psz; "{B3C0FE6C-FB51-4164-BA2F-844AF8F983DA}"
0x18003a04d  call    cs:__imp_SysAllocString
0x18003a053  mov     rsi, rax
0x18003a056  test    rax, rax
0x18003a059  jz      loc_18003A25C
0x18003a05f  mov     rdi, [rbp+57h+var_70]
0x18003a063  mov     rdx, [rdi]
0x18003a066  mov     rbx, [rdx+0A0h]
0x18003a06d  lea     rcx, [rbp+57h+var_78]
0x18003a071  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a076  lea     r8, [rbp+57h+var_78]
0x18003a07a  mov     rdx, rsi
0x18003a07d  mov     rcx, rdi
0x18003a080  mov     rax, rbx
0x18003a083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a088  mov     ebx, eax
0x18003a08a  mov     rcx, rsi; bstrString
0x18003a08d  call    cs:__imp_SysFreeString
0x18003a093  mov     eax, r13d
0x18003a096  mov     [rbp+57h+arg_8], eax
0x18003a099  test    ebx, ebx
0x18003a09b  js      short loc_18003A0B6
0x18003a09d  mov     rcx, [rbp+57h+var_78]
0x18003a0a1  mov     rax, [rcx]
0x18003a0a4  lea     rdx, [rbp+57h+arg_8]
0x18003a0a8  mov     rax, [rax+38h]
0x18003a0ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a0b1  mov     ebx, eax
0x18003a0b3  mov     eax, [rbp+57h+arg_8]
0x18003a0b6  mov     r14d, r13d
0x18003a0b9  test    eax, eax
0x18003a0bb  jle     loc_18003A425
0x18003a0c1  test    ebx, ebx
0x18003a0c3  js      loc_18003A434
0x18003a0c9  mov     [rbp+57h+var_58], r13
0x18003a0cd  mov     [rbp+57h+var_B0], r13
0x18003a0d1  mov     dword ptr [rbp+57h+arg_0], r13d
0x18003a0d5  mov     rdi, [rbp+57h+var_78]
0x18003a0d9  mov     rax, [rdi]
0x18003a0dc  mov     rbx, [rax+50h]
0x18003a0e0  lea     rcx, [rbp+57h+var_58]
0x18003a0e4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a0e9  lea     r8, [rbp+57h+var_58]
0x18003a0ed  mov     edx, r14d
0x18003a0f0  mov     rcx, rdi
0x18003a0f3  mov     rax, rbx
0x18003a0f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a0fb  mov     ebx, eax
0x18003a0fd  test    eax, eax
0x18003a0ff  js      short loc_18003A140
0x18003a101  mov     rdi, [rbp+57h+var_58]
0x18003a105  mov     rax, [rdi]
0x18003a108  mov     rbx, [rax+70h]
0x18003a10c  lea     rcx, [rbp+57h+var_B0]
0x18003a110  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a115  lea     rdx, [rbp+57h+var_B0]
0x18003a119  mov     rcx, rdi
0x18003a11c  mov     rax, rbx
0x18003a11f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a124  mov     ebx, eax
0x18003a126  test    eax, eax
0x18003a128  js      short loc_18003A140
0x18003a12a  mov     rcx, [rbp+57h+var_B0]
0x18003a12e  mov     rax, [rcx]
0x18003a131  lea     rdx, [rbp+57h+arg_0]
0x18003a135  mov     rax, [rax+38h]
0x18003a139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a13e  mov     ebx, eax
0x18003a140  cmp     dword ptr [rbp+57h+arg_0], r13d
0x18003a144  jz      loc_18003A405
0x18003a14a  mov     [rbp+57h+var_80], r13d
0x18003a14e  mov     [rbp+57h+arg_18], r13d
0x18003a152  test    ebx, ebx
0x18003a154  js      short loc_18003A177
0x18003a156  mov     rcx, [rbp+57h+var_70]
0x18003a15a  mov     rax, [rcx]
0x18003a15d  lea     r9, [rbp+57h+arg_18]
0x18003a161  lea     r8, [rbp+57h+var_80]
0x18003a165  mov     rdx, [rbp+57h+var_B0]
0x18003a169  mov     rax, [rax+98h]
0x18003a170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a175  mov     ebx, eax
0x18003a177  mov     [rbp+57h+var_98], r13
0x18003a17b  test    ebx, ebx
0x18003a17d  js      short loc_18003A1B3
0x18003a17f  mov     rax, [r12]
0x18003a183  mov     rbx, [rax+58h]
0x18003a187  lea     rcx, [rbp+57h+var_98]
0x18003a18b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a190  lea     rax, [rbp+57h+var_98]
0x18003a194  mov     [rsp+0E0h+var_C0], rax
0x18003a199  mov     r9d, 5
0x18003a19f  mov     r8d, [rbp+57h+arg_18]
0x18003a1a3  mov     edx, [rbp+57h+var_80]
0x18003a1a6  mov     rcx, r12
0x18003a1a9  mov     rax, rbx
0x18003a1ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a1b1  mov     ebx, eax
0x18003a1b3  mov     [rbp+57h+var_A8], r13
0x18003a1b7  test    ebx, ebx
0x18003a1b9  js      loc_18003A26C
0x18003a1bf  lea     rcx, [rbp+57h+var_A8]
0x18003a1c3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a1c8  lea     rdx, [rbp+57h+var_A8]
0x18003a1cc  call    ??$CreateExternalObjectVector@VInkStroke@Inking@Input@UI@Windows@@V?$AgileVector@PEAVInkStroke@Inking@Input@UI@Windows@@U?$DefaultEqualityPredicate@PEAVInkStroke@Inking@Input@UI@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVInkStroke@Inking@Input@UI@Windows@@@7895@$0A@@Internal@Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVInkStroke@Inking@Input@UI@Windows@@U?$DefaultEqualityPredicate@PEAVInkStroke@Inking@Input@UI@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVInkStroke@Inking@Input@UI@Windows@@@7895@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::UI::Input::Inking::InkStroke,Windows::Foundation::Collections::Internal::AgileVector<Windows::UI::Input::Inking::InkStroke *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Input::Inking::InkStroke *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Input::Inking::InkStroke *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::UI::Input::Inking::InkStroke *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Input::Inking::InkStroke *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Input::Inking::InkStroke *>,0> * *)
0x18003a1d1  mov     ebx, eax
0x18003a1d3  mov     esi, r13d
0x18003a1d6  cmp     dword ptr [rbp+57h+arg_0], r13d
0x18003a1da  jle     short loc_18003A24C
0x18003a1dc  test    ebx, ebx
0x18003a1de  js      short loc_18003A24C
0x18003a1e0  mov     [rbp+57h+arg_10], r13
0x18003a1e4  mov     rdi, [rbp+57h+var_B0]
0x18003a1e8  mov     rax, [rdi]
0x18003a1eb  mov     rbx, [rax+60h]
0x18003a1ef  lea     rcx, [rbp+57h+arg_10]
0x18003a1f3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a1f8  lea     r8, [rbp+57h+arg_10]
0x18003a1fc  mov     edx, esi
0x18003a1fe  mov     rcx, rdi
0x18003a201  mov     rax, rbx
0x18003a204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a209  mov     ebx, eax
0x18003a20b  test    eax, eax
0x18003a20d  js      short loc_18003A23C
0x18003a20f  mov     [rbp+57h+string], r13
0x18003a213  lea     rdx, [rbp+57h+string]; struct IInkStrokeDisp *
0x18003a217  mov     rcx, [rbp+57h+arg_10]; this
0x18003a21b  call    ?GetValueFromIInkStrokeDisp@Inking@Input@UI@Windows@@YAJPEAUIInkStrokeDisp@@PEAPEAX@Z; Windows::UI::Input::Inking::GetValueFromIInkStrokeDisp(IInkStrokeDisp *,void * *)
0x18003a220  mov     ebx, eax
0x18003a222  test    eax, eax
0x18003a224  js      short loc_18003A23C
0x18003a226  mov     rcx, [rbp+57h+var_A8]
0x18003a22a  mov     rax, [rcx]
0x18003a22d  mov     rdx, [rbp+57h+string]
0x18003a231  mov     rax, [rax+68h]
0x18003a235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a23a  mov     ebx, eax
0x18003a23c  lea     rcx, [rbp+57h+arg_10]
0x18003a240  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a245  inc     esi
0x18003a247  cmp     esi, dword ptr [rbp+57h+arg_0]
0x18003a24a  jl      short loc_18003A1DC
0x18003a24c  cmp     ebx, 80040222h
0x18003a252  jnz     short loc_18003A26C
0x18003a254  mov     ebx, r13d
0x18003a257  jmp     loc_18003A3F1
0x18003a25c  mov     ebx, 8007000Eh
0x18003a261  mov     eax, r13d
0x18003a264  mov     [rbp+57h+arg_8], eax
0x18003a267  jmp     loc_18003A0B6
0x18003a26c  mov     [rbp+57h+var_A0], r13
0x18003a270  test    ebx, ebx
0x18003a272  js      loc_18003A3E7
0x18003a278  mov     dword ptr [rbp+57h+arg_10], r13d
0x18003a27c  mov     rcx, [rbp+57h+var_98]
0x18003a280  mov     rax, [rcx]
0x18003a283  lea     rdx, [rbp+57h+arg_10]
0x18003a287  mov     rax, [rax+38h]
0x18003a28b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a290  mov     ebx, eax
0x18003a292  test    eax, eax
0x18003a294  js      loc_18003A3E7
0x18003a29a  lea     rcx, [rbp+57h+var_A0]
0x18003a29e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a2a3  lea     rdx, [rbp+57h+var_A0]
0x18003a2a7  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0> * *)
0x18003a2ac  mov     ebx, eax
0x18003a2ae  mov     esi, r13d
0x18003a2b1  cmp     dword ptr [rbp+57h+arg_10], r13d
0x18003a2b5  jle     loc_18003A378
0x18003a2bb  test    ebx, ebx
0x18003a2bd  js      loc_18003A3E7
0x18003a2c3  mov     [rbp+57h+var_60], r13
0x18003a2c7  mov     rdi, [rbp+57h+var_98]
0x18003a2cb  mov     rax, [rdi]
0x18003a2ce  mov     rbx, [rax+50h]
0x18003a2d2  lea     rcx, [rbp+57h+var_60]
0x18003a2d6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a2db  lea     r8, [rbp+57h+var_60]
0x18003a2df  mov     edx, esi
0x18003a2e1  mov     rcx, rdi
0x18003a2e4  mov     rax, rbx
0x18003a2e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a2ec  mov     ebx, eax
0x18003a2ee  test    eax, eax
0x18003a2f0  js      short loc_18003A364
0x18003a2f2  mov     [rbp+57h+pbstr], r13
0x18003a2f6  mov     rcx, [rbp+57h+var_60]
0x18003a2fa  mov     rax, [rcx]
0x18003a2fd  lea     rdx, [rbp+57h+pbstr]
0x18003a301  mov     rax, [rax+38h]
0x18003a305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a30a  mov     ebx, eax
0x18003a30c  test    eax, eax
0x18003a30e  js      short loc_18003A364
0x18003a310  mov     [rbp+57h+string], r13
0x18003a314  mov     rcx, [rbp+57h+pbstr]; pbstr
0x18003a318  call    cs:__imp_SysStringLen
0x18003a31e  lea     r8, [rbp+57h+string]; string
0x18003a322  mov     edx, eax; length
0x18003a324  mov     rcx, [rbp+57h+pbstr]; sourceString
0x18003a328  call    cs:__imp_WindowsCreateString
0x18003a32e  mov     ebx, eax
0x18003a330  test    eax, eax
0x18003a332  js      short loc_18003A359
0x18003a334  mov     rdx, [rbp+57h+string]
0x18003a338  test    rdx, rdx
0x18003a33b  jz      short loc_18003A359
0x18003a33d  mov     rcx, [rbp+57h+var_A0]
0x18003a341  mov     rax, [rcx]
0x18003a344  mov     rax, [rax+68h]
0x18003a348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a34d  mov     ebx, eax
0x18003a34f  mov     rcx, [rbp+57h+string]; string
0x18003a353  call    cs:__imp_WindowsDeleteString
0x18003a359  mov     rcx, [rbp+57h+pbstr]; bstrString
0x18003a35d  call    cs:__imp_SysFreeString
0x18003a363  nop
0x18003a364  lea     rcx, [rbp+57h+var_60]
0x18003a368  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a36d  inc     esi
0x18003a36f  cmp     esi, dword ptr [rbp+57h+arg_10]
0x18003a372  jl      loc_18003A2BB
0x18003a378  test    ebx, ebx
0x18003a37a  js      short loc_18003A3E7
0x18003a37c  lea     rcx, [rbp+57h+var_50]
0x18003a380  call    ??$Make@VCInkRecognitionResult@Inking@Input@UI@Windows@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCInkRecognitionResult@Inking@Input@UI@Windows@@@12@XZ; Microsoft::WRL::Details::Make<Windows::UI::Input::Inking::CInkRecognitionResult,>(void)
0x18003a385  nop
0x18003a386  mov     rdi, [rbp+57h+var_50]
0x18003a38a  test    rdi, rdi
0x18003a38d  jz      short loc_18003A3C9
0x18003a38f  mov     rax, [rdi]
0x18003a392  mov     r8, [rbp+57h+var_A8]
0x18003a396  mov     [rbp+57h+var_A8], r13
0x18003a39a  mov     rdx, [rbp+57h+var_A0]
0x18003a39e  mov     [rbp+57h+var_A0], r13
0x18003a3a2  mov     rcx, rdi
0x18003a3a5  mov     rax, [rax+50h]
0x18003a3a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a3ae  mov     ebx, eax
0x18003a3b0  test    eax, eax
0x18003a3b2  js      short loc_18003A3CE
0x18003a3b4  mov     rcx, [rbp+57h+var_90]
0x18003a3b8  mov     rax, [rcx]
0x18003a3bb  mov     rdx, rdi
0x18003a3be  mov     rax, [rax+68h]
0x18003a3c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a3c7  jmp     short loc_18003A3CE
0x18003a3c9  mov     ebx, 8007000Eh
0x18003a3ce  test    rdi, rdi
0x18003a3d1  jz      short loc_18003A3E7
0x18003a3d3  mov     [rbp+57h+var_50], r13
0x18003a3d7  mov     rax, [rdi]
0x18003a3da  mov     rcx, rdi
0x18003a3dd  mov     rax, [rax+10h]
0x18003a3e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a3e6  nop
0x18003a3e7  lea     rcx, [rbp+57h+var_A0]
0x18003a3eb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a3f0  nop
0x18003a3f1  lea     rcx, [rbp+57h+var_A8]
0x18003a3f5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a3fa  nop
  ... truncated ...
```
