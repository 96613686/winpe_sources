# UiaManagerCrossMachineStub::GetHwndInfo(HWND__ *,CrossMachineHwndInfo *)

- ea: `0x180017100`
- end: `0x1800175ef`
- name: `?GetHwndInfo@UiaManagerCrossMachineStub@@UEAAJPEAUHWND__@@PEAUCrossMachineHwndInfo@@@Z`
- size: `1263`
- prototype: `int(UiaManagerCrossMachineStub *__hidden this, HWND, struct CrossMachineHwndInfo *)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x18000fb78`
- `0x18000fe00`
- `0x180012240`
- `0x180012484`
- `0x180016c4c`
- `0x180017100`
- `0x180024a40`
- `0x180031540`
- `0x180043680`
- `0x18005da18`
- `0x180064564`
- `0x180065d20`
- `0x1800660a8`
- `0x180068070`
- `0x180091010`

## string_xrefs

- `0x1800171fc`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`
- `0x18001724a`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`
- `0x180017286`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`
- `0x1800172d6`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`
- `0x18001731c`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`
- `0x180017374`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`
- `0x1800173b3`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`
- `0x1800173e8`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`
- `0x180017430`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachinestub.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall UiaManagerCrossMachineStub::GetHwndInfo(
        UiaManagerCrossMachineStub *this,
        HWND a2,
        struct CrossMachineHwndInfo *a3)
{
  UiaManagerCrossMachineStub *v6; // rdi
  char *v7; // r14
  int v8; // eax
  __int64 (__fastcall *v9)(UiaManagerCrossMachineStub *, HWND, __int64 **); // rbx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int CanUiaSynthesizeNonClientAreaProvider; // eax
  int v17; // eax
  __int64 *v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rax
  int v23; // [rsp+20h] [rbp-288h]
  int v24; // [rsp+30h] [rbp-278h] BYREF
  unsigned int v25; // [rsp+34h] [rbp-274h] BYREF
  unsigned int v26; // [rsp+38h] [rbp-270h] BYREF
  int v27; // [rsp+3Ch] [rbp-26Ch] BYREF
  int v28; // [rsp+40h] [rbp-268h] BYREF
  int v29; // [rsp+44h] [rbp-264h] BYREF
  int v30; // [rsp+48h] [rbp-260h] BYREF
  int v31; // [rsp+4Ch] [rbp-25Ch] BYREF
  __int64 *v32; // [rsp+50h] [rbp-258h] BYREF
  __int128 v33; // [rsp+58h] [rbp-250h] BYREF
  __int64 v34; // [rsp+68h] [rbp-240h] BYREF
  __int64 v35; // [rsp+70h] [rbp-238h]
  __int64 v36; // [rsp+78h] [rbp-230h]
  __int64 v37; // [rsp+80h] [rbp-228h] BYREF
  __int128 v38; // [rsp+88h] [rbp-220h] BYREF
  __int64 v39; // [rsp+98h] [rbp-210h]
  __int64 v40; // [rsp+A0h] [rbp-208h]
  __int64 v41; // [rsp+A8h] [rbp-200h]
  __int128 v42; // [rsp+B0h] [rbp-1F8h]
  __int64 v43; // [rsp+C0h] [rbp-1E8h]
  __int128 v44; // [rsp+C8h] [rbp-1E0h]
  __int128 v45; // [rsp+D8h] [rbp-1D0h]
  __int64 v46; // [rsp+E8h] [rbp-1C0h]
  __int128 v47; // [rsp+F0h] [rbp-1B8h]
  char v48; // [rsp+100h] [rbp-1A8h]
  int v49; // [rsp+104h] [rbp-1A4h]
  __int128 v50; // [rsp+110h] [rbp-198h] BYREF
  _BYTE v51[336]; // [rsp+120h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 7;
  LOWORD(v38) = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v48 = 0;
  v49 = 0;
  CrossMachineHwndInfo::operator=(a3, &v37);
  GetHwndInfoService::ResponsePayload::~ResponsePayload((GetHwndInfoService::ResponsePayload *)&v37);
  UiaManagerTraceLoggingProvider::CrossMachineStubGetHwndInfoActivity::CrossMachineStubGetHwndInfoActivity((UiaManagerTraceLoggingProvider::CrossMachineStubGetHwndInfoActivity *)v51);
  v25 = 0;
  v6 = (UiaManagerCrossMachineStub *)((char *)this - 16);
  v7 = (char *)this - 72;
  v8 = (*(__int64 (__fastcall **)(char *, HWND, unsigned int *))(*((_QWORD *)this - 2) + 24LL))(
         (char *)this - 16,
         a2,
         &v25);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2CC,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
      (const char *)(unsigned int)v8,
      v23);
  v32 = 0;
  v9 = *(__int64 (__fastcall **)(UiaManagerCrossMachineStub *, HWND, __int64 **))(*(_QWORD *)v6 + 144LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v32,
    0);
  v10 = v9(v6, a2, &v32);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2CF,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
      (const char *)(unsigned int)v10,
      v23);
  v26 = 0;
  v11 = (*(__int64 (__fastcall **)(UiaManagerCrossMachineStub *, HWND, unsigned int *))(*(_QWORD *)v6 + 48LL))(
          v6,
          a2,
          &v26);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2D2,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
      (const char *)(unsigned int)v11,
      v23);
  UiaManagerCrossMachineStub::GetHwndPropertyValues(v7, &v34, a2);
  v27 = 0;
  v12 = (*(__int64 (__fastcall **)(UiaManagerCrossMachineStub *, HWND, int *))(*(_QWORD *)v6 + 168LL))(v6, a2, &v27);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2D7,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
      (const char *)(unsigned int)v12,
      v23);
  v33 = 0u;
  v13 = (*(__int64 (__fastcall **)(UiaManagerCrossMachineStub *, HWND, __int128 *, char *))(*(_QWORD *)v6 + 56LL))(
          v6,
          a2,
          &v33,
          (char *)&v33 + 8);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2DB,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
      (const char *)(unsigned int)v13,
      v23);
  v24 = 0;
  v28 = 0;
  v29 = 0;
  v14 = (*(__int64 (__fastcall **)(UiaManagerCrossMachineStub *, HWND, int *, int *))(*(_QWORD *)v6 + 152LL))(
          v6,
          a2,
          &v24,
          &v28);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2E0,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
      (const char *)(unsigned int)v14,
      (int)&v29);
  v30 = 0;
  v15 = (*(__int64 (__fastcall **)(UiaManagerCrossMachineStub *, HWND, int *))(*(_QWORD *)v6 + 160LL))(v6, a2, &v30);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2E3,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
      (const char *)(unsigned int)v15,
      (int)&v29);
  v31 = 0;
  CanUiaSynthesizeNonClientAreaProvider = UiaManagerCrossMachineStub::GetCanUiaSynthesizeNonClientAreaProvider(
                                            v6,
                                            a2,
                                            &v31);
  if ( CanUiaSynthesizeNonClientAreaProvider < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2E6,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
      (const char *)(unsigned int)CanUiaSynthesizeNonClientAreaProvider,
      (int)&v29);
  v50 = 0;
  v17 = (*(__int64 (__fastcall **)(UiaManagerCrossMachineStub *, HWND, __int128 *))(*(_QWORD *)v6 + 176LL))(
          v6,
          a2,
          &v50);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2E9,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachinestub.cpp",
      (const char *)(unsigned int)v17,
      (int)&v29);
  v37 = v25;
  v18 = &qword_1800A2748;
  if ( v32 )
    v18 = v32;
  std::wstring::wstring(&v38, v18);
  v41 = v26;
  v19 = v36;
  v36 = 0;
  v20 = v35;
  v35 = 0;
  v21 = v34;
  v34 = 0;
  *(_QWORD *)&v42 = v21;
  *((_QWORD *)&v42 + 1) = v20;
  v43 = v19;
  LOBYTE(v44) = v27 != 0;
  *(_WORD *)((char *)&v44 + 1) = 0;
  BYTE3(v44) = 0;
  BYTE4(v44) = v28 != 0;
  *(_WORD *)((char *)&v44 + 5) = 0;
  BYTE7(v44) = 0;
  *((_QWORD *)&v44 + 1) = (unsigned int)v29;
  v45 = v33;
  LODWORD(v46) = v30;
  BYTE4(v46) = v31 != 0;
  *(_WORD *)((char *)&v46 + 5) = 0;
  HIBYTE(v46) = 0;
  v47 = v50;
  v48 = 1;
  v49 = 0;
  CrossMachineHwndInfo::operator=(a3, &v37);
  GetHwndInfoService::ResponsePayload::~ResponsePayload((GetHwndInfoService::ResponsePayload *)&v37);
  wil::ActivityBase<UiaManagerTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v51);
  std::vector<std::variant<long,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>>>::_Tidy(&v34);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v32);
  UiaManagerTraceLoggingProvider::CrossMachineStubGetHwndInfoActivity::~CrossMachineStubGetHwndInfoActivity((UiaManagerTraceLoggingProvider::CrossMachineStubGetHwndInfoActivity *)v51);
  return 0;
}

