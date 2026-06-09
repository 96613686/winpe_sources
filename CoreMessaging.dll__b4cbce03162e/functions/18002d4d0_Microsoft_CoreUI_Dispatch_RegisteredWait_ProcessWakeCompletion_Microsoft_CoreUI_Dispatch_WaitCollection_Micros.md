# Microsoft::CoreUI::Dispatch::RegisteredWait::ProcessWakeCompletion(Microsoft::CoreUI::Dispatch::WaitCollection *,Microsoft::CoreUI::Dispatch::WaitStatus)

- ea: `0x18002d4d0`
- end: `0x18002d7f2`
- name: `?ProcessWakeCompletion@RegisteredWait@Dispatch@CoreUI@Microsoft@@QEAAXPEAVWaitCollection@234@W4WaitStatus@234@@Z`
- size: `802`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180009c60`
- `0x180009dc0`
- `0x18002c9e0`
- `0x1800b9a28`
- `0x1800c2a64`

## callees

- `0x18000b130`
- `0x18000ec10`
- `0x18002d4d0`
- `0x18002dbdc`
- `0x18002df84`
- `0x18002e030`
- `0x18002e50c`
- `0x18008ae1c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d54b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d54b`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Microsoft::CoreUI::Dispatch::RegisteredWait::ProcessWakeCompletion(__int64 a1, __int64 a2, int a3)
{
  __int64 v6; // r14
  System::Object *v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // r15
  __int64 v10; // r14
  System::Object *v11; // rbx
  System::Object *v12; // rsi
  System::Object *v13; // r12
  __int64 v14; // r13
  System::Object *v15; // rdi
  System::Object *v16; // rbx
  System::Object *v17; // rcx
  System::Object *v18; // rcx
  System::Object *v19; // rcx
  System::Object *v20; // rcx
  System::Object *v21; // rcx
  System::Object *v22; // rbx
  __int64 *v23; // rax
  __int64 v24; // rdx
  System::Object *v25; // rcx
  System::Object *v26; // [rsp+30h] [rbp-40h] BYREF
  int v27; // [rsp+38h] [rbp-38h]
  __int64 v28; // [rsp+40h] [rbp-30h]
  __int64 v29; // [rsp+48h] [rbp-28h]
  char v30; // [rsp+50h] [rbp-20h]
  __int128 v31; // [rsp+58h] [rbp-18h]
  System::Object *v32; // [rsp+B0h] [rbp+40h] BYREF
  System::Object *v33; // [rsp+C8h] [rbp+58h] BYREF

  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0u;
  if ( a3 != -1 && a3 != 258 && a3 != 192 && a3 && (unsigned int)(a3 - 43962) > 3 )
    CFlat::Abandonment::Fail((const char16_t *)a1);
  v6 = *(_QWORD *)(a1 + 48);
  ++*(_DWORD *)(a1 + 16);
  v7 = v26;
  v26 = (System::Object *)a1;
  if ( v7 )
    System::Object::ReleaseNotFrozen$(v7);
  v27 = a3;
  v28 = v6;
  v29 = 0;
  v30 = 1;
  v8 = *((_QWORD *)TlsGetValue(Cn::Context::s_tlsStorage) + 6);
  if ( (*(_DWORD *)(v8 + 72) & 0x80000000) != 0 )
    CFlat::Abandonment::Fail((const char16_t *)v8);
  v31 = *(unsigned int *)(v8 + 72);
  *(_BYTE *)(a1 + 56) = 0;
  v9 = *(_QWORD *)(a2 + 32);
  if ( v9 )
    ++*(_DWORD *)(v9 + 16);
  if ( *(_QWORD *)(a1 + 48) == *(_QWORD *)(v9 + 144) )
  {
    Microsoft::CoreUI::Dispatch::WaitCollection::Callback_DeliverCompletion(a2, &v26);
    goto LABEL_47;
  }
  if ( !*(_QWORD *)(v9 + 152) )
  {
    v22 = *(System::Object **)(v9 + 56);
    v33 = v22;
    if ( v22 )
      ++*((_DWORD *)v22 + 4);
    v23 = (__int64 *)Microsoft::CoreUI::Dispatch::DeferredCallDispatcher::Create$(&v32, v22);
    v24 = *v23;
    *v23 = 0;
    v25 = *(System::Object **)(v9 + 152);
    *(_QWORD *)(v9 + 152) = v24;
    if ( v25 )
      System::Object::ReleaseNotFrozen$(v25);
    if ( v32 )
      System::Object::ReleaseNotFrozen$(v32);
    if ( v22 )
      System::Object::ReleaseNotFrozen$(v22);
  }
  v10 = *(_QWORD *)(v9 + 152);
  if ( v10 )
    ++*(_DWORD *)(v10 + 16);
  v11 = *(System::Object **)(v10 + 72);
  if ( v11 )
    ++*((_DWORD *)v11 + 4);
  Microsoft::CoreUI::Dispatch::DeferredCall$DeferredCallCache::Create(v11, &v32, a2, &v26);
  if ( v11 )
    System::Object::ReleaseNotFrozen$(v11);
  v12 = v32;
  Microsoft::CoreUI::Dispatch::DeferredCallDispatcher::EnsureGroup(v10, &v33, 16);
  v13 = v33;
  v14 = *((_QWORD *)v33 + 4);
  if ( v14 )
    ++*(_DWORD *)(v14 + 16);
  *((_QWORD *)v12 + 6) = v13;
  *((_DWORD *)v12 + 4) += 2;
  if ( v14 )
  {
    ++*(_DWORD *)(v14 + 16);
    v15 = (System::Object *)v14;
    System::Object::ReleaseNotFrozen$(v12);
    v16 = *(System::Object **)(v14 + 40);
    if ( v16 )
      ++*((_DWORD *)v16 + 4);
    System::Object::ReleaseNotFrozen$(v12);
    ++*((_DWORD *)v12 + 4);
    v17 = *(System::Object **)(v14 + 40);
    *(_QWORD *)(v14 + 40) = v12;
    if ( v17 )
      System::Object::ReleaseNotFrozen$(v17);
    ++*((_DWORD *)v12 + 4);
    v18 = (System::Object *)*((_QWORD *)v16 + 4);
    *((_QWORD *)v16 + 4) = v12;
    if ( v18 )
    {
      System::Object::ReleaseNotFrozen$(v18);
LABEL_26:
      ++*((_DWORD *)v15 + 4);
      goto LABEL_27;
    }
  }
  else
  {
    v15 = v12;
    v16 = v12;
  }
  if ( v15 )
    goto LABEL_26;
LABEL_27:
  v19 = (System::Object *)*((_QWORD *)v12 + 4);
  *((_QWORD *)v12 + 4) = v15;
  if ( v19 )
    System::Object::ReleaseNotFrozen$(v19);
  if ( v16 )
    ++*((_DWORD *)v16 + 4);
  v20 = (System::Object *)*((_QWORD *)v12 + 5);
  *((_QWORD *)v12 + 5) = v16;
  if ( v20 )
    System::Object::ReleaseNotFrozen$(v20);
  if ( v16 )
    System::Object::ReleaseNotFrozen$(v16);
  if ( v15 )
    System::Object::ReleaseNotFrozen$(v15);
  if ( v14 )
    System::Object::ReleaseNotFrozen$((System::Object *)v14);
  ++*((_DWORD *)v12 + 4);
  v21 = (System::Object *)*((_QWORD *)v13 + 4);
  *((_QWORD *)v13 + 4) = v12;
  if ( v21 )
    System::Object::ReleaseNotFrozen$(v21);
  *(_DWORD *)(v10 + 88) |= 0x10000u;
  Microsoft::CoreUI::Dispatch::DispatchItem::Activate(v10, 16);
  if ( v13 )
    System::Object::ReleaseNotFrozen$(v13);
  if ( v12 )
    System::Object::ReleaseNotFrozen$(v12);
  if ( v10 )
    System::Object::ReleaseNotFrozen$((System::Object *)v10);
LABEL_47:
  System::Object::ReleaseNotFrozen$((System::Object *)v9);
  if ( v26 )
    System::Object::ReleaseNotFrozen$(v26);
}

```

