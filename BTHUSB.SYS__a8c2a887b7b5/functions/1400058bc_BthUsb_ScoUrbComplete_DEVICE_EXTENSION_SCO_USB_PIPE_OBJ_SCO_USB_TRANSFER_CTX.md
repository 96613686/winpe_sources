# BthUsb_ScoUrbComplete(_DEVICE_EXTENSION *,_SCO_USB_PIPE_OBJ *,_SCO_USB_TRANSFER_CTX *)

- ea: `0x1400058bc`
- end: `0x140005be0`
- name: `?BthUsb_ScoUrbComplete@@YAXPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_PIPE_OBJ@@PEAU_SCO_USB_TRANSFER_CTX@@@Z`
- size: `804`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *, struct _SCO_USB_PIPE_OBJ *, struct _SCO_USB_TRANSFER_CTX *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140008120`
- `0x140009a10`

## callees

- `0x1400058bc`
- `0x140005be8`
- `0x1400068e8`
- `0x1400069ac`
- `0x14000de00`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140005911`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005b8a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005911`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005b8a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400058ed`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005bb6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400058ed`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005bb6`

## pseudocode

```c
void __fastcall BthUsb_ScoUrbComplete(
        struct _DEVICE_EXTENSION *a1,
        struct _SCO_USB_PIPE_OBJ *a2,
        struct _SCO_USB_TRANSFER_CTX *a3)
{
  _URB *Urb; // r13
  unsigned __int64 *p_Lock; // r12
  KIRQL v7; // al
  int v8; // r8d
  unsigned int Flags; // edx
  _LIST_ENTRY *p_InProgressUrbsHead; // r14
  char v11; // r10
  unsigned int v12; // edx
  __int64 v13; // r15
  _LIST_ENTRY *Flink; // rbx
  _SCO_USB_TRANSFER_CTX *p_Blink; // rsi
  _LIST_ENTRY *v16; // rax
  _LIST_ENTRY *v17; // rbp
  unsigned int v18; // edx
  _LIST_ENTRY *v19; // rax
  unsigned int StartFrame; // r8d
  unsigned int v21; // r9d
  int v23; // edx
  int v24; // r8d
  KIRQL v25; // al
  int v26; // [rsp+20h] [rbp-88h]
  int v27; // [rsp+28h] [rbp-80h]
  int v28; // [rsp+30h] [rbp-78h]
  int v29; // [rsp+38h] [rbp-70h]
  KIRQL NewIrql; // [rsp+B8h] [rbp+10h]
  unsigned int Reserved; // [rsp+C0h] [rbp+18h]
  char v33; // [rsp+C0h] [rbp+18h]

  Urb = a3->Urb;
  p_Lock = &a2->Lock;
  Reserved = Urb->UrbPipeRequest.Reserved;
  v7 = KeAcquireSpinLockRaiseToDpc(&a2->Lock);
  a3->Flags &= ~1u;
  Flags = a2->Flags;
  NewIrql = v7;
  if ( (Flags & 1) == 0 )
  {
    p_InProgressUrbsHead = &a2->InProgressUrbsHead;
    v11 = Reserved & 1;
    v12 = Flags | 1;
    v33 = Reserved & 1;
    v13 = 0;
    a2->Flags = v12;
    while ( 1 )
    {
      Flink = p_InProgressUrbsHead->Flink;
      if ( p_InProgressUrbsHead->Flink == p_InProgressUrbsHead )
        break;
      if ( Flink->Blink != p_InProgressUrbsHead )
        goto LABEL_46;
      v16 = Flink->Flink;
      if ( Flink->Flink->Blink != Flink )
        goto LABEL_46;
      p_InProgressUrbsHead->Flink = v16;
      p_Blink = (_SCO_USB_TRANSFER_CTX *)&Flink[-3].Blink;
      v16->Blink = p_InProgressUrbsHead;
      v17 = Flink[2].Flink;
      if ( (HIDWORD(Flink[3].Flink) & 1) != 0 )
      {
        v18 = (unsigned int)v17[8].Flink;
        if ( !v13 || v18 <= Urb->UrbIsochronousTransfer.StartFrame )
        {
          LOBYTE(v8) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
          LOBYTE(v18) = v8;
          WPP_RECORDER_AND_TRACE_SF_LPLL(
            WPP_GLOBAL_Control->AttachedDevice,
            v18,
            v8,
            WPP_GLOBAL_Control->DeviceExtension,
            3,
            v27,
            99,
            v29,
            v11,
            v13,
            (char)v17[8].Flink,
            Urb->UrbIsochronousTransfer.StartFrame);
        }
        v19 = p_InProgressUrbsHead->Flink;
        if ( p_InProgressUrbsHead->Flink->Blink != p_InProgressUrbsHead )
LABEL_46:
          __fastfail(3u);
        Flink->Flink = v19;
        p_Blink = 0;
        Flink->Blink = p_InProgressUrbsHead;
        v19->Blink = Flink;
        p_InProgressUrbsHead->Flink = Flink;
        goto LABEL_43;
      }
      StartFrame = Urb->UrbIsochronousTransfer.StartFrame;
      v21 = (unsigned int)v17[8].Flink;
      if ( v21 > StartFrame )
      {
        LOBYTE(v12) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
        WPP_RECORDER_AND_TRACE_SF_LPLL(
          WPP_GLOBAL_Control->AttachedDevice,
          v12,
          StartFrame,
          WPP_GLOBAL_Control->DeviceExtension,
          3,
          v27,
          100,
          v29,
          v11,
          v13,
          v21,
          Urb->UrbIsochronousTransfer.StartFrame);
        v11 = v33;
      }
      if ( a2->InProgressUrbs-- == 1 )
      {
        LOBYTE(v12) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        WPP_RECORDER_AND_TRACE_SF_LPLL(
          WPP_GLOBAL_Control->AttachedDevice,
          v12,
          StartFrame,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          v27,
          101,
          v29,
          v11,
          v13,
          (char)v17[8].Flink,
          Urb->UrbIsochronousTransfer.StartFrame);
        a2->fNextStartFrame = 0;
      }
      if ( BthUsb_ScoUrbError((struct _SCO_USB_TRANSFER_CTX *)&Flink[-3].Blink, a2->PipeType) && a2->fNextStartFrame )
      {
        LOBYTE(v23) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
        WPP_RECORDER_AND_TRACE_SF_LPLL(
          WPP_GLOBAL_Control->AttachedDevice,
          v23,
          v24,
          WPP_GLOBAL_Control->DeviceExtension,
          3,
          v27,
          102,
          v29,
          v33,
          v13,
          (char)v17[8].Flink,
          Urb->UrbIsochronousTransfer.StartFrame);
        a2->fNextStartFrame = 0;
      }
      if ( Flink == (_LIST_ENTRY *)40 )
        goto LABEL_43;
LABEL_44:
      KeReleaseSpinLock(p_Lock, NewIrql);
      if ( !p_Blink )
        return;
      a2->FnCompleteUrb(a1, p_Blink);
      v25 = KeAcquireSpinLockRaiseToDpc(p_Lock);
      v11 = v33;
      ++v13;
      NewIrql = v25;
    }
    p_Blink = 0;
    LOBYTE(v12) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    WPP_RECORDER_AND_TRACE_SF_LP(
      WPP_GLOBAL_Control->AttachedDevice,
      v12,
      v8,
      WPP_GLOBAL_Control->DeviceExtension,
      v26,
      v27,
      v28,
      v29,
      v11,
      v13);
LABEL_43:
    a2->Flags &= ~1u;
    goto LABEL_44;
  }
  KeReleaseSpinLock(p_Lock, v7);
}

```

