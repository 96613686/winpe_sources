# Art::OdfFunctions::WriteOdpContent(ODF::DocumentStyles &,wchar_t const *,IMXAttributes &,Ofc::TSharedPtr<Art::BlipSaveManager> const &,Metro::Part &,Ofc::TArray<Mso::Xsd::Namespaces::NamespaceUriToken> const &)

- ea: `0x18016a5c4`
- end: `0x18016a882`
- name: `?WriteOdpContent@OdfFunctions@Art@@SAXAEAVDocumentStyles@ODF@@PEB_WAEAUIMXAttributes@@AEBV?$TSharedPtr@VBlipSaveManager@Art@@@Ofc@@AEAVPart@Metro@@AEBV?$TArray@W4NamespaceUriToken@Namespaces@Xsd@Mso@@@7@@Z_0`
- size: `702`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180170ae0`

## callees

- `0x1800025a0`
- `0x180007898`
- `0x18016a5c4`
- `0x180170a40`
- `0x1801a8060`
- `0x1801a80e0`

## import_xrefs

- `oart!__imp_??0SaveContextParam@Art@@QEAA@XZ` at `0x18016a71a`
- `oart!__imp_??0SaveContextParam@Art@@QEAA@XZ` at `0x18016a71a`
- `oart!__imp_??1E2oWriterParams@Art@@UEAA@XZ` at `0x18016a7b5`
- `oart!__imp_??1E2oWriterParams@Art@@UEAA@XZ` at `0x18016a7b5`
- `oart!__imp_??0E2oWriterParams@Art@@QEAA@AEAUISAXContentHandler@@AEAUIMXAttributes@@AEAVCNamespaceList@Ofc@@AEAUIPart@OpenXml@Mso@@AEBV?$TSharedPtr@VBlipSaveManager@Art@@@5@AEBVSaveContextParam@1@AEBV?$TSharedPtr@VView@Art@@@5@@Z` at `0x18016a762`
- `oart!__imp_??0E2oWriterParams@Art@@QEAA@AEAUISAXContentHandler@@AEAUIMXAttributes@@AEAVCNamespaceList@Ofc@@AEAUIPart@OpenXml@Mso@@AEBV?$TSharedPtr@VBlipSaveManager@Art@@@5@AEBVSaveContextParam@1@AEBV?$TSharedPtr@VView@Art@@@5@@Z` at `0x18016a762`
- `mso40uiWin32Client!__imp_??1CNamespaceList@Ofc@@QEAA@XZ` at `0x18016a7d4`
- `mso40uiWin32Client!__imp_??1CNamespaceList@Ofc@@QEAA@XZ` at `0x18016a7d4`
- `mso40uiWin32Client!__imp_?CreateMXXMLWriter@Ofc@@YAXAEAUIStream@@AEAV?$TCntPtr@UIMXWriter@@@1@@Z` at `0x18016a66a`
- `mso40uiWin32Client!__imp_?CreateMXXMLWriter@Ofc@@YAXAEAUIStream@@AEAV?$TCntPtr@UIMXWriter@@@1@@Z` at `0x18016a66a`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18016a707`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18016a707`
- `mso40uiWin32Client!__imp_??1CNamespaceDeclarationTracker@Ofc@@QEAA@XZ` at `0x18016a7bf`
- `mso40uiWin32Client!__imp_??1CNamespaceDeclarationTracker@Ofc@@QEAA@XZ` at `0x18016a7bf`
- `mso40uiWin32Client!__imp_??0CNamespaceList@Ofc@@QEAA@PEBUCBuiltinNamespaceList@1@@Z` at `0x18016a6ad`
- `mso40uiWin32Client!__imp_??0CNamespaceList@Ofc@@QEAA@PEBUCBuiltinNamespaceList@1@@Z` at `0x18016a6ad`
- `mso40uiWin32Client!__imp_??0CNamespaceDeclarationTracker@Ofc@@QEAA@AEAVCNamespaceList@1@AEAUIMXAttributes@@H_N@Z` at `0x18016a6e1`
- `mso40uiWin32Client!__imp_??0CNamespaceDeclarationTracker@Ofc@@QEAA@AEAVCNamespaceList@1@AEAUIMXAttributes@@H_N@Z` at `0x18016a6e1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18016a6c4`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18016a84e`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18016a6c4`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18016a84e`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall Art::OdfFunctions::WriteOdpContent(
        __int64 a1,
        __int64 a2,
        struct IMXAttributes *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  __int64 (__fastcall **v8)(__int64, GUID *, __int64 *); // rax
  int v9; // eax
  unsigned int v10; // ebx
  unsigned int v11; // eax
  __int64 v12; // rax
  int v13; // eax
  int v14; // eax
  __int64 v15; // [rsp+40h] [rbp-C0h] BYREF
  __int64 (__fastcall ***v16)(__int64, GUID *, __int64 *); // [rsp+48h] [rbp-B8h] BYREF
  __int64 v17; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v18[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v19; // [rsp+68h] [rbp-98h] BYREF
  int v20; // [rsp+70h] [rbp-90h]
  __int64 v21; // [rsp+78h] [rbp-88h]
  _BYTE v22[48]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v23[176]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v24[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v25[4464]; // [rsp+180h] [rbp+80h] BYREF

  v19 = a2;
  v20 = 300;
  v21 = a1;
  v18[0] = &Ofc::TElemWriter<Ofc::TCompElemWriter<ODF::DocumentStyles,Ofc::TSelfAdapter<ODF::DocumentStyles>,Ofc::TSelfAdapter<ODF::DocumentStyles>>>::`vftable';
  v18[1] = &v19;
  v17 = 0;
  (*(void (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)a5 + 96LL))(a5, &v17, 4);
  v16 = 0;
  Ofc::CreateMXXMLWriter(v17, &v16);
  v15 = 0;
  v8 = *v16;
  v15 = 0;
  v9 = (*v8)((__int64)v16, &GUID_1545cdfa_9e4e_4497_a8a4_2bf7d0112c44, &v15);
  if ( v9 < 0 )
    Ofc::CHResultException::ThrowTag(v9, 0x2325D5E0u);
  Ofc::CNamespaceList::CNamespaceList((Ofc::CNamespaceList *)v23, 0);
  v23[164] = 0;
  if ( !*(_DWORD *)(a6 + 8) )
  {
    CrashWithRecovery(0x1E892498u, 0);
    __debugbreak();
  }
  Ofc::CNamespaceDeclarationTracker::CNamespaceDeclarationTracker(
    (Ofc::CNamespaceDeclarationTracker *)v22,
    (struct Ofc::CNamespaceList *)v23,
    a3,
    **(_DWORD **)a6,
    1);
  v10 = 1;
  v11 = *(_DWORD *)(a6 + 8);
  if ( v11 > 1 )
  {
    while ( v10 < v11 )
    {
      Ofc::CNamespaceDeclarationTracker::AddUri(
        (Ofc::CNamespaceDeclarationTracker *)v22,
        *(_DWORD *)(*(_QWORD *)a6 + 4LL * v10++));
      v11 = *(_DWORD *)(a6 + 8);
      if ( v10 >= v11 )
        goto LABEL_7;
    }
    CrashWithRecovery(0x1E892498u, 0);
LABEL_17:
    Ofc::CHResultException::ThrowTag(v14, 0x2325D5DDu);
  }
LABEL_7:
  Art::SaveContextParam::SaveContextParam((Art::SaveContextParam *)v24);
  v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a5 + 112LL))(a5);
  Art::E2oWriterParams::E2oWriterParams(
    v25,
    v15,
    a3,
    v23,
    v12,
    a4,
    v24,
    &`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel);
  v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 32LL))(v15);
  if ( v13 < 0 )
    Ofc::CHResultException::ThrowTag(v13, 0x2325D5DEu);
  Ofc::TElemWriter<Ofc::TCompElemWriter<ODF::DocumentStyles,Ofc::TSelfAdapter<ODF::DocumentStyles>,Ofc::TSelfAdapter<ODF::DocumentStyles>>>::Write(
    v18,
    v25);
  v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 40LL))(v15);
  if ( v14 < 0 )
    goto LABEL_17;
  Art::E2oWriterParams::~E2oWriterParams((Art::E2oWriterParams *)v25);
  Ofc::CNamespaceDeclarationTracker::~CNamespaceDeclarationTracker((Ofc::CNamespaceDeclarationTracker *)v22);
  Ofc::CNamespaceList::~CNamespaceList((Ofc::CNamespaceList *)v23);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  if ( v16 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *)))(*v16)[2])(v16);
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
}

