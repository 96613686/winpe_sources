# EM_HandlePolicyUpdate(void *)

- ea: `0x140028a20`
- end: `0x140028c1d`
- name: `?EM_HandlePolicyUpdate@@YAXPEAX@Z`
- size: `509`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x140005608`
- `0x140005690`
- `0x14000abf4`
- `0x1400272a4`
- `0x140028a20`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x140028b8b`
- `ntoskrnl!IoFreeWorkItem` at `0x140028b8b`
- `ntoskrnl!IoAllocateWorkItem` at `0x140028aa4`
- `ntoskrnl!IoAllocateWorkItem` at `0x140028aa4`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140028b27`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140028b27`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140028bb6`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140028bb6`

## pseudocode

```c
void __fastcall EM_HandlePolicyUpdate(char *a1, __int64 a2, __int64 a3)
{
  PDEVICE_OBJECT v4; // rcx
  __int16 DeviceType; // ax
  struct _DEVICE_OBJECT *m_controlDevice; // rcx
  int v7; // edx
  struct _IO_WORKITEM *WorkItem; // rbx
  int v9; // r8d
  int v10; // edx
  int v11; // r8d
  char v12; // si
  NTSTATUS v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  void *v17; // r9

  v4 = WPP_GLOBAL_Control;
  if ( !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xBu)
    || (LOBYTE(a2) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
  {
    LOBYTE(a2) = 0;
  }
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  LOBYTE(a3) = DeviceType != 0;
  if ( (_BYTE)a2 || DeviceType )
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      a2,
      a3,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      12,
      36,
      (__int64)WPP_f44453fc40fe39d84113d29c29467d77_Traceguids);
  if ( (unsigned int)Feature_59215879__private_IsEnabledDeviceUsageNoInline(v4, a2, a3) )
    m_controlDevice = Driver::GetInstance()->m_controlDevice;
  else
    m_controlDevice = (struct _DEVICE_OBJECT *)*((_QWORD *)a1 + 1);
  WorkItem = IoAllocateWorkItem(m_controlDevice);
  if ( WorkItem )
  {
    v13 = IoAcquireRemoveLockEx(
            (PIO_REMOVE_LOCK)(a1 + 56),
            EM_HandlePolicyUpdateWorker,
            "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\enterprisemanagement.cpp",
            0xDBu,
            0x20u);
    v12 = v13;
    if ( v13 >= 0 )
    {
      if ( (unsigned int)Feature_59215879__private_IsEnabledDeviceUsageNoInline(v15, v14, v16) )
        v17 = a1;
      else
        v17 = 0;
      IoQueueWorkItemEx(WorkItem, (PIO_WORKITEM_ROUTINE_EX)EM_HandlePolicyUpdateWorker, DelayedWorkQueue, v17);
    }
    else
    {
      if ( !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xBu)
        || (LOBYTE(v14) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      {
        LOBYTE(v14) = 0;
      }
      LOBYTE(v16) = 1;
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        v14,
        v16,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        12,
        38,
        (__int64)WPP_f44453fc40fe39d84113d29c29467d77_Traceguids,
        v13);
      IoFreeWorkItem(WorkItem);
    }
  }
  else
  {
    if ( !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xBu)
      || (LOBYTE(v7) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
    {
      LOBYTE(v7) = 0;
    }
    LOBYTE(v9) = 1;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v7,
      v9,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      12,
      37,
      (__int64)WPP_f44453fc40fe39d84113d29c29467d77_Traceguids);
    v12 = -102;
  }
  if ( !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xBu)
    || (LOBYTE(v10) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
  {
    LOBYTE(v10) = 0;
  }
  LOBYTE(v11) = 1;
  WPP_RECORDER_AND_TRACE_SF_d(
    WPP_GLOBAL_Control->AttachedDevice,
    v10,
    v11,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    12,
    39,
    (__int64)WPP_f44453fc40fe39d84113d29c29467d77_Traceguids,
    v12);
}

```

## disassembly

