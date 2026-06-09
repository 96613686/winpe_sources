# LegacySystemLanguagePackResourceProvider::_DownloadPackage(Microsoft::WRL::ComPtr<IUpdateCollection> const &,std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>> const &,std::vector<Microsoft::WRL::ComPtr<ICbsCapability>,std::allocator<Microsoft::WRL::ComPtr<ICbsCapability>>> const &,std::function<void (uint,LanguagePackInstallProgressState,unsigned __int64,unsigned __int64)> const &,bool)

- ea: `0x1800487d4`
- end: `0x180048b94`
- name: `?_DownloadPackage@LegacySystemLanguagePackResourceProvider@@AEBAXAEBV?$ComPtr@UIUpdateCollection@@@WRL@Microsoft@@AEBV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@AEBV?$vector@V?$ComPtr@UICbsCapability@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UICbsCapability@@@WRL@Microsoft@@@std@@@6@AEBV?$function@$$A6AXIW4LanguagePackInstallProgressState@@_K1@Z@6@_N@Z`
- size: `960`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180045570`

## callees

- `0x180003a00`
- `0x180012a98`
- `0x180035ce4`
- `0x180043cb8`
- `0x180046280`
- `0x180046330`
- `0x180046450`
- `0x180048274`
- `0x1800487d4`
- `0x180049b88`
- `0x18006a010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18004884b`
- `OLEAUT32!__imp_VariantInit` at `0x18004884b`
- `OLEAUT32!__imp_VariantClear` at `0x180048a76`
- `OLEAUT32!__imp_VariantClear` at `0x180048a76`

## string_xrefs

- `0x180048b03`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\raiiutils.h`
- `0x180048b1c`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\raiiutils.h`
- `0x180048a08`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x180048b31`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x180048b46`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x180048b5b`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x180048b74`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
HRESULT __fastcall LegacySystemLanguagePackResourceProvider::_DownloadPackage(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        __int64 a5,
        char a6)
{
  __int64 *v7; // rdi
  __int64 v8; // r14
  __int128 v9; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  int v11; // eax
  __int64 v12; // rbx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rbx
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  HRESULT result; // eax
  void **v25; // rcx
  __int64 *v26; // rcx
  int v27; // [rsp+28h] [rbp-B9h]
  __int64 v28; // [rsp+38h] [rbp-A9h] BYREF
  __int64 v29; // [rsp+40h] [rbp-A1h]
  _Mtx_t v30; // [rsp+48h] [rbp-99h]
  _QWORD v31[5]; // [rsp+50h] [rbp-91h] BYREF
  char *v32; // [rsp+78h] [rbp-69h] BYREF
  __int64 v33; // [rsp+80h] [rbp-61h] BYREF
  void **v34; // [rsp+88h] [rbp-59h] BYREF
  int v35; // [rsp+90h] [rbp-51h] BYREF
  __int64 v36; // [rsp+98h] [rbp-49h] BYREF
  int v37[2]; // [rsp+A0h] [rbp-41h] BYREF
  __int64 *v38; // [rsp+A8h] [rbp-39h] BYREF
  VARIANTARG pvarg; // [rsp+B0h] [rbp-31h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+130h] [rbp+4Fh]

  LODWORD(v32) = 0;
  LegacySystemLanguagePackResourceProvider::_CreateUpdateDownloader(a1, (unsigned int)&v38, a2, a3, a4, a6);
  Microsoft::WRL::Details::Make<CompletionCallback,>((CompletionCallback **)&v34);
  ProgressCallBackHolder<std::function<void (unsigned int,enum LanguagePackInstallProgressState,unsigned __int64,unsigned __int64)>>::SetProgressCallBack((_Mtx_t)(v34 + 6));
  VariantInit(&pvarg);
  *(_QWORD *)v37 = 0;
  v7 = v38;
  v8 = *v38;
  v9 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  v33 = 0;
  LODWORD(v32) = 4;
  v11 = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ISearchCompletedCallback,IDownloadCompletedCallback,IInstallationCompletedCallback,IDownloadProgressChangedCallback,IInstallationProgressChangedCallback>::QueryInterface(
          v34,
          &GUID_77254866_9f5b_4c8e_b9e2_c77a8530d64b,
          &v33);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE9,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\raiiutils.h",
      (const char *)(unsigned int)v11,
      v27);
  v12 = v33;
  v28 = 0;
  LODWORD(v32) = 12;
  v13 = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ISearchCompletedCallback,IDownloadCompletedCallback,IInstallationCompletedCallback,IDownloadProgressChangedCallback,IInstallationProgressChangedCallback>::QueryInterface(
          v34,
          &GUID_8c3f1cdd_6173_4591_aebd_a56a53ca77c1,
          &v28);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE9,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\raiiutils.h",
      (const char *)(unsigned int)v13,
      v27);
  *(_OWORD *)&v31[1] = v9;
  v31[3] = pRecInfo;
  v14 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, _QWORD *))(v8 + 120))(v7, v28, v12, &v31[1]);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2ED,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v14,
      (int)v37);
  LODWORD(v32) = 4;
  v15 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  v16 = v33;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  v17 = *(_QWORD *)v37;
  if ( *(_QWORD *)v37 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v37 + 8LL))(*(_QWORD *)v37);
  v28 = v17;
  LOBYTE(v29) = 1;
  CancellableWait(v34[27], *(void **)(a1 + 24), 0x1B7740u);
  LOBYTE(v29) = 0;
  v36 = 0;
  v18 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(*v38 + 136))(v38, *(_QWORD *)v37, &v36);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2FF,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v18,
      (int)v37);
  v35 = 0;
  v19 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v36 + 64LL))(v36, &v35);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x302,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v19,
      (int)v37);
  if ( v35 != 2 )
  {
    v33 = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v36 + 72LL))(v36, 0, &v33);
    if ( v20 >= 0 )
    {
      LODWORD(v32) = 0;
      v21 = (*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v33 + 56LL))(v33, &v32);
      if ( v21 >= 0 )
      {
        if ( (int)v32 >= 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x310,
            (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
            (const char *)0x80240034LL,
            (int)v37);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x30C,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
          (const char *)(unsigned int)v32,
          (int)v37);
      }
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x30A,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
        (const char *)(unsigned int)v21,
        (int)v37);
    }
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x307,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v20,
      (int)v37);
  }
  v22 = v36;
  if ( v36 )
  {
    v36 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  v23 = *(_QWORD *)v37;
  if ( *(_QWORD *)v37 )
  {
    *(_QWORD *)v37 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  result = VariantClear(&pvarg);
  if ( v30 )
    result = ProgressCallBackHolder<std::function<void (unsigned int,enum LanguagePackInstallProgressState)>>::_ReleaseCallBack(v30);
  v25 = v34;
  if ( v34 )
  {
    v34 = 0;
    result = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppExtensions::AppExtension *> *>,Microsoft::WRL::FtmBase>::Release(v25);
  }
  v26 = v38;
  if ( v38 )
  {
    v38 = 0;
    return (*(__int64 (__fastcall **)(__int64 *))(*v26 + 16))(v26);
  }
  return result;
}

```

