# WuTrace::RetryAttemptsData::ToJsonBlob(wchar_t * *)

- ea: `0x14003ca4c`
- end: `0x14003cd97`
- name: `?ToJsonBlob@RetryAttemptsData@WuTrace@@QEBAJPEAPEA_W@Z`
- size: `843`
- prototype: `__int64 __fastcall(WuTrace::RetryAttemptsData *__hidden this, wchar_t **)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140037798`
- `0x140037a14`

## callees

- `0x140008de4`
- `0x14001162c`
- `0x14003bf88`
- `0x14003ca4c`
- `0x14003ce70`
- `0x14003cf98`
- `0x140045dc0`
- `0x14004cd00`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14003cc87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14003cc87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14003caac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14003cb06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14003caac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14003cb06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003cc5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003ccbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003cc5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003ccbf`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14003cb40`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14003cb40`

## string_xrefs

- `0x14003caff`: `Windows.Data.Json.JsonValue`
- `0x14003caa5`: `Windows.Data.Json.JsonArray`
- `0x14003cad4`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x14003cb53`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x14003cbec`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x14003ccaa`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`
- `0x14003cd4c`: `C:\__w\1\s\src\Client\lib\util\WuTraceCommonStructs.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=36
__int64 __fastcall WuTrace::RetryAttemptsData::ToJsonBlob(WuTrace::RetryAttemptsData *this, wchar_t **a2)
{
  HRESULT v3; // eax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // eax
  int i; // ebx
  HRESULT v8; // eax
  int v9; // edx
  unsigned int v10; // r8d
  HSTRING v11; // rbx
  __int64 v12; // rcx
  int ActivationFactory; // eax
  int v14; // eax
  unsigned __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // rdi
  __int64 (__fastcall ***v18)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v19)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rbx
  __int64 (__fastcall *v23)(__int64, HSTRING *); // rdi
  PCWSTR StringRawBuffer; // rax
  __int64 (__fastcall ***v25)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  int v29; // eax
  __int64 (__fastcall ***v31)(_QWORD, _QWORD, _QWORD); // [rsp+20h] [rbp-60h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-58h] BYREF
  HSTRING string; // [rsp+40h] [rbp-40h] BYREF
  HSTRING v34; // [rsp+48h] [rbp-38h] BYREF
  __int64 v35; // [rsp+50h] [rbp-30h] BYREF
  __int64 (__fastcall ***v36)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-28h] BYREF
  __int64 v37; // [rsp+60h] [rbp-20h] BYREF
  __int64 (__fastcall ***v38)(_QWORD, GUID *, _QWORD); // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  if ( *(_QWORD *)this && *(_DWORD *)(*(_QWORD *)this + 24LL) )
  {
    v38 = 0;
    string = 0;
    v3 = WindowsCreateStringReference(L"Windows.Data.Json.JsonArray", 0x1Bu, &hstringHeader, &string);
    if ( v3 >= 0 )
    {
      v6 = ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonArray>>(
             (__int64)string,
             (__int64 *)&v38);
      i = v6;
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xEC,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
          (const char *)(unsigned int)v6,
          (int)v31);
LABEL_39:
        v28 = (__int64)v38;
        if ( v38 )
        {
          v38 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
        }
        return (unsigned int)i;
      }
      v37 = 0;
      string = 0;
      v8 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
      if ( v8 >= 0 )
      {
        v11 = string;
        v12 = v37;
        if ( v37 )
        {
          v37 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        }
        ActivationFactory = RoGetActivationFactory(v11, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v37);
        i = ActivationFactory;
        if ( ActivationFactory < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xF0,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
            (const char *)(unsigned int)ActivationFactory,
            (int)v31);
LABEL_37:
          v27 = v37;
          if ( v37 )
          {
            v37 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
          }
          goto LABEL_39;
        }
        v35 = 0;
        v36 = 0;
        v14 = (**v38)(v38, &GUID_d44662bc_dce3_59a8_9272_4b210f33908b, &v36);
        i = v14;
        if ( v14 < 0 )
        {
          v15 = (unsigned int)v14;
          v16 = 244;
LABEL_21:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v16,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
            (const char *)v15,
            (int)v31);
