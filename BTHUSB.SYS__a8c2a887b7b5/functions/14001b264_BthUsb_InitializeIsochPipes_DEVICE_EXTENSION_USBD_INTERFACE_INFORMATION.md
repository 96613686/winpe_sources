# BthUsb_InitializeIsochPipes(_DEVICE_EXTENSION *,_USBD_INTERFACE_INFORMATION *)

- ea: `0x14001b264`
- end: `0x14001b307`
- name: `?BthUsb_InitializeIsochPipes@@_Y2PAGE@@AJPEAU_DEVICE_EXTENSION@@PEAU_USBD_INTERFACE_INFORMATION@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _USBD_INTERFACE_INFORMATION *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000ae54`
- `0x14001b840`

## callees

- `0x14001b264`

## pseudocode

```c
__int64 __fastcall BthUsb_InitializeIsochPipes(struct _DEVICE_EXTENSION *a1, struct _USBD_INTERFACE_INFORMATION *a2)
{
  _USBD_PIPE_INFORMATION *Pipes; // rax
  unsigned int NumberOfPipes; // ecx
  unsigned int v5; // r9d
  unsigned int v6; // r11d
  _USBD_PIPE_INFORMATION *v7; // r8
  unsigned int v8; // ecx
  unsigned int v9; // r8d

  Pipes = a2->Pipes;
  NumberOfPipes = a2->NumberOfPipes;
  v5 = 0;
  v6 = -1073741811;
  v7 = a2->Pipes;
  if ( NumberOfPipes )
  {
    while ( v7->PipeType != UsbdPipeTypeIsochronous || (v7->EndpointAddress & 0x80u) == 0 )
    {
      ++v5;
      ++v7;
      if ( v5 >= NumberOfPipes )
        return v6;
    }
    if ( v7 )
    {
      v8 = 0;
      *(_OWORD *)&a1->Pipes[3].MaximumPacketSize = *(_OWORD *)&v7->MaximumPacketSize;
      *(_QWORD *)&a1->Pipes[3].MaximumTransferSize = *(_QWORD *)&v7->MaximumTransferSize;
      v9 = a2->NumberOfPipes;
      if ( v9 )
      {
        while ( Pipes->PipeType != UsbdPipeTypeIsochronous || (Pipes->EndpointAddress & 0x80u) != 0 )
        {
          ++v8;
          ++Pipes;
          if ( v8 >= v9 )
            return v6;
        }
        if ( Pipes )
        {
          v6 = 0;
          *(_OWORD *)&a1->Pipes[4].MaximumPacketSize = *(_OWORD *)&Pipes->MaximumPacketSize;
          *(_QWORD *)&a1->Pipes[4].MaximumTransferSize = *(_QWORD *)&Pipes->MaximumTransferSize;
        }
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x14001b264  mov     r10, rcx
0x14001b267  lea     rax, [rdx+18h]
0x14001b26b  mov     ecx, [rdx+10h]
0x14001b26e  xor     r9d, r9d
0x14001b271  mov     r11d, 0C000000Dh
0x14001b277  mov     r8, rax
0x14001b27a  test    ecx, ecx
0x14001b27c  jz      loc_14001B303
0x14001b282  cmp     dword ptr [r8+4], 1
0x14001b287  jnz     short loc_14001B290
0x14001b289  cmp     byte ptr [r8+2], 0
0x14001b28e  jl      short loc_14001B29E
0x14001b290  inc     r9d
0x14001b293  add     r8, 18h
0x14001b297  cmp     r9d, ecx
0x14001b29a  jb      short loc_14001B282
0x14001b29c  jmp     short loc_14001B303
0x14001b29e  test    r8, r8
0x14001b2a1  jz      short loc_14001B303
0x14001b2a3  movups  xmm0, xmmword ptr [r8]
0x14001b2a7  xor     ecx, ecx
0x14001b2a9  movups  xmmword ptr [r10+0B8h], xmm0
0x14001b2b1  movsd   xmm1, qword ptr [r8+10h]
0x14001b2b7  movsd   qword ptr [r10+0C8h], xmm1
0x14001b2c0  mov     r8d, [rdx+10h]
0x14001b2c4  test    r8d, r8d
0x14001b2c7  jz      short loc_14001B303
0x14001b2c9  cmp     dword ptr [rax+4], 1
0x14001b2cd  jnz     short loc_14001B2D5
0x14001b2cf  cmp     byte ptr [rax+2], 0
0x14001b2d3  jge     short loc_14001B2E2
0x14001b2d5  inc     ecx
0x14001b2d7  add     rax, 18h
0x14001b2db  cmp     ecx, r8d
0x14001b2de  jb      short loc_14001B2C9
0x14001b2e0  jmp     short loc_14001B303
0x14001b2e2  test    rax, rax
0x14001b2e5  jz      short loc_14001B303
0x14001b2e7  movups  xmm0, xmmword ptr [rax]
0x14001b2ea  xor     r11d, r11d
0x14001b2ed  movups  xmmword ptr [r10+0D0h], xmm0
0x14001b2f5  movsd   xmm1, qword ptr [rax+10h]
0x14001b2fa  movsd   qword ptr [r10+0E0h], xmm1
0x14001b303  mov     eax, r11d
0x14001b306  retn
```
