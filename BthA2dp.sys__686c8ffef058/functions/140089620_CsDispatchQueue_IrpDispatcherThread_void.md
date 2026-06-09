# CsDispatchQueue::IrpDispatcherThread(void)

- ea: `0x140089620`
- end: `0x1400897a9`
- name: `?IrpDispatcherThread@CsDispatchQueue@@AEAAXXZ`
- size: `393`
- prototype: `void __fastcall(CsDispatchQueue *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x14005b200`

## callees

- `0x140003530`
- `0x14002d890`
- `0x14005afa0`
- `0x14005b8a0`
- `0x14005bb10`
- `0x140089620`

## import_xrefs

- `ntoskrnl!KeWaitForMultipleObjects` at `0x14008976f`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14008976f`
- `ntoskrnl!PsTerminateSystemThread` at `0x14008978f`
- `ntoskrnl!PsTerminateSystemThread` at `0x14008978f`

## pseudocode

```c
void __fastcall CsDispatchQueue::IrpDispatcherThread(CsDispatchQueue *this)
{
  bool v2; // dl
  __int64 v3; // rdx
  __int64 v4; // rcx
  struct _IRP *v5; // rdi
  __int64 v6; // r8
  __int64 v7; // r9
  bool v8; // dl
  NTSTATUS v9; // edi
  PVOID Object[7]; // [rsp+50h] [rbp-38h] BYREF

  v2 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      1,
      32,
      (__int64)WPP_6372fbb7e78435cbabebbbab2162309b_Traceguids,
      (char)this);
  Object[0] = (char *)this + 168;
  Object[1] = (char *)this + 144;
  while ( 1 )
  {
    v9 = KeWaitForMultipleObjects(2u, Object, WaitAny, Executive, 0, 0, 0, 0);
    if ( v9 )
      break;
    v5 = CsQueue::RemoveIrp(this);
    if ( v5 )
    {
      if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v4, v3, v6, v7) )
      {
        v8 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_AND_TRACE_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            v8,
            WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
            WPP_GLOBAL_Control->DeviceExtension,
            4,
            1,
            33,
            (__int64)WPP_6372fbb7e78435cbabebbbab2162309b_Traceguids,
            (char)v5);
      }
      utl::function<void (_IRP *)>::operator()((char *)this + 256, v5);
    }
  }
  CsQueue::StopAndFlush(this);
  PsTerminateSystemThread(v9);
}

