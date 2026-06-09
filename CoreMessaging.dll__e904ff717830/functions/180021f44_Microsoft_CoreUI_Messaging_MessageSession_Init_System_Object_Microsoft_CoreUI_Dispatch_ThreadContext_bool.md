# Microsoft::CoreUI::Messaging::MessageSession::Init$(System::Object *,Microsoft::CoreUI::Dispatch::ThreadContext *,bool)

- ea: `0x180021f44`
- end: `0x18002224f`
- name: `?Init$@MessageSession@Messaging@CoreUI@Microsoft@@IEAAXPEAVObject@System@@PEAVThreadContext@Dispatch@34@_N@Z`
- size: `779`
- prototype: `void __fastcall(Microsoft::CoreUI::Messaging::MessageSession *__hidden this, struct System::Object *, struct Microsoft::CoreUI::Dispatch::ThreadContext *, bool)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180052324`

## callees

- `0x1800058d4`
- `0x18000ec10`
- `0x180017bc0`
- `0x18001ab10`
- `0x180021e38`
- `0x180021f44`
- `0x180022258`
- `0x1800222b8`
- `0x18002375c`
- `0x18002ef20`
- `0x18003950c`
- `0x18005fa28`
- `0x180081a50`
- `0x18008cc78`
- `0x18009d670`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800221a7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800221a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022211`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022211`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Microsoft::CoreUI::Messaging::MessageSession::Init$(
        Microsoft::CoreUI::Messaging::MessageSession *this,
        struct System::Object *a2,
        System::Object **a3,
        char a4)
{
  System::Object *v7; // rbx
  __int64 *v8; // rax
  __int64 v9; // rcx
  System::Object *v10; // rax
  __int64 *v11; // rax
  __int64 v12; // rcx
  System::Object *v13; // rax
  System::Object *v14; // rax
  System::Object *v15; // rcx
  System::Object *v16; // rdx
  __int64 *v17; // rax
  const struct CFlat::NewTagType *v18; // rdx
  __int64 v19; // rcx
  System::Object *v20; // rax
  _QWORD *v21; // rax
  _QWORD *v22; // rbx
  System::Object *v23; // rsi
  __int64 Waits; // rax
  System::Object *v25; // rcx
  HANDLE EventW; // rax
  __int64 v27; // rcx
  __int64 v28; // r8
  signed int LastError; // eax
  System::Object *v30; // [rsp+30h] [rbp-30h] BYREF
  int v31; // [rsp+38h] [rbp-28h]
  _QWORD *v32; // [rsp+40h] [rbp-20h]
  struct _EVENT_DATA_DESCRIPTOR v33; // [rsp+48h] [rbp-18h] BYREF

  v31 = 0;
  if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 0x80u) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (__int64)this,
      (const EVENT_DESCRIPTOR *)Messaging_ConstructMessageSession_Start,
      (__int64)a3,
      1u,
      &v33);
  ++*((_DWORD *)this + 8);
  CFlat::SmartPtr<Microsoft::CoreUI::Registrar::RegistrarPartitionContext>::operator=((char *)this + 96, a3);
  CFlat::SmartPtr<Microsoft::CoreUI::Registrar::RegistrarPartitionContext>::operator=((char *)this + 104, a3[5]);
  CFlat::SmartPtr<Microsoft::CoreUI::Registrar::RegistrarPartitionContext>::operator=((char *)this + 112, a3[10]);
  v7 = a3[5];
  if ( v7 )
    ++*((_DWORD *)v7 + 4);
  v8 = (__int64 *)Microsoft::CoreUI::Buffering::BufferManager::Create$(&v30, v7);
  v9 = *v8;
  *v8 = 0;
  v10 = (System::Object *)*((_QWORD *)this + 15);
  *((_QWORD *)this + 15) = v9;
  if ( v10 )
    System::Object::ReleaseNotFrozen$(v10);
  if ( v30 )
    System::Object::ReleaseNotFrozen$(v30);
  if ( v7 )
    System::Object::ReleaseNotFrozen$(v7);
  Microsoft::CoreUI::Messaging::MessageSession::s_localProcessId = Cn::Engine::Direct::_backingField$CurrentProcessId$;
  v11 = (__int64 *)Microsoft::CoreUI::Messaging::MessageInfo::Create$(&v30, this);
  v12 = *v11;
  *v11 = 0;
  v13 = (System::Object *)*((_QWORD *)this + 18);
  *((_QWORD *)this + 18) = v12;
  if ( v13 )
    System::Object::ReleaseNotFrozen$(v13);
  if ( v30 )
    System::Object::ReleaseNotFrozen$(v30);
  CFlat::MemoryManagement::Allocate<CFlat::SmartPtr<Microsoft::CoreUI::Messaging::LocalMessageAdapter>>(&v30);
  v31 = 1;
  Microsoft::CoreUI::Messaging::LocalMessageAdapter::Init$(v30, this);
  v14 = v30;
  v15 = 0;
  v30 = 0;
  v16 = (System::Object *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = v14;
  if ( v16 )
  {
    System::Object::ReleaseNotFrozen$(v16);
    v15 = v30;
  }
  if ( v15 )
    System::Object::ReleaseNotFrozen$(v15);
  if ( a4 )
  {
    v17 = (__int64 *)Microsoft::CoreUI::Messaging::InterconnectMessageAdapter::Create$(&v30, this);
    v19 = *v17;
    *v17 = 0;
    v20 = (System::Object *)*((_QWORD *)this + 19);
    *((_QWORD *)this + 19) = v19;
    if ( v20 )
      System::Object::ReleaseNotFrozen$(v20);
    if ( v30 )
      System::Object::ReleaseNotFrozen$(v30);
    v21 = System::Object::operator new(0x40u, v18);
    v22 = v21;
    if ( v21 )
    {
      v21[1] = &qword_1800D0620;
      *((_DWORD *)v21 + 4) = 1;
      *((_WORD *)v21 + 12) = 0;
      v21[4] = 0;
      *v21 = &Microsoft::CoreUI::Messaging::AlpcSendMessageAdapter::`vftable';
      v21[5] = 0;
      v21[6] = 0;
      v21[7] = 0;
    }
    else
    {
      v22 = 0;
    }
    v32 = v22;
    v31 = 2;
    CFlat::SmartPtr<Microsoft::CoreUI::Registrar::RegistrarPartitionContext>::operator=(v22 + 4, this);
    v23 = *(System::Object **)(*((_QWORD *)this + 12) + 40LL);
    v33.Ptr = (ULONGLONG)v23;
    if ( v23 )
      ++*((_DWORD *)v23 + 4);
    Waits = Microsoft::CoreUI::Dispatch::EventLoop::get_Waits(v23, &v30);
    CFlat::SmartPtr<System::Collections::Generic::List$1<CFlat::SmartPtr<System::Object>>>::operator=(v22 + 6, Waits);
    if ( v30 )
      System::Object::ReleaseNotFrozen$(v30);
    if ( v23 )
      System::Object::ReleaseNotFrozen$(v23);
    v25 = (System::Object *)*((_QWORD *)this + 22);
    *((_QWORD *)this + 22) = v22;
    if ( v25 )
      System::Object::ReleaseNotFrozen$(v25);
  }
  EventW = CreateEventW(0, 1, 0, 0);
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    CFlat::Abandonment::FailWithHR(LastError, 0, 0);
  }
  *((_QWORD *)this + 31) = EventW;
  Microsoft::CoreUI::Messaging::MessageSession::RegisterAdapterCleanupWait(this);
  if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 0x80u) != 0 )
    McGenEventWrite_EventWriteTransfer(
      v27,
      (const EVENT_DESCRIPTOR *)Messaging_ConstructMessageSession_Stop,
      v28,
      1u,
      &v33);
}

```

## disassembly

```asm
0x180021f44  mov     [rsp-28h+arg_8], rbx
0x180021f49  mov     [rsp-28h+arg_18], rsi
0x180021f4e  push    rbp
0x180021f4f  push    rdi
0x180021f50  push    r12
0x180021f52  push    r14
0x180021f54  push    r15
0x180021f56  mov     rbp, rsp
0x180021f59  sub     rsp, 60h
0x180021f5d  mov     rax, cs:__security_cookie
0x180021f64  xor     rax, rsp
0x180021f67  mov     [rbp+var_8], rax
0x180021f6b  mov     sil, r9b
0x180021f6e  mov     rbx, r8
0x180021f71  mov     rdi, rcx
0x180021f74  xor     r15d, r15d
0x180021f77  mov     [rbp+var_28], r15d
0x180021f7b  lea     r12d, [r15+1]
0x180021f7f  cmp     byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits, r15b
0x180021f86  jl      loc_180022228
0x180021f8c  add     [rdi+20h], r12d
0x180021f90  mov     rdx, rbx
0x180021f93  lea     rcx, [rdi+60h]
0x180021f97  call    ??4?$SmartPtr@VRegistrarPartitionContext@Registrar@CoreUI@Microsoft@@@CFlat@@QEAAAEAV01@PEAVRegistrarPartitionContext@Registrar@CoreUI@Microsoft@@@Z; CFlat::SmartPtr<Microsoft::CoreUI::Registrar::RegistrarPartitionContext>::operator=(Microsoft::CoreUI::Registrar::RegistrarPartitionContext *)
0x180021f9c  lea     rcx, [rdi+68h]
0x180021fa0  mov     rdx, [rbx+28h]
0x180021fa4  call    ??4?$SmartPtr@VRegistrarPartitionContext@Registrar@CoreUI@Microsoft@@@CFlat@@QEAAAEAV01@PEAVRegistrarPartitionContext@Registrar@CoreUI@Microsoft@@@Z; CFlat::SmartPtr<Microsoft::CoreUI::Registrar::RegistrarPartitionContext>::operator=(Microsoft::CoreUI::Registrar::RegistrarPartitionContext *)
0x180021fa9  lea     rcx, [rdi+70h]
0x180021fad  mov     rdx, [rbx+50h]
0x180021fb1  call    ??4?$SmartPtr@VRegistrarPartitionContext@Registrar@CoreUI@Microsoft@@@CFlat@@QEAAAEAV01@PEAVRegistrarPartitionContext@Registrar@CoreUI@Microsoft@@@Z; CFlat::SmartPtr<Microsoft::CoreUI::Registrar::RegistrarPartitionContext>::operator=(Microsoft::CoreUI::Registrar::RegistrarPartitionContext *)
0x180021fb6  mov     rbx, [rbx+28h]
0x180021fba  test    rbx, rbx
0x180021fbd  jz      short loc_180021FC3
0x180021fbf  add     [rbx+10h], r12d
0x180021fc3  mov     rdx, rbx
0x180021fc6  lea     rcx, [rbp+var_30]
0x180021fca  call    ?Create$@BufferManager@Buffering@CoreUI@Microsoft@@SA?AV?$SmartPtr@VBufferManager@Buffering@CoreUI@Microsoft@@@CFlat@@PEAVEventLoop@Dispatch@34@@Z; Microsoft::CoreUI::Buffering::BufferManager::Create$(Microsoft::CoreUI::Dispatch::EventLoop *)
0x180021fcf  mov     rcx, [rax]
0x180021fd2  mov     [rax], r15
0x180021fd5  mov     rax, [rdi+78h]
0x180021fd9  mov     [rdi+78h], rcx
0x180021fdd  test    rax, rax
0x180021fe0  jz      short loc_180021FEA
0x180021fe2  mov     rcx, rax; this
0x180021fe5  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180021fea  mov     rcx, [rbp+var_30]; this
0x180021fee  test    rcx, rcx
0x180021ff1  jz      short loc_180021FF8
0x180021ff3  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180021ff8  test    rbx, rbx
0x180021ffb  jz      short loc_180022005
0x180021ffd  mov     rcx, rbx; this
0x180022000  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180022005  mov     eax, cs:?_backingField$CurrentProcessId$@Direct@Engine@Cn@@0IA; uint Cn::Engine::Direct::_backingField$CurrentProcessId$
0x18002200b  mov     cs:?s_localProcessId@MessageSession@Messaging@CoreUI@Microsoft@@0IA, eax; uint Microsoft::CoreUI::Messaging::MessageSession::s_localProcessId
0x180022011  mov     rdx, rdi
0x180022014  lea     rcx, [rbp+var_30]
0x180022018  call    ?Create$@MessageInfo@Messaging@CoreUI@Microsoft@@SA?AV?$SmartPtr@VMessageInfo@Messaging@CoreUI@Microsoft@@@CFlat@@PEAVMessageSession@234@@Z; Microsoft::CoreUI::Messaging::MessageInfo::Create$(Microsoft::CoreUI::Messaging::MessageSession *)
0x18002201d  mov     rcx, [rax]
0x180022020  mov     [rax], r15
0x180022023  mov     rax, [rdi+90h]
0x18002202a  mov     [rdi+90h], rcx
0x180022031  test    rax, rax
0x180022034  jz      short loc_18002203E
0x180022036  mov     rcx, rax; this
0x180022039  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18002203e  mov     rcx, [rbp+var_30]; this
0x180022042  test    rcx, rcx
0x180022045  jz      short loc_18002204D
0x180022047  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18002204c  nop
0x18002204d  lea     rcx, [rbp+var_30]
0x180022051  call    ??$Allocate@V?$SmartPtr@VLocalMessageAdapter@Messaging@CoreUI@Microsoft@@@CFlat@@@MemoryManagement@CFlat@@SA?AV?$SmartPtr@VLocalMessageAdapter@Messaging@CoreUI@Microsoft@@@1@XZ; CFlat::MemoryManagement::Allocate<CFlat::SmartPtr<Microsoft::CoreUI::Messaging::LocalMessageAdapter>>(void)
0x180022056  mov     [rbp+var_28], r12d
0x18002205a  mov     rdx, rdi; struct Microsoft::CoreUI::Messaging::MessageSession *
0x18002205d  mov     rcx, [rbp+var_30]; this
0x180022061  call    ?Init$@LocalMessageAdapter@Messaging@CoreUI@Microsoft@@IEAAXPEAVMessageSession@234@@Z; Microsoft::CoreUI::Messaging::LocalMessageAdapter::Init$(Microsoft::CoreUI::Messaging::MessageSession *)
0x180022066  mov     rax, [rbp+var_30]
0x18002206a  mov     rcx, r15
0x18002206d  mov     [rbp+var_30], rcx
0x180022071  mov     rdx, [rdi+88h]
0x180022078  mov     [rdi+88h], rax
0x18002207f  test    rdx, rdx
0x180022082  jz      short loc_180022090
0x180022084  mov     rcx, rdx; this
0x180022087  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18002208c  mov     rcx, [rbp+var_30]; this
0x180022090  test    rcx, rcx
0x180022093  jz      short loc_18002209A
0x180022095  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18002209a  test    sil, sil
0x18002209d  jz      loc_18002219C
0x1800220a3  mov     rdx, rdi
0x1800220a6  lea     rcx, [rbp+var_30]
0x1800220aa  call    ?Create$@InterconnectMessageAdapter@Messaging@CoreUI@Microsoft@@SA?AV?$SmartPtr@VInterconnectMessageAdapter@Messaging@CoreUI@Microsoft@@@CFlat@@PEAVMessageSession@234@@Z; Microsoft::CoreUI::Messaging::InterconnectMessageAdapter::Create$(Microsoft::CoreUI::Messaging::MessageSession *)
0x1800220af  mov     rcx, [rax]
0x1800220b2  mov     [rax], r15
0x1800220b5  mov     rax, [rdi+98h]
0x1800220bc  mov     [rdi+98h], rcx
0x1800220c3  test    rax, rax
0x1800220c6  jz      short loc_1800220D0
0x1800220c8  mov     rcx, rax; this
0x1800220cb  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x1800220d0  mov     rcx, [rbp+var_30]; this
0x1800220d4  test    rcx, rcx
0x1800220d7  jz      short loc_1800220DF
0x1800220d9  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x1800220de  nop
0x1800220df  mov     ecx, 40h ; '@'; unsigned __int64
0x1800220e4  call    ??2Object@System@@SAPEAX_KAEBUNewTagType@CFlat@@@Z; System::Object::operator new(unsigned __int64,CFlat::NewTagType const &)
0x1800220e9  mov     rbx, rax
0x1800220ec  test    rax, rax
0x1800220ef  jz      loc_1800221EF
0x1800220f5  lea     rax, qword_1800D0620
0x1800220fc  mov     [rbx+8], rax
0x180022100  mov     [rbx+10h], r12d
0x180022104  mov     [rbx+18h], r15w
0x180022109  mov     [rbx+20h], r15
0x18002210d  lea     rax, ??_7AlpcSendMessageAdapter@Messaging@CoreUI@Microsoft@@6B@; const Microsoft::CoreUI::Messaging::AlpcSendMessageAdapter::`vftable'
0x180022114  mov     [rbx], rax
0x180022117  mov     [rbx+28h], r15
0x18002211b  mov     [rbx+30h], r15
0x18002211f  mov     [rbx+38h], r15
0x180022123  mov     [rbp+var_20], rbx
0x180022127  mov     [rbp+var_28], 2
0x18002212e  lea     rcx, [rbx+20h]
0x180022132  mov     rdx, rdi
0x180022135  call    ??4?$SmartPtr@VRegistrarPartitionContext@Registrar@CoreUI@Microsoft@@@CFlat@@QEAAAEAV01@PEAVRegistrarPartitionContext@Registrar@CoreUI@Microsoft@@@Z; CFlat::SmartPtr<Microsoft::CoreUI::Registrar::RegistrarPartitionContext>::operator=(Microsoft::CoreUI::Registrar::RegistrarPartitionContext *)
0x18002213a  mov     rax, [rdi+60h]
0x18002213e  mov     rsi, [rax+28h]
0x180022142  mov     qword ptr [rbp+var_18], rsi
0x180022146  test    rsi, rsi
0x180022149  jz      short loc_18002214F
0x18002214b  add     [rsi+10h], r12d
0x18002214f  lea     rdx, [rbp+var_30]
0x180022153  mov     rcx, rsi
0x180022156  call    ?get_Waits@EventLoop@Dispatch@CoreUI@Microsoft@@QEAA?AV?$SmartPtr@VWaitCollection@Dispatch@CoreUI@Microsoft@@@CFlat@@XZ; Microsoft::CoreUI::Dispatch::EventLoop::get_Waits(void)
0x18002215b  lea     rcx, [rbx+30h]
0x18002215f  mov     rdx, rax
0x180022162  call    ??4?$SmartPtr@V?$List$1@V?$SmartPtr@VObject@System@@@CFlat@@@Generic@Collections@System@@@CFlat@@QEAAAEAV01@$$QEAV01@@Z; CFlat::SmartPtr<System::Collections::Generic::List$1<CFlat::SmartPtr<System::Object>>>::operator=(CFlat::SmartPtr<System::Collections::Generic::List$1<CFlat::SmartPtr<System::Object>>> &&)
0x180022167  mov     rcx, [rbp+var_30]; this
0x18002216b  test    rcx, rcx
0x18002216e  jz      short loc_180022176
0x180022170  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180022175  nop
0x180022176  test    rsi, rsi
0x180022179  jz      short loc_180022183
0x18002217b  mov     rcx, rsi; this
0x18002217e  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180022183  mov     rcx, [rdi+0B0h]; this
0x18002218a  mov     [rdi+0B0h], rbx
0x180022191  test    rcx, rcx
0x180022194  jz      short loc_18002219C
0x180022196  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18002219b  nop
0x18002219c  xor     r9d, r9d; lpName
0x18002219f  xor     r8d, r8d; bInitialState
0x1800221a2  mov     edx, r12d; bManualReset
0x1800221a5  xor     ecx, ecx; lpEventAttributes
0x1800221a7  call    cs:__imp_CreateEventW
0x1800221ad  test    rax, rax
0x1800221b0  jz      short loc_180022211
0x1800221b2  mov     [rdi+0F8h], rax
0x1800221b9  mov     rcx, rdi; this
0x1800221bc  call    ?RegisterAdapterCleanupWait@MessageSession@Messaging@CoreUI@Microsoft@@AEAAXXZ; Microsoft::CoreUI::Messaging::MessageSession::RegisterAdapterCleanupWait(void)
0x1800221c1  cmp     byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits, r15b
0x1800221c8  jl      short loc_1800221F7
0x1800221ca  mov     rcx, [rbp+var_8]
0x1800221ce  xor     rcx, rsp; StackCookie
0x1800221d1  call    __security_check_cookie
0x1800221d6  lea     r11, [rsp+60h+var_s0]
0x1800221db  mov     rbx, [r11+38h]
0x1800221df  mov     rsi, [r11+48h]
0x1800221e3  mov     rsp, r11
0x1800221e6  pop     r15
0x1800221e8  pop     r14
0x1800221ea  pop     r12
0x1800221ec  pop     rdi
0x1800221ed  pop     rbp
0x1800221ee  retn
0x1800221ef  mov     rbx, r15
0x1800221f2  jmp     loc_180022123
0x1800221f7  lea     rax, [rbp+var_18]
0x1800221fb  mov     [rsp+60h+var_40], rax
0x180022200  mov     r9d, r12d
0x180022203  lea     rdx, Messaging_ConstructMessageSession_Stop
0x18002220a  call    McGenEventWrite_EventWriteTransfer
0x18002220f  jmp     short loc_1800221CA
0x180022211  call    cs:__imp_GetLastError
0x180022217  test    eax, eax
0x180022219  jg      short loc_180022245
0x18002221b  xor     r8d, r8d; int
0x18002221e  xor     edx, edx; void *
0x180022220  mov     ecx, eax; int
0x180022222  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x180022228  lea     rax, [rbp+var_18]
0x18002222c  mov     [rsp+60h+var_40], rax
0x180022231  mov     r9d, r12d
0x180022234  lea     rdx, Messaging_ConstructMessageSession_Start
0x18002223b  call    McGenEventWrite_EventWriteTransfer
0x180022240  jmp     loc_180021F8C
0x180022245  movzx   eax, ax
0x180022248  or      eax, 80070000h
0x18002224d  jmp     short loc_18002221B
```
