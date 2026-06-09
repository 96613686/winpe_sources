# QueueFindNextFree

- ea: `0x140007cc0`
- end: `0x140007ede`
- name: `QueueFindNextFree`
- size: `542`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140007f80`
- `0x140009c10`
- `0x14000be7c`

## callees

- `0x140002964`
- `0x140002a24`
- `0x140007cc0`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140007eb0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140007eb0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140007cf2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140007cf2`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140007d2d`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140007db6`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140007e18`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140007d2d`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140007db6`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140007e18`

## pseudocode

```c
__int64 __fastcall QueueFindNextFree(__int64 a1, _WORD *a2, __int64 a3, char a4)
{
  unsigned int v8; // ebx
  __int64 Default; // rax
  _DWORD *v10; // rax
  __int64 v11; // rax
  __int64 v12; // rdx
  int v13; // ebx
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned __int16 v16; // r8
  unsigned __int16 v17; // dx
  unsigned int v18; // eax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-48h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 1240), &LockHandle);
  v8 = 0;
  if ( *(_DWORD *)(a1 + 1248) != 3 )
  {
    if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      Default = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      WPP_RECORDER_SF_(Default, 3u, 2u, 0xAu, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids);
    }
    *(_BYTE *)(a3 + 3) = 5;
    goto LABEL_17;
  }
  if ( a4 )
  {
    v10 = *(_DWORD **)(a1 + 1224);
    if ( *v10 == 1 )
    {
      *v10 = 2;
      ++*(_DWORD *)(a1 + 1388);
      *a2 = 0;
      goto LABEL_24;
    }
    if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v11 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      WPP_RECORDER_SF_(v11, 3u, 2u, 0xBu, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids);
    }
    goto LABEL_16;
  }
  v12 = *(unsigned __int16 *)(a1 + 1232);
  if ( (unsigned __int16)v12 >= *(_WORD *)(a1 + 1280) )
  {
    if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v13 = *(unsigned __int16 *)(a1 + 1232);
      v14 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      WPP_RECORDER_SF_d(v14, 3u, 2u, 0xCu, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids, v13);
    }
LABEL_16:
    *(_WORD *)(a3 + 3) = 10244;
LABEL_17:
    v8 = -2147483631;
    goto LABEL_24;
  }
  v15 = *(_QWORD *)(a1 + 1224);
  *a2 = v12;
  *(_DWORD *)(v15 + 4 * v12) = 2;
  v16 = *(_WORD *)(a1 + 1280);
  ++*(_DWORD *)(a1 + 1388);
  *(_WORD *)(a1 + 1232) = v16;
  if ( v16 > 1u )
  {
    v17 = 1;
    while ( *(_DWORD *)(*(_QWORD *)(a1 + 1224) + 4LL * v17) != 1 )
    {
      if ( ++v17 >= v16 )
        goto LABEL_24;
    }
    *(_WORD *)(a1 + 1232) = v17;
  }
LABEL_24:
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  v18 = *(_DWORD *)(a1 + 1388);
  if ( v18 > *(_DWORD *)(a1 + 1392) )
    *(_DWORD *)(a1 + 1392) = v18;
  return v8;
}

```

## disassembly

