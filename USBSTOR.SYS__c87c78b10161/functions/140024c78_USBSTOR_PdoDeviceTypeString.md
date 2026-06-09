# USBSTOR_PdoDeviceTypeString

- ea: `0x140024c78`
- end: `0x140024cec`
- name: `USBSTOR_PdoDeviceTypeString`
- size: `116`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14001f1c4`
- `0x140023ab8`
- `0x140024a24`

## callees

- `0x140024c78`

## pseudocode

```c
const char *__fastcall USBSTOR_PdoDeviceTypeString(__int64 a1)
{
  __int64 v1; // rdx
  const char *result; // rax

  v1 = *(_QWORD *)(a1 + 64);
  if ( (*(_BYTE *)(v1 + 72) & 0x1F) != 0 )
  {
    switch ( *(_BYTE *)(v1 + 72) & 0x1F )
    {
      case 1:
        return "Sequential";
      case 4:
        return "Worm";
      case 5:
        return "CdRom";
      case 7:
        return "Optical";
      case 8:
        return "Changer";
      default:
        return "Other";
    }
  }
  else
  {
    result = "SFloppy";
    if ( !*(_BYTE *)(v1 + 69) )
      return "Disk";
  }
  return result;
}

```

## disassembly

```asm
0x140024c78  mov     rdx, [rcx+40h]
0x140024c7c  movzx   ecx, byte ptr [rdx+48h]
0x140024c80  and     ecx, 1Fh
0x140024c83  jz      short loc_140024CD4
0x140024c85  sub     ecx, 1
0x140024c88  jz      short loc_140024CCB
0x140024c8a  sub     ecx, 3
0x140024c8d  jz      short loc_140024CC2
0x140024c8f  sub     ecx, 1
0x140024c92  jz      short loc_140024CB9
0x140024c94  sub     ecx, 2
0x140024c97  jz      short loc_140024CB0
0x140024c99  cmp     ecx, 1
0x140024c9c  jz      short loc_140024CA7
0x140024c9e  lea     rax, aOther; "Other"
0x140024ca5  retn
0x140024ca7  lea     rax, aChanger; "Changer"
0x140024cae  retn
0x140024cb0  lea     rax, aOptical; "Optical"
0x140024cb7  retn
0x140024cb9  lea     rax, aCdrom; "CdRom"
0x140024cc0  retn
0x140024cc2  lea     rax, aWorm; "Worm"
0x140024cc9  retn
0x140024ccb  lea     rax, aSequential; "Sequential"
0x140024cd2  retn
0x140024cd4  mov     cl, [rdx+45h]
0x140024cd7  lea     rax, aSfloppy; "SFloppy"
0x140024cde  test    cl, cl
0x140024ce0  lea     rdx, aDisk; "Disk"
0x140024ce7  cmovz   rax, rdx
0x140024ceb  retn
```
