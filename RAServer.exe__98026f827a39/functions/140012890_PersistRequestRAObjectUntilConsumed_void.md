# PersistRequestRAObjectUntilConsumed(void *)

- ea: `0x140012890`
- end: `0x140012a76`
- name: `?PersistRequestRAObjectUntilConsumed@@YAKPEAX@Z`
- size: `486`
- prototype: `__int64 __fastcall(CEventLogger *lpThreadParameter, const struct _EVENT_DESCRIPTOR *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400035c8`
- `0x140012890`
- `0x140015240`
- `0x1400154b0`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140012a45`
- `KERNEL32!GetProcessHeap` at `0x140012a45`
- `KERNEL32!HeapFree` at `0x140012a53`
- `KERNEL32!HeapFree` at `0x140012a53`
- `OLEAUT32!__imp_SysFreeString` at `0x140012a23`
- `OLEAUT32!__imp_SysFreeString` at `0x140012a38`
- `OLEAUT32!__imp_SysFreeString` at `0x140012a23`
- `OLEAUT32!__imp_SysFreeString` at `0x140012a38`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140012951`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140012951`

## string_xrefs

- `0x1400128d0`: `base\diagnosis\ra\dcom\src\raimrequestevnt.cpp`
- `0x140012901`: `base\diagnosis\ra\dcom\src\raimrequestevnt.cpp`
- `0x140012a0f`: `base\diagnosis\ra\dcom\src\raimrequestevnt.cpp`

## pseudocode

```c
__int64 __fastcall PersistRequestRAObjectUntilConsumed(
        CEventLogger *lpThreadParameter,
        const struct _EVENT_DESCRIPTOR *a2)
{
  BSTR *v3; // rbx
  const struct _EVENT_DESCRIPTOR *v4; // rdx
  CEventLogger *v5; // rcx
  HRESULT v6; // esi
  unsigned __int16 *v7; // r8
  const struct _EVENT_DESCRIPTOR *v8; // rdx
  CEventLogger *v9; // rcx
  signed int v10; // eax
  const struct _EVENT_DESCRIPTOR *v11; // rdx
  CEventLogger *v12; // rcx
  unsigned int v13; // r9d
  HANDLE ProcessHeap; // rax
  int v16; // [rsp+40h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  ppv = 0;
  v16 = 0;
  if ( !lpThreadParameter )
  {
    CEventLogger::LogError(
      0,
      a2,
      L"base\\diagnosis\\ra\\dcom\\src\\raimrequestevnt.cpp",
      0x4E3u,
      L"PersistRequestRAObjectUntilConsumed",
      0x80004003);
    goto LABEL_23;
  }
  if ( *(_QWORD *)lpThreadParameter )
  {
    v3 = (BSTR *)((char *)lpThreadParameter + 8);
    if ( *((_QWORD *)lpThreadParameter + 1) )
    {
      v6 = CoCreateInstance(&CLSID_RemoteAssistance, 0, 4u, &GUID_59308e66_7cde_478a_8eba_4d73fdce3545, &ppv);
      if ( v6 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 72LL))(ppv, *(_QWORD *)lpThreadParameter);
        if ( v10 >= 0 )
        {
          v10 = (*(__int64 (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)ppv + 144LL))(ppv, *v3);
          if ( v10 >= 0 )
          {
            v10 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppv + 80LL))(
                    ppv,
                    0,
                    *(_QWORD *)lpThreadParameter,
                    0);
            if ( v10 >= 0 )
            {
              v10 = (*(__int64 (__fastcall **)(LPVOID, int *, _QWORD))(*(_QWORD *)ppv + 96LL))(ppv, &v16, 0);
              if ( v16 )
                goto LABEL_18;
              v13 = 1294;
            }
            else
            {
              v13 = 1285;
            }
          }
          else
          {
            v13 = 1279;
          }
        }
        else
        {
          v13 = 1273;
        }
        CEventLogger::LogError(
          v12,
          v11,
          L"base\\diagnosis\\ra\\dcom\\src\\raimrequestevnt.cpp",
          v13,
          L"PersistRequestRAObjectUntilConsumed",
          v10);
        goto LABEL_18;
      }
      CEventLogger::LogEvent(v5, v4, v7);
      CEventLogger::LogError(
        v9,
        v8,
        L"base\\diagnosis\\ra\\dcom\\src\\raimrequestevnt.cpp",
        0x4F2u,
        L"PersistRequestRAObjectUntilConsumed",
        v6);
    }
    else
    {
      CEventLogger::LogError(
        lpThreadParameter,
        a2,
        L"base\\diagnosis\\ra\\dcom\\src\\raimrequestevnt.cpp",
        0x4E5u,
        L"PersistRequestRAObjectUntilConsumed",
        0x80004003);
    }
  }
  else
  {
    CEventLogger::LogError(
      lpThreadParameter,
      a2,
      L"base\\diagnosis\\ra\\dcom\\src\\raimrequestevnt.cpp",
      0x4E4u,
      L"PersistRequestRAObjectUntilConsumed",
      0x80004003);
    v3 = (BSTR *)((char *)lpThreadParameter + 8);
  }
