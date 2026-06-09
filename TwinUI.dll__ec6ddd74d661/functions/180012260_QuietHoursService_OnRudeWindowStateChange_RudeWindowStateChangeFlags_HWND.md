# QuietHoursService::OnRudeWindowStateChange(RudeWindowStateChangeFlags,HWND__ *)

- ea: `0x180012260`
- end: `0x1800125a7`
- name: `?OnRudeWindowStateChange@QuietHoursService@@UEAAJW4RudeWindowStateChangeFlags@@PEAUHWND__@@@Z`
- size: `839`
- prototype: `int __high(enum RudeWindowStateChangeFlags, HWND)`
- caller_count: `0`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callees

- `0x180012260`
- `0x1800125b0`
- `0x180012608`
- `0x1800126fc`
- `0x1800127c0`
- `0x180012884`
- `0x1800128b8`
- `0x180012954`
- `0x18002dbd8`
- `0x180077dc8`
- `0x180079430`
- `0x180097d60`
- `0x1800ce828`
- `0x1800ce8b4`
- `0x1800d14b4`
- `0x180142e10`
- `0x180143a7c`

## import_xrefs

- `USER32!InternalGetWindowText` at `0x180012497`
- `USER32!InternalGetWindowText` at `0x180012497`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012310`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012310`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongPtrW` at `0x1800124b3`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongPtrW` at `0x1800124cb`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongPtrW` at `0x1800124b3`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongPtrW` at `0x1800124cb`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassNameW` at `0x180012459`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassNameW` at `0x180012459`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x1800123a5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x1800124e7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x1800123a5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x1800124e7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800123c0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800124fe`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800123c0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800124fe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall QuietHoursService::OnRudeWindowStateChange(__int64 a1, char a2, HWND a3)
{
  bool v5; // si
  __int64 v6; // rdx
  QuietHoursService *v7; // rcx
  unsigned int v8; // r9d
  WCHAR *FileNameW; // rax
  Microsoft::WRL::Wrappers::HString *v11; // rcx
  unsigned __int64 v12; // r8
  const unsigned __int16 *v13; // rdx
  bool IsProcessInExclusionList; // r14
  WCHAR *v15; // rax
  bool v16; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+48h] [rbp-B8h] BYREF
  int WindowLongPtrW; // [rsp+4Ch] [rbp-B4h] BYREF
  int v19; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR *v20; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR *v21; // [rsp+60h] [rbp-A0h] BYREF
  void **v22; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v23[272]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v24[8]; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v25[24]; // [rsp+190h] [rbp+90h] BYREF
  int v26; // [rsp+1A8h] [rbp+A8h]
  WCHAR pszPath[264]; // [rsp+1C0h] [rbp+C0h] BYREF
  WCHAR ClassName[264]; // [rsp+3D0h] [rbp+2D0h] BYREF
  WCHAR pString[264]; // [rsp+5E0h] [rbp+4E0h] BYREF

  v5 = a2 & 1;
  wil::ActivityBase<QuietHoursServiceTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<QuietHoursServiceTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    &v22,
    "OnRudeWindowStateChange");
  v22 = &QuietHoursServiceTraceProvider::OnRudeWindowStateChange::`vftable';
  QuietHoursServiceTraceProvider::OnRudeWindowStateChange::StartActivity(
    (QuietHoursServiceTraceProvider::OnRudeWindowStateChange *)&v22,
    v5);
  memset_0(pszPath, 0, 0x208u);
  if ( !v5 || !a3 || QuietHoursService::GetProcessPathOrAppIdFromHwnd(v7, a3, pszPath, v8) < 0 )
    goto LABEL_2;
  IsProcessInExclusionList = QuietHoursService::IsProcessInExclusionList((QuietHoursService *)(a1 - 96), pszPath);
  memset_0(ClassName, 0, 0x208u);
  GetClassNameW(a3, ClassName, 260);
  v20 = ClassName;
  v16 = IsProcessInExclusionList;
  memset_0(pString, 0, 0x208u);
  if ( InternalGetWindowText(a3, pString, 260) )
    QuietHoursServiceTraceProvider::OnRudeWindowStateChange::RudeWindowText<unsigned short (&)[260]>(&v22, pString);
  WindowLongPtrW = GetWindowLongPtrW(a3, -16);
  v17 = GetWindowLongPtrW(a3, -20);
  v19 = 0;
  v15 = PathIsFileSpecW(pszPath) ? pszPath : PathFindFileNameW(pszPath);
  v21 = v15;
  QuietHoursServiceTraceProvider::OnRudeWindowStateChange::QuietHoursFullScreenProcess<unsigned short const *,int,bool &,unsigned short const * &,unsigned long &,unsigned long &>(
    (unsigned int)&v22,
    (unsigned int)&v21,
    (unsigned int)&v19,
    (unsigned int)&v16,
    (__int64)&v20,
    (__int64)&WindowLongPtrW,
    (__int64)&v17);
  if ( !IsProcessInExclusionList )
  {
LABEL_2:
    LOBYTE(v6) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImportantNotifications>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_ImportantNotifications>::GetImpl'::`2'::impl,
      v6);
    *(_BYTE *)(a1 + 345) = v5;
    if ( !v5 )
    {
      WindowsDeleteString(*(HSTRING *)(a1 + 352));
      *(_QWORD *)(a1 + 352) = 0;
LABEL_4:
      QuietHoursService::RaiseWnfIfStateChanged((QuietHoursService *)(a1 - 96));
      goto LABEL_5;
    }
    if ( PathIsFileSpecW(pszPath) )
    {
      FileNameW = pszPath;
      v11 = (Microsoft::WRL::Wrappers::HString *)(a1 + 352);
    }
    else
    {
      FileNameW = PathFindFileNameW(pszPath);
      v11 = (Microsoft::WRL::Wrappers::HString *)(a1 + 352);
      if ( !FileNameW )
      {
        LODWORD(v12) = 0;
        v13 = &pszDefault;
LABEL_14:
        Microsoft::WRL::Wrappers::HString::Set(v11, v13, v12);
        goto LABEL_4;
      }
    }
    v12 = -1;
    do
      ++v12;
    while ( FileNameW[v12] );
    if ( v12 > 0xFFFFFFFF )
      goto LABEL_4;
    v13 = FileNameW;
    goto LABEL_14;
  }
