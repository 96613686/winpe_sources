# CRASrv::GetNoviceUserInfo(ushort * *)

- ea: `0x14000ded0`
- end: `0x14000e0d2`
- name: `?GetNoviceUserInfo@CRASrv@@UEAAJPEAPEAG@Z`
- size: `514`
- prototype: `__int64 __fastcall(CRASrv *this, LPVOID *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400035c8`
- `0x14000aab8`
- `0x14000ded0`
- `0x14000e600`
- `0x140015240`
- `0x1400154b0`
- `0x140017010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000e0bd`
- `OLEAUT32!__imp_SysFreeString` at `0x14000e0bd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000df58`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000df58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000e0a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000e0a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000e043`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000e043`

## string_xrefs

- `0x14000deff`: `base\diagnosis\ra\dcom\src\rasrv.cpp`
- `0x14000e08a`: `base\diagnosis\ra\dcom\src\rasrv.cpp`

## pseudocode

```c
__int64 __fastcall CRASrv::GetNoviceUserInfo(CRASrv *this, LPVOID *a2)
{
  const struct _EVENT_DESCRIPTOR *v4; // rdx
  CEventLogger *v5; // rcx
  HRESULT v6; // ebx
  unsigned __int16 *v7; // r8
  signed int v8; // eax
  const struct _EVENT_DESCRIPTOR *v9; // rdx
  CEventLogger *v10; // rcx
  unsigned int v11; // r9d
  const unsigned __int16 *v12; // rsi
  unsigned __int64 v13; // rbx
  unsigned __int16 *v14; // rax
  const struct _EVENT_DESCRIPTOR *v15; // rdx
  CEventLogger *v16; // rcx
  unsigned __int64 v17; // [rsp+30h] [rbp-10h] BYREF
  int v18; // [rsp+68h] [rbp+28h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp+38h] BYREF

  if ( !a2 )
  {
    CEventLogger::LogError(
      this,
      0,
      L"base\\diagnosis\\ra\\dcom\\src\\rasrv.cpp",
      0x38u,
      L"CRASrv::GetNoviceUserInfo",
      0x80004003);
    return 2147500035LL;
  }
  *a2 = 0;
  bstrString = 0;
  v17 = 0;
  v18 = 0;
  ppv = 0;
  v6 = CoCreateInstance(&CLSID_RemoteAssistance, 0, 4u, &GUID_59308e66_7cde_478a_8eba_4d73fdce3545, &ppv);
  if ( v6 < 0 )
  {
    CEventLogger::LogEvent(v5, v4, v7);
    goto LABEL_22;
  }
  v8 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)ppv + 56LL))(ppv, 1, 0);
  v6 = v8;
  if ( v8 < 0 )
  {
    v11 = 95;
LABEL_21:
    CEventLogger::LogError(v10, v9, L"base\\diagnosis\\ra\\dcom\\src\\rasrv.cpp", v11, L"CRASrv::GetNoviceUserInfo", v8);
LABEL_22:
    if ( *a2 )
    {
      CoTaskMemFree(*a2);
      *a2 = 0;
    }
    goto LABEL_24;
  }
  v8 = (*(__int64 (__fastcall **)(LPVOID, int *, _QWORD))(*(_QWORD *)ppv + 88LL))(ppv, &v18, 0);
  v6 = v8;
  if ( v8 < 0 )
  {
    v11 = 100;
    goto LABEL_21;
  }
  if ( !v18 )
  {
    v6 = -2147024814;
    CEventLogger::LogError(
      v10,
      v9,
      L"base\\diagnosis\\ra\\dcom\\src\\rasrv.cpp",
      0x6Bu,
      L"CRASrv::GetNoviceUserInfo",
      0x80070052);
    goto LABEL_22;
  }
  v8 = (*(__int64 (__fastcall **)(LPVOID, BSTR *))(*(_QWORD *)ppv + 64LL))(ppv, &bstrString);
  v6 = v8;
  if ( v8 < 0 )
  {
    v11 = 114;
    goto LABEL_21;
  }
  v12 = bstrString;
  if ( !bstrString )
  {
    v6 = -2147024882;
    CEventLogger::LogError(
      v10,
      v9,
      L"base\\diagnosis\\ra\\dcom\\src\\rasrv.cpp",
      0x78u,
      L"CRASrv::GetNoviceUserInfo",
      0x8007000E);
    goto LABEL_22;
  }
  v8 = StringCchLengthW(bstrString, (unsigned __int64)v9, &v17);
  v6 = v8;
  if ( v8 < 0 )
  {
    v11 = 124;
    goto LABEL_21;
  }
  v13 = v17;
  v14 = (unsigned __int16 *)CoTaskMemAlloc(2 * v17 + 2);
  *a2 = v14;
  if ( !v14 )
  {
    v6 = -2147024882;
    CEventLogger::LogError(
      v16,
      v15,
      L"base\\diagnosis\\ra\\dcom\\src\\rasrv.cpp",
      0x7Fu,
      L"CRASrv::GetNoviceUserInfo",
      0x8007000E);
    goto LABEL_22;
  }
  v8 = StringCchCopyW(v14, v13 + 1, v12);
  v6 = v8;
  if ( v8 < 0 )
  {
    v11 = 131;
    goto LABEL_21;
  }
LABEL_24:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  SysFreeString(bstrString);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000ded0  mov     [rsp-18h+arg_0], rbx
0x14000ded5  push    rbp
0x14000ded6  push    rsi
0x14000ded7  push    rdi
0x14000ded8  mov     rbp, rsp
0x14000dedb  sub     rsp, 40h
0x14000dedf  mov     rdi, rdx
0x14000dee2  test    rdx, rdx
0x14000dee5  jnz     short loc_14000DF15
0x14000dee7  lea     rax, aCrasrvGetnovic; "CRASrv::GetNoviceUserInfo"
0x14000deee  mov     [rsp+40h+var_18], 80004003h; unsigned int
0x14000def6  lea     r9d, [rdx+38h]; unsigned int
0x14000defa  mov     [rsp+40h+ppv], rax; unsigned __int16 *
0x14000deff  lea     r8, aBaseDiagnosisR_2; "base\\diagnosis\\ra\\dcom\\src\\rasrv.c"...
0x14000df06  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000df0b  mov     eax, 80004003h
0x14000df10  jmp     loc_14000E0C5
0x14000df15  mov     qword ptr [rdx], 0
0x14000df1c  lea     rax, [rbp+arg_10]
0x14000df20  xor     edx, edx; pUnkOuter
0x14000df22  mov     [rbp+bstrString], 0
0x14000df2a  lea     r9, _GUID_59308e66_7cde_478a_8eba_4d73fdce3545; riid
0x14000df31  mov     [rbp+var_10], 0
0x14000df39  lea     rcx, CLSID_RemoteAssistance; rclsid
0x14000df40  mov     [rbp+arg_8], 0
0x14000df47  mov     [rbp+arg_10], 0
0x14000df4f  lea     r8d, [rdx+4]; dwClsContext
0x14000df53  mov     [rsp+40h+ppv], rax; ppv
0x14000df58  call    cs:__imp_CoCreateInstance
0x14000df5e  mov     ebx, eax
0x14000df60  test    eax, eax
0x14000df62  jns     short loc_14000DF6E
0x14000df64  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,ushort *)
0x14000df69  jmp     loc_14000E09B
0x14000df6e  mov     rcx, [rbp+arg_10]
0x14000df72  xor     r9d, r9d
0x14000df75  xor     r8d, r8d
0x14000df78  mov     rax, [rcx]
0x14000df7b  lea     edx, [r9+1]
0x14000df7f  mov     rax, [rax+38h]
0x14000df83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000df88  mov     ebx, eax
0x14000df8a  test    eax, eax
0x14000df8c  jns     short loc_14000DF99
0x14000df8e  mov     r9d, 5Fh ; '_'
0x14000df94  jmp     loc_14000E07F
0x14000df99  mov     rcx, [rbp+arg_10]
0x14000df9d  lea     rdx, [rbp+arg_8]
0x14000dfa1  xor     r8d, r8d
0x14000dfa4  mov     rax, [rcx]
0x14000dfa7  mov     rax, [rax+58h]
0x14000dfab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dfb0  mov     ebx, eax
0x14000dfb2  test    eax, eax
0x14000dfb4  jns     short loc_14000DFC1
0x14000dfb6  mov     r9d, 64h ; 'd'
0x14000dfbc  jmp     loc_14000E07F
0x14000dfc1  cmp     [rbp+arg_8], 0
0x14000dfc5  jnz     short loc_14000DFDF
0x14000dfc7  mov     ebx, 80070052h
0x14000dfcc  mov     [rsp+40h+var_18], 80070052h
0x14000dfd4  mov     r9d, 6Bh ; 'k'
0x14000dfda  jmp     loc_14000E083
0x14000dfdf  mov     rcx, [rbp+arg_10]
0x14000dfe3  lea     rdx, [rbp+bstrString]
0x14000dfe7  mov     rax, [rcx]
0x14000dfea  mov     rax, [rax+40h]
0x14000dfee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dff3  mov     ebx, eax
0x14000dff5  test    eax, eax
0x14000dff7  jns     short loc_14000E001
0x14000dff9  mov     r9d, 72h ; 'r'
0x14000dfff  jmp     short loc_14000E07F
0x14000e001  mov     rsi, [rbp+bstrString]
0x14000e005  test    rsi, rsi
0x14000e008  jnz     short loc_14000E01D
0x14000e00a  mov     ebx, 8007000Eh
0x14000e00f  mov     [rsp+40h+var_18], 8007000Eh
0x14000e017  lea     r9d, [rsi+78h]
0x14000e01b  jmp     short loc_14000E083
0x14000e01d  lea     r8, [rbp+var_10]; unsigned __int64 *
0x14000e021  mov     rcx, rsi; unsigned __int16 *
0x14000e024  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14000e029  mov     ebx, eax
0x14000e02b  test    eax, eax
0x14000e02d  jns     short loc_14000E037
0x14000e02f  mov     r9d, 7Ch ; '|'
0x14000e035  jmp     short loc_14000E07F
0x14000e037  mov     rbx, [rbp+var_10]
0x14000e03b  lea     rcx, ds:2[rbx*2]; cb
0x14000e043  call    cs:__imp_CoTaskMemAlloc
0x14000e049  mov     [rdi], rax
0x14000e04c  test    rax, rax
0x14000e04f  jnz     short loc_14000E064
0x14000e051  mov     ebx, 8007000Eh
0x14000e056  mov     [rsp+40h+var_18], 8007000Eh
0x14000e05e  lea     r9d, [rax+7Fh]
0x14000e062  jmp     short loc_14000E083
0x14000e064  lea     rdx, [rbx+1]; unsigned __int64
0x14000e068  mov     r8, rsi; unsigned __int16 *
0x14000e06b  mov     rcx, rax; unsigned __int16 *
0x14000e06e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000e073  mov     ebx, eax
0x14000e075  test    eax, eax
0x14000e077  jns     short loc_14000E0B0
0x14000e079  mov     r9d, 83h; unsigned int
0x14000e07f  mov     [rsp+40h+var_18], eax; unsigned int
0x14000e083  lea     rax, aCrasrvGetnovic; "CRASrv::GetNoviceUserInfo"
0x14000e08a  lea     r8, aBaseDiagnosisR_2; "base\\diagnosis\\ra\\dcom\\src\\rasrv.c"...
0x14000e091  mov     [rsp+40h+ppv], rax; unsigned __int16 *
0x14000e096  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000e09b  mov     rcx, [rdi]; pv
0x14000e09e  test    rcx, rcx
0x14000e0a1  jz      short loc_14000E0B0
0x14000e0a3  call    cs:__imp_CoTaskMemFree
0x14000e0a9  mov     qword ptr [rdi], 0
0x14000e0b0  lea     rcx, [rbp+arg_10]
0x14000e0b4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14000e0b9  mov     rcx, [rbp+bstrString]; bstrString
0x14000e0bd  call    cs:__imp_SysFreeString
0x14000e0c3  mov     eax, ebx
0x14000e0c5  mov     rbx, [rsp+40h+arg_0]
0x14000e0ca  add     rsp, 40h
0x14000e0ce  pop     rdi
0x14000e0cf  pop     rsi
0x14000e0d0  pop     rbp
0x14000e0d1  retn
```
