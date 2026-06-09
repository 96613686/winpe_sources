# Art::ReadStylesImpl<ODF::LayerSet>(ISAXXMLReader &,ISAXAttributes *,Ofc::CXmlName &,Art::OdfStyleSet,Art::IOdfDocumentContext &,Mso::OpenXml::IPart *,Ofc::TOwningPtr<Art::IOdfReaderParams> &)

- ea: `0x1800ffe6c`
- end: `0x1801000bf`
- name: `??$ReadStylesImpl@VLayerSet@ODF@@@Art@@YAXAEAUISAXXMLReader@@PEAUISAXAttributes@@AEAUCXmlName@Ofc@@W4OdfStyleSet@0@AEAVIOdfDocumentContext@0@PEAUIPart@OpenXml@Mso@@AEAV?$TOwningPtr@VIOdfReaderParams@Art@@@4@@Z`
- size: `595`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180109cd0`

## callees

- `0x180004818`
- `0x1800048d4`
- `0x18000afd4`
- `0x18002ac70`
- `0x1800ffe6c`
- `0x180100720`
- `0x180171a9c`
- `0x1801a80e0`

## import_xrefs

- `KERNEL32!EncodePointer` at `0x1800fff34`
- `KERNEL32!EncodePointer` at `0x1800fff34`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1800fff53`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1800fff53`
- `mso40uiWin32Client!__imp_?StrongMoveAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@0@Z` at `0x180100096`
- `mso40uiWin32Client!__imp_?StrongMoveAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@0@Z` at `0x180100096`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1800fff5d`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1800fff93`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x180100006`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1800fff5d`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1800fff93`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x180100006`
- `mso40uiWin32Client!__imp_??0CCompElemLoaderImpl@Ofc@@IEAA@II@Z` at `0x180100051`
- `mso40uiWin32Client!__imp_??0CCompElemLoaderImpl@Ofc@@IEAA@II@Z` at `0x180100051`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801000a0`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801000a0`
- `mso40uiWin32Client!__imp_?PushContextAndSubLoaderImpl@CSAXReader@Ofc@@AEAAXPEAXAEAVCElemLoader@2@AEBUCXmlName@2@PEAUISAXAttributes@@@Z` at `0x180100072`
- `mso40uiWin32Client!__imp_?PushContextAndSubLoaderImpl@CSAXReader@Ofc@@AEAAXPEAXAEAVCElemLoader@2@AEBUCXmlName@2@PEAUISAXAttributes@@@Z` at `0x180100072`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x1800fff1f`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x1800fff1f`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800ffea1`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800ffefe`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800fffaa`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800ffea1`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800ffefe`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800fffaa`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800ffff5`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800ffff5`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x1800ffeaf`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x1800fffb8`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x1800ffeaf`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x1800fffb8`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall Art::ReadStylesImpl<ODF::LayerSet>(
        __int64 a1,
        struct ISAXAttributes *a2,
        const struct Ofc::CXmlName *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        struct Ofc::CProxyPtrImpl **a7)
{
  void *v10; // rax
  void *v11; // rbx
  __int64 v12; // rsi
  __int64 v13; // rax
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
  struct Ofc::CProxyPtrImpl *v34; // [rsp+30h] [rbp-20h] BYREF
  struct Ofc::CProxyPtrImpl *v35; // [rsp+38h] [rbp-18h] BYREF
  struct Ofc::CSAXReader *v36; // [rsp+40h] [rbp-10h]
  int v37; // [rsp+98h] [rbp+48h] BYREF

  v37 = 0;
  v10 = Mso::Memory::AllocateEx((Mso::Memory *)0x1C8, 0, (unsigned int)a3);
  v11 = v10;
  if ( !v10 )
  {
    ThrowOOM();
    __debugbreak();
  }
  v36 = (struct Ofc::CSAXReader *)v10;
  v12 = a5;
  v13 = (*(__int64 (__fastcall **)(__int64, struct Ofc::CProxyPtrImpl **))(*(_QWORD *)a5 + 280LL))(a5, &v35);
  v37 = 1;
  v14 = Art::OdfReaderParams<ODF::LayerSet>::OdfReaderParams<ODF::LayerSet>(v11, a1, a6, v13);
  if ( v14 )
  {
    v16 = (int *)Mso::Memory::AllocateEx((Mso::Memory *)0x18, 0, v15);
    v18 = v16;
    if ( !v16 )
    {
      v19 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)&v37, v17);
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
  v34 = (struct Ofc::CProxyPtrImpl *)v18;
  Ofc::CProxyPtrImpl::DtorWeakRelease(&v35);
  Checked = Ofc::CProxyPtrImpl::GetChecked((Ofc::CProxyPtrImpl *)v18);
  v22 = *(void (__fastcall **)(void *, __int64))(*(_QWORD *)Checked + 24LL);
  v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 320LL))(v12);
  v22(Checked, v23);
  v24 = Ofc::CProxyPtrImpl::GetChecked(v34);
  v26 = (Mso::Memory *)*((_QWORD *)v24 + 1);
  if ( !v26 )
  {
    v27 = (Mso::Memory *)Mso::Memory::AllocateEx((Mso::Memory *)0x18, 0, v25);
    v28 = v27;
    if ( !v27 )
      ThrowOOM();
    *(_DWORD *)v27 = 0;
    *((_QWORD *)v27 + 1) = 0;
    *((_DWORD *)v27 + 4) = 0;
    *((_DWORD *)v27 + 5) = 0x80000000;
    v26 = (Mso::Memory *)*((_QWORD *)v24 + 1);
    if ( v26 != v28 )
    {
      if ( v26 )
      {
        ODF::LayerSet::~LayerSet(*((ODF::LayerSet **)v24 + 1));
        Mso::Memory::Free(v26, v29);
      }
      *((_QWORD *)v24 + 1) = v28;
      v26 = v28;
    }
  }
  v30 = (struct Ofc::IReaderParams *)Ofc::CProxyPtrImpl::GetChecked(v34);
  SAXReader = Art::OdfSaxReader::CreateSAXReader(v30, a2, a3);
  v32 = SAXReader;
  v36 = SAXReader;
  if ( SAXReader )
    (*(void (__fastcall **)(struct Ofc::CSAXReader *))(*(_QWORD *)SAXReader + 8LL))(SAXReader);
  v33 = (Ofc::CCompElemLoaderImpl *)Ofc::CPrivateHeap::SmallAlloc((struct Ofc::CSAXReader *)((char *)v32 + 40), 0x40u);
  Ofc::CCompElemLoaderImpl::CCompElemLoaderImpl(v33, 1u, 1u);
  *(_QWORD *)v33 = &Ofc::TCompElemLoader<ODF::LayerSet,Ofc::TSelfAdapter<ODF::LayerSet>,Ofc::TSelfAdapter<ODF::LayerSet>>::`vftable';
  Ofc::CSAXReader::PushContextAndSubLoaderImpl(v32, v26, v33, a3, a2);
  if ( v32 )
    (*(void (__fastcall **)(struct Ofc::CSAXReader *))(*(_QWORD *)v32 + 16LL))(v32);
  Ofc::CProxyPtrImpl::StrongMoveAssign(a7, &v34);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v34);
}

