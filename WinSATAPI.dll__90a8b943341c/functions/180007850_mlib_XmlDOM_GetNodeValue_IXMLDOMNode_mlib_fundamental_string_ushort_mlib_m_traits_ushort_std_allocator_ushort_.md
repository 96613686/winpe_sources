# mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,ushort * &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180007850`
- end: `0x180007b7b`
- name: `?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEAPEAGPEAV42@@Z`
- size: `811`
- prototype: ``
- caller_count: `7`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180005080`
- `0x180007128`
- `0x1800074f0`
- `0x180007570`
- `0x180008b30`
- `0x18002e864`
- `0x18002e8fc`

## callees

- `0x180006494`
- `0x180007850`
- `0x180007ea0`
- `0x18000e490`
- `0x180011e70`
- `0x180011ee0`
- `0x180012c06`
- `0x180033010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000792a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007939`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000792a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007939`

## string_xrefs

- `0x180007a77`: `base\winsat\mlib\mxmldom.cpp`
- `0x180007acb`: `base\winsat\mlib\mxmldom.cpp`
- `0x180007b1f`: `base\winsat\mlib\mxmldom.cpp`
- `0x180007af5`: `cannot get text for an XML node`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall mlib::XmlDOM::GetNodeValue(__int64 a1, __int64 a2, char a3, __int64 a4, int a5)
{
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  void *v11; // rax
  __int64 v12; // rcx
  int v13; // edi
  _QWORD *v14; // rbx
  void *v16; // rcx
  int v17; // eax
  int v18; // eax
  int v19; // ebx
  unsigned int v21; // ebx
  unsigned int v22; // ebx
  unsigned int v23; // ebx
  _QWORD *v24; // [rsp+40h] [rbp-38h] BYREF
  __int64 v25; // [rsp+48h] [rbp-30h] BYREF
  _QWORD *v26[2]; // [rsp+50h] [rbp-28h] BYREF

  v26[1] = (_QWORD *)-2LL;
  v24 = 0;
  v25 = 0;
  v9 = operator new(0x28u);
  v10 = v9;
  if ( !v9 )
    std::_Xbad_alloc();
  v26[0] = v9;
  v9[2] = 1;
  v9[3] = 0;
  *v9 = 0;
  v9[1] = 0;
  v11 = operator new(2u);
  if ( !v11 )
    std::_Xbad_alloc();
  v10[3] = v11;
  if ( *v10 )
    memcpy_0(v11, 0, 2LL * *v10);
  v12 = v10[3];
  if ( v12 )
    *(_WORD *)(v12 + 2LL * *v10) = 0;
  v26[0] = v10;
  v13 = mlib::XmlDOM::SelectXml(a1, a2, v26, &v24, 0);
  v14 = v26[0];
  if ( v26[0][2]-- == 1 )
  {
    v16 = (void *)v14[3];
    if ( v16 )
      operator delete(v16);
    operator delete(v14);
  }
  if ( v13 < 0 )
  {
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    if ( v24 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v24 + 16LL))(v24, *v24);
    return (unsigned int)v13;
  }
  else
  {
    a5 = 0;
    v17 = (*(__int64 (__fastcall **)(_QWORD *, int *))(*v24 + 64LL))(v24, &a5);
    if ( v17 < 0 )
    {
      v21 = mlib::XmlDOM::ReportCOMError_w(
              (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
              1717,
              v17,
              (_DWORD)v24,
              (__int64)&GUID_2933bf82_7b36_11d2_b20e_00c04f983e60,
              0,
              (__int64)L"cannot get the length of list");
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
      return v21;
    }
    if ( a5 <= 0 )
    {
      v19 = -2147467259;
      if ( a3 )
        v19 = 0;
    }
    else
    {
      v18 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(*v24 + 72LL))(v24, &v25);
      if ( v18 < 0 )
      {
        v22 = mlib::XmlDOM::ReportCOMError_w(
                (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                1726,
                v18,
                (_DWORD)v24,
                (__int64)&GUID_2933bf82_7b36_11d2_b20e_00c04f983e60,
                0,
                (__int64)L"cannot get the next node in a list");
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
        return v22;
      }
      v19 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 208LL))(v25, a4);
      if ( v19 < 0 )
      {
        v23 = mlib::XmlDOM::ReportCOMError_w(
                (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
                1734,
                v19,
                v25,
                (__int64)&GUID_2933bf80_7b36_11d2_b20e_00c04f983e60,
                0,
                (__int64)L"cannot get text for an XML node");
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
        return v23;
      }
    }
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    if ( v24 )
      (*(void (__fastcall **)(_QWORD *))(*v24 + 16LL))(v24);
    return (unsigned int)v19;
  }
}

