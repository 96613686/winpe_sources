# Microsoft::Windows::Autopilot::JsonHelpers::Merge(Windows::Data::Json::IJsonObject *,Windows::Data::Json::IJsonObject *)

- ea: `0x18008ff44`
- end: `0x1800901b9`
- name: `?Merge@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@0@Z`
- size: `629`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonObject *, struct Windows::Data::Json::IJsonObject *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180196618`

## callees

- `0x180067398`
- `0x180067e54`
- `0x180087634`
- `0x18008f080`
- `0x18008f4b4`
- `0x18008ff44`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090057`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800900ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090155`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090057`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800900ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090155`

## string_xrefs

- `0x18008ff83`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18008ffcc`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x180090122`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x180090140`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18009016e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::JsonHelpers::Merge(
        struct Windows::Data::Json::IJsonObject *a1,
        struct Windows::Data::Json::IJsonObject *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, __int64 *); // rbx
  int v7; // eax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, struct Windows::Data::Json::IJsonValue **); // rbx
  int v16; // eax
  __int64 v17; // rdx
  __int64 v19; // [rsp+20h] [rbp-20h] BYREF
  struct Windows::Data::Json::IJsonValue *v20; // [rsp+28h] [rbp-18h] BYREF
  __int64 v21; // [rsp+30h] [rbp-10h] BYREF
  struct Windows::Data::Json::IJsonObject *v22; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  char v24; // [rsp+78h] [rbp+38h] BYREF
  HSTRING string; // [rsp+80h] [rbp+40h] BYREF
  __int64 v26; // [rsp+88h] [rbp+48h] BYREF

  v22 = a2;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<ModernDeployment::Autopilot::Core::IDiscoveryUrlRequestInfo *>>::InternalAddRef(&v22);
  v21 = 0;
  v3 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *>>(
         &v22,
         &v21);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v26 = 0;
    v5 = v21;
    v6 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
    v7 = v6(v5, &v26);
    v4 = v7;
    if ( v7 >= 0 )
    {
      v24 = 1;
      while ( (*(int (__fastcall **)(__int64, char *))(*(_QWORD *)v26 + 56LL))(v26, &v24) >= 0 && v24 )
      {
        v19 = 0;
        v8 = v26;
        v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
        v10 = v9(v8, &v19);
        v4 = v10;
        if ( v10 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x78,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
            (const char *)(unsigned int)v10,
            v19);
          goto LABEL_22;
        }
        string = 0;
        v11 = v19;
        v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 48LL);
        WindowsDeleteString(0);
        string = 0;
        v13 = v12(v11, &string);
        v4 = v13;
        if ( v13 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7B,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
            (const char *)(unsigned int)v13,
            v19);
          goto LABEL_20;
        }
        v20 = 0;
        v14 = v19;
        v15 = *(__int64 (__fastcall **)(__int64, struct Windows::Data::Json::IJsonValue **))(*(_QWORD *)v19 + 56LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
        v16 = v15(v14, &v20);
        v4 = v16;
        if ( v16 < 0 )
        {
          v17 = 126;
LABEL_18:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v17,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
            (const char *)(unsigned int)v16,
            v19);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
LABEL_20:
          WindowsDeleteString(string);
          string = 0;
LABEL_22:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
          goto LABEL_5;
        }
        v16 = Microsoft::Windows::Autopilot::JsonHelpers::Append(a1, string, v20);
        v4 = v16;
        if ( v16 < 0 )
        {
          v17 = 128;
          goto LABEL_18;
        }
        v16 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v26 + 64LL))(v26, &v24);
        v4 = v16;
        if ( v16 < 0 )
        {
          v17 = 130;
          goto LABEL_18;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
      v4 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x72,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
        (const char *)(unsigned int)v7,
        v19);
LABEL_5:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6E,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)(unsigned int)v3,
      v19);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  return v4;
}

