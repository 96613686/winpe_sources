# DriverRecoveryManager::_EnableOnRebootTask(bool)

- ea: `0x18002a138`
- end: `0x18002a450`
- name: `?_EnableOnRebootTask@DriverRecoveryManager@@AEAAJ_N@Z`
- size: `792`
- prototype: `__int64 __fastcall(DriverRecoveryManager *this, unsigned __int8)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180029a60`
- `0x18002a458`

## callees

- `0x180009fb0`
- `0x1800112a4`
- `0x180018678`
- `0x18001af70`
- `0x180027ba8`
- `0x1800297b0`
- `0x18002a138`
- `0x180045010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18002a1eb`
- `OLEAUT32!__imp_VariantInit` at `0x18002a1eb`
- `OLEAUT32!__imp_VariantClear` at `0x18002a26d`
- `OLEAUT32!__imp_VariantClear` at `0x18002a413`
- `OLEAUT32!__imp_VariantClear` at `0x18002a26d`
- `OLEAUT32!__imp_VariantClear` at `0x18002a413`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002a1a2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002a1a2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002a1d9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002a42c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002a1d9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002a42c`

## string_xrefs

- `0x18002a1b5`: `onecoreuap\base\devices\setup\dsm\service\driverrecovery.cpp`
- `0x18002a256`: `onecoreuap\base\devices\setup\dsm\service\driverrecovery.cpp`
- `0x18002a2bb`: `onecoreuap\base\devices\setup\dsm\service\driverrecovery.cpp`
- `0x18002a31a`: `onecoreuap\base\devices\setup\dsm\service\driverrecovery.cpp`

## pseudocode

```c
__int64 __fastcall DriverRecoveryManager::_EnableOnRebootTask(DriverRecoveryManager *this, unsigned __int8 a2)
{
  __int16 v2; // si
  HRESULT v4; // eax
  int v5; // ebx
  int v7; // eax
  LPVOID v8; // rdi
  __int64 (__fastcall *v9)(LPVOID, _QWORD, __int64 *); // rbx
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, __int64 *); // rbx
  __int64 v13; // rdx
  __int64 v14; // r8
  const wchar_t *v15; // r9
  int ppv; // [rsp+20h] [rbp-E0h]
  _BYTE v17[8]; // [rsp+30h] [rbp-D0h] BYREF
  char v18; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID v19; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B0h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-A8h] BYREF
  VARIANTARG v23; // [rsp+70h] [rbp-90h] BYREF
  VARIANTARG v24; // [rsp+90h] [rbp-70h] BYREF
  VARIANTARG v25; // [rsp+B0h] [rbp-50h] BYREF
  VARIANTARG v26; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v27; // [rsp+E8h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v2 = a2;
  wil::CoInitializeEx(v17);
  v19 = 0;
  Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(&v19);
  v4 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &v19);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E1,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\driverrecovery.cpp",
      (const char *)(unsigned int)v4,
      ppv);
LABEL_3:
    Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(&v19);
    if ( v17[0] )
      CoUninitialize();
    return (unsigned int)v5;
  }
  VariantInit(&pvarg);
  v23 = pvarg;
  v24 = pvarg;
  v25 = pvarg;
  v26 = pvarg;
  v7 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *))(*(_QWORD *)v19 + 80LL))(
         v19,
         &v26,
         &v25,
         &v24);
  v5 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E4,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\driverrecovery.cpp",
      (const char *)(unsigned int)v7,
      (int)&v23);
LABEL_8:
    VariantClear(&pvarg);
    goto LABEL_3;
  }
  v20 = 0;
  v8 = v19;
  v9 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v19 + 56LL);
  Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(&v20);
  v10 = v9(v8, *((_QWORD *)this + 23), &v20);
  v5 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E7,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\driverrecovery.cpp",
      (const char *)(unsigned int)v10,
      (int)&v23);
