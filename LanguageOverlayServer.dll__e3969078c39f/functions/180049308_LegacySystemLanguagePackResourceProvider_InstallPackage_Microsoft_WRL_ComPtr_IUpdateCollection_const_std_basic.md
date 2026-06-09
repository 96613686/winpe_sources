# LegacySystemLanguagePackResourceProvider::_InstallPackage(Microsoft::WRL::ComPtr<IUpdateCollection> const &,std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>> const &,std::vector<Microsoft::WRL::ComPtr<ICbsCapability>,std::allocator<Microsoft::WRL::ComPtr<ICbsCapability>>> const &,std::function<void (uint,LanguagePackInstallProgressState,unsigned __int64,unsigned __int64)> const &,bool)

- ea: `0x180049308`
- end: `0x18004978c`
- name: `?_InstallPackage@LegacySystemLanguagePackResourceProvider@@AEBAXAEBV?$ComPtr@UIUpdateCollection@@@WRL@Microsoft@@AEBV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@AEBV?$vector@V?$ComPtr@UICbsCapability@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UICbsCapability@@@WRL@Microsoft@@@std@@@6@AEBV?$function@$$A6AXIW4LanguagePackInstallProgressState@@_K1@Z@6@_N@Z`
- size: `1156`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180045570`

## callees

- `0x180003a00`
- `0x180012a98`
- `0x180035ce4`
- `0x180043cb8`
- `0x180046170`
- `0x180046280`
- `0x180046330`
- `0x180046450`
- `0x1800483ec`
- `0x180049308`
- `0x180049b88`
- `0x18006a010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800493e1`
- `OLEAUT32!__imp_VariantInit` at `0x1800493e1`
- `OLEAUT32!__imp_VariantClear` at `0x18004961b`
- `OLEAUT32!__imp_VariantClear` at `0x18004961b`

## string_xrefs

- `0x180049703`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\raiiutils.h`
- `0x180049718`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\raiiutils.h`
- `0x1800495a9`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x180049639`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x1800496d5`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x1800496ee`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x18004972d`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x180049742`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x180049757`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x18004976c`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x180049627`: `Interface Property IsBusy or RebootRequiredBeforeInstallation was true`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
HRESULT __fastcall LegacySystemLanguagePackResourceProvider::_InstallPackage(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        __int64 a5,
        char a6)
{
  int v7; // eax
  int v8; // eax
  __int64 *v9; // rbx
  __int64 v10; // rsi
  __int128 v11; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  int v13; // eax
  __int64 v14; // rdi
  int v15; // eax
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rbx
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rcx
  HRESULT result; // eax
  void **v27; // rcx
  __int64 *v28; // rcx
  int v29; // [rsp+28h] [rbp-B9h]
  char *v30; // [rsp+30h] [rbp-B1h]
  __int64 v31; // [rsp+38h] [rbp-A9h] BYREF
  __int64 v32; // [rsp+40h] [rbp-A1h]
  _Mtx_t v33; // [rsp+48h] [rbp-99h]
  _QWORD v34[5]; // [rsp+50h] [rbp-91h] BYREF
  int v35; // [rsp+78h] [rbp-69h] BYREF
  __int16 v36; // [rsp+7Ch] [rbp-65h] BYREF
  __int16 v37; // [rsp+80h] [rbp-61h] BYREF
  __int64 v38; // [rsp+88h] [rbp-59h] BYREF
  void **v39; // [rsp+90h] [rbp-51h] BYREF
  __int64 *v40; // [rsp+98h] [rbp-49h] BYREF
  int v41; // [rsp+A0h] [rbp-41h] BYREF
  __int64 v42; // [rsp+A8h] [rbp-39h] BYREF
  int v43[2]; // [rsp+B0h] [rbp-31h] BYREF
  VARIANTARG pvarg; // [rsp+B8h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+130h] [rbp+4Fh]

  v35 = 0;
  LegacySystemLanguagePackResourceProvider::_CreateUpdateInstaller(a1, (unsigned int)&v40, a2, a3, a4, a6);
  Microsoft::WRL::Details::Make<CompletionCallback,>((CompletionCallback **)&v39);
  ProgressCallBackHolder<std::function<void (unsigned int,enum LanguagePackInstallProgressState,unsigned __int64,unsigned __int64)>>::SetProgressCallBack((_Mtx_t)(v39 + 6));
  v36 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, __int16 *))(*v40 + 216))(v40, &v36);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x320,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v7,
      v29);
  v37 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64 *, __int16 *))(*v40 + 184))(v40, &v37);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x323,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v8,
      v29);
  if ( v36 || v37 )
  {
    result = wil::details::in1diag3::Log_HrMsg(
               retaddr,
               (void *)0x355,
               (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
               (const char *)0x8000000ALL,
               (int)"Interface Property IsBusy or RebootRequiredBeforeInstallation was true",
               v30);
  }
  else
  {
    VariantInit(&pvarg);
    *(_QWORD *)v43 = 0;
    v9 = v40;
    v10 = *v40;
    v11 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    v38 = 0;
    v35 = 4;
    v13 = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ISearchCompletedCallback,IDownloadCompletedCallback,IInstallationCompletedCallback,IDownloadProgressChangedCallback,IInstallationProgressChangedCallback>::QueryInterface(
            v39,
            &GUID_45f4f6f3_d602_4f98_9a8a_3efa152ad2d3,
            &v38);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE9,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\raiiutils.h",
        (const char *)(unsigned int)v13,
        v29);
    v14 = v38;
    v31 = 0;
    v35 = 12;
    v15 = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ISearchCompletedCallback,IDownloadCompletedCallback,IInstallationCompletedCallback,IDownloadProgressChangedCallback,IInstallationProgressChangedCallback>::QueryInterface(
            v39,
            &GUID_e01402d5_f8da_43ba_a012_38894bd048f1,
            &v31);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE9,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\raiiutils.h",
        (const char *)(unsigned int)v15,
        v29);
    *(_OWORD *)&v34[1] = v11;
    v34[3] = pRecInfo;
    v16 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, _QWORD *))(v10 + 136))(v9, v31, v14, &v34[1]);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x32D,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
        (const char *)(unsigned int)v16,
        (int)v43);
    v35 = 4;
    v17 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v18 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v19 = *(_QWORD *)v43;
    if ( *(_QWORD *)v43 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v43 + 8LL))(*(_QWORD *)v43);
    v31 = v19;
    LOBYTE(v32) = 1;
    CancellableWait(v39[27], *(void **)(a1 + 24), 0x1B7740u);
    LOBYTE(v32) = 0;
    v42 = 0;
    v20 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(*v40 + 152))(v40, *(_QWORD *)v43, &v42);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x33F,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
        (const char *)(unsigned int)v20,
        (int)v43);
    v41 = 0;
    v21 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v42 + 72LL))(v42, &v41);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x342,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
        (const char *)(unsigned int)v21,
        (int)v43);
    if ( v41 != 2 )
    {
      v38 = 0;
      v22 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v42 + 80LL))(v42, 0, &v38);
      if ( v22 >= 0 )
      {
        v35 = 0;
        v23 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v38 + 56LL))(v38, &v35);
        if ( v23 >= 0 )
        {
          if ( v35 >= 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x350,
              (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
              (const char *)0x80073CF9LL,
              (int)v43);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x34C,
            (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
            (const char *)(unsigned int)v35,
            (int)v43);
        }
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x34A,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
          (const char *)(unsigned int)v23,
          (int)v43);
      }
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x347,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
        (const char *)(unsigned int)v22,
        (int)v43);
    }
    v24 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v25 = *(_QWORD *)v43;
    if ( *(_QWORD *)v43 )
    {
      *(_QWORD *)v43 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    result = VariantClear(&pvarg);
  }
  if ( v33 )
    result = ProgressCallBackHolder<std::function<void (unsigned int,enum LanguagePackInstallProgressState)>>::_ReleaseCallBack(v33);
  v27 = v39;
  if ( v39 )
  {
    v39 = 0;
    result = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppExtensions::AppExtension *> *>,Microsoft::WRL::FtmBase>::Release(v27);
  }
  v28 = v40;
  if ( v40 )
  {
    v40 = 0;
    return (*(__int64 (__fastcall **)(__int64 *))(*v28 + 16))(v28);
  }
  return result;
}

```

