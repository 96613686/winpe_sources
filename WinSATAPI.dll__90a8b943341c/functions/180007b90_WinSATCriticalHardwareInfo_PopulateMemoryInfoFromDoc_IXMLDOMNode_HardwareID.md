# WinSATCriticalHardwareInfo::PopulateMemoryInfoFromDoc(IXMLDOMNode *,HardwareID)

- ea: `0x180007b90`
- end: `0x180007e93`
- name: `?PopulateMemoryInfoFromDoc@WinSATCriticalHardwareInfo@@AEAAJPEAUIXMLDOMNode@@W4HardwareID@@@Z`
- size: `771`
- prototype: `int __high(struct IXMLDOMNode *, enum HardwareID)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180006620`

## callees

- `0x180007b90`
- `0x180007ea0`
- `0x180008490`
- `0x1800084f0`
- `0x18000867c`
- `0x180008750`
- `0x18000e490`
- `0x180011e70`
- `0x180011ee0`
- `0x180012bf3`
- `0x180012c06`
- `0x180027248`
- `0x18002e864`
- `0x180033010`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x180007e45`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x180007e45`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007d6e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007d7d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007d9e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007dad`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007d6e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007d7d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007d9e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007dad`

## string_xrefs

- `0x180007ca8`: `SystemConfig/Memory/DIMM`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall WinSATCriticalHardwareInfo::PopulateMemoryInfoFromDoc(__int64 a1, __int64 a2, int a3)
{
  const wchar_t *XPathForHardwareID; // rdx
  int v6; // r8d
  int NodeValue; // ebx
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  void *v10; // rax
  __int64 v11; // rdx
  __int64 *v12; // rax
  __int64 *v13; // rbx
  __int64 v14; // rcx
  const wchar_t *i; // rax
  __int64 v16; // rax
  unsigned __int64 v17; // rcx
  void *v18; // rax
  __int64 v19; // rcx
  int v20; // edi
  _QWORD *v21; // rbx
  bool v22; // zf
  void *v23; // rcx
  _QWORD *v24; // rbx
  void *v25; // rcx
  OLECHAR *v27; // [rsp+20h] [rbp-50h]
  unsigned __int64 v28; // [rsp+30h] [rbp-40h] BYREF
  _QWORD *v29; // [rsp+38h] [rbp-38h] BYREF
  const char *v30[2]; // [rsp+40h] [rbp-30h] BYREF
  _QWORD v31[4]; // [rsp+50h] [rbp-20h] BYREF
  int pExceptionObject; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v33; // [rsp+B8h] [rbp+48h] BYREF

  pExceptionObject = a3;
  v30[1] = (const char *)-2LL;
  v28 = 0;
  XPathForHardwareID = GetXPathForHardwareID(8);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v33,
    XPathForHardwareID);
  NodeValue = mlib::XmlDOM::GetNodeValue(a2, (int)&v33, v6, (int)&v28, v27);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v33);
  if ( NodeValue < 0 )
    return (unsigned int)NodeValue;
  *(_QWORD *)(a1 + 40) = RoundTotalPhysMemSize(v28);
  v33 = 0;
  v8 = operator new(0x28u);
  v9 = v8;
  if ( !v8 )
    std::_Xbad_alloc();
  v30[0] = (const char *)v8;
  v8[2] = 1;
  v8[3] = 0;
  *v8 = 0;
  v8[1] = 0;
  v10 = operator new(2u);
  if ( !v10 )
    std::_Xbad_alloc();
  v9[3] = v10;
  if ( *v9 )
    memcpy_0(v10, 0, 2LL * *v9);
  v11 = v9[3];
  if ( v11 )
    *(_WORD *)(v11 + 2LL * *v9) = 0;
  v29 = v9;
  v12 = (__int64 *)operator new(0x28u);
  v13 = v12;
  if ( !v12 )
    std::_Xbad_alloc();
  v28 = (unsigned __int64)v12;
  *v12 = 0;
  v12[1] = 0;
  v12[2] = 1;
  v12[3] = 0;
  v14 = 0x10000;
  for ( i = L"SystemConfig/Memory/DIMM"; ; ++i )
  {
    if ( !v14 )
      throw (mlib::CStringTooBig *)&pExceptionObject;
    if ( !*i )
      break;
    --v14;
  }
  v16 = i - L"SystemConfig/Memory/DIMM";
  *v13 = v16;
  v13[1] = v16;
  v17 = v16 + 1;
  v18 = 0;
  if ( v17 )
  {
    if ( v17 > 0x7FFFFFFFFFFFFFFFLL || (v18 = operator new(2 * v17)) == 0 )
      std::_Xbad_alloc();
  }
  v13[3] = (__int64)v18;
  if ( !v18 )
  {
    v30[0] = "bad allocation";
    exception::exception((exception *)v31, v30, 1);
    v31[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)v31;
  }
  if ( *v13 )
    memcpy_0(v18, L"SystemConfig/Memory/DIMM", 2 * *v13);
  v19 = v13[3];
  if ( v19 )
    *(_WORD *)(v19 + 2 * *v13) = 0;
  v28 = (unsigned __int64)v13;
  v20 = mlib::XmlDOM::SelectXml(a2, (__int64)&v28, &v29, &v33, 0);
  v21 = (_QWORD *)v28;
  v22 = (*(_QWORD *)(v28 + 16))-- == 1;
  if ( v22 )
  {
    v23 = (void *)v21[3];
    if ( v23 )
      operator delete(v23);
    operator delete(v21);
  }
  v24 = v29;
  v22 = v29[2]-- == 1;
  if ( v22 )
  {
    v25 = (void *)v24[3];
    if ( v25 )
      operator delete(v25);
    operator delete(v24);
  }
  if ( v20 < 0 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
    return (unsigned int)v20;
  }
  NodeValue = PopulateWinsatMemoryInfoList(v33, a1 + 56);
  if ( NodeValue < 0 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
    return (unsigned int)NodeValue;
  }
  *(_BYTE *)(a1 + 48) = 1;
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  return 0;
}