```

## disassembly

```asm
0x180017100  mov     r11, rsp
0x180017103  mov     [r11+20h], rbx
0x180017107  push    rsi
0x180017108  push    rdi
0x180017109  push    r12
0x18001710b  push    r14
0x18001710d  push    r15
0x18001710f  sub     rsp, 280h
0x180017116  mov     rax, cs:__security_cookie
0x18001711d  xor     rax, rsp
0x180017120  mov     [rsp+2A8h+var_38], rax
0x180017128  mov     r15, r8
0x18001712b  mov     rsi, rdx
0x18001712e  mov     rbx, rcx
0x180017131  xor     eax, eax
0x180017133  mov     [r11-228h], rax
0x18001713a  xorps   xmm0, xmm0
0x18001713d  movups  [rsp+2A8h+var_220], xmm0
0x180017145  xor     r12d, r12d
0x180017148  mov     [r11-210h], r12
0x18001714f  mov     qword ptr [r11-208h], 7
0x18001715a  mov     [r11-220h], r12w
0x180017162  mov     [r11-200h], rax
0x180017169  movdqa  [rsp+2A8h+var_1F8], xmm0
0x180017172  mov     [r11-1E8h], r12
0x180017179  movups  [rsp+2A8h+var_1E0], xmm0
0x180017181  movups  [rsp+2A8h+var_1D0], xmm0
0x180017189  mov     [r11-1C0h], rax
0x180017190  mov     [r11-1A8h], r12b
0x180017197  mov     [rsp+2A8h+var_1A4], eax
0x18001719e  lea     rdx, [r11-228h]
0x1800171a5  mov     rcx, r8
0x1800171a8  call    ??4CrossMachineHwndInfo@@QEAAAEAU0@$$QEAU0@@Z; CrossMachineHwndInfo::operator=(CrossMachineHwndInfo &&)
0x1800171ad  lea     rcx, [rsp+2A8h+var_228]; this
0x1800171b5  call    ??1ResponsePayload@GetHwndInfoService@@QEAA@XZ; GetHwndInfoService::ResponsePayload::~ResponsePayload(void)
0x1800171ba  lea     rcx, [rsp+2A8h+var_188]; this
0x1800171c2  call    ??$?0$$V@CrossMachineStubGetHwndInfoActivity@UiaManagerTraceLoggingProvider@@AEAA@U?$integral_constant@D$0A@@wistd@@@Z; UiaManagerTraceLoggingProvider::CrossMachineStubGetHwndInfoActivity::CrossMachineStubGetHwndInfoActivity(wistd::integral_constant<char,0>)
0x1800171c7  nop
0x1800171c8  mov     [rsp+2A8h+var_274], r12d
0x1800171cd  lea     rdi, [rbx-10h]
0x1800171d1  lea     r14, [rbx-48h]
0x1800171d5  mov     rax, [r14+38h]
0x1800171d9  lea     r8, [rsp+2A8h+var_274]
0x1800171de  mov     rdx, rsi
0x1800171e1  mov     rcx, rdi
0x1800171e4  mov     rax, [rax+18h]
0x1800171e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171ed  mov     rcx, [rsp+2A8h]; this
0x1800171f5  test    eax, eax
0x1800171f7  jns     short loc_18001720D
0x1800171f9  mov     r9d, eax; char *
0x1800171fc  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x180017203  mov     edx, 2CCh; void *
0x180017208  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001720d  mov     [rsp+2A8h+var_258], r12
0x180017212  mov     rax, [rdi]
0x180017215  mov     rbx, [rax+90h]
0x18001721c  xor     edx, edx
0x18001721e  lea     rcx, [rsp+2A8h+var_258]
0x180017223  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180017228  lea     r8, [rsp+2A8h+var_258]
0x18001722d  mov     rdx, rsi
0x180017230  mov     rcx, rdi
0x180017233  mov     rax, rbx
0x180017236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001723b  mov     rcx, [rsp+2A8h]; this
0x180017243  test    eax, eax
0x180017245  jns     short loc_18001725B
0x180017247  mov     r9d, eax; char *
0x18001724a  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x180017251  mov     edx, 2CFh; void *
0x180017256  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001725b  mov     [rsp+2A8h+var_270], r12d
0x180017260  mov     rax, [rdi]
0x180017263  lea     r8, [rsp+2A8h+var_270]
0x180017268  mov     rdx, rsi
0x18001726b  mov     rcx, rdi
0x18001726e  mov     rax, [rax+30h]
0x180017272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017277  mov     rcx, [rsp+2A8h]; this
0x18001727f  test    eax, eax
0x180017281  jns     short loc_180017297
0x180017283  mov     r9d, eax; char *
0x180017286  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x18001728d  mov     edx, 2D2h; void *
0x180017292  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180017297  mov     r8, rsi
0x18001729a  lea     rdx, [rsp+2A8h+var_240]
0x18001729f  mov     rcx, r14
0x1800172a2  call    ?GetHwndPropertyValues@UiaManagerCrossMachineStub@@AEAA?AV?$vector@V?$variant@JV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@V?$allocator@V?$variant@JV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@PEAUHWND__@@@Z; UiaManagerCrossMachineStub::GetHwndPropertyValues(HWND__ *)
0x1800172a7  nop
0x1800172a8  mov     [rsp+2A8h+var_26C], r12d
0x1800172ad  mov     rax, [rdi]
0x1800172b0  lea     r8, [rsp+2A8h+var_26C]
0x1800172b5  mov     rdx, rsi
0x1800172b8  mov     rcx, rdi
0x1800172bb  mov     rax, [rax+0A8h]
0x1800172c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172c7  mov     rcx, [rsp+2A8h]; this
0x1800172cf  test    eax, eax
0x1800172d1  jns     short loc_1800172E7
0x1800172d3  mov     r9d, eax; char *
0x1800172d6  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x1800172dd  mov     edx, 2D7h; void *
0x1800172e2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800172e7  mov     qword ptr [rsp+2A8h+var_250], r12
0x1800172ec  mov     qword ptr [rsp+2A8h+var_250+8], r12
0x1800172f1  mov     rax, [rdi]
0x1800172f4  lea     r9, [rsp+2A8h+var_250+8]
0x1800172f9  lea     r8, [rsp+2A8h+var_250]
0x1800172fe  mov     rdx, rsi
0x180017301  mov     rcx, rdi
0x180017304  mov     rax, [rax+38h]
0x180017308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001730d  mov     rcx, [rsp+2A8h]; this
0x180017315  test    eax, eax
0x180017317  jns     short loc_18001732D
0x180017319  mov     r9d, eax; char *
0x18001731c  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x180017323  mov     edx, 2DBh; void *
0x180017328  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001732d  mov     [rsp+2A8h+var_278], r12d
0x180017332  mov     [rsp+2A8h+var_268], r12d
0x180017337  mov     [rsp+2A8h+var_264], r12d
0x18001733c  mov     rax, [rdi]
0x18001733f  lea     rcx, [rsp+2A8h+var_264]
0x180017344  mov     qword ptr [rsp+2A8h+var_288], rcx; int
0x180017349  lea     r9, [rsp+2A8h+var_268]
0x18001734e  lea     r8, [rsp+2A8h+var_278]
0x180017353  mov     rdx, rsi
0x180017356  mov     rcx, rdi
0x180017359  mov     rax, [rax+98h]
0x180017360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017365  mov     rcx, [rsp+2A8h]; this
0x18001736d  test    eax, eax
0x18001736f  jns     short loc_180017385
0x180017371  mov     r9d, eax; char *
0x180017374  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x18001737b  mov     edx, 2E0h; void *
0x180017380  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180017385  mov     [rsp+2A8h+var_260], r12d
0x18001738a  mov     rax, [rdi]
0x18001738d  lea     r8, [rsp+2A8h+var_260]
0x180017392  mov     rdx, rsi
0x180017395  mov     rcx, rdi
0x180017398  mov     rax, [rax+0A0h]
0x18001739f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173a4  mov     rcx, [rsp+2A8h]; this
0x1800173ac  test    eax, eax
0x1800173ae  jns     short loc_1800173C4
0x1800173b0  mov     r9d, eax; char *
0x1800173b3  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x1800173ba  mov     edx, 2E3h; void *
0x1800173bf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800173c4  mov     [rsp+2A8h+var_25C], r12d
0x1800173c9  lea     r8, [rsp+2A8h+var_25C]; int *
0x1800173ce  mov     rdx, rsi; HWND
0x1800173d1  mov     rcx, rdi; this
0x1800173d4  call    ?GetCanUiaSynthesizeNonClientAreaProvider@UiaManagerCrossMachineStub@@UEAAJPEAUHWND__@@PEAH@Z; UiaManagerCrossMachineStub::GetCanUiaSynthesizeNonClientAreaProvider(HWND__ *,int *)
0x1800173d9  mov     rcx, [rsp+2A8h]; this
0x1800173e1  test    eax, eax
0x1800173e3  jns     short loc_1800173F9
0x1800173e5  mov     r9d, eax; char *
0x1800173e8  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x1800173ef  mov     edx, 2E6h; void *
0x1800173f4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800173f9  xorps   xmm0, xmm0
0x1800173fc  movups  [rsp+2A8h+var_198], xmm0
0x180017404  mov     rax, [rdi]
0x180017407  lea     r8, [rsp+2A8h+var_198]
0x18001740f  mov     rdx, rsi
0x180017412  mov     rcx, rdi
0x180017415  mov     rax, [rax+0B0h]
0x18001741c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017421  mov     rcx, [rsp+2A8h]; this
0x180017429  test    eax, eax
0x18001742b  jns     short loc_180017441
0x18001742d  mov     r9d, eax; char *
0x180017430  lea     r8, aOnecoreWindows_31; "onecore\\windows\\accessibletech\\uiama"...
0x180017437  mov     edx, 2E9h; void *
0x18001743c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180017441  mov     eax, [rsp+2A8h+var_274]
0x180017445  mov     [rsp+2A8h+var_228], eax
0x18001744c  xor     eax, eax
0x18001744e  mov     [rsp+2A8h+var_224], eax
0x180017455  lea     rdx, qword_1800A2748
0x18001745c  mov     rax, [rsp+2A8h+var_258]
0x180017461  test    rax, rax
0x180017464  cmovnz  rdx, rax
0x180017468  lea     rcx, [rsp+2A8h+var_220]
0x180017470  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180017475  mov     eax, [rsp+2A8h+var_270]
0x180017479  mov     [rsp+2A8h+var_200], eax
0x180017480  xor     eax, eax
0x180017482  mov     [rsp+2A8h+var_1FC], eax
0x180017489  mov     rdx, [rsp+2A8h+var_230]
0x18001748e  mov     [rsp+2A8h+var_230], r12
0x180017493  mov     rcx, [rsp+2A8h+var_238]
0x180017498  mov     [rsp+2A8h+var_238], r12
0x18001749d  mov     rax, [rsp+2A8h+var_240]
0x1800174a2  mov     [rsp+2A8h+var_240], r12
0x1800174a7  mov     qword ptr [rsp+2A8h+var_1F8], rax
0x1800174af  mov     qword ptr [rsp+2A8h+var_1F8+8], rcx
0x1800174b7  mov     [rsp+2A8h+var_1E8], rdx
0x1800174bf  cmp     [rsp+2A8h+var_26C], r12d
0x1800174c4  setnz   byte ptr [rsp+2A8h+var_1E0]
0x1800174cc  xor     eax, eax
0x1800174ce  mov     word ptr [rsp+2A8h+var_1E0+1], ax
0x1800174d6  mov     byte ptr [rsp+2A8h+var_1E0+3], al
0x1800174dd  cmp     [rsp+2A8h+var_268], r12d
0x1800174e2  setnz   byte ptr [rsp+2A8h+var_1E0+4]
0x1800174ea  mov     word ptr [rsp+2A8h+var_1E0+5], ax
0x1800174f2  mov     byte ptr [rsp+2A8h+var_1E0+7], al
0x1800174f9  mov     eax, [rsp+2A8h+var_264]
0x1800174fd  mov     dword ptr [rsp+2A8h+var_1E0+8], eax
0x180017504  xor     eax, eax
0x180017506  mov     dword ptr [rsp+2A8h+var_1E0+0Ch], eax
0x18001750d  mov     rax, qword ptr [rsp+2A8h+var_250]
0x180017512  mov     qword ptr [rsp+2A8h+var_1D0], rax
0x18001751a  mov     rax, qword ptr [rsp+2A8h+var_250+8]
0x18001751f  mov     qword ptr [rsp+2A8h+var_1D0+8], rax
0x180017527  mov     eax, [rsp+2A8h+var_260]
0x18001752b  mov     [rsp+2A8h+var_1C0], eax
0x180017532  cmp     [rsp+2A8h+var_25C], r12d
0x180017537  setnz   [rsp+2A8h+var_1BC]
0x18001753f  xor     eax, eax
0x180017541  mov     [rsp+2A8h+var_1BB], ax
0x180017549  mov     [rsp+2A8h+var_1B9], al
0x180017550  movups  xmm0, [rsp+2A8h+var_198]
0x180017558  movdqu  [rsp+2A8h+var_1B8], xmm0
0x180017561  mov     [rsp+2A8h+var_1A8], 1
0x180017569  mov     [rsp+2A8h+var_1A4], eax
0x180017570  lea     rdx, [rsp+2A8h+var_228]
0x180017578  mov     rcx, r15
0x18001757b  call    ??4CrossMachineHwndInfo@@QEAAAEAU0@$$QEAU0@@Z; CrossMachineHwndInfo::operator=(CrossMachineHwndInfo &&)
0x180017580  lea     rcx, [rsp+2A8h+var_228]; this
0x180017588  call    ??1ResponsePayload@GetHwndInfoService@@QEAA@XZ; GetHwndInfoService::ResponsePayload::~ResponsePayload(void)
0x18001758d  lea     rcx, [rsp+2A8h+var_188]
0x180017595  call    ?Stop@?$ActivityBase@VUiaManagerTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<UiaManagerTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001759a  nop
0x18001759b  lea     rcx, [rsp+2A8h+var_240]
0x1800175a0  call    ?_Tidy@?$vector@V?$variant@JV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@V?$allocator@V?$variant@JV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@@std@@AEAAXXZ; std::vector<std::variant<long,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>>>::_Tidy(void)
0x1800175a5  nop
0x1800175a6  lea     rcx, [rsp+2A8h+var_258]
0x1800175ab  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800175b0  nop
0x1800175b1  lea     rcx, [rsp+2A8h+var_188]; this
0x1800175b9  call    ??1CrossMachineStubGetHwndInfoActivity@UiaManagerTraceLoggingProvider@@QEAA@XZ; UiaManagerTraceLoggingProvider::CrossMachineStubGetHwndInfoActivity::~CrossMachineStubGetHwndInfoActivity(void)
0x1800175be  xor     eax, eax
0x1800175c0  jmp     short loc_1800175C6
0x1800175c2  mov     eax, [rsp+2A8h+var_278]
0x1800175c6  mov     rcx, [rsp+2A8h+var_38]
0x1800175ce  xor     rcx, rsp; StackCookie
0x1800175d1  call    __security_check_cookie
0x1800175d6  mov     rbx, [rsp+2A8h+arg_18]
0x1800175de  add     rsp, 280h
0x1800175e5  pop     r15
0x1800175e7  pop     r14
0x1800175e9  pop     r12
0x1800175eb  pop     rdi
0x1800175ec  pop     rsi
0x1800175ed  retn
```
