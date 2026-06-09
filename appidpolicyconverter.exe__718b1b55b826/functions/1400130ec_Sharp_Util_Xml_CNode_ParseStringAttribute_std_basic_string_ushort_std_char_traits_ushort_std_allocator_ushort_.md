# Sharp::Util::Xml::CNode::ParseStringAttribute(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1400130ec`
- end: `0x140013330`
- name: `?ParseStringAttribute@CNode@Xml@Util@Sharp@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@@Z`
- size: `580`
- prototype: `OLECHAR *__fastcall(__int64, OLECHAR *, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000a560`
- `0x14000cba0`
- `0x14000dc30`
- `0x14000f200`
- `0x140010d90`
- `0x140012fa0`
- `0x140013044`

## callees

- `0x140001d1c`
- `0x1400070e4`
- `0x140007428`
- `0x140007de4`
- `0x140007e8c`
- `0x1400119d4`
- `0x140011a6c`
- `0x1400130ec`
- `0x140013b10`
- `0x140016010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14001320f`
- `OLEAUT32!__imp_SysFreeString` at `0x1400132ef`
- `OLEAUT32!__imp_SysFreeString` at `0x14001320f`
- `OLEAUT32!__imp_SysFreeString` at `0x1400132ef`

## pseudocode

```c
OLECHAR *__fastcall Sharp::Util::Xml::CNode::ParseStringAttribute(__int64 a1, OLECHAR *a2, const unsigned __int16 *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rbx
  __int64 (__fastcall *v9)(__int64, _QWORD, __int64 *); // r14
  ATL::CComBSTR *v10; // rax
  int v11; // ebx
  int v12; // eax
  int v13; // ebx
  __int64 v15; // [rsp+20h] [rbp-49h] BYREF
  __int64 v16; // [rsp+28h] [rbp-41h] BYREF
  int v17; // [rsp+30h] [rbp-39h]
  BSTR v18; // [rsp+38h] [rbp-31h] BYREF
  BSTR bstrString[2]; // [rsp+40h] [rbp-29h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+50h] [rbp-19h] BYREF

  bstrString[1] = a2;
  v17 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids);
  v16 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 8) + 136LL))(*(_QWORD *)(a1 + 8), &v16);
  v7 = v6;
  if ( !v16 )
  {
    v7 = -2147467259;
    goto LABEL_7;
  }
  if ( v6 < 0 )
  {
LABEL_7:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids, v7);
    xml_exception::xml_exception((xml_exception *)pExceptionObject, v7);
    throw (xml_exception *)pExceptionObject;
  }
  v15 = 0;
  v8 = v16;
  v9 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v16 + 56LL);
  if ( *((_QWORD *)a3 + 3) >= 8u )
    a3 = *(const unsigned __int16 **)a3;
  v10 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, a3);
  v11 = v9(v8, *(_QWORD *)v10, &v15);
  SysFreeString(bstrString[0]);
  if ( !v15 )
  {
    v11 = -2147024809;
LABEL_16:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        44,
        WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids,
        (unsigned int)v11);
    xml_exception::xml_exception((xml_exception *)pExceptionObject, v11);
    throw (xml_exception *)pExceptionObject;
  }
  if ( v11 < 0 )
    goto LABEL_16;
  v18 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v15 + 208LL))(v15, &v18);
  v13 = v12;
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids,
        (unsigned int)v12);
    xml_exception::xml_exception((xml_exception *)pExceptionObject, v13);
    throw (xml_exception *)pExceptionObject;
  }
  Sharp::Util::ComHelper::ComBstrToString((__int64)a2, (__int64 *)&v18);
  v17 = 1;
  SysFreeString(v18);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v15);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v16);
  return a2;
}

```

## disassembly

