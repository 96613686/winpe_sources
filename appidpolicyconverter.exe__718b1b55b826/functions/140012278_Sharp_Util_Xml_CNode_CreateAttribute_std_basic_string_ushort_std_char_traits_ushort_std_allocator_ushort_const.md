# Sharp::Util::Xml::CNode::CreateAttribute(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ATL::CComVariant const &)

- ea: `0x140012278`
- end: `0x1400125fd`
- name: `?CreateAttribute@CNode@Xml@Util@Sharp@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVCComVariant@ATL@@@Z`
- size: `901`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, VARIANTARG *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140011240`
- `0x140012604`

## callees

- `0x140001d1c`
- `0x1400070e4`
- `0x140007428`
- `0x140007de4`
- `0x1400119d4`
- `0x140011a6c`
- `0x140012278`
- `0x140013b10`
- `0x140016010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1400123a2`
- `OLEAUT32!__imp_SysFreeString` at `0x1400123ad`
- `OLEAUT32!__imp_SysFreeString` at `0x1400123a2`
- `OLEAUT32!__imp_SysFreeString` at `0x1400123ad`
- `OLEAUT32!__imp_VariantClear` at `0x140012396`
- `OLEAUT32!__imp_VariantClear` at `0x140012396`

## pseudocode

```c
__int64 __fastcall Sharp::Util::Xml::CNode::CreateAttribute(__int64 a1, const unsigned __int16 *a2, VARIANTARG *a3)
{
  int v6; // eax
  int v7; // ebx
  __int64 v8; // rbx
  __int64 (__fastcall *v9)(__int64, VARIANTARG *, __int64, __int64, __int64 *); // r12
  __int64 v10; // r15
  __int64 v11; // r8
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  __int64 v17; // [rsp+30h] [rbp-99h] BYREF
  __int64 v18; // [rsp+38h] [rbp-91h] BYREF
  __int64 v19; // [rsp+40h] [rbp-89h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-81h] BYREF
  BSTR v21[2]; // [rsp+50h] [rbp-79h] BYREF
  VARIANTARG v22; // [rsp+60h] [rbp-69h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-49h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+A0h] [rbp-29h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids);
  v18 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 8) + 184LL))(*(_QWORD *)(a1 + 8), &v18);
  v7 = v6;
  if ( v6 < 0 || !v18 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        57,
        WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids,
        (unsigned int)v6);
    xml_exception::xml_exception((xml_exception *)pExceptionObject, v7);
    throw (xml_exception *)pExceptionObject;
  }
  v17 = 0;
  v8 = v18;
  v9 = *(__int64 (__fastcall **)(__int64, VARIANTARG *, __int64, __int64, __int64 *))(*(_QWORD *)v18 + 448LL);
  v10 = *(_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)v21, &dword_140018714);
  if ( *((_QWORD *)a2 + 3) >= 8u )
    a2 = *(const unsigned __int16 **)a2;
  v11 = *(_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, a2);
  pvarg.vt = 3;
  pvarg.lVal = 2;
  v22 = pvarg;
  v12 = v9(v8, &v22, v11, v10, &v17);
  VariantClear(&pvarg);
  SysFreeString(bstrString);
  SysFreeString(v21[0]);
  if ( v12 < 0 || !v17 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        58,
        WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids,
        (unsigned int)v12);
    xml_exception::xml_exception((xml_exception *)pExceptionObject, v12);
    throw (xml_exception *)pExceptionObject;
  }
  v22 = *a3;
  v13 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v17 + 72LL))(v17, &v22);
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids,
        (unsigned int)v13);
    xml_exception::xml_exception((xml_exception *)pExceptionObject, v13);
    throw (xml_exception *)pExceptionObject;
  }
  v19 = 0;
  v14 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 8) + 136LL))(*(_QWORD *)(a1 + 8), &v19);
  if ( v14 < 0 || !v19 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids,
        (unsigned int)v14);
    xml_exception::xml_exception((xml_exception *)pExceptionObject, v14);
    throw (xml_exception *)pExceptionObject;
  }
  v15 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v19 + 64LL))(v19, v17, 0);
  if ( v15 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        61,
        WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids,
        (unsigned int)v15);
    xml_exception::xml_exception((xml_exception *)pExceptionObject, v15);
    throw (xml_exception *)pExceptionObject;
  }
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v19);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v17);
  return ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v18);
}

