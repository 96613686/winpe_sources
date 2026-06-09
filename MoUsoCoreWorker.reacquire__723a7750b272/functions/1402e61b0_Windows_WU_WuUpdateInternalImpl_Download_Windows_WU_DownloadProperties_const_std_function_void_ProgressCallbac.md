# Windows::WU::WuUpdateInternalImpl::Download(Windows::WU::DownloadProperties const &,std::function<void (ProgressCallbackData)> const &)

- ea: `0x1402e61b0`
- end: `0x1402e66fb`
- name: `?Download@WuUpdateInternalImpl@WU@Windows@@UEAA?AV?$optional@UDownloadResult@WU@Windows@@@std@@AEBUDownloadProperties@23@AEBV?$function@$$A6AXUProgressCallbackData@@@Z@5@@Z`
- size: `1355`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1400413a8`
- `0x140045404`
- `0x140071f48`
- `0x1402e3bd0`
- `0x1402e61b0`
- `0x1402e6ce4`
- `0x1402eb970`
- `0x1402ec8ec`
- `0x1402ec95c`
- `0x140379070`
- `0x1403790d8`
- `0x140380b50`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1402e6373`
- `OLEAUT32!__imp_VariantInit` at `0x1402e6373`
- `OLEAUT32!__imp_VariantClear` at `0x1402e6463`
- `OLEAUT32!__imp_VariantClear` at `0x1402e65bb`
- `OLEAUT32!__imp_VariantClear` at `0x1402e6463`
- `OLEAUT32!__imp_VariantClear` at `0x1402e65bb`

## string_xrefs