LABEL_33:
          v25 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v36;
          if ( v36 )
          {
            v36 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v25)[2])(v25);
          }
          v26 = v35;
          if ( v35 )
          {
            v35 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          }
          goto LABEL_37;
        }
        v17 = *(_QWORD *)this;
        if ( v17 )
        {
          for ( i = 0; i >= 0; i = anonymous_namespace_::AppendRetryAttemptDataToJsonVector(v17, &v31) )
          {
            v17 = *(_QWORD *)(v17 + 8);
            if ( !v17 )
              break;
            v31 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v36;
            if ( v36 )
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v36)[1])(v36);
          }
          if ( i < 0 )
          {
            v15 = (unsigned int)i;
            v16 = 252;
            goto LABEL_21;
          }
        }
        v34 = 0;
        v18 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v36;
        v19 = **v36;
        v20 = v35;
        if ( v35 )
        {
          v35 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        }
        i = v19(v18, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, &v35);
        if ( i >= 0 )
        {
          v22 = v35;
          v23 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v35 + 56LL);
          WindowsDeleteString(v34);
          v34 = 0;
          i = v23(v22, &v34);
          if ( i >= 0 )
          {
            StringRawBuffer = WindowsGetStringRawBuffer(v34, 0);
            i = DuplicateString<wchar_t const *,wchar_t *>(StringRawBuffer);
            if ( i >= 0 )
            {
              i = 0;
              goto LABEL_32;
            }
            v21 = 260;
          }
          else
          {
            v21 = 259;
          }
        }
        else
        {
          v21 = 258;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v21,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
          (const char *)(unsigned int)i,
          (int)v31);
LABEL_32:
        WindowsDeleteString(v34);
        v34 = 0;
        goto LABEL_33;
      }
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v8, v9, v10);
    }
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v3, v4, v5);
    JUMPOUT(0x14003CD96LL);
  }
  v29 = DuplicateString<wchar_t const *,wchar_t *>(&OutputString);
  i = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\WuTraceCommonStructs.cpp",
      (const char *)(unsigned int)v29,
      (int)v31);
    return (unsigned int)i;
  }
  return 0;
}

