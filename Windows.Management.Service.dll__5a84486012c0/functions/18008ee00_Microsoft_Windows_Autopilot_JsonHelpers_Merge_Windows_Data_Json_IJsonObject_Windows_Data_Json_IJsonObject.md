# Microsoft::Windows::Autopilot::JsonHelpers::Merge(Windows::Data::Json::IJsonObject *,Windows::Data::Json::IJsonObject *)

- ea: `0x18008ee00`
- end: `0x18008f062`
- name: `?Merge@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@0@Z`
- size: `610`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonObject *, struct Windows::Data::Json::IJsonObject *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180191634`

## callees

- `0x180067008`
- `0x180067a54`
- `0x1800868d4`
- `0x18008df68`
- `0x18008e380`
- `0x18008ee00`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008ef13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008efa0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f005`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008ef13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008efa0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f005`

## string_xrefs

- `0x18008ee3f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18008ee88`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18008efd2`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18008eff0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18008f018`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`

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
0x18008ee00  push    rbp
0x18008ee02  push    rbx
0x18008ee03  push    rsi
0x18008ee04  push    rdi
0x18008ee05  push    r14
0x18008ee07  mov     rbp, rsp
0x18008ee0a  sub     rsp, 40h
0x18008ee0e  mov     rsi, rcx
0x18008ee11  mov     [rbp+var_8], rdx
0x18008ee15  lea     rcx, [rbp+var_8]
0x18008ee19  call    ?InternalAddRef@?$ComPtr@U?$IAsyncOperationCompletedHandler@PEAUIDiscoveryUrlRequestInfo@Core@Autopilot@ModernDeployment@@@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<ModernDeployment::Autopilot::Core::IDiscoveryUrlRequestInfo *>>::InternalAddRef(void)
0x18008ee1e  xor     r14d, r14d
0x18008ee21  mov     [rbp+var_10], r14
0x18008ee25  lea     rdx, [rbp+var_10]
0x18008ee29  lea     rcx, [rbp+var_8]
0x18008ee2d  call    ??$As@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *>>>)
0x18008ee32  mov     ebx, eax
0x18008ee34  test    eax, eax
0x18008ee36  jns     short loc_18008EE54
0x18008ee38  mov     rcx, [rbp+28h]; this
0x18008ee3c  mov     r9d, eax; char *
0x18008ee3f  lea     r8, aOnecoreuapAdmi_113; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008ee46  lea     edx, [r14+6Eh]; void *
0x18008ee4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008ee4f  jmp     loc_18008F043
0x18008ee54  mov     [rbp+arg_18], r14
0x18008ee58  mov     rdi, [rbp+var_10]
0x18008ee5c  mov     rax, [rdi]
0x18008ee5f  mov     rbx, [rax+30h]
0x18008ee63  lea     rcx, [rbp+arg_18]
0x18008ee67  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008ee6c  lea     rdx, [rbp+arg_18]
0x18008ee70  mov     rcx, rdi
0x18008ee73  mov     rax, rbx
0x18008ee76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ee7b  mov     ebx, eax
0x18008ee7d  test    eax, eax
0x18008ee7f  jns     short loc_18008EEA7
0x18008ee81  mov     rcx, [rbp+28h]; this
0x18008ee85  mov     r9d, eax; char *
0x18008ee88  lea     r8, aOnecoreuapAdmi_113; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008ee8f  mov     edx, 72h ; 'r'; void *
0x18008ee94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008ee99  lea     rcx, [rbp+arg_18]
0x18008ee9d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008eea2  jmp     loc_18008F043
0x18008eea7  mov     [rbp+arg_8], 1
0x18008eeab  mov     rcx, [rbp+arg_18]
0x18008eeaf  mov     rax, [rcx]
0x18008eeb2  lea     rdx, [rbp+arg_8]
0x18008eeb6  mov     rax, [rax+38h]
0x18008eeba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008eebf  test    eax, eax
0x18008eec1  js      loc_18008F037
0x18008eec7  cmp     [rbp+arg_8], r14b
0x18008eecb  jz      loc_18008F037
0x18008eed1  mov     [rbp+var_20], r14
0x18008eed5  mov     rdi, [rbp+arg_18]
0x18008eed9  mov     rax, [rdi]
0x18008eedc  mov     rbx, [rax+30h]
0x18008eee0  lea     rcx, [rbp+var_20]
0x18008eee4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008eee9  lea     rdx, [rbp+var_20]
0x18008eeed  mov     rcx, rdi
0x18008eef0  mov     rax, rbx
0x18008eef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008eef8  mov     ebx, eax
0x18008eefa  test    eax, eax
0x18008eefc  js      loc_18008F011
0x18008ef02  mov     [rbp+string], r14
0x18008ef06  mov     rdi, [rbp+var_20]
0x18008ef0a  mov     rax, [rdi]
0x18008ef0d  mov     rbx, [rax+30h]
0x18008ef11  xor     ecx, ecx; string
0x18008ef13  call    cs:__imp_WindowsDeleteString
0x18008ef19  mov     [rbp+string], r14
0x18008ef1d  lea     rdx, [rbp+string]
0x18008ef21  mov     rcx, rdi
0x18008ef24  mov     rax, rbx
0x18008ef27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ef2c  mov     ebx, eax
0x18008ef2e  test    eax, eax
0x18008ef30  js      loc_18008EFE9
0x18008ef36  mov     [rbp+var_18], r14
0x18008ef3a  mov     rdi, [rbp+var_20]
0x18008ef3e  mov     rax, [rdi]
0x18008ef41  mov     rbx, [rax+38h]
0x18008ef45  lea     rcx, [rbp+var_18]
0x18008ef49  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008ef4e  lea     rdx, [rbp+var_18]
0x18008ef52  mov     rcx, rdi
0x18008ef55  mov     rax, rbx
0x18008ef58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ef5d  mov     ebx, eax
0x18008ef5f  test    eax, eax
0x18008ef61  js      short loc_18008EFC6
0x18008ef63  mov     r8, [rbp+var_18]; struct Windows::Data::Json::IJsonValue *
0x18008ef67  mov     rdx, [rbp+string]; HSTRING
0x18008ef6b  mov     rcx, rsi; struct Windows::Data::Json::IJsonObject *
0x18008ef6e  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEAUHSTRING__@@PEAUIJsonValue@673@@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,HSTRING__ *,Windows::Data::Json::IJsonValue *)
0x18008ef73  mov     ebx, eax
0x18008ef75  test    eax, eax
0x18008ef77  js      short loc_18008EFBF
0x18008ef79  mov     rcx, [rbp+arg_18]
0x18008ef7d  mov     rax, [rcx]
0x18008ef80  lea     rdx, [rbp+arg_8]
0x18008ef84  mov     rax, [rax+40h]
0x18008ef88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ef8d  mov     ebx, eax
0x18008ef8f  test    eax, eax
0x18008ef91  js      short loc_18008EFB8
0x18008ef93  lea     rcx, [rbp+var_18]
0x18008ef97  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008ef9c  mov     rcx, [rbp+string]; string
0x18008efa0  call    cs:__imp_WindowsDeleteString
0x18008efa6  mov     [rbp+string], r14
0x18008efaa  lea     rcx, [rbp+var_20]
0x18008efae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008efb3  jmp     loc_18008EEAB
0x18008efb8  mov     edx, 82h
0x18008efbd  jmp     short loc_18008EFCB
0x18008efbf  mov     edx, 80h
0x18008efc4  jmp     short loc_18008EFCB
0x18008efc6  mov     edx, 7Eh ; '~'; void *
0x18008efcb  mov     rcx, [rbp+28h]; this
0x18008efcf  mov     r9d, eax; char *
0x18008efd2  lea     r8, aOnecoreuapAdmi_113; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008efd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008efde  lea     rcx, [rbp+var_18]
0x18008efe2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008efe7  jmp     short loc_18008F001
0x18008efe9  mov     rcx, [rbp+28h]; this
0x18008efed  mov     r9d, eax; char *
0x18008eff0  lea     r8, aOnecoreuapAdmi_113; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008eff7  mov     edx, 7Bh ; '{'; void *
0x18008effc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008f001  mov     rcx, [rbp+string]; string
0x18008f005  call    cs:__imp_WindowsDeleteString
0x18008f00b  mov     [rbp+string], r14
0x18008f00f  jmp     short loc_18008F029
0x18008f011  mov     rcx, [rbp+28h]; this
0x18008f015  mov     r9d, eax; char *
0x18008f018  lea     r8, aOnecoreuapAdmi_113; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008f01f  mov     edx, 78h ; 'x'; void *
0x18008f024  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008f029  lea     rcx, [rbp+var_20]
0x18008f02d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008f032  jmp     loc_18008EE99
0x18008f037  lea     rcx, [rbp+arg_18]
0x18008f03b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008f040  mov     ebx, r14d
0x18008f043  lea     rcx, [rbp+var_10]
0x18008f047  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008f04c  lea     rcx, [rbp+var_8]
0x18008f050  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008f055  mov     eax, ebx
0x18008f057  add     rsp, 40h
0x18008f05b  pop     r14
0x18008f05d  pop     rdi
0x18008f05e  pop     rsi
0x18008f05f  pop     rbx
0x18008f060  pop     rbp
0x18008f061  retn
```