```

## disassembly

```asm
0x140089620  push    rbx
0x140089622  push    rdi
0x140089623  push    r13
0x140089625  push    r14
0x140089627  push    r15
0x140089629  sub     rsp, 60h
0x14008962d  mov     rbx, rcx
0x140089630  mov     rcx, cs:WPP_GLOBAL_Control
0x140089637  lea     r14, WPP_GLOBAL_Control
0x14008963e  cmp     rcx, r14
0x140089641  jz      short loc_140089654
0x140089643  mov     eax, [rcx+2Ch]
0x140089646  test    al, 1
0x140089648  jz      short loc_140089654
0x14008964a  cmp     byte ptr [rcx+29h], 4
0x14008964e  jb      short loc_140089654
0x140089650  mov     dl, 1
0x140089652  jmp     short loc_140089656
0x140089654  xor     dl, dl
0x140089656  lea     r15, WPP_RECORDER_INITIALIZED
0x14008965d  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140089664  lea     r13, WPP_6372fbb7e78435cbabebbbab2162309b_Traceguids
0x14008966b  setnz   r8b
0x14008966f  test    dl, dl
0x140089671  jnz     short loc_140089678
0x140089673  test    r8b, r8b
0x140089676  jz      short loc_1400896A3
0x140089678  mov     r9, [rcx+40h]
0x14008967c  mov     rcx, [rcx+18h]
0x140089680  mov     [rsp+88h+var_48], rbx
0x140089685  mov     [rsp+88h+WaitBlockArray], r13
0x14008968a  mov     word ptr [rsp+88h+Timeout], 20h ; ' '
0x140089691  mov     dword ptr [rsp+88h+Alertable], 1
0x140089699  mov     [rsp+88h+WaitMode], 4
0x14008969e  call    WPP_RECORDER_AND_TRACE_SF_q
0x1400896a3  lea     rax, [rbx+0A8h]
0x1400896aa  mov     [rsp+88h+Object], rax
0x1400896af  lea     rax, [rbx+90h]
0x1400896b6  mov     [rsp+88h+var_30], rax
0x1400896bb  jmp     loc_140089743
0x1400896c0  call    ?RemoveIrp@CsQueue@@UEAAPEAU_IRP@@XZ; CsQueue::RemoveIrp(void)
0x1400896c5  mov     rdi, rax
0x1400896c8  test    rax, rax
0x1400896cb  jz      short loc_140089743
0x1400896cd  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x1400896d2  test    eax, eax
0x1400896d4  jz      short loc_140089734
0x1400896d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400896dd  cmp     rcx, r14
0x1400896e0  jz      short loc_1400896F3
0x1400896e2  mov     eax, [rcx+2Ch]
0x1400896e5  test    al, 1
0x1400896e7  jz      short loc_1400896F3
0x1400896e9  cmp     byte ptr [rcx+29h], 4
0x1400896ed  jb      short loc_1400896F3
0x1400896ef  mov     dl, 1
0x1400896f1  jmp     short loc_1400896F5
0x1400896f3  xor     dl, dl
0x1400896f5  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400896fc  setnz   r8b
0x140089700  test    dl, dl
0x140089702  jnz     short loc_140089709
0x140089704  test    r8b, r8b
0x140089707  jz      short loc_140089734
0x140089709  mov     r9, [rcx+40h]
0x14008970d  mov     rcx, [rcx+18h]
0x140089711  mov     [rsp+88h+var_48], rdi
0x140089716  mov     [rsp+88h+WaitBlockArray], r13
0x14008971b  mov     word ptr [rsp+88h+Timeout], 21h ; '!'
0x140089722  mov     dword ptr [rsp+88h+Alertable], 1
0x14008972a  mov     [rsp+88h+WaitMode], 4
0x14008972f  call    WPP_RECORDER_AND_TRACE_SF_q
0x140089734  lea     rcx, [rbx+100h]
0x14008973b  mov     rdx, rdi
0x14008973e  call    ??R?$function@$$A6AXPEAU_IRP@@@Z@utl@@QEBAXPEAU_IRP@@@Z; utl::function<void (_IRP *)>::operator()(_IRP *)
0x140089743  xor     r9d, r9d; WaitReason
0x140089746  mov     [rsp+88h+WaitBlockArray], 0; WaitBlockArray
0x14008974f  mov     [rsp+88h+Timeout], 0; Timeout
0x140089758  lea     rdx, [rsp+88h+Object]; Object
0x14008975d  mov     [rsp+88h+Alertable], 0; Alertable
0x140089762  mov     [rsp+88h+WaitMode], 0; WaitMode
0x140089767  lea     r8d, [r9+1]; WaitType
0x14008976b  lea     ecx, [r9+2]; Count
0x14008976f  call    cs:__imp_KeWaitForMultipleObjects
0x140089776  nop     dword ptr [rax+rax+00h]
0x14008977b  mov     edi, eax
0x14008977d  mov     rcx, rbx; this
0x140089780  test    eax, eax
0x140089782  jz      loc_1400896C0
0x140089788  call    ?StopAndFlush@CsQueue@@QEAAXXZ; CsQueue::StopAndFlush(void)
0x14008978d  mov     ecx, edi; ExitStatus
0x14008978f  call    cs:__imp_PsTerminateSystemThread
0x140089796  nop     dword ptr [rax+rax+00h]
0x14008979b  add     rsp, 60h
0x14008979f  pop     r15
0x1400897a1  pop     r14
0x1400897a3  pop     r13
0x1400897a5  pop     rdi
0x1400897a6  pop     rbx
0x1400897a7  retn
```
