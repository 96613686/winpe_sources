# CIMRequestRAEvent::SendExpertRevConnString(ushort *)

- ea: `0x140014ccc`
- end: `0x140014f09`
- name: `?SendExpertRevConnString@CIMRequestRAEvent@@QEAAJPEAG@Z`
- size: `573`
- prototype: `__int64 __fastcall(const struct _EVENT_DESCRIPTOR **this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140011fc0`

## callees

- `0x1400022d3`
- `0x140004f54`
- `0x14000aafc`
- `0x14000e6a0`
- `0x140011b74`
- `0x14001398c`
- `0x140014388`
- `0x140014508`
- `0x140014ccc`
- `0x140015240`
- `0x140015aa0`
- `0x140017010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140014ece`
- `OLEAUT32!__imp_SysFreeString` at `0x140014eda`
- `OLEAUT32!__imp_SysFreeString` at `0x140014ece`
- `OLEAUT32!__imp_SysFreeString` at `0x140014eda`

## string_xrefs

- `0x140014ebc`: `base\diagnosis\ra\dcom\src\publickeyexch.cpp`

## pseudocode

```c
__int64 __fastcall CIMRequestRAEvent::SendExpertRevConnString(
        const struct _EVENT_DESCRIPTOR **this,
        unsigned __int16 *a2)
{
  signed int inited; // eax
  const struct _EVENT_DESCRIPTOR *v5; // rdx
  CIMRequestRAEvent *v6; // rcx
  unsigned int v7; // ebx
  signed int KeyExportString; // eax
  const struct _EVENT_DESCRIPTOR *v9; // rdx
  CEventLogger *v10; // rcx
  unsigned __int64 v11; // r9
  signed int v12; // eax
  const struct _EVENT_DESCRIPTOR *v13; // rdx
  CEventLogger *v14; // rcx
  const struct _EVENT_DESCRIPTOR *v15; // rdx
  signed int v16; // eax
  const struct _EVENT_DESCRIPTOR *v17; // rdx
  CEventLogger *v18; // rcx
  signed int v19; // eax
  const struct _EVENT_DESCRIPTOR *v20; // rdx
  CEventLogger *v21; // rcx
  signed int appended; // eax
  const struct _EVENT_DESCRIPTOR *v23; // rcx
  signed int v24; // eax
  const struct _EVENT_DESCRIPTOR *v25; // rdx
  CEventLogger *v26; // rcx
  BSTR bstrString; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v29; // [rsp+38h] [rbp-C8h] BYREF
  BSTR v30; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v31[264]; // [rsp+50h] [rbp-B0h] BYREF

  v30 = 0;
  bstrString = 0;
  v29 = 0;
  memset_0(v31, 0, 0x208u);
  inited = CIMRequestRAEvent::InitCSP((CIMRequestRAEvent *)this, 1);
  v7 = inited;
  if ( inited >= 0 )
  {
    KeyExportString = CIMRequestRAEvent::GetKeyExportString(v6, this[8], 0, 6u, &v30, &v29);
    v7 = KeyExportString;
    if ( KeyExportString >= 0 )
    {
      v11 = -1;
      do
        ++v11;
      while ( a2[v11] );
      if ( v11 > 0xFFFFFFFF )
      {
        v7 = -2147024362;
        CEventLogger::LogError(
          v10,
          v9,
          L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
          0xB1u,
          L"CIMRequestRAEvent::SendExpertRevConnString",
          0x80070216);
        goto LABEL_22;
      }
      v12 = StringCchPrintfW(v31, 0x104u, L"%d;ET=", (unsigned int)(v11 + 3));
      v7 = v12;
      if ( v12 >= 0 )
      {
        ATL::CComBSTR::operator=(&bstrString, v31);
        ATL::CComBSTR::AppendBSTR(&bstrString, a2);
        if ( v29 )
        {
          v16 = StringCchPrintfW(v31, 0x104u, L"%d;PK=", v29 + 3);
          v7 = v16;
          if ( v16 < 0 )
          {
            CEventLogger::LogError(
              v18,
              v17,
              L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
              0xC9u,
              L"CIMRequestRAEvent::SendExpertRevConnString",
              v16);
            goto LABEL_22;
          }
          v19 = ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrString, v31);
          v7 = v19;
          if ( v19 < 0 )
          {
            CEventLogger::LogError(
              v21,
              v20,
              L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
              0xCDu,
              L"CIMRequestRAEvent::SendExpertRevConnString",
              v19);
            goto LABEL_22;
          }
          appended = ATL::CComBSTR::AppendBSTR(&bstrString, v30);
          if ( appended < 0 )
            ATL::AtlThrowImpl(appended);
        }
        v23 = this[1];
        if ( v23 )
        {
          v24 = (*(__int64 (__fastcall **)(const struct _EVENT_DESCRIPTOR *, BSTR))(*(_QWORD *)&v23->Id + 56LL))(
                  v23,
                  bstrString);
          v7 = v24;
          if ( v24 < 0 )
            CEventLogger::LogError(
              v26,
              v25,
              L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
              0xD9u,
              L"CIMRequestRAEvent::SendExpertRevConnString",
              v24);
        }
        else
        {
          v7 = -2147467261;
          CEventLogger::LogError(
            0,
            v15,
            L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
            0xDEu,
            L"CIMRequestRAEvent::SendExpertRevConnString",
            0x80004003);
        }
      }
      else
      {
        CEventLogger::LogError(
          v14,
          v13,
          L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
          0xBBu,
          L"CIMRequestRAEvent::SendExpertRevConnString",
          v12);
      }
    }
    else
    {
      CEventLogger::LogError(
        v10,
        v9,
        L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
        0xABu,
        L"CIMRequestRAEvent::SendExpertRevConnString",
        KeyExportString);
    }
  }
  else
  {
    CEventLogger::LogError(
      v6,
      v5,
      L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
      0x9Eu,
      L"CIMRequestRAEvent::SendExpertRevConnString",
      inited);
  }
LABEL_22:
  SysFreeString(bstrString);
  SysFreeString(v30);
  return v7;
}

```

