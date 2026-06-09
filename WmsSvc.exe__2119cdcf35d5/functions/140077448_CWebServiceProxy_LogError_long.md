# CWebServiceProxy::LogError(long)

- ea: `0x140077448`
- end: `0x140077721`
- name: `?LogError@CWebServiceProxy@@QEAAXJ@Z`
- size: `729`
- prototype: `void __fastcall(CWebServiceProxy *__hidden this, int)`
- caller_count: `51`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140055bf0`
- `0x140055cf0`
- `0x140055db0`
- `0x140056040`
- `0x140056100`
- `0x140056240`
- `0x140056500`
- `0x140056650`
- `0x1400566e0`
- `0x140056770`
- `0x140056800`
- `0x140056890`
- `0x140056920`
- `0x1400569e0`
- `0x140056aa0`
- `0x140056b30`
- `0x140056bc0`
- `0x140056c50`
- `0x140056ce0`
- `0x140056d60`
- `0x140056e20`
- `0x140056f20`
- `0x140056fe0`
- `0x140057120`
- `0x1400571e0`
- `0x140057270`
- `0x140057390`
- `0x140057420`
- `0x1400574b0`
- `0x140057540`
- `0x1400575d0`
- `0x140057660`
- `0x1400576f0`
- `0x1400577b0`
- `0x140057870`
- `0x140057900`
- `0x140057990`
- `0x140057a20`
- `0x140057ae0`
- `0x140057ba0`
- `0x140057c60`
- `0x140057d60`
- `0x140057e60`
- `0x140057ed8`
- `0x140058260`
- `0x140058644`
- `0x1400588d8`
- `0x140058b04`
- `0x140058d10`
- `0x140058f24`

## callees

- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140065070`
- `0x140077448`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x14007752d`
- `KERNEL32!IsDebuggerPresent` at `0x1400776b7`
- `KERNEL32!IsDebuggerPresent` at `0x14007752d`
- `KERNEL32!IsDebuggerPresent` at `0x1400776b7`
- `OLEAUT32!__imp_SysFreeString` at `0x14007756b`
- `OLEAUT32!__imp_SysFreeString` at `0x140077574`
- `OLEAUT32!__imp_SysFreeString` at `0x14007757d`
- `OLEAUT32!__imp_SysFreeString` at `0x140077625`
- `OLEAUT32!__imp_SysFreeString` at `0x14007756b`
- `OLEAUT32!__imp_SysFreeString` at `0x140077574`
- `OLEAUT32!__imp_SysFreeString` at `0x14007757d`
- `OLEAUT32!__imp_SysFreeString` at `0x140077625`
- `webservices!WsGetErrorProperty` at `0x140077613`
- `webservices!WsGetErrorProperty` at `0x140077613`
- `webservices!WsGetErrorString` at `0x14007763c`
- `webservices!WsGetErrorString` at `0x14007763c`
- `webservices!WsGetFaultErrorProperty` at `0x1400774e4`
- `webservices!WsGetFaultErrorProperty` at `0x1400774e4`
- `webservices!WsResetError` at `0x140077674`
- `webservices!WsResetError` at `0x140077674`

## string_xrefs

- `0x14007750a`: `termsrv\wms\src\common\srcutils\cwebserviceproxy.cpp`
- `0x140077694`: `termsrv\wms\src\common\srcutils\cwebserviceproxy.cpp`
- `0x140077500`: `CWebServiceProxy::LogError`
- `0x14007768a`: `CWebServiceProxy::LogError`
- `0x1400774b5`: `CWebServiceProxy::LogError - ENDPOINT: %s\n`
- `0x1400775e5`: `CWebServiceProxy::LogError - FAULT: %s\n`
- `0x14007765a`: `CWebServiceProxy::LogError - ERROR: %s\n`

## pseudocode

```c
void __fastcall CWebServiceProxy::LogError(CWebServiceProxy *this, int a2)
{
  unsigned __int16 *v4; // r14
  unsigned __int16 *v5; // rdi
  int v6; // eax
  WS_ERROR *v7; // rcx
  HRESULT FaultErrorProperty; // eax
  HRESULT v9; // r13d
  OLECHAR *v10; // r13
  WS_ERROR *v11; // rcx
  ULONG v12; // esi
  WS_ERROR *v13; // rcx
  HRESULT ErrorString; // eax
  __int64 buffer; // [rsp+40h] [rbp-30h] BYREF
  WS_STRING string; // [rsp+48h] [rbp-28h] BYREF
  struct _WS_STRING v17; // [rsp+58h] [rbp-18h] BYREF
  ULONG v18; // [rsp+B8h] [rbp+48h] BYREF
  BSTR bstrString; // [rsp+C0h] [rbp+50h] BYREF
  unsigned __int16 *v20; // [rsp+C8h] [rbp+58h] BYREF

  v18 = 0;
  buffer = 0;
  bstrString = 0;
  v20 = 0;
  v4 = 0;
  v5 = 0;
  string = 0;
  if ( (a2 & 0x1FFF0000) != 0x3D0000 )
    goto LABEL_8;
  v6 = WsStringToBstr((const struct _WS_STRING *)this + 16, &v20);
  v5 = v20;
  if ( v6 < 0 )
    goto LABEL_8;
  DEBUGMSG(L"CWebServiceProxy::LogError - ENDPOINT: %s\n", v20);
  if ( a2 == -2143485933 && (v7 = (WS_ERROR *)*((_QWORD *)this + 1)) != 0 )
  {
    FaultErrorProperty = WsGetFaultErrorProperty(v7, WS_FAULT_ERROR_PROPERTY_FAULT, &buffer, 8u);
    v9 = FaultErrorProperty;
    if ( FaultErrorProperty < 0 )
    {
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\cwebserviceproxy.cpp",
        0x130u,
        L"CWebServiceProxy::LogError",
        L"CHRA",
        L"hr",
        FaultErrorProperty);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\common\\srcutils\\cwebserviceproxy.cpp",
          304,
          L"CWebServiceProxy::LogError",
          L"CHRA",
          L"hr",
          v9);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\srcutils\\cwebserviceproxy.cpp",
          304,
          L"CWebServiceProxy::LogError",
          L"CHRA",
          L"hr",
          v9);