```asm
0x140028a20  push    rbx
0x140028a22  push    rbp
0x140028a23  push    rsi
0x140028a24  push    rdi
0x140028a25  push    r12
0x140028a27  push    r15
0x140028a29  sub     rsp, 58h
0x140028a2d  mov     rdi, rcx
0x140028a30  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140028a37  xor     ebp, ebp
0x140028a39  bt      dword ptr [rcx+2Ch], 0Bh
0x140028a3e  jnb     short loc_140028A48
0x140028a40  cmp     byte ptr [rcx+29h], 5
0x140028a44  mov     dl, 1
0x140028a46  jnb     short loc_140028A4B
0x140028a48  mov     dl, bpl
0x140028a4b  movzx   eax, word ptr [rcx+48h]
0x140028a4f  lea     r12, WPP_f44453fc40fe39d84113d29c29467d77_Traceguids
0x140028a56  test    ax, ax
0x140028a59  setnz   r8b
0x140028a5d  test    dl, dl
0x140028a5f  jnz     short loc_140028A66
0x140028a61  test    ax, ax
0x140028a64  jz      short loc_140028A8C
0x140028a66  mov     r9, [rcx+40h]
0x140028a6a  mov     rcx, [rcx+18h]
0x140028a6e  mov     [rsp+88h+var_50], r12
0x140028a73  mov     [rsp+88h+var_58], 24h ; '$'
0x140028a7a  mov     [rsp+88h+var_60], 0Ch
0x140028a82  mov     byte ptr [rsp+88h+RemlockSize], 5
0x140028a87  call    WPP_RECORDER_AND_TRACE_SF_
0x140028a8c  call    Feature_59215879__private_IsEnabledDeviceUsageNoInline
0x140028a91  test    eax, eax
0x140028a93  jz      short loc_140028AA0
0x140028a95  call    ?GetInstance@Driver@@SAAEAV1@XZ; Driver::GetInstance(void)
0x140028a9a  mov     rcx, [rax+10h]
0x140028a9e  jmp     short loc_140028AA4
0x140028aa0  mov     rcx, [rdi+8]; DeviceObject
0x140028aa4  call    cs:__imp_IoAllocateWorkItem
0x140028aab  nop     dword ptr [rax+rax+00h]
0x140028ab0  mov     rbx, rax
0x140028ab3  test    rax, rax
0x140028ab6  jnz     short loc_140028B04
0x140028ab8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140028abf  bt      dword ptr [rcx+2Ch], 0Bh
0x140028ac4  jnb     short loc_140028ACE
0x140028ac6  cmp     byte ptr [rcx+29h], 2
0x140028aca  mov     dl, 1
0x140028acc  jnb     short loc_140028AD1
0x140028ace  mov     dl, bpl
0x140028ad1  mov     r9, [rcx+40h]
0x140028ad5  mov     r8b, 1
0x140028ad8  mov     rcx, [rcx+18h]
0x140028adc  mov     [rsp+88h+var_50], r12
0x140028ae1  mov     [rsp+88h+var_58], 25h ; '%'
0x140028ae8  mov     [rsp+88h+var_60], 0Ch
0x140028af0  mov     byte ptr [rsp+88h+RemlockSize], 2
0x140028af5  call    WPP_RECORDER_AND_TRACE_SF_
0x140028afa  mov     esi, 0C000009Ah
0x140028aff  jmp     loc_140028BC9
0x140028b04  lea     r12, ?EM_HandlePolicyUpdateWorker@@YAXPEAX0PEAU_IO_WORKITEM@@@Z; EM_HandlePolicyUpdateWorker(void *,void *,_IO_WORKITEM *)
0x140028b0b  mov     [rsp+88h+RemlockSize], 20h ; ' '; RemlockSize
0x140028b13  mov     rdx, r12; Tag
0x140028b16  lea     rcx, [rdi+38h]; RemoveLock
0x140028b1a  mov     r9d, 0DBh; Line
0x140028b20  lea     r8, File; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140028b27  call    cs:__imp_IoAcquireRemoveLockEx
0x140028b2e  nop     dword ptr [rax+rax+00h]
0x140028b33  mov     esi, eax
0x140028b35  test    eax, eax
0x140028b37  jns     short loc_140028B99
0x140028b39  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140028b40  bt      dword ptr [r10+2Ch], 0Bh
0x140028b46  jnb     short loc_140028B51
0x140028b48  cmp     byte ptr [r10+29h], 2
0x140028b4d  mov     dl, 1
0x140028b4f  jnb     short loc_140028B54
0x140028b51  mov     dl, bpl
0x140028b54  mov     r9, [r10+40h]
0x140028b58  lea     r12, WPP_f44453fc40fe39d84113d29c29467d77_Traceguids
0x140028b5f  mov     rcx, [r10+18h]
0x140028b63  mov     r8b, 1
0x140028b66  mov     [rsp+88h+var_48], eax
0x140028b6a  mov     [rsp+88h+var_50], r12
0x140028b6f  mov     [rsp+88h+var_58], 26h ; '&'
0x140028b76  mov     [rsp+88h+var_60], 0Ch
0x140028b7e  mov     byte ptr [rsp+88h+RemlockSize], 2
0x140028b83  call    WPP_RECORDER_AND_TRACE_SF_d
0x140028b88  mov     rcx, rbx; IoWorkItem
0x140028b8b  call    cs:__imp_IoFreeWorkItem
0x140028b92  nop     dword ptr [rax+rax+00h]
0x140028b97  jmp     short loc_140028BC9
0x140028b99  call    Feature_59215879__private_IsEnabledDeviceUsageNoInline
0x140028b9e  mov     r8d, 1; QueueType
0x140028ba4  mov     rdx, r12; WorkerRoutine
0x140028ba7  mov     rcx, rbx; IoWorkItem
0x140028baa  test    eax, eax
0x140028bac  jz      short loc_140028BB3
0x140028bae  mov     r9, rdi
0x140028bb1  jmp     short loc_140028BB6
0x140028bb3  xor     r9d, r9d; Context
0x140028bb6  call    cs:__imp_IoQueueWorkItemEx
0x140028bbd  nop     dword ptr [rax+rax+00h]
0x140028bc2  lea     r12, WPP_f44453fc40fe39d84113d29c29467d77_Traceguids
0x140028bc9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140028bd0  bt      dword ptr [rcx+2Ch], 0Bh
0x140028bd5  jnb     short loc_140028BDF
0x140028bd7  cmp     byte ptr [rcx+29h], 4
0x140028bdb  mov     dl, 1
0x140028bdd  jnb     short loc_140028BE2
0x140028bdf  mov     dl, bpl
0x140028be2  mov     r9, [rcx+40h]
0x140028be6  mov     r8b, 1
0x140028be9  mov     rcx, [rcx+18h]
0x140028bed  mov     [rsp+88h+var_48], esi
0x140028bf1  mov     [rsp+88h+var_50], r12
0x140028bf6  mov     [rsp+88h+var_58], 27h ; '''
0x140028bfd  mov     [rsp+88h+var_60], 0Ch
0x140028c05  mov     byte ptr [rsp+88h+RemlockSize], 4
0x140028c0a  call    WPP_RECORDER_AND_TRACE_SF_d
0x140028c0f  add     rsp, 58h
0x140028c13  pop     r15
0x140028c15  pop     r12
0x140028c17  pop     rdi
0x140028c18  pop     rsi
0x140028c19  pop     rbp
0x140028c1a  pop     rbx
0x140028c1b  retn
```
