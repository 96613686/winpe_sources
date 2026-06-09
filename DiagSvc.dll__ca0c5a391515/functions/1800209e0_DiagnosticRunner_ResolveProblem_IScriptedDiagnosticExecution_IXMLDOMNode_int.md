# DiagnosticRunner::ResolveProblem(IScriptedDiagnosticExecution *,IXMLDOMNode *,int *)

- ea: `0x1800209e0`
- end: `0x18002125e`
- name: `?ResolveProblem@DiagnosticRunner@@AEAAJPEAUIScriptedDiagnosticExecution@@PEAUIXMLDOMNode@@PEAH@Z`
- size: `2174`
- prototype: `int(DiagnosticRunner *__hidden this, struct IScriptedDiagnosticExecution *, struct IXMLDOMNode *, int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180021270`

## callees

- `0x180001720`
- `0x180001e7c`
- `0x180001fec`
- `0x18000216c`
- `0x180003378`
- `0x18001d294`
- `0x18001d648`
- `0x18001e04c`
- `0x1800209e0`
- `0x180024f14`
- `0x180025020`
- `0x180025158`
- `0x180025500`
- `0x180027010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180020cc5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180020cc5`
- `OLEAUT32!__imp_SysFreeString` at `0x180020e6f`
- `OLEAUT32!__imp_SysFreeString` at `0x180021230`
- `OLEAUT32!__imp_SysFreeString` at `0x18002123a`
- `OLEAUT32!__imp_SysFreeString` at `0x180020e6f`
- `OLEAUT32!__imp_SysFreeString` at `0x180021230`
- `OLEAUT32!__imp_SysFreeString` at `0x18002123a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DiagnosticRunner::ResolveProblem(
        DiagnosticRunner *this,
        struct IXMLDOMDocument2 *a2,
        struct IXMLDOMNode *a3,
        int *a4)
{
  struct IXMLDOMNodeList *v7; // r14
  struct IXMLDOMNode *v8; // rsi
  struct IXMLDOMNode *v9; // rbx
  struct IXMLDOMNode *v10; // rdi
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  const char *v14; // r10
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  struct IXMLDOMDocument2 *v27; // rdx
  __int64 v28; // rcx
  struct IXMLDOMNodeList *v29; // r12
  const char *v30; // r8
  __int64 v31; // rcx
  __int64 v32; // r9
  int v33; // r13d
  int ChildNodes; // eax
  struct IXMLDOMDocument2 *v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // r9
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // r8
  __int64 v42; // rcx
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 v45; // rcx
  __int64 v46; // r9
  int v48; // [rsp+70h] [rbp-90h] BYREF
  int v49; // [rsp+74h] [rbp-8Ch] BYREF
  const char *v50; // [rsp+78h] [rbp-88h] BYREF
  const char *v51; // [rsp+80h] [rbp-80h] BYREF
  const char *v52; // [rsp+88h] [rbp-78h] BYREF
  BSTR v53; // [rsp+90h] [rbp-70h] BYREF
  int v54; // [rsp+98h] [rbp-68h] BYREF
  BSTR v55; // [rsp+A0h] [rbp-60h] BYREF
  struct IXMLDOMNodeList *v56; // [rsp+A8h] [rbp-58h] BYREF
  const char *v57; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v58; // [rsp+B8h] [rbp-48h] BYREF
  BSTR bstrString; // [rsp+C0h] [rbp-40h] BYREF
  struct IXMLDOMNode *v60; // [rsp+C8h] [rbp-38h] BYREF
  struct IXMLDOMNode *v61; // [rsp+D0h] [rbp-30h] BYREF
  BSTR v62; // [rsp+D8h] [rbp-28h] BYREF
  struct IXMLDOMNode *v63; // [rsp+E0h] [rbp-20h] BYREF
  struct IXMLDOMNodeList *v64; // [rsp+E8h] [rbp-18h] BYREF
  struct IXMLDOMNode *v65; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v66[16]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v67[9]; // [rsp+108h] [rbp+8h] BYREF
  struct IXMLDOMDocument2 *v68; // [rsp+168h] [rbp+68h] BYREF
  int Node; // [rsp+178h] [rbp+78h] BYREF

  v68 = a2;
  Node = 0;
  v7 = 0;
  v64 = 0;
  v58 = 0;
  v56 = 0;
  v8 = 0;
  v63 = 0;
  v9 = 0;
  v61 = 0;
  v65 = 0;
  v10 = 0;
  v60 = 0;
  bstrString = 0;
  v54 = 0;
  v62 = 0;
  *a4 = 0;
  if ( !a2 || !a3 )
  {
    Node = -2147024809;
    if ( (unsigned int)dword_180039000 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(this, a2, 0) )
      {
        v57 = (char *)this + 64;
        v49 = 1209;
        v50 = (const char *)v13;
        v51 = v14;
        v52 = "ResolveProblem - Invalid Arguments";
        v48 = Node;
        v53 = (BSTR)((char *)this + 193);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v11,
          (__int64)&byte_180031617,
          v12,
          v13,
          &v53,
          (__int64)&v48,
          &v52,
          &v51,
          &v50,
          (__int64)&v49,
          &v57);
      }
    }
  }
  Node = SdpXmlGetNode(L"Status", a2, a3, &v65);
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v16, v15, v17) )
  {
    v53 = (BSTR)((char *)this + 64);
    v48 = 1222;
    v52 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\diagnosticrunner\\lib\\diagnosticrunner.cpp";
    v51 = "DiagnosticRunner::ResolveProblem";
    v50 = "ResolveProblem - Get Problem Status Node";
    v49 = Node;
    v57 = (char *)this + 193;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v18,
      (__int64)&dword_1800315A4,
      v19,
      v20,
      &v57,
      (__int64)&v49,
      &v50,
      &v51,
      &v52,
      (__int64)&v48,
      &v53);
  }
  if ( Node < 0 )
    goto LABEL_64;
  Node = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v65->lpVtbl->get_text)(v65, &v62);
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v22, v21, v23) )
  {
    v53 = v62;
    v52 = (char *)this + 64;
    v48 = 1232;
    v51 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\diagnosticrunner\\lib\\diagnosticrunner.cpp";
    v50 = "DiagnosticRunner::ResolveProblem";
    v57 = "ResolveProblem - Get Text from Problem Status Node";
    v49 = Node;
    v55 = (BSTR)((char *)this + 193);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
      v24,
      (__int64)&word_18003151E,
      v25,
      v26,
      &v55,
      (__int64)&v49,
      &v57,
      &v50,
      &v51,
      (__int64)&v48,
      &v52,
      &v53);
  }
  if ( Node < 0 || (unsigned int)_o__wcsicmp(v62, L"Detected") )
    goto LABEL_64;
  Node = SdpXmlGetNodes(L"./Resolutions/Resolution", 0, (struct IXMLDOMDocument2 *)a3, &v56);
  v29 = v56;
  if ( Node >= 0 )
    Node = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, int *))v56->lpVtbl->get_length)(v56, &v54);
  if ( v54 > 0 )
  {
    *a4 = 1;
    (*(void (__fastcall **)(DiagnosticRunner *, __int64))(*(_QWORD *)this + 144LL))(this, 5);
  }
  v30 = "ResolveProblem - Get Resolution Nodes";
  if ( (unsigned int)dword_180039000 > 5
    && (unsigned __int8)tlgKeywordOn(v28, v27, "ResolveProblem - Get Resolution Nodes") )
  {
    v48 = v54;
    v55 = (BSTR)((char *)this + 64);
    v49 = 1261;
    v53 = (BSTR)"onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\diagnosticrunner\\lib\\diagnosticrunner.cpp";
    v52 = "DiagnosticRunner::ResolveProblem";
    v51 = v30;
    LODWORD(v56) = Node;
    v50 = (char *)this + 193;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v31,
      (__int64)&word_180031496,
      (__int64)v30,
      v32,
      &v50,
      (__int64)&v56,
      &v51,
      &v52,
      &v53,
      (__int64)&v49,
      &v55);
  }
  if ( Node < 0 )
    goto LABEL_56;
  v33 = 0;
  if ( v54 <= 0 )
    goto LABEL_56;
  while ( 1 )
  {
    if ( v8 )
    {
      ((void (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMDocument2 *, const char *))v8->lpVtbl->Release)(
        v8,
        v27,
        v30);
      v63 = 0;
    }
    if ( v9 )
    {
      ((void (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMDocument2 *, const char *))v9->lpVtbl->Release)(
        v9,
        v27,
        v30);
      v9 = 0;
      v61 = 0;
    }
    if ( v10 )
    {
      ((void (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMDocument2 *, const char *))v10->lpVtbl->Release)(
        v10,
        v27,
        v30);
      v10 = 0;
      v60 = 0;
    }
    if ( v7 )
    {
      ((void (__fastcall *)(struct IXMLDOMNodeList *, struct IXMLDOMDocument2 *, const char *))v7->lpVtbl->Release)(
        v7,
        v27,
        v30);
      v7 = 0;
      v64 = 0;
    }
    SysFreeString(bstrString);
    ChildNodes = SdpXmlNextNode(v29, &v63);
    Node = ChildNodes;
    v8 = v63;
    if ( ChildNodes >= 0 )
    {
      ChildNodes = SdpXmlGetNode(L"./ID", v27, v63, &v61);
      Node = ChildNodes;
      v9 = v61;
      if ( ChildNodes >= 0 )
      {
        ChildNodes = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v61->lpVtbl->get_text)(v61, &bstrString);
        Node = ChildNodes;
        if ( ChildNodes >= 0 )
        {
          ChildNodes = SdpXmlGetNode(L"./Script", v27, v8, &v60);
          Node = ChildNodes;
          v10 = v60;
          if ( ChildNodes >= 0 )
          {
            ChildNodes = SdpXmlGetChildNodes(v35, v60, &v64, &v58);
            Node = ChildNodes;
            v7 = v64;
          }
        }
      }
    }
    v36 = (unsigned int)ChildNodes;
    if ( v58 )
      break;
    if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn((unsigned int)ChildNodes, v27, v30) )
    {
      v55 = (BSTR)((char *)this + 64);
      LODWORD(v56) = 1314;
      v53 = (BSTR)"onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\diagnosticrunner\\lib\\diagnosticrunner.cpp";
      v52 = "DiagnosticRunner::ResolveProblem";
      v51 = "ResolveProblem - No Resolution Id Nodes";
      v48 = Node;
      v50 = (char *)this + 193;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v37,
        (__int64)byte_180031423,
        (__int64)v30,
        v38,
        &v50,
        (__int64)&v48,
        &v51,
        &v52,
        &v53,
        (__int64)&v56,
        &v55);
    }
LABEL_49:
    if ( ++v33 >= v54 )
      goto LABEL_54;
  }
  if ( ChildNodes >= 0 )
  {
    v67[0] = &Node;
    v67[1] = &v68;
    v67[2] = &bstrString;
    std::async__lambda_9d1b1523b07cc8425f3c5ec85e556455___(v66, v27, v67);
    v55 = (BSTR)*((int *)this + 84);
    if ( (unsigned int)std::_State_manager<int>::wait_for<__int64,std::ratio<1,1000>>(v66, &v55) == 1 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v68->lpVtbl->appendChild)(v68);
    if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v40, v39, v41) )
    {
      v55 = bstrString;
      LODWORD(v56) = v33;
      v53 = (BSTR)((char *)this + 64);
      v48 = 1344;
      v52 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\diagnosticrunner\\lib\\diagnosticrunner.cpp";
      v51 = "DiagnosticRunner::ResolveProblem";
      v50 = "ResolveProblem - Get Resolution Nodes";
      v49 = Node;
      v57 = (char *)this + 193;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v42,
        (__int64)&word_18003138E,
        v43,
        v44,
        &v57,
        (__int64)&v49,
        &v50,
        &v51,
        &v52,
        (__int64)&v48,
        &v53,
        (__int64)&v56,
        &v55);
    }
    std::_State_manager<int>::~_State_manager<int>(v66);
    ChildNodes = Node;
  }
  if ( ChildNodes >= 0 )
    goto LABEL_49;
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v36, v27, v30) )
  {
    v55 = (BSTR)((char *)this + 64);
    LODWORD(v56) = 1353;
    v53 = (BSTR)"onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\diagnosticrunner\\lib\\diagnosticrunner.cpp";
    v52 = "DiagnosticRunner::ResolveProblem";
    v51 = "ResolveProblem - Failed to Resolve";
    v48 = Node;
    v50 = (char *)this + 193;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v45,
      (__int64)byte_18003131B,
      (__int64)v30,
      v46,
      &v50,
      (__int64)&v48,
      &v51,
      &v52,
      &v53,
      (__int64)&v56,
      &v55);
  }
LABEL_54:
  if ( v7 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v7->lpVtbl->Release)(v7);
LABEL_56:
  if ( v29 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *, struct IXMLDOMDocument2 *, const char *))v29->lpVtbl->Release)(
      v29,
      v27,
      v30);
  if ( v8 )
    ((void (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMDocument2 *, const char *))v8->lpVtbl->Release)(
      v8,
      v27,
      v30);
  if ( v9 )
    ((void (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMDocument2 *, const char *))v9->lpVtbl->Release)(
      v9,
      v27,
      v30);
  if ( v10 )
    ((void (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMDocument2 *, const char *))v10->lpVtbl->Release)(
      v10,
      v27,
      v30);
LABEL_64:
  if ( v65 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v65->lpVtbl->Release)(v65);
  SysFreeString(v62);
  SysFreeString(bstrString);
  return (unsigned int)Node;
}

```

