# CbsOfflineUtil::CbsCreateSessionFromCbsCorePath(wchar_t const *,ICbsSession * *)

- ea: `0x18003e344`
- end: `0x18003e700`
- name: `?CbsCreateSessionFromCbsCorePath@CbsOfflineUtil@@QEAAJPEB_WPEAPEAUICbsSession@@@Z`
- size: `956`
- prototype: `__int64 __fastcall(CbsOfflineUtil *this, const wchar_t *, struct ICbsSession **)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003e1e0`
- `0x18003eca0`
- `0x18003ed90`
- `0x18003eea0`

## callees

- `0x18001e51c`
- `0x18001f660`
- `0x18001fd10`
- `0x1800293a0`
- `0x18003e344`
- `0x18003e810`
- `0x18003e8f8`
- `0x1800a0020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003e462`
- `KERNEL32!GetLastError` at `0x18003e4dc`
- `KERNEL32!GetLastError` at `0x18003e520`
- `KERNEL32!GetLastError` at `0x18003e565`
- `KERNEL32!GetLastError` at `0x18003e462`
- `KERNEL32!GetLastError` at `0x18003e4dc`
- `KERNEL32!GetLastError` at `0x18003e520`
- `KERNEL32!GetLastError` at `0x18003e565`
- `KERNEL32!GetModuleHandleExW` at `0x18003e39c`
- `KERNEL32!GetModuleHandleExW` at `0x18003e3c7`
- `KERNEL32!GetModuleHandleExW` at `0x18003e3e5`
- `KERNEL32!GetModuleHandleExW` at `0x18003e39c`
- `KERNEL32!GetModuleHandleExW` at `0x18003e3c7`
- `KERNEL32!GetModuleHandleExW` at `0x18003e3e5`
- `KERNEL32!GetProcAddress` at `0x18003e4c7`
- `KERNEL32!GetProcAddress` at `0x18003e50b`
- `KERNEL32!GetProcAddress` at `0x18003e554`
- `KERNEL32!GetProcAddress` at `0x18003e4c7`
- `KERNEL32!GetProcAddress` at `0x18003e50b`
- `KERNEL32!GetProcAddress` at `0x18003e554`
- `KERNEL32!LoadLibraryExW` at `0x18003e443`
- `KERNEL32!LoadLibraryExW` at `0x18003e443`
- `OLE32!CoGetMalloc` at `0x18003e5b5`
- `OLE32!CoGetMalloc` at `0x18003e5b5`

## string_xrefs

- `0x18003e391`: `Cbscore.dll`
- `0x18003e3b8`: `cbs_unittests_offline.dll`
- `0x18003e3db`: `servicing_unittests_offline.dll`

## pseudocode

