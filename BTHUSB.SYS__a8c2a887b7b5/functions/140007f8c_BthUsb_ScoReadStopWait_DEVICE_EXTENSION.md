# BthUsb_ScoReadStopWait(_DEVICE_EXTENSION *)

- ea: `0x140007f8c`
- end: `0x14000810f`
- name: `?BthUsb_ScoReadStopWait@@YAXPEAU_DEVICE_EXTENSION@@@Z`
- size: `387`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x14000581c`

## callees

- `0x14000175c`
- `0x1400017d4`
- `0x1400076e8`
- `0x140007f8c`
- `0x14000db7c`
- `0x14000dbc4`
- `0x14001b73c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140008008`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008008`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007ff0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007ff0`

## pseudocode

```c
void __fastcall BthUsb_ScoReadStopWait(struct _DEVICE_EXTENSION *a1, __int16 a2, int a3)
{
  char v4; // di
  KIRQL v5; // al
  unsigned __int16 v6; // dx
  int v7; // r9d
  int v8; // eax
  int v9; // edx
  __int16 v10; // dx
  int v11; // r8d
  __int16 v12; // dx
  int v13; // r8d

  v4 = 1;
  LOBYTE(a2) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    a2,
    a3,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    4,
    19,
    (__int64)WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids);
  v5 = KeAcquireSpinLockRaiseToDpc(&a1->Sco.ReadLock);
  a1->Sco.ReadsEnabled = 0;
  KeReleaseSpinLock(&a1->Sco.ReadLock, v5);
  ResourceQueue_Stop(&a1->Sco.ReadCtxQueue);
  v8 = BthUsb_PipeRequest(a1, v6, a1->Pipes[3].PipeHandle, v7);
  if ( v8 < 0 )
  {
    LOBYTE(v9) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    WPP_RECORDER_AND_TRACE_SF_D(
      WPP_GLOBAL_Control->AttachedDevice,
      v9,
      (_DWORD)WPP_GLOBAL_Control,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      4,
      20,
      (__int64)WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids,
      v8);
  }
  BthUsb_ScoFreePartialUsbCtx(a1);
  LOBYTE(v10) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    v10,
    v11,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    4,
    21,
    (__int64)WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids);
  ResourceQueue_StopAndWait(&a1->Sco.ReadCtxQueue);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    v4 = 0;
  LOBYTE(v12) = v4;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    v12,
    v13,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    4,
    22,
    (__int64)WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids);
}

