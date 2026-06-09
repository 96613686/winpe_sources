# ServiceDrivenActionJsonDescriptor::DetermineAndInitializeAction(IServiceDrivenAction * *,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,Microsoft::WRL::ComPtr<ActionContext>)

- ea: `0x180038890`
- end: `0x180038b43`
- name: `?DetermineAndInitializeAction@ServiceDrivenActionJsonDescriptor@@MEAAJPEAPEAUIServiceDrivenAction@@AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@V?$ComPtr@VActionContext@@@78@@Z`
- size: `691`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003f320`

## callees

- `0x18001055c`
- `0x18001208c`
- `0x180024e70`
- `0x1800253bc`
- `0x18002a488`
- `0x18002a588`
- `0x180036fb8`
- `0x180037128`
- `0x1800372b4`
- `0x1800373f8`
- `0x180038890`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800388ff`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180038966`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800389ca`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180038a43`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800388ff`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180038966`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800389ca`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180038a43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180038a86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180038a86`

## string_xrefs

- `0x18003895f`: `Privileged`
- `0x180038b09`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\servicedrivenactionjsondescriptor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ServiceDrivenActionJsonDescriptor::DetermineAndInitializeAction(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 *a4,
        __int64 *a5)
{
  __int64 v8; // rdx
  const WCHAR *v9; // rcx
  int v10; // eax
  __int64 v11; // rdx
  const WCHAR *v12; // rcx
  __int64 v13; // rdx
  const WCHAR *v14; // rcx
  unsigned int v15; // edi
  __int64 v16; // rdx
  const WCHAR *v17; // rcx
  PCWSTR StringRawBuffer; // rax
  int bIgnoreCase; // [rsp+20h] [rbp-30h]
  HSTRING string; // [rsp+30h] [rbp-20h] BYREF
  __int64 v22; // [rsp+38h] [rbp-18h] BYREF
  _QWORD v23[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  int v25; // [rsp+90h] [rbp+40h] BYREF
  __int64 *v26; // [rsp+98h] [rbp+48h]

  v26 = a4;
  v8 = *(_QWORD *)(a3 + 8);
  if ( v8 != -1 )
  {
    v9 = *(const WCHAR **)a3;
    if ( *(_QWORD *)a3 )
      goto LABEL_9;
    goto LABEL_8;
  }
  if ( !*(_QWORD *)a3 )
  {
    LODWORD(v8) = 0;
LABEL_8:
    v9 = &String1;
    goto LABEL_9;
  }
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)(*(_QWORD *)a3 + 2 * v8) );
  v9 = *(const WCHAR **)a3;
LABEL_9:
  if ( CompareStringOrdinal(v9, v8, L"FileOperation", -1, 1) == 2 )
  {
    v10 = Microsoft::WRL::Details::MakeAndInitialize<FileOperationServiceDrivenAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::ComPtr<ActionContext> &>(
            a2,
            (__int64)a4,
            a5);
    goto LABEL_31;
  }
  v11 = *(_QWORD *)(a3 + 8);
  if ( v11 != -1 )
  {
    v12 = *(const WCHAR **)a3;
    if ( *(_QWORD *)a3 )
      goto LABEL_19;
    goto LABEL_18;
  }
  if ( !*(_QWORD *)a3 )
  {
    LODWORD(v11) = 0;
LABEL_18:
    v12 = &String1;
    goto LABEL_19;
  }
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(*(_QWORD *)a3 + 2 * v11) );
  v12 = *(const WCHAR **)a3;
LABEL_19:
  if ( CompareStringOrdinal(v12, v11, L"Privileged", -1, 1) == 2 )
  {
    v10 = Microsoft::WRL::Details::MakeAndInitialize<PrivilegedAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::ComPtr<ActionContext> &>(
            a2,
            (__int64)a4,
            a5);
    goto LABEL_31;
  }
  v13 = *(_QWORD *)(a3 + 8);
  if ( v13 != -1 )
  {
    v14 = *(const WCHAR **)a3;
    if ( *(_QWORD *)a3 )
      goto LABEL_29;
    goto LABEL_28;
  }
  if ( !*(_QWORD *)a3 )
  {
    LODWORD(v13) = 0;
LABEL_28:
    v14 = &String1;
    goto LABEL_29;
  }
  v13 = -1;
  do
    ++v13;
  while ( *(_WORD *)(*(_QWORD *)a3 + 2 * v13) );
  v14 = *(const WCHAR **)a3;
LABEL_29:
  if ( CompareStringOrdinal(v14, v13, L"Toast", -1, 1) == 2 )
  {
    v10 = Microsoft::WRL::Details::MakeAndInitialize<ToastAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::ComPtr<ActionContext> &>(
            a2,
            (__int64)a4,
            a5);
LABEL_31:
    v15 = v10;
    v25 = v10;
    if ( v10 >= 0 )
      goto LABEL_47;
    goto LABEL_42;
  }
  v16 = *(_QWORD *)(a3 + 8);
  if ( v16 == -1 )
  {
    if ( *(_QWORD *)a3 )
    {
      v16 = -1;
      do
        ++v16;
      while ( *(_WORD *)(*(_QWORD *)a3 + 2 * v16) );
      v17 = *(const WCHAR **)a3;
      goto LABEL_41;
    }
    LODWORD(v16) = 0;
    goto LABEL_40;
  }
  v17 = *(const WCHAR **)a3;
  if ( !*(_QWORD *)a3 )
LABEL_40:
    v17 = &String1;
LABEL_41:
  v15 = -2135164403;
  v25 = -2135164403;
  CompareStringOrdinal(v17, v16, L"LaunchExeV2", -1, 1);
LABEL_42:
  v22 = 0;
  if ( (int)Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(
              (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))a4,
              (__int64)&v22) >= 0 )
  {
    string = 0;
    if ( (*(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v22 + 56LL))(v22, &string) >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v23[0] = -2147483646;
      MitigationRegUtils::SetMitigationRegString(v23, 1, L"LastFailedAction", StringRawBuffer, 0);
    }
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
  }
  v23[0] = -2147483646;
  bIgnoreCase = 0;
  MitigationRegUtils::SetMitigationRegDWORD(v23, 1, L"LastFailedActionHr", v15);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
LABEL_47:
  if ( v15 + 2135164404 <= 1 )
    v15 = Microsoft::WRL::Details::MakeAndInitialize<UnsupportedClientAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,long &>(
            a2,
            a4,
            &v25);
  if ( (v15 & 0x80000000) != 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE4,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\servicedrivenactionjsondescriptor.cpp",
      (const char *)v15,
      bIgnoreCase);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(a4);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(a5);
  return v15;
}

```

