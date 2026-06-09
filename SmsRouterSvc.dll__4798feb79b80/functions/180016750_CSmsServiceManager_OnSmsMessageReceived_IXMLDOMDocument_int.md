# CSmsServiceManager::OnSmsMessageReceived(IXMLDOMDocument *,int)

- ea: `0x180016750`
- end: `0x180016b89`
- name: `?OnSmsMessageReceived@CSmsServiceManager@@UEAAJPEAUIXMLDOMDocument@@H@Z`
- size: `1081`
- prototype: `int(CSmsServiceManager *__hidden this, struct IXMLDOMDocument *, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000108c`
- `0x180003a60`
- `0x18000fc78`
- `0x180014d20`
- `0x180015764`
- `0x180016750`
- `0x180051420`
- `0x180051628`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001678a`
- `OLEAUT32!__imp_SysAllocString` at `0x180016829`
- `OLEAUT32!__imp_SysAllocString` at `0x180016875`
- `OLEAUT32!__imp_SysAllocString` at `0x180016903`
- `OLEAUT32!__imp_SysAllocString` at `0x18001697d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800169c6`
- `OLEAUT32!__imp_SysAllocString` at `0x180016a0f`
- `OLEAUT32!__imp_SysAllocString` at `0x180016a55`
- `OLEAUT32!__imp_SysAllocString` at `0x18001678a`
- `OLEAUT32!__imp_SysAllocString` at `0x180016829`
- `OLEAUT32!__imp_SysAllocString` at `0x180016875`
- `OLEAUT32!__imp_SysAllocString` at `0x180016903`
- `OLEAUT32!__imp_SysAllocString` at `0x18001697d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800169c6`
- `OLEAUT32!__imp_SysAllocString` at `0x180016a0f`
- `OLEAUT32!__imp_SysAllocString` at `0x180016a55`
- `OLEAUT32!__imp_SysFreeString` at `0x180016856`
- `OLEAUT32!__imp_SysFreeString` at `0x1800168a2`
- `OLEAUT32!__imp_SysFreeString` at `0x180016930`
- `OLEAUT32!__imp_SysFreeString` at `0x1800169aa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800169f3`
- `OLEAUT32!__imp_SysFreeString` at `0x180016a3c`
- `OLEAUT32!__imp_SysFreeString` at `0x180016a82`
- `OLEAUT32!__imp_SysFreeString` at `0x180016b44`
- `OLEAUT32!__imp_SysFreeString` at `0x180016856`
- `OLEAUT32!__imp_SysFreeString` at `0x1800168a2`
- `OLEAUT32!__imp_SysFreeString` at `0x180016930`
- `OLEAUT32!__imp_SysFreeString` at `0x1800169aa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800169f3`
- `OLEAUT32!__imp_SysFreeString` at `0x180016a3c`
- `OLEAUT32!__imp_SysFreeString` at `0x180016a82`
- `OLEAUT32!__imp_SysFreeString` at `0x180016b44`
- `OLEAUT32!__imp_VarBstrCmp` at `0x18001684b`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180016897`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180016925`
- `OLEAUT32!__imp_VarBstrCmp` at `0x18001699f`
- `OLEAUT32!__imp_VarBstrCmp` at `0x1800169e8`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180016a31`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180016a77`
- `OLEAUT32!__imp_VarBstrCmp` at `0x18001684b`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180016897`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180016925`
- `OLEAUT32!__imp_VarBstrCmp` at `0x18001699f`
- `OLEAUT32!__imp_VarBstrCmp` at `0x1800169e8`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180016a31`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180016a77`

## string_xrefs

- `0x1800167b9`: `CSmsServiceManager::OnSmsMessageReceived`
- `0x180016811`: `CSmsServiceManager::OnSmsMessageReceived`
- `0x180016965`: `CSmsServiceManager::OnSmsMessageReceived`
- `0x1800168b7`: `/Message/ProtocolId`
- `0x1800168eb`: `Failed to parse protocol ID from malformed message: %S`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSmsServiceManager::OnSmsMessageReceived(CSmsServiceManager *this, struct IXMLDOMNode *a2, int a3)
{
  unsigned int v6; // r14d
  int NodeTextValue; // esi
  OLECHAR *v8; // rax
  OLECHAR *v9; // rbx
  HRESULT v10; // edi
  OLECHAR *v11; // rax
  OLECHAR *v12; // rbx
  HRESULT v13; // edi
  OLECHAR *v14; // rax
  OLECHAR *v15; // rbx
  HRESULT v16; // edi
  OLECHAR *v17; // rax
  OLECHAR *v18; // rbx
  HRESULT v19; // edi
  OLECHAR *v20; // rax
  OLECHAR *v21; // rbx
  HRESULT v22; // edi
  OLECHAR *v23; // rax
  OLECHAR *v24; // rbx
  HRESULT v25; // edi
  OLECHAR *v26; // rax
  OLECHAR *v27; // rbx
  HRESULT v28; // edi
  BSTR bstrLeft; // [rsp+30h] [rbp-59h] BYREF
  int v31; // [rsp+38h] [rbp-51h] BYREF
  int v32; // [rsp+3Ch] [rbp-4Dh] BYREF
  unsigned int v33; // [rsp+40h] [rbp-49h] BYREF
  char v34[32]; // [rsp+50h] [rbp-39h] BYREF
  unsigned int *v35; // [rsp+70h] [rbp-19h]
  __int64 v36; // [rsp+78h] [rbp-11h]
  int *v37; // [rsp+80h] [rbp-9h]
  __int64 v38; // [rsp+88h] [rbp-1h]
  int *v39; // [rsp+90h] [rbp+7h]
  __int64 v40; // [rsp+98h] [rbp+Fh]

  bstrLeft = SysAllocString(&LocaleName);
  if ( !bstrLeft )
    ATL::AtlThrowImpl(-2147024882);
  v6 = 0;
  if ( a2 )
  {
    NodeTextValue = Windows::Sms::Common::CSmsUtil::GetNodeTextValue(a2, L"/Message/MessageType", &bstrLeft);
    if ( NodeTextValue < 0 )
    {
      ((void (__fastcall *)(struct IXMLDOMNode *, BSTR *))a2->lpVtbl->get_xml)(a2, &bstrLeft);
      LogSmsRouterError(
        "CSmsServiceManager::OnSmsMessageReceived",
        0x2B2u,
        NodeTextValue,
        "Malformed Message received: %S",
        bstrLeft);
      goto LABEL_30;
    }
    v8 = SysAllocString(L"Application");
    v9 = v8;
    if ( v8 )
    {
      v10 = VarBstrCmp(bstrLeft, v8, 0x400u, 0);
      SysFreeString(v9);
      if ( v10 == 1 )
      {
        v6 = 2;
        goto LABEL_29;
      }
      v11 = SysAllocString(L"Text");
      v12 = v11;
      if ( v11 )
      {
        v13 = VarBstrCmp(bstrLeft, v11, 0x400u, 0);
        SysFreeString(v12);
        if ( v13 == 1 )
        {
          v6 = 1;
          NodeTextValue = Windows::Sms::Common::CSmsUtil::GetNodeTextValue(a2, L"/Message/ProtocolId", &bstrLeft);
          if ( NodeTextValue < 0 )
          {
            ((void (__fastcall *)(struct IXMLDOMNode *, BSTR *))a2->lpVtbl->get_xml)(a2, &bstrLeft);
            LogSmsRouterError(
              "CSmsServiceManager::OnSmsMessageReceived",
              0x2D5u,
              NodeTextValue,
              "Failed to parse protocol ID from malformed message: %S",
              bstrLeft);
            goto LABEL_30;
          }
          v14 = SysAllocString(L"64");
          v15 = v14;
          if ( v14 )
          {
            v16 = VarBstrCmp(bstrLeft, v14, 0x400u, 0);
            SysFreeString(v15);
            if ( v16 == 1 )
            {
              ((void (__fastcall *)(struct IXMLDOMNode *, BSTR *))a2->lpVtbl->get_xml)(a2, &bstrLeft);
              LogSmsRouterInfo("CSmsServiceManager::OnSmsMessageReceived", 0x2DBu, "Dropping type 0 SMS: %S", bstrLeft);
              goto LABEL_30;
            }
LABEL_29:
            NodeTextValue = CSmsInterceptor::HandleNewMessage((char *)this + 88, a2, v6);
            goto LABEL_30;
          }
        }
        else
        {
          v17 = SysAllocString(L"Voicemail");
          v18 = v17;
          if ( v17 )
          {
            v19 = VarBstrCmp(bstrLeft, v17, 0x400u, 0);
            SysFreeString(v18);
            if ( v19 == 1 )
            {
              v6 = 3;
              goto LABEL_29;
            }
            v20 = SysAllocString(L"Broadcast");
            v21 = v20;
            if ( v20 )
            {
              v22 = VarBstrCmp(bstrLeft, v20, 0x400u, 0);
              SysFreeString(v21);
              if ( v22 == 1 )
              {
                v6 = 6;
                goto LABEL_29;
              }
              v23 = SysAllocString(L"Status");
              v24 = v23;
              if ( v23 )
              {
                v25 = VarBstrCmp(bstrLeft, v23, 0x400u, 0);
                SysFreeString(v24);
                if ( v25 == 1 )
                {
                  v6 = 5;
                  goto LABEL_29;
                }
                v26 = SysAllocString(L"Wap");
                v27 = v26;
                if ( v26 )
                {
                  v28 = VarBstrCmp(bstrLeft, v26, 0x400u, 0);
                  SysFreeString(v27);
                  if ( v28 == 1 )
                    v6 = 4;
                  goto LABEL_29;
                }
              }
            }
          }
        }
      }
    }
    ATL::AtlThrowImpl(-2147024882);
  }
  NodeTextValue = -2147024809;
  LogSmsRouterError("CSmsServiceManager::OnSmsMessageReceived", 0x2AAu, -2147024809, "Message is null");
LABEL_30:
  if ( (unsigned int)dword_18008C078 > 5
    && (qword_18008C088 & 0x400000000000LL) != 0
    && (qword_18008C090 & 0x400000000000LL) == qword_18008C090 )
  {
    v31 = NodeTextValue;
    v32 = a3;
    v33 = v6;
    v39 = &v31;
    v40 = 4;
    v37 = &v32;
    v38 = 4;
    v35 = &v33;
    v36 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_18008C078, byte_18007DD21, 0, 0, 5, v34);
  }
  SysFreeString(bstrLeft);
  return (unsigned int)NodeTextValue;
}

```

