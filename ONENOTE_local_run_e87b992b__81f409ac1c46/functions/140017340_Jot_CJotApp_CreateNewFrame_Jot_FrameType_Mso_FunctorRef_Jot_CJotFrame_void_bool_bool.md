# Jot::CJotApp::CreateNewFrame(Jot::FrameType,Mso::FunctorRef<Jot::CJotFrame * (void)>,bool,bool)

- ea: `0x140017340`
- end: `0x140017859`
- name: `?CreateNewFrame@CJotApp@Jot@@AEAAPEAVCJotFrame@2@W4FrameType@2@V?$FunctorRef@$$A6APEAVCJotFrame@Jot@@XZ@Mso@@_N2@Z`
- size: `1305`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x140017288`
- `0x140079170`

## callees

- `0x14000b818`
- `0x140017340`
- `0x140017860`
- `0x14002ba28`
- `0x14002cccc`
- `0x14002e48c`
- `0x14003568c`
- `0x140057580`
- `0x14011af9c`

## import_xrefs

- `onmain!?GetNamespace@Navigation@OneNote@Office@@YAAEBUTelemetryNamespace@Telemetry@Mso@@XZ` at `0x1400176bf`
- `onmain!?GetNamespace@Navigation@OneNote@Office@@YAAEBUTelemetryNamespace@Telemetry@Mso@@XZ` at `0x1400176bf`
- `onmain!?priPageTitleVisible@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x14001745d`
- `onmain!?FQuickNotesMiniEnabled@QuickNotes@Jot@@YA_NXZ` at `0x140017586`
- `onmain!?FQuickNotesMiniEnabled@QuickNotes@Jot@@YA_NXZ` at `0x140017586`
- `onmain!?FShowQuickWindowCaptureGalleryButton@QuickNotes@Jot@@YA_NXZ` at `0x140017597`
- `onmain!?FShowQuickWindowCaptureGalleryButton@QuickNotes@Jot@@YA_NXZ` at `0x140017597`
- `onmain!?CreatePropertySet@MsoCF@@YA?AV?$CIPtr@UIPropertySet@MsoCF@@U12@@1@PEAUIPropertySet@1@@Z` at `0x140017444`
- `onmain!?CreatePropertySet@MsoCF@@YA?AV?$CIPtr@UIPropertySet@MsoCF@@U12@@1@PEAUIPropertySet@1@@Z` at `0x140017444`
- `USER32!SetFocus` at `0x1400174c6`
- `USER32!SetFocus` at `0x1400174c6`
- `Mso98Win32Client!__imp_?MsoHideCtxUI@@YAXXZ` at `0x1400173ba`
- `Mso98Win32Client!__imp_?MsoHideCtxUI@@YAXXZ` at `0x1400173ba`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1400173fe`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1400173fe`
- `Mso20Win32Client!__imp_?AsIdle@Details@Async@Mso@@YAPEAVIDispatchQueue@23@PEAV423@@Z` at `0x14001772c`
- `Mso20Win32Client!__imp_?AsIdle@Details@Async@Mso@@YAPEAVIDispatchQueue@23@PEAV423@@Z` at `0x140017802`
- `Mso20Win32Client!__imp_?AsIdle@Details@Async@Mso@@YAPEAVIDispatchQueue@23@PEAV423@@Z` at `0x14001772c`
- `Mso20Win32Client!__imp_?AsIdle@Details@Async@Mso@@YAPEAVIDispatchQueue@23@PEAV423@@Z` at `0x140017802`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400173e1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x140017722`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400177f8`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400173e1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x140017722`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400177f8`
- `Mso20Win32Client!__imp_?Post@Async@Mso@@YAXPEAVIDispatchQueue@12@$$QEAV?$Functor@$$A6AXXZ@2@@Z` at `0x140017810`
- `Mso20Win32Client!__imp_?Post@Async@Mso@@YAXPEAVIDispatchQueue@12@$$QEAV?$Functor@$$A6AXXZ@2@@Z` at `0x140017810`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x1400177cd`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x1400177cd`
- `Mso20Win32Client!__imp_?CurrentQueue@Async@Mso@@YAAEAVIDispatchQueue@12@XZ` at `0x140017710`
- `Mso20Win32Client!__imp_?CurrentQueue@Async@Mso@@YAAEAVIDispatchQueue@12@XZ` at `0x1400177e6`
- `Mso20Win32Client!__imp_?CurrentQueue@Async@Mso@@YAAEAVIDispatchQueue@12@XZ` at `0x140017710`
- `Mso20Win32Client!__imp_?CurrentQueue@Async@Mso@@YAAEAVIDispatchQueue@12@XZ` at `0x1400177e6`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x1400176b9`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x1400176b9`
- `Mso20Win32Client!__imp_?MsoFRegSetDw@@YAHPEBU_msoreg@@K@Z` at `0x1400173b4`
- `Mso20Win32Client!__imp_?MsoFRegSetDw@@YAHPEBU_msoreg@@K@Z` at `0x1400173b4`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1400177bd`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1400177bd`

## string_xrefs

- `0x1400176ca`: `CreateNewFrame`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void *__fastcall Jot::CJotApp::CreateNewFrame(__int64 a1, int a2, _QWORD *a3, char a4, char a5)
{
  __int64 v9; // rdi
  _BYTE *v11; // rcx
  char v12; // al
  char v13; // al
  HWND v14; // rax
  void *v15; // rbx
  signed int v16; // ebx
  void *const *v17; // rax
  __int64 v18; // r9
  void *v19; // rcx
  void *const *v20; // rax
  void *v21; // rcx
  int Posture; // r12d
  Jot::QuickNotes *v23; // rcx
  int v24; // ecx
  Jot::QuickNotes *v25; // rcx
  Office::OneNote::Navigation *v26; // rcx
  Mso::Async *v27; // rcx
  Mso::Async::Details *v28; // rax
  struct Mso::Async::IDispatchQueue *v29; // rdx
  __int64 (__fastcall **v30)(); // rcx
  void *const *v31; // rax
  void *const *v33; // rax
  Jot::CJotFrame *v34; // rcx
  unsigned int v35; // r8d
  void *v36; // rax
  Mso::Async *v37; // rcx
  Mso::Async::Details *v38; // rax
  struct Mso::Async::IDispatchQueue *v39; // rdx
  struct Mso::Async::IDispatchQueue *v40; // rax
  __int64 v41; // rcx
  void *const *v42; // rax
  __int16 v43; // [rsp+30h] [rbp-D0h] BYREF
  __int64 (__fastcall **v44)(); // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v45[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v46[2]; // [rsp+42h] [rbp-BEh] BYREF
  _BYTE v47[2]; // [rsp+44h] [rbp-BCh] BYREF
  __int16 v48; // [rsp+46h] [rbp-BAh] BYREF
  char v49; // [rsp+48h] [rbp-B8h]
  __int64 v50; // [rsp+50h] [rbp-B0h] BYREF
  int v51; // [rsp+58h] [rbp-A8h] BYREF
  struct Mso::Async::IDispatchQueue *v52; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v53[2]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v54[5]; // [rsp+78h] [rbp-88h] BYREF
  __int16 v55; // [rsp+A0h] [rbp-60h]
  _QWORD v56[5]; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v57; // [rsp+D0h] [rbp-30h]
  _QWORD v58[5]; // [rsp+D8h] [rbp-28h] BYREF
  __int16 v59; // [rsp+100h] [rbp+0h]
  _QWORD v60[5]; // [rsp+108h] [rbp+8h] BYREF
  __int16 v61; // [rsp+130h] [rbp+30h]
  __int64 v62; // [rsp+138h] [rbp+38h]

  v9 = 0;
  if ( *(_BYTE *)(a1 + 648) )
    return 0;
  if ( !a4 )
    goto LABEL_11;
  a5 = 0;
  while ( 1 )
  {
    v11 = *(_BYTE **)(a1 + 464);
    if ( v11 )
    {
      if ( v11[648] )
      {
        v12 = (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)v11 + 176LL))(v11);
        MsoFRegSetDw((const struct _msoreg *)&vmsoridOneNoteQuickNoteTopmost, v12 != 0);
      }
      MsoHideCtxUI();
    }
    *((_BYTE *)Jot::CJotApp::s_pSingletonJotApp + 648) = 1;
    if ( *a3 )
      break;
    CrashWithRecovery(0x25D9804u, 0);
LABEL_11:
    if ( a2 != 1 )
    {
      v13 = a5;
      goto LABEL_17;
    }
    if ( a5 )
    {
LABEL_18:
      if ( *(_QWORD *)(a1 + 480) )
      {
        if ( a2 == 1 )
        {
          MsoCF::CreatePropertySet(&v44, 0);
          LOBYTE(v43) = 1;
          (*((void (__fastcall **)(__int64 (__fastcall **)(), _QWORD, __int16 *))*v44 + 7))(
            v44,
            Jot::PropertySpace_JotMain::priPageTitleVisible,
            &v43);
          (*(void (__fastcall **)(_QWORD, __int64, __int64 (__fastcall **)(), __int64))(**(_QWORD **)(*(_QWORD *)(a1 + 480) + 104LL)
                                                                                      + 64LL))(
            *(_QWORD *)(*(_QWORD *)(a1 + 480) + 104LL),
            131731,
            v44,
            1);
          if ( v44 )
            (*((void (__fastcall **)(__int64 (__fastcall **)()))*v44 + 2))(v44);
        }
        v14 = (HWND)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(a1 + 480) + 104LL) + 120LL))(*(_QWORD *)(*(_QWORD *)(a1 + 480) + 104LL));
        SetFocus(v14);
        return *(void **)(a1 + 480);
      }
    }
    else
    {
      if ( MsoDwRegGetDw((const struct _msoreg *)&vmsoridOneNoteQuickNoteIsDocked) )
      {
        a5 = 1;
        goto LABEL_18;
      }
      v13 = 0;
      a5 = 0;
LABEL_17:
      if ( v13 )
        goto LABEL_18;
    }
  }
  v15 = (void *)(*(__int64 (__fastcall **)(_QWORD *))*a3)(a3);
  v62 = 0;
  *Ofc::CListImpl::NewTail((Ofc::CListImpl *)(a1 + 440)) = v15;
  v16 = *(_DWORD *)(a1 + 448) - 1;
  v17 = Ofc::CListImpl::IndexToItemAddr((Ofc::CListImpl *)(a1 + 440), v16);
  if ( v17 )
    v19 = *v17;
  else
    v19 = 0;
  LOBYTE(v18) = a4;
  (*(void (__fastcall **)(void *, _QWORD, _QWORD, __int64, char))(*(_QWORD *)v19 + 168LL))(
    v19,
    *(_QWORD *)(a1 + 424),
    *(_QWORD *)(a1 + 432),
    v18,
    a5);
  v20 = Ofc::CListImpl::IndexToItemAddr((Ofc::CListImpl *)(a1 + 440), v16);
  if ( v20 )
    v21 = *v20;
  else
    v21 = 0;
  Posture = Jot::CJotFrame::GetPosture(v21);
  v23 = Jot::CJotApp::s_pSingletonJotApp;
  *((_BYTE *)Jot::CJotApp::s_pSingletonJotApp + 648) = 0;
  if ( a2 == 1 )
  {
    if ( Jot::QuickNotes::FQuickNotesMiniEnabled(v23) )
      v24 = Jot::QuickNotes::FShowQuickWindowCaptureGalleryButton(v25) + 2;
    else
      v24 = 1;
  }
  else
  {
    v24 = 0;
  }
  v51 = v24;
  v54[0] = &Jot::Logging::details::StructuredTraceImplementation<int>::`vftable'{for `Mso::Logging::IStructuredTrace'};
  v54[1] = &Jot::Logging::details::StructuredTraceImplementation<int>::`vftable'{for `Mso::Telemetry::IDataField'};
  v54[2] = L"QNMVersion";
  v54[3] = -1;
  v54[4] = &v51;
  v55 = 4;
  LODWORD(v50) = Posture;
  v56[0] = &Jot::Logging::details::StructuredTraceImplementation<int>::`vftable'{for `Mso::Logging::IStructuredTrace'};
  v56[1] = &Jot::Logging::details::StructuredTraceImplementation<int>::`vftable'{for `Mso::Telemetry::IDataField'};
  v56[2] = L"Posture";
  v56[3] = -1;
  v56[4] = &v50;
  v57 = 4;
  v58[0] = &Jot::Logging::details::StructuredTraceImplementation<bool>::`vftable'{for `Mso::Logging::IStructuredTrace'};
  v58[1] = &Jot::Logging::details::StructuredTraceImplementation<bool>::`vftable'{for `Mso::Telemetry::IDataField'};
  v58[2] = L"Docked";
  v58[3] = -1;
  v58[4] = &a5;
  v59 = 4;
  LODWORD(v44) = a2;
  v60[0] = &Jot::Logging::details::StructuredTraceImplementation<int>::`vftable'{for `Mso::Logging::IStructuredTrace'};
  v60[1] = &Jot::Logging::details::StructuredTraceImplementation<int>::`vftable'{for `Mso::Telemetry::IDataField'};
  v60[2] = L"Type";
  v60[3] = -1;
  v60[4] = &v44;
  v61 = 4;
  v45[1] = 0;
  v48 = 2;
  v49 = 1;
  v46[1] = 0;
  v47[1] = 0;
  v43 = 257;
  Mso::Telemetry::EventFlags::EventFlags(&v52, &v43, v47, v46, &v48, v45);
  v53[0] = Office::OneNote::Navigation::GetNamespace(v26);
  v53[1] = "CreateNewFrame";
  Jot::Logging::SendTelemetryEvent<Jot::Logging::details::StructuredTraceKeyHolder<Jot::Logging::details::StructuredTraceImplementation<bool>,bool>,Jot::Logging::details::StructuredTraceKeyHolder<Jot::Logging::details::StructuredTraceImplementation<bool>,bool>,Jot::Logging::details::StructuredTraceKeyHolder<Jot::Logging::details::StructuredTraceImplementation<bool>,bool>,Jot::Logging::details::StructuredTraceKeyHolder<Jot::Logging::details::StructuredTraceImplementation<bool>,bool>>(
    (unsigned int)v53,
    (unsigned int)&v52,
    (unsigned int)v60,
    (unsigned int)v58,
    (__int64)v56,
    (__int64)v54);
  if ( v16 > 0 )
  {
    v44 = &off_1401D8828;
    v28 = Mso::Async::CurrentQueue(v27);
    if ( !v28 )
      CrashWithRecovery(0x110B458u, 0);
    v52 = Mso::Async::Details::AsIdle(v28, v29);
    Mso::Async::PostTimer<Mso::Async::IDispatchQueue *>(3500, &v52, &v44);
    v30 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*((void (__fastcall **)(__int64 (__fastcall **)()))*v30 + 2))(v30);
    }
  }
  if ( !*(_QWORD *)(a1 + 488) )
  {
    v31 = Ofc::CListImpl::IndexToItemAddr((Ofc::CListImpl *)(a1 + 440), v16);
    if ( v31 ? *v31 : 0LL )
    {
      v33 = Ofc::CListImpl::IndexToItemAddr((Ofc::CListImpl *)(a1 + 440), v16);
      v34 = v33 ? (Jot::CJotFrame *)*v33 : 0LL;
      if ( Jot::CJotFrame::CanSupportInAppPane(v34) )
      {
        LODWORD(v44) = v16;
        v36 = Mso::Memory::AllocateEx((Mso::Memory *)0x18, 0, v35);
        if ( !v36 )
        {
          CrashWithRecoveryOnOOM(0x131F462u);
          __debugbreak();
        }
        v50 = sub_14002BA28(v36, &v44);
        v38 = Mso::Async::CurrentQueue(v37);
        if ( !v38 )
          CrashWithRecovery(0x110B458u, 0);
        v40 = Mso::Async::Details::AsIdle(v38, v39);
        Mso::Async::Post(v40, &v50);
        v41 = v50;
        if ( v50 )
        {
          v50 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
        }
      }
    }
  }
  v42 = Ofc::CListImpl::IndexToItemAddr((Ofc::CListImpl *)(a1 + 440), v16);
  if ( v42 )
    return *v42;
  return (void *)v9;
}

