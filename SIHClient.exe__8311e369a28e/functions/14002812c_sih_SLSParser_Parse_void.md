# sih::SLSParser::Parse(void)

- ea: `0x14002812c`
- end: `0x140028536`
- name: `?Parse@SLSParser@sih@@QEAAXXZ`
- size: `1034`
- prototype: `void __fastcall(sih::SLSParser *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x1400261d4`

## callees

- `0x14000711c`
- `0x1400073f0`
- `0x14001b67c`
- `0x14001ed4c`
- `0x1400217d4`
- `0x140023168`
- `0x140028034`
- `0x140028070`
- `0x14002812c`
- `0x140028eec`
- `0x140029368`
- `0x140029638`
- `0x14002a88c`
- `0x140039bf8`
- `0x140039d20`
- `0x140045963`
- `0x140045af8`
- `0x140045dc0`
- `0x140045de4`
- `0x1400481f8`
- `0x14004cd00`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14002816d`
- `OLEAUT32!__imp_SysAllocString` at `0x14002816d`
- `OLEAUT32!__imp_SysFreeString` at `0x140028471`
- `OLEAUT32!__imp_SysFreeString` at `0x140028471`

## string_xrefs

- `0x1400281c6`: `/ServiceEnvironment`
- `0x1400283a5`: `/ServiceEnvironment[@ServiceID="E7A50285-D08D-499D-9FF8-180FDC2332BC"]/SIHClientData/Actions[@elementVersion="1"]/Action`
- `0x1400282b5`: `/ServiceEnvironment[@ServiceID="E7A50285-D08D-499D-9FF8-180FDC2332BC"]/SIHClientData/Engine[@elementVersion="1"]/Package`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall sih::SLSParser::Parse(sih::SLSParser *this)
{
  sih::SLSParser *v1; // r14
  wchar_t *v2; // rax
  OLECHAR *v3; // rbx
  wchar_t *SLSDOMDocument; // rdi
  unsigned int v5; // eax
  wchar_t *v6; // r15
  unsigned int v7; // eax
  _DWORD *v8; // rax
  _DWORD *v9; // r12
  const wchar_t *v10; // rsi
  unsigned int v11; // eax
  const char *v12; // rcx
  unsigned int v13; // eax
  struct sih::PackageMetadata **v14; // rax
  struct sih::PackageMetadata *v15; // rcx
  _QWORD *v16; // rsi
  wchar_t *v17; // rsi
  unsigned int v18; // eax
  int v19; // eax
  unsigned int i; // esi
  int v21; // eax
  _BYTE pExceptionObject[32]; // [rsp+28h] [rbp-59h] BYREF
  wchar_t *String[7]; // [rsp+48h] [rbp-39h] BYREF
  wchar_t *EndPtr; // [rsp+80h] [rbp-1h] BYREF
  struct IXMLDOMNode *v25; // [rsp+88h] [rbp+7h] BYREF
  int v26; // [rsp+90h] [rbp+Fh] BYREF
  __int128 v27; // [rsp+98h] [rbp+17h] BYREF

  v1 = this;
  if ( *((_QWORD *)this + 3) > 7u )
    this = *(sih::SLSParser **)this;
  v2 = SysAllocString((const OLECHAR *)this);
  v3 = v2;
  String[4] = v2;
  if ( !v2 )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)&v27);
    std::bad_alloc::bad_alloc(pExceptionObject, &v27);
    throw (std::bad_alloc *)pExceptionObject;
  }
  SLSDOMDocument = (wchar_t *)sih::SLSParser::GetSLSDOMDocument(v2);
  String[5] = SLSDOMDocument;
  EndPtr = 0;
  v5 = (*(__int64 (__fastcall **)(wchar_t *, wchar_t **))(*(_QWORD *)SLSDOMDocument + 360LL))(SLSDOMDocument, &EndPtr);
  sih::CheckXmlResult((sih *)v5);
  v6 = EndPtr;
  String[6] = EndPtr;
  v25 = 0;
  v7 = (*(__int64 (__fastcall **)(wchar_t *, const OLECHAR *, struct IXMLDOMNode **))(*(_QWORD *)EndPtr + 296LL))(
         EndPtr,
         L"/ServiceEnvironment",
         &v25);
  sih::CheckXmlResult((sih *)v7);
  v27 = 0;
  sih::XmlNodeWrapper::XmlNodeWrapper((sih::XmlNodeWrapper *)&v27, v25);
  sih::utils::GetAttrValue(String, *((__int64 *)&v27 + 1), L"Revision", 0);
  v8 = (_DWORD *)o__errno_0();
  v9 = v8;
  v10 = (const wchar_t *)String;
  if ( String[3] > (wchar_t *)7 )
    v10 = String[0];
  EndPtr = 0;
  *v8 = 0;
  v11 = o_wcstoul_0(v10, &EndPtr, 10);
  if ( v10 == EndPtr )
    std::_Xinvalid_argument(v12);
  if ( *v9 == 34 )
    std::_Xout_of_range("stoul argument out of range");
  *((_DWORD *)v1 + 8) = v11;
  std::wstring::~wstring(String);
  if ( *((_QWORD *)&v27 + 1) )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v27 + 1) + 16LL))(*((_QWORD *)&v27 + 1));
    *((_QWORD *)&v27 + 1) = 0;
  }
  if ( (_QWORD)v27 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v27 + 16LL))(v27);
    *(_QWORD *)&v27 = 0;
  }
  if ( v25 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v25->lpVtbl->Release)(v25);
  v25 = 0;
  v13 = (*(__int64 (__fastcall **)(wchar_t *, const wchar_t *, struct IXMLDOMNode **))(*(_QWORD *)v6 + 296LL))(
          v6,
          L"/ServiceEnvironment[@ServiceID=\"E7A50285-D08D-499D-9FF8-180FDC2332BC\"]/SIHClientData/Engine[@elementVersion=\"1\"]/Package",
          &v25);
  if ( v13 == 1 )
  {
    sih::hr_exception::hr_exception((sih::hr_exception *)pExceptionObject, -2145103608);
    throw (sih::hr_exception *)pExceptionObject;
  }
  sih::CheckXmlResult((sih *)v13);
  v14 = sih::SLSParser::ParsePackage((struct sih::PackageMetadata **)&EndPtr, v25, 0);
  v15 = *v14;
  *v14 = 0;
  v16 = (_QWORD *)*((_QWORD *)v1 + 5);
  *((_QWORD *)v1 + 5) = v15;
  if ( v16 )
  {
    std::vector<sih::FileMetadata>::_Tidy((__int64)(v16 + 17));
    std::wstring::~wstring(v16 + 12);
    std::vector<std::wstring>::_Tidy((__int64)(v16 + 9));
    std::wstring::~wstring(v16 + 5);
    std::wstring::~wstring(v16 + 1);
    operator delete(v16, (const struct std::nothrow_t *)0xA0);
  }
  v17 = EndPtr;
  if ( EndPtr )
  {
    std::vector<sih::FileMetadata>::_Tidy((__int64)(EndPtr + 68));
    std::wstring::~wstring((_QWORD *)v17 + 12);
    std::vector<std::wstring>::_Tidy((__int64)(v17 + 36));
    std::wstring::~wstring((_QWORD *)v17 + 5);
    std::wstring::~wstring((_QWORD *)v17 + 1);
    operator delete(v17, (const struct std::nothrow_t *)0xA0);
  }
  if ( v25 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v25->lpVtbl->Release)(v25);
  v25 = 0;
  v18 = (*(__int64 (__fastcall **)(wchar_t *, const wchar_t *, struct IXMLDOMNode **))(*(_QWORD *)v6 + 288LL))(
          v6,
          L"/ServiceEnvironment[@ServiceID=\"E7A50285-D08D-499D-9FF8-180FDC2332BC\"]/SIHClientData/Actions[@elementVersion=\"1\"]/Action",
          &v25);
  sih::CheckXmlResult((sih *)v18);
  v26 = 0;
  v19 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, int *))v25->lpVtbl->get_nodeValue)(v25, &v26);
  if ( v19 < 0 )
  {
    sih::hr_exception::hr_exception((sih::hr_exception *)pExceptionObject, v19);
    throw (sih::hr_exception *)pExceptionObject;
  }
  for ( i = 0; (int)i < v26; ++i )
  {
    EndPtr = 0;
    v21 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, _QWORD, wchar_t **))v25->lpVtbl->get_nodeName)(v25, i, &EndPtr);
    if ( v21 < 0 )
    {
      sih::hr_exception::hr_exception((sih::hr_exception *)pExceptionObject, v21);
      throw (sih::hr_exception *)pExceptionObject;
    }
    sih::SLSParser::ParseAction((struct IXMLDOMNode *)EndPtr);
    if ( EndPtr )
      (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)EndPtr + 16LL))(EndPtr);
  }
  if ( v25 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v25->lpVtbl->Release)(v25);
  (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v6 + 16LL))(v6);
  (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)SLSDOMDocument + 16LL))(SLSDOMDocument);
  SysFreeString(v3);
}

```