LABEL_8:
      v10 = bstrString;
      goto LABEL_9;
    }
    v17 = *(struct _WS_STRING *)*(_QWORD *)(buffer + 8);
    WsStringToBstr(&v17, &bstrString);
    v10 = bstrString;
    DEBUGMSG(L"CWebServiceProxy::LogError - FAULT: %s\n", bstrString);
  }
  else
  {
    v10 = bstrString;
  }
  v11 = (WS_ERROR *)*((_QWORD *)this + 1);
  if ( v11 )
  {
    WsGetErrorProperty(v11, WS_ERROR_PROPERTY_STRING_COUNT, &v18, 4u);
    v12 = 0;
    if ( v18 )
    {
      while ( 1 )
      {
        SysFreeString(v4);
        v13 = (WS_ERROR *)*((_QWORD *)this + 1);
        v20 = 0;
        v4 = 0;
        ErrorString = WsGetErrorString(v13, v12, &string);
        LODWORD(bstrString) = ErrorString;
        if ( ErrorString < 0 )
          break;
        WsStringToBstr(&string, &v20);
        v4 = v20;
        DEBUGMSG(L"CWebServiceProxy::LogError - ERROR: %s\n", v20);
        if ( ++v12 >= v18 )
          goto LABEL_17;
      }
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\cwebserviceproxy.cpp",
        0x144u,
        L"CWebServiceProxy::LogError",
        L"CHRA",
        L"hr",
        ErrorString);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\common\\srcutils\\cwebserviceproxy.cpp",
          324,
          L"CWebServiceProxy::LogError",
          L"CHRA",
          L"hr",
          (_DWORD)bstrString);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\srcutils\\cwebserviceproxy.cpp",
          324,
          L"CWebServiceProxy::LogError",
          L"CHRA",
          L"hr",
          (_DWORD)bstrString);
    }
    else
    {
LABEL_17:
      WsResetError(*((WS_ERROR **)this + 1));
    }
  }
LABEL_9:
  SysFreeString(v10);
  SysFreeString(v4);
  SysFreeString(v5);
}

