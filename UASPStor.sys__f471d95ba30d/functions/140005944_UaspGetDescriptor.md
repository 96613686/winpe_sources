# UaspGetDescriptor

- ea: `0x140005944`
- end: `0x140005aa3`
- name: `UaspGetDescriptor`
- size: `351`
- prototype: `__int64 __fastcall(__int64, __int64, char, char, __int16, int, unsigned int, PVOID *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140005aac`
- `0x140005be0`

## callees

- `0x140005944`
- `0x14000607c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140005a3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005a4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005a7c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005a3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005a4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005a7c`
- `ntoskrnl!ExAllocatePool2` at `0x140005988`
- `ntoskrnl!ExAllocatePool2` at `0x1400059ab`
- `ntoskrnl!ExAllocatePool2` at `0x140005988`
- `ntoskrnl!ExAllocatePool2` at `0x1400059ab`

## pseudocode

```c
__int64 __fastcall UaspGetDescriptor(
        __int64 a1,
        __int64 a2,
        char a3,
        char a4,
        __int16 a5,
        int a6,
        unsigned int a7,
        PVOID *a8)
{
  __int64 Pool2; // rax
  int v11; // ebp
  _DWORD *v12; // rsi
  int v13; // ebx

  *a8 = 0;
  Pool2 = ExAllocatePool2(64, a7, 1969320816);
  *a8 = (PVOID)Pool2;
  if ( !Pool2 )
  {
    v13 = -1073741670;
LABEL_13:
    if ( *a8 )
    {
      ExFreePoolWithTag(*a8, 0);
      *a8 = 0;
    }
    return (unsigned int)v13;
  }
  v11 = 2;
  v12 = (_DWORD *)ExAllocatePool2(64, 136, 1969320816);
  if ( v12 )
  {
    while ( 1 )
    {
      *((_QWORD *)v12 + 5) = *a8;
      *v12 = 721032;
      v12[9] = a7;
      *((_QWORD *)v12 + 6) = 0;
      *((_QWORD *)v12 + 7) = 0;
      *((_BYTE *)v12 + 131) = a3;
      *((_BYTE *)v12 + 130) = a4;
      *((_WORD *)v12 + 66) = a5;
      v13 = UaspSyncSendUsbRequestNew(0, a1, v12, 0);
      if ( v13 >= 0 )
      {
        if ( a7 == v12[9] && a3 == *((_BYTE *)*a8 + 1) )
        {
LABEL_8:
          ExFreePoolWithTag(v12, 0);
          goto LABEL_10;
        }
        v13 = -1073741668;
      }
      if ( !v11-- )
        goto LABEL_8;
    }
  }
  ExFreePoolWithTag(*a8, 0);
  *a8 = 0;
  v13 = -1073741670;
LABEL_10:
  if ( v13 < 0 )
    goto LABEL_13;
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140005944  mov     [rsp+arg_0], rcx
0x140005949  push    rbx
0x14000594a  push    rbp
0x14000594b  push    rsi
0x14000594c  push    rdi
0x14000594d  push    r12
0x14000594f  push    r13
0x140005951  push    r14
0x140005953  push    r15
0x140005955  sub     rsp, 28h
0x140005959  mov     rdi, [rsp+68h+arg_38]
0x140005961  mov     r15b, r8b
0x140005964  mov     r14d, [rsp+68h+arg_30]
0x14000596c  mov     ebx, 75617370h
0x140005971  mov     esi, 40h ; '@'
0x140005976  mov     edx, r14d
0x140005979  mov     r8d, ebx
0x14000597c  mov     ecx, esi
0x14000597e  mov     qword ptr [rdi], 0
0x140005985  mov     r13b, r9b
0x140005988  call    cs:__imp_ExAllocatePool2
0x14000598f  nop     dword ptr [rax+rax+00h]
0x140005994  mov     [rdi], rax
0x140005997  test    rax, rax
0x14000599a  jz      loc_140005A6D
0x1400059a0  mov     r8d, ebx
0x1400059a3  lea     edx, [rsi+48h]
0x1400059a6  mov     ecx, esi
0x1400059a8  lea     ebp, [rsi-3Eh]
0x1400059ab  call    cs:__imp_ExAllocatePool2
0x1400059b2  nop     dword ptr [rax+rax+00h]
0x1400059b7  mov     rsi, rax
0x1400059ba  test    rax, rax
0x1400059bd  jz      loc_140005A4A
0x1400059c3  movzx   r12d, [rsp+68h+arg_20]
0x1400059cc  mov     rax, [rdi]
0x1400059cf  xor     r9d, r9d
0x1400059d2  mov     rdx, [rsp+68h+arg_0]
0x1400059d7  mov     r8, rsi
0x1400059da  xor     ecx, ecx
0x1400059dc  mov     [rsi+28h], rax
0x1400059e0  mov     dword ptr [rsi], 0B0088h
0x1400059e6  mov     [rsi+24h], r14d
0x1400059ea  mov     qword ptr [rsi+30h], 0
0x1400059f2  mov     qword ptr [rsi+38h], 0
0x1400059fa  mov     [rsi+83h], r15b
0x140005a01  mov     [rsi+82h], r13b
0x140005a08  mov     [rsi+84h], r12w
0x140005a10  call    UaspSyncSendUsbRequestNew
0x140005a15  mov     ebx, eax
0x140005a17  test    eax, eax
0x140005a19  js      short loc_140005A2F
0x140005a1b  cmp     r14d, [rsi+24h]
0x140005a1f  jnz     short loc_140005A2A
0x140005a21  mov     rax, [rdi]
0x140005a24  cmp     r15b, [rax+1]
0x140005a28  jz      short loc_140005A37
0x140005a2a  mov     ebx, 0C000009Ch
0x140005a2f  mov     eax, ebp
0x140005a31  dec     ebp
0x140005a33  test    eax, eax
0x140005a35  jnz     short loc_1400059CC
0x140005a37  xor     edx, edx; Tag
0x140005a39  mov     rcx, rsi; P
0x140005a3c  call    cs:__imp_ExFreePoolWithTag
0x140005a43  nop     dword ptr [rax+rax+00h]
0x140005a48  jmp     short loc_140005A67
0x140005a4a  mov     rcx, [rdi]; P
0x140005a4d  xor     edx, edx; Tag
0x140005a4f  call    cs:__imp_ExFreePoolWithTag
0x140005a56  nop     dword ptr [rax+rax+00h]
0x140005a5b  mov     qword ptr [rdi], 0
0x140005a62  mov     ebx, 0C000009Ah
0x140005a67  test    ebx, ebx
0x140005a69  jns     short loc_140005A8F
0x140005a6b  jmp     short loc_140005A72
0x140005a6d  mov     ebx, 0C000009Ah
0x140005a72  mov     rcx, [rdi]; P
0x140005a75  test    rcx, rcx
0x140005a78  jz      short loc_140005A8F
0x140005a7a  xor     edx, edx; Tag
0x140005a7c  call    cs:__imp_ExFreePoolWithTag
0x140005a83  nop     dword ptr [rax+rax+00h]
0x140005a88  mov     qword ptr [rdi], 0
0x140005a8f  mov     eax, ebx
0x140005a91  add     rsp, 28h
0x140005a95  pop     r15
0x140005a97  pop     r14
0x140005a99  pop     r13
0x140005a9b  pop     r12
0x140005a9d  pop     rdi
0x140005a9e  pop     rsi
0x140005a9f  pop     rbp
0x140005aa0  pop     rbx
0x140005aa1  retn
```
