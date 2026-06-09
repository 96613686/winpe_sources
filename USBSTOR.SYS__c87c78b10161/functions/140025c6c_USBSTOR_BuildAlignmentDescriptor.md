# USBSTOR_BuildAlignmentDescriptor

- ea: `0x140025c6c`
- end: `0x140025d58`
- name: `USBSTOR_BuildAlignmentDescriptor`
- size: `236`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1400232d0`

## callees

- `0x1400105e8`
- `0x140010664`
- `0x140013a40`
- `0x140025c6c`
- `0x140025d60`

## pseudocode

```c
__int64 __fastcall USBSTOR_BuildAlignmentDescriptor(PDEVICE_OBJECT DeviceObject, void *a2, unsigned int *a3)
{
  _DWORD *DeviceExtension; // rdi
  int v7; // ebx
  unsigned int v8; // ecx
  unsigned int v9; // eax
  int Src; // [rsp+20h] [rbp-48h] BYREF
  __int64 v12; // [rsp+24h] [rbp-44h]
  int v13; // [rsp+2Ch] [rbp-3Ch]
  int v14; // [rsp+30h] [rbp-38h]
  int v15; // [rsp+34h] [rbp-34h]
  int v16; // [rsp+38h] [rbp-30h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  DeviceExtension = DeviceObject->DeviceExtension;
  v7 = USBSTOR_PopulateAlignmentInfo(DeviceObject);
  if ( v7 >= 0 )
  {
    v8 = 28;
    v14 = DeviceExtension[192];
    v15 = DeviceExtension[193];
    v16 = DeviceExtension[194];
    v9 = *a3;
    Src = 28;
    v12 = 28;
    v13 = 0;
    if ( v9 <= 0x1C )
      v8 = v9;
    else
      *a3 = 28;
    memmove(a2, &Src, v8);
    v7 = 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140025c6c  push    rbx
0x140025c6e  push    rbp
0x140025c6f  push    rsi
0x140025c70  push    rdi
0x140025c71  push    r14
0x140025c73  sub     rsp, 40h
0x140025c77  mov     rsi, r8
0x140025c7a  mov     rbp, rdx
0x140025c7d  mov     rbx, rcx
0x140025c80  mov     rcx, cs:WPP_GLOBAL_Control
0x140025c87  lea     r14, WPP_GLOBAL_Control
0x140025c8e  cmp     rcx, r14
0x140025c91  jz      short loc_140025CB5
0x140025c93  mov     eax, [rcx+2Ch]
0x140025c96  test    al, 10h
0x140025c98  jz      short loc_140025CB5
0x140025c9a  cmp     byte ptr [rcx+29h], 4
0x140025c9e  jb      short loc_140025CB5
0x140025ca0  mov     rcx, [rcx+18h]
0x140025ca4  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140025cab  mov     edx, 23h ; '#'
0x140025cb0  call    WPP_SF_
0x140025cb5  mov     rdi, [rbx+40h]
0x140025cb9  mov     rcx, rbx; DeviceObject
0x140025cbc  call    USBSTOR_PopulateAlignmentInfo
0x140025cc1  mov     ebx, eax
0x140025cc3  test    eax, eax
0x140025cc5  js      short loc_140025D19
0x140025cc7  mov     eax, [rdi+300h]
0x140025ccd  mov     ecx, 1Ch
0x140025cd2  mov     [rsp+68h+var_38], eax
0x140025cd6  mov     eax, [rdi+304h]
0x140025cdc  mov     [rsp+68h+var_34], eax
0x140025ce0  mov     eax, [rdi+308h]
0x140025ce6  mov     [rsp+68h+var_30], eax
0x140025cea  mov     eax, [rsi]
0x140025cec  mov     [rsp+68h+Src], ecx
0x140025cf0  mov     [rsp+68h+var_44], rcx
0x140025cf5  mov     [rsp+68h+var_3C], 0
0x140025cfd  cmp     eax, ecx
0x140025cff  jbe     short loc_140025D05
0x140025d01  mov     [rsi], ecx
0x140025d03  jmp     short loc_140025D07
0x140025d05  mov     ecx, eax
0x140025d07  mov     r8d, ecx; Size
0x140025d0a  lea     rdx, [rsp+68h+Src]; Src
0x140025d0f  mov     rcx, rbp; void *
0x140025d12  call    memmove
0x140025d17  xor     ebx, ebx
0x140025d19  mov     rcx, cs:WPP_GLOBAL_Control
0x140025d20  cmp     rcx, r14
0x140025d23  jz      short loc_140025D4A
0x140025d25  mov     eax, [rcx+2Ch]
0x140025d28  test    al, 10h
0x140025d2a  jz      short loc_140025D4A
0x140025d2c  cmp     byte ptr [rcx+29h], 5
0x140025d30  jb      short loc_140025D4A
0x140025d32  mov     rcx, [rcx+18h]
0x140025d36  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140025d3d  mov     edx, 24h ; '$'
0x140025d42  mov     r9d, ebx
0x140025d45  call    WPP_SF_d
0x140025d4a  mov     eax, ebx
0x140025d4c  add     rsp, 40h
0x140025d50  pop     r14
0x140025d52  pop     rdi
0x140025d53  pop     rsi
0x140025d54  pop     rbp
0x140025d55  pop     rbx
0x140025d56  retn
```
