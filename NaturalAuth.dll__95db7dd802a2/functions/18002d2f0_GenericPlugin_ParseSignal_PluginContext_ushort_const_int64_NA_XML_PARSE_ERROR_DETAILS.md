# GenericPlugin::ParseSignal(_PluginContext *,ushort const *,__int64 *,NA_XML_PARSE_ERROR_DETAILS *)

- ea: `0x18002d2f0`
- end: `0x18002d4ba`
- name: `?ParseSignal@GenericPlugin@@CAJPEAU_PluginContext@@PEBGPEA_JPEAUNA_XML_PARSE_ERROR_DETAILS@@@Z`
- size: `458`
- prototype: `static int(struct _PluginContext *, const unsigned __int16 *, __int64 *, struct NA_XML_PARSE_ERROR_DETAILS *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000b578`
- `0x180014e7c`
- `0x18001fb2c`
- `0x180021df4`
- `0x180023340`
- `0x180028a1c`
- `0x18002cf10`
- `0x18002d2f0`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002d321`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002d321`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d48c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d48c`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall GenericPlugin::ParseSignal(
        struct _PluginContext *a1,
        const unsigned __int16 *a2,
        __int64 *a3,
        struct NA_XML_PARSE_ERROR_DETAILS *a4)
{
  HRESULT v8; // ebx
  _bstr_t *v9; // rsi
  _bstr_t *v10; // rax
  LPVOID v11; // rsi
  __int64 (__fastcall *v12)(LPVOID, __int64 *); // rdi
  int v13; // eax
  signed __int64 v14; // rdi
  __int64 (__fastcall *v15)(struct _PluginContext *, __int64 *, signed __int64, __int64 **, struct NA_XML_PARSE_ERROR_DETAILS *); // rsi
  int v16; // eax
  __int64 v17; // rax
  __int64 v19; // rax
  __int64 v20; // [rsp+30h] [rbp-88h] BYREF
  __int64 *v21; // [rsp+38h] [rbp-80h] BYREF
  __int64 v22; // [rsp+40h] [rbp-78h] BYREF
  HRESULT v23; // [rsp+48h] [rbp-70h] BYREF
  LPVOID v24; // [rsp+50h] [rbp-68h] BYREF
  _BYTE v25[16]; // [rsp+58h] [rbp-60h] BYREF
  std::exception *v26; // [rsp+68h] [rbp-50h] BYREF
  __int64 v27; // [rsp+70h] [rbp-48h] BYREF
  int v28; // [rsp+78h] [rbp-40h]
  int v29; // [rsp+C0h] [rbp+8h] BYREF
  const unsigned __int16 *v30; // [rsp+C8h] [rbp+10h]

  v30 = a2;
  v29 = 0;
  v8 = CoInitializeEx(0, 0);
  v23 = v8;
  v21 = &v22;
  try
  {
    v9 = (_bstr_t *)(*(__int64 (**)(void))(*(_QWORD *)a1 + 32LL))();
    v10 = _bstr_t::_bstr_t((_bstr_t *)&v20, a2);
    NAXmlParser::Parse(&v23, &v24, v10, v9, &v29, a4);
    if ( v29 >= 0 )
    {
      v20 = 0;
      v11 = v24;
      v12 = *(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v24 + 104LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
      v13 = v12(v11, &v20);
      if ( v13 < 0 )
        _com_issue_error(v13);
      v21 = 0;
      v14 = _InterlockedExchangeAdd64(&qword_18005FCD0, 1u);
      v15 = *(__int64 (__fastcall **)(struct _PluginContext *, __int64 *, signed __int64, __int64 **, struct NA_XML_PARSE_ERROR_DETAILS *))(*(_QWORD *)a1 + 40LL);
      v22 = v20;
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
      v16 = v15(a1, &v22, v14 + 1, &v21, a4);
      if ( v16 < 0 )
        _com_issue_error(v16);
      *a3 = (*(__int64 (__fastcall **)(__int64 *))(*v21 + 8))(v21);
      v17 = std::map<__int64,std::unique_ptr<GenericPlugin::Signal>>::_Try_emplace<__int64 const &,>(
              (__int64 *)a1 + 6,
              (__int64)v25,
              a3);
      std::unique_ptr<GenericPlugin::Signal>::operator=<TaskSchedulerSignal,std::default_delete<TaskSchedulerSignal>,0>(
        (__int64 *)(*(_QWORD *)v17 + 40LL),
        (__int64 *)&v21);
      std::unique_ptr<TimeSignal::Factory>::~unique_ptr<TimeSignal::Factory>(&v21);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v24);
    if ( v8 >= 0 )
      CoUninitialize();
  }
  catch ( _com_error v27 )
  {
    v29 = v28;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        (unsigned int)WPP_1313e11ac9f43f31e5324403d3fcf239_Traceguids,
        (_DWORD)v30,
        v28);
    _com_error::~_com_error((_com_error *)&v27);
    return (unsigned int)v29;
  }
  catch ( std::bad_alloc )
  {
    return (unsigned int)-2147024882;
  }
  catch ( std::exception *v26 )
  {
    v19 = (*(__int64 (__fastcall **)(std::exception *))(*(_QWORD *)v26 + 8LL))(v26);
    UnhandledException(v19);
    return (unsigned int)-2147220987;
  }
  catch ( ... )
  {
    UnhandledException(0);
    return (unsigned int)-2147220987;
  }
  return (unsigned int)v29;
}

```

