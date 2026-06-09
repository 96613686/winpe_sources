# LaunchExePrivilegedAction::InitializeSuccessResultHint(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray> const &)

- ea: `0x18003fb20`
- end: `0x18003fd5a`
- name: `?InitializeSuccessResultHint@LaunchExePrivilegedAction@@IEAAJAEBV?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@Z`
- size: `570`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003f790`

## callees

- `0x18000abc4`
- `0x18001055c`
- `0x18001208c`
- `0x1800127d4`
- `0x18002407c`
- `0x180024e20`
- `0x1800337fc`
- `0x1800338a8`
- `0x18003f6cc`
- `0x18003fb20`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fcea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fcea`

## string_xrefs

- `0x18003fb8c`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\launchexeprivilegedaction.cpp`
- `0x18003fc92`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\launchexeprivilegedaction.cpp`
- `0x18003fcc7`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\launchexeprivilegedaction.cpp`
- `0x18003fd2e`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\launchexeprivilegedaction.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall LaunchExePrivilegedAction::InitializeSuccessResultHint(
        __int64 a1,
        __int64 (__fastcall ****a2)(_QWORD, GUID *, __int64))
{
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // r8
  const char *v9; // r9
  unsigned __int64 v10; // rdx
  char *v11; // rsi
  unsigned int i; // r14d
  unsigned int v13; // eax
  __int64 (__fastcall ***v14)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v15)(_QWORD, GUID *, __int64); // rbx
  int inited; // eax
  __int64 v17; // rdx
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rdx
  void *v21; // rcx
  LPVOID pv; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int16 *v23[3]; // [rsp+28h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  unsigned int v25; // [rsp+88h] [rbp+48h] BYREF
  __int64 v26; // [rsp+90h] [rbp+50h] BYREF
  __int64 v27; // [rsp+98h] [rbp+58h] BYREF

  if ( !*a2 )
    return 0;
  v27 = 0;
  v5 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
         a2,
         (__int64)&v27);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 131;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\launchexeprivilegedaction.cpp",
      (const char *)(unsigned int)v5,
      (int)pv);
    goto LABEL_28;
  }
  v25 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v27 + 56LL))(v27, &v25);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 134;
    goto LABEL_7;
  }
  wil::make_unique_cotaskmem_nothrow<_SUCCESS_RESULT_HINT [0]>(&pv, v25, v8, v9);
  v11 = (char *)pv;
  if ( pv )
  {
    for ( i = 0; ; ++i )
    {
      v13 = v25;
      if ( i >= v25 )
        break;
      v26 = 0;
      v14 = *a2;
      v15 = (**a2)[6];
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
      inited = v15(v14, (GUID *)i, (__int64)&v26);
      v6 = inited;
      if ( inited < 0 )
      {
        v20 = 143;
        goto LABEL_21;
      }
      inited = JsonUtils::InitLongFromJson(&v26, v17, &v11[204 * i]);
      v6 = inited;
      if ( inited < 0 )
      {
        v20 = 146;
LABEL_21:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\launchexeprivilegedaction.cpp",
          (const char *)(unsigned int)inited,
          (int)pv);
        goto LABEL_22;
      }
      memset(v23, 0, sizeof(v23));
      v18 = JsonUtils::InitStringFromJson(&v26, L"Definition", v23);
      v6 = v18;
      if ( v18 < 0 )
      {
        v19 = 150;
LABEL_17:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v19,
          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\launchexeprivilegedaction.cpp",
          (const char *)(unsigned int)v18,
          (int)pv);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v23);
LABEL_22:
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
        if ( v11 )
          CoTaskMemFree(v11);
        goto LABEL_28;
      }
      v18 = StringCchCopyW((unsigned __int16 *)&v11[204 * i + 4], 0x64u, v23[0]);
      v6 = v18;
      if ( v18 < 0 )
      {
        v19 = 151;
        goto LABEL_17;
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v23);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
    }
    v21 = *(void **)(a1 + 168);
    *(_QWORD *)(a1 + 168) = v11;
    if ( v21 )
    {
      operator delete(v21, v10);
      v13 = v25;
    }
    *(_DWORD *)(a1 + 176) = v13;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v27);
    return 0;
  }
  v6 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x89,
    (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\launchexeprivilegedaction.cpp",
    (const char *)0x8007000ELL,
    0);
LABEL_28:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v27);
  return v6;
}

```