## disassembly

```asm
0x1400058bc  mov     [rsp+arg_0], rcx
0x1400058c1  push    rbx
0x1400058c2  push    rbp
0x1400058c3  push    rsi
0x1400058c4  push    rdi
0x1400058c5  push    r12
0x1400058c7  push    r13
0x1400058c9  push    r14
0x1400058cb  push    r15
0x1400058cd  sub     rsp, 68h
0x1400058d1  mov     r13, [r8+48h]
0x1400058d5  lea     r12, [rdx+28h]
0x1400058d9  mov     rcx, r12; SpinLock
0x1400058dc  mov     rbx, r8
0x1400058df  mov     rdi, rdx
0x1400058e2  mov     eax, [r13+20h]
0x1400058e6  mov     [rsp+0A8h+arg_10], eax
0x1400058ed  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400058f4  nop     dword ptr [rax+rax+00h]
0x1400058f9  and     dword ptr [rbx+5Ch], 0FFFFFFFEh
0x1400058fd  mov     edx, [rdi+30h]
0x140005900  mov     [rsp+0A8h+NewIrql], al
0x140005907  test    dl, 1
0x14000590a  jz      short loc_14000592F
0x14000590c  mov     dl, al; NewIrql
0x14000590e  mov     rcx, r12; SpinLock
0x140005911  call    cs:__imp_KeReleaseSpinLock
0x140005918  nop     dword ptr [rax+rax+00h]
0x14000591d  add     rsp, 68h
0x140005921  pop     r15
0x140005923  pop     r14
0x140005925  pop     r13
0x140005927  pop     r12
0x140005929  pop     rdi
0x14000592a  pop     rsi
0x14000592b  pop     rbp
0x14000592c  pop     rbx
0x14000592d  retn
0x14000592f  mov     r10d, [rsp+0A8h+arg_10]
0x140005937  lea     r14, [rdi+38h]
0x14000593b  and     r10d, 1
0x14000593f  or      edx, 1
0x140005942  mov     [rsp+0A8h+arg_10], r10d
0x14000594a  xor     r15d, r15d
0x14000594d  mov     [rdi+30h], edx
0x140005950  mov     rbx, [r14]
0x140005953  cmp     rbx, r14
0x140005956  jnz     short loc_140005990
0x140005958  xor     esi, esi
0x14000595a  mov     rcx, cs:WPP_GLOBAL_Control
0x140005961  mov     eax, [rcx+2Ch]
0x140005964  test    al, 10h
0x140005966  jz      short loc_140005972
0x140005968  cmp     byte ptr [rcx+29h], 4
0x14000596c  jb      short loc_140005972
0x14000596e  mov     dl, 1
0x140005970  jmp     short loc_140005974
0x140005972  xor     dl, dl
0x140005974  mov     r9, [rcx+40h]
0x140005978  mov     rcx, [rcx+18h]
0x14000597c  mov     [rsp+0A8h+var_60], r15
0x140005981  mov     [rsp+0A8h+var_68], r10d
0x140005986  call    WPP_RECORDER_AND_TRACE_SF_LP
0x14000598b  jmp     loc_140005B7C
0x140005990  cmp     [rbx+8], r14
0x140005994  jnz     loc_140005BD9
0x14000599a  mov     rax, [rbx]
0x14000599d  cmp     [rax+8], rbx
0x1400059a1  jnz     loc_140005BD9
0x1400059a7  mov     [r14], rax
0x1400059aa  lea     rsi, [rbx-28h]
0x1400059ae  mov     [rax+8], r14
0x1400059b2  mov     eax, [rsi+5Ch]
0x1400059b5  mov     rbp, [rsi+48h]
0x1400059b9  test    al, 1
0x1400059bb  jz      loc_140005A48
0x1400059c1  mov     edx, [rbp+80h]
0x1400059c7  test    r15, r15
0x1400059ca  jz      short loc_1400059D5
0x1400059cc  cmp     edx, [r13+80h]
0x1400059d3  ja      short loc_140005A26
0x1400059d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400059dc  mov     eax, [rcx+2Ch]
0x1400059df  test    al, 10h
0x1400059e1  jz      short loc_1400059EE
0x1400059e3  cmp     byte ptr [rcx+29h], 3
0x1400059e7  jb      short loc_1400059EE
0x1400059e9  mov     r8b, 1
0x1400059ec  jmp     short loc_1400059F1
0x1400059ee  xor     r8b, r8b
0x1400059f1  mov     eax, [r13+80h]
0x1400059f8  mov     r9, [rcx+40h]
0x1400059fc  mov     rcx, [rcx+18h]
0x140005a00  mov     [rsp+0A8h+var_50], eax
0x140005a04  mov     [rsp+0A8h+var_58], edx
0x140005a08  mov     dl, r8b
0x140005a0b  mov     [rsp+0A8h+var_60], r15
0x140005a10  mov     [rsp+0A8h+var_68], r10d
0x140005a15  mov     [rsp+0A8h+var_78], 63h ; 'c'
0x140005a1c  mov     [rsp+0A8h+var_88], 3
0x140005a21  call    WPP_RECORDER_AND_TRACE_SF_LPLL
0x140005a26  mov     rax, [r14]
0x140005a29  cmp     [rax+8], r14
0x140005a2d  jnz     loc_140005BD9
0x140005a33  mov     [rbx], rax
0x140005a36  xor     esi, esi
0x140005a38  mov     [rbx+8], r14
0x140005a3c  mov     [rax+8], rbx
0x140005a40  mov     [r14], rbx
0x140005a43  jmp     loc_140005B7C
0x140005a48  mov     r8d, [r13+80h]
0x140005a4f  mov     r9d, [rbp+80h]
0x140005a56  cmp     r9d, r8d
0x140005a59  jbe     short loc_140005AAA
0x140005a5b  mov     rcx, cs:WPP_GLOBAL_Control
0x140005a62  mov     eax, [rcx+2Ch]
0x140005a65  test    al, 10h
0x140005a67  jz      short loc_140005A73
0x140005a69  cmp     byte ptr [rcx+29h], 3
0x140005a6d  jb      short loc_140005A73
0x140005a6f  mov     dl, 1
0x140005a71  jmp     short loc_140005A75
0x140005a73  xor     dl, dl
0x140005a75  mov     [rsp+0A8h+var_50], r8d
0x140005a7a  mov     [rsp+0A8h+var_58], r9d
0x140005a7f  mov     r9, [rcx+40h]
0x140005a83  mov     rcx, [rcx+18h]
0x140005a87  mov     [rsp+0A8h+var_60], r15
0x140005a8c  mov     [rsp+0A8h+var_68], r10d
0x140005a91  mov     [rsp+0A8h+var_78], 64h ; 'd'
0x140005a98  mov     [rsp+0A8h+var_88], 3
0x140005a9d  call    WPP_RECORDER_AND_TRACE_SF_LPLL
0x140005aa2  mov     r10d, [rsp+0A8h+arg_10]
0x140005aaa  sub     dword ptr [rdi+34h], 1
0x140005aae  jnz     short loc_140005B06
0x140005ab0  mov     rcx, cs:WPP_GLOBAL_Control
0x140005ab7  mov     eax, [rcx+2Ch]
0x140005aba  test    al, 10h
0x140005abc  jz      short loc_140005AC8
0x140005abe  cmp     byte ptr [rcx+29h], 4
0x140005ac2  jb      short loc_140005AC8
0x140005ac4  mov     dl, 1
0x140005ac6  jmp     short loc_140005ACA
0x140005ac8  xor     dl, dl
0x140005aca  mov     eax, [r13+80h]
0x140005ad1  mov     r9, [rcx+40h]
0x140005ad5  mov     rcx, [rcx+18h]
0x140005ad9  mov     [rsp+0A8h+var_50], eax
0x140005add  mov     eax, [rbp+80h]
0x140005ae3  mov     [rsp+0A8h+var_58], eax
0x140005ae7  mov     [rsp+0A8h+var_60], r15
0x140005aec  mov     [rsp+0A8h+var_68], r10d
0x140005af1  mov     [rsp+0A8h+var_78], 65h ; 'e'
0x140005af8  mov     [rsp+0A8h+var_88], 4
0x140005afd  call    WPP_RECORDER_AND_TRACE_SF_LPLL
0x140005b02  mov     byte ptr [rdi+4Ch], 0
0x140005b06  mov     edx, [rdi+20h]; enum _BTH_PIPE_TYPE
0x140005b09  mov     rcx, rsi; struct _SCO_USB_TRANSFER_CTX *
0x140005b0c  call    ?BthUsb_ScoUrbError@@YAEPEAU_SCO_USB_TRANSFER_CTX@@W4_BTH_PIPE_TYPE@@@Z; BthUsb_ScoUrbError(_SCO_USB_TRANSFER_CTX *,_BTH_PIPE_TYPE)
0x140005b11  test    al, al
0x140005b13  jz      short loc_140005B77
0x140005b15  cmp     byte ptr [rdi+4Ch], 0
0x140005b19  jz      short loc_140005B77
0x140005b1b  mov     rcx, cs:WPP_GLOBAL_Control
0x140005b22  mov     eax, [rcx+2Ch]
0x140005b25  test    al, 10h
0x140005b27  jz      short loc_140005B33
0x140005b29  cmp     byte ptr [rcx+29h], 3
0x140005b2d  jb      short loc_140005B33
0x140005b2f  mov     dl, 1
0x140005b31  jmp     short loc_140005B35
0x140005b33  xor     dl, dl
0x140005b35  mov     eax, [r13+80h]
0x140005b3c  mov     r9, [rcx+40h]
0x140005b40  mov     rcx, [rcx+18h]
0x140005b44  mov     [rsp+0A8h+var_50], eax
0x140005b48  mov     eax, [rbp+80h]
0x140005b4e  mov     [rsp+0A8h+var_58], eax
0x140005b52  mov     eax, [rsp+0A8h+arg_10]
0x140005b59  mov     [rsp+0A8h+var_60], r15
0x140005b5e  mov     [rsp+0A8h+var_68], eax
0x140005b62  mov     [rsp+0A8h+var_78], 66h ; 'f'
0x140005b69  mov     [rsp+0A8h+var_88], 3
0x140005b6e  call    WPP_RECORDER_AND_TRACE_SF_LPLL
0x140005b73  mov     byte ptr [rdi+4Ch], 0
0x140005b77  test    rsi, rsi
0x140005b7a  jnz     short loc_140005B80
0x140005b7c  and     dword ptr [rdi+30h], 0FFFFFFFEh
0x140005b80  mov     dl, [rsp+0A8h+NewIrql]; NewIrql
0x140005b87  mov     rcx, r12; SpinLock
0x140005b8a  call    cs:__imp_KeReleaseSpinLock
0x140005b91  nop     dword ptr [rax+rax+00h]
0x140005b96  test    rsi, rsi
0x140005b99  jz      loc_14000591D
0x140005b9f  mov     rax, [rdi+8]
0x140005ba3  mov     rdx, rsi
0x140005ba6  mov     rcx, [rsp+0A8h+arg_0]
0x140005bae  call    _guard_dispatch_icall
0x140005bb3  mov     rcx, r12; SpinLock
0x140005bb6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005bbd  nop     dword ptr [rax+rax+00h]
0x140005bc2  mov     r10d, [rsp+0A8h+arg_10]
0x140005bca  inc     r15
0x140005bcd  mov     [rsp+0A8h+NewIrql], al
0x140005bd4  jmp     loc_140005950
0x140005bd9  mov     ecx, 3
0x140005bde  int     29h; Win8: RtlFailFast(ecx)
```
