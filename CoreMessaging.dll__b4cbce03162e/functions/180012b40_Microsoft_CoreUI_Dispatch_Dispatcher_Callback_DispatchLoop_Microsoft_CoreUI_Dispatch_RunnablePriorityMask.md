# Microsoft::CoreUI::Dispatch::Dispatcher::Callback_DispatchLoop(Microsoft::CoreUI::Dispatch::RunnablePriorityMask)

- ea: `0x180012b40`
- end: `0x180013809`
- name: `?Callback_DispatchLoop@Dispatcher@Dispatch@CoreUI@Microsoft@@QEAA?AW4Dispatcher$LoopExitState@234@W4RunnablePriorityMask@234@@Z`
- size: `3273`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180012900`

## callees

- `0x1800058d4`
- `0x18000ec10`
- `0x180010ed0`
- `0x180012b40`
- `0x180013810`
- `0x1800139f0`
- `0x180014140`
- `0x18002e654`
- `0x18005e2f0`
- `0x180065fb0`
- `0x18008a584`
- `0x18008ae1c`
- `0x18008c1a4`
- `0x18008c9f4`
- `0x18008cab8`
- `0x18008cc78`
- `0x18008d418`
- `0x18008e39c`
- `0x18008ee90`
- `0x18008f3ec`
- `0x18008f8ac`
- `0x18009d670`
- `0x1800a61cc`
- `0x1800a623c`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012d3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012d3c`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall Microsoft::CoreUI::Dispatch::Dispatcher::Callback_DispatchLoop(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  __int64 v5; // rbx
  const char16_t *v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rsi
  __int64 v9; // rbx
  System::Object *v10; // rcx
  System::Object *v11; // rcx
  int v12; // eax
  int v13; // ecx
  unsigned int v14; // r13d
  int v15; // r9d
  unsigned int v16; // r8d
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rax
  int v19; // ecx
  int v20; // ebx
  __int64 *v21; // rax
  __int64 v22; // r15
  _DWORD *v23; // r12
  __int64 v24; // r8
  __int64 v25; // rbx
  _BYTE *v26; // rax
  System::Object *v27; // rsi
  System::Object **v28; // rax
  System::Object *v29; // rcx
  __int64 v30; // rbx
  __int64 v31; // rdi
  System::Object *v32; // rcx
  unsigned int v33; // r12d
  System::Object *v34; // rbx
  const struct CFlat::NewTagType *v35; // rdx
  __int64 v36; // rdi
  const char16_t *v37; // rcx
  const char16_t *v38; // rcx
  __int64 v39; // rdx
  char v40; // bl
  __int64 v41; // rbx
  System::Object *v42; // rcx
  System::Object *v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  System::Object *v46; // rbx
  System::Object *v47; // rcx
  unsigned int v48; // edi
  unsigned int v49; // ecx
  __int64 v50; // r8
  unsigned __int64 v51; // rax
  unsigned __int64 v52; // rax
  __int64 v53; // rcx
  int v54; // ebx
  int v55; // eax
  System::Object *v56; // rbx
  System::Object *v57; // rax
  Microsoft::CoreUI::Dispatch::EventLoop *v59; // rcx
  System::Object *v60; // rdi
  int v61; // r15d
  const char16_t *v62; // rcx
  System::Object *v63; // rdi
  __int64 v64; // rcx
  System::Object *v65; // rax
  __int64 v66; // rdx
  __int64 v67; // rbx
  int v68; // eax
  __int64 v69; // rdx
  __int64 v70; // rcx
  __int64 v71; // rax
  unsigned __int64 v72; // rax
  __int64 v73; // rdx
  __int64 v74; // rbx
  __int64 v75; // rax
  __int64 v76; // rax
  System::Object *v77; // rcx
  __int64 v78; // rcx
  const char16_t *v79; // rcx
  System::Object *v80; // rdi
  int v81; // r13d
  System::Object *v82; // rsi
  __int64 v83; // rdx
  __int64 v84; // rax
  __int64 v85; // r15
  System::Object *v86; // rcx
  System::Object *v87; // rcx
  const struct CFlat::NewTagType *v88; // rdx
  System::Object *v89; // rcx
  System::Object *v90; // rax
  System::Object *v91; // rcx
  __int64 v92; // r15
  int v93; // ecx
  const char16_t *v94; // rcx
  __int64 v95; // rdx
  const char16_t *v96; // rcx
  __int64 v97; // r8
  System::Object *v98; // r15
  int v99; // eax
  int v100; // eax
  System::Object *v101; // rcx
  void *v102; // rbx
  int i; // eax
  __int64 v104; // rcx
  __int64 v105; // rax
  __int64 v106; // r8
  System::Object *v107; // rcx
  int v108; // eax
  System::Object *v109; // rcx
  int v110; // eax
  System::Object *v111; // rcx
  _QWORD *v112; // rbx
  int v113; // edx
  int v114; // eax
  __int64 v115; // rcx
  __int64 v116; // rax
  unsigned __int8 v117; // [rsp+30h] [rbp-E8h]
  System::Object *v118; // [rsp+38h] [rbp-E0h] BYREF
  System::Object *v119; // [rsp+40h] [rbp-D8h]
  int v120; // [rsp+48h] [rbp-D0h] BYREF
  System::Object *v121; // [rsp+50h] [rbp-C8h]
  __int64 v122; // [rsp+58h] [rbp-C0h] BYREF
  System::Object *v123; // [rsp+60h] [rbp-B8h] BYREF
  System::Object *v124; // [rsp+68h] [rbp-B0h]
  System::Object *v125; // [rsp+70h] [rbp-A8h]
  _DWORD *v126; // [rsp+78h] [rbp-A0h] BYREF
  System::Object *v127; // [rsp+80h] [rbp-98h] BYREF
  __int64 v128; // [rsp+88h] [rbp-90h] BYREF
  System::Object *v129; // [rsp+90h] [rbp-88h] BYREF
  __int64 v130; // [rsp+98h] [rbp-80h]
  char v131; // [rsp+A0h] [rbp-78h]
  __int64 v132; // [rsp+A8h] [rbp-70h]
  _DWORD *v133; // [rsp+B0h] [rbp-68h]
  System::Object *v134[2]; // [rsp+B8h] [rbp-60h] BYREF
  System::Object *v135; // [rsp+C8h] [rbp-50h]
  _BYTE v136[16]; // [rsp+D0h] [rbp-48h] BYREF

  if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 0x10) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, &Dispatcher_DispatchLoop_Start, a3, 1, v134);
  v5 = *(_QWORD *)(a1 + 72);
  v6 = (const char16_t *)(unsigned int)(*(_DWORD *)(v5 + 32) + 1);
  *(_BYTE *)(a1 + 68) = (int)v6 > 0;
  if ( !*(_BYTE *)(*(_QWORD *)(a1 + 32) + 32LL) && (int)v6 > 0 )
    CFlat::Abandonment::Fail(v6);
  v121 = 0;
  v119 = 0;
  if ( v5 )
    ++*(_DWORD *)(v5 + 16);
  v7 = *(int *)(v5 + 32);
  if ( (int)v7 >= 0 )
  {
    v8 = *(_QWORD *)(v5 + 24);
    if ( (unsigned int)v7 >= *(_DWORD *)(v8 + 24) )
      CFlat::Abandonment::Fail(v6);
    v79 = (const char16_t *)(3 * v7);
    v80 = *(System::Object **)(v8 + 24 * v7 + 32);
    if ( v80 )
      ++*((_DWORD *)v80 + 4);
    v81 = *(_DWORD *)(v8 + 24 * v7 + 40);
    v82 = *(System::Object **)(v8 + 24 * v7 + 48);
    if ( v82 )
      ++*((_DWORD *)v82 + 4);
    v83 = *(_QWORD *)(v5 + 24);
    v84 = *(int *)(v5 + 32);
    if ( (unsigned int)v84 >= *(_DWORD *)(v83 + 24) )
      CFlat::Abandonment::Fail(v79);
    v85 = v83 + 24 * v84;
    v86 = *(System::Object **)(v85 + 32);
    *(_QWORD *)(v85 + 32) = 0;
    if ( v86 )
      System::Object::ReleaseNotFrozen$(v86);
    *(_DWORD *)(v85 + 40) = 0;
    v87 = *(System::Object **)(v85 + 48);
    *(_QWORD *)(v85 + 48) = 0;
    if ( v87 )
      System::Object::ReleaseNotFrozen$(v87);
    --*(_DWORD *)(v5 + 32);
    System::Object::ReleaseNotFrozen$((System::Object *)v5);
    if ( v80 )
      ++*((_DWORD *)v80 + 4);
    v89 = v121;
    v90 = v80;
    v121 = v80;
    if ( v89 )
    {
      System::Object::ReleaseNotFrozen$(v89);
      v90 = v121;
    }
    v117 = *((_BYTE *)v90 + 70);
    *(_WORD *)((char *)v90 + 69) = 0;
    if ( v82 )
      ++*((_DWORD *)v82 + 4);
    v91 = v119;
    v119 = v82;
    if ( v91 )
      System::Object::ReleaseNotFrozen$(v91);
    v92 = *(_QWORD *)(a1 + 72);
    if ( v92 )
      ++*(_DWORD *)(v92 + 16);
    if ( v80 )
      ++*((_DWORD *)v80 + 4);
    v93 = *(_DWORD *)(*(_QWORD *)(v92 + 24) + 24LL);
    if ( v93 > *(_DWORD *)(v92 + 32) + 1 )
      goto LABEL_182;
    v96 = (const char16_t *)(unsigned int)(2 * v93);
    LODWORD(v118) = (_DWORD)v96;
    if ( (unsigned int)v96 > 0x7FFFFFFF )
      CFlat::Abandonment::Fail(v96);
    v112 = System::Object::operator new(24LL * (int)v96 + 32, v88);
    v112[1] = &unk_1800D53D0;
    *((_DWORD *)v112 + 4) = 1;
    *v112 = &CFlat::Array$2<Microsoft::CoreUI::Dispatch::Dispatcher$DispatchFrame,1>::`vftable';
    *((_DWORD *)v112 + 6) = 0;
    v113 = (int)v118;
    if ( (int)v118 > 0 )
    {
      v114 = 0;
      do
      {
        v115 = 3LL * v114;
        v112[v115 + 5] = 0;
        v112[v115 + 4] = 0;
        LODWORD(v112[v115 + 5]) = 0;
        v112[v115 + 6] = 0;
        v114 = ++*((_DWORD *)v112 + 6);
      }
      while ( v114 < v113 );
    }
    v106 = (unsigned int)(*(_DWORD *)(v92 + 32) + 1);
    v107 = *(System::Object **)(v92 + 24);
    v118 = v107;
    if ( v107 && (v108 = *((_DWORD *)v107 + 4), v108 > 0) )
    {
      *((_DWORD *)v107 + 4) = v108 + 1;
      CFlat::Array$2<Microsoft::CoreUI::Dispatch::Dispatcher$DispatchFrame,1>::Copy(v107, v112, v106);
      v109 = v118;
    }
    else
    {
      CFlat::Array$2<Microsoft::CoreUI::Dispatch::Dispatcher$DispatchFrame,1>::Copy(v107, v112, v106);
      v109 = v118;
      if ( !v118 )
      {
LABEL_207:
        if ( v112 )
        {
          v110 = *((_DWORD *)v112 + 4);
          if ( v110 > 0 )
            *((_DWORD *)v112 + 4) = v110 + 1;
        }
        v111 = *(System::Object **)(v92 + 24);
        *(_QWORD *)(v92 + 24) = v112;
        if ( v111 )
          System::Object::Release$(v111);
        if ( v112 )
          System::Object::Release$((System::Object *)v112);
LABEL_182:
        v94 = (const char16_t *)*(int *)(v92 + 32);
        *(_DWORD *)(v92 + 32) = (_DWORD)v94 + 1;
        v95 = *(_QWORD *)(v92 + 24);
        if ( (unsigned int)((_DWORD)v94 + 1) >= *(_DWORD *)(v95 + 24) )
          CFlat::Abandonment::Fail(v94);
        v9 = v95 + 24LL * (_QWORD)v94;
        if ( v80 )
          ++*((_DWORD *)v80 + 4);
        v10 = *(System::Object **)(v9 + 56);
        *(_QWORD *)(v9 + 56) = v80;
        if ( v10 )
          System::Object::ReleaseNotFrozen$(v10);
        *(_DWORD *)(v9 + 64) = v81;
        v11 = *(System::Object **)(v9 + 72);
        *(_QWORD *)(v9 + 72) = 0;
        if ( v11 )
          System::Object::ReleaseNotFrozen$(v11);
        if ( v80 )
          System::Object::ReleaseNotFrozen$(v80);
        if ( v92 )
          System::Object::ReleaseNotFrozen$((System::Object *)v92);
        if ( v82 )
          System::Object::ReleaseNotFrozen$(v82);
        if ( v80 )
          System::Object::ReleaseNotFrozen$(v80);
        goto LABEL_25;
      }
    }
    System::Object::Release$(v109);
    goto LABEL_207;
  }
  System::Object::ReleaseNotFrozen$((System::Object *)v5);
  v117 = 0;
LABEL_25:
  v120 = *(_DWORD *)(a1 + 52);
  if ( a2 )
  {
    if ( a2 != 1 )
    {
      CFlat::Generics::EnumToString<int>(
        &v122,
        a2,
        &Microsoft::CoreUI::Dispatch::RunnablePriorityMask$StaticType$::TypeId$);
      System::String::Concat(&v126, &off_1800D7460, v122);
      CFlat::Abandonment::Fail(v62);
    }
    v12 = 4136;
  }
  else
  {
    v12 = 0x1FFFF;
  }
  *(_DWORD *)(a1 + 52) = v12;
  v13 = v12 & *(_DWORD *)(a1 + 48);
  v14 = 12;
  v15 = 12;
  if ( (v13 & 0xFFFF0000) != 0 )
    v15 = 28;
  v16 = v13 << 16;
  if ( (v13 & 0xFFFF0000) != 0 )
    v16 = v12 & *(_DWORD *)(a1 + 48);
  if ( (v16 & 0xFF000000) == 0 )
  {
    v16 <<= 8;
    v15 -= 8;
  }
  v17 = 16 * v16;
  if ( (v16 & 0xF0000000) != 0 )
    v17 = v16;
  v18 = v17 >> 28;
  v19 = v15 - 4;
  if ( (v16 & 0xF0000000) != 0 )
    v19 = v15;
  v20 = v19 + dword_1800E49B0[v18];
  if ( v20 < 0 )
    v20 = 0;
  if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 0x10) != 0 )
    McTemplateU0qqq_EventWriteTransfer(
      v19,
      (unsigned int)&Dispatcher_WakeLevel_UpdateWakeLevel,
      *(_DWORD *)(a1 + 48),
      *(_DWORD *)(a1 + 56),
      v20);
  *(_DWORD *)(a1 + 56) = v20;
  v21 = (__int64 *)std::initializer_list<CFlat::SmartPtr<System::Object>>::initializer_list<CFlat::SmartPtr<System::Object>>(
                     v136,
                     a1,
                     &v120);
  v131 = 0;
  v22 = *v21;
  v130 = v22;
  v132 = v22;
  v23 = (_DWORD *)v21[1];
  v126 = v23;
  v133 = v23;
  *(_DWORD *)(a1 + 104) = 0;
  *(_DWORD *)(a1 + 64) = GetCurrentThreadId();
  while ( 1 )
  {
    v25 = *(_QWORD *)(a1 + 32);
    v123 = (System::Object *)v25;
    if ( v25 )
      ++*(_DWORD *)(v25 + 16);
    v26 = *(_BYTE **)(v25 + 88);
    if ( v26
      && *v26
      && Microsoft::CoreUI::Dispatch::EventLoop::get_CanExit((Microsoft::CoreUI::Dispatch::EventLoop *)v25) )
    {
      Microsoft::CoreUI::Dispatch::EventLoop::Exit(v59, 1);
      v60 = *(System::Object **)(v25 + 168);
      v134[0] = v60;
      if ( v60 )
        ++*((_DWORD *)v60 + 4);
      (*(void (__fastcall **)(System::Object *))(*(_QWORD *)v60 + 288LL))(v60);
      if ( v60 )
        System::Object::ReleaseNotFrozen$(v60);
    }
    if ( v25 )
      System::Object::ReleaseNotFrozen$((System::Object *)v25);
    v27 = v119;
    if ( *(_QWORD *)(a1 + 80) && (*(_QWORD *)(a1 + 88) & 0x3FFFFFFFFFFFFFFFLL) != 0x2BCA2875F4373FFFLL )
    {
      System::DateTime::get_UtcNow(&v127);
      v63 = v127;
      v64 = (*(_QWORD *)(a1 + 88) & 0x3FFFFFFFFFFFFFFFLL) - ((unsigned __int64)v127 & 0x3FFFFFFFFFFFFFFFLL);
      if ( v64 <= 0 || v64 > *(_QWORD *)(a1 + 96) )
      {
        v123 = v127;
        v65 = (System::Object *)System::DateTime::ToFileTimeUtc((System::DateTime *)&v123);
        v124 = v65;
        v118 = v65;
        if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 0x10) != 0 )
          McTemplateU0tx_EventWriteTransfer(
            (unsigned int)v65,
            v66,
            1,
            (unsigned int)v65 | (unsigned __int64)v124 & 0xFFFFFFFF00000000uLL);
        v67 = *(_QWORD *)(a1 + 80);
        v134[0] = (System::Object *)v67;
        if ( v67 )
        {
          v68 = *(_DWORD *)(v67 + 16);
          if ( v68 > 0 )
            *(_DWORD *)(v67 + 16) = v68 + 1;
        }
        LOBYTE(v66) = 1;
        if ( *(_DWORD *)(v67 + 24) == 1 )
          (*(void (__fastcall **)(_QWORD, __int64, System::Object **))(v67 + 40))(*(_QWORD *)(v67 + 48), v66, &v118);
        else
          CFlat::DelegateImpl<Microsoft::CoreUI::Dispatch::DispatchCallback,0,void (bool,CFlat::Ref<Microsoft::CoreUI::Dispatch::FILETIME>),long (void *,bool,_FILETIME *),0>::MulticastInvoke(
            v67,
            v66,
            &v118);
        if ( v67 )
          System::Object::Release$((System::Object *)v67);
        if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 0x10) != 0 )
          McTemplateU0x_EventWriteTransfer(v70, v69, v118);
        System::DateTime::get_UtcNow(&v122);
        v125 = v118;
        System::DateTime::FromFileTimeUtc(&v128, v118);
        v71 = v128;
        *(_QWORD *)(a1 + 88) = v128;
        v24 = 0x3FFFFFFFFFFFFFFFLL;
        v72 = v71 & 0x3FFFFFFFFFFFFFFFLL;
        v73 = v72 - ((unsigned __int64)v63 & 0x3FFFFFFFFFFFFFFFLL);
        if ( v73 <= 0 )
        {
          if ( v73 == -1 )
          {
            *(_QWORD *)(a1 + 88) = v122;
            *(_QWORD *)(a1 + 96) = 0;
            goto LABEL_49;
          }
LABEL_221:
          *(_QWORD *)(a1 + 88) = 0x2BCA2875F4373FFFLL;
          *(_QWORD *)(a1 + 96) = 0x7FFFFFFFFFFFFFFFLL;
          goto LABEL_49;
        }
        if ( v72 >= 0x2BCA2875F4373FFFLL )
          goto LABEL_221;
        v116 = v72 - (v122 & 0x3FFFFFFFFFFFFFFFLL);
        *(_QWORD *)(a1 + 96) = v116;
        if ( v116 > v73 )
        {
          *(_QWORD *)(a1 + 96) = v73;
        }
        else if ( v116 < 0 )
        {
          *(_QWORD *)(a1 + 96) = 0;
        }
      }
      else
      {
        *(_QWORD *)(a1 + 96) = v64;
      }
    }
LABEL_49:
    v123 = v27;
    if ( v27 )
    {
      ++*((_DWORD *)v27 + 4);
      LODWORD(v31) = *((_DWORD *)v27 + 16);
    }
    else
    {
      LOBYTE(v24) = 1;
      v28 = (System::Object **)Microsoft::CoreUI::Dispatch::Dispatcher::PeekNextItem(a1, &v129, v24);
      v27 = *v28;
      *v28 = 0;
      v123 = v27;
      v29 = v129;
      if ( v129 )
        System::Object::ReleaseNotFrozen$(v129);
      if ( !v27 )
      {
        v40 = 1;
        goto LABEL_89;
      }
      v31 = *((int *)v27 + 16);
      v30 = *(_QWORD *)(a1 + 40);
      if ( (unsigned int)v31 >= *(_DWORD *)(v30 + 24) )
        CFlat::Abandonment::Fail((const char16_t *)v29);
      v74 = *(_QWORD *)(v30 + 8 * v31 + 32);
      if ( v74 )
        ++*(_DWORD *)(v74 + 16);
      v75 = *(_QWORD *)(v74 + 32);
      if ( v75 )
      {
        v76 = *(_QWORD *)(v75 + 40);
        if ( v76 )
          ++*(_DWORD *)(v76 + 16);
        v77 = *(System::Object **)(v74 + 32);
        *(_QWORD *)(v74 + 32) = v76;
        if ( v77 )
          System::Object::ReleaseNotFrozen$(v77);
      }
      v78 = *(_QWORD *)(v74 + 32);
      if ( v78 )
      {
        v32 = *(System::Object **)(v78 + 40);
        if ( v32 )
        {
          ++*((_DWORD *)v32 + 4);
          System::Object::ReleaseNotFrozen$(v32);
        }
      }
      if ( v74 )
        System::Object::ReleaseNotFrozen$((System::Object *)v74);
    }
    v33 = v31;
    v34 = *(System::Object **)(*(_QWORD *)(a1 + 32) + 168LL);
    v134[0] = v34;
    if ( v34 )
      ++*((_DWORD *)v34 + 4);
    (*(void (__fastcall **)(System::Object *, _QWORD))(*(_QWORD *)v34 + 144LL))(v34, (unsigned int)v31);
    if ( v34 )
      System::Object::ReleaseNotFrozen$(v34);
    v36 = *(_QWORD *)(a1 + 72);
    if ( v36 )
      ++*(_DWORD *)(v36 + 16);
    ++*((_DWORD *)v27 + 4);
    v37 = (const char16_t *)*(unsigned int *)(*(_QWORD *)(v36 + 24) + 24LL);
    if ( (int)v37 <= *(_DWORD *)(v36 + 32) + 1 )
    {
      v61 = 2 * (_DWORD)v37;
      if ( (unsigned int)(2 * (_DWORD)v37) > 0x7FFFFFFF )
        CFlat::Abandonment::Fail(v37);
      v102 = System::Object::operator new(24LL * v61 + 32, v35);
      *((_QWORD *)v102 + 1) = &unk_1800D53D0;
      *((_DWORD *)v102 + 4) = 1;
      *(_QWORD *)v102 = &CFlat::Array$2<Microsoft::CoreUI::Dispatch::Dispatcher$DispatchFrame,1>::`vftable';
      *((_DWORD *)v102 + 6) = 0;
      if ( v61 > 0 )
      {
        for ( i = 0; i < v61; i = *((_DWORD *)v102 + 6) )
        {
          v104 = i;
          v105 = 3LL * i;
          *((_QWORD *)v102 + v105 + 5) = 0;
          *((_QWORD *)v102 + v105 + 6) = 0;
          *((_QWORD *)v102 + v105 + 4) = 0;
          *((_DWORD *)v102 + 2 * v105 + 10) = 0;
          *((_QWORD *)v102 + 3 * v104 + 6) = 0;
          ++*((_DWORD *)v102 + 6);
        }
      }
      v97 = (unsigned int)(*(_DWORD *)(v36 + 32) + 1);
      v98 = *(System::Object **)(v36 + 24);
      if ( v98 )
      {
        v99 = *((_DWORD *)v98 + 4);
        if ( v99 > 0 )
        {
          *((_DWORD *)v98 + 4) = v99 + 1;
          CFlat::Array$2<Microsoft::CoreUI::Dispatch::Dispatcher$DispatchFrame,1>::Copy(v98, v102, v97);
          goto LABEL_189;
        }
      }
      CFlat::Array$2<Microsoft::CoreUI::Dispatch::Dispatcher$DispatchFrame,1>::Copy(*(_QWORD *)(v36 + 24), v102, v97);
      if ( v98 )
LABEL_189:
        System::Object::Release$(v98);
      if ( v102 )
      {
        v100 = *((_DWORD *)v102 + 4);
        if ( v100 > 0 )
          *((_DWORD *)v102 + 4) = v100 + 1;
      }
      v101 = *(System::Object **)(v36 + 24);
      *(_QWORD *)(v36 + 24) = v102;
      if ( v101 )
        System::Object::Release$(v101);
      if ( v102 )
        System::Object::Release$((System::Object *)v102);
    }
    v38 = (const char16_t *)*(int *)(v36 + 32);
    *(_DWORD *)(v36 + 32) = (_DWORD)v38 + 1;
    v39 = *(_QWORD *)(v36 + 24);
    if ( (unsigned int)((_DWORD)v38 + 1) >= *(_DWORD *)(v39 + 24) )
      CFlat::Abandonment::Fail(v38);
    v41 = v39 + 24LL * (_QWORD)v38;
    ++*((_DWORD *)v27 + 4);
    v42 = *(System::Object **)(v41 + 56);
    *(_QWORD *)(v41 + 56) = v27;
    if ( v42 )
      System::Object::ReleaseNotFrozen$(v42);
    *(_DWORD *)(v41 + 64) = v33;
    v43 = *(System::Object **)(v41 + 72);
    *(_QWORD *)(v41 + 72) = 0;
    if ( v43 )
      System::Object::ReleaseNotFrozen$(v43);
    System::Object::ReleaseNotFrozen$(v27);
    if ( v36 )
      System::Object::ReleaseNotFrozen$((System::Object *)v36);
    *(_WORD *)((char *)v27 + 69) = 1;
    if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 0x10) != 0 )
      McTemplateU0q_EventWriteTransfer(v44, &Dispatcher_DispatchItem_Start, v33);
    (*(void (__fastcall **)(System::Object *))(*(_QWORD *)v27 + 64LL))(v27);
    if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 0x10) != 0 )
      McTemplateU0q_EventWriteTransfer(v45, &Dispatcher_DispatchItem_Stop, v33);
    *(_WORD *)((char *)v27 + 69) = 0;
    v46 = *(System::Object **)(a1 + 72);
    if ( v46 )
      ++*((_DWORD *)v46 + 4);
    Microsoft::CoreUI::Support::Stack$1<Microsoft::CoreUI::Dispatch::Dispatcher$DispatchFrame>::Pop(v46, v134);
    if ( v135 )
      System::Object::ReleaseNotFrozen$(v135);
    if ( v134[0] )
      System::Object::ReleaseNotFrozen$(v134[0]);
    if ( v46 )
      System::Object::ReleaseNotFrozen$(v46);
    System::Object::ReleaseNotFrozen$(v27);
    v40 = 0;
    v22 = v130;
    v23 = v126;
