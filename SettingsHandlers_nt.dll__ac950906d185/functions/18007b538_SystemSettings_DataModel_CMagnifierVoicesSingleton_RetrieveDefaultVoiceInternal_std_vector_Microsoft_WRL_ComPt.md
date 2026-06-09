# SystemSettings::DataModel::CMagnifierVoicesSingleton::RetrieveDefaultVoiceInternal(std::vector<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>,std::allocator<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>>> const &,ushort const *,ushort * *)

- ea: `0x18007b538`
- end: `0x18007b8dd`
- name: `?RetrieveDefaultVoiceInternal@CMagnifierVoicesSingleton@DataModel@SystemSettings@@AEAAJAEBV?$vector@V?$ComPtr@UIVoiceInformation@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIVoiceInformation@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@@std@@@std@@PEBGPEAPEAG@Z`
- size: `933`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007b330`

## callees

- `0x180011bb0`
- `0x180019a20`
- `0x18001e4b0`
- `0x1800410cc`
- `0x1800773c4`
- `0x1800782c0`
- `0x1800786dc`
- `0x1800796f8`
- `0x180079808`
- `0x18007b538`
- `0x18007d49c`
- `0x180289010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18007b7c3`
- `OLEAUT32!__imp_SysFreeString` at `0x18007b7d5`
- `OLEAUT32!__imp_SysFreeString` at `0x18007b7c3`
- `OLEAUT32!__imp_SysFreeString` at `0x18007b7d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b5a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b60c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b6bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b71c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b747`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b7f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b85a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b8a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b5a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b60c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b6bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b71c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b747`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b7f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b85a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b8a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007b63c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007b6f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007b77b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007b63c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007b6f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007b77b`

## string_xrefs

- `0x18007b590`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\magnifier.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall SystemSettings::DataModel::CMagnifierVoicesSingleton::RetrieveDefaultVoiceInternal(
        __int64 a1,
        __int64 **a2,
        const unsigned __int16 *a3,
        _QWORD *a4)
{
  const unsigned __int16 *v5; // rsi
  int v7; // eax
  unsigned int v8; // ebx
  __int64 result; // rax
  __int64 *v10; // r15
  __int64 *v11; // r13
  __int64 v12; // rbx
  int (__fastcall *v13)(__int64, HSTRING *); // rdi
  const unsigned __int16 *StringRawBuffer; // rax
  SystemSettings::DataModel::CMagnifierVoicesSingleton *v15; // rcx
  int matched; // r14d
  __int64 v17; // rsi
  int (__fastcall *v18)(__int64, BSTR *); // rdi
  BSTR v19; // rsi
  int (__fastcall *v20)(BSTR, HSTRING, HSTRING *); // rdi
  PCWSTR v21; // rax
  int (__fastcall *v22)(__int64, HSTRING *); // rdi
  const unsigned __int16 *v23; // rax
  __int64 v24; // rdx
  _DWORD *v25; // rdx
  _DWORD *i; // r8
  _DWORD *v27; // rcx
  __int64 v28; // rax
  const char *v29; // r9
  BSTR v30; // [rsp+20h] [rbp-88h] BYREF
  HSTRING v31; // [rsp+28h] [rbp-80h] BYREF
  HSTRING v32; // [rsp+30h] [rbp-78h] BYREF
  HSTRING v33; // [rsp+38h] [rbp-70h] BYREF
  HSTRING string; // [rsp+40h] [rbp-68h] BYREF
  __int64 v35; // [rsp+48h] [rbp-60h] BYREF
  __int128 v36; // [rsp+50h] [rbp-58h] BYREF
  __int64 v37; // [rsp+60h] [rbp-48h]
  __int64 v38; // [rsp+68h] [rbp-40h] BYREF
  char v39[8]; // [rsp+70h] [rbp-38h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  __int64 v42; // [rsp+B0h] [rbp+8h] BYREF
  const unsigned __int16 *v43; // [rsp+C0h] [rbp+18h]

  v43 = a3;
  v42 = a1;
  v5 = a3;
  string = 0;
  v7 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, L"NarratorTuned", 0xDu);
  v8 = v7;
  if ( v7 >= 0 )
  {
    *a4 = 0;
    v36 = 0;
    v37 = 0;
    v31 = 0;
    v10 = *a2;
    v11 = a2[1];
    try
    {
      while ( v10 != v11 )
      {
        v12 = *v10;
        v38 = v12;
        if ( v12 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
        v33 = 0;
        v13 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v12 + 64LL);
        WindowsDeleteString(0);
        v33 = 0;
        if ( v13(v12, &v33) >= 0 )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(v33, 0);
          matched = SystemSettings::DataModel::CMagnifierVoicesSingleton::ComputeLocaleMatchScore(
                      v15,
                      v5,
                      StringRawBuffer);
          LODWORD(v42) = matched;
          v35 = 0;
          if ( (int)Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>::As<Windows::Media::SpeechSynthesis::Internal::IVoiceInformationAllProperties>(
                      &v38,
                      &v35) >= 0 )
          {
            v30 = 0;
            v17 = v35;
            v18 = *(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v35 + 56LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
            if ( v18(v17, &v30) >= 0 )
            {
              v32 = 0;
              v19 = v30;
              v20 = *(int (__fastcall **)(BSTR, HSTRING, HSTRING *))(*(_QWORD *)v30 + 48LL);
              WindowsDeleteString(0);
              v32 = 0;
              if ( v20(v19, string, &v32) >= 0 )
              {
                v21 = WindowsGetStringRawBuffer(v32, 0);
                if ( *v21 == 49 && !v21[1] )
                  LODWORD(v42) = matched + 1;
              }
              WindowsDeleteString(v32);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
            v5 = v43;
          }
          v22 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v12 + 72LL);
          WindowsDeleteString(v31);
          v31 = 0;
          if ( v22(v12, &v31) >= 0 )
          {
            v30 = 0;
            v23 = WindowsGetStringRawBuffer(v31, 0);
            if ( ATL::CComBSTR::Append((ATL::CComBSTR *)&v30, v23) >= 0 )
            {
              v24 = std::make_pair<int &,ATL::CComBSTR &>(v39, &v42, &v30);
              std::vector<std::pair<int,ATL::CComBSTR>>::push_back(&v36, v24);
              SysFreeString(bstrString);
            }
            SysFreeString(v30);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
        }
        WindowsDeleteString(v33);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
        ++v10;
      }
      v25 = (_DWORD *)v36;
      if ( (_QWORD)v36 != *((_QWORD *)&v36 + 1) )
      {
        for ( i = (_DWORD *)(v36 + 16); i != *((_DWORD **)&v36 + 1); i += 4 )
        {
          v27 = i;
          if ( *v25 >= *i )
            v27 = v25;
          v25 = v27;
        }
        if ( v25 != *((_DWORD **)&v36 + 1) && (int)*v25 > 0 )
        {
          v28 = *((_QWORD *)v25 + 1);
          *((_QWORD *)v25 + 1) = 0;
          *a4 = v28;
        }
      }
      WindowsDeleteString(v31);
      v31 = 0;
      if ( (_QWORD)v36 )
      {
        std::_Destroy_range<std::allocator<std::pair<int,ATL::CComBSTR>>>(v36, *((__int64 *)&v36 + 1));
        std::_Deallocate<16>((void *)v36, (v37 - v36) & 0xFFFFFFFFFFFFFFF0uLL);
        v36 = 0;
        v37 = 0;
      }
      WindowsDeleteString(string);
      result = 0;
    }
    catch ( ... )
    {
      LODWORD(v42) = wil::details::in1diag3::Return_CaughtException(
                       retaddr,
                       (void *)0x3A3,
                       (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\magnifier.cpp",
                       v29);
      return (unsigned int)v42;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34C,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\magnifier.cpp",
      (const char *)(unsigned int)v7,
      (int)v30);
    WindowsDeleteString(string);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x18007b538  mov     rax, rsp
0x18007b53b  mov     [rax+10h], rbx
0x18007b53f  mov     [rax+20h], rsi
0x18007b543  mov     [rax+18h], r8
0x18007b547  mov     [rax+8], rcx
0x18007b54b  push    rdi
0x18007b54c  push    r12
0x18007b54e  push    r13
0x18007b550  push    r14
0x18007b552  push    r15
0x18007b554  sub     rsp, 80h
0x18007b55b  mov     r12, r9
0x18007b55e  mov     rsi, r8
0x18007b561  mov     rdi, rdx
0x18007b564  xor     r14d, r14d
0x18007b567  mov     [rax-68h], r14
0x18007b56b  lea     r8d, [r14+0Dh]; unsigned int
0x18007b56f  lea     rdx, aNarratortuned; "NarratorTuned"
0x18007b576  lea     rcx, [rax-68h]; this
0x18007b57a  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18007b57f  mov     ebx, eax
0x18007b581  test    eax, eax
0x18007b583  jns     short loc_18007B5BA
0x18007b585  mov     rcx, [rsp+0A8h]; this
0x18007b58d  mov     r9d, eax; char *
0x18007b590  lea     r8, aShellSystemset_79; "shell\\systemsettingsthreshold\\handler"...
0x18007b597  mov     edx, 34Ch; void *
0x18007b59c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b5a1  nop
0x18007b5a2  mov     rcx, [rsp+0A8h+string]; string
0x18007b5a7  call    cs:__imp_WindowsDeleteString
0x18007b5ae  nop     dword ptr [rax+rax+00h]
0x18007b5b3  mov     eax, ebx
0x18007b5b5  jmp     loc_18007B8BF
0x18007b5ba  mov     [r12], r14
0x18007b5be  xorps   xmm0, xmm0
0x18007b5c1  movdqu  [rsp+0A8h+var_58], xmm0
0x18007b5c7  mov     [rsp+0A8h+var_48], r14
0x18007b5cc  mov     [rsp+0A8h+var_80], r14
0x18007b5d1  mov     r15, [rdi]
0x18007b5d4  mov     r13, [rdi+8]
0x18007b5d8  cmp     r15, r13
0x18007b5db  jz      loc_18007B812
0x18007b5e1  mov     rbx, [r15]
0x18007b5e4  mov     [rsp+0A8h+var_40], rbx
0x18007b5e9  test    rbx, rbx
0x18007b5ec  jz      short loc_18007B5FE
0x18007b5ee  mov     rax, [rbx]
0x18007b5f1  mov     rcx, rbx
0x18007b5f4  mov     rax, [rax+8]
0x18007b5f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b5fd  nop
0x18007b5fe  mov     [rsp+0A8h+var_70], r14
0x18007b603  mov     rax, [rbx]
0x18007b606  mov     rdi, [rax+40h]
0x18007b60a  xor     ecx, ecx; string
0x18007b60c  call    cs:__imp_WindowsDeleteString
0x18007b613  nop     dword ptr [rax+rax+00h]
0x18007b618  mov     [rsp+0A8h+var_70], r14
0x18007b61d  lea     rdx, [rsp+0A8h+var_70]
0x18007b622  mov     rcx, rbx
0x18007b625  mov     rax, rdi
0x18007b628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b62d  test    eax, eax
0x18007b62f  js      loc_18007B7ED
0x18007b635  xor     edx, edx; length
0x18007b637  mov     rcx, [rsp+0A8h+var_70]; string
0x18007b63c  call    cs:__imp_WindowsGetStringRawBuffer
0x18007b643  nop     dword ptr [rax+rax+00h]
0x18007b648  mov     r8, rax; unsigned __int16 *
0x18007b64b  mov     rdx, rsi; unsigned __int16 *
0x18007b64e  call    ?ComputeLocaleMatchScore@CMagnifierVoicesSingleton@DataModel@SystemSettings@@AEAAHPEBG0@Z; SystemSettings::DataModel::CMagnifierVoicesSingleton::ComputeLocaleMatchScore(ushort const *,ushort const *)
0x18007b653  mov     r14d, eax
0x18007b656  mov     dword ptr [rsp+0A8h+arg_0], eax
0x18007b65d  xor     edi, edi
0x18007b65f  mov     [rsp+0A8h+var_60], rdi
0x18007b664  lea     rdx, [rsp+0A8h+var_60]
0x18007b669  lea     rcx, [rsp+0A8h+var_40]
0x18007b66e  call    ??$As@UIVoiceInformationAllProperties@Internal@SpeechSynthesis@Media@Windows@@@?$ComPtr@UIVoiceInformation@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIVoiceInformationAllProperties@Internal@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>::As<Windows::Media::SpeechSynthesis::Internal::IVoiceInformationAllProperties>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::Internal::IVoiceInformationAllProperties>>)
0x18007b673  test    eax, eax
0x18007b675  js      loc_18007B73B
0x18007b67b  mov     [rsp+0A8h+var_88], rdi
0x18007b680  mov     rsi, [rsp+0A8h+var_60]
0x18007b685  mov     rax, [rsi]
0x18007b688  mov     rdi, [rax+38h]
0x18007b68c  lea     rcx, [rsp+0A8h+var_88]
0x18007b691  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007b696  lea     rdx, [rsp+0A8h+var_88]
0x18007b69b  mov     rcx, rsi
0x18007b69e  mov     rax, rdi
0x18007b6a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b6a6  xor     ecx, ecx; string
0x18007b6a8  test    eax, eax
0x18007b6aa  js      short loc_18007B729
0x18007b6ac  mov     [rsp+0A8h+var_78], rcx
0x18007b6b1  mov     rsi, [rsp+0A8h+var_88]
0x18007b6b6  mov     rax, [rsi]
0x18007b6b9  mov     rdi, [rax+30h]
0x18007b6bd  call    cs:__imp_WindowsDeleteString
0x18007b6c4  nop     dword ptr [rax+rax+00h]
0x18007b6c9  mov     [rsp+0A8h+var_78], 0
0x18007b6d2  lea     r8, [rsp+0A8h+var_78]
0x18007b6d7  mov     rdx, [rsp+0A8h+string]
0x18007b6dc  mov     rcx, rsi
0x18007b6df  mov     rax, rdi
0x18007b6e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b6e7  xor     edi, edi
0x18007b6e9  test    eax, eax
0x18007b6eb  js      short loc_18007B717
0x18007b6ed  xor     edx, edx; length
0x18007b6ef  mov     rcx, [rsp+0A8h+var_78]; string
0x18007b6f4  call    cs:__imp_WindowsGetStringRawBuffer
0x18007b6fb  nop     dword ptr [rax+rax+00h]
0x18007b700  cmp     word ptr [rax], 31h ; '1'
0x18007b704  jnz     short loc_18007B717
0x18007b706  cmp     [rax+2], di
0x18007b70a  jnz     short loc_18007B717
0x18007b70c  inc     r14d
0x18007b70f  mov     dword ptr [rsp+0A8h+arg_0], r14d
0x18007b717  mov     rcx, [rsp+0A8h+var_78]; string
0x18007b71c  call    cs:__imp_WindowsDeleteString
0x18007b723  nop     dword ptr [rax+rax+00h]
0x18007b728  nop
0x18007b729  lea     rcx, [rsp+0A8h+var_88]
0x18007b72e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007b733  mov     rsi, [rsp+0A8h+arg_10]
0x18007b73b  mov     rax, [rbx]
0x18007b73e  mov     rdi, [rax+48h]
0x18007b742  mov     rcx, [rsp+0A8h+var_80]; string
0x18007b747  call    cs:__imp_WindowsDeleteString
0x18007b74e  nop     dword ptr [rax+rax+00h]
0x18007b753  xor     r14d, r14d
0x18007b756  mov     [rsp+0A8h+var_80], r14
0x18007b75b  lea     rdx, [rsp+0A8h+var_80]
0x18007b760  mov     rcx, rbx
0x18007b763  mov     rax, rdi
0x18007b766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b76b  test    eax, eax
0x18007b76d  js      short loc_18007B7E2
0x18007b76f  mov     [rsp+0A8h+var_88], r14
0x18007b774  xor     edx, edx; length
0x18007b776  mov     rcx, [rsp+0A8h+var_80]; string
0x18007b77b  call    cs:__imp_WindowsGetStringRawBuffer
0x18007b782  nop     dword ptr [rax+rax+00h]
0x18007b787  mov     rdx, rax; unsigned __int16 *
0x18007b78a  lea     rcx, [rsp+0A8h+var_88]; this
0x18007b78f  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18007b794  test    eax, eax
0x18007b796  js      short loc_18007B7D0
0x18007b798  lea     r8, [rsp+0A8h+var_88]
0x18007b79d  lea     rdx, [rsp+0A8h+arg_0]
0x18007b7a5  lea     rcx, [rsp+0A8h+var_38]
0x18007b7aa  call    ??$make_pair@AEAHAEAVCComBSTR@ATL@@@std@@YA?AU?$pair@HVCComBSTR@ATL@@@0@AEAHAEAVCComBSTR@ATL@@@Z; std::make_pair<int &,ATL::CComBSTR &>(int &,ATL::CComBSTR &)
0x18007b7af  nop
0x18007b7b0  mov     rdx, rax
0x18007b7b3  lea     rcx, [rsp+0A8h+var_58]
0x18007b7b8  call    ?push_back@?$vector@U?$pair@HVCComBSTR@ATL@@@std@@V?$allocator@U?$pair@HVCComBSTR@ATL@@@std@@@2@@std@@QEAAX$$QEAU?$pair@HVCComBSTR@ATL@@@2@@Z; std::vector<std::pair<int,ATL::CComBSTR>>::push_back(std::pair<int,ATL::CComBSTR> &&)
0x18007b7bd  nop
0x18007b7be  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x18007b7c3  call    cs:__imp_SysFreeString
0x18007b7ca  nop     dword ptr [rax+rax+00h]
0x18007b7cf  nop
0x18007b7d0  mov     rcx, [rsp+0A8h+var_88]; bstrString
0x18007b7d5  call    cs:__imp_SysFreeString
0x18007b7dc  nop     dword ptr [rax+rax+00h]
0x18007b7e1  nop
0x18007b7e2  lea     rcx, [rsp+0A8h+var_60]
0x18007b7e7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007b7ec  nop
0x18007b7ed  mov     rcx, [rsp+0A8h+var_70]; string
0x18007b7f2  call    cs:__imp_WindowsDeleteString
0x18007b7f9  nop     dword ptr [rax+rax+00h]
0x18007b7fe  nop
0x18007b7ff  lea     rcx, [rsp+0A8h+var_40]
0x18007b804  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007b809  add     r15, 8
0x18007b80d  jmp     loc_18007B5D8
0x18007b812  mov     rdx, qword ptr [rsp+0A8h+var_58]
0x18007b817  mov     r9, qword ptr [rsp+0A8h+var_58+8]
0x18007b81c  cmp     rdx, r9
0x18007b81f  jz      short loc_18007B855
0x18007b821  lea     r8, [rdx+10h]
0x18007b825  jmp     short loc_18007B83A
0x18007b827  mov     rcx, r8
0x18007b82a  mov     eax, [r8]
0x18007b82d  cmp     [rdx], eax
0x18007b82f  cmovge  rcx, rdx
0x18007b833  mov     rdx, rcx
0x18007b836  add     r8, 10h
0x18007b83a  cmp     r8, r9
0x18007b83d  jnz     short loc_18007B827
0x18007b83f  cmp     rdx, r9
0x18007b842  jz      short loc_18007B855
0x18007b844  cmp     [rdx], r14d
0x18007b847  jle     short loc_18007B855
0x18007b849  mov     rax, [rdx+8]
0x18007b84d  mov     [rdx+8], r14
0x18007b851  mov     [r12], rax
0x18007b855  mov     rcx, [rsp+0A8h+var_80]; string
0x18007b85a  call    cs:__imp_WindowsDeleteString
0x18007b861  nop     dword ptr [rax+rax+00h]
0x18007b866  mov     [rsp+0A8h+var_80], r14
0x18007b86b  mov     rcx, qword ptr [rsp+0A8h+var_58]
0x18007b870  test    rcx, rcx
0x18007b873  jz      short loc_18007B8A3
0x18007b875  mov     rdx, qword ptr [rsp+0A8h+var_58+8]
0x18007b87a  call    ??$_Destroy_range@V?$allocator@U?$pair@HVCComBSTR@ATL@@@std@@@std@@@std@@YAXPEAU?$pair@HVCComBSTR@ATL@@@0@QEAU10@AEAV?$allocator@U?$pair@HVCComBSTR@ATL@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::pair<int,ATL::CComBSTR>>>(std::pair<int,ATL::CComBSTR> *,std::pair<int,ATL::CComBSTR> * const,std::allocator<std::pair<int,ATL::CComBSTR>> &)
0x18007b87f  mov     rcx, qword ptr [rsp+0A8h+var_58]
0x18007b884  mov     rdx, [rsp+0A8h+var_48]
0x18007b889  sub     rdx, rcx
0x18007b88c  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18007b890  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18007b895  xorps   xmm0, xmm0
0x18007b898  movdqu  [rsp+0A8h+var_58], xmm0
0x18007b89e  mov     [rsp+0A8h+var_48], r14
0x18007b8a3  mov     rcx, [rsp+0A8h+string]; string
0x18007b8a8  call    cs:__imp_WindowsDeleteString
0x18007b8af  nop     dword ptr [rax+rax+00h]
0x18007b8b4  xor     eax, eax
0x18007b8b6  jmp     short loc_18007B8BF
0x18007b8b8  mov     eax, dword ptr [rsp+0A8h+arg_0]
0x18007b8bf  lea     r11, [rsp+0A8h+var_28]
0x18007b8c7  mov     rbx, [r11+38h]
0x18007b8cb  mov     rsi, [r11+48h]
0x18007b8cf  mov     rsp, r11
0x18007b8d2  pop     r15
0x18007b8d4  pop     r14
0x18007b8d6  pop     r13
0x18007b8d8  pop     r12
0x18007b8da  pop     rdi
0x18007b8db  retn
```
