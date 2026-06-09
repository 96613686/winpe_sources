# BthUsb_ScoUrbStart(_DEVICE_EXTENSION *,_SCO_USB_PIPE_OBJ *,_SCO_USB_TRANSFER_CTX *)

- ea: `0x140005c8c`
- end: `0x140005f5a`
- name: `?BthUsb_ScoUrbStart@@YAJPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_PIPE_OBJ@@PEAU_SCO_USB_TRANSFER_CTX@@@Z`
- size: `718`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _SCO_USB_PIPE_OBJ *, struct _SCO_USB_TRANSFER_CTX *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140007c5c`
- `0x1400094f8`

## callees

- `0x1400017d4`
- `0x140005c8c`
- `0x140006638`
- `0x1400067e8`
- `0x140006abc`
- `0x14000de00`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140005cf5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005f18`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005cf5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005f18`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005cb5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005de3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005cb5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005de3`

## pseudocode

```c
__int64 __fastcall BthUsb_ScoUrbStart(
        struct _DEVICE_EXTENSION *a1,
        struct _SCO_USB_PIPE_OBJ *a2,
        struct _SCO_USB_TRANSFER_CTX *a3)
{
  unsigned int Reserved; // r15d
  KIRQL v7; // al
  bool v8; // zf
  KIRQL v9; // r12
  unsigned int NextStartFrame; // eax
  unsigned int v11; // ebp
  unsigned __int16 *p_Id; // rsi
  int *p_InProgressUrbs; // rdi
  int v14; // r15d
  int (__fastcall *QueryBusTime)(void *, unsigned int *); // rax
  void *BusContext; // rcx
  int v17; // edx
  int v18; // r8d
  int v19; // edi
  int v20; // edx
  int v21; // r8d
  int v22; // edx
  int InProgressUrbs; // r9d
  unsigned int v24; // r12d
  unsigned int v25; // r8d
  const ScoUsbAltSetting *p_MAX_PENDING_READ_REQS_SPAN; // rax
  unsigned int v27; // eax
  int v28; // edx
  _LIST_ENTRY *Blink; // rdx
  int v31; // [rsp+20h] [rbp-88h]
  int v32; // [rsp+28h] [rbp-80h]
  int v33; // [rsp+28h] [rbp-80h]
  int v34; // [rsp+30h] [rbp-78h]
  int v35; // [rsp+38h] [rbp-70h]
  int v36; // [rsp+38h] [rbp-70h]
  int v37; // [rsp+B8h] [rbp+10h] BYREF
  unsigned int v38; // [rsp+C0h] [rbp+18h]

  Reserved = a3->Urb->UrbPipeRequest.Reserved;
  v7 = KeAcquireSpinLockRaiseToDpc(&a2->Lock);
  v8 = a2->fNextStartFrame == 0;
  v9 = v7;
  NextStartFrame = a2->NextStartFrame;
  v38 = NextStartFrame;
  if ( v8 )
  {
    v14 = Reserved & 1;
    KeReleaseSpinLock(&a2->Lock, v9);
    QueryBusTime = a1->Sco.UsbBusInterface.QueryBusTime;
    BusContext = a1->Sco.UsbBusInterface.BusContext;
    v37 = 0;
    v18 = QueryBusTime(BusContext, (unsigned int *)&v37);
    if ( v18 < 0 )
    {
      v19 = 0;
      LOBYTE(v17) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      WPP_RECORDER_AND_TRACE_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        v17,
        v18,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        5,
        33,
        (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
        v18);
    }
    else
    {
      v19 = v37;
    }
    p_Id = &a2->Id;
    v11 = a2->FnAlignFrame(a1, a3, a2->Id, v19 + 4);
    LOBYTE(v20) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    WPP_RECORDER_AND_TRACE_SF_LLLL(
      WPP_GLOBAL_Control->AttachedDevice,
      v20,
      v21,
      WPP_GLOBAL_Control->DeviceExtension,
      v31,
      v32,
      96,
      v35,
      v14,
      v19,
      v19 + 4,
      v11);
    p_InProgressUrbs = &a2->InProgressUrbs;
    LOBYTE(v37) = KeAcquireSpinLockRaiseToDpc(&a2->Lock);
    InProgressUrbs = a2->InProgressUrbs;
    v9 = v37;
    if ( InProgressUrbs > 0 )
    {
      v24 = v38;
      v25 = 1000 * (v38 - v11);
      p_MAX_PENDING_READ_REQS_SPAN = (const ScoUsbAltSetting *)&a1->Sco.UsbAltSetting->MAX_PENDING_READ_REQS_SPAN;
      if ( !v14 )
        p_MAX_PENDING_READ_REQS_SPAN = a1->Sco.UsbAltSetting;
      if ( v25 <= p_MAX_PENDING_READ_REQS_SPAN->MAX_PENDING_WRITE_REQS_SPAN )
      {
        LOBYTE(v22) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        WPP_RECORDER_AND_TRACE_SF_LdLLL(
          WPP_GLOBAL_Control->AttachedDevice,
          v22,
          v25,
          WPP_GLOBAL_Control->DeviceExtension,
          v31,
          v33,
          v34,
          v36,
          v14,
          InProgressUrbs,
          v38,
          v11,
          -24 * (v38 - v11));
        v11 = v24;
      }
      v9 = v37;
    }
  }
  else
  {
    v11 = NextStartFrame;
    p_Id = &a2->Id;
    p_InProgressUrbs = &a2->InProgressUrbs;
  }
  v27 = a2->FnGetNextFrame(a1, a3, *p_Id, v11);
  a2->NextStartFrame = v27;
  LOBYTE(v28) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_LL(
    WPP_GLOBAL_Control->AttachedDevice,
    v28,
    (_DWORD)WPP_GLOBAL_Control,
    WPP_GLOBAL_Control->DeviceExtension,
    v31,
    5,
    98,
    (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
    v11,
    v27);
  a2->fNextStartFrame = 1;
  a3->Flags |= 1u;
  Blink = a2->InProgressUrbsHead.Blink;
  if ( Blink->Flink != &a2->InProgressUrbsHead )
    __fastfail(3u);
  a3->ListEntry.Flink = &a2->InProgressUrbsHead;
  a3->ListEntry.Blink = Blink;
  Blink->Flink = &a3->ListEntry;
  a2->InProgressUrbsHead.Blink = &a3->ListEntry;
  ++*p_InProgressUrbs;
  KeReleaseSpinLock(&a2->Lock, v9);
  a3->Urb->UrbIsochronousTransfer.StartFrame = v11;
  a2->FnSendUrb(a1, a3);
  return 259;
}

```

