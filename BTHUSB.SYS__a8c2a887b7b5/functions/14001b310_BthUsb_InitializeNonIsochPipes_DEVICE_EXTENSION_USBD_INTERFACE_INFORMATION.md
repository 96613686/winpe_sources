# BthUsb_InitializeNonIsochPipes(_DEVICE_EXTENSION *,_USBD_INTERFACE_INFORMATION *)

- ea: `0x14001b310`
- end: `0x14001b3fa`
- name: `?BthUsb_InitializeNonIsochPipes@@_Y2PAGE@@AJPEAU_DEVICE_EXTENSION@@PEAU_USBD_INTERFACE_INFORMATION@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _USBD_INTERFACE_INFORMATION *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14001b840`

## callees

- `0x14001b310`

## pseudocode

```c
__int64 __fastcall BthUsb_InitializeNonIsochPipes(struct _DEVICE_EXTENSION *a1, struct _USBD_INTERFACE_INFORMATION *a2)
{
  _USBD_PIPE_INFORMATION *Pipes; // rax
  unsigned int v4; // ecx
  unsigned int NumberOfPipes; // edx
  unsigned int v7; // r11d
  _USBD_PIPE_INFORMATION *v8; // r8
  unsigned int v9; // edx
  _USBD_PIPE_INFORMATION *v10; // rcx
  unsigned int v11; // r8d
  __int64 v12; // xmm1_8
  unsigned int v13; // ecx
  unsigned int v14; // edx

  Pipes = a2->Pipes;
  v4 = 0;
  NumberOfPipes = a2->NumberOfPipes;
  v7 = -1073741811;
  v8 = Pipes;
  if ( NumberOfPipes )
  {
    while ( v8->PipeType != UsbdPipeTypeBulk || (v8->EndpointAddress & 0x80u) == 0 )
    {
      ++v4;
      ++v8;
      if ( v4 >= NumberOfPipes )
        return v7;
    }
    if ( v8 )
    {
      v9 = 0;
      v10 = Pipes;
      *(_OWORD *)&a1->Pipes[0].MaximumPacketSize = *(_OWORD *)&v8->MaximumPacketSize;
      *(_QWORD *)&a1->Pipes[0].MaximumTransferSize = *(_QWORD *)&v8->MaximumTransferSize;
      v11 = a2->NumberOfPipes;
      if ( v11 )
      {
        while ( v10->PipeType != UsbdPipeTypeBulk || (v10->EndpointAddress & 0x80u) != 0 )
        {
          ++v9;
          ++v10;
          if ( v9 >= v11 )
            return v7;
        }
        if ( v10 )
        {
          *(_OWORD *)&a1->Pipes[1].MaximumPacketSize = *(_OWORD *)&v10->MaximumPacketSize;
          v12 = *(_QWORD *)&v10->MaximumTransferSize;
          v13 = 0;
          *(_QWORD *)&a1->Pipes[1].MaximumTransferSize = v12;
          v14 = a2->NumberOfPipes;
          if ( v14 )
          {
            while ( Pipes->PipeType != UsbdPipeTypeInterrupt || (Pipes->EndpointAddress & 0x80u) == 0 )
            {
              ++v13;
              ++Pipes;
              if ( v13 >= v14 )
                return v7;
            }
            if ( Pipes )
            {
              v7 = 0;
              *(_OWORD *)&a1->Pipes[2].MaximumPacketSize = *(_OWORD *)&Pipes->MaximumPacketSize;
              *(_QWORD *)&a1->Pipes[2].MaximumTransferSize = *(_QWORD *)&Pipes->MaximumTransferSize;
            }
          }
        }
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x14001b310  lea     rax, [rdx+18h]
0x14001b314  mov     r9, rcx
0x14001b317  xor     ecx, ecx
0x14001b319  mov     r10, rdx
0x14001b31c  mov     edx, [rdx+10h]
0x14001b31f  mov     r11d, 0C000000Dh
0x14001b325  mov     r8, rax
0x14001b328  test    edx, edx
0x14001b32a  jz      loc_14001B3F6
0x14001b330  cmp     dword ptr [r8+4], 2
0x14001b335  jnz     short loc_14001B33E
0x14001b337  cmp     byte ptr [r8+2], 0
0x14001b33c  jl      short loc_14001B34D
0x14001b33e  inc     ecx
0x14001b340  add     r8, 18h
0x14001b344  cmp     ecx, edx
0x14001b346  jb      short loc_14001B330
0x14001b348  jmp     loc_14001B3F6
0x14001b34d  test    r8, r8
0x14001b350  jz      loc_14001B3F6
0x14001b356  movups  xmm0, xmmword ptr [r8]
0x14001b35a  xor     edx, edx
0x14001b35c  mov     rcx, rax
0x14001b35f  movups  xmmword ptr [r9+70h], xmm0
0x14001b364  movsd   xmm1, qword ptr [r8+10h]
0x14001b36a  movsd   qword ptr [r9+80h], xmm1
0x14001b373  mov     r8d, [r10+10h]
0x14001b377  test    r8d, r8d
0x14001b37a  jz      short loc_14001B3F6
0x14001b37c  cmp     dword ptr [rcx+4], 2
0x14001b380  jnz     short loc_14001B388
0x14001b382  cmp     byte ptr [rcx+2], 0
0x14001b386  jge     short loc_14001B395
0x14001b388  inc     edx
0x14001b38a  add     rcx, 18h
0x14001b38e  cmp     edx, r8d
0x14001b391  jb      short loc_14001B37C
0x14001b393  jmp     short loc_14001B3F6
0x14001b395  test    rcx, rcx
0x14001b398  jz      short loc_14001B3F6
0x14001b39a  movups  xmm0, xmmword ptr [rcx]
0x14001b39d  movups  xmmword ptr [r9+88h], xmm0
0x14001b3a5  movsd   xmm1, qword ptr [rcx+10h]
0x14001b3aa  xor     ecx, ecx
0x14001b3ac  movsd   qword ptr [r9+98h], xmm1
0x14001b3b5  mov     edx, [r10+10h]
0x14001b3b9  test    edx, edx
0x14001b3bb  jz      short loc_14001B3F6
0x14001b3bd  cmp     dword ptr [rax+4], 3
0x14001b3c1  jnz     short loc_14001B3C9
0x14001b3c3  cmp     byte ptr [rax+2], 0
0x14001b3c7  jl      short loc_14001B3D5
0x14001b3c9  inc     ecx
0x14001b3cb  add     rax, 18h
0x14001b3cf  cmp     ecx, edx
0x14001b3d1  jb      short loc_14001B3BD
0x14001b3d3  jmp     short loc_14001B3F6
0x14001b3d5  test    rax, rax
0x14001b3d8  jz      short loc_14001B3F6
0x14001b3da  movups  xmm0, xmmword ptr [rax]
0x14001b3dd  xor     r11d, r11d
0x14001b3e0  movups  xmmword ptr [r9+0A0h], xmm0
0x14001b3e8  movsd   xmm1, qword ptr [rax+10h]
0x14001b3ed  movsd   qword ptr [r9+0B0h], xmm1
0x14001b3f6  mov     eax, r11d
0x14001b3f9  retn
```
