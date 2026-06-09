# WaasMedic::CServiceHealthPlugin::MatchRegKeysFromXMLFile(ushort const *,bool &)

- ea: `0x18004bc00`
- end: `0x18004bed3`
- name: `?MatchRegKeysFromXMLFile@CServiceHealthPlugin@WaasMedic@@AEAAJPEBGAEA_N@Z`
- size: `723`
- prototype: `int(WaasMedic::CServiceHealthPlugin *__hidden this, const unsigned __int16 *, bool *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180002058`
- `0x180003bd4`
- `0x180003c18`
- `0x1800040b8`
- `0x180009a54`
- `0x180016c9c`
- `0x18002543c`
- `0x180034290`
- `0x180034930`
- `0x18004aed4`
- `0x18004bc00`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18004bdee`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18004bdee`

## string_xrefs

- `0x18004bcdc`: `onecore\enduser\waasmedic\lib\plugins\servicehealthplugin.cpp`
- `0x18004bd6f`: `onecore\enduser\waasmedic\lib\plugins\servicehealthplugin.cpp`
- `0x18004bcf7`: `Looking for registry information in file %ws`
- `0x18004bd44`: `Successfully gathered registry information for %ws`
- `0x18004bd1f`: `Failed to gather registry info from file [%ws] ErrorCode = 0x%08x`
- `0x18004bdbf`: `Registry info on the device does NOT match with Registry info in component XML for Registry [%ws]. ErrorCode = 0x%08x`
- `0x18004bda6`: `Registry info on the device matches XML for registry [%ws]`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WaasMedic::CServiceHealthPlugin::MatchRegKeysFromXMLFile(
        WaasMedic::CServiceHealthPlugin *this,
        const unsigned __int16 *a2,
        bool *a3)
{
  unsigned int v6; // ebx
  __int64 v7; // rdx
  WaasMedic::CRegKeyInformationFromXML *v8; // rax
  WaasMedic::CRegKeyInformationFromXML *v9; // rdi
  _QWORD *v10; // rax
  _QWORD *v11; // rax
  WaasMedic::CRegKeyInformationFromXML *v12; // rsi
  int v14; // eax
  WaasMedic::CRegKeyInformationFromXML *v15; // r14
  int matched; // eax
  unsigned int v17; // r15d
  __int64 v18; // rbx
  _QWORD *v19; // rax
  _QWORD *v20; // rcx
  const struct _tlgProvider_t *v21; // rax
  int v22; // r9d
  int v23; // [rsp+20h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  WaasMedic::CRegKeyInformationFromXML *v25; // [rsp+98h] [rbp+48h] BYREF
  unsigned __int16 *v26; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v27; // [rsp+A8h] [rbp+58h] BYREF

  v26 = 0;
  LOBYTE(v25) = 0;
  *a3 = 0;
  if ( !a2 )
  {
    v6 = -2147467261;
    v7 = 776;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\servicehealthplugin.cpp",
      (const char *)v6,
      v23);
    return v6;
  }
  v8 = (WaasMedic::CRegKeyInformationFromXML *)operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  v27 = (__int64)v8;
  if ( v8 )
  {
    *(_OWORD *)v8 = 0;
    *((_QWORD *)v8 + 2) = 0;
    *((_QWORD *)v8 + 3) = 7;
    *(_WORD *)v8 = 0;
    *((_OWORD *)v8 + 2) = 0;
    *((_QWORD *)v8 + 6) = 0;
    *((_QWORD *)v8 + 7) = 7;
    *((_WORD *)v8 + 16) = 0;
    *((_QWORD *)v8 + 8) = 0;
    *((_QWORD *)v8 + 9) = 0;
    v10 = operator new(0x18u);
    *v10 = v10;
    v10[1] = v10;
    *((_QWORD *)v9 + 8) = v10;
    *((_QWORD *)v9 + 10) = 0;
    *((_QWORD *)v9 + 11) = 0;
    v11 = operator new(0x18u);
    *v11 = v11;
    v11[1] = v11;
    *((_QWORD *)v9 + 10) = v11;
  }
  else
  {
    v9 = 0;
  }
  v12 = v9;
  v26 = (unsigned __int16 *)v9;
  if ( !v9 )
  {
    v6 = -2147024882;
    v7 = 779;
    goto LABEL_8;
  }
  LogLevelW(4u, L"Looking for registry information in file %ws", a2);
  v14 = WaasMedic::CRegKeyInformationFromXML::GatherRegKeyInfoFromXML(v9, a2);
  v6 = v14;
  if ( v14 < 0 )
  {
    LogLevelW(2u, L"Failed to gather registry info from file [%ws] ErrorCode = 0x%08x", a2, (unsigned int)v14);
LABEL_17:
    WaasMedic::CRegKeyInformationFromXML::~CRegKeyInformationFromXML(v9);
    operator delete(v9, (const struct std::nothrow_t *)0x60);
    return v6;
  }
  if ( *((_QWORD *)v9 + 3) <= 7u )
    v15 = v9;
  else
    v15 = *(WaasMedic::CRegKeyInformationFromXML **)v9;
  LogLevelW(4u, L"Successfully gathered registry information for %ws", v15);
  matched = WaasMedic::CRegKeyInformationFromXML::MatchRegKeyValues(v9, (bool *)&v25);
  v17 = matched;
  if ( matched < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31A,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\servicehealthplugin.cpp",
      (const char *)(unsigned int)matched,
      v23);
    v6 = v17;
    goto LABEL_17;
  }
  if ( (_BYTE)v25 )
  {
    LogLevelW(4u, L"Registry info on the device matches XML for registry [%ws]", v15);
  }
  else
  {
    LogLevelW(
      3u,
      L"Registry info on the device does NOT match with Registry info in component XML for Registry [%ws]. ErrorCode = 0x%08x",
      v15,
      v6);
    if ( *((_QWORD *)this + 34) == 0xAAAAAAAAAAAAAAALL )
      std::_Xlength_error("list too long");
    v18 = *((_QWORD *)this + 33);
    v19 = operator new(0x18u);
    v12 = 0;
    v19[2] = v9;
    ++*((_QWORD *)this + 34);
    v20 = *(_QWORD **)(v18 + 8);
    *v19 = v18;
    v19[1] = v20;
    *(_QWORD *)(v18 + 8) = v19;
    *v20 = v19;
    *a3 = 1;
    v21 = WaasMedic::TelemetryProvider::Provider();
    if ( *(_DWORD *)v21 > 5u
      && (*((_QWORD *)v21 + 2) & 0x400000000000LL) != 0
      && (*((_QWORD *)v21 + 3) & 0x400000000000LL) == *((_QWORD *)v21 + 3) )
    {
      v25 = v15;
      v26 = &gc_pszVersionString;
      v27 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v21,
        (unsigned int)&dword_18008A07C,
        0,
        v22,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&v25);
    }
  }
  if ( v12 )
  {
    WaasMedic::CRegKeyInformationFromXML::~CRegKeyInformationFromXML(v12);
    operator delete(v12, (const struct std::nothrow_t *)0x60);
  }
  return 0;
}