## disassembly

```asm
0x140005c8c  mov     [rsp+arg_0], rbx
0x140005c91  push    rbp
0x140005c92  push    rsi
0x140005c93  push    rdi
0x140005c94  push    r12
0x140005c96  push    r13
0x140005c98  push    r14
0x140005c9a  push    r15
0x140005c9c  sub     rsp, 70h
0x140005ca0  mov     rax, [r8+48h]
0x140005ca4  mov     r13, rcx
0x140005ca7  lea     rcx, [rdx+28h]; SpinLock
0x140005cab  mov     r14, r8
0x140005cae  mov     rbx, rdx
0x140005cb1  mov     r15d, [rax+20h]
0x140005cb5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005cbc  nop     dword ptr [rax+rax+00h]
0x140005cc1  cmp     byte ptr [rbx+4Ch], 0
0x140005cc5  lea     rsi, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x140005ccc  mov     r12b, al
0x140005ccf  mov     eax, [rbx+48h]
0x140005cd2  mov     [rsp+0A8h+arg_10], eax
0x140005cd9  jz      short loc_140005CEA
0x140005cdb  mov     ebp, eax
0x140005cdd  lea     rsi, [rbx+24h]
0x140005ce1  lea     rdi, [rbx+34h]
0x140005ce5  jmp     loc_140005E7A
0x140005cea  mov     dl, r12b; NewIrql
0x140005ced  lea     rcx, [rbx+28h]; SpinLock
0x140005cf1  and     r15d, 1
0x140005cf5  call    cs:__imp_KeReleaseSpinLock
0x140005cfc  nop     dword ptr [rax+rax+00h]
0x140005d01  mov     rax, [r13+118h]
0x140005d08  lea     rdx, [rsp+0A8h+arg_8]
0x140005d10  mov     rcx, [r13+0F8h]
0x140005d17  mov     [rsp+0A8h+arg_8], 0
0x140005d22  call    _guard_dispatch_icall
0x140005d27  mov     r8d, eax
0x140005d2a  test    eax, eax
0x140005d2c  js      short loc_140005D37
0x140005d2e  mov     edi, [rsp+0A8h+arg_8]
0x140005d35  jmp     short loc_140005D7E
0x140005d37  xor     edi, edi
0x140005d39  mov     rcx, cs:WPP_GLOBAL_Control
0x140005d40  mov     eax, [rcx+2Ch]
0x140005d43  test    al, 10h
0x140005d45  jz      short loc_140005D51
0x140005d47  cmp     byte ptr [rcx+29h], 2
0x140005d4b  jb      short loc_140005D51
0x140005d4d  mov     dl, 1
0x140005d4f  jmp     short loc_140005D53
0x140005d51  xor     dl, dl
0x140005d53  mov     r9, [rcx+40h]
0x140005d57  mov     rcx, [rcx+18h]
0x140005d5b  mov     [rsp+0A8h+var_68], r8d
0x140005d60  mov     [rsp+0A8h+var_70], rsi
0x140005d65  mov     [rsp+0A8h+var_78], 21h ; '!'
0x140005d6c  mov     [rsp+0A8h+var_80], 5
0x140005d74  mov     [rsp+0A8h+var_88], 2
0x140005d79  call    WPP_RECORDER_AND_TRACE_SF_D
0x140005d7e  mov     rax, [rbx+10h]
0x140005d82  lea     r12d, [rdi+4]
0x140005d86  lea     rsi, [rbx+24h]
0x140005d8a  mov     r9d, r12d
0x140005d8d  movzx   r8d, word ptr [rsi]
0x140005d91  mov     rdx, r14
0x140005d94  mov     rcx, r13
0x140005d97  call    _guard_dispatch_icall
0x140005d9c  mov     ebp, eax
0x140005d9e  mov     rax, cs:WPP_GLOBAL_Control
0x140005da5  mov     ecx, [rax+2Ch]
0x140005da8  test    cl, 8
0x140005dab  jz      short loc_140005DB7
0x140005dad  cmp     byte ptr [rax+29h], 4
0x140005db1  jb      short loc_140005DB7
0x140005db3  mov     dl, 1
0x140005db5  jmp     short loc_140005DB9
0x140005db7  xor     dl, dl
0x140005db9  mov     r9, [rax+40h]
0x140005dbd  mov     rcx, [rax+18h]
0x140005dc1  mov     [rsp+0A8h+var_50], ebp
0x140005dc5  mov     [rsp+0A8h+var_58], r12d
0x140005dca  mov     [rsp+0A8h+var_60], edi
0x140005dce  mov     [rsp+0A8h+var_68], r15d
0x140005dd3  mov     [rsp+0A8h+var_78], 60h ; '`'
0x140005dda  call    WPP_RECORDER_AND_TRACE_SF_LLLL
0x140005ddf  lea     rcx, [rbx+28h]; SpinLock
0x140005de3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005dea  nop     dword ptr [rax+rax+00h]
0x140005def  lea     rdi, [rbx+34h]
0x140005df3  mov     byte ptr [rsp+0A8h+arg_8], al
0x140005dfa  mov     r9d, [rdi]
0x140005dfd  mov     r12b, al
0x140005e00  test    r9d, r9d
0x140005e03  jle     short loc_140005E7A
0x140005e05  mov     rcx, [r13+478h]
0x140005e0c  mov     r12d, [rsp+0A8h+arg_10]
0x140005e14  mov     eax, r12d
0x140005e17  sub     eax, ebp
0x140005e19  imul    r8d, eax, 3E8h
0x140005e20  test    r15d, r15d
0x140005e23  lea     rax, [rcx+4]
0x140005e27  cmovz   rax, rcx
0x140005e2b  cmp     r8d, [rax]
0x140005e2e  ja      short loc_140005E72
0x140005e30  mov     rcx, cs:WPP_GLOBAL_Control
0x140005e37  mov     eax, [rcx+2Ch]
0x140005e3a  test    al, 8
0x140005e3c  jz      short loc_140005E48
0x140005e3e  cmp     byte ptr [rcx+29h], 4
0x140005e42  jb      short loc_140005E48
0x140005e44  mov     dl, 1
0x140005e46  jmp     short loc_140005E4A
0x140005e48  xor     dl, dl
0x140005e4a  mov     [rsp+0A8h+var_48], r8d
0x140005e4f  mov     [rsp+0A8h+var_50], ebp
0x140005e53  mov     [rsp+0A8h+var_58], r12d
0x140005e58  mov     [rsp+0A8h+var_60], r9d
0x140005e5d  mov     r9, [rcx+40h]
0x140005e61  mov     rcx, [rcx+18h]
0x140005e65  mov     [rsp+0A8h+var_68], r15d
0x140005e6a  call    WPP_RECORDER_AND_TRACE_SF_LdLLL
0x140005e6f  mov     ebp, r12d
0x140005e72  mov     r12b, byte ptr [rsp+0A8h+arg_8]
0x140005e7a  mov     rax, [rbx+18h]
0x140005e7e  mov     r9d, ebp
0x140005e81  movzx   r8d, word ptr [rsi]
0x140005e85  mov     rdx, r14
0x140005e88  mov     rcx, r13
0x140005e8b  call    _guard_dispatch_icall
0x140005e90  mov     [rbx+48h], eax
0x140005e93  mov     r8, cs:WPP_GLOBAL_Control
0x140005e9a  mov     ecx, [r8+2Ch]
0x140005e9e  test    cl, 10h
0x140005ea1  jz      short loc_140005EAE
0x140005ea3  cmp     byte ptr [r8+29h], 4
0x140005ea8  jb      short loc_140005EAE
0x140005eaa  mov     dl, 1
0x140005eac  jmp     short loc_140005EB0
0x140005eae  xor     dl, dl
0x140005eb0  mov     r9, [r8+40h]
0x140005eb4  mov     rcx, [r8+18h]
0x140005eb8  mov     [rsp+0A8h+var_60], eax
0x140005ebc  lea     rax, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x140005ec3  mov     [rsp+0A8h+var_68], ebp
0x140005ec7  mov     [rsp+0A8h+var_70], rax
0x140005ecc  mov     [rsp+0A8h+var_78], 62h ; 'b'
0x140005ed3  mov     [rsp+0A8h+var_80], 5
0x140005edb  call    WPP_RECORDER_AND_TRACE_SF_LL
0x140005ee0  mov     byte ptr [rbx+4Ch], 1
0x140005ee4  lea     rcx, [rbx+38h]
0x140005ee8  or      dword ptr [r14+5Ch], 1
0x140005eed  mov     rdx, [rcx+8]
0x140005ef1  cmp     [rdx], rcx
0x140005ef4  jz      short loc_140005EFD
0x140005ef6  mov     ecx, 3
0x140005efb  int     29h; Win8: RtlFailFast(ecx)
0x140005efd  lea     rax, [r14+28h]
0x140005f01  mov     [rax], rcx
0x140005f04  mov     [rax+8], rdx
0x140005f08  mov     [rdx], rax
0x140005f0b  mov     dl, r12b; NewIrql
0x140005f0e  mov     [rcx+8], rax
0x140005f12  lea     rcx, [rbx+28h]; SpinLock
0x140005f16  inc     dword ptr [rdi]
0x140005f18  call    cs:__imp_KeReleaseSpinLock
0x140005f1f  nop     dword ptr [rax+rax+00h]
0x140005f24  mov     rax, [r14+48h]
0x140005f28  mov     rdx, r14
0x140005f2b  mov     rcx, r13
0x140005f2e  mov     [rax+80h], ebp
0x140005f34  mov     rax, [rbx]
0x140005f37  call    _guard_dispatch_icall
0x140005f3c  mov     rbx, [rsp+0A8h+arg_0]
0x140005f44  mov     eax, 103h
0x140005f49  add     rsp, 70h
0x140005f4d  pop     r15
0x140005f4f  pop     r14
0x140005f51  pop     r13
0x140005f53  pop     r12
0x140005f55  pop     rdi
0x140005f56  pop     rsi
0x140005f57  pop     rbp
0x140005f58  retn
```
