# Microsoft::CoreUI::Dispatch::WaitController::StartWaitCycle(Microsoft::CoreUI::Dispatch::IocpWait *,Microsoft::CoreUI::Support::IoCompletionPort)

- ea: `0x1800372fc`
- end: `0x1800374f0`
- name: `?StartWaitCycle@WaitController@Dispatch@CoreUI@Microsoft@@QEAA_NPEAVIocpWait@234@UIoCompletionPort@Support@34@@Z`
- size: `500`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005b688`

## callees

- `0x1800036a0`
- `0x180007d80`
- `0x18000a3d4`
- `0x18000ec10`
- `0x18002d988`
- `0x1800372fc`
- `0x18003773c`
- `0x18004f1ac`
- `0x18005f230`
- `0x1800b96c0`
- `0x1800b98a4`
- `0x1800b9940`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037361`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037361`
- `ntdll!NtAssociateWaitCompletionPacket` at `0x1800373a1`
- `ntdll!NtAssociateWaitCompletionPacket` at `0x1800373a1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall Microsoft::CoreUI::Dispatch::WaitController::StartWaitCycle(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rcx
  System::Object *v6; // r12
  __int64 v7; // rbx
  _QWORD *Value; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // r14
  __int64 v14; // rdi
  __int64 v15; // rsi
  int v16; // eax
  int v17; // edx
  int v18; // ecx
  char v19; // r15
  char v20; // bl
  __int64 v22; // rax
  __int64 v23; // rdi
  int v24; // edx
  int v25; // ecx
  _QWORD *v26; // rax
  _BYTE v27[128]; // [rsp+40h] [rbp-29h] BYREF
  __int64 v28; // [rsp+D0h] [rbp+67h] BYREF
  System::Object *v29; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 v30; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v31; // [rsp+E8h] [rbp+7Fh]

  v30 = a3;
  v31 = a1 + 80;
  v28 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 32LL) + 168LL);
  CFlat::Cast::Checked<CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::Win32EventLoopBridge>,Microsoft::CoreUI::Dispatch::EventLoopBridge *>(
    &v29,
    &v28);
  v6 = v29;
  if ( !*((_QWORD *)v29 + 7) || (v22 = *((_QWORD *)v29 + 4), *(_BYTE *)(v22 + 176)) || *(_DWORD *)(v22 + 68) == 4 )
  {
    v7 = *(_QWORD *)(a2 + 72);
  }
  else
  {
    v7 = *(_QWORD *)(a2 + 80);
    if ( !v7 )
    {
      v23 = *(_QWORD *)(a2 + 72);
      v7 = Cn::Engine::Heap::ProcessAllocate(v5, 16);
      *(_QWORD *)(v7 + 8) = v23;
      *(_QWORD *)(a2 + 80) = v7;
    }
  }
  Value = TlsGetValue(Cn::Context::s_tlsStorage);
  if ( !v7 )
    CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,unsigned long,void *)>>::GetHashCode(
      v10,
      v9,
      v11,
      v12);
  v13 = *(unsigned int *)(Value[6] + 72LL);
  v14 = *(_QWORD *)(a2 + 48);
  v15 = *(_QWORD *)(a2 + 64);
  v16 = NtAssociateWaitCompletionPacket(v15, a3, v14, v7, v13, 0, 0, 0);
  v19 = v16;
  if ( v16 < 0 )
  {
    Microsoft::CoreUI::Support::IoCompletionPort::ReportAssociationError(&v30, v15, v14, v7, v13, v16);
    if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 0x400) != 0 )
      McTemplateU0pppq_EventWriteTransfer(v25, v24, v15, v30, v14, v19);
    v20 = 0;
  }
  else
  {
    if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 0x200) != 0 )
      McTemplateU0pppp_EventWriteTransfer(v18, v17, v15, v14, v7, v13);
    v20 = 1;
  }
  *(_BYTE *)(a2 + 56) = v20;
  if ( !v20 )
  {
    Microsoft::CoreUI::Dispatch::WakeRecord::WakeRecord(v27, a2, 0xFFFFFFFFLL, *(_QWORD *)(a2 + 48), 0, 0);
    v26 = (_QWORD *)CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::EventLoopBridge>::Copy(v31, &v28);
    Microsoft::CoreUI::Dispatch::RegisteredWait::QueueWakeCompletion(a2, *v26, v27);
    CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::EventLoop>::~SmartPtr<Microsoft::CoreUI::Dispatch::EventLoop>(&v28);
    v20 = 0;
    CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::EventLoop>::~SmartPtr<Microsoft::CoreUI::Dispatch::EventLoop>(v27);
  }
  if ( v6 )
    System::Object::ReleaseNotFrozen$(v6);
  return v20;
}

