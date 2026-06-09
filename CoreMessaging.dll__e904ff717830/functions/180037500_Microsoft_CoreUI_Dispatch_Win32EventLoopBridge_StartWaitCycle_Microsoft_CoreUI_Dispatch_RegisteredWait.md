# Microsoft::CoreUI::Dispatch::Win32EventLoopBridge::StartWaitCycle(Microsoft::CoreUI::Dispatch::RegisteredWait *)

- ea: `0x180037500`
- end: `0x180037736`
- name: `?StartWaitCycle@Win32EventLoopBridge@Dispatch@CoreUI@Microsoft@@UEAA_NPEAVRegisteredWait@234@@Z`
- size: `566`
- prototype: `bool __fastcall(Microsoft::CoreUI::Dispatch::Win32EventLoopBridge *__hidden this, struct Microsoft::CoreUI::Dispatch::RegisteredWait *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000aa10`

## callees

- `0x1800036a0`
- `0x180007d80`
- `0x18000a3d4`
- `0x18000ec10`
- `0x18002d988`
- `0x180037500`
- `0x18003773c`
- `0x18004f1ac`
- `0x18005f230`
- `0x18008ae1c`
- `0x1800b96c0`
- `0x1800b98a4`
- `0x1800b9940`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037588`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037588`
- `ntdll!NtAssociateWaitCompletionPacket` at `0x1800375c8`
- `ntdll!NtAssociateWaitCompletionPacket` at `0x1800375c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall Microsoft::CoreUI::Dispatch::Win32EventLoopBridge::StartWaitCycle(
        Microsoft::CoreUI::Dispatch::Win32EventLoopBridge *this,
        __int64 **a2)
{
  __int64 v3; // r12
  __int64 v4; // r15
  __int64 v5; // rbx
  _QWORD *Value; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // r14
  __int64 *v12; // rdi
  __int64 *v13; // rsi
  int v14; // eax
  int v15; // edx
  int v16; // ecx
  char v17; // r15
  char v18; // bl
  __int64 v20; // rcx
  __int64 *v21; // rdi
  int v22; // edx
  int v23; // ecx
  _QWORD *v24; // rax
  _BYTE v25[128]; // [rsp+40h] [rbp-29h] BYREF
  __int64 v26; // [rsp+D0h] [rbp+67h] BYREF
  System::Object *v27; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 v28; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v29; // [rsp+E8h] [rbp+7Fh]

  v3 = *((_QWORD *)this + 5);
  v29 = v3;
  if ( v3 )
    ++*(_DWORD *)(v3 + 16);
  if ( a2 && a2[1] != &qword_1800D2A40 )
    CFlat::Abandonment::Fail((const char16_t *)this);
  v4 = *(_QWORD *)(v3 + 88);
  v26 = v4;
  v28 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 80) + 32LL) + 168LL);
  CFlat::Cast::Checked<CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::Win32EventLoopBridge>,Microsoft::CoreUI::Dispatch::EventLoopBridge *>(
    &v27,
    &v28);
  if ( !*((_QWORD *)v27 + 7) || (v20 = *((_QWORD *)v27 + 4), *(_BYTE *)(v20 + 176)) || *(_DWORD *)(v20 + 68) == 4 )
  {
    v5 = (__int64)a2[9];
  }
  else
  {
    v5 = (__int64)a2[10];
    if ( !v5 )
    {
      v21 = a2[9];
      v5 = Cn::Engine::Heap::ProcessAllocate(v20, 16);
      *(_QWORD *)(v5 + 8) = v21;
      a2[10] = (__int64 *)v5;
    }
  }
  Value = TlsGetValue(Cn::Context::s_tlsStorage);
  if ( !v5 )
    CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,unsigned long,void *)>>::GetHashCode(
      v8,
      v7,
      v9,
      v10);
  v11 = *(unsigned int *)(Value[6] + 72LL);
  v12 = a2[6];
  v13 = a2[8];
  v14 = NtAssociateWaitCompletionPacket(v13, v4, v12, v5, v11, 0, 0, 0);
  v17 = v14;
  if ( v14 < 0 )
  {
    Microsoft::CoreUI::Support::IoCompletionPort::ReportAssociationError(&v26, v13, v12, v5, v11, v14);
    if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 0x400) != 0 )
      McTemplateU0pppq_EventWriteTransfer(v23, v22, (_DWORD)v13, v26, (char)v12, v17);
    v18 = 0;
  }
  else
  {
    if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 0x200) != 0 )
      McTemplateU0pppp_EventWriteTransfer(v16, v15, (_DWORD)v13, (_DWORD)v12, v5, v11);
    v18 = 1;
  }
  *((_BYTE *)a2 + 56) = v18;
  if ( !v18 )
  {
    Microsoft::CoreUI::Dispatch::WakeRecord::WakeRecord(v25, a2, 0xFFFFFFFFLL, a2[6], 0, 0);
    v24 = (_QWORD *)CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::EventLoopBridge>::Copy(v3 + 80, &v26);
    Microsoft::CoreUI::Dispatch::RegisteredWait::QueueWakeCompletion(a2, *v24, v25);
    CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::EventLoop>::~SmartPtr<Microsoft::CoreUI::Dispatch::EventLoop>(&v26);
    v18 = 0;
    CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::EventLoop>::~SmartPtr<Microsoft::CoreUI::Dispatch::EventLoop>(v25);
  }
  if ( v27 )
    System::Object::ReleaseNotFrozen$(v27);
  if ( v3 )
    System::Object::ReleaseNotFrozen$((System::Object *)v3);
  return v18;
}

```

