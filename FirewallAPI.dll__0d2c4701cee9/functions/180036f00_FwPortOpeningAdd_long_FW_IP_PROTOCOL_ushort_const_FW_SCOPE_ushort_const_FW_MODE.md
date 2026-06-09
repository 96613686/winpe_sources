# FwPortOpeningAdd(long,FW_IP_PROTOCOL_,ushort const *,FW_SCOPE_,ushort const *,FW_MODE_)

- ea: `0x180036f00`
- end: `0x1800371e5`
- name: `?FwPortOpeningAdd@@YAJJW4FW_IP_PROTOCOL_@@PEBGW4FW_SCOPE_@@1W4FW_MODE_@@@Z`
- size: `741`
- prototype: `int __high(int, enum FW_IP_PROTOCOL_, const unsigned __int16 *, enum FW_SCOPE_, const unsigned __int16 *, enum FW_MODE_)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800371ec`

## callees

- `0x180026e1c`
- `0x1800294b0`
- `0x18003336c`
- `0x180036f00`
- `0x1800374a4`
- `0x180037504`
- `0x180037d4c`
- `0x180062010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180037084`
- `OLEAUT32!__imp_SysFreeString` at `0x1800370d1`
- `OLEAUT32!__imp_SysFreeString` at `0x180037084`
- `OLEAUT32!__imp_SysFreeString` at `0x1800370d1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180036ff4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180036ff4`
- `fwbase!FwNtStatusToHResult` at `0x1800370ea`
- `fwbase!FwNtStatusToHResult` at `0x1800370ea`
- `fwbase!FwReportReturnError` at `0x180037180`
- `fwbase!FwReportReturnError` at `0x1800371b7`
- `fwbase!FwReportReturnError` at `0x180037180`
- `fwbase!FwReportReturnError` at `0x1800371b7`

## string_xrefs