```

## disassembly

```asm
0x18016a5c4  mov     [rsp-8+arg_0], rbx
0x18016a5c9  push    rbp
0x18016a5ca  push    rsi
0x18016a5cb  push    rdi
0x18016a5cc  push    r14
0x18016a5ce  push    r15
0x18016a5d0  lea     rbp, [rsp-1200h]
0x18016a5d8  mov     eax, 1300h
0x18016a5dd  call    _alloca_probe
0x18016a5e2  sub     rsp, rax
0x18016a5e5  mov     rax, cs:__security_cookie
0x18016a5ec  xor     rax, rsp
0x18016a5ef  mov     [rbp+1220h+var_30], rax
0x18016a5f6  mov     r15, r9
0x18016a5f9  mov     rsi, r8
0x18016a5fc  mov     r14, [rbp+1220h+arg_20]
0x18016a603  mov     rdi, [rbp+1220h+arg_28]
0x18016a60a  mov     [rsp+1320h+var_12B8], rdx
0x18016a60f  mov     [rsp+1320h+var_12B0], 12Ch
0x18016a617  mov     [rsp+1320h+var_12A8], rcx
0x18016a61c  lea     rax, ??_7?$TElemWriter@V?$TCompElemWriter@VDocumentStyles@ODF@@V?$TSelfAdapter@VDocumentStyles@ODF@@@Ofc@@V34@@Ofc@@@Ofc@@6B@; const Ofc::TElemWriter<Ofc::TCompElemWriter<ODF::DocumentStyles,Ofc::TSelfAdapter<ODF::DocumentStyles>,Ofc::TSelfAdapter<ODF::DocumentStyles>>>::`vftable'
0x18016a623  mov     [rsp+1320h+var_12C8], rax
0x18016a628  lea     rax, [rsp+1320h+var_12B8]
0x18016a62d  mov     [rsp+1320h+var_12C0], rax
0x18016a632  mov     [rsp+1320h+var_12D0], 0
0x18016a63b  mov     rax, [r14]
0x18016a63e  xor     r9d, r9d
0x18016a641  lea     r8d, [r9+4]
0x18016a645  lea     rdx, [rsp+1320h+var_12D0]
0x18016a64a  mov     rcx, r14
0x18016a64d  mov     rax, [rax+60h]
0x18016a651  call    cs:__guard_dispatch_icall_fptr
0x18016a657  mov     [rsp+1320h+var_12D8], 0
0x18016a660  lea     rdx, [rsp+1320h+var_12D8]
0x18016a665  mov     rcx, [rsp+1320h+var_12D0]
0x18016a66a  call    cs:__imp_?CreateMXXMLWriter@Ofc@@YAXAEAUIStream@@AEAV?$TCntPtr@UIMXWriter@@@1@@Z; Ofc::CreateMXXMLWriter(IStream &,Ofc::TCntPtr<IMXWriter> &)
0x18016a670  mov     [rsp+1320h+var_12E0], 0
0x18016a679  mov     rcx, [rsp+1320h+var_12D8]
0x18016a67e  mov     rax, [rcx]
0x18016a681  mov     [rsp+1320h+var_12E0], 0
0x18016a68a  lea     r8, [rsp+1320h+var_12E0]
0x18016a68f  lea     rdx, _GUID_1545cdfa_9e4e_4497_a8a4_2bf7d0112c44
0x18016a696  mov     rax, [rax]
0x18016a699  call    cs:__guard_dispatch_icall_fptr
0x18016a69f  test    eax, eax
0x18016a6a1  js      loc_18016A865
0x18016a6a7  xor     edx, edx
0x18016a6a9  lea     rcx, [rbp+1220h+var_1270]
0x18016a6ad  call    cs:__imp_??0CNamespaceList@Ofc@@QEAA@PEBUCBuiltinNamespaceList@1@@Z; Ofc::CNamespaceList::CNamespaceList(Ofc::CBuiltinNamespaceList const *)
0x18016a6b3  mov     [rbp+1220h+var_11CC], 0
0x18016a6b7  cmp     dword ptr [rdi+8], 0
0x18016a6bb  ja      short loc_18016A6CB
0x18016a6bd  xor     edx, edx
0x18016a6bf  mov     ecx, 1E892498h
0x18016a6c4  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18016a6ca  int     3; Trap to Debugger
0x18016a6cb  mov     r9, [rdi]
0x18016a6ce  mov     byte ptr [rsp+1320h+var_1300], 1
0x18016a6d3  mov     r9d, [r9]
0x18016a6d6  mov     r8, rsi
0x18016a6d9  lea     rdx, [rbp+1220h+var_1270]
0x18016a6dd  lea     rcx, [rbp+1220h+var_12A0]
0x18016a6e1  call    cs:__imp_??0CNamespaceDeclarationTracker@Ofc@@QEAA@AEAVCNamespaceList@1@AEAUIMXAttributes@@H_N@Z; Ofc::CNamespaceDeclarationTracker::CNamespaceDeclarationTracker(Ofc::CNamespaceList &,IMXAttributes &,int,bool)
0x18016a6e7  mov     ebx, 1
0x18016a6ec  mov     eax, [rdi+8]
0x18016a6ef  cmp     eax, ebx
0x18016a6f1  jbe     short loc_18016A716
0x18016a6f3  cmp     ebx, eax
0x18016a6f5  jnb     loc_18016A847
0x18016a6fb  mov     eax, ebx
0x18016a6fd  mov     rdx, [rdi]
0x18016a700  mov     edx, [rdx+rax*4]
0x18016a703  lea     rcx, [rbp+1220h+var_12A0]
0x18016a707  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18016a70d  inc     ebx
0x18016a70f  mov     eax, [rdi+8]
0x18016a712  cmp     ebx, eax
0x18016a714  jb      short loc_18016A6F3
0x18016a716  lea     rcx, [rbp+1220h+var_11C0]
0x18016a71a  call    cs:__imp_??0SaveContextParam@Art@@QEAA@XZ; Art::SaveContextParam::SaveContextParam(void)
0x18016a720  mov     rax, [r14]
0x18016a723  mov     rcx, r14
0x18016a726  mov     rax, [rax+70h]
0x18016a72a  call    cs:__guard_dispatch_icall_fptr
0x18016a730  lea     rcx, ?s_pProxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4QEAV23@EA; Ofc::CProxyPtrImpl * `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_pProxyPtrSentinel
0x18016a737  mov     [rsp+1320h+var_12E8], rcx
0x18016a73c  lea     rcx, [rbp+1220h+var_11C0]
0x18016a740  mov     [rsp+1320h+var_12F0], rcx
0x18016a745  mov     [rsp+1320h+var_12F8], r15
0x18016a74a  mov     [rsp+1320h+var_1300], rax
0x18016a74f  lea     r9, [rbp+1220h+var_1270]
0x18016a753  mov     r8, rsi
0x18016a756  mov     rdx, [rsp+1320h+var_12E0]
0x18016a75b  lea     rcx, [rbp+1220h+var_11A0]
0x18016a762  call    cs:__imp_??0E2oWriterParams@Art@@QEAA@AEAUISAXContentHandler@@AEAUIMXAttributes@@AEAVCNamespaceList@Ofc@@AEAUIPart@OpenXml@Mso@@AEBV?$TSharedPtr@VBlipSaveManager@Art@@@5@AEBVSaveContextParam@1@AEBV?$TSharedPtr@VView@Art@@@5@@Z; Art::E2oWriterParams::E2oWriterParams(ISAXContentHandler &,IMXAttributes &,Ofc::CNamespaceList &,Mso::OpenXml::IPart &,Ofc::TSharedPtr<Art::BlipSaveManager> const &,Art::SaveContextParam const &,Ofc::TSharedPtr<Art::View> const &)
0x18016a768  nop
0x18016a769  mov     rcx, [rsp+1320h+var_12E0]
0x18016a76e  mov     rax, [rcx]
0x18016a771  mov     rax, [rax+20h]
0x18016a775  call    cs:__guard_dispatch_icall_fptr
0x18016a77b  test    eax, eax
0x18016a77d  js      loc_18016A875
0x18016a783  lea     rdx, [rbp+1220h+var_11A0]
0x18016a78a  lea     rcx, [rsp+1320h+var_12C8]
0x18016a78f  call    ?Write@?$TElemWriter@V?$TCompElemWriter@VDocumentStyles@ODF@@V?$TSelfAdapter@VDocumentStyles@ODF@@@Ofc@@V34@@Ofc@@@Ofc@@UEBAXAEAVIWriterParams@2@@Z; Ofc::TElemWriter<Ofc::TCompElemWriter<ODF::DocumentStyles,Ofc::TSelfAdapter<ODF::DocumentStyles>,Ofc::TSelfAdapter<ODF::DocumentStyles>>>::Write(Ofc::IWriterParams &)
0x18016a794  mov     rcx, [rsp+1320h+var_12E0]
0x18016a799  mov     rax, [rcx]
0x18016a79c  mov     rax, [rax+28h]
0x18016a7a0  call    cs:__guard_dispatch_icall_fptr
0x18016a7a6  test    eax, eax
0x18016a7a8  js      loc_18016A855
0x18016a7ae  lea     rcx, [rbp+1220h+var_11A0]
0x18016a7b5  call    cs:__imp_??1E2oWriterParams@Art@@UEAA@XZ; Art::E2oWriterParams::~E2oWriterParams(void)
0x18016a7bb  lea     rcx, [rbp+1220h+var_12A0]
0x18016a7bf  call    cs:__imp_??1CNamespaceDeclarationTracker@Ofc@@QEAA@XZ; Ofc::CNamespaceDeclarationTracker::~CNamespaceDeclarationTracker(void)
0x18016a7c5  nop     word ptr [rax+rax+00000000h]
0x18016a7d0  lea     rcx, [rbp+1220h+var_1270]
0x18016a7d4  call    cs:__imp_??1CNamespaceList@Ofc@@QEAA@XZ; Ofc::CNamespaceList::~CNamespaceList(void)
0x18016a7da  mov     rcx, [rsp+1320h+var_12E0]
0x18016a7df  test    rcx, rcx
0x18016a7e2  jz      short loc_18016A7F2
0x18016a7e4  mov     rax, [rcx]
0x18016a7e7  mov     rax, [rax+10h]
0x18016a7eb  call    cs:__guard_dispatch_icall_fptr
0x18016a7f1  nop
0x18016a7f2  mov     rcx, [rsp+1320h+var_12D8]
0x18016a7f7  test    rcx, rcx
0x18016a7fa  jz      short loc_18016A80A
0x18016a7fc  mov     rax, [rcx]
0x18016a7ff  mov     rax, [rax+10h]
0x18016a803  call    cs:__guard_dispatch_icall_fptr
0x18016a809  nop
0x18016a80a  mov     rcx, [rsp+1320h+var_12D0]
0x18016a80f  test    rcx, rcx
0x18016a812  jz      short loc_18016A821
0x18016a814  mov     rax, [rcx]
0x18016a817  mov     rax, [rax+10h]
0x18016a81b  call    cs:__guard_dispatch_icall_fptr
0x18016a821  mov     rcx, [rbp+1220h+var_30]
0x18016a828  xor     rcx, rsp; StackCookie
0x18016a82b  call    __security_check_cookie
0x18016a830  mov     rbx, [rsp+1320h+arg_0]
0x18016a838  add     rsp, 1300h
0x18016a83f  pop     r15
0x18016a841  pop     r14
0x18016a843  pop     rdi
0x18016a844  pop     rsi
0x18016a845  pop     rbp
0x18016a846  retn
0x18016a847  xor     edx, edx
0x18016a849  mov     ecx, 1E892498h
0x18016a84e  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18016a854  nop
0x18016a855  mov     edx, 2325D5DDh; unsigned int
0x18016a85a  mov     ecx, eax; int
0x18016a85c  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x18016a862  jmp     short $+2
0x18016a864  nop
0x18016a865  mov     edx, 2325D5E0h; unsigned int
0x18016a86a  mov     ecx, eax; int
0x18016a86c  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x18016a872  jmp     short $+2
0x18016a874  nop
0x18016a875  mov     edx, 2325D5DEh; unsigned int
0x18016a87a  mov     ecx, eax; int
0x18016a87c  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
```
