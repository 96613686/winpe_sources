# PushButtonReset::XmlDocument::CreateElement(PushButtonReset::XmlNode * *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x180059430`
- end: `0x180059845`
- name: `?CreateElement@XmlDocument@PushButtonReset@@QEAAJPEAPEAVXmlNode@2@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1@Z`
- size: `1045`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180050e24`
- `0x180050fe8`

## callees

- `0x180005c00`
- `0x180005cc0`
- `0x180023620`
- `0x180037344`
- `0x1800527e0`
- `0x1800588dc`
- `0x180059430`
- `0x180059e54`
- `0x18005a498`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180059458`
- `OLEAUT32!__imp_SysAllocString` at `0x1800594d9`
- `OLEAUT32!__imp_SysAllocString` at `0x180059458`
- `OLEAUT32!__imp_SysAllocString` at `0x1800594d9`

## string_xrefs

- `0x180059491`: `base\reset\util\src\xml.cpp`
- `0x180059522`: `base\reset\util\src\xml.cpp`
- `0x180059631`: `base\reset\util\src\xml.cpp`
- `0x1800596c6`: `base\reset\util\src\xml.cpp`
- `0x180059776`: `base\reset\util\src\xml.cpp`
- `0x180059498`: `PushButtonReset::XmlDocument::CreateElement`
- `0x180059529`: `PushButtonReset::XmlDocument::CreateElement`
- `0x180059638`: `PushButtonReset::XmlDocument::CreateElement`
- `0x1800596cd`: `PushButtonReset::XmlDocument::CreateElement`
- `0x18005977d`: `PushButtonReset::XmlDocument::CreateElement`
- `0x18005961d`: `Failed to create element [%s]`
- `0x18005950e`: `Failed to allocate bstrURI`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall PushButtonReset::XmlDocument::CreateElement(
        struct PushButtonReset::XmlDocument *a1,
        __int64 *a2,
        const OLECHAR **a3,
        const OLECHAR **a4)
{
  BSTR v8; // rax
  __int64 v10; // r14
  __int64 (__fastcall *v11)(__int64, __int128 *, _QWORD, __int64, __int64); // rsi
  __int64 v12; // rdi
  __int64 v13; // rbx
  _QWORD *v14; // rax
  int v15; // ebx
  PushButtonReset::XmlNode *v16; // rax
  struct IXMLDOMNode *v17; // rdx
  __int64 v18; // rax
  void **v19; // [rsp+40h] [rbp-49h] BYREF
  __int64 v20; // [rsp+48h] [rbp-41h] BYREF
  void **v21; // [rsp+50h] [rbp-39h] BYREF
  BSTR v22; // [rsp+58h] [rbp-31h] BYREF
  void **v23; // [rsp+60h] [rbp-29h] BYREF
  struct IXMLDOMNode *v24; // [rsp+68h] [rbp-21h]
  void **v25; // [rsp+70h] [rbp-19h] BYREF
  __int64 v26; // [rsp+78h] [rbp-11h]
  __int128 v27; // [rsp+80h] [rbp-9h] BYREF
  struct PushButtonReset::XmlDocument *v28; // [rsp+90h] [rbp+7h]
  struct PushButtonReset::XmlDocument *v29; // [rsp+100h] [rbp+77h] BYREF

  v8 = SysAllocString(*a3);
  v21 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
  v22 = v8;
  if ( !*(_QWORD *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v21) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942414LL,
      "PushButtonReset::XmlDocument::CreateElement",
      "base\\reset\\util\\src\\xml.cpp",
      455,
      L"Failed to allocate bstrName");
    v21 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
    RAII::CleanupInfo<unsigned short *>::Release(&v22);
    return 2147942414LL;
  }
  v19 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
  v20 = 0;
  if ( *((int *)*a4 - 4) > 0 )
  {
    v29 = (struct PushButtonReset::XmlDocument *)SysAllocString(*a4);
    ((void (__fastcall *)(void ***, struct PushButtonReset::XmlDocument **))v19[6])(&v19, &v29);
    if ( !*(_QWORD *)((__int64 (__fastcall *)(void ***))v19[4])(&v19) )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        2147942414LL,
        "PushButtonReset::XmlDocument::CreateElement",
        "base\\reset\\util\\src\\xml.cpp",
        461,
        L"Failed to allocate bstrURI");
      v19 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
      RAII::CleanupInfo<unsigned short *>::Release(&v20);
      v21 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
      RAII::CleanupInfo<unsigned short *>::Release(&v22);
      return 2147942414LL;
    }
  }
  v29 = 0;
  v27 = 0;
  LOWORD(v27) = 22;
  DWORD2(v27) = 1;
  v24 = 0;
  v23 = &RAII::CAutoRelease<IXMLDOMNode *>::`vftable';
  v10 = (*(__int64 (__fastcall **)(struct PushButtonReset::XmlDocument *))(*(_QWORD *)a1 + 24LL))(a1);
  v11 = *(__int64 (__fastcall **)(__int64, __int128 *, _QWORD, __int64, __int64))(*(_QWORD *)v10 + 448LL);
  v12 = ((__int64 (__fastcall *)(void ***))v23[1])(&v23);
  v13 = *(_QWORD *)((__int64 (__fastcall *)(void ***))v19[4])(&v19);
  v14 = (_QWORD *)((__int64 (__fastcall *)(void ***))v21[4])(&v21);
  v28 = v29;
  v15 = v11(v10, &v27, *v14, v13, v12);
  if ( v15 >= 0 )
  {
    v29 = a1;
    v26 = PbrNew<PushButtonReset::XmlNode,PushButtonReset::XmlDocument * &>(&v29);
    v25 = &RAII::CAutoPbrDelete<PushButtonReset::XmlNode *>::`vftable';
    if ( (unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!((__int64 *)&v25) )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        2147942414LL,
        "PushButtonReset::XmlDocument::CreateElement",
        "base\\reset\\util\\src\\xml.cpp",
        473,
        L"Failed to allocate xnode");
      v25 = &RAII::CAutoPbrDelete<PushButtonReset::XmlNode *>::`vftable';
      RAII::CAutoPbrDelete<PushButtonReset::XmlNode *>::Release(&v25);
      v23 = &RAII::CAutoRelease<IXMLDOMNode *>::`vftable';
      RAII::CAutoRelease<IXMLDOMParseError *>::Release(&v23);
      v19 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
      RAII::CleanupInfo<unsigned short *>::Release(&v20);
      v21 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
      RAII::CleanupInfo<unsigned short *>::Release(&v22);
      return 2147942414LL;
    }
    v16 = (PushButtonReset::XmlNode *)((__int64 (__fastcall *)(void ***))v25[3])(&v25);
    v17 = v24;
    v24 = 0;
    v15 = PushButtonReset::XmlNode::Initialize(v16, v17);
    if ( v15 >= 0 )
    {
      v18 = v26;
      v26 = 0;
      *a2 = v18;
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v15,
        "PushButtonReset::XmlDocument::CreateElement",
        "base\\reset\\util\\src\\xml.cpp",
        476,
        L"Failed to initialize node for DOM element %s",
        *a3);
    }
    v25 = &RAII::CAutoPbrDelete<PushButtonReset::XmlNode *>::`vftable';
    RAII::CAutoPbrDelete<PushButtonReset::XmlNode *>::Release(&v25);
    v23 = &RAII::CAutoRelease<IXMLDOMNode *>::`vftable';
    RAII::CAutoRelease<IXMLDOMParseError *>::Release(&v23);
    v19 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
    RAII::CleanupInfo<unsigned short *>::Release(&v20);
    v21 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
    RAII::CleanupInfo<unsigned short *>::Release(&v22);
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v15,
      "PushButtonReset::XmlDocument::CreateElement",
      "base\\reset\\util\\src\\xml.cpp",
      470,
      L"Failed to create element [%s]",
      *a3);
    v23 = &RAII::CAutoRelease<IXMLDOMNode *>::`vftable';
    RAII::CAutoRelease<IXMLDOMParseError *>::Release(&v23);
    v19 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
    RAII::CleanupInfo<unsigned short *>::Release(&v20);
    v21 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
    RAII::CleanupInfo<unsigned short *>::Release(&v22);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180059430  push    rbp
0x180059432  push    rbx
0x180059433  push    rsi
0x180059434  push    rdi
0x180059435  push    r12
0x180059437  push    r13
0x180059439  push    r14
0x18005943b  push    r15
0x18005943d  lea     rbp, [rsp-1Fh]
0x180059442  sub     rsp, 0A8h
0x180059449  mov     rbx, r9
0x18005944c  mov     r15, r8
0x18005944f  mov     r13, rdx
0x180059452  mov     r12, rcx
0x180059455  mov     rcx, [r8]; psz
0x180059458  call    cs:__imp_SysAllocString
0x18005945e  lea     rdi, ??_7?$CAutoCleanup@PEAG@RAII@@6B@; const RAII::CAutoCleanup<ushort *>::`vftable'
0x180059465  mov     [rbp+57h+var_90], rdi
0x180059469  mov     [rbp+57h+var_88], rax
0x18005946d  lea     rcx, [rbp+57h+var_90]
0x180059471  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180059476  xor     esi, esi
0x180059478  cmp     [rax], rsi
0x18005947b  jnz     short loc_1800594C5
0x18005947d  lea     rax, aFailedToAlloca_39; "Failed to allocate bstrName"
0x180059484  mov     [rsp+0E0h+var_B8], rax
0x180059489  mov     dword ptr [rsp+0E0h+var_C0], 1C7h
0x180059491  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x180059498  lea     r8, aPushbuttonrese_16; "PushButtonReset::XmlDocument::CreateEle"...
0x18005949f  mov     edx, 8007000Eh
0x1800594a4  lea     ecx, [rsi+2]
0x1800594a7  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800594ac  nop
0x1800594ad  mov     [rbp+57h+var_90], rdi
0x1800594b1  lea     rcx, [rbp+57h+var_88]
0x1800594b5  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x1800594ba  nop
0x1800594bb  mov     eax, 8007000Eh
0x1800594c0  jmp     loc_180059831
0x1800594c5  mov     [rbp+57h+var_A0], rdi
0x1800594c9  mov     [rbp+57h+var_98], rsi
0x1800594cd  mov     rcx, [rbx]; psz
0x1800594d0  cmp     [rcx-10h], esi
0x1800594d3  jle     loc_180059561
0x1800594d9  call    cs:__imp_SysAllocString
0x1800594df  mov     [rbp+57h+arg_10], rax
0x1800594e3  mov     rax, [rbp+57h+var_A0]
0x1800594e7  lea     rdx, [rbp+57h+arg_10]
0x1800594eb  lea     rcx, [rbp+57h+var_A0]
0x1800594ef  mov     rax, [rax+30h]
0x1800594f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800594f8  mov     rax, [rbp+57h+var_A0]
0x1800594fc  lea     rcx, [rbp+57h+var_A0]
0x180059500  mov     rax, [rax+20h]
0x180059504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059509  cmp     [rax], rsi
0x18005950c  jnz     short loc_180059561
0x18005950e  lea     rax, aFailedToAlloca_1; "Failed to allocate bstrURI"
0x180059515  mov     [rsp+0E0h+var_B8], rax
0x18005951a  mov     dword ptr [rsp+0E0h+var_C0], 1CDh
0x180059522  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x180059529  lea     r8, aPushbuttonrese_16; "PushButtonReset::XmlDocument::CreateEle"...
0x180059530  mov     edx, 8007000Eh
0x180059535  mov     ecx, 2
0x18005953a  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005953f  nop
0x180059540  mov     [rbp+57h+var_A0], rdi
0x180059544  lea     rcx, [rbp+57h+var_98]
0x180059548  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005954d  nop
0x18005954e  mov     [rbp+57h+var_90], rdi
0x180059552  lea     rcx, [rbp+57h+var_88]
0x180059556  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005955b  nop
0x18005955c  jmp     loc_1800594BB
0x180059561  xorps   xmm0, xmm0
0x180059564  xor     eax, eax
0x180059566  mov     [rbp+57h+arg_10], rax
0x18005956a  movups  [rbp+57h+var_60], xmm0
0x18005956e  mov     eax, 16h
0x180059573  mov     word ptr [rbp+57h+var_60], ax
0x180059577  mov     dword ptr [rbp+57h+var_60+8], 1
0x18005957e  mov     [rbp+57h+var_78], rsi
0x180059582  lea     rax, ??_7?$CAutoRelease@PEAUIXMLDOMNode@@@RAII@@6B@; const RAII::CAutoRelease<IXMLDOMNode *>::`vftable'
0x180059589  mov     [rbp+57h+var_80], rax
0x18005958d  mov     rax, [r12]
0x180059591  mov     rcx, r12
0x180059594  mov     rax, [rax+18h]
0x180059598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005959d  mov     r14, rax
0x1800595a0  mov     rcx, [rax]
0x1800595a3  mov     rsi, [rcx+1C0h]
0x1800595aa  mov     rcx, [rbp+57h+var_80]
0x1800595ae  mov     rax, [rcx+8]
0x1800595b2  lea     rcx, [rbp+57h+var_80]
0x1800595b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800595bb  mov     rdi, rax
0x1800595be  mov     rcx, [rbp+57h+var_A0]
0x1800595c2  mov     rax, [rcx+20h]
0x1800595c6  lea     rcx, [rbp+57h+var_A0]
0x1800595ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800595cf  mov     rbx, [rax]
0x1800595d2  mov     rcx, [rbp+57h+var_90]
0x1800595d6  mov     rax, [rcx+20h]
0x1800595da  lea     rcx, [rbp+57h+var_90]
0x1800595de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800595e3  movups  xmm0, [rbp+57h+var_60]
0x1800595e7  movaps  [rbp+57h+var_60], xmm0
0x1800595eb  movsd   xmm1, [rbp+57h+arg_10]
0x1800595f0  movsd   [rbp+57h+var_50], xmm1
0x1800595f5  mov     [rsp+0E0h+var_C0], rdi
0x1800595fa  mov     r9, rbx
0x1800595fd  mov     r8, [rax]
0x180059600  lea     rdx, [rbp+57h+var_60]
0x180059604  mov     rcx, r14
0x180059607  mov     rax, rsi
0x18005960a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005960f  mov     ebx, eax
0x180059611  test    eax, eax
0x180059613  jns     short loc_180059689
0x180059615  mov     rcx, [r15]
0x180059618  mov     [rsp+0E0h+var_B0], rcx
0x18005961d  lea     rax, aFailedToCreate_33; "Failed to create element [%s]"
0x180059624  mov     [rsp+0E0h+var_B8], rax
0x180059629  mov     dword ptr [rsp+0E0h+var_C0], 1D6h
0x180059631  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x180059638  lea     r8, aPushbuttonrese_16; "PushButtonReset::XmlDocument::CreateEle"...
0x18005963f  mov     edx, ebx
0x180059641  mov     ecx, 2
0x180059646  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005964b  nop
0x18005964c  lea     rax, ??_7?$CAutoRelease@PEAUIXMLDOMNode@@@RAII@@6B@; const RAII::CAutoRelease<IXMLDOMNode *>::`vftable'
0x180059653  mov     [rbp+57h+var_80], rax
0x180059657  lea     rcx, [rbp+57h+var_80]
0x18005965b  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x180059660  nop
0x180059661  lea     rdi, ??_7?$CAutoCleanup@PEAG@RAII@@6B@; const RAII::CAutoCleanup<ushort *>::`vftable'
0x180059668  mov     [rbp+57h+var_A0], rdi
0x18005966c  lea     rcx, [rbp+57h+var_98]
0x180059670  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x180059675  nop
0x180059676  mov     [rbp+57h+var_90], rdi
0x18005967a  lea     rcx, [rbp+57h+var_88]
0x18005967e  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x180059683  nop
0x180059684  jmp     loc_18005982F
0x180059689  mov     [rbp+57h+arg_10], r12
0x18005968d  lea     rcx, [rbp+57h+arg_10]
0x180059691  call    ??$PbrNew@VXmlNode@PushButtonReset@@AEAPEAVXmlDocument@2@@@YAPEAVXmlNode@PushButtonReset@@AEAPEAVXmlDocument@1@@Z; PbrNew<PushButtonReset::XmlNode,PushButtonReset::XmlDocument * &>(PushButtonReset::XmlDocument * &)
0x180059696  mov     [rbp+57h+var_68], rax
0x18005969a  lea     rdi, ??_7?$CAutoPbrDelete@PEAVXmlNode@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::XmlNode *>::`vftable'
0x1800596a1  mov     [rbp+57h+var_70], rdi
0x1800596a5  lea     rcx, [rbp+57h+var_70]
0x1800596a9  call    ??7?$CAutoCleanupBase@PEAUISetupOneSettings@@@RAII@@UEBA_NXZ; RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(void)
0x1800596ae  test    al, al
0x1800596b0  jz      short loc_18005972F
0x1800596b2  lea     rax, aFailedToAlloca_18; "Failed to allocate xnode"
0x1800596b9  mov     [rsp+0E0h+var_B8], rax
0x1800596be  mov     dword ptr [rsp+0E0h+var_C0], 1D9h
0x1800596c6  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x1800596cd  lea     r8, aPushbuttonrese_16; "PushButtonReset::XmlDocument::CreateEle"...
0x1800596d4  mov     edx, 8007000Eh
0x1800596d9  mov     ecx, 2
0x1800596de  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800596e3  nop
0x1800596e4  mov     [rbp+57h+var_70], rdi
0x1800596e8  lea     rcx, [rbp+57h+var_70]
0x1800596ec  call    ?Release@?$CAutoPbrDelete@PEAVXmlNode@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::XmlNode *>::Release(void)
0x1800596f1  nop
0x1800596f2  lea     rax, ??_7?$CAutoRelease@PEAUIXMLDOMNode@@@RAII@@6B@; const RAII::CAutoRelease<IXMLDOMNode *>::`vftable'
0x1800596f9  mov     [rbp+57h+var_80], rax
0x1800596fd  lea     rcx, [rbp+57h+var_80]
0x180059701  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x180059706  nop
0x180059707  lea     rdi, ??_7?$CAutoCleanup@PEAG@RAII@@6B@; const RAII::CAutoCleanup<ushort *>::`vftable'
0x18005970e  mov     [rbp+57h+var_A0], rdi
0x180059712  lea     rcx, [rbp+57h+var_98]
0x180059716  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005971b  nop
0x18005971c  mov     [rbp+57h+var_90], rdi
0x180059720  lea     rcx, [rbp+57h+var_88]
0x180059724  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x180059729  nop
0x18005972a  jmp     loc_1800594BB
0x18005972f  mov     rax, [rbp+57h+var_70]
0x180059733  lea     rcx, [rbp+57h+var_70]
0x180059737  mov     rax, [rax+18h]
0x18005973b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059740  mov     rdx, [rbp+57h+var_78]; struct IXMLDOMNode *
0x180059744  mov     [rbp+57h+var_78], 0
0x18005974c  mov     rcx, rax; this
0x18005974f  call    ?Initialize@XmlNode@PushButtonReset@@AEAAJPEAUIXMLDOMNode@@@Z; PushButtonReset::XmlNode::Initialize(IXMLDOMNode *)
0x180059754  mov     ebx, eax
0x180059756  test    eax, eax
0x180059758  jns     short loc_1800597D9
0x18005975a  mov     rcx, [r15]
0x18005975d  mov     [rsp+0E0h+var_B0], rcx
0x180059762  lea     rax, aFailedToInitia_0; "Failed to initialize node for DOM eleme"...
0x180059769  mov     [rsp+0E0h+var_B8], rax
0x18005976e  mov     dword ptr [rsp+0E0h+var_C0], 1DCh
0x180059776  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005977d  lea     r8, aPushbuttonrese_16; "PushButtonReset::XmlDocument::CreateEle"...
0x180059784  mov     edx, ebx
0x180059786  mov     ecx, 2
0x18005978b  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180059790  nop
0x180059791  mov     [rbp+57h+var_70], rdi
0x180059795  lea     rcx, [rbp+57h+var_70]
0x180059799  call    ?Release@?$CAutoPbrDelete@PEAVXmlNode@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::XmlNode *>::Release(void)
0x18005979e  nop
0x18005979f  lea     rax, ??_7?$CAutoRelease@PEAUIXMLDOMNode@@@RAII@@6B@; const RAII::CAutoRelease<IXMLDOMNode *>::`vftable'
0x1800597a6  mov     [rbp+57h+var_80], rax
0x1800597aa  lea     rcx, [rbp+57h+var_80]
0x1800597ae  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x1800597b3  nop
0x1800597b4  lea     rdi, ??_7?$CAutoCleanup@PEAG@RAII@@6B@; const RAII::CAutoCleanup<ushort *>::`vftable'
0x1800597bb  mov     [rbp+57h+var_A0], rdi
0x1800597bf  lea     rcx, [rbp+57h+var_98]
0x1800597c3  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x1800597c8  nop
0x1800597c9  mov     [rbp+57h+var_90], rdi
0x1800597cd  lea     rcx, [rbp+57h+var_88]
0x1800597d1  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x1800597d6  nop
0x1800597d7  jmp     short loc_18005982F
0x1800597d9  mov     rax, [rbp+57h+var_68]
0x1800597dd  mov     [rbp+57h+var_68], 0
0x1800597e5  mov     [r13+0], rax
0x1800597e9  mov     [rbp+57h+var_70], rdi
0x1800597ed  lea     rcx, [rbp+57h+var_70]
0x1800597f1  call    ?Release@?$CAutoPbrDelete@PEAVXmlNode@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::XmlNode *>::Release(void)
0x1800597f6  nop
0x1800597f7  lea     rax, ??_7?$CAutoRelease@PEAUIXMLDOMNode@@@RAII@@6B@; const RAII::CAutoRelease<IXMLDOMNode *>::`vftable'
0x1800597fe  mov     [rbp+57h+var_80], rax
0x180059802  lea     rcx, [rbp+57h+var_80]
0x180059806  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005980b  nop
0x18005980c  lea     rdi, ??_7?$CAutoCleanup@PEAG@RAII@@6B@; const RAII::CAutoCleanup<ushort *>::`vftable'
0x180059813  mov     [rbp+57h+var_A0], rdi
0x180059817  lea     rcx, [rbp+57h+var_98]
0x18005981b  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x180059820  nop
0x180059821  mov     [rbp+57h+var_90], rdi
0x180059825  lea     rcx, [rbp+57h+var_88]
0x180059829  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005982e  nop
0x18005982f  mov     eax, ebx
0x180059831  add     rsp, 0A8h
0x180059838  pop     r15
0x18005983a  pop     r14
0x18005983c  pop     r13
0x18005983e  pop     r12
0x180059840  pop     rdi
0x180059841  pop     rsi
0x180059842  pop     rbx
0x180059843  pop     rbp
0x180059844  retn
```
