# HelpUtil::LaunchHelp(ushort const *,ushort const *)

- ea: `0x18002f3d8`
- end: `0x18002f493`
- name: `?LaunchHelp@HelpUtil@@YAXPEBG0@Z`
- size: `187`
- prototype: `void __fastcall(HelpUtil *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002db88`
- `0x18003c400`
- `0x1800694fc`

## callees

- `0x18000cb74`
- `0x18002f3d8`
- `0x18005e18c`
- `0x180080010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002f461`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f461`
- `ole32!CoCreateInstance` at `0x18002f41f`
- `ole32!CoCreateInstance` at `0x18002f41f`
- `PhotoBase!?RecordHelpEntryPoint@Sqm@@YAXPEBG@Z` at `0x18002f3f2`
- `PhotoBase!?RecordHelpEntryPoint@Sqm@@YAXPEBG@Z` at `0x18002f3f2`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002f42b`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002f472`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002f42b`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002f472`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall HelpUtil::LaunchHelp(HelpUtil *this, Sqm *a2, const unsigned __int16 *a3)
{
  HRESULT v4; // eax
  int v5; // edx
  LPVOID v6; // rdi
  __int64 (__fastcall *v7)(LPVOID, _QWORD); // rbx
  _QWORD *v8; // rax
  int v9; // ebx
  int v10; // edx
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp+18h] BYREF

  if ( a2 )
    Sqm::RecordHelpEntryPoint(a2, (const unsigned __int16 *)a2);
  ppv = 0;
  v4 = CoCreateInstance(&CLSID_HxHelpPane, 0, 0x17u, &GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee, &ppv);
  if ( v4 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v4, v5);
    __debugbreak();
  }
  v6 = ppv;
  v7 = *(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 24LL);
  v8 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, (const unsigned __int16 *)this);
  v9 = v7(v6, *v8);
  SysFreeString(bstrString);
  if ( v9 < 0 )
    Base::Throw((Base *)(unsigned int)v9, v10);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&ppv);
}

```

## disassembly

```asm
0x18002f3d8  mov     [rsp+arg_0], rbx
0x18002f3dd  mov     [rsp+arg_18], rsi
0x18002f3e2  push    rdi
0x18002f3e3  sub     rsp, 30h
0x18002f3e7  mov     rsi, rcx
0x18002f3ea  test    rdx, rdx
0x18002f3ed  jz      short loc_18002F3F8
0x18002f3ef  mov     rcx, rdx
0x18002f3f2  call    cs:__imp_?RecordHelpEntryPoint@Sqm@@YAXPEBG@Z; Sqm::RecordHelpEntryPoint(ushort const *)
0x18002f3f8  mov     [rsp+38h+arg_8], 0
0x18002f401  lea     rax, [rsp+38h+arg_8]
0x18002f406  mov     [rsp+38h+ppv], rax; ppv
0x18002f40b  lea     r9, _GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee; riid
0x18002f412  xor     edx, edx; pUnkOuter
0x18002f414  lea     r8d, [rdx+17h]; dwClsContext
0x18002f418  lea     rcx, CLSID_HxHelpPane; rclsid
0x18002f41f  call    cs:__imp_CoCreateInstance
0x18002f425  test    eax, eax
0x18002f427  jns     short loc_18002F432
0x18002f429  mov     ecx, eax
0x18002f42b  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18002f431  int     3; Trap to Debugger
0x18002f432  mov     rdi, [rsp+38h+arg_8]
0x18002f437  mov     rax, [rdi]
0x18002f43a  mov     rbx, [rax+18h]
0x18002f43e  mov     rdx, rsi; unsigned __int16 *
0x18002f441  lea     rcx, [rsp+38h+bstrString]; this
0x18002f446  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18002f44b  nop
0x18002f44c  mov     rdx, [rax]
0x18002f44f  mov     rcx, rdi
0x18002f452  mov     rax, rbx
0x18002f455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f45a  mov     ebx, eax
0x18002f45c  mov     rcx, [rsp+38h+bstrString]; bstrString
0x18002f461  call    cs:__imp_SysFreeString
0x18002f467  mov     ecx, ebx
0x18002f469  shr     ecx, 1Fh
0x18002f46c  test    cl, cl
0x18002f46e  jz      short loc_18002F479
0x18002f470  mov     ecx, ebx
0x18002f472  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18002f478  nop
0x18002f479  lea     rcx, [rsp+38h+arg_8]
0x18002f47e  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18002f483  mov     rbx, [rsp+38h+arg_0]
0x18002f488  mov     rsi, [rsp+38h+arg_18]
0x18002f48d  add     rsp, 30h
0x18002f491  pop     rdi
0x18002f492  retn
```