## disassembly

```asm
0x18003fb20  push    rbp
0x18003fb22  push    rbx
0x18003fb23  push    rsi
0x18003fb24  push    rdi
0x18003fb25  push    r12
0x18003fb27  push    r14
0x18003fb29  push    r15
0x18003fb2b  mov     rbp, rsp
0x18003fb2e  sub     rsp, 40h
0x18003fb32  mov     r12, rdx
0x18003fb35  mov     r15, rcx
0x18003fb38  cmp     qword ptr [rdx], 0
0x18003fb3c  jnz     short loc_18003FB45
0x18003fb3e  xor     eax, eax
0x18003fb40  jmp     loc_18003FD4B
0x18003fb45  mov     [rbp+arg_18], 0
0x18003fb4d  lea     rdx, [rbp+arg_18]
0x18003fb51  mov     rcx, r12
0x18003fb54  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x18003fb59  mov     ebx, eax
0x18003fb5b  test    eax, eax
0x18003fb5d  jns     short loc_18003FB66
0x18003fb5f  mov     edx, 83h
0x18003fb64  jmp     short loc_18003FB8C
0x18003fb66  mov     [rbp+arg_8], 0
0x18003fb6d  mov     rcx, [rbp+arg_18]
0x18003fb71  mov     rax, [rcx]
0x18003fb74  lea     rdx, [rbp+arg_8]
0x18003fb78  mov     rax, [rax+38h]
0x18003fb7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fb81  mov     ebx, eax
0x18003fb83  test    eax, eax
0x18003fb85  jns     short loc_18003FBA4
0x18003fb87  mov     edx, 86h; void *
0x18003fb8c  lea     r8, aOnecoreBaseDia_11; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003fb93  mov     r9d, eax; char *
0x18003fb96  mov     rcx, [rbp+38h]; this
0x18003fb9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fb9f  jmp     loc_18003FD40
0x18003fba4  mov     edx, [rbp+arg_8]
0x18003fba7  lea     rcx, [rbp+pv]
0x18003fbab  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@U_SUCCESS_RESULT_HINT@@@wil@@YA?AV?$unique_ptr@$$BY0A@U_SUCCESS_RESULT_HINT@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<_SUCCESS_RESULT_HINT [0]>(unsigned __int64)
0x18003fbb0  nop
0x18003fbb1  mov     rsi, [rbp+pv]
0x18003fbb5  test    rsi, rsi
0x18003fbb8  jz      loc_18003FD22
0x18003fbbe  xor     r14d, r14d
0x18003fbc1  mov     eax, [rbp+arg_8]
0x18003fbc4  cmp     r14d, eax
0x18003fbc7  jnb     loc_18003FCF2
0x18003fbcd  mov     [rbp+arg_10], 0
0x18003fbd5  mov     rdi, [r12]
0x18003fbd9  mov     rax, [rdi]
0x18003fbdc  mov     rbx, [rax+30h]
0x18003fbe0  lea     rcx, [rbp+arg_10]
0x18003fbe4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003fbe9  lea     r8, [rbp+arg_10]
0x18003fbed  mov     edx, r14d
0x18003fbf0  mov     rcx, rdi
0x18003fbf3  mov     rax, rbx
0x18003fbf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fbfb  mov     ebx, eax
0x18003fbfd  test    eax, eax
0x18003fbff  js      loc_18003FCBF
0x18003fc05  mov     eax, r14d
0x18003fc08  imul    rdi, rax, 0CCh
0x18003fc0f  add     rdi, rsi
0x18003fc12  mov     r8, rdi
0x18003fc15  lea     rcx, [rbp+arg_10]
0x18003fc19  call    ?InitLongFromJson@JsonUtils@@SAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGAEAJ@Z; JsonUtils::InitLongFromJson(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &,ushort const *,long &)
0x18003fc1e  mov     ebx, eax
0x18003fc20  test    eax, eax
0x18003fc22  js      loc_18003FCB8
0x18003fc28  mov     [rbp+var_18], 0
0x18003fc30  mov     [rbp+var_10], 0
0x18003fc38  mov     [rbp+var_8], 0
0x18003fc40  lea     r8, [rbp+var_18]
0x18003fc44  lea     rdx, aDefinition; "Definition"
0x18003fc4b  lea     rcx, [rbp+arg_10]
0x18003fc4f  call    ?InitStringFromJson@JsonUtils@@SAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; JsonUtils::InitStringFromJson(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &,ushort const *,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x18003fc54  mov     ebx, eax
0x18003fc56  test    eax, eax
0x18003fc58  js      short loc_18003FCB1
0x18003fc5a  lea     rcx, [rdi+4]; unsigned __int16 *
0x18003fc5e  mov     r8, [rbp+var_18]; unsigned __int16 *
0x18003fc62  mov     edx, 64h ; 'd'; unsigned __int64
0x18003fc67  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003fc6c  mov     ebx, eax
0x18003fc6e  test    eax, eax
0x18003fc70  js      short loc_18003FC8D
0x18003fc72  lea     rcx, [rbp+var_18]
0x18003fc76  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003fc7b  nop
0x18003fc7c  lea     rcx, [rbp+arg_10]
0x18003fc80  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003fc85  inc     r14d
0x18003fc88  jmp     loc_18003FBC1
0x18003fc8d  mov     edx, 97h; void *
0x18003fc92  lea     r8, aOnecoreBaseDia_11; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003fc99  mov     r9d, eax; char *
0x18003fc9c  mov     rcx, [rbp+38h]; this
0x18003fca0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fca5  nop
0x18003fca6  lea     rcx, [rbp+var_18]
0x18003fcaa  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003fcaf  jmp     short loc_18003FCD8
0x18003fcb1  mov     edx, 96h
0x18003fcb6  jmp     short loc_18003FC92
0x18003fcb8  mov     edx, 92h
0x18003fcbd  jmp     short loc_18003FCC4
0x18003fcbf  mov     edx, 8Fh; void *
0x18003fcc4  mov     r9d, eax; char *
0x18003fcc7  lea     r8, aOnecoreBaseDia_11; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003fcce  mov     rcx, [rbp+38h]; this
0x18003fcd2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fcd7  nop
0x18003fcd8  lea     rcx, [rbp+arg_10]
0x18003fcdc  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003fce1  nop
0x18003fce2  test    rsi, rsi
0x18003fce5  jz      short loc_18003FD40
0x18003fce7  mov     rcx, rsi; pv
0x18003fcea  call    cs:__imp_CoTaskMemFree
0x18003fcf0  jmp     short loc_18003FD40
0x18003fcf2  mov     rcx, [r15+0A8h]; void *
0x18003fcf9  mov     [r15+0A8h], rsi
0x18003fd00  test    rcx, rcx
0x18003fd03  jz      short loc_18003FD0D
0x18003fd05  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003fd0a  mov     eax, [rbp+arg_8]
0x18003fd0d  mov     [r15+0B0h], eax
0x18003fd14  lea     rcx, [rbp+arg_18]
0x18003fd18  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003fd1d  jmp     loc_18003FB3E
0x18003fd22  mov     rcx, [rbp+38h]; this
0x18003fd26  mov     ebx, 8007000Eh
0x18003fd2b  mov     r9d, ebx; char *
0x18003fd2e  lea     r8, aOnecoreBaseDia_11; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003fd35  mov     edx, 89h; void *
0x18003fd3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fd3f  nop
0x18003fd40  lea     rcx, [rbp+arg_18]
0x18003fd44  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003fd49  mov     eax, ebx
0x18003fd4b  add     rsp, 40h
0x18003fd4f  pop     r15
0x18003fd51  pop     r14
0x18003fd53  pop     r12
0x18003fd55  pop     rdi
0x18003fd56  pop     rsi
0x18003fd57  pop     rbx
0x18003fd58  pop     rbp
0x18003fd59  retn
```