```

## disassembly

```asm
0x140012278  push    rbp
0x14001227a  push    rbx
0x14001227b  push    rsi
0x14001227c  push    rdi
0x14001227d  push    r12
0x14001227f  push    r14
0x140012281  push    r15
0x140012283  lea     rbp, [rsp-27h]
0x140012288  sub     rsp, 0F0h
0x14001228f  mov     rax, cs:__security_cookie
0x140012296  xor     rax, rsp
0x140012299  mov     [rbp+57h+var_40], rax
0x14001229d  mov     r14, r8
0x1400122a0  mov     rdi, rdx
0x1400122a3  mov     rsi, rcx
0x1400122a6  lea     r15, WPP_GLOBAL_Control
0x1400122ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400122b4  cmp     rcx, r15
0x1400122b7  jz      short loc_1400122D4
0x1400122b9  test    byte ptr [rcx+1Ch], 8
0x1400122bd  jz      short loc_1400122D4
0x1400122bf  mov     edx, 38h ; '8'
0x1400122c4  lea     r8, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids
0x1400122cb  mov     rcx, [rcx+10h]
0x1400122cf  call    WPP_SF_
0x1400122d4  mov     [rsp+120h+var_E8], 0
0x1400122dd  mov     rcx, [rsi+8]
0x1400122e1  mov     rax, [rcx]
0x1400122e4  lea     rdx, [rsp+120h+var_E8]
0x1400122e9  mov     rax, [rax+0B8h]
0x1400122f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400122f5  mov     ebx, eax
0x1400122f7  test    eax, eax
0x1400122f9  js      loc_1400125B7
0x1400122ff  cmp     [rsp+120h+var_E8], 0
0x140012305  jz      loc_1400125B7
0x14001230b  mov     [rsp+120h+var_F0], 0
0x140012314  mov     rbx, [rsp+120h+var_E8]
0x140012319  mov     rax, [rbx]
0x14001231c  mov     r12, [rax+1C0h]
0x140012323  lea     rdx, dword_140018714; unsigned __int16 *
0x14001232a  lea     rcx, [rbp+57h+var_D0]; this
0x14001232e  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x140012333  nop
0x140012334  mov     r15, [rax]
0x140012337  cmp     qword ptr [rdi+18h], 8
0x14001233c  jb      short loc_140012341
0x14001233e  mov     rdi, [rdi]
0x140012341  mov     rdx, rdi; unsigned __int16 *
0x140012344  lea     rcx, [rsp+120h+bstrString]; this
0x140012349  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x14001234e  nop
0x14001234f  mov     r8, [rax]
0x140012352  mov     eax, 3
0x140012357  mov     word ptr [rbp+57h+pvarg], ax
0x14001235b  mov     dword ptr [rbp+57h+pvarg+8], 2
0x140012362  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x140012366  movaps  [rbp+57h+var_C0], xmm0
0x14001236a  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x14001236f  movsd   [rbp+57h+var_B0], xmm1
0x140012374  lea     rax, [rsp+120h+var_F0]
0x140012379  mov     [rsp+120h+var_100], rax
0x14001237e  mov     r9, r15
0x140012381  lea     rdx, [rbp+57h+var_C0]
0x140012385  mov     rcx, rbx
0x140012388  mov     rax, r12
0x14001238b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012390  mov     ebx, eax
0x140012392  lea     rcx, [rbp+57h+pvarg]; pvarg
0x140012396  call    cs:__imp_VariantClear
0x14001239c  nop
0x14001239d  mov     rcx, [rsp+120h+bstrString]; bstrString
0x1400123a2  call    cs:__imp_SysFreeString
0x1400123a8  nop
0x1400123a9  mov     rcx, [rbp+57h+var_D0]; bstrString
0x1400123ad  call    cs:__imp_SysFreeString
0x1400123b3  test    ebx, ebx
0x1400123b5  js      loc_14001256A
0x1400123bb  mov     rcx, [rsp+120h+var_F0]
0x1400123c0  test    rcx, rcx
0x1400123c3  jz      loc_14001256A
0x1400123c9  movups  xmm0, xmmword ptr [r14]
0x1400123cd  movaps  [rbp+57h+var_C0], xmm0
0x1400123d1  movsd   xmm1, qword ptr [r14+10h]
0x1400123d7  movsd   [rbp+57h+var_B0], xmm1
0x1400123dc  mov     rax, [rcx]
0x1400123df  lea     rdx, [rbp+57h+var_C0]
0x1400123e3  mov     rax, [rax+48h]
0x1400123e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400123ec  mov     ebx, eax
0x1400123ee  test    eax, eax
0x1400123f0  jns     short loc_14001243F
0x1400123f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400123f9  lea     rax, WPP_GLOBAL_Control
0x140012400  cmp     rcx, rax
0x140012403  jz      short loc_140012423
0x140012405  test    byte ptr [rcx+1Ch], 1
0x140012409  jz      short loc_140012423
0x14001240b  mov     edx, 3Bh ; ';'
0x140012410  mov     r9d, ebx
0x140012413  lea     r8, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids
0x14001241a  mov     rcx, [rcx+10h]
0x14001241e  call    WPP_SF_d
0x140012423  mov     edx, ebx; int
0x140012425  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140012429  call    ??0xml_exception@@QEAA@J@Z; xml_exception::xml_exception(long)
0x14001242e  lea     rdx, _TI3?AVxml_exception@@; pThrowInfo
0x140012435  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140012439  call    _CxxThrowException_0
0x14001243f  mov     [rsp+120h+var_E0], 0
0x140012448  mov     rcx, [rsi+8]
0x14001244c  mov     rax, [rcx]
0x14001244f  lea     rdx, [rsp+120h+var_E0]
0x140012454  mov     rax, [rax+88h]
0x14001245b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012460  mov     ebx, eax
0x140012462  test    eax, eax
0x140012464  js      loc_14001251D
0x14001246a  mov     rcx, [rsp+120h+var_E0]
0x14001246f  test    rcx, rcx
0x140012472  jz      loc_14001251D
0x140012478  mov     rax, [rcx]
0x14001247b  xor     r8d, r8d
0x14001247e  mov     rdx, [rsp+120h+var_F0]
0x140012483  mov     rax, [rax+40h]
0x140012487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001248c  mov     ebx, eax
0x14001248e  test    eax, eax
0x140012490  jns     short loc_1400124DF
0x140012492  mov     rcx, cs:WPP_GLOBAL_Control
0x140012499  lea     rax, WPP_GLOBAL_Control
0x1400124a0  cmp     rcx, rax
0x1400124a3  jz      short loc_1400124C3
0x1400124a5  test    byte ptr [rcx+1Ch], 1
0x1400124a9  jz      short loc_1400124C3
0x1400124ab  mov     edx, 3Dh ; '='
0x1400124b0  mov     r9d, ebx
0x1400124b3  lea     r8, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids
0x1400124ba  mov     rcx, [rcx+10h]
0x1400124be  call    WPP_SF_d
0x1400124c3  mov     edx, ebx; int
0x1400124c5  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1400124c9  call    ??0xml_exception@@QEAA@J@Z; xml_exception::xml_exception(long)
0x1400124ce  lea     rdx, _TI3?AVxml_exception@@; pThrowInfo
0x1400124d5  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400124d9  call    _CxxThrowException_0
0x1400124df  lea     rcx, [rsp+120h+var_E0]
0x1400124e4  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1400124e9  nop
0x1400124ea  lea     rcx, [rsp+120h+var_F0]
0x1400124ef  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1400124f4  nop
0x1400124f5  lea     rcx, [rsp+120h+var_E8]
0x1400124fa  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1400124ff  mov     rcx, [rbp+57h+var_40]
0x140012503  xor     rcx, rsp; StackCookie
0x140012506  call    __security_check_cookie
0x14001250b  add     rsp, 0F0h
0x140012512  pop     r15
0x140012514  pop     r14
0x140012516  pop     r12
0x140012518  pop     rdi
0x140012519  pop     rsi
0x14001251a  pop     rbx
0x14001251b  pop     rbp
0x14001251c  retn
0x14001251d  mov     rcx, cs:WPP_GLOBAL_Control
0x140012524  lea     rax, WPP_GLOBAL_Control
0x14001252b  cmp     rcx, rax
0x14001252e  jz      short loc_14001254E
0x140012530  test    byte ptr [rcx+1Ch], 1
0x140012534  jz      short loc_14001254E
0x140012536  mov     edx, 3Ch ; '<'
0x14001253b  mov     r9d, ebx
0x14001253e  lea     r8, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids
0x140012545  mov     rcx, [rcx+10h]
0x140012549  call    WPP_SF_d
0x14001254e  mov     edx, ebx; int
0x140012550  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140012554  call    ??0xml_exception@@QEAA@J@Z; xml_exception::xml_exception(long)
0x140012559  lea     rdx, _TI3?AVxml_exception@@; pThrowInfo
0x140012560  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140012564  call    _CxxThrowException_0
0x14001256a  mov     rcx, cs:WPP_GLOBAL_Control
0x140012571  lea     rax, WPP_GLOBAL_Control
0x140012578  cmp     rcx, rax
0x14001257b  jz      short loc_14001259B
0x14001257d  test    byte ptr [rcx+1Ch], 1
0x140012581  jz      short loc_14001259B
0x140012583  mov     edx, 3Ah ; ':'
0x140012588  mov     r9d, ebx
0x14001258b  lea     r8, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids
0x140012592  mov     rcx, [rcx+10h]
0x140012596  call    WPP_SF_d
0x14001259b  mov     edx, ebx; int
0x14001259d  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1400125a1  call    ??0xml_exception@@QEAA@J@Z; xml_exception::xml_exception(long)
0x1400125a6  lea     rdx, _TI3?AVxml_exception@@; pThrowInfo
0x1400125ad  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400125b1  call    _CxxThrowException_0
0x1400125b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400125be  cmp     rcx, r15
0x1400125c1  jz      short loc_1400125E1
0x1400125c3  test    byte ptr [rcx+1Ch], 1
0x1400125c7  jz      short loc_1400125E1
0x1400125c9  mov     edx, 39h ; '9'
0x1400125ce  mov     r9d, ebx
0x1400125d1  lea     r8, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids
0x1400125d8  mov     rcx, [rcx+10h]
0x1400125dc  call    WPP_SF_d
0x1400125e1  mov     edx, ebx; int
0x1400125e3  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1400125e7  call    ??0xml_exception@@QEAA@J@Z; xml_exception::xml_exception(long)
0x1400125ec  lea     rdx, _TI3?AVxml_exception@@; pThrowInfo
0x1400125f3  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400125f7  call    _CxxThrowException_0
```
