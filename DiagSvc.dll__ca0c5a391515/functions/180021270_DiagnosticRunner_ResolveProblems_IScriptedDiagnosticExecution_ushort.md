# DiagnosticRunner::ResolveProblems(IScriptedDiagnosticExecution *,ushort *)

- ea: `0x180021270`
- end: `0x180021992`
- name: `?ResolveProblems@DiagnosticRunner@@MEAAJPEAUIScriptedDiagnosticExecution@@PEAG@Z`
- size: `1826`
- prototype: `__int64 __fastcall(DiagnosticRunner *__hidden this, struct IScriptedDiagnosticExecution *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task`

## callees

- `0x180001720`
- `0x180001e7c`
- `0x180001fec`
- `0x18000216c`
- `0x180003b84`
- `0x18001c700`
- `0x18001d648`
- `0x18001e04c`
- `0x1800209e0`
- `0x180021270`
- `0x18002345c`
- `0x180024d8c`
- `0x180025158`
- `0x180025500`
- `0x180027010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800218cc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800218cc`

## string_xrefs

- `0x1800213cd`: `ResolveProblems - Create Problem List Xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DiagnosticRunner::ResolveProblems(
        DiagnosticRunner *this,
        struct IScriptedDiagnosticExecution *a2,
        unsigned __int16 *a3)
{
  struct IXMLDOMNodeList *v5; // rdi
  struct IXMLDOMNode *v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  struct IXMLDOMDocument2 *v16; // r15
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  int i; // r14d
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  OLECHAR *v31; // rax
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // r8
  __int64 v43; // rcx
  __int64 v44; // r8
  __int64 v45; // r9
  int v47; // [rsp+68h] [rbp-59h] BYREF
  int v48; // [rsp+6Ch] [rbp-55h] BYREF
  BSTR v49; // [rsp+70h] [rbp-51h] BYREF
  const char *v50; // [rsp+78h] [rbp-49h] BYREF
  const char *v51; // [rsp+80h] [rbp-41h] BYREF
  const char *v52; // [rsp+88h] [rbp-39h] BYREF
  const char *v53; // [rsp+90h] [rbp-31h] BYREF
  struct IXMLDOMNodeList *v54; // [rsp+98h] [rbp-29h] BYREF
  int v55; // [rsp+A0h] [rbp-21h] BYREF
  int v56; // [rsp+A4h] [rbp-1Dh] BYREF
  const char *v57; // [rsp+A8h] [rbp-19h] BYREF
  struct IXMLDOMNode *v58; // [rsp+B0h] [rbp-11h] BYREF
  BSTR bstrString; // [rsp+B8h] [rbp-9h] BYREF
  struct IXMLDOMDocument2 *p_Nodes; // [rsp+C0h] [rbp-1h] BYREF
  struct IScriptedDiagnosticExecution **v61; // [rsp+C8h] [rbp+7h]
  BSTR *p_bstrString; // [rsp+D0h] [rbp+Fh]
  __int64 v63; // [rsp+D8h] [rbp+17h] BYREF
  char v64; // [rsp+E0h] [rbp+1Fh]
  char v65; // [rsp+E8h] [rbp+27h]
  struct IScriptedDiagnosticExecution *v66; // [rsp+130h] [rbp+6Fh] BYREF
  int Nodes; // [rsp+140h] [rbp+7Fh] BYREF

  v66 = a2;
  Nodes = 0;
  p_Nodes = 0;
  v5 = 0;
  v54 = 0;
  v6 = 0;
  v58 = 0;
  bstrString = 0;
  v55 = 0;
  v56 = 0;
  if ( a2 && a3 )
    goto LABEL_7;
  Nodes = -2147024809;
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(this, a2, "DiagnosticRunner::ResolveProblems") )
  {
    v57 = (char *)this + 64;
    v48 = 1074;
    v50 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\diagnosticrunner\\lib\\diagnosticrunner.cpp";
    v51 = (const char *)v8;
    v52 = "ResolveProblems - Invalid Arguments";
    v47 = Nodes;
    v53 = (char *)this + 193;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v7,
      (__int64)&dword_18003196C,
      v8,
      v9,
      &v53,
      (__int64)&v47,
      &v52,
      &v51,
      &v50,
      (__int64)&v48,
      &v57);
  }
  if ( Nodes >= 0 )
  {
LABEL_7:
    Nodes = SdpXmlCreate(a3, (LPVOID *)&p_Nodes);
    if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v11, v10, v12) )
    {
      v53 = (const char *)a3;
      v52 = (char *)this + 64;
      v47 = 1085;
      v51 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\diagnosticrunner\\lib\\diagnosticrunner.cpp";
      v50 = "DiagnosticRunner::ResolveProblems";
      v57 = "ResolveProblems - Create Problem List Xml";
      v48 = Nodes;
      v49 = (BSTR)((char *)this + 193);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v13,
        (__int64)&byte_1800318EF,
        v14,
        v15,
        &v49,
        (__int64)&v48,
        &v57,
        &v50,
        &v51,
        (__int64)&v47,
        &v52,
        &v53);
    }
    v16 = p_Nodes;
    if ( Nodes >= 0 )
    {
      Nodes = SdpXmlGetNodes(L"/Rootcauses/Rootcause", p_Nodes, 0, &v54);
      if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v18, v17, v19) )
      {
        v49 = (BSTR)((char *)this + 64);
        v47 = 1099;
        v53 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\diagnosticrunner\\lib\\diagnosticrunner.cpp";
        v52 = "DiagnosticRunner::ResolveProblems";
        v51 = "ResolveProblems - Get Rootcause node";
        v48 = Nodes;
        v50 = (char *)this + 193;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v20,
          (__int64)&dword_18003187C,
          v21,
          v22,
          &v50,
          (__int64)&v48,
          &v51,
          &v52,
          &v53,
          (__int64)&v47,
          &v49);
      }
      v5 = v54;
      if ( Nodes >= 0 )
      {
        Nodes = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, int *))v54->lpVtbl->get_length)(v54, &v55);
        if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v24, v23, v25) )
        {
          v47 = v55;
          v49 = (BSTR)((char *)this + 64);
          v48 = 1110;
          v53 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\diagnosticrunner\\lib\\diagnosticrunner.cpp";
          v52 = "DiagnosticRunner::ResolveProblems";
          v51 = "ResolveProblems - get Rootcause node length";
          LODWORD(v54) = Nodes;
          v50 = (char *)this + 193;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v24,
            (__int64)&byte_1800317F7,
            v25,
            v26,
            &v50,
            (__int64)&v54,
            &v51,
            &v52,
            &v53,
            (__int64)&v48,
            &v49);
        }
        if ( Nodes >= 0 )
        {
          for ( i = 0; i < v55; ++i )
          {
            if ( v6 )
            {
              ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
              v58 = 0;
            }
            Nodes = SdpXmlNextNode(v5, &v58);
            v6 = v58;
            if ( Nodes < 0 )
              break;
            Nodes = DiagnosticRunner::ResolveProblem(this, v66, v58, &v56);
            if ( Nodes < 0 )
              break;
          }
          if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v24, v23, v25) )
          {
            v49 = (BSTR)((char *)this + 64);
            LODWORD(v54) = 1134;
            v53 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\diagnosticrunner\\lib\\diagnosticrunner.cpp";
            v52 = "DiagnosticRunner::ResolveProblems";
            v51 = "ResolveProblems - Resolved Each Problem";
            v47 = Nodes;
            v50 = (char *)this + 193;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v28,
              (__int64)&dword_180031784,
              v29,
              v30,
              &v50,
              (__int64)&v47,
              &v51,
              &v52,
              &v53,
              (__int64)&v54,
              &v49);
          }
          if ( Nodes >= 0 && v56 == 1 )
          {
            (*(void (__fastcall **)(DiagnosticRunner *, __int64))(*(_QWORD *)this + 144LL))(this, 6);
            p_Nodes = (struct IXMLDOMDocument2 *)&Nodes;
            v61 = &v66;
            p_bstrString = &bstrString;
            v31 = (OLECHAR *)operator new(0x120u);
            v49 = v31;
            if ( v31 )
              v32 = std::_Task_async_state_void_::_Task_async_state_void__std::_Fake_no_copy_callable_adapter__lambda_500f122f6c2ed47e2ec1ed2575b23773_____(
                      v31,
                      &p_Nodes);
            else
              v32 = 0;
            v63 = v32;
            v64 = 0;
            v65 = 0;
            v33 = *(_QWORD *)std::_Promise<int>::_Get_state_for_future(&v63);
            p_Nodes = (struct IXMLDOMDocument2 *)v33;
            LOBYTE(v61) = 1;
            if ( v33 )
              _InterlockedIncrement((volatile signed __int32 *)(v33 + 8));
            std::_State_manager<int>::~_State_manager<int>(&v63);
            v49 = (BSTR)*((int *)this + 84);
            if ( (unsigned int)std::_State_manager<int>::wait_for<__int64,std::ratio<1,1000>>(&p_Nodes, &v49) == 1 )
              (*(void (__fastcall **)(struct IScriptedDiagnosticExecution *))(*(_QWORD *)v66 + 168LL))(v66);
            if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v35, v34, v36) )
            {
              v49 = bstrString;
              v53 = (char *)this + 64;
              LODWORD(v54) = 1161;
              v52 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\diagnosticrunner\\lib\\diagnosticrunner.cpp";
              v51 = "DiagnosticRunner::ResolveProblems";
              v50 = "ResolveProblems - Verifying the results";
              v47 = Nodes;
              v57 = (char *)this + 193;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
                v37,
                (__int64)byte_1800316FD,
                v38,
                v39,
                &v57,
                (__int64)&v47,
                &v50,
                &v51,
                &v52,
                (__int64)&v54,
                &v53,
                &v49);
            }
            std::_State_manager<int>::~_State_manager<int>(&p_Nodes);
          }
        }
      }
    }
    if ( v16 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v16->lpVtbl->Release)(v16);
    if ( v5 )
      ((void (__fastcall *)(struct IXMLDOMNodeList *))v5->lpVtbl->Release)(v5);
    if ( v6 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
  }
  SysFreeString(bstrString);
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v41, v40, v42) )
  {
    v49 = (BSTR)((char *)this + 64);
    LODWORD(v54) = 1176;
    v53 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\diagnosticrunner\\lib\\diagnosticrunner.cpp";
    v52 = "DiagnosticRunner::ResolveProblems";
    v51 = "Execute - resolved the problems";
    v47 = Nodes;
    v50 = (char *)this + 193;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v43,
      (__int64)word_18003168A,
      v44,
      v45,
      &v50,
      (__int64)&v47,
      &v51,
      &v52,
      &v53,
      (__int64)&v54,
      &v49);
  }
  return (unsigned int)Nodes;
}

```

