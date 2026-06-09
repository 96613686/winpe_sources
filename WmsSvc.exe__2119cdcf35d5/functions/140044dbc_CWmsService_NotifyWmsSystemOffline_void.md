# CWmsService::NotifyWmsSystemOffline(void)

- ea: `0x140044dbc`
- end: `0x140044f8d`
- name: `?NotifyWmsSystemOffline@CWmsService@@AEAAJXZ`
- size: `465`
- prototype: `__int64 __fastcall(CWmsService *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x140045180`
- `0x140045500`

## callees

- `0x140044940`
- `0x140044dbc`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007cb9e`
- `0x14007cbd0`
- `0x14007e010`

## import_xrefs

- `KERNEL32!GetComputerNameExW` at `0x140044e31`
- `KERNEL32!GetComputerNameExW` at `0x140044e31`
- `KERNEL32!GetLastError` at `0x140044e3b`
- `KERNEL32!GetLastError` at `0x140044e3b`
- `KERNEL32!IsDebuggerPresent` at `0x140044efd`
- `KERNEL32!IsDebuggerPresent` at `0x140044efd`
- `OLEAUT32!__imp_SysAllocString` at `0x140044e75`
- `OLEAUT32!__imp_SysAllocString` at `0x140044e75`
- `OLEAUT32!__imp_SysFreeString` at `0x140044f59`
- `OLEAUT32!__imp_SysFreeString` at `0x140044f59`

## string_xrefs

- `0x140044ee0`: `termsrv\wms\src\devices\wmssvc\wmsservice.cpp`
- `0x140044dfc`: `CWmsService::NotifyWmsSystemOffline\n`
- `0x140044ed5`: `CWmsService::NotifyWmsSystemOffline`
- `0x140044e88`: `bstrComputerName`

## pseudocode

```c
__int64 __fastcall CWmsService::NotifyWmsSystemOffline(CWmsService *this)
{
  OLECHAR *v2; // rbp
  __int64 v3; // rdx
  __int64 v4; // r8
  const unsigned __int16 *v5; // r9
  int SvcEventSink; // ebx
  signed int LastError; // eax
  const unsigned __int16 *v8; // r15
  const unsigned __int16 *v9; // r12
  unsigned int v10; // r14d
  BSTR v11; // rax
  DWORD nSize[4]; // [rsp+40h] [rbp-248h] BYREF
  WCHAR Buffer[256]; // [rsp+50h] [rbp-238h] BYREF

  memset_0(Buffer, 0, sizeof(Buffer));
  nSize[0] = 256;
  v2 = 0;
  DEBUGMSG(L"CWmsService::NotifyWmsSystemOffline\n");
  SvcEventSink = CWmsService::CreateSvcEventSink(this, v3, v4, v5);
  if ( SvcEventSink >= 0 )
  {
    if ( GetComputerNameExW(ComputerNameDnsFullyQualified, Buffer, nSize) )
    {
      v11 = SysAllocString(Buffer);
      v2 = v11;
      if ( v11 )
      {
        SvcEventSink = (*(__int64 (__fastcall **)(_QWORD, BSTR))(**((_QWORD **)this + 145) + 216LL))(
                         *((_QWORD *)this + 145),
                         v11);
        if ( SvcEventSink >= 0 )
          goto LABEL_15;
        v8 = L"hr";
        v10 = 531;
        v9 = L"CHRA";
      }
      else
      {
        SvcEventSink = -2147024882;
        v8 = L"bstrComputerName";
        v9 = L"CPR";
        v10 = 528;
      }
    }
    else
    {
      LastError = GetLastError();
      SvcEventSink = LastError;
      if ( LastError > 0 )
        SvcEventSink = (unsigned __int16)LastError | 0x80070000;
      v8 = L"dwRet";
      v9 = L"CBRAEx";
      if ( SvcEventSink >= 0 )
        SvcEventSink = -2147467259;
      v10 = 525;
    }
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmsservice.cpp",
      v10,
      L"CWmsService::NotifyWmsSystemOffline",
      v9,
      v8,
      SvcEventSink);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmsservice.cpp",
        v10,
        L"CWmsService::NotifyWmsSystemOffline",
        v9,
        v8,
        SvcEventSink);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmsservice.cpp",
        v10,
        L"CWmsService::NotifyWmsSystemOffline",
        v9,
        v8,
        SvcEventSink);
  }
LABEL_15:
  SysFreeString(v2);
  return (unsigned int)SvcEventSink;
}