## disassembly

```asm
0x1800487d4  mov     rax, rsp
0x1800487d7  push    rbp
0x1800487d8  push    rbx
0x1800487d9  push    rsi
0x1800487da  push    rdi
0x1800487db  push    r14
0x1800487dd  push    r15
0x1800487df  lea     rbp, [rax-4Fh]
0x1800487e3  sub     rsp, 0F8h
0x1800487ea  movaps  xmmword ptr [rax-48h], xmm6
0x1800487ee  movaps  xmmword ptr [rax-58h], xmm7
0x1800487f2  mov     rax, cs:__security_cookie
0x1800487f9  xor     rax, rsp
0x1800487fc  mov     [rbp+47h+var_60], rax
0x180048800  mov     rsi, rcx
0x180048803  xor     r15d, r15d
0x180048806  mov     dword ptr [rbp+47h+var_B0], r15d
0x18004880a  mov     al, [rbp+47h+arg_28]
0x18004880d  mov     byte ptr [rsp+120h+var_F8], al
0x180048811  mov     qword ptr [rsp+120h+var_100], r9; int
0x180048816  mov     r9, r8
0x180048819  mov     r8, rdx
0x18004881c  lea     rdx, [rbp+47h+var_80]
0x180048820  call    ?_CreateUpdateDownloader@LegacySystemLanguagePackResourceProvider@@AEBA?AV?$ComPtr@UIUpdateDownloader@@@WRL@Microsoft@@AEBV?$ComPtr@UIUpdateCollection@@@34@AEBV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@AEBV?$vector@V?$ComPtr@UICbsCapability@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UICbsCapability@@@WRL@Microsoft@@@std@@@7@_N@Z; LegacySystemLanguagePackResourceProvider::_CreateUpdateDownloader(Microsoft::WRL::ComPtr<IUpdateCollection> const &,std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>> const &,std::vector<Microsoft::WRL::ComPtr<ICbsCapability>> const &,bool)
0x180048825  nop
0x180048826  lea     rcx, [rbp+47h+var_A0]
0x18004882a  call    ??$Make@VCompletionCallback@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCompletionCallback@@@12@XZ; Microsoft::WRL::Details::Make<CompletionCallback,>(void)
0x18004882f  nop
0x180048830  mov     rcx, [rbp+47h+var_A0]
0x180048834  add     rcx, 30h ; '0'; _Mtx_t
0x180048838  mov     r8, [rbp+47h+arg_20]
0x18004883c  lea     rdx, [rsp+120h+var_E0]
0x180048841  call    ?SetProgressCallBack@?$ProgressCallBackHolder@V?$function@$$A6AXIW4LanguagePackInstallProgressState@@_K1@Z@std@@@@QEAA@AEBV?$function@$$A6AXIW4LanguagePackInstallProgressState@@_K1@Z@std@@@Z; ProgressCallBackHolder<std::function<void (uint,LanguagePackInstallProgressState,unsigned __int64,unsigned __int64)>>::SetProgressCallBack(std::function<void (uint,LanguagePackInstallProgressState,unsigned __int64,unsigned __int64)> const &)
0x180048846  nop
0x180048847  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18004884b  call    cs:__imp_VariantInit
0x180048851  nop
0x180048852  mov     qword ptr [rbp+47h+var_88], r15
0x180048856  mov     rdi, [rbp+47h+var_80]
0x18004885a  mov     r14, [rdi]
0x18004885d  movups  xmm6, xmmword ptr [rbp+47h+pvarg]
0x180048861  movsd   xmm7, qword ptr [rbp+47h+pvarg+10h]
0x180048866  mov     [rbp+47h+var_A8], r15
0x18004886a  mov     dword ptr [rbp+47h+var_B0], 4
0x180048871  lea     r8, [rbp+47h+var_A8]
0x180048875  lea     rdx, _GUID_77254866_9f5b_4c8e_b9e2_c77a8530d64b
0x18004887c  mov     rcx, [rbp+47h+var_A0]
0x180048880  call    ?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UISearchCompletedCallback@@UIDownloadCompletedCallback@@UIInstallationCompletedCallback@@UIDownloadProgressChangedCallback@@UIInstallationProgressChangedCallback@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ISearchCompletedCallback,IDownloadCompletedCallback,IInstallationCompletedCallback,IDownloadProgressChangedCallback,IInstallationProgressChangedCallback>::QueryInterface(_GUID const &,void * *)
0x180048885  mov     rcx, [rbp+4Fh]; this
0x180048889  test    eax, eax
0x18004888b  js      loc_180048B00
0x180048891  mov     rbx, [rbp+47h+var_A8]
0x180048895  mov     [rsp+120h+var_F0], r15
0x18004889a  mov     dword ptr [rbp+47h+var_B0], 0Ch
0x1800488a1  lea     r8, [rsp+120h+var_F0]
0x1800488a6  lea     rdx, _GUID_8c3f1cdd_6173_4591_aebd_a56a53ca77c1
0x1800488ad  mov     rcx, [rbp+47h+var_A0]
0x1800488b1  call    ?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UISearchCompletedCallback@@UIDownloadCompletedCallback@@UIInstallationCompletedCallback@@UIDownloadProgressChangedCallback@@UIInstallationProgressChangedCallback@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ISearchCompletedCallback,IDownloadCompletedCallback,IInstallationCompletedCallback,IDownloadProgressChangedCallback,IInstallationProgressChangedCallback>::QueryInterface(_GUID const &,void * *)
0x1800488b6  test    eax, eax
0x1800488b8  js      loc_180048B15
0x1800488be  movaps  xmmword ptr [rsp+120h+var_D8+8], xmm6
0x1800488c3  movsd   [rbp+47h+var_C0], xmm7
0x1800488c8  lea     rax, [rbp+47h+var_88]
0x1800488cc  mov     qword ptr [rsp+120h+var_100], rax; int
0x1800488d1  lea     r9, [rsp+120h+var_D8+8]
0x1800488d6  mov     r8, rbx
0x1800488d9  mov     rdx, [rsp+120h+var_F0]
0x1800488de  mov     rcx, rdi
0x1800488e1  mov     rax, [r14+78h]
0x1800488e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800488ea  mov     rcx, [rbp+4Fh]; this
0x1800488ee  test    eax, eax
0x1800488f0  js      loc_180048B2E
0x1800488f6  mov     dword ptr [rbp+47h+var_B0], 4
0x1800488fd  mov     rcx, [rsp+120h+var_F0]
0x180048902  test    rcx, rcx
0x180048905  jz      short loc_180048919
0x180048907  mov     [rsp+120h+var_F0], r15
0x18004890c  mov     rax, [rcx]
0x18004890f  mov     rax, [rax+10h]
0x180048913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048918  nop
0x180048919  mov     rcx, [rbp+47h+var_A8]
0x18004891d  test    rcx, rcx
0x180048920  jz      short loc_180048933
0x180048922  mov     [rbp+47h+var_A8], r15
0x180048926  mov     rax, [rcx]
0x180048929  mov     rax, [rax+10h]
0x18004892d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048932  nop
0x180048933  mov     rbx, qword ptr [rbp+47h+var_88]
0x180048937  test    rbx, rbx
0x18004893a  jz      short loc_18004894C
0x18004893c  mov     rax, [rbx]
0x18004893f  mov     rcx, rbx
0x180048942  mov     rax, [rax+8]
0x180048946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004894b  nop
0x18004894c  mov     [rsp+120h+var_F0], rbx
0x180048951  mov     byte ptr [rsp+120h+var_E8], 1
0x180048956  mov     r8d, 1B7740h; unsigned int
0x18004895c  mov     rdx, [rsi+18h]; void *
0x180048960  mov     rcx, [rbp+47h+var_A0]
0x180048964  mov     rcx, [rcx+0D8h]; void *
0x18004896b  call    ?CancellableWait@@YAXPEAX0K@Z; CancellableWait(void *,void *,ulong)
0x180048970  mov     byte ptr [rsp+120h+var_E8], r15b
0x180048975  mov     [rbp+47h+var_90], r15
0x180048979  mov     rcx, [rbp+47h+var_80]
0x18004897d  mov     rax, [rcx]
0x180048980  lea     r8, [rbp+47h+var_90]
0x180048984  mov     rdx, qword ptr [rbp+47h+var_88]
0x180048988  mov     rax, [rax+88h]
0x18004898f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048994  mov     rcx, [rbp+4Fh]; this
0x180048998  test    eax, eax
0x18004899a  js      loc_180048B43
0x1800489a0  mov     [rbp+47h+var_98], r15d
0x1800489a4  mov     rcx, [rbp+47h+var_90]
0x1800489a8  mov     rax, [rcx]
0x1800489ab  lea     rdx, [rbp+47h+var_98]
0x1800489af  mov     rax, [rax+40h]
0x1800489b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800489b8  mov     rcx, [rbp+4Fh]; this
0x1800489bc  test    eax, eax
0x1800489be  js      loc_180048B58
0x1800489c4  cmp     [rbp+47h+var_98], 2
0x1800489c8  jz      short loc_180048A29
0x1800489ca  mov     [rbp+47h+var_A8], r15
0x1800489ce  mov     rcx, [rbp+47h+var_90]
0x1800489d2  mov     rax, [rcx]
0x1800489d5  lea     r8, [rbp+47h+var_A8]
0x1800489d9  xor     edx, edx
0x1800489db  mov     rax, [rax+48h]
0x1800489df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800489e4  test    eax, eax
0x1800489e6  js      loc_180048B6D
0x1800489ec  mov     dword ptr [rbp+47h+var_B0], r15d
0x1800489f0  mov     rcx, [rbp+47h+var_A8]
0x1800489f4  mov     rax, [rcx]
0x1800489f7  lea     rdx, [rbp+47h+var_B0]
0x1800489fb  mov     rax, [rax+38h]
0x1800489ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a04  mov     rcx, [rbp+4Fh]; this
0x180048a08  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x180048a0f  test    eax, eax
0x180048a11  js      loc_180048B86
0x180048a17  mov     r9d, dword ptr [rbp+47h+var_B0]; char *
0x180048a1b  test    r9d, r9d
0x180048a1e  js      loc_180048AF5
0x180048a24  jmp     loc_180048AE4
0x180048a29  mov     rcx, [rbp+47h+var_90]
0x180048a2d  test    rcx, rcx
0x180048a30  jz      short loc_180048A43
0x180048a32  mov     [rbp+47h+var_90], r15
0x180048a36  mov     rax, [rcx]
0x180048a39  mov     rax, [rax+10h]
0x180048a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a42  nop
0x180048a43  test    rbx, rbx
0x180048a46  jz      short loc_180048A58
0x180048a48  mov     rax, [rbx]
0x180048a4b  mov     rcx, rbx
0x180048a4e  mov     rax, [rax+10h]
0x180048a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a57  nop
0x180048a58  mov     rcx, qword ptr [rbp+47h+var_88]
0x180048a5c  test    rcx, rcx
0x180048a5f  jz      short loc_180048A72
0x180048a61  mov     qword ptr [rbp+47h+var_88], r15
0x180048a65  mov     rax, [rcx]
0x180048a68  mov     rax, [rax+10h]
0x180048a6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a71  nop
0x180048a72  lea     rcx, [rbp+47h+pvarg]; pvarg
0x180048a76  call    cs:__imp_VariantClear
0x180048a7c  nop
0x180048a7d  mov     rcx, [rsp+120h+var_E0]; _Mtx_t
0x180048a82  test    rcx, rcx
0x180048a85  jz      short loc_180048A8D
0x180048a87  call    ?_ReleaseCallBack@?$ProgressCallBackHolder@V?$function@$$A6AXIW4LanguagePackInstallProgressState@@@Z@std@@@@CAXPEAV1@@Z; ProgressCallBackHolder<std::function<void (uint,LanguagePackInstallProgressState)>>::_ReleaseCallBack(ProgressCallBackHolder<std::function<void (uint,LanguagePackInstallProgressState)>> *)
0x180048a8c  nop
0x180048a8d  mov     rcx, [rbp+47h+var_A0]
0x180048a91  test    rcx, rcx
0x180048a94  jz      short loc_180048AA0
0x180048a96  mov     [rbp+47h+var_A0], r15
0x180048a9a  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppExtensions::AppExtension *> *>,Microsoft::WRL::FtmBase>::Release(void)
0x180048a9f  nop
0x180048aa0  mov     rcx, [rbp+47h+var_80]
0x180048aa4  test    rcx, rcx
0x180048aa7  jz      short loc_180048ABA
0x180048aa9  mov     [rbp+47h+var_80], r15
0x180048aad  mov     rax, [rcx]
0x180048ab0  mov     rax, [rax+10h]
0x180048ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048ab9  nop
0x180048aba  mov     rcx, [rbp+47h+var_60]
0x180048abe  xor     rcx, rsp; StackCookie
0x180048ac1  call    __security_check_cookie
0x180048ac6  lea     r11, [rsp+120h+var_28]
0x180048ace  movaps  xmm6, xmmword ptr [r11-18h]
0x180048ad3  movaps  xmm7, xmmword ptr [r11-28h]
0x180048ad8  mov     rsp, r11
0x180048adb  pop     r15
0x180048add  pop     r14
0x180048adf  pop     rdi
0x180048ae0  pop     rsi
0x180048ae1  pop     rbx
0x180048ae2  pop     rbp
0x180048ae3  retn
0x180048ae4  mov     r9d, 80240034h; char *
0x180048aea  mov     edx, 310h; void *
0x180048aef  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048af5  mov     edx, 30Ch; void *
0x180048afa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048b00  mov     r9d, eax; char *
0x180048b03  lea     r8, aOnecoreBaseLan_22; "onecore\\base\\languageoverlay\\service"...
0x180048b0a  mov     edx, 0E9h; void *
0x180048b0f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048b15  mov     rcx, [rbp+4Fh]; this
0x180048b19  mov     r9d, eax; char *
0x180048b1c  lea     r8, aOnecoreBaseLan_22; "onecore\\base\\languageoverlay\\service"...
0x180048b23  mov     edx, 0E9h; void *
0x180048b28  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048b2e  mov     r9d, eax; char *
0x180048b31  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x180048b38  mov     edx, 2EDh; void *
0x180048b3d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048b43  mov     r9d, eax; char *
0x180048b46  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x180048b4d  mov     edx, 2FFh; void *
0x180048b52  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048b58  mov     r9d, eax; char *
0x180048b5b  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x180048b62  mov     edx, 302h; void *
0x180048b67  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048b6d  mov     rcx, [rbp+4Fh]; this
0x180048b71  mov     r9d, eax; char *
0x180048b74  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x180048b7b  mov     edx, 307h; void *
0x180048b80  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048b86  mov     r9d, eax; char *
0x180048b89  mov     edx, 30Ah; void *
0x180048b8e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
