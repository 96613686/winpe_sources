# WinSATCriticalHardwareInfo::PopulateFromDoc(IXMLDOMDocument2 *,HardwareID)

- ea: `0x180006620`
- end: `0x180006a94`
- name: `?PopulateFromDoc@WinSATCriticalHardwareInfo@@QEAAJPEAUIXMLDOMDocument2@@W4HardwareID@@@Z`
- size: `1140`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180005080`

## callees

- `0x180006494`
- `0x180006620`
- `0x180007b90`
- `0x180008490`
- `0x18000e490`
- `0x18000e938`
- `0x180015f4c`
- `0x18002cbd0`
- `0x18002ccd8`
- `0x18002cd94`
- `0x18002ce4c`
- `0x18002ceec`
- `0x180033010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006700`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000670f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006738`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006747`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006700`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000670f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006738`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006747`
- `OLEAUT32!__imp_SysAllocString` at `0x180006789`
- `OLEAUT32!__imp_SysAllocString` at `0x1800067ba`
- `OLEAUT32!__imp_SysAllocString` at `0x1800067eb`
- `OLEAUT32!__imp_SysAllocString` at `0x180006789`
- `OLEAUT32!__imp_SysAllocString` at `0x1800067ba`
- `OLEAUT32!__imp_SysAllocString` at `0x1800067eb`
- `OLEAUT32!__imp_SysFreeString` at `0x180006776`
- `OLEAUT32!__imp_SysFreeString` at `0x1800067a7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800067d8`
- `OLEAUT32!__imp_SysFreeString` at `0x180006930`
- `OLEAUT32!__imp_SysFreeString` at `0x180006940`
- `OLEAUT32!__imp_SysFreeString` at `0x180006950`
- `OLEAUT32!__imp_SysFreeString` at `0x1800069b0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800069c0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800069d0`
- `OLEAUT32!__imp_SysFreeString` at `0x180006776`
- `OLEAUT32!__imp_SysFreeString` at `0x1800067a7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800067d8`
- `OLEAUT32!__imp_SysFreeString` at `0x180006930`
- `OLEAUT32!__imp_SysFreeString` at `0x180006940`
- `OLEAUT32!__imp_SysFreeString` at `0x180006950`
- `OLEAUT32!__imp_SysFreeString` at `0x1800069b0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800069c0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800069d0`

## string_xrefs