LABEL_18:
  if ( *(_QWORD *)lpThreadParameter )
  {
    SysFreeString(*(BSTR *)lpThreadParameter);
    *(_QWORD *)lpThreadParameter = 0;
  }
  if ( *v3 )
  {
    SysFreeString(*v3);
    *v3 = 0;
  }
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, lpThreadParameter);
LABEL_23:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  return 0;
}

```

## disassembly

```asm
0x140012890  mov     rax, rsp
0x140012893  mov     [rax+18h], rbx
0x140012897  mov     [rax+20h], rsi
0x14001289b  push    rdi
0x14001289c  sub     rsp, 30h
0x1400128a0  mov     rdi, rcx
0x1400128a3  mov     qword ptr [rax+10h], 0
0x1400128ab  mov     dword ptr [rax+8], 0
0x1400128b2  test    rcx, rcx
0x1400128b5  jnz     short loc_1400128E1
0x1400128b7  mov     dword ptr [rax-10h], 80004003h
0x1400128be  lea     rax, aPersistrequest; "PersistRequestRAObjectUntilConsumed"
0x1400128c5  mov     [rsp+38h+ppv], rax; unsigned __int16 *
0x1400128ca  mov     r9d, 4E3h; unsigned int
0x1400128d0  lea     r8, aBaseDiagnosisR_0; "base\\diagnosis\\ra\\dcom\\src\\raimreq"...
0x1400128d7  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400128dc  jmp     loc_140012A5A
0x1400128e1  cmp     qword ptr [rcx], 0
0x1400128e5  jnz     short loc_140012916
0x1400128e7  mov     [rsp+38h+var_10], 80004003h; unsigned int
0x1400128ef  lea     rax, aPersistrequest; "PersistRequestRAObjectUntilConsumed"
0x1400128f6  mov     [rsp+38h+ppv], rax; unsigned __int16 *
0x1400128fb  mov     r9d, 4E4h; unsigned int
0x140012901  lea     r8, aBaseDiagnosisR_0; "base\\diagnosis\\ra\\dcom\\src\\raimreq"...
0x140012908  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14001290d  lea     rbx, [rdi+8]
0x140012911  jmp     loc_140012A1B
0x140012916  lea     rbx, [rcx+8]
0x14001291a  cmp     qword ptr [rbx], 0
0x14001291e  jnz     short loc_140012933
0x140012920  mov     [rsp+38h+var_10], 80004003h
0x140012928  mov     r9d, 4E5h
0x14001292e  jmp     loc_140012A03
0x140012933  lea     rax, [rsp+38h+arg_8]
0x140012938  mov     [rsp+38h+ppv], rax; ppv
0x14001293d  lea     r9, _GUID_59308e66_7cde_478a_8eba_4d73fdce3545; riid
0x140012944  xor     edx, edx; pUnkOuter
0x140012946  lea     r8d, [rdx+4]; dwClsContext
0x14001294a  lea     rcx, CLSID_RemoteAssistance; rclsid
0x140012951  call    cs:__imp_CoCreateInstance
0x140012957  mov     esi, eax
0x140012959  test    eax, eax
0x14001295b  jns     short loc_140012971
0x14001295d  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,ushort *)
0x140012962  mov     [rsp+38h+var_10], esi
0x140012966  mov     r9d, 4F2h
0x14001296c  jmp     loc_140012A03
0x140012971  mov     rcx, [rsp+38h+arg_8]
0x140012976  mov     rax, [rcx]
0x140012979  mov     rdx, [rdi]
0x14001297c  mov     rax, [rax+48h]
0x140012980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012985  test    eax, eax
0x140012987  jns     short loc_140012991
0x140012989  mov     r9d, 4F9h
0x14001298f  jmp     short loc_1400129FF
0x140012991  mov     rcx, [rsp+38h+arg_8]
0x140012996  mov     rax, [rcx]
0x140012999  mov     rdx, [rbx]
0x14001299c  mov     rax, [rax+90h]
0x1400129a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400129a8  test    eax, eax
0x1400129aa  jns     short loc_1400129B4
0x1400129ac  mov     r9d, 4FFh
0x1400129b2  jmp     short loc_1400129FF
0x1400129b4  mov     rcx, [rsp+38h+arg_8]
0x1400129b9  mov     rax, [rcx]
0x1400129bc  xor     r9d, r9d
0x1400129bf  mov     r8, [rdi]
0x1400129c2  xor     edx, edx
0x1400129c4  mov     rax, [rax+50h]
0x1400129c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400129cd  test    eax, eax
0x1400129cf  jns     short loc_1400129D9
0x1400129d1  mov     r9d, 505h
0x1400129d7  jmp     short loc_1400129FF
0x1400129d9  mov     rcx, [rsp+38h+arg_8]
0x1400129de  mov     rax, [rcx]
0x1400129e1  xor     r8d, r8d
0x1400129e4  lea     rdx, [rsp+38h+arg_0]
0x1400129e9  mov     rax, [rax+60h]
0x1400129ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400129f2  cmp     [rsp+38h+arg_0], 0
0x1400129f7  jnz     short loc_140012A1B
0x1400129f9  mov     r9d, 50Eh; unsigned int
0x1400129ff  mov     [rsp+38h+var_10], eax; unsigned int
0x140012a03  lea     rax, aPersistrequest; "PersistRequestRAObjectUntilConsumed"
0x140012a0a  mov     [rsp+38h+ppv], rax; unsigned __int16 *
0x140012a0f  lea     r8, aBaseDiagnosisR_0; "base\\diagnosis\\ra\\dcom\\src\\raimreq"...
0x140012a16  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140012a1b  mov     rcx, [rdi]; bstrString
0x140012a1e  test    rcx, rcx
0x140012a21  jz      short loc_140012A30
0x140012a23  call    cs:__imp_SysFreeString
0x140012a29  mov     qword ptr [rdi], 0
0x140012a30  mov     rcx, [rbx]; bstrString
0x140012a33  test    rcx, rcx
0x140012a36  jz      short loc_140012A45
0x140012a38  call    cs:__imp_SysFreeString
0x140012a3e  mov     qword ptr [rbx], 0
0x140012a45  call    cs:__imp_GetProcessHeap
0x140012a4b  mov     rcx, rax; hHeap
0x140012a4e  mov     r8, rdi; lpMem
0x140012a51  xor     edx, edx; dwFlags
0x140012a53  call    cs:__imp_HeapFree
0x140012a59  nop
0x140012a5a  lea     rcx, [rsp+38h+arg_8]
0x140012a5f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140012a64  xor     eax, eax
0x140012a66  mov     rbx, [rsp+38h+arg_10]
0x140012a6b  mov     rsi, [rsp+38h+arg_18]
0x140012a70  add     rsp, 30h
0x140012a74  pop     rdi
0x140012a75  retn
```
