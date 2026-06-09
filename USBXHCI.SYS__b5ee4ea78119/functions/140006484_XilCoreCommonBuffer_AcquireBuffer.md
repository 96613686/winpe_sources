# XilCoreCommonBuffer_AcquireBuffer

- ea: `0x140006484`
- end: `0x14000661a`
- name: `XilCoreCommonBuffer_AcquireBuffer`
- size: `406`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400060c0`
- `0x140006260`
- `0x140006438`

## callees

- `0x140006484`
- `0x14002c0fc`
- `0x14002c5b0`
- `0x14003b238`
- `0x140057db0`
- `0x140059d80`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000653c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400065ba`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000653c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400065ba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006504`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000658a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006504`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000658a`
- `ntoskrnl!KeGetCurrentIrql` at `0x140006552`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400065dc`
- `ntoskrnl!KeGetCurrentIrql` at `0x140006552`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400065dc`

## string_xrefs

- `0x1400065ec`: `Common buffer allocation failure at DISPATCH LEVEL`

## pseudocode

```c
__int64 __fastcall XilCoreCommonBuffer_AcquireBuffer(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        _BYTE *a5)
{
  __int64 Buffer; // rax
  __int64 v10; // rbx
  unsigned int i; // ecx
  unsigned int *v12; // r14
  __int64 v13; // r8

  if ( a2 <= 0x1000 )
  {
    for ( i = 0; i < 2; ++i )
    {
      v12 = (unsigned int *)(a1 + ((unsigned __int64)i << 6) + 32);
      if ( a2 <= *v12 )
        break;
    }
    *(_BYTE *)(a1 + 25) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 16));
    v10 = XilCoreCommonBuffer_AcquireBufferWithSegmenter(a1, (_DWORD)v12, a3, a4, (__int64)a5);
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 16), *(_BYTE *)(a1 + 25));
    if ( v10 && !*a5 )
      goto LABEL_16;
    if ( KeGetCurrentIrql() )
    {
      *a5 = 1;
    }
    else
    {
      v13 = v10 == 0;
      if ( *a5 )
        v13 = v12[4] + (unsigned int)v13;
      XilCoreCommonBuffer_AllocateBuffers(a1, v12, v13);
      *a5 = 0;
      if ( v10 )
        goto LABEL_16;
      *(_BYTE *)(a1 + 25) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 16));
      v10 = XilCoreCommonBuffer_AcquireBufferWithSegmenter(a1, (_DWORD)v12, a3, a4, (__int64)a5);
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 16), *(_BYTE *)(a1 + 25));
    }
    if ( v10 )
    {
LABEL_16:
      *(_DWORD *)(v10 + 80) = 1;
      *(_DWORD *)(v10 + 44) = a2;
      return v10;
    }
  }
  else
  {
    Buffer = XilCoreCommonBuffer_AllocateBuffer(a1, a2);
    v10 = Buffer;
    if ( Buffer )
    {
      *a5 = 0;
      memset(*(void **)(Buffer + 16), 0, a2);
      *(_QWORD *)(v10 + 72) = a3;
      *(_DWORD *)(v10 + 64) = a4;
      goto LABEL_16;
    }
  }
  if ( KeGetCurrentIrql() )
    MicrosoftTelemetryAssertTriggeredArgsMsgKM(
      "usbxhci.sys",
      a4,
      a2,
      "Common buffer allocation failure at DISPATCH LEVEL");
  return v10;
}