```c
__int64 __fastcall CbsOfflineUtil::CbsCreateSessionFromCbsCorePath(
        CbsOfflineUtil *this,
        const wchar_t *a2,
        struct ICbsSession **a3)
{
  HMODULE *v3; // rdi
  HMODULE Library; // rax
  signed int LastError; // eax
  int Malloc; // ebx
  void (*v11)(void); // rax
  FARPROC ProcAddress; // rax
  signed int v13; // eax
  FARPROC v14; // rax
  signed int v15; // eax
  FARPROC v16; // rax
  signed int v17; // eax
  __int64 *v18; // rdi
  LPMALLOC *InitPointer; // rax
  __int64 v20; // rdx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, _QWORD, GUID *, __int64); // rbx
  __int64 v23; // rax
  struct ICbsSession *v24; // rax
  __int64 v25; // rcx
  __int64 (__fastcall *v26)(); // [rsp+20h] [rbp-60h]
  HMODULE phModule; // [rsp+50h] [rbp-30h] BYREF
  HMODULE v28; // [rsp+58h] [rbp-28h] BYREF
  HMODULE v29; // [rsp+60h] [rbp-20h] BYREF
  struct ICbsSession *v30; // [rsp+68h] [rbp-18h] BYREF
  __int64 v31; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v3 = (HMODULE *)((char *)this + 8);
  v31 = 0;
  v30 = 0;
  if ( !*((_QWORD *)this + 1) )
  {
    phModule = 0;
    if ( GetModuleHandleExW(2u, L"Cbscore.dll", &phModule) )
    {
      v28 = 0;
      v29 = 0;
      if ( !GetModuleHandleExW(2u, L"cbs_unittests_offline.dll", &v28)
        && !GetModuleHandleExW(2u, L"servicing_unittests_offline.dll", &v29)
        && phModule != &_ImageBase )
      {
        if ( v30 )
        {
          (*(void (__fastcall **)(struct ICbsSession *))(*(_QWORD *)v30 + 16LL))(v30);
          v30 = 0;
        }
        if ( v31 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        return 2147942450LL;
      }
    }
    Library = LoadLibraryExW(a2, 0, 8u);
    Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(v3, Library);
    if ( !*v3 )
    {
      LastError = GetLastError();
      Malloc = LastError;
      if ( LastError > 0 )
        Malloc = (unsigned __int16)LastError | 0x80070000;
      if ( Malloc == -2147024770 )
        Malloc = -2147467263;
      goto LABEL_16;
    }
    ProcAddress = GetProcAddress(*v3, "CbsCoreInitialize");
    *((_QWORD *)this + 12) = ProcAddress;
    if ( !ProcAddress )
    {
      v13 = GetLastError();
      Malloc = v13;
      if ( v13 > 0 )
        Malloc = (unsigned __int16)v13 | 0x80070000;
LABEL_25:
      Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(v3);
LABEL_16:
      if ( v30 )
      {
        (*(void (__fastcall **)(struct ICbsSession *))(*(_QWORD *)v30 + 16LL))(v30);
        v30 = 0;
      }
      if ( !v31 )
        return (unsigned int)Malloc;
      v11 = *(void (**)(void))(*(_QWORD *)v31 + 16LL);
LABEL_20:
      v11();
      return (unsigned int)Malloc;
    }
    v14 = GetProcAddress(*v3, "CbsCoreFinalize");
    *((_QWORD *)this + 13) = v14;
    if ( !v14 )
    {
      v15 = GetLastError();
      Malloc = v15;
      if ( v15 > 0 )
        Malloc = (unsigned __int16)v15 | 0x80070000;
      *((_QWORD *)this + 12) = 0;
      goto LABEL_25;
    }
    if ( g_TestMode )
    {
      v16 = GetProcAddress(*v3, "SetTestMode");
      if ( !v16 )
      {
        v17 = GetLastError();
        Malloc = v17;
        if ( v17 > 0 )
          Malloc = (unsigned __int16)v17 | 0x80070000;
        *((_QWORD *)this + 12) = 0;
        *((_QWORD *)this + 13) = 0;
        goto LABEL_25;
      }
      ((void (__fastcall *)(__int64))v16)(1);
    }
  }
  v18 = (__int64 *)((char *)this + 112);
  if ( !*((_QWORD *)this + 14) )
  {
    InitPointer = (LPMALLOC *)Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(&v31);
    Malloc = CoGetMalloc(1u, InitPointer);
    if ( Malloc < 0 )
    {
      v20 = 212;
LABEL_39:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"onecore\\base\\cbs\\offlineutil\\cbsofflineutil.cpp",
        (const char *)(unsigned int)Malloc,
        (int)v26);
      if ( v30 )
      {
        (*(void (__fastcall **)(struct ICbsSession *))(*(_QWORD *)v30 + 16LL))(v30);
        v30 = 0;
      }
      if ( !v31 )
        return (unsigned int)Malloc;
      v11 = *(void (**)(void))(*(_QWORD *)v31 + 16LL);
      goto LABEL_20;
    }
    if ( *v18 )
    {
      INTERNAL_ERROR_ACTION(-1073741595);
      JUMPOUT(0x18003E6FFLL);
    }
    v26 = CbsUtilInstanceDestroyed;
    Malloc = (*((__int64 (__fastcall **)(__int64, void *, __int64 (__fastcall *)(), __int64 (__fastcall *)()))this + 12))(
               v31,
               &CCbsLogMonitorProvider::Init,
               RtlFinalizeSmartLBlobUcsWritingContext,
               CbsUtilInstanceCreated);
    if ( Malloc < 0 )
    {
      v20 = 226;
      goto LABEL_39;
    }
  }
  v21 = *v18;
  v22 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64))(*(_QWORD *)v21 + 24LL);
  v23 = Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(&v30);
  Malloc = v22(v21, 0, &GUID_75207391_23f2_4396_85f0_8fdb879ed0ed, v23);
  if ( Malloc < 0 )
  {
    v20 = 233;
    goto LABEL_39;
  }
  v24 = v30;
  v25 = v31;
  v30 = 0;
  *a3 = v24;
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  return 0;
}

```

