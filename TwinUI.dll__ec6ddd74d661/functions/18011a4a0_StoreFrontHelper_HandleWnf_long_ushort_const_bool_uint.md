# StoreFrontHelper::HandleWnf(long,ushort const *,bool,uint)

- ea: `0x18011a4a0`
- end: `0x18011a7ce`
- name: `?HandleWnf@StoreFrontHelper@@AEAAJJPEBG_NI@Z`
- size: `814`
- prototype: `int(StoreFrontHelper *__hidden this, int, const unsigned __int16 *, bool, unsigned int)`
- caller_count: `2`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x18011a2f4`
- `0x180128de4`

## callees

- `0x180009dd0`
- `0x1800378dc`
- `0x1800529c8`
- `0x18007bef8`
- `0x18011a4a0`
- `0x18034ab80`
- `0x18034aeb0`
- `0x18034b160`
- `0x18034b498`
- `0x18034c604`
- `0x18034c958`
- `0x18034ca68`
- `0x18034caf4`
- `0x18038576c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011a585`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011a740`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011a757`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011a585`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011a740`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011a757`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011a54b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011a650`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011a680`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011a6c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011a6db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011a7a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011a54b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011a650`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011a680`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011a6c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011a6db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011a7a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a506`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a506`

## pseudocode

```c
__int64 __fastcall StoreFrontHelper::HandleWnf(
        StoreFrontHelper *this,
        int a2,
        CallerIdentity *a3,
        char a4,
        unsigned int a5)
{
  int PackageInfoFromPackageFullName; // eax
  void *v9; // r14
  int v10; // ebx
  StoreFrontHelperUtils *StringRawBuffer; // rax
  struct Microsoft::WRL::Wrappers::HString *v12; // r8
  int AppDisplayNameFromPackageFamilyName; // eax
  StoreFrontHelper *v14; // rcx
  int v15; // eax
  __int64 v16; // rdx
  StorePopup *v17; // rax
  bool *v18; // r8
  StoreFrontHelper *v19; // rcx
  const unsigned __int16 *v20; // r8
  const unsigned __int16 *v21; // rbx
  StorePopup *v22; // rax
  const unsigned __int16 *v23; // r8
  StorePopup *v25; // rax
  const unsigned __int16 *v26; // rdx
  struct PACKAGE_INFO **v27; // [rsp+20h] [rbp-30h]
  int v28; // [rsp+20h] [rbp-30h]
  HSTRING v29; // [rsp+30h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-18h] BYREF
  HSTRING string; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  int v33; // [rsp+80h] [rbp+30h] BYREF
  int v34; // [rsp+84h] [rbp+34h]

  v34 = HIDWORD(this);
  string = 0;
  v33 = 0;
  pv = 0;
  PackageInfoFromPackageFullName = CallerIdentity::GetPackageInfoFromPackageFullName(
                                     a3,
                                     (const unsigned __int16 *)0x100,
                                     (unsigned int)&v33,
                                     (unsigned int *)&pv,
                                     v27);
  v9 = pv;
  v10 = PackageInfoFromPackageFullName;
  if ( PackageInfoFromPackageFullName >= 0 )
    v10 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&string);
  CoTaskMemFree(v9);
  if ( v10 >= 0 )
  {
    v29 = 0;
    StringRawBuffer = (StoreFrontHelperUtils *)WindowsGetStringRawBuffer(string, 0);
    AppDisplayNameFromPackageFamilyName = StoreFrontHelperUtils::GetAppDisplayNameFromPackageFamilyName(
                                            StringRawBuffer,
                                            (const unsigned __int16 *)&v29,
                                            v12);
    v10 = AppDisplayNameFromPackageFamilyName;
    if ( AppDisplayNameFromPackageFamilyName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x50,
        (unsigned int)"shell\\twinui\\storefronthelper\\lib\\storefronthelper.cpp",
        (const char *)(unsigned int)AppDisplayNameFromPackageFamilyName,
        v28);
LABEL_7:
      WindowsDeleteString(v29);
LABEL_32:
      v29 = 0;
      goto LABEL_33;
    }
    pv = 0;
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&pv);
    Microsoft::WRL::Details::MakeAndInitialize<StoreFrontNotificationHelper,StoreFrontNotificationHelper,>(&pv);
    switch ( a2 )
    {
      case -2143326196:
        v15 = StoreFrontHelper::ForceAppShutdown(v14, (const unsigned __int16 *)a3);
        v10 = v15;
        if ( v15 < 0 )
        {
          v16 = 98;
          goto LABEL_17;
        }
        v25 = (StorePopup *)WindowsGetStringRawBuffer(string, 0);
        v15 = StorePopup::ShowOfflineWarningDialog(v25, v26);
        v10 = v15;
        if ( v15 < 0 )
        {
          v16 = 99;
          goto LABEL_17;
        }
        break;
      case -2143326195:
        StoreFrontNotificationHelper::ShowNotification(v14, 0, string, v29, 0);
        break;
      case -2143326194:
        StoreFrontNotificationHelper::ShowNotification(v14, 1, string, v29, a5);
        break;
      case -2143322105:
        v15 = StoreFrontHelper::ForceAppShutdown(v14, (const unsigned __int16 *)a3);
        v10 = v15;
        if ( v15 < 0 )
        {
          v16 = 102;
          goto LABEL_17;
        }
        break;
      case -2143322103:
        v15 = StoreFrontHelper::ForceAppShutdown(v14, (const unsigned __int16 *)a3);
        v10 = v15;
        if ( v15 < 0 )
        {
          v16 = 88;
          goto LABEL_17;
        }
        v21 = WindowsGetStringRawBuffer(string, 0);
        v22 = (StorePopup *)WindowsGetStringRawBuffer(v29, 0);
        v15 = StorePopup::ShowTrialExpiredDialog(v22, v21, v23);
        v10 = v15;
        if ( v15 < 0 )
        {
          v16 = 89;
          goto LABEL_17;
        }
        break;
      case -2143322008:
        LOBYTE(v33) = 0;
        v15 = StoreFrontHelper::ForceAppShutdown(v14, (const unsigned __int16 *)a3);
        v10 = v15;
        if ( v15 < 0 )
        {
          v16 = 107;
          goto LABEL_17;
        }
        v17 = (StorePopup *)WindowsGetStringRawBuffer(v29, 0);
        if ( (int)StorePopup::ShowConcurrencyLimitDialog(v17, (const unsigned __int16 *)&v33, v18) >= 0 )
        {
          if ( (_BYTE)v33 )
          {
            WindowsGetStringRawBuffer(string, 0);
            v15 = StoreFrontHelper::ResumeApp(v19, (const unsigned __int16 *)a3, v20);
            v10 = v15;
            if ( v15 < 0 )
            {
              v16 = 111;
              goto LABEL_17;
            }
          }
        }
        break;
      default:
        if ( a4 )
        {
          v15 = StoreFrontHelper::ForceAppShutdown(v14, (const unsigned __int16 *)a3);
          v10 = v15;
          if ( v15 < 0 )
          {
            v16 = 118;
LABEL_17:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v16,
              (unsigned int)"shell\\twinui\\storefronthelper\\lib\\storefronthelper.cpp",
              (const char *)(unsigned int)v15,
              v28);
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&pv);
            goto LABEL_7;
          }
        }
        break;
    }
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&pv);
    WindowsDeleteString(v29);
    v10 = 0;
    goto LABEL_32;
  }
  StoreFrontHelperTelemetry::TraceLoggingInfo("GetFamilyNameFromPackageFullName failed with 0x%x", v10);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4D,
    (unsigned int)"shell\\twinui\\storefronthelper\\lib\\storefronthelper.cpp",
    (const char *)(unsigned int)v10,
    v28);
LABEL_33:
  WindowsDeleteString(string);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18011a4a0  mov     [rsp-28h+arg_8], rbx
0x18011a4a5  mov     [rsp-28h+arg_10], rsi
0x18011a4aa  mov     qword ptr [rsp-28h+arg_0], rcx
0x18011a4af  push    rbp
0x18011a4b0  push    rdi
0x18011a4b1  push    r12
0x18011a4b3  push    r14
0x18011a4b5  push    r15
0x18011a4b7  mov     rbp, rsp
0x18011a4ba  sub     rsp, 50h
0x18011a4be  mov     rsi, r8
0x18011a4c1  xor     r12d, r12d
0x18011a4c4  mov     r15b, r9b
0x18011a4c7  mov     [rbp+string], r12
0x18011a4cb  mov     edi, edx
0x18011a4cd  mov     [rbp+arg_0], r12d
0x18011a4d1  mov     rcx, rsi; this
0x18011a4d4  mov     [rbp+pv], r12
0x18011a4d8  lea     r9, [rbp+pv]; unsigned int *
0x18011a4dc  mov     edx, 100h; unsigned __int16 *
0x18011a4e1  lea     r8, [rbp+arg_0]; unsigned int
0x18011a4e5  call    ?GetPackageInfoFromPackageFullName@CallerIdentity@@YAJPEBGIPEAIPEAPEAUPACKAGE_INFO@@@Z; CallerIdentity::GetPackageInfoFromPackageFullName(ushort const *,uint,uint *,PACKAGE_INFO * *)
0x18011a4ea  mov     r14, [rbp+pv]
0x18011a4ee  mov     ebx, eax
0x18011a4f0  test    eax, eax
0x18011a4f2  js      short loc_18011A503
0x18011a4f4  lea     rdx, [r14+18h]
0x18011a4f8  lea     rcx, [rbp+string]; string
0x18011a4fc  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18011a501  mov     ebx, eax
0x18011a503  mov     rcx, r14; pv
0x18011a506  call    cs:__imp_CoTaskMemFree
0x18011a50d  nop     dword ptr [rax+rax+00h]
0x18011a512  test    ebx, ebx
0x18011a514  jns     short loc_18011A541
0x18011a516  mov     edx, ebx
0x18011a518  lea     rcx, aGetfamilynamef; "GetFamilyNameFromPackageFullName failed"...
0x18011a51f  call    ?TraceLoggingInfo@StoreFrontHelperTelemetry@@SAXPEBDZZ; StoreFrontHelperTelemetry::TraceLoggingInfo(char const *,...)
0x18011a524  mov     rcx, [rbp+28h]; this
0x18011a528  lea     r8, aShellTwinuiSto_0; "shell\\twinui\\storefronthelper\\lib\\s"...
0x18011a52f  mov     r9d, ebx; char *
0x18011a532  mov     edx, 4Dh ; 'M'; void *
0x18011a537  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011a53c  jmp     loc_18011A753
0x18011a541  mov     rcx, [rbp+string]; string
0x18011a545  xor     edx, edx; length
0x18011a547  mov     [rbp+var_20], r12
0x18011a54b  call    cs:__imp_WindowsGetStringRawBuffer
0x18011a552  nop     dword ptr [rax+rax+00h]
0x18011a557  mov     rcx, rax; this
0x18011a55a  lea     rdx, [rbp+var_20]; unsigned __int16 *
0x18011a55e  call    ?GetAppDisplayNameFromPackageFamilyName@StoreFrontHelperUtils@@YAJPEBGAEAVHString@Wrappers@WRL@Microsoft@@@Z; StoreFrontHelperUtils::GetAppDisplayNameFromPackageFamilyName(ushort const *,Microsoft::WRL::Wrappers::HString &)
0x18011a563  mov     ebx, eax
0x18011a565  test    eax, eax
0x18011a567  jns     short loc_18011A596
0x18011a569  mov     rcx, [rbp+28h]; this
0x18011a56d  lea     r8, aShellTwinuiSto_0; "shell\\twinui\\storefronthelper\\lib\\s"...
0x18011a574  mov     r9d, eax; char *
0x18011a577  mov     edx, 50h ; 'P'; void *
0x18011a57c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011a581  mov     rcx, [rbp+var_20]; string
0x18011a585  call    cs:__imp_WindowsDeleteString
0x18011a58c  nop     dword ptr [rax+rax+00h]
0x18011a591  jmp     loc_18011A74F
0x18011a596  lea     rcx, [rbp+pv]
0x18011a59a  mov     [rbp+pv], r12
0x18011a59e  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18011a5a3  lea     rcx, [rbp+pv]
0x18011a5a7  call    ??$MakeAndInitialize@VStoreFrontNotificationHelper@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVStoreFrontNotificationHelper@@@Z; Microsoft::WRL::Details::MakeAndInitialize<StoreFrontNotificationHelper,StoreFrontNotificationHelper,>(StoreFrontNotificationHelper * *)
0x18011a5ac  cmp     edi, 803F700Ch
0x18011a5b2  jz      loc_18011A788
0x18011a5b8  cmp     edi, 803F700Dh
0x18011a5be  jz      loc_18011A77F
0x18011a5c4  cmp     edi, 803F700Eh
0x18011a5ca  jz      loc_18011A71A
0x18011a5d0  cmp     edi, 803F8007h
0x18011a5d6  jz      loc_18011A702
0x18011a5dc  cmp     edi, 803F8009h
0x18011a5e2  jz      loc_18011A6A8
0x18011a5e8  cmp     edi, 803F8068h
0x18011a5ee  jz      short loc_18011A631
0x18011a5f0  test    r15b, r15b
0x18011a5f3  jz      loc_18011A733
0x18011a5f9  mov     rdx, rsi; unsigned __int16 *
0x18011a5fc  call    ?ForceAppShutdown@StoreFrontHelper@@AEAAJPEBG@Z; StoreFrontHelper::ForceAppShutdown(ushort const *)
0x18011a601  mov     ebx, eax
0x18011a603  test    eax, eax
0x18011a605  jns     loc_18011A733
0x18011a60b  mov     edx, 76h ; 'v'; void *
0x18011a610  mov     rcx, [rbp+28h]; this
0x18011a614  lea     r8, aShellTwinuiSto_0; "shell\\twinui\\storefronthelper\\lib\\s"...
0x18011a61b  mov     r9d, eax; char *
0x18011a61e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011a623  lea     rcx, [rbp+pv]
0x18011a627  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18011a62c  jmp     loc_18011A581
0x18011a631  mov     rdx, rsi; unsigned __int16 *
0x18011a634  mov     byte ptr [rbp+arg_0], r12b
0x18011a638  call    ?ForceAppShutdown@StoreFrontHelper@@AEAAJPEBG@Z; StoreFrontHelper::ForceAppShutdown(ushort const *)
0x18011a63d  mov     ebx, eax
0x18011a63f  test    eax, eax
0x18011a641  jns     short loc_18011A64A
0x18011a643  mov     edx, 6Bh ; 'k'
0x18011a648  jmp     short loc_18011A610
0x18011a64a  mov     rcx, [rbp+var_20]; string
0x18011a64e  xor     edx, edx; length
0x18011a650  call    cs:__imp_WindowsGetStringRawBuffer
0x18011a657  nop     dword ptr [rax+rax+00h]
0x18011a65c  mov     rcx, rax; this
0x18011a65f  lea     rdx, [rbp+arg_0]; unsigned __int16 *
0x18011a663  call    ?ShowConcurrencyLimitDialog@StorePopup@@YAJPEBGAEA_N@Z; StorePopup::ShowConcurrencyLimitDialog(ushort const *,bool &)
0x18011a668  test    eax, eax
0x18011a66a  js      loc_18011A733
0x18011a670  cmp     byte ptr [rbp+arg_0], r12b
0x18011a674  jz      loc_18011A733
0x18011a67a  mov     rcx, [rbp+string]; string
0x18011a67e  xor     edx, edx; length
0x18011a680  call    cs:__imp_WindowsGetStringRawBuffer
0x18011a687  nop     dword ptr [rax+rax+00h]
0x18011a68c  mov     rdx, rsi; unsigned __int16 *
0x18011a68f  call    ?ResumeApp@StoreFrontHelper@@AEAAJPEBG0@Z; StoreFrontHelper::ResumeApp(ushort const *,ushort const *)
0x18011a694  mov     ebx, eax
0x18011a696  test    eax, eax
0x18011a698  jns     loc_18011A733
0x18011a69e  mov     edx, 6Fh ; 'o'
0x18011a6a3  jmp     loc_18011A610
0x18011a6a8  mov     rdx, rsi; unsigned __int16 *
0x18011a6ab  call    ?ForceAppShutdown@StoreFrontHelper@@AEAAJPEBG@Z; StoreFrontHelper::ForceAppShutdown(ushort const *)
0x18011a6b0  mov     ebx, eax
0x18011a6b2  test    eax, eax
0x18011a6b4  jns     short loc_18011A6C0
0x18011a6b6  mov     edx, 58h ; 'X'
0x18011a6bb  jmp     loc_18011A610
0x18011a6c0  mov     rcx, [rbp+string]; string
0x18011a6c4  xor     edx, edx; length
0x18011a6c6  call    cs:__imp_WindowsGetStringRawBuffer
0x18011a6cd  nop     dword ptr [rax+rax+00h]
0x18011a6d2  mov     rcx, [rbp+var_20]; string
0x18011a6d6  xor     edx, edx; length
0x18011a6d8  mov     rbx, rax
0x18011a6db  call    cs:__imp_WindowsGetStringRawBuffer
0x18011a6e2  nop     dword ptr [rax+rax+00h]
0x18011a6e7  mov     rcx, rax; this
0x18011a6ea  mov     rdx, rbx; unsigned __int16 *
0x18011a6ed  call    ?ShowTrialExpiredDialog@StorePopup@@YAJPEBG0@Z; StorePopup::ShowTrialExpiredDialog(ushort const *,ushort const *)
0x18011a6f2  mov     ebx, eax
0x18011a6f4  test    eax, eax
0x18011a6f6  jns     short loc_18011A733
0x18011a6f8  mov     edx, 59h ; 'Y'
0x18011a6fd  jmp     loc_18011A610
0x18011a702  mov     rdx, rsi; unsigned __int16 *
0x18011a705  call    ?ForceAppShutdown@StoreFrontHelper@@AEAAJPEBG@Z; StoreFrontHelper::ForceAppShutdown(ushort const *)
0x18011a70a  mov     ebx, eax
0x18011a70c  test    eax, eax
0x18011a70e  jns     short loc_18011A733
0x18011a710  mov     edx, 66h ; 'f'
0x18011a715  jmp     loc_18011A610
0x18011a71a  mov     eax, [rbp+arg_20]
0x18011a71d  mov     edx, 1
0x18011a722  mov     [rsp+50h+var_30], eax
0x18011a726  mov     r8, [rbp+string]
0x18011a72a  mov     r9, [rbp+var_20]
0x18011a72e  call    ?ShowNotification@StoreFrontNotificationHelper@@QEAAJW4NotificationType@@PEAUHSTRING__@@1I@Z; StoreFrontNotificationHelper::ShowNotification(NotificationType,HSTRING__ *,HSTRING__ *,uint)
0x18011a733  lea     rcx, [rbp+pv]
0x18011a737  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18011a73c  mov     rcx, [rbp+var_20]; string
0x18011a740  call    cs:__imp_WindowsDeleteString
0x18011a747  nop     dword ptr [rax+rax+00h]
0x18011a74c  mov     ebx, r12d
0x18011a74f  mov     [rbp+var_20], r12
0x18011a753  mov     rcx, [rbp+string]; string
0x18011a757  call    cs:__imp_WindowsDeleteString
0x18011a75e  nop     dword ptr [rax+rax+00h]
0x18011a763  lea     r11, [rsp+50h+var_s0]
0x18011a768  mov     eax, ebx
0x18011a76a  mov     rbx, [r11+38h]
0x18011a76e  mov     rsi, [r11+40h]
0x18011a772  mov     rsp, r11
0x18011a775  pop     r15
0x18011a777  pop     r14
0x18011a779  pop     r12
0x18011a77b  pop     rdi
0x18011a77c  pop     rbp
0x18011a77d  retn
0x18011a77f  mov     [rsp+50h+var_30], r12d
0x18011a784  xor     edx, edx
0x18011a786  jmp     short loc_18011A726
0x18011a788  mov     rdx, rsi; unsigned __int16 *
0x18011a78b  call    ?ForceAppShutdown@StoreFrontHelper@@AEAAJPEBG@Z; StoreFrontHelper::ForceAppShutdown(ushort const *)
0x18011a790  mov     ebx, eax
0x18011a792  test    eax, eax
0x18011a794  jns     short loc_18011A7A0
0x18011a796  mov     edx, 62h ; 'b'
0x18011a79b  jmp     loc_18011A610
0x18011a7a0  mov     rcx, [rbp+string]; string
0x18011a7a4  xor     edx, edx; length
0x18011a7a6  call    cs:__imp_WindowsGetStringRawBuffer
0x18011a7ad  nop     dword ptr [rax+rax+00h]
0x18011a7b2  mov     rcx, rax; this
0x18011a7b5  call    ?ShowOfflineWarningDialog@StorePopup@@YAJPEBG@Z; StorePopup::ShowOfflineWarningDialog(ushort const *)
0x18011a7ba  mov     ebx, eax
0x18011a7bc  test    eax, eax
0x18011a7be  jns     loc_18011A733
0x18011a7c4  mov     edx, 63h ; 'c'
0x18011a7c9  jmp     loc_18011A610
```