```

## disassembly

```asm
0x1800372fc  mov     [rsp-8+arg_10], r8
0x180037301  push    rbp
0x180037302  push    rbx
0x180037303  push    rsi
0x180037304  push    rdi
0x180037305  push    r12
0x180037307  push    r13
0x180037309  push    r14
0x18003730b  push    r15
0x18003730d  lea     rbp, [rsp-1Fh]
0x180037312  sub     rsp, 88h
0x180037319  mov     r15, r8
0x18003731c  mov     r13, rdx
0x18003731f  lea     rax, [rcx+50h]
0x180037323  mov     [rbp+57h+arg_18], rax
0x180037327  mov     rax, [rax]
0x18003732a  mov     rcx, [rax+20h]
0x18003732e  mov     rax, [rcx+0A8h]
0x180037335  mov     [rbp+57h+arg_0], rax
0x180037339  lea     rdx, [rbp+57h+arg_0]
0x18003733d  lea     rcx, [rbp+57h+arg_8]
0x180037341  call    ??$Checked@V?$SmartPtr@VWin32EventLoopBridge@Dispatch@CoreUI@Microsoft@@@CFlat@@PEAVEventLoopBridge@Dispatch@CoreUI@Microsoft@@@Cast@CFlat@@SA?A_P$$QEAPEAVEventLoopBridge@Dispatch@CoreUI@Microsoft@@@Z
0x180037346  nop
0x180037347  mov     r12, [rbp+57h+arg_8]
0x18003734b  cmp     qword ptr [r12+38h], 0
0x180037351  jnz     loc_1800373EC
0x180037357  mov     rbx, [r13+48h]
0x18003735b  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180037361  call    cs:__imp_TlsGetValue
0x180037367  test    rbx, rbx
0x18003736a  jz      loc_180037431
0x180037370  mov     rax, [rax+30h]
0x180037374  mov     r14d, [rax+48h]
0x180037378  mov     rdi, [r13+30h]
0x18003737c  mov     rsi, [r13+40h]
0x180037380  xor     eax, eax
0x180037382  mov     [rsp+0C0h+var_88], rax
0x180037387  mov     [rsp+0C0h+var_90], rax
0x18003738c  mov     dword ptr [rsp+0C0h+var_98], eax
0x180037390  mov     [rsp+0C0h+var_A0], r14
0x180037395  mov     r9, rbx
0x180037398  mov     r8, rdi
0x18003739b  mov     rdx, r15
0x18003739e  mov     rcx, rsi
0x1800373a1  call    cs:__imp_NtAssociateWaitCompletionPacket
0x1800373a7  mov     r15d, eax
0x1800373aa  test    eax, eax
0x1800373ac  js      loc_180037451
0x1800373b2  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits+1, 2
0x1800373b9  jnz     short loc_180037437
0x1800373bb  mov     bl, 1
0x1800373bd  mov     [r13+38h], bl
0x1800373c1  test    bl, bl
0x1800373c3  jz      loc_180037493
0x1800373c9  test    r12, r12
0x1800373cc  jz      short loc_1800373D6
0x1800373ce  mov     rcx, r12; this
0x1800373d1  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x1800373d6  mov     al, bl
0x1800373d8  add     rsp, 88h
0x1800373df  pop     r15
0x1800373e1  pop     r14
0x1800373e3  pop     r13
0x1800373e5  pop     r12
0x1800373e7  pop     rdi
0x1800373e8  pop     rsi
0x1800373e9  pop     rbx
0x1800373ea  pop     rbp
0x1800373eb  retn
0x1800373ec  mov     rax, [r12+20h]
0x1800373f1  cmp     byte ptr [rax+0B0h], 0
0x1800373f8  jnz     loc_180037357
0x1800373fe  cmp     dword ptr [rax+44h], 4
0x180037402  jz      loc_180037357
0x180037408  mov     rbx, [r13+50h]
0x18003740c  test    rbx, rbx
0x18003740f  jnz     loc_18003735B
0x180037415  mov     rdi, [r13+48h]
0x180037419  lea     edx, [rbx+10h]
0x18003741c  call    ?ProcessAllocate@Heap@Engine@Cn@@SAPEAXUAllocType@23@_K@Z; Cn::Engine::Heap::ProcessAllocate(Cn::Engine::AllocType,unsigned __int64)
0x180037421  mov     rbx, rax
0x180037424  mov     [rax+8], rdi
0x180037428  mov     [r13+50h], rax
0x18003742c  jmp     loc_18003735B
0x180037431  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
0x180037437  mov     [rsp+0C0h+var_98], r14
0x18003743c  mov     [rsp+0C0h+var_A0], rbx
0x180037441  mov     r9, rdi
0x180037444  mov     r8, rsi
0x180037447  call    McTemplateU0pppp_EventWriteTransfer
0x18003744c  jmp     loc_1800373BB
0x180037451  mov     dword ptr [rsp+0C0h+var_98], r15d
0x180037456  mov     [rsp+0C0h+var_A0], r14
0x18003745b  mov     r9, rbx
0x18003745e  mov     r8, rdi
0x180037461  mov     rdx, rsi
0x180037464  lea     rcx, [rbp+57h+arg_10]
0x180037468  call    ?ReportAssociationError@IoCompletionPort@Support@CoreUI@Microsoft@@AEAAXUWaitCompletionPacket@234@UWin32Handle@234@UIntPtr@System@@2I@Z; Microsoft::CoreUI::Support::IoCompletionPort::ReportAssociationError(Microsoft::CoreUI::Support::WaitCompletionPacket,Microsoft::CoreUI::Support::Win32Handle,System::IntPtr,System::IntPtr,uint)
0x18003746d  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits+1, 4
0x180037474  jz      short loc_18003748C
0x180037476  mov     dword ptr [rsp+0C0h+var_98], r15d
0x18003747b  mov     [rsp+0C0h+var_A0], rdi
0x180037480  mov     r9, [rbp+57h+arg_10]
0x180037484  mov     r8, rsi
0x180037487  call    McTemplateU0pppq_EventWriteTransfer
0x18003748c  xor     bl, bl
0x18003748e  jmp     loc_1800373BD
0x180037493  mov     dword ptr [rsp+0C0h+var_98], 0
0x18003749b  mov     dword ptr [rsp+0C0h+var_A0], 0
0x1800374a3  mov     r9, [r13+30h]
0x1800374a7  or      r8d, 0FFFFFFFFh
0x1800374ab  mov     rdx, r13
0x1800374ae  lea     rcx, [rbp+57h+var_80]
0x1800374b2  call    ??0WakeRecord@Dispatch@CoreUI@Microsoft@@QEAA@PEAVRegisteredWait@123@W4WaitStatus@123@UWin32Handle@Support@23@II@Z; Microsoft::CoreUI::Dispatch::WakeRecord::WakeRecord(Microsoft::CoreUI::Dispatch::RegisteredWait *,Microsoft::CoreUI::Dispatch::WaitStatus,Microsoft::CoreUI::Support::Win32Handle,uint,uint)
0x1800374b7  nop
0x1800374b8  lea     rdx, [rbp+57h+arg_0]
0x1800374bc  mov     rcx, [rbp+57h+arg_18]
0x1800374c0  call    ?Copy@?$SmartPtr@VEventLoopBridge@Dispatch@CoreUI@Microsoft@@@CFlat@@QEBA?AV12@XZ; CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::EventLoopBridge>::Copy(void)
0x1800374c5  nop
0x1800374c6  lea     r8, [rbp+57h+var_80]
0x1800374ca  mov     rdx, [rax]
0x1800374cd  mov     rcx, r13
0x1800374d0  call    ?QueueWakeCompletion@RegisteredWait@Dispatch@CoreUI@Microsoft@@QEAAXPEAVWaitCollection@234@U?$Ref@UWakeRecord@Dispatch@CoreUI@Microsoft@@@CFlat@@@Z; Microsoft::CoreUI::Dispatch::RegisteredWait::QueueWakeCompletion(Microsoft::CoreUI::Dispatch::WaitCollection *,CFlat::Ref<Microsoft::CoreUI::Dispatch::WakeRecord>)
0x1800374d5  nop
0x1800374d6  lea     rcx, [rbp+57h+arg_0]
0x1800374da  call    ??1?$SmartPtr@VEventLoop@Dispatch@CoreUI@Microsoft@@@CFlat@@QEAA@XZ; CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::EventLoop>::~SmartPtr<Microsoft::CoreUI::Dispatch::EventLoop>(void)
0x1800374df  xor     bl, bl
0x1800374e1  lea     rcx, [rbp+57h+var_80]
0x1800374e5  call    ??1?$SmartPtr@VEventLoop@Dispatch@CoreUI@Microsoft@@@CFlat@@QEAA@XZ; CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::EventLoop>::~SmartPtr<Microsoft::CoreUI::Dispatch::EventLoop>(void)
0x1800374ea  jmp     loc_1800373C9
```
