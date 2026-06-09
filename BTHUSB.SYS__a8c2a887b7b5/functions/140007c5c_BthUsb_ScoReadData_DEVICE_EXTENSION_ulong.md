# BthUsb_ScoReadData(_DEVICE_EXTENSION *,ulong)

- ea: `0x140007c5c`
- end: `0x140007d7b`
- name: `?BthUsb_ScoReadData@@YAJPEAU_DEVICE_EXTENSION@@K@Z`
- size: `287`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400076e8`
- `0x140007da8`
- `0x1400081b0`

## callees

- `0x140005c8c`
- `0x140007c5c`
- `0x14000da00`

## pseudocode

```c
__int64 __fastcall BthUsb_ScoReadData(struct _DEVICE_EXTENSION *a1, unsigned int a2)
{
  unsigned int i; // ebp
  __int64 Item; // rax
  struct _SCO_USB_TRANSFER_CTX *v6; // r8
  __int64 v7; // rdx
  int v8; // r9d
  unsigned int v9; // r11d
  unsigned int v10; // r10d
  _DWORD *j; // rcx
  int MaximumPacketSize; // eax

  for ( i = 0; i < a2; ++i )
  {
    Item = ResourceQueue_GetItem(&a1->Sco.ReadCtxQueue);
    v6 = (struct _SCO_USB_TRANSFER_CTX *)Item;
    if ( !Item )
      break;
    v7 = *(_QWORD *)(Item + 72);
    v8 = 0;
    v9 = *(_DWORD *)(Item + 80);
    v10 = 0;
    *(_QWORD *)(Item + 56) = a1;
    *(_DWORD *)(Item + 96) = 3;
    for ( j = (_DWORD *)(v7 + 140); v10 < v9; j += 3 )
    {
      *j = v8;
      ++v10;
      MaximumPacketSize = a1->Pipes[3].MaximumPacketSize;
      j[1] = MaximumPacketSize;
      v8 += MaximumPacketSize;
      j[2] = 0;
    }
    *(_WORD *)(v7 + 2) = 10;
    *(_DWORD *)(v7 + 4) = 0;
    *(_QWORD *)(v7 + 8) = 0;
    *(_DWORD *)(v7 + 16) = 0;
    *(_WORD *)v7 = 12 * v9 + 152;
    *(_QWORD *)(v7 + 24) = a1->Pipes[3].PipeHandle;
    *(_DWORD *)(v7 + 32) = 3;
    *(_DWORD *)(v7 + 36) = v8;
    *(_QWORD *)(v7 + 40) = v6->TransferBuffer;
    *(_QWORD *)(v7 + 48) = v6->TransferMdl;
    *(_QWORD *)(v7 + 56) = 0;
    *(_DWORD *)(v7 + 128) = 0;
    *(_DWORD *)(v7 + 132) = v9;
    *(_DWORD *)(v7 + 136) = 0;
    BthUsb_ScoUrbStart(a1, &a1->Sco.ReadPipeObj, v6);
  }
  return 259;
}

```

## disassembly

```asm
0x140007c5c  push    rbx
0x140007c5e  push    rbp
0x140007c5f  push    rsi
0x140007c60  push    rdi
0x140007c61  sub     rsp, 28h
0x140007c65  xor     ebp, ebp
0x140007c67  mov     edi, edx
0x140007c69  mov     rbx, rcx
0x140007c6c  test    edx, edx
0x140007c6e  jz      loc_140007D6C
0x140007c74  lea     rcx, [rbx+198h]
0x140007c7b  call    ResourceQueue_GetItem
0x140007c80  mov     r8, rax; struct _SCO_USB_TRANSFER_CTX *
0x140007c83  test    rax, rax
0x140007c86  jz      loc_140007D6C
0x140007c8c  mov     rdx, [rax+48h]
0x140007c90  xor     r9d, r9d
0x140007c93  mov     r11d, [rax+50h]
0x140007c97  xor     r10d, r10d
0x140007c9a  mov     [rax+38h], rbx
0x140007c9e  mov     dword ptr [rax+60h], 3
0x140007ca5  lea     rcx, [rdx+8Ch]
0x140007cac  test    r11d, r11d
0x140007caf  jz      short loc_140007CD4
0x140007cb1  mov     [rcx], r9d
0x140007cb4  inc     r10d
0x140007cb7  movzx   eax, word ptr [rbx+0B8h]
0x140007cbe  mov     [rcx+4], eax
0x140007cc1  add     r9d, eax
0x140007cc4  mov     dword ptr [rcx+8], 0
0x140007ccb  lea     rcx, [rcx+0Ch]
0x140007ccf  cmp     r10d, r11d
0x140007cd2  jb      short loc_140007CB1
0x140007cd4  movzx   eax, r11w
0x140007cd8  mov     word ptr [rdx+2], 0Ah
0x140007cde  add     ax, ax
0x140007ce1  mov     dword ptr [rdx+4], 0
0x140007ce8  mov     qword ptr [rdx+8], 0
0x140007cf0  mov     dword ptr [rdx+10h], 0
0x140007cf7  lea     ecx, [rax+r11]
0x140007cfb  mov     eax, 98h
0x140007d00  shl     cx, 2
0x140007d04  add     cx, ax
0x140007d07  mov     [rdx], cx
0x140007d0a  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x140007d0d  mov     rax, [rbx+0C0h]
0x140007d14  mov     [rdx+18h], rax
0x140007d18  mov     dword ptr [rdx+20h], 3
0x140007d1f  mov     [rdx+24h], r9d
0x140007d23  mov     rax, [r8+68h]
0x140007d27  mov     [rdx+28h], rax
0x140007d2b  mov     rax, [r8+70h]
0x140007d2f  mov     [rdx+30h], rax
0x140007d33  mov     qword ptr [rdx+38h], 0
0x140007d3b  mov     dword ptr [rdx+80h], 0
0x140007d45  mov     [rdx+84h], r11d
0x140007d4c  mov     dword ptr [rdx+88h], 0
0x140007d56  lea     rdx, [rbx+1F8h]; struct _SCO_USB_PIPE_OBJ *
0x140007d5d  call    ?BthUsb_ScoUrbStart@@YAJPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_PIPE_OBJ@@PEAU_SCO_USB_TRANSFER_CTX@@@Z; BthUsb_ScoUrbStart(_DEVICE_EXTENSION *,_SCO_USB_PIPE_OBJ *,_SCO_USB_TRANSFER_CTX *)
0x140007d62  inc     ebp
0x140007d64  cmp     ebp, edi
0x140007d66  jb      loc_140007C74
0x140007d6c  mov     eax, 103h
0x140007d71  add     rsp, 28h
0x140007d75  pop     rdi
0x140007d76  pop     rsi
0x140007d77  pop     rbp
0x140007d78  pop     rbx
0x140007d79  retn
```