- `0x180037179`: `FwPortOpeningAdd`
- `0x1800371b0`: `FwPortOpeningAdd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FwPortOpeningAdd(
        unsigned int a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        OLECHAR *a5,
        int a6)
{
  HRESULT v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // edi
  int v14; // r12d
  LPVOID v15; // r8
  __int64 (__fastcall *v16)(LPVOID, _QWORD); // rbx
  _QWORD *v17; // rax
  __int64 v18; // rdx
  __int64 (__fastcall *v19)(LPVOID, _QWORD); // rbx
  _QWORD *v20; // rax
  BSTR v22; // [rsp+30h] [rbp-38h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-30h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-28h] BYREF
  struct INetFwOpenPorts *v25; // [rsp+48h] [rbp-20h] BYREF

  v22 = a5;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_b0516bc2b3bb3db5719010192741acba_Traceguids);
  ppv = 0;
  v25 = 0;
  v10 = FwServicePortBuiltIn(a1, a2, &ppv);
  v12 = v10;
  if ( v10 < 0 )
    goto LABEL_31;
  v13 = 1;
  v14 = 0;
  v15 = ppv;
  if ( !ppv )
  {
    v10 = FwPortOpeningInit(&v25);
    v12 = v10;
    if ( v10 < 0 )
      goto LABEL_31;
    v10 = ((__int64 (__fastcall *)(struct INetFwOpenPorts *, _QWORD, _QWORD, LPVOID *))v25->lpVtbl->Item)(
            v25,
            a1,
            a2,
            &ppv);
    v12 = v10;
    if ( v10 == -2147024894 )
    {
      v10 = CoCreateInstance(
              &GUID_0ca545c6_37ad_4a6c_bf92_9f7610067ef5,
              0,
              1u,
              &GUID_e0483ba0_47ff_4d9c_a6d6_7741d0b195f7,
              &ppv);
      v12 = v10;
      if ( v10 < 0 )
        goto LABEL_31;
      v10 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 96LL))(ppv, a2);
      v12 = v10;
      if ( v10 < 0 )
        goto LABEL_31;
      v10 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 112LL))(ppv, a1);
      v12 = v10;
      if ( v10 < 0 )
        goto LABEL_31;
    }
    else
    {
      if ( v10 < 0 )
        goto LABEL_31;
      v14 = 1;
    }
    v13 = 0;
    if ( a3 )
    {
      v16 = *(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 64LL);
      v17 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, a3);
      v12 = v16(ppv, *v17);
      SysFreeString(bstrString);
      if ( v12 < 0 )
        goto LABEL_16;
    }
    v15 = ppv;
  }
  if ( a4 == 2 )
  {
    v19 = *(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v15 + 144LL);
    v20 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v22, v22);
    v12 = v19(ppv, *v20);
    SysFreeString(v22);
    if ( v12 == -2147024883 || v12 == (unsigned int)FwNtStatusToHResult(3221225485LL) )
    {
      v12 = -2147023189;
LABEL_16:
      v18 = (unsigned int)v12;
LABEL_32:
      FwReportReturnError("FwPortOpeningAdd", v18);
      goto LABEL_33;
    }
    if ( v12 < 0 )
      goto LABEL_16;
    goto LABEL_26;
  }
  if ( a4 != 3 )
  {
    v10 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v15 + 128LL))(v15, a4);
    v12 = v10;
    if ( v10 >= 0 )
    {
LABEL_26:
      v15 = ppv;
      goto LABEL_27;
    }
LABEL_31:
    v18 = (unsigned int)v10;
    goto LABEL_32;
  }
LABEL_27:
  LOWORD(v11) = -((unsigned int)(a6 - 1) <= 1);
  v10 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v15 + 160LL))(v15, v11);
  v12 = v10;
  if ( v10 < 0 )
    goto LABEL_31;
  if ( !v13 && !v14 )
  {
    v10 = ((__int64 (__fastcall *)(struct INetFwOpenPorts *, LPVOID))v25->lpVtbl->Add)(v25, ppv);
    v12 = v10;
    if ( v10 < 0 )
      goto LABEL_31;
  }
LABEL_33:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  FwPortOpeningFree(&v25);
  if ( v12 < 0 )
    return (unsigned int)FwReportReturnError("FwPortOpeningAdd", (unsigned int)v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180036f00  push    rbp
0x180036f02  push    rbx
0x180036f03  push    rsi
0x180036f04  push    rdi
0x180036f05  push    r12
0x180036f07  push    r13
0x180036f09  push    r14
0x180036f0b  push    r15
0x180036f0d  mov     rbp, rsp
0x180036f10  sub     rsp, 68h
0x180036f14  mov     rax, cs:__security_cookie
0x180036f1b  xor     rax, rsp
0x180036f1e  mov     [rbp+var_18], rax
0x180036f22  mov     esi, r9d
0x180036f25  mov     r13, r8
0x180036f28  mov     r14d, edx
0x180036f2b  mov     r15d, ecx
0x180036f2e  mov     rax, [rbp+arg_20]
0x180036f32  mov     [rbp+var_38], rax
0x180036f36  lea     rax, WPP_GLOBAL_Control
0x180036f3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180036f44  cmp     rcx, rax
0x180036f47  jz      short loc_180036F64
0x180036f49  test    byte ptr [rcx+1Ch], 8
0x180036f4d  jz      short loc_180036F64
0x180036f4f  mov     edx, 2Ch ; ','
0x180036f54  lea     r8, WPP_b0516bc2b3bb3db5719010192741acba_Traceguids
0x180036f5b  mov     rcx, [rcx+10h]
0x180036f5f  call    WPP_SF_
0x180036f64  mov     [rbp+var_28], 0
0x180036f6c  mov     [rbp+var_20], 0
0x180036f74  lea     r8, [rbp+var_28]
0x180036f78  mov     edx, r14d
0x180036f7b  mov     ecx, r15d
0x180036f7e  call    ?FwServicePortBuiltIn@@YAJJW4FW_IP_PROTOCOL_@@PEAPEAUINetFwOpenPort@@@Z; FwServicePortBuiltIn(long,FW_IP_PROTOCOL_,INetFwOpenPort * *)
0x180036f83  mov     ebx, eax
0x180036f85  test    eax, eax
0x180036f87  js      loc_180037177
0x180036f8d  mov     edi, 1
0x180036f92  xor     r12d, r12d
0x180036f95  mov     r8, [rbp+var_28]
0x180036f99  test    r8, r8
0x180036f9c  jnz     loc_18003709F
0x180036fa2  lea     rcx, [rbp+var_20]; struct INetFwOpenPorts **
0x180036fa6  call    ?FwPortOpeningInit@@YAJPEAPEAUINetFwOpenPorts@@@Z; FwPortOpeningInit(INetFwOpenPorts * *)
0x180036fab  mov     ebx, eax
0x180036fad  test    eax, eax
0x180036faf  js      loc_180037177
0x180036fb5  mov     rcx, [rbp+var_20]
0x180036fb9  mov     rax, [rcx]
0x180036fbc  lea     r9, [rbp+var_28]
0x180036fc0  mov     r8d, r14d
0x180036fc3  mov     edx, r15d
0x180036fc6  mov     rax, [rax+50h]
0x180036fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036fcf  mov     ebx, eax
0x180036fd1  cmp     eax, 80070002h
0x180036fd6  jnz     short loc_180037045
0x180036fd8  lea     rax, [rbp+var_28]
0x180036fdc  mov     [rsp+68h+ppv], rax; ppv
0x180036fe1  lea     r9, _GUID_e0483ba0_47ff_4d9c_a6d6_7741d0b195f7; riid
0x180036fe8  xor     edx, edx; pUnkOuter
0x180036fea  mov     r8d, edi; dwClsContext
0x180036fed  lea     rcx, _GUID_0ca545c6_37ad_4a6c_bf92_9f7610067ef5; rclsid
0x180036ff4  call    cs:__imp_CoCreateInstance
0x180036ffb  nop     dword ptr [rax+rax+00h]
0x180037000  mov     ebx, eax
0x180037002  test    eax, eax
0x180037004  js      loc_180037177
0x18003700a  mov     rcx, [rbp+var_28]
0x18003700e  mov     rax, [rcx]
0x180037011  mov     edx, r14d
0x180037014  mov     rax, [rax+60h]
0x180037018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003701d  mov     ebx, eax
0x18003701f  test    eax, eax
0x180037021  js      loc_180037177
0x180037027  mov     rcx, [rbp+var_28]
0x18003702b  mov     rax, [rcx]
0x18003702e  mov     edx, r15d
0x180037031  mov     rax, [rax+70h]
0x180037035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003703a  mov     ebx, eax
0x18003703c  test    eax, eax
0x18003703e  jns     short loc_180037050
0x180037040  jmp     loc_180037177
0x180037045  test    eax, eax
0x180037047  js      loc_180037177
0x18003704d  mov     r12d, edi
0x180037050  xor     edi, edi
0x180037052  test    r13, r13
0x180037055  jz      short loc_18003709B
0x180037057  mov     rax, [rbp+var_28]
0x18003705b  mov     rcx, [rax]
0x18003705e  mov     rbx, [rcx+40h]
0x180037062  mov     rdx, r13; unsigned __int16 *
0x180037065  lea     rcx, [rbp+bstrString]; this
0x180037069  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18003706e  nop
0x18003706f  mov     rdx, [rax]
0x180037072  mov     rcx, [rbp+var_28]
0x180037076  mov     rax, rbx
0x180037079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003707e  mov     ebx, eax
0x180037080  mov     rcx, [rbp+bstrString]; bstrString
0x180037084  call    cs:__imp_SysFreeString
0x18003708b  nop     dword ptr [rax+rax+00h]
0x180037090  test    ebx, ebx
0x180037092  jns     short loc_18003709B
0x180037094  mov     edx, ebx
0x180037096  jmp     loc_180037179
0x18003709b  mov     r8, [rbp+var_28]
0x18003709f  cmp     esi, 2
0x1800370a2  jnz     short loc_180037107
0x1800370a4  mov     rax, [r8]
0x1800370a7  mov     rbx, [rax+90h]
0x1800370ae  mov     rdx, [rbp+var_38]; unsigned __int16 *
0x1800370b2  lea     rcx, [rbp+var_38]; this
0x1800370b6  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800370bb  nop
0x1800370bc  mov     rdx, [rax]
0x1800370bf  mov     rcx, [rbp+var_28]
0x1800370c3  mov     rax, rbx
0x1800370c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800370cb  mov     ebx, eax
0x1800370cd  mov     rcx, [rbp+var_38]; bstrString
0x1800370d1  call    cs:__imp_SysFreeString
0x1800370d8  nop     dword ptr [rax+rax+00h]
0x1800370dd  cmp     ebx, 8007000Dh
0x1800370e3  jz      short loc_180037100
0x1800370e5  mov     ecx, 0C000000Dh
0x1800370ea  call    cs:__imp_FwNtStatusToHResult
0x1800370f1  nop     dword ptr [rax+rax+00h]
0x1800370f6  cmp     ebx, eax
0x1800370f8  jz      short loc_180037100
0x1800370fa  test    ebx, ebx
0x1800370fc  jns     short loc_180037126
0x1800370fe  jmp     short loc_180037094
0x180037100  mov     ebx, 800706ABh
0x180037105  jmp     short loc_180037094
0x180037107  cmp     esi, 3
0x18003710a  jz      short loc_18003712A
0x18003710c  mov     rax, [r8]
0x18003710f  mov     edx, esi
0x180037111  mov     rcx, r8
0x180037114  mov     rax, [rax+80h]
0x18003711b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037120  mov     ebx, eax
0x180037122  test    eax, eax
0x180037124  js      short loc_180037177
0x180037126  mov     r8, [rbp+var_28]
0x18003712a  mov     eax, [rbp+arg_28]
0x18003712d  dec     eax
0x18003712f  xor     ecx, ecx
0x180037131  cmp     eax, 1
0x180037134  setbe   cl
0x180037137  mov     rax, [r8]
0x18003713a  neg     ecx
0x18003713c  sbb     dx, dx
0x18003713f  mov     rcx, r8
0x180037142  mov     rax, [rax+0A0h]
0x180037149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003714e  mov     ebx, eax
0x180037150  test    eax, eax
0x180037152  js      short loc_180037177
0x180037154  test    edi, edi
0x180037156  jnz     short loc_18003718C
0x180037158  test    r12d, r12d
0x18003715b  jnz     short loc_18003718C
0x18003715d  mov     rcx, [rbp+var_20]
0x180037161  mov     rax, [rcx]
0x180037164  mov     rdx, [rbp+var_28]
0x180037168  mov     rax, [rax+40h]
0x18003716c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037171  mov     ebx, eax
0x180037173  test    eax, eax
0x180037175  jns     short loc_18003718C
0x180037177  mov     edx, eax
0x180037179  lea     rcx, aFwportopeninga_0; "FwPortOpeningAdd"
0x180037180  call    cs:__imp_FwReportReturnError
0x180037187  nop     dword ptr [rax+rax+00h]
0x18003718c  mov     rcx, [rbp+var_28]
0x180037190  test    rcx, rcx
0x180037193  jz      short loc_1800371A1
0x180037195  mov     rax, [rcx]
0x180037198  mov     rax, [rax+10h]
0x18003719c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800371a1  lea     rcx, [rbp+var_20]; struct INetFwOpenPorts **
0x1800371a5  call    ?FwPortOpeningFree@@YAXPEAPEAUINetFwOpenPorts@@@Z; FwPortOpeningFree(INetFwOpenPorts * *)
0x1800371aa  test    ebx, ebx
0x1800371ac  jns     short loc_1800371C5
0x1800371ae  mov     edx, ebx
0x1800371b0  lea     rcx, aFwportopeninga_0; "FwPortOpeningAdd"
0x1800371b7  call    cs:__imp_FwReportReturnError
0x1800371be  nop     dword ptr [rax+rax+00h]
0x1800371c3  mov     ebx, eax
0x1800371c5  mov     eax, ebx
0x1800371c7  mov     rcx, [rbp+var_18]
0x1800371cb  xor     rcx, rsp; StackCookie
0x1800371ce  call    __security_check_cookie
0x1800371d3  add     rsp, 68h
0x1800371d7  pop     r15
0x1800371d9  pop     r14
0x1800371db  pop     r13
0x1800371dd  pop     r12
0x1800371df  pop     rdi
0x1800371e0  pop     rsi
0x1800371e1  pop     rbx
0x1800371e2  pop     rbp
0x1800371e3  retn
```
