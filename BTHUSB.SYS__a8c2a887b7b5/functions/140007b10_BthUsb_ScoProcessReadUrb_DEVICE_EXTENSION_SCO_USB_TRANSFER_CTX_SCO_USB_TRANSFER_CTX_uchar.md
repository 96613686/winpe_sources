# BthUsb_ScoProcessReadUrb(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *,_SCO_USB_TRANSFER_CTX *,uchar *)

- ea: `0x140007b10`
- end: `0x140007be2`
- name: `?BthUsb_ScoProcessReadUrb@@YAXPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_TRANSFER_CTX@@1PEAE@Z`
- size: `210`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *, struct _SCO_USB_TRANSFER_CTX *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140007b10`
- `0x1400085b4`
- `0x14000de00`

## pseudocode

```c
void __fastcall BthUsb_ScoProcessReadUrb(
        struct _DEVICE_EXTENSION *a1,
        struct _SCO_USB_TRANSFER_CTX *a2,
        struct _SCO_USB_TRANSFER_CTX *a3,
        unsigned __int8 *a4)
{
  struct _SCO_DATA_PACKET *v8; // rax
  unsigned __int16 v9; // dx
  _SCO_USB_CHANNEL *v10; // rcx
  int v11; // eax
  int (__fastcall *Callback)(void *, _BTH_SCO_MP_INDICATION_CODE, _BTH_SCO_MP_INDICATION_PARAMETERS *); // rax
  void *CallbackContext; // rcx
  unsigned int v14; // [rsp+30h] [rbp-68h] BYREF
  _QWORD v15[2]; // [rsp+38h] [rbp-60h] BYREF
  __int128 v16; // [rsp+48h] [rbp-50h]
  __int128 v17; // [rsp+58h] [rbp-40h]

  v14 = 0;
LABEL_2:
  while ( 1 )
  {
    v8 = BthUsb_ScoReconstructReadPackets(a1, (__int64)a2, a3, &v14, a4);
    if ( !v8 )
      break;
    v9 = 0;
    while ( 1 )
    {
      v10 = &a1->Sco.Channel[v9];
      if ( v10->ConnectionHandle == (*(_WORD *)v8 & 0xFFF) )
        break;
      if ( ++v9 >= 3u )
        goto LABEL_2;
    }
    if ( v10 )
    {
      v15[0] = v10->ConnectionHandle;
      v15[1] = (char *)v8 + 3;
      v11 = *((unsigned __int8 *)v8 + 2);
      v16 = 0;
      LODWORD(v16) = v11;
      Callback = v10->Callback;
      CallbackContext = v10->CallbackContext;
      v17 = 0;
      *((_QWORD *)&v16 + 1) = 0;
      Callback(CallbackContext, ScoMpIndicationRead, (_BTH_SCO_MP_INDICATION_PARAMETERS *)v15);
    }
  }
}

```

## disassembly

```asm
0x140007b10  push    rbx
0x140007b12  push    rbp
0x140007b13  push    rsi
0x140007b14  push    rdi
0x140007b15  sub     rsp, 78h
0x140007b19  mov     rdi, r9
0x140007b1c  mov     [rsp+98h+var_68], 0
0x140007b24  mov     rsi, r8
0x140007b27  mov     rbp, rdx
0x140007b2a  mov     rbx, rcx
0x140007b2d  lea     r9, [rsp+98h+var_68]; unsigned int *
0x140007b32  mov     [rsp+98h+var_78], rdi; unsigned __int8 *
0x140007b37  mov     r8, rsi; struct _SCO_USB_TRANSFER_CTX *
0x140007b3a  mov     rdx, rbp; struct _SCO_USB_TRANSFER_CTX *
0x140007b3d  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x140007b40  call    ?BthUsb_ScoReconstructReadPackets@@YAPEAU_SCO_DATA_PACKET@@PEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_TRANSFER_CTX@@1PEAKPEAE@Z; BthUsb_ScoReconstructReadPackets(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *,_SCO_USB_TRANSFER_CTX *,ulong *,uchar *)
0x140007b45  mov     r9, rax
0x140007b48  test    rax, rax
0x140007b4b  jz      loc_140007BD8
0x140007b51  movzx   r8d, word ptr [rax]
0x140007b55  mov     eax, 0FFFh
0x140007b5a  and     r8w, ax
0x140007b5e  xor     edx, edx
0x140007b60  movzx   ecx, dx
0x140007b63  imul    rcx, 98h
0x140007b6a  add     rcx, 2B0h
0x140007b71  add     rcx, rbx
0x140007b74  cmp     [rcx], r8w
0x140007b78  jz      short loc_140007B85
0x140007b7a  inc     dx
0x140007b7d  cmp     dx, 3
0x140007b81  jb      short loc_140007B60
0x140007b83  jmp     short loc_140007B2D
0x140007b85  test    rcx, rcx
0x140007b88  jz      short loc_140007B2D
0x140007b8a  movzx   eax, word ptr [rcx]
0x140007b8d  lea     r8, [rsp+98h+var_60]
0x140007b92  xorps   xmm0, xmm0
0x140007b95  xor     edx, edx
0x140007b97  movups  [rsp+98h+var_60], xmm0
0x140007b9c  mov     word ptr [rsp+98h+var_60], ax
0x140007ba1  lea     rax, [r9+3]
0x140007ba5  mov     qword ptr [rsp+98h+var_60+8], rax
0x140007baa  movzx   eax, byte ptr [r9+2]
0x140007baf  movups  [rsp+98h+var_50], xmm0
0x140007bb4  mov     dword ptr [rsp+98h+var_50], eax
0x140007bb8  mov     rax, [rcx+30h]
0x140007bbc  mov     rcx, [rcx+38h]
0x140007bc0  movups  [rsp+98h+var_40], xmm0
0x140007bc5  mov     qword ptr [rsp+98h+var_50+8], 0
0x140007bce  call    _guard_dispatch_icall
0x140007bd3  jmp     loc_140007B2D
0x140007bd8  add     rsp, 78h
0x140007bdc  pop     rdi
0x140007bdd  pop     rsi
0x140007bde  pop     rbp
0x140007bdf  pop     rbx
0x140007be0  retn
```
