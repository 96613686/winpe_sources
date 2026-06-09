# SystemSettings::DataModel::CNarratorVoicesSingleton::RetrieveDefaultVoiceInternal(std::vector<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>,std::allocator<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>>> const &,ushort const *,ushort * *)

- ea: `0x1800842a8`
- end: `0x180084661`
- name: `?RetrieveDefaultVoiceInternal@CNarratorVoicesSingleton@DataModel@SystemSettings@@AEAAJAEBV?$vector@V?$ComPtr@UIVoiceInformation@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIVoiceInformation@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@@std@@@std@@PEBGPEAPEAG@Z`
- size: `953`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800840a0`

## callees

- `0x180011bb0`
- `0x180019a20`
- `0x18001e4b0`
- `0x180024410`
- `0x1800410cc`
- `0x1800773c4`
- `0x1800782c0`
- `0x1800786dc`
- `0x1800796f8`
- `0x180079808`
- `0x18007d49c`
- `0x1800842a8`
- `0x180289010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180084547`
- `OLEAUT32!__imp_SysFreeString` at `0x180084559`
- `OLEAUT32!__imp_SysFreeString` at `0x180084547`
- `OLEAUT32!__imp_SysFreeString` at `0x180084559`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084317`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084379`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084438`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800844a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800844cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084576`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800845de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008462c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084317`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084379`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084438`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800844a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800844cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084576`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800845de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008462c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800843a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008446d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800844ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800843a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008446d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800844ff`

## string_xrefs

