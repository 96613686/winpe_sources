# DeviceCommandScheduler::CancelTask(DeviceCommand *)

- ea: `0x14004bf10`
- end: `0x14004c0b2`
- name: `?CancelTask@DeviceCommandScheduler@@QEAAXPEAVDeviceCommand@@@Z`
- size: `418`
- prototype: `void __fastcall(DeviceCommandScheduler *__hidden this, struct DeviceCommand *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14005f868`
- `0x14006e8e8`

## callees

- `0x1400259d8`
- `0x14002a7c8`
- `0x140034e04`
- `0x140034ec4`
- `0x14004bf10`
- `0x14004c0b8`
- `0x14004c4f4`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14004bf5c`
- `ntoskrnl!ExAllocatePool2` at `0x14004bf5c`

## pseudocode

```c
void __fastcall DeviceCommandScheduler::CancelTask(DeviceCommandScheduler *this, struct DeviceCommand *a2)
{
  struct DeviceCommand *v2; // rsi
  DeviceCommand *Pool2; // rax
  DeviceCommand *v5; // rbx
  int v6; // edx
  int started; // edi
  int v8; // r8d
  __int64 v9; // [rsp+28h] [rbp-40h]

  v2 = a2;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      15,
      (__int64)WPP_2b7c372e88823a80955d729bf23dceec_Traceguids);
  }
  if ( v2 )
  {
    Pool2 = (DeviceCommand *)ExAllocatePool2(64, 248, 1198089303);
    v5 = Pool2;
    if ( Pool2 )
    {
      DeviceCommand::DeviceCommand(Pool2, v2->m_ActivityId);
      v5->__vftable = (DeviceCommand_vtbl *)&CancelDeviceCommand::`vftable';
      started = CancelDeviceCommand::Initialize(v5, v2, this->m_pAdapter);
      if ( started )
        goto LABEL_18;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v6) = 4;
        WPP_RECORDER_SF_q(
          WPP_GLOBAL_Control->DeviceExtension,
          v6,
          v8,
          16,
          (__int64)WPP_2b7c372e88823a80955d729bf23dceec_Traceguids,
          (char)v2);
      }
      started = DeviceCommandScheduler::StartCommand(
                  this,
                  v5,
                  (struct IOperationCompletionCallback *)((unsigned __int64)&this->IOperationCompletionCallback
                                                        & -(__int64)(this != 0)),
                  v2->m_pParentJob);
      if ( started )
LABEL_18:
        ((void (__fastcall *)(DeviceCommand *, __int64))v5->~DeviceCommand)(v5, 1);
    }
    else
    {
      started = -1073741670;
    }
  }
  else
  {
    started = -1073741811;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v9) = started;
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      17,
      (__int64)WPP_2b7c372e88823a80955d729bf23dceec_Traceguids,
      v9);
  }
}

```

## disassembly

```asm
0x14004bf10  push    rbx
0x14004bf12  push    rbp
0x14004bf13  push    rsi
0x14004bf14  push    rdi
0x14004bf15  push    r13
0x14004bf17  push    r14
0x14004bf19  push    r15
0x14004bf1b  sub     rsp, 30h
0x14004bf1f  mov     rsi, rdx
0x14004bf22  mov     rbp, rcx
0x14004bf25  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004bf2c  xor     r14d, r14d
0x14004bf2f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14004bf36  lea     r13, WPP_2b7c372e88823a80955d729bf23dceec_Traceguids
0x14004bf3d  jnz     loc_14004C059
0x14004bf43  test    rsi, rsi
0x14004bf46  jz      loc_14004C090
0x14004bf4c  mov     edx, 0F8h
0x14004bf51  mov     ecx, 40h ; '@'
0x14004bf56  mov     r8d, 47696457h
0x14004bf5c  call    cs:__imp_ExAllocatePool2
0x14004bf63  nop     dword ptr [rax+rax+00h]
0x14004bf68  mov     rbx, rax
0x14004bf6b  test    rax, rax
0x14004bf6e  jz      loc_14004C02B
0x14004bf74  mov     edx, [rsi+8]; unsigned int
0x14004bf77  mov     rcx, rax; this
0x14004bf7a  call    ??0DeviceCommand@@QEAA@K@Z; DeviceCommand::DeviceCommand(ulong)
0x14004bf7f  lea     rcx, ??_7CancelDeviceCommand@@6B@; const CancelDeviceCommand::`vftable'
0x14004bf86  mov     rdx, rsi; DeviceCommand *
0x14004bf89  mov     [rbx], rcx
0x14004bf8c  mov     rcx, rbx; this
0x14004bf8f  mov     r8, [rbp+0B0h]; struct CAdapter *
0x14004bf96  call    ?Initialize@CancelDeviceCommand@@QEAAHPEAVDeviceCommand@@PEAVCAdapter@@@Z; CancelDeviceCommand::Initialize(DeviceCommand *,CAdapter *)
0x14004bf9b  mov     edi, eax
0x14004bf9d  test    eax, eax
0x14004bf9f  jnz     loc_14004C09A
0x14004bfa5  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14004bfac  jnz     loc_14004C032
0x14004bfb2  mov     r9, [rsi+0A8h]; struct CJobBase *
0x14004bfb9  lea     rcx, [rbp+8]
0x14004bfbd  mov     rax, rbp
0x14004bfc0  mov     rdx, rbx; struct DeviceCommand *
0x14004bfc3  neg     rax
0x14004bfc6  sbb     r8, r8
0x14004bfc9  and     r8, rcx; struct IOperationCompletionCallback *
0x14004bfcc  mov     rcx, rbp; this
0x14004bfcf  call    ?StartCommand@DeviceCommandScheduler@@QEAAHPEAVDeviceCommand@@PEAVIOperationCompletionCallback@@PEAVCJobBase@@@Z; DeviceCommandScheduler::StartCommand(DeviceCommand *,IOperationCompletionCallback *,CJobBase *)
0x14004bfd4  mov     edi, eax
0x14004bfd6  test    eax, eax
0x14004bfd8  jnz     loc_14004C09A
0x14004bfde  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14004bfe5  jnz     short loc_14004BFF7
0x14004bfe7  add     rsp, 30h
0x14004bfeb  pop     r15
0x14004bfed  pop     r14
0x14004bfef  pop     r13
0x14004bff1  pop     rdi
0x14004bff2  pop     rsi
0x14004bff3  pop     rbp
0x14004bff4  pop     rbx
0x14004bff5  retn
0x14004bff7  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bffe  cmp     byte ptr [rcx+29h], 5
0x14004c002  jnb     short loc_14004C00B
0x14004c004  cmp     [rcx+48h], r14w
0x14004c009  jz      short loc_14004BFE7
0x14004c00b  mov     rcx, [rcx+40h]
0x14004c00f  mov     r9d, 11h
0x14004c015  mov     dword ptr [rsp+68h+var_40], edi
0x14004c019  mov     dl, 5
0x14004c01b  mov     [rsp+68h+var_48], r13
0x14004c020  lea     r8d, [r9-10h]
0x14004c024  call    WPP_RECORDER_SF_D
0x14004c029  jmp     short loc_14004BFE7
0x14004c02b  mov     edi, 0C000009Ah
0x14004c030  jmp     short loc_14004BFDE
0x14004c032  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c039  mov     r9d, 10h
0x14004c03f  mov     [rsp+68h+var_40], rsi
0x14004c044  mov     dl, 4
0x14004c046  mov     [rsp+68h+var_48], r13
0x14004c04b  mov     rcx, [rcx+40h]
0x14004c04f  call    WPP_RECORDER_SF_q
0x14004c054  jmp     loc_14004BFB2
0x14004c059  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c060  cmp     byte ptr [rcx+29h], 5
0x14004c064  jnb     short loc_14004C071
0x14004c066  cmp     [rcx+48h], r14w
0x14004c06b  jz      loc_14004BF43
0x14004c071  mov     rcx, [rcx+40h]
0x14004c075  mov     r9d, 0Fh
0x14004c07b  mov     dl, 5
0x14004c07d  mov     [rsp+68h+var_48], r13
0x14004c082  lea     r8d, [r9-0Eh]
0x14004c086  call    WPP_RECORDER_SF_
0x14004c08b  jmp     loc_14004BF43
0x14004c090  mov     edi, 0C000000Dh
0x14004c095  jmp     loc_14004BFDE
0x14004c09a  mov     rax, [rbx]
0x14004c09d  mov     edx, 1
0x14004c0a2  mov     rcx, rbx
0x14004c0a5  mov     rax, [rax]
0x14004c0a8  call    _guard_dispatch_icall
0x14004c0ad  jmp     loc_14004BFDE
```
