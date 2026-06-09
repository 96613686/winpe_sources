# Art::ReadStylesImpl<ODF::Styles>(ISAXXMLReader &,ISAXAttributes *,Ofc::CXmlName &,Art::OdfStyleSet,Art::IOdfDocumentContext &,Mso::OpenXml::IPart *,Ofc::TOwningPtr<Art::IOdfReaderParams> &)

- ea: `0x1801000c0`
- end: `0x180100316`
- name: `??$ReadStylesImpl@VStyles@ODF@@@Art@@YAXAEAUISAXXMLReader@@PEAUISAXAttributes@@AEAUCXmlName@Ofc@@W4OdfStyleSet@0@AEAVIOdfDocumentContext@0@PEAUIPart@OpenXml@Mso@@AEAV?$TOwningPtr@VIOdfReaderParams@Art@@@4@@Z`
- size: `598`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180109d10`

## callees

- `0x180004818`
- `0x1800048d4`
- `0x18000afd4`
- `0x180014b40`
- `0x1801000c0`
- `0x180100860`
- `0x180171a9c`
- `0x1801a80e0`

## import_xrefs

- `KERNEL32!EncodePointer` at `0x180100188`
- `KERNEL32!EncodePointer` at `0x180100188`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801001a7`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801001a7`
- `mso40uiWin32Client!__imp_?StrongMoveAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@0@Z` at `0x1801002ed`
- `mso40uiWin32Client!__imp_?StrongMoveAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@0@Z` at `0x1801002ed`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1801001b1`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1801001e7`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x18010025c`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1801001b1`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1801001e7`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x18010025c`
- `mso40uiWin32Client!__imp_??0CCompElemLoaderImpl@Ofc@@IEAA@II@Z` at `0x1801002a7`
- `mso40uiWin32Client!__imp_??0CCompElemLoaderImpl@Ofc@@IEAA@II@Z` at `0x1801002a7`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801002f7`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801002f7`
- `mso40uiWin32Client!__imp_?PushContextAndSubLoaderImpl@CSAXReader@Ofc@@AEAAXPEAXAEAVCElemLoader@2@AEBUCXmlName@2@PEAUISAXAttributes@@@Z` at `0x1801002c8`
- `mso40uiWin32Client!__imp_?PushContextAndSubLoaderImpl@CSAXReader@Ofc@@AEAAXPEAXAEAVCElemLoader@2@AEBUCXmlName@2@PEAUISAXAttributes@@@Z` at `0x1801002c8`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x180100173`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x180100173`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1801000f5`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x180100152`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1801001fe`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1801000f5`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x180100152`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1801001fe`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18010024b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18010024b`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x180100103`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x18010020c`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x180100103`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x18010020c`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall Art::ReadStylesImpl<ODF::Styles>(
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
  v14 = Art::OdfReaderParams<ODF::Styles>::OdfReaderParams<ODF::Styles>(v11, a1, a6, v13);
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
  v30 = (struct Ofc::IReaderParams *)Ofc::CProxyPtrImpl::GetChecked(v34);
  SAXReader = Art::OdfSaxReader::CreateSAXReader(v30, a2, a3);
  v32 = SAXReader;
  v36 = SAXReader;
  if ( SAXReader )
    (*(void (__fastcall **)(struct Ofc::CSAXReader *))(*(_QWORD *)SAXReader + 8LL))(SAXReader);
  v33 = (Ofc::CCompElemLoaderImpl *)Ofc::CPrivateHeap::SmallAlloc((struct Ofc::CSAXReader *)((char *)v32 + 40), 0x40u);
  Ofc::CCompElemLoaderImpl::CCompElemLoaderImpl(v33, 1u, 1u);
  *(_QWORD *)v33 = &Ofc::TCompElemLoader<ODF::Styles,Ofc::TSelfAdapter<ODF::Styles>,Ofc::TSelfAdapter<ODF::Styles>>::`vftable';
  Ofc::CSAXReader::PushContextAndSubLoaderImpl(v32, v26, v33, a3, a2);
  if ( v32 )
    (*(void (__fastcall **)(struct Ofc::CSAXReader *))(*(_QWORD *)v32 + 16LL))(v32);
  Ofc::CProxyPtrImpl::StrongMoveAssign(a7, &v34);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v34);
}

```

## disassembly

```asm
0x1801000c0  mov     [rsp-28h+arg_0], rbx
0x1801000c5  mov     [rsp-28h+arg_8], rsi
0x1801000ca  mov     [rsp-28h+arg_18], r9d
0x1801000cf  push    rbp
0x1801000d0  push    rdi
0x1801000d1  push    r13
0x1801000d3  push    r14
0x1801000d5  push    r15
0x1801000d7  mov     rbp, rsp
0x1801000da  sub     rsp, 50h
0x1801000de  mov     r14, r8
0x1801000e1  mov     r15, rdx
0x1801000e4  mov     rdi, rcx
0x1801000e7  mov     [rbp+arg_18], 0
0x1801000ee  xor     edx, edx
0x1801000f0  mov     ecx, 1C8h
0x1801000f5  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x1801000fb  mov     rbx, rax
0x1801000fe  test    rax, rax
0x180100101  jnz     short loc_18010010A
0x180100103  call    cs:__imp_?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x180100109  int     3; Trap to Debugger
0x18010010a  mov     [rbp+var_10], rbx
0x18010010e  mov     rsi, [rbp+arg_20]
0x180100112  mov     rax, [rsi]
0x180100115  lea     rdx, [rbp+var_18]
0x180100119  mov     rcx, rsi
0x18010011c  mov     rax, [rax+118h]
0x180100123  call    cs:__guard_dispatch_icall_fptr
0x180100129  mov     r13d, 1
0x18010012f  mov     [rbp+arg_18], r13d
0x180100133  mov     r9, rax
0x180100136  mov     r8, [rbp+arg_28]
0x18010013a  mov     rdx, rdi
0x18010013d  mov     rcx, rbx
0x180100140  call    ??0?$OdfReaderParams@VStyles@ODF@@@Art@@QEAA@AEAUISAXXMLReader@@AEAUIPart@OpenXml@Mso@@AEBV?$TWeakPtr@VIOdfDocumentContext@Art@@@Ofc@@W4OdfStyleSet@1@@Z; Art::OdfReaderParams<ODF::Styles>::OdfReaderParams<ODF::Styles>(ISAXXMLReader &,Mso::OpenXml::IPart &,Ofc::TWeakPtr<Art::IOdfDocumentContext> const &,Art::OdfStyleSet)
0x180100145  mov     rdi, rax
0x180100148  test    rax, rax
0x18010014b  jz      short loc_180100198
0x18010014d  xor     edx, edx
0x18010014f  lea     ecx, [rdx+18h]
0x180100152  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x180100158  mov     rbx, rax
0x18010015b  test    rax, rax
0x18010015e  jnz     short loc_18010017A
0x180100160  lea     rcx, [rbp+arg_18]; this
0x180100164  call    ??0MsoReserveTag@@QEAA@I@Z; MsoReserveTag::MsoReserveTag(uint)
0x180100169  mov     rcx, rax
0x18010016c  call    ??BMsoReserveTag@@QEBAIXZ; MsoReserveTag::operator uint(void)
0x180100171  mov     ecx, eax
0x180100173  call    cs:__imp_?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
0x180100179  int     3; Trap to Debugger
0x18010017a  mov     [rax], r13d
0x18010017d  mov     [rax+4], r13d
0x180100181  lea     rcx, ??$TDeleteFromProxy@V?$OdfReaderParams@VPath@ODF@@@Art@@@Ofc@@YAXPEAX@Z; Ptr
0x180100188  call    cs:__imp_EncodePointer
0x18010018e  mov     [rbx+8], rax
0x180100192  mov     [rbx+10h], rdi
0x180100196  jmp     short loc_18010019F
0x180100198  lea     rbx, ?s_proxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4UProxyPtrSentinel@?1??123@KAAEBQEAV23@XZ@B; `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::ProxyPtrSentinel const `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_proxyPtrSentinel
0x18010019f  mov     [rbp+var_20], rbx
0x1801001a3  lea     rcx, [rbp+var_18]
0x1801001a7  call    cs:__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x1801001ad  mov     rcx, [rbp+var_20]
0x1801001b1  call    cs:__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1801001b7  mov     rdi, rax
0x1801001ba  mov     rdx, [rax]
0x1801001bd  mov     rbx, [rdx+18h]
0x1801001c1  mov     rdx, [rsi]
0x1801001c4  mov     rcx, rsi
0x1801001c7  mov     rax, [rdx+140h]
0x1801001ce  call    cs:__guard_dispatch_icall_fptr
0x1801001d4  mov     rdx, rax
0x1801001d7  mov     rcx, rdi
0x1801001da  mov     rax, rbx
0x1801001dd  call    cs:__guard_dispatch_icall_fptr
0x1801001e3  mov     rcx, [rbp+var_20]
0x1801001e7  call    cs:__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1801001ed  mov     rdi, rax
0x1801001f0  mov     rsi, [rax+8]
0x1801001f4  test    rsi, rsi
0x1801001f7  jnz     short loc_180100258
0x1801001f9  xor     edx, edx
0x1801001fb  lea     ecx, [rsi+18h]
0x1801001fe  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x180100204  mov     rbx, rax
0x180100207  test    rax, rax
0x18010020a  jnz     short loc_180100213
0x18010020c  call    cs:__imp_?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x180100212  int     3; Trap to Debugger
0x180100213  mov     qword ptr [rax], 0
0x18010021a  mov     qword ptr [rax+10h], 0
0x180100222  mov     qword ptr [rax+8], 0
0x18010022a  mov     dword ptr [rax+14h], 80000000h
0x180100231  mov     rsi, [rdi+8]
0x180100235  cmp     rsi, rbx
0x180100238  jz      short loc_180100258
0x18010023a  test    rsi, rsi
0x18010023d  jz      short loc_180100251
0x18010023f  lea     rcx, [rsi+8]
0x180100243  call    ??1?$TArray@V?$NumListFormatContent_@$0A@@NumListFormatData@ODF@@@Ofc@@QEAA@XZ; Ofc::TArray<ODF::NumListFormatData::NumListFormatContent_<0>>::~TArray<ODF::NumListFormatData::NumListFormatContent_<0>>(void)
0x180100248  mov     rcx, rsi
0x18010024b  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180100251  mov     [rdi+8], rbx
0x180100255  mov     rsi, rbx
0x180100258  mov     rcx, [rbp+var_20]
0x18010025c  call    cs:__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180100262  mov     r8, r14; struct Ofc::CXmlName *
0x180100265  mov     rdx, r15; struct ISAXAttributes *
0x180100268  mov     rcx, rax; struct Ofc::IReaderParams *
0x18010026b  call    ?CreateSAXReader@OdfSaxReader@Art@@SAPEAVCSAXReader@Ofc@@AEAVIReaderParams@4@PEAUISAXAttributes@@AEBUCXmlName@4@@Z; Art::OdfSaxReader::CreateSAXReader(Ofc::IReaderParams &,ISAXAttributes *,Ofc::CXmlName const &)
0x180100270  mov     rbx, rax
0x180100273  mov     [rbp+var_10], rax
0x180100277  test    rax, rax
0x18010027a  jz      short loc_18010028D
0x18010027c  mov     rax, [rax]
0x18010027f  mov     rcx, rbx
0x180100282  mov     rax, [rax+8]
0x180100286  call    cs:__guard_dispatch_icall_fptr
0x18010028c  nop
0x18010028d  lea     rcx, [rbx+28h]; this
0x180100291  mov     edx, 40h ; '@'; unsigned __int64
0x180100296  call    ?SmallAlloc@CPrivateHeap@Ofc@@QEAAPEAX_K@Z; Ofc::CPrivateHeap::SmallAlloc(unsigned __int64)
0x18010029b  mov     rdi, rax
0x18010029e  mov     r8d, r13d
0x1801002a1  mov     edx, r13d
0x1801002a4  mov     rcx, rax
0x1801002a7  call    cs:__imp_??0CCompElemLoaderImpl@Ofc@@IEAA@II@Z; Ofc::CCompElemLoaderImpl::CCompElemLoaderImpl(uint,uint)
0x1801002ad  lea     rax, ??_7?$TCompElemLoader@VStyles@ODF@@V?$TSelfAdapter@VStyles@ODF@@@Ofc@@V34@@Ofc@@6B@; const Ofc::TCompElemLoader<ODF::Styles,Ofc::TSelfAdapter<ODF::Styles>,Ofc::TSelfAdapter<ODF::Styles>>::`vftable'
0x1801002b4  mov     [rdi], rax
0x1801002b7  mov     [rsp+50h+var_30], r15
0x1801002bc  mov     r9, r14
0x1801002bf  mov     r8, rdi
0x1801002c2  mov     rdx, rsi
0x1801002c5  mov     rcx, rbx
0x1801002c8  call    cs:__imp_?PushContextAndSubLoaderImpl@CSAXReader@Ofc@@AEAAXPEAXAEAVCElemLoader@2@AEBUCXmlName@2@PEAUISAXAttributes@@@Z; Ofc::CSAXReader::PushContextAndSubLoaderImpl(void *,Ofc::CElemLoader &,Ofc::CXmlName const &,ISAXAttributes *)
0x1801002ce  nop
0x1801002cf  nop
0x1801002d0  test    rbx, rbx
0x1801002d3  jz      short loc_1801002E5
0x1801002d5  mov     rax, [rbx]
0x1801002d8  mov     rcx, rbx
0x1801002db  mov     rax, [rax+10h]
0x1801002df  call    cs:__guard_dispatch_icall_fptr
0x1801002e5  lea     rdx, [rbp+var_20]
0x1801002e9  mov     rcx, [rbp+arg_30]
0x1801002ed  call    cs:__imp_?StrongMoveAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@0@Z; Ofc::CProxyPtrImpl::StrongMoveAssign(Ofc::CProxyPtrImpl * *,Ofc::CProxyPtrImpl * *)
0x1801002f3  lea     rcx, [rbp+var_20]
0x1801002f7  call    cs:__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1801002fd  lea     r11, [rsp+50h+var_s0]
0x180100302  mov     rbx, [r11+30h]
0x180100306  mov     rsi, [r11+38h]
0x18010030a  mov     rsp, r11
0x18010030d  pop     r15
0x18010030f  pop     r14
0x180100311  pop     r13
0x180100313  pop     rdi
0x180100314  pop     rbp
0x180100315  retn
```
