# FwPortOpeningAdd(long,FW_IP_PROTOCOL_,ushort const *,FW_SCOPE_,ushort const *,FW_MODE_)

- ea: `0x180034850`
- end: `0x180034b10`
- name: `?FwPortOpeningAdd@@YAJJW4FW_IP_PROTOCOL_@@PEBGW4FW_SCOPE_@@1W4FW_MODE_@@@Z`
- size: `704`
- prototype: `int __high(int, enum FW_IP_PROTOCOL_, const unsigned __int16 *, enum FW_SCOPE_, const unsigned __int16 *, enum FW_MODE_)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180034b18`

## callees

- `0x18002527c`
- `0x1800277b0`
- `0x18003104c`
- `0x180034850`
- `0x180034da0`
- `0x180034e00`
- `0x1800355cc`
- `0x18005e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800349ce`
- `OLEAUT32!__imp_SysFreeString` at `0x180034a15`
- `OLEAUT32!__imp_SysFreeString` at `0x1800349ce`
- `OLEAUT32!__imp_SysFreeString` at `0x180034a15`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180034944`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180034944`
- `fwbase!FwNtStatusToHResult` at `0x180034a28`
- `fwbase!FwNtStatusToHResult` at `0x180034a28`
- `fwbase!FwReportReturnError` at `0x180034ab8`
- `fwbase!FwReportReturnError` at `0x180034ae9`
- `fwbase!FwReportReturnError` at `0x180034ab8`
- `fwbase!FwReportReturnError` at `0x180034ae9`

## string_xrefs