LABEL_11:
    Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(&v20);
    goto LABEL_8;
  }
  v21 = 0;
  v11 = v20;
  v12 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v20 + 104LL);
  Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(&v21);
  v5 = v12(v11, *((_QWORD *)this + 24), &v21);
  if ( v5 < 0 )
  {
    v13 = 490;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\driverrecovery.cpp",
      (const char *)(unsigned int)v5,
      (int)&v23);
    Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(&v21);
    goto LABEL_11;
  }
  v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v21 + 88LL))(v21, (unsigned __int16)(v2 - 1));
  if ( v5 < 0 )
  {
    v13 = 491;
    goto LABEL_14;
  }
  if ( (Microsoft_Windows_DeviceSetupManagerEnableBits & 1) != 0 )
  {
    v18 = v2 ^ 1;
    v26.pRecInfo = (IRecordInfo *)&v18;
    v27 = 1;
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_WINDOWS_DEVICESETUPMANAGER_Context,
      DriverRecoveryOnRebootEnablement,
      v14,
      2,
      &v26);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v15 = L"disabled";
    if ( !(_BYTE)v2 )
      v15 = L"enabled";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_ab30234a52263744e5d3d91a9e86c909_Traceguids, v15);
  }
  *((_BYTE *)this + 200) = v2 ^ 1;
  Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(&v21);
  Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(&v20);
  VariantClear(&pvarg);
  Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(&v19);
  if ( v17[0] )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x18002a138  push    rbp
