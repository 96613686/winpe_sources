# CIMRequestRAEvent::SendEncryptedNoviceTicket(void)

- ea: `0x140014a90`
- end: `0x140014cc6`
- name: `?SendEncryptedNoviceTicket@CIMRequestRAEvent@@QEAAJXZ`
- size: `566`
- prototype: `__int64 __fastcall(CIMRequestRAEvent *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140011fc0`

## callees

- `0x1400035c8`
- `0x140013ef8`
- `0x140014a90`
- `0x140015240`
- `0x1400154b0`
- `0x140017010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140014c96`
- `OLEAUT32!__imp_SysFreeString` at `0x140014ca1`
- `OLEAUT32!__imp_SysFreeString` at `0x140014cac`
- `OLEAUT32!__imp_SysFreeString` at `0x140014c96`
- `OLEAUT32!__imp_SysFreeString` at `0x140014ca1`
- `OLEAUT32!__imp_SysFreeString` at `0x140014cac`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140014ae2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140014ae2`

## string_xrefs

- `0x140014bd5`: `base\diagnosis\ra\dcom\src\publickeyexch.cpp`
- `0x140014c85`: `base\diagnosis\ra\dcom\src\publickeyexch.cpp`

## pseudocode

```c
__int64 __fastcall CIMRequestRAEvent::SendEncryptedNoviceTicket(CIMRequestRAEvent *this)
{
  const struct _EVENT_DESCRIPTOR *v2; // rdx
  CEventLogger *v3; // rcx
  HRESULT v4; // ebx
  unsigned __int16 *v5; // r8
  const struct _EVENT_DESCRIPTOR *v6; // rdx
  CEventLogger *v7; // rcx
  __int64 v8; // rcx
  signed int v9; // eax
  const struct _EVENT_DESCRIPTOR *v10; // rdx
  CEventLogger *v11; // rcx
  signed int v12; // eax
  const struct _EVENT_DESCRIPTOR *v13; // rdx
  CEventLogger *v14; // rcx
  signed int v15; // eax
  const struct _EVENT_DESCRIPTOR *v16; // rdx
  CEventLogger *v17; // rcx
  signed int v18; // eax
  const struct _EVENT_DESCRIPTOR *v19; // rdx
  CEventLogger *v20; // rcx
  signed int v21; // eax
  const struct _EVENT_DESCRIPTOR *v22; // rdx
  CEventLogger *v23; // rcx
  signed int v24; // eax
  CEventLogger *v25; // rcx
  __int64 v26; // rcx
  signed int v27; // eax
  const struct _EVENT_DESCRIPTOR *v28; // rdx
  CEventLogger *v29; // rcx
  unsigned int v30; // r9d
  BSTR v32; // [rsp+30h] [rbp-10h] BYREF
  BSTR v33; // [rsp+38h] [rbp-8h] BYREF
  int v34; // [rsp+68h] [rbp+28h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp+38h] BYREF

  ppv = 0;
  v33 = 0;
  v32 = 0;
  bstrString = 0;
  v34 = 0;
  v4 = CoCreateInstance(&CLSID_RemoteAssistance, 0, 4u, &GUID_59308e66_7cde_478a_8eba_4d73fdce3545, &ppv);
  if ( v4 < 0 )
  {
    CEventLogger::LogEvent(v3, v2, v5);
    CEventLogger::LogError(
      v7,
      v6,
      L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
      0x3E8u,
      L"CIMRequestRAEvent::SendEncryptedNoviceTicket",
      v4);
    goto LABEL_24;
  }
  v8 = *((_QWORD *)this + 1);
  if ( !v8 )
  {
    v30 = 1017;
    goto LABEL_23;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v8 + 32LL))(v8, &bstrString);
  v4 = v9;
  if ( v9 < 0 )
  {
    CEventLogger::LogError(
      v11,
      v10,
      L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
      0x3F0u,
      L"CIMRequestRAEvent::SendEncryptedNoviceTicket",
      v9);
    goto LABEL_24;
  }
  v12 = (*(__int64 (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)ppv + 128LL))(ppv, bstrString);
  v4 = v12;
  if ( v12 < 0 )
  {
    CEventLogger::LogError(
      v14,
      v13,
      L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
      0x3FFu,
      L"CIMRequestRAEvent::SendEncryptedNoviceTicket",
      v12);
    goto LABEL_24;
  }
  v15 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 112LL))(ppv, *((_QWORD *)this + 11));
  v4 = v15;
  if ( v15 < 0 )
  {
    CEventLogger::LogError(
      v17,
      v16,
      L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
      0x405u,
      L"CIMRequestRAEvent::SendEncryptedNoviceTicket",
      v15);
    goto LABEL_24;
  }
  v18 = (*(__int64 (__fastcall **)(LPVOID, int *, _QWORD))(*(_QWORD *)ppv + 88LL))(ppv, &v34, 0);
  v4 = v18;
  if ( v18 < 0 )
  {
    CEventLogger::LogError(
      v20,
      v19,
      L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
      0x410u,
      L"CIMRequestRAEvent::SendEncryptedNoviceTicket",
      v18);
    goto LABEL_24;
  }
  if ( !v34 )
  {
    CEventLogger::LogError(
      v20,
      v19,
      L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
      0x411u,
      L"CIMRequestRAEvent::SendEncryptedNoviceTicket",
      0);
    v4 = -2147467259;
    goto LABEL_24;
  }
  v21 = (*(__int64 (__fastcall **)(LPVOID, BSTR *))(*(_QWORD *)ppv + 64LL))(ppv, &v33);
  v4 = v21;
  if ( v21 < 0 )
  {
    CEventLogger::LogError(
      v23,
      v22,
      L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
      0x416u,
      L"CIMRequestRAEvent::SendEncryptedNoviceTicket",
      v21);
    goto LABEL_24;
  }
  v24 = CIMRequestRAEvent::GenEncryptdNoviceBlob(this, v33, &v32);
  v4 = v24;
  if ( v24 < 0 )
  {
    CEventLogger::LogError(
      v25,
      v2,
      L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
      0x41Du,
      L"CIMRequestRAEvent::SendEncryptedNoviceTicket",
      v24);
    goto LABEL_24;
  }
  v26 = *((_QWORD *)this + 1);
  if ( !v26 )
  {
    v30 = 1067;
LABEL_23:
    v4 = -2147467261;
    CEventLogger::LogError(
      0,
      v2,
      L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
      v30,
      L"CIMRequestRAEvent::SendEncryptedNoviceTicket",
      0x80004003);
    goto LABEL_24;
  }
  v27 = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v26 + 56LL))(v26, v32);
  v4 = v27;
  if ( v27 < 0 )
    CEventLogger::LogError(
      v29,
      v28,
      L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
      0x424u,
      L"CIMRequestRAEvent::SendEncryptedNoviceTicket",
      v27);
