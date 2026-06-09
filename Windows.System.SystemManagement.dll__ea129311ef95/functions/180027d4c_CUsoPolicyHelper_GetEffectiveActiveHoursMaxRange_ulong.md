# CUsoPolicyHelper::GetEffectiveActiveHoursMaxRange(ulong *)

- ea: `0x180027d4c`
- end: `0x180027f26`
- name: `?GetEffectiveActiveHoursMaxRange@CUsoPolicyHelper@@SAJPEAK@Z`
- size: `474`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800254d0`
- `0x1800281b0`

## callees

- `0x180007d74`
- `0x18000f824`
- `0x180027928`
- `0x180027d4c`
- `0x18002817c`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180027de4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180027eaf`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180027ee5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180027de4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180027eaf`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180027ee5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027e3d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027e3d`
- `OLEAUT32!__imp_VariantInit` at `0x180027d9d`
- `OLEAUT32!__imp_VariantInit` at `0x180027d9d`
- `OLEAUT32!__imp_VariantClear` at `0x180027def`
- `OLEAUT32!__imp_VariantClear` at `0x180027ef0`
- `OLEAUT32!__imp_VariantClear` at `0x180027def`
- `OLEAUT32!__imp_VariantClear` at `0x180027ef0`

## string_xrefs

- `0x180027d72`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`
- `0x180027dcc`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`
- `0x180027e00`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`
- `0x180027e4e`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`
- `0x180027e8d`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`
- `0x180027efd`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CUsoPolicyHelper::GetEffectiveActiveHoursMaxRange(unsigned int *a1)
{
  unsigned int v3; // edx
  int v4; // eax
  unsigned int v5; // edi
  HRESULT v6; // eax
  HRESULT v7; // eax
  int v8; // eax
  unsigned int v9; // eax
  HRESULT v10; // eax
  int ppv; // [rsp+20h] [rbp-50h]
  int ppva; // [rsp+20h] [rbp-50h]
  int ppvb; // [rsp+20h] [rbp-50h]
  __int128 v14; // [rsp+40h] [rbp-30h] BYREF
  _BYTE pvarg[32]; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]
  int v17; // [rsp+80h] [rbp+10h] BYREF
  LPVOID v18; // [rsp+88h] [rbp+18h] BYREF

  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x160,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usopolicyhelperlib\\usopolicyhelper.cpp",
      (const char *)0x80070057LL,
      ppv);
    return 2147942487LL;
  }
  v14 = 0;
  memset(pvarg, 0, sizeof(pvarg));
  VariantInit((VARIANTARG *)pvarg);
  v17 = 0;
  v4 = CCoInit::Initialize((CCoInit *)&v17, v3);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16A,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usopolicyhelperlib\\usopolicyhelper.cpp",
      (const char *)(unsigned int)v4,
      ppv);
    if ( v17 )
      CoUninitialize();
LABEL_6:
    v6 = VariantClear((VARIANTARG *)pvarg);
    if ( v6 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x166,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usopolicyhelperlib\\usopolicyhelper.cpp",
        (const char *)(unsigned int)v6,
        ppva);
    return v5;
  }
  v18 = 0;
  v7 = CoCreateInstance(
         &GUID_07369a67_07a6_4608_abea_379491cb7c46,
         0,
         1u,
         &GUID_152807bd_4d18_46c5_ae31_dd8d597d0559,
         &v18);
  if ( v7 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int128 *))(*(_QWORD *)v18 + 32LL))(v18, 22, &v14);
    v5 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17E,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usopolicyhelperlib\\usopolicyhelper.cpp",
        (const char *)(unsigned int)v8,
        ppvb);
      wil::com_ptr_t<IUpdatePolicyReader,wil::err_returncode_policy>::~com_ptr_t<IUpdatePolicyReader,wil::err_returncode_policy>((__int64 *)&v18);
      if ( v17 )
        CoUninitialize();
      goto LABEL_6;
    }
    v9 = 18;
    if ( DWORD1(v14) == 1 && *(_WORD *)pvarg == 3 )
      v9 = *(_DWORD *)&pvarg[8];
    *a1 = v9;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x171,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usopolicyhelperlib\\usopolicyhelper.cpp",
      (const char *)(unsigned int)v7,
      ppvb);
    *a1 = 18;
  }
  wil::com_ptr_t<IUpdatePolicyReader,wil::err_returncode_policy>::~com_ptr_t<IUpdatePolicyReader,wil::err_returncode_policy>((__int64 *)&v18);
  if ( v17 )
    CoUninitialize();
  v10 = VariantClear((VARIANTARG *)pvarg);
  if ( v10 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usopolicyhelperlib\\usopolicyhelper.cpp",
      (const char *)(unsigned int)v10,
      ppvb);
  return 0;
}

```

## disassembly

