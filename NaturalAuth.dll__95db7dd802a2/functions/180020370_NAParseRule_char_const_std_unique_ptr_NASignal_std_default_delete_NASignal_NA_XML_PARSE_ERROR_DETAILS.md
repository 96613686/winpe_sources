# NAParseRule(char const *,std::unique_ptr<NASignal,std::default_delete<NASignal>> *,NA_XML_PARSE_ERROR_DETAILS *)

- ea: `0x180020370`
- end: `0x180020675`
- name: `?NAParseRule@@YAJPEBDPEAV?$unique_ptr@VNASignal@@U?$default_delete@VNASignal@@@std@@@std@@PEAUNA_XML_PARSE_ERROR_DETAILS@@@Z`
- size: `773`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, __int64 *, _DWORD *)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000bbe8`
- `0x18000d220`

## callees

- `0x1800011c0`
- `0x18000166c`
- `0x180004170`
- `0x18000459c`
- `0x18000b7b8`
- `0x18000c9e0`
- `0x18000cab8`
- `0x180014e7c`
- `0x180020078`
- `0x180020370`
- `0x1800219a0`
- `0x180021df4`
- `0x180021efc`
- `0x180023340`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800203b6`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800203b6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180020623`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180020623`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall NAParseRule(LPCCH lpMultiByteStr, __int64 *a2, _DWORD *a3)
{
  _DWORD *v3; // r12
  int *v6; // r15
  HRESULT v7; // ebx
  __int64 v8; // rdx
  _QWORD *v9; // rax
  _QWORD *v10; // rdi
  LPVOID v11; // rsi
  __int64 (__fastcall *v12)(LPVOID, __int64 *); // rdi
  int v13; // eax
  __int64 v14; // rsi
  __int64 (__fastcall *v15)(__int64, _QWORD **); // rdi
  int v16; // eax
  unsigned int v17; // edi
  __int64 CorrelationVector; // rax
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int v23; // [rsp+50h] [rbp-C8h] BYREF
  __int64 v24; // [rsp+58h] [rbp-C0h] BYREF
  _QWORD *v25; // [rsp+60h] [rbp-B8h] BYREF
  HRESULT v26; // [rsp+68h] [rbp-B0h] BYREF
  _QWORD *v27; // [rsp+70h] [rbp-A8h] BYREF
  LPVOID v28; // [rsp+78h] [rbp-A0h] BYREF
  _DWORD *v29; // [rsp+80h] [rbp-98h] BYREF
  __int64 v30; // [rsp+88h] [rbp-90h] BYREF
  _QWORD v31[3]; // [rsp+90h] [rbp-88h] BYREF
  _DWORD v32[8]; // [rsp+A8h] [rbp-70h] BYREF
  _BYTE v33[32]; // [rsp+C8h] [rbp-50h] BYREF

  v3 = a3;
  v29 = a3;
  v6 = a3;
  v23 = 0;
  v7 = CoInitializeEx(0, 0);
  v26 = v7;
  v8 = *a2;
  *a2 = 0;
  if ( v8 )
    std::default_delete<NASignal>::operator()();
  v31[2] = v31;
  v31[0] = qword_18005F9B8;
  if ( qword_18005F9B8 )
    _InterlockedIncrement((volatile signed __int32 *)(qword_18005F9B8 + 16LL));
  try
  {
    v9 = operator new(0x18u);
    v10 = v9;
    v31[1] = v9;
    if ( v9 )
    {
      v9[1] = 0;
      *((_DWORD *)v9 + 4) = 1;
      *v9 = _com_util::ConvertStringToBSTR(lpMultiByteStr);
    }
    v27 = v10;
    if ( !v10 )
      _com_issue_error(-2147024882);
    NAXmlParser::Parse(&v26, &v28, (_bstr_t *)&v27, (_bstr_t *)v31, &v23, v3);
    if ( v23 < 0 )
      _com_issue_error(v23);
    v24 = 0;
    v11 = v28;
    v12 = *(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v28 + 104LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    v13 = v12(v11, &v24);
    if ( v13 < 0 )
      _com_issue_error(v13);
    v25 = 0;
    v14 = v24;
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v24 + 104LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    v16 = v15(v14, &v25);
    if ( v16 < 0 )
      _com_issue_error(v16);
    v27 = v25;
    if ( v25 )
      (*(void (__fastcall **)(_QWORD *))(*v25 + 8LL))(v25);
    v17 = NAHandleElement(&v27, a2, v3);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  }
  catch ( _com_error v32 )
  {
    v23 = v32[2];
    _com_error::~_com_error((_com_error *)v32);
    v17 = v23;
    v7 = v26;
    v3 = v29;
    v6 = v29;
  }
  v9 = operator new(0x18u);
  v10 = v9;
  v31[1] = v9;
}

```

## disassembly

```asm
0x180020370  mov     [rsp+arg_18], rbx
0x180020375  push    rsi
0x180020376  push    rdi
0x180020377  push    r12
0x180020379  push    r13
0x18002037b  push    r15
0x18002037d  sub     rsp, 0F0h
0x180020384  mov     rax, cs:__security_cookie
0x18002038b  xor     rax, rsp
0x18002038e  mov     [rsp+118h+var_30], rax
0x180020396  mov     r12, r8
0x180020399  mov     r13, rdx
0x18002039c  mov     rsi, rcx
0x18002039f  mov     [rsp+118h+var_98], r8
0x1800203a7  mov     r15, r8
0x1800203aa  mov     [rsp+118h+var_C8], 0
0x1800203b2  xor     edx, edx; dwCoInit
0x1800203b4  xor     ecx, ecx; pvReserved
0x1800203b6  call    cs:__imp_CoInitializeEx
0x1800203bc  mov     ebx, eax
0x1800203be  mov     [rsp+118h+var_B0], eax
0x1800203c2  mov     rdx, [r13+0]
0x1800203c6  mov     qword ptr [r13+0], 0
0x1800203ce  test    rdx, rdx
0x1800203d1  jz      short loc_1800203D9
0x1800203d3  call    ??R?$default_delete@VNASignal@@@std@@QEBAXPEAVNASignal@@@Z; std::default_delete<NASignal>::operator()(NASignal *)
0x1800203d8  nop
0x1800203d9  lea     rax, [rsp+118h+var_88]
0x1800203e1  mov     [rsp+118h+var_78], rax
0x1800203e9  mov     rax, cs:qword_18005F9B8
0x1800203f0  mov     [rsp+118h+var_88], rax
0x1800203f8  test    rax, rax
0x1800203fb  jz      short loc_180020401
0x1800203fd  lock inc dword ptr [rax+10h]
0x180020401  mov     ecx, 18h; Size
0x180020406  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002040b  mov     rdi, rax
0x18002040e  mov     [rsp+118h+var_80], rax
0x180020416  test    rdi, rdi
0x180020419  jz      short loc_180020435
0x18002041b  mov     qword ptr [rax+8], 0
0x180020423  mov     dword ptr [rax+10h], 1
0x18002042a  mov     rcx, rsi; lpMultiByteStr
0x18002042d  call    ?ConvertStringToBSTR@_com_util@@YAPEAGPEBD@Z; _com_util::ConvertStringToBSTR(char const *)
0x180020432  mov     [rdi], rax
0x180020435  mov     [rsp+118h+var_A8], rdi
0x18002043a  test    rdi, rdi
0x18002043d  jz      loc_180020653
0x180020443  mov     [rsp+118h+var_F0], r12
0x180020448  lea     rax, [rsp+118h+var_C8]
0x18002044d  mov     [rsp+118h+var_F8], rax
0x180020452  lea     r9, [rsp+118h+var_88]
0x18002045a  lea     r8, [rsp+118h+var_A8]
0x18002045f  lea     rdx, [rsp+118h+var_A0]
0x180020464  lea     rcx, [rsp+118h+var_B0]
0x180020469  call    ?Parse@NAXmlParser@@QEBA?AV?$ComPtr@UIXMLDOMDocument3@@@WRL@Microsoft@@V_bstr_t@@0PEAJPEAUNA_XML_PARSE_ERROR_DETAILS@@@Z; NAXmlParser::Parse(_bstr_t,_bstr_t,long *,NA_XML_PARSE_ERROR_DETAILS *)
0x18002046e  nop
0x18002046f  mov     ecx, [rsp+118h+var_C8]; int
0x180020473  test    ecx, ecx
0x180020475  js      loc_18002065E
0x18002047b  mov     [rsp+118h+var_C0], 0
0x180020484  mov     rsi, [rsp+118h+var_A0]
0x180020489  mov     rax, [rsi]
0x18002048c  mov     rdi, [rax+68h]
0x180020490  lea     rcx, [rsp+118h+var_C0]
0x180020495  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002049a  lea     rdx, [rsp+118h+var_C0]
0x18002049f  mov     rcx, rsi
0x1800204a2  mov     rax, rdi
0x1800204a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204aa  test    eax, eax
0x1800204ac  js      loc_180020664
0x1800204b2  mov     [rsp+118h+var_B8], 0
0x1800204bb  mov     rsi, [rsp+118h+var_C0]
0x1800204c0  mov     rax, [rsi]
0x1800204c3  mov     rdi, [rax+68h]
0x1800204c7  lea     rcx, [rsp+118h+var_B8]
0x1800204cc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800204d1  lea     rdx, [rsp+118h+var_B8]
0x1800204d6  mov     rcx, rsi
0x1800204d9  mov     rax, rdi
0x1800204dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204e1  test    eax, eax
0x1800204e3  js      loc_18002066C
0x1800204e9  mov     rcx, [rsp+118h+var_B8]
0x1800204ee  mov     [rsp+118h+var_A8], rcx
0x1800204f3  test    rcx, rcx
0x1800204f6  jz      short loc_180020505
0x1800204f8  mov     rax, [rcx]
0x1800204fb  mov     rax, [rax+8]
0x1800204ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020504  nop
0x180020505  mov     r8, r12
0x180020508  mov     rdx, r13
0x18002050b  lea     rcx, [rsp+118h+var_A8]
0x180020510  call    NAHandleElement
0x180020515  mov     edi, eax
0x180020517  lea     rcx, [rsp+118h+var_B8]
0x18002051c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020521  nop
0x180020522  lea     rcx, [rsp+118h+var_C0]
0x180020527  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002052c  nop
0x18002052d  lea     rcx, [rsp+118h+var_A0]
0x180020532  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020537  nop
0x180020538  jmp     short loc_18002054D
0x18002053a  mov     edi, [rsp+118h+var_C8]
0x18002053e  mov     ebx, [rsp+118h+var_B0]
0x180020542  mov     r12, [rsp+118h+var_98]
0x18002054a  mov     r15, r12
0x18002054d  mov     eax, cs:dword_18005C570
0x180020553  cmp     eax, 5
0x180020556  jbe     loc_18002061F
0x18002055c  mov     rdx, 400000000000h
0x180020566  lea     rcx, dword_18005C570
0x18002056d  call    _tlgKeywordOn
0x180020572  test    al, al
0x180020574  jz      loc_18002061F
0x18002057a  lea     rcx, [rsp+118h+var_50]
0x180020582  call    ?GetCorrelationVector@NaturalAuthTraceLogging@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; NaturalAuthTraceLogging::GetCorrelationVector(void)
0x180020587  mov     rcx, rax
0x18002058a  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18002058f  mov     [rsp+118h+var_90], rax
0x180020597  lea     rax, [r15+208h]
0x18002059e  mov     [rsp+118h+var_98], rax
0x1800205a6  lea     rax, [r15+8]
0x1800205aa  mov     [rsp+118h+var_A0], rax
0x1800205af  mov     eax, [r15+4]
0x1800205b3  mov     [rsp+118h+var_C8], eax
0x1800205b7  mov     eax, [r12]
0x1800205bb  mov     dword ptr [rsp+118h+var_C0], eax
0x1800205bf  mov     dword ptr [rsp+118h+var_B8], edi
0x1800205c3  lea     rax, [rsp+118h+var_90]
0x1800205cb  mov     [rsp+118h+var_D0], rax
0x1800205d0  lea     rax, [rsp+118h+var_98]
0x1800205d8  mov     [rsp+118h+var_D8], rax
0x1800205dd  lea     rax, [rsp+118h+var_A0]
0x1800205e2  mov     [rsp+118h+var_E0], rax
0x1800205e7  lea     rax, [rsp+118h+var_C8]
0x1800205ec  mov     [rsp+118h+var_E8], rax
0x1800205f1  lea     rax, [rsp+118h+var_C0]
0x1800205f6  mov     [rsp+118h+var_F0], rax
0x1800205fb  lea     rax, [rsp+118h+var_B8]
0x180020600  mov     [rsp+118h+var_F8], rax
0x180020605  lea     rdx, unk_18004FC50
0x18002060c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &)
0x180020611  lea     rcx, [rsp+118h+var_50]
0x180020619  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18002061e  nop
0x18002061f  test    ebx, ebx
0x180020621  js      short loc_180020629
0x180020623  call    cs:__imp_CoUninitialize
0x180020629  mov     eax, edi
0x18002062b  mov     rcx, [rsp+118h+var_30]
0x180020633  xor     rcx, rsp; StackCookie
0x180020636  call    __security_check_cookie
0x18002063b  mov     rbx, [rsp+118h+arg_18]
0x180020643  add     rsp, 0F0h
0x18002064a  pop     r15
0x18002064c  pop     r13
0x18002064e  pop     r12
0x180020650  pop     rdi
0x180020651  pop     rsi
0x180020652  retn
0x180020653  mov     ecx, 8007000Eh; int
0x180020658  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002065e  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180020664  mov     ecx, eax; int
0x180020666  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002066c  mov     ecx, eax; int
0x18002066e  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
