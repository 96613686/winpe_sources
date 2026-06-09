# Microsoft::CoreUI::Dispatch::UserAdapter::DrainCoreMessagingQueue(Microsoft::CoreUI::Dispatch::UserAdapter$UserPriority,void * *)

- ea: `0x180008354`
- end: `0x180008705`
- name: `?DrainCoreMessagingQueue@UserAdapter@Dispatch@CoreUI@Microsoft@@AEAAXW4UserAdapter$UserPriority@234@PEAPEAX@Z`
- size: `945`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180008ae8`
- `0x1800158ac`

## callees

- `0x1800067f0`
- `0x1800080a8`
- `0x180008354`
- `0x180009750`
- `0x18000ec10`
- `0x180012900`
- `0x180019c44`
- `0x18003950c`
- `0x180048a20`
- `0x18004a850`
- `0x18005cf2c`
- `0x18005cff8`
- `0x18005d200`
- `0x18008ae1c`
- `0x18008b758`
- `0x18008c9f4`
- `0x18008cc1c`
- `0x18008f8ac`
- `0x1800c7ff0`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180008511`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180008511`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086af`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180008483`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180008483`
- `ext-ms-win-rtcore-ntuser-integration-l1-1-0!__imp_GetQueueStatusReadonly` at `0x1800085f8`
- `ext-ms-win-rtcore-ntuser-integration-l1-1-0!__imp_GetQueueStatusReadonly` at `0x1800085f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::CoreUI::Dispatch::UserAdapter::DrainCoreMessagingQueue(__int64 a1, __int64 a2, void **a3)
{
  int v4; // r12d
  __int64 v6; // rcx
  __int64 result; // rax
  __int64 v8; // rdi
  char v9; // si
  const char16_t *v10; // rcx
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // rax
  int i; // r8d
  __int64 v15; // rax
  __int64 (__fastcall ***v16)(_QWORD, __int64, GUID *, __int64); // rcx
  void *Native; // rax
  const char16_t *v18; // rcx
  _QWORD *Value; // rsi
  void *v20; // r15
  __int64 v21; // rax
  Cn::Engine::Lock *v22; // rcx
  __int64 *v23; // rax
  __int64 v24; // rsi
  unsigned int *v25; // r14
  __int64 v26; // rax
  System::Object *v27; // rdi
  unsigned int QueueStatusReadonly; // eax
  __int64 v29; // r8
  __int64 v30; // r8
  const char16_t *v31; // rcx
  signed int LastError; // eax
  _BYTE v33[16]; // [rsp+30h] [rbp-58h] BYREF
  char v34; // [rsp+40h] [rbp-48h]
  __int64 v35; // [rsp+48h] [rbp-40h]
  _DWORD *v36; // [rsp+50h] [rbp-38h]
  int v37; // [rsp+90h] [rbp+8h] BYREF
  void *v38; // [rsp+A0h] [rbp+18h] BYREF
  char v39; // [rsp+A8h] [rbp+20h] BYREF

  v4 = a2;
  if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 0x10) != 0 )
    McTemplateU0q_EventWriteTransfer(a1, &Adapter_OnUserDispatch_Start, (unsigned int)a2);
  if ( a3 )
    *a3 = 0;
  v6 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL);
  result = *(_QWORD *)(v6 + 48);
  v8 = *(_QWORD *)(result + 48);
  if ( (*(_BYTE *)(v8 + 232) & 1) != 0 )
  {
    if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 0x10) == 0 )
      return result;
    v30 = 1;
    return McTemplateU0t_EventWriteTransfer(v6, a2, v30);
  }
  if ( a3 )
  {
    if ( v8 )
      ++*(_DWORD *)(v8 + 16);
    v9 = 0;
    if ( v8 )
    {
      v10 = *(const char16_t **)(v8 + 8);
      if ( v10 == (const char16_t *)&CFlat::ComImportAdapter::TypeId$ )
      {
        Native = CFlat::ComImportAdapter::GetNativeInterface$(
                   (CFlat::ComImportAdapter *)v8,
                   (const struct CFlat::ComInterfaceTypeId *)&Microsoft::CoreUI::IExportMessageSession::TypeId$);
        if ( !Native )
          CFlat::Abandonment::Fail(v31);
      }
      else
      {
        v11 = 0;
        v12 = *v10;
        while ( 1 )
        {
          if ( v11 >= v12 )
            goto LABEL_51;
          v13 = *v10;
          if ( &CFlat::IImplementsComInterface::TypeId$ == *(_UNKNOWN **)&v10[8 * (v11 - v13)] )
            break;
          ++v11;
        }
        if ( !*(_QWORD *)&v10[8 * (v11 - v13) + 4] )
LABEL_51:
          CFlat::Abandonment::Fail(v10);
        for ( i = 0; i < v12; ++i )
        {
          v15 = *v10;
          if ( &CFlat::IImplementsComInterface::TypeId$ == *(_UNKNOWN **)&v10[8 * (i - v15)] )
          {
            v16 = *(__int64 (__fastcall ****)(_QWORD, __int64, GUID *, __int64))&v10[8 * (i - v15) + 4];
            goto LABEL_19;
          }
        }
        v16 = 0;
LABEL_19:
        Native = (void *)(**v16)(v16, v8, &GUID_4b2edab9_129b_4733_be15_356853d55ace, v8);
        if ( !Native )
          CFlat::Abandonment::Fail(v18);
        v9 = 1;
      }
    }
    else
    {
      Native = 0;
    }
    v38 = Native;
    if ( Native )
    {
      if ( !v9 )
      {
        Value = TlsGetValue(Cn::Context::s_tlsStorage);
        v20 = CFlat::EntryExit::ValidateCall(Value, v38, 1);
        CFlat::EntryExit::OnBeginCallToNative(Value);
        v21 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v39, &v38);
        CFlat::SehSafe::Execute__lambda_707e52aa1c4238b763f1e5fddd3a6954___(Value, v21);
        v22 = (Cn::Engine::Lock *)Value[11];
        if ( v22 )
        {
          Cn::Engine::Lock::Enter(v22);
          Cn::Context::SetCurrentContext((struct Cn::Context *)Value);
        }
        Value[2] = v20;
      }
    }
    else
    {
      CFlat::Contracts::Contract::Requires(v9 != 1);
    }
    *a3 = v38;
    if ( v8 )
      System::Object::ReleaseNotFrozen$((System::Object *)v8);
  }
  if ( !ResetEvent(*(HANDLE *)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL) + 144LL)) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    CFlat::Abandonment::FailWithHR(LastError, 0, 0);
  }
  v37 = *(_DWORD *)(a1 + 48);
  *(_DWORD *)(a1 + 48) = v4;
  v23 = (__int64 *)std::initializer_list<CFlat::SmartPtr<System::Object>>::initializer_list<CFlat::SmartPtr<System::Object>>(
                     v33,
                     a1,
                     &v37);
  v34 = 0;
  v24 = *v23;
  v35 = *v23;
  v25 = (unsigned int *)v23[1];
  v36 = v25;
  *(_BYTE *)(a1 + 77) = 0;
  try
  {
    do
    {
      v26 = *(_QWORD *)(a1 + 32);
      v27 = *(System::Object **)(v26 + 32);
      if ( *((_DWORD *)v27 + 45) )
        break;
      v38 = *(void **)(v26 + 32);
      if ( v27 )
        ++*((_DWORD *)v27 + 4);
      Microsoft::CoreUI::Dispatch::EventLoop::Callback_RunCoreLoop(v27, 3);
      if ( v27 )
        System::Object::ReleaseNotFrozen$(v27);
      v6 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL);
    }
    while ( *(_BYTE *)(v6 + 184) );
    if ( *(_DWORD *)(a1 + 48) == 1 )
    {
      v29 = *(_QWORD *)(a1 + 40);
      if ( (*(_BYTE *)(v29 + 24) & 8) != 0 )
        Microsoft::CoreUI::Dispatch::UserAdapter::ScheduleDispatch(a1, 1, v29, 0, 0);
    }
    if ( ((*(_DWORD *)(a1 + 48) - 3) & 0xFFFFFFFD) == 0 )
    {
      QueueStatusReadonly = GetQueueStatusReadonly(8);
      v6 = HIWORD(QueueStatusReadonly);
      LOBYTE(v6) = (QueueStatusReadonly & 0x80000) != 0;
      if ( ((unsigned __int8)v6 & ((QueueStatusReadonly & 8) == 0)) != 0 )
      {
        _interlockedbittestandreset((volatile signed __int32 *)(*(_QWORD *)(a1 + 40) + 24LL), 4u);
        Microsoft::CoreUI::Dispatch::UserAdapter::EnsureUserDispatchScheduled(a1, 10);
      }
    }
  }
  catch ( ... )
  {
    v34 = 1;
    *(_DWORD *)(v35 + 48) = *v36;
    throw;
  }
  if ( *(_BYTE *)(a1 + 24) )
  {
    *(_BYTE *)(a1 + 24) = 0;
    Microsoft::CoreUI::Dispatch::UserAdapter::EnsureUserDispatchScheduled((Microsoft::CoreUI::Dispatch::UserAdapter *)a1);
  }
  result = *v25;
  *(_DWORD *)(v24 + 48) = result;
  if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 0x10) != 0 )
  {
    v30 = 0;
    return McTemplateU0t_EventWriteTransfer(v6, a2, v30);
  }
  return result;
}

```