## disassembly

```asm
0x14002812c  mov     rax, rsp
0x14002812f  mov     [rax+10h], rbx
0x140028133  mov     [rax+18h], rsi
0x140028137  mov     [rax+20h], rdi
0x14002813b  push    rbp
0x14002813c  push    r12
0x14002813e  push    r13
0x140028140  push    r14
0x140028142  push    r15
0x140028144  lea     rbp, [rax-5Fh]
0x140028148  sub     rsp, 0B0h
0x14002814f  mov     rax, cs:__security_cookie
0x140028156  xor     rax, rsp
0x140028159  mov     [rbp+57h+var_28], rax
0x14002815d  mov     r14, rcx
0x140028160  xor     r13d, r13d
0x140028163  cmp     qword ptr [rcx+18h], 7
0x140028168  jbe     short loc_14002816D
0x14002816a  mov     rcx, [rcx]; psz
0x14002816d  call    cs:__imp_SysAllocString
0x140028173  mov     rbx, rax
0x140028176  mov     [rbp+57h+var_70], rax
0x14002817a  test    rax, rax
0x14002817d  jz      loc_1400284DC
0x140028183  mov     rcx, rax; wchar_t *
0x140028186  call    ?GetSLSDOMDocument@SLSParser@sih@@CAPEAUIXMLDOMDocument2@@PEA_W@Z; sih::SLSParser::GetSLSDOMDocument(wchar_t *)
0x14002818b  mov     rdi, rax
0x14002818e  mov     [rbp+57h+var_68], rax
0x140028192  mov     [rbp+57h+EndPtr], r13
0x140028196  mov     rax, [rax]
0x140028199  lea     rdx, [rbp+57h+EndPtr]
0x14002819d  mov     rcx, rdi
0x1400281a0  mov     rax, [rax+168h]
0x1400281a7  call    _guard_dispatch_icall
0x1400281ac  mov     ecx, eax; this
0x1400281ae  call    ?CheckXmlResult@sih@@YAXJJ@Z; sih::CheckXmlResult(long,long)
0x1400281b3  mov     r15, [rbp+57h+EndPtr]
0x1400281b7  mov     [rbp+57h+var_60], r15
0x1400281bb  mov     [rbp+57h+var_50], r13
0x1400281bf  mov     rax, [r15]
0x1400281c2  lea     r8, [rbp+57h+var_50]
0x1400281c6  lea     rdx, aServiceenviron; "/ServiceEnvironment"
0x1400281cd  mov     rcx, r15
0x1400281d0  mov     rax, [rax+128h]
0x1400281d7  call    _guard_dispatch_icall
0x1400281dc  mov     ecx, eax; this
0x1400281de  call    ?CheckXmlResult@sih@@YAXJJ@Z; sih::CheckXmlResult(long,long)
0x1400281e3  xorps   xmm0, xmm0
0x1400281e6  movups  [rbp+57h+var_40], xmm0
0x1400281ea  mov     rdx, [rbp+57h+var_50]; struct IXMLDOMNode *
0x1400281ee  lea     rcx, [rbp+57h+var_40]; this
0x1400281f2  call    ??0XmlNodeWrapper@sih@@QEAA@PEAUIXMLDOMNode@@@Z; sih::XmlNodeWrapper::XmlNodeWrapper(IXMLDOMNode *)
0x1400281f7  nop
0x1400281f8  xor     r9d, r9d
0x1400281fb  lea     r8, aRevision; "Revision"
0x140028202  mov     rdx, qword ptr [rbp+57h+var_40+8]
0x140028206  lea     rcx, [rbp+57h+String]
0x14002820a  call    ?GetAttrValue@utils@sih@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUIXMLDOMNamedNodeMap@@PEB_W_N@Z; sih::utils::GetAttrValue(IXMLDOMNamedNodeMap *,wchar_t const *,bool)
0x14002820f  nop
0x140028210  call    _o__errno_0
0x140028215  mov     r12, rax
0x140028218  lea     rsi, [rbp+57h+String]
0x14002821c  cmp     [rbp+57h+var_78], 7
0x140028221  cmova   rsi, [rbp+57h+String]
0x140028226  mov     [rbp+57h+EndPtr], r13
0x14002822a  mov     [rax], r13d
0x14002822d  mov     r8d, 0Ah; Radix
0x140028233  lea     rdx, [rbp+57h+EndPtr]; EndPtr
0x140028237  mov     rcx, rsi; String
0x14002823a  call    _o_wcstoul_0
0x14002823f  cmp     rsi, [rbp+57h+EndPtr]
0x140028243  jz      loc_140028504
0x140028249  cmp     dword ptr [r12], 22h ; '"'
0x14002824e  jz      loc_14002850A
0x140028254  mov     [r14+20h], eax
0x140028258  lea     rcx, [rbp+57h+String]; void *
0x14002825c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140028261  nop
0x140028262  mov     rcx, qword ptr [rbp+57h+var_40+8]
0x140028266  test    rcx, rcx
0x140028269  jz      short loc_14002827B
0x14002826b  mov     rax, [rcx]
0x14002826e  mov     rax, [rax+10h]
0x140028272  call    _guard_dispatch_icall
0x140028277  mov     qword ptr [rbp+57h+var_40+8], r13
0x14002827b  mov     rcx, qword ptr [rbp+57h+var_40]
0x14002827f  test    rcx, rcx
0x140028282  jz      short loc_140028294
0x140028284  mov     rax, [rcx]
0x140028287  mov     rax, [rax+10h]
0x14002828b  call    _guard_dispatch_icall
0x140028290  mov     qword ptr [rbp+57h+var_40], r13
0x140028294  mov     rcx, [rbp+57h+var_50]
0x140028298  test    rcx, rcx
0x14002829b  jz      short loc_1400282AA
0x14002829d  mov     rax, [rcx]
0x1400282a0  mov     rax, [rax+10h]
0x1400282a4  call    _guard_dispatch_icall
0x1400282a9  nop
0x1400282aa  mov     [rbp+57h+var_50], r13
0x1400282ae  mov     rax, [r15]
0x1400282b1  lea     r8, [rbp+57h+var_50]
0x1400282b5  lea     rdx, aServiceenviron_1; "/ServiceEnvironment[@ServiceID=\"E7A502"...
0x1400282bc  mov     rcx, r15
0x1400282bf  mov     rax, [rax+128h]
0x1400282c6  call    _guard_dispatch_icall
0x1400282cb  cmp     eax, 1
0x1400282ce  jz      loc_140028517
0x1400282d4  mov     ecx, eax; this
0x1400282d6  call    ?CheckXmlResult@sih@@YAXJJ@Z; sih::CheckXmlResult(long,long)
0x1400282db  xor     r8d, r8d
0x1400282de  mov     rdx, [rbp+57h+var_50]
0x1400282e2  lea     rcx, [rbp+57h+EndPtr]
0x1400282e6  call    ?ParsePackage@SLSParser@sih@@CA?AV?$unique_ptr@VPackageMetadata@sih@@U?$default_delete@VPackageMetadata@sih@@@std@@@std@@PEAUIXMLDOMNode@@W4PackageType@2@@Z; sih::SLSParser::ParsePackage(IXMLDOMNode *,sih::PackageType)
0x1400282eb  mov     rcx, [rax]
0x1400282ee  mov     [rax], r13
0x1400282f1  mov     rsi, [r14+28h]
0x1400282f5  mov     [r14+28h], rcx
0x1400282f9  mov     r12d, 0A0h
0x1400282ff  test    rsi, rsi
0x140028302  jz      short loc_14002833F
0x140028304  lea     rcx, [rsi+88h]
0x14002830b  call    ?_Tidy@?$vector@VFileMetadata@sih@@V?$allocator@VFileMetadata@sih@@@std@@@std@@AEAAXXZ; std::vector<sih::FileMetadata>::_Tidy(void)
0x140028310  lea     rcx, [rsi+60h]; void *
0x140028314  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140028319  lea     rcx, [rsi+48h]
0x14002831d  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x140028322  lea     rcx, [rsi+28h]; void *
0x140028326  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002832b  lea     rcx, [rsi+8]; void *
0x14002832f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140028334  mov     edx, r12d; struct std::nothrow_t *
0x140028337  mov     rcx, rsi; void *
0x14002833a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002833f  mov     rsi, [rbp+57h+EndPtr]
0x140028343  test    rsi, rsi
0x140028346  jz      short loc_140028384
0x140028348  lea     rcx, [rsi+88h]
0x14002834f  call    ?_Tidy@?$vector@VFileMetadata@sih@@V?$allocator@VFileMetadata@sih@@@std@@@std@@AEAAXXZ; std::vector<sih::FileMetadata>::_Tidy(void)
0x140028354  lea     rcx, [rsi+60h]; void *
0x140028358  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002835d  lea     rcx, [rsi+48h]
0x140028361  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x140028366  lea     rcx, [rsi+28h]; void *
0x14002836a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002836f  lea     rcx, [rsi+8]; void *
0x140028373  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140028378  mov     rdx, r12; struct std::nothrow_t *
0x14002837b  mov     rcx, rsi; void *
0x14002837e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140028383  nop
0x140028384  mov     rcx, [rbp+57h+var_50]
0x140028388  test    rcx, rcx
0x14002838b  jz      short loc_14002839A
0x14002838d  mov     rax, [rcx]
0x140028390  mov     rax, [rax+10h]
0x140028394  call    _guard_dispatch_icall
0x140028399  nop
0x14002839a  mov     [rbp+57h+var_50], r13
0x14002839e  mov     rax, [r15]
0x1400283a1  lea     r8, [rbp+57h+var_50]
0x1400283a5  lea     rdx, aServiceenviron_0; "/ServiceEnvironment[@ServiceID=\"E7A502"...
0x1400283ac  mov     rcx, r15
0x1400283af  mov     rax, [rax+120h]
0x1400283b6  call    _guard_dispatch_icall
0x1400283bb  mov     ecx, eax; this
0x1400283bd  call    ?CheckXmlResult@sih@@YAXJJ@Z; sih::CheckXmlResult(long,long)
0x1400283c2  mov     [rbp+57h+var_48], r13d
0x1400283c6  mov     rcx, [rbp+57h+var_50]
0x1400283ca  mov     rax, [rcx]
0x1400283cd  lea     rdx, [rbp+57h+var_48]
0x1400283d1  mov     rax, [rax+40h]
0x1400283d5  call    _guard_dispatch_icall
0x1400283da  test    eax, eax
0x1400283dc  js      loc_1400284A4
0x1400283e2  mov     esi, r13d
0x1400283e5  cmp     [rbp+57h+var_48], r13d
0x1400283e9  jle     short loc_140028438
0x1400283eb  mov     [rbp+57h+EndPtr], r13
0x1400283ef  mov     rcx, [rbp+57h+var_50]
0x1400283f3  mov     rax, [rcx]
0x1400283f6  lea     r8, [rbp+57h+EndPtr]
0x1400283fa  mov     edx, esi
0x1400283fc  mov     rax, [rax+38h]
0x140028400  call    _guard_dispatch_icall
0x140028405  test    eax, eax
0x140028407  js      loc_1400284C0
0x14002840d  lea     rdx, [r14+30h]
0x140028411  mov     rcx, [rbp+57h+EndPtr]; struct IXMLDOMNode *
0x140028415  call    ?ParseAction@SLSParser@sih@@CAXPEAUIXMLDOMNode@@AEAV?$vector@VAction@sih@@V?$allocator@VAction@sih@@@std@@@std@@@Z; sih::SLSParser::ParseAction(IXMLDOMNode *,std::vector<sih::Action> &)
0x14002841a  nop
0x14002841b  mov     rcx, [rbp+57h+EndPtr]
0x14002841f  test    rcx, rcx
0x140028422  jz      short loc_140028431
0x140028424  mov     rax, [rcx]
0x140028427  mov     rax, [rax+10h]
0x14002842b  call    _guard_dispatch_icall
0x140028430  nop
0x140028431  inc     esi
0x140028433  cmp     esi, [rbp+57h+var_48]
0x140028436  jl      short loc_1400283EB
0x140028438  mov     rcx, [rbp+57h+var_50]
0x14002843c  test    rcx, rcx
0x14002843f  jz      short loc_14002844E
0x140028441  mov     rax, [rcx]
0x140028444  mov     rax, [rax+10h]
0x140028448  call    _guard_dispatch_icall
0x14002844d  nop
0x14002844e  mov     rax, [r15]
0x140028451  mov     rcx, r15
0x140028454  mov     rax, [rax+10h]
0x140028458  call    _guard_dispatch_icall
0x14002845d  nop
0x14002845e  mov     rax, [rdi]
0x140028461  mov     rcx, rdi
0x140028464  mov     rax, [rax+10h]
0x140028468  call    _guard_dispatch_icall
0x14002846d  nop
0x14002846e  mov     rcx, rbx; bstrString
0x140028471  call    cs:__imp_SysFreeString
0x140028477  mov     rcx, [rbp+57h+var_28]
0x14002847b  xor     rcx, rsp; StackCookie
0x14002847e  call    __security_check_cookie
0x140028483  lea     r11, [rsp+0D0h+var_20]
0x14002848b  mov     rbx, [r11+38h]
0x14002848f  mov     rsi, [r11+40h]
0x140028493  mov     rdi, [r11+48h]
0x140028497  mov     rsp, r11
0x14002849a  pop     r15
0x14002849c  pop     r14
0x14002849e  pop     r13
0x1400284a0  pop     r12
0x1400284a2  pop     rbp
0x1400284a3  retn
0x1400284a4  mov     edx, eax; int
0x1400284a6  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1400284aa  call    ??0hr_exception@sih@@QEAA@J@Z; sih::hr_exception::hr_exception(long)
0x1400284af  lea     rdx, _TI3?AVhr_exception@sih@@; pThrowInfo
0x1400284b6  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400284ba  call    _CxxThrowException
0x1400284c0  mov     edx, eax; int
0x1400284c2  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1400284c6  call    ??0hr_exception@sih@@QEAA@J@Z; sih::hr_exception::hr_exception(long)
0x1400284cb  lea     rdx, _TI3?AVhr_exception@sih@@; pThrowInfo
0x1400284d2  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400284d6  call    _CxxThrowException
0x1400284dc  lea     rcx, [rbp+57h+var_40]; this
0x1400284e0  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x1400284e5  nop
0x1400284e6  lea     rdx, [rbp+57h+var_40]
0x1400284ea  lea     rcx, [rbp+57h+pExceptionObject]
0x1400284ee  call    ??0bad_alloc@std@@QEAA@$$QEAV01@@Z; std::bad_alloc::bad_alloc(std::bad_alloc &&)
0x1400284f3  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1400284fa  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400284fe  call    _CxxThrowException
0x140028504  call    ?_Xinvalid_argument@std@@YAXPEBD@Z; std::_Xinvalid_argument(char const *)
0x14002850a  lea     rcx, aStoulArgumentO; "stoul argument out of range"
0x140028511  call    ?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x140028517  mov     edx, 80245108h; int
0x14002851c  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140028520  call    ??0hr_exception@sih@@QEAA@J@Z; sih::hr_exception::hr_exception(long)
0x140028525  lea     rdx, _TI3?AVhr_exception@sih@@; pThrowInfo
0x14002852c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140028530  call    _CxxThrowException
```