LABEL_89:
    v47 = v119;
    v119 = 0;
    if ( v47 )
      System::Object::ReleaseNotFrozen$(v47);
    if ( v40 )
      break;
    Cn::Com::DeferredRelease::Callback_ProcessItems();
  }
  if ( !*(_BYTE *)(a1 + 68) )
    *(_DWORD *)(a1 + 64) = 0;
  v48 = *(_DWORD *)(a1 + 104);
  *(_DWORD *)(a1 + 104) = 0;
  *(_BYTE *)(a1 + 68) = *(_DWORD *)(*(_QWORD *)(a1 + 72) + 32LL) + 1 > 1;
  *(_DWORD *)(v22 + 52) = *v23;
  v49 = *(_DWORD *)(a1 + 52) & *(_DWORD *)(a1 + 48);
  if ( (v49 & 0xFFFF0000) != 0 )
    v14 = 28;
  v50 = v49 << 16;
  if ( (v49 & 0xFFFF0000) != 0 )
    v50 = v49;
  if ( (v50 & 0xFF000000) == 0 )
  {
    v50 = (unsigned int)((_DWORD)v50 << 8);
    v14 -= 8;
  }
  v51 = (unsigned int)(16 * v50);
  if ( (v50 & 0xF0000000) != 0 )
    v51 = (unsigned int)v50;
  v52 = v51 >> 28;
  v53 = v14 - 4;
  if ( (v50 & 0xF0000000) != 0 )
    v53 = v14;
  v54 = v53 + dword_1800E49B0[v52];
  if ( v54 < 0 )
    v54 = 0;
  if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 0x10) != 0 )
    McTemplateU0qqq_EventWriteTransfer(
      v53,
      (unsigned int)&Dispatcher_WakeLevel_UpdateWakeLevel,
      *(_DWORD *)(a1 + 48),
      *(_DWORD *)(a1 + 56),
      v54);
  v55 = *(_DWORD *)(a1 + 56);
  *(_DWORD *)(a1 + 56) = v54;
  if ( v54 > v55 )
  {
    ++*(_DWORD *)(a1 + 60);
    v56 = *(System::Object **)(*(_QWORD *)(a1 + 32) + 168LL);
    v134[0] = v56;
    if ( v56 )
      ++*((_DWORD *)v56 + 4);
    (*(void (__fastcall **)(System::Object *))(*(_QWORD *)v56 + 112LL))(v56);
    if ( v56 )
      System::Object::ReleaseNotFrozen$(v56);
  }
  v57 = v121;
  if ( v121 )
  {
    *((_BYTE *)v121 + 69) = 1;
    v53 = v117;
    *((_BYTE *)v57 + 70) = v117;
  }
  if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 0x10) != 0 )
    McGenEventWrite_EventWriteTransfer(v53, &Dispatcher_DispatchLoop_Stop, v50, 1, v136);
  if ( v119 )
    System::Object::ReleaseNotFrozen$(v119);
  if ( v121 )
    System::Object::ReleaseNotFrozen$(v121);
  return v48;
}

