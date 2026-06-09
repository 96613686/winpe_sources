# BthUsb_ScoReadAlignFrame(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *,ushort,ulong)

- ea: `0x140007bf0`
- end: `0x140007c56`
- name: `?BthUsb_ScoReadAlignFrame@@YAKPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_TRANSFER_CTX@@GK@Z`
- size: `102`
- prototype: `unsigned int __fastcall(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *, unsigned __int16, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140007bf0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140007c20`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007c20`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007c09`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007c09`

## pseudocode

```c
__int64 __fastcall BthUsb_ScoReadAlignFrame(
        struct _DEVICE_EXTENSION *a1,
        struct _SCO_USB_TRANSFER_CTX *a2,
        __int64 a3,
        unsigned int a4)
{
  unsigned __int64 *p_ReadLock; // rbx
  KIRQL v7; // al
  unsigned int ReadLastFrame; // edi
  unsigned int READ_FRAMES_X_REQ; // ecx
  unsigned int v10; // edx

  p_ReadLock = &a1->Sco.ReadLock;
  v7 = KeAcquireSpinLockRaiseToDpc(&a1->Sco.ReadLock);
  ReadLastFrame = a1->Sco.ReadLastFrame;
  KeReleaseSpinLock(p_ReadLock, v7);
  READ_FRAMES_X_REQ = a1->Sco.UsbAltSetting->READ_FRAMES_X_REQ;
  v10 = (a4 - ReadLastFrame) % READ_FRAMES_X_REQ;
  if ( v10 )
    return a4 + READ_FRAMES_X_REQ - v10;
  else
    return a4;
}

```

## disassembly

```asm
0x140007bf0  push    rbx
0x140007bf2  push    rbp
0x140007bf3  push    rsi
0x140007bf4  push    rdi
0x140007bf5  sub     rsp, 28h
0x140007bf9  lea     rbx, [rcx+248h]
0x140007c00  mov     rsi, rcx
0x140007c03  mov     rcx, rbx; SpinLock
0x140007c06  mov     ebp, r9d
0x140007c09  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007c10  nop     dword ptr [rax+rax+00h]
0x140007c15  mov     edi, [rsi+250h]
0x140007c1b  mov     rcx, rbx; SpinLock
0x140007c1e  mov     dl, al; NewIrql
0x140007c20  call    cs:__imp_KeReleaseSpinLock
0x140007c27  nop     dword ptr [rax+rax+00h]
0x140007c2c  mov     rax, [rsi+478h]
0x140007c33  xor     edx, edx
0x140007c35  mov     ecx, [rax+48h]
0x140007c38  mov     eax, ebp
0x140007c3a  sub     eax, edi
0x140007c3c  div     ecx
0x140007c3e  test    edx, edx
0x140007c40  jz      short loc_140007C48
0x140007c42  sub     ecx, edx
0x140007c44  add     ecx, ebp
0x140007c46  jmp     short loc_140007C4A
0x140007c48  mov     ecx, ebp
0x140007c4a  mov     eax, ecx
0x140007c4c  add     rsp, 28h
0x140007c50  pop     rdi
0x140007c51  pop     rsi
0x140007c52  pop     rbp
0x140007c53  pop     rbx
0x140007c54  retn
```
