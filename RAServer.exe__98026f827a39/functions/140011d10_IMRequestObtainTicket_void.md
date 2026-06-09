# IMRequestObtainTicket(void *)

- ea: `0x140011d10`
- end: `0x140011fab`
- name: `?IMRequestObtainTicket@@YAKPEAX@Z`
- size: `667`
- prototype: `__int64 __fastcall(char *lpThreadParameter, const struct _EVENT_DESCRIPTOR *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400035c8`
- `0x14000e664`
- `0x140011d10`
- `0x140015240`
- `0x1400154b0`
- `0x140017010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140011f44`
- `OLEAUT32!__imp_SysFreeString` at `0x140011f86`
- `OLEAUT32!__imp_SysFreeString` at `0x140011f91`
- `OLEAUT32!__imp_SysFreeString` at `0x140011f44`
- `OLEAUT32!__imp_SysFreeString` at `0x140011f86`
- `OLEAUT32!__imp_SysFreeString` at `0x140011f91`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140011d80`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140011d80`

## string_xrefs

- `0x140011f70`: `base\diagnosis\ra\dcom\src\raimrequest.cpp`
- `0x140011d57`: `base\diagnosis\ra\dcom\src\raimrequestevnt.cpp`
- `0x140011da7`: `base\diagnosis\ra\dcom\src\raimrequestevnt.cpp`
- `0x140011ee7`: `base\diagnosis\ra\dcom\src\raimrequestevnt.cpp`

## pseudocode