```asm
0x1400130ec  mov     [rsp-8+arg_18], rbx
0x1400130f1  push    rbp
0x1400130f2  push    rsi
0x1400130f3  push    rdi
0x1400130f4  push    r12
0x1400130f6  push    r14
0x1400130f8  lea     rbp, [rsp-37h]
0x1400130fd  sub     rsp, 0A0h
0x140013104  mov     rax, cs:__security_cookie
0x14001310b  xor     rax, rsp
0x14001310e  mov     [rbp+57h+var_30], rax
0x140013112  mov     rdi, r8
0x140013115  mov     rsi, rdx
0x140013118  mov     rbx, rcx
0x14001311b  mov     [rbp+57h+var_78], rdx
0x14001311f  mov     [rbp+57h+var_90], 0
0x140013126  lea     r12, WPP_GLOBAL_Control
0x14001312d  mov     rcx, cs:WPP_GLOBAL_Control
0x140013134  cmp     rcx, r12
0x140013137  jz      short loc_140013154
0x140013139  test    byte ptr [rcx+1Ch], 8
0x14001313d  jz      short loc_140013154
0x14001313f  mov     edx, 2Ah ; '*'
0x140013144  lea     r8, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids
0x14001314b  mov     rcx, [rcx+10h]
0x14001314f  call    WPP_SF_
0x140013154  mov     [rbp+57h+var_98], 0
0x14001315c  mov     rcx, [rbx+8]
0x140013160  mov     rax, [rcx]
0x140013163  lea     rdx, [rbp+57h+var_98]
0x140013167  mov     rax, [rax+88h]
0x14001316e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013173  mov     ebx, eax
0x140013175  cmp     [rbp+57h+var_98], 0
0x14001317a  jnz     short loc_140013183
0x14001317c  mov     ebx, 80004005h
0x140013181  jmp     short loc_140013187
0x140013183  test    eax, eax
0x140013185  jns     short loc_1400131CD
0x140013187  mov     rcx, cs:WPP_GLOBAL_Control
0x14001318e  cmp     rcx, r12
0x140013191  jz      short loc_1400131B1
0x140013193  test    byte ptr [rcx+1Ch], 1
0x140013197  jz      short loc_1400131B1
0x140013199  mov     edx, 2Bh ; '+'
0x14001319e  mov     r9d, ebx
0x1400131a1  lea     r8, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids
0x1400131a8  mov     rcx, [rcx+10h]
0x1400131ac  call    WPP_SF_d
0x1400131b1  mov     edx, ebx; int
0x1400131b3  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1400131b7  call    ??0xml_exception@@QEAA@J@Z; xml_exception::xml_exception(long)
0x1400131bc  lea     rdx, _TI3?AVxml_exception@@; pThrowInfo
0x1400131c3  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400131c7  call    _CxxThrowException_0
0x1400131cd  mov     [rbp+57h+var_A0], 0
0x1400131d5  mov     rbx, [rbp+57h+var_98]
0x1400131d9  mov     rax, [rbx]
0x1400131dc  mov     r14, [rax+38h]
0x1400131e0  cmp     qword ptr [rdi+18h], 8
0x1400131e5  jb      short loc_1400131EA
0x1400131e7  mov     rdi, [rdi]
0x1400131ea  mov     rdx, rdi; unsigned __int16 *
0x1400131ed  lea     rcx, [rbp+57h+bstrString]; this
0x1400131f1  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1400131f6  nop
0x1400131f7  lea     r8, [rbp+57h+var_A0]
0x1400131fb  mov     rdx, [rax]
0x1400131fe  mov     rcx, rbx
0x140013201  mov     rax, r14
0x140013204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013209  mov     ebx, eax
0x14001320b  mov     rcx, [rbp+57h+bstrString]; bstrString
0x14001320f  call    cs:__imp_SysFreeString
0x140013215  cmp     [rbp+57h+var_A0], 0
0x14001321a  jnz     short loc_140013223
0x14001321c  mov     ebx, 80070057h
0x140013221  jmp     short loc_140013227
0x140013223  test    ebx, ebx
0x140013225  jns     short loc_14001326D
0x140013227  mov     rcx, cs:WPP_GLOBAL_Control
0x14001322e  cmp     rcx, r12
0x140013231  jz      short loc_140013251
0x140013233  test    byte ptr [rcx+1Ch], 1
0x140013237  jz      short loc_140013251
0x140013239  mov     edx, 2Ch ; ','
0x14001323e  mov     r9d, ebx
0x140013241  lea     r8, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids
0x140013248  mov     rcx, [rcx+10h]
0x14001324c  call    WPP_SF_d
0x140013251  mov     edx, ebx; int
0x140013253  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140013257  call    ??0xml_exception@@QEAA@J@Z; xml_exception::xml_exception(long)
0x14001325c  lea     rdx, _TI3?AVxml_exception@@; pThrowInfo
0x140013263  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140013267  call    _CxxThrowException_0
0x14001326d  mov     [rbp+57h+var_88], 0
0x140013275  mov     rcx, [rbp+57h+var_A0]
0x140013279  mov     rax, [rcx]
0x14001327c  lea     rdx, [rbp+57h+var_88]
0x140013280  mov     rax, [rax+0D0h]
0x140013287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001328c  mov     ebx, eax
0x14001328e  test    eax, eax
0x140013290  jns     short loc_1400132D8
0x140013292  mov     rcx, cs:WPP_GLOBAL_Control
0x140013299  cmp     rcx, r12
0x14001329c  jz      short loc_1400132BC
0x14001329e  test    byte ptr [rcx+1Ch], 1
0x1400132a2  jz      short loc_1400132BC
0x1400132a4  mov     edx, 2Dh ; '-'
0x1400132a9  mov     r9d, eax
0x1400132ac  lea     r8, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids
0x1400132b3  mov     rcx, [rcx+10h]
0x1400132b7  call    WPP_SF_d
0x1400132bc  mov     edx, ebx; int
0x1400132be  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1400132c2  call    ??0xml_exception@@QEAA@J@Z; xml_exception::xml_exception(long)
0x1400132c7  lea     rdx, _TI3?AVxml_exception@@; pThrowInfo
0x1400132ce  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400132d2  call    _CxxThrowException_0
0x1400132d8  lea     rdx, [rbp+57h+var_88]
0x1400132dc  mov     rcx, rsi
0x1400132df  call    ?ComBstrToString@ComHelper@Util@Sharp@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVCComBSTR@ATL@@@Z; Sharp::Util::ComHelper::ComBstrToString(ATL::CComBSTR const &)
0x1400132e4  mov     [rbp+57h+var_90], 1
0x1400132eb  mov     rcx, [rbp+57h+var_88]; bstrString
0x1400132ef  call    cs:__imp_SysFreeString
0x1400132f5  nop
0x1400132f6  lea     rcx, [rbp+57h+var_A0]
0x1400132fa  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1400132ff  nop
0x140013300  lea     rcx, [rbp+57h+var_98]
0x140013304  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x140013309  mov     rax, rsi
0x14001330c  mov     rcx, [rbp+57h+var_30]
0x140013310  xor     rcx, rsp; StackCookie
0x140013313  call    __security_check_cookie
0x140013318  mov     rbx, [rsp+0C0h+arg_18]
0x140013320  add     rsp, 0A0h
0x140013327  pop     r14
0x140013329  pop     r12
0x14001332b  pop     rdi
0x14001332c  pop     rsi
0x14001332d  pop     rbp
0x14001332e  retn
```