- `0x180034ab1`: `FwPortOpeningAdd`
- `0x180034ae2`: `FwPortOpeningAdd`

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
0x180034850  push    rbp
0x180034852  push    rbx
0x180034853  push    rsi
0x180034854  push    rdi
0x180034855  push    r12
0x180034857  push    r13
0x180034859  push    r14
0x18003485b  push    r15
0x18003485d  mov     rbp, rsp
0x180034860  sub     rsp, 68h
0x180034864  mov     rax, cs:__security_cookie
0x18003486b  xor     rax, rsp
0x18003486e  mov     [rbp+var_18], rax
0x180034872  mov     esi, r9d
0x180034875  mov     r13, r8
0x180034878  mov     r14d, edx
0x18003487b  mov     r15d, ecx
0x18003487e  mov     rax, [rbp+arg_20]
0x180034882  mov     [rbp+var_38], rax
0x180034886  lea     rax, WPP_GLOBAL_Control
0x18003488d  mov     rcx, cs:WPP_GLOBAL_Control
0x180034894  cmp     rcx, rax
0x180034897  jz      short loc_1800348B4
0x180034899  test    byte ptr [rcx+1Ch], 8
0x18003489d  jz      short loc_1800348B4
0x18003489f  mov     edx, 2Ch ; ','
0x1800348a4  lea     r8, WPP_b0516bc2b3bb3db5719010192741acba_Traceguids
0x1800348ab  mov     rcx, [rcx+10h]
0x1800348af  call    WPP_SF_
0x1800348b4  mov     [rbp+var_28], 0
0x1800348bc  mov     [rbp+var_20], 0
0x1800348c4  lea     r8, [rbp+var_28]
0x1800348c8  mov     edx, r14d
0x1800348cb  mov     ecx, r15d
0x1800348ce  call    ?FwServicePortBuiltIn@@YAJJW4FW_IP_PROTOCOL_@@PEAPEAUINetFwOpenPort@@@Z; FwServicePortBuiltIn(long,FW_IP_PROTOCOL_,INetFwOpenPort * *)
0x1800348d3  mov     ebx, eax
0x1800348d5  test    eax, eax
0x1800348d7  js      loc_180034AAF
0x1800348dd  mov     edi, 1
0x1800348e2  xor     r12d, r12d
0x1800348e5  mov     r8, [rbp+var_28]
0x1800348e9  test    r8, r8
0x1800348ec  jnz     loc_1800349E3
0x1800348f2  lea     rcx, [rbp+var_20]; struct INetFwOpenPorts **
0x1800348f6  call    ?FwPortOpeningInit@@YAJPEAPEAUINetFwOpenPorts@@@Z; FwPortOpeningInit(INetFwOpenPorts * *)
0x1800348fb  mov     ebx, eax
0x1800348fd  test    eax, eax
0x1800348ff  js      loc_180034AAF
0x180034905  mov     rcx, [rbp+var_20]
0x180034909  mov     rax, [rcx]
0x18003490c  lea     r9, [rbp+var_28]
0x180034910  mov     r8d, r14d
0x180034913  mov     edx, r15d
0x180034916  mov     rax, [rax+50h]
0x18003491a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003491f  mov     ebx, eax
0x180034921  cmp     eax, 80070002h
0x180034926  jnz     short loc_18003498F
0x180034928  lea     rax, [rbp+var_28]
0x18003492c  mov     [rsp+68h+ppv], rax; ppv
0x180034931  lea     r9, _GUID_e0483ba0_47ff_4d9c_a6d6_7741d0b195f7; riid
0x180034938  xor     edx, edx; pUnkOuter
0x18003493a  mov     r8d, edi; dwClsContext
0x18003493d  lea     rcx, _GUID_0ca545c6_37ad_4a6c_bf92_9f7610067ef5; rclsid
0x180034944  call    cs:__imp_CoCreateInstance
0x18003494a  mov     ebx, eax
0x18003494c  test    eax, eax
0x18003494e  js      loc_180034AAF
0x180034954  mov     rcx, [rbp+var_28]
0x180034958  mov     rax, [rcx]
0x18003495b  mov     edx, r14d
0x18003495e  mov     rax, [rax+60h]
0x180034962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034967  mov     ebx, eax
0x180034969  test    eax, eax
0x18003496b  js      loc_180034AAF
0x180034971  mov     rcx, [rbp+var_28]
0x180034975  mov     rax, [rcx]
0x180034978  mov     edx, r15d
0x18003497b  mov     rax, [rax+70h]
0x18003497f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034984  mov     ebx, eax
0x180034986  test    eax, eax
0x180034988  jns     short loc_18003499A
0x18003498a  jmp     loc_180034AAF
0x18003498f  test    eax, eax
0x180034991  js      loc_180034AAF
0x180034997  mov     r12d, edi
0x18003499a  xor     edi, edi
0x18003499c  test    r13, r13
0x18003499f  jz      short loc_1800349DF
0x1800349a1  mov     rax, [rbp+var_28]
0x1800349a5  mov     rcx, [rax]
0x1800349a8  mov     rbx, [rcx+40h]
0x1800349ac  mov     rdx, r13; unsigned __int16 *
0x1800349af  lea     rcx, [rbp+bstrString]; this
0x1800349b3  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800349b8  nop
0x1800349b9  mov     rdx, [rax]
0x1800349bc  mov     rcx, [rbp+var_28]
0x1800349c0  mov     rax, rbx
0x1800349c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800349c8  mov     ebx, eax
0x1800349ca  mov     rcx, [rbp+bstrString]; bstrString
0x1800349ce  call    cs:__imp_SysFreeString
0x1800349d4  test    ebx, ebx
0x1800349d6  jns     short loc_1800349DF
0x1800349d8  mov     edx, ebx
0x1800349da  jmp     loc_180034AB1
0x1800349df  mov     r8, [rbp+var_28]
0x1800349e3  cmp     esi, 2
0x1800349e6  jnz     short loc_180034A3F
0x1800349e8  mov     rax, [r8]
0x1800349eb  mov     rbx, [rax+90h]
0x1800349f2  mov     rdx, [rbp+var_38]; unsigned __int16 *
0x1800349f6  lea     rcx, [rbp+var_38]; this
0x1800349fa  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800349ff  nop
0x180034a00  mov     rdx, [rax]
0x180034a03  mov     rcx, [rbp+var_28]
0x180034a07  mov     rax, rbx
0x180034a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034a0f  mov     ebx, eax
0x180034a11  mov     rcx, [rbp+var_38]; bstrString
0x180034a15  call    cs:__imp_SysFreeString
0x180034a1b  cmp     ebx, 8007000Dh
0x180034a21  jz      short loc_180034A38
0x180034a23  mov     ecx, 0C000000Dh
0x180034a28  call    cs:__imp_FwNtStatusToHResult
0x180034a2e  cmp     ebx, eax
0x180034a30  jz      short loc_180034A38
0x180034a32  test    ebx, ebx
0x180034a34  jns     short loc_180034A5E
0x180034a36  jmp     short loc_1800349D8
0x180034a38  mov     ebx, 800706ABh
0x180034a3d  jmp     short loc_1800349D8
0x180034a3f  cmp     esi, 3
0x180034a42  jz      short loc_180034A62
0x180034a44  mov     rax, [r8]
0x180034a47  mov     edx, esi
0x180034a49  mov     rcx, r8
0x180034a4c  mov     rax, [rax+80h]
0x180034a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034a58  mov     ebx, eax
0x180034a5a  test    eax, eax
0x180034a5c  js      short loc_180034AAF
0x180034a5e  mov     r8, [rbp+var_28]
0x180034a62  mov     eax, [rbp+arg_28]
0x180034a65  dec     eax
0x180034a67  xor     ecx, ecx
0x180034a69  cmp     eax, 1
0x180034a6c  setbe   cl
0x180034a6f  mov     rax, [r8]
0x180034a72  neg     ecx
0x180034a74  sbb     dx, dx
0x180034a77  mov     rcx, r8
0x180034a7a  mov     rax, [rax+0A0h]
0x180034a81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034a86  mov     ebx, eax
0x180034a88  test    eax, eax
0x180034a8a  js      short loc_180034AAF
0x180034a8c  test    edi, edi
0x180034a8e  jnz     short loc_180034ABE
0x180034a90  test    r12d, r12d
0x180034a93  jnz     short loc_180034ABE
0x180034a95  mov     rcx, [rbp+var_20]
0x180034a99  mov     rax, [rcx]
0x180034a9c  mov     rdx, [rbp+var_28]
0x180034aa0  mov     rax, [rax+40h]
0x180034aa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034aa9  mov     ebx, eax
0x180034aab  test    eax, eax
0x180034aad  jns     short loc_180034ABE
0x180034aaf  mov     edx, eax
0x180034ab1  lea     rcx, aFwportopeninga_0; "FwPortOpeningAdd"
0x180034ab8  call    cs:__imp_FwReportReturnError
0x180034abe  mov     rcx, [rbp+var_28]
0x180034ac2  test    rcx, rcx
0x180034ac5  jz      short loc_180034AD3
0x180034ac7  mov     rax, [rcx]
0x180034aca  mov     rax, [rax+10h]
0x180034ace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034ad3  lea     rcx, [rbp+var_20]; struct INetFwOpenPorts **
0x180034ad7  call    ?FwPortOpeningFree@@YAXPEAPEAUINetFwOpenPorts@@@Z; FwPortOpeningFree(INetFwOpenPorts * *)
0x180034adc  test    ebx, ebx
0x180034ade  jns     short loc_180034AF1
0x180034ae0  mov     edx, ebx
0x180034ae2  lea     rcx, aFwportopeninga_0; "FwPortOpeningAdd"
0x180034ae9  call    cs:__imp_FwReportReturnError
0x180034aef  mov     ebx, eax
0x180034af1  mov     eax, ebx
0x180034af3  mov     rcx, [rbp+var_18]
0x180034af7  xor     rcx, rsp; StackCookie
0x180034afa  call    __security_check_cookie
0x180034aff  add     rsp, 68h
0x180034b03  pop     r15
0x180034b05  pop     r14
0x180034b07  pop     r13
0x180034b09  pop     r12
0x180034b0b  pop     rdi
0x180034b0c  pop     rsi
0x180034b0d  pop     rbx
0x180034b0e  pop     rbp
0x180034b0f  retn
```
