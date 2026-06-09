# PushButtonReset::XmlNode::SelectNode(PushButtonReset::XmlNode * *,ushort const *,...)

- ea: `0x18005ab64`
- end: `0x18005aecc`
- name: `?SelectNode@XmlNode@PushButtonReset@@QEAAJPEAPEAV12@PEBGZZ`
- size: `872`
- prototype: `__int64(PushButtonReset::XmlNode *__hidden this, struct PushButtonReset::XmlNode **, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800528fc`

## callees

- `0x180004af8`
- `0x180005c00`
- `0x180005cc0`
- `0x180008a5c`
- `0x18000d92c`
- `0x180023620`
- `0x180037344`
- `0x1800527e0`
- `0x1800588dc`
- `0x180059e54`
- `0x18005a498`
- `0x18005ab64`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18005abb5`
- `OLEAUT32!__imp_SysAllocString` at `0x18005abb5`

## string_xrefs

- `0x18005abed`: `base\reset\util\src\xml.cpp`
- `0x18005aca3`: `base\reset\util\src\xml.cpp`
- `0x18005ad6e`: `base\reset\util\src\xml.cpp`
- `0x18005ae12`: `base\reset\util\src\xml.cpp`
- `0x18005abd9`: `Failed to allocate bstrXPath`
- `0x18005abf4`: `PushButtonReset::XmlNode::SelectNode`
- `0x18005acaa`: `PushButtonReset::XmlNode::SelectNode`
- `0x18005ad75`: `PushButtonReset::XmlNode::SelectNode`
- `0x18005ae19`: `PushButtonReset::XmlNode::SelectNode`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 PushButtonReset::XmlNode::SelectNode(
        PushButtonReset::XmlNode *this,
        struct PushButtonReset::XmlNode **a2,
        const unsigned __int16 *a3,
        ...)
{
  OLECHAR *v5; // rbx
  BSTR v6; // rax
  __int64 v7; // r14
  __int64 (__fastcall *v8)(__int64, _QWORD, __int64); // rsi
  __int64 v9; // rdi
  _QWORD *v10; // rax
  int v11; // edi
  PushButtonReset::XmlNode *v12; // rax
  struct IXMLDOMNode *v13; // rdx
  struct PushButtonReset::XmlNode *v14; // rax
  OLECHAR *psz; // [rsp+40h] [rbp-40h] BYREF
  void **v17; // [rsp+48h] [rbp-38h] BYREF
  struct IXMLDOMNode *v18; // [rsp+50h] [rbp-30h]
  void **v19; // [rsp+58h] [rbp-28h] BYREF
  BSTR v20; // [rsp+60h] [rbp-20h] BYREF
  void **v21; // [rsp+68h] [rbp-18h] BYREF
  __int64 v22; // [rsp+70h] [rbp-10h]
  va_list va; // [rsp+D8h] [rbp+58h] BYREF

  va_start(va, a3);
  psz = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&psz);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::FormatV(
    &psz,
    a3,
    (__int64 *)va);
  v5 = psz;
  v6 = SysAllocString(psz);
  v19 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
  v20 = v6;
  if ( !*(_QWORD *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v19) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942414LL,
      "PushButtonReset::XmlNode::SelectNode",
      "base\\reset\\util\\src\\xml.cpp",
      955,
      L"Failed to allocate bstrXPath");
    v19 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
    RAII::CleanupInfo<unsigned short *>::Release(&v20);
LABEL_9:
    v11 = -2147024882;
    goto LABEL_14;
  }
  v18 = 0;
  v17 = &RAII::CAutoRelease<IXMLDOMNode *>::`vftable';
  v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 1) + 24LL))((char *)this + 8);
  v8 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v7 + 296LL);
  v9 = ((__int64 (__fastcall *)(void ***))v17[1])(&v17);
  v10 = (_QWORD *)((__int64 (__fastcall *)(void ***))v19[4])(&v19);
  v11 = v8(v7, *v10, v9);
  if ( v11 >= 0 )
  {
    if ( ((unsigned __int8 (__fastcall *)(void ***))v17[9])(&v17) )
    {
      v17 = &RAII::CAutoRelease<IXMLDOMNode *>::`vftable';
      RAII::CAutoRelease<IXMLDOMParseError *>::Release(&v17);
      v19 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
      RAII::CleanupInfo<unsigned short *>::Release(&v20);
      v11 = -2147023728;
    }
    else
    {
      v22 = PbrNew<PushButtonReset::XmlNode,PushButtonReset::XmlDocument * &>((struct PushButtonReset::XmlDocument **)this);
      v21 = &RAII::CAutoPbrDelete<PushButtonReset::XmlNode *>::`vftable';
      if ( (unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!((__int64 *)&v21) )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          2147942414LL,
          "PushButtonReset::XmlNode::SelectNode",
          "base\\reset\\util\\src\\xml.cpp",
          967,
          L"Failed to allocate xnode");
        v21 = &RAII::CAutoPbrDelete<PushButtonReset::XmlNode *>::`vftable';
        RAII::CAutoPbrDelete<PushButtonReset::XmlNode *>::Release(&v21);
        v17 = &RAII::CAutoRelease<IXMLDOMNode *>::`vftable';
        RAII::CAutoRelease<IXMLDOMParseError *>::Release(&v17);
        v19 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
        RAII::CleanupInfo<unsigned short *>::Release(&v20);
        goto LABEL_9;
      }
      v12 = (PushButtonReset::XmlNode *)((__int64 (__fastcall *)(void ***))v21[3])(&v21);
      v13 = v18;
      v18 = 0;
      v11 = PushButtonReset::XmlNode::Initialize(v12, v13);
      if ( v11 >= 0 )
      {
        v14 = (struct PushButtonReset::XmlNode *)v22;
        v22 = 0;
        *a2 = v14;
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v11,
          "PushButtonReset::XmlNode::SelectNode",
          "base\\reset\\util\\src\\xml.cpp",
          970,
          L"Failed to initialize result for [%s]",
          v5);
      }
      v21 = &RAII::CAutoPbrDelete<PushButtonReset::XmlNode *>::`vftable';
      RAII::CAutoPbrDelete<PushButtonReset::XmlNode *>::Release(&v21);
      v17 = &RAII::CAutoRelease<IXMLDOMNode *>::`vftable';
      RAII::CAutoRelease<IXMLDOMParseError *>::Release(&v17);
      v19 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
      RAII::CleanupInfo<unsigned short *>::Release(&v20);
    }
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v11,
      "PushButtonReset::XmlNode::SelectNode",
      "base\\reset\\util\\src\\xml.cpp",
      959,
      L"Failed to run query [%s]",
      v5);
    v17 = &RAII::CAutoRelease<IXMLDOMNode *>::`vftable';
    RAII::CAutoRelease<IXMLDOMParseError *>::Release(&v17);
    v19 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
    RAII::CleanupInfo<unsigned short *>::Release(&v20);
  }
LABEL_14:
  ATL::CStringData::Release((ATL::CStringData *)(v5 - 12));
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18005ab64  mov     [rsp-38h+arg_10], r8
0x18005ab69  mov     [rsp-38h+arg_18], r9
0x18005ab6e  push    rbp
0x18005ab6f  push    rbx
0x18005ab70  push    rsi
0x18005ab71  push    rdi
0x18005ab72  push    r12
0x18005ab74  push    r14
0x18005ab76  push    r15
0x18005ab78  mov     rbp, rsp
0x18005ab7b  sub     rsp, 80h
0x18005ab82  mov     r12, rdx
0x18005ab85  mov     r15, rcx
0x18005ab88  mov     [rbp+psz], 0
0x18005ab90  lea     rbx, [rbp+arg_18]
0x18005ab94  lea     rcx, [rbp+psz]
0x18005ab98  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18005ab9d  nop
0x18005ab9e  mov     r8, rbx
0x18005aba1  mov     rdx, [rbp+arg_10]
0x18005aba5  lea     rcx, [rbp+psz]
0x18005aba9  call    ?FormatV@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGPEAD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::FormatV(ushort const *,char *)
0x18005abae  mov     rbx, [rbp+psz]
0x18005abb2  mov     rcx, rbx; psz
0x18005abb5  call    cs:__imp_SysAllocString
0x18005abbb  lea     rdi, ??_7?$CAutoCleanup@PEAG@RAII@@6B@; const RAII::CAutoCleanup<ushort *>::`vftable'
0x18005abc2  mov     [rbp+var_28], rdi
0x18005abc6  mov     [rbp+var_20], rax
0x18005abca  lea     rcx, [rbp+var_28]
0x18005abce  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18005abd3  cmp     qword ptr [rax], 0
0x18005abd7  jnz     short loc_18005AC1E
0x18005abd9  lea     rax, aFailedToAlloca_34; "Failed to allocate bstrXPath"
0x18005abe0  mov     [rsp+80h+var_58], rax
0x18005abe5  mov     [rsp+80h+var_60], 3BBh
0x18005abed  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005abf4  lea     r8, aPushbuttonrese_84; "PushButtonReset::XmlNode::SelectNode"
0x18005abfb  mov     edx, 8007000Eh
0x18005ac00  mov     ecx, 2
0x18005ac05  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005ac0a  nop
0x18005ac0b  mov     [rbp+var_28], rdi
0x18005ac0f  lea     rcx, [rbp+var_20]
0x18005ac13  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005ac18  nop
0x18005ac19  jmp     loc_18005ADC4
0x18005ac1e  mov     [rbp+var_30], 0
0x18005ac26  lea     rax, ??_7?$CAutoRelease@PEAUIXMLDOMNode@@@RAII@@6B@; const RAII::CAutoRelease<IXMLDOMNode *>::`vftable'
0x18005ac2d  mov     [rbp+var_38], rax
0x18005ac31  lea     rcx, [r15+8]
0x18005ac35  mov     rax, [rcx]
0x18005ac38  mov     rax, [rax+18h]
0x18005ac3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ac41  mov     r14, rax
0x18005ac44  mov     rcx, [rax]
0x18005ac47  mov     rsi, [rcx+128h]
0x18005ac4e  mov     rcx, [rbp+var_38]
0x18005ac52  mov     rax, [rcx+8]
0x18005ac56  lea     rcx, [rbp+var_38]
0x18005ac5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ac5f  mov     rdi, rax
0x18005ac62  mov     rcx, [rbp+var_28]
0x18005ac66  mov     rax, [rcx+20h]
0x18005ac6a  lea     rcx, [rbp+var_28]
0x18005ac6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ac73  mov     r8, rdi
0x18005ac76  mov     rdx, [rax]
0x18005ac79  mov     rcx, r14
0x18005ac7c  mov     rax, rsi
0x18005ac7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ac84  mov     edi, eax
0x18005ac86  test    eax, eax
0x18005ac88  jns     short loc_18005ACED
0x18005ac8a  mov     [rsp+80h+var_50], rbx
0x18005ac8f  lea     rax, aFailedToRunQue; "Failed to run query [%s]"
0x18005ac96  mov     [rsp+80h+var_58], rax
0x18005ac9b  mov     [rsp+80h+var_60], 3BFh
0x18005aca3  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005acaa  lea     r8, aPushbuttonrese_84; "PushButtonReset::XmlNode::SelectNode"
0x18005acb1  mov     edx, edi
0x18005acb3  mov     ecx, 2
0x18005acb8  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005acbd  nop
0x18005acbe  lea     rax, ??_7?$CAutoRelease@PEAUIXMLDOMNode@@@RAII@@6B@; const RAII::CAutoRelease<IXMLDOMNode *>::`vftable'
0x18005acc5  mov     [rbp+var_38], rax
0x18005acc9  lea     rcx, [rbp+var_38]
0x18005accd  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005acd2  nop
0x18005acd3  lea     rax, ??_7?$CAutoCleanup@PEAG@RAII@@6B@; const RAII::CAutoCleanup<ushort *>::`vftable'
0x18005acda  mov     [rbp+var_28], rax
0x18005acde  lea     rcx, [rbp+var_20]
0x18005ace2  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005ace7  nop
0x18005ace8  jmp     loc_18005AEAF
0x18005aced  mov     rax, [rbp+var_38]
0x18005acf1  lea     rcx, [rbp+var_38]
0x18005acf5  mov     rax, [rax+48h]
0x18005acf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005acfe  test    al, al
0x18005ad00  jz      short loc_18005AD36
0x18005ad02  lea     rax, ??_7?$CAutoRelease@PEAUIXMLDOMNode@@@RAII@@6B@; const RAII::CAutoRelease<IXMLDOMNode *>::`vftable'
0x18005ad09  mov     [rbp+var_38], rax
0x18005ad0d  lea     rcx, [rbp+var_38]
0x18005ad11  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005ad16  nop
0x18005ad17  lea     rax, ??_7?$CAutoCleanup@PEAG@RAII@@6B@; const RAII::CAutoCleanup<ushort *>::`vftable'
0x18005ad1e  mov     [rbp+var_28], rax
0x18005ad22  lea     rcx, [rbp+var_20]
0x18005ad26  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005ad2b  nop
0x18005ad2c  mov     edi, 80070490h
0x18005ad31  jmp     loc_18005AEAF
0x18005ad36  mov     rcx, r15
0x18005ad39  call    ??$PbrNew@VXmlNode@PushButtonReset@@AEAPEAVXmlDocument@2@@@YAPEAVXmlNode@PushButtonReset@@AEAPEAVXmlDocument@1@@Z; PbrNew<PushButtonReset::XmlNode,PushButtonReset::XmlDocument * &>(PushButtonReset::XmlDocument * &)
0x18005ad3e  mov     [rbp+var_10], rax
0x18005ad42  lea     rsi, ??_7?$CAutoPbrDelete@PEAVXmlNode@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::XmlNode *>::`vftable'
0x18005ad49  mov     [rbp+var_18], rsi
0x18005ad4d  lea     rcx, [rbp+var_18]
0x18005ad51  call    ??7?$CAutoCleanupBase@PEAUISetupOneSettings@@@RAII@@UEBA_NXZ; RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(void)
0x18005ad56  test    al, al
0x18005ad58  jz      short loc_18005ADCE
0x18005ad5a  lea     rax, aFailedToAlloca_18; "Failed to allocate xnode"
0x18005ad61  mov     [rsp+80h+var_58], rax
0x18005ad66  mov     [rsp+80h+var_60], 3C7h
0x18005ad6e  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005ad75  lea     r8, aPushbuttonrese_84; "PushButtonReset::XmlNode::SelectNode"
0x18005ad7c  mov     edx, 8007000Eh
0x18005ad81  mov     ecx, 2
0x18005ad86  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005ad8b  nop
0x18005ad8c  mov     [rbp+var_18], rsi
0x18005ad90  lea     rcx, [rbp+var_18]
0x18005ad94  call    ?Release@?$CAutoPbrDelete@PEAVXmlNode@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::XmlNode *>::Release(void)
0x18005ad99  nop
0x18005ad9a  lea     rax, ??_7?$CAutoRelease@PEAUIXMLDOMNode@@@RAII@@6B@; const RAII::CAutoRelease<IXMLDOMNode *>::`vftable'
0x18005ada1  mov     [rbp+var_38], rax
0x18005ada5  lea     rcx, [rbp+var_38]
0x18005ada9  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005adae  nop
0x18005adaf  lea     rax, ??_7?$CAutoCleanup@PEAG@RAII@@6B@; const RAII::CAutoCleanup<ushort *>::`vftable'
0x18005adb6  mov     [rbp+var_28], rax
0x18005adba  lea     rcx, [rbp+var_20]
0x18005adbe  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005adc3  nop
0x18005adc4  mov     edi, 8007000Eh
0x18005adc9  jmp     loc_18005AEAF
0x18005adce  mov     rax, [rbp+var_18]
0x18005add2  lea     rcx, [rbp+var_18]
0x18005add6  mov     rax, [rax+18h]
0x18005adda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005addf  mov     rdx, [rbp+var_30]; struct IXMLDOMNode *
0x18005ade3  mov     [rbp+var_30], 0
0x18005adeb  mov     rcx, rax; this
0x18005adee  call    ?Initialize@XmlNode@PushButtonReset@@AEAAJPEAUIXMLDOMNode@@@Z; PushButtonReset::XmlNode::Initialize(IXMLDOMNode *)
0x18005adf3  mov     edi, eax
0x18005adf5  test    eax, eax
0x18005adf7  jns     short loc_18005AE67
0x18005adf9  mov     [rsp+80h+var_50], rbx
0x18005adfe  lea     rax, aFailedToInitia_8; "Failed to initialize result for [%s]"
0x18005ae05  mov     [rsp+80h+var_58], rax
0x18005ae0a  mov     [rsp+80h+var_60], 3CAh
0x18005ae12  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005ae19  lea     r8, aPushbuttonrese_84; "PushButtonReset::XmlNode::SelectNode"
0x18005ae20  mov     edx, edi
0x18005ae22  mov     ecx, 2
0x18005ae27  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005ae2c  nop
0x18005ae2d  mov     [rbp+var_18], rsi
0x18005ae31  lea     rcx, [rbp+var_18]
0x18005ae35  call    ?Release@?$CAutoPbrDelete@PEAVXmlNode@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::XmlNode *>::Release(void)
0x18005ae3a  nop
0x18005ae3b  lea     rax, ??_7?$CAutoRelease@PEAUIXMLDOMNode@@@RAII@@6B@; const RAII::CAutoRelease<IXMLDOMNode *>::`vftable'
0x18005ae42  mov     [rbp+var_38], rax
0x18005ae46  lea     rcx, [rbp+var_38]
0x18005ae4a  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005ae4f  nop
0x18005ae50  lea     rax, ??_7?$CAutoCleanup@PEAG@RAII@@6B@; const RAII::CAutoCleanup<ushort *>::`vftable'
0x18005ae57  mov     [rbp+var_28], rax
0x18005ae5b  lea     rcx, [rbp+var_20]
0x18005ae5f  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005ae64  nop
0x18005ae65  jmp     short loc_18005AEAF
0x18005ae67  mov     rax, [rbp+var_10]
0x18005ae6b  mov     [rbp+var_10], 0
0x18005ae73  mov     [r12], rax
0x18005ae77  mov     [rbp+var_18], rsi
0x18005ae7b  lea     rcx, [rbp+var_18]
0x18005ae7f  call    ?Release@?$CAutoPbrDelete@PEAVXmlNode@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::XmlNode *>::Release(void)
0x18005ae84  nop
0x18005ae85  lea     rax, ??_7?$CAutoRelease@PEAUIXMLDOMNode@@@RAII@@6B@; const RAII::CAutoRelease<IXMLDOMNode *>::`vftable'
0x18005ae8c  mov     [rbp+var_38], rax
0x18005ae90  lea     rcx, [rbp+var_38]
0x18005ae94  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005ae99  nop
0x18005ae9a  lea     rax, ??_7?$CAutoCleanup@PEAG@RAII@@6B@; const RAII::CAutoCleanup<ushort *>::`vftable'
0x18005aea1  mov     [rbp+var_28], rax
0x18005aea5  lea     rcx, [rbp+var_20]
0x18005aea9  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005aeae  nop
0x18005aeaf  lea     rcx, [rbx-18h]; this
0x18005aeb3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18005aeb8  mov     eax, edi
0x18005aeba  add     rsp, 80h
0x18005aec1  pop     r15
0x18005aec3  pop     r14
0x18005aec5  pop     r12
0x18005aec7  pop     rdi
0x18005aec8  pop     rsi
0x18005aec9  pop     rbx
0x18005aeca  pop     rbp
0x18005aecb  retn
```
