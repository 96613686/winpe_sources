# Art::OdfFunctions::WriteOdpContent(ODF::DocumentContent &,wchar_t const *,IMXAttributes &,Ofc::TSharedPtr<Art::BlipSaveManager> const &,Metro::Part &,Ofc::TArray<Mso::Xsd::Namespaces::NamespaceUriToken> const &)

- ea: `0x18016a054`
- end: `0x18016a30a`
- name: `?WriteOdpContent@OdfFunctions@Art@@SAXAEAVDocumentContent@ODF@@PEB_WAEAUIMXAttributes@@AEBV?$TSharedPtr@VBlipSaveManager@Art@@@Ofc@@AEAVPart@Metro@@AEBV?$TArray@W4NamespaceUriToken@Namespaces@Xsd@Mso@@@7@@Z_0`
- size: `694`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180170ac0`

## callees

- `0x1800025a0`
- `0x180007898`
- `0x18016a054`
- `0x180170940`
- `0x1801a8060`
- `0x1801a80e0`

## import_xrefs

- `oart!__imp_??0SaveContextParam@Art@@QEAA@XZ` at `0x18016a1aa`
- `oart!__imp_??0SaveContextParam@Art@@QEAA@XZ` at `0x18016a1aa`
- `oart!__imp_??1E2oWriterParams@Art@@UEAA@XZ` at `0x18016a245`
- `oart!__imp_??1E2oWriterParams@Art@@UEAA@XZ` at `0x18016a245`
- `oart!__imp_??0E2oWriterParams@Art@@QEAA@AEAUISAXContentHandler@@AEAUIMXAttributes@@AEAVCNamespaceList@Ofc@@AEAUIPart@OpenXml@Mso@@AEBV?$TSharedPtr@VBlipSaveManager@Art@@@5@AEBVSaveContextParam@1@AEBV?$TSharedPtr@VView@Art@@@5@@Z` at `0x18016a1f2`
- `oart!__imp_??0E2oWriterParams@Art@@QEAA@AEAUISAXContentHandler@@AEAUIMXAttributes@@AEAVCNamespaceList@Ofc@@AEAUIPart@OpenXml@Mso@@AEBV?$TSharedPtr@VBlipSaveManager@Art@@@5@AEBVSaveContextParam@1@AEBV?$TSharedPtr@VView@Art@@@5@@Z` at `0x18016a1f2`
- `mso40uiWin32Client!__imp_??1CNamespaceList@Ofc@@QEAA@XZ` at `0x18016a259`
- `mso40uiWin32Client!__imp_??1CNamespaceList@Ofc@@QEAA@XZ` at `0x18016a259`
- `mso40uiWin32Client!__imp_?CreateMXXMLWriter@Ofc@@YAXAEAUIStream@@AEAV?$TCntPtr@UIMXWriter@@@1@@Z` at `0x18016a0fa`
- `mso40uiWin32Client!__imp_?CreateMXXMLWriter@Ofc@@YAXAEAUIStream@@AEAV?$TCntPtr@UIMXWriter@@@1@@Z` at `0x18016a0fa`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18016a197`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18016a197`
- `mso40uiWin32Client!__imp_??1CNamespaceDeclarationTracker@Ofc@@QEAA@XZ` at `0x18016a24f`
- `mso40uiWin32Client!__imp_??1CNamespaceDeclarationTracker@Ofc@@QEAA@XZ` at `0x18016a24f`
- `mso40uiWin32Client!__imp_??0CNamespaceList@Ofc@@QEAA@PEBUCBuiltinNamespaceList@1@@Z` at `0x18016a13d`
- `mso40uiWin32Client!__imp_??0CNamespaceList@Ofc@@QEAA@PEBUCBuiltinNamespaceList@1@@Z` at `0x18016a13d`
- `mso40uiWin32Client!__imp_??0CNamespaceDeclarationTracker@Ofc@@QEAA@AEAVCNamespaceList@1@AEAUIMXAttributes@@H_N@Z` at `0x18016a171`
- `mso40uiWin32Client!__imp_??0CNamespaceDeclarationTracker@Ofc@@QEAA@AEAVCNamespaceList@1@AEAUIMXAttributes@@H_N@Z` at `0x18016a171`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18016a154`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18016a2d3`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18016a154`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18016a2d3`

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
  v18[0] = &Ofc::TElemWriter<Ofc::TCompElemWriter<ODF::DocumentContent,Ofc::TSelfAdapter<ODF::DocumentContent>,Ofc::TSelfAdapter<ODF::DocumentContent>>>::`vftable';
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
  Ofc::TElemWriter<Ofc::TCompElemWriter<ODF::DocumentContent,Ofc::TSelfAdapter<ODF::DocumentContent>,Ofc::TSelfAdapter<ODF::DocumentContent>>>::Write(
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
0x18016a054  mov     [rsp-8+arg_0], rbx
0x18016a059  push    rbp
0x18016a05a  push    rsi
0x18016a05b  push    rdi
0x18016a05c  push    r14
0x18016a05e  push    r15
0x18016a060  lea     rbp, [rsp-1200h]
0x18016a068  mov     eax, 1300h
0x18016a06d  call    _alloca_probe
0x18016a072  sub     rsp, rax
0x18016a075  mov     rax, cs:__security_cookie
0x18016a07c  xor     rax, rsp
0x18016a07f  mov     [rbp+1220h+var_30], rax
0x18016a086  mov     r15, r9
0x18016a089  mov     rsi, r8
0x18016a08c  mov     r14, [rbp+1220h+arg_20]
0x18016a093  mov     rdi, [rbp+1220h+arg_28]
0x18016a09a  mov     [rsp+1320h+var_12B8], rdx
0x18016a09f  mov     [rsp+1320h+var_12B0], 12Ch
0x18016a0a7  mov     [rsp+1320h+var_12A8], rcx
0x18016a0ac  lea     rax, ??_7?$TElemWriter@V?$TCompElemWriter@VDocumentContent@ODF@@V?$TSelfAdapter@VDocumentContent@ODF@@@Ofc@@V34@@Ofc@@@Ofc@@6B@; const Ofc::TElemWriter<Ofc::TCompElemWriter<ODF::DocumentContent,Ofc::TSelfAdapter<ODF::DocumentContent>,Ofc::TSelfAdapter<ODF::DocumentContent>>>::`vftable'
0x18016a0b3  mov     [rsp+1320h+var_12C8], rax
0x18016a0b8  lea     rax, [rsp+1320h+var_12B8]
0x18016a0bd  mov     [rsp+1320h+var_12C0], rax
0x18016a0c2  mov     [rsp+1320h+var_12D0], 0
0x18016a0cb  mov     rax, [r14]
0x18016a0ce  xor     r9d, r9d
0x18016a0d1  lea     r8d, [r9+4]
0x18016a0d5  lea     rdx, [rsp+1320h+var_12D0]
0x18016a0da  mov     rcx, r14
0x18016a0dd  mov     rax, [rax+60h]
0x18016a0e1  call    cs:__guard_dispatch_icall_fptr
0x18016a0e7  mov     [rsp+1320h+var_12D8], 0
0x18016a0f0  lea     rdx, [rsp+1320h+var_12D8]
0x18016a0f5  mov     rcx, [rsp+1320h+var_12D0]
0x18016a0fa  call    cs:__imp_?CreateMXXMLWriter@Ofc@@YAXAEAUIStream@@AEAV?$TCntPtr@UIMXWriter@@@1@@Z; Ofc::CreateMXXMLWriter(IStream &,Ofc::TCntPtr<IMXWriter> &)
0x18016a100  mov     [rsp+1320h+var_12E0], 0
0x18016a109  mov     rcx, [rsp+1320h+var_12D8]
0x18016a10e  mov     rax, [rcx]
0x18016a111  mov     [rsp+1320h+var_12E0], 0
0x18016a11a  lea     r8, [rsp+1320h+var_12E0]
0x18016a11f  lea     rdx, _GUID_1545cdfa_9e4e_4497_a8a4_2bf7d0112c44
0x18016a126  mov     rax, [rax]
0x18016a129  call    cs:__guard_dispatch_icall_fptr
0x18016a12f  test    eax, eax
0x18016a131  js      loc_18016A2EA
0x18016a137  xor     edx, edx
0x18016a139  lea     rcx, [rbp+1220h+var_1270]
0x18016a13d  call    cs:__imp_??0CNamespaceList@Ofc@@QEAA@PEBUCBuiltinNamespaceList@1@@Z; Ofc::CNamespaceList::CNamespaceList(Ofc::CBuiltinNamespaceList const *)
0x18016a143  mov     [rbp+1220h+var_11CC], 0
0x18016a147  cmp     dword ptr [rdi+8], 0
0x18016a14b  ja      short loc_18016A15B
0x18016a14d  xor     edx, edx
0x18016a14f  mov     ecx, 1E892498h
0x18016a154  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18016a15a  int     3; Trap to Debugger
0x18016a15b  mov     r9, [rdi]
0x18016a15e  mov     byte ptr [rsp+1320h+var_1300], 1
0x18016a163  mov     r9d, [r9]
0x18016a166  mov     r8, rsi
0x18016a169  lea     rdx, [rbp+1220h+var_1270]
0x18016a16d  lea     rcx, [rbp+1220h+var_12A0]
0x18016a171  call    cs:__imp_??0CNamespaceDeclarationTracker@Ofc@@QEAA@AEAVCNamespaceList@1@AEAUIMXAttributes@@H_N@Z; Ofc::CNamespaceDeclarationTracker::CNamespaceDeclarationTracker(Ofc::CNamespaceList &,IMXAttributes &,int,bool)
0x18016a177  mov     ebx, 1
0x18016a17c  mov     eax, [rdi+8]
0x18016a17f  cmp     eax, ebx
0x18016a181  jbe     short loc_18016A1A6
0x18016a183  cmp     ebx, eax
0x18016a185  jnb     loc_18016A2CC
0x18016a18b  mov     eax, ebx
0x18016a18d  mov     rdx, [rdi]
0x18016a190  mov     edx, [rdx+rax*4]
0x18016a193  lea     rcx, [rbp+1220h+var_12A0]
0x18016a197  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18016a19d  inc     ebx
0x18016a19f  mov     eax, [rdi+8]
0x18016a1a2  cmp     ebx, eax
0x18016a1a4  jb      short loc_18016A183
0x18016a1a6  lea     rcx, [rbp+1220h+var_11C0]
0x18016a1aa  call    cs:__imp_??0SaveContextParam@Art@@QEAA@XZ; Art::SaveContextParam::SaveContextParam(void)
0x18016a1b0  mov     rax, [r14]
0x18016a1b3  mov     rcx, r14
0x18016a1b6  mov     rax, [rax+70h]
0x18016a1ba  call    cs:__guard_dispatch_icall_fptr
0x18016a1c0  lea     rcx, ?s_pProxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4QEAV23@EA; Ofc::CProxyPtrImpl * `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_pProxyPtrSentinel
0x18016a1c7  mov     [rsp+1320h+var_12E8], rcx
0x18016a1cc  lea     rcx, [rbp+1220h+var_11C0]
0x18016a1d0  mov     [rsp+1320h+var_12F0], rcx
0x18016a1d5  mov     [rsp+1320h+var_12F8], r15
0x18016a1da  mov     [rsp+1320h+var_1300], rax
0x18016a1df  lea     r9, [rbp+1220h+var_1270]
0x18016a1e3  mov     r8, rsi
0x18016a1e6  mov     rdx, [rsp+1320h+var_12E0]
0x18016a1eb  lea     rcx, [rbp+1220h+var_11A0]
0x18016a1f2  call    cs:__imp_??0E2oWriterParams@Art@@QEAA@AEAUISAXContentHandler@@AEAUIMXAttributes@@AEAVCNamespaceList@Ofc@@AEAUIPart@OpenXml@Mso@@AEBV?$TSharedPtr@VBlipSaveManager@Art@@@5@AEBVSaveContextParam@1@AEBV?$TSharedPtr@VView@Art@@@5@@Z; Art::E2oWriterParams::E2oWriterParams(ISAXContentHandler &,IMXAttributes &,Ofc::CNamespaceList &,Mso::OpenXml::IPart &,Ofc::TSharedPtr<Art::BlipSaveManager> const &,Art::SaveContextParam const &,Ofc::TSharedPtr<Art::View> const &)
0x18016a1f8  nop
0x18016a1f9  mov     rcx, [rsp+1320h+var_12E0]
0x18016a1fe  mov     rax, [rcx]
0x18016a201  mov     rax, [rax+20h]
0x18016a205  call    cs:__guard_dispatch_icall_fptr
0x18016a20b  test    eax, eax
0x18016a20d  js      loc_18016A2FD
0x18016a213  lea     rdx, [rbp+1220h+var_11A0]
0x18016a21a  lea     rcx, [rsp+1320h+var_12C8]
0x18016a21f  call    ?Write@?$TElemWriter@V?$TCompElemWriter@VDocumentContent@ODF@@V?$TSelfAdapter@VDocumentContent@ODF@@@Ofc@@V34@@Ofc@@@Ofc@@UEBAXAEAVIWriterParams@2@@Z; Ofc::TElemWriter<Ofc::TCompElemWriter<ODF::DocumentContent,Ofc::TSelfAdapter<ODF::DocumentContent>,Ofc::TSelfAdapter<ODF::DocumentContent>>>::Write(Ofc::IWriterParams &)
0x18016a224  mov     rcx, [rsp+1320h+var_12E0]
0x18016a229  mov     rax, [rcx]
0x18016a22c  mov     rax, [rax+28h]
0x18016a230  call    cs:__guard_dispatch_icall_fptr
0x18016a236  test    eax, eax
0x18016a238  js      loc_18016A2DA
0x18016a23e  lea     rcx, [rbp+1220h+var_11A0]
0x18016a245  call    cs:__imp_??1E2oWriterParams@Art@@UEAA@XZ; Art::E2oWriterParams::~E2oWriterParams(void)
0x18016a24b  lea     rcx, [rbp+1220h+var_12A0]
0x18016a24f  call    cs:__imp_??1CNamespaceDeclarationTracker@Ofc@@QEAA@XZ; Ofc::CNamespaceDeclarationTracker::~CNamespaceDeclarationTracker(void)
0x18016a255  lea     rcx, [rbp+1220h+var_1270]
0x18016a259  call    cs:__imp_??1CNamespaceList@Ofc@@QEAA@XZ; Ofc::CNamespaceList::~CNamespaceList(void)
0x18016a25f  mov     rcx, [rsp+1320h+var_12E0]
0x18016a264  test    rcx, rcx
0x18016a267  jz      short loc_18016A277
0x18016a269  mov     rax, [rcx]
0x18016a26c  mov     rax, [rax+10h]
0x18016a270  call    cs:__guard_dispatch_icall_fptr
0x18016a276  nop
0x18016a277  mov     rcx, [rsp+1320h+var_12D8]
0x18016a27c  test    rcx, rcx
0x18016a27f  jz      short loc_18016A28F
0x18016a281  mov     rax, [rcx]
0x18016a284  mov     rax, [rax+10h]
0x18016a288  call    cs:__guard_dispatch_icall_fptr
0x18016a28e  nop
0x18016a28f  mov     rcx, [rsp+1320h+var_12D0]
0x18016a294  test    rcx, rcx
0x18016a297  jz      short loc_18016A2A6
0x18016a299  mov     rax, [rcx]
0x18016a29c  mov     rax, [rax+10h]
0x18016a2a0  call    cs:__guard_dispatch_icall_fptr
0x18016a2a6  mov     rcx, [rbp+1220h+var_30]
0x18016a2ad  xor     rcx, rsp; StackCookie
0x18016a2b0  call    __security_check_cookie
0x18016a2b5  mov     rbx, [rsp+1320h+arg_0]
0x18016a2bd  add     rsp, 1300h
0x18016a2c4  pop     r15
0x18016a2c6  pop     r14
0x18016a2c8  pop     rdi
0x18016a2c9  pop     rsi
0x18016a2ca  pop     rbp
0x18016a2cb  retn
0x18016a2cc  xor     edx, edx
0x18016a2ce  mov     ecx, 1E892498h
0x18016a2d3  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18016a2d9  nop
0x18016a2da  mov     edx, 2325D5DDh; unsigned int
0x18016a2df  mov     ecx, eax; int
0x18016a2e1  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x18016a2e7  jmp     short $+2
0x18016a2e9  nop
0x18016a2ea  mov     edx, 2325D5E0h; unsigned int
0x18016a2ef  mov     ecx, eax; int
0x18016a2f1  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x18016a2f7  jmp     short loc_18016A2FC
0x18016a2fc  nop
0x18016a2fd  mov     edx, 2325D5DEh; unsigned int
0x18016a302  mov     ecx, eax; int
0x18016a304  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
```