```

## disassembly

```asm
0x18008ff44  push    rbp
0x18008ff46  push    rbx
0x18008ff47  push    rsi
0x18008ff48  push    rdi
0x18008ff49  push    r14
0x18008ff4b  mov     rbp, rsp
0x18008ff4e  sub     rsp, 40h
0x18008ff52  mov     rsi, rcx
0x18008ff55  mov     [rbp+var_8], rdx
0x18008ff59  lea     rcx, [rbp+var_8]
0x18008ff5d  call    ?InternalAddRef@?$ComPtr@U?$IAsyncOperationCompletedHandler@PEAUIDiscoveryUrlRequestInfo@Core@Autopilot@ModernDeployment@@@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<ModernDeployment::Autopilot::Core::IDiscoveryUrlRequestInfo *>>::InternalAddRef(void)
0x18008ff62  xor     r14d, r14d
0x18008ff65  mov     [rbp+var_10], r14
0x18008ff69  lea     rdx, [rbp+var_10]
0x18008ff6d  lea     rcx, [rbp+var_8]
0x18008ff71  call    ??$As@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *>>>)
0x18008ff76  mov     ebx, eax
0x18008ff78  test    eax, eax
0x18008ff7a  jns     short loc_18008FF98
0x18008ff7c  mov     rcx, [rbp+28h]; this
0x18008ff80  mov     r9d, eax; char *
0x18008ff83  lea     r8, aOnecoreuapAdmi_113; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008ff8a  lea     edx, [r14+6Eh]; void *
0x18008ff8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008ff93  jmp     loc_180090199
0x18008ff98  mov     [rbp+arg_18], r14
0x18008ff9c  mov     rdi, [rbp+var_10]
0x18008ffa0  mov     rax, [rdi]
0x18008ffa3  mov     rbx, [rax+30h]
0x18008ffa7  lea     rcx, [rbp+arg_18]
0x18008ffab  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008ffb0  lea     rdx, [rbp+arg_18]
0x18008ffb4  mov     rcx, rdi
0x18008ffb7  mov     rax, rbx
0x18008ffba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ffbf  mov     ebx, eax
0x18008ffc1  test    eax, eax
0x18008ffc3  jns     short loc_18008FFEB
0x18008ffc5  mov     rcx, [rbp+28h]; this
0x18008ffc9  mov     r9d, eax; char *
0x18008ffcc  lea     r8, aOnecoreuapAdmi_113; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008ffd3  mov     edx, 72h ; 'r'; void *
0x18008ffd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008ffdd  lea     rcx, [rbp+arg_18]
0x18008ffe1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008ffe6  jmp     loc_180090199
0x18008ffeb  mov     [rbp+arg_8], 1
0x18008ffef  mov     rcx, [rbp+arg_18]
0x18008fff3  mov     rax, [rcx]
0x18008fff6  lea     rdx, [rbp+arg_8]
0x18008fffa  mov     rax, [rax+38h]
0x18008fffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090003  test    eax, eax
0x180090005  js      loc_18009018D
0x18009000b  cmp     [rbp+arg_8], r14b
0x18009000f  jz      loc_18009018D
0x180090015  mov     [rbp+var_20], r14
0x180090019  mov     rdi, [rbp+arg_18]
0x18009001d  mov     rax, [rdi]
0x180090020  mov     rbx, [rax+30h]
0x180090024  lea     rcx, [rbp+var_20]
0x180090028  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009002d  lea     rdx, [rbp+var_20]
0x180090031  mov     rcx, rdi
0x180090034  mov     rax, rbx
0x180090037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009003c  mov     ebx, eax
0x18009003e  test    eax, eax
0x180090040  js      loc_180090167
0x180090046  mov     [rbp+string], r14
0x18009004a  mov     rdi, [rbp+var_20]
0x18009004e  mov     rax, [rdi]
0x180090051  mov     rbx, [rax+30h]
0x180090055  xor     ecx, ecx; string
0x180090057  call    cs:__imp_WindowsDeleteString
0x18009005e  nop     dword ptr [rax+rax+00h]
0x180090063  mov     [rbp+string], r14
0x180090067  lea     rdx, [rbp+string]
0x18009006b  mov     rcx, rdi
0x18009006e  mov     rax, rbx
0x180090071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090076  mov     ebx, eax
0x180090078  test    eax, eax
0x18009007a  js      loc_180090139
0x180090080  mov     [rbp+var_18], r14
0x180090084  mov     rdi, [rbp+var_20]
0x180090088  mov     rax, [rdi]
0x18009008b  mov     rbx, [rax+38h]
0x18009008f  lea     rcx, [rbp+var_18]
0x180090093  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180090098  lea     rdx, [rbp+var_18]
0x18009009c  mov     rcx, rdi
0x18009009f  mov     rax, rbx
0x1800900a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800900a7  mov     ebx, eax
0x1800900a9  test    eax, eax
0x1800900ab  js      short loc_180090116
0x1800900ad  mov     r8, [rbp+var_18]; struct Windows::Data::Json::IJsonValue *
0x1800900b1  mov     rdx, [rbp+string]; HSTRING
0x1800900b5  mov     rcx, rsi; struct Windows::Data::Json::IJsonObject *
0x1800900b8  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEAUHSTRING__@@PEAUIJsonValue@673@@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,HSTRING__ *,Windows::Data::Json::IJsonValue *)
0x1800900bd  mov     ebx, eax
0x1800900bf  test    eax, eax
0x1800900c1  js      short loc_18009010F
0x1800900c3  mov     rcx, [rbp+arg_18]
0x1800900c7  mov     rax, [rcx]
0x1800900ca  lea     rdx, [rbp+arg_8]
0x1800900ce  mov     rax, [rax+40h]
0x1800900d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800900d7  mov     ebx, eax
0x1800900d9  test    eax, eax
0x1800900db  js      short loc_180090108
0x1800900dd  lea     rcx, [rbp+var_18]
0x1800900e1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800900e6  mov     rcx, [rbp+string]; string
0x1800900ea  call    cs:__imp_WindowsDeleteString
0x1800900f1  nop     dword ptr [rax+rax+00h]
0x1800900f6  mov     [rbp+string], r14
0x1800900fa  lea     rcx, [rbp+var_20]
0x1800900fe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180090103  jmp     loc_18008FFEF
0x180090108  mov     edx, 82h
0x18009010d  jmp     short loc_18009011B
0x18009010f  mov     edx, 80h
0x180090114  jmp     short loc_18009011B
0x180090116  mov     edx, 7Eh ; '~'; void *
0x18009011b  mov     rcx, [rbp+28h]; this
0x18009011f  mov     r9d, eax; char *
0x180090122  lea     r8, aOnecoreuapAdmi_113; "onecoreuap\\admin\\moderndeployment\\au"...
0x180090129  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009012e  lea     rcx, [rbp+var_18]
0x180090132  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180090137  jmp     short loc_180090151
0x180090139  mov     rcx, [rbp+28h]; this
0x18009013d  mov     r9d, eax; char *
0x180090140  lea     r8, aOnecoreuapAdmi_113; "onecoreuap\\admin\\moderndeployment\\au"...
0x180090147  mov     edx, 7Bh ; '{'; void *
0x18009014c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180090151  mov     rcx, [rbp+string]; string
0x180090155  call    cs:__imp_WindowsDeleteString
0x18009015c  nop     dword ptr [rax+rax+00h]
0x180090161  mov     [rbp+string], r14
0x180090165  jmp     short loc_18009017F
0x180090167  mov     rcx, [rbp+28h]; this
0x18009016b  mov     r9d, eax; char *
0x18009016e  lea     r8, aOnecoreuapAdmi_113; "onecoreuap\\admin\\moderndeployment\\au"...
0x180090175  mov     edx, 78h ; 'x'; void *
0x18009017a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009017f  lea     rcx, [rbp+var_20]
0x180090183  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180090188  jmp     loc_18008FFDD
0x18009018d  lea     rcx, [rbp+arg_18]
0x180090191  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180090196  mov     ebx, r14d
0x180090199  lea     rcx, [rbp+var_10]
0x18009019d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800901a2  lea     rcx, [rbp+var_8]
0x1800901a6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800901ab  mov     eax, ebx
0x1800901ad  add     rsp, 40h
0x1800901b1  pop     r14
0x1800901b3  pop     rdi
0x1800901b4  pop     rsi
0x1800901b5  pop     rbx
0x1800901b6  pop     rbp
0x1800901b7  retn
```
