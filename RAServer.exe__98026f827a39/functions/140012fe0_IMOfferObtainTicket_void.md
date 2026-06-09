# IMOfferObtainTicket(void *)

- ea: `0x140012fe0`
- end: `0x14001323c`
- name: `?IMOfferObtainTicket@@YAKPEAX@Z`
- size: `604`
- prototype: `__int64 __fastcall(_QWORD *lpThreadParameter, const struct _EVENT_DESCRIPTOR *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400035c8`
- `0x14000e664`
- `0x140012fe0`
- `0x140015240`
- `0x140017010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1400131d5`
- `OLEAUT32!__imp_SysFreeString` at `0x140013217`
- `OLEAUT32!__imp_SysFreeString` at `0x140013222`
- `OLEAUT32!__imp_SysFreeString` at `0x1400131d5`
- `OLEAUT32!__imp_SysFreeString` at `0x140013217`
- `OLEAUT32!__imp_SysFreeString` at `0x140013222`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140013050`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140013050`

## string_xrefs

- `0x140013201`: `base\diagnosis\ra\dcom\src\raimoffer.cpp`
- `0x140013027`: `base\diagnosis\ra\dcom\src\raimofferevnt.cpp`
- `0x140013177`: `base\diagnosis\ra\dcom\src\raimofferevnt.cpp`

## pseudocode

```c
__int64 __fastcall IMOfferObtainTicket(_QWORD *lpThreadParameter, const struct _EVENT_DESCRIPTOR *a2)
{
  HRESULT v3; // eax
  const struct _EVENT_DESCRIPTOR *v4; // rdx
  CEventLogger *v5; // rcx
  unsigned int v6; // r9d
  __int64 v7; // rcx
  const struct _EVENT_DESCRIPTOR *v8; // rdx
  CEventLogger *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rdi
  void (__fastcall *v12)(__int64, _QWORD, _QWORD); // rbx
  ATL::CComBSTR *v13; // rax
  BSTR bstrString[2]; // [rsp+30h] [rbp-10h] BYREF
  int v16; // [rsp+60h] [rbp+20h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+28h] BYREF
  BSTR v18; // [rsp+70h] [rbp+30h] BYREF
  BSTR v19; // [rsp+78h] [rbp+38h] BYREF

  v16 = 0;
  ppv = 0;
  v19 = 0;
  v18 = 0;
  if ( !lpThreadParameter )
  {
    CEventLogger::LogError(
      0,
      a2,
      L"base\\diagnosis\\ra\\dcom\\src\\raimofferevnt.cpp",
      0x315u,
      L"IMOfferObtainTicket",
      0x80004003);
    goto LABEL_26;
  }
  v3 = CoCreateInstance(&CLSID_RemoteAssistance, 0, 4u, &GUID_59308e66_7cde_478a_8eba_4d73fdce3545, &ppv);
  if ( v3 >= 0 )
  {
    v7 = lpThreadParameter[1];
    if ( !v7 )
    {
      CEventLogger::LogError(
        0,
        v4,
        L"base\\diagnosis\\ra\\dcom\\src\\raimofferevnt.cpp",
        0x323u,
        L"IMOfferObtainTicket",
        0x80004003);
      goto LABEL_22;
    }
    v3 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v7 + 32LL))(v7, &v18);
    if ( v3 >= 0 )
    {
      v3 = (*(__int64 (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)ppv + 128LL))(ppv, v18);
      if ( v3 >= 0 )
      {
        v3 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 56LL))(ppv, 1, 1);
        if ( v3 >= 0 )
        {
          v3 = (*(__int64 (__fastcall **)(LPVOID, int *, _QWORD))(*(_QWORD *)ppv + 88LL))(ppv, &v16, 0);
          if ( v3 >= 0 )
          {
            if ( !v16 )
            {
              CEventLogger::LogError(
                v5,
                v4,
                L"base\\diagnosis\\ra\\dcom\\src\\raimofferevnt.cpp",
                0x33Au,
                L"IMOfferObtainTicket",
                0);
              goto LABEL_22;
            }
            v3 = (*(__int64 (__fastcall **)(LPVOID, BSTR *))(*(_QWORD *)ppv + 64LL))(ppv, &v19);
            if ( v3 >= 0 )
            {
              v3 = (*(__int64 (__fastcall **)(_QWORD, BSTR))(*(_QWORD *)lpThreadParameter[1] + 56LL))(
                     lpThreadParameter[1],
                     v19);
              if ( v3 >= 0 )
                goto LABEL_26;
              v6 = 837;
            }
            else
            {
              v6 = 831;
            }
          }
          else
          {
            v6 = 825;
          }
        }
        else
        {
          v6 = 819;
        }
      }
      else
      {
        v6 = 806;
      }
    }
    else
    {
      v6 = 805;
    }
  }
  else
  {
    v6 = 797;
  }
  CEventLogger::LogError(v5, v4, L"base\\diagnosis\\ra\\dcom\\src\\raimofferevnt.cpp", v6, L"IMOfferObtainTicket", v3);
LABEL_22:
  v10 = lpThreadParameter[1];
  if ( v10 )
  {
    v11 = *(_QWORD *)(v10 + 24);
    if ( v11 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v11 + 8LL))(*(_QWORD *)(v10 + 24));
      v12 = *(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v11 + 56LL);
      v13 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, L"Termination");
      v12(v11, 0, *(_QWORD *)v13);
      SysFreeString(bstrString[0]);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    else
    {
      CEventLogger::LogError(
        v9,
        v8,
        L"base\\diagnosis\\ra\\dcom\\src\\raimoffer.cpp",
        0x190u,
        L"CIMOfferRA::get_RendezvousSession",
        0);
    }
  }
LABEL_26:
  SysFreeString(v18);
  SysFreeString(v19);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  return 0;
}

```

