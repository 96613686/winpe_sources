# PersistOfferRAObjectUntilConsumed(void *)

- ea: `0x140013760`
- end: `0x140013948`
- name: `?PersistOfferRAObjectUntilConsumed@@YAKPEAX@Z`
- size: `488`
- prototype: `__int64 __fastcall(CEventLogger *lpThreadParameter, const struct _EVENT_DESCRIPTOR *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400035c8`
- `0x140013760`
- `0x140015240`
- `0x1400154b0`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140013917`
- `KERNEL32!GetProcessHeap` at `0x140013917`
- `KERNEL32!HeapFree` at `0x140013925`
- `KERNEL32!HeapFree` at `0x140013925`
- `OLEAUT32!__imp_SysFreeString` at `0x1400138f5`
- `OLEAUT32!__imp_SysFreeString` at `0x14001390a`
- `OLEAUT32!__imp_SysFreeString` at `0x1400138f5`
- `OLEAUT32!__imp_SysFreeString` at `0x14001390a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140013821`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140013821`

## string_xrefs

- `0x1400137a0`: `base\diagnosis\ra\dcom\src\raimofferevnt.cpp`
- `0x1400137d1`: `base\diagnosis\ra\dcom\src\raimofferevnt.cpp`
- `0x1400138e1`: `base\diagnosis\ra\dcom\src\raimofferevnt.cpp`

## pseudocode