## disassembly

```asm
0x140014ccc  mov     [rsp-8+arg_10], rbx
0x140014cd1  mov     [rsp-8+arg_18], rsi
0x140014cd6  push    rbp
0x140014cd7  push    rdi
0x140014cd8  push    r14
0x140014cda  lea     rbp, [rsp-170h]
0x140014ce2  sub     rsp, 270h
0x140014ce9  mov     rax, cs:__security_cookie
0x140014cf0  xor     rax, rsp
0x140014cf3  mov     [rbp+180h+var_20], rax
0x140014cfa  mov     rsi, rdx
0x140014cfd  mov     rdi, rcx
0x140014d00  xor     r14d, r14d
0x140014d03  mov     [rsp+280h+var_240], r14
0x140014d08  mov     [rsp+280h+bstrString], r14
0x140014d0d  mov     [rsp+280h+var_248], r14d
0x140014d12  xor     edx, edx; Val
0x140014d14  mov     r8d, 208h; Size
0x140014d1a  lea     rcx, [rsp+280h+var_230]; void *
0x140014d1f  call    memset_0
0x140014d24  lea     edx, [r14+1]; int
0x140014d28  mov     rcx, rdi; this
0x140014d2b  call    ?InitCSP@CIMRequestRAEvent@@QEAAJH@Z; CIMRequestRAEvent::InitCSP(int)
0x140014d30  mov     ebx, eax
0x140014d32  test    eax, eax
0x140014d34  jns     short loc_140014D45
0x140014d36  mov     dword ptr [rsp+280h+var_258], eax
0x140014d3a  mov     r9d, 9Eh
0x140014d40  jmp     loc_140014EB0
0x140014d45  lea     rax, [rsp+280h+var_248]
0x140014d4a  mov     [rsp+280h+var_258], rax; unsigned int *
0x140014d4f  lea     rax, [rsp+280h+var_240]
0x140014d54  mov     [rsp+280h+var_260], rax; unsigned __int16 **
0x140014d59  mov     r9d, 6; unsigned int
0x140014d5f  xor     r8d, r8d; unsigned __int64
0x140014d62  mov     rdx, [rdi+40h]; unsigned __int64
0x140014d66  call    ?GetKeyExportString@CIMRequestRAEvent@@QEAAJ_K0KPEAPEAGPEAK@Z; CIMRequestRAEvent::GetKeyExportString(unsigned __int64,unsigned __int64,ulong,ushort * *,ulong *)
0x140014d6b  mov     ebx, eax
0x140014d6d  test    eax, eax
0x140014d6f  jns     short loc_140014D80
0x140014d71  mov     dword ptr [rsp+280h+var_258], eax
0x140014d75  mov     r9d, 0ABh
0x140014d7b  jmp     loc_140014EB0
0x140014d80  or      r9, 0FFFFFFFFFFFFFFFFh
0x140014d84  inc     r9
0x140014d87  cmp     [rsi+r9*2], r14w
0x140014d8c  jnz     short loc_140014D84
0x140014d8e  mov     eax, 0FFFFFFFFh
0x140014d93  cmp     r9, rax
0x140014d96  ja      loc_140014E9D
0x140014d9c  add     r9d, 3
0x140014da0  lea     r8, aDEt; "%d;ET="
0x140014da7  mov     edx, 104h; unsigned __int64
0x140014dac  lea     rcx, [rsp+280h+var_230]; unsigned __int16 *
0x140014db1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140014db6  mov     ebx, eax
0x140014db8  test    eax, eax
0x140014dba  jns     short loc_140014DCB
0x140014dbc  mov     dword ptr [rsp+280h+var_258], eax
0x140014dc0  mov     r9d, 0BBh
0x140014dc6  jmp     loc_140014EB0
0x140014dcb  lea     rdx, [rsp+280h+var_230]
0x140014dd0  lea     rcx, [rsp+280h+bstrString]
0x140014dd5  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x140014dda  mov     rdx, rsi; unsigned __int16 *
0x140014ddd  lea     rcx, [rsp+280h+bstrString]; this
0x140014de2  call    ?AppendBSTR@CComBSTR@ATL@@QEAAJPEAG@Z; ATL::CComBSTR::AppendBSTR(ushort *)
0x140014de7  mov     r9d, [rsp+280h+var_248]
0x140014dec  test    r9d, r9d
0x140014def  jz      short loc_140014E5C
0x140014df1  add     r9d, 3
0x140014df5  lea     r8, aDPk; "%d;PK="
0x140014dfc  mov     edx, 104h; unsigned __int64
0x140014e01  lea     rcx, [rsp+280h+var_230]; unsigned __int16 *
0x140014e06  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140014e0b  mov     ebx, eax
0x140014e0d  test    eax, eax
0x140014e0f  jns     short loc_140014E20
0x140014e11  mov     dword ptr [rsp+280h+var_258], eax
0x140014e15  mov     r9d, 0C9h
0x140014e1b  jmp     loc_140014EB0
0x140014e20  lea     rdx, [rsp+280h+var_230]; unsigned __int16 *
0x140014e25  lea     rcx, [rsp+280h+bstrString]; this
0x140014e2a  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x140014e2f  mov     ebx, eax
0x140014e31  test    eax, eax
0x140014e33  jns     short loc_140014E41
0x140014e35  mov     dword ptr [rsp+280h+var_258], eax
0x140014e39  mov     r9d, 0CDh
0x140014e3f  jmp     short loc_140014EB0
0x140014e41  mov     rdx, [rsp+280h+var_240]; unsigned __int16 *
0x140014e46  lea     rcx, [rsp+280h+bstrString]; this
0x140014e4b  call    ?AppendBSTR@CComBSTR@ATL@@QEAAJPEAG@Z; ATL::CComBSTR::AppendBSTR(ushort *)
0x140014e50  test    eax, eax
0x140014e52  jns     short loc_140014E5C
0x140014e54  mov     ecx, eax; int
0x140014e56  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140014e5c  mov     rcx, [rdi+8]
0x140014e60  test    rcx, rcx
0x140014e63  jz      short loc_140014E88
0x140014e65  mov     rax, [rcx]
0x140014e68  mov     rdx, [rsp+280h+bstrString]
0x140014e6d  mov     rax, [rax+38h]
0x140014e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014e76  mov     ebx, eax
0x140014e78  test    eax, eax
0x140014e7a  jns     short loc_140014EC9
0x140014e7c  mov     dword ptr [rsp+280h+var_258], eax
0x140014e80  mov     r9d, 0D9h
0x140014e86  jmp     short loc_140014EB0
0x140014e88  mov     ebx, 80004003h
0x140014e8d  mov     dword ptr [rsp+280h+var_258], 80004003h
0x140014e95  mov     r9d, 0DEh
0x140014e9b  jmp     short loc_140014EB0
0x140014e9d  mov     ebx, 80070216h
0x140014ea2  mov     dword ptr [rsp+280h+var_258], 80070216h; unsigned int
0x140014eaa  mov     r9d, 0B1h; unsigned int
0x140014eb0  lea     rax, aCimrequestraev_1; "CIMRequestRAEvent::SendExpertRevConnStr"...
0x140014eb7  mov     [rsp+280h+var_260], rax; unsigned __int16 *
0x140014ebc  lea     r8, aBaseDiagnosisR; "base\\diagnosis\\ra\\dcom\\src\\publick"...
0x140014ec3  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140014ec8  nop
0x140014ec9  mov     rcx, [rsp+280h+bstrString]; bstrString
0x140014ece  call    cs:__imp_SysFreeString
0x140014ed4  nop
0x140014ed5  mov     rcx, [rsp+280h+var_240]; bstrString
0x140014eda  call    cs:__imp_SysFreeString
0x140014ee0  mov     eax, ebx
0x140014ee2  mov     rcx, [rbp+180h+var_20]
0x140014ee9  xor     rcx, rsp; StackCookie
0x140014eec  call    __security_check_cookie
0x140014ef1  lea     r11, [rsp+280h+var_10]
0x140014ef9  mov     rbx, [r11+30h]
0x140014efd  mov     rsi, [r11+38h]
0x140014f01  mov     rsp, r11
0x140014f04  pop     r14
0x140014f06  pop     rdi
0x140014f07  pop     rbp
0x140014f08  retn
```