## disassembly

```asm
0x18002d4d0  mov     [rsp-38h+arg_8], rbx
0x18002d4d5  push    rbp
0x18002d4d6  push    rsi
0x18002d4d7  push    rdi
0x18002d4d8  push    r12
0x18002d4da  push    r13
0x18002d4dc  push    r14
0x18002d4de  push    r15
0x18002d4e0  mov     rbp, rsp
0x18002d4e3  sub     rsp, 70h
0x18002d4e7  mov     ebx, r8d
0x18002d4ea  mov     rsi, rdx
0x18002d4ed  mov     rdi, rcx
0x18002d4f0  xor     r13d, r13d
0x18002d4f3  mov     [rbp+var_40], r13
0x18002d4f7  mov     [rbp+var_38], r13d
0x18002d4fb  mov     [rbp+var_30], r13
0x18002d4ff  mov     [rbp+var_28], r13
0x18002d503  mov     [rbp+var_20], r13b
0x18002d507  xorps   xmm0, xmm0
0x18002d50a  movdqu  [rbp+var_18], xmm0
0x18002d50f  mov     qword ptr [rbp+var_18+8], r13
0x18002d513  cmp     r8d, 0FFFFFFFFh
0x18002d517  jnz     loc_18002D7BC
0x18002d51d  mov     r14, [rcx+30h]
0x18002d521  inc     dword ptr [rcx+10h]
0x18002d524  mov     rcx, [rbp+var_40]; this
0x18002d528  mov     [rbp+var_40], rdi
0x18002d52c  test    rcx, rcx
0x18002d52f  jz      short loc_18002D536
0x18002d531  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18002d536  mov     [rbp+var_38], ebx
0x18002d539  mov     [rbp+var_30], r14
0x18002d53d  mov     [rbp+var_28], r13
0x18002d541  mov     [rbp+var_20], 1
0x18002d545  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18002d54b  call    cs:__imp_TlsGetValue
0x18002d551  mov     rcx, [rax+30h]; char16_t *
0x18002d555  mov     eax, [rcx+48h]
0x18002d558  bt      rax, 1Fh
0x18002d55d  jb      loc_18002D749
0x18002d563  mov     qword ptr [rbp+var_18], rax
0x18002d567  mov     qword ptr [rbp+var_18+8], r13
0x18002d56b  mov     [rdi+38h], r13b
0x18002d56f  mov     r15, [rsi+20h]
0x18002d573  mov     [rbp+var_50], r15
0x18002d577  test    r15, r15
0x18002d57a  jz      short loc_18002D580
0x18002d57c  inc     dword ptr [r15+10h]
0x18002d580  mov     rax, [r15+90h]
0x18002d587  cmp     [rdi+30h], rax
0x18002d58b  jz      loc_18002D74F
0x18002d591  cmp     [r15+98h], r13
0x18002d598  jz      loc_18002D75D
0x18002d59e  mov     r14, [r15+98h]
0x18002d5a5  mov     [rbp+var_48], r14
0x18002d5a9  test    r14, r14
0x18002d5ac  jz      short loc_18002D5B2
0x18002d5ae  inc     dword ptr [r14+10h]
0x18002d5b2  mov     rbx, [r14+48h]
0x18002d5b6  test    rbx, rbx
0x18002d5b9  jz      short loc_18002D5BE
0x18002d5bb  inc     dword ptr [rbx+10h]
0x18002d5be  lea     r9, [rbp+var_40]
0x18002d5c2  mov     r8, rsi
0x18002d5c5  lea     rdx, [rbp+arg_0]
0x18002d5c9  mov     rcx, rbx
0x18002d5cc  call    ?Create@DeferredCall$DeferredCallCache@Dispatch@CoreUI@Microsoft@@QEAA?AV?$SmartPtr@VDeferredCall@Dispatch@CoreUI@Microsoft@@@CFlat@@PEAVWaitCollection@234@U?$Ref@UWakeRecord@Dispatch@CoreUI@Microsoft@@@6@@Z; Microsoft::CoreUI::Dispatch::DeferredCall$DeferredCallCache::Create(Microsoft::CoreUI::Dispatch::WaitCollection *,CFlat::Ref<Microsoft::CoreUI::Dispatch::WakeRecord>)
0x18002d5d1  nop
0x18002d5d2  test    rbx, rbx
0x18002d5d5  jz      short loc_18002D5DF
0x18002d5d7  mov     rcx, rbx; this
0x18002d5da  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18002d5df  mov     rsi, [rbp+arg_0]
0x18002d5e3  mov     r8d, 10h
0x18002d5e9  lea     rdx, [rbp+arg_18]
0x18002d5ed  mov     rcx, r14
0x18002d5f0  call    ?EnsureGroup@DeferredCallDispatcher@Dispatch@CoreUI@Microsoft@@AEAA?AV?$SmartPtr@VDoubleListItem$FIFO@Support@CoreUI@Microsoft@@@CFlat@@W4InternalPriority@234@@Z; Microsoft::CoreUI::Dispatch::DeferredCallDispatcher::EnsureGroup(Microsoft::CoreUI::Dispatch::InternalPriority)
0x18002d5f5  nop
0x18002d5f6  mov     r12, [rbp+arg_18]
0x18002d5fa  mov     r13, [r12+20h]
0x18002d5ff  test    r13, r13
0x18002d602  jz      short loc_18002D608
0x18002d604  inc     dword ptr [r13+10h]
0x18002d608  mov     [rsi+30h], r12
0x18002d60c  add     dword ptr [rsi+10h], 2
0x18002d610  test    r13, r13
0x18002d613  jz      short loc_18002D664
0x18002d615  inc     dword ptr [r13+10h]
0x18002d619  mov     rdi, r13
0x18002d61c  mov     rcx, rsi; this
0x18002d61f  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18002d624  mov     rbx, [r13+28h]
0x18002d628  test    rbx, rbx
0x18002d62b  jz      short loc_18002D630
0x18002d62d  inc     dword ptr [rbx+10h]
0x18002d630  mov     rcx, rsi; this
0x18002d633  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18002d638  inc     dword ptr [rsi+10h]
0x18002d63b  mov     rcx, [r13+28h]; this
0x18002d63f  mov     [r13+28h], rsi
0x18002d643  test    rcx, rcx
0x18002d646  jz      short loc_18002D64D
0x18002d648  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18002d64d  inc     dword ptr [rsi+10h]
0x18002d650  mov     rcx, [rbx+20h]; this
0x18002d654  mov     [rbx+20h], rsi
0x18002d658  test    rcx, rcx
0x18002d65b  jz      short loc_18002D66A
0x18002d65d  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18002d662  jmp     short loc_18002D66F
0x18002d664  mov     rdi, rsi
0x18002d667  mov     rbx, rsi
0x18002d66a  test    rdi, rdi
0x18002d66d  jz      short loc_18002D672
0x18002d66f  inc     dword ptr [rdi+10h]
0x18002d672  mov     rcx, [rsi+20h]; this
0x18002d676  mov     [rsi+20h], rdi
0x18002d67a  test    rcx, rcx
0x18002d67d  jz      short loc_18002D684
0x18002d67f  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18002d684  test    rbx, rbx
0x18002d687  jz      short loc_18002D68C
0x18002d689  inc     dword ptr [rbx+10h]
0x18002d68c  mov     rcx, [rsi+28h]; this
0x18002d690  mov     [rsi+28h], rbx
0x18002d694  test    rcx, rcx
0x18002d697  jz      short loc_18002D69E
0x18002d699  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18002d69e  test    rbx, rbx
0x18002d6a1  jz      short loc_18002D6AB
0x18002d6a3  mov     rcx, rbx; this
0x18002d6a6  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18002d6ab  test    rdi, rdi
0x18002d6ae  jz      short loc_18002D6B8
0x18002d6b0  mov     rcx, rdi; this
0x18002d6b3  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18002d6b8  test    r13, r13
0x18002d6bb  jz      short loc_18002D6C5
0x18002d6bd  mov     rcx, r13; this
0x18002d6c0  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18002d6c5  inc     dword ptr [rsi+10h]
0x18002d6c8  mov     rcx, [r12+20h]; this
0x18002d6cd  mov     [r12+20h], rsi
0x18002d6d2  test    rcx, rcx
0x18002d6d5  jz      short loc_18002D6DC
0x18002d6d7  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18002d6dc  bts     dword ptr [r14+58h], 10h
0x18002d6e2  mov     edx, 10h
0x18002d6e7  mov     rcx, r14
0x18002d6ea  call    ?Activate@DispatchItem@Dispatch@CoreUI@Microsoft@@QEAAXW4InternalPriority@234@@Z; Microsoft::CoreUI::Dispatch::DispatchItem::Activate(Microsoft::CoreUI::Dispatch::InternalPriority)
0x18002d6ef  nop
0x18002d6f0  test    r12, r12
0x18002d6f3  jz      short loc_18002D6FE
0x18002d6f5  mov     rcx, r12; this
0x18002d6f8  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18002d6fd  nop
0x18002d6fe  test    rsi, rsi
0x18002d701  jz      short loc_18002D70C
0x18002d703  mov     rcx, rsi; this
0x18002d706  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18002d70b  nop
0x18002d70c  test    r14, r14
0x18002d70f  jz      short loc_18002D71A
0x18002d711  mov     rcx, r14; this
0x18002d714  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18002d719  nop
0x18002d71a  mov     rcx, r15; this
0x18002d71d  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18002d722  nop
0x18002d723  mov     rcx, [rbp+var_40]; this
0x18002d727  test    rcx, rcx
0x18002d72a  jz      short loc_18002D731
0x18002d72c  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18002d731  mov     rbx, [rsp+70h+arg_8]
0x18002d739  add     rsp, 70h
0x18002d73d  pop     r15
0x18002d73f  pop     r14
0x18002d741  pop     r13
0x18002d743  pop     r12
0x18002d745  pop     rdi
0x18002d746  pop     rsi
0x18002d747  pop     rbp
0x18002d748  retn
0x18002d749  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18002d74f  lea     rdx, [rbp+var_40]
0x18002d753  mov     rcx, rsi
0x18002d756  call    ?Callback_DeliverCompletion@WaitCollection@Dispatch@CoreUI@Microsoft@@QEAA_NU?$Ref@UWakeRecord@Dispatch@CoreUI@Microsoft@@@CFlat@@@Z; Microsoft::CoreUI::Dispatch::WaitCollection::Callback_DeliverCompletion(CFlat::Ref<Microsoft::CoreUI::Dispatch::WakeRecord>)
0x18002d75b  jmp     short loc_18002D71A
0x18002d75d  mov     rbx, [r15+38h]
0x18002d761  mov     [rbp+arg_18], rbx
0x18002d765  test    rbx, rbx
0x18002d768  jz      short loc_18002D76D
0x18002d76a  inc     dword ptr [rbx+10h]
0x18002d76d  mov     rdx, rbx
0x18002d770  lea     rcx, [rbp+arg_0]
0x18002d774  call    ?Create$@DeferredCallDispatcher@Dispatch@CoreUI@Microsoft@@SA?AV?$SmartPtr@VDeferredCallDispatcher@Dispatch@CoreUI@Microsoft@@@CFlat@@PEAVDispatcher@234@@Z; Microsoft::CoreUI::Dispatch::DeferredCallDispatcher::Create$(Microsoft::CoreUI::Dispatch::Dispatcher *)
0x18002d779  mov     rdx, [rax]
0x18002d77c  mov     [rax], r13
0x18002d77f  mov     rcx, [r15+98h]; this
0x18002d786  mov     [r15+98h], rdx
0x18002d78d  test    rcx, rcx
0x18002d790  jz      short loc_18002D797
0x18002d792  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18002d797  mov     rcx, [rbp+arg_0]; this
0x18002d79b  test    rcx, rcx
0x18002d79e  jz      short loc_18002D7A6
0x18002d7a0  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18002d7a5  nop
0x18002d7a6  test    rbx, rbx
0x18002d7a9  jz      loc_18002D59E
0x18002d7af  mov     rcx, rbx; this
0x18002d7b2  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18002d7b7  jmp     loc_18002D59E
0x18002d7bc  cmp     ebx, 102h
0x18002d7c2  jz      loc_18002D51D
0x18002d7c8  cmp     ebx, 0C0h
0x18002d7ce  jz      loc_18002D51D
0x18002d7d4  test    ebx, ebx
0x18002d7d6  jz      loc_18002D51D
0x18002d7dc  lea     eax, [r8-0ABBAh]
0x18002d7e3  cmp     eax, 3
0x18002d7e6  jbe     loc_18002D51D
0x18002d7ec  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
```
