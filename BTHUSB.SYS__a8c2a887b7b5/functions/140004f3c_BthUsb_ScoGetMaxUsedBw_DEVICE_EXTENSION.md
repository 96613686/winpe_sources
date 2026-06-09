# BthUsb_ScoGetMaxUsedBw(_DEVICE_EXTENSION *)

- ea: `0x140004f3c`
- end: `0x140004f88`
- name: `?BthUsb_ScoGetMaxUsedBw@@YAKPEAU_DEVICE_EXTENSION@@@Z`
- size: `76`
- prototype: `unsigned int __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400030e0`
- `0x140005180`

## callees

- `0x140004f3c`

## pseudocode

```c
__int64 __fastcall BthUsb_ScoGetMaxUsedBw(struct _DEVICE_EXTENSION *a1)
{
  unsigned int v1; // r8d
  __int64 i; // rdx
  __int64 v4; // rcx
  unsigned int RxBandwidth; // eax
  unsigned int TxBandwidth; // ecx

  v1 = 0;
  for ( i = 0; i != 3; ++i )
  {
    v4 = i;
    if ( a1->Sco.Channel[i].ConnectionHandle != 0xFFFF )
    {
      RxBandwidth = a1->Sco.Channel[v4].RxBandwidth;
      TxBandwidth = a1->Sco.Channel[v4].TxBandwidth;
      if ( v1 >= RxBandwidth )
        RxBandwidth = v1;
      v1 = RxBandwidth;
      if ( RxBandwidth < TxBandwidth )
        v1 = TxBandwidth;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x140004f3c  xor     r8d, r8d
0x140004f3f  mov     r9, rcx
0x140004f42  xor     edx, edx
0x140004f44  imul    rcx, rdx, 98h
0x140004f4b  mov     eax, 0FFFFh
0x140004f50  cmp     [rcx+r9+2B0h], ax
0x140004f59  jz      short loc_140004F7B
0x140004f5b  mov     eax, [rcx+r9+2C8h]
0x140004f63  cmp     r8d, eax
0x140004f66  mov     ecx, [rcx+r9+2C4h]
0x140004f6e  cmovnb  eax, r8d
0x140004f72  cmp     eax, ecx
0x140004f74  mov     r8d, eax
0x140004f77  cmovb   r8d, ecx
0x140004f7b  inc     rdx
0x140004f7e  cmp     rdx, 3
0x140004f82  jnz     short loc_140004F44
0x140004f84  mov     eax, r8d
0x140004f87  retn
```
