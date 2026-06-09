# SessionDataUtil::GetDeploymentSessionInfoOverride

- ea: `0x18005c2f0`
- end: `0x18005c5f9`
- name: `SessionDataUtil::GetDeploymentSessionInfoOverride`
- size: `777`
- prototype: `__int64 __fastcall(SessionDataUtil *this, LPCWCH lpWideCharStr)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005e764`

## callees

- `0x180003180`
- `0x180007b6c`
- `0x18000dce4`
- `0x1800259b8`
- `0x180027948`
- `0x18004c04c`
- `0x18004c16c`
- `0x18005bb6c`
- `0x18005c2f0`
- `0x18005f1b4`
- `0x180061960`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005c44a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005c481`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005c44a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005c481`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005c458`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005c48f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005c458`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005c48f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005c4eb`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005c4eb`
- `OLEAUT32!__imp_SysStringLen` at `0x18005c46d`
- `OLEAUT32!__imp_SysStringLen` at `0x18005c46d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005c4ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005c4ce`

## string_xrefs

- `0x18005c4c7`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall SessionDataUtil::GetDeploymentSessionInfoOverride(
        const WCHAR *this,
        LPCWCH lpWideCharStr,
        _QWORD *a3)
{
  int v6; // eax
  CHAR *v7; // rcx
  CHAR *v8; // rbx
  int v9; // eax
  wchar_t **v10; // r9
  void *v11; // rcx
  void *v12; // rdi
  int ExtendedSessionData; // eax
  void *v14; // rsi
  HANDLE ProcessHeap; // rax
  UINT v16; // eax
  HANDLE v17; // rax
  HRESULT v18; // eax
  int v19; // edx
  unsigned int v20; // r8d
  unsigned int v21; // edi
  __int64 v22; // rbx
  int (__fastcall *v23)(__int64, _QWORD, JsonUtil **); // rdi
  __int64 v24; // rax
  struct ABI::Windows::Data::Json::IJsonObject **v25; // r9
  int NamedObject; // eax
  __int64 v27; // rbx
  __int64 v28; // rdx
  wchar_t v29[4]; // [rsp+20h] [rbp-60h] BYREF
  LPCCH lpMultiByteStr; // [rsp+28h] [rbp-58h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-50h] BYREF
  HSTRING string; // [rsp+48h] [rbp-38h] BYREF
  LPCWCH v33; // [rsp+50h] [rbp-30h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-28h] BYREF
  JsonUtil *v35; // [rsp+60h] [rbp-20h] BYREF
  __int64 v36; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v33 = lpWideCharStr;
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
      (const char *)0x80004003LL,
      *(int *)v29);
    return 2147500035LL;
  }
  *a3 = 0;
  if ( !this || !*this || !lpWideCharStr || !*lpWideCharStr )
    return 0;
  lpMultiByteStr = 0;
  v6 = ConvertWideToAnsi_Alloc(lpWideCharStr, (char **)&lpMultiByteStr);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xA7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
      (const char *)(unsigned int)v6,
      *(int *)v29);
    v7 = (CHAR *)lpMultiByteStr;
    if ( !lpMultiByteStr )
      return 0;
LABEL_9:
    SusFree(v7);
    return 0;
  }
  *(_QWORD *)v29 = 0;
  v8 = (CHAR *)lpMultiByteStr;
  v9 = ConvertAnsiToWide_Alloc(lpMultiByteStr, (wchar_t **)v29);
  if ( v9 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xAD,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
      (const char *)(unsigned int)v9,
      *(int *)v29);
    v11 = *(void **)v29;
    if ( !*(_QWORD *)v29 )
    {
LABEL_14:
      if ( !v8 )
        return 0;
      v7 = v8;
      goto LABEL_9;
    }
LABEL_13:
    SusFree(v11);
    goto LABEL_14;
  }
  lpMem = 0;
  v12 = *(void **)v29;
  ExtendedSessionData = SessionDataUtil::ExtractExtendedSessionData(
                          this,
                          *(const wchar_t **)v29,
                          (wchar_t *)&lpMem,
                          v10);
  if ( ExtendedSessionData < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xB3,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
      (const char *)(unsigned int)ExtendedSessionData,
      *(int *)v29);
    v14 = lpMem;
