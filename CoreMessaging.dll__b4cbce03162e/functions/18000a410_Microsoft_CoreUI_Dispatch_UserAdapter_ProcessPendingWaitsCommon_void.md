# Microsoft::CoreUI::Dispatch::UserAdapter::ProcessPendingWaitsCommon(void)

- ea: `0x18000a410`
- end: `0x18000a8dd`
- name: `?ProcessPendingWaitsCommon@UserAdapter@Dispatch@CoreUI@Microsoft@@AEAA_NXZ`
- size: `1229`
- prototype: `bool __fastcall(Microsoft::CoreUI::Dispatch::UserAdapter *__hidden this)`
- caller_count: `3`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180008bb4`
- `0x180009820`
- `0x180009dc0`

## callees

- `0x18000a410`
- `0x18000a8e4`
- `0x18000a98c`
- `0x18000b130`
- `0x18000ec10`
- `0x180010ed0`
- `0x180026bd0`
- `0x18002dbdc`
- `0x18002df84`
- `0x18002e030`
- `0x18002e50c`
- `0x18008ae1c`
- `0x18008cb30`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a4ad`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a628`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a6f4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a4ad`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a628`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a6f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Microsoft::CoreUI::Dispatch::UserAdapter::ProcessPendingWaitsCommon(
        Microsoft::CoreUI::Dispatch::UserAdapter *this)
{
  __int64 v1; // rdi
  struct Cn::Engine::GCHandleLocalEntry *v2; // rbx
  unsigned __int8 v3; // di
  struct _TEB *v4; // rbx
  __int64 SpareUlong0; // rax
  SIZE_T v6; // rbx
  __int64 v7; // rax
  char16_t *v8; // rcx
  char16_t *v9; // rbx
  __int64 v11; // rsi
  char16_t *v12; // r15
  char16_t *v13; // rax
  System::Object *v14; // rcx
  System::Object *v15; // rcx
  System::Object *v16; // rbx
  System::Object *v17; // rcx
  char *Value; // rax
  System::Object *v19; // rcx
  int v20; // eax
  System::Object *v21; // rcx
  System::Object *v22; // r12
  System::Object *v23; // rdi
  __int64 v24; // rbx
  System::Object *v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // r14
  __int64 v28; // rsi
  System::Object *v29; // rbx
  System::Object *v30; // r15
  System::Object *v31; // rax
  __int64 v32; // r13
  System::Object *v33; // rdi
  System::Object *v34; // rbx
  System::Object *v35; // rax
  System::Object *v36; // rcx
  System::Object *v37; // rcx
  System::Object *v38; // rbx
  __int64 *v39; // rax
  __int64 v40; // rdx
  System::Object *v41; // rcx
  System::Object *v42; // [rsp+20h] [rbp-49h] BYREF
  int v43; // [rsp+28h] [rbp-41h]
  __int64 v44; // [rsp+30h] [rbp-39h]
  __int64 v45; // [rsp+38h] [rbp-31h]
  char v46; // [rsp+40h] [rbp-29h]
  __int128 v47; // [rsp+48h] [rbp-21h]
  System::Object *v48; // [rsp+58h] [rbp-11h] BYREF
  System::Object *v49; // [rsp+60h] [rbp-9h] BYREF
  System::Object *v50; // [rsp+68h] [rbp-1h] BYREF
  char16_t *v51; // [rsp+70h] [rbp+7h]
  __int64 v52; // [rsp+78h] [rbp+Fh]
  System::Object *v53; // [rsp+D0h] [rbp+67h] BYREF
  struct Cn::Engine::GCHandleLocalEntry *v54; // [rsp+D8h] [rbp+6Fh] BYREF
  System::Object *v55; // [rsp+E0h] [rbp+77h] BYREF
  System::Object *v56; // [rsp+E8h] [rbp+7Fh] BYREF

  v1 = *(_QWORD *)(*((_QWORD *)this + 4) + 32LL);
  v53 = (System::Object *)v1;
  if ( v1 )
    ++*(_DWORD *)(v1 + 16);
  v2 = *(struct Cn::Engine::GCHandleLocalEntry **)(v1 + 168);
  v54 = v2;
  if ( v2 )
    ++*((_DWORD *)v2 + 4);
  (*(void (__fastcall **)(struct Cn::Engine::GCHandleLocalEntry *, System::Object **))(*(_QWORD *)v2 + 200LL))(v2, &v56);
  if ( v2 )
    System::Object::ReleaseNotFrozen$(v2);
  if ( v1 )
    System::Object::ReleaseNotFrozen$((System::Object *)v1);
  v3 = 0;
  v4 = NtCurrentTeb();
  SpareUlong0 = (int)v4->SpareUlong0;
  if ( (int)SpareUlong0 < 0 )
    v4 = (struct _TEB *)((char *)v4 + SpareUlong0);
  v6 = v4->Win32ClientInfo[61];
  v7 = *(unsigned int *)(*((_QWORD *)TlsGetValue(Cn::Context::s_tlsStorage) + 6) + 72LL);
  v8 = *(char16_t **)(v6 + 8 * v7 + 8);
  *(_QWORD *)(v6 + 8 * v7 + 8) = 0;
  v9 = 0;
  if ( v8 )
  {
    do
    {
      v13 = *(char16_t **)v8;
      *(_QWORD *)v8 = v9;
      v9 = v8;
      v8 = v13;
    }
    while ( v13 );
  }
  while ( v9 )
  {
    v11 = *((_QWORD *)v9 + 1);
    v12 = *(char16_t **)v9;
    v51 = *(char16_t **)v9;
    *(_QWORD *)v9 = 0;
    if ( !v11 )
      CFlat::Abandonment::Fail(v8);
    v54 = 0;
    Value = (char *)TlsGetValue(Cn::Context::s_tlsStorage);
    Cn::Engine::GCHandleTable::LocalValidateValue(
      (Cn::Engine::GCHandleTable *)(Value + 248),
      v11,
      &v54,
      (struct Cn::Engine::GCHandleEntryID *)&v53);
    v19 = *(System::Object **)v54;
    v53 = v19;
    if ( v19 )
    {
      v20 = *((_DWORD *)v19 + 4);
      if ( v20 > 0 )
        *((_DWORD *)v19 + 4) = v20 + 1;
    }
    CFlat::Cast::Checked<CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::IocpWait>,CFlat::SmartPtr<System::Object>>(
      &v48,
      &v53);
    v21 = v53;
    if ( v53 )
      System::Object::Release$(v53);
    v22 = v48;
    if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 0x200) != 0 )
      McTemplateU0pp_EventWriteTransfer(
        v21,
        &IoCompletionPort_UserAdapter_HandleCompletion,
        *((_QWORD *)v48 + 8),
        *((_QWORD *)v48 + 6));
    if ( *((_BYTE *)v22 + 24) )
    {
      Microsoft::CoreUI::Dispatch::IocpWait::ReleaseHandle(v22);
      goto LABEL_44;
    }
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v45 = 0;
    v46 = 0;
    v47 = 0u;
    v23 = v56;
    v24 = *((_QWORD *)v22 + 6);
    ++*((_DWORD *)v22 + 4);
    v25 = v42;
    v42 = v22;
    if ( v25 )
      System::Object::ReleaseNotFrozen$(v25);
    v43 = 0;
    v44 = v24;
    v45 = 0;
    v46 = 1;
    v26 = *((_QWORD *)TlsGetValue(Cn::Context::s_tlsStorage) + 6);
    if ( (*(_DWORD *)(v26 + 72) & 0x80000000) != 0 )
      CFlat::Abandonment::Fail((const char16_t *)v26);
    v47 = *(unsigned int *)(v26 + 72);
    *((_BYTE *)v22 + 56) = 0;
    v27 = *((_QWORD *)v23 + 4);
    v54 = (struct Cn::Engine::GCHandleLocalEntry *)v27;
    if ( v27 )
      ++*(_DWORD *)(v27 + 16);
    if ( *((_QWORD *)v22 + 6) != *(_QWORD *)(v27 + 144) )
    {
      if ( !*(_QWORD *)(v27 + 152) )
      {
        v38 = *(System::Object **)(v27 + 56);
        v53 = v38;
        if ( v38 )
          ++*((_DWORD *)v38 + 4);
        v39 = (__int64 *)Microsoft::CoreUI::Dispatch::DeferredCallDispatcher::Create$(&v49, v38);
        v40 = *v39;
        *v39 = 0;
        v41 = *(System::Object **)(v27 + 152);
        *(_QWORD *)(v27 + 152) = v40;
        if ( v41 )
          System::Object::ReleaseNotFrozen$(v41);
        if ( v49 )
          System::Object::ReleaseNotFrozen$(v49);
        if ( v38 )
          System::Object::ReleaseNotFrozen$(v38);
      }
      v28 = *(_QWORD *)(v27 + 152);
      v52 = v28;
      if ( v28 )
        ++*(_DWORD *)(v28 + 16);
      v29 = *(System::Object **)(v28 + 72);
      if ( v29 )
        ++*((_DWORD *)v29 + 4);
      Microsoft::CoreUI::Dispatch::DeferredCall$DeferredCallCache::Create(v29, &v50, v23, &v42);
      if ( v29 )
        System::Object::ReleaseNotFrozen$(v29);
      v30 = v50;
      Microsoft::CoreUI::Dispatch::DeferredCallDispatcher::EnsureGroup(v28, &v55, 16);
      v31 = v55;
      v32 = *((_QWORD *)v55 + 4);
      if ( v32 )
      {
        ++*(_DWORD *)(v32 + 16);
        *((_QWORD *)v30 + 6) = v31;
        v53 = (System::Object *)((char *)v30 + 16);
        *((_DWORD *)v30 + 4) += 2;
        ++*(_DWORD *)(v32 + 16);
        v33 = (System::Object *)v32;
        System::Object::ReleaseNotFrozen$(v30);
        v34 = *(System::Object **)(v32 + 40);
        if ( v34 )
          ++*((_DWORD *)v34 + 4);
        System::Object::ReleaseNotFrozen$(v30);
        v35 = v53;
        ++*(_DWORD *)v53;
        v36 = *(System::Object **)(v32 + 40);
        *(_QWORD *)(v32 + 40) = v30;
        if ( v36 )
        {
          System::Object::ReleaseNotFrozen$(v36);
          v35 = v53;
        }
        ++*(_DWORD *)v35;
        v37 = (System::Object *)*((_QWORD *)v34 + 4);
        *((_QWORD *)v34 + 4) = v30;
        if ( v37 )
        {
          System::Object::ReleaseNotFrozen$(v37);
LABEL_21:
          ++*((_DWORD *)v33 + 4);
LABEL_22:
          v14 = (System::Object *)*((_QWORD *)v30 + 4);
          *((_QWORD *)v30 + 4) = v33;
          if ( v14 )
            System::Object::ReleaseNotFrozen$(v14);
          if ( v34 )
            ++*((_DWORD *)v34 + 4);
          v15 = (System::Object *)*((_QWORD *)v30 + 5);
          *((_QWORD *)v30 + 5) = v34;
          if ( v15 )
            System::Object::ReleaseNotFrozen$(v15);
          if ( v34 )
            System::Object::ReleaseNotFrozen$(v34);
          if ( v33 )
            System::Object::ReleaseNotFrozen$(v33);
          if ( v32 )
            System::Object::ReleaseNotFrozen$((System::Object *)v32);
          ++*(_DWORD *)v53;
          v16 = v55;
          v17 = (System::Object *)*((_QWORD *)v55 + 4);
          *((_QWORD *)v55 + 4) = v30;
          if ( v17 )
            System::Object::ReleaseNotFrozen$(v17);
          *(_DWORD *)(v28 + 88) |= 0x10000u;
          Microsoft::CoreUI::Dispatch::DispatchItem::Activate(v28, 16);
          if ( v16 )
            System::Object::ReleaseNotFrozen$(v16);
          if ( v30 )
            System::Object::ReleaseNotFrozen$(v30);
          System::Object::ReleaseNotFrozen$((System::Object *)v28);
          v12 = v51;
          goto LABEL_41;
        }
      }
      else
      {
        *((_QWORD *)v30 + 6) = v55;
        v33 = v30;
        v35 = (System::Object *)((char *)v30 + 16);
        v34 = v30;
        *((_DWORD *)v30 + 4) += 2;
      }
      v53 = v35;
      if ( v33 )
        goto LABEL_21;
      goto LABEL_22;
    }
    Microsoft::CoreUI::Dispatch::WaitCollection::Callback_DeliverCompletion(v23, &v42);
LABEL_41:
    System::Object::ReleaseNotFrozen$((System::Object *)v27);
    if ( v42 )
      System::Object::ReleaseNotFrozen$(v42);
    v3 = 1;
LABEL_44:
    v9 = v12;
    System::Object::ReleaseNotFrozen$(v22);
  }
  if ( v56 )
    System::Object::ReleaseNotFrozen$(v56);
  return v3;
}

```