```asm
0x140007cc0  push    rbx
0x140007cc2  push    rbp
0x140007cc3  push    rsi
0x140007cc4  push    rdi
0x140007cc5  push    r14
0x140007cc7  sub     rsp, 50h
0x140007ccb  mov     r14, rdx
0x140007cce  mov     rdi, rcx
0x140007cd1  xorps   xmm0, xmm0
0x140007cd4  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x140007cd9  xor     eax, eax
0x140007cdb  add     rcx, 4D8h; SpinLock
0x140007ce2  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x140007ce7  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x140007cec  mov     bpl, r9b
0x140007cef  mov     rsi, r8
0x140007cf2  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140007cf9  nop     dword ptr [rax+rax+00h]
0x140007cfe  xor     ebx, ebx
0x140007d00  cmp     dword ptr [rdi+4E0h], 3
0x140007d07  jz      short loc_140007D60
0x140007d09  cmp     cs:gTracingEnabled, bl
0x140007d0f  jz      short loc_140007D57
0x140007d11  lea     rax, WPP_RECORDER_INITIALIZED
0x140007d18  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007d1f  jz      short loc_140007D57
0x140007d21  mov     rcx, cs:WPP_GLOBAL_Control
0x140007d28  mov     ebx, 0Ah
0x140007d2d  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140007d34  nop     dword ptr [rax+rax+00h]
0x140007d39  movzx   r9d, bx
0x140007d3d  lea     r8d, [rbx-8]
0x140007d41  mov     rcx, rax
0x140007d44  mov     dl, 3
0x140007d46  lea     rax, WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids
0x140007d4d  mov     [rsp+78h+var_58], rax
0x140007d52  call    WPP_RECORDER_SF_
0x140007d57  mov     byte ptr [rsi+3], 5
0x140007d5b  jmp     loc_140007E4C
0x140007d60  test    bpl, bpl
0x140007d63  jz      short loc_140007DE2
0x140007d65  mov     rax, [rdi+4C8h]
0x140007d6c  mov     ecx, 1
0x140007d71  cmp     [rax], ecx
0x140007d73  jnz     short loc_140007D8A
0x140007d75  mov     dword ptr [rax], 2
0x140007d7b  add     [rdi+56Ch], ecx
0x140007d81  mov     [r14], bx
0x140007d85  jmp     loc_140007EAB
0x140007d8a  cmp     cs:gTracingEnabled, bl
0x140007d90  jz      loc_140007E46
0x140007d96  lea     rax, WPP_RECORDER_INITIALIZED
0x140007d9d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007da4  jz      loc_140007E46
0x140007daa  mov     rcx, cs:WPP_GLOBAL_Control
0x140007db1  mov     ebx, 0Bh
0x140007db6  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140007dbd  nop     dword ptr [rax+rax+00h]
0x140007dc2  movzx   r9d, bx
0x140007dc6  lea     r8d, [rbx-9]
0x140007dca  mov     rcx, rax
0x140007dcd  mov     dl, 3
0x140007dcf  lea     rax, WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids
0x140007dd6  mov     [rsp+78h+var_58], rax
0x140007ddb  call    WPP_RECORDER_SF_
0x140007de0  jmp     short loc_140007E46
0x140007de2  movzx   edx, word ptr [rdi+4D0h]
0x140007de9  cmp     dx, [rdi+500h]
0x140007df0  jb      short loc_140007E53
0x140007df2  cmp     cs:gTracingEnabled, bl
0x140007df8  jz      short loc_140007E46
0x140007dfa  lea     rax, WPP_RECORDER_INITIALIZED
0x140007e01  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007e08  jz      short loc_140007E46
0x140007e0a  mov     rcx, cs:WPP_GLOBAL_Control
0x140007e11  mov     ebx, edx
0x140007e13  mov     ebp, 0Ch
0x140007e18  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140007e1f  nop     dword ptr [rax+rax+00h]
0x140007e24  mov     [rsp+78h+var_50], ebx
0x140007e28  lea     r8d, [rbp-0Ah]
0x140007e2c  mov     rcx, rax
0x140007e2f  movzx   r9d, bp
0x140007e33  lea     rax, WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids
0x140007e3a  mov     dl, 3
0x140007e3c  mov     [rsp+78h+var_58], rax
0x140007e41  call    WPP_RECORDER_SF_d
0x140007e46  mov     word ptr [rsi+3], 2804h
0x140007e4c  mov     ebx, 80000011h
0x140007e51  jmp     short loc_140007EAB
0x140007e53  mov     rax, [rdi+4C8h]
0x140007e5a  mov     ecx, 1
0x140007e5f  mov     [r14], dx
0x140007e63  mov     dword ptr [rax+rdx*4], 2
0x140007e6a  movzx   r8d, word ptr [rdi+500h]
0x140007e72  add     [rdi+56Ch], ecx
0x140007e78  mov     [rdi+4D0h], r8w
0x140007e80  cmp     cx, r8w
0x140007e84  jnb     short loc_140007EAB
0x140007e86  mov     r9, [rdi+4C8h]
0x140007e8d  movzx   edx, cx
0x140007e90  movzx   eax, dx
0x140007e93  cmp     [r9+rax*4], ecx
0x140007e97  jz      short loc_140007EA4
0x140007e99  add     dx, cx
0x140007e9c  cmp     dx, r8w
0x140007ea0  jb      short loc_140007E90
0x140007ea2  jmp     short loc_140007EAB
0x140007ea4  mov     [rdi+4D0h], dx
0x140007eab  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x140007eb0  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140007eb7  nop     dword ptr [rax+rax+00h]
0x140007ebc  mov     eax, [rdi+56Ch]
0x140007ec2  cmp     eax, [rdi+570h]
0x140007ec8  jbe     short loc_140007ED0
0x140007eca  mov     [rdi+570h], eax
0x140007ed0  mov     eax, ebx
0x140007ed2  add     rsp, 50h
0x140007ed6  pop     r14
0x140007ed8  pop     rdi
0x140007ed9  pop     rsi
0x140007eda  pop     rbp
0x140007edb  pop     rbx
0x140007edc  retn
```