LABEL_18:
    if ( v14 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v14);
    }
    if ( !v12 )
      goto LABEL_14;
    v11 = v12;
    goto LABEL_13;
  }
  v16 = SysStringLen((BSTR)lpMem);
  v14 = lpMem;
  if ( !v16 )
    goto LABEL_18;
  if ( lpMem )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v14);
  }
  if ( v12 )
    SusFree(v12);
  if ( v8 )
    SusFree(v8);
  v36 = 0;
  string = 0;
  v18 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v18 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v18, v19, v20);
    JUMPOUT(0x18005C5F8LL);
  }
  if ( (int)RoGetActivationFactory(string, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v36) >= 0 )
  {
    v35 = 0;
    v22 = v36;
    v23 = *(int (__fastcall **)(__int64, _QWORD, JsonUtil **))(*(_QWORD *)v36 + 48LL);
    v35 = 0;
    v24 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v33);
    if ( v23(v22, *(_QWORD *)(v24 + 24), &v35) < 0 )
    {
      v21 = 0;
LABEL_43:
      if ( v35 )
        (*(void (__fastcall **)(JsonUtil *))(*(_QWORD *)v35 + 16LL))(v35);
      goto LABEL_45;
    }
    *(_QWORD *)v29 = 0;
    NamedObject = JsonUtil::GetNamedObject(
                    v35,
                    (struct ABI::Windows::Data::Json::IJsonObject *)L"DeploymentSessionInfo",
                    v29,
                    v25);
    v21 = NamedObject;
    v27 = *(_QWORD *)v29;
    if ( NamedObject >= 0 )
    {
      if ( !*(_QWORD *)v29
        || (NamedObject = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *))v29)(
                            *(_QWORD *)v29,
                            &GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3,
                            a3),
            v21 = NamedObject,
            NamedObject >= 0) )
      {
        v21 = 0;
LABEL_41:
        if ( v27 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        goto LABEL_43;
      }
      v28 = 217;
    }
    else
    {
      v28 = 213;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
      (const char *)(unsigned int)NamedObject,
      *(int *)v29);
    goto LABEL_41;
  }
  v21 = 0;
LABEL_45:
  if ( v36 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  return v21;
}

