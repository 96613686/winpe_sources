# USBSTOR_GetDescriptor

- ea: `0x140026cec`
- end: `0x140026ed5`
- name: `USBSTOR_GetDescriptor`
- size: `489`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140029134`
- `0x1400293cc`

## callees

- `0x140001950`
- `0x1400105e8`
- `0x140010664`
- `0x140026cec`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140026d44`
- `ntoskrnl!ExAllocatePool2` at `0x140026d68`
- `ntoskrnl!ExAllocatePool2` at `0x140026d44`
- `ntoskrnl!ExAllocatePool2` at `0x140026d68`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026de1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026e9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026eb8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026de1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026e9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026eb8`

## pseudocode

```c
__int64 __fastcall USBSTOR_GetDescriptor(
        __int64 a1,
        __int64 a2,
        char a3,
        char a4,
        __int16 a5,
        __int64 a6,
        unsigned int a7,
        PVOID *a8)
{
  __int64 Pool2; // rax
  int v12; // r14d
  _DWORD *v13; // rsi
  int v14; // ebx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 155, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  *a8 = 0;
  Pool2 = ExAllocatePool2(64, a7, 1396788565);
  *a8 = (PVOID)Pool2;
  if ( !Pool2 )
  {
    v14 = -1073741670;
LABEL_21:
    if ( *a8 )
    {
      ExFreePoolWithTag(*a8, 0);
      *a8 = 0;
    }
    goto LABEL_9;
  }
  v12 = 2;
  v13 = (_DWORD *)ExAllocatePool2(64, 136, 1396788565);
  if ( v13 )
  {
    while ( 1 )
    {
      *((_QWORD *)v13 + 5) = *a8;
      *((_WORD *)v13 + 66) = a5;
      *v13 = 721032;
      v13[9] = a7;
      *((_QWORD *)v13 + 6) = 0;
      *((_QWORD *)v13 + 7) = 0;
      *((_BYTE *)v13 + 131) = a3;
      *((_BYTE *)v13 + 130) = a4;
      v14 = USBSTOR_SyncSendUsbRequest(a1, v13);
      if ( v14 >= 0 )
      {
        if ( a7 == v13[9] && a3 == *((_BYTE *)*a8 + 1) )
        {
LABEL_7:
          ExFreePoolWithTag(v13, 0);
          goto LABEL_8;
        }
        v14 = -1073741668;
      }
      if ( !v12-- )
        goto LABEL_7;
    }
  }
  ExFreePoolWithTag(*a8, 0);
  *a8 = 0;
  v14 = -1073741670;
LABEL_8:
  if ( v14 < 0 )
    goto LABEL_21;
LABEL_9:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 156, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140026cec  push    rbx
0x140026cee  push    rbp
0x140026cef  push    rsi
0x140026cf0  push    rdi
0x140026cf1  push    r12
0x140026cf3  push    r13
0x140026cf5  push    r14
0x140026cf7  push    r15
0x140026cf9  sub     rsp, 28h
0x140026cfd  mov     r12b, r9b
0x140026d00  mov     r15b, r8b
0x140026d03  mov     r13, rcx
0x140026d06  mov     rcx, cs:WPP_GLOBAL_Control
0x140026d0d  lea     rax, WPP_GLOBAL_Control
0x140026d14  cmp     rcx, rax
0x140026d17  jnz     loc_140026E31
0x140026d1d  mov     rdi, [rsp+68h+arg_38]
0x140026d25  mov     ebx, 53414D55h
0x140026d2a  mov     ebp, [rsp+68h+arg_30]
0x140026d31  mov     esi, 40h ; '@'
0x140026d36  mov     edx, ebp
0x140026d38  mov     r8d, ebx
0x140026d3b  mov     ecx, esi
0x140026d3d  mov     qword ptr [rdi], 0
0x140026d44  call    cs:__imp_ExAllocatePool2
0x140026d4b  nop     dword ptr [rax+rax+00h]
0x140026d50  mov     [rdi], rax
0x140026d53  test    rax, rax
0x140026d56  jz      loc_140026E88
0x140026d5c  mov     r8d, ebx
0x140026d5f  lea     edx, [rsi+48h]
0x140026d62  mov     ecx, esi
0x140026d64  lea     r14d, [rsi-3Eh]
0x140026d68  call    cs:__imp_ExAllocatePool2
0x140026d6f  nop     dword ptr [rax+rax+00h]
0x140026d74  mov     rsi, rax
0x140026d77  test    rax, rax
0x140026d7a  jz      loc_140026EB3
0x140026d80  mov     rax, [rdi]
0x140026d83  mov     rdx, rsi
0x140026d86  mov     [rsi+28h], rax
0x140026d8a  mov     rcx, r13
0x140026d8d  movzx   eax, [rsp+68h+arg_20]
0x140026d95  mov     [rsi+84h], ax
0x140026d9c  mov     dword ptr [rsi], 0B0088h
0x140026da2  mov     [rsi+24h], ebp
0x140026da5  mov     qword ptr [rsi+30h], 0
0x140026dad  mov     qword ptr [rsi+38h], 0
0x140026db5  mov     [rsi+83h], r15b
0x140026dbc  mov     [rsi+82h], r12b
0x140026dc3  call    USBSTOR_SyncSendUsbRequest
0x140026dc8  mov     ebx, eax
0x140026dca  test    eax, eax
0x140026dcc  js      short loc_140026E21
0x140026dce  cmp     ebp, [rsi+24h]
0x140026dd1  jnz     short loc_140026E1C
0x140026dd3  mov     rax, [rdi]
0x140026dd6  cmp     r15b, [rax+1]
0x140026dda  jnz     short loc_140026E1C
0x140026ddc  xor     edx, edx; Tag
0x140026dde  mov     rcx, rsi; P
0x140026de1  call    cs:__imp_ExFreePoolWithTag
0x140026de8  nop     dword ptr [rax+rax+00h]
0x140026ded  test    ebx, ebx
0x140026def  js      loc_140026E8D
0x140026df5  mov     rcx, cs:WPP_GLOBAL_Control
0x140026dfc  lea     rax, WPP_GLOBAL_Control
0x140026e03  cmp     rcx, rax
0x140026e06  jnz     short loc_140026E60
0x140026e08  mov     eax, ebx
0x140026e0a  add     rsp, 28h
0x140026e0e  pop     r15
0x140026e10  pop     r14
0x140026e12  pop     r13
0x140026e14  pop     r12
0x140026e16  pop     rdi
0x140026e17  pop     rsi
0x140026e18  pop     rbp
0x140026e19  pop     rbx
0x140026e1a  retn
0x140026e1c  mov     ebx, 0C000009Ch
0x140026e21  mov     eax, r14d
0x140026e24  dec     r14d
0x140026e27  test    eax, eax
0x140026e29  jnz     loc_140026D80
0x140026e2f  jmp     short loc_140026DDC
0x140026e31  mov     eax, [rcx+2Ch]
0x140026e34  test    al, 1
0x140026e36  jz      loc_140026D1D
0x140026e3c  cmp     byte ptr [rcx+29h], 4
0x140026e40  jb      loc_140026D1D
0x140026e46  mov     rcx, [rcx+18h]
0x140026e4a  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140026e51  mov     edx, 9Bh
0x140026e56  call    WPP_SF_
0x140026e5b  jmp     loc_140026D1D
0x140026e60  mov     edx, [rcx+2Ch]
0x140026e63  test    dl, 1
0x140026e66  jz      short loc_140026E08
0x140026e68  cmp     byte ptr [rcx+29h], 4
0x140026e6c  jb      short loc_140026E08
0x140026e6e  mov     rcx, [rcx+18h]
0x140026e72  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140026e79  mov     edx, 9Ch
0x140026e7e  mov     r9d, ebx
0x140026e81  call    WPP_SF_d
0x140026e86  jmp     short loc_140026E08
0x140026e88  mov     ebx, 0C000009Ah
0x140026e8d  mov     rcx, [rdi]; P
0x140026e90  test    rcx, rcx
0x140026e93  jz      loc_140026DF5
0x140026e99  xor     edx, edx; Tag
0x140026e9b  call    cs:__imp_ExFreePoolWithTag
0x140026ea2  nop     dword ptr [rax+rax+00h]
0x140026ea7  mov     qword ptr [rdi], 0
0x140026eae  jmp     loc_140026DF5
0x140026eb3  mov     rcx, [rdi]; P
0x140026eb6  xor     edx, edx; Tag
0x140026eb8  call    cs:__imp_ExFreePoolWithTag
0x140026ebf  nop     dword ptr [rax+rax+00h]
0x140026ec4  mov     qword ptr [rdi], 0
0x140026ecb  mov     ebx, 0C000009Ah
0x140026ed0  jmp     loc_140026DED
```