## disassembly

```asm
0x180021270  mov     rax, rsp
0x180021273  mov     [rax+8], rbx
0x180021277  mov     [rax+18h], rsi
0x18002127b  mov     [rax+10h], rdx
0x18002127f  push    rbp
0x180021280  push    rdi
0x180021281  push    r12
0x180021283  push    r14
0x180021285  push    r15
0x180021287  lea     rbp, [rax-5Fh]
0x18002128b  sub     rsp, 0F0h
0x180021292  mov     r14, r8
0x180021295  mov     rsi, rcx
0x180021298  xor     r12d, r12d
0x18002129b  mov     [rbp+57h+arg_18], r12d
0x18002129f  mov     [rbp+57h+var_58], r12
0x1800212a3  mov     edi, r12d
0x1800212a6  mov     [rbp+57h+var_80], r12
0x1800212aa  mov     ebx, r12d
0x1800212ad  mov     [rbp+57h+var_68], rbx
0x1800212b1  mov     [rbp+57h+bstrString], r12
0x1800212b5  mov     [rbp+57h+var_78], r12d
0x1800212b9  mov     [rbp+57h+var_74], r12d
0x1800212bd  lea     r15, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x1800212c4  lea     r8, aDiagnosticrunn_0; "DiagnosticRunner::ResolveProblems"
0x1800212cb  test    rdx, rdx
0x1800212ce  jz      short loc_1800212D9
0x1800212d0  test    r14, r14
0x1800212d3  jnz     loc_180021380
0x1800212d9  mov     [rbp+57h+arg_18], 80070057h
0x1800212e0  mov     eax, cs:dword_180039000
0x1800212e6  cmp     eax, 5
0x1800212e9  jbe     loc_180021376
0x1800212ef  call    _tlgKeywordOn
0x1800212f4  test    al, al
0x1800212f6  jz      short loc_180021376
0x1800212f8  lea     rax, [rsi+40h]
0x1800212fc  mov     [rbp+57h+var_70], rax
0x180021300  mov     [rbp+57h+var_AC], 432h
0x180021307  mov     [rbp+57h+var_A0], r15
0x18002130b  mov     [rbp+57h+var_98], r8
0x18002130f  lea     rax, aResolveproblem_10; "ResolveProblems - Invalid Arguments"
0x180021316  mov     [rbp+57h+var_90], rax
0x18002131a  mov     eax, [rbp+57h+arg_18]
0x18002131d  mov     [rbp+57h+var_B0], eax
0x180021320  lea     rax, [rsi+0C1h]
0x180021327  mov     [rbp+57h+var_88], rax
0x18002132b  lea     rax, [rbp+57h+var_70]
0x18002132f  mov     [rsp+110h+var_C0], rax
0x180021334  lea     rax, [rbp+57h+var_AC]
0x180021338  mov     [rsp+110h+var_C8], rax
0x18002133d  lea     rax, [rbp+57h+var_A0]
0x180021341  mov     [rsp+110h+var_D0], rax
0x180021346  lea     rax, [rbp+57h+var_98]
0x18002134a  mov     [rsp+110h+var_D8], rax
0x18002134f  lea     rax, [rbp+57h+var_90]
0x180021353  mov     [rsp+110h+var_E0], rax
0x180021358  lea     rax, [rbp+57h+var_B0]
0x18002135c  mov     [rsp+110h+var_E8], rax
0x180021361  lea     rax, [rbp+57h+var_88]
0x180021365  mov     [rsp+110h+var_F0], rax
0x18002136a  lea     rdx, dword_18003196C
0x180021371  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180021376  cmp     [rbp+57h+arg_18], r12d
0x18002137a  jl      loc_1800218C8
0x180021380  lea     rdx, [rbp+57h+var_58]; struct IXMLDOMDocument2 **
0x180021384  mov     rcx, r14; psz
0x180021387  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x18002138c  mov     [rbp+57h+arg_18], eax
0x18002138f  mov     eax, cs:dword_180039000
0x180021395  cmp     eax, 5
0x180021398  jbe     loc_18002143D
0x18002139e  call    _tlgKeywordOn
0x1800213a3  test    al, al
0x1800213a5  jz      loc_18002143D
0x1800213ab  mov     [rbp+57h+var_88], r14
0x1800213af  lea     rax, [rsi+40h]
0x1800213b3  mov     [rbp+57h+var_90], rax
0x1800213b7  mov     [rbp+57h+var_B0], 43Dh
0x1800213be  mov     [rbp+57h+var_98], r15
0x1800213c2  lea     rax, aDiagnosticrunn_0; "DiagnosticRunner::ResolveProblems"
0x1800213c9  mov     [rbp+57h+var_A0], rax
0x1800213cd  lea     rax, aResolveproblem_1; "ResolveProblems - Create Problem List X"...
0x1800213d4  mov     [rbp+57h+var_70], rax
0x1800213d8  mov     eax, [rbp+57h+arg_18]
0x1800213db  mov     [rbp+57h+var_AC], eax
0x1800213de  lea     rax, [rsi+0C1h]
0x1800213e5  mov     [rbp+57h+var_A8], rax
0x1800213e9  lea     rax, [rbp+57h+var_88]
0x1800213ed  mov     [rsp+110h+var_B8], rax
0x1800213f2  lea     rax, [rbp+57h+var_90]
0x1800213f6  mov     [rsp+110h+var_C0], rax
0x1800213fb  lea     rax, [rbp+57h+var_B0]
0x1800213ff  mov     [rsp+110h+var_C8], rax
0x180021404  lea     rax, [rbp+57h+var_98]
0x180021408  mov     [rsp+110h+var_D0], rax
0x18002140d  lea     rax, [rbp+57h+var_A0]
0x180021411  mov     [rsp+110h+var_D8], rax
0x180021416  lea     rax, [rbp+57h+var_70]
0x18002141a  mov     [rsp+110h+var_E0], rax
0x18002141f  lea     rax, [rbp+57h+var_AC]
0x180021423  mov     [rsp+110h+var_E8], rax
0x180021428  lea     rax, [rbp+57h+var_A8]
0x18002142c  mov     [rsp+110h+var_F0], rax
0x180021431  lea     rdx, byte_1800318EF
0x180021438  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18002143d  mov     r15, [rbp+57h+var_58]
0x180021441  cmp     [rbp+57h+arg_18], r12d
0x180021445  jl      loc_180021885
0x18002144b  lea     r9, [rbp+57h+var_80]; struct IXMLDOMNodeList **
0x18002144f  xor     r8d, r8d; struct IXMLDOMNode *
0x180021452  mov     rdx, r15; struct IXMLDOMDocument2 *
0x180021455  lea     rcx, aRootcausesRoot; "/Rootcauses/Rootcause"
0x18002145c  call    ?SdpXmlGetNodes@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@@Z; SdpXmlGetNodes(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *)
0x180021461  mov     [rbp+57h+arg_18], eax
0x180021464  mov     eax, cs:dword_180039000
0x18002146a  cmp     eax, 5
0x18002146d  jbe     loc_18002150E
0x180021473  call    _tlgKeywordOn
0x180021478  test    al, al
0x18002147a  jz      loc_18002150E
0x180021480  lea     rax, [rsi+40h]
0x180021484  mov     [rbp+57h+var_A8], rax
0x180021488  mov     [rbp+57h+var_B0], 44Bh
0x18002148f  lea     r14, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180021496  mov     [rbp+57h+var_88], r14
0x18002149a  lea     rax, aDiagnosticrunn_0; "DiagnosticRunner::ResolveProblems"
0x1800214a1  mov     [rbp+57h+var_90], rax
0x1800214a5  lea     rax, aResolveproblem_2; "ResolveProblems - Get Rootcause node"
0x1800214ac  mov     [rbp+57h+var_98], rax
0x1800214b0  mov     eax, [rbp+57h+arg_18]
0x1800214b3  mov     [rbp+57h+var_AC], eax
0x1800214b6  lea     rax, [rsi+0C1h]
0x1800214bd  mov     [rbp+57h+var_A0], rax
0x1800214c1  lea     rax, [rbp+57h+var_A8]
0x1800214c5  mov     [rsp+110h+var_C0], rax
0x1800214ca  lea     rax, [rbp+57h+var_B0]
0x1800214ce  mov     [rsp+110h+var_C8], rax
0x1800214d3  lea     rax, [rbp+57h+var_88]
0x1800214d7  mov     [rsp+110h+var_D0], rax
0x1800214dc  lea     rax, [rbp+57h+var_90]
0x1800214e0  mov     [rsp+110h+var_D8], rax
0x1800214e5  lea     rax, [rbp+57h+var_98]
0x1800214e9  mov     [rsp+110h+var_E0], rax
0x1800214ee  lea     rax, [rbp+57h+var_AC]
0x1800214f2  mov     [rsp+110h+var_E8], rax
0x1800214f7  lea     rax, [rbp+57h+var_A0]
0x1800214fb  mov     [rsp+110h+var_F0], rax
0x180021500  lea     rdx, dword_18003187C
0x180021507  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002150c  jmp     short loc_180021515
0x18002150e  lea     r14, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180021515  mov     rdi, [rbp+57h+var_80]
0x180021519  cmp     [rbp+57h+arg_18], r12d
0x18002151d  jl      loc_180021885
0x180021523  mov     rax, [rdi]
0x180021526  lea     rdx, [rbp+57h+var_78]
0x18002152a  mov     rcx, rdi
0x18002152d  mov     rax, [rax+40h]
0x180021531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021536  mov     [rbp+57h+arg_18], eax
0x180021539  mov     eax, cs:dword_180039000
0x18002153f  cmp     eax, 5
0x180021542  jbe     loc_1800215E9
0x180021548  call    _tlgKeywordOn
0x18002154d  test    al, al
0x18002154f  jz      loc_1800215E9
0x180021555  mov     eax, [rbp+57h+var_78]
0x180021558  mov     [rbp+57h+var_B0], eax
0x18002155b  lea     rax, [rsi+40h]
0x18002155f  mov     [rbp+57h+var_A8], rax
0x180021563  mov     [rbp+57h+var_AC], 456h
0x18002156a  mov     [rbp+57h+var_88], r14
0x18002156e  lea     rax, aDiagnosticrunn_0; "DiagnosticRunner::ResolveProblems"
0x180021575  mov     [rbp+57h+var_90], rax
0x180021579  lea     rax, aResolveproblem_0; "ResolveProblems - get Rootcause node le"...
0x180021580  mov     [rbp+57h+var_98], rax
0x180021584  mov     eax, [rbp+57h+arg_18]
0x180021587  mov     dword ptr [rbp+57h+var_80], eax
0x18002158a  lea     rax, [rsi+0C1h]
0x180021591  mov     [rbp+57h+var_A0], rax
0x180021595  lea     rax, [rbp+57h+var_B0]
0x180021599  mov     [rsp+110h+var_B8], rax
0x18002159e  lea     rax, [rbp+57h+var_A8]
0x1800215a2  mov     [rsp+110h+var_C0], rax
0x1800215a7  lea     rax, [rbp+57h+var_AC]
0x1800215ab  mov     [rsp+110h+var_C8], rax
0x1800215b0  lea     rax, [rbp+57h+var_88]
0x1800215b4  mov     [rsp+110h+var_D0], rax
0x1800215b9  lea     rax, [rbp+57h+var_90]
0x1800215bd  mov     [rsp+110h+var_D8], rax
0x1800215c2  lea     rax, [rbp+57h+var_98]
0x1800215c6  mov     [rsp+110h+var_E0], rax
0x1800215cb  lea     rax, [rbp+57h+var_80]
0x1800215cf  mov     [rsp+110h+var_E8], rax
0x1800215d4  lea     rax, [rbp+57h+var_A0]
0x1800215d8  mov     [rsp+110h+var_F0], rax
0x1800215dd  lea     rdx, byte_1800317F7
0x1800215e4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@333434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800215e9  cmp     [rbp+57h+arg_18], r12d
0x1800215ed  jl      loc_180021885
0x1800215f3  mov     r14d, r12d
0x1800215f6  cmp     [rbp+57h+var_78], r12d
0x1800215fa  jle     short loc_18002164E
0x1800215fc  test    rbx, rbx
0x1800215ff  jz      short loc_180021614
0x180021601  mov     rax, [rbx]
0x180021604  mov     rcx, rbx
0x180021607  mov     rax, [rax+10h]
0x18002160b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021610  mov     [rbp+57h+var_68], r12
0x180021614  lea     rdx, [rbp+57h+var_68]; struct IXMLDOMNode **
0x180021618  mov     rcx, rdi; struct IXMLDOMNodeList *
0x18002161b  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180021620  mov     [rbp+57h+arg_18], eax
0x180021623  mov     rbx, [rbp+57h+var_68]
0x180021627  test    eax, eax
0x180021629  js      short loc_18002164E
0x18002162b  lea     r9, [rbp+57h+var_74]; int *
0x18002162f  mov     r8, rbx; struct IXMLDOMNode *
0x180021632  mov     rdx, [rbp+57h+arg_8]; struct IScriptedDiagnosticExecution *
0x180021636  mov     rcx, rsi; this
0x180021639  call    ?ResolveProblem@DiagnosticRunner@@AEAAJPEAUIScriptedDiagnosticExecution@@PEAUIXMLDOMNode@@PEAH@Z; DiagnosticRunner::ResolveProblem(IScriptedDiagnosticExecution *,IXMLDOMNode *,int *)
0x18002163e  mov     [rbp+57h+arg_18], eax
0x180021641  test    eax, eax
0x180021643  js      short loc_18002164E
0x180021645  inc     r14d
0x180021648  cmp     r14d, [rbp+57h+var_78]
0x18002164c  jl      short loc_1800215FC
0x18002164e  mov     eax, cs:dword_180039000
0x180021654  cmp     eax, 5
0x180021657  jbe     loc_1800216F8
0x18002165d  call    _tlgKeywordOn
0x180021662  test    al, al
0x180021664  jz      loc_1800216F8
0x18002166a  lea     rax, [rsi+40h]
0x18002166e  mov     [rbp+57h+var_A8], rax
0x180021672  mov     dword ptr [rbp+57h+var_80], 46Eh
0x180021679  lea     r14, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180021680  mov     [rbp+57h+var_88], r14
0x180021684  lea     rax, aDiagnosticrunn_0; "DiagnosticRunner::ResolveProblems"
0x18002168b  mov     [rbp+57h+var_90], rax
0x18002168f  lea     rax, aResolveproblem_5; "ResolveProblems - Resolved Each Problem"
0x180021696  mov     [rbp+57h+var_98], rax
0x18002169a  mov     eax, [rbp+57h+arg_18]
0x18002169d  mov     [rbp+57h+var_B0], eax
0x1800216a0  lea     rax, [rsi+0C1h]
0x1800216a7  mov     [rbp+57h+var_A0], rax
0x1800216ab  lea     rax, [rbp+57h+var_A8]
0x1800216af  mov     [rsp+110h+var_C0], rax
0x1800216b4  lea     rax, [rbp+57h+var_80]
0x1800216b8  mov     [rsp+110h+var_C8], rax
0x1800216bd  lea     rax, [rbp+57h+var_88]
0x1800216c1  mov     [rsp+110h+var_D0], rax
0x1800216c6  lea     rax, [rbp+57h+var_90]
0x1800216ca  mov     [rsp+110h+var_D8], rax
0x1800216cf  lea     rax, [rbp+57h+var_98]
0x1800216d3  mov     [rsp+110h+var_E0], rax
0x1800216d8  lea     rax, [rbp+57h+var_B0]
0x1800216dc  mov     [rsp+110h+var_E8], rax
0x1800216e1  lea     rax, [rbp+57h+var_A0]
0x1800216e5  mov     [rsp+110h+var_F0], rax
0x1800216ea  lea     rdx, dword_180031784
0x1800216f1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800216f6  jmp     short loc_1800216FF
0x1800216f8  lea     r14, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x1800216ff  cmp     [rbp+57h+arg_18], r12d
0x180021703  jl      loc_180021885
0x180021709  cmp     [rbp+57h+var_74], 1
0x18002170d  jnz     loc_180021885
0x180021713  mov     rax, [rsi]
0x180021716  mov     edx, 6
0x18002171b  mov     rcx, rsi
0x18002171e  mov     rax, [rax+90h]
0x180021725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002172a  lea     rax, [rbp+57h+arg_18]
0x18002172e  mov     [rbp+57h+var_58], rax
0x180021732  lea     rax, [rbp+57h+arg_8]
0x180021736  mov     [rbp+57h+var_50], rax
0x18002173a  lea     rax, [rbp+57h+bstrString]
0x18002173e  mov     [rbp+57h+var_48], rax
0x180021742  mov     ecx, 120h; Size
0x180021747  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002174c  mov     [rbp+57h+var_A8], rax
0x180021750  test    rax, rax
0x180021753  jz      short loc_180021763
0x180021755  lea     rdx, [rbp+57h+var_58]
0x180021759  mov     rcx, rax
0x18002175c  call    std___Task_async_state_void____Task_async_state_void__std___Fake_no_copy_callable_adapter__lambda_500f122f6c2ed47e2ec1ed2575b23773_____
0x180021761  jmp     short loc_180021766
0x180021763  mov     rax, r12
0x180021766  mov     [rbp+57h+var_40], rax
0x18002176a  mov     [rbp+57h+var_38], r12b
0x18002176e  mov     [rbp+57h+var_30], r12b
0x180021772  lea     rcx, [rbp+57h+var_40]
0x180021776  call    ?_Get_state_for_future@?$_Promise@H@std@@QEAAAEAV?$_State_manager@H@2@XZ; std::_Promise<int>::_Get_state_for_future(void)
0x18002177b  mov     rcx, [rax]
0x18002177e  mov     [rbp+57h+var_58], rcx
0x180021782  mov     byte ptr [rbp+57h+var_50], 1
0x180021786  test    rcx, rcx
  ... truncated ...
```
