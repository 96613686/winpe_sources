# Windows::WU::WuUpdateInternalImpl::DownloadEx(Windows::WU::DownloadProperties const &,std::function<void (ProgressCallbackData)> const &)

- ea: `0x1402e6710`
- end: `0x1402e6cdc`
- name: `?DownloadEx@WuUpdateInternalImpl@WU@Windows@@UEAA?AV?$optional@UDownloadResult@WU@Windows@@@std@@AEBUDownloadProperties@23@AEBV?$function@$$A6AXUProgressCallbackData@@@Z@5@@Z`
- size: `1484`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1400413a8`
- `0x140045404`
- `0x140071f48`
- `0x1402e3bd0`
- `0x1402e6710`
- `0x1402e6ce4`
- `0x1402eb970`
- `0x1402ec8ec`
- `0x1402ec95c`
- `0x140379070`
- `0x1403790d8`
- `0x140380b50`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1402e6901`
- `OLEAUT32!__imp_VariantInit` at `0x1402e6901`
- `OLEAUT32!__imp_VariantClear` at `0x1402e6a03`
- `OLEAUT32!__imp_VariantClear` at `0x1402e6b71`
- `OLEAUT32!__imp_VariantClear` at `0x1402e6a03`
- `OLEAUT32!__imp_VariantClear` at `0x1402e6b71`

## string_xrefs