```

## disassembly

```asm
0x14003ca4c  mov     [rsp-18h+arg_10], rbx
0x14003ca51  mov     [rsp-18h+arg_18], rsi
0x14003ca56  push    rbp
0x14003ca57  push    rdi
0x14003ca58  push    r14
0x14003ca5a  mov     rbp, rsp
0x14003ca5d  sub     rsp, 80h
0x14003ca64  mov     rax, cs:__security_cookie
0x14003ca6b  xor     rax, rsp
0x14003ca6e  mov     [rbp+var_8], rax
0x14003ca72  mov     rsi, rdx
0x14003ca75  mov     rdi, rcx
0x14003ca78  mov     rax, [rcx]
0x14003ca7b  xor     r14d, r14d
0x14003ca7e  test    rax, rax
0x14003ca81  jz      loc_14003CD33
0x14003ca87  cmp     [rax+18h], r14d
0x14003ca8b  jz      loc_14003CD33
0x14003ca91  mov     [rbp+var_18], r14
0x14003ca95  mov     [rbp+string], r14
0x14003ca99  lea     r9, [rbp+string]; string
0x14003ca9d  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14003caa1  lea     edx, [r14+1Bh]; length
0x14003caa5  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QB_WB; "Windows.Data.Json.JsonArray"
0x14003caac  call    cs:__imp_WindowsCreateStringReference
0x14003cab2  test    eax, eax
0x14003cab4  js      loc_14003CD8F
0x14003caba  lea     rdx, [rbp+var_18]
0x14003cabe  mov     rcx, [rbp+string]
0x14003cac2  call    ??$ActivateInstance@V?$ComPtr@UIJsonArray@Json@Data@Windows@ABI@@@WRL@Microsoft@@@Foundation@Windows@ABI@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonArray@Json@Data@Windows@ABI@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonArray>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ABI::Windows::Data::Json::IJsonArray>>)
0x14003cac7  mov     ebx, eax
0x14003cac9  test    eax, eax
0x14003cacb  jns     short loc_14003CAEA
0x14003cacd  mov     rcx, [rbp+18h]; this
0x14003cad1  mov     r9d, eax; char *
0x14003cad4  lea     r8, aCW1SSrcClientL_21; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003cadb  mov     edx, 0ECh; void *
0x14003cae0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003cae5  jmp     loc_14003CD17
0x14003caea  mov     [rbp+var_20], r14
0x14003caee  mov     [rbp+string], r14
0x14003caf2  lea     r9, [rbp+string]; string
0x14003caf6  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14003cafa  mov     edx, 1Bh; length
0x14003caff  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QB_WB; "Windows.Data.Json.JsonValue"
0x14003cb06  call    cs:__imp_WindowsCreateStringReference
0x14003cb0c  test    eax, eax
0x14003cb0e  js      loc_14003CD87
0x14003cb14  mov     rbx, [rbp+string]
0x14003cb18  mov     rcx, [rbp+var_20]
0x14003cb1c  test    rcx, rcx
0x14003cb1f  jz      short loc_14003CB32
0x14003cb21  mov     [rbp+var_20], r14
0x14003cb25  mov     rax, [rcx]
0x14003cb28  mov     rax, [rax+10h]
0x14003cb2c  call    _guard_dispatch_icall
0x14003cb31  nop
0x14003cb32  lea     r8, [rbp+var_20]
0x14003cb36  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x14003cb3d  mov     rcx, rbx
0x14003cb40  call    cs:__imp_RoGetActivationFactory
0x14003cb46  mov     ebx, eax
0x14003cb48  test    eax, eax
0x14003cb4a  jns     short loc_14003CB69
0x14003cb4c  mov     rcx, [rbp+18h]; this
0x14003cb50  mov     r9d, eax; char *
0x14003cb53  lea     r8, aCW1SSrcClientL_21; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003cb5a  mov     edx, 0F0h; void *
0x14003cb5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003cb64  jmp     loc_14003CCFD
0x14003cb69  mov     [rbp+var_30], r14
0x14003cb6d  mov     [rbp+var_28], r14
0x14003cb71  mov     rcx, [rbp+var_18]
0x14003cb75  mov     rax, [rcx]
0x14003cb78  lea     r8, [rbp+var_28]
0x14003cb7c  lea     rdx, _GUID_d44662bc_dce3_59a8_9272_4b210f33908b
0x14003cb83  mov     rax, [rax]
0x14003cb86  call    _guard_dispatch_icall
0x14003cb8b  mov     ebx, eax
0x14003cb8d  test    eax, eax
0x14003cb8f  jns     short loc_14003CB9B
0x14003cb91  mov     r9d, eax
0x14003cb94  mov     edx, 0F4h
0x14003cb99  jmp     short loc_14003CBEC
0x14003cb9b  mov     rdi, [rdi]
0x14003cb9e  test    rdi, rdi
0x14003cba1  jz      short loc_14003CC01
0x14003cba3  mov     ebx, r14d
0x14003cba6  jmp     short loc_14003CBD7
0x14003cba8  mov     rcx, [rbp+var_28]
0x14003cbac  mov     [rbp+var_60], rcx
0x14003cbb0  test    rcx, rcx
0x14003cbb3  jz      short loc_14003CBC2
0x14003cbb5  mov     rax, [rcx]
0x14003cbb8  mov     rax, [rax+8]
0x14003cbbc  call    _guard_dispatch_icall
0x14003cbc1  nop
0x14003cbc2  lea     rdx, [rbp+var_60]
0x14003cbc6  mov     rcx, rdi
0x14003cbc9  call    _anonymous_namespace___AppendRetryAttemptDataToJsonVector
0x14003cbce  mov     ebx, eax
0x14003cbd0  shr     eax, 1Fh
0x14003cbd3  test    al, al
0x14003cbd5  jnz     short loc_14003CBE0
0x14003cbd7  mov     rdi, [rdi+8]
0x14003cbdb  test    rdi, rdi
0x14003cbde  jnz     short loc_14003CBA8
0x14003cbe0  test    ebx, ebx
0x14003cbe2  jns     short loc_14003CC01
0x14003cbe4  mov     r9d, ebx; char *
0x14003cbe7  mov     edx, 0FCh; void *
0x14003cbec  lea     r8, aCW1SSrcClientL_21; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003cbf3  mov     rcx, [rbp+18h]; this
0x14003cbf7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003cbfc  jmp     loc_14003CCC9
0x14003cc01  mov     [rbp+var_38], r14
0x14003cc05  mov     rbx, [rbp+var_28]
0x14003cc09  mov     rax, [rbx]
0x14003cc0c  mov     rdi, [rax]
0x14003cc0f  mov     rcx, [rbp+var_30]
0x14003cc13  test    rcx, rcx
0x14003cc16  jz      short loc_14003CC29
0x14003cc18  mov     [rbp+var_30], r14
0x14003cc1c  mov     rdx, [rcx]
0x14003cc1f  mov     rax, [rdx+10h]
0x14003cc23  call    _guard_dispatch_icall
0x14003cc28  nop
0x14003cc29  lea     r8, [rbp+var_30]
0x14003cc2d  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x14003cc34  mov     rcx, rbx
0x14003cc37  mov     rax, rdi
0x14003cc3a  call    _guard_dispatch_icall
0x14003cc3f  mov     ebx, eax
0x14003cc41  test    eax, eax
0x14003cc43  jns     short loc_14003CC4C
0x14003cc45  mov     edx, 102h
0x14003cc4a  jmp     short loc_14003CCA3
0x14003cc4c  mov     rbx, [rbp+var_30]
0x14003cc50  mov     rax, [rbx]
0x14003cc53  mov     rdi, [rax+38h]
0x14003cc57  mov     rcx, [rbp+var_38]; string
0x14003cc5b  call    cs:__imp_WindowsDeleteString
0x14003cc61  mov     [rbp+var_38], r14
0x14003cc65  lea     rdx, [rbp+var_38]
0x14003cc69  mov     rcx, rbx
0x14003cc6c  mov     rax, rdi
0x14003cc6f  call    _guard_dispatch_icall
0x14003cc74  mov     ebx, eax
0x14003cc76  test    eax, eax
0x14003cc78  jns     short loc_14003CC81
0x14003cc7a  mov     edx, 103h
0x14003cc7f  jmp     short loc_14003CCA3
0x14003cc81  xor     edx, edx; length
0x14003cc83  mov     rcx, [rbp+var_38]; string
0x14003cc87  call    cs:__imp_WindowsGetStringRawBuffer
0x14003cc8d  mov     rdx, rsi
0x14003cc90  mov     rcx, rax
0x14003cc93  call    ??$DuplicateString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x14003cc98  mov     ebx, eax
0x14003cc9a  test    eax, eax
0x14003cc9c  jns     short loc_14003CCB8
0x14003cc9e  mov     edx, 104h; void *
0x14003cca3  mov     rcx, [rbp+18h]; this
0x14003cca7  mov     r9d, ebx; char *
0x14003ccaa  lea     r8, aCW1SSrcClientL_21; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003ccb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003ccb6  jmp     short loc_14003CCBB
0x14003ccb8  mov     ebx, r14d
0x14003ccbb  mov     rcx, [rbp+var_38]; string
0x14003ccbf  call    cs:__imp_WindowsDeleteString
0x14003ccc5  mov     [rbp+var_38], r14
0x14003ccc9  mov     rcx, [rbp+var_28]
0x14003cccd  test    rcx, rcx
0x14003ccd0  jz      short loc_14003CCE3
0x14003ccd2  mov     [rbp+var_28], r14
0x14003ccd6  mov     rax, [rcx]
0x14003ccd9  mov     rax, [rax+10h]
0x14003ccdd  call    _guard_dispatch_icall
0x14003cce2  nop
0x14003cce3  mov     rcx, [rbp+var_30]
0x14003cce7  test    rcx, rcx
0x14003ccea  jz      short loc_14003CCFD
0x14003ccec  mov     [rbp+var_30], r14
0x14003ccf0  mov     rax, [rcx]
0x14003ccf3  mov     rax, [rax+10h]
0x14003ccf7  call    _guard_dispatch_icall
0x14003ccfc  nop
0x14003ccfd  mov     rcx, [rbp+var_20]
0x14003cd01  test    rcx, rcx
0x14003cd04  jz      short loc_14003CD17
0x14003cd06  mov     [rbp+var_20], r14
0x14003cd0a  mov     rax, [rcx]
0x14003cd0d  mov     rax, [rax+10h]
0x14003cd11  call    _guard_dispatch_icall
0x14003cd16  nop
0x14003cd17  mov     rcx, [rbp+var_18]
0x14003cd1b  test    rcx, rcx
0x14003cd1e  jz      short loc_14003CD31
0x14003cd20  mov     [rbp+var_18], r14
0x14003cd24  mov     rdx, [rcx]
0x14003cd27  mov     rax, [rdx+10h]
0x14003cd2b  call    _guard_dispatch_icall
0x14003cd30  nop
0x14003cd31  jmp     short loc_14003CD5D
0x14003cd33  lea     rcx, OutputString
0x14003cd3a  call    ??$DuplicateString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x14003cd3f  mov     ebx, eax
0x14003cd41  test    eax, eax
0x14003cd43  jns     short loc_14003CD61
0x14003cd45  mov     rcx, [rbp+18h]; this
0x14003cd49  mov     r9d, eax; char *
0x14003cd4c  lea     r8, aCW1SSrcClientL_21; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003cd53  mov     edx, 0E6h; void *
0x14003cd58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003cd5d  mov     eax, ebx
0x14003cd5f  jmp     short loc_14003CD63
0x14003cd61  xor     eax, eax
0x14003cd63  mov     rcx, [rbp+var_8]
0x14003cd67  xor     rcx, rsp; StackCookie
0x14003cd6a  call    __security_check_cookie
0x14003cd6f  lea     r11, [rsp+80h+var_s0]
0x14003cd77  mov     rbx, [r11+30h]
0x14003cd7b  mov     rsi, [r11+38h]
0x14003cd7f  mov     rsp, r11
0x14003cd82  pop     r14
0x14003cd84  pop     rdi
0x14003cd85  pop     rbp
0x14003cd86  retn
0x14003cd87  mov     ecx, eax; this
0x14003cd89  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x14003cd8e  nop
0x14003cd8f  mov     ecx, eax; this
0x14003cd91  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