```

## disassembly

```asm
0x180007b90  mov     [rsp-28h+pExceptionObject], r8d
0x180007b95  push    rbp
0x180007b96  push    rsi
0x180007b97  push    rdi
0x180007b98  push    r14
0x180007b9a  push    r15
0x180007b9c  mov     rbp, rsp
0x180007b9f  sub     rsp, 70h
0x180007ba3  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFEh
0x180007bab  mov     [rsp+70h+arg_0], rbx
0x180007bb3  mov     rdi, rdx
0x180007bb6  mov     rsi, rcx
0x180007bb9  xor     r14d, r14d
0x180007bbc  mov     [rbp+var_40], r14
0x180007bc0  lea     ecx, [r14+8]
0x180007bc4  call    ?GetXPathForHardwareID@@YAPEBGW4HardwareID@@@Z; GetXPathForHardwareID(HardwareID)
0x180007bc9  mov     rdx, rax
0x180007bcc  lea     rcx, [rbp+arg_18]
0x180007bd0  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x180007bd5  nop
0x180007bd6  lea     r9, [rbp+var_40]; int
0x180007bda  lea     rdx, [rbp+arg_18]; int
0x180007bde  mov     rcx, rdi; int
0x180007be1  call    ?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEA_KPEAV42@@Z; mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,unsigned __int64 &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x180007be6  mov     ebx, eax
0x180007be8  lea     rcx, [rbp+arg_18]
0x180007bec  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180007bf1  test    ebx, ebx
0x180007bf3  js      loc_180007E86
0x180007bf9  mov     rcx, [rbp+var_40]; unsigned __int64
0x180007bfd  call    ?RoundTotalPhysMemSize@@YA_K_K@Z; RoundTotalPhysMemSize(unsigned __int64)
0x180007c02  mov     [rsi+28h], rax
0x180007c06  mov     [rbp+arg_18], r14
0x180007c0a  lea     ecx, [r14+28h]; Size
0x180007c0e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007c13  mov     rbx, rax
0x180007c16  test    rax, rax
0x180007c19  jz      loc_180007E1A
0x180007c1f  mov     [rbp+var_30], rax
0x180007c23  mov     qword ptr [rax+10h], 1
0x180007c2b  mov     [rax+18h], r14
0x180007c2f  mov     [rax], r14
0x180007c32  mov     [rax+8], r14
0x180007c36  lea     ecx, [r14+2]; Size
0x180007c3a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007c3f  test    rax, rax
0x180007c42  jz      loc_180007E8D
0x180007c48  mov     [rbx+18h], rax
0x180007c4c  mov     r8, [rbx]
0x180007c4f  test    r8, r8
0x180007c52  jz      short loc_180007C61
0x180007c54  add     r8, r8; Size
0x180007c57  xor     edx, edx; Src
0x180007c59  mov     rcx, rax; void *
0x180007c5c  call    memcpy_0
0x180007c61  mov     rdx, [rbx+18h]
0x180007c65  test    rdx, rdx
0x180007c68  jz      short loc_180007C72
0x180007c6a  mov     rax, [rbx]
0x180007c6d  mov     [rdx+rax*2], r14w
0x180007c72  mov     [rbp+var_38], rbx
0x180007c76  mov     ecx, 28h ; '('; Size
0x180007c7b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007c80  mov     rbx, rax
0x180007c83  test    rax, rax
0x180007c86  jz      loc_180007E20
0x180007c8c  mov     [rbp+var_40], rax
0x180007c90  mov     [rax], r14
0x180007c93  mov     [rax+8], r14
0x180007c97  mov     qword ptr [rax+10h], 1
0x180007c9f  mov     [rax+18h], r14
0x180007ca3  mov     ecx, 10000h
0x180007ca8  lea     r15, aSystemconfigMe_0; "SystemConfig/Memory/DIMM"
0x180007caf  mov     rax, r15
0x180007cb2  test    rcx, rcx
0x180007cb5  jz      loc_180007E09
0x180007cbb  cmp     word ptr [rax], 0
0x180007cbf  jz      short loc_180007CCA
0x180007cc1  add     rax, 2
0x180007cc5  dec     rcx
0x180007cc8  jmp     short loc_180007CB2
0x180007cca  sub     rax, r15
0x180007ccd  sar     rax, 1
0x180007cd0  mov     [rbx], rax
0x180007cd3  mov     [rbx+8], rax
0x180007cd7  lea     rcx, [rax+1]
0x180007cdb  mov     rax, r14
0x180007cde  test    rcx, rcx
0x180007ce1  jz      short loc_180007D07
0x180007ce3  mov     rax, 7FFFFFFFFFFFFFFFh
0x180007ced  cmp     rcx, rax
0x180007cf0  ja      loc_180007E26
0x180007cf6  add     rcx, rcx; Size
0x180007cf9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007cfe  test    rax, rax
0x180007d01  jz      loc_180007E26
0x180007d07  mov     [rbx+18h], rax
0x180007d0b  test    rax, rax
0x180007d0e  jz      loc_180007E2C
0x180007d14  mov     r8, [rbx]
0x180007d17  test    r8, r8
0x180007d1a  jz      short loc_180007D2A
0x180007d1c  add     r8, r8; Size
0x180007d1f  mov     rdx, r15; Src
0x180007d22  mov     rcx, rax; void *
0x180007d25  call    memcpy_0
0x180007d2a  mov     rcx, [rbx+18h]
0x180007d2e  test    rcx, rcx
0x180007d31  jz      short loc_180007D3B
0x180007d33  mov     rax, [rbx]
0x180007d36  mov     [rcx+rax*2], r14w
0x180007d3b  mov     [rbp+var_40], rbx
0x180007d3f  mov     [rsp+70h+var_50], r14
0x180007d44  lea     r9, [rbp+arg_18]
0x180007d48  lea     r8, [rbp+var_38]
0x180007d4c  lea     rdx, [rbp+var_40]
0x180007d50  mov     rcx, rdi
0x180007d53  call    ?SelectXml@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@1PEAPEAUIXMLDOMNodeList@@PEAV42@@Z; mlib::XmlDOM::SelectXml(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,IXMLDOMNodeList * *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x180007d58  mov     edi, eax
0x180007d5a  mov     rbx, [rbp+var_40]
0x180007d5e  sub     qword ptr [rbx+10h], 1
0x180007d63  jnz     short loc_180007D8A
0x180007d65  mov     rcx, [rbx+18h]
0x180007d69  test    rcx, rcx
0x180007d6c  jz      short loc_180007D7A
0x180007d6e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007d75  nop     dword ptr [rax+rax+00h]
0x180007d7a  mov     rcx, rbx
0x180007d7d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007d84  nop     dword ptr [rax+rax+00h]
0x180007d89  nop
0x180007d8a  mov     rbx, [rbp+var_38]
0x180007d8e  sub     qword ptr [rbx+10h], 1
0x180007d93  jnz     short loc_180007DB9
0x180007d95  mov     rcx, [rbx+18h]
0x180007d99  test    rcx, rcx
0x180007d9c  jz      short loc_180007DAA
0x180007d9e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007da5  nop     dword ptr [rax+rax+00h]
0x180007daa  mov     rcx, rbx
0x180007dad  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007db4  nop     dword ptr [rax+rax+00h]
0x180007db9  test    edi, edi
0x180007dbb  js      loc_180007E6D
0x180007dc1  lea     rdx, [rsi+38h]
0x180007dc5  mov     rcx, [rbp+arg_18]
0x180007dc9  call    PopulateWinsatMemoryInfoList
0x180007dce  mov     ebx, eax
0x180007dd0  test    eax, eax
0x180007dd2  js      loc_180007E7D
0x180007dd8  mov     byte ptr [rsi+30h], 1
0x180007ddc  mov     rcx, [rbp+arg_18]
0x180007de0  test    rcx, rcx
0x180007de3  jz      short loc_180007DF2
0x180007de5  mov     rax, [rcx]
0x180007de8  mov     rax, [rax+10h]
0x180007dec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007df1  nop
0x180007df2  xor     eax, eax
0x180007df4  mov     rbx, [rsp+70h+arg_0]
0x180007dfc  add     rsp, 70h
0x180007e00  pop     r15
0x180007e02  pop     r14
0x180007e04  pop     rdi
0x180007e05  pop     rsi
0x180007e06  pop     rbp
0x180007e07  retn
0x180007e09  lea     rdx, _TI1?AVCStringTooBig@mlib@@; pThrowInfo
0x180007e10  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180007e14  call    _CxxThrowException_0
0x180007e1a  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180007e20  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180007e26  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180007e2c  lea     rax, aBadAllocation; "bad allocation"
0x180007e33  mov     [rbp+var_30], rax
0x180007e37  mov     r8d, 1
0x180007e3d  lea     rdx, [rbp+var_30]
0x180007e41  lea     rcx, [rbp+var_20]
0x180007e45  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x180007e4c  nop     dword ptr [rax+rax+00h]
0x180007e51  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180007e58  mov     [rbp+var_20], rax
0x180007e5c  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180007e63  lea     rcx, [rbp+var_20]; pExceptionObject
0x180007e67  call    _CxxThrowException_0
0x180007e6d  lea     rcx, [rbp+arg_18]
0x180007e71  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007e76  mov     eax, edi
0x180007e78  jmp     loc_180007DF4
0x180007e7d  lea     rcx, [rbp+arg_18]
0x180007e81  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007e86  mov     eax, ebx
0x180007e88  jmp     loc_180007DF4
0x180007e8d  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