```

## disassembly

```asm
0x140006484  push    rbx
0x140006486  push    rbp
0x140006487  push    rsi
0x140006488  push    rdi
0x140006489  push    r12
0x14000648b  push    r13
0x14000648d  push    r14
0x14000648f  push    r15
0x140006491  sub     rsp, 38h
0x140006495  mov     edi, edx
0x140006497  mov     r15d, r9d
0x14000649a  mov     r12, r8
0x14000649d  mov     rbp, rcx
0x1400064a0  cmp     edx, 1000h
0x1400064a6  jbe     short loc_1400064E1
0x1400064a8  mov     edx, edi
0x1400064aa  call    XilCoreCommonBuffer_AllocateBuffer
0x1400064af  mov     rbx, rax
0x1400064b2  test    rax, rax
0x1400064b5  jz      loc_1400065DC
0x1400064bb  mov     rcx, [rsp+78h+arg_20]
0x1400064c3  mov     r8d, edi; Size
0x1400064c6  xor     edx, edx; Val
0x1400064c8  mov     byte ptr [rcx], 0
0x1400064cb  mov     rcx, [rax+10h]; void *
0x1400064cf  call    memset
0x1400064d4  mov     [rbx+48h], r12
0x1400064d8  mov     [rbx+40h], r15d
0x1400064dc  jmp     loc_1400065D0
0x1400064e1  xor     ecx, ecx
0x1400064e3  mov     r14d, ecx
0x1400064e6  shl     r14, 6
0x1400064ea  add     r14, 20h ; ' '
0x1400064ee  add     r14, rbp
0x1400064f1  cmp     edi, [r14]
0x1400064f4  jbe     short loc_1400064FD
0x1400064f6  inc     ecx
0x1400064f8  cmp     ecx, 2
0x1400064fb  jb      short loc_1400064E3
0x1400064fd  lea     r13, [rbp+10h]
0x140006501  mov     rcx, r13; SpinLock
0x140006504  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000650b  nop     dword ptr [rax+rax+00h]
0x140006510  mov     rsi, [rsp+78h+arg_20]
0x140006518  mov     r9d, r15d
0x14000651b  mov     r8, r12
0x14000651e  mov     [r13+9], al
0x140006522  mov     rdx, r14
0x140006525  mov     [rsp+78h+var_58], rsi
0x14000652a  mov     rcx, rbp
0x14000652d  call    XilCoreCommonBuffer_AcquireBufferWithSegmenter
0x140006532  mov     dl, [r13+9]; NewIrql
0x140006536  mov     rcx, r13; SpinLock
0x140006539  mov     rbx, rax
0x14000653c  call    cs:__imp_KeReleaseSpinLock
0x140006543  nop     dword ptr [rax+rax+00h]
0x140006548  test    rbx, rbx
0x14000654b  jz      short loc_140006552
0x14000654d  cmp     byte ptr [rsi], 0
0x140006550  jz      short loc_1400065D0
0x140006552  call    cs:__imp_KeGetCurrentIrql
0x140006559  nop     dword ptr [rax+rax+00h]
0x14000655e  test    al, al
0x140006560  jnz     short loc_1400065C8
0x140006562  xor     r8d, r8d
0x140006565  test    rbx, rbx
0x140006568  setz    r8b
0x14000656c  cmp     [rsi], al
0x14000656e  jz      short loc_140006574
0x140006570  add     r8d, [r14+10h]
0x140006574  mov     rdx, r14
0x140006577  mov     rcx, rbp
0x14000657a  call    XilCoreCommonBuffer_AllocateBuffers
0x14000657f  mov     byte ptr [rsi], 0
0x140006582  test    rbx, rbx
0x140006585  jnz     short loc_1400065D0
0x140006587  mov     rcx, r13; SpinLock
0x14000658a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006591  nop     dword ptr [rax+rax+00h]
0x140006596  mov     r9d, r15d
0x140006599  mov     [rsp+78h+var_58], rsi
0x14000659e  mov     r8, r12
0x1400065a1  mov     [r13+9], al
0x1400065a5  mov     rdx, r14
0x1400065a8  mov     rcx, rbp
0x1400065ab  call    XilCoreCommonBuffer_AcquireBufferWithSegmenter
0x1400065b0  mov     dl, [r13+9]; NewIrql
0x1400065b4  mov     rcx, r13; SpinLock
0x1400065b7  mov     rbx, rax
0x1400065ba  call    cs:__imp_KeReleaseSpinLock
0x1400065c1  nop     dword ptr [rax+rax+00h]
0x1400065c6  jmp     short loc_1400065CB
0x1400065c8  mov     byte ptr [rsi], 1
0x1400065cb  test    rbx, rbx
0x1400065ce  jz      short loc_1400065DC
0x1400065d0  mov     dword ptr [rbx+50h], 1
0x1400065d7  mov     [rbx+2Ch], edi
0x1400065da  jmp     short loc_140006605
0x1400065dc  call    cs:__imp_KeGetCurrentIrql
0x1400065e3  nop     dword ptr [rax+rax+00h]
0x1400065e8  test    al, al
0x1400065ea  jz      short loc_140006605
0x1400065ec  lea     r9, aCommonBufferAl; __annotation("Debug", "TelemetryAssert", "FALSE", "Common buffer allocation failure at DISPATCH LEVEL")
0x1400065f3  mov     r8d, edi
0x1400065f6  mov     edx, r15d
0x1400065f9  lea     rcx, aUsbxhciSys; "usbxhci.sys"
0x140006600  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x140006605  mov     rax, rbx
0x140006608  add     rsp, 38h
0x14000660c  pop     r15
0x14000660e  pop     r14
0x140006610  pop     r13
0x140006612  pop     r12
0x140006614  pop     rdi
0x140006615  pop     rsi
0x140006616  pop     rbp
0x140006617  pop     rbx
0x140006618  retn
```
