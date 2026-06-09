# GetActiveHoursPolicyValues(ulong *,ulong *,bool *)

- ea: `0x18003f5f4`
- end: `0x18003f90e`
- name: `?GetActiveHoursPolicyValues@@YAJPEAK0PEA_N@Z`
- size: `794`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003f914`

## callees

- `0x18000912c`
- `0x18000d544`
- `0x1800291d8`
- `0x18003f5f4`
- `0x18003fb60`
- `0x180046010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003f709`
- `OLEAUT32!__imp_VariantInit` at `0x18003f713`
- `OLEAUT32!__imp_VariantInit` at `0x18003f709`
- `OLEAUT32!__imp_VariantInit` at `0x18003f713`
- `OLEAUT32!__imp_VariantClear` at `0x18003f769`
- `OLEAUT32!__imp_VariantClear` at `0x18003f78f`
- `OLEAUT32!__imp_VariantClear` at `0x18003f811`
- `OLEAUT32!__imp_VariantClear` at `0x18003f837`
- `OLEAUT32!__imp_VariantClear` at `0x18003f892`
- `OLEAUT32!__imp_VariantClear` at `0x18003f8b8`
- `OLEAUT32!__imp_VariantClear` at `0x18003f769`
- `OLEAUT32!__imp_VariantClear` at `0x18003f78f`
- `OLEAUT32!__imp_VariantClear` at `0x18003f811`
- `OLEAUT32!__imp_VariantClear` at `0x18003f837`
- `OLEAUT32!__imp_VariantClear` at `0x18003f892`
- `OLEAUT32!__imp_VariantClear` at `0x18003f8b8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003f6b5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003f6b5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18003f68c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18003f8eb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18003f68c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18003f8eb`

## string_xrefs

- `0x18003f630`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`
- `0x18003f674`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`
- `0x18003f6c8`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`
- `0x18003f753`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`
- `0x18003f77a`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`
- `0x18003f7a4`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`
- `0x18003f7fb`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`
- `0x18003f822`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`
- `0x18003f848`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`
- `0x18003f8a3`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`
- `0x18003f8c9`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetActiveHoursPolicyValues(LONG *a1, LONG *a2, bool *a3)
{
  bool v6; // r14
  __int64 v7; // rdx
  unsigned int v8; // ebx
  int v10; // eax
  bool v11; // zf
  HRESULT v12; // eax
  int v13; // eax
  HRESULT v14; // eax
  HRESULT v15; // eax
  LONG lVal; // edi
  LONG v17; // esi
  int v18; // eax
  HRESULT v19; // eax
  HRESULT v20; // eax
  HRESULT v21; // eax
  HRESULT v22; // eax
  int ppv; // [rsp+20h] [rbp-59h]
  int ppva; // [rsp+20h] [rbp-59h]
  int ppvb; // [rsp+20h] [rbp-59h]
  int ppvc; // [rsp+20h] [rbp-59h]
  __int128 v27; // [rsp+48h] [rbp-31h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-21h] BYREF
  __int128 v29; // [rsp+70h] [rbp-9h] BYREF
  VARIANTARG v30; // [rsp+80h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  int v32; // [rsp+E0h] [rbp+67h] BYREF
  LPVOID v33; // [rsp+F8h] [rbp+7Fh] BYREF

  v6 = 0;
  if ( !a1 )
  {
    v7 = 63;
LABEL_3:
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usopolicyhelperlib\\usopolicyhelper.cpp",
      (const char *)0x80070057LL,
      ppv);
    return v8;
  }
  if ( !a2 )
  {
    v7 = 64;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v7 = 65;
    goto LABEL_3;
  }
  v32 = 0;
  v10 = CCoInit::Initialize((CCoInit *)&v32, (unsigned int)a2);
  v8 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x44,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usopolicyhelperlib\\usopolicyhelper.cpp",
      (const char *)(unsigned int)v10,
      ppv);
LABEL_11:
    v11 = v32 == 0;
LABEL_12:
    if ( !v11 )
      CoUninitialize();
    return v8;
  }
  v33 = 0;
  v12 = CoCreateInstance(
          &GUID_07369a67_07a6_4608_abea_379491cb7c46,
          0,
          1u,
          &GUID_152807bd_4d18_46c5_ae31_dd8d597d0559,
          &v33);
  v8 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usopolicyhelperlib\\usopolicyhelper.cpp",
      (const char *)(unsigned int)v12,
      ppva);
LABEL_16:
    wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>((__int64 *)&v33);
    goto LABEL_11;
  }
  v27 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v29 = 0;
  memset(&v30, 0, sizeof(v30));
  VariantInit(&pvarg);
  VariantInit(&v30);
  v13 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int128 *))(*(_QWORD *)v33 + 24LL))(v33, 23, &v27);
  v8 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usopolicyhelperlib\\usopolicyhelper.cpp",
      (const char *)(unsigned int)v13,
      ppva);
    v14 = VariantClear(&pvarg);
    if ( v14 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x53,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usopolicyhelperlib\\usopolicyhelper.cpp",
        (const char *)(unsigned int)v14,
        ppvb);
    v15 = VariantClear(&v30);
    if ( v15 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x54,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usopolicyhelperlib\\usopolicyhelper.cpp",
        (const char *)(unsigned int)v15,
        ppvb);
    goto LABEL_16;
  }
  lVal = 0;
  v17 = 0;
  if ( DWORD1(v27) == 1 && pvarg.vt == 3 )
  {
    v18 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int128 *))(*(_QWORD *)v33 + 24LL))(v33, 24, &v29);
    v8 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x64,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usopolicyhelperlib\\usopolicyhelper.cpp",
        (const char *)(unsigned int)v18,
        ppva);
      v19 = VariantClear(&pvarg);
      if ( v19 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x53,
          (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usopolicyhelperlib\\usopolicyhelper.cpp",
          (const char *)(unsigned int)v19,
          ppvc);
      v20 = VariantClear(&v30);
      if ( v20 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x54,
          (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usopolicyhelperlib\\usopolicyhelper.cpp",
          (const char *)(unsigned int)v20,
          ppvc);
      wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>((__int64 *)&v33);
      v11 = v32 == 0;
      goto LABEL_12;
    }
    if ( DWORD1(v29) == 1 && v30.vt == 3 )
    {
      lVal = pvarg.lVal;
      v17 = v30.lVal;
      v6 = 1;
    }
  }
  *a1 = lVal;
  *a2 = v17;
  *a3 = v6;
  v21 = VariantClear(&pvarg);
  if ( v21 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usopolicyhelperlib\\usopolicyhelper.cpp",
      (const char *)(unsigned int)v21,
      ppva);
  v22 = VariantClear(&v30);
  if ( v22 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usopolicyhelperlib\\usopolicyhelper.cpp",
      (const char *)(unsigned int)v22,
      ppva);
  wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>((__int64 *)&v33);
  if ( v32 )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x18003f5f4  mov     [rsp-8+arg_8], rbx
0x18003f5f9  push    rbp
0x18003f5fa  push    rsi
0x18003f5fb  push    rdi
0x18003f5fc  push    r12
0x18003f5fe  push    r13
0x18003f600  push    r14
0x18003f602  push    r15
0x18003f604  lea     rbp, [rsp-27h]
0x18003f609  sub     rsp, 0A0h
0x18003f610  mov     r15, r8
0x18003f613  mov     r12, rdx
0x18003f616  mov     r13, rcx
0x18003f619  xor     r14d, r14d
0x18003f61c  test    rcx, rcx
0x18003f61f  jnz     short loc_18003F643
0x18003f621  lea     edx, [rcx+3Fh]; void *
0x18003f624  mov     ebx, 80070057h
0x18003f629  mov     rcx, [rbp+5Fh]; this
0x18003f62d  mov     r9d, ebx; char *
0x18003f630  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003f637  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f63c  mov     eax, ebx
0x18003f63e  jmp     loc_18003F8F3
0x18003f643  test    r12, r12
0x18003f646  jnz     short loc_18003F64F
0x18003f648  lea     edx, [r12+40h]
0x18003f64d  jmp     short loc_18003F624
0x18003f64f  test    r15, r15
0x18003f652  jnz     short loc_18003F65A
0x18003f654  lea     edx, [r15+41h]; unsigned int
0x18003f658  jmp     short loc_18003F624
0x18003f65a  mov     [rbp+57h+arg_0], r14d
0x18003f65e  lea     rcx, [rbp+57h+arg_0]; this
0x18003f662  call    ?Initialize@CCoInit@@QEAAJK@Z; CCoInit::Initialize(ulong)
0x18003f667  mov     ebx, eax
0x18003f669  test    eax, eax
0x18003f66b  jns     short loc_18003F694
0x18003f66d  mov     rcx, [rbp+5Fh]; this
0x18003f671  mov     r9d, eax; char *
0x18003f674  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003f67b  mov     edx, 44h ; 'D'; void *
0x18003f680  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f685  nop
0x18003f686  cmp     [rbp+57h+arg_0], r14d
0x18003f68a  jz      short loc_18003F63C
0x18003f68c  call    cs:__imp_CoUninitialize
0x18003f692  jmp     short loc_18003F63C
0x18003f694  mov     [rbp+57h+arg_18], r14
0x18003f698  lea     rax, [rbp+57h+arg_18]
0x18003f69c  mov     qword ptr [rsp+0D0h+ppv], rax; int
0x18003f6a1  lea     r9, _GUID_152807bd_4d18_46c5_ae31_dd8d597d0559; riid
0x18003f6a8  xor     edx, edx; pUnkOuter
0x18003f6aa  lea     r8d, [rdx+1]; dwClsContext
0x18003f6ae  lea     rcx, _GUID_07369a67_07a6_4608_abea_379491cb7c46; rclsid
0x18003f6b5  call    cs:__imp_CoCreateInstance
0x18003f6bb  mov     ebx, eax
0x18003f6bd  test    eax, eax
0x18003f6bf  jns     short loc_18003F6E5
0x18003f6c1  mov     rcx, [rbp+5Fh]; this
0x18003f6c5  mov     r9d, eax; char *
0x18003f6c8  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003f6cf  mov     edx, 4Bh ; 'K'; void *
0x18003f6d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f6d9  nop
0x18003f6da  lea     rcx, [rbp+57h+arg_18]
0x18003f6de  call    ??1?$com_ptr_t@UITaskSchedulerEx2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(void)
0x18003f6e3  jmp     short loc_18003F686
0x18003f6e5  xorps   xmm0, xmm0
0x18003f6e8  xor     eax, eax
0x18003f6ea  movups  [rbp+57h+var_88], xmm0
0x18003f6ee  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18003f6f2  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18003f6f6  xorps   xmm1, xmm1
0x18003f6f9  movups  [rbp+57h+var_60], xmm1
0x18003f6fd  movups  xmmword ptr [rbp+57h+var_50], xmm1
0x18003f701  mov     qword ptr [rbp+57h+var_50+10h], rax
0x18003f705  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18003f709  call    cs:__imp_VariantInit
0x18003f70f  lea     rcx, [rbp+57h+var_50]; pvarg
0x18003f713  call    cs:__imp_VariantInit
0x18003f719  lea     rax, [rbp+57h+var_88]
0x18003f71d  mov     [rbp+57h+var_A0], rax
0x18003f721  lea     rax, [rbp+57h+var_60]
0x18003f725  mov     [rbp+57h+var_98], rax
0x18003f729  mov     [rbp+57h+var_90], 1
0x18003f72d  mov     rcx, [rbp+57h+arg_18]
0x18003f731  mov     rax, [rcx]
0x18003f734  lea     r8, [rbp+57h+var_88]
0x18003f738  mov     edx, 17h
0x18003f73d  mov     rax, [rax+18h]
0x18003f741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f746  mov     ebx, eax
0x18003f748  test    eax, eax
0x18003f74a  jns     short loc_18003F7BA
0x18003f74c  mov     rcx, [rbp+5Fh]; this
0x18003f750  mov     r9d, eax; char *
0x18003f753  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003f75a  mov     edx, 5Dh ; ']'; void *
0x18003f75f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f764  nop
0x18003f765  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18003f769  call    cs:__imp_VariantClear
0x18003f76f  mov     rcx, [rbp+5Fh]; this
0x18003f773  test    eax, eax
0x18003f775  jns     short loc_18003F78B
0x18003f777  mov     r9d, eax; char *
0x18003f77a  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003f781  mov     edx, 53h ; 'S'; void *
0x18003f786  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003f78b  lea     rcx, [rbp+57h+var_50]; pvarg
0x18003f78f  call    cs:__imp_VariantClear
0x18003f795  mov     rcx, [rbp+5Fh]; this
0x18003f799  test    eax, eax
0x18003f79b  jns     loc_18003F6DA
0x18003f7a1  mov     r9d, eax; char *
0x18003f7a4  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003f7ab  mov     edx, 54h ; 'T'; void *
0x18003f7b0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003f7b5  jmp     loc_18003F6DA
0x18003f7ba  mov     edi, r14d
0x18003f7bd  mov     esi, r14d
0x18003f7c0  cmp     dword ptr [rbp+57h+var_88+4], 1
0x18003f7c4  jnz     loc_18003F883
0x18003f7ca  cmp     word ptr [rbp+57h+pvarg], 3
0x18003f7cf  jnz     loc_18003F883
0x18003f7d5  mov     rcx, [rbp+57h+arg_18]
0x18003f7d9  mov     rax, [rcx]
0x18003f7dc  lea     r8, [rbp+57h+var_60]
0x18003f7e0  mov     edx, 18h
0x18003f7e5  mov     rax, [rax+18h]
0x18003f7e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f7ee  mov     ebx, eax
0x18003f7f0  test    eax, eax
0x18003f7f2  jns     short loc_18003F86D
0x18003f7f4  mov     rcx, [rbp+5Fh]; this
0x18003f7f8  mov     r9d, eax; char *
0x18003f7fb  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003f802  mov     edx, 64h ; 'd'; void *
0x18003f807  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f80c  nop
0x18003f80d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18003f811  call    cs:__imp_VariantClear
0x18003f817  mov     rcx, [rbp+5Fh]; this
0x18003f81b  test    eax, eax
0x18003f81d  jns     short loc_18003F833
0x18003f81f  mov     r9d, eax; char *
0x18003f822  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003f829  mov     edx, 53h ; 'S'; void *
0x18003f82e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003f833  lea     rcx, [rbp+57h+var_50]; pvarg
0x18003f837  call    cs:__imp_VariantClear
0x18003f83d  mov     rcx, [rbp+5Fh]; this
0x18003f841  test    eax, eax
0x18003f843  jns     short loc_18003F85A
0x18003f845  mov     r9d, eax; char *
0x18003f848  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003f84f  mov     edx, 54h ; 'T'; void *
0x18003f854  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003f859  nop
0x18003f85a  lea     rcx, [rbp+57h+arg_18]
0x18003f85e  call    ??1?$com_ptr_t@UITaskSchedulerEx2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(void)
0x18003f863  nop
0x18003f864  cmp     [rbp+57h+arg_0], 0
0x18003f868  jmp     loc_18003F68A
0x18003f86d  cmp     dword ptr [rbp+57h+var_60+4], 1
0x18003f871  jnz     short loc_18003F883
0x18003f873  cmp     word ptr [rbp+57h+var_50], 3
0x18003f878  jnz     short loc_18003F883
0x18003f87a  mov     edi, dword ptr [rbp+57h+pvarg+8]
0x18003f87d  mov     esi, dword ptr [rbp+57h+var_50+8]
0x18003f880  mov     r14b, 1
0x18003f883  mov     [r13+0], edi
0x18003f887  mov     [r12], esi
0x18003f88b  mov     [r15], r14b
0x18003f88e  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18003f892  call    cs:__imp_VariantClear
0x18003f898  mov     rcx, [rbp+5Fh]; this
0x18003f89c  test    eax, eax
0x18003f89e  jns     short loc_18003F8B4
0x18003f8a0  mov     r9d, eax; char *
0x18003f8a3  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003f8aa  mov     edx, 53h ; 'S'; void *
0x18003f8af  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003f8b4  lea     rcx, [rbp+57h+var_50]; pvarg
0x18003f8b8  call    cs:__imp_VariantClear
0x18003f8be  mov     rcx, [rbp+5Fh]; this
0x18003f8c2  test    eax, eax
0x18003f8c4  jns     short loc_18003F8DB
0x18003f8c6  mov     r9d, eax; char *
0x18003f8c9  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003f8d0  mov     edx, 54h ; 'T'; void *
0x18003f8d5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003f8da  nop
0x18003f8db  lea     rcx, [rbp+57h+arg_18]
0x18003f8df  call    ??1?$com_ptr_t@UITaskSchedulerEx2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(void)
0x18003f8e4  nop
0x18003f8e5  cmp     [rbp+57h+arg_0], 0
0x18003f8e9  jz      short loc_18003F8F1
0x18003f8eb  call    cs:__imp_CoUninitialize
0x18003f8f1  xor     eax, eax
0x18003f8f3  mov     rbx, [rsp+0D0h+arg_8]
0x18003f8fb  add     rsp, 0A0h
0x18003f902  pop     r15
0x18003f904  pop     r14
0x18003f906  pop     r13
0x18003f908  pop     r12
0x18003f90a  pop     rdi
0x18003f90b  pop     rsi
0x18003f90c  pop     rbp
0x18003f90d  retn
```
