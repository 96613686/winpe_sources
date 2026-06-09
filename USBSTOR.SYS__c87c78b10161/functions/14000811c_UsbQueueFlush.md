# UsbQueueFlush

- ea: `0x14000811c`
- end: `0x14000827f`
- name: `UsbQueueFlush`
- size: `355`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140023f70`
- `0x14002877c`

## callees

- `0x140006910`
- `0x14000811c`
- `0x14000f39c`
- `0x140010664`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140008178`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140008178`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000819c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000819c`

## pseudocode

```c
__int64 __fastcall UsbQueueFlush(__int64 a1, __int64 a2)
{
  __int128 *v4; // rdx
  _QWORD *v5; // r8
  _QWORD *v6; // rax
  __int64 v7; // rdx
  __int64 result; // rax
  __int64 v9; // rax
  _QWORD *v10; // rcx
  _QWORD *v11; // rax
  __int128 v12; // [rsp+20h] [rbp-38h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-28h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  v12 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x1Du,
      (__int64)WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids);
  }
  *((_QWORD *)&v12 + 1) = &v12;
  *(_QWORD *)&v12 = &v12;
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a2 + 288), &LockHandle);
  *(_BYTE *)(a2 + 304) = 0;
  while ( 1 )
  {
    v6 = UsbDequeueIrp(a2, v4, v5);
    if ( !v6 )
      break;
    v10 = (_QWORD *)*((_QWORD *)&v12 + 1);
    if ( **((__int128 ***)&v12 + 1) != &v12 )
LABEL_15:
      __fastfail(3u);
    v11 = v6 + 21;
    v4 = &v12;
    *v11 = &v12;
    v11[1] = v10;
    *v10 = v11;
    *((_QWORD *)&v12 + 1) = v11;
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  while ( 1 )
  {
    v7 = v12;
    result = (__int64)&v12;
    if ( (__int128 *)v12 == &v12 )
      break;
    if ( *(__int128 **)(v12 + 8) != &v12 )
      goto LABEL_15;
    v9 = *(_QWORD *)v12;
    if ( *(_QWORD *)(*(_QWORD *)v12 + 8LL) != (_QWORD)v12 )
      goto LABEL_15;
    *(_QWORD *)&v12 = *(_QWORD *)v12;
    *(_QWORD *)(v9 + 8) = &v12;
    UsbCompleteFlushedIrp(a1, (IRP *)(v7 - 168));
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      return WPP_SF_(
               (__int64)WPP_GLOBAL_Control->AttachedDevice,
               0x1Eu,
               (__int64)WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x14000811c  push    rbp
0x14000811e  push    rbx
0x14000811f  push    rsi
0x140008120  push    rdi
0x140008121  mov     rbp, rsp
0x140008124  sub     rsp, 58h
0x140008128  xorps   xmm0, xmm0
0x14000812b  xor     eax, eax
0x14000812d  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x140008131  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140008135  mov     rbx, rdx
0x140008138  movups  [rbp+var_38], xmm0
0x14000813c  mov     rdi, rcx
0x14000813f  mov     rcx, cs:WPP_GLOBAL_Control
0x140008146  lea     rsi, WPP_GLOBAL_Control
0x14000814d  cmp     rcx, rsi
0x140008150  jz      short loc_14000815D
0x140008152  mov     eax, [rcx+2Ch]
0x140008155  test    al, 20h
0x140008157  jnz     loc_140008237
0x14000815d  lea     rax, [rbp+var_38]
0x140008161  mov     qword ptr [rbp+var_38+8], rax
0x140008165  lea     rcx, [rbx+120h]; SpinLock
0x14000816c  lea     rax, [rbp+var_38]
0x140008170  lea     rdx, [rbp+LockHandle]; LockHandle
0x140008174  mov     qword ptr [rbp+var_38], rax
0x140008178  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000817f  nop     dword ptr [rax+rax+00h]
0x140008184  mov     byte ptr [rbx+130h], 0
0x14000818b  mov     rcx, rbx
0x14000818e  call    UsbDequeueIrp
0x140008193  test    rax, rax
0x140008196  jnz     short loc_140008206
0x140008198  lea     rcx, [rbp+LockHandle]; LockHandle
0x14000819c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400081a3  nop     dword ptr [rax+rax+00h]
0x1400081a8  mov     rdx, qword ptr [rbp+var_38]
0x1400081ac  lea     rax, [rbp+var_38]
0x1400081b0  cmp     rdx, rax
0x1400081b3  jnz     short loc_1400081D6
0x1400081b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400081bc  cmp     rcx, rsi
0x1400081bf  jz      short loc_1400081CC
0x1400081c1  mov     eax, [rcx+2Ch]
0x1400081c4  test    al, 20h
0x1400081c6  jnz     loc_14000825B
0x1400081cc  add     rsp, 58h
0x1400081d0  pop     rdi
0x1400081d1  pop     rsi
0x1400081d2  pop     rbx
0x1400081d3  pop     rbp
0x1400081d4  retn
0x1400081d6  lea     rax, [rbp+var_38]
0x1400081da  cmp     [rdx+8], rax
0x1400081de  jnz     short loc_140008230
0x1400081e0  mov     rax, [rdx]
0x1400081e3  cmp     [rax+8], rdx
0x1400081e7  jnz     short loc_140008230
0x1400081e9  lea     rcx, [rbp+var_38]
0x1400081ed  mov     qword ptr [rbp+var_38], rax
0x1400081f1  mov     [rax+8], rcx
0x1400081f5  add     rdx, 0FFFFFFFFFFFFFF58h
0x1400081fc  mov     rcx, rdi
0x1400081ff  call    UsbCompleteFlushedIrp
0x140008204  jmp     short loc_1400081A8
0x140008206  mov     rcx, qword ptr [rbp+var_38+8]
0x14000820a  lea     rdx, [rbp+var_38]
0x14000820e  cmp     [rcx], rdx
0x140008211  jnz     short loc_140008230
0x140008213  add     rax, 0A8h
0x140008219  lea     rdx, [rbp+var_38]
0x14000821d  mov     [rax], rdx
0x140008220  mov     [rax+8], rcx
0x140008224  mov     [rcx], rax
0x140008227  mov     qword ptr [rbp+var_38+8], rax
0x14000822b  jmp     loc_14000818B
0x140008230  mov     ecx, 3
0x140008235  int     29h; Win8: RtlFailFast(ecx)
0x140008237  cmp     byte ptr [rcx+29h], 4
0x14000823b  jb      loc_14000815D
0x140008241  mov     rcx, [rcx+18h]
0x140008245  lea     r8, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids
0x14000824c  mov     edx, 1Dh
0x140008251  call    WPP_SF_
0x140008256  jmp     loc_14000815D
0x14000825b  cmp     byte ptr [rcx+29h], 4
0x14000825f  jb      loc_1400081CC
0x140008265  mov     rcx, [rcx+18h]
0x140008269  lea     r8, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids
0x140008270  mov     edx, 1Eh
0x140008275  call    WPP_SF_
0x14000827a  jmp     loc_1400081CC
```
