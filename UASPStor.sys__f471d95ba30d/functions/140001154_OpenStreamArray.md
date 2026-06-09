# OpenStreamArray

- ea: `0x140001154`
- end: `0x140001394`
- name: `OpenStreamArray`
- size: `576`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1400015cc`

## callees

- `0x140001154`
- `0x1400052b8`
- `0x14000607c`
- `0x14000d370`
- `0x14000d560`
- `0x14000dc00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400011db`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400011db`

## pseudocode

```c
__int64 __fastcall OpenStreamArray(__int64 a1, __int64 a2, void *a3, void *a4, void *a5)
{
  void *Pool; // rbp
  __int64 v10; // rcx
  NTSTATUS v11; // ebx
  PURB v12; // r8
  PURB v14; // rdi
  __int64 v15; // rbx
  __int64 v16; // r9
  __int64 v17; // r9
  ULONG Reserved; // ecx
  unsigned __int8 v19; // r9
  __int64 v20; // rcx
  __int64 v21; // r9
  ULONG v22; // ecx
  unsigned __int8 v23; // r9
  __int64 v24; // rcx
  ULONG v25; // ecx
  unsigned __int8 v26; // r9
  __int64 v27; // rcx
  PURB Urb; // [rsp+50h] [rbp+8h] BYREF

  Urb = 0;
  Pool = 0;
  v11 = USBD_UrbAllocate(*(USBD_HANDLE *)(a1 + 1272), &Urb);
  if ( v11 < 0 )
    goto LABEL_4;
  Pool = (void *)UaspAllocatePool(v10, 24LL * *(unsigned __int16 *)(a1 + 1280));
  if ( !Pool )
  {
    v11 = -1073741670;
LABEL_4:
    v12 = Urb;
    goto LABEL_5;
  }
  v14 = Urb;
  v15 = *(unsigned __int16 *)(a1 + 1280);
  memset(Urb, 0, sizeof(struct _URB));
  memset(Pool, 0, 24 * v15);
  *(_DWORD *)&v14->UrbHeader.Length = 3473456;
  v14->UrbSelectInterface.ConfigurationHandle = a3;
  v14->UrbPipeRequest.Reserved = v15;
  v14->UrbControlTransfer.TransferBufferLength = 1573120;
  v14->UrbSelectInterface.Interface.InterfaceHandle = Pool;
  LOBYTE(v16) = 1;
  v11 = UaspSyncSendUsbRequestNew(a1, *(_QWORD *)(a1 + 16), Urb, v16);
  if ( v11 < 0 )
    goto LABEL_4;
  v12 = Urb;
  Reserved = Urb->UrbPipeRequest.Reserved;
  if ( Reserved > *(unsigned __int16 *)(a1 + 1280) )
    goto LABEL_12;
  v19 = 0;
  if ( Reserved )
  {
    do
    {
      v20 = v19++;
      *(_QWORD *)(224 * v20 + a2 + 48) = *((_QWORD *)v12->UrbSelectInterface.Interface.InterfaceHandle + 3 * v20);
    }
    while ( v19 < v12->UrbPipeRequest.Reserved );
  }
  v12->UrbSelectInterface.ConfigurationHandle = a4;
  LOBYTE(v17) = 1;
  v11 = UaspSyncSendUsbRequestNew(a1, *(_QWORD *)(a1 + 16), Urb, v17);
  if ( v11 < 0 )
    goto LABEL_4;
  v12 = Urb;
  v22 = Urb->UrbPipeRequest.Reserved;
  if ( v22 > *(unsigned __int16 *)(a1 + 1280) )
    goto LABEL_12;
  v23 = 0;
  if ( v22 )
  {
    do
    {
      v24 = v23++;
      *(_QWORD *)(224 * v24 + a2 + 56) = *((_QWORD *)v12->UrbSelectInterface.Interface.InterfaceHandle + 3 * v24);
    }
    while ( v23 < v12->UrbPipeRequest.Reserved );
  }
  LOBYTE(v21) = 1;
  v12->UrbSelectInterface.ConfigurationHandle = a5;
  v11 = UaspSyncSendUsbRequestNew(a1, *(_QWORD *)(a1 + 16), Urb, v21);
  if ( v11 < 0 )
    goto LABEL_4;
  v12 = Urb;
  v25 = Urb->UrbPipeRequest.Reserved;
  if ( v25 > *(unsigned __int16 *)(a1 + 1280) )
  {
LABEL_12:
    v11 = -1073741668;
  }
  else
  {
    v26 = 0;
    if ( v25 )
    {
      do
      {
        v27 = v26++;
        *(_QWORD *)(224 * v27 + a2 + 64) = *((_QWORD *)v12->UrbSelectInterface.Interface.InterfaceHandle + 3 * v27);
      }
      while ( v26 < v12->UrbPipeRequest.Reserved );
    }
  }
LABEL_5:
  if ( v12 )
    USBD_UrbFree(*(USBD_HANDLE *)(a1 + 1272), v12);
  if ( Pool )
    ExFreePoolWithTag(Pool, 0);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140001154  mov     rax, rsp
0x140001157  mov     [rax+10h], rbx
0x14000115b  mov     [rax+18h], rbp
0x14000115f  push    rsi
0x140001160  push    rdi
0x140001161  push    r12
0x140001163  push    r14
0x140001165  push    r15
0x140001167  sub     rsp, 20h
0x14000116b  mov     r14, rdx
0x14000116e  mov     qword ptr [rax+8], 0
0x140001176  mov     rsi, rcx
0x140001179  lea     rdx, [rax+8]; Urb
0x14000117d  mov     rcx, [rcx+4F8h]; USBDHandle
0x140001184  mov     r15, r9
0x140001187  mov     r12, r8
0x14000118a  xor     ebp, ebp
0x14000118c  call    USBD_UrbAllocate
0x140001191  mov     ebx, eax
0x140001193  test    eax, eax
0x140001195  js      short loc_1400011B8
0x140001197  movzx   eax, word ptr [rsi+500h]
0x14000119e  lea     rdx, [rax+rax*2]
0x1400011a2  shl     rdx, 3
0x1400011a6  call    UaspAllocatePool
0x1400011ab  mov     rbp, rax
0x1400011ae  test    rax, rax
0x1400011b1  jnz     short loc_140001201
0x1400011b3  mov     ebx, 0C000009Ah
0x1400011b8  mov     r8, [rsp+48h+Urb]
0x1400011bd  test    r8, r8
0x1400011c0  jz      short loc_1400011D1
0x1400011c2  mov     rcx, [rsi+4F8h]; USBDHandle
0x1400011c9  mov     rdx, r8; Urb
0x1400011cc  call    USBD_UrbFree
0x1400011d1  test    rbp, rbp
0x1400011d4  jz      short loc_1400011E7
0x1400011d6  xor     edx, edx; Tag
0x1400011d8  mov     rcx, rbp; P
0x1400011db  call    cs:__imp_ExFreePoolWithTag
0x1400011e2  nop     dword ptr [rax+rax+00h]
0x1400011e7  mov     rbp, [rsp+48h+arg_10]
0x1400011ec  mov     eax, ebx
0x1400011ee  mov     rbx, [rsp+48h+arg_8]
0x1400011f3  add     rsp, 20h
0x1400011f7  pop     r15
0x1400011f9  pop     r14
0x1400011fb  pop     r12
0x1400011fd  pop     rdi
0x1400011fe  pop     rsi
0x1400011ff  retn
0x140001201  mov     rdi, [rsp+48h+Urb]
0x140001206  xor     edx, edx; Val
0x140001208  movzx   ebx, word ptr [rsi+500h]
0x14000120f  mov     rcx, rdi; void *
0x140001212  mov     r8d, 98h; Size
0x140001218  call    memset
0x14000121d  lea     r8, [rbx+rbx*2]
0x140001221  xor     edx, edx; Val
0x140001223  shl     r8, 3; Size
0x140001227  mov     rcx, rbp; void *
0x14000122a  call    memset
0x14000122f  mov     dword ptr [rdi], 350030h
0x140001235  mov     rcx, rsi
0x140001238  mov     [rdi+18h], r12
0x14000123c  mov     [rdi+20h], ebx
0x14000123f  mov     dword ptr [rdi+24h], 180100h
0x140001246  mov     [rdi+28h], rbp
0x14000124a  mov     dil, 1
0x14000124d  mov     r8, [rsp+48h+Urb]
0x140001252  mov     r9b, dil
0x140001255  mov     rdx, [rsi+10h]
0x140001259  call    UaspSyncSendUsbRequestNew
0x14000125e  mov     ebx, eax
0x140001260  test    eax, eax
0x140001262  js      loc_1400011B8
0x140001268  mov     r8, [rsp+48h+Urb]
0x14000126d  movzx   eax, word ptr [rsi+500h]
0x140001274  mov     ecx, [r8+20h]
0x140001278  cmp     ecx, eax
0x14000127a  jbe     short loc_140001286
0x14000127c  mov     ebx, 0C000009Ch
0x140001281  jmp     loc_1400011BD
0x140001286  xor     r9b, r9b
0x140001289  test    ecx, ecx
0x14000128b  jz      short loc_1400012B6
0x14000128d  mov     rax, [r8+28h]
0x140001291  movzx   ecx, r9b
0x140001295  add     r9b, dil
0x140001298  lea     rdx, [rcx+rcx*2]
0x14000129c  mov     rax, [rax+rdx*8]
0x1400012a0  imul    rcx, 0E0h
0x1400012a7  mov     [rcx+r14+30h], rax
0x1400012ac  movzx   eax, r9b
0x1400012b0  cmp     eax, [r8+20h]
0x1400012b4  jb      short loc_14000128D
0x1400012b6  mov     [r8+18h], r15
0x1400012ba  mov     r9b, dil
0x1400012bd  mov     r8, [rsp+48h+Urb]
0x1400012c2  mov     rcx, rsi
0x1400012c5  mov     rdx, [rsi+10h]
0x1400012c9  call    UaspSyncSendUsbRequestNew
0x1400012ce  mov     ebx, eax
0x1400012d0  test    eax, eax
0x1400012d2  js      loc_1400011B8
0x1400012d8  mov     r8, [rsp+48h+Urb]
0x1400012dd  movzx   eax, word ptr [rsi+500h]
0x1400012e4  mov     ecx, [r8+20h]
0x1400012e8  cmp     ecx, eax
0x1400012ea  ja      short loc_14000127C
0x1400012ec  xor     r9b, r9b
0x1400012ef  test    ecx, ecx
0x1400012f1  jz      short loc_14000131C
0x1400012f3  mov     rax, [r8+28h]
0x1400012f7  movzx   ecx, r9b
0x1400012fb  add     r9b, dil
0x1400012fe  lea     rdx, [rcx+rcx*2]
0x140001302  mov     rax, [rax+rdx*8]
0x140001306  imul    rcx, 0E0h
0x14000130d  mov     [rcx+r14+38h], rax
0x140001312  movzx   eax, r9b
0x140001316  cmp     eax, [r8+20h]
0x14000131a  jb      short loc_1400012F3
0x14000131c  mov     rax, [rsp+48h+arg_20]
0x140001321  mov     r9b, dil
0x140001324  mov     [r8+18h], rax
0x140001328  mov     rcx, rsi
0x14000132b  mov     r8, [rsp+48h+Urb]
0x140001330  mov     rdx, [rsi+10h]
0x140001334  call    UaspSyncSendUsbRequestNew
0x140001339  mov     ebx, eax
0x14000133b  test    eax, eax
0x14000133d  js      loc_1400011B8
0x140001343  mov     r8, [rsp+48h+Urb]
0x140001348  movzx   eax, word ptr [rsi+500h]
0x14000134f  mov     ecx, [r8+20h]
0x140001353  cmp     ecx, eax
0x140001355  ja      loc_14000127C
0x14000135b  xor     r9b, r9b
0x14000135e  test    ecx, ecx
0x140001360  jz      loc_1400011BD
0x140001366  mov     rax, [r8+28h]
0x14000136a  movzx   ecx, r9b
0x14000136e  add     r9b, dil
0x140001371  lea     rdx, [rcx+rcx*2]
0x140001375  mov     rax, [rax+rdx*8]
0x140001379  imul    rcx, 0E0h
0x140001380  mov     [rcx+r14+40h], rax
0x140001385  movzx   eax, r9b
0x140001389  cmp     eax, [r8+20h]
0x14000138d  jb      short loc_140001366
0x14000138f  jmp     loc_1400011BD
```