```

## disassembly

```asm
0x140007f8c  push    rbx
0x140007f8e  push    rbp
0x140007f8f  push    rsi
0x140007f90  push    rdi
0x140007f91  push    r15
0x140007f93  sub     rsp, 50h
0x140007f97  mov     rsi, rcx
0x140007f9a  mov     rcx, cs:WPP_GLOBAL_Control
0x140007fa1  mov     dil, 1
0x140007fa4  mov     ebp, 4
0x140007fa9  mov     eax, [rcx+2Ch]
0x140007fac  test    al, 8
0x140007fae  jz      short loc_140007FBB
0x140007fb0  cmp     [rcx+29h], bpl
0x140007fb4  jb      short loc_140007FBB
0x140007fb6  mov     dl, dil
0x140007fb9  jmp     short loc_140007FBD
0x140007fbb  xor     dl, dl
0x140007fbd  mov     r9, [rcx+40h]
0x140007fc1  lea     r15, WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids
0x140007fc8  mov     rcx, [rcx+18h]
0x140007fcc  mov     [rsp+78h+var_40], r15
0x140007fd1  mov     [rsp+78h+var_48], 13h
0x140007fd8  mov     [rsp+78h+var_50], ebp
0x140007fdc  mov     [rsp+78h+var_58], bpl
0x140007fe1  call    WPP_RECORDER_AND_TRACE_SF_
0x140007fe6  lea     rbx, [rsi+248h]
0x140007fed  mov     rcx, rbx; SpinLock
0x140007ff0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007ff7  nop     dword ptr [rax+rax+00h]
0x140007ffc  mov     rcx, rbx; SpinLock
0x140007fff  mov     byte ptr [rsi+256h], 0
0x140008006  mov     dl, al; NewIrql
0x140008008  call    cs:__imp_KeReleaseSpinLock
0x14000800f  nop     dword ptr [rax+rax+00h]
0x140008014  lea     rbx, [rsi+198h]
0x14000801b  mov     rcx, rbx
0x14000801e  call    ResourceQueue_Stop
0x140008023  mov     r8, [rsi+0C0h]; void *
0x14000802a  mov     rcx, rsi; struct _DEVICE_EXTENSION *
0x14000802d  call    ?BthUsb_PipeRequest@@YAJPEAU_DEVICE_EXTENSION@@GPEAXJ@Z; BthUsb_PipeRequest(_DEVICE_EXTENSION *,ushort,void *,long)
0x140008032  test    eax, eax
0x140008034  jns     short loc_14000807A
0x140008036  mov     r8, cs:WPP_GLOBAL_Control
0x14000803d  mov     ecx, [r8+2Ch]
0x140008041  test    cl, 8
0x140008044  jz      short loc_140008052
0x140008046  cmp     byte ptr [r8+29h], 2
0x14000804b  jb      short loc_140008052
0x14000804d  mov     dl, dil
0x140008050  jmp     short loc_140008054
0x140008052  xor     dl, dl
0x140008054  mov     r9, [r8+40h]
0x140008058  mov     rcx, [r8+18h]
0x14000805c  mov     [rsp+78h+var_38], eax
0x140008060  mov     [rsp+78h+var_40], r15
0x140008065  mov     [rsp+78h+var_48], 14h
0x14000806c  mov     [rsp+78h+var_50], ebp
0x140008070  mov     [rsp+78h+var_58], 2
0x140008075  call    WPP_RECORDER_AND_TRACE_SF_D
0x14000807a  mov     rcx, rsi; struct _DEVICE_EXTENSION *
0x14000807d  call    ?BthUsb_ScoFreePartialUsbCtx@@YAXPEAU_DEVICE_EXTENSION@@@Z; BthUsb_ScoFreePartialUsbCtx(_DEVICE_EXTENSION *)
0x140008082  mov     rcx, cs:WPP_GLOBAL_Control
0x140008089  mov     eax, [rcx+2Ch]
0x14000808c  test    al, 8
0x14000808e  jz      short loc_14000809B
0x140008090  cmp     [rcx+29h], bpl
0x140008094  jb      short loc_14000809B
0x140008096  mov     dl, dil
0x140008099  jmp     short loc_14000809D
0x14000809b  xor     dl, dl
0x14000809d  mov     r9, [rcx+40h]
0x1400080a1  mov     rcx, [rcx+18h]
0x1400080a5  mov     [rsp+78h+var_40], r15
0x1400080aa  mov     [rsp+78h+var_48], 15h
0x1400080b1  mov     [rsp+78h+var_50], ebp
0x1400080b5  mov     [rsp+78h+var_58], bpl
0x1400080ba  call    WPP_RECORDER_AND_TRACE_SF_
0x1400080bf  mov     rcx, rbx
0x1400080c2  call    ResourceQueue_StopAndWait
0x1400080c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400080ce  mov     eax, [rcx+2Ch]
0x1400080d1  test    al, 8
0x1400080d3  jz      short loc_1400080DB
0x1400080d5  cmp     [rcx+29h], bpl
0x1400080d9  jnb     short loc_1400080DE
0x1400080db  xor     dil, dil
0x1400080de  mov     r9, [rcx+40h]
0x1400080e2  mov     dl, dil
0x1400080e5  mov     rcx, [rcx+18h]
0x1400080e9  mov     [rsp+78h+var_40], r15
0x1400080ee  mov     [rsp+78h+var_48], 16h
0x1400080f5  mov     [rsp+78h+var_50], ebp
0x1400080f9  mov     [rsp+78h+var_58], bpl
0x1400080fe  call    WPP_RECORDER_AND_TRACE_SF_
0x140008103  add     rsp, 50h
0x140008107  pop     r15
0x140008109  pop     rdi
0x14000810a  pop     rsi
0x14000810b  pop     rbp
0x14000810c  pop     rbx
0x14000810d  retn
```
