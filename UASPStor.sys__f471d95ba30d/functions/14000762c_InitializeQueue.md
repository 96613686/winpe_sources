# InitializeQueue

- ea: `0x14000762c`
- end: `0x140007856`
- name: `InitializeQueue`
- size: `554`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400015cc`

## callees

- `0x14000762c`
- `0x14000d370`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x140007659`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000766c`
- `ntoskrnl!KeInitializeSpinLock` at `0x140007659`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000766c`
- `ntoskrnl!IoAllocateIrp` at `0x1400076b7`
- `ntoskrnl!IoAllocateIrp` at `0x1400076fc`
- `ntoskrnl!IoAllocateIrp` at `0x140007741`
- `ntoskrnl!IoAllocateIrp` at `0x140007789`
- `ntoskrnl!IoAllocateIrp` at `0x1400076b7`
- `ntoskrnl!IoAllocateIrp` at `0x1400076fc`
- `ntoskrnl!IoAllocateIrp` at `0x140007741`
- `ntoskrnl!IoAllocateIrp` at `0x140007789`

## pseudocode

```c
__int64 __fastcall InitializeQueue(__int64 a1, __int64 a2)
{
  unsigned __int16 v2; // r13
  NTSTATUS v4; // ebx
  unsigned __int16 v6; // r12
  __int64 v7; // rbp
  __int64 v8; // rsi
  PIRP Irp; // rax
  PIRP v10; // rax
  PIRP v11; // rax
  PIRP v12; // rax
  unsigned __int64 v13; // r15
  _QWORD *v14; // rdx
  PURB Urb; // [rsp+78h] [rbp+10h] BYREF

  v2 = *(_WORD *)(a2 + 1280);
  v4 = 0;
  Urb = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)(a2 + 1240));
  KeInitializeSpinLock((PKSPIN_LOCK)(a2 + 1136));
  v6 = 0;
  if ( v2 )
  {
    while ( 1 )
    {
      v7 = *(_QWORD *)(a2 + 1176);
      v8 = 224LL * v6;
      *(_QWORD *)(v8 + v7) = a2;
      *(_WORD *)(v8 + v7 + 40) = v6;
      *(_DWORD *)(*(_QWORD *)(a2 + 1224) + 4LL * v6) = 1;
      Irp = IoAllocateIrp(*(_BYTE *)(a1 + 76), 0);
      if ( !Irp )
        break;
      *(_QWORD *)(v8 + v7 + 112) = Irp;
      v4 = USBD_UrbAllocate(*(USBD_HANDLE *)(a2 + 1272), &Urb);
      if ( v4 < 0 )
        return (unsigned int)v4;
      *(_QWORD *)(v8 + v7 + 80) = Urb;
      v10 = IoAllocateIrp(*(_BYTE *)(a1 + 76), 0);
      if ( !v10 )
        break;
      *(_QWORD *)(v8 + v7 + 120) = v10;
      v4 = USBD_UrbAllocate(*(USBD_HANDLE *)(a2 + 1272), &Urb);
      if ( v4 < 0 )
        return (unsigned int)v4;
      *(_QWORD *)(v8 + v7 + 88) = Urb;
      v11 = IoAllocateIrp(*(_BYTE *)(a1 + 76), 0);
      if ( !v11 )
        break;
      *(_QWORD *)(v8 + v7 + 128) = v11;
      v4 = USBD_UrbAllocate(*(USBD_HANDLE *)(a2 + 1272), &Urb);
      if ( v4 < 0 )
        return (unsigned int)v4;
      *(_QWORD *)(v8 + v7 + 96) = Urb;
      v12 = IoAllocateIrp(*(_BYTE *)(a1 + 76), 0);
      if ( !v12 )
        break;
      *(_QWORD *)(v8 + v7 + 136) = v12;
      v4 = USBD_UrbAllocate(*(USBD_HANDLE *)(a2 + 1272), &Urb);
      if ( v4 < 0 )
        return (unsigned int)v4;
      *(_QWORD *)(v8 + v7 + 104) = Urb;
      v13 = (unsigned __int64)v6 << 10;
      v14 = (_QWORD *)(*(_QWORD *)(a2 + 1160) + 40LL * v6);
      *(_QWORD *)(v8 + v7 + 208) = v14;
      *(_QWORD *)(v8 + v7 + 216) = *(_QWORD *)(a2 + 1168) + 40LL * v6;
      *v14 = v13 + *(_QWORD *)(a2 + 1200);
      **(_QWORD **)(v8 + v7 + 216) = v13 + *(_QWORD *)(a2 + 1192);
      if ( ++v6 >= v2 )
        goto LABEL_11;
    }
    return (unsigned int)-1073741670;
  }
  else
  {
LABEL_11:
    *(_WORD *)(a2 + 1232) = 1;
    *(_DWORD *)(a2 + 1248) = 3;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000762c  push    rbx
0x14000762e  push    rbp
0x14000762f  push    rsi
0x140007630  push    rdi
0x140007631  push    r12
0x140007633  push    r13
0x140007635  push    r14
0x140007637  push    r15
0x140007639  sub     rsp, 28h
0x14000763d  movzx   r13d, word ptr [rdx+500h]
0x140007645  mov     r14, rcx
0x140007648  xor     ebx, ebx
0x14000764a  lea     rcx, [rdx+4D8h]; SpinLock
0x140007651  mov     [rsp+68h+Urb], rbx
0x140007656  mov     rdi, rdx
0x140007659  call    cs:__imp_KeInitializeSpinLock
0x140007660  nop     dword ptr [rax+rax+00h]
0x140007665  lea     rcx, [rdi+470h]; SpinLock
0x14000766c  call    cs:__imp_KeInitializeSpinLock
0x140007673  nop     dword ptr [rax+rax+00h]
0x140007678  xor     eax, eax
0x14000767a  lea     ecx, [rbx+1]
0x14000767d  xor     r12d, r12d
0x140007680  cmp     ax, r13w
0x140007684  jnb     loc_14000782A
0x14000768a  mov     rbp, [rdi+498h]
0x140007691  xor     edx, edx; ChargeQuota
0x140007693  movzx   r15d, r12w
0x140007697  imul    rsi, r15, 0E0h
0x14000769e  mov     [rsi+rbp], rdi
0x1400076a2  mov     [rsi+rbp+28h], r12w
0x1400076a8  mov     rax, [rdi+4C8h]
0x1400076af  mov     [rax+r15*4], ecx
0x1400076b3  mov     cl, [r14+4Ch]; StackSize
0x1400076b7  call    cs:__imp_IoAllocateIrp
0x1400076be  nop     dword ptr [rax+rax+00h]
0x1400076c3  test    rax, rax
0x1400076c6  jz      loc_14000784F
0x1400076cc  mov     [rsi+rbp+70h], rax
0x1400076d1  lea     rdx, [rsp+68h+Urb]; Urb
0x1400076d6  mov     rcx, [rdi+4F8h]; USBDHandle
0x1400076dd  call    USBD_UrbAllocate
0x1400076e2  mov     ebx, eax
0x1400076e4  test    eax, eax
0x1400076e6  js      loc_14000783B
0x1400076ec  mov     rax, [rsp+68h+Urb]
0x1400076f1  xor     edx, edx; ChargeQuota
0x1400076f3  mov     [rsi+rbp+50h], rax
0x1400076f8  mov     cl, [r14+4Ch]; StackSize
0x1400076fc  call    cs:__imp_IoAllocateIrp
0x140007703  nop     dword ptr [rax+rax+00h]
0x140007708  test    rax, rax
0x14000770b  jz      loc_14000784F
0x140007711  mov     [rsi+rbp+78h], rax
0x140007716  lea     rdx, [rsp+68h+Urb]; Urb
0x14000771b  mov     rcx, [rdi+4F8h]; USBDHandle
0x140007722  call    USBD_UrbAllocate
0x140007727  mov     ebx, eax
0x140007729  test    eax, eax
0x14000772b  js      loc_14000783B
0x140007731  mov     rax, [rsp+68h+Urb]
0x140007736  xor     edx, edx; ChargeQuota
0x140007738  mov     [rsi+rbp+58h], rax
0x14000773d  mov     cl, [r14+4Ch]; StackSize
0x140007741  call    cs:__imp_IoAllocateIrp
0x140007748  nop     dword ptr [rax+rax+00h]
0x14000774d  test    rax, rax
0x140007750  jz      loc_14000784F
0x140007756  mov     [rsi+rbp+80h], rax
0x14000775e  lea     rdx, [rsp+68h+Urb]; Urb
0x140007763  mov     rcx, [rdi+4F8h]; USBDHandle
0x14000776a  call    USBD_UrbAllocate
0x14000776f  mov     ebx, eax
0x140007771  test    eax, eax
0x140007773  js      loc_14000783B
0x140007779  mov     rax, [rsp+68h+Urb]
0x14000777e  xor     edx, edx; ChargeQuota
0x140007780  mov     [rsi+rbp+60h], rax
0x140007785  mov     cl, [r14+4Ch]; StackSize
0x140007789  call    cs:__imp_IoAllocateIrp
0x140007790  nop     dword ptr [rax+rax+00h]
0x140007795  test    rax, rax
0x140007798  jz      loc_14000784F
0x14000779e  mov     [rsi+rbp+88h], rax
0x1400077a6  lea     rdx, [rsp+68h+Urb]; Urb
0x1400077ab  mov     rcx, [rdi+4F8h]; USBDHandle
0x1400077b2  call    USBD_UrbAllocate
0x1400077b7  mov     ebx, eax
0x1400077b9  test    eax, eax
0x1400077bb  js      short loc_14000783B
0x1400077bd  mov     rax, [rsp+68h+Urb]
0x1400077c2  lea     rcx, [r15+r15*4]
0x1400077c6  mov     [rsi+rbp+68h], rax
0x1400077cb  mov     rax, [rdi+488h]
0x1400077d2  shl     r15, 0Ah
0x1400077d6  lea     rdx, [rax+rcx*8]
0x1400077da  mov     [rsi+rbp+0D0h], rdx
0x1400077e2  mov     rax, [rdi+490h]
0x1400077e9  lea     rcx, [rax+rcx*8]
0x1400077ed  mov     [rsi+rbp+0D8h], rcx
0x1400077f5  mov     rcx, [rdi+4B0h]
0x1400077fc  add     rcx, r15
0x1400077ff  mov     [rdx], rcx
0x140007802  mov     rcx, [rdi+4A8h]
0x140007809  mov     rax, [rsi+rbp+0D8h]
0x140007811  add     rcx, r15
0x140007814  mov     [rax], rcx
0x140007817  mov     ecx, 1
0x14000781c  add     r12w, cx
0x140007820  cmp     r12w, r13w
0x140007824  jb      loc_14000768A
0x14000782a  mov     [rdi+4D0h], cx
0x140007831  mov     dword ptr [rdi+4E0h], 3
0x14000783b  mov     eax, ebx
0x14000783d  add     rsp, 28h
0x140007841  pop     r15
0x140007843  pop     r14
0x140007845  pop     r13
0x140007847  pop     r12
0x140007849  pop     rdi
0x14000784a  pop     rsi
0x14000784b  pop     rbp
0x14000784c  pop     rbx
0x14000784d  retn
0x14000784f  mov     ebx, 0C000009Ah
0x140007854  jmp     short loc_14000783B
```