## disassembly

```asm
0x180016750  mov     [rsp-8+arg_10], rbx
0x180016755  push    rbp
0x180016756  push    rsi
0x180016757  push    rdi
0x180016758  push    r12
0x18001675a  push    r13
0x18001675c  push    r14
0x18001675e  push    r15
0x180016760  lea     rbp, [rsp-27h]
0x180016765  sub     rsp, 0B0h
0x18001676c  mov     rax, cs:__security_cookie
0x180016773  xor     rax, rsp
0x180016776  mov     [rbp+57h+var_40], rax
0x18001677a  mov     r12d, r8d
0x18001677d  mov     r15, rdx
0x180016780  mov     r13, rcx
0x180016783  lea     rcx, LocaleName; psz
0x18001678a  call    cs:__imp_SysAllocString
0x180016790  mov     [rbp+57h+bstrLeft], rax
0x180016794  test    rax, rax
0x180016797  jz      loc_180016B73
0x18001679d  xor     r14d, r14d
0x1800167a0  test    r15, r15
0x1800167a3  jnz     short loc_1800167CA
0x1800167a5  mov     esi, 80070057h
0x1800167aa  lea     r9, aMessageIsNull; "Message is null"
0x1800167b1  mov     r8d, esi; int
0x1800167b4  mov     edx, 2AAh; unsigned int
0x1800167b9  lea     rcx, aCsmsserviceman; "CSmsServiceManager::OnSmsMessageReceive"...
0x1800167c0  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x1800167c5  jmp     loc_180016AA3
0x1800167ca  lea     r8, [rbp+57h+bstrLeft]; unsigned __int16 **
0x1800167ce  lea     rdx, aMessageMessage; "/Message/MessageType"
0x1800167d5  mov     rcx, r15; struct IXMLDOMNode *
0x1800167d8  call    ?GetNodeTextValue@CSmsUtil@Common@Sms@Windows@@SAJPEAUIXMLDOMNode@@PEBGPEAPEAG@Z; Windows::Sms::Common::CSmsUtil::GetNodeTextValue(IXMLDOMNode *,ushort const *,ushort * *)
0x1800167dd  mov     esi, eax
0x1800167df  test    eax, eax
0x1800167e1  jns     short loc_180016822
0x1800167e3  mov     rdx, [r15]
0x1800167e6  mov     rax, [rdx+110h]
0x1800167ed  lea     rdx, [rbp+57h+bstrLeft]
0x1800167f1  mov     rcx, r15
0x1800167f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167f9  mov     rcx, [rbp+57h+bstrLeft]
0x1800167fd  mov     [rsp+0E0h+var_C0], rcx
0x180016802  lea     r9, aMalformedMessa; "Malformed Message received: %S"
0x180016809  mov     edx, 2B2h; unsigned int
0x18001680e  mov     r8d, esi; int
0x180016811  lea     rcx, aCsmsserviceman; "CSmsServiceManager::OnSmsMessageReceive"...
0x180016818  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18001681d  jmp     loc_180016AA3
0x180016822  lea     rcx, aApplication; "Application"
0x180016829  call    cs:__imp_SysAllocString
0x18001682f  mov     rbx, rax
0x180016832  test    rax, rax
0x180016835  jz      loc_180016B7E
0x18001683b  xor     r9d, r9d; dwFlags
0x18001683e  mov     r8d, 400h; lcid
0x180016844  mov     rdx, rax; bstrRight
0x180016847  mov     rcx, [rbp+57h+bstrLeft]; bstrLeft
0x18001684b  call    cs:__imp_VarBstrCmp
0x180016851  mov     edi, eax
0x180016853  mov     rcx, rbx; bstrString
0x180016856  call    cs:__imp_SysFreeString
0x18001685c  mov     esi, 1
0x180016861  cmp     edi, esi
0x180016863  jnz     short loc_18001686E
0x180016865  lea     r14d, [rsi+1]
0x180016869  jmp     loc_180016A92
0x18001686e  lea     rcx, psz; "Text"
0x180016875  call    cs:__imp_SysAllocString
0x18001687b  mov     rbx, rax
0x18001687e  test    rax, rax
0x180016881  jz      loc_180016B7E
0x180016887  xor     r9d, r9d; dwFlags
0x18001688a  mov     r8d, 400h; lcid
0x180016890  mov     rdx, rax; bstrRight
0x180016893  mov     rcx, [rbp+57h+bstrLeft]; bstrLeft
0x180016897  call    cs:__imp_VarBstrCmp
0x18001689d  mov     edi, eax
0x18001689f  mov     rcx, rbx; bstrString
0x1800168a2  call    cs:__imp_SysFreeString
0x1800168a8  cmp     edi, esi
0x1800168aa  jnz     loc_180016976
0x1800168b0  mov     r14d, esi
0x1800168b3  lea     r8, [rbp+57h+bstrLeft]; unsigned __int16 **
0x1800168b7  lea     rdx, aMessageProtoco; "/Message/ProtocolId"
0x1800168be  mov     rcx, r15; struct IXMLDOMNode *
0x1800168c1  call    ?GetNodeTextValue@CSmsUtil@Common@Sms@Windows@@SAJPEAUIXMLDOMNode@@PEBGPEAPEAG@Z; Windows::Sms::Common::CSmsUtil::GetNodeTextValue(IXMLDOMNode *,ushort const *,ushort * *)
0x1800168c6  mov     esi, eax
0x1800168c8  test    eax, eax
0x1800168ca  jns     short loc_1800168FC
0x1800168cc  mov     rax, [r15]
0x1800168cf  lea     rdx, [rbp+57h+bstrLeft]
0x1800168d3  mov     rcx, r15
0x1800168d6  mov     rax, [rax+110h]
0x1800168dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168e2  mov     rax, [rbp+57h+bstrLeft]
0x1800168e6  mov     [rsp+0E0h+var_C0], rax
0x1800168eb  lea     r9, aFailedToParseP; "Failed to parse protocol ID from malfor"...
0x1800168f2  mov     edx, 2D5h
0x1800168f7  jmp     loc_18001680E
0x1800168fc  lea     rcx, a64; "64"
0x180016903  call    cs:__imp_SysAllocString
0x180016909  mov     rbx, rax
0x18001690c  test    rax, rax
0x18001690f  jz      loc_180016B7E
0x180016915  xor     r9d, r9d; dwFlags
0x180016918  mov     r8d, 400h; lcid
0x18001691e  mov     rdx, rax; bstrRight
0x180016921  mov     rcx, [rbp+57h+bstrLeft]; bstrLeft
0x180016925  call    cs:__imp_VarBstrCmp
0x18001692b  mov     edi, eax
0x18001692d  mov     rcx, rbx; bstrString
0x180016930  call    cs:__imp_SysFreeString
0x180016936  cmp     edi, r14d
0x180016939  jnz     loc_180016A92
0x18001693f  mov     rax, [r15]
0x180016942  lea     rdx, [rbp+57h+bstrLeft]
0x180016946  mov     rcx, r15
0x180016949  mov     rax, [rax+110h]
0x180016950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016955  mov     r9, [rbp+57h+bstrLeft]
0x180016959  lea     r8, aDroppingType0S; "Dropping type 0 SMS: %S"
0x180016960  mov     edx, 2DBh; unsigned int
0x180016965  lea     rcx, aCsmsserviceman; "CSmsServiceManager::OnSmsMessageReceive"...
0x18001696c  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180016971  jmp     loc_180016AA3
0x180016976  lea     rcx, aVoicemail; "Voicemail"
0x18001697d  call    cs:__imp_SysAllocString
0x180016983  mov     rbx, rax
0x180016986  test    rax, rax
0x180016989  jz      loc_180016B7E
0x18001698f  xor     r9d, r9d; dwFlags
0x180016992  mov     r8d, 400h; lcid
0x180016998  mov     rdx, rax; bstrRight
0x18001699b  mov     rcx, [rbp+57h+bstrLeft]; bstrLeft
0x18001699f  call    cs:__imp_VarBstrCmp
0x1800169a5  mov     edi, eax
0x1800169a7  mov     rcx, rbx; bstrString
0x1800169aa  call    cs:__imp_SysFreeString
0x1800169b0  cmp     edi, esi
0x1800169b2  jnz     short loc_1800169BF
0x1800169b4  mov     r14d, 3
0x1800169ba  jmp     loc_180016A92
0x1800169bf  lea     rcx, aBroadcast; "Broadcast"
0x1800169c6  call    cs:__imp_SysAllocString
0x1800169cc  mov     rbx, rax
0x1800169cf  test    rax, rax
0x1800169d2  jz      loc_180016B7E
0x1800169d8  xor     r9d, r9d; dwFlags
0x1800169db  mov     r8d, 400h; lcid
0x1800169e1  mov     rdx, rax; bstrRight
0x1800169e4  mov     rcx, [rbp+57h+bstrLeft]; bstrLeft
0x1800169e8  call    cs:__imp_VarBstrCmp
0x1800169ee  mov     edi, eax
0x1800169f0  mov     rcx, rbx; bstrString
0x1800169f3  call    cs:__imp_SysFreeString
0x1800169f9  cmp     edi, esi
0x1800169fb  jnz     short loc_180016A08
0x1800169fd  mov     r14d, 6
0x180016a03  jmp     loc_180016A92
0x180016a08  lea     rcx, aStatus; "Status"
0x180016a0f  call    cs:__imp_SysAllocString
0x180016a15  mov     rbx, rax
0x180016a18  test    rax, rax
0x180016a1b  jz      loc_180016B7E
0x180016a21  xor     r9d, r9d; dwFlags
0x180016a24  mov     r8d, 400h; lcid
0x180016a2a  mov     rdx, rax; bstrRight
0x180016a2d  mov     rcx, [rbp+57h+bstrLeft]; bstrLeft
0x180016a31  call    cs:__imp_VarBstrCmp
0x180016a37  mov     edi, eax
0x180016a39  mov     rcx, rbx; bstrString
0x180016a3c  call    cs:__imp_SysFreeString
0x180016a42  cmp     edi, esi
0x180016a44  jnz     short loc_180016A4E
0x180016a46  mov     r14d, 5
0x180016a4c  jmp     short loc_180016A92
0x180016a4e  lea     rcx, aWap; "Wap"
0x180016a55  call    cs:__imp_SysAllocString
0x180016a5b  mov     rbx, rax
0x180016a5e  test    rax, rax
0x180016a61  jz      loc_180016B7E
0x180016a67  xor     r9d, r9d; dwFlags
0x180016a6a  mov     r8d, 400h; lcid
0x180016a70  mov     rdx, rax; bstrRight
0x180016a73  mov     rcx, [rbp+57h+bstrLeft]; bstrLeft
0x180016a77  call    cs:__imp_VarBstrCmp
0x180016a7d  mov     edi, eax
0x180016a7f  mov     rcx, rbx; bstrString
0x180016a82  call    cs:__imp_SysFreeString
0x180016a88  cmp     edi, esi
0x180016a8a  jnz     short loc_180016A92
0x180016a8c  mov     r14d, 4
0x180016a92  lea     rcx, [r13+58h]
0x180016a96  mov     r8d, r14d
0x180016a99  mov     rdx, r15
0x180016a9c  call    ?HandleNewMessage@CSmsInterceptor@@QEAAJPEAUIXMLDOMDocument@@W4SmsMessageType@Common@Sms@Windows@@@Z; CSmsInterceptor::HandleNewMessage(IXMLDOMDocument *,Windows::Sms::Common::SmsMessageType)
0x180016aa1  mov     esi, eax
0x180016aa3  mov     eax, cs:dword_18008C078
0x180016aa9  cmp     eax, 5
0x180016aac  jbe     loc_180016B40
0x180016ab2  mov     rcx, cs:qword_18008C090
0x180016ab9  mov     rax, cs:qword_18008C088
0x180016ac0  mov     rdx, 400000000000h
0x180016aca  test    rdx, rax
0x180016acd  jz      short loc_180016B40
0x180016acf  mov     rax, rcx
0x180016ad2  and     rax, rdx
0x180016ad5  cmp     rax, rcx
0x180016ad8  jnz     short loc_180016B40
0x180016ada  mov     [rbp+57h+var_A8], esi
0x180016add  mov     [rbp+57h+var_A4], r12d
0x180016ae1  mov     [rbp+57h+var_A0], r14d
0x180016ae5  lea     rax, [rbp+57h+var_A8]
0x180016ae9  mov     [rbp+57h+var_50], rax
0x180016aed  mov     [rbp+57h+var_48], 4
0x180016af5  lea     rax, [rbp+57h+var_A4]
0x180016af9  mov     [rbp+57h+var_60], rax
0x180016afd  mov     [rbp+57h+var_58], 4
0x180016b05  lea     rax, [rbp+57h+var_A0]
0x180016b09  mov     [rbp+57h+var_70], rax
0x180016b0d  mov     [rbp+57h+var_68], 4
0x180016b15  lea     rax, [rbp+57h+var_90]
0x180016b19  mov     [rsp+0E0h+var_B8], rax
0x180016b1e  mov     dword ptr [rsp+0E0h+var_C0], 5
0x180016b26  xor     r9d, r9d
0x180016b29  xor     r8d, r8d
0x180016b2c  lea     rdx, byte_18007DD21
0x180016b33  lea     rcx, dword_18008C078
0x180016b3a  call    _tlgWriteTransfer_EventWriteTransfer
0x180016b3f  nop
0x180016b40  mov     rcx, [rbp+57h+bstrLeft]; bstrString
0x180016b44  call    cs:__imp_SysFreeString
0x180016b4a  mov     eax, esi
0x180016b4c  mov     rcx, [rbp+57h+var_40]
0x180016b50  xor     rcx, rsp; StackCookie
0x180016b53  call    __security_check_cookie
0x180016b58  mov     rbx, [rsp+0E0h+arg_10]
0x180016b60  add     rsp, 0B0h
0x180016b67  pop     r15
0x180016b69  pop     r14
0x180016b6b  pop     r13
0x180016b6d  pop     r12
0x180016b6f  pop     rdi
0x180016b70  pop     rsi
0x180016b71  pop     rbp
0x180016b72  retn
0x180016b73  mov     ecx, 8007000Eh; int
0x180016b78  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180016b7e  mov     ecx, 8007000Eh; int
0x180016b83  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