```c
__int64 __fastcall PersistOfferRAObjectUntilConsumed(
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
      L"base\\diagnosis\\ra\\dcom\\src\\raimofferevnt.cpp",
      0x374u,
      L"PersistOfferRAObjectUntilConsumed",
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
            v10 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)ppv + 80LL))(
                    ppv,
                    1,
                    *(_QWORD *)lpThreadParameter);
            if ( v10 >= 0 )
            {
              v10 = (*(__int64 (__fastcall **)(LPVOID, int *, _QWORD))(*(_QWORD *)ppv + 96LL))(ppv, &v16, 0);
              if ( v16 )
                goto LABEL_18;
              v13 = 927;
            }
            else
            {
              v13 = 918;
            }
          }
          else
          {
            v13 = 912;
          }
        }
        else
        {
          v13 = 906;
        }
        CEventLogger::LogError(
          v12,
          v11,
          L"base\\diagnosis\\ra\\dcom\\src\\raimofferevnt.cpp",
          v13,
          L"PersistOfferRAObjectUntilConsumed",
          v10);
        goto LABEL_18;
      }
      CEventLogger::LogEvent(v5, v4, v7);
      CEventLogger::LogError(
        v9,
        v8,
        L"base\\diagnosis\\ra\\dcom\\src\\raimofferevnt.cpp",
        0x383u,
        L"PersistOfferRAObjectUntilConsumed",
        v6);
    }
    else
    {
      CEventLogger::LogError(
        lpThreadParameter,
        a2,
        L"base\\diagnosis\\ra\\dcom\\src\\raimofferevnt.cpp",
        0x376u,
        L"PersistOfferRAObjectUntilConsumed",
        0x80004003);
    }
  }
  else
  {
    CEventLogger::LogError(
      lpThreadParameter,
      a2,
      L"base\\diagnosis\\ra\\dcom\\src\\raimofferevnt.cpp",
      0x375u,
      L"PersistOfferRAObjectUntilConsumed",
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
0x140013760  mov     rax, rsp
0x140013763  mov     [rax+18h], rbx
0x140013767  mov     [rax+20h], rsi
0x14001376b  push    rdi
0x14001376c  sub     rsp, 30h
0x140013770  mov     rdi, rcx
0x140013773  mov     qword ptr [rax+10h], 0
0x14001377b  mov     dword ptr [rax+8], 0
0x140013782  test    rcx, rcx
0x140013785  jnz     short loc_1400137B1
0x140013787  mov     dword ptr [rax-10h], 80004003h
0x14001378e  lea     rax, aPersistofferra; "PersistOfferRAObjectUntilConsumed"
0x140013795  mov     [rsp+38h+ppv], rax; unsigned __int16 *
0x14001379a  mov     r9d, 374h; unsigned int
0x1400137a0  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\dcom\\src\\raimoff"...
0x1400137a7  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400137ac  jmp     loc_14001392C
0x1400137b1  cmp     qword ptr [rcx], 0
0x1400137b5  jnz     short loc_1400137E6
0x1400137b7  mov     [rsp+38h+var_10], 80004003h; unsigned int
0x1400137bf  lea     rax, aPersistofferra; "PersistOfferRAObjectUntilConsumed"
0x1400137c6  mov     [rsp+38h+ppv], rax; unsigned __int16 *
0x1400137cb  mov     r9d, 375h; unsigned int
0x1400137d1  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\dcom\\src\\raimoff"...
0x1400137d8  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400137dd  lea     rbx, [rdi+8]
0x1400137e1  jmp     loc_1400138ED
0x1400137e6  lea     rbx, [rcx+8]
0x1400137ea  cmp     qword ptr [rbx], 0
0x1400137ee  jnz     short loc_140013803
0x1400137f0  mov     [rsp+38h+var_10], 80004003h
0x1400137f8  mov     r9d, 376h
0x1400137fe  jmp     loc_1400138D5
0x140013803  lea     rax, [rsp+38h+arg_8]
0x140013808  mov     [rsp+38h+ppv], rax; ppv
0x14001380d  lea     r9, _GUID_59308e66_7cde_478a_8eba_4d73fdce3545; riid
0x140013814  xor     edx, edx; pUnkOuter
0x140013816  lea     r8d, [rdx+4]; dwClsContext
0x14001381a  lea     rcx, CLSID_RemoteAssistance; rclsid
0x140013821  call    cs:__imp_CoCreateInstance
0x140013827  mov     esi, eax
0x140013829  test    eax, eax
0x14001382b  jns     short loc_140013841
0x14001382d  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,ushort *)
0x140013832  mov     [rsp+38h+var_10], esi
0x140013836  mov     r9d, 383h
0x14001383c  jmp     loc_1400138D5
0x140013841  mov     rcx, [rsp+38h+arg_8]
0x140013846  mov     rax, [rcx]
0x140013849  mov     rdx, [rdi]
0x14001384c  mov     rax, [rax+48h]
0x140013850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013855  test    eax, eax
0x140013857  jns     short loc_140013861
0x140013859  mov     r9d, 38Ah
0x14001385f  jmp     short loc_1400138D1
0x140013861  mov     rcx, [rsp+38h+arg_8]
0x140013866  mov     rax, [rcx]
0x140013869  mov     rdx, [rbx]
0x14001386c  mov     rax, [rax+90h]
0x140013873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013878  test    eax, eax
0x14001387a  jns     short loc_140013884
0x14001387c  mov     r9d, 390h
0x140013882  jmp     short loc_1400138D1
0x140013884  mov     rcx, [rsp+38h+arg_8]
0x140013889  mov     rax, [rcx]
0x14001388c  xor     r9d, r9d
0x14001388f  mov     r8, [rdi]
0x140013892  lea     edx, [r9+1]
0x140013896  mov     rax, [rax+50h]
0x14001389a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001389f  test    eax, eax
0x1400138a1  jns     short loc_1400138AB
0x1400138a3  mov     r9d, 396h
0x1400138a9  jmp     short loc_1400138D1
0x1400138ab  mov     rcx, [rsp+38h+arg_8]
0x1400138b0  mov     rax, [rcx]
0x1400138b3  xor     r8d, r8d
0x1400138b6  lea     rdx, [rsp+38h+arg_0]
0x1400138bb  mov     rax, [rax+60h]
0x1400138bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400138c4  cmp     [rsp+38h+arg_0], 0
0x1400138c9  jnz     short loc_1400138ED
0x1400138cb  mov     r9d, 39Fh; unsigned int
0x1400138d1  mov     [rsp+38h+var_10], eax; unsigned int
0x1400138d5  lea     rax, aPersistofferra; "PersistOfferRAObjectUntilConsumed"
0x1400138dc  mov     [rsp+38h+ppv], rax; unsigned __int16 *
0x1400138e1  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\dcom\\src\\raimoff"...
0x1400138e8  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400138ed  mov     rcx, [rdi]; bstrString
0x1400138f0  test    rcx, rcx
0x1400138f3  jz      short loc_140013902
0x1400138f5  call    cs:__imp_SysFreeString
0x1400138fb  mov     qword ptr [rdi], 0
0x140013902  mov     rcx, [rbx]; bstrString
0x140013905  test    rcx, rcx
0x140013908  jz      short loc_140013917
0x14001390a  call    cs:__imp_SysFreeString
0x140013910  mov     qword ptr [rbx], 0
0x140013917  call    cs:__imp_GetProcessHeap
0x14001391d  mov     rcx, rax; hHeap
0x140013920  mov     r8, rdi; lpMem
0x140013923  xor     edx, edx; dwFlags
0x140013925  call    cs:__imp_HeapFree
0x14001392b  nop
0x14001392c  lea     rcx, [rsp+38h+arg_8]
0x140013931  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140013936  xor     eax, eax
0x140013938  mov     rbx, [rsp+38h+arg_10]
0x14001393d  mov     rsi, [rsp+38h+arg_18]
0x140013942  add     rsp, 30h
0x140013946  pop     rdi
0x140013947  retn
```