## disassembly

```asm
0x180049308  mov     rax, rsp
0x18004930b  push    rbp
0x18004930c  push    rbx
0x18004930d  push    rsi
0x18004930e  push    rdi
0x18004930f  push    r14
0x180049311  push    r15
0x180049313  lea     rbp, [rax-4Fh]
0x180049317  sub     rsp, 0F8h
0x18004931e  movaps  xmmword ptr [rax-48h], xmm6
0x180049322  movaps  xmmword ptr [rax-58h], xmm7
0x180049326  mov     rax, cs:__security_cookie
0x18004932d  xor     rax, rsp
0x180049330  mov     [rbp+47h+var_58], rax
0x180049334  mov     r14, rcx
0x180049337  xor     r15d, r15d
0x18004933a  mov     dword ptr [rbp+47h+var_B0], r15d
0x18004933e  mov     al, byte ptr [rbp+47h+arg_28]
0x180049341  mov     byte ptr [rsp+120h+var_F8], al; char *
0x180049345  mov     qword ptr [rsp+120h+var_100], r9; int
0x18004934a  mov     r9, r8
0x18004934d  mov     r8, rdx
0x180049350  lea     rdx, [rbp+47h+var_90]
0x180049354  call    ?_CreateUpdateInstaller@LegacySystemLanguagePackResourceProvider@@AEBA?AV?$ComPtr@UIUpdateInstaller@@@WRL@Microsoft@@AEBV?$ComPtr@UIUpdateCollection@@@34@AEBV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@AEBV?$vector@V?$ComPtr@UICbsCapability@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UICbsCapability@@@WRL@Microsoft@@@std@@@7@_N@Z; LegacySystemLanguagePackResourceProvider::_CreateUpdateInstaller(Microsoft::WRL::ComPtr<IUpdateCollection> const &,std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>> const &,std::vector<Microsoft::WRL::ComPtr<ICbsCapability>> const &,bool)
0x180049359  nop
0x18004935a  lea     rcx, [rbp+47h+var_98]
0x18004935e  call    ??$Make@VCompletionCallback@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCompletionCallback@@@12@XZ; Microsoft::WRL::Details::Make<CompletionCallback,>(void)
0x180049363  nop
0x180049364  mov     rcx, [rbp+47h+var_98]
0x180049368  add     rcx, 30h ; '0'; _Mtx_t
0x18004936c  mov     r8, [rbp+47h+arg_20]
0x180049370  lea     rdx, [rsp+120h+var_E0]
0x180049375  call    ?SetProgressCallBack@?$ProgressCallBackHolder@V?$function@$$A6AXIW4LanguagePackInstallProgressState@@_K1@Z@std@@@@QEAA@AEBV?$function@$$A6AXIW4LanguagePackInstallProgressState@@_K1@Z@std@@@Z; ProgressCallBackHolder<std::function<void (uint,LanguagePackInstallProgressState,unsigned __int64,unsigned __int64)>>::SetProgressCallBack(std::function<void (uint,LanguagePackInstallProgressState,unsigned __int64,unsigned __int64)> const &)
0x18004937a  nop
0x18004937b  mov     word ptr [rbp+47h+var_B0+4], r15w
0x180049380  mov     rcx, [rbp+47h+var_90]
0x180049384  mov     rax, [rcx]
0x180049387  lea     rdx, [rbp+47h+var_B0+4]
0x18004938b  mov     rax, [rax+0D8h]
0x180049392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049397  mov     rcx, [rbp+4Fh]; this
0x18004939b  test    eax, eax
0x18004939d  js      loc_1800496D2
0x1800493a3  mov     [rbp+47h+var_A8], r15w
0x1800493a8  mov     rcx, [rbp+47h+var_90]
0x1800493ac  mov     rax, [rcx]
0x1800493af  lea     rdx, [rbp+47h+var_A8]
0x1800493b3  mov     rax, [rax+0B8h]
0x1800493ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800493bf  test    eax, eax
0x1800493c1  js      loc_1800496E7
0x1800493c7  cmp     word ptr [rbp+47h+var_B0+4], r15w
0x1800493cc  jnz     loc_180049623
0x1800493d2  cmp     [rbp+47h+var_A8], r15w
0x1800493d7  jnz     loc_180049623
0x1800493dd  lea     rcx, [rbp+47h+pvarg]; pvarg
0x1800493e1  call    cs:__imp_VariantInit
0x1800493e7  nop
0x1800493e8  mov     qword ptr [rbp+47h+var_78], r15
0x1800493ec  mov     rbx, [rbp+47h+var_90]
0x1800493f0  mov     rsi, [rbx]
0x1800493f3  movups  xmm6, xmmword ptr [rbp+47h+pvarg]
0x1800493f7  movsd   xmm7, qword ptr [rbp+47h+pvarg+10h]
0x1800493fc  mov     [rbp+47h+var_A0], r15
0x180049400  mov     dword ptr [rbp+47h+var_B0], 4
0x180049407  lea     r8, [rbp+47h+var_A0]
0x18004940b  lea     rdx, _GUID_45f4f6f3_d602_4f98_9a8a_3efa152ad2d3
0x180049412  mov     rcx, [rbp+47h+var_98]
0x180049416  call    ?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UISearchCompletedCallback@@UIDownloadCompletedCallback@@UIInstallationCompletedCallback@@UIDownloadProgressChangedCallback@@UIInstallationProgressChangedCallback@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ISearchCompletedCallback,IDownloadCompletedCallback,IInstallationCompletedCallback,IDownloadProgressChangedCallback,IInstallationProgressChangedCallback>::QueryInterface(_GUID const &,void * *)
0x18004941b  mov     rcx, [rbp+4Fh]; this
0x18004941f  test    eax, eax
0x180049421  js      loc_180049700
0x180049427  mov     rdi, [rbp+47h+var_A0]
0x18004942b  mov     [rsp+120h+var_F0], r15
0x180049430  mov     dword ptr [rbp+47h+var_B0], 0Ch
0x180049437  lea     r8, [rsp+120h+var_F0]
0x18004943c  lea     rdx, _GUID_e01402d5_f8da_43ba_a012_38894bd048f1
0x180049443  mov     rcx, [rbp+47h+var_98]
0x180049447  call    ?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UISearchCompletedCallback@@UIDownloadCompletedCallback@@UIInstallationCompletedCallback@@UIDownloadProgressChangedCallback@@UIInstallationProgressChangedCallback@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ISearchCompletedCallback,IDownloadCompletedCallback,IInstallationCompletedCallback,IDownloadProgressChangedCallback,IInstallationProgressChangedCallback>::QueryInterface(_GUID const &,void * *)
0x18004944c  mov     rcx, [rbp+4Fh]; this
0x180049450  test    eax, eax
0x180049452  js      loc_180049715
0x180049458  movaps  xmmword ptr [rsp+120h+var_D8+8], xmm6
0x18004945d  movsd   [rbp+47h+var_C0], xmm7
0x180049462  lea     rax, [rbp+47h+var_78]
0x180049466  mov     qword ptr [rsp+120h+var_100], rax; int
0x18004946b  lea     r9, [rsp+120h+var_D8+8]
0x180049470  mov     r8, rdi
0x180049473  mov     rdx, [rsp+120h+var_F0]
0x180049478  mov     rcx, rbx
0x18004947b  mov     rax, [rsi+88h]
0x180049482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049487  mov     rcx, [rbp+4Fh]; this
0x18004948b  test    eax, eax
0x18004948d  js      loc_18004972A
0x180049493  mov     dword ptr [rbp+47h+var_B0], 4
0x18004949a  mov     rcx, [rsp+120h+var_F0]
0x18004949f  test    rcx, rcx
0x1800494a2  jz      short loc_1800494B6
0x1800494a4  mov     [rsp+120h+var_F0], r15
0x1800494a9  mov     rax, [rcx]
0x1800494ac  mov     rax, [rax+10h]
0x1800494b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800494b5  nop
0x1800494b6  mov     rcx, [rbp+47h+var_A0]
0x1800494ba  test    rcx, rcx
0x1800494bd  jz      short loc_1800494D0
0x1800494bf  mov     [rbp+47h+var_A0], r15
0x1800494c3  mov     rax, [rcx]
0x1800494c6  mov     rax, [rax+10h]
0x1800494ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800494cf  nop
0x1800494d0  mov     rbx, qword ptr [rbp+47h+var_78]
0x1800494d4  test    rbx, rbx
0x1800494d7  jz      short loc_1800494E9
0x1800494d9  mov     rax, [rbx]
0x1800494dc  mov     rcx, rbx
0x1800494df  mov     rax, [rax+8]
0x1800494e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800494e8  nop
0x1800494e9  mov     [rsp+120h+var_F0], rbx
0x1800494ee  mov     byte ptr [rsp+120h+var_E8], 1
0x1800494f3  mov     r8d, 1B7740h; unsigned int
0x1800494f9  mov     rdx, [r14+18h]; void *
0x1800494fd  mov     rcx, [rbp+47h+var_98]
0x180049501  mov     rcx, [rcx+0D8h]; void *
0x180049508  call    ?CancellableWait@@YAXPEAX0K@Z; CancellableWait(void *,void *,ulong)
0x18004950d  mov     byte ptr [rsp+120h+var_E8], r15b
0x180049512  mov     [rbp+47h+var_80], r15
0x180049516  mov     rcx, [rbp+47h+var_90]
0x18004951a  mov     rax, [rcx]
0x18004951d  lea     r8, [rbp+47h+var_80]
0x180049521  mov     rdx, qword ptr [rbp+47h+var_78]
0x180049525  mov     rax, [rax+98h]
0x18004952c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049531  mov     rcx, [rbp+4Fh]; this
0x180049535  test    eax, eax
0x180049537  js      loc_18004973F
0x18004953d  mov     [rbp+47h+var_88], r15d
0x180049541  mov     rcx, [rbp+47h+var_80]
0x180049545  mov     rax, [rcx]
0x180049548  lea     rdx, [rbp+47h+var_88]
0x18004954c  mov     rax, [rax+48h]
0x180049550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049555  mov     rcx, [rbp+4Fh]; this
0x180049559  test    eax, eax
0x18004955b  js      loc_180049754
0x180049561  cmp     [rbp+47h+var_88], 2
0x180049565  jz      short loc_1800495CE
0x180049567  mov     [rbp+47h+var_A0], r15
0x18004956b  mov     rcx, [rbp+47h+var_80]
0x18004956f  mov     rax, [rcx]
0x180049572  lea     r8, [rbp+47h+var_A0]
0x180049576  xor     edx, edx
0x180049578  mov     rax, [rax+50h]
0x18004957c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049581  mov     rcx, [rbp+4Fh]; this
0x180049585  test    eax, eax
0x180049587  js      loc_180049769
0x18004958d  mov     dword ptr [rbp+47h+var_B0], r15d
0x180049591  mov     rcx, [rbp+47h+var_A0]
0x180049595  mov     rax, [rcx]
0x180049598  lea     rdx, [rbp+47h+var_B0]
0x18004959c  mov     rax, [rax+38h]
0x1800495a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800495a5  mov     rcx, [rbp+4Fh]; this
0x1800495a9  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x1800495b0  test    eax, eax
0x1800495b2  js      loc_18004977E
0x1800495b8  mov     r9d, dword ptr [rbp+47h+var_B0]; char *
0x1800495bc  mov     rcx, [rbp+4Fh]; this
0x1800495c0  test    r9d, r9d
0x1800495c3  js      loc_1800496C7
0x1800495c9  jmp     loc_1800496B2
0x1800495ce  mov     rcx, [rbp+47h+var_80]
0x1800495d2  test    rcx, rcx
0x1800495d5  jz      short loc_1800495E8
0x1800495d7  mov     [rbp+47h+var_80], r15
0x1800495db  mov     rax, [rcx]
0x1800495de  mov     rax, [rax+10h]
0x1800495e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800495e7  nop
0x1800495e8  test    rbx, rbx
0x1800495eb  jz      short loc_1800495FD
0x1800495ed  mov     rax, [rbx]
0x1800495f0  mov     rcx, rbx
0x1800495f3  mov     rax, [rax+10h]
0x1800495f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800495fc  nop
0x1800495fd  mov     rcx, qword ptr [rbp+47h+var_78]
0x180049601  test    rcx, rcx
0x180049604  jz      short loc_180049617
0x180049606  mov     qword ptr [rbp+47h+var_78], r15
0x18004960a  mov     rax, [rcx]
0x18004960d  mov     rax, [rax+10h]
0x180049611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049616  nop
0x180049617  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18004961b  call    cs:__imp_VariantClear
0x180049621  jmp     short loc_18004964B
0x180049623  mov     rcx, [rbp+4Fh]; this
0x180049627  lea     rax, aInterfacePrope; "Interface Property IsBusy or RebootRequ"...
0x18004962e  mov     qword ptr [rsp+120h+var_100], rax; int
0x180049633  mov     r9d, 8000000Ah; char *
0x180049639  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x180049640  mov     edx, 355h; void *
0x180049645  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004964a  nop
0x18004964b  mov     rcx, [rsp+120h+var_E0]; _Mtx_t
0x180049650  test    rcx, rcx
0x180049653  jz      short loc_18004965B
0x180049655  call    ?_ReleaseCallBack@?$ProgressCallBackHolder@V?$function@$$A6AXIW4LanguagePackInstallProgressState@@@Z@std@@@@CAXPEAV1@@Z; ProgressCallBackHolder<std::function<void (uint,LanguagePackInstallProgressState)>>::_ReleaseCallBack(ProgressCallBackHolder<std::function<void (uint,LanguagePackInstallProgressState)>> *)
0x18004965a  nop
0x18004965b  mov     rcx, [rbp+47h+var_98]
0x18004965f  test    rcx, rcx
0x180049662  jz      short loc_18004966E
0x180049664  mov     [rbp+47h+var_98], r15
0x180049668  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::AppExtensions::AppExtension *> *>,Microsoft::WRL::FtmBase>::Release(void)
0x18004966d  nop
0x18004966e  mov     rcx, [rbp+47h+var_90]
0x180049672  test    rcx, rcx
0x180049675  jz      short loc_180049688
0x180049677  mov     [rbp+47h+var_90], r15
0x18004967b  mov     rax, [rcx]
0x18004967e  mov     rax, [rax+10h]
0x180049682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049687  nop
0x180049688  mov     rcx, [rbp+47h+var_58]
0x18004968c  xor     rcx, rsp; StackCookie
0x18004968f  call    __security_check_cookie
0x180049694  lea     r11, [rsp+120h+var_28]
0x18004969c  movaps  xmm6, xmmword ptr [r11-18h]
0x1800496a1  movaps  xmm7, xmmword ptr [r11-28h]
0x1800496a6  mov     rsp, r11
0x1800496a9  pop     r15
0x1800496ab  pop     r14
0x1800496ad  pop     rdi
0x1800496ae  pop     rsi
0x1800496af  pop     rbx
0x1800496b0  pop     rbp
0x1800496b1  retn
0x1800496b2  mov     rcx, [rbp+4Fh]; this
0x1800496b6  mov     r9d, 80073CF9h; char *
0x1800496bc  mov     edx, 350h; void *
0x1800496c1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800496c7  mov     edx, 34Ch; void *
0x1800496cc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800496d2  mov     r9d, eax; char *
0x1800496d5  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x1800496dc  mov     edx, 320h; void *
0x1800496e1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800496e7  mov     rcx, [rbp+4Fh]; this
0x1800496eb  mov     r9d, eax; char *
0x1800496ee  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x1800496f5  mov     edx, 323h; void *
0x1800496fa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180049700  mov     r9d, eax; char *
0x180049703  lea     r8, aOnecoreBaseLan_22; "onecore\\base\\languageoverlay\\service"...
0x18004970a  mov     edx, 0E9h; void *
0x18004970f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180049715  mov     r9d, eax; char *
0x180049718  lea     r8, aOnecoreBaseLan_22; "onecore\\base\\languageoverlay\\service"...
0x18004971f  mov     edx, 0E9h; void *
0x180049724  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004972a  mov     r9d, eax; char *
0x18004972d  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x180049734  mov     edx, 32Dh; void *
0x180049739  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004973f  mov     r9d, eax; char *
0x180049742  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x180049749  mov     edx, 33Fh; void *
0x18004974e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180049754  mov     r9d, eax; char *
0x180049757  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x18004975e  mov     edx, 342h; void *
0x180049763  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180049769  mov     r9d, eax; char *
0x18004976c  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x180049773  mov     edx, 347h; void *
0x180049778  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004977e  mov     r9d, eax; char *
0x180049781  mov     edx, 34Ah; void *
0x180049786  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