```

## disassembly

```asm
0x1800ffe6c  mov     [rsp-28h+arg_0], rbx
0x1800ffe71  mov     [rsp-28h+arg_8], rsi
0x1800ffe76  mov     [rsp-28h+arg_18], r9d
0x1800ffe7b  push    rbp
0x1800ffe7c  push    rdi
0x1800ffe7d  push    r13
0x1800ffe7f  push    r14
0x1800ffe81  push    r15
0x1800ffe83  mov     rbp, rsp
0x1800ffe86  sub     rsp, 50h
0x1800ffe8a  mov     r14, r8
0x1800ffe8d  mov     r15, rdx
0x1800ffe90  mov     rdi, rcx
0x1800ffe93  mov     [rbp+arg_18], 0
0x1800ffe9a  xor     edx, edx
0x1800ffe9c  mov     ecx, 1C8h
0x1800ffea1  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x1800ffea7  mov     rbx, rax
0x1800ffeaa  test    rax, rax
0x1800ffead  jnz     short loc_1800FFEB6
0x1800ffeaf  call    cs:__imp_?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x1800ffeb5  int     3; Trap to Debugger
0x1800ffeb6  mov     [rbp+var_10], rbx
0x1800ffeba  mov     rsi, [rbp+arg_20]
0x1800ffebe  mov     rax, [rsi]
0x1800ffec1  lea     rdx, [rbp+var_18]
0x1800ffec5  mov     rcx, rsi
0x1800ffec8  mov     rax, [rax+118h]
0x1800ffecf  call    cs:__guard_dispatch_icall_fptr
0x1800ffed5  mov     r13d, 1
0x1800ffedb  mov     [rbp+arg_18], r13d
0x1800ffedf  mov     r9, rax
0x1800ffee2  mov     r8, [rbp+arg_28]
0x1800ffee6  mov     rdx, rdi
0x1800ffee9  mov     rcx, rbx
0x1800ffeec  call    ??0?$OdfReaderParams@VLayerSet@ODF@@@Art@@QEAA@AEAUISAXXMLReader@@AEAUIPart@OpenXml@Mso@@AEBV?$TWeakPtr@VIOdfDocumentContext@Art@@@Ofc@@W4OdfStyleSet@1@@Z; Art::OdfReaderParams<ODF::LayerSet>::OdfReaderParams<ODF::LayerSet>(ISAXXMLReader &,Mso::OpenXml::IPart &,Ofc::TWeakPtr<Art::IOdfDocumentContext> const &,Art::OdfStyleSet)
0x1800ffef1  mov     rdi, rax
0x1800ffef4  test    rax, rax
0x1800ffef7  jz      short loc_1800FFF44
0x1800ffef9  xor     edx, edx
0x1800ffefb  lea     ecx, [rdx+18h]
0x1800ffefe  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x1800fff04  mov     rbx, rax
0x1800fff07  test    rax, rax
0x1800fff0a  jnz     short loc_1800FFF26
0x1800fff0c  lea     rcx, [rbp+arg_18]; this
0x1800fff10  call    ??0MsoReserveTag@@QEAA@I@Z; MsoReserveTag::MsoReserveTag(uint)
0x1800fff15  mov     rcx, rax
0x1800fff18  call    ??BMsoReserveTag@@QEBAIXZ; MsoReserveTag::operator uint(void)
0x1800fff1d  mov     ecx, eax
0x1800fff1f  call    cs:__imp_?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
0x1800fff25  int     3; Trap to Debugger
0x1800fff26  mov     [rax], r13d
0x1800fff29  mov     [rax+4], r13d
0x1800fff2d  lea     rcx, ??$TDeleteFromProxy@V?$OdfReaderParams@VPath@ODF@@@Art@@@Ofc@@YAXPEAX@Z; Ptr
0x1800fff34  call    cs:__imp_EncodePointer
0x1800fff3a  mov     [rbx+8], rax
0x1800fff3e  mov     [rbx+10h], rdi
0x1800fff42  jmp     short loc_1800FFF4B
0x1800fff44  lea     rbx, ?s_proxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4UProxyPtrSentinel@?1??123@KAAEBQEAV23@XZ@B; `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::ProxyPtrSentinel const `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_proxyPtrSentinel
0x1800fff4b  mov     [rbp+var_20], rbx
0x1800fff4f  lea     rcx, [rbp+var_18]
0x1800fff53  call    cs:__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x1800fff59  mov     rcx, [rbp+var_20]
0x1800fff5d  call    cs:__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1800fff63  mov     rdi, rax
0x1800fff66  mov     rdx, [rax]
0x1800fff69  mov     rbx, [rdx+18h]
0x1800fff6d  mov     rdx, [rsi]
0x1800fff70  mov     rcx, rsi
0x1800fff73  mov     rax, [rdx+140h]
0x1800fff7a  call    cs:__guard_dispatch_icall_fptr
0x1800fff80  mov     rdx, rax
0x1800fff83  mov     rcx, rdi
0x1800fff86  mov     rax, rbx
0x1800fff89  call    cs:__guard_dispatch_icall_fptr
0x1800fff8f  mov     rcx, [rbp+var_20]
0x1800fff93  call    cs:__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1800fff99  mov     rdi, rax
0x1800fff9c  mov     rsi, [rax+8]
0x1800fffa0  test    rsi, rsi
0x1800fffa3  jnz     short loc_180100002
0x1800fffa5  xor     edx, edx
0x1800fffa7  lea     ecx, [rsi+18h]
0x1800fffaa  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x1800fffb0  mov     rbx, rax
0x1800fffb3  test    rax, rax
0x1800fffb6  jnz     short loc_1800FFFC0
0x1800fffb8  call    cs:__imp_?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x1800fffbe  nop
0x1800fffbf  nop
0x1800fffc0  mov     dword ptr [rax], 0
0x1800fffc6  mov     qword ptr [rax+8], 0
0x1800fffce  mov     dword ptr [rax+10h], 0
0x1800fffd5  mov     dword ptr [rax+14h], 80000000h
0x1800fffdc  mov     rsi, [rdi+8]
0x1800fffe0  cmp     rsi, rbx
0x1800fffe3  jz      short loc_180100002
0x1800fffe5  test    rsi, rsi
0x1800fffe8  jz      short loc_1800FFFFB
0x1800fffea  mov     rcx, rsi; this
0x1800fffed  call    ??1LayerSet@ODF@@QEAA@XZ; ODF::LayerSet::~LayerSet(void)
0x1800ffff2  mov     rcx, rsi
0x1800ffff5  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800ffffb  mov     [rdi+8], rbx
0x1800fffff  mov     rsi, rbx
0x180100002  mov     rcx, [rbp+var_20]
0x180100006  call    cs:__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18010000c  mov     r8, r14; struct Ofc::CXmlName *
0x18010000f  mov     rdx, r15; struct ISAXAttributes *
0x180100012  mov     rcx, rax; struct Ofc::IReaderParams *
0x180100015  call    ?CreateSAXReader@OdfSaxReader@Art@@SAPEAVCSAXReader@Ofc@@AEAVIReaderParams@4@PEAUISAXAttributes@@AEBUCXmlName@4@@Z; Art::OdfSaxReader::CreateSAXReader(Ofc::IReaderParams &,ISAXAttributes *,Ofc::CXmlName const &)
0x18010001a  mov     rbx, rax
0x18010001d  mov     [rbp+var_10], rax
0x180100021  test    rax, rax
0x180100024  jz      short loc_180100037
0x180100026  mov     rax, [rax]
0x180100029  mov     rcx, rbx
0x18010002c  mov     rax, [rax+8]
0x180100030  call    cs:__guard_dispatch_icall_fptr
0x180100036  nop
0x180100037  lea     rcx, [rbx+28h]; this
0x18010003b  mov     edx, 40h ; '@'; unsigned __int64
0x180100040  call    ?SmallAlloc@CPrivateHeap@Ofc@@QEAAPEAX_K@Z; Ofc::CPrivateHeap::SmallAlloc(unsigned __int64)
0x180100045  mov     rdi, rax
0x180100048  mov     r8d, r13d
0x18010004b  mov     edx, r13d
0x18010004e  mov     rcx, rax
0x180100051  call    cs:__imp_??0CCompElemLoaderImpl@Ofc@@IEAA@II@Z; Ofc::CCompElemLoaderImpl::CCompElemLoaderImpl(uint,uint)
0x180100057  lea     rax, ??_7?$TCompElemLoader@VLayerSet@ODF@@V?$TSelfAdapter@VLayerSet@ODF@@@Ofc@@V34@@Ofc@@6B@; const Ofc::TCompElemLoader<ODF::LayerSet,Ofc::TSelfAdapter<ODF::LayerSet>,Ofc::TSelfAdapter<ODF::LayerSet>>::`vftable'
0x18010005e  mov     [rdi], rax
0x180100061  mov     [rsp+50h+var_30], r15
0x180100066  mov     r9, r14
0x180100069  mov     r8, rdi
0x18010006c  mov     rdx, rsi
0x18010006f  mov     rcx, rbx
0x180100072  call    cs:__imp_?PushContextAndSubLoaderImpl@CSAXReader@Ofc@@AEAAXPEAXAEAVCElemLoader@2@AEBUCXmlName@2@PEAUISAXAttributes@@@Z; Ofc::CSAXReader::PushContextAndSubLoaderImpl(void *,Ofc::CElemLoader &,Ofc::CXmlName const &,ISAXAttributes *)
0x180100078  nop
0x180100079  test    rbx, rbx
0x18010007c  jz      short loc_18010008E
0x18010007e  mov     rax, [rbx]
0x180100081  mov     rcx, rbx
0x180100084  mov     rax, [rax+10h]
0x180100088  call    cs:__guard_dispatch_icall_fptr
0x18010008e  lea     rdx, [rbp+var_20]
0x180100092  mov     rcx, [rbp+arg_30]
0x180100096  call    cs:__imp_?StrongMoveAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@0@Z; Ofc::CProxyPtrImpl::StrongMoveAssign(Ofc::CProxyPtrImpl * *,Ofc::CProxyPtrImpl * *)
0x18010009c  lea     rcx, [rbp+var_20]
0x1801000a0  call    cs:__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1801000a6  lea     r11, [rsp+50h+var_s0]
0x1801000ab  mov     rbx, [r11+30h]
0x1801000af  mov     rsi, [r11+38h]
0x1801000b3  mov     rsp, r11
0x1801000b6  pop     r15
0x1801000b8  pop     r14
0x1801000ba  pop     r13
0x1801000bc  pop     rdi
0x1801000bd  pop     rbp
0x1801000be  retn
```