```asm
0x180027d4c  mov     [rsp-8+arg_10], rbx
0x180027d51  mov     [rsp-8+arg_18], rdi
0x180027d56  push    rbp
0x180027d57  mov     rbp, rsp
0x180027d5a  sub     rsp, 70h
0x180027d5e  mov     rbx, rcx
0x180027d61  test    rcx, rcx
0x180027d64  jnz     short loc_180027D8A
0x180027d66  mov     rcx, [rbp+8]; this
0x180027d6a  mov     ebx, 80070057h
0x180027d6f  mov     r9d, ebx; char *
0x180027d72  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180027d79  mov     edx, 160h; void *
0x180027d7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027d83  mov     eax, ebx
0x180027d85  jmp     loc_180027F14
0x180027d8a  xorps   xmm0, xmm0
0x180027d8d  movups  [rbp+var_30], xmm0
0x180027d91  movups  xmmword ptr [rbp+pvarg], xmm0
0x180027d95  movups  xmmword ptr [rbp+pvarg+10h], xmm0
0x180027d99  lea     rcx, [rbp+pvarg]; pvarg
0x180027d9d  call    cs:__imp_VariantInit
0x180027da3  lea     rax, [rbp+var_30]
0x180027da7  mov     [rbp+var_40], rax
0x180027dab  mov     [rbp+var_38], 1
0x180027daf  mov     [rbp+arg_0], 0
0x180027db6  lea     rcx, [rbp+arg_0]; this
0x180027dba  call    ?Initialize@CCoInit@@QEAAJK@Z; CCoInit::Initialize(ulong)
0x180027dbf  mov     edi, eax
0x180027dc1  test    eax, eax
0x180027dc3  jns     short loc_180027E18
0x180027dc5  mov     rcx, [rbp+8]; this
0x180027dc9  mov     r9d, eax; char *
0x180027dcc  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180027dd3  mov     edx, 16Ah; void *
0x180027dd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027ddd  nop
0x180027dde  cmp     [rbp+arg_0], 0
0x180027de2  jz      short loc_180027DEB
0x180027de4  call    cs:__imp_CoUninitialize
0x180027dea  nop
0x180027deb  lea     rcx, [rbp+pvarg]; pvarg
0x180027def  call    cs:__imp_VariantClear
0x180027df5  test    eax, eax
0x180027df7  jns     short loc_180027E11
0x180027df9  mov     rcx, [rbp+8]; this
0x180027dfd  mov     r9d, eax; char *
0x180027e00  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180027e07  mov     edx, 166h; void *
0x180027e0c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027e11  mov     eax, edi
0x180027e13  jmp     loc_180027F14
0x180027e18  mov     [rbp+arg_8], 0
0x180027e20  lea     rax, [rbp+arg_8]
0x180027e24  mov     qword ptr [rsp+70h+ppv], rax; int
0x180027e29  lea     r9, _GUID_152807bd_4d18_46c5_ae31_dd8d597d0559; riid
0x180027e30  xor     edx, edx; pUnkOuter
0x180027e32  lea     r8d, [rdx+1]; dwClsContext
0x180027e36  lea     rcx, _GUID_07369a67_07a6_4608_abea_379491cb7c46; rclsid
0x180027e3d  call    cs:__imp_CoCreateInstance
0x180027e43  mov     rcx, [rbp+8]; this
0x180027e47  test    eax, eax
0x180027e49  jns     short loc_180027E67
0x180027e4b  mov     r9d, eax; char *
0x180027e4e  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180027e55  mov     edx, 171h; void *
0x180027e5a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027e5f  mov     dword ptr [rbx], 12h
0x180027e65  jmp     short loc_180027ED5
0x180027e67  mov     rcx, [rbp+arg_8]
0x180027e6b  mov     rax, [rcx]
0x180027e6e  lea     r8, [rbp+var_30]
0x180027e72  mov     edx, 16h
0x180027e77  mov     rax, [rax+20h]
0x180027e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e80  mov     edi, eax
0x180027e82  test    eax, eax
0x180027e84  jns     short loc_180027EBF
0x180027e86  mov     rcx, [rbp+8]; this
0x180027e8a  mov     r9d, eax; char *
0x180027e8d  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180027e94  mov     edx, 17Eh; void *
0x180027e99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027e9e  nop
0x180027e9f  lea     rcx, [rbp+arg_8]
0x180027ea3  call    ??1?$com_ptr_t@UIUpdatePolicyReader@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUpdatePolicyReader,wil::err_returncode_policy>::~com_ptr_t<IUpdatePolicyReader,wil::err_returncode_policy>(void)
0x180027ea8  nop
0x180027ea9  cmp     [rbp+arg_0], 0
0x180027ead  jz      short loc_180027EB6
0x180027eaf  call    cs:__imp_CoUninitialize
0x180027eb5  nop
0x180027eb6  lea     rcx, [rbp+pvarg]
0x180027eba  jmp     loc_180027DEF
0x180027ebf  mov     eax, 12h
0x180027ec4  cmp     dword ptr [rbp+var_30+4], 1
0x180027ec8  jnz     short loc_180027ED3
0x180027eca  cmp     word ptr [rbp+pvarg], 3
0x180027ecf  cmovz   eax, dword ptr [rbp+pvarg+8]
0x180027ed3  mov     [rbx], eax
0x180027ed5  lea     rcx, [rbp+arg_8]
0x180027ed9  call    ??1?$com_ptr_t@UIUpdatePolicyReader@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUpdatePolicyReader,wil::err_returncode_policy>::~com_ptr_t<IUpdatePolicyReader,wil::err_returncode_policy>(void)
0x180027ede  nop
0x180027edf  cmp     [rbp+arg_0], 0
0x180027ee3  jz      short loc_180027EEC
0x180027ee5  call    cs:__imp_CoUninitialize
0x180027eeb  nop
0x180027eec  lea     rcx, [rbp+pvarg]; pvarg
0x180027ef0  call    cs:__imp_VariantClear
0x180027ef6  test    eax, eax
0x180027ef8  jns     short loc_180027F12
0x180027efa  mov     r9d, eax; char *
0x180027efd  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180027f04  mov     edx, 166h; void *
0x180027f09  mov     rcx, [rbp+8]; this
0x180027f0d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027f12  xor     eax, eax
0x180027f14  lea     r11, [rsp+70h+var_s0]
0x180027f19  mov     rbx, [r11+20h]
0x180027f1d  mov     rdi, [r11+28h]
0x180027f21  mov     rsp, r11
0x180027f24  pop     rbp
0x180027f25  retn
```
