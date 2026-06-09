# Art::ReadStylesImpl<ODF::AutomaticStyles>(ISAXXMLReader &,ISAXAttributes *,Ofc::CXmlName &,Art::OdfStyleSet,Art::IOdfDocumentContext &,Mso::OpenXml::IPart *,Ofc::TOwningPtr<Art::IOdfReaderParams> &)

- ea: `0x1800ff990`
- end: `0x1800ffbfb`
- name: `??$ReadStylesImpl@VAutomaticStyles@ODF@@@Art@@YAXAEAUISAXXMLReader@@PEAUISAXAttributes@@AEAUCXmlName@Ofc@@W4OdfStyleSet@0@AEAVIOdfDocumentContext@0@PEAUIPart@OpenXml@Mso@@AEAV?$TOwningPtr@VIOdfReaderParams@Art@@@4@@Z`
- size: `619`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180109c30`

## callees

- `0x180004818`
- `0x1800048d4`
- `0x18000afd4`
- `0x180014b40`
- `0x1800ff990`
- `0x1801004a0`
- `0x180171a9c`
- `0x1801a80e0`

## import_xrefs

- `KERNEL32!EncodePointer` at `0x1800ffa63`
- `KERNEL32!EncodePointer` at `0x1800ffa63`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1800ffa88`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1800ffa88`
- `mso40uiWin32Client!__imp_?StrongMoveAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@0@Z` at `0x1800ffbcd`
- `mso40uiWin32Client!__imp_?StrongMoveAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@0@Z` at `0x1800ffbcd`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1800ffa92`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1800ffac8`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1800ffb3d`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1800ffa92`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1800ffac8`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1800ffb3d`
- `mso40uiWin32Client!__imp_??0CCompElemLoaderImpl@Ofc@@IEAA@II@Z` at `0x1800ffb88`
- `mso40uiWin32Client!__imp_??0CCompElemLoaderImpl@Ofc@@IEAA@II@Z` at `0x1800ffb88`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1800ffbd7`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1800ffbd7`
- `mso40uiWin32Client!__imp_?PushContextAndSubLoaderImpl@CSAXReader@Ofc@@AEAAXPEAXAEAVCElemLoader@2@AEBUCXmlName@2@PEAUISAXAttributes@@@Z` at `0x1800ffba9`
- `mso40uiWin32Client!__imp_?PushContextAndSubLoaderImpl@CSAXReader@Ofc@@AEAAXPEAXAEAVCElemLoader@2@AEBUCXmlName@2@PEAUISAXAttributes@@@Z` at `0x1800ffba9`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x1800ffa48`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x1800ffa48`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800ff9c9`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800ffa27`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800ffadf`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800ff9c9`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800ffa27`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800ffadf`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800ffb2c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800ffb2c`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x1800ff9d7`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x1800ffaed`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x1800ff9d7`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x1800ffaed`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall Art::ReadStylesImpl<ODF::AutomaticStyles>(
        int a1,
        struct ISAXAttributes *a2,
        const struct Ofc::CXmlName *a3,
        int a4,
        __int64 a5,
        int a6,
        struct Ofc::CProxyPtrImpl **a7)
{
  struct Ofc::CSAXReader *v11; // rax
  int v12; // ebx
  int v13; // eax
  __int64 v14; // rdi
  unsigned int v15; // r8d
  int *v16; // rax
  unsigned int v17; // edx
  int *v18; // rbx
  MsoReserveTag *v19; // rax
  unsigned int v20; // eax
  void *Checked; // rdi
  void (__fastcall *v22)(void *, __int64); // rbx
  __int64 v23; // rax
  void *v24; // rdi
  unsigned int v25; // r8d
  Mso::Memory *v26; // rsi
  Mso::Memory *v27; // rax
  Mso::Memory *v28; // rbx
  void *v29; // rdx
  struct Ofc::IReaderParams *v30; // rax
  struct Ofc::CSAXReader *SAXReader; // rax
  struct Ofc::CSAXReader *v32; // rbx
  Ofc::CCompElemLoaderImpl *v33; // rdi
  int v34; // [rsp+30h] [rbp-20h] BYREF
  struct Ofc::CProxyPtrImpl *v35; // [rsp+38h] [rbp-18h] BYREF
  struct Ofc::CProxyPtrImpl *v36; // [rsp+40h] [rbp-10h] BYREF
  struct Ofc::CSAXReader *v37; // [rsp+48h] [rbp-8h]

