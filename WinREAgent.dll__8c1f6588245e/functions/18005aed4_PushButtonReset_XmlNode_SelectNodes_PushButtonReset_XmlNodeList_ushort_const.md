# PushButtonReset::XmlNode::SelectNodes(PushButtonReset::XmlNodeList * *,ushort const *,...)

- ea: `0x18005aed4`
- end: `0x18005b511`
- name: `?SelectNodes@XmlNode@PushButtonReset@@QEAAJPEAPEAVXmlNodeList@2@PEBGZZ`
- size: `1597`
- prototype: `__int64(PushButtonReset::XmlNode *__hidden this, struct PushButtonReset::XmlNodeList **, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180052a7c`

## callees

- `0x180004af8`
- `0x180005c00`
- `0x180005cc0`
- `0x180006828`
- `0x180008a5c`
- `0x180009fd8`
- `0x18000d92c`
- `0x180023620`
- `0x180037344`
- `0x1800527e0`
- `0x180052800`
- `0x1800552ec`
- `0x1800588dc`
- `0x180059e54`
- `0x18005a498`
- `0x18005aed4`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18005af29`
- `OLEAUT32!__imp_SysAllocString` at `0x18005af29`

## string_xrefs

- `0x18005af60`: `base\reset\util\src\xml.cpp`
- `0x18005b011`: `base\reset\util\src\xml.cpp`
- `0x18005b0cb`: `base\reset\util\src\xml.cpp`
- `0x18005b169`: `base\reset\util\src\xml.cpp`
- `0x18005b30f`: `base\reset\util\src\xml.cpp`
- `0x18005b39e`: `base\reset\util\src\xml.cpp`
- `0x18005b43a`: `base\reset\util\src\xml.cpp`
- `0x18005af4c`: `Failed to allocate bstrXPath`
- `0x18005af67`: `PushButtonReset::XmlNode::SelectNodes`
- `0x18005b018`: `PushButtonReset::XmlNode::SelectNodes`
- `0x18005b0d2`: `PushButtonReset::XmlNode::SelectNodes`
- `0x18005b170`: `PushButtonReset::XmlNode::SelectNodes`
- `0x18005b316`: `PushButtonReset::XmlNode::SelectNodes`
- `0x18005b3a5`: `PushButtonReset::XmlNode::SelectNodes`
- `0x18005b441`: `PushButtonReset::XmlNode::SelectNodes`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 PushButtonReset::XmlNode::SelectNodes(
        PushButtonReset::XmlNode *this,
        struct PushButtonReset::XmlNodeList **a2,
        const unsigned __int16 *a3,
        ...)
{
  OLECHAR *v4; // rbx
  BSTR v5; // rax
  __int64 v6; // r14
  __int64 (__fastcall *v7)(__int64, _QWORD, __int64); // rsi
  __int64 v8; // rdi
  _QWORD *v9; // rax
  int v10; // edi
  __int64 v11; // rax
  unsigned int i; // r14d
  __int64 v13; // rsi
  __int64 (__fastcall *v14)(__int64, _QWORD, __int64); // rdi
  __int64 v15; // rax
  PushButtonReset::XmlNode *v16; // rax
  struct IXMLDOMNode *v17; // rdx
  __int64 v18; // rax
  _QWORD *v19; // rsi
  __int64 v20; // r12
  unsigned __int64 v21; // r15
  struct PushButtonReset::XmlNodeList *v22; // rax
  int v24; // [rsp+48h] [rbp-49h] BYREF
  OLECHAR *psz; // [rsp+50h] [rbp-41h] BYREF
  _QWORD v26[2]; // [rsp+58h] [rbp-39h] BYREF
  void **v27; // [rsp+68h] [rbp-29h] BYREF
  BSTR v28; // [rsp+70h] [rbp-21h] BYREF
  void **v29; // [rsp+78h] [rbp-19h] BYREF
  struct PushButtonReset::XmlNodeList *v30; // [rsp+80h] [rbp-11h]
  void **v31; // [rsp+88h] [rbp-9h] BYREF
  struct IXMLDOMNode *v32; // [rsp+90h] [rbp-1h]
  void **v33; // [rsp+98h] [rbp+7h] BYREF
  __int64 v34; // [rsp+A0h] [rbp+Fh]
  va_list va; // [rsp+110h] [rbp+7Fh] BYREF

  va_start(va, a3);
  psz = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&psz);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::FormatV(&psz, a3, va);
  v4 = psz;
  v5 = SysAllocString(psz);
  v27 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
  v28 = v5;
  if ( !*(_QWORD *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v27) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942414LL,
      "PushButtonReset::XmlNode::SelectNodes",
      "base\\reset\\util\\src\\xml.cpp",
      989,
      L"Failed to allocate bstrXPath");
    v27 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
    RAII::CleanupInfo<unsigned short *>::Release(&v28);
LABEL_9:
    v10 = -2147024882;
    goto LABEL_25;
  }
  v26[1] = 0;
  v26[0] = &RAII::CAutoRelease<IXMLDOMNodeList *>::`vftable';
  v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 1) + 24LL))((char *)this + 8);
  v7 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v6 + 288LL);
  v8 = (*(__int64 (__fastcall **)(_QWORD *))(v26[0] + 8LL))(v26);
  v9 = (_QWORD *)((__int64 (__fastcall *)(void ***))v27[4])(&v27);
  v10 = v7(v6, *v9, v8);
  if ( v10 >= 0 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD *))(v26[0] + 72LL))(v26) )
    {
      v26[0] = &RAII::CAutoRelease<IXMLDOMNodeList *>::`vftable';
      RAII::CAutoRelease<IXMLDOMParseError *>::Release(v26);
      v27 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
      RAII::CleanupInfo<unsigned short *>::Release(&v28);
      v10 = -2147023728;
    }
    else
    {
      v30 = (struct PushButtonReset::XmlNodeList *)PbrNew<PushButtonReset::XmlNodeList,>();
      v29 = &RAII::CAutoPbrDelete<PushButtonReset::XmlNodeList *>::`vftable';
      if ( (unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!((__int64 *)&v29) )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          2147942414LL,
          "PushButtonReset::XmlNode::SelectNodes",
          "base\\reset\\util\\src\\xml.cpp",
          1001,
          L"Failed to allocate xnodes");
        v29 = &RAII::CAutoPbrDelete<PushButtonReset::XmlNodeList *>::`vftable';
        RAII::CAutoPbrDelete<PushButtonReset::XmlNodeList *>::Release(&v29);
        v26[0] = &RAII::CAutoRelease<IXMLDOMNodeList *>::`vftable';
        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v26);
        v27 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
        RAII::CleanupInfo<unsigned short *>::Release(&v28);
        goto LABEL_9;
      }
      v24 = 0;
      v11 = (*(__int64 (__fastcall **)(_QWORD *))(v26[0] + 24LL))(v26);
      v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v11 + 64LL))(v11, &v24);
      if ( v10 >= 0 )
      {
        for ( i = 0; (int)i < v24; ++i )
        {
          v32 = 0;
          v31 = &RAII::CAutoRelease<IXMLDOMNode *>::`vftable';
          v13 = (*(__int64 (__fastcall **)(_QWORD *))(v26[0] + 24LL))(v26);
          v14 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v13 + 56LL);
          v15 = ((__int64 (__fastcall *)(void ***))v31[1])(&v31);
          v10 = v14(v13, i, v15);
          if ( v10 < 0 )
          {
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)v10,
              "PushButtonReset::XmlNode::SelectNodes",
              "base\\reset\\util\\src\\xml.cpp",
              1013,
              L"Failed to get result %u for [%s]",
              i,
              v4);
            v31 = &RAII::CAutoRelease<IXMLDOMNode *>::`vftable';
            RAII::CAutoRelease<IXMLDOMParseError *>::Release(&v31);
            v29 = &RAII::CAutoPbrDelete<PushButtonReset::XmlNodeList *>::`vftable';
            RAII::CAutoPbrDelete<PushButtonReset::XmlNodeList *>::Release(&v29);
            v26[0] = &RAII::CAutoRelease<IXMLDOMNodeList *>::`vftable';
            RAII::CAutoRelease<IXMLDOMParseError *>::Release(v26);
            v27 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
            RAII::CleanupInfo<unsigned short *>::Release(&v28);
            goto LABEL_25;
          }
          v34 = PbrNew<PushButtonReset::XmlNode,PushButtonReset::XmlDocument * &>((struct PushButtonReset::XmlDocument **)this);
          v33 = &RAII::CAutoPbrDelete<PushButtonReset::XmlNode *>::`vftable';
          if ( (unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!((__int64 *)&v33) )
          {
            PushButtonReset::Logging::TraceErr(
              2,
              2147942414LL,
              "PushButtonReset::XmlNode::SelectNodes",
              "base\\reset\\util\\src\\xml.cpp",
              1016,
              L"Failed to allocate xnode");
            v33 = &RAII::CAutoPbrDelete<PushButtonReset::XmlNode *>::`vftable';
            RAII::CAutoPbrDelete<PushButtonReset::XmlNode *>::Release(&v33);
            v31 = &RAII::CAutoRelease<IXMLDOMNode *>::`vftable';
            RAII::CAutoRelease<IXMLDOMParseError *>::Release(&v31);
            v29 = &RAII::CAutoPbrDelete<PushButtonReset::XmlNodeList *>::`vftable';
            RAII::CAutoPbrDelete<PushButtonReset::XmlNodeList *>::Release(&v29);
            v26[0] = &RAII::CAutoRelease<IXMLDOMNodeList *>::`vftable';
            RAII::CAutoRelease<IXMLDOMParseError *>::Release(v26);
            v27 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
            RAII::CleanupInfo<unsigned short *>::Release(&v28);
            goto LABEL_9;
          }
          v16 = (PushButtonReset::XmlNode *)((__int64 (__fastcall *)(void ***))v33[3])(&v33);
          v17 = v32;
          v32 = 0;
          v10 = PushButtonReset::XmlNode::Initialize(v16, v17);
          if ( v10 < 0 )
          {
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)v10,
              "PushButtonReset::XmlNode::SelectNodes",
              "base\\reset\\util\\src\\xml.cpp",
              1021,
              L"Failed to initialize result %u for [%s]",
              i,
              v4);
            v33 = &RAII::CAutoPbrDelete<PushButtonReset::XmlNode *>::`vftable';
            RAII::CAutoPbrDelete<PushButtonReset::XmlNode *>::Release(&v33);
            v31 = &RAII::CAutoRelease<IXMLDOMNode *>::`vftable';
            RAII::CAutoRelease<IXMLDOMParseError *>::Release(&v31);
            v29 = &RAII::CAutoPbrDelete<PushButtonReset::XmlNodeList *>::`vftable';
            RAII::CAutoPbrDelete<PushButtonReset::XmlNodeList *>::Release(&v29);
            v26[0] = &RAII::CAutoRelease<IXMLDOMNodeList *>::`vftable';
            RAII::CAutoRelease<IXMLDOMParseError *>::Release(v26);
            v27 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
            RAII::CleanupInfo<unsigned short *>::Release(&v28);
            goto LABEL_25;
          }
          v18 = ((__int64 (__fastcall *)(void ***))v29[3])(&v29);
          v19 = (_QWORD *)v18;
          v20 = v34;
          v34 = 0;
          v21 = *(_QWORD *)(v18 + 8);
          if ( v21 >= *(_QWORD *)(v18 + 16)
            && !(unsigned __int8)ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::GrowBuffer(
                                   v18,
                                   v21 + 1) )
          {
            ATL::AtlThrowImpl(-2147024882);
          }
          *(_QWORD *)(*v19 + 8 * v21) = v20;
          ++v19[1];
          v33 = &RAII::CAutoPbrDelete<PushButtonReset::XmlNode *>::`vftable';
          RAII::CAutoPbrDelete<PushButtonReset::XmlNode *>::Release(&v33);
          v31 = &RAII::CAutoRelease<IXMLDOMNode *>::`vftable';
          RAII::CAutoRelease<IXMLDOMParseError *>::Release(&v31);
        }
        v22 = v30;
        v30 = 0;
        *a2 = v22;
        v29 = &RAII::CAutoPbrDelete<PushButtonReset::XmlNodeList *>::`vftable';
        RAII::CAutoPbrDelete<PushButtonReset::XmlNodeList *>::Release(&v29);
        v26[0] = &RAII::CAutoRelease<IXMLDOMNodeList *>::`vftable';
        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v26);
        v27 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
        RAII::CleanupInfo<unsigned short *>::Release(&v28);
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v10,
          "PushButtonReset::XmlNode::SelectNodes",
          "base\\reset\\util\\src\\xml.cpp",
          1005,
          &pszFormat);
        v29 = &RAII::CAutoPbrDelete<PushButtonReset::XmlNodeList *>::`vftable';
        RAII::CAutoPbrDelete<PushButtonReset::XmlNodeList *>::Release(&v29);
        v26[0] = &RAII::CAutoRelease<IXMLDOMNodeList *>::`vftable';
        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v26);
        v27 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
        RAII::CleanupInfo<unsigned short *>::Release(&v28);
      }
    }
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v10,
      "PushButtonReset::XmlNode::SelectNodes",
      "base\\reset\\util\\src\\xml.cpp",
      993,
      L"Failed to run query [%s]",
      v4);
    v26[0] = &RAII::CAutoRelease<IXMLDOMNodeList *>::`vftable';
    RAII::CAutoRelease<IXMLDOMParseError *>::Release(v26);
    v27 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
    RAII::CleanupInfo<unsigned short *>::Release(&v28);
  }
