# Microsoft::CoreUI::Dispatch::WaitController::DrainSignaledIocpWaits(void)

- ea: `0x180009dc0`
- end: `0x18000a3cb`
- name: `?DrainSignaledIocpWaits@WaitController@Dispatch@CoreUI@Microsoft@@AEAAXXZ`
- size: `1547`
- prototype: `void __fastcall(Microsoft::CoreUI::Dispatch::WaitController *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180009c60`

## callees

- `0x180009dc0`
- `0x18000a3d4`
- `0x18000a410`
- `0x18000a98c`
- `0x18000b130`
- `0x18000ec10`
- `0x180010ed0`
- `0x18002d4d0`
- `0x18002dbdc`
- `0x18002df84`
- `0x18002e50c`
- `0x1800727ac`
- `0x18008ae1c`
- `0x18008cb30`
- `0x18008cc78`
- `0x18008f3cc`
- `0x18008f584`
- `0x18009d670`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009f9b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a224`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a303`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009f9b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a224`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a303`
- `ntdll!NtRemoveIoCompletionEx` at `0x180009e72`
- `ntdll!NtRemoveIoCompletionEx` at `0x180009e72`
- `ntdll!NtSetIoCompletionEx` at `0x18000a246`
- `ntdll!NtSetIoCompletionEx` at `0x18000a246`
- `ext-ms-win-rtcore-ntuser-integration-l1-1-0!__imp_DrainThreadCoreMessagingCompletions2` at `0x180009eac`
- `ext-ms-win-rtcore-ntuser-integration-l1-1-0!__imp_DrainThreadCoreMessagingCompletions2` at `0x180009eac`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall Microsoft::CoreUI::Dispatch::WaitController::DrainSignaledIocpWaits(
        Microsoft::CoreUI::Dispatch::WaitController *this)
{
  System::Object *v2; // rbx
  __int64 v3; // rdi
  int v4; // r12d
  int v5; // eax
  const char16_t *v6; // rcx
  __int64 v7; // r8
  __int64 v8; // rax
  System::Object *v9; // rdi
  int v10; // eax
  System::Object *v11; // rdi
  __int128 v12; // xmm6
  __int64 v13; // rcx
  __int64 v14; // rsi
  __int64 v15; // r13
  System::Object *v16; // rax
  System::Object *v17; // rdi
  System::Object *v18; // rcx
  System::Object *v19; // rdx
  System::Object *v20; // rax
  System::Object *v21; // r14
  System::Object *v22; // rdi
  _DWORD *v23; // r8
  System::Object *v24; // rdx
  System::Object *v25; // rcx
  System::Object *v26; // rcx
  System::Object *v27; // rcx
  System::Object *v28; // r14
  System::Object *v29; // rcx
  System::Object *v30; // rdi
  __int64 v31; // rdi
  _QWORD *v32; // rax
  int v33; // eax
  System::Object *v34; // rdi
  __int64 *v35; // rax
  __int64 v36; // rdx
  System::Object *v37; // rcx
  char *Value; // rax
  System::Object *v39; // rcx
  int v40; // eax
  System::Object *v41; // rdi
  System::Object *v42; // rsi
  __int64 v43; // [rsp+28h] [rbp-D8h]
  System::Object *v44; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD *v45; // [rsp+38h] [rbp-C8h] BYREF
  System::Object *v46; // [rsp+40h] [rbp-C0h] BYREF
  System::Object *v47; // [rsp+48h] [rbp-B8h] BYREF
  System::Object *v48; // [rsp+50h] [rbp-B0h]
  __int128 v49; // [rsp+60h] [rbp-A0h]
  System::Object *v50[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v51; // [rsp+80h] [rbp-80h]
  char v52; // [rsp+90h] [rbp-70h]
  __int128 v53; // [rsp+98h] [rbp-68h]
  System::Object *v54; // [rsp+A8h] [rbp-58h] BYREF
  System::Object *v55; // [rsp+B0h] [rbp-50h] BYREF
  System::Object *v56[3]; // [rsp+B8h] [rbp-48h] BYREF
  System::Object *v57; // [rsp+D0h] [rbp-30h] BYREF

  v47 = *(System::Object **)(*(_QWORD *)(*((_QWORD *)this + 10) + 32LL) + 168LL);
  CFlat::Cast::Checked<CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::Win32EventLoopBridge>,Microsoft::CoreUI::Dispatch::EventLoopBridge *>(
    &v54,
    &v47);
  v2 = v54;
  v3 = *((_QWORD *)v54 + 7);
  if ( v3 )
  {
    v8 = *((_QWORD *)v54 + 4);
    if ( !*(_BYTE *)(v8 + 176) && *(_DWORD *)(v8 + 68) != 4 )
    {
      ++*(_DWORD *)(v3 + 16);
      if ( !(unsigned int)DrainThreadCoreMessagingCompletions2(**(_QWORD **)(v3 + 40)) )
        Cn::FailFast::ForWin32();
      System::Object::ReleaseNotFrozen$((System::Object *)v3);
      v9 = (System::Object *)*((_QWORD *)v2 + 7);
      v48 = v9;
      if ( v9 )
        ++*((_DWORD *)v9 + 4);
      Microsoft::CoreUI::Dispatch::UserAdapter::ProcessPendingWaitsCommon(v9);
      if ( v9 )
        System::Object::ReleaseNotFrozen$(v9);
      goto LABEL_13;
    }
  }
  *((_QWORD *)&v49 + 1) = 0;
  v4 = 0;
  while ( 1 )
  {
    *(_OWORD *)v50 = 0;
    v51 = 0;
    LODWORD(v45) = 0;
    v49 = 0u;
    v44 = 0;
    LOBYTE(v43) = 0;
    v5 = ((__int64 (__fastcall *)(_QWORD, System::Object **, __int64, _DWORD **, System::Object **, __int64))NtRemoveIoCompletionEx)(
           *((_QWORD *)this + 11),
           v50,
           1,
           &v45,
           &v44,
           v43);
    if ( v5 )
    {
      if ( v5 != 258 )
        Cn::FailFast::ForNtStatus(v5);
      goto LABEL_13;
    }
    v10 = (int)v50[1];
    v11 = v50[0];
    if ( SLODWORD(v50[1]) >= 0 && !v50[0] )
      break;
    *(System::Object **)&v49 = v50[1];
    *((System::Object **)&v49 + 1) = v50[0];
    if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 0x200) != 0 )
    {
      McTemplateU0pp_EventWriteTransfer(v6, &IoCompletionPort_RemovedCompletion, v50[1], v50[0]);
      v11 = (System::Object *)*((_QWORD *)&v49 + 1);
      v10 = v49;
    }
    if ( v10 < 0 )
    {
      v12 = v49;
      v53 = 0u;
      v50[0] = 0;
      LODWORD(v50[1]) = 0;
      v51 = 0u;
      v52 = 1;
      v13 = *((_QWORD *)TlsGetValue(Cn::Context::s_tlsStorage) + 6);
      if ( *(int *)(v13 + 72) < 0 )
        CFlat::Abandonment::Fail((const char16_t *)v13);
      v53 = v12;
      v14 = *(_QWORD *)(*((_QWORD *)this + 10) + 32LL);
      v56[1] = (System::Object *)v14;
      if ( v14 )
        ++*(_DWORD *)(v14 + 16);
      if ( !*(_QWORD *)(v14 + 152) )
      {
        v34 = *(System::Object **)(v14 + 56);
        v48 = v34;
        if ( v34 )
          ++*((_DWORD *)v34 + 4);
        v35 = (__int64 *)Microsoft::CoreUI::Dispatch::DeferredCallDispatcher::Create$(v56, v34);
        v36 = *v35;
        *v35 = 0;
        v37 = *(System::Object **)(v14 + 152);
        *(_QWORD *)(v14 + 152) = v36;
        if ( v37 )
          System::Object::ReleaseNotFrozen$(v37);
        if ( v56[0] )
          System::Object::ReleaseNotFrozen$(v56[0]);
        if ( v34 )
          System::Object::ReleaseNotFrozen$(v34);
      }
      v15 = *(_QWORD *)(v14 + 152);
      v56[2] = (System::Object *)v15;
      if ( v15 )
        ++*(_DWORD *)(v15 + 16);
      v16 = (System::Object *)*((_QWORD *)this + 10);
      v48 = v16;
      v57 = v16;
      if ( v16 )
        ++*((_DWORD *)v16 + 4);
      v17 = *(System::Object **)(v15 + 72);
      if ( v17 )
        ++*((_DWORD *)v17 + 4);
      Microsoft::CoreUI::Dispatch::DeferredCall$DeferredCallCache::Create(v17, &v46, v16, v50);
      if ( v17 )
        System::Object::ReleaseNotFrozen$(v17);
      Microsoft::CoreUI::Dispatch::DeferredCallDispatcher::EnsureGroup(v15, &v47, 9);
      v18 = v47;
      v19 = (System::Object *)*((_QWORD *)v47 + 4);
      v44 = v19;
      v20 = v46;
      if ( v19 )
      {
        ++*((_DWORD *)v19 + 4);
        *((_QWORD *)v20 + 6) = v18;
        v45 = (_DWORD *)((char *)v20 + 16);
        *((_DWORD *)v20 + 4) += 2;
        ++*((_DWORD *)v19 + 4);
        v21 = v19;
        System::Object::ReleaseNotFrozen$(v20);
        v22 = (System::Object *)*((_QWORD *)v21 + 5);
        if ( v22 )
          ++*((_DWORD *)v22 + 4);
        System::Object::ReleaseNotFrozen$(v46);
        v23 = v45;
        ++*v45;
        v24 = (System::Object *)*((_QWORD *)v21 + 5);
        v20 = v46;
        *((_QWORD *)v21 + 5) = v46;
        if ( v24 )
        {
          System::Object::ReleaseNotFrozen$(v24);
          v20 = v46;
          v23 = v45;
        }
        ++*v23;
        v25 = (System::Object *)*((_QWORD *)v22 + 4);
        *((_QWORD *)v22 + 4) = v20;
        if ( v25 )
        {
          System::Object::ReleaseNotFrozen$(v25);
          goto LABEL_41;
        }
        v45 = v23;
      }
      else
      {
        *((_QWORD *)v46 + 6) = v47;
        v21 = v20;
        v45 = (_DWORD *)((char *)v20 + 16);
        v22 = v20;
        *((_DWORD *)v20 + 4) += 2;
      }
      if ( v21 )
      {
LABEL_41:
        ++*((_DWORD *)v21 + 4);
        v20 = v46;
      }
      v26 = (System::Object *)*((_QWORD *)v20 + 4);
      *((_QWORD *)v20 + 4) = v21;
      if ( v26 )
      {
        System::Object::ReleaseNotFrozen$(v26);
        v20 = v46;
      }
      if ( v22 )
        ++*((_DWORD *)v22 + 4);
      v27 = (System::Object *)*((_QWORD *)v20 + 5);
      *((_QWORD *)v20 + 5) = v22;
      if ( v27 )
        System::Object::ReleaseNotFrozen$(v27);
      if ( v22 )
        System::Object::ReleaseNotFrozen$(v22);
      if ( v21 )
        System::Object::ReleaseNotFrozen$(v21);
      if ( v44 )
        System::Object::ReleaseNotFrozen$(v44);
      ++*v45;
      v28 = v47;
      v29 = (System::Object *)*((_QWORD *)v47 + 4);
      v30 = v46;
      *((_QWORD *)v47 + 4) = v46;
      if ( v29 )
        System::Object::ReleaseNotFrozen$(v29);
      *(_DWORD *)(v15 + 88) |= 0x200u;
      Microsoft::CoreUI::Dispatch::DispatchItem::Activate(v15, 9);
      if ( v28 )
        System::Object::ReleaseNotFrozen$(v28);
      if ( v30 )
        System::Object::ReleaseNotFrozen$(v30);
      if ( v48 )
        System::Object::ReleaseNotFrozen$(v48);
      System::Object::ReleaseNotFrozen$((System::Object *)v15);
      if ( v14 )
        System::Object::ReleaseNotFrozen$((System::Object *)v14);
      if ( v50[0] )
        System::Object::ReleaseNotFrozen$(v50[0]);
      goto LABEL_66;
    }
    if ( !v11 )
      CFlat::Abandonment::Fail(v6);
    v44 = 0;
    Value = (char *)TlsGetValue(Cn::Context::s_tlsStorage);
    Cn::Engine::GCHandleTable::LocalValidateValue(
      (Cn::Engine::GCHandleTable *)(Value + 248),
      (unsigned int)v11,
      &v44,
      (struct Cn::Engine::GCHandleEntryID *)&v45);
    v39 = *(System::Object **)v44;
    v44 = v39;
    if ( v39 )
    {
      v40 = *((_DWORD *)v39 + 4);
      if ( v40 > 0 )
        *((_DWORD *)v39 + 4) = v40 + 1;
    }
    CFlat::Cast::Checked<CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::RegisteredWait>,CFlat::SmartPtr<System::Object>>(
      &v55,
      &v44);
    if ( v44 )
      System::Object::Release$(v44);
    v41 = v55;
    v42 = (System::Object *)*((_QWORD *)this + 10);
    v48 = v42;
    if ( v42 )
      ++*((_DWORD *)v42 + 4);
    Microsoft::CoreUI::Dispatch::RegisteredWait::ProcessWakeCompletion(v41, v42, 0);
    if ( v42 )
      System::Object::ReleaseNotFrozen$(v42);
    if ( v41 )
      System::Object::ReleaseNotFrozen$(v41);
LABEL_66:
    if ( ++v4 == 2 )
    {
      v31 = *((_QWORD *)this + 12);
      v32 = TlsGetValue(Cn::Context::s_tlsStorage);
      v33 = NtSetIoCompletionEx(*((_QWORD *)this + 11), v31, 0, *(unsigned int *)(v32[6] + 72LL), 0, 0);
      if ( v33 < 0 )
        Cn::FailFast::ForNtStatus(v33);
    }
  }
  if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 0x200) != 0 )
    McGenEventWrite_EventWriteTransfer(v6, &IoCompletionPort_RemovedEndOfBatch, v7, 1, &v57);
