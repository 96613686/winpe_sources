# Microsoft::CoreUI::Dispatch::ThreadContext::Init$(bool,bool,bool)

- ea: `0x180051c90`
- end: `0x180051fe3`
- name: `?Init$@ThreadContext@Dispatch@CoreUI@Microsoft@@IEAAX_N00@Z`
- size: `851`
- prototype: `void __fastcall(Microsoft::CoreUI::Dispatch::ThreadContext *__hidden this, bool, bool, bool)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180051c20`

## callees

- `0x18000ec10`
- `0x180010ed0`
- `0x180023288`
- `0x18002c4c8`
- `0x18002eb74`
- `0x18004ffc4`
- `0x180051c90`
- `0x180051fec`
- `0x18005219c`
- `0x18005227c`
- `0x1800522ac`
- `0x180052324`
- `0x18005239c`
- `0x18005240c`
- `0x18008cc78`
- `0x18009d670`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180051d42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180051d42`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Microsoft::CoreUI::Dispatch::ThreadContext::Init$(System::Object **this, char a2, __int64 a3, char a4)
{
  char v5; // r15
  __int64 v8; // rax
  System::Object **v9; // r14
  DWORD CurrentThreadId; // eax
  __int64 *v11; // rax
  __int64 v12; // r8
  System::Object *v13; // rdx
  System::Object *v14; // rcx
  __int64 *v15; // rax
  System::Object *v16; // rdx
  System::Object *v17; // rcx
  System::Object *v18; // rdi
  System::Object *v19; // rsi
  __int64 v20; // rdx
  System::Object *v21; // r9
  System::Object *v22; // rdi
  int v23; // eax
  __int64 *v24; // rax
  System::Object *v25; // rdx
  System::Object *v26; // rcx
  __int64 *v27; // rax
  __int64 v28; // r9
  System::Object *v29; // rdx
  System::Object *v30; // rcx
  System::Object *v31; // rdi
  int v32; // eax
  __int64 *v33; // rax
  __int64 v34; // r8
  System::Object *v35; // rdx
  System::Object *v36; // rcx
  System::Object *v37; // rcx
  ULONGLONG v38; // rbx
  Microsoft::CoreUI::Messaging::InterconnectMessageAdapter *v39; // rdi
  System::Object *v40; // [rsp+30h] [rbp-30h] BYREF
  System::Object *v41; // [rsp+38h] [rbp-28h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v42; // [rsp+40h] [rbp-20h] BYREF

  v5 = a3;
  if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer((__int64)this, &Session_ConstructThreadContext_Start, a3, 1u, &v42);
  CFlat::ContextLocal$1<CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::ThreadContext>>::set_Value(this, this);
  *((_DWORD *)this + 23) = 0;
  this[12] = (System::Object *)(this + 14);
  *((_DWORD *)this + 27) = 8;
  *((_DWORD *)this + 26) = 0;
  this[18] = (System::Object *)(this + 20);
  *((_DWORD *)this + 39) = 8;
  *((_DWORD *)this + 38) = 0;
  v8 = System::Object::Create$(&v41);
  v9 = this + 28;
  CFlat::SmartPtr<System::Action>::operator=(this + 28, v8);
  if ( v41 )
    System::Object::Release$(v41);
  if ( a2 )
    CurrentThreadId = 0;
  else
    CurrentThreadId = GetCurrentThreadId();
  *((_DWORD *)this + 44) = CurrentThreadId;
  CFlat::SmartPtr<Cn::Engine::Lock>::SmartPtr<Cn::Engine::Lock>(
    &v42,
    &Microsoft::CoreUI::Dispatch::ThreadContext::s_identityTable);
  CFlat::SmartPtr<Cn::Engine::Lock>::SmartPtr<Cn::Engine::Lock>(&v42.Size, &qword_180106830);
  v11 = (__int64 *)Microsoft::CoreUI::Identity::IdentityTableView::Create$(&v41, *((unsigned int *)this + 44), &v42);
  v13 = (System::Object *)*v11;
  *v11 = 0;
  v14 = this[10];
  this[10] = v13;
  if ( v14 )
    System::Object::ReleaseNotFrozen$(v14);
  if ( v41 )
    System::Object::ReleaseNotFrozen$(v41);
  if ( v5 )
  {
    v41 = 0;
    v15 = (__int64 *)Microsoft::CoreUI::Registrar::RegistrarClient::Create$(&v40);
    v16 = (System::Object *)*v15;
    *v15 = 0;
    v17 = this[8];
    this[8] = v16;
    if ( v17 )
      System::Object::ReleaseNotFrozen$(v17);
    if ( v40 )
      System::Object::ReleaseNotFrozen$(v40);
    v18 = this[8];
    v40 = v18;
    if ( v18 )
      ++*((_DWORD *)v18 + 4);
    v19 = this[10];
    v42.Ptr = (ULONGLONG)v19;
    if ( v19 )
      ++*((_DWORD *)v19 + 4);
    Microsoft::CoreUI::Registrar::RegistrarClient::Initialize(v18, (__int64)(this + 4));
    if ( v19 )
      System::Object::ReleaseNotFrozen$(v19);
    if ( v18 )
      System::Object::ReleaseNotFrozen$(v18);
    v21 = v41;
    v22 = *v9;
    if ( *v9 )
    {
      v23 = *((_DWORD *)v22 + 4);
      if ( v23 > 0 )
        *((_DWORD *)v22 + 4) = v23 + 1;
    }
    v24 = (__int64 *)Microsoft::CoreUI::Services::ThreadEndpoint::Create$(&v40, v20, this, v21);
    v25 = (System::Object *)*v24;
    *v24 = 0;
    v26 = this[9];
    this[9] = v25;
    if ( v26 )
      System::Object::ReleaseNotFrozen$(v26);
    if ( v40 )
      System::Object::ReleaseNotFrozen$(v40);
    if ( v22 )
      System::Object::Release$(v22);
  }
  LOBYTE(v12) = a4;
  v27 = (__int64 *)Microsoft::CoreUI::Dispatch::EventLoop::Create$(&v40, this, v12);
  v29 = (System::Object *)*v27;
  *v27 = 0;
  v30 = this[5];
  this[5] = v29;
  if ( v30 )
    System::Object::ReleaseNotFrozen$(v30);
  if ( v40 )
    System::Object::ReleaseNotFrozen$(v40);
  v31 = *v9;
  v42.Ptr = (ULONGLONG)v31;
  if ( v31 )
  {
    v32 = *((_DWORD *)v31 + 4);
    if ( v32 > 0 )
      *((_DWORD *)v31 + 4) = v32 + 1;
  }
  LOBYTE(v28) = v5;
  v33 = (__int64 *)Microsoft::CoreUI::Messaging::MessageSession::Create$(&v40, v29, this, v28);
  v35 = (System::Object *)*v33;
  *v33 = 0;
  v36 = this[6];
  this[6] = v35;
  if ( v36 )
    System::Object::ReleaseNotFrozen$(v36);
  v37 = v40;
  if ( v40 )
    System::Object::ReleaseNotFrozen$(v40);
  if ( v31 )
    System::Object::Release$(v31);
  v38 = (ULONGLONG)this[6];
  v42.Ptr = v38;
  if ( v38 )
    ++*(_DWORD *)(v38 + 16);
  v39 = *(Microsoft::CoreUI::Messaging::InterconnectMessageAdapter **)(v38 + 152);
  if ( v39 )
  {
    v40 = *(System::Object **)(v38 + 152);
    ++*((_DWORD *)v39 + 4);
    Microsoft::CoreUI::Messaging::InterconnectMessageAdapter::CompleteInitialization(v39);
    System::Object::ReleaseNotFrozen$(v39);
  }
  if ( v38 )
    System::Object::ReleaseNotFrozen$((System::Object *)v38);
  if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer((__int64)v37, &Session_ConstructThreadContext_Stop, v34, 1u, &v42);
}

```