- `0x1402e6c0d`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402e6c22`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402e6c37`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402e6c4c`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402e6c61`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402e6c76`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402e6c8b`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402e6ca0`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402e6cb5`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402e6cca`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall Windows::WU::WuUpdateInternalImpl::DownloadEx(
        Windows::WU::WuUpdateInternalImpl *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int v8; // eax
  __int64 (__fastcall **v9)(__int64 *, GUID *, __int64 *); // rax
  int v10; // eax
  struct _GUID *updated; // rax
  const wchar_t *v12; // r8
  __int64 (__fastcall **v13)(__int64 *, GUID *, __int64 *); // rax
  int v14; // eax
  int v15; // eax
  _OWORD *v16; // rbx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rax
  int v20; // eax
  int v21; // eax
  __int64 v22; // rax
  int v23; // eax
  void (*v24)(void); // rax
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rax
  int v28; // eax
  int v29; // eax
  bool v30; // cl
  int v31; // eax
  int v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+20h] [rbp-E0h]
  __int64 v35; // [rsp+40h] [rbp-C0h]
  VARIANTARG v36; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD *v37; // [rsp+70h] [rbp-90h] BYREF
  __int64 (__fastcall **v38)(); // [rsp+80h] [rbp-80h] BYREF
  __int128 v39; // [rsp+88h] [rbp-78h]
  __int64 (__fastcall ***v40)(); // [rsp+B8h] [rbp-48h]
  int v41; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v42; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v43; // [rsp+D0h] [rbp-30h]
  __int64 v44; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v45; // [rsp+E0h] [rbp-20h] BYREF
  __int64 *v46; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v47; // [rsp+F0h] [rbp-10h] BYREF
  __int64 *v48; // [rsp+F8h] [rbp-8h] BYREF
  VARIANTARG pvarg; // [rsp+100h] [rbp+0h] BYREF
  __int128 v50; // [rsp+118h] [rbp+18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v42 = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(**((_QWORD **)this + 14) + 104LL))(*((_QWORD *)this + 14), &v42);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2E2,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
      (const char *)(unsigned int)v8,
      v33);
  v46 = 0;
  v9 = (__int64 (__fastcall **)(__int64 *, GUID *, __int64 *))*v42;
  v46 = 0;
  v10 = (*v9)(v42, &GUID_94726306_f12a_482a_a774_fb4f870d98c0, (__int64 *)&v46);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2E5,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
      (const char *)(unsigned int)v10,
      v33);
  updated = (struct _GUID *)Windows::WU::WuUpdateInternalImpl::UpdateId(this, &v36);
  if ( *(_QWORD *)updated[1].Data4 > 7u )
    updated = *(struct _GUID **)&updated->Data1;
  v50 = (__int128)*Windows::Strings::to_guid((Windows::Strings *)&v37, updated, v12);
  std::wstring::~wstring(&v36);
  v45 = 0;
  v13 = (__int64 (__fastcall **)(__int64 *, GUID *, __int64 *))*v42;
  v45 = 0;
  v14 = (*v13)(v42, &GUID_d7708661_fce5_4317_852b_bbc9a95edcab, &v45);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2EA,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
      (const char *)(unsigned int)v14,
      v33);
  v15 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)v45 + 24LL))(
          v45,
          &v50,
          *(unsigned int *)(a3 + 44));
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2EB,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
      (const char *)(unsigned int)v15,
      v33);
  Windows::WU::WuUpdateInternalImpl::SetDownloadProperties((__int64)this, (__int64 *)a3, (OLECHAR *)&v42);
  v16 = operator new(0x30u);
  *(_QWORD *)&v36.vt = v16;
  *v16 = 0;
  v16[1] = 0;
  v16[2] = 0;
  v17 = 0;
  v18 = 0;
  v19 = *((_QWORD *)this + 3);
  if ( v19 )
  {
    v17 = *((_QWORD *)this + 2);
    v18 = *((_QWORD *)this + 3);
    _InterlockedIncrement((volatile signed __int32 *)(v19 + 12));
  }
  *(_QWORD *)v16 = &Windows::WU::WuCallback<IDownloadProgressChangedCallback,IDownloadCompletedCallback,IDownloadJob,IDownloadProgressChangedCallbackArgs,IDownloadCompletedCallbackArgs>::`vftable'{for `IDownloadProgressChangedCallback'};
  *((_QWORD *)v16 + 1) = &Windows::WU::WuCallback<IDownloadProgressChangedCallback,IDownloadCompletedCallback,IDownloadJob,IDownloadProgressChangedCallbackArgs,IDownloadCompletedCallbackArgs>::`vftable'{for `IDownloadCompletedCallback'};
  *((_WORD *)v16 + 8) = 0;
  *((_QWORD *)v16 + 3) = v17;
  *((_QWORD *)v16 + 4) = v18;
  *((_DWORD *)v16 + 10) = 0;
  v37 = v16;
  (*(void (__fastcall **)(_OWORD *))(*(_QWORD *)v16 + 8LL))(v16);
  v44 = 0;
  wil::CoCreateInstance<UpdateCollection,IUpdateCollection,wil::err_exception_policy>(&v44);
  v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v44 + 96LL))(v44, *((_QWORD *)this + 15), 0);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2F2,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
      (const char *)(unsigned int)v20,
      v33);
  v21 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v42 + 112))(v42, v44);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2F4,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
      (const char *)(unsigned int)v21,
      v33);
  VariantInit(&pvarg);
  v43 = 0;
  v22 = *v46;
  v43 = 0;
  v36 = pvarg;
  v23 = (*(__int64 (__fastcall **)(__int64 *, bool, _OWORD *, __int64))(v22 + 144))(
          v46,
          *(_BYTE *)(a3 + 101) != 0,
          v16,
          (__int64)v16 + 8);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2FD,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
      (const char *)(unsigned int)v23,
      (int)&v36);
  *(_QWORD *)&v36.vt = a4;
  v36.llVal = (LONGLONG)this;
  v38 = off_1403D70B8;
  v39 = *(_OWORD *)&v36.vt;
  v40 = &v38;
  (*(void (__fastcall **)(_OWORD *))(*(_QWORD *)v16 + 8LL))(v16);
  *(_QWORD *)&v36.vt = v43;
  if ( v43 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 8LL))(v43);
  if ( (unsigned __int8)Windows::WU::WuUpdateInternalImpl::WaitForCompletion<IInstallationJob,Windows::WU::WuCallback<IInstallationProgressChangedCallback,IInstallationCompletedCallback,IInstallationJob,IInstallationProgressChangedCallbackArgs,IInstallationCompletedCallbackArgs>,IInstallationProgress>(
                          this,
                          a3 + 96) )
  {
    v48 = 0;
    v25 = *v42;
    v48 = 0;
    v26 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 **))(v25 + 136))(v42, v43, &v48);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x309,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)(unsigned int)v26,
        v34);
    v47 = 0;
    v27 = *v48;
    v47 = 0;
    v28 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v27 + 72))(v48, 0, &v47);
    if ( v28 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x30C,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)(unsigned int)v28,
        v34);
    v41 = 0;
    v29 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v47 + 56LL))(v47, &v41);
    if ( v29 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x30F,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)(unsigned int)v29,
        v34);
    v30 = 0;
    v31 = v41;
    if ( v41 >= 0 )
    {
      v30 = Windows::WU::WuUpdateInternalImpl::IpuUpdate(this, (const struct Windows::WU::DownloadProperties *)a3);
      v31 = v41;
    }
    LODWORD(v35) = v31;
    BYTE4(v35) = v30;
    *(_WORD *)((char *)&v35 + 5) = 0;
    HIBYTE(v35) = 0;
    *(_QWORD *)a2 = v35;
    *(_BYTE *)(a2 + 8) = 1;
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    if ( v48 )
      (*(void (__fastcall **)(__int64 *))(*v48 + 16))(v48);
    if ( v43 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    VariantClear(&pvarg);
    if ( v44 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    (*(void (__fastcall **)(_OWORD *))(*(_QWORD *)v16 + 16LL))(v16);
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    if ( v46 )
      (*(void (__fastcall **)(__int64 *))(*v46 + 16))(v46);
    if ( v42 )
    {
      v24 = *(void (**)(void))(*v42 + 16);
      goto LABEL_44;
    }
  }
  else
  {
    *(_BYTE *)(a2 + 8) = 0;
    if ( v43 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    VariantClear(&pvarg);
    if ( v44 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    (*(void (__fastcall **)(_OWORD *))(*(_QWORD *)v16 + 16LL))(v16);
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    if ( v46 )
      (*(void (__fastcall **)(__int64 *))(*v46 + 16))(v46);
    if ( v42 )
    {
      v24 = *(void (**)(void))(*v42 + 16);
LABEL_44:
      v24();
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1402e6710  mov     [rsp-8+arg_18], rbx
0x1402e6715  push    rbp
0x1402e6716  push    rsi
0x1402e6717  push    rdi
0x1402e6718  push    r12
0x1402e671a  push    r13
0x1402e671c  push    r14
0x1402e671e  push    r15
0x1402e6720  lea     rbp, [rsp-30h]
0x1402e6725  sub     rsp, 130h
0x1402e672c  mov     rax, cs:__security_cookie
0x1402e6733  xor     rax, rsp
0x1402e6736  mov     [rbp+60h+var_38], rax
0x1402e673a  mov     r12, r9
0x1402e673d  mov     r14, r8
0x1402e6740  mov     rsi, rdx
0x1402e6743  mov     rdi, rcx
0x1402e6746  xor     r13d, r13d
0x1402e6749  mov     [rbp+60h+var_98], r13
0x1402e674d  mov     rcx, [rcx+70h]
0x1402e6751  mov     rax, [rcx]
0x1402e6754  mov     [rbp+60h+var_98], r13
0x1402e6758  lea     rdx, [rbp+60h+var_98]
0x1402e675c  mov     rax, [rax+68h]
0x1402e6760  call    _guard_dispatch_icall
0x1402e6765  mov     rcx, [rbp+68h]; this
0x1402e6769  test    eax, eax
0x1402e676b  js      loc_1402E6C1F
0x1402e6771  mov     [rbp+60h+var_78], r13
0x1402e6775  mov     rcx, [rbp+60h+var_98]
0x1402e6779  mov     rax, [rcx]
0x1402e677c  mov     [rbp+60h+var_78], r13
0x1402e6780  lea     r8, [rbp+60h+var_78]
0x1402e6784  lea     rdx, _GUID_94726306_f12a_482a_a774_fb4f870d98c0
0x1402e678b  mov     rax, [rax]
0x1402e678e  call    _guard_dispatch_icall
0x1402e6793  mov     rcx, [rbp+68h]; this
0x1402e6797  test    eax, eax
0x1402e6799  js      loc_1402E6C34
0x1402e679f  lea     rdx, [rsp+160h+var_110]
0x1402e67a4  mov     rcx, rdi
0x1402e67a7  call    ?UpdateId@WuUpdateInternalImpl@WU@Windows@@UEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Windows::WU::WuUpdateInternalImpl::UpdateId(void)
0x1402e67ac  nop
0x1402e67ad  cmp     qword ptr [rax+18h], 7
0x1402e67b2  jbe     short loc_1402E67B7
0x1402e67b4  mov     rax, [rax]
0x1402e67b7  mov     rdx, rax; retstr
0x1402e67ba  lea     rcx, [rsp+160h+var_F0]; this
0x1402e67bf  call    ?to_guid@Strings@Windows@@YA?AU_GUID@@PEB_W@Z; Windows::Strings::to_guid(wchar_t const *)
0x1402e67c4  movups  xmm0, xmmword ptr [rax]
0x1402e67c7  movdqu  [rbp+60h+var_48], xmm0
0x1402e67cc  lea     rcx, [rsp+160h+var_110]
0x1402e67d1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402e67d6  mov     [rbp+60h+var_80], r13
0x1402e67da  mov     rcx, [rbp+60h+var_98]
0x1402e67de  mov     rax, [rcx]
0x1402e67e1  mov     [rbp+60h+var_80], r13
0x1402e67e5  lea     r8, [rbp+60h+var_80]
0x1402e67e9  lea     rdx, _GUID_d7708661_fce5_4317_852b_bbc9a95edcab
0x1402e67f0  mov     rax, [rax]
0x1402e67f3  call    _guard_dispatch_icall
0x1402e67f8  mov     rcx, [rbp+68h]; this
0x1402e67fc  test    eax, eax
0x1402e67fe  js      loc_1402E6C49
0x1402e6804  mov     rcx, [rbp+60h+var_80]
0x1402e6808  mov     rax, [rcx]
0x1402e680b  mov     r8d, [r14+2Ch]
0x1402e680f  lea     rdx, [rbp+60h+var_48]
0x1402e6813  mov     rax, [rax+18h]
0x1402e6817  call    _guard_dispatch_icall
0x1402e681c  mov     rcx, [rbp+68h]; this
0x1402e6820  test    eax, eax
0x1402e6822  js      loc_1402E6C5E
0x1402e6828  lea     r8, [rbp+60h+var_98]
0x1402e682c  mov     rdx, r14
0x1402e682f  mov     rcx, rdi
0x1402e6832  call    ?SetDownloadProperties@WuUpdateInternalImpl@WU@Windows@@AEAAXAEBUDownloadProperties@23@AEBV?$com_ptr_t@UIUpdateDownloader@@Uerr_exception_policy@wil@@@wil@@@Z; Windows::WU::WuUpdateInternalImpl::SetDownloadProperties(Windows::WU::DownloadProperties const &,wil::com_ptr_t<IUpdateDownloader,wil::err_exception_policy> const &)
0x1402e6837  mov     ecx, 30h ; '0'; Size
0x1402e683c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1402e6841  mov     rbx, rax
0x1402e6844  mov     qword ptr [rsp+160h+var_110], rax
0x1402e6849  xorps   xmm0, xmm0
0x1402e684c  movups  xmmword ptr [rax], xmm0
0x1402e684f  movups  xmmword ptr [rax+10h], xmm0
0x1402e6853  movups  xmmword ptr [rax+20h], xmm0
0x1402e6857  mov     rcx, r13
0x1402e685a  mov     rdx, r13
0x1402e685d  mov     rax, [rdi+18h]
0x1402e6861  test    rax, rax
0x1402e6864  jz      short loc_1402E6871
0x1402e6866  mov     rcx, [rdi+10h]
0x1402e686a  mov     rdx, rax
0x1402e686d  lock inc dword ptr [rax+0Ch]
0x1402e6871  lea     rax, ??_7?$WuCallback@UIDownloadProgressChangedCallback@@UIDownloadCompletedCallback@@UIDownloadJob@@UIDownloadProgressChangedCallbackArgs@@UIDownloadCompletedCallbackArgs@@@WU@Windows@@6BIDownloadProgressChangedCallback@@@; const Windows::WU::WuCallback<IDownloadProgressChangedCallback,IDownloadCompletedCallback,IDownloadJob,IDownloadProgressChangedCallbackArgs,IDownloadCompletedCallbackArgs>::`vftable'{for `IDownloadProgressChangedCallback'}
0x1402e6878  mov     [rbx], rax
0x1402e687b  lea     rax, ??_7?$WuCallback@UIDownloadProgressChangedCallback@@UIDownloadCompletedCallback@@UIDownloadJob@@UIDownloadProgressChangedCallbackArgs@@UIDownloadCompletedCallbackArgs@@@WU@Windows@@6BIDownloadCompletedCallback@@@; const Windows::WU::WuCallback<IDownloadProgressChangedCallback,IDownloadCompletedCallback,IDownloadJob,IDownloadProgressChangedCallbackArgs,IDownloadCompletedCallbackArgs>::`vftable'{for `IDownloadCompletedCallback'}
0x1402e6882  mov     [rbx+8], rax
0x1402e6886  mov     [rbx+10h], r13w
0x1402e688b  mov     [rbx+18h], rcx
0x1402e688f  mov     [rbx+20h], rdx
0x1402e6893  mov     [rbx+28h], r13d
0x1402e6897  mov     [rsp+160h+var_F0], rbx
0x1402e689c  mov     rax, [rbx]
0x1402e689f  mov     rcx, rbx
0x1402e68a2  mov     rax, [rax+8]
0x1402e68a6  call    _guard_dispatch_icall
0x1402e68ab  nop
0x1402e68ac  mov     [rbp+60h+var_88], r13
0x1402e68b0  lea     rcx, [rbp+60h+var_88]
0x1402e68b4  call    ??$CoCreateInstance@VUpdateCollection@@UIUpdateCollection@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIUpdateCollection@@Uerr_exception_policy@wil@@@0@K@Z; wil::CoCreateInstance<UpdateCollection,IUpdateCollection,wil::err_exception_policy>(ulong)
0x1402e68b9  nop
0x1402e68ba  mov     rcx, [rbp+60h+var_88]
0x1402e68be  mov     rax, [rcx]
0x1402e68c1  xor     r8d, r8d
0x1402e68c4  mov     rdx, [rdi+78h]
0x1402e68c8  mov     rax, [rax+60h]
0x1402e68cc  call    _guard_dispatch_icall
0x1402e68d1  mov     rcx, [rbp+68h]; this
0x1402e68d5  test    eax, eax
0x1402e68d7  js      loc_1402E6C73
0x1402e68dd  mov     rcx, [rbp+60h+var_98]
0x1402e68e1  mov     rax, [rcx]
0x1402e68e4  mov     rdx, [rbp+60h+var_88]
0x1402e68e8  mov     rax, [rax+70h]
0x1402e68ec  call    _guard_dispatch_icall
0x1402e68f1  mov     rcx, [rbp+68h]; this
0x1402e68f5  test    eax, eax
0x1402e68f7  js      loc_1402E6C88
0x1402e68fd  lea     rcx, [rbp+60h+pvarg]; pvarg
0x1402e6901  call    cs:__imp_VariantInit
0x1402e6907  nop
0x1402e6908  mov     [rbp+60h+var_90], r13
0x1402e690c  mov     rcx, [rbp+60h+var_78]
0x1402e6910  mov     rax, [rcx]
0x1402e6913  mov     [rbp+60h+var_90], r13
0x1402e6917  movups  xmm0, xmmword ptr [rbp+60h+pvarg]
0x1402e691b  movaps  xmmword ptr [rsp+160h+var_110], xmm0
0x1402e6920  movsd   xmm1, qword ptr [rbp+60h+pvarg+10h]
0x1402e6925  movsd   [rsp+160h+var_100], xmm1
0x1402e692b  mov     edx, r13d
0x1402e692e  cmp     [r14+65h], r13b
0x1402e6932  setnz   dl
0x1402e6935  lea     r8, [rbp+60h+var_90]
0x1402e6939  mov     [rsp+160h+var_138], r8
0x1402e693e  lea     r8, [rsp+160h+var_110]
0x1402e6943  mov     qword ptr [rsp+160h+var_140], r8; int
0x1402e6948  lea     r9, [rbx+8]
0x1402e694c  mov     r8, rbx
0x1402e694f  mov     rax, [rax+90h]
0x1402e6956  call    _guard_dispatch_icall
0x1402e695b  mov     rcx, [rbp+68h]; this
0x1402e695f  test    eax, eax
0x1402e6961  js      loc_1402E6C9D
0x1402e6967  mov     qword ptr [rsp+160h+var_110], r12
0x1402e696c  mov     qword ptr [rsp+160h+var_110+8], rdi
0x1402e6971  lea     rax, off_1403D70B8
0x1402e6978  mov     [rbp+60h+var_E0], rax
0x1402e697c  movups  xmm0, xmmword ptr [rsp+160h+var_110]
0x1402e6981  movdqu  [rbp+60h+var_D8], xmm0
0x1402e6986  lea     rax, [rbp+60h+var_E0]
0x1402e698a  mov     [rbp+60h+var_A8], rax
0x1402e698e  mov     [rsp+160h+var_120], rbx
0x1402e6993  mov     rax, [rbx]
0x1402e6996  mov     rcx, rbx
0x1402e6999  mov     rax, [rax+8]
0x1402e699d  call    _guard_dispatch_icall
0x1402e69a2  nop
0x1402e69a3  mov     rcx, [rbp+60h+var_90]
0x1402e69a7  mov     qword ptr [rsp+160h+var_110], rcx
0x1402e69ac  test    rcx, rcx
0x1402e69af  jz      short loc_1402E69BE
0x1402e69b1  mov     rax, [rcx]
0x1402e69b4  mov     rax, [rax+8]
0x1402e69b8  call    _guard_dispatch_icall
0x1402e69bd  nop
0x1402e69be  lea     rax, [r14+60h]
0x1402e69c2  mov     qword ptr [rsp+160h+var_140], rax; int
0x1402e69c7  lea     r9, [rbp+60h+var_E0]
0x1402e69cb  lea     r8, [rsp+160h+var_120]
0x1402e69d0  lea     rdx, [rsp+160h+var_110]
0x1402e69d5  mov     rcx, rdi
0x1402e69d8  call    ??$WaitForCompletion@UIInstallationJob@@V?$WuCallback@UIInstallationProgressChangedCallback@@UIInstallationCompletedCallback@@UIInstallationJob@@UIInstallationProgressChangedCallbackArgs@@UIInstallationCompletedCallbackArgs@@@WU@Windows@@UIInstallationProgress@@@WuUpdateInternalImpl@WU@Windows@@AEAA_NV?$com_ptr_t@UIInstallationJob@@Uerr_exception_policy@wil@@@wil@@V?$com_ptr_t@V?$WuCallback@UIInstallationProgressChangedCallback@@UIInstallationCompletedCallback@@UIInstallationJob@@UIInstallationProgressChangedCallbackArgs@@UIInstallationCompletedCallbackArgs@@@WU@Windows@@Uerr_exception_policy@wil@@@4@V?$function@$$A6AXV?$com_ptr_t@UIInstallationProgress@@Uerr_exception_policy@wil@@@wil@@@Z@std@@AEBV?$duration@HU?$ratio@$0DM@$00@std@@@chrono@7@@Z; Windows::WU::WuUpdateInternalImpl::WaitForCompletion<IInstallationJob,Windows::WU::WuCallback<IInstallationProgressChangedCallback,IInstallationCompletedCallback,IInstallationJob,IInstallationProgressChangedCallbackArgs,IInstallationCompletedCallbackArgs>,IInstallationProgress>(wil::com_ptr_t<IInstallationJob,wil::err_exception_policy>,wil::com_ptr_t<Windows::WU::WuCallback<IInstallationProgressChangedCallback,IInstallationCompletedCallback,IInstallationJob,IInstallationProgressChangedCallbackArgs,IInstallationCompletedCallbackArgs>,wil::err_exception_policy>,std::function<void (wil::com_ptr_t<IInstallationProgress,wil::err_exception_policy>)>,std::chrono::duration<int,std::ratio<60,1>> const &)
0x1402e69dd  test    al, al
0x1402e69df  jnz     loc_1402E6A75
0x1402e69e5  mov     [rsi+8], r13b
0x1402e69e9  mov     rcx, [rbp+60h+var_90]
0x1402e69ed  test    rcx, rcx
0x1402e69f0  jz      short loc_1402E69FF
0x1402e69f2  mov     rax, [rcx]
0x1402e69f5  mov     rax, [rax+10h]
0x1402e69f9  call    _guard_dispatch_icall
0x1402e69fe  nop
0x1402e69ff  lea     rcx, [rbp+60h+pvarg]; pvarg
0x1402e6a03  call    cs:__imp_VariantClear
0x1402e6a09  nop
0x1402e6a0a  mov     rcx, [rbp+60h+var_88]
0x1402e6a0e  test    rcx, rcx
0x1402e6a11  jz      short loc_1402E6A20
0x1402e6a13  mov     rax, [rcx]
0x1402e6a16  mov     rax, [rax+10h]
0x1402e6a1a  call    _guard_dispatch_icall
0x1402e6a1f  nop
0x1402e6a20  mov     rax, [rbx]
0x1402e6a23  mov     rcx, rbx
0x1402e6a26  mov     rax, [rax+10h]
0x1402e6a2a  call    _guard_dispatch_icall
0x1402e6a2f  nop
0x1402e6a30  mov     rcx, [rbp+60h+var_80]
0x1402e6a34  test    rcx, rcx
0x1402e6a37  jz      short loc_1402E6A46
0x1402e6a39  mov     rax, [rcx]
0x1402e6a3c  mov     rax, [rax+10h]
0x1402e6a40  call    _guard_dispatch_icall
0x1402e6a45  nop
0x1402e6a46  mov     rcx, [rbp+60h+var_78]
0x1402e6a4a  test    rcx, rcx
0x1402e6a4d  jz      short loc_1402E6A5C
0x1402e6a4f  mov     rax, [rcx]
0x1402e6a52  mov     rax, [rax+10h]
0x1402e6a56  call    _guard_dispatch_icall
0x1402e6a5b  nop
0x1402e6a5c  mov     rcx, [rbp+60h+var_98]
0x1402e6a60  test    rcx, rcx
0x1402e6a63  jz      loc_1402E6BE0
0x1402e6a69  mov     rax, [rcx]
0x1402e6a6c  mov     rax, [rax+10h]
0x1402e6a70  jmp     loc_1402E6BDA
0x1402e6a75  mov     [rbp+60h+var_68], r13
0x1402e6a79  mov     rcx, [rbp+60h+var_98]
0x1402e6a7d  mov     rax, [rcx]
0x1402e6a80  mov     [rbp+60h+var_68], r13
0x1402e6a84  lea     r8, [rbp+60h+var_68]
0x1402e6a88  mov     rdx, [rbp+60h+var_90]
0x1402e6a8c  mov     rax, [rax+88h]
0x1402e6a93  call    _guard_dispatch_icall
0x1402e6a98  mov     rcx, [rbp+68h]; this
0x1402e6a9c  test    eax, eax
0x1402e6a9e  js      loc_1402E6CB2
0x1402e6aa4  mov     [rbp+60h+var_70], r13
0x1402e6aa8  mov     rcx, [rbp+60h+var_68]
0x1402e6aac  mov     rax, [rcx]
0x1402e6aaf  mov     [rbp+60h+var_70], r13
0x1402e6ab3  lea     r8, [rbp+60h+var_70]
0x1402e6ab7  xor     edx, edx
0x1402e6ab9  mov     rax, [rax+48h]
0x1402e6abd  call    _guard_dispatch_icall
0x1402e6ac2  mov     rcx, [rbp+68h]; this
0x1402e6ac6  test    eax, eax
0x1402e6ac8  js      loc_1402E6CC7
0x1402e6ace  mov     [rbp+60h+var_A0], r13d
0x1402e6ad2  mov     rcx, [rbp+60h+var_70]
0x1402e6ad6  mov     rax, [rcx]
0x1402e6ad9  lea     rdx, [rbp+60h+var_A0]
0x1402e6add  mov     rax, [rax+38h]
0x1402e6ae1  call    _guard_dispatch_icall
0x1402e6ae6  mov     rcx, [rbp+68h]; this
0x1402e6aea  test    eax, eax
0x1402e6aec  js      loc_1402E6C0A
0x1402e6af2  mov     cl, r13b
0x1402e6af5  mov     eax, [rbp+60h+var_A0]
0x1402e6af8  test    eax, eax
0x1402e6afa  js      short loc_1402E6B0C
0x1402e6afc  mov     rdx, r14; struct Windows::WU::DownloadProperties *
0x1402e6aff  mov     rcx, rdi; this
0x1402e6b02  call    ?IpuUpdate@WuUpdateInternalImpl@WU@Windows@@MEBA_NAEBUDownloadProperties@23@@Z; Windows::WU::WuUpdateInternalImpl::IpuUpdate(Windows::WU::DownloadProperties const &)
0x1402e6b07  mov     cl, al
0x1402e6b09  mov     eax, [rbp+60h+var_A0]
0x1402e6b0c  mov     dword ptr [rsp+160h+var_120], eax
0x1402e6b10  mov     byte ptr [rsp+160h+var_120+4], cl
0x1402e6b14  xor     eax, eax
0x1402e6b16  mov     word ptr [rsp+160h+var_120+5], ax
0x1402e6b1b  mov     byte ptr [rsp+160h+var_120+7], al
0x1402e6b1f  mov     rax, [rsp+160h+var_120]
0x1402e6b24  mov     [rsi], rax
0x1402e6b27  mov     byte ptr [rsi+8], 1
0x1402e6b2b  mov     rcx, [rbp+60h+var_70]
0x1402e6b2f  test    rcx, rcx
0x1402e6b32  jz      short loc_1402E6B41
0x1402e6b34  mov     rax, [rcx]
0x1402e6b37  mov     rax, [rax+10h]
0x1402e6b3b  call    _guard_dispatch_icall
0x1402e6b40  nop
0x1402e6b41  mov     rcx, [rbp+60h+var_68]
0x1402e6b45  test    rcx, rcx
0x1402e6b48  jz      short loc_1402E6B57
0x1402e6b4a  mov     rax, [rcx]
0x1402e6b4d  mov     rax, [rax+10h]
0x1402e6b51  call    _guard_dispatch_icall
0x1402e6b56  nop
0x1402e6b57  mov     rcx, [rbp+60h+var_90]
0x1402e6b5b  test    rcx, rcx
0x1402e6b5e  jz      short loc_1402E6B6D
0x1402e6b60  mov     rax, [rcx]
0x1402e6b63  mov     rax, [rax+10h]
0x1402e6b67  call    _guard_dispatch_icall
0x1402e6b6c  nop
0x1402e6b6d  lea     rcx, [rbp+60h+pvarg]; pvarg
0x1402e6b71  call    cs:__imp_VariantClear
0x1402e6b77  nop
0x1402e6b78  mov     rcx, [rbp+60h+var_88]
  ... truncated ...
```
