# CIMRequestRAEvent::Notify(int)

- ea: `0x140014618`
- end: `0x140014738`
- name: `?Notify@CIMRequestRAEvent@@QEAAJH@Z`
- size: `288`
- prototype: `__int64 __fastcall(CIMRequestRAEvent *__hidden this, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140011fc0`

## callees

- `0x14000aafc`
- `0x14000e6a0`
- `0x140014618`
- `0x140015240`
- `0x140015aa0`
- `0x140017010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14001470b`
- `OLEAUT32!__imp_SysFreeString` at `0x14001470b`
- `OLEAUT32!__imp_SysStringLen` at `0x1400146a8`
- `OLEAUT32!__imp_SysStringLen` at `0x1400146a8`

## string_xrefs

- `0x1400146fb`: `base\diagnosis\ra\dcom\src\publickeyexch.cpp`

## pseudocode

```c
__int64 __fastcall CIMRequestRAEvent::Notify(CIMRequestRAEvent *this, int a2)
{
  int v2; // r8d
  OLECHAR *v4; // rbx
  int v5; // r9d
  signed int v6; // eax
  const struct _EVENT_DESCRIPTOR *v7; // rdx
  CEventLogger *v8; // rcx
  unsigned int v9; // edi
  const struct _EVENT_DESCRIPTOR *v10; // rdx
  __int64 v11; // rcx
  signed int v12; // eax
  const struct _EVENT_DESCRIPTOR *v13; // rdx
  CEventLogger *v14; // rcx
  int v16; // [rsp+20h] [rbp-248h]
  BSTR pbstr; // [rsp+30h] [rbp-238h] BYREF
  unsigned __int16 v18[264]; // [rsp+40h] [rbp-228h] BYREF

  v2 = a2;
  v4 = 0;
  pbstr = 0;
  v5 = 0;
  while ( a2 >= 1 )
  {
    ++v5;
    a2 /= 0xAu;
  }
  v16 = v2;
  v6 = StringCchPrintfW(v18, 0x104u, L"%d;NOTIFY=%d", (unsigned int)(v5 + 7), v16);
  v9 = v6;
  if ( v6 >= 0 )
  {
    ATL::CComBSTR::operator=(&pbstr, v18);
    v4 = pbstr;
    if ( SysStringLen(pbstr) )
    {
      v11 = *((_QWORD *)this + 1);
      if ( v11 )
      {
        v12 = (*(__int64 (__fastcall **)(__int64, OLECHAR *))(*(_QWORD *)v11 + 56LL))(v11, v4);
        v9 = v12;
        if ( v12 < 0 )
          CEventLogger::LogError(
            v14,
            v13,
            L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
            0x506u,
            L"CIMRequestRAEvent::Notify",
            v12);
      }
      else
      {
        v9 = -2147467261;
        CEventLogger::LogError(
          0,
          v10,
          L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
          0x50Bu,
          L"CIMRequestRAEvent::Notify",
          0x80004003);
      }
    }
  }
  else
  {
    CEventLogger::LogError(
      v8,
      v7,
      L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
      0x4FAu,
      L"CIMRequestRAEvent::Notify",
      v6);
  }
  SysFreeString(v4);
  return v9;
}

```

## disassembly

```asm
0x140014618  mov     [rsp+arg_10], rbx
0x14001461d  mov     [rsp+arg_18], rsi
0x140014622  push    rdi
0x140014623  sub     rsp, 260h
0x14001462a  mov     rax, cs:__security_cookie
0x140014631  xor     rax, rsp
0x140014634  mov     [rsp+268h+var_18], rax
0x14001463c  mov     r8d, edx
0x14001463f  mov     rsi, rcx
0x140014642  xor     ebx, ebx
0x140014644  mov     [rsp+268h+pbstr], rbx
0x140014649  xor     r9d, r9d
0x14001464c  jmp     short loc_14001465B
0x14001464e  inc     r9d
0x140014651  mov     eax, 0CCCCCCCDh
0x140014656  mul     edx
0x140014658  shr     edx, 3
0x14001465b  cmp     edx, 1
0x14001465e  jge     short loc_14001464E
0x140014660  add     r9d, 7
0x140014664  mov     dword ptr [rsp+268h+var_248], r8d
0x140014669  lea     r8, aDNotifyD; "%d;NOTIFY=%d"
0x140014670  mov     edx, 104h; unsigned __int64
0x140014675  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x14001467a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001467f  mov     edi, eax
0x140014681  test    eax, eax
0x140014683  jns     short loc_140014691
0x140014685  mov     [rsp+268h+var_240], eax
0x140014689  mov     r9d, 4FAh
0x14001468f  jmp     short loc_1400146EF
0x140014691  lea     rdx, [rsp+268h+var_228]
0x140014696  lea     rcx, [rsp+268h+pbstr]
0x14001469b  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x1400146a0  mov     rbx, [rsp+268h+pbstr]
0x1400146a5  mov     rcx, rbx; pbstr
0x1400146a8  call    cs:__imp_SysStringLen
0x1400146ae  test    eax, eax
0x1400146b0  jz      short loc_140014708
0x1400146b2  mov     rcx, [rsi+8]; this
0x1400146b6  test    rcx, rcx
0x1400146b9  jz      short loc_1400146DC
0x1400146bb  mov     rax, [rcx]
0x1400146be  mov     rdx, rbx
0x1400146c1  mov     rax, [rax+38h]
0x1400146c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400146ca  mov     edi, eax
0x1400146cc  test    eax, eax
0x1400146ce  jns     short loc_140014708
0x1400146d0  mov     [rsp+268h+var_240], eax
0x1400146d4  mov     r9d, 506h
0x1400146da  jmp     short loc_1400146EF
0x1400146dc  mov     edi, 80004003h
0x1400146e1  mov     [rsp+268h+var_240], 80004003h; unsigned int
0x1400146e9  mov     r9d, 50Bh; unsigned int
0x1400146ef  lea     rax, aCimrequestraev_10; "CIMRequestRAEvent::Notify"
0x1400146f6  mov     [rsp+268h+var_248], rax; unsigned __int16 *
0x1400146fb  lea     r8, aBaseDiagnosisR; "base\\diagnosis\\ra\\dcom\\src\\publick"...
0x140014702  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140014707  nop
0x140014708  mov     rcx, rbx; bstrString
0x14001470b  call    cs:__imp_SysFreeString
0x140014711  mov     eax, edi
0x140014713  mov     rcx, [rsp+268h+var_18]
0x14001471b  xor     rcx, rsp; StackCookie
0x14001471e  call    __security_check_cookie
0x140014723  lea     r11, [rsp+268h+var_8]
0x14001472b  mov     rbx, [r11+20h]
0x14001472f  mov     rsi, [r11+28h]
0x140014733  mov     rsp, r11
0x140014736  pop     rdi
0x140014737  retn
```