```c
__int64 __fastcall IMRequestObtainTicket(char *lpThreadParameter, const struct _EVENT_DESCRIPTOR *a2)
{
  const struct _EVENT_DESCRIPTOR *v3; // rdx
  CEventLogger *v4; // rcx
  HRESULT v5; // edi
  unsigned __int16 *v6; // r8
  const struct _EVENT_DESCRIPTOR *v7; // rdx
  CEventLogger *v8; // rcx
  const struct _EVENT_DESCRIPTOR *v9; // rdx
  CEventLogger *v10; // rcx
  _QWORD *v11; // rbx
  signed int v12; // eax
  const struct _EVENT_DESCRIPTOR *v13; // rdx
  CEventLogger *v14; // rcx
  unsigned int v15; // r9d
  __int64 v16; // rax
  __int64 v17; // rdi
  void (__fastcall *v18)(__int64, _QWORD, _QWORD); // rbx
  ATL::CComBSTR *v19; // rax
  BSTR bstrString[2]; // [rsp+30h] [rbp-10h] BYREF
  int v22; // [rsp+60h] [rbp+20h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+28h] BYREF
  BSTR v24; // [rsp+70h] [rbp+30h] BYREF
  BSTR v25; // [rsp+78h] [rbp+38h] BYREF

  v22 = 0;
  ppv = 0;
  v25 = 0;
  v24 = 0;
  if ( !lpThreadParameter )
  {
    CEventLogger::LogError(
      0,
      a2,
      L"base\\diagnosis\\ra\\dcom\\src\\raimrequestevnt.cpp",
      0x44Eu,
      L"IMRequestObtainTicket",
      0x80004003);
    goto LABEL_28;
  }
  v5 = CoCreateInstance(&CLSID_RemoteAssistance, 0, 4u, &GUID_59308e66_7cde_478a_8eba_4d73fdce3545, &ppv);
  if ( v5 < 0 )
  {
    CEventLogger::LogEvent(v4, v3, v6);
    CEventLogger::LogError(
      v8,
      v7,
      L"base\\diagnosis\\ra\\dcom\\src\\raimrequestevnt.cpp",
      0x45Bu,
      L"IMRequestObtainTicket",
      v5);
    v11 = lpThreadParameter + 8;
    goto LABEL_24;
  }
  v11 = lpThreadParameter + 8;
  if ( !*v11 )
  {
    CEventLogger::LogError(
      0,
      v3,
      L"base\\diagnosis\\ra\\dcom\\src\\raimrequestevnt.cpp",
      0x465u,
      L"IMRequestObtainTicket",
      0x8000FFFF);
    goto LABEL_24;
  }
  v12 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(*(_QWORD *)*v11 + 32LL))(*v11, &v24);
  if ( v12 >= 0 )
  {
    v12 = (*(__int64 (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)ppv + 128LL))(ppv, v24);
    if ( v12 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64))(*(_QWORD *)ppv + 56LL))(ppv, 0, 1);
      if ( v12 >= 0 )
      {
        v12 = (*(__int64 (__fastcall **)(LPVOID, int *, _QWORD))(*(_QWORD *)ppv + 88LL))(ppv, &v22, 0);
        if ( v12 >= 0 )
        {
          if ( !v22 )
          {
            CEventLogger::LogError(
              v14,
              v13,
              L"base\\diagnosis\\ra\\dcom\\src\\raimrequestevnt.cpp",
              0x499u,
              L"IMRequestObtainTicket",
              0x8000FFFF);
            goto LABEL_24;
          }
          v12 = (*(__int64 (__fastcall **)(LPVOID, BSTR *))(*(_QWORD *)ppv + 64LL))(ppv, &v25);
          if ( v12 >= 0 )
          {
            if ( !*v11 )
            {
              CEventLogger::LogError(
                0,
                v13,
                L"base\\diagnosis\\ra\\dcom\\src\\raimrequestevnt.cpp",
                0x4ADu,
                L"IMRequestObtainTicket",
                0x8000FFFF);
              goto LABEL_24;
            }
            v12 = (*(__int64 (__fastcall **)(_QWORD, BSTR))(*(_QWORD *)*v11 + 56LL))(*v11, v25);
            if ( v12 >= 0 )
              goto LABEL_28;
            v15 = 1203;
          }
          else
          {
            v15 = 1187;
          }
        }
        else
        {
          v15 = 1165;
        }
      }
      else
      {
        v15 = 1155;
      }
    }
    else
    {
      v15 = 1136;
    }
  }
  else
  {
    v15 = 1131;
  }
  CEventLogger::LogError(
    v14,
    v13,
    L"base\\diagnosis\\ra\\dcom\\src\\raimrequestevnt.cpp",
    v15,
    L"IMRequestObtainTicket",
    v12);
LABEL_24:
  v16 = *v11;
  if ( *v11 )
  {
    v17 = *(_QWORD *)(v16 + 24);
    if ( v17 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v17 + 8LL))(*(_QWORD *)(v16 + 24));
      v18 = *(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v17 + 56LL);
      v19 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, L"Termination");
      v18(v17, 0, *(_QWORD *)v19);
      SysFreeString(bstrString[0]);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    else
    {
      CEventLogger::LogError(
        v10,
        v9,
        L"base\\diagnosis\\ra\\dcom\\src\\raimrequest.cpp",
        0x1B6u,
        L"CIMRequestRA::get_RendezvousSession",
        0);
    }
  }
LABEL_28:
  SysFreeString(v24);
  SysFreeString(v25);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  return 0;
}

```

## disassembly

