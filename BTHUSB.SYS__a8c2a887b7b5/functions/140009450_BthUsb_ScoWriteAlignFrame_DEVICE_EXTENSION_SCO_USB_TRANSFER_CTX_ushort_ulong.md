# BthUsb_ScoWriteAlignFrame(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *,ushort,ulong)

- ea: `0x140009450`
- end: `0x1400094f2`
- name: `?BthUsb_ScoWriteAlignFrame@@YAKPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_TRANSFER_CTX@@GK@Z`
- size: `162`
- prototype: `unsigned int __fastcall(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *, unsigned __int16, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140009450`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140009491`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009491`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009471`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009471`

## pseudocode

```c
__int64 __fastcall BthUsb_ScoWriteAlignFrame(
        struct _DEVICE_EXTENSION *a1,
        struct _SCO_USB_TRANSFER_CTX *a2,
        unsigned __int16 a3,
        unsigned int a4)
{
  unsigned __int64 *p_WriteLock; // rbx
  int v5; // edi
  KIRQL v8; // al
  unsigned int WriteLastFrame; // r15d
  int WriteLastPipeId; // r14d
  unsigned __int16 *p_NumChannels; // r8
  int v12; // edx
  unsigned int WriteFramesPerReq; // ecx
  unsigned int v14; // r8d
  unsigned int v15; // edx

  p_WriteLock = &a1->Sco.WriteLock;
  v5 = a3;
  v8 = KeAcquireSpinLockRaiseToDpc(&a1->Sco.WriteLock);
  WriteLastFrame = a1->Sco.WriteLastFrame;
  WriteLastPipeId = a1->Sco.WriteLastPipeId;
  KeReleaseSpinLock(p_WriteLock, v8);
  p_NumChannels = &a1->Sco.NumChannels;
  v12 = v5;
  if ( (unsigned __int16)WriteLastPipeId > (unsigned __int16)v5 )
    v12 = *p_NumChannels + v5;
  WriteFramesPerReq = a1->Sco.WriteFramesPerReq;
  v14 = WriteFramesPerReq * *p_NumChannels;
  v15 = (a4 - WriteFramesPerReq * (v12 - WriteLastPipeId) - WriteLastFrame) % v14;
  if ( v15 )
    return a4 + v14 - v15;
  else
    return a4;
}

```

## disassembly

```asm
0x140009450  push    rbx
0x140009452  push    rbp
0x140009453  push    rsi
0x140009454  push    rdi
0x140009455  push    r14
0x140009457  push    r15
0x140009459  sub     rsp, 28h
0x14000945d  lea     rbx, [rcx+260h]
0x140009464  movzx   edi, r8w
0x140009468  mov     rbp, rcx
0x14000946b  mov     esi, r9d
0x14000946e  mov     rcx, rbx; SpinLock
0x140009471  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140009478  nop     dword ptr [rax+rax+00h]
0x14000947d  mov     r15d, [rbp+268h]
0x140009484  mov     rcx, rbx; SpinLock
0x140009487  movzx   r14d, word ptr [rbp+26Ch]
0x14000948f  mov     dl, al; NewIrql
0x140009491  call    cs:__imp_KeReleaseSpinLock
0x140009498  nop     dword ptr [rax+rax+00h]
0x14000949d  lea     r8, [rbp+2ACh]
0x1400094a4  mov     edx, edi
0x1400094a6  cmp     r14w, di
0x1400094aa  jbe     short loc_1400094B2
0x1400094ac  movzx   eax, word ptr [r8]
0x1400094b0  add     edx, eax
0x1400094b2  mov     ecx, [rbp+270h]
0x1400094b8  sub     edx, r14d
0x1400094bb  movzx   r8d, word ptr [r8]
0x1400094bf  mov     eax, esi
0x1400094c1  imul    edx, ecx
0x1400094c4  imul    r8d, ecx
0x1400094c8  sub     eax, edx
0x1400094ca  xor     edx, edx
0x1400094cc  sub     eax, r15d
0x1400094cf  div     r8d
0x1400094d2  test    edx, edx
0x1400094d4  jz      short loc_1400094DE
0x1400094d6  sub     r8d, edx
0x1400094d9  add     r8d, esi
0x1400094dc  jmp     short loc_1400094E1
0x1400094de  mov     r8d, esi
0x1400094e1  mov     eax, r8d
0x1400094e4  add     rsp, 28h
0x1400094e8  pop     r15
0x1400094ea  pop     r14
0x1400094ec  pop     rdi
0x1400094ed  pop     rsi
0x1400094ee  pop     rbp
0x1400094ef  pop     rbx
0x1400094f0  retn
```