```

## disassembly

```asm
0x18004bc00  mov     [rsp-38h+arg_0], rbx
0x18004bc05  push    rbp
0x18004bc06  push    rsi
0x18004bc07  push    rdi
0x18004bc08  push    r12
0x18004bc0a  push    r13
0x18004bc0c  push    r14
0x18004bc0e  push    r15
0x18004bc10  mov     rbp, rsp
0x18004bc13  sub     rsp, 50h
0x18004bc17  mov     r12, r8
0x18004bc1a  mov     r14, rdx
0x18004bc1d  mov     r13, rcx
0x18004bc20  xor     r15d, r15d
0x18004bc23  mov     [rbp+arg_10], r15
0x18004bc27  mov     byte ptr [rbp+arg_8], r15b
0x18004bc2b  mov     [r8], r15b
0x18004bc2e  test    rdx, rdx
0x18004bc31  jnz     short loc_18004BC42
0x18004bc33  mov     ebx, 80004003h
0x18004bc38  mov     edx, 308h
0x18004bc3d  jmp     loc_18004BCD9
0x18004bc42  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004bc49  mov     ecx, 60h ; '`'; unsigned __int64
0x18004bc4e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004bc53  mov     rdi, rax
0x18004bc56  mov     [rbp+arg_18], rax
0x18004bc5a  mov     ecx, 7
0x18004bc5f  lea     ebx, [rcx+11h]
0x18004bc62  test    rax, rax
0x18004bc65  jz      short loc_18004BCC0
0x18004bc67  xorps   xmm0, xmm0
0x18004bc6a  movups  xmmword ptr [rax], xmm0
0x18004bc6d  mov     [rax+10h], r15
0x18004bc71  mov     [rax+18h], rcx
0x18004bc75  mov     [rax], r15w
0x18004bc79  movups  xmmword ptr [rax+20h], xmm0
0x18004bc7d  mov     [rax+30h], r15
0x18004bc81  mov     [rax+38h], rcx
0x18004bc85  mov     [rax+20h], r15w
0x18004bc8a  mov     [rax+40h], r15
0x18004bc8e  mov     [rax+48h], r15
0x18004bc92  mov     ecx, ebx; Size
0x18004bc94  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004bc99  mov     [rax], rax
0x18004bc9c  mov     [rax+8], rax
0x18004bca0  mov     [rdi+40h], rax
0x18004bca4  mov     [rdi+50h], r15
0x18004bca8  mov     [rdi+58h], r15
0x18004bcac  mov     ecx, ebx; Size
0x18004bcae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004bcb3  mov     [rax], rax
0x18004bcb6  mov     [rax+8], rax
0x18004bcba  mov     [rdi+50h], rax
0x18004bcbe  jmp     short loc_18004BCC3
0x18004bcc0  mov     rdi, r15
0x18004bcc3  mov     rsi, rdi
0x18004bcc6  mov     [rbp+arg_10], rdi
0x18004bcca  test    rdi, rdi
0x18004bccd  jnz     short loc_18004BCF4
0x18004bccf  mov     ebx, 8007000Eh
0x18004bcd4  mov     edx, 30Bh; void *
0x18004bcd9  mov     r9d, ebx; char *
0x18004bcdc  lea     r8, aOnecoreEnduser_40; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18004bce3  mov     rcx, [rbp+38h]; this
0x18004bce7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bcec  nop
0x18004bced  mov     eax, ebx
0x18004bcef  jmp     loc_18004BEBB
0x18004bcf4  mov     r8, r14
0x18004bcf7  lea     rdx, aLookingForRegi; "Looking for registry information in fil"...
0x18004bcfe  mov     ecx, 4; unsigned __int8
0x18004bd03  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004bd08  mov     rdx, r14; unsigned __int16 *
0x18004bd0b  mov     rcx, rdi; this
0x18004bd0e  call    ?GatherRegKeyInfoFromXML@CRegKeyInformationFromXML@WaasMedic@@QEAAJPEBG@Z; WaasMedic::CRegKeyInformationFromXML::GatherRegKeyInfoFromXML(ushort const *)
0x18004bd13  mov     ebx, eax
0x18004bd15  test    eax, eax
0x18004bd17  jns     short loc_18004BD32
0x18004bd19  mov     r9d, eax
0x18004bd1c  mov     r8, r14
0x18004bd1f  lea     rdx, aFailedToGather; "Failed to gather registry info from fil"...
0x18004bd26  mov     ecx, 2; unsigned __int8
0x18004bd2b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004bd30  jmp     short loc_18004BD83
0x18004bd32  cmp     qword ptr [rdi+18h], 7
0x18004bd37  jbe     short loc_18004BD3E
0x18004bd39  mov     r14, [rdi]
0x18004bd3c  jmp     short loc_18004BD41
0x18004bd3e  mov     r14, rdi
0x18004bd41  mov     r8, r14
0x18004bd44  lea     rdx, aSuccessfullyGa_1; "Successfully gathered registry informat"...
0x18004bd4b  mov     ecx, 4; unsigned __int8
0x18004bd50  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004bd55  lea     rdx, [rbp+arg_8]; bool *
0x18004bd59  mov     rcx, rdi; this
0x18004bd5c  call    ?MatchRegKeyValues@CRegKeyInformationFromXML@WaasMedic@@QEAAJPEA_N@Z; WaasMedic::CRegKeyInformationFromXML::MatchRegKeyValues(bool *)
0x18004bd61  mov     r15d, eax
0x18004bd64  test    eax, eax
0x18004bd66  jns     short loc_18004BD9D
0x18004bd68  mov     rcx, [rbp+38h]; this
0x18004bd6c  mov     r9d, eax; char *
0x18004bd6f  lea     r8, aOnecoreEnduser_40; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18004bd76  mov     edx, 31Ah; void *
0x18004bd7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bd80  mov     ebx, r15d
0x18004bd83  mov     rcx, rdi; this
0x18004bd86  call    ??1CRegKeyInformationFromXML@WaasMedic@@QEAA@XZ; WaasMedic::CRegKeyInformationFromXML::~CRegKeyInformationFromXML(void)
0x18004bd8b  mov     edx, 60h ; '`'; struct std::nothrow_t *
0x18004bd90  mov     rcx, rdi; void *
0x18004bd93  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004bd98  jmp     loc_18004BCED
0x18004bd9d  mov     r8, r14
0x18004bda0  cmp     byte ptr [rbp+arg_8], 0
0x18004bda4  jz      short loc_18004BDBC
0x18004bda6  lea     rdx, aRegistryInfoOn; "Registry info on the device matches XML"...
0x18004bdad  mov     ecx, 4; unsigned __int8
0x18004bdb2  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004bdb7  jmp     loc_18004BE9F
0x18004bdbc  mov     r9d, ebx
0x18004bdbf  lea     rdx, aRegistryInfoOn_0; "Registry info on the device does NOT ma"...
0x18004bdc6  mov     ecx, 3; unsigned __int8
0x18004bdcb  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004bdd0  lea     r15, [r13+108h]
0x18004bdd7  mov     rax, 0AAAAAAAAAAAAAAAh
0x18004bde1  cmp     [r15+8], rax
0x18004bde5  jnz     short loc_18004BDF5
0x18004bde7  lea     rcx, aListTooLong; "list too long"
0x18004bdee  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18004bdf5  mov     rbx, [r15]
0x18004bdf8  mov     [rbp+var_10], r15
0x18004bdfc  mov     [rbp+var_8], 0
0x18004be04  mov     ecx, 18h; Size
0x18004be09  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004be0e  xor     esi, esi
0x18004be10  mov     [rax+10h], rdi
0x18004be14  inc     qword ptr [r15+8]
0x18004be18  mov     rcx, [rbx+8]
0x18004be1c  mov     [rax], rbx
0x18004be1f  mov     [rax+8], rcx
0x18004be23  mov     [rbx+8], rax
0x18004be27  mov     [rcx], rax
0x18004be2a  mov     byte ptr [r12], 1
0x18004be2f  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x18004be34  mov     ecx, [rax]
0x18004be36  cmp     ecx, 5
0x18004be39  jbe     short loc_18004BE9F
0x18004be3b  mov     rdx, [rax+18h]
0x18004be3f  mov     rcx, [rax+10h]
0x18004be43  mov     r8, 400000000000h
0x18004be4d  test    r8, rcx
0x18004be50  jz      short loc_18004BE9F
0x18004be52  mov     rcx, rdx
0x18004be55  and     rcx, r8
0x18004be58  cmp     rcx, rdx
0x18004be5b  jnz     short loc_18004BE9F
0x18004be5d  mov     [rbp+arg_8], r14
0x18004be61  lea     rcx, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x18004be68  mov     [rbp+arg_10], rcx
0x18004be6c  mov     [rbp+arg_18], 1000000h
0x18004be74  lea     rcx, [rbp+arg_8]
0x18004be78  mov     [rsp+50h+var_20], rcx
0x18004be7d  lea     rcx, [rbp+arg_10]
0x18004be81  mov     [rsp+50h+var_28], rcx
0x18004be86  lea     rcx, [rbp+arg_18]
0x18004be8a  mov     [rsp+50h+var_30], rcx
0x18004be8f  lea     rdx, dword_18008A07C
0x18004be96  mov     rcx, rax
0x18004be99  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18004be9e  nop
0x18004be9f  test    rsi, rsi
0x18004bea2  jz      short loc_18004BEB9
0x18004bea4  mov     rcx, rsi; this
0x18004bea7  call    ??1CRegKeyInformationFromXML@WaasMedic@@QEAA@XZ; WaasMedic::CRegKeyInformationFromXML::~CRegKeyInformationFromXML(void)
0x18004beac  mov     edx, 60h ; '`'; struct std::nothrow_t *
0x18004beb1  mov     rcx, rsi; void *
0x18004beb4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004beb9  xor     eax, eax
0x18004bebb  mov     rbx, [rsp+50h+arg_0]
0x18004bec3  add     rsp, 50h
0x18004bec7  pop     r15
0x18004bec9  pop     r14
0x18004becb  pop     r13
0x18004becd  pop     r12
0x18004becf  pop     rdi
0x18004bed0  pop     rsi
0x18004bed1  pop     rbp
0x18004bed2  retn
```