LABEL_24:
  SysFreeString(bstrString);
  SysFreeString(v32);
  SysFreeString(v33);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140014a90  push    rbp
0x140014a92  push    rbx
0x140014a93  push    rdi
0x140014a94  mov     rbp, rsp
0x140014a97  sub     rsp, 40h
0x140014a9b  mov     rdi, rcx
0x140014a9e  mov     [rbp+arg_10], 0
0x140014aa6  mov     [rbp+var_8], 0
0x140014aae  mov     [rbp+var_10], 0
0x140014ab6  mov     [rbp+bstrString], 0
0x140014abe  mov     [rbp+arg_8], 0
0x140014ac5  lea     rax, [rbp+arg_10]
0x140014ac9  mov     [rsp+40h+ppv], rax; ppv
0x140014ace  lea     r9, _GUID_59308e66_7cde_478a_8eba_4d73fdce3545; riid
0x140014ad5  xor     edx, edx; pUnkOuter
0x140014ad7  lea     r8d, [rdx+4]; dwClsContext
0x140014adb  lea     rcx, CLSID_RemoteAssistance; rclsid
0x140014ae2  call    cs:__imp_CoCreateInstance
0x140014ae8  mov     ebx, eax
0x140014aea  test    eax, eax
0x140014aec  jns     short loc_140014B02
0x140014aee  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,ushort *)
0x140014af3  mov     [rsp+40h+var_18], ebx
0x140014af7  mov     r9d, 3E8h
0x140014afd  jmp     loc_140014C79
0x140014b02  mov     rcx, [rdi+8]; this
0x140014b06  test    rcx, rcx
0x140014b09  jz      loc_140014C66
0x140014b0f  mov     rax, [rcx]
0x140014b12  lea     rdx, [rbp+bstrString]
0x140014b16  mov     rax, [rax+20h]
0x140014b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014b1f  mov     ebx, eax
0x140014b21  test    eax, eax
0x140014b23  jns     short loc_140014B34
0x140014b25  mov     [rsp+40h+var_18], eax
0x140014b29  mov     r9d, 3F0h
0x140014b2f  jmp     loc_140014C79
0x140014b34  mov     rcx, [rbp+arg_10]
0x140014b38  mov     rax, [rcx]
0x140014b3b  mov     rdx, [rbp+bstrString]
0x140014b3f  mov     rax, [rax+80h]
0x140014b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014b4b  mov     ebx, eax
0x140014b4d  test    eax, eax
0x140014b4f  jns     short loc_140014B60
0x140014b51  mov     [rsp+40h+var_18], eax
0x140014b55  mov     r9d, 3FFh
0x140014b5b  jmp     loc_140014C79
0x140014b60  mov     rcx, [rbp+arg_10]
0x140014b64  mov     rax, [rcx]
0x140014b67  mov     rdx, [rdi+58h]
0x140014b6b  mov     rax, [rax+70h]
0x140014b6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014b74  mov     ebx, eax
0x140014b76  test    eax, eax
0x140014b78  jns     short loc_140014B89
0x140014b7a  mov     [rsp+40h+var_18], eax
0x140014b7e  mov     r9d, 405h
0x140014b84  jmp     loc_140014C79
0x140014b89  mov     rcx, [rbp+arg_10]
0x140014b8d  mov     rax, [rcx]
0x140014b90  xor     r8d, r8d
0x140014b93  lea     rdx, [rbp+arg_8]
0x140014b97  mov     rax, [rax+58h]
0x140014b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014ba0  mov     ebx, eax
0x140014ba2  test    eax, eax
0x140014ba4  jns     short loc_140014BB5
0x140014ba6  mov     [rsp+40h+var_18], eax
0x140014baa  mov     r9d, 410h
0x140014bb0  jmp     loc_140014C79
0x140014bb5  cmp     [rbp+arg_8], 0
0x140014bb9  jnz     short loc_140014BEB
0x140014bbb  mov     [rsp+40h+var_18], 0; unsigned int
0x140014bc3  lea     rax, aCimrequestraev_11; "CIMRequestRAEvent::SendEncryptedNoviceT"...
0x140014bca  mov     [rsp+40h+ppv], rax; unsigned __int16 *
0x140014bcf  mov     r9d, 411h; unsigned int
0x140014bd5  lea     r8, aBaseDiagnosisR; "base\\diagnosis\\ra\\dcom\\src\\publick"...
0x140014bdc  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140014be1  mov     ebx, 80004005h
0x140014be6  jmp     loc_140014C92
0x140014beb  mov     rcx, [rbp+arg_10]
0x140014bef  mov     rax, [rcx]
0x140014bf2  lea     rdx, [rbp+var_8]
0x140014bf6  mov     rax, [rax+40h]
0x140014bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014bff  mov     ebx, eax
0x140014c01  test    eax, eax
0x140014c03  jns     short loc_140014C11
0x140014c05  mov     [rsp+40h+var_18], eax
0x140014c09  mov     r9d, 416h
0x140014c0f  jmp     short loc_140014C79
0x140014c11  lea     r8, [rbp+var_10]; unsigned __int16 **
0x140014c15  mov     rdx, [rbp+var_8]; unsigned __int16 *
0x140014c19  mov     rcx, rdi; this
0x140014c1c  call    ?GenEncryptdNoviceBlob@CIMRequestRAEvent@@QEAAJPEAGPEAPEAG@Z; CIMRequestRAEvent::GenEncryptdNoviceBlob(ushort *,ushort * *)
0x140014c21  mov     ebx, eax
0x140014c23  test    eax, eax
0x140014c25  jns     short loc_140014C33
0x140014c27  mov     [rsp+40h+var_18], eax
0x140014c2b  mov     r9d, 41Dh
0x140014c31  jmp     short loc_140014C79
0x140014c33  mov     rcx, [rdi+8]
0x140014c37  test    rcx, rcx
0x140014c3a  jz      short loc_140014C5E
0x140014c3c  mov     rax, [rcx]
0x140014c3f  mov     rdx, [rbp+var_10]
0x140014c43  mov     rax, [rax+38h]
0x140014c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014c4c  mov     ebx, eax
0x140014c4e  test    eax, eax
0x140014c50  jns     short loc_140014C92
0x140014c52  mov     [rsp+40h+var_18], eax
0x140014c56  mov     r9d, 424h
0x140014c5c  jmp     short loc_140014C79
0x140014c5e  mov     r9d, 42Bh
0x140014c64  jmp     short loc_140014C6C
0x140014c66  mov     r9d, 3F9h; unsigned int
0x140014c6c  mov     [rsp+40h+var_18], 80004003h; unsigned int
0x140014c74  mov     ebx, 80004003h
0x140014c79  lea     rax, aCimrequestraev_11; "CIMRequestRAEvent::SendEncryptedNoviceT"...
0x140014c80  mov     [rsp+40h+ppv], rax; unsigned __int16 *
0x140014c85  lea     r8, aBaseDiagnosisR; "base\\diagnosis\\ra\\dcom\\src\\publick"...
0x140014c8c  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140014c91  nop
0x140014c92  mov     rcx, [rbp+bstrString]; bstrString
0x140014c96  call    cs:__imp_SysFreeString
0x140014c9c  nop
0x140014c9d  mov     rcx, [rbp+var_10]; bstrString
0x140014ca1  call    cs:__imp_SysFreeString
0x140014ca7  nop
0x140014ca8  mov     rcx, [rbp+var_8]; bstrString
0x140014cac  call    cs:__imp_SysFreeString
0x140014cb2  nop
0x140014cb3  lea     rcx, [rbp+arg_10]
0x140014cb7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140014cbc  mov     eax, ebx
0x140014cbe  add     rsp, 40h
0x140014cc2  pop     rdi
0x140014cc3  pop     rbx
0x140014cc4  pop     rbp
0x140014cc5  retn
```