LABEL_25:
  ATL::CStringData::Release((ATL::CStringData *)(v4 - 12));
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18005aed4  mov     rax, rsp
0x18005aed7  mov     [rax+18h], r8
0x18005aedb  mov     [rax+10h], rdx
0x18005aedf  mov     [rax+20h], r9
0x18005aee3  push    rbp
0x18005aee4  push    rbx
0x18005aee5  push    rsi
0x18005aee6  push    rdi
0x18005aee7  push    r12
0x18005aee9  push    r13
0x18005aeeb  push    r14
0x18005aeed  push    r15
0x18005aeef  lea     rbp, [rax-5Fh]
0x18005aef3  sub     rsp, 0A8h
0x18005aefa  mov     r13, rcx
0x18005aefd  xor     r15d, r15d
0x18005af00  mov     [rbp+57h+psz], r15
0x18005af04  lea     rbx, [rbp+57h+arg_18]
0x18005af08  lea     rcx, [rbp+57h+psz]
0x18005af0c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18005af11  nop
0x18005af12  mov     r8, rbx
0x18005af15  mov     rdx, [rbp+57h+arg_10]
0x18005af19  lea     rcx, [rbp+57h+psz]
0x18005af1d  call    ?FormatV@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGPEAD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::FormatV(ushort const *,char *)
0x18005af22  mov     rbx, [rbp+57h+psz]
0x18005af26  mov     rcx, rbx; psz
0x18005af29  call    cs:__imp_SysAllocString
0x18005af2f  lea     r12, ??_7?$CAutoCleanup@PEAG@RAII@@6B@; const RAII::CAutoCleanup<ushort *>::`vftable'
0x18005af36  mov     [rbp+57h+var_80], r12
0x18005af3a  mov     [rbp+57h+var_78], rax
0x18005af3e  lea     rcx, [rbp+57h+var_80]
0x18005af42  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18005af47  cmp     [rax], r15
0x18005af4a  jnz     short loc_18005AF90
0x18005af4c  lea     rax, aFailedToAlloca_34; "Failed to allocate bstrXPath"
0x18005af53  mov     [rsp+0E0h+var_B8], rax
0x18005af58  mov     dword ptr [rsp+0E0h+var_C0], 3DDh
0x18005af60  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005af67  lea     r8, aPushbuttonrese_100; "PushButtonReset::XmlNode::SelectNodes"
0x18005af6e  mov     edx, 8007000Eh
0x18005af73  lea     ecx, [r15+2]
0x18005af77  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005af7c  nop
0x18005af7d  mov     [rbp+57h+var_80], r12
0x18005af81  lea     rcx, [rbp+57h+var_78]
0x18005af85  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005af8a  nop
0x18005af8b  jmp     loc_18005B11A
0x18005af90  mov     [rbp+57h+var_88], r15
0x18005af94  lea     rax, ??_7?$CAutoRelease@PEAUIXMLDOMNodeList@@@RAII@@6B@; const RAII::CAutoRelease<IXMLDOMNodeList *>::`vftable'
0x18005af9b  mov     [rbp+57h+var_90], rax
0x18005af9f  lea     rcx, [r13+8]
0x18005afa3  mov     rax, [rcx]
0x18005afa6  mov     rax, [rax+18h]
0x18005afaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005afaf  mov     r14, rax
0x18005afb2  mov     rcx, [rax]
0x18005afb5  mov     rsi, [rcx+120h]
0x18005afbc  mov     rcx, [rbp+57h+var_90]
0x18005afc0  mov     rax, [rcx+8]
0x18005afc4  lea     rcx, [rbp+57h+var_90]
0x18005afc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005afcd  mov     rdi, rax
0x18005afd0  mov     rcx, [rbp+57h+var_80]
0x18005afd4  mov     rax, [rcx+20h]
0x18005afd8  lea     rcx, [rbp+57h+var_80]
0x18005afdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005afe1  mov     r8, rdi
0x18005afe4  mov     rdx, [rax]
0x18005afe7  mov     rcx, r14
0x18005afea  mov     rax, rsi
0x18005afed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aff2  mov     edi, eax
0x18005aff4  test    eax, eax
0x18005aff6  jns     short loc_18005B054
0x18005aff8  mov     [rsp+0E0h+var_B0], rbx
0x18005affd  lea     rax, aFailedToRunQue; "Failed to run query [%s]"
0x18005b004  mov     [rsp+0E0h+var_B8], rax
0x18005b009  mov     dword ptr [rsp+0E0h+var_C0], 3E1h
0x18005b011  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005b018  lea     r8, aPushbuttonrese_100; "PushButtonReset::XmlNode::SelectNodes"
0x18005b01f  mov     edx, edi
0x18005b021  mov     ecx, 2
0x18005b026  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005b02b  nop
0x18005b02c  lea     rax, ??_7?$CAutoRelease@PEAUIXMLDOMNodeList@@@RAII@@6B@; const RAII::CAutoRelease<IXMLDOMNodeList *>::`vftable'
0x18005b033  mov     [rbp+57h+var_90], rax
0x18005b037  lea     rcx, [rbp+57h+var_90]
0x18005b03b  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005b040  nop
0x18005b041  mov     [rbp+57h+var_80], r12
0x18005b045  lea     rcx, [rbp+57h+var_78]
0x18005b049  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005b04e  nop
0x18005b04f  jmp     loc_18005B4F2
0x18005b054  mov     rax, [rbp+57h+var_90]
0x18005b058  lea     rcx, [rbp+57h+var_90]
0x18005b05c  mov     rax, [rax+48h]
0x18005b060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b065  test    al, al
0x18005b067  jz      short loc_18005B096
0x18005b069  lea     rax, ??_7?$CAutoRelease@PEAUIXMLDOMNodeList@@@RAII@@6B@; const RAII::CAutoRelease<IXMLDOMNodeList *>::`vftable'
0x18005b070  mov     [rbp+57h+var_90], rax
0x18005b074  lea     rcx, [rbp+57h+var_90]
0x18005b078  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005b07d  nop
0x18005b07e  mov     [rbp+57h+var_80], r12
0x18005b082  lea     rcx, [rbp+57h+var_78]
0x18005b086  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005b08b  nop
0x18005b08c  mov     edi, 80070490h
0x18005b091  jmp     loc_18005B4F2
0x18005b096  call    ??$PbrNew@VXmlNodeList@PushButtonReset@@$$V@@YAPEAVXmlNodeList@PushButtonReset@@XZ; PbrNew<PushButtonReset::XmlNodeList,>(void)
0x18005b09b  mov     [rbp+57h+var_68], rax
0x18005b09f  lea     rsi, ??_7?$CAutoPbrDelete@PEAVXmlNodeList@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::XmlNodeList *>::`vftable'
0x18005b0a6  mov     [rbp+57h+var_70], rsi
0x18005b0aa  lea     rcx, [rbp+57h+var_70]
0x18005b0ae  call    ??7?$CAutoCleanupBase@PEAUISetupOneSettings@@@RAII@@UEBA_NXZ; RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(void)
0x18005b0b3  test    al, al
0x18005b0b5  jz      short loc_18005B124
0x18005b0b7  lea     rax, aFailedToAlloca_16; "Failed to allocate xnodes"
0x18005b0be  mov     [rsp+0E0h+var_B8], rax
0x18005b0c3  mov     dword ptr [rsp+0E0h+var_C0], 3E9h
0x18005b0cb  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005b0d2  lea     r8, aPushbuttonrese_100; "PushButtonReset::XmlNode::SelectNodes"
0x18005b0d9  mov     edx, 8007000Eh
0x18005b0de  mov     ecx, 2
0x18005b0e3  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005b0e8  nop
0x18005b0e9  mov     [rbp+57h+var_70], rsi
0x18005b0ed  lea     rcx, [rbp+57h+var_70]
0x18005b0f1  call    ?Release@?$CAutoPbrDelete@PEAVXmlNodeList@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::XmlNodeList *>::Release(void)
0x18005b0f6  nop
0x18005b0f7  lea     rax, ??_7?$CAutoRelease@PEAUIXMLDOMNodeList@@@RAII@@6B@; const RAII::CAutoRelease<IXMLDOMNodeList *>::`vftable'
0x18005b0fe  mov     [rbp+57h+var_90], rax
0x18005b102  lea     rcx, [rbp+57h+var_90]
0x18005b106  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005b10b  nop
0x18005b10c  mov     [rbp+57h+var_80], r12
0x18005b110  lea     rcx, [rbp+57h+var_78]
0x18005b114  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005b119  nop
0x18005b11a  mov     edi, 8007000Eh
0x18005b11f  jmp     loc_18005B4F2
0x18005b124  mov     [rbp+57h+var_A0], r15d
0x18005b128  mov     rax, [rbp+57h+var_90]
0x18005b12c  lea     rcx, [rbp+57h+var_90]
0x18005b130  mov     rax, [rax+18h]
0x18005b134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b139  mov     r8, rax
0x18005b13c  mov     rcx, [rax]
0x18005b13f  mov     rax, [rcx+40h]
0x18005b143  lea     rdx, [rbp+57h+var_A0]
0x18005b147  mov     rcx, r8
0x18005b14a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b14f  mov     edi, eax
0x18005b151  test    eax, eax
0x18005b153  jns     short loc_18005B1BA
0x18005b155  lea     rax, pszFormat
0x18005b15c  mov     [rsp+0E0h+var_B8], rax
0x18005b161  mov     dword ptr [rsp+0E0h+var_C0], 3EDh
0x18005b169  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005b170  lea     r8, aPushbuttonrese_100; "PushButtonReset::XmlNode::SelectNodes"
0x18005b177  mov     edx, edi
0x18005b179  mov     ecx, 2
0x18005b17e  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005b183  nop
0x18005b184  mov     [rbp+57h+var_70], rsi
0x18005b188  lea     rcx, [rbp+57h+var_70]
0x18005b18c  call    ?Release@?$CAutoPbrDelete@PEAVXmlNodeList@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::XmlNodeList *>::Release(void)
0x18005b191  nop
0x18005b192  lea     rax, ??_7?$CAutoRelease@PEAUIXMLDOMNodeList@@@RAII@@6B@; const RAII::CAutoRelease<IXMLDOMNodeList *>::`vftable'
0x18005b199  mov     [rbp+57h+var_90], rax
0x18005b19d  lea     rcx, [rbp+57h+var_90]
0x18005b1a1  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005b1a6  nop
0x18005b1a7  mov     [rbp+57h+var_80], r12
0x18005b1ab  lea     rcx, [rbp+57h+var_78]
0x18005b1af  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005b1b4  nop
0x18005b1b5  jmp     loc_18005B4F2
0x18005b1ba  mov     r14d, r15d
0x18005b1bd  lea     r12, ??_7?$CAutoRelease@PEAUIXMLDOMNode@@@RAII@@6B@; const RAII::CAutoRelease<IXMLDOMNode *>::`vftable'
0x18005b1c4  cmp     r14d, [rbp+57h+var_A0]
0x18005b1c8  jge     loc_18005B4A4
0x18005b1ce  mov     [rbp+57h+var_58], r15
0x18005b1d2  mov     [rbp+57h+var_60], r12
0x18005b1d6  mov     rax, [rbp+57h+var_90]
0x18005b1da  lea     rcx, [rbp+57h+var_90]
0x18005b1de  mov     rax, [rax+18h]
0x18005b1e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b1e7  mov     rsi, rax
0x18005b1ea  mov     rcx, [rax]
0x18005b1ed  mov     rdi, [rcx+38h]
0x18005b1f1  mov     rcx, [rbp+57h+var_60]
0x18005b1f5  mov     rax, [rcx+8]
0x18005b1f9  lea     rcx, [rbp+57h+var_60]
0x18005b1fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b202  mov     r8, rax
0x18005b205  mov     edx, r14d
0x18005b208  mov     rcx, rsi
0x18005b20b  mov     rax, rdi
0x18005b20e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b213  mov     edi, eax
0x18005b215  test    eax, eax
0x18005b217  js      loc_18005B41C
0x18005b21d  mov     rcx, r13
0x18005b220  call    ??$PbrNew@VXmlNode@PushButtonReset@@AEAPEAVXmlDocument@2@@@YAPEAVXmlNode@PushButtonReset@@AEAPEAVXmlDocument@1@@Z; PbrNew<PushButtonReset::XmlNode,PushButtonReset::XmlDocument * &>(PushButtonReset::XmlDocument * &)
0x18005b225  mov     [rbp+57h+var_48], rax
0x18005b229  lea     rsi, ??_7?$CAutoPbrDelete@PEAVXmlNode@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::XmlNode *>::`vftable'
0x18005b230  mov     [rbp+57h+var_50], rsi
0x18005b234  lea     rcx, [rbp+57h+var_50]
0x18005b238  call    ??7?$CAutoCleanupBase@PEAUISetupOneSettings@@@RAII@@UEBA_NXZ; RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(void)
0x18005b23d  test    al, al
0x18005b23f  jnz     loc_18005B38A
0x18005b245  mov     rax, [rbp+57h+var_50]
0x18005b249  lea     rcx, [rbp+57h+var_50]
0x18005b24d  mov     rax, [rax+18h]
0x18005b251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b256  mov     rdx, [rbp+57h+var_58]; struct IXMLDOMNode *
0x18005b25a  mov     [rbp+57h+var_58], r15
0x18005b25e  mov     rcx, rax; this
0x18005b261  call    ?Initialize@XmlNode@PushButtonReset@@AEAAJPEAUIXMLDOMNode@@@Z; PushButtonReset::XmlNode::Initialize(IXMLDOMNode *)
0x18005b266  mov     edi, eax
0x18005b268  test    eax, eax
0x18005b26a  js      loc_18005B2F1
0x18005b270  mov     rax, [rbp+57h+var_70]
0x18005b274  lea     rcx, [rbp+57h+var_70]
0x18005b278  mov     rax, [rax+18h]
0x18005b27c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b281  mov     rsi, rax
0x18005b284  mov     r12, [rbp+57h+var_48]
0x18005b288  mov     [rbp+57h+var_48], r15
0x18005b28c  mov     r15, [rax+8]
0x18005b290  cmp     r15, [rax+10h]
0x18005b294  jb      short loc_18005B2A6
0x18005b296  lea     rdx, [r15+1]
0x18005b29a  mov     rcx, rax
0x18005b29d  call    ?GrowBuffer@?$CAtlArray@PEAUPACKAGE_INFO@WinREAgent@@V?$CElementTraits@PEAUPACKAGE_INFO@WinREAgent@@@ATL@@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::GrowBuffer(unsigned __int64)
0x18005b2a2  test    al, al
0x18005b2a4  jz      short loc_18005B2E6
0x18005b2a6  mov     rax, [rsi]
0x18005b2a9  mov     [rax+r15*8], r12
0x18005b2ad  inc     qword ptr [rsi+8]
0x18005b2b1  lea     rax, ??_7?$CAutoPbrDelete@PEAVXmlNode@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::XmlNode *>::`vftable'
0x18005b2b8  mov     [rbp+57h+var_50], rax
0x18005b2bc  lea     rcx, [rbp+57h+var_50]
0x18005b2c0  call    ?Release@?$CAutoPbrDelete@PEAVXmlNode@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::XmlNode *>::Release(void)
0x18005b2c5  nop
0x18005b2c6  lea     r12, ??_7?$CAutoRelease@PEAUIXMLDOMNode@@@RAII@@6B@; const RAII::CAutoRelease<IXMLDOMNode *>::`vftable'
0x18005b2cd  mov     [rbp+57h+var_60], r12
0x18005b2d1  lea     rcx, [rbp+57h+var_60]
0x18005b2d5  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005b2da  nop
0x18005b2db  inc     r14d
0x18005b2de  xor     r15d, r15d
0x18005b2e1  jmp     loc_18005B1C4
0x18005b2e6  mov     ecx, 8007000Eh; int
0x18005b2eb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18005b2f1  mov     [rsp+38h], rbx
0x18005b2f6  mov     dword ptr [rsp+0E0h+var_B0], r14d
0x18005b2fb  lea     rax, aFailedToInitia_7; "Failed to initialize result %u for [%s]"
0x18005b302  mov     [rsp+0E0h+var_B8], rax
0x18005b307  mov     dword ptr [rsp+0E0h+var_C0], 3FDh
0x18005b30f  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005b316  lea     r8, aPushbuttonrese_100; "PushButtonReset::XmlNode::SelectNodes"
0x18005b31d  mov     edx, edi
0x18005b31f  mov     ecx, 2
0x18005b324  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005b329  nop
0x18005b32a  mov     [rbp+57h+var_50], rsi
0x18005b32e  lea     rcx, [rbp+57h+var_50]
0x18005b332  call    ?Release@?$CAutoPbrDelete@PEAVXmlNode@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::XmlNode *>::Release(void)
0x18005b337  nop
0x18005b338  mov     [rbp+57h+var_60], r12
0x18005b33c  lea     rcx, [rbp+57h+var_60]
0x18005b340  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005b345  nop
0x18005b346  lea     rax, ??_7?$CAutoPbrDelete@PEAVXmlNodeList@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::XmlNodeList *>::`vftable'
0x18005b34d  mov     [rbp+57h+var_70], rax
0x18005b351  lea     rcx, [rbp+57h+var_70]
0x18005b355  call    ?Release@?$CAutoPbrDelete@PEAVXmlNodeList@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::XmlNodeList *>::Release(void)
0x18005b35a  nop
0x18005b35b  lea     rax, ??_7?$CAutoRelease@PEAUIXMLDOMNodeList@@@RAII@@6B@; const RAII::CAutoRelease<IXMLDOMNodeList *>::`vftable'
0x18005b362  mov     [rbp+57h+var_90], rax
0x18005b366  lea     rcx, [rbp+57h+var_90]
0x18005b36a  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005b36f  nop
0x18005b370  lea     rax, ??_7?$CAutoCleanup@PEAG@RAII@@6B@; const RAII::CAutoCleanup<ushort *>::`vftable'
0x18005b377  mov     [rbp+57h+var_80], rax
0x18005b37b  lea     rcx, [rbp+57h+var_78]
0x18005b37f  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005b384  nop
0x18005b385  jmp     loc_18005B4F2
0x18005b38a  lea     rax, aFailedToAlloca_18; "Failed to allocate xnode"
0x18005b391  mov     [rsp+0E0h+var_B8], rax
0x18005b396  mov     dword ptr [rsp+0E0h+var_C0], 3F8h
0x18005b39e  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005b3a5  lea     r8, aPushbuttonrese_100; "PushButtonReset::XmlNode::SelectNodes"
  ... truncated ...
```