- `0x1402e6641`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402e6656`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402e666b`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402e6680`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402e6695`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402e66aa`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402e66bf`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402e66d4`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`
- `0x1402e66e9`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\WuUpdateInternalImpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall Windows::WU::WuUpdateInternalImpl::Download(
        Windows::WU::WuUpdateInternalImpl *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int v8; // eax
  struct _GUID *updated; // rax
  const wchar_t *v10; // r8
  __int64 (__fastcall **v11)(__int64 *, GUID *, __int64 *); // rax
  int v12; // eax
  int v13; // eax
  _OWORD *v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rax
  int v18; // eax
  int v19; // eax
  __int64 v20; // rax
  int v21; // eax
  void (*v22)(void); // rax
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rax
  int v26; // eax
  int v27; // eax
  bool v28; // cl
  int v29; // eax
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+20h] [rbp-E0h]
  __int64 v33; // [rsp+30h] [rbp-D0h]
  VARIANTARG v34; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD *v35; // [rsp+60h] [rbp-A0h] BYREF
  __int64 (__fastcall **v36)(); // [rsp+70h] [rbp-90h] BYREF
  __int128 v37; // [rsp+78h] [rbp-88h]
  __int64 (__fastcall ***v38)(); // [rsp+A8h] [rbp-58h]
  int v39; // [rsp+B0h] [rbp-50h] BYREF
  __int64 *v40; // [rsp+B8h] [rbp-48h] BYREF
  int v41[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v42; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v43; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v44; // [rsp+D8h] [rbp-28h] BYREF
  __int64 *v45; // [rsp+E0h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v47; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v40 = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(**((_QWORD **)this + 14) + 104LL))(*((_QWORD *)this + 14), &v40);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2AA,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
      (const char *)(unsigned int)v8,
      v31);
  updated = (struct _GUID *)Windows::WU::WuUpdateInternalImpl::UpdateId(this, &v34);
  if ( *(_QWORD *)updated[1].Data4 > 7u )
    updated = *(struct _GUID **)&updated->Data1;
  v47 = (__int128)*Windows::Strings::to_guid((Windows::Strings *)&v35, updated, v10);
  std::wstring::~wstring(&v34);
  v43 = 0;
  v11 = (__int64 (__fastcall **)(__int64 *, GUID *, __int64 *))*v40;
  v43 = 0;
  v12 = (*v11)(v40, &GUID_d7708661_fce5_4317_852b_bbc9a95edcab, &v43);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2AF,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
      (const char *)(unsigned int)v12,
      v31);
  v13 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)v43 + 24LL))(
          v43,
          &v47,
          *(unsigned int *)(a3 + 44));
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2B0,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
      (const char *)(unsigned int)v13,
      v31);
  Windows::WU::WuUpdateInternalImpl::SetDownloadProperties((__int64)this, (__int64 *)a3, (OLECHAR *)&v40);
  v14 = operator new(0x30u);
  *(_QWORD *)&v34.vt = v14;
  *v14 = 0;
  v14[1] = 0;
  v14[2] = 0;
  v15 = 0;
  v16 = 0;
  v17 = *((_QWORD *)this + 3);
  if ( v17 )
  {
    v15 = *((_QWORD *)this + 2);
    v16 = *((_QWORD *)this + 3);
    _InterlockedIncrement((volatile signed __int32 *)(v17 + 12));
  }
  *(_QWORD *)v14 = &Windows::WU::WuCallback<IDownloadProgressChangedCallback,IDownloadCompletedCallback,IDownloadJob,IDownloadProgressChangedCallbackArgs,IDownloadCompletedCallbackArgs>::`vftable'{for `IDownloadProgressChangedCallback'};
  *((_QWORD *)v14 + 1) = &Windows::WU::WuCallback<IDownloadProgressChangedCallback,IDownloadCompletedCallback,IDownloadJob,IDownloadProgressChangedCallbackArgs,IDownloadCompletedCallbackArgs>::`vftable'{for `IDownloadCompletedCallback'};
  *((_WORD *)v14 + 8) = 0;
  *((_QWORD *)v14 + 3) = v15;
  *((_QWORD *)v14 + 4) = v16;
  *((_DWORD *)v14 + 10) = 0;
  v35 = v14;
  (*(void (__fastcall **)(_OWORD *))(*(_QWORD *)v14 + 8LL))(v14);
  v42 = 0;
  wil::CoCreateInstance<UpdateCollection,IUpdateCollection,wil::err_exception_policy>(&v42);
  v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v42 + 96LL))(v42, *((_QWORD *)this + 15), 0);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2B7,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
      (const char *)(unsigned int)v18,
      v31);
  v19 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v40 + 112))(v40, v42);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2B9,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
      (const char *)(unsigned int)v19,
      v31);
  VariantInit(&pvarg);
  *(_QWORD *)v41 = 0;
  v20 = *v40;
  *(_QWORD *)v41 = 0;
  v34 = pvarg;
  v21 = (*(__int64 (__fastcall **)(__int64 *, _OWORD *, __int64, VARIANTARG *))(v20 + 120))(
          v40,
          v14,
          (__int64)v14 + 8,
          &v34);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2C1,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
      (const char *)(unsigned int)v21,
      (int)v41);
  *(_QWORD *)&v34.vt = a4;
  v34.llVal = (LONGLONG)this;
  v36 = off_1403D7088;
  v37 = *(_OWORD *)&v34.vt;
  v38 = &v36;
  (*(void (__fastcall **)(_OWORD *))(*(_QWORD *)v14 + 8LL))(v14);
  *(_QWORD *)&v34.vt = *(_QWORD *)v41;
  if ( *(_QWORD *)v41 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v41 + 8LL))(*(_QWORD *)v41);
  if ( (unsigned __int8)Windows::WU::WuUpdateInternalImpl::WaitForCompletion<IInstallationJob,Windows::WU::WuCallback<IInstallationProgressChangedCallback,IInstallationCompletedCallback,IInstallationJob,IInstallationProgressChangedCallbackArgs,IInstallationCompletedCallbackArgs>,IInstallationProgress>(
                          this,
                          a3 + 96) )
  {
    v45 = 0;
    v23 = *v40;
    v45 = 0;
    v24 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 **))(v23 + 136))(v40, *(_QWORD *)v41, &v45);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2CD,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)(unsigned int)v24,
        v32);
    v44 = 0;
    v25 = *v45;
    v44 = 0;
    v26 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v25 + 72))(v45, 0, &v44);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2D0,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)(unsigned int)v26,
        v32);
    v39 = 0;
    v27 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v44 + 56LL))(v44, &v39);
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2D3,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\WuUpdateInternalImpl.cpp",
        (const char *)(unsigned int)v27,
        v32);
    v28 = 0;
    v29 = v39;
    if ( v39 >= 0 )
    {
      v28 = Windows::WU::WuUpdateInternalImpl::IpuUpdate(this, (const struct Windows::WU::DownloadProperties *)a3);
      v29 = v39;
    }
    LODWORD(v33) = v29;
    BYTE4(v33) = v28;
    *(_WORD *)((char *)&v33 + 5) = 0;
    HIBYTE(v33) = 0;
    *(_QWORD *)a2 = v33;
    *(_BYTE *)(a2 + 8) = 1;
    if ( v44 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    if ( v45 )
      (*(void (__fastcall **)(__int64 *))(*v45 + 16))(v45);
    if ( *(_QWORD *)v41 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v41 + 16LL))(*(_QWORD *)v41);
    VariantClear(&pvarg);
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    (*(void (__fastcall **)(_OWORD *))(*(_QWORD *)v14 + 16LL))(v14);
    if ( v43 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    if ( v40 )
    {
      v22 = *(void (**)(void))(*v40 + 16);
      goto LABEL_39;
    }
  }
  else
  {
    *(_BYTE *)(a2 + 8) = 0;
    if ( *(_QWORD *)v41 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v41 + 16LL))(*(_QWORD *)v41);
    VariantClear(&pvarg);
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    (*(void (__fastcall **)(_OWORD *))(*(_QWORD *)v14 + 16LL))(v14);
    if ( v43 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    if ( v40 )
    {
      v22 = *(void (**)(void))(*v40 + 16);
LABEL_39:
      v22();
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1402e61b0  mov     [rsp-8+arg_18], rbx
0x1402e61b5  push    rbp
0x1402e61b6  push    rsi
0x1402e61b7  push    rdi
0x1402e61b8  push    r12
0x1402e61ba  push    r13
0x1402e61bc  push    r14
0x1402e61be  push    r15
0x1402e61c0  lea     rbp, [rsp-20h]
0x1402e61c5  sub     rsp, 120h
0x1402e61cc  mov     rax, cs:__security_cookie
0x1402e61d3  xor     rax, rsp
0x1402e61d6  mov     [rbp+50h+var_40], rax
0x1402e61da  mov     r12, r9
0x1402e61dd  mov     r14, r8
0x1402e61e0  mov     rsi, rdx
0x1402e61e3  mov     rdi, rcx
0x1402e61e6  xor     r13d, r13d
0x1402e61e9  mov     [rbp+50h+var_98], r13
0x1402e61ed  mov     rcx, [rcx+70h]
0x1402e61f1  mov     rax, [rcx]
0x1402e61f4  mov     [rbp+50h+var_98], r13
0x1402e61f8  lea     rdx, [rbp+50h+var_98]
0x1402e61fc  mov     rax, [rax+68h]
0x1402e6200  call    _guard_dispatch_icall
0x1402e6205  mov     rcx, [rbp+58h]; this
0x1402e6209  test    eax, eax
0x1402e620b  js      loc_1402E6653
0x1402e6211  lea     rdx, [rsp+150h+var_110]
0x1402e6216  mov     rcx, rdi
0x1402e6219  call    ?UpdateId@WuUpdateInternalImpl@WU@Windows@@UEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Windows::WU::WuUpdateInternalImpl::UpdateId(void)
0x1402e621e  nop
0x1402e621f  cmp     qword ptr [rax+18h], 7
0x1402e6224  jbe     short loc_1402E6229
0x1402e6226  mov     rax, [rax]
0x1402e6229  mov     rdx, rax; retstr
0x1402e622c  lea     rcx, [rsp+150h+var_F0]; this
0x1402e6231  call    ?to_guid@Strings@Windows@@YA?AU_GUID@@PEB_W@Z; Windows::Strings::to_guid(wchar_t const *)
0x1402e6236  movups  xmm0, xmmword ptr [rax]
0x1402e6239  movdqu  [rbp+50h+var_50], xmm0
0x1402e623e  lea     rcx, [rsp+150h+var_110]
0x1402e6243  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402e6248  mov     [rbp+50h+var_80], r13
0x1402e624c  mov     rcx, [rbp+50h+var_98]
0x1402e6250  mov     rax, [rcx]
0x1402e6253  mov     [rbp+50h+var_80], r13
0x1402e6257  lea     r8, [rbp+50h+var_80]
0x1402e625b  lea     rdx, _GUID_d7708661_fce5_4317_852b_bbc9a95edcab
0x1402e6262  mov     rax, [rax]
0x1402e6265  call    _guard_dispatch_icall
0x1402e626a  mov     rcx, [rbp+58h]; this
0x1402e626e  test    eax, eax
0x1402e6270  js      loc_1402E6668
0x1402e6276  mov     rcx, [rbp+50h+var_80]
0x1402e627a  mov     rax, [rcx]
0x1402e627d  mov     r8d, [r14+2Ch]
0x1402e6281  lea     rdx, [rbp+50h+var_50]
0x1402e6285  mov     rax, [rax+18h]
0x1402e6289  call    _guard_dispatch_icall
0x1402e628e  mov     rcx, [rbp+58h]; this
0x1402e6292  test    eax, eax
0x1402e6294  js      loc_1402E667D
0x1402e629a  lea     r8, [rbp+50h+var_98]
0x1402e629e  mov     rdx, r14
0x1402e62a1  mov     rcx, rdi
0x1402e62a4  call    ?SetDownloadProperties@WuUpdateInternalImpl@WU@Windows@@AEAAXAEBUDownloadProperties@23@AEBV?$com_ptr_t@UIUpdateDownloader@@Uerr_exception_policy@wil@@@wil@@@Z; Windows::WU::WuUpdateInternalImpl::SetDownloadProperties(Windows::WU::DownloadProperties const &,wil::com_ptr_t<IUpdateDownloader,wil::err_exception_policy> const &)
0x1402e62a9  mov     ecx, 30h ; '0'; Size
0x1402e62ae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1402e62b3  mov     rbx, rax
0x1402e62b6  mov     qword ptr [rsp+150h+var_110], rax
0x1402e62bb  xorps   xmm0, xmm0
0x1402e62be  movups  xmmword ptr [rax], xmm0
0x1402e62c1  movups  xmmword ptr [rax+10h], xmm0
0x1402e62c5  movups  xmmword ptr [rax+20h], xmm0
0x1402e62c9  mov     rcx, r13
0x1402e62cc  mov     rdx, r13
0x1402e62cf  mov     rax, [rdi+18h]
0x1402e62d3  test    rax, rax
0x1402e62d6  jz      short loc_1402E62E3
0x1402e62d8  mov     rcx, [rdi+10h]
0x1402e62dc  mov     rdx, rax
0x1402e62df  lock inc dword ptr [rax+0Ch]
0x1402e62e3  lea     rax, ??_7?$WuCallback@UIDownloadProgressChangedCallback@@UIDownloadCompletedCallback@@UIDownloadJob@@UIDownloadProgressChangedCallbackArgs@@UIDownloadCompletedCallbackArgs@@@WU@Windows@@6BIDownloadProgressChangedCallback@@@; const Windows::WU::WuCallback<IDownloadProgressChangedCallback,IDownloadCompletedCallback,IDownloadJob,IDownloadProgressChangedCallbackArgs,IDownloadCompletedCallbackArgs>::`vftable'{for `IDownloadProgressChangedCallback'}
0x1402e62ea  mov     [rbx], rax
0x1402e62ed  lea     rax, ??_7?$WuCallback@UIDownloadProgressChangedCallback@@UIDownloadCompletedCallback@@UIDownloadJob@@UIDownloadProgressChangedCallbackArgs@@UIDownloadCompletedCallbackArgs@@@WU@Windows@@6BIDownloadCompletedCallback@@@; const Windows::WU::WuCallback<IDownloadProgressChangedCallback,IDownloadCompletedCallback,IDownloadJob,IDownloadProgressChangedCallbackArgs,IDownloadCompletedCallbackArgs>::`vftable'{for `IDownloadCompletedCallback'}
0x1402e62f4  mov     [rbx+8], rax
0x1402e62f8  mov     [rbx+10h], r13w
0x1402e62fd  mov     [rbx+18h], rcx
0x1402e6301  mov     [rbx+20h], rdx
0x1402e6305  mov     [rbx+28h], r13d
0x1402e6309  mov     [rsp+150h+var_F0], rbx
0x1402e630e  mov     rax, [rbx]
0x1402e6311  mov     rcx, rbx
0x1402e6314  mov     rax, [rax+8]
0x1402e6318  call    _guard_dispatch_icall
0x1402e631d  nop
0x1402e631e  mov     [rbp+50h+var_88], r13
0x1402e6322  lea     rcx, [rbp+50h+var_88]
0x1402e6326  call    ??$CoCreateInstance@VUpdateCollection@@UIUpdateCollection@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIUpdateCollection@@Uerr_exception_policy@wil@@@0@K@Z; wil::CoCreateInstance<UpdateCollection,IUpdateCollection,wil::err_exception_policy>(ulong)
0x1402e632b  nop
0x1402e632c  mov     rcx, [rbp+50h+var_88]
0x1402e6330  mov     rax, [rcx]
0x1402e6333  xor     r8d, r8d
0x1402e6336  mov     rdx, [rdi+78h]
0x1402e633a  mov     rax, [rax+60h]
0x1402e633e  call    _guard_dispatch_icall
0x1402e6343  mov     rcx, [rbp+58h]; this
0x1402e6347  test    eax, eax
0x1402e6349  js      loc_1402E6692
0x1402e634f  mov     rcx, [rbp+50h+var_98]
0x1402e6353  mov     rax, [rcx]
0x1402e6356  mov     rdx, [rbp+50h+var_88]
0x1402e635a  mov     rax, [rax+70h]
0x1402e635e  call    _guard_dispatch_icall
0x1402e6363  mov     rcx, [rbp+58h]; this
0x1402e6367  test    eax, eax
0x1402e6369  js      loc_1402E66A7
0x1402e636f  lea     rcx, [rbp+50h+pvarg]; pvarg
0x1402e6373  call    cs:__imp_VariantInit
0x1402e6379  nop
0x1402e637a  mov     qword ptr [rbp+50h+var_90], r13
0x1402e637e  mov     rcx, [rbp+50h+var_98]
0x1402e6382  mov     rax, [rcx]
0x1402e6385  mov     qword ptr [rbp+50h+var_90], r13
0x1402e6389  movups  xmm0, xmmword ptr [rbp+50h+pvarg]
0x1402e638d  movaps  [rsp+150h+var_110], xmm0
0x1402e6392  movsd   xmm1, qword ptr [rbp+50h+pvarg+10h]
0x1402e6397  movsd   [rsp+150h+var_100], xmm1
0x1402e639d  lea     rdx, [rbp+50h+var_90]
0x1402e63a1  mov     qword ptr [rsp+150h+var_130], rdx; int
0x1402e63a6  lea     r9, [rsp+150h+var_110]
0x1402e63ab  lea     r8, [rbx+8]
0x1402e63af  mov     rdx, rbx
0x1402e63b2  mov     rax, [rax+78h]
0x1402e63b6  call    _guard_dispatch_icall
0x1402e63bb  mov     rcx, [rbp+58h]; this
0x1402e63bf  test    eax, eax
0x1402e63c1  js      loc_1402E66BC
0x1402e63c7  mov     qword ptr [rsp+150h+var_110], r12
0x1402e63cc  mov     qword ptr [rsp+150h+var_110+8], rdi
0x1402e63d1  lea     rax, off_1403D7088
0x1402e63d8  mov     [rsp+150h+var_E0], rax
0x1402e63dd  movups  xmm0, [rsp+150h+var_110]
0x1402e63e2  movdqu  [rsp+150h+var_D8], xmm0
0x1402e63e8  lea     rax, [rsp+150h+var_E0]
0x1402e63ed  mov     [rbp+50h+var_A8], rax
0x1402e63f1  mov     [rsp+150h+var_120], rbx
0x1402e63f6  mov     rax, [rbx]
0x1402e63f9  mov     rcx, rbx
0x1402e63fc  mov     rax, [rax+8]
0x1402e6400  call    _guard_dispatch_icall
0x1402e6405  nop
0x1402e6406  mov     rcx, qword ptr [rbp+50h+var_90]
0x1402e640a  mov     qword ptr [rsp+150h+var_110], rcx
0x1402e640f  test    rcx, rcx
0x1402e6412  jz      short loc_1402E6421
0x1402e6414  mov     rax, [rcx]
0x1402e6417  mov     rax, [rax+8]
0x1402e641b  call    _guard_dispatch_icall
0x1402e6420  nop
0x1402e6421  lea     rax, [r14+60h]
0x1402e6425  mov     qword ptr [rsp+150h+var_130], rax; int
0x1402e642a  lea     r9, [rsp+150h+var_E0]
0x1402e642f  lea     r8, [rsp+150h+var_120]
0x1402e6434  lea     rdx, [rsp+150h+var_110]
0x1402e6439  mov     rcx, rdi
0x1402e643c  call    ??$WaitForCompletion@UIInstallationJob@@V?$WuCallback@UIInstallationProgressChangedCallback@@UIInstallationCompletedCallback@@UIInstallationJob@@UIInstallationProgressChangedCallbackArgs@@UIInstallationCompletedCallbackArgs@@@WU@Windows@@UIInstallationProgress@@@WuUpdateInternalImpl@WU@Windows@@AEAA_NV?$com_ptr_t@UIInstallationJob@@Uerr_exception_policy@wil@@@wil@@V?$com_ptr_t@V?$WuCallback@UIInstallationProgressChangedCallback@@UIInstallationCompletedCallback@@UIInstallationJob@@UIInstallationProgressChangedCallbackArgs@@UIInstallationCompletedCallbackArgs@@@WU@Windows@@Uerr_exception_policy@wil@@@4@V?$function@$$A6AXV?$com_ptr_t@UIInstallationProgress@@Uerr_exception_policy@wil@@@wil@@@Z@std@@AEBV?$duration@HU?$ratio@$0DM@$00@std@@@chrono@7@@Z; Windows::WU::WuUpdateInternalImpl::WaitForCompletion<IInstallationJob,Windows::WU::WuCallback<IInstallationProgressChangedCallback,IInstallationCompletedCallback,IInstallationJob,IInstallationProgressChangedCallbackArgs,IInstallationCompletedCallbackArgs>,IInstallationProgress>(wil::com_ptr_t<IInstallationJob,wil::err_exception_policy>,wil::com_ptr_t<Windows::WU::WuCallback<IInstallationProgressChangedCallback,IInstallationCompletedCallback,IInstallationJob,IInstallationProgressChangedCallbackArgs,IInstallationCompletedCallbackArgs>,wil::err_exception_policy>,std::function<void (wil::com_ptr_t<IInstallationProgress,wil::err_exception_policy>)>,std::chrono::duration<int,std::ratio<60,1>> const &)
0x1402e6441  test    al, al
0x1402e6443  jnz     short loc_1402E64BF
0x1402e6445  mov     [rsi+8], r13b
0x1402e6449  mov     rcx, qword ptr [rbp+50h+var_90]
0x1402e644d  test    rcx, rcx
0x1402e6450  jz      short loc_1402E645F
0x1402e6452  mov     rax, [rcx]
0x1402e6455  mov     rax, [rax+10h]
0x1402e6459  call    _guard_dispatch_icall
0x1402e645e  nop
0x1402e645f  lea     rcx, [rbp+50h+pvarg]; pvarg
0x1402e6463  call    cs:__imp_VariantClear
0x1402e6469  nop
0x1402e646a  mov     rcx, [rbp+50h+var_88]
0x1402e646e  test    rcx, rcx
0x1402e6471  jz      short loc_1402E6480
0x1402e6473  mov     rax, [rcx]
0x1402e6476  mov     rax, [rax+10h]
0x1402e647a  call    _guard_dispatch_icall
0x1402e647f  nop
0x1402e6480  mov     rax, [rbx]
0x1402e6483  mov     rcx, rbx
0x1402e6486  mov     rax, [rax+10h]
0x1402e648a  call    _guard_dispatch_icall
0x1402e648f  nop
0x1402e6490  mov     rcx, [rbp+50h+var_80]
0x1402e6494  test    rcx, rcx
0x1402e6497  jz      short loc_1402E64A6
0x1402e6499  mov     rax, [rcx]
0x1402e649c  mov     rax, [rax+10h]
0x1402e64a0  call    _guard_dispatch_icall
0x1402e64a5  nop
0x1402e64a6  mov     rcx, [rbp+50h+var_98]
0x1402e64aa  test    rcx, rcx
0x1402e64ad  jz      loc_1402E6614
0x1402e64b3  mov     rax, [rcx]
0x1402e64b6  mov     rax, [rax+10h]
0x1402e64ba  jmp     loc_1402E660E
0x1402e64bf  mov     [rbp+50h+var_70], r13
0x1402e64c3  mov     rcx, [rbp+50h+var_98]
0x1402e64c7  mov     rax, [rcx]
0x1402e64ca  mov     [rbp+50h+var_70], r13
0x1402e64ce  lea     r8, [rbp+50h+var_70]
0x1402e64d2  mov     rdx, qword ptr [rbp+50h+var_90]
0x1402e64d6  mov     rax, [rax+88h]
0x1402e64dd  call    _guard_dispatch_icall
0x1402e64e2  mov     rcx, [rbp+58h]; this
0x1402e64e6  test    eax, eax
0x1402e64e8  js      loc_1402E66D1
0x1402e64ee  mov     [rbp+50h+var_78], r13
0x1402e64f2  mov     rcx, [rbp+50h+var_70]
0x1402e64f6  mov     rax, [rcx]
0x1402e64f9  mov     [rbp+50h+var_78], r13
0x1402e64fd  lea     r8, [rbp+50h+var_78]
0x1402e6501  xor     edx, edx
0x1402e6503  mov     rax, [rax+48h]
0x1402e6507  call    _guard_dispatch_icall
0x1402e650c  mov     rcx, [rbp+58h]; this
0x1402e6510  test    eax, eax
0x1402e6512  js      loc_1402E66E6
0x1402e6518  mov     [rbp+50h+var_A0], r13d
0x1402e651c  mov     rcx, [rbp+50h+var_78]
0x1402e6520  mov     rax, [rcx]
0x1402e6523  lea     rdx, [rbp+50h+var_A0]
0x1402e6527  mov     rax, [rax+38h]
0x1402e652b  call    _guard_dispatch_icall
0x1402e6530  mov     rcx, [rbp+58h]; this
0x1402e6534  test    eax, eax
0x1402e6536  js      loc_1402E663E
0x1402e653c  mov     cl, r13b
0x1402e653f  mov     eax, [rbp+50h+var_A0]
0x1402e6542  test    eax, eax
0x1402e6544  js      short loc_1402E6556
0x1402e6546  mov     rdx, r14; struct Windows::WU::DownloadProperties *
0x1402e6549  mov     rcx, rdi; this
0x1402e654c  call    ?IpuUpdate@WuUpdateInternalImpl@WU@Windows@@MEBA_NAEBUDownloadProperties@23@@Z; Windows::WU::WuUpdateInternalImpl::IpuUpdate(Windows::WU::DownloadProperties const &)
0x1402e6551  mov     cl, al
0x1402e6553  mov     eax, [rbp+50h+var_A0]
0x1402e6556  mov     dword ptr [rsp+150h+var_120], eax
0x1402e655a  mov     byte ptr [rsp+150h+var_120+4], cl
0x1402e655e  xor     eax, eax
0x1402e6560  mov     word ptr [rsp+150h+var_120+5], ax
0x1402e6565  mov     byte ptr [rsp+150h+var_120+7], al
0x1402e6569  mov     rax, [rsp+150h+var_120]
0x1402e656e  mov     [rsi], rax
0x1402e6571  mov     byte ptr [rsi+8], 1
0x1402e6575  mov     rcx, [rbp+50h+var_78]
0x1402e6579  test    rcx, rcx
0x1402e657c  jz      short loc_1402E658B
0x1402e657e  mov     rax, [rcx]
0x1402e6581  mov     rax, [rax+10h]
0x1402e6585  call    _guard_dispatch_icall
0x1402e658a  nop
0x1402e658b  mov     rcx, [rbp+50h+var_70]
0x1402e658f  test    rcx, rcx
0x1402e6592  jz      short loc_1402E65A1
0x1402e6594  mov     rax, [rcx]
0x1402e6597  mov     rax, [rax+10h]
0x1402e659b  call    _guard_dispatch_icall
0x1402e65a0  nop
0x1402e65a1  mov     rcx, qword ptr [rbp+50h+var_90]
0x1402e65a5  test    rcx, rcx
0x1402e65a8  jz      short loc_1402E65B7
0x1402e65aa  mov     rax, [rcx]
0x1402e65ad  mov     rax, [rax+10h]
0x1402e65b1  call    _guard_dispatch_icall
0x1402e65b6  nop
0x1402e65b7  lea     rcx, [rbp+50h+pvarg]; pvarg
0x1402e65bb  call    cs:__imp_VariantClear
0x1402e65c1  nop
0x1402e65c2  mov     rcx, [rbp+50h+var_88]
0x1402e65c6  test    rcx, rcx
0x1402e65c9  jz      short loc_1402E65D8
0x1402e65cb  mov     rax, [rcx]
0x1402e65ce  mov     rax, [rax+10h]
0x1402e65d2  call    _guard_dispatch_icall
0x1402e65d7  nop
0x1402e65d8  mov     rax, [rbx]
0x1402e65db  mov     rcx, rbx
0x1402e65de  mov     rax, [rax+10h]
0x1402e65e2  call    _guard_dispatch_icall
0x1402e65e7  nop
0x1402e65e8  mov     rcx, [rbp+50h+var_80]
0x1402e65ec  test    rcx, rcx
0x1402e65ef  jz      short loc_1402E65FE
0x1402e65f1  mov     rax, [rcx]
0x1402e65f4  mov     rax, [rax+10h]
0x1402e65f8  call    _guard_dispatch_icall
0x1402e65fd  nop
0x1402e65fe  mov     rcx, [rbp+50h+var_98]
0x1402e6602  test    rcx, rcx
0x1402e6605  jz      short loc_1402E6614
0x1402e6607  mov     rdx, [rcx]
  ... truncated ...
```