- `0x18000687d`: `base\winsat\mlib\mxmldom.cpp`
- `0x180006914`: `base\winsat\mlib\mxmldom.cpp`
- `0x1800068a8`: `cannot get the root node for an XML documentt`
- `0x1800068eb`: `cannot select a XML node for from an XPATH expression`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall WinSATCriticalHardwareInfo::PopulateFromDoc(__int64 a1, __int64 *a2)
{
  __int64 v4; // rdi
  __int64 i; // rbx
  __int64 v6; // rsi
  __int64 j; // rbx
  __int64 v8; // rax
  bool v9; // zf
  _QWORD *v10; // rdi
  void *v11; // rcx
  __int64 v12; // rax
  _QWORD *v13; // rdi
  void *v14; // rcx
  OLECHAR *v15; // rbx
  OLECHAR *v16; // rdi
  BSTR v17; // rax
  OLECHAR *v18; // rsi
  __int64 v19; // rax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // r14d
  int v26; // ebx
  BSTR v27; // [rsp+50h] [rbp-21h]
  __int128 v28; // [rsp+68h] [rbp-9h]
  __int128 v29; // [rsp+88h] [rbp+17h] BYREF
  __int64 v30; // [rsp+98h] [rbp+27h]
  _QWORD *v31; // [rsp+D8h] [rbp+67h] BYREF
  __int64 v32; // [rsp+F0h] [rbp+7Fh] BYREF

  v31 = 0;
  *(_BYTE *)a1 = 0;
  v4 = *(_QWORD *)(a1 + 16);
  for ( i = *(_QWORD *)(a1 + 8); i != v4; i += 24 )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(i + 8);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(i);
  }
  *(_QWORD *)(a1 + 16) = *(_QWORD *)(a1 + 8);
  *(_QWORD *)(a1 + 32) = -1;
  *(_QWORD *)(a1 + 40) = -1;
  *(_WORD *)(a1 + 96) = 0;
  *(_WORD *)(a1 + 224) = 0;
  *(_QWORD *)(a1 + 232) = -1;
  *(_DWORD *)(a1 + 84) = -1;
  *(_QWORD *)(a1 + 88) = -1;
  *(_BYTE *)(a1 + 48) = 0;
  *(_WORD *)(a1 + 240) = 0;
  *(_WORD *)(a1 + 368) = 0;
  v6 = *(_QWORD *)(a1 + 64);
  for ( j = *(_QWORD *)(a1 + 56); j != v6; j += 40 )
  {
    v8 = *(_QWORD *)(j + 16);
    v9 = (*(_QWORD *)(v8 + 16))-- == 1;
    if ( v9 )
    {
      v10 = *(_QWORD **)(j + 16);
      if ( v10 )
      {
        v11 = (void *)v10[3];
        if ( v11 )
          operator delete(v11);
        operator delete(v10);
      }
    }
    v12 = *(_QWORD *)(j + 8);
    v9 = (*(_QWORD *)(v12 + 16))-- == 1;
    if ( v9 )
    {
      v13 = *(_QWORD **)(j + 8);
      if ( v13 )
      {
        v14 = (void *)v13[3];
        if ( v14 )
          operator delete(v14);
        operator delete(v13);
      }
    }
  }
  *(_QWORD *)(a1 + 64) = *(_QWORD *)(a1 + 56);
  v32 = 0;
  v31 = 0;
  SysFreeString(0);
  v15 = SysAllocString(L"/WinSAT");
  if ( !v15
    || (SysFreeString(0), (v16 = SysAllocString(L"SelectionNamespaces")) == 0)
    || (SysFreeString(0), v17 = SysAllocString(&String2), v18 = v17, (v27 = v17) == 0) )
  {
    ATL::AtlThrowImpl(-2147024882);
  }
  *(_QWORD *)&v28 = 8;
  *((_QWORD *)&v28 + 1) = v17;
  v19 = *a2;
  v29 = v28;
  v30 = 0;
  v20 = (*(__int64 (__fastcall **)(__int64 *, OLECHAR *, __int128 *))(v19 + 640))(a2, v16, &v29);
  if ( v20 >= 0 )
  {
    v22 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(*a2 + 360))(a2, &v32);
    if ( v22 >= 0 )
    {
      v23 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD **))(*(_QWORD *)v32 + 296LL))(v32, v15, &v31);
      if ( v23 >= 0 )
      {
        if ( v32 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
        SysFreeString(v18);
        SysFreeString(v16);
        SysFreeString(v15);
        goto LABEL_31;
      }
      v31 = 0;
      v21 = mlib::XmlDOM::ReportCOMError_w(
              (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
              1130,
              v23,
              v32,
              (__int64)&GUID_2933bf86_7b36_11d2_b20e_00c04f983e60,
              0,
              (__int64)L"cannot select a XML node for from an XPATH expression");
    }
    else
    {
      v21 = mlib::XmlDOM::ReportCOMError_w(
              (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
              1123,
              v22,
              (_DWORD)a2,
              (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
              0,
              (__int64)L"cannot get the root node for an XML documentt");
    }
  }
  else
  {
    v21 = mlib::XmlDOM::ReportCOMError_w(
            (unsigned int)"base\\winsat\\mlib\\mxmldom.cpp",
            1116,
            v20,
            (_DWORD)a2,
            (__int64)&GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
            0,
            (__int64)L"cannot set the %s document propert",
            v16,
            v16,
            v27,
            -2,
            v15);
  }
  v24 = v21;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
  SysFreeString(v18);
  SysFreeString(v16);
  SysFreeString(v15);
  if ( v24 < 0 )
  {
    if ( v31 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v31 + 16LL))(v31, *v31);
    return (unsigned int)v24;
  }
LABEL_31:
  v26 = WinSATCriticalHardwareInfo::PopulateCPUInfoFromDoc(a1, v31);
  if ( v26 < 0
    || (v26 = WinSATCriticalHardwareInfo::PopulateSystemInfoFromDoc(a1, v31), v26 < 0)
    || (v26 = WinSATCriticalHardwareInfo::PopulateMemoryInfoFromDoc(a1, v31), v26 < 0)
    || (v26 = WinSATCriticalHardwareInfo::PopulateDiskInfoFromDoc(a1, v31), v26 < 0)
    || (v26 = WinSATCriticalHardwareInfo::PopulateVideoInfoFromDoc(a1, v31), v26 < 0)
    || (v26 = WinSATCriticalHardwareInfo::PopulateVersionInfoFromDoc(a1, v31), v26 < 0) )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
    return (unsigned int)v26;
  }
  else if ( (unsigned __int8)WinSATCriticalHardwareInfo::IsPopulated(a1, 4095) )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
    return 0;
  }
  else
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180006620  mov     rax, rsp
0x180006623  push    rbp
0x180006624  push    rdi
0x180006625  push    r12
0x180006627  push    r14
0x180006629  push    r15
0x18000662b  lea     rbp, [rax-5Fh]
0x18000662f  sub     rsp, 0A0h
0x180006636  mov     [rbp+57h+var_70], 0FFFFFFFFFFFFFFFEh
0x18000663e  mov     [rax+10h], rbx
0x180006642  mov     [rax+18h], rsi
0x180006646  mov     r14, rdx
0x180006649  mov     r15, rcx
0x18000664c  xor     r12d, r12d
0x18000664f  mov     [rbp+57h+arg_0], r12
0x180006653  mov     [rcx], r12b
0x180006656  mov     rdi, [rcx+10h]
0x18000665a  mov     rbx, [rcx+8]
0x18000665e  cmp     rbx, rdi
0x180006661  jz      short loc_18000667D
0x180006663  lea     rcx, [rbx+8]
0x180006667  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18000666c  mov     rcx, rbx
0x18000666f  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180006674  add     rbx, 18h
0x180006678  cmp     rbx, rdi
0x18000667b  jnz     short loc_180006663
0x18000667d  mov     rax, [r15+8]
0x180006681  mov     [r15+10h], rax
0x180006685  mov     qword ptr [r15+20h], 0FFFFFFFFFFFFFFFFh
0x18000668d  mov     qword ptr [r15+28h], 0FFFFFFFFFFFFFFFFh
0x180006695  mov     [r15+60h], r12w
0x18000669a  mov     word ptr [r15+0E0h], 0
0x1800066a4  mov     qword ptr [r15+0E8h], 0FFFFFFFFFFFFFFFFh
0x1800066af  mov     dword ptr [r15+54h], 0FFFFFFFFh
0x1800066b7  mov     qword ptr [r15+58h], 0FFFFFFFFFFFFFFFFh
0x1800066bf  mov     byte ptr [r15+30h], 0
0x1800066c4  mov     [r15+0F0h], r12w
0x1800066cc  mov     word ptr [r15+170h], 0
0x1800066d6  mov     rsi, [r15+40h]
0x1800066da  mov     rbx, [r15+38h]
0x1800066de  cmp     rbx, rsi
0x1800066e1  jz      short loc_18000675C
0x1800066e3  mov     rax, [rbx+10h]
0x1800066e7  sub     qword ptr [rax+10h], 1
0x1800066ec  jnz     short loc_18000671B
0x1800066ee  mov     rdi, [rbx+10h]
0x1800066f2  test    rdi, rdi
0x1800066f5  jz      short loc_18000671B
0x1800066f7  mov     rcx, [rdi+18h]
0x1800066fb  test    rcx, rcx
0x1800066fe  jz      short loc_18000670C
0x180006700  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006707  nop     dword ptr [rax+rax+00h]
0x18000670c  mov     rcx, rdi
0x18000670f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006716  nop     dword ptr [rax+rax+00h]
0x18000671b  mov     rax, [rbx+8]
0x18000671f  sub     qword ptr [rax+10h], 1
0x180006724  jnz     short loc_180006753
0x180006726  mov     rdi, [rbx+8]
0x18000672a  test    rdi, rdi
0x18000672d  jz      short loc_180006753
0x18000672f  mov     rcx, [rdi+18h]
0x180006733  test    rcx, rcx
0x180006736  jz      short loc_180006744
0x180006738  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000673f  nop     dword ptr [rax+rax+00h]
0x180006744  mov     rcx, rdi
0x180006747  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000674e  nop     dword ptr [rax+rax+00h]
0x180006753  add     rbx, 28h ; '('
0x180006757  cmp     rbx, rsi
0x18000675a  jnz     short loc_1800066E3
0x18000675c  mov     rax, [r15+38h]
0x180006760  mov     [r15+40h], rax
0x180006764  mov     [rbp+57h+var_80], r12
0x180006768  mov     [rbp+57h+var_78], r12
0x18000676c  mov     [rbp+57h+arg_18], r12
0x180006770  mov     [rbp+57h+arg_0], r12
0x180006774  xor     ecx, ecx; bstrString
0x180006776  call    cs:__imp_SysFreeString
0x18000677d  nop     dword ptr [rax+rax+00h]
0x180006782  lea     rcx, psz; "/WinSAT"
0x180006789  call    cs:__imp_SysAllocString
0x180006790  nop     dword ptr [rax+rax+00h]
0x180006795  mov     rbx, rax
0x180006798  mov     [rbp+57h+var_68], rax
0x18000679c  test    rax, rax
0x18000679f  jz      loc_180006A89
0x1800067a5  xor     ecx, ecx; bstrString
0x1800067a7  call    cs:__imp_SysFreeString
0x1800067ae  nop     dword ptr [rax+rax+00h]
0x1800067b3  lea     rcx, aSelectionnames; "SelectionNamespaces"
0x1800067ba  call    cs:__imp_SysAllocString
0x1800067c1  nop     dword ptr [rax+rax+00h]
0x1800067c6  mov     rdi, rax
0x1800067c9  mov     [rbp+57h+var_80], rax
0x1800067cd  test    rax, rax
0x1800067d0  jz      loc_180006A89
0x1800067d6  xor     ecx, ecx; bstrString
0x1800067d8  call    cs:__imp_SysFreeString
0x1800067df  nop     dword ptr [rax+rax+00h]
0x1800067e4  lea     rcx, String2; psz
0x1800067eb  call    cs:__imp_SysAllocString
0x1800067f2  nop     dword ptr [rax+rax+00h]
0x1800067f7  mov     rsi, rax
0x1800067fa  mov     [rbp+57h+var_78], rax
0x1800067fe  test    rax, rax
0x180006801  jz      loc_180006A89
0x180006807  xorps   xmm0, xmm0
0x18000680a  xor     eax, eax
0x18000680c  movups  [rbp+57h+var_60], xmm0
0x180006810  mov     [rbp+57h+var_50], rax
0x180006814  mov     eax, 8
0x180006819  mov     word ptr [rbp+57h+var_60], ax
0x18000681d  mov     qword ptr [rbp+57h+var_60+8], rsi
0x180006821  mov     rax, [r14]
0x180006824  movups  xmm0, [rbp+57h+var_60]
0x180006828  movaps  [rbp+57h+var_40], xmm0
0x18000682c  movsd   xmm1, [rbp+57h+var_50]
0x180006831  movsd   [rbp+57h+var_30], xmm1
0x180006836  lea     r8, [rbp+57h+var_40]
0x18000683a  mov     rdx, rdi
0x18000683d  mov     rcx, r14
0x180006840  mov     rax, [rax+280h]
0x180006847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000684c  test    eax, eax
0x18000684e  jns     short loc_18000688E
0x180006850  mov     [rsp+0C0h+var_88], rdi
0x180006855  lea     rcx, aCannotSetTheSD; "cannot set the %s document propert"
0x18000685c  mov     [rsp+0C0h+var_90], rcx
0x180006861  mov     [rsp+0C0h+var_98], r12
0x180006866  lea     rcx, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60
0x18000686d  mov     [rsp+0C0h+var_A0], rcx
0x180006872  mov     r9, r14
0x180006875  mov     r8d, eax
0x180006878  mov     edx, 45Ch
0x18000687d  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x180006884  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x180006889  jmp     loc_180006920
0x18000688e  mov     rax, [r14]
0x180006891  lea     rdx, [rbp+57h+arg_18]
0x180006895  mov     rcx, r14
0x180006898  mov     rax, [rax+168h]
0x18000689f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068a4  test    eax, eax
0x1800068a6  jns     short loc_1800068C5
0x1800068a8  lea     rcx, aCannotGetTheRo; "cannot get the root node for an XML doc"...
0x1800068af  mov     [rsp+0C0h+var_90], rcx
0x1800068b4  lea     rcx, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60
0x1800068bb  mov     r9, r14
0x1800068be  mov     edx, 463h
0x1800068c3  jmp     short loc_180006907
0x1800068c5  mov     rcx, [rbp+57h+arg_18]
0x1800068c9  mov     rax, [rcx]
0x1800068cc  lea     r8, [rbp+57h+arg_0]
0x1800068d0  mov     rdx, rbx
0x1800068d3  mov     rax, [rax+128h]
0x1800068da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068df  test    eax, eax
0x1800068e1  jns     loc_180006997
0x1800068e7  mov     [rbp+57h+arg_0], r12
0x1800068eb  lea     rcx, aCannotSelectAX; "cannot select a XML node for from an XP"...
0x1800068f2  mov     [rsp+0C0h+var_90], rcx
0x1800068f7  lea     rcx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x1800068fe  mov     r9, [rbp+57h+arg_18]
0x180006902  mov     edx, 46Ah
0x180006907  mov     [rsp+0C0h+var_98], r12
0x18000690c  mov     [rsp+0C0h+var_A0], rcx
0x180006911  mov     r8d, eax
0x180006914  lea     rcx, aBaseWinsatMlib_0; "base\\winsat\\mlib\\mxmldom.cpp"
0x18000691b  call    ?ReportCOMError_w@XmlDOM@mlib@@CAJPEBDKJPEAUIUnknown@@AEBU_GUID@@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEBGZZ; mlib::XmlDOM::ReportCOMError_w(char const *,ulong,long,IUnknown *,_GUID const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,ushort const *,...)
0x180006920  mov     r14d, eax
0x180006923  lea     rcx, [rbp+57h+arg_18]
0x180006927  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000692c  nop
0x18000692d  mov     rcx, rsi; bstrString
0x180006930  call    cs:__imp_SysFreeString
0x180006937  nop     dword ptr [rax+rax+00h]
0x18000693c  nop
0x18000693d  mov     rcx, rdi; bstrString
0x180006940  call    cs:__imp_SysFreeString
0x180006947  nop     dword ptr [rax+rax+00h]
0x18000694c  nop
0x18000694d  mov     rcx, rbx; bstrString
0x180006950  call    cs:__imp_SysFreeString
0x180006957  nop     dword ptr [rax+rax+00h]
0x18000695c  test    r14d, r14d
0x18000695f  jns     short loc_1800069DC
0x180006961  mov     rcx, [rbp+57h+arg_0]
0x180006965  test    rcx, rcx
0x180006968  jz      short loc_180006977
0x18000696a  mov     rdx, [rcx]
0x18000696d  mov     rax, [rdx+10h]
0x180006971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006976  nop
0x180006977  mov     eax, r14d
0x18000697a  lea     r11, [rsp+0C0h+var_20]
0x180006982  mov     rbx, [r11+38h]
0x180006986  mov     rsi, [r11+40h]
0x18000698a  mov     rsp, r11
0x18000698d  pop     r15
0x18000698f  pop     r14
0x180006991  pop     r12
0x180006993  pop     rdi
0x180006994  pop     rbp
0x180006995  retn
0x180006997  mov     rcx, [rbp+57h+arg_18]
0x18000699b  test    rcx, rcx
0x18000699e  jz      short loc_1800069AD
0x1800069a0  mov     rax, [rcx]
0x1800069a3  mov     rax, [rax+10h]
0x1800069a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069ac  nop
0x1800069ad  mov     rcx, rsi; bstrString
0x1800069b0  call    cs:__imp_SysFreeString
0x1800069b7  nop     dword ptr [rax+rax+00h]
0x1800069bc  nop
0x1800069bd  mov     rcx, rdi; bstrString
0x1800069c0  call    cs:__imp_SysFreeString
0x1800069c7  nop     dword ptr [rax+rax+00h]
0x1800069cc  nop
0x1800069cd  mov     rcx, rbx; bstrString
0x1800069d0  call    cs:__imp_SysFreeString
0x1800069d7  nop     dword ptr [rax+rax+00h]
0x1800069dc  mov     rdx, [rbp+57h+arg_0]
0x1800069e0  mov     rcx, r15
0x1800069e3  call    ?PopulateCPUInfoFromDoc@WinSATCriticalHardwareInfo@@AEAAJPEAUIXMLDOMNode@@W4HardwareID@@@Z; WinSATCriticalHardwareInfo::PopulateCPUInfoFromDoc(IXMLDOMNode *,HardwareID)
0x1800069e8  mov     ebx, eax
0x1800069ea  test    eax, eax
0x1800069ec  jns     short loc_1800069FE
0x1800069ee  lea     rcx, [rbp+57h+arg_0]
0x1800069f2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800069f7  mov     eax, ebx
0x1800069f9  jmp     loc_18000697A
0x1800069fe  mov     rdx, [rbp+57h+arg_0]
0x180006a02  mov     rcx, r15
0x180006a05  call    ?PopulateSystemInfoFromDoc@WinSATCriticalHardwareInfo@@AEAAJPEAUIXMLDOMNode@@W4HardwareID@@@Z; WinSATCriticalHardwareInfo::PopulateSystemInfoFromDoc(IXMLDOMNode *,HardwareID)
0x180006a0a  mov     ebx, eax
0x180006a0c  test    eax, eax
0x180006a0e  js      short loc_1800069EE
0x180006a10  mov     rdx, [rbp+57h+arg_0]
0x180006a14  mov     rcx, r15
0x180006a17  call    ?PopulateMemoryInfoFromDoc@WinSATCriticalHardwareInfo@@AEAAJPEAUIXMLDOMNode@@W4HardwareID@@@Z; WinSATCriticalHardwareInfo::PopulateMemoryInfoFromDoc(IXMLDOMNode *,HardwareID)
0x180006a1c  mov     ebx, eax
0x180006a1e  test    eax, eax
0x180006a20  js      short loc_1800069EE
0x180006a22  mov     rdx, [rbp+57h+arg_0]
0x180006a26  mov     rcx, r15
0x180006a29  call    ?PopulateDiskInfoFromDoc@WinSATCriticalHardwareInfo@@AEAAJPEAUIXMLDOMNode@@W4HardwareID@@@Z; WinSATCriticalHardwareInfo::PopulateDiskInfoFromDoc(IXMLDOMNode *,HardwareID)
0x180006a2e  mov     ebx, eax
0x180006a30  test    eax, eax
0x180006a32  js      short loc_1800069EE
0x180006a34  mov     rdx, [rbp+57h+arg_0]
0x180006a38  mov     rcx, r15
0x180006a3b  call    ?PopulateVideoInfoFromDoc@WinSATCriticalHardwareInfo@@AEAAJPEAUIXMLDOMNode@@W4HardwareID@@@Z; WinSATCriticalHardwareInfo::PopulateVideoInfoFromDoc(IXMLDOMNode *,HardwareID)
0x180006a40  mov     ebx, eax
0x180006a42  test    eax, eax
0x180006a44  js      short loc_1800069EE
0x180006a46  mov     rdx, [rbp+57h+arg_0]
0x180006a4a  mov     rcx, r15
0x180006a4d  call    ?PopulateVersionInfoFromDoc@WinSATCriticalHardwareInfo@@AEAAJPEAUIXMLDOMNode@@W4HardwareID@@@Z; WinSATCriticalHardwareInfo::PopulateVersionInfoFromDoc(IXMLDOMNode *,HardwareID)
0x180006a52  mov     ebx, eax
0x180006a54  test    eax, eax
0x180006a56  js      short loc_1800069EE
0x180006a58  mov     edx, 0FFFh
0x180006a5d  mov     rcx, r15
0x180006a60  call    ?IsPopulated@WinSATCriticalHardwareInfo@@QEBA_NW4HardwareID@@@Z; WinSATCriticalHardwareInfo::IsPopulated(HardwareID)
0x180006a65  nop
0x180006a66  lea     rcx, [rbp+57h+arg_0]
0x180006a6a  test    al, al
0x180006a6c  jnz     short loc_180006A7D
0x180006a6e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180006a73  mov     eax, 80004005h
0x180006a78  jmp     loc_18000697A
0x180006a7d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180006a82  xor     eax, eax
0x180006a84  jmp     loc_18000697A
0x180006a89  mov     ecx, 8007000Eh; int
0x180006a8e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
