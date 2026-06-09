# FwAllowedProgramAdd(ushort const *,ushort const *,FW_SCOPE_,ushort const *,FW_MODE_)

- ea: `0x180033c98`
- end: `0x180033f47`
- name: `?FwAllowedProgramAdd@@YAJPEBG0W4FW_SCOPE_@@0W4FW_MODE_@@@Z`
- size: `687`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800357c0`

## callees

- `0x1800246a4`
- `0x18002508c`
- `0x18002527c`
- `0x1800277b0`
- `0x18003104c`
- `0x180033c98`
- `0x18005e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180033d4d`
- `OLEAUT32!__imp_SysFreeString` at `0x180033dc4`
- `OLEAUT32!__imp_SysFreeString` at `0x180033e19`
- `OLEAUT32!__imp_SysFreeString` at `0x180033e58`
- `OLEAUT32!__imp_SysFreeString` at `0x180033d4d`
- `OLEAUT32!__imp_SysFreeString` at `0x180033dc4`
- `OLEAUT32!__imp_SysFreeString` at `0x180033e19`
- `OLEAUT32!__imp_SysFreeString` at `0x180033e58`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033d78`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033d78`
- `fwbase!FwNtStatusToHResult` at `0x180033e6b`
- `fwbase!FwNtStatusToHResult` at `0x180033e6b`
- `fwbase!FwReportReturnError` at `0x180033ef5`
- `fwbase!FwReportReturnError` at `0x180033f22`
- `fwbase!FwReportReturnError` at `0x180033ef5`
- `fwbase!FwReportReturnError` at `0x180033f22`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FwAllowedProgramAdd(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        int a5)
{
  HRESULT v9; // eax
  int v10; // ebx
  HRESULT (__stdcall *Item)(INetFwAuthorizedApplications *, BSTR, INetFwAuthorizedApplication **); // rbx
  _QWORD *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 (__fastcall *v15)(LPVOID, _QWORD); // rbx
  _QWORD *v16; // rax
  int v17; // esi
  LPVOID v18; // r8
  __int64 (__fastcall *v19)(LPVOID, _QWORD); // rbx
  _QWORD *v20; // rax
  __int64 (__fastcall *v21)(LPVOID, _QWORD); // rbx
  _QWORD *v22; // rax
  BSTR bstrString; // [rsp+30h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-18h] BYREF
  struct INetFwAuthorizedApplications *v26; // [rsp+40h] [rbp-10h] BYREF

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_b0516bc2b3bb3db5719010192741acba_Traceguids);
  ppv = 0;
  v26 = 0;
  v9 = FwAllowedProgramInit(&v26);
  v10 = v9;
  if ( v9 < 0 )
    goto LABEL_30;
  Item = v26->lpVtbl->Item;
  v12 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, a1);
  v10 = ((__int64 (__fastcall *)(struct INetFwAuthorizedApplications *, _QWORD, LPVOID *))Item)(v26, *v12, &ppv);
  SysFreeString(bstrString);
  if ( v10 == -2147024894 )
  {
    v9 = CoCreateInstance(
           &GUID_ec9846b3_2762_4a6b_a214_6acb603462d2,
           0,
           1u,
           &GUID_b5e64ffa_c2c5_444e_a301_fb5e00018050,
           &ppv);
    v10 = v9;
    if ( v9 < 0 )
      goto LABEL_30;
    if ( !ppv )
    {
LABEL_8:
      v14 = 2147549183LL;
LABEL_31:
      FwReportReturnError("FwAllowedProgramAdd", v14);
      goto LABEL_32;
    }
    v15 = *(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 80LL);
    v16 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, a1);
    v10 = v15(ppv, *v16);
    SysFreeString(bstrString);
    if ( v10 < 0 )
    {
LABEL_10:
      v14 = (unsigned int)v10;
      goto LABEL_31;
    }
    v17 = 0;
  }
  else
  {
    if ( v10 < 0 )
      goto LABEL_10;
    v17 = 1;
  }
  v18 = ppv;
  if ( !ppv )
    goto LABEL_8;
  if ( a2 )
  {
    v19 = *(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 64LL);
    v20 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, a2);
    v10 = v19(ppv, *v20);
    SysFreeString(bstrString);
    if ( v10 < 0 )
      goto LABEL_10;
    v18 = ppv;
  }
  if ( a3 == 2 )
  {
    v21 = *(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v18 + 128LL);
    v22 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, a4);
    v10 = v21(ppv, *v22);
    SysFreeString(bstrString);
    if ( v10 == -2147024883 || v10 == (unsigned int)FwNtStatusToHResult(3221225485LL) )
    {
      v10 = -2147023189;
      goto LABEL_10;
    }
    if ( v10 < 0 )
      goto LABEL_10;
    goto LABEL_26;
  }
  if ( a3 != 3 )
  {
    v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v18 + 112LL))(v18, a3);
    v10 = v9;
    if ( v9 >= 0 )
    {
LABEL_26:
      v18 = ppv;
      goto LABEL_27;
    }
LABEL_30:
    v14 = (unsigned int)v9;
    goto LABEL_31;
  }
LABEL_27:
  LOWORD(v13) = -((unsigned int)(a5 - 1) <= 1);
  v9 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v18 + 144LL))(v18, v13);
  v10 = v9;
  if ( v9 < 0 )
    goto LABEL_30;
  if ( !v17 )
  {
    v9 = ((__int64 (__fastcall *)(struct INetFwAuthorizedApplications *, LPVOID))v26->lpVtbl->Add)(v26, ppv);
    v10 = v9;
    if ( v9 < 0 )
      goto LABEL_30;
  }
LABEL_32:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  FwAllowedProgramFree(&v26);
  if ( v10 < 0 )
    return (unsigned int)FwReportReturnError("FwAllowedProgramAdd", (unsigned int)v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180033c98  push    rbp
0x180033c9a  push    rbx
0x180033c9b  push    rsi
0x180033c9c  push    rdi
0x180033c9d  push    r12
0x180033c9f  push    r14
0x180033ca1  push    r15
0x180033ca3  mov     rbp, rsp
0x180033ca6  sub     rsp, 50h
0x180033caa  mov     rax, cs:__security_cookie
0x180033cb1  xor     rax, rsp
0x180033cb4  mov     [rbp+var_8], rax
0x180033cb8  mov     r15, r9
0x180033cbb  mov     edi, r8d
0x180033cbe  mov     r14, rdx
0x180033cc1  mov     rsi, rcx
0x180033cc4  lea     rax, WPP_GLOBAL_Control
0x180033ccb  mov     rcx, cs:WPP_GLOBAL_Control
0x180033cd2  cmp     rcx, rax
0x180033cd5  jz      short loc_180033CF2
0x180033cd7  test    byte ptr [rcx+1Ch], 8
0x180033cdb  jz      short loc_180033CF2
0x180033cdd  mov     edx, 12h
0x180033ce2  lea     r8, WPP_b0516bc2b3bb3db5719010192741acba_Traceguids
0x180033ce9  mov     rcx, [rcx+10h]
0x180033ced  call    WPP_SF_
0x180033cf2  mov     [rbp+var_18], 0
0x180033cfa  mov     [rbp+var_10], 0
0x180033d02  lea     rcx, [rbp+var_10]; struct INetFwAuthorizedApplications **
0x180033d06  call    ?FwAllowedProgramInit@@YAJPEAPEAUINetFwAuthorizedApplications@@@Z; FwAllowedProgramInit(INetFwAuthorizedApplications * *)
0x180033d0b  mov     ebx, eax
0x180033d0d  lea     r12, aFwallowedprogr_5; "FwAllowedProgramAdd"
0x180033d14  test    eax, eax
0x180033d16  js      loc_180033EF0
0x180033d1c  mov     rax, [rbp+var_10]
0x180033d20  mov     rcx, [rax]
0x180033d23  mov     rbx, [rcx+50h]
0x180033d27  mov     rdx, rsi; unsigned __int16 *
0x180033d2a  lea     rcx, [rbp+bstrString]; this
0x180033d2e  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180033d33  nop
0x180033d34  lea     r8, [rbp+var_18]
0x180033d38  mov     rdx, [rax]
0x180033d3b  mov     rcx, [rbp+var_10]
0x180033d3f  mov     rax, rbx
0x180033d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033d47  mov     ebx, eax
0x180033d49  mov     rcx, [rbp+bstrString]; bstrString
0x180033d4d  call    cs:__imp_SysFreeString
0x180033d53  cmp     ebx, 80070002h
0x180033d59  jnz     short loc_180033DD9
0x180033d5b  lea     rax, [rbp+var_18]
0x180033d5f  mov     [rsp+50h+ppv], rax; ppv
0x180033d64  lea     r9, _GUID_b5e64ffa_c2c5_444e_a301_fb5e00018050; riid
0x180033d6b  xor     edx, edx; pUnkOuter
0x180033d6d  lea     r8d, [rdx+1]; dwClsContext
0x180033d71  lea     rcx, _GUID_ec9846b3_2762_4a6b_a214_6acb603462d2; rclsid
0x180033d78  call    cs:__imp_CoCreateInstance
0x180033d7e  mov     ebx, eax
0x180033d80  test    eax, eax
0x180033d82  js      loc_180033EF0
0x180033d88  mov     rax, [rbp+var_18]
0x180033d8c  test    rax, rax
0x180033d8f  jnz     short loc_180033D9B
0x180033d91  mov     edx, 8000FFFFh
0x180033d96  jmp     loc_180033EF2
0x180033d9b  mov     rax, [rax]
0x180033d9e  mov     rbx, [rax+50h]
0x180033da2  mov     rdx, rsi; unsigned __int16 *
0x180033da5  lea     rcx, [rbp+bstrString]; this
0x180033da9  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180033dae  nop
0x180033daf  mov     rdx, [rax]
0x180033db2  mov     rcx, [rbp+var_18]
0x180033db6  mov     rax, rbx
0x180033db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033dbe  mov     ebx, eax
0x180033dc0  mov     rcx, [rbp+bstrString]; bstrString
0x180033dc4  call    cs:__imp_SysFreeString
0x180033dca  test    ebx, ebx
0x180033dcc  jns     short loc_180033DD5
0x180033dce  mov     edx, ebx
0x180033dd0  jmp     loc_180033EF2
0x180033dd5  xor     esi, esi
0x180033dd7  jmp     short loc_180033DE2
0x180033dd9  test    ebx, ebx
0x180033ddb  js      short loc_180033DCE
0x180033ddd  mov     esi, 1
0x180033de2  mov     r8, [rbp+var_18]
0x180033de6  test    r8, r8
0x180033de9  jz      short loc_180033D91
0x180033deb  test    r14, r14
0x180033dee  jz      short loc_180033E27
0x180033df0  mov     rax, [r8]
0x180033df3  mov     rbx, [rax+40h]
0x180033df7  mov     rdx, r14; unsigned __int16 *
0x180033dfa  lea     rcx, [rbp+bstrString]; this
0x180033dfe  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180033e03  nop
0x180033e04  mov     rdx, [rax]
0x180033e07  mov     rcx, [rbp+var_18]
0x180033e0b  mov     rax, rbx
0x180033e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e13  mov     ebx, eax
0x180033e15  mov     rcx, [rbp+bstrString]; bstrString
0x180033e19  call    cs:__imp_SysFreeString
0x180033e1f  test    ebx, ebx
0x180033e21  js      short loc_180033DCE
0x180033e23  mov     r8, [rbp+var_18]
0x180033e27  cmp     edi, 2
0x180033e2a  jnz     short loc_180033E88
0x180033e2c  mov     rax, [r8]
0x180033e2f  mov     rbx, [rax+80h]
0x180033e36  mov     rdx, r15; unsigned __int16 *
0x180033e39  lea     rcx, [rbp+bstrString]; this
0x180033e3d  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180033e42  nop
0x180033e43  mov     rdx, [rax]
0x180033e46  mov     rcx, [rbp+var_18]
0x180033e4a  mov     rax, rbx
0x180033e4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e52  mov     ebx, eax
0x180033e54  mov     rcx, [rbp+bstrString]; bstrString
0x180033e58  call    cs:__imp_SysFreeString
0x180033e5e  cmp     ebx, 8007000Dh
0x180033e64  jz      short loc_180033E7E
0x180033e66  mov     ecx, 0C000000Dh
0x180033e6b  call    cs:__imp_FwNtStatusToHResult
0x180033e71  cmp     ebx, eax
0x180033e73  jz      short loc_180033E7E
0x180033e75  test    ebx, ebx
0x180033e77  jns     short loc_180033EA4
0x180033e79  jmp     loc_180033DCE
0x180033e7e  mov     ebx, 800706ABh
0x180033e83  jmp     loc_180033DCE
0x180033e88  cmp     edi, 3
0x180033e8b  jz      short loc_180033EA8
0x180033e8d  mov     rax, [r8]
0x180033e90  mov     edx, edi
0x180033e92  mov     rcx, r8
0x180033e95  mov     rax, [rax+70h]
0x180033e99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e9e  mov     ebx, eax
0x180033ea0  test    eax, eax
0x180033ea2  js      short loc_180033EF0
0x180033ea4  mov     r8, [rbp+var_18]
0x180033ea8  mov     eax, [rbp+arg_20]
0x180033eab  dec     eax
0x180033ead  xor     ecx, ecx
0x180033eaf  cmp     eax, 1
0x180033eb2  setbe   cl
0x180033eb5  mov     rax, [r8]
0x180033eb8  neg     ecx
0x180033eba  sbb     dx, dx
0x180033ebd  mov     rcx, r8
0x180033ec0  mov     rax, [rax+90h]
0x180033ec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033ecc  mov     ebx, eax
0x180033ece  test    eax, eax
0x180033ed0  js      short loc_180033EF0
0x180033ed2  test    esi, esi
0x180033ed4  jnz     short loc_180033EFB
0x180033ed6  mov     rcx, [rbp+var_10]
0x180033eda  mov     rax, [rcx]
0x180033edd  mov     rdx, [rbp+var_18]
0x180033ee1  mov     rax, [rax+40h]
0x180033ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033eea  mov     ebx, eax
0x180033eec  test    eax, eax
0x180033eee  jns     short loc_180033EFB
0x180033ef0  mov     edx, eax
0x180033ef2  mov     rcx, r12
0x180033ef5  call    cs:__imp_FwReportReturnError
0x180033efb  mov     rcx, [rbp+var_18]
0x180033eff  test    rcx, rcx
0x180033f02  jz      short loc_180033F10
0x180033f04  mov     rax, [rcx]
0x180033f07  mov     rax, [rax+10h]
0x180033f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f10  lea     rcx, [rbp+var_10]; struct INetFwAuthorizedApplications **
0x180033f14  call    ?FwAllowedProgramFree@@YAXPEAPEAUINetFwAuthorizedApplications@@@Z; FwAllowedProgramFree(INetFwAuthorizedApplications * *)
0x180033f19  test    ebx, ebx
0x180033f1b  jns     short loc_180033F2A
0x180033f1d  mov     edx, ebx
0x180033f1f  mov     rcx, r12
0x180033f22  call    cs:__imp_FwReportReturnError
0x180033f28  mov     ebx, eax
0x180033f2a  mov     eax, ebx
0x180033f2c  mov     rcx, [rbp+var_8]
0x180033f30  xor     rcx, rsp; StackCookie
0x180033f33  call    __security_check_cookie
0x180033f38  add     rsp, 50h
0x180033f3c  pop     r15
0x180033f3e  pop     r14
0x180033f40  pop     r12
0x180033f42  pop     rdi
0x180033f43  pop     rsi
0x180033f44  pop     rbx
0x180033f45  pop     rbp
0x180033f46  retn
```
