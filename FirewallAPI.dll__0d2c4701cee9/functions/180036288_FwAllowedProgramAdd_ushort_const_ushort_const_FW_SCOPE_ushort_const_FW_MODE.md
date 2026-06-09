# FwAllowedProgramAdd(ushort const *,ushort const *,FW_SCOPE_,ushort const *,FW_MODE_)

- ea: `0x180036288`
- end: `0x18003656c`
- name: `?FwAllowedProgramAdd@@YAJPEBG0W4FW_SCOPE_@@0W4FW_MODE_@@@Z`
- size: `740`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180037f60`

## callees

- `0x18002622c`
- `0x180026bdc`
- `0x180026e1c`
- `0x1800294b0`
- `0x18003336c`
- `0x180036288`
- `0x180062010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18003633d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800363c4`
- `OLEAUT32!__imp_SysFreeString` at `0x18003641f`
- `OLEAUT32!__imp_SysFreeString` at `0x180036464`
- `OLEAUT32!__imp_SysFreeString` at `0x18003633d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800363c4`
- `OLEAUT32!__imp_SysFreeString` at `0x18003641f`
- `OLEAUT32!__imp_SysFreeString` at `0x180036464`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180036372`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180036372`
- `fwbase!FwNtStatusToHResult` at `0x18003647d`
- `fwbase!FwNtStatusToHResult` at `0x18003647d`
- `fwbase!FwReportReturnError` at `0x18003650d`
- `fwbase!FwReportReturnError` at `0x180036540`
- `fwbase!FwReportReturnError` at `0x18003650d`
- `fwbase!FwReportReturnError` at `0x180036540`

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
0x180036288  push    rbp
0x18003628a  push    rbx
0x18003628b  push    rsi
0x18003628c  push    rdi
0x18003628d  push    r12
0x18003628f  push    r14
0x180036291  push    r15
0x180036293  mov     rbp, rsp
0x180036296  sub     rsp, 50h
0x18003629a  mov     rax, cs:__security_cookie
0x1800362a1  xor     rax, rsp
0x1800362a4  mov     [rbp+var_8], rax
0x1800362a8  mov     r15, r9
0x1800362ab  mov     edi, r8d
0x1800362ae  mov     r14, rdx
0x1800362b1  mov     rsi, rcx
0x1800362b4  lea     rax, WPP_GLOBAL_Control
0x1800362bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800362c2  cmp     rcx, rax
0x1800362c5  jz      short loc_1800362E2
0x1800362c7  test    byte ptr [rcx+1Ch], 8
0x1800362cb  jz      short loc_1800362E2
0x1800362cd  mov     edx, 12h
0x1800362d2  lea     r8, WPP_b0516bc2b3bb3db5719010192741acba_Traceguids
0x1800362d9  mov     rcx, [rcx+10h]
0x1800362dd  call    WPP_SF_
0x1800362e2  mov     [rbp+var_18], 0
0x1800362ea  mov     [rbp+var_10], 0
0x1800362f2  lea     rcx, [rbp+var_10]; struct INetFwAuthorizedApplications **
0x1800362f6  call    ?FwAllowedProgramInit@@YAJPEAPEAUINetFwAuthorizedApplications@@@Z; FwAllowedProgramInit(INetFwAuthorizedApplications * *)
0x1800362fb  mov     ebx, eax
0x1800362fd  lea     r12, aFwallowedprogr_5; "FwAllowedProgramAdd"
0x180036304  test    eax, eax
0x180036306  js      loc_180036508
0x18003630c  mov     rax, [rbp+var_10]
0x180036310  mov     rcx, [rax]
0x180036313  mov     rbx, [rcx+50h]
0x180036317  mov     rdx, rsi; unsigned __int16 *
0x18003631a  lea     rcx, [rbp+bstrString]; this
0x18003631e  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180036323  nop
0x180036324  lea     r8, [rbp+var_18]
0x180036328  mov     rdx, [rax]
0x18003632b  mov     rcx, [rbp+var_10]
0x18003632f  mov     rax, rbx
0x180036332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036337  mov     ebx, eax
0x180036339  mov     rcx, [rbp+bstrString]; bstrString
0x18003633d  call    cs:__imp_SysFreeString
0x180036344  nop     dword ptr [rax+rax+00h]
0x180036349  cmp     ebx, 80070002h
0x18003634f  jnz     loc_1800363DF
0x180036355  lea     rax, [rbp+var_18]
0x180036359  mov     [rsp+50h+ppv], rax; ppv
0x18003635e  lea     r9, _GUID_b5e64ffa_c2c5_444e_a301_fb5e00018050; riid
0x180036365  xor     edx, edx; pUnkOuter
0x180036367  lea     r8d, [rdx+1]; dwClsContext
0x18003636b  lea     rcx, _GUID_ec9846b3_2762_4a6b_a214_6acb603462d2; rclsid
0x180036372  call    cs:__imp_CoCreateInstance
0x180036379  nop     dword ptr [rax+rax+00h]
0x18003637e  mov     ebx, eax
0x180036380  test    eax, eax
0x180036382  js      loc_180036508
0x180036388  mov     rax, [rbp+var_18]
0x18003638c  test    rax, rax
0x18003638f  jnz     short loc_18003639B
0x180036391  mov     edx, 8000FFFFh
0x180036396  jmp     loc_18003650A
0x18003639b  mov     rax, [rax]
0x18003639e  mov     rbx, [rax+50h]
0x1800363a2  mov     rdx, rsi; unsigned __int16 *
0x1800363a5  lea     rcx, [rbp+bstrString]; this
0x1800363a9  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800363ae  nop
0x1800363af  mov     rdx, [rax]
0x1800363b2  mov     rcx, [rbp+var_18]
0x1800363b6  mov     rax, rbx
0x1800363b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800363be  mov     ebx, eax
0x1800363c0  mov     rcx, [rbp+bstrString]; bstrString
0x1800363c4  call    cs:__imp_SysFreeString
0x1800363cb  nop     dword ptr [rax+rax+00h]
0x1800363d0  test    ebx, ebx
0x1800363d2  jns     short loc_1800363DB
0x1800363d4  mov     edx, ebx
0x1800363d6  jmp     loc_18003650A
0x1800363db  xor     esi, esi
0x1800363dd  jmp     short loc_1800363E8
0x1800363df  test    ebx, ebx
0x1800363e1  js      short loc_1800363D4
0x1800363e3  mov     esi, 1
0x1800363e8  mov     r8, [rbp+var_18]
0x1800363ec  test    r8, r8
0x1800363ef  jz      short loc_180036391
0x1800363f1  test    r14, r14
0x1800363f4  jz      short loc_180036433
0x1800363f6  mov     rax, [r8]
0x1800363f9  mov     rbx, [rax+40h]
0x1800363fd  mov     rdx, r14; unsigned __int16 *
0x180036400  lea     rcx, [rbp+bstrString]; this
0x180036404  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180036409  nop
0x18003640a  mov     rdx, [rax]
0x18003640d  mov     rcx, [rbp+var_18]
0x180036411  mov     rax, rbx
0x180036414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036419  mov     ebx, eax
0x18003641b  mov     rcx, [rbp+bstrString]; bstrString
0x18003641f  call    cs:__imp_SysFreeString
0x180036426  nop     dword ptr [rax+rax+00h]
0x18003642b  test    ebx, ebx
0x18003642d  js      short loc_1800363D4
0x18003642f  mov     r8, [rbp+var_18]
0x180036433  cmp     edi, 2
0x180036436  jnz     short loc_1800364A0
0x180036438  mov     rax, [r8]
0x18003643b  mov     rbx, [rax+80h]
0x180036442  mov     rdx, r15; unsigned __int16 *
0x180036445  lea     rcx, [rbp+bstrString]; this
0x180036449  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18003644e  nop
0x18003644f  mov     rdx, [rax]
0x180036452  mov     rcx, [rbp+var_18]
0x180036456  mov     rax, rbx
0x180036459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003645e  mov     ebx, eax
0x180036460  mov     rcx, [rbp+bstrString]; bstrString
0x180036464  call    cs:__imp_SysFreeString
0x18003646b  nop     dword ptr [rax+rax+00h]
0x180036470  cmp     ebx, 8007000Dh
0x180036476  jz      short loc_180036496
0x180036478  mov     ecx, 0C000000Dh
0x18003647d  call    cs:__imp_FwNtStatusToHResult
0x180036484  nop     dword ptr [rax+rax+00h]
0x180036489  cmp     ebx, eax
0x18003648b  jz      short loc_180036496
0x18003648d  test    ebx, ebx
0x18003648f  jns     short loc_1800364BC
0x180036491  jmp     loc_1800363D4
0x180036496  mov     ebx, 800706ABh
0x18003649b  jmp     loc_1800363D4
0x1800364a0  cmp     edi, 3
0x1800364a3  jz      short loc_1800364C0
0x1800364a5  mov     rax, [r8]
0x1800364a8  mov     edx, edi
0x1800364aa  mov     rcx, r8
0x1800364ad  mov     rax, [rax+70h]
0x1800364b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800364b6  mov     ebx, eax
0x1800364b8  test    eax, eax
0x1800364ba  js      short loc_180036508
0x1800364bc  mov     r8, [rbp+var_18]
0x1800364c0  mov     eax, [rbp+arg_20]
0x1800364c3  dec     eax
0x1800364c5  xor     ecx, ecx
0x1800364c7  cmp     eax, 1
0x1800364ca  setbe   cl
0x1800364cd  mov     rax, [r8]
0x1800364d0  neg     ecx
0x1800364d2  sbb     dx, dx
0x1800364d5  mov     rcx, r8
0x1800364d8  mov     rax, [rax+90h]
0x1800364df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800364e4  mov     ebx, eax
0x1800364e6  test    eax, eax
0x1800364e8  js      short loc_180036508
0x1800364ea  test    esi, esi
0x1800364ec  jnz     short loc_180036519
0x1800364ee  mov     rcx, [rbp+var_10]
0x1800364f2  mov     rax, [rcx]
0x1800364f5  mov     rdx, [rbp+var_18]
0x1800364f9  mov     rax, [rax+40h]
0x1800364fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036502  mov     ebx, eax
0x180036504  test    eax, eax
0x180036506  jns     short loc_180036519
0x180036508  mov     edx, eax
0x18003650a  mov     rcx, r12
0x18003650d  call    cs:__imp_FwReportReturnError
0x180036514  nop     dword ptr [rax+rax+00h]
0x180036519  mov     rcx, [rbp+var_18]
0x18003651d  test    rcx, rcx
0x180036520  jz      short loc_18003652E
0x180036522  mov     rax, [rcx]
0x180036525  mov     rax, [rax+10h]
0x180036529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003652e  lea     rcx, [rbp+var_10]; struct INetFwAuthorizedApplications **
0x180036532  call    ?FwAllowedProgramFree@@YAXPEAPEAUINetFwAuthorizedApplications@@@Z; FwAllowedProgramFree(INetFwAuthorizedApplications * *)
0x180036537  test    ebx, ebx
0x180036539  jns     short loc_18003654E
0x18003653b  mov     edx, ebx
0x18003653d  mov     rcx, r12
0x180036540  call    cs:__imp_FwReportReturnError
0x180036547  nop     dword ptr [rax+rax+00h]
0x18003654c  mov     ebx, eax
0x18003654e  mov     eax, ebx
0x180036550  mov     rcx, [rbp+var_8]
0x180036554  xor     rcx, rsp; StackCookie
0x180036557  call    __security_check_cookie
0x18003655c  add     rsp, 50h
0x180036560  pop     r15
0x180036562  pop     r14
0x180036564  pop     r12
0x180036566  pop     rdi
0x180036567  pop     rsi
0x180036568  pop     rbx
0x180036569  pop     rbp
0x18003656a  retn
```