```

## disassembly

```asm
0x140017340  push    rbp
0x140017342  push    rbx
0x140017343  push    rsi
0x140017344  push    rdi
0x140017345  push    r12
0x140017347  push    r14
0x140017349  push    r15
0x14001734b  lea     rbp, [rsp-40h]
0x140017350  sub     rsp, 140h
0x140017357  mov     r12b, r9b
0x14001735a  mov     rbx, r8
0x14001735d  mov     r15d, edx
0x140017360  mov     rsi, rcx
0x140017363  xor     edi, edi
0x140017365  cmp     [rcx+288h], dil
0x14001736c  jz      short loc_140017375
0x14001736e  xor     eax, eax
0x140017370  jmp     loc_140017847
0x140017375  test    r12b, r12b
0x140017378  jz      short loc_1400173E8
0x14001737a  mov     [rbp+70h+arg_20], dil
0x140017381  mov     rcx, [rsi+1D0h]
0x140017388  test    rcx, rcx
0x14001738b  jz      short loc_1400173C0
0x14001738d  cmp     [rcx+288h], dil
0x140017394  jz      short loc_1400173BA
0x140017396  mov     rax, [rcx]
0x140017399  mov     rax, [rax+0B0h]
0x1400173a0  call    cs:__guard_dispatch_icall_fptr
0x1400173a6  mov     edx, edi
0x1400173a8  test    al, al
0x1400173aa  setnz   dl
0x1400173ad  lea     rcx, ?vmsoridOneNoteQuickNoteTopmost@@3U_msoreg@@B; _msoreg const vmsoridOneNoteQuickNoteTopmost
0x1400173b4  call    cs:__imp_?MsoFRegSetDw@@YAHPEBU_msoreg@@K@Z; MsoFRegSetDw(_msoreg const *,ulong)
0x1400173ba  call    cs:__imp_?MsoHideCtxUI@@YAXXZ; MsoHideCtxUI(void)
0x1400173c0  mov     rax, cs:?s_pSingletonJotApp@CJotApp@Jot@@0PEAV12@EA; Jot::CJotApp * Jot::CJotApp::s_pSingletonJotApp
0x1400173c7  mov     byte ptr [rax+288h], 1
0x1400173ce  mov     rax, [rbx]
0x1400173d1  test    rax, rax
0x1400173d4  jnz     loc_1400174D8
0x1400173da  xor     edx, edx
0x1400173dc  mov     ecx, 25D9804h
0x1400173e1  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1400173e7  nop
0x1400173e8  cmp     r15d, 1
0x1400173ec  jnz     short loc_14001741C
0x1400173ee  cmp     [rbp+70h+arg_20], dil
0x1400173f5  jnz     short loc_14001742A
0x1400173f7  lea     rcx, ?vmsoridOneNoteQuickNoteIsDocked@@3U_msoreg@@B; _msoreg const vmsoridOneNoteQuickNoteIsDocked
0x1400173fe  call    cs:__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z; MsoDwRegGetDw(_msoreg const *)
0x140017404  test    eax, eax
0x140017406  jz      short loc_140017411
0x140017408  mov     [rbp+70h+arg_20], r15b
0x14001740f  jmp     short loc_14001742A
0x140017411  mov     al, dil
0x140017414  mov     [rbp+70h+arg_20], al
0x14001741a  jmp     short loc_140017422
0x14001741c  mov     al, [rbp+70h+arg_20]
0x140017422  test    al, al
0x140017424  jz      loc_140017381
0x14001742a  cmp     [rsi+1E0h], rdi
0x140017431  jz      loc_140017381
0x140017437  cmp     r15d, 1
0x14001743b  jnz     short loc_1400174AB
0x14001743d  xor     edx, edx
0x14001743f  lea     rcx, [rsp+170h+var_138]
0x140017444  call    cs:__imp_?CreatePropertySet@MsoCF@@YA?AV?$CIPtr@UIPropertySet@MsoCF@@U12@@1@PEAUIPropertySet@1@@Z; MsoCF::CreatePropertySet(MsoCF::IPropertySet *)
0x14001744a  nop
0x14001744b  mov     byte ptr [rsp+170h+var_140], r15b
0x140017450  mov     rcx, [rsp+170h+var_138]
0x140017455  mov     rax, [rcx]
0x140017458  lea     r8, [rsp+170h+var_140]
0x14001745d  mov     rdx, cs:__imp_?priPageTitleVisible@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_JotMain::priPageTitleVisible
0x140017464  mov     rax, [rax+38h]
0x140017468  call    cs:__guard_dispatch_icall_fptr
0x14001746e  mov     rax, [rsi+1E0h]
0x140017475  mov     rcx, [rax+68h]
0x140017479  mov     rax, [rcx]
0x14001747c  mov     r9d, r15d
0x14001747f  mov     r8, [rsp+170h+var_138]
0x140017484  mov     edx, 20293h
0x140017489  mov     rax, [rax+40h]
0x14001748d  call    cs:__guard_dispatch_icall_fptr
0x140017493  nop
0x140017494  mov     rcx, [rsp+170h+var_138]
0x140017499  test    rcx, rcx
0x14001749c  jz      short loc_1400174AB
0x14001749e  mov     rax, [rcx]
0x1400174a1  mov     rax, [rax+10h]
0x1400174a5  call    cs:__guard_dispatch_icall_fptr
0x1400174ab  mov     rax, [rsi+1E0h]
0x1400174b2  mov     rcx, [rax+68h]
0x1400174b6  mov     rax, [rcx]
0x1400174b9  mov     rax, [rax+78h]
0x1400174bd  call    cs:__guard_dispatch_icall_fptr
0x1400174c3  mov     rcx, rax; hWnd
0x1400174c6  call    cs:__imp_SetFocus
0x1400174cc  mov     rax, [rsi+1E0h]
0x1400174d3  jmp     loc_140017847
0x1400174d8  mov     rcx, rbx
0x1400174db  mov     rax, [rax]
0x1400174de  call    cs:__guard_dispatch_icall_fptr
0x1400174e4  mov     rbx, rax
0x1400174e7  lea     r14, [rsi+1B8h]
0x1400174ee  mov     rcx, r14; this
0x1400174f1  call    ?NewTail@CListImpl@Ofc@@IEAAPEAPEAXXZ; Ofc::CListImpl::NewTail(void)
0x1400174f6  mov     [rbp+70h+var_38], rdi
0x1400174fa  mov     [rax], rbx
0x1400174fd  mov     ebx, [rsi+1C0h]
0x140017503  dec     ebx
0x140017505  mov     edx, ebx; unsigned int
0x140017507  mov     rcx, r14; this
0x14001750a  call    ?IndexToItemAddr@CListImpl@Ofc@@IEBAPEBQEAXK@Z; Ofc::CListImpl::IndexToItemAddr(ulong)
0x14001750f  test    rax, rax
0x140017512  jz      short loc_140017519
0x140017514  mov     rcx, [rax]
0x140017517  jmp     short loc_14001751C
0x140017519  mov     rcx, rdi
0x14001751c  mov     rax, [rcx]
0x14001751f  mov     r10b, [rbp+70h+arg_20]
0x140017526  mov     byte ptr [rsp+170h+var_150], r10b
0x14001752b  mov     r9b, r12b
0x14001752e  mov     r8, [rsi+1B0h]
0x140017535  mov     rdx, [rsi+1A8h]
0x14001753c  mov     rax, [rax+0A8h]
0x140017543  call    cs:__guard_dispatch_icall_fptr
0x140017549  mov     edx, ebx; unsigned int
0x14001754b  mov     rcx, r14; this
0x14001754e  call    ?IndexToItemAddr@CListImpl@Ofc@@IEBAPEBQEAXK@Z; Ofc::CListImpl::IndexToItemAddr(ulong)
0x140017553  test    rax, rax
0x140017556  jz      short loc_14001755D
0x140017558  mov     rcx, [rax]
0x14001755b  jmp     short loc_140017560
0x14001755d  mov     rcx, rdi
0x140017560  call    ?GetPosture@CJotFrame@Jot@@QEBA?AW4JotFramePosture@2@XZ; Jot::CJotFrame::GetPosture(void)
0x140017565  mov     r12d, eax
0x140017568  mov     rcx, cs:?s_pSingletonJotApp@CJotApp@Jot@@0PEAV12@EA; Jot::CJotApp * Jot::CJotApp::s_pSingletonJotApp
0x14001756f  mov     [rcx+288h], dil
0x140017576  cmp     r15d, 1
0x14001757a  jz      short loc_140017586
0x14001757c  mov     ecx, edi
0x14001757e  mov     r10d, 2
0x140017584  jmp     short loc_1400175AC
0x140017586  call    cs:__imp_?FQuickNotesMiniEnabled@QuickNotes@Jot@@YA_NXZ; Jot::QuickNotes::FQuickNotesMiniEnabled(void)
0x14001758c  test    al, al
0x14001758e  jnz     short loc_140017597
0x140017590  mov     ecx, 1
0x140017595  jmp     short loc_14001757E
0x140017597  call    cs:__imp_?FShowQuickWindowCaptureGalleryButton@QuickNotes@Jot@@YA_NXZ; Jot::QuickNotes::FShowQuickWindowCaptureGalleryButton(void)
0x14001759d  neg     al
0x14001759f  sbb     ecx, ecx
0x1400175a1  neg     ecx
0x1400175a3  mov     r10d, 2
0x1400175a9  add     ecx, r10d
0x1400175ac  mov     [rsp+170h+var_118], ecx
0x1400175b0  lea     r9, ??_7?$StructuredTraceImplementation@H@details@Logging@Jot@@6BIStructuredTrace@2Mso@@@; const Jot::Logging::details::StructuredTraceImplementation<int>::`vftable'{for `Mso::Logging::IStructuredTrace'}
0x1400175b7  mov     [rsp+170h+var_F8], r9
0x1400175bc  lea     r8, ??_7?$StructuredTraceImplementation@H@details@Logging@Jot@@6BIDataField@Telemetry@Mso@@@; const Jot::Logging::details::StructuredTraceImplementation<int>::`vftable'{for `Mso::Telemetry::IDataField'}
0x1400175c3  mov     [rbp+70h+var_F0], r8
0x1400175c7  lea     rax, aQnmversion; "QNMVersion"
0x1400175ce  mov     [rbp+70h+var_E8], rax
0x1400175d2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400175d6  mov     [rbp+70h+var_E0], rcx
0x1400175da  lea     rax, [rsp+170h+var_118]
0x1400175df  mov     [rbp+70h+var_D8], rax
0x1400175e3  lea     edx, [rcx+5]
0x1400175e6  mov     [rbp+70h+var_D0], dx
0x1400175ea  mov     dword ptr [rsp+170h+var_120], r12d
0x1400175ef  mov     [rbp+70h+var_C8], r9
0x1400175f3  mov     [rbp+70h+var_C0], r8
0x1400175f7  lea     rax, aPosture; "Posture"
0x1400175fe  mov     [rbp+70h+var_B8], rax
0x140017602  mov     [rbp+70h+var_B0], rcx
0x140017606  lea     rax, [rsp+170h+var_120]
0x14001760b  mov     [rbp+70h+var_A8], rax
0x14001760f  mov     [rbp+70h+var_A0], dx
0x140017613  lea     rax, ??_7?$StructuredTraceImplementation@_N@details@Logging@Jot@@6BIStructuredTrace@2Mso@@@; const Jot::Logging::details::StructuredTraceImplementation<bool>::`vftable'{for `Mso::Logging::IStructuredTrace'}
0x14001761a  mov     [rbp+70h+var_98], rax
0x14001761e  lea     rax, ??_7?$StructuredTraceImplementation@_N@details@Logging@Jot@@6BIDataField@Telemetry@Mso@@@; const Jot::Logging::details::StructuredTraceImplementation<bool>::`vftable'{for `Mso::Telemetry::IDataField'}
0x140017625  mov     [rbp+70h+var_90], rax
0x140017629  lea     rax, aDocked; "Docked"
0x140017630  mov     [rbp+70h+var_88], rax
0x140017634  mov     [rbp+70h+var_80], rcx
0x140017638  lea     rax, [rbp+70h+arg_20]
0x14001763f  mov     [rbp+70h+var_78], rax
0x140017643  mov     [rbp+70h+var_70], dx
0x140017647  mov     dword ptr [rsp+170h+var_138], r15d
0x14001764c  mov     [rbp+70h+var_68], r9
0x140017650  mov     [rbp+70h+var_60], r8
0x140017654  lea     rax, aType; "Type"
0x14001765b  mov     [rbp+70h+var_58], rax
0x14001765f  mov     [rbp+70h+var_50], rcx
0x140017663  lea     rax, [rsp+170h+var_138]
0x140017668  mov     [rbp+70h+var_48], rax
0x14001766c  mov     [rbp+70h+var_40], dx
0x140017670  mov     [rsp+170h+var_12F], dil
0x140017675  mov     [rsp+170h+var_12A], r10w
0x14001767b  mov     [rsp+170h+var_128], 1
0x140017680  mov     [rsp+170h+var_12D], dil
0x140017685  mov     [rsp+170h+var_12B], dil
0x14001768a  mov     [rsp+170h+var_140], 101h
0x140017691  lea     rax, [rsp+170h+var_130]
0x140017696  mov     [rsp+170h+var_148], rax
0x14001769b  lea     rax, [rsp+170h+var_12A]
0x1400176a0  mov     [rsp+170h+var_150], rax
0x1400176a5  lea     r9, [rsp+170h+var_12E]
0x1400176aa  lea     r8, [rsp+170h+var_12C]
0x1400176af  lea     rdx, [rsp+170h+var_140]
0x1400176b4  lea     rcx, [rsp+170h+var_110]
0x1400176b9  call    cs:__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z; Mso::Telemetry::EventFlags::EventFlags(std::optional<Mso::Telemetry::SamplingPolicy> const &,std::optional<Mso::Telemetry::PersistencePriority> const &,std::optional<Mso::Telemetry::CostPriority> const &,std::optional<Mso::Telemetry::DataCategories> const &,std::optional<Mso::Telemetry::DiagnosticLevel> const &)
0x1400176bf  call    cs:__imp_?GetNamespace@Navigation@OneNote@Office@@YAAEBUTelemetryNamespace@Telemetry@Mso@@XZ; Office::OneNote::Navigation::GetNamespace(void)
0x1400176c5  mov     [rsp+170h+var_108], rax
0x1400176ca  lea     rax, aCreatenewframe; "CreateNewFrame"
0x1400176d1  mov     [rsp+170h+var_100], rax
0x1400176d6  lea     rax, [rsp+170h+var_F8]
0x1400176db  mov     [rsp+170h+var_148], rax
0x1400176e0  lea     rax, [rbp+70h+var_C8]
0x1400176e4  mov     [rsp+170h+var_150], rax
0x1400176e9  lea     r9, [rbp+70h+var_98]
0x1400176ed  lea     r8, [rbp+70h+var_68]
0x1400176f1  lea     rdx, [rsp+170h+var_110]
0x1400176f6  lea     rcx, [rsp+170h+var_108]
0x1400176fb  call    ??$SendTelemetryEvent@U?$StructuredTraceKeyHolder@U?$StructuredTraceImplementation@_N@details@Logging@Jot@@_N@details@Logging@Jot@@U1234@U1234@U1234@@Logging@Jot@@YAXAEBUEventName@Telemetry@Mso@@AEBUEventFlags@34@$$QEAU?$StructuredTraceKeyHolder@U?$StructuredTraceImplementation@_N@details@Logging@Jot@@_N@details@01@222@Z; Jot::Logging::SendTelemetryEvent<Jot::Logging::details::StructuredTraceKeyHolder<Jot::Logging::details::StructuredTraceImplementation<bool>,bool>,Jot::Logging::details::StructuredTraceKeyHolder<Jot::Logging::details::StructuredTraceImplementation<bool>,bool>,Jot::Logging::details::StructuredTraceKeyHolder<Jot::Logging::details::StructuredTraceImplementation<bool>,bool>,Jot::Logging::details::StructuredTraceKeyHolder<Jot::Logging::details::StructuredTraceImplementation<bool>,bool>>(Mso::Telemetry::EventName const &,Mso::Telemetry::EventFlags const &,Jot::Logging::details::StructuredTraceKeyHolder<Jot::Logging::details::StructuredTraceImplementation<bool>,bool> &&,Jot::Logging::details::StructuredTraceKeyHolder<Jot::Logging::details::StructuredTraceImplementation<bool>,bool> &&,Jot::Logging::details::StructuredTraceKeyHolder<Jot::Logging::details::StructuredTraceImplementation<bool>,bool> &&,Jot::Logging::details::StructuredTraceKeyHolder<Jot::Logging::details::StructuredTraceImplementation<bool>,bool> &&)
0x140017700  test    ebx, ebx
0x140017702  jle     short loc_140017767
0x140017704  lea     rax, off_1401D8828
0x14001770b  mov     [rsp+170h+var_138], rax
0x140017710  call    cs:__imp_?CurrentQueue@Async@Mso@@YAAEAVIDispatchQueue@12@XZ; Mso::Async::CurrentQueue(void)
0x140017716  test    rax, rax
0x140017719  jnz     short loc_140017729
0x14001771b  xor     edx, edx
0x14001771d  mov     ecx, 110B458h
0x140017722  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x140017728  nop
0x140017729  mov     rcx, rax
0x14001772c  call    cs:__imp_?AsIdle@Details@Async@Mso@@YAPEAVIDispatchQueue@23@PEAV423@@Z; Mso::Async::Details::AsIdle(Mso::Async::IDispatchQueue *)
0x140017732  mov     [rsp+170h+var_110], rax
0x140017737  lea     r8, [rsp+170h+var_138]
0x14001773c  lea     rdx, [rsp+170h+var_110]
0x140017741  mov     ecx, 0DACh
0x140017746  call    ??$PostTimer@PEAVIDispatchQueue@Async@Mso@@@Async@Mso@@YAXI$$QEAPEAVIDispatchQueue@01@$$QEAV?$Functor@$$A6AXXZ@1@@Z; Mso::Async::PostTimer<Mso::Async::IDispatchQueue *>(uint,Mso::Async::IDispatchQueue * &&,Mso::Functor<void (void)> &&)
0x14001774b  mov     rcx, [rsp+170h+var_138]
0x140017750  test    rcx, rcx
0x140017753  jz      short loc_140017767
0x140017755  mov     [rsp+170h+var_138], rdi
0x14001775a  mov     rax, [rcx]
0x14001775d  mov     rax, [rax+10h]
0x140017761  call    cs:__guard_dispatch_icall_fptr
0x140017767  cmp     [rsi+1E8h], rdi
0x14001776e  jnz     loc_140017832
0x140017774  mov     edx, ebx; unsigned int
0x140017776  mov     rcx, r14; this
0x140017779  call    ?IndexToItemAddr@CListImpl@Ofc@@IEBAPEBQEAXK@Z; Ofc::CListImpl::IndexToItemAddr(ulong)
0x14001777e  test    rax, rax
0x140017781  jz      short loc_140017788
0x140017783  mov     rax, [rax]
0x140017786  jmp     short loc_14001778B
0x140017788  mov     rax, rdi
0x14001778b  test    rax, rax
0x14001778e  jz      loc_140017832
0x140017794  mov     edx, ebx; unsigned int
0x140017796  mov     rcx, r14; this
0x140017799  call    ?IndexToItemAddr@CListImpl@Ofc@@IEBAPEBQEAXK@Z; Ofc::CListImpl::IndexToItemAddr(ulong)
0x14001779e  test    rax, rax
0x1400177a1  jz      short loc_1400177A8
0x1400177a3  mov     rcx, [rax]
0x1400177a6  jmp     short loc_1400177AB
0x1400177a8  mov     rcx, rdi; this
0x1400177ab  call    ?CanSupportInAppPane@CJotFrame@Jot@@QEBA_NXZ; Jot::CJotFrame::CanSupportInAppPane(void)
0x1400177b0  test    al, al
0x1400177b2  jz      short loc_140017832
0x1400177b4  mov     dword ptr [rsp+170h+var_138], ebx
0x1400177b8  xor     edx, edx
0x1400177ba  lea     ecx, [rdx+18h]
0x1400177bd  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x1400177c3  test    rax, rax
0x1400177c6  jnz     short loc_1400177D4
0x1400177c8  mov     ecx, 131F462h
0x1400177cd  call    cs:__imp_?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
0x1400177d3  int     3; Trap to Debugger
0x1400177d4  lea     rdx, [rsp+170h+var_138]
0x1400177d9  mov     rcx, rax
0x1400177dc  call    sub_14002BA28
0x1400177e1  mov     [rsp+170h+var_120], rax
0x1400177e6  call    cs:__imp_?CurrentQueue@Async@Mso@@YAAEAVIDispatchQueue@12@XZ; Mso::Async::CurrentQueue(void)
0x1400177ec  test    rax, rax
0x1400177ef  jnz     short loc_1400177FF
0x1400177f1  xor     edx, edx
0x1400177f3  mov     ecx, 110B458h
0x1400177f8  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1400177fe  nop
0x1400177ff  mov     rcx, rax
0x140017802  call    cs:__imp_?AsIdle@Details@Async@Mso@@YAPEAVIDispatchQueue@23@PEAV423@@Z; Mso::Async::Details::AsIdle(Mso::Async::IDispatchQueue *)
0x140017808  lea     rdx, [rsp+170h+var_120]
0x14001780d  mov     rcx, rax
0x140017810  call    cs:__imp_?Post@Async@Mso@@YAXPEAVIDispatchQueue@12@$$QEAV?$Functor@$$A6AXXZ@2@@Z; Mso::Async::Post(Mso::Async::IDispatchQueue *,Mso::Functor<void (void)> &&)
0x140017816  mov     rcx, [rsp+170h+var_120]
0x14001781b  test    rcx, rcx
0x14001781e  jz      short loc_140017832
0x140017820  mov     [rsp+170h+var_120], rdi
  ... truncated ...
```
