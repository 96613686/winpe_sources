# Art::ReadStylesImpl<ODF::FontFaceDecls>(ISAXXMLReader &,ISAXAttributes *,Ofc::CXmlName &,Art::OdfStyleSet,Art::IOdfDocumentContext &,Mso::OpenXml::IPart *,Ofc::TOwningPtr<Art::IOdfReaderParams> &)

- ea: `0x1800ffc00`
- end: `0x1800ffe6b`
- name: `??$ReadStylesImpl@VFontFaceDecls@ODF@@@Art@@YAXAEAUISAXXMLReader@@PEAUISAXAttributes@@AEAUCXmlName@Ofc@@W4OdfStyleSet@0@AEAVIOdfDocumentContext@0@PEAUIPart@OpenXml@Mso@@AEAV?$TOwningPtr@VIOdfReaderParams@Art@@@4@@Z`
- size: `619`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180109c80`

## callees

- `0x180004818`
- `0x1800048d4`
- `0x18000afd4`
- `0x180072c20`
- `0x1800ffc00`
- `0x1801005e0`
- `0x180171a9c`
- `0x1801a80e0`

## import_xrefs

- `KERNEL32!EncodePointer` at `0x1800ffcd3`
- `KERNEL32!EncodePointer` at `0x1800ffcd3`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1800ffcf8`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1800ffcf8`
- `mso40uiWin32Client!__imp_?StrongMoveAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@0@Z` at `0x1800ffe3d`
- `mso40uiWin32Client!__imp_?StrongMoveAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@0@Z` at `0x1800ffe3d`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1800ffd02`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1800ffd38`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1800ffdac`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1800ffd02`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1800ffd38`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1800ffdac`
- `mso40uiWin32Client!__imp_??0CCompElemLoaderImpl@Ofc@@IEAA@II@Z` at `0x1800ffdf7`
- `mso40uiWin32Client!__imp_??0CCompElemLoaderImpl@Ofc@@IEAA@II@Z` at `0x1800ffdf7`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1800ffe47`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1800ffe47`
- `mso40uiWin32Client!__imp_?PushContextAndSubLoaderImpl@CSAXReader@Ofc@@AEAAXPEAXAEAVCElemLoader@2@AEBUCXmlName@2@PEAUISAXAttributes@@@Z` at `0x1800ffe18`
- `mso40uiWin32Client!__imp_?PushContextAndSubLoaderImpl@CSAXReader@Ofc@@AEAAXPEAXAEAVCElemLoader@2@AEBUCXmlName@2@PEAUISAXAttributes@@@Z` at `0x1800ffe18`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x1800ffcb8`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x1800ffcb8`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800ffc39`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800ffc97`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800ffd4f`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800ffc39`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800ffc97`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800ffd4f`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800ffd9b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800ffd9b`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x1800ffc47`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x1800ffd5d`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x1800ffc47`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x1800ffd5d`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall Art::ReadStylesImpl<ODF::FontFaceDecls>(
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
  v14 = Art::OdfReaderParams<ODF::FontFaceDecls>::OdfReaderParams<ODF::FontFaceDecls>(v12, a1, a6, v13, a4);
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
        ODF::FontFaceDeclsData::~FontFaceDeclsData(*((ODF::FontFaceDeclsData **)v24 + 1));
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
  *(_QWORD *)v33 = &Ofc::TCompElemLoader<ODF::FontFaceDecls,Ofc::TSelfAdapter<ODF::FontFaceDecls>,Ofc::TSelfAdapter<ODF::FontFaceDecls>>::`vftable';
  Ofc::CSAXReader::PushContextAndSubLoaderImpl(v32, v26, v33, a3, a2);
  if ( v32 )
    (*(void (__fastcall **)(struct Ofc::CSAXReader *))(*(_QWORD *)v32 + 16LL))(v32);
  Ofc::CProxyPtrImpl::StrongMoveAssign(a7, &v35);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v35);
}

```

## disassembly

```asm
0x1800ffc00  mov     rax, rsp
0x1800ffc03  mov     [rax+8], rbx
0x1800ffc07  mov     [rax+10h], rsi
0x1800ffc0b  mov     [rax+18h], rdi
0x1800ffc0f  mov     [rax+20h], r12
0x1800ffc13  push    rbp
0x1800ffc14  push    r14
0x1800ffc16  push    r15
0x1800ffc18  mov     rbp, rsp
0x1800ffc1b  sub     rsp, 50h
0x1800ffc1f  mov     edi, r9d
0x1800ffc22  mov     r14, r8
0x1800ffc25  mov     r15, rdx
0x1800ffc28  mov     r12, rcx
0x1800ffc2b  mov     [rbp+var_20], 0
0x1800ffc32  xor     edx, edx
0x1800ffc34  mov     ecx, 1C8h
0x1800ffc39  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x1800ffc3f  mov     rbx, rax
0x1800ffc42  test    rax, rax
0x1800ffc45  jnz     short loc_1800FFC4E
0x1800ffc47  call    cs:__imp_?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x1800ffc4d  int     3; Trap to Debugger
0x1800ffc4e  mov     [rbp+var_8], rbx
0x1800ffc52  mov     rsi, [rbp+arg_20]
0x1800ffc56  mov     rax, [rsi]
0x1800ffc59  lea     rdx, [rbp+var_10]
0x1800ffc5d  mov     rcx, rsi
0x1800ffc60  mov     rax, [rax+118h]
0x1800ffc67  call    cs:__guard_dispatch_icall_fptr
0x1800ffc6d  mov     [rbp+var_20], 1
0x1800ffc74  mov     dword ptr [rsp+50h+var_30], edi
0x1800ffc78  mov     r9, rax
0x1800ffc7b  mov     r8, [rbp+arg_28]
0x1800ffc7f  mov     rdx, r12
0x1800ffc82  mov     rcx, rbx
0x1800ffc85  call    ??0?$OdfReaderParams@VFontFaceDecls@ODF@@@Art@@QEAA@AEAUISAXXMLReader@@AEAUIPart@OpenXml@Mso@@AEBV?$TWeakPtr@VIOdfDocumentContext@Art@@@Ofc@@W4OdfStyleSet@1@@Z; Art::OdfReaderParams<ODF::FontFaceDecls>::OdfReaderParams<ODF::FontFaceDecls>(ISAXXMLReader &,Mso::OpenXml::IPart &,Ofc::TWeakPtr<Art::IOdfDocumentContext> const &,Art::OdfStyleSet)
0x1800ffc8a  mov     rdi, rax
0x1800ffc8d  test    rax, rax
0x1800ffc90  jz      short loc_1800FFCE3
0x1800ffc92  xor     edx, edx
0x1800ffc94  lea     ecx, [rdx+18h]
0x1800ffc97  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x1800ffc9d  mov     rbx, rax
0x1800ffca0  test    rax, rax
0x1800ffca3  jnz     short loc_1800FFCBF
0x1800ffca5  lea     rcx, [rbp+var_20]; this
0x1800ffca9  call    ??0MsoReserveTag@@QEAA@I@Z; MsoReserveTag::MsoReserveTag(uint)
0x1800ffcae  mov     rcx, rax
0x1800ffcb1  call    ??BMsoReserveTag@@QEBAIXZ; MsoReserveTag::operator uint(void)
0x1800ffcb6  mov     ecx, eax
0x1800ffcb8  call    cs:__imp_?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
0x1800ffcbe  int     3; Trap to Debugger
0x1800ffcbf  mov     r12d, 1
0x1800ffcc5  mov     [rax], r12d
0x1800ffcc8  mov     [rax+4], r12d
0x1800ffccc  lea     rcx, ??$TDeleteFromProxy@V?$OdfReaderParams@VPath@ODF@@@Art@@@Ofc@@YAXPEAX@Z; Ptr
0x1800ffcd3  call    cs:__imp_EncodePointer
0x1800ffcd9  mov     [rbx+8], rax
0x1800ffcdd  mov     [rbx+10h], rdi
0x1800ffce1  jmp     short loc_1800FFCF0
0x1800ffce3  lea     rbx, ?s_proxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4UProxyPtrSentinel@?1??123@KAAEBQEAV23@XZ@B; `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::ProxyPtrSentinel const `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_proxyPtrSentinel
0x1800ffcea  mov     r12d, 1
0x1800ffcf0  mov     [rbp+var_18], rbx
0x1800ffcf4  lea     rcx, [rbp+var_10]
0x1800ffcf8  call    cs:__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x1800ffcfe  mov     rcx, [rbp+var_18]
0x1800ffd02  call    cs:__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1800ffd08  mov     rdi, rax
0x1800ffd0b  mov     rdx, [rax]
0x1800ffd0e  mov     rbx, [rdx+18h]
0x1800ffd12  mov     rdx, [rsi]
0x1800ffd15  mov     rcx, rsi
0x1800ffd18  mov     rax, [rdx+140h]
0x1800ffd1f  call    cs:__guard_dispatch_icall_fptr
0x1800ffd25  mov     rdx, rax
0x1800ffd28  mov     rcx, rdi
0x1800ffd2b  mov     rax, rbx
0x1800ffd2e  call    cs:__guard_dispatch_icall_fptr
0x1800ffd34  mov     rcx, [rbp+var_18]
0x1800ffd38  call    cs:__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1800ffd3e  mov     rdi, rax
0x1800ffd41  mov     rsi, [rax+8]
0x1800ffd45  test    rsi, rsi
0x1800ffd48  jnz     short loc_1800FFDA8
0x1800ffd4a  xor     edx, edx
0x1800ffd4c  lea     ecx, [rsi+18h]
0x1800ffd4f  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x1800ffd55  mov     rbx, rax
0x1800ffd58  test    rax, rax
0x1800ffd5b  jnz     short loc_1800FFD64
0x1800ffd5d  call    cs:__imp_?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x1800ffd63  int     3; Trap to Debugger
0x1800ffd64  mov     qword ptr [rax], 0
0x1800ffd6b  mov     qword ptr [rax+10h], 0
0x1800ffd73  mov     qword ptr [rax+8], 0
0x1800ffd7b  mov     dword ptr [rax+14h], 80000000h
0x1800ffd82  mov     rsi, [rdi+8]
0x1800ffd86  cmp     rsi, rbx
0x1800ffd89  jz      short loc_1800FFDA8
0x1800ffd8b  test    rsi, rsi
0x1800ffd8e  jz      short loc_1800FFDA1
0x1800ffd90  mov     rcx, rsi; this
0x1800ffd93  call    ??1FontFaceDeclsData@ODF@@QEAA@XZ; ODF::FontFaceDeclsData::~FontFaceDeclsData(void)
0x1800ffd98  mov     rcx, rsi
0x1800ffd9b  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800ffda1  mov     [rdi+8], rbx
0x1800ffda5  mov     rsi, rbx
0x1800ffda8  mov     rcx, [rbp+var_18]
0x1800ffdac  call    cs:__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1800ffdb2  mov     r8, r14; struct Ofc::CXmlName *
0x1800ffdb5  mov     rdx, r15; struct ISAXAttributes *
0x1800ffdb8  mov     rcx, rax; struct Ofc::IReaderParams *
0x1800ffdbb  call    ?CreateSAXReader@OdfSaxReader@Art@@SAPEAVCSAXReader@Ofc@@AEAVIReaderParams@4@PEAUISAXAttributes@@AEBUCXmlName@4@@Z; Art::OdfSaxReader::CreateSAXReader(Ofc::IReaderParams &,ISAXAttributes *,Ofc::CXmlName const &)
0x1800ffdc0  mov     rbx, rax
0x1800ffdc3  mov     [rbp+var_8], rax
0x1800ffdc7  test    rax, rax
0x1800ffdca  jz      short loc_1800FFDDD
0x1800ffdcc  mov     rax, [rax]
0x1800ffdcf  mov     rcx, rbx
0x1800ffdd2  mov     rax, [rax+8]
0x1800ffdd6  call    cs:__guard_dispatch_icall_fptr
0x1800ffddc  nop
0x1800ffddd  lea     rcx, [rbx+28h]; this
0x1800ffde1  mov     edx, 40h ; '@'; unsigned __int64
0x1800ffde6  call    ?SmallAlloc@CPrivateHeap@Ofc@@QEAAPEAX_K@Z; Ofc::CPrivateHeap::SmallAlloc(unsigned __int64)
0x1800ffdeb  mov     rdi, rax
0x1800ffdee  mov     r8d, r12d
0x1800ffdf1  mov     edx, r12d
0x1800ffdf4  mov     rcx, rax
0x1800ffdf7  call    cs:__imp_??0CCompElemLoaderImpl@Ofc@@IEAA@II@Z; Ofc::CCompElemLoaderImpl::CCompElemLoaderImpl(uint,uint)
0x1800ffdfd  lea     rax, ??_7?$TCompElemLoader@VFontFaceDecls@ODF@@V?$TSelfAdapter@VFontFaceDecls@ODF@@@Ofc@@V34@@Ofc@@6B@; const Ofc::TCompElemLoader<ODF::FontFaceDecls,Ofc::TSelfAdapter<ODF::FontFaceDecls>,Ofc::TSelfAdapter<ODF::FontFaceDecls>>::`vftable'
0x1800ffe04  mov     [rdi], rax
0x1800ffe07  mov     [rsp+50h+var_30], r15
0x1800ffe0c  mov     r9, r14
0x1800ffe0f  mov     r8, rdi
0x1800ffe12  mov     rdx, rsi
0x1800ffe15  mov     rcx, rbx
0x1800ffe18  call    cs:__imp_?PushContextAndSubLoaderImpl@CSAXReader@Ofc@@AEAAXPEAXAEAVCElemLoader@2@AEBUCXmlName@2@PEAUISAXAttributes@@@Z; Ofc::CSAXReader::PushContextAndSubLoaderImpl(void *,Ofc::CElemLoader &,Ofc::CXmlName const &,ISAXAttributes *)
0x1800ffe1e  nop
0x1800ffe1f  nop
0x1800ffe20  test    rbx, rbx
0x1800ffe23  jz      short loc_1800FFE35
0x1800ffe25  mov     rax, [rbx]
0x1800ffe28  mov     rcx, rbx
0x1800ffe2b  mov     rax, [rax+10h]
0x1800ffe2f  call    cs:__guard_dispatch_icall_fptr
0x1800ffe35  lea     rdx, [rbp+var_18]
0x1800ffe39  mov     rcx, [rbp+arg_30]
0x1800ffe3d  call    cs:__imp_?StrongMoveAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@0@Z; Ofc::CProxyPtrImpl::StrongMoveAssign(Ofc::CProxyPtrImpl * *,Ofc::CProxyPtrImpl * *)
0x1800ffe43  lea     rcx, [rbp+var_18]
0x1800ffe47  call    cs:__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1800ffe4d  lea     r11, [rsp+50h+var_s0]
0x1800ffe52  mov     rbx, [r11+20h]
0x1800ffe56  mov     rsi, [r11+28h]
0x1800ffe5a  mov     rdi, [r11+30h]
0x1800ffe5e  mov     r12, [r11+38h]
0x1800ffe62  mov     rsp, r11
0x1800ffe65  pop     r15
0x1800ffe67  pop     r14
0x1800ffe69  pop     rbp
0x1800ffe6a  retn
```