```

## disassembly

```asm
0x18005c2f0  mov     [rsp-28h+arg_18], rbx
0x18005c2f5  push    rbp
0x18005c2f6  push    rsi
0x18005c2f7  push    rdi
0x18005c2f8  push    r14
0x18005c2fa  push    r15
0x18005c2fc  mov     rbp, rsp
0x18005c2ff  sub     rsp, 80h
0x18005c306  mov     rax, cs:__security_cookie
0x18005c30d  xor     rax, rsp
0x18005c310  mov     [rbp+var_10], rax
0x18005c314  mov     r14, r8
0x18005c317  mov     rax, rdx
0x18005c31a  mov     rsi, rcx
0x18005c31d  mov     [rbp+var_30], rdx
0x18005c321  xor     r15d, r15d
0x18005c324  test    r8, r8
0x18005c327  jnz     short loc_18005C34A
0x18005c329  mov     rcx, [rbp+28h]; this
0x18005c32d  mov     ebx, 80004003h
0x18005c332  mov     r9d, ebx; char *
0x18005c335  lea     r8, aCW1SSrcClientL_14; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005c33c  mov     edx, 0C4h; void *
0x18005c341  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c346  mov     eax, ebx
0x18005c348  jmp     short loc_18005C3A0
0x18005c34a  mov     [r8], r15
0x18005c34d  test    rsi, rsi
0x18005c350  jz      short loc_18005C39E
0x18005c352  cmp     [rcx], r15w
0x18005c356  jz      short loc_18005C39E
0x18005c358  test    rax, rax
0x18005c35b  jz      short loc_18005C39E
0x18005c35d  cmp     [rdx], r15w
0x18005c361  jz      short loc_18005C39E
0x18005c363  mov     [rbp+lpMultiByteStr], r15
0x18005c367  lea     rdx, [rbp+lpMultiByteStr]; char **
0x18005c36b  mov     rcx, rax; lpWideCharStr
0x18005c36e  call    ?ConvertWideToAnsi_Alloc@@YAJPEB_WPEAPEAD@Z; ConvertWideToAnsi_Alloc(wchar_t const *,char * *)
0x18005c373  mov     rcx, [rbp+28h]; this
0x18005c377  test    eax, eax
0x18005c379  jns     short loc_18005C3C3
0x18005c37b  mov     r9d, eax; char *
0x18005c37e  lea     r8, aCW1SSrcClientL_14; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005c385  mov     edx, 0A7h; void *
0x18005c38a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005c38f  nop
0x18005c390  mov     rcx, [rbp+lpMultiByteStr]; lpMem
0x18005c394  test    rcx, rcx
0x18005c397  jz      short loc_18005C39E
0x18005c399  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18005c39e  xor     eax, eax
0x18005c3a0  mov     rcx, [rbp+var_10]
0x18005c3a4  xor     rcx, rsp; StackCookie
0x18005c3a7  call    __security_check_cookie
0x18005c3ac  mov     rbx, [rsp+80h+arg_18]
0x18005c3b4  add     rsp, 80h
0x18005c3bb  pop     r15
0x18005c3bd  pop     r14
0x18005c3bf  pop     rdi
0x18005c3c0  pop     rsi
0x18005c3c1  pop     rbp
0x18005c3c2  retn
0x18005c3c3  mov     qword ptr [rbp+var_60], r15
0x18005c3c7  lea     rdx, [rbp+var_60]; wchar_t **
0x18005c3cb  mov     rbx, [rbp+lpMultiByteStr]
0x18005c3cf  mov     rcx, rbx; lpMultiByteStr
0x18005c3d2  call    ?ConvertAnsiToWide_Alloc@@YAJPEBDPEAPEA_W@Z; ConvertAnsiToWide_Alloc(char const *,wchar_t * *)
0x18005c3d7  mov     rcx, [rbp+28h]; this
0x18005c3db  test    eax, eax
0x18005c3dd  jns     short loc_18005C40D
0x18005c3df  mov     r9d, eax; char *
0x18005c3e2  lea     r8, aCW1SSrcClientL_14; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005c3e9  mov     edx, 0ADh; void *
0x18005c3ee  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005c3f3  nop
0x18005c3f4  mov     rcx, qword ptr [rbp+var_60]; lpMem
0x18005c3f8  test    rcx, rcx
0x18005c3fb  jz      short loc_18005C403
0x18005c3fd  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18005c402  nop
0x18005c403  test    rbx, rbx
0x18005c406  jz      short loc_18005C39E
0x18005c408  mov     rcx, rbx
0x18005c40b  jmp     short loc_18005C399
0x18005c40d  mov     [rbp+lpMem], r15
0x18005c411  lea     r8, [rbp+lpMem]; wchar_t *
0x18005c415  mov     rdi, qword ptr [rbp+var_60]
0x18005c419  mov     rdx, rdi; wchar_t *
0x18005c41c  mov     rcx, rsi; this
0x18005c41f  call    ?ExtractExtendedSessionData@SessionDataUtil@@YAJPEB_W0PEAPEA_W@Z; SessionDataUtil::ExtractExtendedSessionData(wchar_t const *,wchar_t const *,wchar_t * *)
0x18005c424  mov     rcx, [rbp+28h]; this
0x18005c428  test    eax, eax
0x18005c42a  jns     short loc_18005C469
0x18005c42c  mov     r9d, eax; char *
0x18005c42f  lea     r8, aCW1SSrcClientL_14; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005c436  mov     edx, 0B3h; void *
0x18005c43b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005c440  nop
0x18005c441  mov     rsi, [rbp+lpMem]
0x18005c445  test    rsi, rsi
0x18005c448  jz      short loc_18005C45F
0x18005c44a  call    cs:__imp_GetProcessHeap
0x18005c450  mov     rcx, rax; hHeap
0x18005c453  mov     r8, rsi; lpMem
0x18005c456  xor     edx, edx; dwFlags
0x18005c458  call    cs:__imp_HeapFree
0x18005c45e  nop
0x18005c45f  test    rdi, rdi
0x18005c462  jz      short loc_18005C403
0x18005c464  mov     rcx, rdi
0x18005c467  jmp     short loc_18005C3FD
0x18005c469  mov     rcx, [rbp+lpMem]; pbstr
0x18005c46d  call    cs:__imp_SysStringLen
0x18005c473  nop
0x18005c474  mov     rsi, [rbp+lpMem]
0x18005c478  test    eax, eax
0x18005c47a  jz      short loc_18005C445
0x18005c47c  test    rsi, rsi
0x18005c47f  jz      short loc_18005C496
0x18005c481  call    cs:__imp_GetProcessHeap
0x18005c487  mov     rcx, rax; hHeap
0x18005c48a  mov     r8, rsi; lpMem
0x18005c48d  xor     edx, edx; dwFlags
0x18005c48f  call    cs:__imp_HeapFree
0x18005c495  nop
0x18005c496  test    rdi, rdi
0x18005c499  jz      short loc_18005C4A4
0x18005c49b  mov     rcx, rdi; lpMem
0x18005c49e  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18005c4a3  nop
0x18005c4a4  test    rbx, rbx
0x18005c4a7  jz      short loc_18005C4B2
0x18005c4a9  mov     rcx, rbx; lpMem
0x18005c4ac  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18005c4b1  nop
0x18005c4b2  mov     [rbp+var_18], r15
0x18005c4b6  mov     [rbp+string], r15
0x18005c4ba  lea     r9, [rbp+string]; string
0x18005c4be  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18005c4c2  mov     edx, 1Ch; length
0x18005c4c7  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QB_WB; "Windows.Data.Json.JsonObject"
0x18005c4ce  call    cs:__imp_WindowsCreateStringReference
0x18005c4d4  test    eax, eax
0x18005c4d6  js      loc_18005C5F1
0x18005c4dc  lea     r8, [rbp+var_18]
0x18005c4e0  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x18005c4e7  mov     rcx, [rbp+string]
0x18005c4eb  call    cs:__imp_RoGetActivationFactory
0x18005c4f1  shr     eax, 1Fh
0x18005c4f4  test    al, al
0x18005c4f6  jz      short loc_18005C500
0x18005c4f8  mov     edi, r15d
0x18005c4fb  jmp     loc_18005C5D4
0x18005c500  mov     [rbp+var_20], r15
0x18005c504  mov     rbx, [rbp+var_18]
0x18005c508  mov     rax, [rbx]
0x18005c50b  mov     rdi, [rax+30h]
0x18005c50f  mov     [rbp+var_20], r15
0x18005c513  lea     rdx, [rbp+var_30]
0x18005c517  lea     rcx, [rbp+hstringHeader]
0x18005c51b  call    ??$?0PEA_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEA_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t * const &,Microsoft::WRL::Details::Dummy)
0x18005c520  nop
0x18005c521  lea     r8, [rbp+var_20]
0x18005c525  mov     rdx, [rax+18h]
0x18005c529  mov     rcx, rbx
0x18005c52c  mov     rax, rdi
0x18005c52f  call    _guard_dispatch_icall
0x18005c534  shr     eax, 1Fh
0x18005c537  test    al, al
0x18005c539  jz      short loc_18005C540
0x18005c53b  mov     edi, r15d
0x18005c53e  jmp     short loc_18005C5BE
0x18005c540  mov     qword ptr [rbp+var_60], r15
0x18005c544  lea     r8, [rbp+var_60]; wchar_t *
0x18005c548  lea     rdx, aDeploymentsess; "DeploymentSessionInfo"
0x18005c54f  mov     rcx, [rbp+var_20]; this
0x18005c553  call    ?GetNamedObject@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WPEAPEAU23456@@Z; JsonUtil::GetNamedObject(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,ABI::Windows::Data::Json::IJsonObject * *)
0x18005c558  mov     edi, eax
0x18005c55a  mov     rbx, qword ptr [rbp+var_60]
0x18005c55e  test    eax, eax
0x18005c560  jns     short loc_18005C569
0x18005c562  mov     edx, 0D5h
0x18005c567  jmp     short loc_18005C591
0x18005c569  test    rbx, rbx
0x18005c56c  jz      short loc_18005C5A6
0x18005c56e  mov     rax, [rbx]
0x18005c571  mov     r8, r14
0x18005c574  lea     rdx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3
0x18005c57b  mov     rcx, rbx
0x18005c57e  mov     rax, [rax]
0x18005c581  call    _guard_dispatch_icall
0x18005c586  mov     edi, eax
0x18005c588  test    eax, eax
0x18005c58a  jns     short loc_18005C5A6
0x18005c58c  mov     edx, 0D9h; void *
0x18005c591  lea     r8, aCW1SSrcClientL_14; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005c598  mov     r9d, eax; char *
0x18005c59b  mov     rcx, [rbp+28h]; this
0x18005c59f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c5a4  jmp     short loc_18005C5A9
0x18005c5a6  mov     edi, r15d
0x18005c5a9  test    rbx, rbx
0x18005c5ac  jz      short loc_18005C5BE
0x18005c5ae  mov     rax, [rbx]
0x18005c5b1  mov     rcx, rbx
0x18005c5b4  mov     rax, [rax+10h]
0x18005c5b8  call    _guard_dispatch_icall
0x18005c5bd  nop
0x18005c5be  mov     rcx, [rbp+var_20]
0x18005c5c2  test    rcx, rcx
0x18005c5c5  jz      short loc_18005C5D4
0x18005c5c7  mov     rax, [rcx]
0x18005c5ca  mov     rax, [rax+10h]
0x18005c5ce  call    _guard_dispatch_icall
0x18005c5d3  nop
0x18005c5d4  mov     rcx, [rbp+var_18]
0x18005c5d8  test    rcx, rcx
0x18005c5db  jz      short loc_18005C5EA
0x18005c5dd  mov     rdx, [rcx]
0x18005c5e0  mov     rax, [rdx+10h]
0x18005c5e4  call    _guard_dispatch_icall
0x18005c5e9  nop
0x18005c5ea  mov     eax, edi
0x18005c5ec  jmp     loc_18005C3A0
0x18005c5f1  mov     ecx, eax; this
0x18005c5f3  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
