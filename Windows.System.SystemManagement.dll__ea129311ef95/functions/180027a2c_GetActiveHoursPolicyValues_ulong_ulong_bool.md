# GetActiveHoursPolicyValues(ulong *,ulong *,bool *)

- ea: `0x180027a2c`
- end: `0x180027d46`
- name: `?GetActiveHoursPolicyValues@@YAJPEAK0PEA_N@Z`
- size: `794`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int *, bool *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180027f2c`
- `0x1800281b0`

## callees

- `0x180007d74`
- `0x18000f824`
- `0x180027928`
- `0x180027a2c`
- `0x18002817c`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180027ac4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180027d23`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180027ac4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180027d23`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027aed`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027aed`
- `OLEAUT32!__imp_VariantInit` at `0x180027b41`
- `OLEAUT32!__imp_VariantInit` at `0x180027b4b`
- `OLEAUT32!__imp_VariantInit` at `0x180027b41`
- `OLEAUT32!__imp_VariantInit` at `0x180027b4b`
- `OLEAUT32!__imp_VariantClear` at `0x180027ba1`
- `OLEAUT32!__imp_VariantClear` at `0x180027bc7`
- `OLEAUT32!__imp_VariantClear` at `0x180027c49`
- `OLEAUT32!__imp_VariantClear` at `0x180027c6f`
- `OLEAUT32!__imp_VariantClear` at `0x180027cca`
- `OLEAUT32!__imp_VariantClear` at `0x180027cf0`
- `OLEAUT32!__imp_VariantClear` at `0x180027ba1`
- `OLEAUT32!__imp_VariantClear` at `0x180027bc7`
- `OLEAUT32!__imp_VariantClear` at `0x180027c49`
- `OLEAUT32!__imp_VariantClear` at `0x180027c6f`
- `OLEAUT32!__imp_VariantClear` at `0x180027cca`
- `OLEAUT32!__imp_VariantClear` at `0x180027cf0`

## string_xrefs

- `0x180027a68`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`
- `0x180027aac`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`
- `0x180027b00`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`
- `0x180027b8b`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`
- `0x180027bb2`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`
- `0x180027bdc`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`
- `0x180027c33`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`
- `0x180027c5a`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`
- `0x180027c80`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`
- `0x180027cdb`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`
- `0x180027d01`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`

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
    wil::com_ptr_t<IUpdatePolicyReader,wil::err_returncode_policy>::~com_ptr_t<IUpdatePolicyReader,wil::err_returncode_policy>((__int64 *)&v33);
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
      wil::com_ptr_t<IUpdatePolicyReader,wil::err_returncode_policy>::~com_ptr_t<IUpdatePolicyReader,wil::err_returncode_policy>((__int64 *)&v33);
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
  wil::com_ptr_t<IUpdatePolicyReader,wil::err_returncode_policy>::~com_ptr_t<IUpdatePolicyReader,wil::err_returncode_policy>((__int64 *)&v33);
  if ( v32 )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x180027a2c  mov     [rsp-8+arg_8], rbx