```

## disassembly

```asm
0x180012b40  mov     [rsp+arg_10], rbx
0x180012b45  mov     [rsp+arg_18], rsi
0x180012b4a  push    rdi
0x180012b4b  push    r12
0x180012b4d  push    r13
0x180012b4f  push    r14
0x180012b51  push    r15
0x180012b53  sub     rsp, 0F0h
0x180012b5a  mov     rax, cs:__security_cookie
0x180012b61  xor     rax, rsp
0x180012b64  mov     [rsp+118h+var_38], rax
0x180012b6c  mov     r12d, edx
0x180012b6f  mov     r14, rcx
0x180012b72  xor     edi, edi
0x180012b74  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits, 10h
0x180012b7b  jnz     loc_18001377F
0x180012b81  mov     rbx, [r14+48h]
0x180012b85  mov     ecx, [rbx+20h]
0x180012b88  inc     ecx; char16_t *
0x180012b8a  test    ecx, ecx
0x180012b8c  setnle  al
0x180012b8f  mov     [r14+44h], al
0x180012b93  mov     rax, [r14+20h]
0x180012b97  cmp     [rax+20h], dil
0x180012b9b  jnz     short loc_180012BA5
0x180012b9d  test    ecx, ecx
0x180012b9f  jg      loc_180013140
0x180012ba5  mov     [rsp+118h+var_C8], rdi
0x180012baa  mov     [rsp+118h+var_D8], rdi
0x180012baf  test    rbx, rbx
0x180012bb2  jz      short loc_180012BB7
0x180012bb4  inc     dword ptr [rbx+10h]
0x180012bb7  movsxd  rax, dword ptr [rbx+20h]
0x180012bbb  test    eax, eax
0x180012bbd  js      short loc_180012BD2
0x180012bbf  mov     rsi, [rbx+18h]
0x180012bc3  cmp     eax, [rsi+18h]
0x180012bc6  jb      loc_180013404
0x180012bcc  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x180012bd2  mov     rcx, rbx; this
0x180012bd5  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180012bda  mov     [rsp+118h+var_E8], 0
0x180012bdf  jmp     short loc_180012C53
0x180012be1  lea     rcx, [rcx+rcx*2]
0x180012be5  lea     rbx, [rdx+rcx*8]
0x180012be9  test    rdi, rdi
0x180012bec  jz      short loc_180012BF1
0x180012bee  inc     dword ptr [rdi+10h]
0x180012bf1  mov     rcx, [rbx+38h]; this
0x180012bf5  mov     [rbx+38h], rdi
0x180012bf9  test    rcx, rcx
0x180012bfc  jz      short loc_180012C03
0x180012bfe  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180012c03  mov     [rbx+40h], r13d
0x180012c07  mov     rcx, [rbx+48h]; this
0x180012c0b  mov     qword ptr [rbx+48h], 0
0x180012c13  test    rcx, rcx
0x180012c16  jz      short loc_180012C1D
0x180012c18  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180012c1d  test    rdi, rdi
0x180012c20  jz      short loc_180012C2A
0x180012c22  mov     rcx, rdi; this
0x180012c25  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180012c2a  test    r15, r15
0x180012c2d  jz      short loc_180012C37
0x180012c2f  mov     rcx, r15; this
0x180012c32  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180012c37  test    rsi, rsi
0x180012c3a  jz      short loc_180012C44
0x180012c3c  mov     rcx, rsi; this
0x180012c3f  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180012c44  test    rdi, rdi
0x180012c47  jz      short loc_180012C51
0x180012c49  mov     rcx, rdi; this
0x180012c4c  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180012c51  xor     edi, edi
0x180012c53  mov     eax, [r14+34h]
0x180012c57  mov     [rsp+118h+var_D0], eax
0x180012c5b  test    r12d, r12d
0x180012c5e  jnz     loc_18001312C
0x180012c64  mov     eax, 1FFFFh
0x180012c69  mov     [r14+34h], eax
0x180012c6d  mov     r10d, [r14+30h]
0x180012c71  mov     ecx, r10d
0x180012c74  and     ecx, eax
0x180012c76  test    ecx, 0FFFF0000h
0x180012c7c  mov     r13d, 0Ch
0x180012c82  mov     r9d, r13d
0x180012c85  mov     edx, 1Ch
0x180012c8a  cmovnz  r9d, edx
0x180012c8e  mov     r8d, ecx
0x180012c91  shl     r8d, 10h
0x180012c95  test    ecx, 0FFFF0000h
0x180012c9b  cmovnz  r8d, ecx
0x180012c9f  test    r8d, 0FF000000h
0x180012ca6  jnz     short loc_180012CB0
0x180012ca8  shl     r8d, 8
0x180012cac  add     r9d, 0FFFFFFF8h
0x180012cb0  mov     edx, r8d
0x180012cb3  mov     eax, r8d
0x180012cb6  shl     eax, 4
0x180012cb9  test    r8d, 0F0000000h
0x180012cc0  cmovnz  eax, r8d
0x180012cc4  shr     rax, 1Ch
0x180012cc8  lea     r8, dword_1800E49B0
0x180012ccf  lea     ecx, [r9-4]
0x180012cd3  test    edx, 0F0000000h
0x180012cd9  cmovnz  ecx, r9d
0x180012cdd  mov     ebx, [r8+rax*4]
0x180012ce1  add     ebx, ecx
0x180012ce3  cmovs   ebx, edi
0x180012ce6  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits, 10h
0x180012ced  jnz     loc_1800131F0
0x180012cf3  mov     [r14+38h], ebx
0x180012cf7  lea     r8, [rsp+118h+var_D0]
0x180012cfc  mov     rdx, r14
0x180012cff  lea     rcx, [rsp+118h+var_48]
0x180012d07  call    ??0?$initializer_list@V?$SmartPtr@VObject@System@@@CFlat@@@std@@QEAA@PEBV?$SmartPtr@VObject@System@@@CFlat@@0@Z; std::initializer_list<CFlat::SmartPtr<System::Object>>::initializer_list<CFlat::SmartPtr<System::Object>>(CFlat::SmartPtr<System::Object> const *,CFlat::SmartPtr<System::Object> const *)
0x180012d0c  mov     [rsp+118h+var_78], 0
0x180012d14  mov     r15, [rax]
0x180012d17  mov     [rsp+118h+var_80], r15
0x180012d1f  mov     [rsp+118h+var_70], r15
0x180012d27  mov     r12, [rax+8]
0x180012d2b  mov     [rsp+118h+var_A0], r12
0x180012d30  mov     [rsp+118h+var_68], r12
0x180012d38  mov     [r14+68h], edi
0x180012d3c  call    cs:__imp_GetCurrentThreadId
0x180012d42  mov     [r14+40h], eax
0x180012d46  mov     rbx, [r14+20h]
0x180012d4a  mov     [rsp+118h+var_B8], rbx
0x180012d4f  test    rbx, rbx
0x180012d52  jz      short loc_180012D57
0x180012d54  inc     dword ptr [rbx+10h]
0x180012d57  mov     rax, [rbx+58h]
0x180012d5b  test    rax, rax
0x180012d5e  jnz     loc_180013146
0x180012d64  test    rbx, rbx
0x180012d67  jz      short loc_180012D71
0x180012d69  mov     rcx, rbx; this
0x180012d6c  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180012d71  mov     rsi, [rsp+118h+var_D8]
0x180012d76  cmp     qword ptr [r14+50h], 0
0x180012d7b  jz      short loc_180012DA1
0x180012d7d  mov     rax, [r14+58h]
0x180012d81  mov     rbx, 3FFFFFFFFFFFFFFFh
0x180012d8b  and     rax, rbx
0x180012d8e  mov     rcx, 2BCA2875F4373FFFh
0x180012d98  cmp     rax, rcx
0x180012d9b  jnz     loc_180013259
0x180012da1  mov     [rsp+118h+var_B8], rsi
0x180012da6  test    rsi, rsi
0x180012da9  jz      short loc_180012DAE
0x180012dab  inc     dword ptr [rsi+10h]
0x180012dae  test    rsi, rsi
0x180012db1  jnz     short loc_180012E03
0x180012db3  mov     r8b, 1
0x180012db6  lea     rdx, [rsp+118h+var_88]
0x180012dbe  mov     rcx, r14
0x180012dc1  call    ?PeekNextItem@Dispatcher@Dispatch@CoreUI@Microsoft@@AEAA?AV?$SmartPtr@VDispatchItem@Dispatch@CoreUI@Microsoft@@@CFlat@@_N@Z; Microsoft::CoreUI::Dispatch::Dispatcher::PeekNextItem(bool)
0x180012dc6  mov     rsi, [rax]
0x180012dc9  mov     [rax], rdi
0x180012dcc  mov     [rsp+118h+var_B8], rsi
0x180012dd1  mov     rcx, [rsp+118h+var_88]; this
0x180012dd9  test    rcx, rcx
0x180012ddc  jz      short loc_180012DE3
0x180012dde  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180012de3  test    rsi, rsi
0x180012de6  jz      loc_180012EAB
0x180012dec  movsxd  rdi, dword ptr [rsi+40h]
0x180012df0  mov     rbx, [r14+28h]
0x180012df4  cmp     edi, [rbx+18h]
0x180012df7  jb      loc_1800133B3
0x180012dfd  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x180012e03  mov     edi, [rsi+40h]
0x180012e06  jmp     short loc_180012E2A
0x180012e08  mov     rcx, [rcx+28h]; this
0x180012e0c  test    rcx, rcx
0x180012e0f  jz      short loc_180012E19
0x180012e11  inc     dword ptr [rcx+10h]
0x180012e14  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180012e19  test    rbx, rbx
0x180012e1c  jz      loc_1800137FD
0x180012e22  mov     rcx, rbx; this
0x180012e25  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180012e2a  mov     r12d, edi
0x180012e2d  mov     rbx, [r14+20h]
0x180012e31  mov     rbx, [rbx+0A8h]
0x180012e38  mov     [rsp+118h+var_60], rbx
0x180012e40  test    rbx, rbx
0x180012e43  jz      short loc_180012E48
0x180012e45  inc     dword ptr [rbx+10h]
0x180012e48  mov     rax, [rbx]
0x180012e4b  mov     edx, edi
0x180012e4d  mov     rcx, rbx
0x180012e50  mov     rax, [rax+90h]
0x180012e57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e5c  nop
0x180012e5d  test    rbx, rbx
0x180012e60  jz      short loc_180012E6A
0x180012e62  mov     rcx, rbx; this
0x180012e65  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180012e6a  mov     rdi, [r14+48h]
0x180012e6e  test    rdi, rdi
0x180012e71  jz      short loc_180012E76
0x180012e73  inc     dword ptr [rdi+10h]
0x180012e76  test    rsi, rsi
0x180012e79  jz      short loc_180012E7E
0x180012e7b  inc     dword ptr [rsi+10h]
0x180012e7e  mov     rax, [rdi+18h]
0x180012e82  mov     ecx, [rax+18h]; char16_t *
0x180012e85  mov     eax, [rdi+20h]
0x180012e88  inc     eax
0x180012e8a  cmp     ecx, eax
0x180012e8c  jle     loc_1800131D9
0x180012e92  movsxd  rcx, dword ptr [rdi+20h]; char16_t *
0x180012e96  lea     eax, [rcx+1]
0x180012e99  mov     [rdi+20h], eax
0x180012e9c  mov     rdx, [rdi+18h]
0x180012ea0  cmp     eax, [rdx+18h]
0x180012ea3  jb      short loc_180012EB2
0x180012ea5  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x180012eab  mov     bl, 1
0x180012ead  jmp     loc_180012FA4
0x180012eb2  lea     rcx, [rcx+rcx*2]
0x180012eb6  lea     rbx, [rdx+rcx*8]
0x180012eba  test    rsi, rsi
0x180012ebd  jz      short loc_180012EC2
0x180012ebf  inc     dword ptr [rsi+10h]
0x180012ec2  mov     rcx, [rbx+38h]; this
0x180012ec6  mov     [rbx+38h], rsi
0x180012eca  test    rcx, rcx
0x180012ecd  jz      short loc_180012ED4
0x180012ecf  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180012ed4  mov     [rbx+40h], r12d
0x180012ed8  mov     rcx, [rbx+48h]; this
0x180012edc  mov     qword ptr [rbx+48h], 0
0x180012ee4  test    rcx, rcx
0x180012ee7  jz      short loc_180012EEE
0x180012ee9  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180012eee  test    rsi, rsi
0x180012ef1  jz      short loc_180012EFB
0x180012ef3  mov     rcx, rsi; this
0x180012ef6  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180012efb  test    rdi, rdi
0x180012efe  jz      short loc_180012F08
0x180012f00  mov     rcx, rdi; this
0x180012f03  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180012f08  mov     word ptr [rsi+45h], 1
0x180012f0e  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits, 10h
0x180012f15  jnz     loc_1800132EE
0x180012f1b  mov     rax, [rsi]
0x180012f1e  mov     rcx, rsi
0x180012f21  mov     rax, [rax+40h]
0x180012f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f2a  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits, 10h
0x180012f31  jnz     loc_18001339F
0x180012f37  mov     word ptr [rsi+45h], 0
0x180012f3d  mov     rbx, [r14+48h]
0x180012f41  test    rbx, rbx
0x180012f44  jz      short loc_180012F49
0x180012f46  inc     dword ptr [rbx+10h]
0x180012f49  lea     rdx, [rsp+118h+var_60]
0x180012f51  mov     rcx, rbx
0x180012f54  call    ?Pop@?$Stack$1@UDispatcher$DispatchFrame@Dispatch@CoreUI@Microsoft@@@Support@CoreUI@Microsoft@@QEAA?AUDispatcher$DispatchFrame@Dispatch@34@XZ; Microsoft::CoreUI::Support::Stack$1<Microsoft::CoreUI::Dispatch::Dispatcher$DispatchFrame>::Pop(void)
0x180012f59  mov     rcx, [rsp+118h+var_50]; this
0x180012f61  test    rcx, rcx
0x180012f64  jz      short loc_180012F6B
0x180012f66  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180012f6b  mov     rcx, [rsp+118h+var_60]; this
0x180012f73  test    rcx, rcx
0x180012f76  jz      short loc_180012F7D
0x180012f78  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180012f7d  test    rbx, rbx
0x180012f80  jz      short loc_180012F8B
0x180012f82  mov     rcx, rbx; this
0x180012f85  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180012f8a  nop
0x180012f8b  mov     rcx, rsi; this
0x180012f8e  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180012f93  xor     bl, bl
0x180012f95  mov     r15, [rsp+118h+var_80]
0x180012f9d  mov     r12, [rsp+118h+var_A0]
0x180012fa2  xor     edi, edi
0x180012fa4  mov     rcx, [rsp+118h+var_D8]; this
0x180012fa9  mov     [rsp+118h+var_D8], rdi
0x180012fae  test    rcx, rcx
0x180012fb1  jz      short loc_180012FB8
0x180012fb3  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180012fb8  test    bl, bl
0x180012fba  jz      loc_180013121
0x180012fc0  cmp     byte ptr [r14+44h], 0
0x180012fc5  jnz     short loc_180012FCB
0x180012fc7  mov     [r14+40h], edi
0x180012fcb  mov     edi, [r14+68h]
0x180012fcf  mov     dword ptr [r14+68h], 0
0x180012fd7  mov     rax, [r14+48h]
0x180012fdb  mov     ecx, [rax+20h]
0x180012fde  inc     ecx
0x180012fe0  cmp     ecx, 1
0x180012fe3  setnle  al
  ... truncated ...
```
