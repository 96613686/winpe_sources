# EtwOpnEventControlEnableCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x14001db50`
- end: `0x14001dbf7`
- name: `?EtwOpnEventControlEnableCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `167`
- prototype: `ETWENABLECALLBACK`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14001db50`
- `0x140020c18`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x14001dbe4`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001dbe4`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14001db96`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14001db96`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001dbaf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001dbaf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001db65`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001db65`

## pseudocode

```c
void __fastcall EtwOpnEventControlEnableCallback(
        LPCGUID SourceId,
        ULONG ControlCode,
        UCHAR Level,
        ULONGLONG MatchAnyKeyword)
{
  struct _LIST_ENTRY *v4; // rbx
  __int64 v5; // r8
  __int16 Flink; // [rsp+38h] [rbp+10h] BYREF
  __int16 v7; // [rsp+3Ah] [rbp+12h]

  if ( ControlCode == 1 )
  {
    LOBYTE(WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue);
    if ( (struct _LIST_ENTRY **)WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink == &WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink )
    {
      v4 = 0;
    }
    else
    {
      v4 = WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink - 3;
      ExAcquireRundownProtection((PEX_RUNDOWN_REF)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink[-2]);
    }
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue, (KIRQL)WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink);
    if ( v4 )
    {
      Flink = (__int16)v4[5].Flink;
      v7 = WORD1(v4[5].Flink);
      MbbUtilWriteMbimVersionOpnEvent(0, 0, v5, (__int64)&Flink);
      ExReleaseRundownProtection((PEX_RUNDOWN_REF)&v4[1]);
    }
  }
}

```

## disassembly

```asm
0x14001db50  cmp     edx, 1
0x14001db53  jnz     locret_14001DBF5
0x14001db59  push    rbx
0x14001db5a  sub     rsp, 20h
0x14001db5e  lea     rcx, WPP_MAIN_CB.DeviceQueue; SpinLock
0x14001db65  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001db6c  nop     dword ptr [rax+rax+00h]
0x14001db71  mov     rbx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x14001db78  mov     byte ptr cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink, al
0x14001db7e  lea     rax, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x14001db85  cmp     rbx, rax
0x14001db88  jnz     short loc_14001DB8E
0x14001db8a  xor     ebx, ebx
0x14001db8c  jmp     short loc_14001DBA2
0x14001db8e  add     rbx, 0FFFFFFFFFFFFFFD0h
0x14001db92  lea     rcx, [rbx+10h]; RunRef
0x14001db96  call    cs:__imp_ExAcquireRundownProtection
0x14001db9d  nop     dword ptr [rax+rax+00h]
0x14001dba2  mov     dl, byte ptr cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink; NewIrql
0x14001dba8  lea     rcx, WPP_MAIN_CB.DeviceQueue; SpinLock
0x14001dbaf  call    cs:__imp_KeReleaseSpinLock
0x14001dbb6  nop     dword ptr [rax+rax+00h]
0x14001dbbb  test    rbx, rbx
0x14001dbbe  jz      short loc_14001DBF0
0x14001dbc0  movzx   eax, word ptr [rbx+50h]
0x14001dbc4  lea     r9, [rsp+28h+arg_8]
0x14001dbc9  mov     [rsp+28h+arg_8], ax
0x14001dbce  xor     edx, edx
0x14001dbd0  movzx   eax, word ptr [rbx+52h]
0x14001dbd4  xor     ecx, ecx
0x14001dbd6  mov     [rsp+28h+arg_A], ax
0x14001dbdb  call    ?MbbUtilWriteMbimVersionOpnEvent@@YAXPEAU_GUID@@KW4_MBB_STATUS@@PEAU_MBB_MS_VERSION_INFO@@@Z; MbbUtilWriteMbimVersionOpnEvent(_GUID *,ulong,_MBB_STATUS,_MBB_MS_VERSION_INFO *)
0x14001dbe0  lea     rcx, [rbx+10h]; RunRef
0x14001dbe4  call    cs:__imp_ExReleaseRundownProtection
0x14001dbeb  nop     dword ptr [rax+rax+00h]
0x14001dbf0  add     rsp, 20h
0x14001dbf4  pop     rbx
0x14001dbf5  retn
```