## disassembly

```asm
0x180038890  mov     [rsp-28h+arg_0], rbx
0x180038895  mov     [rsp-28h+arg_18], r9
0x18003889a  push    rbp
0x18003889b  push    rsi
0x18003889c  push    rdi
0x18003889d  push    r12
0x18003889f  push    r15
0x1800388a1  mov     rbp, rsp
0x1800388a4  sub     rsp, 50h
0x1800388a8  mov     rsi, r9
0x1800388ab  mov     rdi, r8
0x1800388ae  mov     r15, rdx
0x1800388b1  mov     rdx, [r8+8]; cchCount1
0x1800388b5  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800388b9  xor     ebx, ebx
0x1800388bb  cmp     rdx, r12
0x1800388be  jnz     short loc_1800388DE
0x1800388c0  mov     rax, [r8]
0x1800388c3  test    rax, rax
0x1800388c6  jz      short loc_1800388D9
0x1800388c8  mov     rdx, r12
0x1800388cb  inc     rdx
0x1800388ce  cmp     [rax+rdx*2], bx
0x1800388d2  jnz     short loc_1800388CB
0x1800388d4  mov     rcx, rax
0x1800388d7  jmp     short loc_1800388ED
0x1800388d9  mov     rdx, rbx
0x1800388dc  jmp     short loc_1800388E6
0x1800388de  mov     rcx, [r8]
0x1800388e1  test    rcx, rcx
0x1800388e4  jnz     short loc_1800388ED
0x1800388e6  lea     rcx, String1; lpString1
0x1800388ed  mov     [rsp+50h+bIgnoreCase], 1; bIgnoreCase
0x1800388f5  mov     r9d, r12d; cchCount2
0x1800388f8  lea     r8, aFileoperation; "FileOperation"
0x1800388ff  call    cs:__imp_CompareStringOrdinal
0x180038905  cmp     eax, 2
0x180038908  jnz     short loc_18003891E
0x18003890a  mov     r8, [rbp+arg_20]
0x18003890e  mov     rdx, rsi
0x180038911  mov     rcx, r15
0x180038914  call    ??$MakeAndInitialize@VFileOperationServiceDrivenAction@@UIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@AEAV?$ComPtr@VActionContext@@@45@@Details@WRL@Microsoft@@YAJPEAPEAUIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@12@AEAV?$ComPtr@VActionContext@@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<FileOperationServiceDrivenAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::ComPtr<ActionContext> &>(IServiceDrivenAction * *,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::ComPtr<ActionContext> &)
0x180038919  jmp     loc_1800389E4
0x18003891e  mov     rdx, [rdi+8]; cchCount1
0x180038922  cmp     rdx, r12
0x180038925  jnz     short loc_180038945
0x180038927  mov     rax, [rdi]
0x18003892a  test    rax, rax
0x18003892d  jz      short loc_180038940
0x18003892f  mov     rdx, r12
0x180038932  inc     rdx
0x180038935  cmp     [rax+rdx*2], bx
0x180038939  jnz     short loc_180038932
0x18003893b  mov     rcx, rax
0x18003893e  jmp     short loc_180038954
0x180038940  mov     rdx, rbx
0x180038943  jmp     short loc_18003894D
0x180038945  mov     rcx, [rdi]
0x180038948  test    rcx, rcx
0x18003894b  jnz     short loc_180038954
0x18003894d  lea     rcx, String1; lpString1
0x180038954  mov     [rsp+50h+bIgnoreCase], 1; bIgnoreCase
0x18003895c  mov     r9d, r12d; cchCount2
0x18003895f  lea     r8, String2; "Privileged"
0x180038966  call    cs:__imp_CompareStringOrdinal
0x18003896c  cmp     eax, 2
0x18003896f  jnz     short loc_180038982
0x180038971  mov     r8, [rbp+arg_20]
0x180038975  mov     rdx, rsi
0x180038978  mov     rcx, r15
0x18003897b  call    ??$MakeAndInitialize@VPrivilegedAction@@UIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@AEAV?$ComPtr@VActionContext@@@45@@Details@WRL@Microsoft@@YAJPEAPEAUIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@12@AEAV?$ComPtr@VActionContext@@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<PrivilegedAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::ComPtr<ActionContext> &>(IServiceDrivenAction * *,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::ComPtr<ActionContext> &)
0x180038980  jmp     short loc_1800389E4
0x180038982  mov     rdx, [rdi+8]; cchCount1
0x180038986  cmp     rdx, r12
0x180038989  jnz     short loc_1800389A9
0x18003898b  mov     rax, [rdi]
0x18003898e  test    rax, rax
0x180038991  jz      short loc_1800389A4
0x180038993  mov     rdx, r12
0x180038996  inc     rdx
0x180038999  cmp     [rax+rdx*2], bx
0x18003899d  jnz     short loc_180038996
0x18003899f  mov     rcx, rax
0x1800389a2  jmp     short loc_1800389B8
0x1800389a4  mov     rdx, rbx
0x1800389a7  jmp     short loc_1800389B1
0x1800389a9  mov     rcx, [rdi]
0x1800389ac  test    rcx, rcx
0x1800389af  jnz     short loc_1800389B8
0x1800389b1  lea     rcx, String1; lpString1
0x1800389b8  mov     [rsp+50h+bIgnoreCase], 1; bIgnoreCase
0x1800389c0  mov     r9d, r12d; cchCount2
0x1800389c3  lea     r8, aToast; "Toast"
0x1800389ca  call    cs:__imp_CompareStringOrdinal
0x1800389d0  cmp     eax, 2
0x1800389d3  jnz     short loc_1800389F3
0x1800389d5  mov     r8, [rbp+arg_20]
0x1800389d9  mov     rdx, rsi
0x1800389dc  mov     rcx, r15
0x1800389df  call    ??$MakeAndInitialize@VToastAction@@UIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@AEAV?$ComPtr@VActionContext@@@45@@Details@WRL@Microsoft@@YAJPEAPEAUIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@12@AEAV?$ComPtr@VActionContext@@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<ToastAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::ComPtr<ActionContext> &>(IServiceDrivenAction * *,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::WRL::ComPtr<ActionContext> &)
0x1800389e4  mov     edi, eax
0x1800389e6  mov     [rbp+arg_10], eax
0x1800389e9  test    eax, eax
0x1800389eb  jns     loc_180038AE2
0x1800389f1  jmp     short loc_180038A49
0x1800389f3  mov     rdx, [rdi+8]; cchCount1
0x1800389f7  cmp     rdx, r12
0x1800389fa  jnz     short loc_180038A1A
0x1800389fc  mov     rax, [rdi]
0x1800389ff  test    rax, rax
0x180038a02  jz      short loc_180038A15
0x180038a04  mov     rdx, r12
0x180038a07  inc     rdx
0x180038a0a  cmp     [rax+rdx*2], bx
0x180038a0e  jnz     short loc_180038A07
0x180038a10  mov     rcx, rax
0x180038a13  jmp     short loc_180038A29
0x180038a15  mov     rdx, rbx
0x180038a18  jmp     short loc_180038A22
0x180038a1a  mov     rcx, [rdi]
0x180038a1d  test    rcx, rcx
0x180038a20  jnz     short loc_180038A29
0x180038a22  lea     rcx, String1; lpString1
0x180038a29  mov     edi, 80BBFA0Dh
0x180038a2e  mov     [rbp+arg_10], edi
0x180038a31  mov     [rsp+50h+bIgnoreCase], 1; bIgnoreCase
0x180038a39  mov     r9d, r12d; cchCount2
0x180038a3c  lea     r8, aLaunchexev2; "LaunchExeV2"
0x180038a43  call    cs:__imp_CompareStringOrdinal
0x180038a49  mov     [rbp+var_18], rbx
0x180038a4d  lea     rdx, [rbp+var_18]
0x180038a51  mov     rcx, rsi
0x180038a54  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x180038a59  mov     r12, 0FFFFFFFF80000002h
0x180038a60  test    eax, eax
0x180038a62  js      short loc_180038AB7
0x180038a64  mov     [rbp+string], rbx
0x180038a68  mov     rcx, [rbp+var_18]
0x180038a6c  mov     rax, [rcx]
0x180038a6f  lea     rdx, [rbp+string]
0x180038a73  mov     rax, [rax+38h]
0x180038a77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038a7c  test    eax, eax
0x180038a7e  js      short loc_180038AAE
0x180038a80  xor     edx, edx; length
0x180038a82  mov     rcx, [rbp+string]; string
0x180038a86  call    cs:__imp_WindowsGetStringRawBuffer
0x180038a8c  mov     [rbp+var_10], r12
0x180038a90  mov     qword ptr [rsp+50h+bIgnoreCase], rbx
0x180038a95  mov     r9, rax
0x180038a98  lea     r8, aLastfailedacti_0; "LastFailedAction"
0x180038a9f  mov     edx, 1
0x180038aa4  lea     rcx, [rbp+var_10]
0x180038aa8  call    ?SetMitigationRegString@MitigationRegUtils@@SAJAEBQEAUHKEY__@@W4MitigationRegistryKey@@PEBG22@Z; MitigationRegUtils::SetMitigationRegString(HKEY__ * const &,MitigationRegistryKey,ushort const *,ushort const *,ushort const *)
0x180038aad  nop
0x180038aae  lea     rcx, [rbp+string]; this
0x180038ab2  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180038ab7  mov     [rbp+var_10], r12
0x180038abb  mov     qword ptr [rsp+50h+bIgnoreCase], rbx; int
0x180038ac0  mov     r9d, edi
0x180038ac3  lea     r8, aLastfailedacti; "LastFailedActionHr"
0x180038aca  mov     edx, 1
0x180038acf  lea     rcx, [rbp+var_10]
0x180038ad3  call    ?SetMitigationRegDWORD@MitigationRegUtils@@SAJAEBQEAUHKEY__@@W4MitigationRegistryKey@@PEBGK2@Z; MitigationRegUtils::SetMitigationRegDWORD(HKEY__ * const &,MitigationRegistryKey,ushort const *,ulong,ushort const *)
0x180038ad8  nop
0x180038ad9  lea     rcx, [rbp+var_18]
0x180038add  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180038ae2  lea     eax, [rdi+7F4405F4h]
0x180038ae8  cmp     eax, 1
0x180038aeb  ja      short loc_180038AFE
0x180038aed  lea     r8, [rbp+arg_10]
0x180038af1  mov     rdx, rsi
0x180038af4  mov     rcx, r15
0x180038af7  call    ??$MakeAndInitialize@VUnsupportedClientAction@@UIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@AEAJ@Details@WRL@Microsoft@@YAJPEAPEAUIServiceDrivenAction@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@12@AEAJ@Z; Microsoft::WRL::Details::MakeAndInitialize<UnsupportedClientAction,IServiceDrivenAction,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,long &>(IServiceDrivenAction * *,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,long &)
0x180038afc  mov     edi, eax
0x180038afe  test    edi, edi
0x180038b00  jns     short loc_180038B1B
0x180038b02  mov     rcx, [rbp+28h]; this
0x180038b06  mov     r9d, edi; char *
0x180038b09  lea     r8, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180038b10  mov     edx, 0E4h; void *
0x180038b15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038b1a  nop
0x180038b1b  mov     rcx, rsi
0x180038b1e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180038b23  nop
0x180038b24  mov     rcx, [rbp+arg_20]
0x180038b28  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180038b2d  mov     eax, edi
0x180038b2f  mov     rbx, [rsp+50h+arg_0]
0x180038b37  add     rsp, 50h
0x180038b3b  pop     r15
0x180038b3d  pop     r12
0x180038b3f  pop     rdi
0x180038b40  pop     rsi
0x180038b41  pop     rbp
0x180038b42  retn
```
