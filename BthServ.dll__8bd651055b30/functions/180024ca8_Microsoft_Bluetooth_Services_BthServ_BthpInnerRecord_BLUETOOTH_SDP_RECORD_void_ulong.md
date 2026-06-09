# Microsoft::Bluetooth::Services::BthServ::BthpInnerRecord(_BLUETOOTH_SDP_RECORD *,void *,ulong *)

- ea: `0x180024ca8`
- end: `0x180024d75`
- name: `?BthpInnerRecord@BthServ@Services@Bluetooth@Microsoft@@YAPEAU_BLUETOOTH_SDP_RECORD@@PEAU5@PEAXPEAK@Z`
- size: `205`
- prototype: `struct _BLUETOOTH_SDP_RECORD *__fastcall(Microsoft::Bluetooth::Services::BthServ *__hidden this, struct _BLUETOOTH_SDP_RECORD *, void *, unsigned int *)`
- caller_count: `7`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022f30`
- `0x1800237e8`
- `0x180024738`
- `0x1800248ac`
- `0x180024e1c`
- `0x1800257dc`
- `0x180025e24`

## callees

- `0x180024ca8`
- `0x180024d7c`

## pseudocode

```c
struct _BLUETOOTH_SDP_RECORD *__fastcall Microsoft::Bluetooth::Services::BthServ::BthpInnerRecord(
        Microsoft::Bluetooth::Services::BthServ *this,
        struct _BLUETOOTH_SDP_RECORD *a2,
        unsigned __int32 *a3,
        unsigned int *a4)
{
  __int64 v6; // r11
  __int64 v7; // rcx
  unsigned __int32 v8; // eax

  if ( !(unsigned int)Microsoft::Bluetooth::Services::BthServ::BthpIsRecordSizeValid(this, a2, a3) )
    goto LABEL_22;
  switch ( *(_BYTE *)v6 & 7 )
  {
    case 0:
      if ( *(_BYTE *)v6 < 8u )
        goto LABEL_22;
      v8 = 1;
LABEL_19:
      v7 = v6 + 1;
      goto LABEL_20;
    case 1:
      v8 = 2;
      goto LABEL_19;
    case 2:
      v8 = 4;
      goto LABEL_19;
    case 3:
      v8 = 8;
      goto LABEL_19;
    case 4:
      v8 = 16;
      goto LABEL_19;
    case 5:
      v8 = *(unsigned __int8 *)(v6 + 1);
      v7 = v6 + 2;
      goto LABEL_20;
    case 6:
      v7 = v6 + 3;
      v8 = (unsigned __int16)__ROR2__(*(_WORD *)(v6 + 1), 8);
      goto LABEL_20;
  }
  if ( (*(_BYTE *)v6 & 7) != 7 )
  {
LABEL_22:
    v7 = 0;
    *a3 = 0;
    return (struct _BLUETOOTH_SDP_RECORD *)v7;
  }
  v7 = v6 + 5;
  v8 = _byteswap_ulong(*(_DWORD *)(v6 + 1));
LABEL_20:
  *a3 = v8;
  if ( v7 && v7 + (unsigned __int64)v8 > (unsigned __int64)a2 )
    goto LABEL_22;
  return (struct _BLUETOOTH_SDP_RECORD *)v7;
}

```

## disassembly

```asm
0x180024ca8  mov     [rsp+arg_0], rbx
0x180024cad  push    rdi
0x180024cae  sub     rsp, 20h
0x180024cb2  mov     rbx, r8
0x180024cb5  mov     rdi, rdx
0x180024cb8  mov     r11, rcx
0x180024cbb  call    ?BthpIsRecordSizeValid@BthServ@Services@Bluetooth@Microsoft@@YAHPEAU_BLUETOOTH_SDP_RECORD@@PEAX@Z; Microsoft::Bluetooth::Services::BthServ::BthpIsRecordSizeValid(_BLUETOOTH_SDP_RECORD *,void *)
0x180024cc0  xor     r8d, r8d
0x180024cc3  test    eax, eax
0x180024cc5  jz      loc_180024D61
0x180024ccb  movzx   edx, byte ptr [r11]
0x180024ccf  mov     ecx, edx
0x180024cd1  and     ecx, 7
0x180024cd4  jz      short loc_180024D3E
0x180024cd6  sub     ecx, 1
0x180024cd9  jz      short loc_180024D37
0x180024cdb  sub     ecx, 1
0x180024cde  jz      short loc_180024D30
0x180024ce0  sub     ecx, 1
0x180024ce3  jz      short loc_180024D29
0x180024ce5  sub     ecx, 1
0x180024ce8  jz      short loc_180024D22
0x180024cea  sub     ecx, 1
0x180024ced  jz      short loc_180024D17
0x180024cef  sub     ecx, 1
0x180024cf2  jz      short loc_180024D05
0x180024cf4  cmp     ecx, 1
0x180024cf7  jnz     short loc_180024D61
0x180024cf9  mov     eax, [r11+1]
0x180024cfd  lea     rcx, [r11+5]
0x180024d01  bswap   eax
0x180024d03  jmp     short loc_180024D50
0x180024d05  movzx   eax, word ptr [r11+1]
0x180024d0a  lea     rcx, [r11+3]
0x180024d0e  ror     ax, 8
0x180024d12  movzx   eax, ax
0x180024d15  jmp     short loc_180024D50
0x180024d17  movzx   eax, byte ptr [r11+1]
0x180024d1c  lea     rcx, [r11+2]
0x180024d20  jmp     short loc_180024D50
0x180024d22  mov     eax, 10h
0x180024d27  jmp     short loc_180024D4C
0x180024d29  mov     eax, 8
0x180024d2e  jmp     short loc_180024D4C
0x180024d30  mov     eax, 4
0x180024d35  jmp     short loc_180024D4C
0x180024d37  mov     eax, 2
0x180024d3c  jmp     short loc_180024D4C
0x180024d3e  mov     eax, 8
0x180024d43  cmp     dl, al
0x180024d45  jb      short loc_180024D61
0x180024d47  mov     eax, 1
0x180024d4c  lea     rcx, [r11+1]
0x180024d50  mov     [rbx], eax
0x180024d52  test    rcx, rcx
0x180024d55  jz      short loc_180024D67
0x180024d57  mov     eax, eax
0x180024d59  add     rax, rcx
0x180024d5c  cmp     rax, rdi
0x180024d5f  jbe     short loc_180024D67
0x180024d61  mov     rcx, r8
0x180024d64  mov     [rbx], r8d
0x180024d67  mov     rbx, [rsp+28h+arg_0]
0x180024d6c  mov     rax, rcx
0x180024d6f  add     rsp, 20h
0x180024d73  pop     rdi
0x180024d74  retn
```