```asm
0x140011d10  push    rbp
0x140011d12  push    rbx
0x140011d13  push    rdi
0x140011d14  mov     rbp, rsp
0x140011d17  sub     rsp, 40h
0x140011d1b  mov     rbx, rcx
0x140011d1e  mov     [rbp+arg_0], 0
0x140011d25  mov     [rbp+arg_8], 0
0x140011d2d  mov     [rbp+arg_18], 0
0x140011d35  mov     [rbp+arg_10], 0
0x140011d3d  test    rcx, rcx
0x140011d40  jnz     short loc_140011D63
0x140011d42  mov     [rsp+40h+var_18], 80004003h
0x140011d4a  lea     rax, aImrequestobtai; "IMRequestObtainTicket"
0x140011d51  mov     r9d, 44Eh
0x140011d57  lea     r8, aBaseDiagnosisR_0; "base\\diagnosis\\ra\\dcom\\src\\raimreq"...
0x140011d5e  jmp     loc_140011F77
0x140011d63  lea     rax, [rbp+arg_8]
0x140011d67  mov     [rsp+40h+ppv], rax; ppv
0x140011d6c  lea     r9, _GUID_59308e66_7cde_478a_8eba_4d73fdce3545; riid
0x140011d73  xor     edx, edx; pUnkOuter
0x140011d75  lea     r8d, [rdx+4]; dwClsContext
0x140011d79  lea     rcx, CLSID_RemoteAssistance; rclsid
0x140011d80  call    cs:__imp_CoCreateInstance
0x140011d86  mov     edi, eax
0x140011d88  test    eax, eax
0x140011d8a  jns     short loc_140011DBC
0x140011d8c  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,ushort *)
0x140011d91  mov     [rsp+40h+var_18], edi; unsigned int
0x140011d95  lea     rax, aImrequestobtai; "IMRequestObtainTicket"
0x140011d9c  mov     [rsp+40h+ppv], rax; unsigned __int16 *
0x140011da1  mov     r9d, 45Bh; unsigned int
0x140011da7  lea     r8, aBaseDiagnosisR_0; "base\\diagnosis\\ra\\dcom\\src\\raimreq"...
0x140011dae  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140011db3  add     rbx, 8
0x140011db7  jmp     loc_140011EF3
0x140011dbc  add     rbx, 8
0x140011dc0  mov     rcx, [rbx]
0x140011dc3  test    rcx, rcx
0x140011dc6  jnz     short loc_140011DDB
0x140011dc8  mov     [rsp+40h+var_18], 8000FFFFh
0x140011dd0  mov     r9d, 465h
0x140011dd6  jmp     loc_140011EDB
0x140011ddb  mov     rax, [rcx]
0x140011dde  lea     rdx, [rbp+arg_10]
0x140011de2  mov     rax, [rax+20h]
0x140011de6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011deb  test    eax, eax
0x140011ded  jns     short loc_140011DFA
0x140011def  mov     r9d, 46Bh
0x140011df5  jmp     loc_140011ED7
0x140011dfa  mov     rcx, [rbp+arg_8]
0x140011dfe  mov     rax, [rcx]
0x140011e01  mov     rdx, [rbp+arg_10]
0x140011e05  mov     rax, [rax+80h]
0x140011e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011e11  test    eax, eax
0x140011e13  jns     short loc_140011E20
0x140011e15  mov     r9d, 470h
0x140011e1b  jmp     loc_140011ED7
0x140011e20  mov     rcx, [rbp+arg_8]
0x140011e24  mov     rax, [rcx]
0x140011e27  xor     r9d, r9d
0x140011e2a  xor     edx, edx
0x140011e2c  lea     r8d, [r9+1]
0x140011e30  mov     rax, [rax+38h]
0x140011e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011e39  test    eax, eax
0x140011e3b  jns     short loc_140011E48
0x140011e3d  mov     r9d, 483h
0x140011e43  jmp     loc_140011ED7
0x140011e48  mov     rcx, [rbp+arg_8]
0x140011e4c  mov     rax, [rcx]
0x140011e4f  xor     r8d, r8d
0x140011e52  lea     rdx, [rbp+arg_0]
0x140011e56  mov     rax, [rax+58h]
0x140011e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011e5f  test    eax, eax
0x140011e61  jns     short loc_140011E6B
0x140011e63  mov     r9d, 48Dh
0x140011e69  jmp     short loc_140011ED7
0x140011e6b  cmp     [rbp+arg_0], 0
0x140011e6f  jnz     short loc_140011E81
0x140011e71  mov     [rsp+40h+var_18], 8000FFFFh
0x140011e79  mov     r9d, 499h
0x140011e7f  jmp     short loc_140011EDB
0x140011e81  mov     rcx, [rbp+arg_8]
0x140011e85  mov     rax, [rcx]
0x140011e88  lea     rdx, [rbp+arg_18]
0x140011e8c  mov     rax, [rax+40h]
0x140011e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011e95  test    eax, eax
0x140011e97  jns     short loc_140011EA1
0x140011e99  mov     r9d, 4A3h
0x140011e9f  jmp     short loc_140011ED7
0x140011ea1  mov     rcx, [rbx]
0x140011ea4  test    rcx, rcx
0x140011ea7  jnz     short loc_140011EB9
0x140011ea9  mov     [rsp+40h+var_18], 8000FFFFh
0x140011eb1  mov     r9d, 4ADh
0x140011eb7  jmp     short loc_140011EDB
0x140011eb9  mov     rax, [rcx]
0x140011ebc  mov     rdx, [rbp+arg_18]
0x140011ec0  mov     rax, [rax+38h]
0x140011ec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011ec9  test    eax, eax
0x140011ecb  jns     loc_140011F82
0x140011ed1  mov     r9d, 4B3h; unsigned int
0x140011ed7  mov     [rsp+40h+var_18], eax; unsigned int
0x140011edb  lea     rax, aImrequestobtai; "IMRequestObtainTicket"
0x140011ee2  mov     [rsp+40h+ppv], rax; unsigned __int16 *
0x140011ee7  lea     r8, aBaseDiagnosisR_0; "base\\diagnosis\\ra\\dcom\\src\\raimreq"...
0x140011eee  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140011ef3  mov     rax, [rbx]
0x140011ef6  test    rax, rax
0x140011ef9  jz      loc_140011F82
0x140011eff  mov     rdi, [rax+18h]
0x140011f03  test    rdi, rdi
0x140011f06  jz      short loc_140011F5B
0x140011f08  mov     rax, [rdi]
0x140011f0b  mov     rcx, rdi
0x140011f0e  mov     rax, [rax+8]
0x140011f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011f17  mov     rax, [rdi]
0x140011f1a  mov     rbx, [rax+38h]
0x140011f1e  lea     rdx, aTermination; "Termination"
0x140011f25  lea     rcx, [rbp+bstrString]; this
0x140011f29  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x140011f2e  nop
0x140011f2f  mov     r8, [rax]
0x140011f32  xor     edx, edx
0x140011f34  mov     rcx, rdi
0x140011f37  mov     rax, rbx
0x140011f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011f3f  nop
0x140011f40  mov     rcx, [rbp+bstrString]; bstrString
0x140011f44  call    cs:__imp_SysFreeString
0x140011f4a  mov     rax, [rdi]
0x140011f4d  mov     rcx, rdi
0x140011f50  mov     rax, [rax+10h]
0x140011f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011f59  jmp     short loc_140011F82
0x140011f5b  mov     [rsp+40h+var_18], 0; unsigned int
0x140011f63  lea     rax, aCimrequestraGe; "CIMRequestRA::get_RendezvousSession"
0x140011f6a  mov     r9d, 1B6h; unsigned int
0x140011f70  lea     r8, aBaseDiagnosisR_1; "base\\diagnosis\\ra\\dcom\\src\\raimreq"...
0x140011f77  mov     [rsp+40h+ppv], rax; unsigned __int16 *
0x140011f7c  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140011f81  nop
0x140011f82  mov     rcx, [rbp+arg_10]; bstrString
0x140011f86  call    cs:__imp_SysFreeString
0x140011f8c  nop
0x140011f8d  mov     rcx, [rbp+arg_18]; bstrString
0x140011f91  call    cs:__imp_SysFreeString
0x140011f97  nop
0x140011f98  lea     rcx, [rbp+arg_8]
0x140011f9c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140011fa1  xor     eax, eax
0x140011fa3  add     rsp, 40h
0x140011fa7  pop     rdi
0x140011fa8  pop     rbx
0x140011fa9  pop     rbp
0x140011faa  retn
```