## disassembly

```asm
0x180008354  mov     [rsp+arg_8], rbx
0x180008359  push    rsi
0x18000835a  push    rdi
0x18000835b  push    r12
0x18000835d  push    r14
0x18000835f  push    r15
0x180008361  sub     rsp, 60h
0x180008365  mov     r14, r8
0x180008368  mov     r12d, edx
0x18000836b  mov     rbx, rcx
0x18000836e  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits, 10h
0x180008375  jnz     loc_1800086C6
0x18000837b  test    r14, r14
0x18000837e  jz      short loc_180008387
0x180008380  mov     qword ptr [r14], 0
0x180008387  mov     rax, [rbx+20h]
0x18000838b  mov     rcx, [rax+20h]
0x18000838f  mov     rax, [rcx+30h]
0x180008393  mov     rdi, [rax+30h]
0x180008397  mov     r15d, 1
0x18000839d  test    [rdi+0E8h], r15b
0x1800083a4  jnz     loc_180008667
0x1800083aa  test    r14, r14
0x1800083ad  jz      loc_180008502
0x1800083b3  test    rdi, rdi
0x1800083b6  jz      short loc_1800083BC
0x1800083b8  add     [rdi+10h], r15d
0x1800083bc  xor     sil, sil
0x1800083bf  test    rdi, rdi
0x1800083c2  jz      loc_180008465
0x1800083c8  mov     rcx, [rdi+8]; char16_t *
0x1800083cc  lea     rax, ?TypeId$@ComImportAdapter@CFlat@@2U?$ObjectTypeIdField@VComImportAdapter@CFlat@@$0A@$0A@@2@B; CFlat::ObjectTypeIdField<CFlat::ComImportAdapter,0,0> const CFlat::ComImportAdapter::TypeId$
0x1800083d3  cmp     rcx, rax
0x1800083d6  jz      loc_180008691
0x1800083dc  xor     r8d, r8d
0x1800083df  movzx   r9d, word ptr [rcx]
0x1800083e3  lea     r10, ?TypeId$@IImplementsComInterface@CFlat@@2U?$InterfaceTypeIdField@VIImplementsComInterface@CFlat@@$0A@$0A@@2@B; CFlat::InterfaceTypeIdField<CFlat::IImplementsComInterface,0,0> const CFlat::IImplementsComInterface::TypeId$
0x1800083ea  cmp     r8d, r9d
0x1800083ed  jge     loc_180008661
0x1800083f3  movzx   eax, word ptr [rcx]
0x1800083f6  movsxd  rdx, r8d
0x1800083f9  sub     rdx, rax
0x1800083fc  add     rdx, rdx
0x1800083ff  cmp     r10, [rcx+rdx*8]
0x180008403  jnz     short loc_18000845B
0x180008405  cmp     qword ptr [rcx+rdx*8+8], 0
0x18000840b  jz      loc_180008661
0x180008411  xor     r8d, r8d
0x180008414  cmp     r8d, r9d
0x180008417  jge     loc_18000865A
0x18000841d  movzx   eax, word ptr [rcx]
0x180008420  movsxd  rdx, r8d
0x180008423  sub     rdx, rax
0x180008426  add     rdx, rdx
0x180008429  cmp     r10, [rcx+rdx*8]
0x18000842d  jnz     short loc_180008460
0x18000842f  mov     rcx, [rcx+rdx*8+8]
0x180008434  mov     rax, [rcx]
0x180008437  mov     r9, rdi
0x18000843a  lea     r8, _GUID_4b2edab9_129b_4733_be15_356853d55ace
0x180008441  mov     rdx, rdi
0x180008444  mov     rax, [rax]
0x180008447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000844c  test    rax, rax
0x18000844f  jnz     loc_1800086DA
0x180008455  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18000845b  add     r8d, r15d
0x18000845e  jmp     short loc_1800083EA
0x180008460  add     r8d, r15d
0x180008463  jmp     short loc_180008414
0x180008465  xor     eax, eax
0x180008467  mov     [rsp+88h+arg_10], rax
0x18000846f  test    rax, rax
0x180008472  jz      loc_180008681
0x180008478  test    sil, sil
0x18000847b  jnz     short loc_1800084EA
0x18000847d  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180008483  call    cs:__imp_TlsGetValue
0x180008489  mov     rsi, rax
0x18000848c  mov     r8d, r15d; int
0x18000848f  mov     rdx, [rsp+88h+arg_10]; void *
0x180008497  mov     rcx, rax; void *
0x18000849a  call    ?ValidateCall@EntryExit@CFlat@@SAPEAXPEAX0H@Z; CFlat::EntryExit::ValidateCall(void *,void *,int)
0x18000849f  mov     r15, rax
0x1800084a2  mov     rcx, rsi; void *
0x1800084a5  call    ?OnBeginCallToNative@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnBeginCallToNative(void *)
0x1800084aa  lea     rdx, [rsp+88h+arg_10]
0x1800084b2  lea     rcx, [rsp+88h+arg_18]
0x1800084ba  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800084bf  mov     rdx, rax
0x1800084c2  mov     rcx, rsi
0x1800084c5  call    CFlat__SehSafe__Execute__lambda_707e52aa1c4238b763f1e5fddd3a6954___
0x1800084ca  mov     rcx, [rsi+58h]; this
0x1800084ce  test    rcx, rcx
0x1800084d1  jz      short loc_1800084E0
0x1800084d3  call    ?Enter@Lock@Engine@Cn@@QEAAXXZ; Cn::Engine::Lock::Enter(void)
0x1800084d8  mov     rcx, rsi; lpTlsValue
0x1800084db  call    ?SetCurrentContext@Context@Cn@@CAXPEAV12@@Z; Cn::Context::SetCurrentContext(Cn::Context *)
0x1800084e0  mov     [rsi+10h], r15
0x1800084e4  mov     r15d, 1
0x1800084ea  mov     rax, [rsp+88h+arg_10]
0x1800084f2  mov     [r14], rax
0x1800084f5  test    rdi, rdi
0x1800084f8  jz      short loc_180008502
0x1800084fa  mov     rcx, rdi; this
0x1800084fd  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180008502  mov     rax, [rbx+20h]
0x180008506  mov     rcx, [rax+20h]
0x18000850a  mov     rcx, [rcx+90h]; hEvent
0x180008511  call    cs:__imp_ResetEvent
0x180008517  test    eax, eax
0x180008519  jz      loc_1800086AF
0x18000851f  mov     eax, [rbx+30h]
0x180008522  mov     [rsp+88h+arg_0], eax
0x180008529  mov     [rbx+30h], r12d
0x18000852d  lea     r8, [rsp+88h+arg_0]
0x180008535  mov     rdx, rbx
0x180008538  lea     rcx, [rsp+88h+var_58]
0x18000853d  call    ??0?$initializer_list@V?$SmartPtr@VObject@System@@@CFlat@@@std@@QEAA@PEBV?$SmartPtr@VObject@System@@@CFlat@@0@Z; std::initializer_list<CFlat::SmartPtr<System::Object>>::initializer_list<CFlat::SmartPtr<System::Object>>(CFlat::SmartPtr<System::Object> const *,CFlat::SmartPtr<System::Object> const *)
0x180008542  mov     [rsp+88h+var_48], 0
0x180008547  mov     rsi, [rax]
0x18000854a  mov     [rsp+88h+var_40], rsi
0x18000854f  mov     r14, [rax+8]
0x180008553  mov     [rsp+88h+var_38], r14
0x180008558  mov     byte ptr [rbx+4Dh], 0
0x18000855c  mov     r12d, 3
0x180008562  mov     rax, [rbx+20h]
0x180008566  mov     rdi, [rax+20h]
0x18000856a  cmp     dword ptr [rdi+0B4h], 0
0x180008571  ja      short loc_1800085AE
0x180008573  mov     [rsp+88h+arg_10], rdi
0x18000857b  test    rdi, rdi
0x18000857e  jz      short loc_180008584
0x180008580  add     [rdi+10h], r15d
0x180008584  mov     edx, r12d
0x180008587  mov     rcx, rdi
0x18000858a  call    ?Callback_RunCoreLoop@EventLoop@Dispatch@CoreUI@Microsoft@@QEAA?AW4Dispatcher$LoopExitState@234@W4RunMode@234@@Z; Microsoft::CoreUI::Dispatch::EventLoop::Callback_RunCoreLoop(Microsoft::CoreUI::Dispatch::RunMode)
0x18000858f  nop
0x180008590  test    rdi, rdi
0x180008593  jz      short loc_18000859D
0x180008595  mov     rcx, rdi; this
0x180008598  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18000859d  mov     rax, [rbx+20h]
0x1800085a1  mov     rcx, [rax+20h]
0x1800085a5  cmp     byte ptr [rcx+0B8h], 0
0x1800085ac  jnz     short loc_180008562
0x1800085ae  cmp     [rbx+30h], r15d
0x1800085b2  jz      short loc_180008630
0x1800085b4  mov     eax, [rbx+30h]
0x1800085b7  sub     eax, r12d
0x1800085ba  test    eax, 0FFFFFFFDh
0x1800085bf  jz      short loc_1800085F3
0x1800085c1  cmp     byte ptr [rbx+18h], 0
0x1800085c5  jnz     loc_1800086EC
0x1800085cb  mov     eax, [r14]
0x1800085ce  mov     [rsi+30h], eax
0x1800085d1  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits, 10h
0x1800085d8  jnz     loc_1800086FD
0x1800085de  mov     rbx, [rsp+88h+arg_8]
0x1800085e6  add     rsp, 60h
0x1800085ea  pop     r15
0x1800085ec  pop     r14
0x1800085ee  pop     r12
0x1800085f0  pop     rdi
0x1800085f1  pop     rsi
0x1800085f2  retn
0x1800085f3  mov     ecx, 8
0x1800085f8  call    cs:__imp_GetQueueStatusReadonly
0x1800085fe  mov     ecx, eax
0x180008600  shr     ecx, 10h
0x180008603  bt      cx, r12w
0x180008608  setb    cl
0x18000860b  bt      ax, r12w
0x180008610  setnb   al
0x180008613  test    al, cl
0x180008615  jz      short loc_1800085C1
0x180008617  mov     rax, [rbx+28h]
0x18000861b  lock btr dword ptr [rax+18h], 4
0x180008621  mov     edx, 0Ah
0x180008626  mov     rcx, rbx
0x180008629  call    ?EnsureUserDispatchScheduled@UserAdapter@Dispatch@CoreUI@Microsoft@@QEAAXW4InternalPriority@234@@Z; Microsoft::CoreUI::Dispatch::UserAdapter::EnsureUserDispatchScheduled(Microsoft::CoreUI::Dispatch::InternalPriority)
0x18000862e  jmp     short loc_1800085C1
0x180008630  mov     r8, [rbx+28h]
0x180008634  test    byte ptr [r8+18h], 8
0x180008639  jz      loc_1800085B4
0x18000863f  mov     [rsp+88h+var_68], 0
0x180008647  xor     r9d, r9d
0x18000864a  mov     edx, r15d
0x18000864d  mov     rcx, rbx
0x180008650  call    ?ScheduleDispatch@UserAdapter@Dispatch@CoreUI@Microsoft@@QEAAXW4InternalPriority@234@PEAX_NI@Z; Microsoft::CoreUI::Dispatch::UserAdapter::ScheduleDispatch(Microsoft::CoreUI::Dispatch::InternalPriority,void *,bool,uint)
0x180008655  jmp     loc_1800085B4
0x18000865a  xor     ecx, ecx
0x18000865c  jmp     loc_180008434
0x180008661  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x180008667  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits, 10h
0x18000866e  jz      loc_1800085DE
0x180008674  mov     r8d, r15d
0x180008677  call    McTemplateU0t_EventWriteTransfer
0x18000867c  jmp     loc_1800085DE
0x180008681  xor     sil, r15b
0x180008684  mov     cl, sil; bool
0x180008687  call    ?Requires@Contract@Contracts@CFlat@@SAX_N@Z; CFlat::Contracts::Contract::Requires(bool)
0x18000868c  jmp     loc_1800084EA
0x180008691  lea     rdx, ?TypeId$@IExportMessageSession@CoreUI@Microsoft@@2U?$ComInterfaceTypeIdField@VIExportMessageSession@CoreUI@Microsoft@@UIMessageSession@@$0A@@CFlat@@B; struct CFlat::ComInterfaceTypeId *
0x180008698  mov     rcx, rdi; this
0x18000869b  call    ?GetNativeInterface$@ComImportAdapter@CFlat@@QEAAPEAXPEBUComInterfaceTypeId@2@@Z; CFlat::ComImportAdapter::GetNativeInterface$(CFlat::ComInterfaceTypeId const *)
0x1800086a0  test    rax, rax
0x1800086a3  jnz     loc_180008467
0x1800086a9  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x1800086af  call    cs:__imp_GetLastError
0x1800086b5  test    eax, eax
0x1800086b7  jg      short loc_1800086E2
0x1800086b9  xor     r8d, r8d; int
0x1800086bc  xor     edx, edx; void *
0x1800086be  mov     ecx, eax; int
0x1800086c0  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x1800086c6  mov     r8d, r12d
0x1800086c9  lea     rdx, Adapter_OnUserDispatch_Start
0x1800086d0  call    McTemplateU0q_EventWriteTransfer
0x1800086d5  jmp     loc_18000837B
0x1800086da  mov     sil, r15b
0x1800086dd  jmp     loc_180008467
0x1800086e2  movzx   eax, ax
0x1800086e5  or      eax, 80070000h
0x1800086ea  jmp     short loc_1800086B9
0x1800086ec  mov     byte ptr [rbx+18h], 0
0x1800086f0  mov     rcx, rbx; this
0x1800086f3  call    ?EnsureUserDispatchScheduled@UserAdapter@Dispatch@CoreUI@Microsoft@@QEAAXXZ; Microsoft::CoreUI::Dispatch::UserAdapter::EnsureUserDispatchScheduled(void)
0x1800086f8  jmp     loc_1800085CB
0x1800086fd  xor     r8d, r8d
0x180008700  jmp     loc_180008677
```
