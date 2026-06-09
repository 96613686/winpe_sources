# CRemoteAssistance::WaitForTicket(int *,int)

- ea: `0x14000efc0`
- end: `0x14000f0a7`
- name: `?WaitForTicket@CRemoteAssistance@@UEAAJPEAHH@Z`
- size: `231`
- prototype: `__int64 __fastcall(CRemoteAssistance *__hidden this, int *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000e664`
- `0x14000e6fc`
- `0x14000efc0`
- `0x140015240`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000f06a`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f06a`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x14000f037`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x14000f037`

## string_xrefs

- `0x14000f00d`: `base\diagnosis\ra\dcom\src\remoteassistance.cpp`
- `0x14000f08d`: `base\diagnosis\ra\dcom\src\remoteassistance.cpp`

## pseudocode

```c
__int64 __fastcall CRemoteAssistance::WaitForTicket(CRemoteAssistance *this, int *a2, int a3)
{
  __int64 v4; // rdx
  const struct _EVENT_DESCRIPTOR *v7; // rdx
  CEventLogger *v8; // rcx
  unsigned int v9; // edi
  BOOL v10; // ebx
  int v11; // ecx
  BSTR bstrString; // [rsp+50h] [rbp+8h] BYREF
  HANDLE pHandles; // [rsp+58h] [rbp+10h] BYREF
  DWORD dwindex; // [rsp+60h] [rbp+18h] BYREF

  dwindex = 0;
  v4 = 0xFFFFFFFFLL;
  if ( a3 != 1 )
    v4 = 120000;
  pHandles = (HANDLE)*((_QWORD *)this + 10);
  if ( a2 )
  {
    v9 = CoWaitForMultipleHandles(1u, v4, 1u, &pHandles, &dwindex);
    if ( v9 )
    {
      CEventLogger::LogError(
        v8,
        v7,
        L"base\\diagnosis\\ra\\dcom\\src\\remoteassistance.cpp",
        0x270u,
        L"CRemoteAssistance::WaitForTicket",
        v9);
      v11 = 0;
    }
    else
    {
      ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, &Class);
      v10 = ATL::CComBSTR::operator==((BSTR *)this + 8, &bstrString);
      SysFreeString(bstrString);
      v11 = !v10;
    }
    *a2 = v11;
    return v9;
  }
  else
  {
    CEventLogger::LogError(
      this,
      (const struct _EVENT_DESCRIPTOR *)v4,
      L"base\\diagnosis\\ra\\dcom\\src\\remoteassistance.cpp",
      0x254u,
      L"CRemoteAssistance::WaitForTicket",
      0x80004003);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x14000efc0  push    rbx
0x14000efc2  push    rsi
0x14000efc3  push    rdi
0x14000efc4  sub     rsp, 30h
0x14000efc8  mov     rsi, rdx
0x14000efcb  mov     [rsp+48h+dwindex], 0
0x14000efd3  or      edx, 0FFFFFFFFh
0x14000efd6  mov     eax, 1D4C0h
0x14000efdb  cmp     r8d, 1
0x14000efdf  mov     rbx, rcx
0x14000efe2  cmovnz  edx, eax; struct _EVENT_DESCRIPTOR *
0x14000efe5  mov     rax, [rcx+50h]
0x14000efe9  mov     [rsp+48h+pHandles], rax
0x14000efee  test    rsi, rsi
0x14000eff1  jnz     short loc_14000F020
0x14000eff3  lea     rax, aCremoteassista_0; "CRemoteAssistance::WaitForTicket"
0x14000effa  mov     [rsp+48h+var_20], 80004003h; unsigned int
0x14000f002  mov     r9d, 254h; unsigned int
0x14000f008  mov     [rsp+48h+lpdwindex], rax; unsigned __int16 *
0x14000f00d  lea     r8, aBaseDiagnosisR_6; "base\\diagnosis\\ra\\dcom\\src\\remotea"...
0x14000f014  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000f019  mov     eax, 80004003h
0x14000f01e  jmp     short loc_14000F09F
0x14000f020  mov     ecx, 1; dwFlags
0x14000f025  lea     rax, [rsp+48h+dwindex]
0x14000f02a  mov     r8d, ecx; cHandles
0x14000f02d  mov     [rsp+48h+lpdwindex], rax; lpdwindex
0x14000f032  lea     r9, [rsp+48h+pHandles]; pHandles
0x14000f037  call    cs:__imp_CoWaitForMultipleHandles
0x14000f03d  mov     edi, eax
0x14000f03f  test    eax, eax
0x14000f041  jnz     short loc_14000F077
0x14000f043  lea     rdx, Class; unsigned __int16 *
0x14000f04a  lea     rcx, [rsp+48h+bstrString]; this
0x14000f04f  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x14000f054  lea     rcx, [rbx+40h]
0x14000f058  lea     rdx, [rsp+48h+bstrString]
0x14000f05d  call    ??8CComBSTR@ATL@@QEBA_NAEBV01@@Z; ATL::CComBSTR::operator==(ATL::CComBSTR const &)
0x14000f062  mov     rcx, [rsp+48h+bstrString]; bstrString
0x14000f067  movzx   ebx, al
0x14000f06a  call    cs:__imp_SysFreeString
0x14000f070  mov     ecx, ebx
0x14000f072  xor     ecx, 1
0x14000f075  jmp     short loc_14000F09B
0x14000f077  lea     rax, aCremoteassista_0; "CRemoteAssistance::WaitForTicket"
0x14000f07e  mov     [rsp+48h+var_20], edi; unsigned int
0x14000f082  mov     r9d, 270h; unsigned int
0x14000f088  mov     [rsp+48h+lpdwindex], rax; unsigned __int16 *
0x14000f08d  lea     r8, aBaseDiagnosisR_6; "base\\diagnosis\\ra\\dcom\\src\\remotea"...
0x14000f094  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000f099  xor     ecx, ecx
0x14000f09b  mov     [rsi], ecx
0x14000f09d  mov     eax, edi
0x14000f09f  add     rsp, 30h
0x14000f0a3  pop     rdi
0x14000f0a4  pop     rsi
0x14000f0a5  pop     rbx
0x14000f0a6  retn
```
