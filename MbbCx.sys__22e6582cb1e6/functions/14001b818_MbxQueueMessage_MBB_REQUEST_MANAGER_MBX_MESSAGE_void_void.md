# MbxQueueMessage(_MBB_REQUEST_MANAGER *,MBX_MESSAGE,void *,void *)

- ea: `0x14001b818`
- end: `0x14001b8a2`
- name: `?MbxQueueMessage@@YAHPEAU_MBB_REQUEST_MANAGER@@W4MBX_MESSAGE@@PEAX2@Z`
- size: `138`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000b030`
- `0x14000efa4`
- `0x1400196ac`
- `0x14001a168`
- `0x14001b0b0`
- `0x14001b1c0`
- `0x14001ffa4`
- `0x140020330`

## callees

- `0x1400051ac`
- `0x14001b818`
- `0x14002426c`

## pseudocode

```c
__int64 __fastcall MbxQueueMessage(PKSPIN_LOCK *a1, int a2, void *a3, void *a4)
{
  unsigned int v5; // ebx
  void (*v7)(void *, void *, void *, void *); // [rsp+28h] [rbp-20h]
  int v8; // [rsp+30h] [rbp-18h]

  v5 = MbbWorkMgrQueueWorkItem(
         a1[52],
         a1,
         (void *)a2,
         a3,
         a4,
         (void (*)(void *, void *, void *, void *))MbxMessagesHandler);
  if ( v5 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v8 = v5;
    LODWORD(v7) = a2;
    WPP_RECORDER_SF_DD(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      2u,
      4u,
      0x26u,
      (__int64)WPP_801d9c80458c3ec5e4bb5440382a0f20_Traceguids,
      v7,
      v8);
  }
  return v5;
}

```

## disassembly

```asm
0x14001b818  mov     [rsp+arg_0], rbx
0x14001b81d  push    rdi
0x14001b81e  sub     rsp, 40h
0x14001b822  movsxd  rdi, edx
0x14001b825  mov     rax, r8
0x14001b828  lea     rdx, ?MbxMessagesHandler@@YAXPEAX000@Z; MbxMessagesHandler(void *,void *,void *,void *)
0x14001b82f  mov     r8, rdi; void *
0x14001b832  mov     [rsp+48h+var_20], rdx; void (*)(void *, void *, void *, void *)
0x14001b837  mov     rdx, rcx; void *
0x14001b83a  mov     rcx, [rcx+1A0h]; SpinLock
0x14001b841  mov     [rsp+48h+var_28], r9; void *
0x14001b846  mov     r9, rax; void *
0x14001b849  call    ?MbbWorkMgrQueueWorkItem@@YAHPEAX0000P6AX0000@Z@Z; MbbWorkMgrQueueWorkItem(void *,void *,void *,void *,void *,void (*)(void *,void *,void *,void *))
0x14001b84e  mov     ebx, eax
0x14001b850  test    eax, eax
0x14001b852  jz      short loc_14001B894
0x14001b854  lea     rax, WPP_RECORDER_INITIALIZED
0x14001b85b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001b862  jz      short loc_14001B894
0x14001b864  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b86b  lea     rax, WPP_801d9c80458c3ec5e4bb5440382a0f20_Traceguids
0x14001b872  mov     r9d, 26h ; '&'
0x14001b878  mov     [rsp+48h+var_18], ebx
0x14001b87c  mov     dword ptr [rsp+48h+var_20], edi
0x14001b880  mov     dl, 2
0x14001b882  mov     [rsp+48h+var_28], rax
0x14001b887  mov     rcx, [rcx+40h]
0x14001b88b  lea     r8d, [r9-22h]
0x14001b88f  call    WPP_RECORDER_SF_DD
0x14001b894  mov     eax, ebx
0x14001b896  mov     rbx, [rsp+48h+arg_0]
0x14001b89b  add     rsp, 40h
0x14001b89f  pop     rdi
0x14001b8a0  retn
```