  v34 = 0;
  v11 = (struct Ofc::CSAXReader *)Mso::Memory::AllocateEx((Mso::Memory *)0x1C8, 0, (unsigned int)a3);
  v12 = (int)v11;
  if ( !v11 )
  {
    ThrowOOM();
    __debugbreak();
  }
  v37 = v11;
  v13 = (*(__int64 (__fastcall **)(__int64, struct Ofc::CProxyPtrImpl **))(*(_QWORD *)a5 + 280LL))(a5, &v36);
  v34 = 1;
  v14 = Art::OdfReaderParams<ODF::AutomaticStyles>::OdfReaderParams<ODF::AutomaticStyles>(v12, a1, a6, v13, a4);
  if ( v14 )
  {
    v16 = (int *)Mso::Memory::AllocateEx((Mso::Memory *)0x18, 0, v15);
    v18 = v16;
    if ( !v16 )
    {
      v19 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)&v34, v17);
      v20 = MsoReserveTag::operator unsigned int(v19);
      CrashWithRecoveryOnOOM(v20);
      __debugbreak();
    }
    *v16 = 1;
    v16[1] = 1;
    *((_QWORD *)v16 + 1) = EncodePointer(Ofc::TDeleteFromProxy<Art::OdfReaderParams<ODF::Path>>);
    *((_QWORD *)v18 + 2) = v14;
  }
  else
  {
    v18 = &`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
  }
  v35 = (struct Ofc::CProxyPtrImpl *)v18;
  Ofc::CProxyPtrImpl::DtorWeakRelease(&v36);
  Checked = Ofc::CProxyPtrImpl::GetChecked((Ofc::CProxyPtrImpl *)v18);
  v22 = *(void (__fastcall **)(void *, __int64))(*(_QWORD *)Checked + 24LL);
  v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a5 + 320LL))(a5);
  v22(Checked, v23);
  v24 = Ofc::CProxyPtrImpl::GetChecked(v35);
  v26 = (Mso::Memory *)*((_QWORD *)v24 + 1);
  if ( !v26 )
  {
    v27 = (Mso::Memory *)Mso::Memory::AllocateEx((Mso::Memory *)0x18, 0, v25);
    v28 = v27;
    if ( !v27 )
    {
      ThrowOOM();
      __debugbreak();
    }
    *(_QWORD *)v27 = 0;
    *((_QWORD *)v27 + 2) = 0;
    *((_QWORD *)v27 + 1) = 0;
    *((_DWORD *)v27 + 5) = 0x80000000;
    v26 = (Mso::Memory *)*((_QWORD *)v24 + 1);
    if ( v26 != v27 )
    {
      if ( v26 )
      {
        Ofc::TArray<ODF::NumListFormatData::NumListFormatContent_<0>>::~TArray<ODF::NumListFormatData::NumListFormatContent_<0>>((char *)v26 + 8);
        Mso::Memory::Free(v26, v29);
      }
      *((_QWORD *)v24 + 1) = v28;
      v26 = v28;
    }
  }
  v30 = (struct Ofc::IReaderParams *)Ofc::CProxyPtrImpl::GetChecked(v35);
  SAXReader = Art::OdfSaxReader::CreateSAXReader(v30, a2, a3);
  v32 = SAXReader;
  v37 = SAXReader;
  if ( SAXReader )
    (*(void (__fastcall **)(struct Ofc::CSAXReader *))(*(_QWORD *)SAXReader + 8LL))(SAXReader);
  v33 = (Ofc::CCompElemLoaderImpl *)Ofc::CPrivateHeap::SmallAlloc((struct Ofc::CSAXReader *)((char *)v32 + 40), 0x40u);
  Ofc::CCompElemLoaderImpl::CCompElemLoaderImpl(v33, 1u, 1u);
  *(_QWORD *)v33 = &Ofc::TCompElemLoader<ODF::AutomaticStyles,Ofc::TSelfAdapter<ODF::AutomaticStyles>,Ofc::TSelfAdapter<ODF::AutomaticStyles>>::`vftable';
  Ofc::CSAXReader::PushContextAndSubLoaderImpl(v32, v26, v33, a3, a2);
  if ( v32 )
    (*(void (__fastcall **)(struct Ofc::CSAXReader *))(*(_QWORD *)v32 + 16LL))(v32);
  Ofc::CProxyPtrImpl::StrongMoveAssign(a7, &v35);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v35);
}