## disassembly

```asm
0x140012fe0  push    rbp
0x140012fe2  push    rbx
0x140012fe3  push    rdi
0x140012fe4  mov     rbp, rsp
0x140012fe7  sub     rsp, 40h
0x140012feb  mov     rbx, rcx
0x140012fee  mov     [rbp+arg_0], 0
0x140012ff5  mov     [rbp+arg_8], 0
0x140012ffd  mov     [rbp+arg_18], 0
0x140013005  mov     [rbp+arg_10], 0
0x14001300d  test    rcx, rcx
0x140013010  jnz     short loc_140013033
0x140013012  mov     [rsp+40h+var_18], 80004003h
0x14001301a  lea     rax, aImofferobtaint; "IMOfferObtainTicket"
0x140013021  mov     r9d, 315h
0x140013027  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\dcom\\src\\raimoff"...
0x14001302e  jmp     loc_140013208
0x140013033  lea     rax, [rbp+arg_8]
0x140013037  mov     [rsp+40h+ppv], rax; ppv
0x14001303c  lea     r9, _GUID_59308e66_7cde_478a_8eba_4d73fdce3545; riid
0x140013043  xor     edx, edx; pUnkOuter
0x140013045  lea     r8d, [rdx+4]; dwClsContext
0x140013049  lea     rcx, CLSID_RemoteAssistance; rclsid
0x140013050  call    cs:__imp_CoCreateInstance
0x140013056  test    eax, eax
0x140013058  jns     short loc_140013065
0x14001305a  mov     r9d, 31Dh
0x140013060  jmp     loc_140013167
0x140013065  mov     rcx, [rbx+8]
0x140013069  test    rcx, rcx
0x14001306c  jnz     short loc_140013081
0x14001306e  mov     [rsp+40h+var_18], 80004003h
0x140013076  mov     r9d, 323h
0x14001307c  jmp     loc_14001316B
0x140013081  mov     rax, [rcx]
0x140013084  lea     rdx, [rbp+arg_10]
0x140013088  mov     rax, [rax+20h]
0x14001308c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013091  test    eax, eax
0x140013093  jns     short loc_1400130A0
0x140013095  mov     r9d, 325h
0x14001309b  jmp     loc_140013167
0x1400130a0  mov     rcx, [rbp+arg_8]
0x1400130a4  mov     rax, [rcx]
0x1400130a7  mov     rdx, [rbp+arg_10]
0x1400130ab  mov     rax, [rax+80h]
0x1400130b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400130b7  test    eax, eax
0x1400130b9  jns     short loc_1400130C6
0x1400130bb  mov     r9d, 326h
0x1400130c1  jmp     loc_140013167
0x1400130c6  mov     rcx, [rbp+arg_8]
0x1400130ca  mov     rax, [rcx]
0x1400130cd  xor     r9d, r9d
0x1400130d0  lea     edx, [r9+1]
0x1400130d4  mov     r8d, edx
0x1400130d7  mov     rax, [rax+38h]
0x1400130db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400130e0  test    eax, eax
0x1400130e2  jns     short loc_1400130EC
0x1400130e4  mov     r9d, 333h
0x1400130ea  jmp     short loc_140013167
0x1400130ec  mov     rcx, [rbp+arg_8]
0x1400130f0  mov     rax, [rcx]
0x1400130f3  xor     r8d, r8d
0x1400130f6  lea     rdx, [rbp+arg_0]
0x1400130fa  mov     rax, [rax+58h]
0x1400130fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013103  test    eax, eax
0x140013105  jns     short loc_14001310F
0x140013107  mov     r9d, 339h
0x14001310d  jmp     short loc_140013167
0x14001310f  cmp     [rbp+arg_0], 0
0x140013113  jnz     short loc_140013125
0x140013115  mov     [rsp+40h+var_18], 0
0x14001311d  mov     r9d, 33Ah
0x140013123  jmp     short loc_14001316B
0x140013125  mov     rcx, [rbp+arg_8]
0x140013129  mov     rax, [rcx]
0x14001312c  lea     rdx, [rbp+arg_18]
0x140013130  mov     rax, [rax+40h]
0x140013134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013139  test    eax, eax
0x14001313b  jns     short loc_140013145
0x14001313d  mov     r9d, 33Fh
0x140013143  jmp     short loc_140013167
0x140013145  mov     rcx, [rbx+8]
0x140013149  mov     rax, [rcx]
0x14001314c  mov     rdx, [rbp+arg_18]
0x140013150  mov     rax, [rax+38h]
0x140013154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013159  test    eax, eax
0x14001315b  jns     loc_140013213
0x140013161  mov     r9d, 345h; unsigned int
0x140013167  mov     [rsp+40h+var_18], eax; unsigned int
0x14001316b  lea     rax, aImofferobtaint; "IMOfferObtainTicket"
0x140013172  mov     [rsp+40h+ppv], rax; unsigned __int16 *
0x140013177  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\dcom\\src\\raimoff"...
0x14001317e  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140013183  mov     rax, [rbx+8]
0x140013187  test    rax, rax
0x14001318a  jz      loc_140013213
0x140013190  mov     rdi, [rax+18h]
0x140013194  test    rdi, rdi
0x140013197  jz      short loc_1400131EC
0x140013199  mov     rax, [rdi]
0x14001319c  mov     rcx, rdi
0x14001319f  mov     rax, [rax+8]
0x1400131a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400131a8  mov     rax, [rdi]
0x1400131ab  mov     rbx, [rax+38h]
0x1400131af  lea     rdx, aTermination; "Termination"
0x1400131b6  lea     rcx, [rbp+bstrString]; this
0x1400131ba  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1400131bf  nop
0x1400131c0  mov     r8, [rax]
0x1400131c3  xor     edx, edx
0x1400131c5  mov     rcx, rdi
0x1400131c8  mov     rax, rbx
0x1400131cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400131d0  nop
0x1400131d1  mov     rcx, [rbp+bstrString]; bstrString
0x1400131d5  call    cs:__imp_SysFreeString
0x1400131db  mov     rax, [rdi]
0x1400131de  mov     rcx, rdi
0x1400131e1  mov     rax, [rax+10h]
0x1400131e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400131ea  jmp     short loc_140013213
0x1400131ec  mov     [rsp+40h+var_18], 0; unsigned int
0x1400131f4  lea     rax, aCimofferraGetR; "CIMOfferRA::get_RendezvousSession"
0x1400131fb  mov     r9d, 190h; unsigned int
0x140013201  lea     r8, aBaseDiagnosisR_4; "base\\diagnosis\\ra\\dcom\\src\\raimoff"...
0x140013208  mov     [rsp+40h+ppv], rax; unsigned __int16 *
0x14001320d  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140013212  nop
0x140013213  mov     rcx, [rbp+arg_10]; bstrString
0x140013217  call    cs:__imp_SysFreeString
0x14001321d  nop
0x14001321e  mov     rcx, [rbp+arg_18]; bstrString
0x140013222  call    cs:__imp_SysFreeString
0x140013228  nop
0x140013229  lea     rcx, [rbp+arg_8]
0x14001322d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140013232  xor     eax, eax
0x140013234  add     rsp, 40h
0x140013238  pop     rdi
0x140013239  pop     rbx
0x14001323a  pop     rbp
0x14001323b  retn
```