## disassembly

```asm
0x180037500  push    rbp
0x180037502  push    rbx
0x180037503  push    rsi
0x180037504  push    rdi
0x180037505  push    r12
0x180037507  push    r13
0x180037509  push    r14
0x18003750b  push    r15
0x18003750d  lea     rbp, [rsp-1Fh]
0x180037512  sub     rsp, 88h
0x180037519  mov     r13, rdx
0x18003751c  mov     r12, [rcx+28h]
0x180037520  mov     [rbp+57h+arg_18], r12
0x180037524  test    r12, r12
0x180037527  jz      short loc_18003752E
0x180037529  inc     dword ptr [r12+10h]
0x18003752e  test    r13, r13
0x180037531  jz      short loc_180037544
0x180037533  lea     rax, qword_1800D2A40
0x18003753a  cmp     [rdx+8], rax
0x18003753e  jnz     loc_18003762C
0x180037544  mov     r15, [r12+58h]
0x180037549  mov     [rbp+57h+arg_0], r15
0x18003754d  mov     rax, [r12+50h]
0x180037552  mov     rcx, [rax+20h]
0x180037556  mov     rax, [rcx+0A8h]
0x18003755d  mov     [rbp+57h+arg_10], rax
0x180037561  lea     rdx, [rbp+57h+arg_10]
0x180037565  lea     rcx, [rbp+57h+arg_8]
0x180037569  call    ??$Checked@V?$SmartPtr@VWin32EventLoopBridge@Dispatch@CoreUI@Microsoft@@@CFlat@@PEAVEventLoopBridge@Dispatch@CoreUI@Microsoft@@@Cast@CFlat@@SA?A_P$$QEAPEAVEventLoopBridge@Dispatch@CoreUI@Microsoft@@@Z
0x18003756e  nop
0x18003756f  mov     rax, [rbp+57h+arg_8]
0x180037573  cmp     qword ptr [rax+38h], 0
0x180037578  jnz     loc_180037632
0x18003757e  mov     rbx, [r13+48h]
0x180037582  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180037588  call    cs:__imp_TlsGetValue
0x18003758e  test    rbx, rbx
0x180037591  jz      loc_180037676
0x180037597  mov     rax, [rax+30h]
0x18003759b  mov     r14d, [rax+48h]
0x18003759f  mov     rdi, [r13+30h]
0x1800375a3  mov     rsi, [r13+40h]
0x1800375a7  xor     eax, eax
0x1800375a9  mov     [rsp+0C0h+var_88], rax
0x1800375ae  mov     [rsp+0C0h+var_90], rax
0x1800375b3  mov     dword ptr [rsp+0C0h+var_98], eax
0x1800375b7  mov     [rsp+0C0h+var_A0], r14
0x1800375bc  mov     r9, rbx
0x1800375bf  mov     r8, rdi
0x1800375c2  mov     rdx, r15
0x1800375c5  mov     rcx, rsi
0x1800375c8  call    cs:__imp_NtAssociateWaitCompletionPacket
0x1800375ce  mov     r15d, eax
0x1800375d1  test    eax, eax
0x1800375d3  js      loc_180037696
0x1800375d9  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits+1, 2
0x1800375e0  jnz     loc_18003767C
0x1800375e6  mov     ebx, 1
0x1800375eb  mov     [r13+38h], bl
0x1800375ef  test    bl, bl
0x1800375f1  jz      loc_1800376D8
0x1800375f7  mov     rax, [rbp+57h+arg_8]
0x1800375fb  test    rax, rax
0x1800375fe  jz      short loc_180037609
0x180037600  mov     rcx, rax; this
0x180037603  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180037608  nop
0x180037609  test    r12, r12
0x18003760c  jz      short loc_180037616
0x18003760e  mov     rcx, r12; this
0x180037611  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180037616  mov     al, bl
0x180037618  add     rsp, 88h
0x18003761f  pop     r15
0x180037621  pop     r14
0x180037623  pop     r13
0x180037625  pop     r12
0x180037627  pop     rdi
0x180037628  pop     rsi
0x180037629  pop     rbx
0x18003762a  pop     rbp
0x18003762b  retn
0x18003762c  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x180037632  mov     rcx, [rax+20h]
0x180037636  cmp     byte ptr [rcx+0B0h], 0
0x18003763d  jnz     loc_18003757E
0x180037643  cmp     dword ptr [rcx+44h], 4
0x180037647  jz      loc_18003757E
0x18003764d  mov     rbx, [r13+50h]
0x180037651  test    rbx, rbx
0x180037654  jnz     loc_180037582
0x18003765a  mov     rdi, [r13+48h]
0x18003765e  lea     edx, [rbx+10h]
0x180037661  call    ?ProcessAllocate@Heap@Engine@Cn@@SAPEAXUAllocType@23@_K@Z; Cn::Engine::Heap::ProcessAllocate(Cn::Engine::AllocType,unsigned __int64)
0x180037666  mov     rbx, rax
0x180037669  mov     [rax+8], rdi
0x18003766d  mov     [r13+50h], rax
0x180037671  jmp     loc_180037582
0x180037676  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
0x18003767c  mov     [rsp+0C0h+var_98], r14
0x180037681  mov     [rsp+0C0h+var_A0], rbx
0x180037686  mov     r9, rdi
0x180037689  mov     r8, rsi
0x18003768c  call    McTemplateU0pppp_EventWriteTransfer
0x180037691  jmp     loc_1800375E6
0x180037696  mov     dword ptr [rsp+0C0h+var_98], r15d
0x18003769b  mov     [rsp+0C0h+var_A0], r14
0x1800376a0  mov     r9, rbx
0x1800376a3  mov     r8, rdi
0x1800376a6  mov     rdx, rsi
0x1800376a9  lea     rcx, [rbp+57h+arg_0]
0x1800376ad  call    ?ReportAssociationError@IoCompletionPort@Support@CoreUI@Microsoft@@AEAAXUWaitCompletionPacket@234@UWin32Handle@234@UIntPtr@System@@2I@Z; Microsoft::CoreUI::Support::IoCompletionPort::ReportAssociationError(Microsoft::CoreUI::Support::WaitCompletionPacket,Microsoft::CoreUI::Support::Win32Handle,System::IntPtr,System::IntPtr,uint)
0x1800376b2  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits+1, 4
0x1800376b9  jz      short loc_1800376D1
0x1800376bb  mov     dword ptr [rsp+0C0h+var_98], r15d
0x1800376c0  mov     [rsp+0C0h+var_A0], rdi
0x1800376c5  mov     r9, [rbp+57h+arg_0]
0x1800376c9  mov     r8, rsi
0x1800376cc  call    McTemplateU0pppq_EventWriteTransfer
0x1800376d1  xor     bl, bl
0x1800376d3  jmp     loc_1800375EB
0x1800376d8  mov     dword ptr [rsp+0C0h+var_98], 0
0x1800376e0  mov     dword ptr [rsp+0C0h+var_A0], 0
0x1800376e8  mov     r9, [r13+30h]
0x1800376ec  or      r8d, 0FFFFFFFFh
0x1800376f0  mov     rdx, r13
0x1800376f3  lea     rcx, [rbp+57h+var_80]
0x1800376f7  call    ??0WakeRecord@Dispatch@CoreUI@Microsoft@@QEAA@PEAVRegisteredWait@123@W4WaitStatus@123@UWin32Handle@Support@23@II@Z; Microsoft::CoreUI::Dispatch::WakeRecord::WakeRecord(Microsoft::CoreUI::Dispatch::RegisteredWait *,Microsoft::CoreUI::Dispatch::WaitStatus,Microsoft::CoreUI::Support::Win32Handle,uint,uint)
0x1800376fc  nop
0x1800376fd  lea     rdx, [rbp+57h+arg_0]
0x180037701  lea     rcx, [r12+50h]
0x180037706  call    ?Copy@?$SmartPtr@VEventLoopBridge@Dispatch@CoreUI@Microsoft@@@CFlat@@QEBA?AV12@XZ; CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::EventLoopBridge>::Copy(void)
0x18003770b  nop
0x18003770c  lea     r8, [rbp+57h+var_80]
0x180037710  mov     rdx, [rax]
0x180037713  mov     rcx, r13
0x180037716  call    ?QueueWakeCompletion@RegisteredWait@Dispatch@CoreUI@Microsoft@@QEAAXPEAVWaitCollection@234@U?$Ref@UWakeRecord@Dispatch@CoreUI@Microsoft@@@CFlat@@@Z; Microsoft::CoreUI::Dispatch::RegisteredWait::QueueWakeCompletion(Microsoft::CoreUI::Dispatch::WaitCollection *,CFlat::Ref<Microsoft::CoreUI::Dispatch::WakeRecord>)
0x18003771b  nop
0x18003771c  lea     rcx, [rbp+57h+arg_0]
0x180037720  call    ??1?$SmartPtr@VEventLoop@Dispatch@CoreUI@Microsoft@@@CFlat@@QEAA@XZ; CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::EventLoop>::~SmartPtr<Microsoft::CoreUI::Dispatch::EventLoop>(void)
0x180037725  xor     bl, bl
0x180037727  lea     rcx, [rbp+57h+var_80]
0x18003772b  call    ??1?$SmartPtr@VEventLoop@Dispatch@CoreUI@Microsoft@@@CFlat@@QEAA@XZ; CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::EventLoop>::~SmartPtr<Microsoft::CoreUI::Dispatch::EventLoop>(void)
0x180037730  jmp     loc_1800375F7
```