```

## disassembly

```asm
0x140044dbc  mov     [rsp+arg_8], rbx
0x140044dc1  mov     [rsp+arg_10], rbp
0x140044dc6  push    rsi
0x140044dc7  push    rdi
0x140044dc8  push    r12
0x140044dca  push    r14
0x140044dcc  push    r15
0x140044dce  sub     rsp, 260h
0x140044dd5  mov     rax, cs:__security_cookie
0x140044ddc  xor     rax, rsp
0x140044ddf  mov     [rsp+288h+var_38], rax
0x140044de7  mov     rdi, rcx
0x140044dea  xor     edx, edx; Val
0x140044dec  lea     rcx, [rsp+288h+Buffer]; void *
0x140044df1  mov     r8d, 200h; Size
0x140044df7  call    memset_0
0x140044dfc  lea     rcx, aCwmsserviceNot; "CWmsService::NotifyWmsSystemOffline\n"
0x140044e03  mov     [rsp+288h+nSize], 100h
0x140044e0b  xor     ebp, ebp
0x140044e0d  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140044e12  mov     rcx, rdi; this
0x140044e15  call    ?CreateSvcEventSink@CWmsService@@AEAAJXZ; CWmsService::CreateSvcEventSink(void)
0x140044e1a  mov     ebx, eax
0x140044e1c  test    eax, eax
0x140044e1e  js      loc_140044F56
0x140044e24  lea     r8, [rsp+288h+nSize]; nSize
0x140044e29  lea     rdx, [rsp+288h+Buffer]; lpBuffer
0x140044e2e  lea     ecx, [rbp+3]; NameType
0x140044e31  call    cs:__imp_GetComputerNameExW
0x140044e37  test    eax, eax
0x140044e39  jnz     short loc_140044E70
0x140044e3b  call    cs:__imp_GetLastError
0x140044e41  mov     ebx, eax
0x140044e43  test    eax, eax
0x140044e45  jle     short loc_140044E50
0x140044e47  movzx   ebx, ax
0x140044e4a  or      ebx, 80070000h
0x140044e50  test    ebx, ebx
0x140044e52  lea     r15, aDwret; "dwRet"
0x140044e59  mov     eax, 80004005h
0x140044e5e  lea     r12, aCbraex; "CBRAEx"
0x140044e65  cmovns  ebx, eax
0x140044e68  mov     r14d, 20Dh
0x140044e6e  jmp     short loc_140044ED5
0x140044e70  lea     rcx, [rsp+288h+Buffer]; psz
0x140044e75  call    cs:__imp_SysAllocString
0x140044e7b  mov     rbp, rax
0x140044e7e  test    rax, rax
0x140044e81  jnz     short loc_140044E9E
0x140044e83  mov     ebx, 8007000Eh
0x140044e88  lea     r15, aBstrcomputerna; "bstrComputerName"
0x140044e8f  lea     r12, aCpr; "CPR"
0x140044e96  mov     r14d, 210h
0x140044e9c  jmp     short loc_140044ED5
0x140044e9e  mov     rcx, [rdi+488h]
0x140044ea5  mov     rdx, rbp
0x140044ea8  mov     rax, [rcx]
0x140044eab  mov     rax, [rax+0D8h]
0x140044eb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044eb7  mov     ebx, eax
0x140044eb9  test    eax, eax
0x140044ebb  jns     loc_140044F56
0x140044ec1  lea     r15, aHr; "hr"
0x140044ec8  mov     r14d, 213h
0x140044ece  lea     r12, aChra; "CHRA"
0x140044ed5  lea     rsi, aCwmsserviceNot_0; "CWmsService::NotifyWmsSystemOffline"
0x140044edc  mov     [rsp+288h+var_260], ebx; int
0x140044ee0  lea     rdi, aTermsrvWmsSrcD_6; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140044ee7  mov     [rsp+288h+var_268], r15; unsigned __int16 *
0x140044eec  mov     r8, rsi; unsigned __int16 *
0x140044eef  mov     rcx, rdi; unsigned __int16 *
0x140044ef2  mov     r9, r12; unsigned __int16 *
0x140044ef5  mov     edx, r14d; unsigned int
0x140044ef8  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140044efd  call    cs:__imp_IsDebuggerPresent
0x140044f03  test    eax, eax
0x140044f05  jz      short loc_140044F33
0x140044f07  mov     [rsp+288h+var_250], ebx
0x140044f0b  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140044f12  mov     [rsp+288h+var_258], r15
0x140044f17  mov     r9d, r14d
0x140044f1a  mov     qword ptr [rsp+288h+var_260], r12
0x140044f1f  mov     r8, rdi
0x140044f22  mov     ecx, 2; unsigned __int8
0x140044f27  mov     [rsp+288h+var_268], rsi
0x140044f2c  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140044f31  jmp     short loc_140044F56
0x140044f33  mov     dword ptr [rsp+288h+var_258], ebx
0x140044f37  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140044f3e  mov     qword ptr [rsp+288h+var_260], r15
0x140044f43  mov     r9, rsi
0x140044f46  mov     r8d, r14d
0x140044f49  mov     [rsp+288h+var_268], r12
0x140044f4e  mov     rdx, rdi
0x140044f51  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140044f56  mov     rcx, rbp; bstrString
0x140044f59  call    cs:__imp_SysFreeString
0x140044f5f  mov     eax, ebx
0x140044f61  mov     rcx, [rsp+288h+var_38]
0x140044f69  xor     rcx, rsp; StackCookie
0x140044f6c  call    __security_check_cookie
0x140044f71  lea     r11, [rsp+288h+var_28]
0x140044f79  mov     rbx, [r11+38h]
0x140044f7d  mov     rbp, [r11+40h]
0x140044f81  mov     rsp, r11
0x140044f84  pop     r15
0x140044f86  pop     r14
0x140044f88  pop     r12
0x140044f8a  pop     rdi
0x140044f8b  pop     rsi
0x140044f8c  retn
```
