# Art::LoadOdfParagraph(Art::TextBody &,Art::IOdfDocumentContext &,ISAXXMLReader &,ISAXAttributes *,Ofc::CXmlName const &,Ofc::TOwningPtr<Art::IOdfReaderParams> &)

- ea: `0x18011e7a0`
- end: `0x18011ea01`
- name: `?LoadOdfParagraph@Art@@YAXAEAVTextBody@1@AEAVIOdfDocumentContext@1@AEAUISAXXMLReader@@PEAUISAXAttributes@@AEBUCXmlName@Ofc@@AEAV?$TOwningPtr@VIOdfReaderParams@Art@@@7@@Z`
- size: `609`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004818`
- `0x1800048d4`
- `0x18000afd4`
- `0x1800f0110`
- `0x1800f06e0`
- `0x18011e7a0`
- `0x180171a9c`
- `0x1801a80e0`

## import_xrefs

- `KERNEL32!EncodePointer` at `0x18011e874`
- `KERNEL32!EncodePointer` at `0x18011e874`
- `mso40uiWin32Client!__imp_?StrongMoveAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@0@Z` at `0x18011e9ba`
- `mso40uiWin32Client!__imp_?StrongMoveAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@0@Z` at `0x18011e9ba`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x18011e893`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x18011e8ca`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x18011e937`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x18011e893`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x18011e8ca`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x18011e937`
- `mso40uiWin32Client!__imp_??0CCompElemLoaderImpl@Ofc@@IEAA@II@Z` at `0x18011e91a`
- `mso40uiWin32Client!__imp_??0CCompElemLoaderImpl@Ofc@@IEAA@II@Z` at `0x18011e91a`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x18011e9dc`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x18011e9dc`
- `mso40uiWin32Client!__imp_?PushContextAndSubLoaderImpl@CSAXReader@Ofc@@AEAAXPEAXAEAVCElemLoader@2@AEBUCXmlName@2@PEAUISAXAttributes@@@Z` at `0x18011e9ac`
- `mso40uiWin32Client!__imp_?PushContextAndSubLoaderImpl@CSAXReader@Ofc@@AEAAXPEAXAEAVCElemLoader@2@AEBUCXmlName@2@PEAUISAXAttributes@@@Z` at `0x18011e9ac`
- `mso40uiWin32Client!__imp_??0CUriTokenizer@Ofc@@QEAA@PEBUCBuiltinNamespaceList@1@@Z` at `0x18011e809`
- `mso40uiWin32Client!__imp_??0CUriTokenizer@Ofc@@QEAA@PEBUCBuiltinNamespaceList@1@@Z` at `0x18011e809`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x18011e85c`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x18011e85c`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18011e7d0`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18011e83a`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18011e94e`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18011e7d0`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18011e83a`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18011e94e`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18011e989`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18011e989`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x18011e7de`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x18011e959`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x18011e7de`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x18011e959`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Art::LoadOdfParagraph(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        struct ISAXAttributes *a4,
        struct Ofc::CXmlName *a5,
        Ofc::CProxyPtrImpl **a6)
{
  _QWORD *v10; // rbx
  unsigned int v11; // r8d
  struct Ofc::CProxyPtrImpl *v12; // rax
  unsigned int v13; // edx
  struct Ofc::CProxyPtrImpl *v14; // rdi
  MsoReserveTag *v15; // rax
  unsigned int v16; // eax
  void *Checked; // rdi
  void (__fastcall *v18)(void *, __int64); // rbx
  __int64 v19; // rax
  struct Ofc::IReaderParams *v20; // rax
  struct Ofc::CSAXReader *SAXReader; // rax
  struct Ofc::CSAXReader *v22; // rbx
  Ofc::CCompElemLoaderImpl *v23; // r14
  void *v24; // rbp
  unsigned int v25; // r8d
  Mso::Memory *v26; // rdi
  struct Ofc::CProxyPtrImpl *v27; // rax
  __int64 v28; // rsi
  void *v29; // rdx
  struct Ofc::CSAXReader *v30; // [rsp+30h] [rbp-38h] BYREF
  struct Ofc::CProxyPtrImpl *v31[3]; // [rsp+38h] [rbp-30h] BYREF

  v10 = Mso::Memory::AllocateEx((Mso::Memory *)0x158, 0, a3);
  if ( !v10 )
  {
    ThrowOOM();
    __debugbreak();
  }
  *v10 = &Art::OdfDefReaderParams<ODF::P>::`vftable';
  v10[1] = 0;
  v10[2] = a3;
  v10[3] = 0;
  Ofc::CUriTokenizer::CUriTokenizer((Ofc::CUriTokenizer *)(v10 + 4), 0);
  *v10 = &Art::OdfParagraphReaderParams::`vftable';
  v10[40] = &Art::OdfParaParam::`vftable';
  v10[41] = a2;
  v10[42] = a1;
  v12 = (struct Ofc::CProxyPtrImpl *)Mso::Memory::AllocateEx((Mso::Memory *)0x18, 0, v11);
  v14 = v12;
  if ( !v12 )
  {
    v15 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)&v30, v13);
    v16 = MsoReserveTag::operator unsigned int(v15);
    CrashWithRecoveryOnOOM(v16);
    __debugbreak();
  }
  *(_DWORD *)v12 = 1;
  *((_DWORD *)v12 + 1) = 1;
  *((_QWORD *)v12 + 1) = EncodePointer(Ofc::TDeleteFromProxy<Art::OdfParagraphReaderParams>);
  *((_QWORD *)v14 + 2) = v10;
  v31[0] = v14;
  Checked = Ofc::CProxyPtrImpl::GetChecked(*a6);
  v18 = *(void (__fastcall **)(void *, __int64))(*(_QWORD *)Checked + 24LL);
  v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 320LL))(a2);
  v18(Checked, v19);
  v20 = (struct Ofc::IReaderParams *)Ofc::CProxyPtrImpl::GetChecked(v31[0]);
  SAXReader = Art::OdfSaxReader::CreateSAXReader(v20, a4, a5);
  v22 = SAXReader;
  v30 = SAXReader;
  if ( SAXReader )
    (*(void (__fastcall **)(struct Ofc::CSAXReader *))(*(_QWORD *)SAXReader + 8LL))(SAXReader);
  v23 = (Ofc::CCompElemLoaderImpl *)Ofc::CPrivateHeap::SmallAlloc((struct Ofc::CSAXReader *)((char *)v22 + 40), 0x48u);
  Ofc::CCompElemLoaderImpl::CCompElemLoaderImpl(v23, 1u, 1u);
  *(_QWORD *)v23 = &Ofc::TCompElemMixedContentLoader<ODF::P,Ofc::TSelfAdapter<ODF::P>,Ofc::TSelfAdapter<ODF::P>>::`vftable';
  *((_QWORD *)v23 + 8) = 0;
  v24 = Ofc::CProxyPtrImpl::GetChecked(v31[0]);
  v26 = (Mso::Memory *)*((_QWORD *)v24 + 1);
  if ( !v26 )
  {
    v27 = (struct Ofc::CProxyPtrImpl *)Mso::Memory::AllocateEx((Mso::Memory *)8, 0, v25);
    if ( !v27 )
    {
      ThrowOOM();
      __debugbreak();
    }
    v31[1] = v27;
    v28 = ODF::P::P(v27);
    v26 = (Mso::Memory *)*((_QWORD *)v24 + 1);
    if ( v26 != (Mso::Memory *)v28 )
    {
      if ( v26 )
      {
        ODF::P::~P(*((ODF::P **)v24 + 1));
        Mso::Memory::Free(v26, v29);
      }
      *((_QWORD *)v24 + 1) = v28;
      v26 = (Mso::Memory *)v28;
    }
  }
  Ofc::CSAXReader::PushContextAndSubLoaderImpl(v22, v26, v23, a5, a4);
  Ofc::CProxyPtrImpl::StrongMoveAssign(a6, v31);
  if ( v22 )
    (*(void (__fastcall **)(struct Ofc::CSAXReader *))(*(_QWORD *)v22 + 16LL))(v22);
  Ofc::CProxyPtrImpl::DtorStrongRelease(v31);
}

```