0x18002a13a  push    rbx
0x18002a13b  push    rsi
0x18002a13c  push    rdi
0x18002a13d  push    r12
0x18002a13f  push    r14
0x18002a141  lea     rbp, [rsp-8]
0x18002a146  sub     rsp, 108h
0x18002a14d  mov     rax, cs:__security_cookie
0x18002a154  xor     rax, rsp
0x18002a157  mov     [rbp+30h+var_40], rax
0x18002a15b  movzx   esi, dl
0x18002a15e  mov     r14, rcx
0x18002a161  lea     rcx, [rsp+130h+var_100]
0x18002a166  call    ?CoInitializeEx@wil@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@1@K@Z; wil::CoInitializeEx(ulong)
0x18002a16b  nop
0x18002a16c  mov     [rsp+130h+var_F0], 0
0x18002a175  lea     rcx, [rsp+130h+var_F0]
0x18002a17a  call    ?InternalRelease@?$ComPtr@UIDsmDriverPackageSource@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(void)
0x18002a17f  lea     rax, [rsp+130h+var_F0]
0x18002a184  mov     qword ptr [rsp+130h+ppv], rax; int
0x18002a189  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18002a190  mov     r12d, 1
0x18002a196  mov     r8d, r12d; dwClsContext
0x18002a199  xor     edx, edx; pUnkOuter
0x18002a19b  lea     rcx, CLSID_TaskScheduler; rclsid
0x18002a1a2  call    cs:__imp_CoCreateInstance
0x18002a1a8  mov     ebx, eax
0x18002a1aa  test    eax, eax
0x18002a1ac  jns     short loc_18002A1E6
0x18002a1ae  mov     rcx, [rbp+38h]; this
0x18002a1b2  mov     r9d, eax; char *
0x18002a1b5  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x18002a1bc  mov     edx, 1E1h; void *
0x18002a1c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a1c6  nop
0x18002a1c7  lea     rcx, [rsp+130h+var_F0]
0x18002a1cc  call    ?InternalRelease@?$ComPtr@UIDsmDriverPackageSource@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(void)
0x18002a1d1  nop
0x18002a1d2  cmp     [rsp+130h+var_100], 0
0x18002a1d7  jz      short loc_18002A1DF
0x18002a1d9  call    cs:__imp_CoUninitialize
0x18002a1df  mov     eax, ebx
0x18002a1e1  jmp     loc_18002A434
0x18002a1e6  lea     rcx, [rsp+130h+pvarg]; pvarg
0x18002a1eb  call    cs:__imp_VariantInit
0x18002a1f1  nop
0x18002a1f2  mov     rcx, [rsp+130h+var_F0]
0x18002a1f7  movups  xmm1, xmmword ptr [rsp+130h+pvarg]
0x18002a1fc  movsd   xmm0, qword ptr [rsp+130h+pvarg+10h]
0x18002a202  movaps  xmmword ptr [rsp+130h+var_C0], xmm1
0x18002a207  movsd   [rbp+30h+var_B0], xmm0
0x18002a20c  movaps  [rbp+30h+var_A0], xmm1
0x18002a210  movsd   [rbp+30h+var_90], xmm0
0x18002a215  movaps  [rbp+30h+var_80], xmm1
0x18002a219  movsd   [rbp+30h+var_70], xmm0
0x18002a21e  movaps  [rbp+30h+var_60], xmm1
0x18002a222  movsd   [rbp+30h+var_50], xmm0
0x18002a227  mov     rax, [rcx]
0x18002a22a  lea     rdx, [rsp+130h+var_C0]
0x18002a22f  mov     qword ptr [rsp+130h+ppv], rdx; int
0x18002a234  lea     r9, [rbp+30h+var_A0]
0x18002a238  lea     r8, [rbp+30h+var_80]
0x18002a23c  lea     rdx, [rbp+30h+var_60]
0x18002a240  mov     rax, [rax+50h]
0x18002a244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a249  mov     ebx, eax
0x18002a24b  test    eax, eax
0x18002a24d  jns     short loc_18002A278
0x18002a24f  mov     rcx, [rbp+38h]; this
0x18002a253  mov     r9d, eax; char *
0x18002a256  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x18002a25d  mov     edx, 1E4h; void *
0x18002a262  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a267  nop
0x18002a268  lea     rcx, [rsp+130h+pvarg]; pvarg
0x18002a26d  call    cs:__imp_VariantClear
0x18002a273  jmp     loc_18002A1C7
0x18002a278  mov     [rsp+130h+var_E8], 0
0x18002a281  mov     rdi, [rsp+130h+var_F0]
0x18002a286  mov     rax, [rdi]
0x18002a289  mov     rbx, [rax+38h]
0x18002a28d  lea     rcx, [rsp+130h+var_E8]
0x18002a292  call    ?InternalRelease@?$ComPtr@UIDsmDriverPackageSource@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(void)
0x18002a297  lea     r8, [rsp+130h+var_E8]
0x18002a29c  mov     rdx, [r14+0B8h]
0x18002a2a3  mov     rcx, rdi
0x18002a2a6  mov     rax, rbx
0x18002a2a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a2ae  mov     ebx, eax
0x18002a2b0  test    eax, eax
0x18002a2b2  jns     short loc_18002A2D9
0x18002a2b4  mov     rcx, [rbp+38h]; this
0x18002a2b8  mov     r9d, eax; char *
0x18002a2bb  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x18002a2c2  mov     edx, 1E7h; void *
0x18002a2c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a2cc  nop
0x18002a2cd  lea     rcx, [rsp+130h+var_E8]
0x18002a2d2  call    ?InternalRelease@?$ComPtr@UIDsmDriverPackageSource@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(void)
0x18002a2d7  jmp     short loc_18002A268
0x18002a2d9  mov     [rsp+130h+var_E0], 0
0x18002a2e2  mov     rdi, [rsp+130h+var_E8]
0x18002a2e7  mov     rax, [rdi]
0x18002a2ea  mov     rbx, [rax+68h]
0x18002a2ee  lea     rcx, [rsp+130h+var_E0]
0x18002a2f3  call    ?InternalRelease@?$ComPtr@UIDsmDriverPackageSource@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(void)
0x18002a2f8  lea     r8, [rsp+130h+var_E0]
0x18002a2fd  mov     rdx, [r14+0C0h]
0x18002a304  mov     rcx, rdi
0x18002a307  mov     rax, rbx
0x18002a30a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a30f  mov     ebx, eax
0x18002a311  test    eax, eax
0x18002a313  jns     short loc_18002A33A
0x18002a315  mov     edx, 1EAh; void *
0x18002a31a  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x18002a321  mov     r9d, ebx; char *
0x18002a324  mov     rcx, [rbp+38h]; this
0x18002a328  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a32d  nop
0x18002a32e  lea     rcx, [rsp+130h+var_E0]
0x18002a333  call    ?InternalRelease@?$ComPtr@UIDsmDriverPackageSource@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(void)
0x18002a338  jmp     short loc_18002A2CD
0x18002a33a  mov     rcx, [rsp+130h+var_E0]
0x18002a33f  mov     rax, [rcx]
0x18002a342  movzx   edx, si
0x18002a345  sub     dx, r12w
0x18002a349  mov     rax, [rax+58h]
0x18002a34d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a352  mov     ebx, eax
0x18002a354  test    eax, eax
0x18002a356  jns     short loc_18002A35F
0x18002a358  mov     edx, 1EBh
0x18002a35d  jmp     short loc_18002A31A
0x18002a35f  mov     bl, sil
0x18002a362  xor     bl, r12b
0x18002a365  test    cs:Microsoft_Windows_DeviceSetupManagerEnableBits, r12b
0x18002a36c  jz      short loc_18002A3A5
0x18002a36e  mov     [rsp+130h+var_F8], bl
0x18002a372  lea     rax, [rsp+130h+var_F8]
0x18002a377  mov     [rbp+30h+var_50], rax
0x18002a37b  mov     [rbp+30h+var_48], 1
0x18002a383  lea     rax, [rbp+30h+var_60]
0x18002a387  mov     qword ptr [rsp+130h+ppv], rax
0x18002a38c  mov     r9d, 2
0x18002a392  lea     rdx, DriverRecoveryOnRebootEnablement
0x18002a399  lea     rcx, MICROSOFT_WINDOWS_DEVICESETUPMANAGER_Context
0x18002a3a0  call    McGenEventWrite_EventWriteTransfer
0x18002a3a5  lea     rax, WPP_GLOBAL_Control
0x18002a3ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a3b3  cmp     rcx, rax
0x18002a3b6  jz      short loc_18002A3F1
0x18002a3b8  test    dword ptr [rcx+1Ch], 800h
0x18002a3bf  jz      short loc_18002A3F1
0x18002a3c1  cmp     byte ptr [rcx+19h], 4
0x18002a3c5  jb      short loc_18002A3F1
0x18002a3c7  lea     rax, aEnabled; "enabled"
0x18002a3ce  lea     r9, aDisabled; "disabled"
0x18002a3d5  test    sil, sil
0x18002a3d8  cmovz   r9, rax
0x18002a3dc  mov     edx, 0Fh
0x18002a3e1  lea     r8, WPP_ab30234a52263744e5d3d91a9e86c909_Traceguids
0x18002a3e8  mov     rcx, [rcx+10h]
0x18002a3ec  call    WPP_SF_S
0x18002a3f1  mov     [r14+0C8h], bl
0x18002a3f8  lea     rcx, [rsp+130h+var_E0]
0x18002a3fd  call    ?InternalRelease@?$ComPtr@UIDsmDriverPackageSource@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(void)
0x18002a402  nop
0x18002a403  lea     rcx, [rsp+130h+var_E8]
0x18002a408  call    ?InternalRelease@?$ComPtr@UIDsmDriverPackageSource@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(void)
0x18002a40d  nop
0x18002a40e  lea     rcx, [rsp+130h+pvarg]; pvarg
0x18002a413  call    cs:__imp_VariantClear
0x18002a419  nop
0x18002a41a  lea     rcx, [rsp+130h+var_F0]
0x18002a41f  call    ?InternalRelease@?$ComPtr@UIDsmDriverPackageSource@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(void)
0x18002a424  nop
0x18002a425  cmp     [rsp+130h+var_100], 0
0x18002a42a  jz      short loc_18002A432
0x18002a42c  call    cs:__imp_CoUninitialize
0x18002a432  xor     eax, eax
0x18002a434  mov     rcx, [rbp+30h+var_40]
0x18002a438  xor     rcx, rsp; StackCookie
0x18002a43b  call    __security_check_cookie
0x18002a440  add     rsp, 108h
0x18002a447  pop     r14
0x18002a449  pop     r12
0x18002a44b  pop     rdi
0x18002a44c  pop     rsi
0x18002a44d  pop     rbx
0x18002a44e  pop     rbp
0x18002a44f  retn
```