```

## disassembly

```asm
0x1800ff990  mov     rax, rsp
0x1800ff993  mov     [rax+8], rbx
0x1800ff997  mov     [rax+10h], rsi
0x1800ff99b  mov     [rax+18h], rdi
0x1800ff99f  mov     [rax+20h], r12
0x1800ff9a3  push    rbp
0x1800ff9a4  push    r14
0x1800ff9a6  push    r15
0x1800ff9a8  mov     rbp, rsp
0x1800ff9ab  sub     rsp, 50h
0x1800ff9af  mov     edi, r9d
0x1800ff9b2  mov     r14, r8
0x1800ff9b5  mov     r15, rdx
0x1800ff9b8  mov     r12, rcx
0x1800ff9bb  mov     [rbp+var_20], 0
0x1800ff9c2  xor     edx, edx
0x1800ff9c4  mov     ecx, 1C8h
0x1800ff9c9  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x1800ff9cf  mov     rbx, rax
0x1800ff9d2  test    rax, rax
0x1800ff9d5  jnz     short loc_1800FF9DE
0x1800ff9d7  call    cs:__imp_?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x1800ff9dd  int     3; Trap to Debugger
0x1800ff9de  mov     [rbp+var_8], rbx
0x1800ff9e2  mov     rsi, [rbp+arg_20]
0x1800ff9e6  mov     rax, [rsi]
0x1800ff9e9  lea     rdx, [rbp+var_10]
0x1800ff9ed  mov     rcx, rsi
0x1800ff9f0  mov     rax, [rax+118h]
0x1800ff9f7  call    cs:__guard_dispatch_icall_fptr
0x1800ff9fd  mov     [rbp+var_20], 1
0x1800ffa04  mov     dword ptr [rsp+50h+var_30], edi
0x1800ffa08  mov     r9, rax
0x1800ffa0b  mov     r8, [rbp+arg_28]
0x1800ffa0f  mov     rdx, r12
0x1800ffa12  mov     rcx, rbx
0x1800ffa15  call    ??0?$OdfReaderParams@VAutomaticStyles@ODF@@@Art@@QEAA@AEAUISAXXMLReader@@AEAUIPart@OpenXml@Mso@@AEBV?$TWeakPtr@VIOdfDocumentContext@Art@@@Ofc@@W4OdfStyleSet@1@@Z; Art::OdfReaderParams<ODF::AutomaticStyles>::OdfReaderParams<ODF::AutomaticStyles>(ISAXXMLReader &,Mso::OpenXml::IPart &,Ofc::TWeakPtr<Art::IOdfDocumentContext> const &,Art::OdfStyleSet)
0x1800ffa1a  mov     rdi, rax
0x1800ffa1d  test    rax, rax
0x1800ffa20  jz      short loc_1800FFA73
0x1800ffa22  xor     edx, edx
0x1800ffa24  lea     ecx, [rdx+18h]
0x1800ffa27  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x1800ffa2d  mov     rbx, rax
0x1800ffa30  test    rax, rax
0x1800ffa33  jnz     short loc_1800FFA4F
0x1800ffa35  lea     rcx, [rbp+var_20]; this
0x1800ffa39  call    ??0MsoReserveTag@@QEAA@I@Z; MsoReserveTag::MsoReserveTag(uint)
0x1800ffa3e  mov     rcx, rax
0x1800ffa41  call    ??BMsoReserveTag@@QEBAIXZ; MsoReserveTag::operator uint(void)
0x1800ffa46  mov     ecx, eax
0x1800ffa48  call    cs:__imp_?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
0x1800ffa4e  int     3; Trap to Debugger
0x1800ffa4f  mov     r12d, 1
0x1800ffa55  mov     [rax], r12d
0x1800ffa58  mov     [rax+4], r12d
0x1800ffa5c  lea     rcx, ??$TDeleteFromProxy@V?$OdfReaderParams@VPath@ODF@@@Art@@@Ofc@@YAXPEAX@Z; Ptr
0x1800ffa63  call    cs:__imp_EncodePointer
0x1800ffa69  mov     [rbx+8], rax
0x1800ffa6d  mov     [rbx+10h], rdi
0x1800ffa71  jmp     short loc_1800FFA80
0x1800ffa73  lea     rbx, ?s_proxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4UProxyPtrSentinel@?1??123@KAAEBQEAV23@XZ@B; `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::ProxyPtrSentinel const `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_proxyPtrSentinel
0x1800ffa7a  mov     r12d, 1
0x1800ffa80  mov     [rbp+var_18], rbx
0x1800ffa84  lea     rcx, [rbp+var_10]
0x1800ffa88  call    cs:__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x1800ffa8e  mov     rcx, [rbp+var_18]
0x1800ffa92  call    cs:__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1800ffa98  mov     rdi, rax
0x1800ffa9b  mov     rdx, [rax]
0x1800ffa9e  mov     rbx, [rdx+18h]
0x1800ffaa2  mov     rdx, [rsi]
0x1800ffaa5  mov     rcx, rsi
0x1800ffaa8  mov     rax, [rdx+140h]
0x1800ffaaf  call    cs:__guard_dispatch_icall_fptr
0x1800ffab5  mov     rdx, rax
0x1800ffab8  mov     rcx, rdi
0x1800ffabb  mov     rax, rbx
0x1800ffabe  call    cs:__guard_dispatch_icall_fptr
0x1800ffac4  mov     rcx, [rbp+var_18]
0x1800ffac8  call    cs:__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1800fface  mov     rdi, rax
0x1800ffad1  mov     rsi, [rax+8]
0x1800ffad5  test    rsi, rsi
0x1800ffad8  jnz     short loc_1800FFB39
0x1800ffada  xor     edx, edx
0x1800ffadc  lea     ecx, [rsi+18h]
0x1800ffadf  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x1800ffae5  mov     rbx, rax
0x1800ffae8  test    rax, rax
0x1800ffaeb  jnz     short loc_1800FFAF4
0x1800ffaed  call    cs:__imp_?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x1800ffaf3  int     3; Trap to Debugger
0x1800ffaf4  mov     qword ptr [rax], 0
0x1800ffafb  mov     qword ptr [rax+10h], 0
0x1800ffb03  mov     qword ptr [rax+8], 0
0x1800ffb0b  mov     dword ptr [rax+14h], 80000000h
0x1800ffb12  mov     rsi, [rdi+8]
0x1800ffb16  cmp     rsi, rbx
0x1800ffb19  jz      short loc_1800FFB39
0x1800ffb1b  test    rsi, rsi
0x1800ffb1e  jz      short loc_1800FFB32
0x1800ffb20  lea     rcx, [rsi+8]
0x1800ffb24  call    ??1?$TArray@V?$NumListFormatContent_@$0A@@NumListFormatData@ODF@@@Ofc@@QEAA@XZ; Ofc::TArray<ODF::NumListFormatData::NumListFormatContent_<0>>::~TArray<ODF::NumListFormatData::NumListFormatContent_<0>>(void)
0x1800ffb29  mov     rcx, rsi
0x1800ffb2c  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800ffb32  mov     [rdi+8], rbx
0x1800ffb36  mov     rsi, rbx
0x1800ffb39  mov     rcx, [rbp+var_18]
0x1800ffb3d  call    cs:__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1800ffb43  mov     r8, r14; struct Ofc::CXmlName *
0x1800ffb46  mov     rdx, r15; struct ISAXAttributes *
0x1800ffb49  mov     rcx, rax; struct Ofc::IReaderParams *
0x1800ffb4c  call    ?CreateSAXReader@OdfSaxReader@Art@@SAPEAVCSAXReader@Ofc@@AEAVIReaderParams@4@PEAUISAXAttributes@@AEBUCXmlName@4@@Z; Art::OdfSaxReader::CreateSAXReader(Ofc::IReaderParams &,ISAXAttributes *,Ofc::CXmlName const &)
0x1800ffb51  mov     rbx, rax
0x1800ffb54  mov     [rbp+var_8], rax
0x1800ffb58  test    rax, rax
0x1800ffb5b  jz      short loc_1800FFB6E
0x1800ffb5d  mov     rax, [rax]
0x1800ffb60  mov     rcx, rbx
0x1800ffb63  mov     rax, [rax+8]
0x1800ffb67  call    cs:__guard_dispatch_icall_fptr
0x1800ffb6d  nop
0x1800ffb6e  lea     rcx, [rbx+28h]; this
0x1800ffb72  mov     edx, 40h ; '@'; unsigned __int64
0x1800ffb77  call    ?SmallAlloc@CPrivateHeap@Ofc@@QEAAPEAX_K@Z; Ofc::CPrivateHeap::SmallAlloc(unsigned __int64)
0x1800ffb7c  mov     rdi, rax
0x1800ffb7f  mov     r8d, r12d
0x1800ffb82  mov     edx, r12d
0x1800ffb85  mov     rcx, rax
0x1800ffb88  call    cs:__imp_??0CCompElemLoaderImpl@Ofc@@IEAA@II@Z; Ofc::CCompElemLoaderImpl::CCompElemLoaderImpl(uint,uint)
0x1800ffb8e  lea     rax, ??_7?$TCompElemLoader@VAutomaticStyles@ODF@@V?$TSelfAdapter@VAutomaticStyles@ODF@@@Ofc@@V34@@Ofc@@6B@; const Ofc::TCompElemLoader<ODF::AutomaticStyles,Ofc::TSelfAdapter<ODF::AutomaticStyles>,Ofc::TSelfAdapter<ODF::AutomaticStyles>>::`vftable'
0x1800ffb95  mov     [rdi], rax
0x1800ffb98  mov     [rsp+50h+var_30], r15
0x1800ffb9d  mov     r9, r14
0x1800ffba0  mov     r8, rdi
0x1800ffba3  mov     rdx, rsi
0x1800ffba6  mov     rcx, rbx
0x1800ffba9  call    cs:__imp_?PushContextAndSubLoaderImpl@CSAXReader@Ofc@@AEAAXPEAXAEAVCElemLoader@2@AEBUCXmlName@2@PEAUISAXAttributes@@@Z; Ofc::CSAXReader::PushContextAndSubLoaderImpl(void *,Ofc::CElemLoader &,Ofc::CXmlName const &,ISAXAttributes *)
0x1800ffbaf  nop
0x1800ffbb0  test    rbx, rbx
0x1800ffbb3  jz      short loc_1800FFBC5
0x1800ffbb5  mov     rax, [rbx]
0x1800ffbb8  mov     rcx, rbx
0x1800ffbbb  mov     rax, [rax+10h]
0x1800ffbbf  call    cs:__guard_dispatch_icall_fptr
0x1800ffbc5  lea     rdx, [rbp+var_18]
0x1800ffbc9  mov     rcx, [rbp+arg_30]
0x1800ffbcd  call    cs:__imp_?StrongMoveAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@0@Z; Ofc::CProxyPtrImpl::StrongMoveAssign(Ofc::CProxyPtrImpl * *,Ofc::CProxyPtrImpl * *)
0x1800ffbd3  lea     rcx, [rbp+var_18]
0x1800ffbd7  call    cs:__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1800ffbdd  lea     r11, [rsp+50h+var_s0]
0x1800ffbe2  mov     rbx, [r11+20h]
0x1800ffbe6  mov     rsi, [r11+28h]
0x1800ffbea  mov     rdi, [r11+30h]
0x1800ffbee  mov     r12, [r11+38h]
0x1800ffbf2  mov     rsp, r11
0x1800ffbf5  pop     r15
0x1800ffbf7  pop     r14
0x1800ffbf9  pop     rbp
0x1800ffbfa  retn
```