LABEL_5:
  wil::ActivityBase<QuietHoursServiceTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v22);
  v22 = &QuietHoursServiceTraceProvider::OnRudeWindowStateChange::`vftable';
  wil::ActivityBase<QuietHoursServiceTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v22);
  if ( v26 )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v25);
  wil::details::shared_object<wil::ActivityBase<QuietHoursServiceTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<QuietHoursServiceTraceProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(v24);
  wil::ActivityBase<QuietHoursServiceTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<QuietHoursServiceTraceProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<QuietHoursServiceTraceProvider,_TlgReflectorTag_Param0IsProviderType>(v23);
  return 0;
}

```

## disassembly

```asm
0x180012260  mov     [rsp-8+arg_8], rbx
0x180012265  mov     [rsp-8+arg_18], rsi
0x18001226a  push    rbp
0x18001226b  push    rdi
0x18001226c  push    r12
0x18001226e  push    r13
0x180012270  push    r14
0x180012272  lea     rbp, [rsp-700h]
0x18001227a  sub     rsp, 800h
0x180012281  mov     rax, cs:__security_cookie
0x180012288  xor     rax, rsp
0x18001228b  mov     [rbp+720h+var_30], rax
0x180012292  mov     rdi, r8
0x180012295  mov     esi, edx
0x180012297  mov     rbx, rcx
0x18001229a  and     esi, 1
0x18001229d  lea     rdx, aOnrudewindowst; "OnRudeWindowStateChange"
0x1800122a4  lea     rcx, [rsp+820h+var_7B0]
0x1800122a9  call    ??0?$ActivityBase@VQuietHoursServiceTraceProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<QuietHoursServiceTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<QuietHoursServiceTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800122ae  lea     rax, ??_7OnRudeWindowStateChange@QuietHoursServiceTraceProvider@@6B@; const QuietHoursServiceTraceProvider::OnRudeWindowStateChange::`vftable'
0x1800122b5  mov     [rsp+820h+var_7B0], rax
0x1800122ba  mov     dl, sil; bool
0x1800122bd  lea     rcx, [rsp+820h+var_7B0]; this
0x1800122c2  call    ?StartActivity@OnRudeWindowStateChange@QuietHoursServiceTraceProvider@@QEAAX_N@Z; QuietHoursServiceTraceProvider::OnRudeWindowStateChange::StartActivity(bool)
0x1800122c7  nop
0x1800122c8  mov     r13d, 208h
0x1800122ce  mov     r8d, r13d; Size
0x1800122d1  xor     edx, edx; Val
0x1800122d3  lea     rcx, [rbp+720h+pszPath]; void *
0x1800122da  call    memset_0
0x1800122df  xor     r12d, r12d
0x1800122e2  test    sil, sil
0x1800122e5  jnz     loc_180012405
0x1800122eb  mov     dl, 1
0x1800122ed  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ImportantNotifications@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ImportantNotifications@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImportantNotifications> `wil::Feature<__WilFeatureTraits_Feature_ImportantNotifications>::GetImpl(void)'::`2'::impl
0x1800122f4  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ImportantNotifications@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImportantNotifications>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800122f9  mov     [rbx+159h], sil
0x180012300  test    sil, sil
0x180012303  jnz     loc_18001239E
0x180012309  mov     rcx, [rbx+160h]; string
0x180012310  call    cs:__imp_WindowsDeleteString
0x180012317  nop     dword ptr [rax+rax+00h]
0x18001231c  mov     [rbx+160h], r12
0x180012323  lea     rcx, [rbx-60h]; this
0x180012327  call    ?RaiseWnfIfStateChanged@QuietHoursService@@AEAAXXZ; QuietHoursService::RaiseWnfIfStateChanged(void)
0x18001232c  lea     rcx, [rsp+820h+var_7B0]
0x180012331  call    ?Stop@?$ActivityBase@VQuietHoursServiceTraceProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<QuietHoursServiceTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180012336  lea     rax, ??_7OnRudeWindowStateChange@QuietHoursServiceTraceProvider@@6B@; const QuietHoursServiceTraceProvider::OnRudeWindowStateChange::`vftable'
0x18001233d  mov     [rsp+820h+var_7B0], rax
0x180012342  lea     rcx, [rsp+820h+var_7B0]
0x180012347  call    ?Destroy@?$ActivityBase@VQuietHoursServiceTraceProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<QuietHoursServiceTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001234c  nop
0x18001234d  cmp     [rbp+720h+var_678], r12d
0x180012354  jnz     loc_180012595
0x18001235a  lea     rcx, [rbp+720h+var_698]
0x180012361  call    ?reset@?$shared_object@V?$ActivityData@VQuietHoursServiceTraceProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VQuietHoursServiceTraceProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<QuietHoursServiceTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<QuietHoursServiceTraceProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180012366  lea     rcx, [rsp+820h+var_7A8]
0x18001236b  call    ??1?$ActivityData@VQuietHoursServiceTraceProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VQuietHoursServiceTraceProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<QuietHoursServiceTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<QuietHoursServiceTraceProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<QuietHoursServiceTraceProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x180012370  xor     eax, eax
0x180012372  mov     rcx, [rbp+720h+var_30]
0x180012379  xor     rcx, rsp; StackCookie
0x18001237c  call    __security_check_cookie
0x180012381  lea     r11, [rsp+820h+var_20]
0x180012389  mov     rbx, [r11+38h]
0x18001238d  mov     rsi, [r11+48h]
0x180012391  mov     rsp, r11
0x180012394  pop     r14
0x180012396  pop     r13
0x180012398  pop     r12
0x18001239a  pop     rdi
0x18001239b  pop     rbp
0x18001239c  retn
0x18001239e  lea     rcx, [rbp+720h+pszPath]; pszPath
0x1800123a5  call    cs:__imp_PathIsFileSpecW
0x1800123ac  nop     dword ptr [rax+rax+00h]
0x1800123b1  test    eax, eax
0x1800123b3  jnz     loc_180012554
0x1800123b9  lea     rcx, [rbp+720h+pszPath]; pszPath
0x1800123c0  call    cs:__imp_PathFindFileNameW
0x1800123c7  nop     dword ptr [rax+rax+00h]
0x1800123cc  lea     rcx, [rbx+160h]; this
0x1800123d3  test    rax, rax
0x1800123d6  jz      loc_180012567
0x1800123dc  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800123e0  inc     r8; unsigned int
0x1800123e3  cmp     [rax+r8*2], r12w
0x1800123e8  jnz     short loc_1800123E0
0x1800123ea  mov     edx, 0FFFFFFFFh
0x1800123ef  cmp     r8, rdx
0x1800123f2  ja      loc_180012323
0x1800123f8  mov     rdx, rax; unsigned __int16 *
0x1800123fb  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180012400  jmp     loc_180012323
0x180012405  test    rdi, rdi
0x180012408  jz      loc_1800122EB
0x18001240e  lea     r8, [rbp+720h+pszPath]; unsigned __int16 *
0x180012415  mov     rdx, rdi; HWND
0x180012418  call    ?GetProcessPathOrAppIdFromHwnd@QuietHoursService@@AEAAJPEAUHWND__@@PEAGI@Z; QuietHoursService::GetProcessPathOrAppIdFromHwnd(HWND__ *,ushort *,uint)
0x18001241d  test    eax, eax
0x18001241f  js      loc_1800122EB
0x180012425  lea     rcx, [rbx-60h]; this
0x180012429  lea     rdx, [rbp+720h+pszPath]; unsigned __int16 *
0x180012430  call    ?IsProcessInExclusionList@QuietHoursService@@AEBA_NPEBG@Z; QuietHoursService::IsProcessInExclusionList(ushort const *)
0x180012435  mov     r14b, al
0x180012438  mov     r8, r13; Size
0x18001243b  xor     edx, edx; Val
0x18001243d  lea     rcx, [rbp+720h+ClassName]; void *
0x180012444  call    memset_0
0x180012449  mov     r8d, 104h; nMaxCount
0x18001244f  lea     rdx, [rbp+720h+ClassName]; lpClassName
0x180012456  mov     rcx, rdi; hWnd
0x180012459  call    cs:__imp_GetClassNameW
0x180012460  nop     dword ptr [rax+rax+00h]
0x180012465  lea     rax, [rbp+720h+ClassName]
0x18001246c  mov     [rsp+820h+var_7C8], rax
0x180012471  mov     [rsp+820h+var_7E0], r14b
0x180012476  mov     r8, r13; Size
0x180012479  xor     edx, edx; Val
0x18001247b  lea     rcx, [rbp+720h+pString]; void *
0x180012482  call    memset_0
0x180012487  mov     r8d, 104h; cchMaxCount
0x18001248d  lea     rdx, [rbp+720h+pString]; pString
0x180012494  mov     rcx, rdi; hWnd
0x180012497  call    cs:__imp_InternalGetWindowText
0x18001249e  nop     dword ptr [rax+rax+00h]
0x1800124a3  test    eax, eax
0x1800124a5  jnz     loc_18001257F
0x1800124ab  mov     edx, 0FFFFFFF0h; nIndex
0x1800124b0  mov     rcx, rdi; hWnd
0x1800124b3  call    cs:__imp_GetWindowLongPtrW
0x1800124ba  nop     dword ptr [rax+rax+00h]
0x1800124bf  mov     [rsp+820h+var_7D4], eax
0x1800124c3  mov     edx, 0FFFFFFECh; nIndex
0x1800124c8  mov     rcx, rdi; hWnd
0x1800124cb  call    cs:__imp_GetWindowLongPtrW
0x1800124d2  nop     dword ptr [rax+rax+00h]
0x1800124d7  mov     [rsp+820h+var_7D8], eax
0x1800124db  mov     [rsp+820h+var_7D0], r12d
0x1800124e0  lea     rcx, [rbp+720h+pszPath]; pszPath
0x1800124e7  call    cs:__imp_PathIsFileSpecW
0x1800124ee  nop     dword ptr [rax+rax+00h]
0x1800124f3  test    eax, eax
0x1800124f5  jnz     short loc_180012576
0x1800124f7  lea     rcx, [rbp+720h+pszPath]; pszPath
0x1800124fe  call    cs:__imp_PathFindFileNameW
0x180012505  nop     dword ptr [rax+rax+00h]
0x18001250a  mov     [rsp+820h+var_7C0], rax
0x18001250f  lea     rax, [rsp+820h+var_7D8]
0x180012514  mov     [rsp+820h+var_7F0], rax
0x180012519  lea     rax, [rsp+820h+var_7D4]
0x18001251e  mov     [rsp+820h+var_7F8], rax
0x180012523  lea     rax, [rsp+820h+var_7C8]
0x180012528  mov     [rsp+820h+var_800], rax
0x18001252d  lea     r9, [rsp+820h+var_7E0]
0x180012532  lea     r8, [rsp+820h+var_7D0]
0x180012537  lea     rdx, [rsp+820h+var_7C0]
0x18001253c  lea     rcx, [rsp+820h+var_7B0]
0x180012541  call    ??$QuietHoursFullScreenProcess@PEBGHAEA_NAEAPEBGAEAKAEAK@OnRudeWindowStateChange@QuietHoursServiceTraceProvider@@QEAAX$$QEAPEBG$$QEAHAEA_NAEAPEBGAEAK4@Z; QuietHoursServiceTraceProvider::OnRudeWindowStateChange::QuietHoursFullScreenProcess<ushort const *,int,bool &,ushort const * &,ulong &,ulong &>(ushort const * &&,int &&,bool &,ushort const * &,ulong &,ulong &)
0x180012546  test    r14b, r14b
0x180012549  jz      loc_1800122EB
0x18001254f  jmp     loc_18001232C
0x180012554  lea     rax, [rbp+720h+pszPath]
0x18001255b  lea     rcx, [rbx+160h]
0x180012562  jmp     loc_1800123DC
0x180012567  xor     r8d, r8d
0x18001256a  lea     rdx, pszDefault
0x180012571  jmp     loc_1800123FB
0x180012576  lea     rax, [rbp+720h+pszPath]
0x18001257d  jmp     short loc_18001250A
0x18001257f  lea     rdx, [rbp+720h+pString]
0x180012586  lea     rcx, [rsp+820h+var_7B0]
0x18001258b  call    ??$RudeWindowText@AEAY0BAE@G@OnRudeWindowStateChange@QuietHoursServiceTraceProvider@@QEAAXAEAY0BAE@G@Z; QuietHoursServiceTraceProvider::OnRudeWindowStateChange::RudeWindowText<ushort (&)[260]>(ushort (&)[260])
0x180012590  jmp     loc_1800124AB
0x180012595  lea     rcx, [rbp+720h+var_690]; this
0x18001259c  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800125a1  jmp     loc_18001235A
```