## disassembly

```asm
0x18003e344  mov     [rsp-28h+arg_18], rbx
0x18003e349  push    rbp
0x18003e34a  push    rsi
0x18003e34b  push    rdi
0x18003e34c  push    r14
0x18003e34e  push    r15
0x18003e350  mov     rbp, rsp
0x18003e353  sub     rsp, 80h
0x18003e35a  mov     rax, cs:__security_cookie
0x18003e361  xor     rax, rsp
0x18003e364  mov     [rbp+var_8], rax
0x18003e368  xor     r15d, r15d
0x18003e36b  lea     rdi, [rcx+8]
0x18003e36f  mov     r14, r8
0x18003e372  mov     rbx, rdx
0x18003e375  mov     rsi, rcx
0x18003e378  mov     [rbp+var_10], r15
0x18003e37c  mov     [rbp+var_18], r15
0x18003e380  cmp     [rdi], r15
0x18003e383  jnz     loc_18003E597
0x18003e389  lea     r8, [rbp+phModule]; phModule
0x18003e38d  mov     [rbp+phModule], r15
0x18003e391  lea     rdx, aCbscoreDll_1; "Cbscore.dll"
0x18003e398  lea     ecx, [r15+2]; dwFlags
0x18003e39c  call    cs:__imp_GetModuleHandleExW
0x18003e3a3  nop     dword ptr [rax+rax+00h]
0x18003e3a8  test    eax, eax
0x18003e3aa  jz      loc_18003E43A
0x18003e3b0  lea     r8, [rbp+var_28]; phModule
0x18003e3b4  mov     [rbp+var_28], r15
0x18003e3b8  lea     rdx, aCbsUnittestsOf; "cbs_unittests_offline.dll"
0x18003e3bf  mov     [rbp+var_20], r15
0x18003e3c3  lea     ecx, [r15+2]; dwFlags
0x18003e3c7  call    cs:__imp_GetModuleHandleExW
0x18003e3ce  nop     dword ptr [rax+rax+00h]
0x18003e3d3  test    eax, eax
0x18003e3d5  jnz     short loc_18003E43A
0x18003e3d7  lea     r8, [rbp+var_20]; phModule
0x18003e3db  lea     rdx, aServicingUnitt; "servicing_unittests_offline.dll"
0x18003e3e2  lea     ecx, [rax+2]; dwFlags
0x18003e3e5  call    cs:__imp_GetModuleHandleExW
0x18003e3ec  nop     dword ptr [rax+rax+00h]
0x18003e3f1  test    eax, eax
0x18003e3f3  jnz     short loc_18003E43A
0x18003e3f5  lea     rax, __ImageBase
0x18003e3fc  cmp     [rbp+phModule], rax
0x18003e400  jz      short loc_18003E43A
0x18003e402  mov     rcx, [rbp+var_18]
0x18003e406  test    rcx, rcx
0x18003e409  jz      short loc_18003E41B
0x18003e40b  mov     rax, [rcx]
0x18003e40e  mov     rax, [rax+10h]
0x18003e412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e417  mov     [rbp+var_18], r15
0x18003e41b  mov     rcx, [rbp+var_10]
0x18003e41f  test    rcx, rcx
0x18003e422  jz      short loc_18003E430
0x18003e424  mov     rax, [rcx]
0x18003e427  mov     rax, [rax+10h]
0x18003e42b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e430  mov     eax, 80070032h
0x18003e435  jmp     loc_18003E6D1
0x18003e43a  xor     edx, edx; hFile
0x18003e43c  mov     rcx, rbx; lpLibFileName
0x18003e43f  lea     r8d, [rdx+8]; dwFlags
0x18003e443  call    cs:__imp_LoadLibraryExW
0x18003e44a  nop     dword ptr [rax+rax+00h]
0x18003e44f  mov     rdx, rax
0x18003e452  mov     rcx, rdi
0x18003e455  call    ?TakeOwnership@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXPEA_W@Z; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(wchar_t *)
0x18003e45a  mov     rcx, [rdi]; hModule
0x18003e45d  test    rcx, rcx
0x18003e460  jnz     short loc_18003E4C0
0x18003e462  call    cs:__imp_GetLastError
0x18003e469  nop     dword ptr [rax+rax+00h]
0x18003e46e  mov     ebx, eax
0x18003e470  test    eax, eax
0x18003e472  jle     short loc_18003E47D
0x18003e474  movzx   ebx, ax
0x18003e477  or      ebx, 80070000h
0x18003e47d  cmp     ebx, 8007007Eh
0x18003e483  mov     eax, 80004001h
0x18003e488  cmovz   ebx, eax
0x18003e48b  mov     rcx, [rbp+var_18]
0x18003e48f  test    rcx, rcx
0x18003e492  jz      short loc_18003E4A4
0x18003e494  mov     rax, [rcx]
0x18003e497  mov     rax, [rax+10h]
0x18003e49b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e4a0  mov     [rbp+var_18], r15
0x18003e4a4  mov     rcx, [rbp+var_10]
0x18003e4a8  test    rcx, rcx
0x18003e4ab  jz      short loc_18003E4B9
0x18003e4ad  mov     rdx, [rcx]
0x18003e4b0  mov     rax, [rdx+10h]
0x18003e4b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e4b9  mov     eax, ebx
0x18003e4bb  jmp     loc_18003E6D1
0x18003e4c0  lea     rdx, aCbscoreinitial; "CbsCoreInitialize"
0x18003e4c7  call    cs:__imp_GetProcAddress
0x18003e4ce  nop     dword ptr [rax+rax+00h]
0x18003e4d3  mov     [rsi+60h], rax
0x18003e4d7  test    rax, rax
0x18003e4da  jnz     short loc_18003E501
0x18003e4dc  call    cs:__imp_GetLastError
0x18003e4e3  nop     dword ptr [rax+rax+00h]
0x18003e4e8  mov     ebx, eax
0x18003e4ea  test    eax, eax
0x18003e4ec  jle     short loc_18003E4F7
0x18003e4ee  movzx   ebx, ax
0x18003e4f1  or      ebx, 80070000h
0x18003e4f7  mov     rcx, rdi
0x18003e4fa  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x18003e4ff  jmp     short loc_18003E48B
0x18003e501  mov     rcx, [rdi]; hModule
0x18003e504  lea     rdx, aCbscorefinaliz; "CbsCoreFinalize"
0x18003e50b  call    cs:__imp_GetProcAddress
0x18003e512  nop     dword ptr [rax+rax+00h]
0x18003e517  mov     [rsi+68h], rax
0x18003e51b  test    rax, rax
0x18003e51e  jnz     short loc_18003E541
0x18003e520  call    cs:__imp_GetLastError
0x18003e527  nop     dword ptr [rax+rax+00h]
0x18003e52c  mov     ebx, eax
0x18003e52e  test    eax, eax
0x18003e530  jle     short loc_18003E53B
0x18003e532  movzx   ebx, ax
0x18003e535  or      ebx, 80070000h
0x18003e53b  mov     [rsi+60h], r15
0x18003e53f  jmp     short loc_18003E4F7
0x18003e541  cmp     cs:?g_TestMode@@3_NA, r15b; bool g_TestMode
0x18003e548  jz      short loc_18003E597
0x18003e54a  mov     rcx, [rdi]; hModule
0x18003e54d  lea     rdx, aSettestmode; "SetTestMode"
0x18003e554  call    cs:__imp_GetProcAddress
0x18003e55b  nop     dword ptr [rax+rax+00h]
0x18003e560  test    rax, rax
0x18003e563  jnz     short loc_18003E58D
0x18003e565  call    cs:__imp_GetLastError
0x18003e56c  nop     dword ptr [rax+rax+00h]
0x18003e571  mov     ebx, eax
0x18003e573  test    eax, eax
0x18003e575  jle     short loc_18003E580
0x18003e577  movzx   ebx, ax
0x18003e57a  or      ebx, 80070000h
0x18003e580  mov     [rsi+60h], r15
0x18003e584  mov     [rsi+68h], r15
0x18003e588  jmp     loc_18003E4F7
0x18003e58d  mov     ecx, 1
0x18003e592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e597  lea     rdi, [rsi+70h]
0x18003e59b  cmp     [rdi], r15
0x18003e59e  jnz     loc_18003E675
0x18003e5a4  lea     rcx, [rbp+var_10]
0x18003e5a8  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x18003e5ad  mov     rdx, rax; ppMalloc
0x18003e5b0  mov     ecx, 1; dwMemContext
0x18003e5b5  call    cs:__imp_CoGetMalloc
0x18003e5bc  nop     dword ptr [rax+rax+00h]
0x18003e5c1  mov     ebx, eax
0x18003e5c3  test    eax, eax
0x18003e5c5  jns     short loc_18003E611
0x18003e5c7  mov     edx, 0D4h; void *
0x18003e5cc  mov     rcx, [rbp+28h]; this
0x18003e5d0  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\offlineutil\\cbsoff"...
0x18003e5d7  mov     r9d, ebx; char *
0x18003e5da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e5df  mov     rcx, [rbp+var_18]
0x18003e5e3  test    rcx, rcx
0x18003e5e6  jz      short loc_18003E5F8
0x18003e5e8  mov     rdx, [rcx]
0x18003e5eb  mov     rax, [rdx+10h]
0x18003e5ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e5f4  mov     [rbp+var_18], r15
0x18003e5f8  mov     rcx, [rbp+var_10]
0x18003e5fc  test    rcx, rcx
0x18003e5ff  jz      loc_18003E4B9
0x18003e605  mov     rax, [rcx]
0x18003e608  mov     rax, [rax+10h]
0x18003e60c  jmp     loc_18003E4B4
0x18003e611  cmp     [rdi], r15
0x18003e614  jnz     loc_18003E6F5
0x18003e61a  mov     rcx, [rbp+var_10]
0x18003e61e  lea     rax, RtlFinalizeSmartLBlobUcsWritingContext
0x18003e625  mov     [rsp+80h+var_48], rdi
0x18003e62a  lea     r9, CbsUtilInstanceCreated
0x18003e631  mov     [rsp+80h+var_50], rax
0x18003e636  lea     r8, RtlFinalizeSmartLBlobUcsWritingContext
0x18003e63d  lea     rax, RtlFinalizeSmartLBlobUcsWritingContext
0x18003e644  mov     [rsp+80h+var_58], rax
0x18003e649  lea     rdx, ?Init@CCbsLogMonitorProvider@@UEAA?AW4tagLOGRESULT@@PEAXPEAVILogContext@@@Z; CCbsLogMonitorProvider::Init(void *,ILogContext *)
0x18003e650  lea     rax, CbsUtilInstanceDestroyed
0x18003e657  mov     [rsp+80h+var_60], rax
0x18003e65c  mov     rax, [rsi+60h]
0x18003e660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e665  mov     ebx, eax
0x18003e667  test    eax, eax
0x18003e669  jns     short loc_18003E675
0x18003e66b  mov     edx, 0E2h
0x18003e670  jmp     loc_18003E5CC
0x18003e675  mov     rdi, [rdi]
0x18003e678  lea     rcx, [rbp+var_18]
0x18003e67c  mov     rax, [rdi]
0x18003e67f  mov     rbx, [rax+18h]
0x18003e683  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x18003e688  mov     r9, rax
0x18003e68b  lea     r8, _GUID_75207391_23f2_4396_85f0_8fdb879ed0ed
0x18003e692  mov     rax, rbx
0x18003e695  xor     edx, edx
0x18003e697  mov     rcx, rdi
0x18003e69a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e69f  mov     ebx, eax
0x18003e6a1  test    eax, eax
0x18003e6a3  jns     short loc_18003E6AF
0x18003e6a5  mov     edx, 0E9h
0x18003e6aa  jmp     loc_18003E5CC
0x18003e6af  mov     rax, [rbp+var_18]
0x18003e6b3  mov     rcx, [rbp+var_10]
0x18003e6b7  mov     [rbp+var_18], r15
0x18003e6bb  mov     [r14], rax
0x18003e6be  test    rcx, rcx
0x18003e6c1  jz      short loc_18003E6CF
0x18003e6c3  mov     rax, [rcx]
0x18003e6c6  mov     rax, [rax+10h]
0x18003e6ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e6cf  xor     eax, eax
0x18003e6d1  mov     rcx, [rbp+var_8]
0x18003e6d5  xor     rcx, rsp; StackCookie
0x18003e6d8  call    __security_check_cookie
0x18003e6dd  mov     rbx, [rsp+80h+arg_18]
0x18003e6e5  add     rsp, 80h
0x18003e6ec  pop     r15
0x18003e6ee  pop     r14
0x18003e6f0  pop     rdi
0x18003e6f1  pop     rsi
0x18003e6f2  pop     rbp
0x18003e6f3  retn
0x18003e6f5  mov     ecx, 0C00000E5h; int
0x18003e6fa  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