## disassembly

```asm
0x18000a410  push    rbp
0x18000a412  push    rbx
0x18000a413  push    rsi
0x18000a414  push    rdi
0x18000a415  push    r12
0x18000a417  push    r13
0x18000a419  push    r14
0x18000a41b  push    r15
0x18000a41d  lea     rbp, [rsp-1Fh]
0x18000a422  sub     rsp, 88h
0x18000a429  xor     r13d, r13d
0x18000a42c  mov     rax, [rcx+20h]
0x18000a430  mov     rdi, [rax+20h]
0x18000a434  mov     [rbp+57h+arg_0], rdi
0x18000a438  test    rdi, rdi
0x18000a43b  jz      short loc_18000A440
0x18000a43d  inc     dword ptr [rdi+10h]
0x18000a440  mov     rbx, [rdi+0A8h]
0x18000a447  mov     [rbp+57h+arg_8], rbx
0x18000a44b  test    rbx, rbx
0x18000a44e  jz      short loc_18000A453
0x18000a450  inc     dword ptr [rbx+10h]
0x18000a453  mov     rax, [rbx]
0x18000a456  lea     rdx, [rbp+57h+arg_18]
0x18000a45a  mov     rcx, rbx
0x18000a45d  mov     rax, [rax+0C8h]
0x18000a464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a469  nop
0x18000a46a  test    rbx, rbx
0x18000a46d  jz      short loc_18000A478
0x18000a46f  mov     rcx, rbx; this
0x18000a472  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a477  nop
0x18000a478  test    rdi, rdi
0x18000a47b  jz      short loc_18000A485
0x18000a47d  mov     rcx, rdi; this
0x18000a480  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a485  xor     dil, dil
0x18000a488  mov     rbx, gs:30h
0x18000a491  movsxd  rax, dword ptr [rbx+180Ch]
0x18000a498  test    eax, eax
0x18000a49a  js      loc_18000A8A3
0x18000a4a0  mov     rbx, [rbx+9E8h]
0x18000a4a7  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18000a4ad  call    cs:__imp_TlsGetValue
0x18000a4b3  mov     rcx, [rax+30h]
0x18000a4b7  mov     eax, [rcx+48h]
0x18000a4ba  mov     rcx, [rbx+rax*8+8]; char16_t *
0x18000a4bf  mov     [rbx+rax*8+8], r13
0x18000a4c4  mov     rbx, r13
0x18000a4c7  test    rcx, rcx
0x18000a4ca  jnz     short loc_18000A520
0x18000a4cc  mov     r14d, 80000000h
0x18000a4d2  test    rbx, rbx
0x18000a4d5  jnz     short loc_18000A4FD
0x18000a4d7  mov     rcx, [rbp+57h+arg_18]; this
0x18000a4db  test    rcx, rcx
0x18000a4de  jz      short loc_18000A4E5
0x18000a4e0  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a4e5  movzx   eax, dil
0x18000a4e9  add     rsp, 88h
0x18000a4f0  pop     r15
0x18000a4f2  pop     r14
0x18000a4f4  pop     r13
0x18000a4f6  pop     r12
0x18000a4f8  pop     rdi
0x18000a4f9  pop     rsi
0x18000a4fa  pop     rbx
0x18000a4fb  pop     rbp
0x18000a4fc  retn
0x18000a4fd  mov     rsi, [rbx+8]
0x18000a501  mov     r15, [rbx]
0x18000a504  mov     [rbp+57h+var_50], r15
0x18000a508  mov     [rbx], r13
0x18000a50b  test    rsi, rsi
0x18000a50e  jnz     loc_18000A61E
0x18000a514  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18000a520  mov     rax, [rcx]
0x18000a523  mov     [rcx], rbx
0x18000a526  mov     rbx, rcx
0x18000a529  mov     rcx, rax
0x18000a52c  test    rax, rax
0x18000a52f  jz      short loc_18000A4CC
0x18000a531  jmp     short loc_18000A520
0x18000a533  mov     [rbp+57h+arg_0], rax
0x18000a537  test    rdi, rdi
0x18000a53a  jz      short loc_18000A53F
0x18000a53c  inc     dword ptr [rdi+10h]
0x18000a53f  mov     rcx, [r15+20h]; this
0x18000a543  mov     [r15+20h], rdi
0x18000a547  test    rcx, rcx
0x18000a54a  jz      short loc_18000A551
0x18000a54c  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a551  test    rbx, rbx
0x18000a554  jz      short loc_18000A559
0x18000a556  inc     dword ptr [rbx+10h]
0x18000a559  mov     rcx, [r15+28h]; this
0x18000a55d  mov     [r15+28h], rbx
0x18000a561  test    rcx, rcx
0x18000a564  jz      short loc_18000A56B
0x18000a566  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a56b  test    rbx, rbx
0x18000a56e  jz      short loc_18000A578
0x18000a570  mov     rcx, rbx; this
0x18000a573  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a578  test    rdi, rdi
0x18000a57b  jz      short loc_18000A585
0x18000a57d  mov     rcx, rdi; this
0x18000a580  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a585  test    r13, r13
0x18000a588  jz      short loc_18000A592
0x18000a58a  mov     rcx, r13; this
0x18000a58d  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a592  mov     rax, [rbp+57h+arg_0]
0x18000a596  inc     dword ptr [rax]
0x18000a598  mov     rbx, [rbp+57h+arg_10]
0x18000a59c  mov     rcx, [rbx+20h]; this
0x18000a5a0  mov     [rbx+20h], r15
0x18000a5a4  test    rcx, rcx
0x18000a5a7  jz      short loc_18000A5AE
0x18000a5a9  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a5ae  or      dword ptr [rsi+58h], 10000h
0x18000a5b5  mov     edx, 10h
0x18000a5ba  mov     rcx, rsi
0x18000a5bd  call    ?Activate@DispatchItem@Dispatch@CoreUI@Microsoft@@QEAAXW4InternalPriority@234@@Z; Microsoft::CoreUI::Dispatch::DispatchItem::Activate(Microsoft::CoreUI::Dispatch::InternalPriority)
0x18000a5c2  nop
0x18000a5c3  test    rbx, rbx
0x18000a5c6  jz      short loc_18000A5D1
0x18000a5c8  mov     rcx, rbx; this
0x18000a5cb  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a5d0  nop
0x18000a5d1  test    r15, r15
0x18000a5d4  jz      short loc_18000A5DF
0x18000a5d6  mov     rcx, r15; this
0x18000a5d9  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a5de  nop
0x18000a5df  mov     rcx, rsi; this
0x18000a5e2  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a5e7  mov     r15, [rbp+57h+var_50]
0x18000a5eb  xor     r13d, r13d
0x18000a5ee  mov     rcx, r14; this
0x18000a5f1  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a5f6  nop
0x18000a5f7  mov     rcx, [rbp+57h+var_A0]; this
0x18000a5fb  test    rcx, rcx
0x18000a5fe  jz      short loc_18000A605
0x18000a600  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a605  mov     dil, 1
0x18000a608  mov     r14d, 80000000h
0x18000a60e  mov     rbx, r15
0x18000a611  mov     rcx, r12; this
0x18000a614  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a619  jmp     loc_18000A4D2
0x18000a61e  mov     [rbp+57h+arg_8], r13
0x18000a622  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18000a628  call    cs:__imp_TlsGetValue
0x18000a62e  lea     rcx, [rax+0F8h]; this
0x18000a635  lea     r9, [rbp+57h+arg_0]; struct Cn::Engine::GCHandleEntryID *
0x18000a639  lea     r8, [rbp+57h+arg_8]; struct Cn::Engine::GCHandleLocalEntry **
0x18000a63d  mov     edx, esi; unsigned int
0x18000a63f  call    ?LocalValidateValue@GCHandleTable@Engine@Cn@@AEAAXIPEAPEAUGCHandleLocalEntry@23@PEAUGCHandleEntryID@23@@Z; Cn::Engine::GCHandleTable::LocalValidateValue(uint,Cn::Engine::GCHandleLocalEntry * *,Cn::Engine::GCHandleEntryID *)
0x18000a644  mov     rax, [rbp+57h+arg_8]
0x18000a648  mov     rcx, [rax]
0x18000a64b  mov     [rbp+57h+arg_0], rcx
0x18000a64f  test    rcx, rcx
0x18000a652  jz      short loc_18000A660
0x18000a654  mov     eax, [rcx+10h]
0x18000a657  test    eax, eax
0x18000a659  jle     short loc_18000A660
0x18000a65b  inc     eax
0x18000a65d  mov     [rcx+10h], eax
0x18000a660  lea     rdx, [rbp+57h+arg_0]
0x18000a664  lea     rcx, [rbp+57h+var_68]
0x18000a668  call    ??$Checked@V?$SmartPtr@VIocpWait@Dispatch@CoreUI@Microsoft@@@CFlat@@V?$SmartPtr@VObject@System@@@2@@Cast@CFlat@@SA?A_P$$QEAV?$SmartPtr@VObject@System@@@1@@Z
0x18000a66d  nop
0x18000a66e  mov     rcx, [rbp+57h+arg_0]; this
0x18000a672  test    rcx, rcx
0x18000a675  jz      short loc_18000A67C
0x18000a677  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x18000a67c  mov     r12, [rbp+57h+var_68]
0x18000a680  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits+1, 2
0x18000a687  jnz     loc_18000A8AB
0x18000a68d  cmp     byte ptr [r12+18h], 0
0x18000a693  jnz     loc_18000A896
0x18000a699  mov     [rbp+57h+var_A0], r13
0x18000a69d  mov     [rbp+57h+var_98], r13d
0x18000a6a1  xor     eax, eax
0x18000a6a3  mov     [rbp+57h+var_90], r13
0x18000a6a7  mov     [rbp+57h+var_88], rax
0x18000a6ab  mov     [rbp+57h+var_80], al
0x18000a6ae  xorps   xmm0, xmm0
0x18000a6b1  movdqu  [rbp+57h+var_78], xmm0
0x18000a6b6  mov     qword ptr [rbp+57h+var_78+8], r13
0x18000a6ba  mov     rdi, [rbp+57h+arg_18]
0x18000a6be  mov     rbx, [r12+30h]
0x18000a6c3  inc     dword ptr [r12+10h]
0x18000a6c8  mov     rcx, [rbp+57h+var_A0]; this
0x18000a6cc  mov     [rbp+57h+var_A0], r12
0x18000a6d0  test    rcx, rcx
0x18000a6d3  jz      short loc_18000A6DA
0x18000a6d5  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a6da  mov     [rbp+57h+var_98], r13d
0x18000a6de  mov     [rbp+57h+var_90], rbx
0x18000a6e2  mov     [rbp+57h+var_88], 0
0x18000a6ea  mov     [rbp+57h+var_80], 1
0x18000a6ee  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18000a6f4  call    cs:__imp_TlsGetValue
0x18000a6fa  mov     rcx, [rax+30h]; char16_t *
0x18000a6fe  mov     eax, [rcx+48h]
0x18000a701  test    r14, rax
0x18000a704  jnz     loc_18000A820
0x18000a70a  mov     qword ptr [rbp+57h+var_78], rax
0x18000a70e  mov     qword ptr [rbp+57h+var_78+8], r13
0x18000a712  mov     byte ptr [r12+38h], 0
0x18000a718  mov     r14, [rdi+20h]
0x18000a71c  mov     [rbp+57h+arg_8], r14
0x18000a720  test    r14, r14
0x18000a723  jz      short loc_18000A729
0x18000a725  inc     dword ptr [r14+10h]
0x18000a729  mov     rax, [r14+90h]
0x18000a730  cmp     [r12+30h], rax
0x18000a735  jz      loc_18000A826
0x18000a73b  cmp     qword ptr [r14+98h], 0
0x18000a743  jz      loc_18000A837
0x18000a749  mov     rsi, [r14+98h]
0x18000a750  mov     [rbp+57h+var_48], rsi
0x18000a754  test    rsi, rsi
0x18000a757  jz      short loc_18000A75C
0x18000a759  inc     dword ptr [rsi+10h]
0x18000a75c  mov     rbx, [rsi+48h]
0x18000a760  test    rbx, rbx
0x18000a763  jz      short loc_18000A768
0x18000a765  inc     dword ptr [rbx+10h]
0x18000a768  lea     r9, [rbp+57h+var_A0]
0x18000a76c  mov     r8, rdi
0x18000a76f  lea     rdx, [rbp+57h+var_58]
0x18000a773  mov     rcx, rbx
0x18000a776  call    ?Create@DeferredCall$DeferredCallCache@Dispatch@CoreUI@Microsoft@@QEAA?AV?$SmartPtr@VDeferredCall@Dispatch@CoreUI@Microsoft@@@CFlat@@PEAVWaitCollection@234@U?$Ref@UWakeRecord@Dispatch@CoreUI@Microsoft@@@6@@Z; Microsoft::CoreUI::Dispatch::DeferredCall$DeferredCallCache::Create(Microsoft::CoreUI::Dispatch::WaitCollection *,CFlat::Ref<Microsoft::CoreUI::Dispatch::WakeRecord>)
0x18000a77b  nop
0x18000a77c  test    rbx, rbx
0x18000a77f  jz      short loc_18000A789
0x18000a781  mov     rcx, rbx; this
0x18000a784  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a789  mov     r15, [rbp+57h+var_58]
0x18000a78d  mov     r8d, 10h
0x18000a793  lea     rdx, [rbp+57h+arg_10]
0x18000a797  mov     rcx, rsi
0x18000a79a  call    ?EnsureGroup@DeferredCallDispatcher@Dispatch@CoreUI@Microsoft@@AEAA?AV?$SmartPtr@VDoubleListItem$FIFO@Support@CoreUI@Microsoft@@@CFlat@@W4InternalPriority@234@@Z; Microsoft::CoreUI::Dispatch::DeferredCallDispatcher::EnsureGroup(Microsoft::CoreUI::Dispatch::InternalPriority)
0x18000a79f  nop
0x18000a7a0  mov     rax, [rbp+57h+arg_10]
0x18000a7a4  mov     r13, [rax+20h]
0x18000a7a8  test    r13, r13
0x18000a7ab  jz      loc_18000A8C6
0x18000a7b1  inc     dword ptr [r13+10h]
0x18000a7b5  mov     [r15+30h], rax
0x18000a7b9  lea     rax, [r15+10h]
0x18000a7bd  mov     [rbp+57h+arg_0], rax
0x18000a7c1  add     dword ptr [rax], 2
0x18000a7c4  inc     dword ptr [r13+10h]
0x18000a7c8  mov     rdi, r13
0x18000a7cb  mov     rcx, r15; this
0x18000a7ce  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a7d3  mov     rbx, [r13+28h]
0x18000a7d7  test    rbx, rbx
0x18000a7da  jz      short loc_18000A7DF
0x18000a7dc  inc     dword ptr [rbx+10h]
0x18000a7df  mov     rcx, r15; this
0x18000a7e2  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a7e7  mov     rax, [rbp+57h+arg_0]
0x18000a7eb  inc     dword ptr [rax]
0x18000a7ed  mov     rcx, [r13+28h]; this
0x18000a7f1  mov     [r13+28h], r15
0x18000a7f5  test    rcx, rcx
0x18000a7f8  jz      short loc_18000A803
0x18000a7fa  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a7ff  mov     rax, [rbp+57h+arg_0]
0x18000a803  inc     dword ptr [rax]
0x18000a805  mov     rcx, [rbx+20h]; this
0x18000a809  mov     [rbx+20h], r15
0x18000a80d  test    rcx, rcx
0x18000a810  jz      loc_18000A533
0x18000a816  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a81b  jmp     loc_18000A53C
0x18000a820  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18000a826  lea     rdx, [rbp+57h+var_A0]
0x18000a82a  mov     rcx, rdi
0x18000a82d  call    ?Callback_DeliverCompletion@WaitCollection@Dispatch@CoreUI@Microsoft@@QEAA_NU?$Ref@UWakeRecord@Dispatch@CoreUI@Microsoft@@@CFlat@@@Z; Microsoft::CoreUI::Dispatch::WaitCollection::Callback_DeliverCompletion(CFlat::Ref<Microsoft::CoreUI::Dispatch::WakeRecord>)
0x18000a832  jmp     loc_18000A5EE
0x18000a837  mov     rbx, [r14+38h]
0x18000a83b  mov     [rbp+57h+arg_0], rbx
0x18000a83f  test    rbx, rbx
0x18000a842  jz      short loc_18000A847
0x18000a844  inc     dword ptr [rbx+10h]
0x18000a847  mov     rdx, rbx
0x18000a84a  lea     rcx, [rbp+57h+var_60]
0x18000a84e  call    ?Create$@DeferredCallDispatcher@Dispatch@CoreUI@Microsoft@@SA?AV?$SmartPtr@VDeferredCallDispatcher@Dispatch@CoreUI@Microsoft@@@CFlat@@PEAVDispatcher@234@@Z; Microsoft::CoreUI::Dispatch::DeferredCallDispatcher::Create$(Microsoft::CoreUI::Dispatch::Dispatcher *)
0x18000a853  mov     rdx, [rax]
0x18000a856  mov     [rax], r13
0x18000a859  mov     rcx, [r14+98h]; this
0x18000a860  mov     [r14+98h], rdx
  ... truncated ...
```