```

## disassembly

```asm
0x180007850  mov     rax, rsp
0x180007853  push    r12
0x180007855  push    r14
0x180007857  push    r15
0x180007859  sub     rsp, 60h
0x18000785d  mov     qword ptr [rax-20h], 0FFFFFFFFFFFFFFFEh
0x180007865  mov     [rax+8], rbx
0x180007869  mov     [rax+10h], rsi
0x18000786d  mov     [rax+18h], rdi
0x180007871  mov     r14, r9
0x180007874  movzx   r15d, r8b
0x180007878  mov     rdi, rdx
0x18000787b  mov     rsi, rcx
0x18000787e  xor     r12d, r12d
0x180007881  mov     [rax-38h], r12
0x180007885  mov     [rax-30h], r12
0x180007889  lea     ecx, [r12+28h]; Size
0x18000788e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007893  mov     rbx, rax
0x180007896  test    rax, rax
0x180007899  jz      loc_180007A41
0x18000789f  mov     [rsp+78h+var_28], rax
0x1800078a4  mov     qword ptr [rax+10h], 1
0x1800078ac  mov     [rax+18h], r12
0x1800078b0  mov     [rax], r12
0x1800078b3  mov     [rax+8], r12
0x1800078b7  lea     ecx, [r12+2]; Size
0x1800078bc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800078c1  test    rax, rax
0x1800078c4  jz      loc_180007A47
0x1800078ca  mov     [rbx+18h], rax
0x1800078ce  mov     r8, [rbx]
0x1800078d1  test    r8, r8
0x1800078d4  jz      short loc_1800078E3
0x1800078d6  add     r8, r8; Size
0x1800078d9  xor     edx, edx; Src
0x1800078db  mov     rcx, rax; void *
0x1800078de  call    memcpy_0
0x1800078e3  mov     rcx, [rbx+18h]
0x1800078e7  test    rcx, rcx
0x1800078ea  jz      short loc_1800078F4
0x1800078ec  mov     rax, [rbx]
0x1800078ef  mov     [rcx+rax*2], r12w
0x1800078f4  mov     [rsp+78h+var_28], rbx
0x1800078f9  mov     [rsp+78h+var_58], r12
0x1800078fe  lea     r9, [rsp+78h+var_38]
0x180007903  lea     r8, [rsp+78h+var_28]
0x180007908  mov     rdx, rdi
0x18000790b  mov     rcx, rsi
0x18000790e  call    ?SelectXml@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@1PEAPEAUIXMLDOMNodeList@@PEAV42@@Z; mlib::XmlDOM::SelectXml(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,IXMLDOMNodeList * *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x180007913  mov     edi, eax
0x180007915  mov     rbx, [rsp+78h+var_28]
0x18000791a  sub     qword ptr [rbx+10h], 1
0x18000791f  jnz     short loc_180007945
0x180007921  mov     rcx, [rbx+18h]
0x180007925  test    rcx, rcx
0x180007928  jz      short loc_180007936
0x18000792a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007931  nop     dword ptr [rax+rax+00h]
0x180007936  mov     rcx, rbx
0x180007939  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007940  nop     dword ptr [rax+rax+00h]
0x180007945  test    edi, edi
0x180007947  js      loc_180007A0F
0x18000794d  mov     [rsp+78h+arg_20], r12d
0x180007955  mov     rcx, [rsp+78h+var_38]
0x18000795a  mov     rax, [rcx]
0x18000795d  lea     rdx, [rsp+78h+arg_20]
0x180007965  mov     rax, [rax+40h]
0x180007969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000796e  test    eax, eax
0x180007970  js      loc_180007A4D
0x180007976  cmp     [rsp+78h+arg_20], 0
0x18000797e  jle     loc_180007B49
0x180007984  mov     rcx, [rsp+78h+var_38]
0x180007989  mov     rax, [rcx]
0x18000798c  lea     rdx, [rsp+78h+var_30]
0x180007991  mov     rax, [rax+48h]
0x180007995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000799a  test    eax, eax
0x18000799c  js      loc_180007AA1
0x1800079a2  mov     rcx, [rsp+78h+var_30]
0x1800079a7  mov     rax, [rcx]
0x1800079aa  mov     rdx, r14
0x1800079ad  mov     rax, [rax+0D0h]
0x1800079b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079b9  mov     ebx, eax
0x1800079bb  test    eax, eax
0x1800079bd  js      loc_180007AF5
0x1800079c3  mov     rcx, [rsp+78h+var_30]
0x1800079c8  test    rcx, rcx
0x1800079cb  jz      short loc_1800079DA
0x1800079cd  mov     rax, [rcx]
0x1800079d0  mov     rax, [rax+10h]
0x1800079d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079d9  nop
0x1800079da  mov     rcx, [rsp+78h+var_38]
0x1800079df  test    rcx, rcx
0x1800079e2  jz      short loc_1800079F1
0x1800079e4  mov     rax, [rcx]
0x1800079e7  mov     rax, [rax+10h]
0x1800079eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079f0  nop
0x1800079f1  mov     eax, ebx
0x1800079f3  lea     r11, [rsp+78h+var_18]
0x1800079f8  mov     rbx, [r11+20h]
0x1800079fc  mov     rsi, [r11+28h]
0x180007a00  mov     rdi, [r11+30h]
0x180007a04  mov     rsp, r11
0x180007a07  pop     r15
0x180007a09  pop     r14
0x180007a0b  pop     r12
0x180007a0d  retn
0x180007a0f  mov     rcx, [rsp+78h+var_30]
0x180007a14  test    rcx, rcx
0x180007a17  jz      short loc_180007A26
0x180007a19  mov     rax, [rcx]
0x180007a1c  mov     rax, [rax+10h]
0x180007a20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a25  nop
0x180007a26  mov     rcx, [rsp+78h+var_38]
0x180007a2b  test    rcx, rcx
0x180007a2e  jz      short loc_180007A3D
0x180007a30  mov     rdx, [rcx]
0x180007a33  mov     rax, [rdx+10h]
0x180007a37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a3c  nop
0x180007a3d  mov     eax, edi
0x180007a3f  jmp     short loc_1800079F3
0x180007a41  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180007a47  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180007a4d  lea     rcx, aCannotGetTheLe; "cannot get the length of list"
0x180007a54  mov     [rsp+78h+var_48], rcx
0x180007a59  mov     [rsp+78h+var_50], r12
0x180007a5e  lea     rcx, _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60
0x180007a65  mov     [rsp+78h+var_58], rcx
0x180007a6a  mov     r9, [rsp+78h+var_38]
0x180007a6f  mov     r8d, eax
0x180007a72  mov     edx, 6B5h
0x180007a77  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x180007a7e  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x180007a83  mov     ebx, eax
0x180007a85  lea     rcx, [rsp+78h+var_30]
0x180007a8a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007a8f  nop
0x180007a90  lea     rcx, [rsp+78h+var_38]
0x180007a95  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007a9a  mov     eax, ebx
0x180007a9c  jmp     loc_1800079F3
0x180007aa1  lea     rcx, aCannotGetTheNe; "cannot get the next node in a list"
0x180007aa8  mov     [rsp+78h+var_48], rcx
0x180007aad  mov     [rsp+78h+var_50], r12
0x180007ab2  lea     rcx, _GUID_2933bf82_7b36_11d2_b20e_00c04f983e60
0x180007ab9  mov     [rsp+78h+var_58], rcx
0x180007abe  mov     r9, [rsp+78h+var_38]
0x180007ac3  mov     r8d, eax
0x180007ac6  mov     edx, 6BEh
0x180007acb  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x180007ad2  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x180007ad7  mov     ebx, eax
0x180007ad9  lea     rcx, [rsp+78h+var_30]
0x180007ade  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007ae3  nop
0x180007ae4  lea     rcx, [rsp+78h+var_38]
0x180007ae9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007aee  mov     eax, ebx
0x180007af0  jmp     loc_1800079F3
0x180007af5  lea     rax, aCannotGetTextF; "cannot get text for an XML node"
0x180007afc  mov     [rsp+78h+var_48], rax
0x180007b01  mov     [rsp+78h+var_50], r12
0x180007b06  lea     rax, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x180007b0d  mov     [rsp+78h+var_58], rax
0x180007b12  mov     r9, [rsp+78h+var_30]
0x180007b17  mov     r8d, ebx
0x180007b1a  mov     edx, 6C6h
0x180007b1f  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x180007b26  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x180007b2b  mov     ebx, eax
0x180007b2d  lea     rcx, [rsp+78h+var_30]
0x180007b32  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007b37  nop
0x180007b38  lea     rcx, [rsp+78h+var_38]
0x180007b3d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007b42  mov     eax, ebx
0x180007b44  jmp     loc_1800079F3
0x180007b49  mov     ebx, 80004005h
0x180007b4e  test    r15b, r15b
0x180007b51  cmovnz  ebx, r12d
0x180007b55  jmp     loc_1800079C3
0x180007b5a  lea     rcx, [rsp+78h+var_30]
0x180007b5f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007b64  nop
0x180007b65  lea     rcx, [rsp+78h+var_38]
0x180007b6a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007b6f  mov     eax, [rsp+78h+arg_20]
0x180007b76  jmp     loc_1800079F3
```