## disassembly

```asm
0x18002d2f0  mov     rax, rsp
0x18002d2f3  mov     [rax+18h], rbx
0x18002d2f7  mov     [rax+10h], rdx
0x18002d2fb  push    rsi
0x18002d2fc  push    rdi
0x18002d2fd  push    r12
0x18002d2ff  push    r14
0x18002d301  push    r15
0x18002d303  sub     rsp, 90h
0x18002d30a  mov     r15, r9
0x18002d30d  mov     r12, r8
0x18002d310  mov     rdi, rdx
0x18002d313  mov     r14, rcx
0x18002d316  mov     dword ptr [rax+8], 0
0x18002d31d  xor     edx, edx; dwCoInit
0x18002d31f  xor     ecx, ecx; pvReserved
0x18002d321  call    cs:__imp_CoInitializeEx
0x18002d327  mov     ebx, eax
0x18002d329  mov     [rsp+0B8h+var_70], eax
0x18002d32d  lea     rax, [rsp+0B8h+var_78]
0x18002d332  mov     [rsp+0B8h+var_80], rax
0x18002d337  mov     rax, [r14]
0x18002d33a  lea     rdx, [rsp+0B8h+var_78]
0x18002d33f  mov     rcx, r14
0x18002d342  mov     rax, [rax+20h]
0x18002d346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d34b  mov     rsi, rax
0x18002d34e  mov     rdx, rdi; unsigned __int16 *
0x18002d351  lea     rcx, [rsp+0B8h+var_88]; this
0x18002d356  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002d35b  nop
0x18002d35c  mov     [rsp+0B8h+var_90], r15
0x18002d361  lea     rcx, [rsp+0B8h+arg_0]
0x18002d369  mov     [rsp+0B8h+var_98], rcx
0x18002d36e  mov     r9, rsi
0x18002d371  mov     r8, rax
0x18002d374  lea     rdx, [rsp+0B8h+var_68]
0x18002d379  lea     rcx, [rsp+0B8h+var_70]
0x18002d37e  call    ?Parse@NAXmlParser@@QEBA?AV?$ComPtr@UIXMLDOMDocument3@@@WRL@Microsoft@@V_bstr_t@@0PEAJPEAUNA_XML_PARSE_ERROR_DETAILS@@@Z; NAXmlParser::Parse(_bstr_t,_bstr_t,long *,NA_XML_PARSE_ERROR_DETAILS *)
0x18002d383  nop
0x18002d384  cmp     [rsp+0B8h+arg_0], 0
0x18002d38c  jl      loc_18002D47D
0x18002d392  mov     [rsp+0B8h+var_88], 0
0x18002d39b  mov     rsi, [rsp+0B8h+var_68]
0x18002d3a0  mov     rax, [rsi]
0x18002d3a3  mov     rdi, [rax+68h]
0x18002d3a7  lea     rcx, [rsp+0B8h+var_88]
0x18002d3ac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d3b1  lea     rdx, [rsp+0B8h+var_88]
0x18002d3b6  mov     rcx, rsi
0x18002d3b9  mov     rax, rdi
0x18002d3bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3c1  test    eax, eax
0x18002d3c3  jns     short loc_18002D3CC
0x18002d3c5  mov     ecx, eax; int
0x18002d3c7  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002d3cc  mov     [rsp+0B8h+var_80], 0
0x18002d3d5  mov     edi, 1
0x18002d3da  lock xadd cs:qword_18005FCD0, rdi
0x18002d3e3  mov     rax, [r14]
0x18002d3e6  mov     rsi, [rax+28h]
0x18002d3ea  mov     rcx, [rsp+0B8h+var_88]
0x18002d3ef  mov     [rsp+0B8h+var_78], rcx
0x18002d3f4  test    rcx, rcx
0x18002d3f7  jz      short loc_18002D406
0x18002d3f9  mov     rax, [rcx]
0x18002d3fc  mov     rax, [rax+8]
0x18002d400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d405  nop
0x18002d406  mov     [rsp+0B8h+var_98], r15
0x18002d40b  lea     r9, [rsp+0B8h+var_80]
0x18002d410  lea     r8, [rdi+1]
0x18002d414  lea     rdx, [rsp+0B8h+var_78]
0x18002d419  mov     rcx, r14
0x18002d41c  mov     rax, rsi
0x18002d41f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d424  test    eax, eax
0x18002d426  jns     short loc_18002D42F
0x18002d428  mov     ecx, eax; int
0x18002d42a  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002d42f  mov     rcx, [rsp+0B8h+var_80]
0x18002d434  mov     rax, [rcx]
0x18002d437  mov     rax, [rax+8]
0x18002d43b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d440  mov     [r12], rax
0x18002d444  lea     rcx, [r14+30h]
0x18002d448  mov     r8, r12
0x18002d44b  lea     rdx, [rsp+0B8h+var_60]
0x18002d450  call    ??$_Try_emplace@AEB_J$$V@?$map@_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@U?$less@_J@2@V?$allocator@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@PEAX@std@@_N@1@AEB_J@Z; std::map<__int64,std::unique_ptr<GenericPlugin::Signal>>::_Try_emplace<__int64 const &,>(__int64 const &)
0x18002d455  mov     rcx, [rax]
0x18002d458  add     rcx, 28h ; '('
0x18002d45c  lea     rdx, [rsp+0B8h+var_80]
0x18002d461  call    ??$?4VTaskSchedulerSignal@@U?$default_delete@VTaskSchedulerSignal@@@std@@$0A@@?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@QEAAAEAV01@$$QEAV?$unique_ptr@VTaskSchedulerSignal@@U?$default_delete@VTaskSchedulerSignal@@@std@@@1@@Z; std::unique_ptr<GenericPlugin::Signal>::operator=<TaskSchedulerSignal,std::default_delete<TaskSchedulerSignal>,0>(std::unique_ptr<TaskSchedulerSignal> &&)
0x18002d466  nop
0x18002d467  lea     rcx, [rsp+0B8h+var_80]
0x18002d46c  call    ??1?$unique_ptr@VFactory@TimeSignal@@U?$default_delete@VFactory@TimeSignal@@@std@@@std@@QEAA@XZ; std::unique_ptr<TimeSignal::Factory>::~unique_ptr<TimeSignal::Factory>(void)
0x18002d471  nop
0x18002d472  lea     rcx, [rsp+0B8h+var_88]
0x18002d477  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d47c  nop
0x18002d47d  lea     rcx, [rsp+0B8h+var_68]
0x18002d482  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d487  nop
0x18002d488  test    ebx, ebx
0x18002d48a  js      short loc_18002D493
0x18002d48c  call    cs:__imp_CoUninitialize
0x18002d492  nop
0x18002d493  jmp     short loc_18002D49B
0x18002d495  jmp     short loc_18002D49B
0x18002d497  jmp     short loc_18002D49B
0x18002d499  jmp     short $+2
0x18002d49b  mov     eax, [rsp+0B8h+arg_0]
0x18002d4a2  mov     rbx, [rsp+0B8h+arg_10]
0x18002d4aa  add     rsp, 90h
0x18002d4b1  pop     r15
0x18002d4b3  pop     r14
0x18002d4b5  pop     r12
0x18002d4b7  pop     rdi
0x18002d4b8  pop     rsi
0x18002d4b9  retn
```