```

## disassembly

```asm
0x140077448  mov     [rsp-38h+arg_0], rbx
0x14007744d  push    rbp
0x14007744e  push    rsi
0x14007744f  push    rdi
0x140077450  push    r12
0x140077452  push    r13
0x140077454  push    r14
0x140077456  push    r15
0x140077458  mov     rbp, rsp
0x14007745b  sub     rsp, 70h
0x14007745f  xor     r15d, r15d
0x140077462  mov     eax, edx
0x140077464  and     eax, 1FFF0000h
0x140077469  mov     [rbp+arg_8], r15d
0x14007746d  mov     [rbp+buffer], r15
0x140077471  xorps   xmm0, xmm0
0x140077474  mov     [rbp+bstrString], r15
0x140077478  mov     esi, edx
0x14007747a  mov     [rbp+arg_18], r15
0x14007747e  mov     rbx, rcx
0x140077481  mov     r14d, r15d
0x140077484  mov     edi, r15d
0x140077487  movups  xmmword ptr [rbp+string.length], xmm0
0x14007748b  cmp     eax, 3D0000h
0x140077490  jnz     loc_140077564
0x140077496  add     rcx, 100h; struct _WS_STRING *
0x14007749d  lea     rdx, [rbp+arg_18]; unsigned __int16 **
0x1400774a1  call    ?WsStringToBstr@@YAJPEBU_WS_STRING@@PEAPEAG@Z; WsStringToBstr(_WS_STRING const *,ushort * *)
0x1400774a6  mov     rdi, [rbp+arg_18]
0x1400774aa  test    eax, eax
0x1400774ac  js      loc_140077564
0x1400774b2  mov     rdx, rdi
0x1400774b5  lea     rcx, aCwebservicepro_0; "CWebServiceProxy::LogError - ENDPOINT: "...
0x1400774bc  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400774c1  cmp     esi, 803D0013h
0x1400774c7  jnz     loc_1400775F6
0x1400774cd  mov     rcx, [rbx+8]; error
0x1400774d1  test    rcx, rcx
0x1400774d4  jz      loc_1400775F6
0x1400774da  lea     r9d, [r15+8]; bufferSize
0x1400774de  xor     edx, edx; id
0x1400774e0  lea     r8, [rbp+buffer]; buffer
0x1400774e4  call    cs:__imp_WsGetFaultErrorProperty
0x1400774ea  mov     r13d, eax
0x1400774ed  test    eax, eax
0x1400774ef  jns     loc_1400775C4
0x1400774f5  mov     [rsp+70h+var_48], eax; int
0x1400774f9  lea     r12, aChra; "CHRA"
0x140077500  lea     rsi, aCwebservicepro_4; "CWebServiceProxy::LogError"
0x140077507  mov     r9, r12; unsigned __int16 *
0x14007750a  lea     rbx, aTermsrvWmsSrcC_9; "termsrv\\wms\\src\\common\\srcutils\\cw"...
0x140077511  mov     r8, rsi; unsigned __int16 *
0x140077514  lea     r15, aHr; "hr"
0x14007751b  mov     rcx, rbx; unsigned __int16 *
0x14007751e  mov     edx, 130h; unsigned int
0x140077523  mov     [rsp+70h+var_50], r15; unsigned __int16 *
0x140077528  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14007752d  call    cs:__imp_IsDebuggerPresent
0x140077533  test    eax, eax
0x140077535  jz      short loc_14007759B
0x140077537  mov     [rsp+70h+var_38], r13d
0x14007753c  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140077543  mov     [rsp+70h+var_40], r15
0x140077548  lea     ecx, [r14+2]; unsigned __int8
0x14007754c  mov     qword ptr [rsp+70h+var_48], r12
0x140077551  mov     r9d, 130h
0x140077557  mov     r8, rbx
0x14007755a  mov     [rsp+70h+var_50], rsi
0x14007755f  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140077564  mov     r13, [rbp+bstrString]
0x140077568  mov     rcx, r13; bstrString
0x14007756b  call    cs:__imp_SysFreeString
0x140077571  mov     rcx, r14; bstrString
0x140077574  call    cs:__imp_SysFreeString
0x14007757a  mov     rcx, rdi; bstrString
0x14007757d  call    cs:__imp_SysFreeString
0x140077583  mov     rbx, [rsp+70h+arg_0]
0x14007758b  add     rsp, 70h
0x14007758f  pop     r15
0x140077591  pop     r14
0x140077593  pop     r13
0x140077595  pop     r12
0x140077597  pop     rdi
0x140077598  pop     rsi
0x140077599  pop     rbp
0x14007759a  retn
0x14007759b  mov     dword ptr [rsp+70h+var_40], r13d
0x1400775a0  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400775a7  mov     qword ptr [rsp+70h+var_48], r15
0x1400775ac  mov     r9, rsi
0x1400775af  mov     r8d, 130h
0x1400775b5  mov     [rsp+70h+var_50], r12
0x1400775ba  mov     rdx, rbx
0x1400775bd  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400775c2  jmp     short loc_140077564
0x1400775c4  mov     rax, [rbp+buffer]
0x1400775c8  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x1400775cc  mov     rcx, [rax+8]
0x1400775d0  movups  xmm0, xmmword ptr [rcx]
0x1400775d3  lea     rcx, [rbp+var_18]; struct _WS_STRING *
0x1400775d7  movdqu  xmmword ptr [rbp+var_18.length], xmm0
0x1400775dc  call    ?WsStringToBstr@@YAJPEBU_WS_STRING@@PEAPEAG@Z; WsStringToBstr(_WS_STRING const *,ushort * *)
0x1400775e1  mov     r13, [rbp+bstrString]
0x1400775e5  lea     rcx, aCwebservicepro_2; "CWebServiceProxy::LogError - FAULT: %s"...
0x1400775ec  mov     rdx, r13
0x1400775ef  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400775f4  jmp     short loc_1400775FA
0x1400775f6  mov     r13, [rbp+bstrString]
0x1400775fa  mov     rcx, [rbx+8]; error
0x1400775fe  test    rcx, rcx
0x140077601  jz      loc_140077568
0x140077607  mov     r9d, 4; bufferSize
0x14007760d  lea     r8, [rbp+arg_8]; buffer
0x140077611  xor     edx, edx; id
0x140077613  call    cs:__imp_WsGetErrorProperty
0x140077619  mov     esi, r15d
0x14007761c  cmp     [rbp+arg_8], r15d
0x140077620  jbe     short loc_140077670
0x140077622  mov     rcx, r14; bstrString
0x140077625  call    cs:__imp_SysFreeString
0x14007762b  mov     rcx, [rbx+8]; error
0x14007762f  lea     r8, [rbp+string]; string
0x140077633  mov     edx, esi; index
0x140077635  mov     [rbp+arg_18], r15
0x140077639  mov     r14, r15
0x14007763c  call    cs:__imp_WsGetErrorString
0x140077642  mov     dword ptr [rbp+bstrString], eax
0x140077645  test    eax, eax
0x140077647  js      short loc_14007767F
0x140077649  lea     rdx, [rbp+arg_18]; unsigned __int16 **
0x14007764d  lea     rcx, [rbp+string]; struct _WS_STRING *
0x140077651  call    ?WsStringToBstr@@YAJPEBU_WS_STRING@@PEAPEAG@Z; WsStringToBstr(_WS_STRING const *,ushort * *)
0x140077656  mov     r14, [rbp+arg_18]
0x14007765a  lea     rcx, aCwebservicepro_1; "CWebServiceProxy::LogError - ERROR: %s"...
0x140077661  mov     rdx, r14
0x140077664  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140077669  inc     esi
0x14007766b  cmp     esi, [rbp+arg_8]
0x14007766e  jb      short loc_140077622
0x140077670  mov     rcx, [rbx+8]; error
0x140077674  call    cs:__imp_WsResetError
0x14007767a  jmp     loc_140077568
0x14007767f  mov     [rsp+70h+var_48], eax; int
0x140077683  lea     r12, aChra; "CHRA"
0x14007768a  lea     rsi, aCwebservicepro_4; "CWebServiceProxy::LogError"
0x140077691  mov     r9, r12; unsigned __int16 *
0x140077694  lea     rbx, aTermsrvWmsSrcC_9; "termsrv\\wms\\src\\common\\srcutils\\cw"...
0x14007769b  mov     r8, rsi; unsigned __int16 *
0x14007769e  lea     r15, aHr; "hr"
0x1400776a5  mov     rcx, rbx; unsigned __int16 *
0x1400776a8  mov     edx, 144h; unsigned int
0x1400776ad  mov     [rsp+70h+var_50], r15; unsigned __int16 *
0x1400776b2  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400776b7  call    cs:__imp_IsDebuggerPresent
0x1400776bd  test    eax, eax
0x1400776bf  mov     eax, dword ptr [rbp+bstrString]
0x1400776c2  jz      short loc_1400776F6
0x1400776c4  mov     [rsp+70h+var_38], eax
0x1400776c8  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400776cf  mov     [rsp+70h+var_40], r15
0x1400776d4  mov     r9d, 144h
0x1400776da  mov     qword ptr [rsp+70h+var_48], r12
0x1400776df  mov     r8, rbx
0x1400776e2  mov     ecx, 2; unsigned __int8
0x1400776e7  mov     [rsp+70h+var_50], rsi
0x1400776ec  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400776f1  jmp     loc_140077568
0x1400776f6  mov     dword ptr [rsp+70h+var_40], eax
0x1400776fa  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140077701  mov     qword ptr [rsp+70h+var_48], r15
0x140077706  mov     r9, rsi
0x140077709  mov     r8d, 144h
0x14007770f  mov     [rsp+70h+var_50], r12
0x140077714  mov     rdx, rbx
0x140077717  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14007771c  jmp     loc_140077568
```