0x180027a31  push    rbp
0x180027a32  push    rsi
0x180027a33  push    rdi
0x180027a34  push    r12
0x180027a36  push    r13
0x180027a38  push    r14
0x180027a3a  push    r15
0x180027a3c  lea     rbp, [rsp-27h]
0x180027a41  sub     rsp, 0A0h
0x180027a48  mov     r15, r8
0x180027a4b  mov     r12, rdx
0x180027a4e  mov     r13, rcx
0x180027a51  xor     r14d, r14d
0x180027a54  test    rcx, rcx
0x180027a57  jnz     short loc_180027A7B
0x180027a59  lea     edx, [rcx+3Fh]; void *
0x180027a5c  mov     ebx, 80070057h
0x180027a61  mov     rcx, [rbp+5Fh]; this
0x180027a65  mov     r9d, ebx; char *
0x180027a68  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180027a6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027a74  mov     eax, ebx
0x180027a76  jmp     loc_180027D2B
0x180027a7b  test    r12, r12
0x180027a7e  jnz     short loc_180027A87
0x180027a80  lea     edx, [r12+40h]
0x180027a85  jmp     short loc_180027A5C
0x180027a87  test    r15, r15
0x180027a8a  jnz     short loc_180027A92
0x180027a8c  lea     edx, [r15+41h]; unsigned int
0x180027a90  jmp     short loc_180027A5C
0x180027a92  mov     [rbp+57h+arg_0], r14d
0x180027a96  lea     rcx, [rbp+57h+arg_0]; this
0x180027a9a  call    ?Initialize@CCoInit@@QEAAJK@Z; CCoInit::Initialize(ulong)
0x180027a9f  mov     ebx, eax
0x180027aa1  test    eax, eax
0x180027aa3  jns     short loc_180027ACC
0x180027aa5  mov     rcx, [rbp+5Fh]; this
0x180027aa9  mov     r9d, eax; char *
0x180027aac  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180027ab3  mov     edx, 44h ; 'D'; void *
0x180027ab8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027abd  nop
0x180027abe  cmp     [rbp+57h+arg_0], r14d
0x180027ac2  jz      short loc_180027A74
0x180027ac4  call    cs:__imp_CoUninitialize
0x180027aca  jmp     short loc_180027A74
0x180027acc  mov     [rbp+57h+arg_18], r14
0x180027ad0  lea     rax, [rbp+57h+arg_18]
0x180027ad4  mov     qword ptr [rsp+0D0h+ppv], rax; int
0x180027ad9  lea     r9, _GUID_152807bd_4d18_46c5_ae31_dd8d597d0559; riid
0x180027ae0  xor     edx, edx; pUnkOuter
0x180027ae2  lea     r8d, [rdx+1]; dwClsContext
0x180027ae6  lea     rcx, _GUID_07369a67_07a6_4608_abea_379491cb7c46; rclsid
0x180027aed  call    cs:__imp_CoCreateInstance
0x180027af3  mov     ebx, eax
0x180027af5  test    eax, eax
0x180027af7  jns     short loc_180027B1D
0x180027af9  mov     rcx, [rbp+5Fh]; this
0x180027afd  mov     r9d, eax; char *
0x180027b00  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180027b07  mov     edx, 4Bh ; 'K'; void *
0x180027b0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027b11  nop
0x180027b12  lea     rcx, [rbp+57h+arg_18]
0x180027b16  call    ??1?$com_ptr_t@UIUpdatePolicyReader@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUpdatePolicyReader,wil::err_returncode_policy>::~com_ptr_t<IUpdatePolicyReader,wil::err_returncode_policy>(void)
0x180027b1b  jmp     short loc_180027ABE
0x180027b1d  xorps   xmm0, xmm0
0x180027b20  xor     eax, eax
0x180027b22  movups  [rbp+57h+var_88], xmm0
0x180027b26  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180027b2a  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180027b2e  xorps   xmm1, xmm1
0x180027b31  movups  [rbp+57h+var_60], xmm1
0x180027b35  movups  xmmword ptr [rbp+57h+var_50], xmm1
0x180027b39  mov     qword ptr [rbp+57h+var_50+10h], rax
0x180027b3d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180027b41  call    cs:__imp_VariantInit
0x180027b47  lea     rcx, [rbp+57h+var_50]; pvarg
0x180027b4b  call    cs:__imp_VariantInit
0x180027b51  lea     rax, [rbp+57h+var_88]
0x180027b55  mov     [rbp+57h+var_A0], rax
0x180027b59  lea     rax, [rbp+57h+var_60]
0x180027b5d  mov     [rbp+57h+var_98], rax
0x180027b61  mov     [rbp+57h+var_90], 1
0x180027b65  mov     rcx, [rbp+57h+arg_18]
0x180027b69  mov     rax, [rcx]
0x180027b6c  lea     r8, [rbp+57h+var_88]
0x180027b70  mov     edx, 17h
0x180027b75  mov     rax, [rax+18h]
0x180027b79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b7e  mov     ebx, eax
0x180027b80  test    eax, eax
0x180027b82  jns     short loc_180027BF2
0x180027b84  mov     rcx, [rbp+5Fh]; this
0x180027b88  mov     r9d, eax; char *
0x180027b8b  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180027b92  mov     edx, 5Dh ; ']'; void *
0x180027b97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027b9c  nop
0x180027b9d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180027ba1  call    cs:__imp_VariantClear
0x180027ba7  mov     rcx, [rbp+5Fh]; this
0x180027bab  test    eax, eax
0x180027bad  jns     short loc_180027BC3
0x180027baf  mov     r9d, eax; char *
0x180027bb2  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180027bb9  mov     edx, 53h ; 'S'; void *
0x180027bbe  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027bc3  lea     rcx, [rbp+57h+var_50]; pvarg
0x180027bc7  call    cs:__imp_VariantClear
0x180027bcd  mov     rcx, [rbp+5Fh]; this
0x180027bd1  test    eax, eax
0x180027bd3  jns     loc_180027B12
0x180027bd9  mov     r9d, eax; char *
0x180027bdc  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180027be3  mov     edx, 54h ; 'T'; void *
0x180027be8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027bed  jmp     loc_180027B12
0x180027bf2  mov     edi, r14d
0x180027bf5  mov     esi, r14d
0x180027bf8  cmp     dword ptr [rbp+57h+var_88+4], 1
0x180027bfc  jnz     loc_180027CBB
0x180027c02  cmp     word ptr [rbp+57h+pvarg], 3
0x180027c07  jnz     loc_180027CBB
0x180027c0d  mov     rcx, [rbp+57h+arg_18]
0x180027c11  mov     rax, [rcx]
0x180027c14  lea     r8, [rbp+57h+var_60]
0x180027c18  mov     edx, 18h
0x180027c1d  mov     rax, [rax+18h]
0x180027c21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c26  mov     ebx, eax
0x180027c28  test    eax, eax
0x180027c2a  jns     short loc_180027CA5
0x180027c2c  mov     rcx, [rbp+5Fh]; this
0x180027c30  mov     r9d, eax; char *
0x180027c33  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180027c3a  mov     edx, 64h ; 'd'; void *
0x180027c3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027c44  nop
0x180027c45  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180027c49  call    cs:__imp_VariantClear
0x180027c4f  mov     rcx, [rbp+5Fh]; this
0x180027c53  test    eax, eax
0x180027c55  jns     short loc_180027C6B
0x180027c57  mov     r9d, eax; char *
0x180027c5a  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180027c61  mov     edx, 53h ; 'S'; void *
0x180027c66  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027c6b  lea     rcx, [rbp+57h+var_50]; pvarg
0x180027c6f  call    cs:__imp_VariantClear
0x180027c75  mov     rcx, [rbp+5Fh]; this
0x180027c79  test    eax, eax
0x180027c7b  jns     short loc_180027C92
0x180027c7d  mov     r9d, eax; char *
0x180027c80  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180027c87  mov     edx, 54h ; 'T'; void *
0x180027c8c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027c91  nop
0x180027c92  lea     rcx, [rbp+57h+arg_18]
0x180027c96  call    ??1?$com_ptr_t@UIUpdatePolicyReader@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUpdatePolicyReader,wil::err_returncode_policy>::~com_ptr_t<IUpdatePolicyReader,wil::err_returncode_policy>(void)
0x180027c9b  nop
0x180027c9c  cmp     [rbp+57h+arg_0], 0
0x180027ca0  jmp     loc_180027AC2
0x180027ca5  cmp     dword ptr [rbp+57h+var_60+4], 1
0x180027ca9  jnz     short loc_180027CBB
0x180027cab  cmp     word ptr [rbp+57h+var_50], 3
0x180027cb0  jnz     short loc_180027CBB
0x180027cb2  mov     edi, dword ptr [rbp+57h+pvarg+8]
0x180027cb5  mov     esi, dword ptr [rbp+57h+var_50+8]
0x180027cb8  mov     r14b, 1
0x180027cbb  mov     [r13+0], edi
0x180027cbf  mov     [r12], esi
0x180027cc3  mov     [r15], r14b
0x180027cc6  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180027cca  call    cs:__imp_VariantClear
0x180027cd0  mov     rcx, [rbp+5Fh]; this
0x180027cd4  test    eax, eax
0x180027cd6  jns     short loc_180027CEC
0x180027cd8  mov     r9d, eax; char *
0x180027cdb  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180027ce2  mov     edx, 53h ; 'S'; void *
0x180027ce7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027cec  lea     rcx, [rbp+57h+var_50]; pvarg
0x180027cf0  call    cs:__imp_VariantClear
0x180027cf6  mov     rcx, [rbp+5Fh]; this
0x180027cfa  test    eax, eax
0x180027cfc  jns     short loc_180027D13
0x180027cfe  mov     r9d, eax; char *
0x180027d01  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180027d08  mov     edx, 54h ; 'T'; void *
0x180027d0d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027d12  nop
0x180027d13  lea     rcx, [rbp+57h+arg_18]
0x180027d17  call    ??1?$com_ptr_t@UIUpdatePolicyReader@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUpdatePolicyReader,wil::err_returncode_policy>::~com_ptr_t<IUpdatePolicyReader,wil::err_returncode_policy>(void)
0x180027d1c  nop
0x180027d1d  cmp     [rbp+57h+arg_0], 0
0x180027d21  jz      short loc_180027D29
0x180027d23  call    cs:__imp_CoUninitialize
0x180027d29  xor     eax, eax
0x180027d2b  mov     rbx, [rsp+0D0h+arg_8]
0x180027d33  add     rsp, 0A0h
0x180027d3a  pop     r15
0x180027d3c  pop     r14
0x180027d3e  pop     r13
0x180027d40  pop     r12
0x180027d42  pop     rdi
0x180027d43  pop     rsi
0x180027d44  pop     rbp
0x180027d45  retn
```
