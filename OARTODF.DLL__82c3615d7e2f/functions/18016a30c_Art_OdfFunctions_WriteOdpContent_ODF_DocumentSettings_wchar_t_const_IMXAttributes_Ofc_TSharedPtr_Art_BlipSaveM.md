# Art::OdfFunctions::WriteOdpContent(ODF::DocumentSettings &,wchar_t const *,IMXAttributes &,Ofc::TSharedPtr<Art::BlipSaveManager> const &,Metro::Part &,Ofc::TArray<Mso::Xsd::Namespaces::NamespaceUriToken> const &)

- ea: `0x18016a30c`
- end: `0x18016a5c2`
- name: `?WriteOdpContent@OdfFunctions@Art@@SAXAEAVDocumentSettings@ODF@@PEB_WAEAUIMXAttributes@@AEBV?$TSharedPtr@VBlipSaveManager@Art@@@Ofc@@AEAVPart@Metro@@AEBV?$TArray@W4NamespaceUriToken@Namespaces@Xsd@Mso@@@7@@Z_0`
- size: `694`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180170ad0`

## callees

- `0x1800025a0`
- `0x180007898`
- `0x18016a30c`
- `0x1801709c0`
- `0x1801a8060`
- `0x1801a80e0`

## import_xrefs

- `oart!__imp_??0SaveContextParam@Art@@QEAA@XZ` at `0x18016a462`
- `oart!__imp_??0SaveContextParam@Art@@QEAA@XZ` at `0x18016a462`
- `oart!__imp_??1E2oWriterParams@Art@@UEAA@XZ` at `0x18016a4fd`
- `oart!__imp_??1E2oWriterParams@Art@@UEAA@XZ` at `0x18016a4fd`
- `oart!__imp_??0E2oWriterParams@Art@@QEAA@AEAUISAXContentHandler@@AEAUIMXAttributes@@AEAVCNamespaceList@Ofc@@AEAUIPart@OpenXml@Mso@@AEBV?$TSharedPtr@VBlipSaveManager@Art@@@5@AEBVSaveContextParam@1@AEBV?$TSharedPtr@VView@Art@@@5@@Z` at `0x18016a4aa`
- `oart!__imp_??0E2oWriterParams@Art@@QEAA@AEAUISAXContentHandler@@AEAUIMXAttributes@@AEAVCNamespaceList@Ofc@@AEAUIPart@OpenXml@Mso@@AEBV?$TSharedPtr@VBlipSaveManager@Art@@@5@AEBVSaveContextParam@1@AEBV?$TSharedPtr@VView@Art@@@5@@Z` at `0x18016a4aa`
- `mso40uiWin32Client!__imp_??1CNamespaceList@Ofc@@QEAA@XZ` at `0x18016a511`
- `mso40uiWin32Client!__imp_??1CNamespaceList@Ofc@@QEAA@XZ` at `0x18016a511`
- `mso40uiWin32Client!__imp_?CreateMXXMLWriter@Ofc@@YAXAEAUIStream@@AEAV?$TCntPtr@UIMXWriter@@@1@@Z` at `0x18016a3b2`
- `mso40uiWin32Client!__imp_?CreateMXXMLWriter@Ofc@@YAXAEAUIStream@@AEAV?$TCntPtr@UIMXWriter@@@1@@Z` at `0x18016a3b2`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18016a44f`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x18016a44f`
- `mso40uiWin32Client!__imp_??1CNamespaceDeclarationTracker@Ofc@@QEAA@XZ` at `0x18016a507`
- `mso40uiWin32Client!__imp_??1CNamespaceDeclarationTracker@Ofc@@QEAA@XZ` at `0x18016a507`
- `mso40uiWin32Client!__imp_??0CNamespaceList@Ofc@@QEAA@PEBUCBuiltinNamespaceList@1@@Z` at `0x18016a3f5`
- `mso40uiWin32Client!__imp_??0CNamespaceList@Ofc@@QEAA@PEBUCBuiltinNamespaceList@1@@Z` at `0x18016a3f5`
- `mso40uiWin32Client!__imp_??0CNamespaceDeclarationTracker@Ofc@@QEAA@AEAVCNamespaceList@1@AEAUIMXAttributes@@H_N@Z` at `0x18016a429`
- `mso40uiWin32Client!__imp_??0CNamespaceDeclarationTracker@Ofc@@QEAA@AEAVCNamespaceList@1@AEAUIMXAttributes@@H_N@Z` at `0x18016a429`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18016a40c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18016a58c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18016a40c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18016a58c`

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
  v18[0] = &Ofc::TElemWriter<Ofc::TCompElemWriter<ODF::DocumentSettings,Ofc::TSelfAdapter<ODF::DocumentSettings>,Ofc::TSelfAdapter<ODF::DocumentSettings>>>::`vftable';
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
  Ofc::TElemWriter<Ofc::TCompElemWriter<ODF::DocumentSettings,Ofc::TSelfAdapter<ODF::DocumentSettings>,Ofc::TSelfAdapter<ODF::DocumentSettings>>>::Write(
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
0x18016a30c  mov     [rsp-8+arg_0], rbx
0x18016a311  push    rbp
0x18016a312  push    rsi
0x18016a313  push    rdi
0x18016a314  push    r14
0x18016a316  push    r15
0x18016a318  lea     rbp, [rsp-1200h]
0x18016a320  mov     eax, 1300h
0x18016a325  call    _alloca_probe
0x18016a32a  sub     rsp, rax
0x18016a32d  mov     rax, cs:__security_cookie
0x18016a334  xor     rax, rsp
0x18016a337  mov     [rbp+1220h+var_30], rax
0x18016a33e  mov     r15, r9
0x18016a341  mov     rsi, r8
0x18016a344  mov     r14, [rbp+1220h+arg_20]
0x18016a34b  mov     rdi, [rbp+1220h+arg_28]
0x18016a352  mov     [rsp+1320h+var_12B8], rdx
0x18016a357  mov     [rsp+1320h+var_12B0], 12Ch
0x18016a35f  mov     [rsp+1320h+var_12A8], rcx
0x18016a364  lea     rax, ??_7?$TElemWriter@V?$TCompElemWriter@VDocumentSettings@ODF@@V?$TSelfAdapter@VDocumentSettings@ODF@@@Ofc@@V34@@Ofc@@@Ofc@@6B@; const Ofc::TElemWriter<Ofc::TCompElemWriter<ODF::DocumentSettings,Ofc::TSelfAdapter<ODF::DocumentSettings>,Ofc::TSelfAdapter<ODF::DocumentSettings>>>::`vftable'
0x18016a36b  mov     [rsp+1320h+var_12C8], rax
0x18016a370  lea     rax, [rsp+1320h+var_12B8]
0x18016a375  mov     [rsp+1320h+var_12C0], rax
0x18016a37a  mov     [rsp+1320h+var_12D0], 0
0x18016a383  mov     rax, [r14]
0x18016a386  xor     r9d, r9d
0x18016a389  lea     r8d, [r9+4]
0x18016a38d  lea     rdx, [rsp+1320h+var_12D0]
0x18016a392  mov     rcx, r14
0x18016a395  mov     rax, [rax+60h]
0x18016a399  call    cs:__guard_dispatch_icall_fptr
0x18016a39f  mov     [rsp+1320h+var_12D8], 0
0x18016a3a8  lea     rdx, [rsp+1320h+var_12D8]
0x18016a3ad  mov     rcx, [rsp+1320h+var_12D0]
0x18016a3b2  call    cs:__imp_?CreateMXXMLWriter@Ofc@@YAXAEAUIStream@@AEAV?$TCntPtr@UIMXWriter@@@1@@Z; Ofc::CreateMXXMLWriter(IStream &,Ofc::TCntPtr<IMXWriter> &)
0x18016a3b8  mov     [rsp+1320h+var_12E0], 0
0x18016a3c1  mov     rcx, [rsp+1320h+var_12D8]
0x18016a3c6  mov     rax, [rcx]
0x18016a3c9  mov     [rsp+1320h+var_12E0], 0
0x18016a3d2  lea     r8, [rsp+1320h+var_12E0]
0x18016a3d7  lea     rdx, _GUID_1545cdfa_9e4e_4497_a8a4_2bf7d0112c44
0x18016a3de  mov     rax, [rax]
0x18016a3e1  call    cs:__guard_dispatch_icall_fptr
0x18016a3e7  test    eax, eax
0x18016a3e9  js      loc_18016A5A3
0x18016a3ef  xor     edx, edx
0x18016a3f1  lea     rcx, [rbp+1220h+var_1270]
0x18016a3f5  call    cs:__imp_??0CNamespaceList@Ofc@@QEAA@PEBUCBuiltinNamespaceList@1@@Z; Ofc::CNamespaceList::CNamespaceList(Ofc::CBuiltinNamespaceList const *)
0x18016a3fb  mov     [rbp+1220h+var_11CC], 0
0x18016a3ff  cmp     dword ptr [rdi+8], 0
0x18016a403  ja      short loc_18016A413
0x18016a405  xor     edx, edx
0x18016a407  mov     ecx, 1E892498h
0x18016a40c  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18016a412  int     3; Trap to Debugger
0x18016a413  mov     r9, [rdi]
0x18016a416  mov     byte ptr [rsp+1320h+var_1300], 1
0x18016a41b  mov     r9d, [r9]
0x18016a41e  mov     r8, rsi
0x18016a421  lea     rdx, [rbp+1220h+var_1270]
0x18016a425  lea     rcx, [rbp+1220h+var_12A0]
0x18016a429  call    cs:__imp_??0CNamespaceDeclarationTracker@Ofc@@QEAA@AEAVCNamespaceList@1@AEAUIMXAttributes@@H_N@Z; Ofc::CNamespaceDeclarationTracker::CNamespaceDeclarationTracker(Ofc::CNamespaceList &,IMXAttributes &,int,bool)
0x18016a42f  mov     ebx, 1
0x18016a434  mov     eax, [rdi+8]
0x18016a437  cmp     eax, ebx
0x18016a439  jbe     short loc_18016A45E
0x18016a43b  cmp     ebx, eax
0x18016a43d  jnb     loc_18016A585
0x18016a443  mov     eax, ebx
0x18016a445  mov     rdx, [rdi]
0x18016a448  mov     edx, [rdx+rax*4]
0x18016a44b  lea     rcx, [rbp+1220h+var_12A0]
0x18016a44f  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x18016a455  inc     ebx
0x18016a457  mov     eax, [rdi+8]
0x18016a45a  cmp     ebx, eax
0x18016a45c  jb      short loc_18016A43B
0x18016a45e  lea     rcx, [rbp+1220h+var_11C0]
0x18016a462  call    cs:__imp_??0SaveContextParam@Art@@QEAA@XZ; Art::SaveContextParam::SaveContextParam(void)
0x18016a468  mov     rax, [r14]
0x18016a46b  mov     rcx, r14
0x18016a46e  mov     rax, [rax+70h]
0x18016a472  call    cs:__guard_dispatch_icall_fptr
0x18016a478  lea     rcx, ?s_pProxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4QEAV23@EA; Ofc::CProxyPtrImpl * `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_pProxyPtrSentinel
0x18016a47f  mov     [rsp+1320h+var_12E8], rcx
0x18016a484  lea     rcx, [rbp+1220h+var_11C0]
0x18016a488  mov     [rsp+1320h+var_12F0], rcx
0x18016a48d  mov     [rsp+1320h+var_12F8], r15
0x18016a492  mov     [rsp+1320h+var_1300], rax
0x18016a497  lea     r9, [rbp+1220h+var_1270]
0x18016a49b  mov     r8, rsi
0x18016a49e  mov     rdx, [rsp+1320h+var_12E0]
0x18016a4a3  lea     rcx, [rbp+1220h+var_11A0]
0x18016a4aa  call    cs:__imp_??0E2oWriterParams@Art@@QEAA@AEAUISAXContentHandler@@AEAUIMXAttributes@@AEAVCNamespaceList@Ofc@@AEAUIPart@OpenXml@Mso@@AEBV?$TSharedPtr@VBlipSaveManager@Art@@@5@AEBVSaveContextParam@1@AEBV?$TSharedPtr@VView@Art@@@5@@Z; Art::E2oWriterParams::E2oWriterParams(ISAXContentHandler &,IMXAttributes &,Ofc::CNamespaceList &,Mso::OpenXml::IPart &,Ofc::TSharedPtr<Art::BlipSaveManager> const &,Art::SaveContextParam const &,Ofc::TSharedPtr<Art::View> const &)
0x18016a4b0  nop
0x18016a4b1  mov     rcx, [rsp+1320h+var_12E0]
0x18016a4b6  mov     rax, [rcx]
0x18016a4b9  mov     rax, [rax+20h]
0x18016a4bd  call    cs:__guard_dispatch_icall_fptr
0x18016a4c3  test    eax, eax
0x18016a4c5  js      loc_18016A5B5
0x18016a4cb  lea     rdx, [rbp+1220h+var_11A0]
0x18016a4d2  lea     rcx, [rsp+1320h+var_12C8]
0x18016a4d7  call    ?Write@?$TElemWriter@V?$TCompElemWriter@VDocumentSettings@ODF@@V?$TSelfAdapter@VDocumentSettings@ODF@@@Ofc@@V34@@Ofc@@@Ofc@@UEBAXAEAVIWriterParams@2@@Z; Ofc::TElemWriter<Ofc::TCompElemWriter<ODF::DocumentSettings,Ofc::TSelfAdapter<ODF::DocumentSettings>,Ofc::TSelfAdapter<ODF::DocumentSettings>>>::Write(Ofc::IWriterParams &)
0x18016a4dc  mov     rcx, [rsp+1320h+var_12E0]
0x18016a4e1  mov     rax, [rcx]
0x18016a4e4  mov     rax, [rax+28h]
0x18016a4e8  call    cs:__guard_dispatch_icall_fptr
0x18016a4ee  test    eax, eax
0x18016a4f0  js      loc_18016A593
0x18016a4f6  lea     rcx, [rbp+1220h+var_11A0]
0x18016a4fd  call    cs:__imp_??1E2oWriterParams@Art@@UEAA@XZ; Art::E2oWriterParams::~E2oWriterParams(void)
0x18016a503  lea     rcx, [rbp+1220h+var_12A0]
0x18016a507  call    cs:__imp_??1CNamespaceDeclarationTracker@Ofc@@QEAA@XZ; Ofc::CNamespaceDeclarationTracker::~CNamespaceDeclarationTracker(void)
0x18016a50d  lea     rcx, [rbp+1220h+var_1270]
0x18016a511  call    cs:__imp_??1CNamespaceList@Ofc@@QEAA@XZ; Ofc::CNamespaceList::~CNamespaceList(void)
0x18016a517  mov     rcx, [rsp+1320h+var_12E0]
0x18016a51c  test    rcx, rcx
0x18016a51f  jz      short loc_18016A530
0x18016a521  mov     rax, [rcx]
0x18016a524  mov     rax, [rax+10h]
0x18016a528  call    cs:__guard_dispatch_icall_fptr
0x18016a52e  nop
0x18016a52f  nop
0x18016a530  mov     rcx, [rsp+1320h+var_12D8]
0x18016a535  test    rcx, rcx
0x18016a538  jz      short loc_18016A548
0x18016a53a  mov     rax, [rcx]
0x18016a53d  mov     rax, [rax+10h]
0x18016a541  call    cs:__guard_dispatch_icall_fptr
0x18016a547  nop
0x18016a548  mov     rcx, [rsp+1320h+var_12D0]
0x18016a54d  test    rcx, rcx
0x18016a550  jz      short loc_18016A55F
0x18016a552  mov     rax, [rcx]
0x18016a555  mov     rax, [rax+10h]
0x18016a559  call    cs:__guard_dispatch_icall_fptr
0x18016a55f  mov     rcx, [rbp+1220h+var_30]
0x18016a566  xor     rcx, rsp; StackCookie
0x18016a569  call    __security_check_cookie
0x18016a56e  mov     rbx, [rsp+1320h+arg_0]
0x18016a576  add     rsp, 1300h
0x18016a57d  pop     r15
0x18016a57f  pop     r14
0x18016a581  pop     rdi
0x18016a582  pop     rsi
0x18016a583  pop     rbp
0x18016a584  retn
0x18016a585  xor     edx, edx
0x18016a587  mov     ecx, 1E892498h
0x18016a58c  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18016a592  nop
0x18016a593  mov     edx, 2325D5DDh; unsigned int
0x18016a598  mov     ecx, eax; int
0x18016a59a  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x18016a5a0  jmp     short $+2
0x18016a5a2  nop
0x18016a5a3  mov     edx, 2325D5E0h; unsigned int
0x18016a5a8  mov     ecx, eax; int
0x18016a5aa  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x18016a5b0  jmp     short loc_18016A5B4
0x18016a5b4  nop
0x18016a5b5  mov     edx, 2325D5DEh; unsigned int
0x18016a5ba  mov     ecx, eax; int
0x18016a5bc  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
```