## disassembly

```asm
0x180051c90  push    rbp
0x180051c92  push    rbx
0x180051c93  push    rsi
0x180051c94  push    rdi
0x180051c95  push    r12
0x180051c97  push    r14
0x180051c99  push    r15
0x180051c9b  mov     rbp, rsp
0x180051c9e  sub     rsp, 60h
0x180051ca2  mov     rax, cs:__security_cookie
0x180051ca9  xor     rax, rsp
0x180051cac  mov     [rbp+var_10], rax
0x180051cb0  mov     r12b, r9b
0x180051cb3  mov     r15b, r8b
0x180051cb6  mov     dil, dl
0x180051cb9  mov     rbx, rcx
0x180051cbc  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits, 8
0x180051cc3  jnz     loc_180051FC3
0x180051cc9  mov     rdx, rbx
0x180051ccc  call    ?set_Value@?$ContextLocal$1@V?$SmartPtr@VThreadContext@Dispatch@CoreUI@Microsoft@@@CFlat@@@CFlat@@QEAAXPEAVThreadContext@Dispatch@CoreUI@Microsoft@@@Z; CFlat::ContextLocal$1<CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::ThreadContext>>::set_Value(Microsoft::CoreUI::Dispatch::ThreadContext *)
0x180051cd1  mov     dword ptr [rbx+5Ch], 0
0x180051cd8  lea     rax, [rbx+70h]
0x180051cdc  mov     [rbx+60h], rax
0x180051ce0  mov     dword ptr [rbx+6Ch], 8
0x180051ce7  mov     dword ptr [rbx+68h], 0
0x180051cee  lea     rax, [rbx+0A0h]
0x180051cf5  mov     [rbx+90h], rax
0x180051cfc  mov     dword ptr [rbx+9Ch], 8
0x180051d06  mov     dword ptr [rbx+98h], 0
0x180051d10  lea     rcx, [rbp+var_28]
0x180051d14  call    ?Create$@Object@System@@SA?AV?$SmartPtr@VObject@System@@@CFlat@@XZ; System::Object::Create$(void)
0x180051d19  lea     r14, [rbx+0E0h]
0x180051d20  mov     rdx, rax
0x180051d23  mov     rcx, r14
0x180051d26  call    ??4?$SmartPtr@VAction@System@@@CFlat@@QEAAAEAV01@$$QEAV01@@Z; CFlat::SmartPtr<System::Action>::operator=(CFlat::SmartPtr<System::Action> &&)
0x180051d2b  mov     rcx, [rbp+var_28]; this
0x180051d2f  test    rcx, rcx
0x180051d32  jz      short loc_180051D39
0x180051d34  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x180051d39  test    dil, dil
0x180051d3c  jnz     loc_180051F9F
0x180051d42  call    cs:__imp_GetCurrentThreadId
0x180051d48  mov     [rbx+0B0h], eax
0x180051d4e  lea     rdx, ?s_identityTable@ThreadContext@Dispatch@CoreUI@Microsoft@@2UIdentityTable@Identity@34@A; Microsoft::CoreUI::Identity::IdentityTable Microsoft::CoreUI::Dispatch::ThreadContext::s_identityTable
0x180051d55  lea     rcx, [rbp+var_20]
0x180051d59  call    ??0?$SmartPtr@VLock@Engine@Cn@@@CFlat@@QEAA@AEBV01@@Z; CFlat::SmartPtr<Cn::Engine::Lock>::SmartPtr<Cn::Engine::Lock>(CFlat::SmartPtr<Cn::Engine::Lock> const &)
0x180051d5e  lea     rdx, qword_180106830
0x180051d65  lea     rcx, [rbp+var_18]
0x180051d69  call    ??0?$SmartPtr@VLock@Engine@Cn@@@CFlat@@QEAA@AEBV01@@Z; CFlat::SmartPtr<Cn::Engine::Lock>::SmartPtr<Cn::Engine::Lock>(CFlat::SmartPtr<Cn::Engine::Lock> const &)
0x180051d6e  lea     r8, [rbp+var_20]
0x180051d72  mov     edx, [rbx+0B0h]
0x180051d78  lea     rcx, [rbp+var_28]
0x180051d7c  call    ?Create$@IdentityTableView@Identity@CoreUI@Microsoft@@SA?AV?$SmartPtr@VIdentityTableView@Identity@CoreUI@Microsoft@@@CFlat@@IUIdentityTable@234@@Z; Microsoft::CoreUI::Identity::IdentityTableView::Create$(uint,Microsoft::CoreUI::Identity::IdentityTable)
0x180051d81  mov     rdx, [rax]
0x180051d84  mov     qword ptr [rax], 0
0x180051d8b  mov     rcx, [rbx+50h]; this
0x180051d8f  mov     [rbx+50h], rdx
0x180051d93  test    rcx, rcx
0x180051d96  jz      short loc_180051D9D
0x180051d98  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180051d9d  mov     rcx, [rbp+var_28]; this
0x180051da1  test    rcx, rcx
0x180051da4  jz      short loc_180051DAB
0x180051da6  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180051dab  test    r15b, r15b
0x180051dae  jz      loc_180051EA1
0x180051db4  mov     [rbp+var_28], 0
0x180051dbc  lea     rcx, [rbp+var_30]
0x180051dc0  call    ?Create$@RegistrarClient@Registrar@CoreUI@Microsoft@@SA?AV?$SmartPtr@VRegistrarClient@Registrar@CoreUI@Microsoft@@@CFlat@@XZ; Microsoft::CoreUI::Registrar::RegistrarClient::Create$(void)
0x180051dc5  mov     rdx, [rax]
0x180051dc8  mov     qword ptr [rax], 0
0x180051dcf  mov     rcx, [rbx+40h]; this
0x180051dd3  mov     [rbx+40h], rdx
0x180051dd7  test    rcx, rcx
0x180051dda  jz      short loc_180051DE1
0x180051ddc  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180051de1  mov     rcx, [rbp+var_30]; this
0x180051de5  test    rcx, rcx
0x180051de8  jz      short loc_180051DEF
0x180051dea  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180051def  mov     rdi, [rbx+40h]
0x180051df3  mov     [rbp+var_30], rdi
0x180051df7  test    rdi, rdi
0x180051dfa  jz      short loc_180051DFF
0x180051dfc  inc     dword ptr [rdi+10h]
0x180051dff  lea     rax, [rbx+20h]
0x180051e03  mov     rsi, [rbx+50h]
0x180051e07  mov     [rbp+var_20], rsi
0x180051e0b  test    rsi, rsi
0x180051e0e  jz      short loc_180051E13
0x180051e10  inc     dword ptr [rsi+10h]
0x180051e13  mov     [rsp+60h+var_40], rax; __int64
0x180051e18  lea     r9, [rbp+var_28]
0x180051e1c  mov     r8, rbx
0x180051e1f  mov     rdx, rsi
0x180051e22  mov     rcx, rdi; this
0x180051e25  call    ?Initialize@RegistrarClient@Registrar@CoreUI@Microsoft@@QEAAXPEAVIdentityTableView@Identity@34@PEAVThreadContext@Dispatch@34@U?$Ref@UHIDENTITY@CoreUI@Microsoft@@@CFlat@@2@Z; Microsoft::CoreUI::Registrar::RegistrarClient::Initialize(Microsoft::CoreUI::Identity::IdentityTableView *,Microsoft::CoreUI::Dispatch::ThreadContext *,CFlat::Ref<Microsoft::CoreUI::HIDENTITY>,CFlat::Ref<Microsoft::CoreUI::HIDENTITY>)
0x180051e2a  nop
0x180051e2b  test    rsi, rsi
0x180051e2e  jz      short loc_180051E39
0x180051e30  mov     rcx, rsi; this
0x180051e33  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180051e38  nop
0x180051e39  test    rdi, rdi
0x180051e3c  jz      short loc_180051E46
0x180051e3e  mov     rcx, rdi; this
0x180051e41  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180051e46  mov     r9, [rbp+var_28]
0x180051e4a  mov     rdi, [r14]
0x180051e4d  test    rdi, rdi
0x180051e50  jz      short loc_180051E5E
0x180051e52  mov     eax, [rdi+10h]
0x180051e55  test    eax, eax
0x180051e57  jle     short loc_180051E5E
0x180051e59  inc     eax
0x180051e5b  mov     [rdi+10h], eax
0x180051e5e  mov     r8, rbx
0x180051e61  lea     rcx, [rbp+var_30]
0x180051e65  call    ?Create$@ThreadEndpoint@Services@CoreUI@Microsoft@@SA?AV?$SmartPtr@VThreadEndpoint@Services@CoreUI@Microsoft@@@CFlat@@PEAVObject@System@@PEAVThreadContext@Dispatch@34@UHIDENTITY@34@@Z; Microsoft::CoreUI::Services::ThreadEndpoint::Create$(System::Object *,Microsoft::CoreUI::Dispatch::ThreadContext *,Microsoft::CoreUI::HIDENTITY)
0x180051e6a  mov     rdx, [rax]
0x180051e6d  mov     qword ptr [rax], 0
0x180051e74  mov     rcx, [rbx+48h]; this
0x180051e78  mov     [rbx+48h], rdx
0x180051e7c  test    rcx, rcx
0x180051e7f  jz      short loc_180051E86
0x180051e81  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180051e86  mov     rcx, [rbp+var_30]; this
0x180051e8a  test    rcx, rcx
0x180051e8d  jz      short loc_180051E94
0x180051e8f  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180051e94  test    rdi, rdi
0x180051e97  jz      short loc_180051EA1
0x180051e99  mov     rcx, rdi; this
0x180051e9c  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x180051ea1  mov     r8b, r12b
0x180051ea4  mov     rdx, rbx
0x180051ea7  lea     rcx, [rbp+var_30]
0x180051eab  call    ?Create$@EventLoop@Dispatch@CoreUI@Microsoft@@SA?AV?$SmartPtr@VEventLoop@Dispatch@CoreUI@Microsoft@@@CFlat@@PEAVThreadContext@234@_N@Z; Microsoft::CoreUI::Dispatch::EventLoop::Create$(Microsoft::CoreUI::Dispatch::ThreadContext *,bool)
0x180051eb0  mov     rdx, [rax]
0x180051eb3  mov     qword ptr [rax], 0
0x180051eba  mov     rcx, [rbx+28h]; this
0x180051ebe  mov     [rbx+28h], rdx
0x180051ec2  test    rcx, rcx
0x180051ec5  jz      short loc_180051ECC
0x180051ec7  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180051ecc  mov     rcx, [rbp+var_30]; this
0x180051ed0  test    rcx, rcx
0x180051ed3  jz      short loc_180051EDA
0x180051ed5  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180051eda  mov     rdi, [r14]
0x180051edd  mov     [rbp+var_20], rdi
0x180051ee1  test    rdi, rdi
0x180051ee4  jz      short loc_180051EF2
0x180051ee6  mov     eax, [rdi+10h]
0x180051ee9  test    eax, eax
0x180051eeb  jle     short loc_180051EF2
0x180051eed  inc     eax
0x180051eef  mov     [rdi+10h], eax
0x180051ef2  mov     r9b, r15b
0x180051ef5  mov     r8, rbx
0x180051ef8  lea     rcx, [rbp+var_30]
0x180051efc  call    ?Create$@MessageSession@Messaging@CoreUI@Microsoft@@SA?AV?$SmartPtr@VMessageSession@Messaging@CoreUI@Microsoft@@@CFlat@@PEAVObject@System@@PEAVThreadContext@Dispatch@34@_N@Z; Microsoft::CoreUI::Messaging::MessageSession::Create$(System::Object *,Microsoft::CoreUI::Dispatch::ThreadContext *,bool)
0x180051f01  mov     rdx, [rax]
0x180051f04  mov     qword ptr [rax], 0
0x180051f0b  mov     rcx, [rbx+30h]; this
0x180051f0f  mov     [rbx+30h], rdx
0x180051f13  test    rcx, rcx
0x180051f16  jz      short loc_180051F1D
0x180051f18  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180051f1d  mov     rcx, [rbp+var_30]; this
0x180051f21  test    rcx, rcx
0x180051f24  jz      short loc_180051F2C
0x180051f26  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180051f2b  nop
0x180051f2c  test    rdi, rdi
0x180051f2f  jz      short loc_180051F39
0x180051f31  mov     rcx, rdi; this
0x180051f34  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x180051f39  mov     rbx, [rbx+30h]
0x180051f3d  mov     [rbp+var_20], rbx
0x180051f41  test    rbx, rbx
0x180051f44  jz      short loc_180051F49
0x180051f46  inc     dword ptr [rbx+10h]
0x180051f49  mov     rdi, [rbx+98h]
0x180051f50  test    rdi, rdi
0x180051f53  jz      short loc_180051F6E
0x180051f55  mov     [rbp+var_30], rdi
0x180051f59  inc     dword ptr [rdi+10h]
0x180051f5c  mov     rcx, rdi; this
0x180051f5f  call    ?CompleteInitialization@InterconnectMessageAdapter@Messaging@CoreUI@Microsoft@@QEAAXXZ; Microsoft::CoreUI::Messaging::InterconnectMessageAdapter::CompleteInitialization(void)
0x180051f64  nop
0x180051f65  mov     rcx, rdi; this
0x180051f68  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180051f6d  nop
0x180051f6e  test    rbx, rbx
0x180051f71  jz      short loc_180051F7B
0x180051f73  mov     rcx, rbx; this
0x180051f76  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180051f7b  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits, 8
0x180051f82  jnz     short loc_180051FA6
0x180051f84  mov     rcx, [rbp+var_10]
0x180051f88  xor     rcx, rsp; StackCookie
0x180051f8b  call    __security_check_cookie
0x180051f90  add     rsp, 60h
0x180051f94  pop     r15
0x180051f96  pop     r14
0x180051f98  pop     r12
0x180051f9a  pop     rdi
0x180051f9b  pop     rsi
0x180051f9c  pop     rbx
0x180051f9d  pop     rbp
0x180051f9e  retn
0x180051f9f  xor     eax, eax
0x180051fa1  jmp     loc_180051D48
0x180051fa6  lea     rax, [rbp+var_20]
0x180051faa  mov     [rsp+60h+var_40], rax
0x180051faf  mov     r9d, 1
0x180051fb5  lea     rdx, Session_ConstructThreadContext_Stop
0x180051fbc  call    McGenEventWrite_EventWriteTransfer
0x180051fc1  jmp     short loc_180051F84
0x180051fc3  lea     rax, [rbp+var_20]
0x180051fc7  mov     [rsp+60h+var_40], rax
0x180051fcc  mov     r9d, 1
0x180051fd2  lea     rdx, Session_ConstructThreadContext_Start
0x180051fd9  call    McGenEventWrite_EventWriteTransfer
0x180051fde  jmp     loc_180051CC9
```