LABEL_13:
  System::Object::ReleaseNotFrozen$(v2);
}

```

## disassembly

```asm
0x180009dc0  push    rbp
0x180009dc2  push    rbx
0x180009dc3  push    rsi
0x180009dc4  push    rdi
0x180009dc5  push    r12
0x180009dc7  push    r13
0x180009dc9  push    r14
0x180009dcb  push    r15
0x180009dcd  lea     rbp, [rsp-8]
0x180009dd2  sub     rsp, 108h
0x180009dd9  movaps  [rsp+140h+var_50], xmm6
0x180009de1  mov     rax, cs:__security_cookie
0x180009de8  xor     rax, rsp
0x180009deb  mov     [rbp+40h+var_60], rax
0x180009def  mov     r15, rcx
0x180009df2  xor     r14d, r14d
0x180009df5  mov     rax, [rcx+50h]
0x180009df9  mov     rdx, [rax+20h]
0x180009dfd  mov     rax, [rdx+0A8h]
0x180009e04  mov     [rsp+140h+var_F8], rax
0x180009e09  lea     rdx, [rsp+140h+var_F8]
0x180009e0e  lea     rcx, [rbp+40h+var_98]
0x180009e12  call    ??$Checked@V?$SmartPtr@VWin32EventLoopBridge@Dispatch@CoreUI@Microsoft@@@CFlat@@PEAVEventLoopBridge@Dispatch@CoreUI@Microsoft@@@Cast@CFlat@@SA?A_P$$QEAPEAVEventLoopBridge@Dispatch@CoreUI@Microsoft@@@Z
0x180009e17  nop
0x180009e18  mov     rbx, [rbp+40h+var_98]
0x180009e1c  mov     rdi, [rbx+38h]
0x180009e20  test    rdi, rdi
0x180009e23  jnz     short loc_180009E8F
0x180009e25  xor     eax, eax
0x180009e27  mov     qword ptr [rsp+140h+var_E0+8], rax
0x180009e2c  mov     r12d, r14d
0x180009e2f  xorps   xmm0, xmm0
0x180009e32  movups  xmmword ptr [rsp+140h+var_D0], xmm0
0x180009e37  movups  [rbp+40h+var_C0], xmm0
0x180009e3b  mov     dword ptr [rsp+140h+var_108], r14d
0x180009e40  mov     qword ptr [rsp+140h+var_E0], r14
0x180009e45  mov     qword ptr [rsp+140h+var_E0+8], r14
0x180009e4a  mov     [rsp+140h+var_110], r14
0x180009e4f  mov     byte ptr [rsp+140h+var_118], 0
0x180009e54  lea     rax, [rsp+140h+var_110]
0x180009e59  mov     [rsp+140h+var_120], rax
0x180009e5e  lea     r9, [rsp+140h+var_108]
0x180009e63  mov     r8d, 1
0x180009e69  lea     rdx, [rsp+140h+var_D0]
0x180009e6e  mov     rcx, [r15+58h]
0x180009e72  call    cs:__imp_NtRemoveIoCompletionEx
0x180009e78  test    eax, eax
0x180009e7a  jz      loc_180009F1A
0x180009e80  cmp     eax, 102h
0x180009e85  jz      short loc_180009EEA
0x180009e87  mov     ecx, eax; int
0x180009e89  call    ?ForNtStatus@FailFast@Cn@@SAXH@Z; Cn::FailFast::ForNtStatus(int)
0x180009e8f  mov     rax, [rbx+20h]
0x180009e93  cmp     byte ptr [rax+0B0h], 0
0x180009e9a  jnz     short loc_180009E25
0x180009e9c  cmp     dword ptr [rax+44h], 4
0x180009ea0  jz      short loc_180009E25
0x180009ea2  inc     dword ptr [rdi+10h]
0x180009ea5  mov     rcx, [rdi+28h]
0x180009ea9  mov     rcx, [rcx]
0x180009eac  call    cs:__imp_DrainThreadCoreMessagingCompletions2
0x180009eb2  test    eax, eax
0x180009eb4  jz      loc_18000A26B
0x180009eba  mov     rcx, rdi; this
0x180009ebd  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180009ec2  mov     rdi, [rbx+38h]
0x180009ec6  mov     [rsp+140h+var_F0], rdi
0x180009ecb  test    rdi, rdi
0x180009ece  jz      short loc_180009ED3
0x180009ed0  inc     dword ptr [rdi+10h]
0x180009ed3  mov     rcx, rdi; this
0x180009ed6  call    ?ProcessPendingWaitsCommon@UserAdapter@Dispatch@CoreUI@Microsoft@@AEAA_NXZ; Microsoft::CoreUI::Dispatch::UserAdapter::ProcessPendingWaitsCommon(void)
0x180009edb  nop
0x180009edc  test    rdi, rdi
0x180009edf  jz      short loc_180009EEA
0x180009ee1  mov     rcx, rdi; this
0x180009ee4  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180009ee9  nop
0x180009eea  mov     rcx, rbx; this
0x180009eed  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180009ef2  mov     rcx, [rbp+40h+var_60]
0x180009ef6  xor     rcx, rsp; StackCookie
0x180009ef9  call    __security_check_cookie
0x180009efe  movaps  xmm6, [rsp+140h+var_50]
0x180009f06  add     rsp, 108h
0x180009f0d  pop     r15
0x180009f0f  pop     r14
0x180009f11  pop     r13
0x180009f13  pop     r12
0x180009f15  pop     rdi
0x180009f16  pop     rsi
0x180009f17  pop     rbx
0x180009f18  pop     rbp
0x180009f19  retn
0x180009f1a  mov     rax, [rsp+140h+var_D0+8]
0x180009f1f  mov     rdi, [rsp+140h+var_D0]
0x180009f24  test    eax, eax
0x180009f26  jns     loc_18000A0DE
0x180009f2c  mov     qword ptr [rsp+140h+var_E0], rax
0x180009f31  mov     qword ptr [rsp+140h+var_E0+8], rdi
0x180009f36  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits+1, 2
0x180009f3d  jnz     loc_18000A2D7
0x180009f43  test    eax, eax
0x180009f45  jns     loc_18000A25C
0x180009f4b  movaps  xmm6, [rsp+140h+var_E0]
0x180009f50  mov     rcx, r14; this
0x180009f53  mov     dword ptr [rsp+140h+var_D0+8], r14d
0x180009f58  xor     eax, eax
0x180009f5a  mov     qword ptr [rbp+40h+var_C0], r14
0x180009f5e  mov     qword ptr [rbp+40h+var_C0+8], rax
0x180009f62  mov     [rbp+40h+var_B0], al
0x180009f65  xorps   xmm0, xmm0
0x180009f68  movdqu  [rbp+40h+var_A8], xmm0
0x180009f6d  mov     qword ptr [rbp+40h+var_A8+8], r14
0x180009f71  mov     [rsp+140h+var_D0], r14
0x180009f76  test    r14, r14
0x180009f79  jz      short loc_180009F80
0x180009f7b  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180009f80  mov     dword ptr [rsp+140h+var_D0+8], r14d
0x180009f85  mov     qword ptr [rbp+40h+var_C0], r14
0x180009f89  mov     qword ptr [rbp+40h+var_C0+8], 0
0x180009f91  mov     [rbp+40h+var_B0], 1
0x180009f95  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180009f9b  call    cs:__imp_TlsGetValue
0x180009fa1  mov     rcx, [rax+30h]; char16_t *
0x180009fa5  test    dword ptr [rcx+48h], 80000000h
0x180009fac  jnz     loc_18000A271
0x180009fb2  movups  [rbp+40h+var_A8], xmm6
0x180009fb6  mov     rsi, [r15+50h]
0x180009fba  mov     rsi, [rsi+20h]
0x180009fbe  mov     [rbp+40h+var_80], rsi
0x180009fc2  test    rsi, rsi
0x180009fc5  jz      short loc_180009FCA
0x180009fc7  inc     dword ptr [rsi+10h]
0x180009fca  cmp     qword ptr [rsi+98h], 0
0x180009fd2  jz      loc_18000A277
0x180009fd8  mov     r13, [rsi+98h]
0x180009fdf  mov     [rbp+40h+var_78], r13
0x180009fe3  test    r13, r13
0x180009fe6  jz      short loc_180009FEC
0x180009fe8  inc     dword ptr [r13+10h]
0x180009fec  mov     rax, [r15+50h]
0x180009ff0  mov     [rsp+140h+var_F0], rax
0x180009ff5  mov     [rbp+40h+var_70], rax
0x180009ff9  test    rax, rax
0x180009ffc  jz      short loc_18000A001
0x180009ffe  inc     dword ptr [rax+10h]
0x18000a001  mov     rdi, [r13+48h]
0x18000a005  test    rdi, rdi
0x18000a008  jz      short loc_18000A00D
0x18000a00a  inc     dword ptr [rdi+10h]
0x18000a00d  lea     r9, [rsp+140h+var_D0]
0x18000a012  mov     r8, rax
0x18000a015  lea     rdx, [rsp+140h+var_100]
0x18000a01a  mov     rcx, rdi
0x18000a01d  call    ?Create@DeferredCall$DeferredCallCache@Dispatch@CoreUI@Microsoft@@QEAA?AV?$SmartPtr@VDeferredCall@Dispatch@CoreUI@Microsoft@@@CFlat@@PEAVWaitCollection@234@U?$Ref@UWakeRecord@Dispatch@CoreUI@Microsoft@@@6@@Z; Microsoft::CoreUI::Dispatch::DeferredCall$DeferredCallCache::Create(Microsoft::CoreUI::Dispatch::WaitCollection *,CFlat::Ref<Microsoft::CoreUI::Dispatch::WakeRecord>)
0x18000a022  nop
0x18000a023  test    rdi, rdi
0x18000a026  jz      short loc_18000A030
0x18000a028  mov     rcx, rdi; this
0x18000a02b  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a030  mov     r8d, 9
0x18000a036  lea     rdx, [rsp+140h+var_F8]
0x18000a03b  mov     rcx, r13
0x18000a03e  call    ?EnsureGroup@DeferredCallDispatcher@Dispatch@CoreUI@Microsoft@@AEAA?AV?$SmartPtr@VDoubleListItem$FIFO@Support@CoreUI@Microsoft@@@CFlat@@W4InternalPriority@234@@Z; Microsoft::CoreUI::Dispatch::DeferredCallDispatcher::EnsureGroup(Microsoft::CoreUI::Dispatch::InternalPriority)
0x18000a043  nop
0x18000a044  mov     rcx, [rsp+140h+var_F8]
0x18000a049  mov     rdx, [rcx+20h]
0x18000a04d  mov     [rsp+140h+var_110], rdx
0x18000a052  mov     rax, [rsp+140h+var_100]
0x18000a057  test    rdx, rdx
0x18000a05a  jz      loc_18000A3AF
0x18000a060  inc     dword ptr [rdx+10h]
0x18000a063  mov     [rax+30h], rcx
0x18000a067  lea     rcx, [rax+10h]
0x18000a06b  mov     [rsp+140h+var_108], rcx
0x18000a070  add     dword ptr [rcx], 2
0x18000a073  inc     dword ptr [rdx+10h]
0x18000a076  mov     r14, rdx
0x18000a079  mov     rcx, rax; this
0x18000a07c  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a081  mov     rdi, [r14+28h]
0x18000a085  test    rdi, rdi
0x18000a088  jz      short loc_18000A08D
0x18000a08a  inc     dword ptr [rdi+10h]
0x18000a08d  mov     rcx, [rsp+140h+var_100]; this
0x18000a092  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a097  mov     r8, [rsp+140h+var_108]
0x18000a09c  inc     dword ptr [r8]
0x18000a09f  mov     rdx, [r14+28h]
0x18000a0a3  mov     rax, [rsp+140h+var_100]
0x18000a0a8  mov     [r14+28h], rax
0x18000a0ac  test    rdx, rdx
0x18000a0af  jz      short loc_18000A0C3
0x18000a0b1  mov     rcx, rdx; this
0x18000a0b4  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a0b9  mov     rax, [rsp+140h+var_100]
0x18000a0be  mov     r8, [rsp+140h+var_108]
0x18000a0c3  inc     dword ptr [r8]
0x18000a0c6  mov     rcx, [rdi+20h]; this
0x18000a0ca  mov     [rdi+20h], rax
0x18000a0ce  test    rcx, rcx
0x18000a0d1  jz      loc_18000A3A5
0x18000a0d7  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a0dc  jmp     short loc_18000A119
0x18000a0de  test    rdi, rdi
0x18000a0e1  jnz     loc_180009F2C
0x18000a0e7  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits+1, 2
0x18000a0ee  jz      loc_180009EEA
0x18000a0f4  lea     rax, [rbp+40h+var_70]
0x18000a0f8  mov     [rsp+140h+var_120], rax
0x18000a0fd  mov     r9d, 1
0x18000a103  lea     rdx, IoCompletionPort_RemovedEndOfBatch
0x18000a10a  call    McGenEventWrite_EventWriteTransfer
0x18000a10f  jmp     loc_180009EEA
0x18000a114  test    r14, r14
0x18000a117  jz      short loc_18000A122
0x18000a119  inc     dword ptr [r14+10h]
0x18000a11d  mov     rax, [rsp+140h+var_100]
0x18000a122  mov     rcx, [rax+20h]; this
0x18000a126  mov     [rax+20h], r14
0x18000a12a  test    rcx, rcx
0x18000a12d  jz      short loc_18000A139
0x18000a12f  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a134  mov     rax, [rsp+140h+var_100]
0x18000a139  test    rdi, rdi
0x18000a13c  jz      short loc_18000A141
0x18000a13e  inc     dword ptr [rdi+10h]
0x18000a141  mov     rcx, [rax+28h]; this
0x18000a145  mov     [rax+28h], rdi
0x18000a149  test    rcx, rcx
0x18000a14c  jz      short loc_18000A153
0x18000a14e  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a153  test    rdi, rdi
0x18000a156  jz      short loc_18000A160
0x18000a158  mov     rcx, rdi; this
0x18000a15b  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a160  test    r14, r14
0x18000a163  jz      short loc_18000A16D
0x18000a165  mov     rcx, r14; this
0x18000a168  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a16d  mov     rax, [rsp+140h+var_110]
0x18000a172  test    rax, rax
0x18000a175  jz      short loc_18000A17F
0x18000a177  mov     rcx, rax; this
0x18000a17a  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a17f  mov     rax, [rsp+140h+var_108]
0x18000a184  inc     dword ptr [rax]
0x18000a186  mov     r14, [rsp+140h+var_F8]
0x18000a18b  mov     rcx, [r14+20h]; this
0x18000a18f  mov     rdi, [rsp+140h+var_100]
0x18000a194  mov     [r14+20h], rdi
0x18000a198  test    rcx, rcx
0x18000a19b  jz      short loc_18000A1A2
0x18000a19d  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a1a2  or      dword ptr [r13+58h], 200h
0x18000a1aa  mov     edx, 9
0x18000a1af  mov     rcx, r13
0x18000a1b2  call    ?Activate@DispatchItem@Dispatch@CoreUI@Microsoft@@QEAAXW4InternalPriority@234@@Z; Microsoft::CoreUI::Dispatch::DispatchItem::Activate(Microsoft::CoreUI::Dispatch::InternalPriority)
0x18000a1b7  nop
0x18000a1b8  test    r14, r14
0x18000a1bb  jz      short loc_18000A1C6
0x18000a1bd  mov     rcx, r14; this
0x18000a1c0  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a1c5  nop
0x18000a1c6  test    rdi, rdi
0x18000a1c9  jz      short loc_18000A1D4
0x18000a1cb  mov     rcx, rdi; this
0x18000a1ce  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a1d3  nop
0x18000a1d4  mov     rcx, [rsp+140h+var_F0]; this
0x18000a1d9  test    rcx, rcx
0x18000a1dc  jz      short loc_18000A1E4
0x18000a1de  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a1e3  nop
0x18000a1e4  mov     rcx, r13; this
0x18000a1e7  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a1ec  nop
0x18000a1ed  test    rsi, rsi
0x18000a1f0  jz      short loc_18000A1FB
0x18000a1f2  mov     rcx, rsi; this
0x18000a1f5  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a1fa  nop
0x18000a1fb  mov     rcx, [rsp+140h+var_D0]; this
0x18000a200  test    rcx, rcx
0x18000a203  jz      short loc_18000A20A
0x18000a205  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000a20a  xor     r14d, r14d
0x18000a20d  inc     r12d
0x18000a210  cmp     r12d, 2
0x18000a214  jnz     loc_180009E2F
0x18000a21a  mov     rdi, [r15+60h]
0x18000a21e  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18000a224  call    cs:__imp_TlsGetValue
0x18000a22a  mov     rcx, [rax+30h]
0x18000a22e  mov     r9d, [rcx+48h]
0x18000a232  mov     [rsp+140h+var_118], r14
0x18000a237  mov     dword ptr [rsp+140h+var_120], r14d
0x18000a23c  xor     r8d, r8d
0x18000a23f  mov     rdx, rdi
  ... truncated ...
```