## disassembly

```asm
0x18011e7a0  mov     rax, rsp
0x18011e7a3  mov     [rax+8], rbx
0x18011e7a7  mov     [rax+10h], rbp
0x18011e7ab  mov     [rax+18h], rsi
0x18011e7af  mov     [rax+20h], rdi
0x18011e7b3  push    r12
0x18011e7b5  push    r14
0x18011e7b7  push    r15
0x18011e7b9  sub     rsp, 50h
0x18011e7bd  mov     r15, r9
0x18011e7c0  mov     rdi, r8
0x18011e7c3  mov     rsi, rdx
0x18011e7c6  mov     rbp, rcx
0x18011e7c9  xor     edx, edx
0x18011e7cb  mov     ecx, 158h
0x18011e7d0  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x18011e7d6  mov     rbx, rax
0x18011e7d9  test    rax, rax
0x18011e7dc  jnz     short loc_18011E7E5
0x18011e7de  call    cs:__imp_?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x18011e7e4  int     3; Trap to Debugger
0x18011e7e5  lea     rax, ??_7?$OdfDefReaderParams@VP@ODF@@@Art@@6B@; const Art::OdfDefReaderParams<ODF::P>::`vftable'
0x18011e7ec  mov     [rbx], rax
0x18011e7ef  mov     qword ptr [rbx+8], 0
0x18011e7f7  mov     [rbx+10h], rdi
0x18011e7fb  mov     qword ptr [rbx+18h], 0
0x18011e803  lea     rcx, [rbx+20h]
0x18011e807  xor     edx, edx
0x18011e809  call    cs:__imp_??0CUriTokenizer@Ofc@@QEAA@PEBUCBuiltinNamespaceList@1@@Z; Ofc::CUriTokenizer::CUriTokenizer(Ofc::CBuiltinNamespaceList const *)
0x18011e80f  lea     rax, ??_7OdfParagraphReaderParams@Art@@6B@; const Art::OdfParagraphReaderParams::`vftable'
0x18011e816  mov     [rbx], rax
0x18011e819  lea     rax, ??_7OdfParaParam@Art@@6B@; const Art::OdfParaParam::`vftable'
0x18011e820  mov     [rbx+140h], rax
0x18011e827  mov     [rbx+148h], rsi
0x18011e82e  mov     [rbx+150h], rbp
0x18011e835  xor     edx, edx
0x18011e837  lea     ecx, [rdx+18h]
0x18011e83a  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x18011e840  mov     rdi, rax
0x18011e843  test    rax, rax
0x18011e846  jnz     short loc_18011E863
0x18011e848  lea     rcx, [rsp+68h+var_38]; this
0x18011e84d  call    ??0MsoReserveTag@@QEAA@I@Z; MsoReserveTag::MsoReserveTag(uint)
0x18011e852  mov     rcx, rax
0x18011e855  call    ??BMsoReserveTag@@QEBAIXZ; MsoReserveTag::operator uint(void)
0x18011e85a  mov     ecx, eax
0x18011e85c  call    cs:__imp_?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
0x18011e862  int     3; Trap to Debugger
0x18011e863  mov     ebp, 1
0x18011e868  mov     [rax], ebp
0x18011e86a  mov     [rax+4], ebp
0x18011e86d  lea     rcx, ??$TDeleteFromProxy@VOdfParagraphReaderParams@Art@@@Ofc@@YAXPEAX@Z; Ptr
0x18011e874  call    cs:__imp_EncodePointer
0x18011e87a  mov     [rdi+8], rax
0x18011e87e  mov     [rdi+10h], rbx
0x18011e882  mov     [rsp+68h+var_30], rdi
0x18011e887  mov     r12, [rsp+68h+arg_28]
0x18011e88f  mov     rcx, [r12]
0x18011e893  call    cs:__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18011e899  mov     rdi, rax
0x18011e89c  mov     rcx, [rax]
0x18011e89f  mov     rbx, [rcx+18h]
0x18011e8a3  mov     rcx, [rsi]
0x18011e8a6  mov     rax, [rcx+140h]
0x18011e8ad  mov     rcx, rsi
0x18011e8b0  call    cs:__guard_dispatch_icall_fptr
0x18011e8b6  mov     rdx, rax
0x18011e8b9  mov     rcx, rdi
0x18011e8bc  mov     rax, rbx
0x18011e8bf  call    cs:__guard_dispatch_icall_fptr
0x18011e8c5  mov     rcx, [rsp+68h+var_30]
0x18011e8ca  call    cs:__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18011e8d0  mov     r8, [rsp+68h+arg_20]; struct Ofc::CXmlName *
0x18011e8d8  mov     rdx, r15; struct ISAXAttributes *
0x18011e8db  mov     rcx, rax; struct Ofc::IReaderParams *
0x18011e8de  call    ?CreateSAXReader@OdfSaxReader@Art@@SAPEAVCSAXReader@Ofc@@AEAVIReaderParams@4@PEAUISAXAttributes@@AEBUCXmlName@4@@Z; Art::OdfSaxReader::CreateSAXReader(Ofc::IReaderParams &,ISAXAttributes *,Ofc::CXmlName const &)
0x18011e8e3  mov     rbx, rax
0x18011e8e6  mov     [rsp+68h+var_38], rax
0x18011e8eb  test    rax, rax
0x18011e8ee  jz      short loc_18011E901
0x18011e8f0  mov     rax, [rax]
0x18011e8f3  mov     rcx, rbx
0x18011e8f6  mov     rax, [rax+8]
0x18011e8fa  call    cs:__guard_dispatch_icall_fptr
0x18011e900  nop
0x18011e901  lea     rcx, [rbx+28h]; this
0x18011e905  mov     edx, 48h ; 'H'; unsigned __int64
0x18011e90a  call    ?SmallAlloc@CPrivateHeap@Ofc@@QEAAPEAX_K@Z; Ofc::CPrivateHeap::SmallAlloc(unsigned __int64)
0x18011e90f  mov     r14, rax
0x18011e912  mov     r8d, ebp
0x18011e915  mov     edx, ebp
0x18011e917  mov     rcx, rax
0x18011e91a  call    cs:__imp_??0CCompElemLoaderImpl@Ofc@@IEAA@II@Z; Ofc::CCompElemLoaderImpl::CCompElemLoaderImpl(uint,uint)
0x18011e920  lea     rax, ??_7?$TCompElemMixedContentLoader@VP@ODF@@V?$TSelfAdapter@VP@ODF@@@Ofc@@V34@@Ofc@@6B@; const Ofc::TCompElemMixedContentLoader<ODF::P,Ofc::TSelfAdapter<ODF::P>,Ofc::TSelfAdapter<ODF::P>>::`vftable'
0x18011e927  mov     [r14], rax
0x18011e92a  mov     qword ptr [r14+40h], 0
0x18011e932  mov     rcx, [rsp+68h+var_30]
0x18011e937  call    cs:__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18011e93d  mov     rbp, rax
0x18011e940  mov     rdi, [rax+8]
0x18011e944  test    rdi, rdi
0x18011e947  jnz     short loc_18011E996
0x18011e949  xor     edx, edx
0x18011e94b  lea     ecx, [rdi+8]
0x18011e94e  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x18011e954  test    rax, rax
0x18011e957  jnz     short loc_18011E960
0x18011e959  call    cs:__imp_?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x18011e95f  int     3; Trap to Debugger
0x18011e960  mov     [rsp+68h+var_28], rax
0x18011e965  mov     rcx, rax; this
0x18011e968  call    ??0P@ODF@@QEAA@XZ; ODF::P::P(void)
0x18011e96d  mov     rsi, rax
0x18011e970  mov     rdi, [rbp+8]
0x18011e974  cmp     rdi, rax
0x18011e977  jz      short loc_18011E996
0x18011e979  test    rdi, rdi
0x18011e97c  jz      short loc_18011E98F
0x18011e97e  mov     rcx, rdi; this
0x18011e981  call    ??1P@ODF@@QEAA@XZ; ODF::P::~P(void)
0x18011e986  mov     rcx, rdi
0x18011e989  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18011e98f  mov     [rbp+8], rsi
0x18011e993  mov     rdi, rsi
0x18011e996  mov     [rsp+68h+var_48], r15
0x18011e99b  mov     r9, [rsp+68h+arg_20]
0x18011e9a3  mov     r8, r14
0x18011e9a6  mov     rdx, rdi
0x18011e9a9  mov     rcx, rbx
0x18011e9ac  call    cs:__imp_?PushContextAndSubLoaderImpl@CSAXReader@Ofc@@AEAAXPEAXAEAVCElemLoader@2@AEBUCXmlName@2@PEAUISAXAttributes@@@Z; Ofc::CSAXReader::PushContextAndSubLoaderImpl(void *,Ofc::CElemLoader &,Ofc::CXmlName const &,ISAXAttributes *)
0x18011e9b2  lea     rdx, [rsp+68h+var_30]
0x18011e9b7  mov     rcx, r12
0x18011e9ba  call    cs:__imp_?StrongMoveAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@0@Z; Ofc::CProxyPtrImpl::StrongMoveAssign(Ofc::CProxyPtrImpl * *,Ofc::CProxyPtrImpl * *)
0x18011e9c0  nop
0x18011e9c1  test    rbx, rbx
0x18011e9c4  jz      short loc_18011E9D7
0x18011e9c6  mov     rax, [rbx]
0x18011e9c9  mov     rcx, rbx
0x18011e9cc  mov     rax, [rax+10h]
0x18011e9d0  call    cs:__guard_dispatch_icall_fptr
0x18011e9d6  nop
0x18011e9d7  lea     rcx, [rsp+68h+var_30]
0x18011e9dc  call    cs:__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18011e9e2  lea     r11, [rsp+68h+var_18]
0x18011e9e7  mov     rbx, [r11+20h]
0x18011e9eb  mov     rbp, [r11+28h]
0x18011e9ef  mov     rsi, [r11+30h]
0x18011e9f3  mov     rdi, [r11+38h]
0x18011e9f7  mov     rsp, r11
0x18011e9fa  pop     r15
0x18011e9fc  pop     r14
0x18011e9fe  pop     r12
0x18011ea00  retn
```