## disassembly

```asm
0x1800209e0  mov     [rsp-8+arg_0], rbx
0x1800209e5  mov     [rsp-8+arg_8], rdx
0x1800209ea  push    rbp
0x1800209eb  push    rsi
0x1800209ec  push    rdi
0x1800209ed  push    r12
0x1800209ef  push    r13
0x1800209f1  push    r14
0x1800209f3  push    r15
0x1800209f5  lea     rbp, [rsp-20h]
0x1800209fa  sub     rsp, 120h
0x180020a01  mov     r13, r9
0x180020a04  mov     r12, r8
0x180020a07  mov     r15, rcx
0x180020a0a  xor     r8d, r8d
0x180020a0d  mov     [rbp+50h+arg_18], r8d
0x180020a11  mov     r14d, r8d
0x180020a14  mov     [rbp+50h+var_68], r8
0x180020a18  mov     [rbp+50h+var_98], r8d
0x180020a1c  mov     [rbp+50h+var_A8], r8
0x180020a20  mov     esi, r8d
0x180020a23  mov     [rbp+50h+var_70], r8
0x180020a27  mov     ebx, r8d
0x180020a2a  mov     [rbp+50h+var_80], rbx
0x180020a2e  mov     [rbp+50h+var_60], r8
0x180020a32  mov     edi, r8d
0x180020a35  mov     [rbp+50h+var_88], r8
0x180020a39  mov     [rbp+50h+bstrString], r8
0x180020a3d  mov     [rbp+50h+var_B8], r8d
0x180020a41  mov     [rbp+50h+var_78], r8
0x180020a45  mov     [r9], r8d
0x180020a48  lea     r9, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180020a4f  lea     r10, aDiagnosticrunn_3; "DiagnosticRunner::ResolveProblem"
0x180020a56  test    rdx, rdx
0x180020a59  jz      short loc_180020A64
0x180020a5b  test    r12, r12
0x180020a5e  jnz     loc_180020B0B
0x180020a64  mov     [rbp+50h+arg_18], 80070057h
0x180020a6b  mov     eax, cs:dword_180039000
0x180020a71  cmp     eax, 5
0x180020a74  jbe     loc_180020B0B
0x180020a7a  call    _tlgKeywordOn
0x180020a7f  test    al, al
0x180020a81  jz      loc_180020B0B
0x180020a87  lea     rax, [r15+40h]
0x180020a8b  mov     [rbp+50h+var_A0], rax
0x180020a8f  mov     [rsp+150h+var_DC], 4B9h
0x180020a97  mov     [rsp+150h+var_D8], r9
0x180020a9c  mov     [rbp+50h+var_D0], r10
0x180020aa0  lea     rax, aResolveproblem_9; "ResolveProblem - Invalid Arguments"
0x180020aa7  mov     [rbp+50h+var_C8], rax
0x180020aab  mov     eax, [rbp+50h+arg_18]
0x180020aae  mov     [rsp+150h+var_E0], eax
0x180020ab2  lea     rax, [r15+0C1h]
0x180020ab9  mov     [rbp+50h+var_C0], rax
0x180020abd  lea     rax, [rbp+50h+var_A0]
0x180020ac1  mov     [rsp+150h+var_100], rax
0x180020ac6  lea     rax, [rsp+150h+var_DC]
0x180020acb  mov     [rsp+150h+var_108], rax
0x180020ad0  lea     rax, [rsp+150h+var_D8]
0x180020ad5  mov     [rsp+150h+var_110], rax
0x180020ada  lea     rax, [rbp+50h+var_D0]
0x180020ade  mov     [rsp+150h+var_118], rax
0x180020ae3  lea     rax, [rbp+50h+var_C8]
0x180020ae7  mov     [rsp+150h+var_120], rax
0x180020aec  lea     rax, [rsp+150h+var_E0]
0x180020af1  mov     [rsp+150h+var_128], rax
0x180020af6  lea     rax, [rbp+50h+var_C0]
0x180020afa  mov     [rsp+150h+var_130], rax
0x180020aff  lea     rdx, byte_180031617
0x180020b06  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180020b0b  lea     r9, [rbp+50h+var_60]; struct IXMLDOMNode **
0x180020b0f  mov     r8, r12; struct IXMLDOMNode *
0x180020b12  lea     rcx, aStatus; "Status"
0x180020b19  call    ?SdpXmlGetNode@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAU2@@Z; SdpXmlGetNode(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNode * *)
0x180020b1e  mov     [rbp+50h+arg_18], eax
0x180020b21  mov     eax, cs:dword_180039000
0x180020b27  cmp     eax, 5
0x180020b2a  jbe     loc_180020BCF
0x180020b30  call    _tlgKeywordOn
0x180020b35  test    al, al
0x180020b37  jz      loc_180020BCF
0x180020b3d  lea     rax, [r15+40h]
0x180020b41  mov     [rbp+50h+var_C0], rax
0x180020b45  mov     [rsp+150h+var_E0], 4C6h
0x180020b4d  lea     rax, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180020b54  mov     [rbp+50h+var_C8], rax
0x180020b58  lea     rax, aDiagnosticrunn_3; "DiagnosticRunner::ResolveProblem"
0x180020b5f  mov     [rbp+50h+var_D0], rax
0x180020b63  lea     rax, aResolveproblem_3; "ResolveProblem - Get Problem Status Nod"...
0x180020b6a  mov     [rsp+150h+var_D8], rax
0x180020b6f  mov     eax, [rbp+50h+arg_18]
0x180020b72  mov     [rsp+150h+var_DC], eax
0x180020b76  lea     rax, [r15+0C1h]
0x180020b7d  mov     [rbp+50h+var_A0], rax
0x180020b81  lea     rax, [rbp+50h+var_C0]
0x180020b85  mov     [rsp+150h+var_100], rax
0x180020b8a  lea     rax, [rsp+150h+var_E0]
0x180020b8f  mov     [rsp+150h+var_108], rax
0x180020b94  lea     rax, [rbp+50h+var_C8]
0x180020b98  mov     [rsp+150h+var_110], rax
0x180020b9d  lea     rax, [rbp+50h+var_D0]
0x180020ba1  mov     [rsp+150h+var_118], rax
0x180020ba6  lea     rax, [rsp+150h+var_D8]
0x180020bab  mov     [rsp+150h+var_120], rax
0x180020bb0  lea     rax, [rsp+150h+var_DC]
0x180020bb5  mov     [rsp+150h+var_128], rax
0x180020bba  lea     rax, [rbp+50h+var_A0]
0x180020bbe  mov     [rsp+150h+var_130], rax
0x180020bc3  lea     rdx, dword_1800315A4
0x180020bca  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180020bcf  cmp     [rbp+50h+arg_18], ebx
0x180020bd2  jl      loc_180021217
0x180020bd8  mov     rcx, [rbp+50h+var_60]
0x180020bdc  mov     rax, [rcx]
0x180020bdf  lea     rdx, [rbp+50h+var_78]
0x180020be3  mov     rax, [rax+0D0h]
0x180020bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bef  mov     [rbp+50h+arg_18], eax
0x180020bf2  mov     eax, cs:dword_180039000
0x180020bf8  cmp     eax, 5
0x180020bfb  jbe     loc_180020CB1
0x180020c01  call    _tlgKeywordOn
0x180020c06  test    al, al
0x180020c08  jz      loc_180020CB1
0x180020c0e  mov     rax, [rbp+50h+var_78]
0x180020c12  mov     [rbp+50h+var_C0], rax
0x180020c16  lea     rax, [r15+40h]
0x180020c1a  mov     [rbp+50h+var_C8], rax
0x180020c1e  mov     [rsp+150h+var_E0], 4D0h
0x180020c26  lea     rax, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180020c2d  mov     [rbp+50h+var_D0], rax
0x180020c31  lea     rax, aDiagnosticrunn_3; "DiagnosticRunner::ResolveProblem"
0x180020c38  mov     [rsp+150h+var_D8], rax
0x180020c3d  lea     rax, aResolveproblem_7; "ResolveProblem - Get Text from Problem "...
0x180020c44  mov     [rbp+50h+var_A0], rax
0x180020c48  mov     eax, [rbp+50h+arg_18]
0x180020c4b  mov     [rsp+150h+var_DC], eax
0x180020c4f  lea     rax, [r15+0C1h]
0x180020c56  mov     [rbp+50h+var_B0], rax
0x180020c5a  lea     rax, [rbp+50h+var_C0]
0x180020c5e  mov     [rsp+150h+var_F8], rax
0x180020c63  lea     rax, [rbp+50h+var_C8]
0x180020c67  mov     [rsp+150h+var_100], rax
0x180020c6c  lea     rax, [rsp+150h+var_E0]
0x180020c71  mov     [rsp+150h+var_108], rax
0x180020c76  lea     rax, [rbp+50h+var_D0]
0x180020c7a  mov     [rsp+150h+var_110], rax
0x180020c7f  lea     rax, [rsp+150h+var_D8]
0x180020c84  mov     [rsp+150h+var_118], rax
0x180020c89  lea     rax, [rbp+50h+var_A0]
0x180020c8d  mov     [rsp+150h+var_120], rax
0x180020c92  lea     rax, [rsp+150h+var_DC]
0x180020c97  mov     [rsp+150h+var_128], rax
0x180020c9c  lea     rax, [rbp+50h+var_B0]
0x180020ca0  mov     [rsp+150h+var_130], rax
0x180020ca5  lea     rdx, word_18003151E
0x180020cac  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180020cb1  cmp     [rbp+50h+arg_18], ebx
0x180020cb4  jl      loc_180021217
0x180020cba  lea     rdx, aDetected; "Detected"
0x180020cc1  mov     rcx, [rbp+50h+var_78]
0x180020cc5  call    cs:__imp__o__wcsicmp
0x180020ccb  test    eax, eax
0x180020ccd  jnz     loc_180021217
0x180020cd3  lea     r9, [rbp+50h+var_A8]; struct IXMLDOMNodeList **
0x180020cd7  mov     r8, r12; struct IXMLDOMNode *
0x180020cda  xor     edx, edx; struct IXMLDOMDocument2 *
0x180020cdc  lea     rcx, aResolutionsRes; "./Resolutions/Resolution"
0x180020ce3  call    ?SdpXmlGetNodes@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@@Z; SdpXmlGetNodes(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *)
0x180020ce8  mov     [rbp+50h+arg_18], eax
0x180020ceb  mov     r12, [rbp+50h+var_A8]
0x180020cef  test    eax, eax
0x180020cf1  js      short loc_180020D0A
0x180020cf3  mov     rax, [r12]
0x180020cf7  lea     rdx, [rbp+50h+var_B8]
0x180020cfb  mov     rcx, r12
0x180020cfe  mov     rax, [rax+40h]
0x180020d02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d07  mov     [rbp+50h+arg_18], eax
0x180020d0a  cmp     [rbp+50h+var_B8], ebx
0x180020d0d  jle     short loc_180020D2E
0x180020d0f  mov     dword ptr [r13+0], 1
0x180020d17  mov     rax, [r15]
0x180020d1a  mov     edx, 5
0x180020d1f  mov     rcx, r15
0x180020d22  mov     rax, [rax+90h]
0x180020d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d2e  mov     eax, cs:dword_180039000
0x180020d34  lea     r8, aResolveproblem_4; "ResolveProblem - Get Resolution Nodes"
0x180020d3b  cmp     eax, 5
0x180020d3e  jbe     loc_180020DEB
0x180020d44  call    _tlgKeywordOn
0x180020d49  test    al, al
0x180020d4b  jz      loc_180020DEB
0x180020d51  mov     eax, [rbp+50h+var_B8]
0x180020d54  mov     [rsp+150h+var_E0], eax
0x180020d58  lea     rax, [r15+40h]
0x180020d5c  mov     [rbp+50h+var_B0], rax
0x180020d60  mov     [rsp+150h+var_DC], 4EDh
0x180020d68  lea     rax, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180020d6f  mov     [rbp+50h+var_C0], rax
0x180020d73  lea     rax, aDiagnosticrunn_3; "DiagnosticRunner::ResolveProblem"
0x180020d7a  mov     [rbp+50h+var_C8], rax
0x180020d7e  mov     [rbp+50h+var_D0], r8
0x180020d82  mov     eax, [rbp+50h+arg_18]
0x180020d85  mov     dword ptr [rbp+50h+var_A8], eax
0x180020d88  lea     rax, [r15+0C1h]
0x180020d8f  mov     [rsp+150h+var_D8], rax
0x180020d94  lea     rax, [rsp+150h+var_E0]
0x180020d99  mov     [rsp+150h+var_F8], rax
0x180020d9e  lea     rax, [rbp+50h+var_B0]
0x180020da2  mov     [rsp+150h+var_100], rax
0x180020da7  lea     rax, [rsp+150h+var_DC]
0x180020dac  mov     [rsp+150h+var_108], rax
0x180020db1  lea     rax, [rbp+50h+var_C0]
0x180020db5  mov     [rsp+150h+var_110], rax
0x180020dba  lea     rax, [rbp+50h+var_C8]
0x180020dbe  mov     [rsp+150h+var_118], rax
0x180020dc3  lea     rax, [rbp+50h+var_D0]
0x180020dc7  mov     [rsp+150h+var_120], rax
0x180020dcc  lea     rax, [rbp+50h+var_A8]
0x180020dd0  mov     [rsp+150h+var_128], rax
0x180020dd5  lea     rax, [rsp+150h+var_D8]
0x180020dda  mov     [rsp+150h+var_130], rax
0x180020ddf  lea     rdx, word_180031496
0x180020de6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@333434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180020deb  cmp     [rbp+50h+arg_18], ebx
0x180020dee  jl      loc_1800211C6
0x180020df4  xor     r13d, r13d
0x180020df7  cmp     [rbp+50h+var_B8], ebx
0x180020dfa  jle     loc_1800211C6
0x180020e00  test    rsi, rsi
0x180020e03  jz      short loc_180020E1C
0x180020e05  mov     rax, [rsi]
0x180020e08  mov     rcx, rsi
0x180020e0b  mov     rax, [rax+10h]
0x180020e0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e14  mov     [rbp+50h+var_70], 0
0x180020e1c  test    rbx, rbx
0x180020e1f  jz      short loc_180020E36
0x180020e21  mov     rax, [rbx]
0x180020e24  mov     rcx, rbx
0x180020e27  mov     rax, [rax+10h]
0x180020e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e30  xor     ebx, ebx
0x180020e32  mov     [rbp+50h+var_80], rbx
0x180020e36  test    rdi, rdi
0x180020e39  jz      short loc_180020E50
0x180020e3b  mov     rax, [rdi]
0x180020e3e  mov     rcx, rdi
0x180020e41  mov     rax, [rax+10h]
0x180020e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e4a  xor     edi, edi
0x180020e4c  mov     [rbp+50h+var_88], rdi
0x180020e50  test    r14, r14
0x180020e53  jz      short loc_180020E6B
0x180020e55  mov     rax, [r14]
0x180020e58  mov     rcx, r14
0x180020e5b  mov     rax, [rax+10h]
0x180020e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e64  xor     r14d, r14d
0x180020e67  mov     [rbp+50h+var_68], r14
0x180020e6b  mov     rcx, [rbp+50h+bstrString]; bstrString
0x180020e6f  call    cs:__imp_SysFreeString
0x180020e75  lea     rdx, [rbp+50h+var_70]; struct IXMLDOMNode **
0x180020e79  mov     rcx, r12; struct IXMLDOMNodeList *
0x180020e7c  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180020e81  mov     [rbp+50h+arg_18], eax
0x180020e84  mov     rsi, [rbp+50h+var_70]
0x180020e88  test    eax, eax
0x180020e8a  js      short loc_180020EFC
0x180020e8c  lea     r9, [rbp+50h+var_80]; struct IXMLDOMNode **
0x180020e90  mov     r8, rsi; struct IXMLDOMNode *
0x180020e93  lea     rcx, aId_1; "./ID"
0x180020e9a  call    ?SdpXmlGetNode@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAU2@@Z; SdpXmlGetNode(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNode * *)
0x180020e9f  mov     [rbp+50h+arg_18], eax
0x180020ea2  mov     rbx, [rbp+50h+var_80]
0x180020ea6  test    eax, eax
0x180020ea8  js      short loc_180020EFC
0x180020eaa  mov     rax, [rbx]
0x180020ead  lea     rdx, [rbp+50h+bstrString]
0x180020eb1  mov     rcx, rbx
0x180020eb4  mov     rax, [rax+0D0h]
0x180020ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ec0  mov     [rbp+50h+arg_18], eax
0x180020ec3  test    eax, eax
0x180020ec5  js      short loc_180020EFC
0x180020ec7  lea     r9, [rbp+50h+var_88]; struct IXMLDOMNode **
0x180020ecb  mov     r8, rsi; struct IXMLDOMNode *
0x180020ece  lea     rcx, aScript; "./Script"
0x180020ed5  call    ?SdpXmlGetNode@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAU2@@Z; SdpXmlGetNode(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNode * *)
0x180020eda  mov     [rbp+50h+arg_18], eax
0x180020edd  mov     rdi, [rbp+50h+var_88]
0x180020ee1  test    eax, eax
0x180020ee3  js      short loc_180020EFC
0x180020ee5  lea     r9, [rbp+50h+var_98]; unsigned int *
0x180020ee9  lea     r8, [rbp+50h+var_68]; struct IXMLDOMNodeList **
0x180020eed  mov     rdx, rdi; struct IXMLDOMNode *
0x180020ef0  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
  ... truncated ...
```