- `0x180084300`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\narrator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall SystemSettings::DataModel::CNarratorVoicesSingleton::RetrieveDefaultVoiceInternal(
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
  int v22; // edx
  int (__fastcall *v23)(__int64, HSTRING *); // rdi
  const unsigned __int16 *v24; // rax
  __int64 v25; // rdx
  _DWORD *v26; // rdx
  _DWORD *i; // r8
  _DWORD *v28; // rcx
  __int64 v29; // rax
  const char *v30; // r9
  BSTR v31; // [rsp+20h] [rbp-88h] BYREF
  HSTRING v32; // [rsp+28h] [rbp-80h] BYREF
  HSTRING v33; // [rsp+30h] [rbp-78h] BYREF
  HSTRING v34; // [rsp+38h] [rbp-70h] BYREF
  HSTRING string; // [rsp+40h] [rbp-68h] BYREF
  __int64 v36; // [rsp+48h] [rbp-60h] BYREF
  __int128 v37; // [rsp+50h] [rbp-58h] BYREF
  __int64 v38; // [rsp+60h] [rbp-48h]
  __int64 v39; // [rsp+68h] [rbp-40h] BYREF
  char v40[8]; // [rsp+70h] [rbp-38h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  __int64 v43; // [rsp+B0h] [rbp+8h] BYREF
  const unsigned __int16 *v44; // [rsp+C0h] [rbp+18h]

  v44 = a3;
  v43 = a1;
  v5 = a3;
  string = 0;
  v7 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, L"NarratorTuned", 0xDu);
  v8 = v7;
  if ( v7 >= 0 )
  {
    *a4 = 0;
    std::vector<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>>::vector<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>>(&v37);
    v32 = 0;
    v10 = *a2;
    v11 = a2[1];
    try
    {
      while ( v10 != v11 )
      {
        v12 = *v10;
        v39 = v12;
        if ( v12 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
        v34 = 0;
        v13 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v12 + 64LL);
        WindowsDeleteString(0);
        v34 = 0;
        if ( v13(v12, &v34) >= 0 )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(v34, 0);
          matched = SystemSettings::DataModel::CMagnifierVoicesSingleton::ComputeLocaleMatchScore(
                      v15,
                      v5,
                      StringRawBuffer);
          LODWORD(v43) = matched;
          v36 = 0;
          if ( (int)Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>::As<Windows::Media::SpeechSynthesis::Internal::IVoiceInformationAllProperties>(
                      &v39,
                      &v36) >= 0 )
          {
            v31 = 0;
            v17 = v36;
            v18 = *(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v36 + 56LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
            if ( v18(v17, &v31) >= 0 )
            {
              v33 = 0;
              v19 = v31;
              v20 = *(int (__fastcall **)(BSTR, HSTRING, HSTRING *))(*(_QWORD *)v31 + 48LL);
              WindowsDeleteString(0);
              v33 = 0;
              if ( v20(v19, string, &v33) >= 0 )
              {
                v21 = WindowsGetStringRawBuffer(v33, 0);
                v22 = *v21 - 49;
                if ( *v21 == 49 )
                  v22 = v21[1];
                if ( !v22 )
                  LODWORD(v43) = matched + 1;
              }
              WindowsDeleteString(v33);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
            v5 = v44;
          }
          v23 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v12 + 72LL);
          WindowsDeleteString(v32);
          v32 = 0;
          if ( v23(v12, &v32) >= 0 )
          {
            v31 = 0;
            v24 = WindowsGetStringRawBuffer(v32, 0);
            if ( ATL::CComBSTR::Append((ATL::CComBSTR *)&v31, v24) >= 0 )
            {
              v25 = std::make_pair<int &,ATL::CComBSTR &>(v40, &v43, &v31);
              std::vector<std::pair<int,ATL::CComBSTR>>::push_back(&v37, v25);
              SysFreeString(bstrString);
            }
            SysFreeString(v31);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
        }
        WindowsDeleteString(v34);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
        ++v10;
      }
      v26 = (_DWORD *)v37;
      if ( (_QWORD)v37 != *((_QWORD *)&v37 + 1) )
      {
        for ( i = (_DWORD *)(v37 + 16); i != *((_DWORD **)&v37 + 1); i += 4 )
        {
          v28 = i;
          if ( *v26 >= *i )
            v28 = v26;
          v26 = v28;
        }
        if ( v26 != *((_DWORD **)&v37 + 1) && (int)*v26 > 0 )
        {
          v29 = *((_QWORD *)v26 + 1);
          *((_QWORD *)v26 + 1) = 0;
          *a4 = v29;
        }
      }
      WindowsDeleteString(v32);
      v32 = 0;
      if ( (_QWORD)v37 )
      {
        std::_Destroy_range<std::allocator<std::pair<int,ATL::CComBSTR>>>(v37, *((_QWORD *)&v37 + 1));
        std::_Deallocate<16>(v37, (v38 - v37) & 0xFFFFFFFFFFFFFFF0uLL);
        v37 = 0;
        v38 = 0;
      }
      WindowsDeleteString(string);
      result = 0;
    }
    catch ( ... )
    {
      LODWORD(v43) = wil::details::in1diag3::Return_CaughtException(
                       retaddr,
                       (void *)0x29A,
                       (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\narrator.cpp",
                       v30);
      return (unsigned int)v43;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x245,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\narrator.cpp",
      (const char *)(unsigned int)v7,
      (int)v31);
    WindowsDeleteString(string);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x1800842a8  mov     rax, rsp
0x1800842ab  mov     [rax+10h], rbx
0x1800842af  mov     [rax+20h], rsi
0x1800842b3  mov     [rax+18h], r8
0x1800842b7  mov     [rax+8], rcx
0x1800842bb  push    rdi
0x1800842bc  push    r12
0x1800842be  push    r13
0x1800842c0  push    r14
0x1800842c2  push    r15
0x1800842c4  sub     rsp, 80h
0x1800842cb  mov     r12, r9
0x1800842ce  mov     rsi, r8
0x1800842d1  mov     rdi, rdx
0x1800842d4  xor     r14d, r14d
0x1800842d7  mov     [rax-68h], r14
0x1800842db  lea     r8d, [r14+0Dh]; unsigned int
0x1800842df  lea     rdx, aNarratortuned_0; "NarratorTuned"
0x1800842e6  lea     rcx, [rax-68h]; this
0x1800842ea  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1800842ef  mov     ebx, eax
0x1800842f1  test    eax, eax
0x1800842f3  jns     short loc_18008432A
0x1800842f5  mov     rcx, [rsp+0A8h]; this
0x1800842fd  mov     r9d, eax; char *
0x180084300  lea     r8, aShellSystemset_68; "shell\\systemsettingsthreshold\\handler"...
0x180084307  mov     edx, 245h; void *
0x18008430c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084311  nop
0x180084312  mov     rcx, [rsp+0A8h+string]; string
0x180084317  call    cs:__imp_WindowsDeleteString
0x18008431e  nop     dword ptr [rax+rax+00h]
0x180084323  mov     eax, ebx
0x180084325  jmp     loc_180084643
0x18008432a  mov     [r12], r14
0x18008432e  lea     rcx, [rsp+0A8h+var_58]; void *
0x180084333  call    ??0?$vector@V?$ComPtr@UIVoiceInformation@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIVoiceInformation@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>>::vector<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>>(void)
0x180084338  nop
0x180084339  mov     [rsp+0A8h+var_80], r14
0x18008433e  mov     r15, [rdi]
0x180084341  mov     r13, [rdi+8]
0x180084345  cmp     r15, r13
0x180084348  jz      loc_180084596
0x18008434e  mov     rbx, [r15]
0x180084351  mov     [rsp+0A8h+var_40], rbx
0x180084356  test    rbx, rbx
0x180084359  jz      short loc_18008436B
0x18008435b  mov     rax, [rbx]
0x18008435e  mov     rcx, rbx
0x180084361  mov     rax, [rax+8]
0x180084365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008436a  nop
0x18008436b  mov     [rsp+0A8h+var_70], r14
0x180084370  mov     rax, [rbx]
0x180084373  mov     rdi, [rax+40h]
0x180084377  xor     ecx, ecx; string
0x180084379  call    cs:__imp_WindowsDeleteString
0x180084380  nop     dword ptr [rax+rax+00h]
0x180084385  mov     [rsp+0A8h+var_70], r14
0x18008438a  lea     rdx, [rsp+0A8h+var_70]
0x18008438f  mov     rcx, rbx
0x180084392  mov     rax, rdi
0x180084395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008439a  test    eax, eax
0x18008439c  js      loc_180084571
0x1800843a2  xor     edx, edx; length
0x1800843a4  mov     rcx, [rsp+0A8h+var_70]; string
0x1800843a9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800843b0  nop     dword ptr [rax+rax+00h]
0x1800843b5  mov     r8, rax; unsigned __int16 *
0x1800843b8  mov     rdx, rsi; unsigned __int16 *
0x1800843bb  call    ?ComputeLocaleMatchScore@CMagnifierVoicesSingleton@DataModel@SystemSettings@@AEAAHPEBG0@Z; SystemSettings::DataModel::CMagnifierVoicesSingleton::ComputeLocaleMatchScore(ushort const *,ushort const *)
0x1800843c0  mov     r14d, eax
0x1800843c3  mov     dword ptr [rsp+0A8h+arg_0], eax
0x1800843ca  mov     [rsp+0A8h+var_60], 0
0x1800843d3  lea     rdx, [rsp+0A8h+var_60]
0x1800843d8  lea     rcx, [rsp+0A8h+var_40]
0x1800843dd  call    ??$As@UIVoiceInformationAllProperties@Internal@SpeechSynthesis@Media@Windows@@@?$ComPtr@UIVoiceInformation@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIVoiceInformationAllProperties@Internal@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>::As<Windows::Media::SpeechSynthesis::Internal::IVoiceInformationAllProperties>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::Internal::IVoiceInformationAllProperties>>)
0x1800843e2  test    eax, eax
0x1800843e4  js      loc_1800844BF
0x1800843ea  mov     [rsp+0A8h+var_88], 0
0x1800843f3  mov     rsi, [rsp+0A8h+var_60]
0x1800843f8  mov     rax, [rsi]
0x1800843fb  mov     rdi, [rax+38h]
0x1800843ff  lea     rcx, [rsp+0A8h+var_88]
0x180084404  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180084409  lea     rdx, [rsp+0A8h+var_88]
0x18008440e  mov     rcx, rsi
0x180084411  mov     rax, rdi
0x180084414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084419  test    eax, eax
0x18008441b  js      loc_1800844AD
0x180084421  mov     [rsp+0A8h+var_78], 0
0x18008442a  mov     rsi, [rsp+0A8h+var_88]
0x18008442f  mov     rax, [rsi]
0x180084432  mov     rdi, [rax+30h]
0x180084436  xor     ecx, ecx; string
0x180084438  call    cs:__imp_WindowsDeleteString
0x18008443f  nop     dword ptr [rax+rax+00h]
0x180084444  mov     [rsp+0A8h+var_78], 0
0x18008444d  lea     r8, [rsp+0A8h+var_78]
0x180084452  mov     rdx, [rsp+0A8h+string]
0x180084457  mov     rcx, rsi
0x18008445a  mov     rax, rdi
0x18008445d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084462  test    eax, eax
0x180084464  js      short loc_18008449B
0x180084466  xor     edx, edx; length
0x180084468  mov     rcx, [rsp+0A8h+var_78]; string
0x18008446d  call    cs:__imp_WindowsGetStringRawBuffer
0x180084474  nop     dword ptr [rax+rax+00h]
0x180084479  movzx   edx, word ptr [rax]
0x18008447c  sub     edx, 31h ; '1'
0x18008447f  jnz     short loc_18008448C
0x180084481  movzx   edx, word ptr [rax+2]
0x180084485  xor     eax, eax
0x180084487  movzx   ecx, ax
0x18008448a  sub     edx, ecx
0x18008448c  test    edx, edx
0x18008448e  jnz     short loc_18008449B
0x180084490  inc     r14d
0x180084493  mov     dword ptr [rsp+0A8h+arg_0], r14d
0x18008449b  mov     rcx, [rsp+0A8h+var_78]; string
0x1800844a0  call    cs:__imp_WindowsDeleteString
0x1800844a7  nop     dword ptr [rax+rax+00h]
0x1800844ac  nop
0x1800844ad  lea     rcx, [rsp+0A8h+var_88]
0x1800844b2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800844b7  mov     rsi, [rsp+0A8h+arg_10]
0x1800844bf  mov     rax, [rbx]
0x1800844c2  mov     rdi, [rax+48h]
0x1800844c6  mov     rcx, [rsp+0A8h+var_80]; string
0x1800844cb  call    cs:__imp_WindowsDeleteString
0x1800844d2  nop     dword ptr [rax+rax+00h]
0x1800844d7  xor     r14d, r14d
0x1800844da  mov     [rsp+0A8h+var_80], r14
0x1800844df  lea     rdx, [rsp+0A8h+var_80]
0x1800844e4  mov     rcx, rbx
0x1800844e7  mov     rax, rdi
0x1800844ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800844ef  test    eax, eax
0x1800844f1  js      short loc_180084566
0x1800844f3  mov     [rsp+0A8h+var_88], r14
0x1800844f8  xor     edx, edx; length
0x1800844fa  mov     rcx, [rsp+0A8h+var_80]; string
0x1800844ff  call    cs:__imp_WindowsGetStringRawBuffer
0x180084506  nop     dword ptr [rax+rax+00h]
0x18008450b  mov     rdx, rax; unsigned __int16 *
0x18008450e  lea     rcx, [rsp+0A8h+var_88]; this
0x180084513  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x180084518  test    eax, eax
0x18008451a  js      short loc_180084554
0x18008451c  lea     r8, [rsp+0A8h+var_88]
0x180084521  lea     rdx, [rsp+0A8h+arg_0]
0x180084529  lea     rcx, [rsp+0A8h+var_38]
0x18008452e  call    ??$make_pair@AEAHAEAVCComBSTR@ATL@@@std@@YA?AU?$pair@HVCComBSTR@ATL@@@0@AEAHAEAVCComBSTR@ATL@@@Z; std::make_pair<int &,ATL::CComBSTR &>(int &,ATL::CComBSTR &)
0x180084533  nop
0x180084534  mov     rdx, rax
0x180084537  lea     rcx, [rsp+0A8h+var_58]
0x18008453c  call    ?push_back@?$vector@U?$pair@HVCComBSTR@ATL@@@std@@V?$allocator@U?$pair@HVCComBSTR@ATL@@@std@@@2@@std@@QEAAX$$QEAU?$pair@HVCComBSTR@ATL@@@2@@Z; std::vector<std::pair<int,ATL::CComBSTR>>::push_back(std::pair<int,ATL::CComBSTR> &&)
0x180084541  nop
0x180084542  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x180084547  call    cs:__imp_SysFreeString
0x18008454e  nop     dword ptr [rax+rax+00h]
0x180084553  nop
0x180084554  mov     rcx, [rsp+0A8h+var_88]; bstrString
0x180084559  call    cs:__imp_SysFreeString
0x180084560  nop     dword ptr [rax+rax+00h]
0x180084565  nop
0x180084566  lea     rcx, [rsp+0A8h+var_60]
0x18008456b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180084570  nop
0x180084571  mov     rcx, [rsp+0A8h+var_70]; string
0x180084576  call    cs:__imp_WindowsDeleteString
0x18008457d  nop     dword ptr [rax+rax+00h]
0x180084582  nop
0x180084583  lea     rcx, [rsp+0A8h+var_40]
0x180084588  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008458d  add     r15, 8
0x180084591  jmp     loc_180084345
0x180084596  mov     rdx, qword ptr [rsp+0A8h+var_58]
0x18008459b  mov     r9, qword ptr [rsp+0A8h+var_58+8]
0x1800845a0  cmp     rdx, r9
0x1800845a3  jz      short loc_1800845D9
0x1800845a5  lea     r8, [rdx+10h]
0x1800845a9  jmp     short loc_1800845BE
0x1800845ab  mov     rcx, r8
0x1800845ae  mov     eax, [r8]
0x1800845b1  cmp     [rdx], eax
0x1800845b3  cmovge  rcx, rdx
0x1800845b7  mov     rdx, rcx
0x1800845ba  add     r8, 10h
0x1800845be  cmp     r8, r9
0x1800845c1  jnz     short loc_1800845AB
0x1800845c3  cmp     rdx, r9
0x1800845c6  jz      short loc_1800845D9
0x1800845c8  cmp     [rdx], r14d
0x1800845cb  jle     short loc_1800845D9
0x1800845cd  mov     rax, [rdx+8]
0x1800845d1  mov     [rdx+8], r14
0x1800845d5  mov     [r12], rax
0x1800845d9  mov     rcx, [rsp+0A8h+var_80]; string
0x1800845de  call    cs:__imp_WindowsDeleteString
0x1800845e5  nop     dword ptr [rax+rax+00h]
0x1800845ea  mov     [rsp+0A8h+var_80], r14
0x1800845ef  mov     rcx, qword ptr [rsp+0A8h+var_58]
0x1800845f4  test    rcx, rcx
0x1800845f7  jz      short loc_180084627
0x1800845f9  mov     rdx, qword ptr [rsp+0A8h+var_58+8]
0x1800845fe  call    ??$_Destroy_range@V?$allocator@U?$pair@HVCComBSTR@ATL@@@std@@@std@@@std@@YAXPEAU?$pair@HVCComBSTR@ATL@@@0@QEAU10@AEAV?$allocator@U?$pair@HVCComBSTR@ATL@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::pair<int,ATL::CComBSTR>>>(std::pair<int,ATL::CComBSTR> *,std::pair<int,ATL::CComBSTR> * const,std::allocator<std::pair<int,ATL::CComBSTR>> &)
0x180084603  mov     rcx, qword ptr [rsp+0A8h+var_58]
0x180084608  mov     rdx, [rsp+0A8h+var_48]
0x18008460d  sub     rdx, rcx
0x180084610  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180084614  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180084619  xorps   xmm0, xmm0
0x18008461c  movdqu  [rsp+0A8h+var_58], xmm0
0x180084622  mov     [rsp+0A8h+var_48], r14
0x180084627  mov     rcx, [rsp+0A8h+string]; string
0x18008462c  call    cs:__imp_WindowsDeleteString
0x180084633  nop     dword ptr [rax+rax+00h]
0x180084638  xor     eax, eax
0x18008463a  jmp     short loc_180084643
0x18008463c  mov     eax, dword ptr [rsp+0A8h+arg_0]
0x180084643  lea     r11, [rsp+0A8h+var_28]
0x18008464b  mov     rbx, [r11+38h]
0x18008464f  mov     rsi, [r11+48h]
0x180084653  mov     rsp, r11
0x180084656  pop     r15
0x180084658  pop     r14
0x18008465a  pop     r13
0x18008465c  pop     r12
0x18008465e  pop     rdi
0x18008465f  retn
```
