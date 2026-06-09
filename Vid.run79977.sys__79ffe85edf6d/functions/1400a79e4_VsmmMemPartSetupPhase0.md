# VsmmMemPartSetupPhase0

- ea: `0x1400a79e4`
- end: `0x1400a7c34`
- name: `VsmmMemPartSetupPhase0`
- size: `592`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1400c0ccc`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x1400a7494`
- `0x1400a79e4`
- `0x1400a8cac`
- `0x1400bffc4`

## import_xrefs

- `ntoskrnl!ZwOpenPartition` at `0x1400a7a8d`
- `ntoskrnl!ZwOpenPartition` at `0x1400a7a8d`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1400a7b38`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1400a7b38`

## pseudocode

```c
__int64 __fastcall VsmmMemPartSetupPhase0(__int64 a1, const UNICODE_STRING *a2)
{
  char UseNonMirroredPartitionForVsmmp; // al
  char v5; // cl
  int v6; // ebx
  unsigned __int8 *v7; // rdx
  int *v8; // rax
  int v10; // [rsp+30h] [rbp-89h] BYREF
  int v11; // [rsp+34h] [rbp-85h] BYREF
  int v12; // [rsp+38h] [rbp-81h] BYREF
  _QWORD v13[2]; // [rsp+40h] [rbp-79h] BYREF
  _BYTE v14[48]; // [rsp+50h] [rbp-69h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+80h] [rbp-39h] BYREF
  _BYTE v16[16]; // [rsp+A0h] [rbp-19h] BYREF
  _BYTE v17[16]; // [rsp+B0h] [rbp-9h] BYREF
  int *v18; // [rsp+C0h] [rbp+7h]
  __int64 v19; // [rsp+C8h] [rbp+Fh]
  int *v20; // [rsp+D0h] [rbp+17h]
  __int64 v21; // [rsp+D8h] [rbp+1Fh]
  int *v22; // [rsp+E0h] [rbp+27h]
  __int64 v23; // [rsp+E8h] [rbp+2Fh]

  v13[0] = 4325440;
  v13[1] = L"\\KernelObjects\\NonMirroredMemory";
  memset(v14, 0, 44);
  if ( *(_DWORD *)(a1 + 28) )
    UseNonMirroredPartitionForVsmmp = VsmmMemReserveQueryUseNonMirroredPartitionForVsmmp();
  else
    UseNonMirroredPartitionForVsmmp = 1;
  v5 = 0;
  if ( (*(_DWORD *)(a1 + 160) & 0x40) == 0 )
    v5 = UseNonMirroredPartitionForVsmmp;
  if ( v5 )
  {
    *(_DWORD *)v14 = 48;
    *(_QWORD *)&v14[16] = v13;
    *(_QWORD *)&v14[8] = 0;
    *(_DWORD *)&v14[24] = 512;
    *(_OWORD *)&v14[32] = 0;
    ZwOpenPartition(a1 + 96, 2031619, v14);
  }
  if ( !*(_QWORD *)(a1 + 96) )
  {
    v6 = VsmmMemPartOpenSystemMemoryPartition(a1 + 96);
    if ( v6 < 0 )
    {
      if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        goto LABEL_18;
      tlgCreate1Sz_char(v16, "VsmmMemPartSetupPhase0");
      tlgCreate1Sz_char(v17, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c");
      v10 = 813;
      v18 = &v10;
      v7 = (unsigned __int8 *)&unk_14004CA7B;
      v20 = &v11;
      v12 = *(_DWORD *)(a1 + 28);
      v8 = &v12;
      goto LABEL_17;
    }
  }
  v6 = RtlDuplicateUnicodeString(0, a2, (PUNICODE_STRING)(a1 + 224));
  if ( v6 >= 0 )
    return 0;
  if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v16, "VsmmMemPartSetupPhase0");
    tlgCreate1Sz_char(v17, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c");
    v12 = 827;
    v18 = &v12;
    v7 = (unsigned __int8 *)&unk_14004C9CF;
    v20 = &v11;
    v10 = *(_DWORD *)(a1 + 28);
    v8 = &v10;
LABEL_17:
    v22 = v8;
    v19 = 4;
    v11 = v6;
    v21 = 4;
    v23 = 4;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140065110, v7, 0, 0, 7u, &v15);
  }
LABEL_18:
  VsmmMemPartTeardown(a1);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400a79e4  mov     [rsp-8+arg_10], rbx
0x1400a79e9  push    rbp
0x1400a79ea  push    rsi
0x1400a79eb  push    rdi
0x1400a79ec  lea     rbp, [rsp-47h]
0x1400a79f1  sub     rsp, 100h
0x1400a79f8  mov     rax, cs:__security_cookie
0x1400a79ff  xor     rax, rsp
0x1400a7a02  mov     [rbp+57h+var_20], rax
0x1400a7a06  xorps   xmm0, xmm0
0x1400a7a09  mov     [rbp+57h+var_D0], 420040h
0x1400a7a11  lea     rax, aKernelobjectsN; "\\KernelObjects\\NonMirroredMemory"
0x1400a7a18  mov     rsi, rdx
0x1400a7a1b  mov     [rbp+57h+var_C8], rax
0x1400a7a1f  mov     rdi, rcx
0x1400a7a22  xor     eax, eax
0x1400a7a24  mov     ebx, 40h ; '@'
0x1400a7a29  movups  [rbp+57h+var_B0], xmm0
0x1400a7a2d  movups  [rbp+57h+var_C0], xmm0
0x1400a7a31  movups  [rbp+57h+var_B0+0Ch], xmm0
0x1400a7a35  cmp     [rcx+1Ch], eax
0x1400a7a38  jnz     short loc_1400A7A3E
0x1400a7a3a  mov     al, 1
0x1400a7a3c  jmp     short loc_1400A7A43
0x1400a7a3e  call    VsmmMemReserveQueryUseNonMirroredPartitionForVsmmp
0x1400a7a43  mov     ecx, [rdi+0A0h]
0x1400a7a49  test    bl, cl
0x1400a7a4b  mov     ecx, 0
0x1400a7a50  movzx   eax, al
0x1400a7a53  cmovz   ecx, eax
0x1400a7a56  test    cl, cl
0x1400a7a58  jz      short loc_1400A7A99
0x1400a7a5a  lea     rax, [rbp+57h+var_D0]
0x1400a7a5e  mov     dword ptr [rbp+57h+var_C0], 30h ; '0'
0x1400a7a65  xorps   xmm0, xmm0
0x1400a7a68  mov     qword ptr [rbp+57h+var_B0], rax
0x1400a7a6c  lea     rcx, [rdi+60h]
0x1400a7a70  mov     qword ptr [rbp+57h+var_C0+8], 0
0x1400a7a78  lea     r8, [rbp+57h+var_C0]
0x1400a7a7c  mov     dword ptr [rbp+57h+var_B0+8], 200h
0x1400a7a83  mov     edx, 1F0003h
0x1400a7a88  movdqu  [rbp+57h+var_A0], xmm0
0x1400a7a8d  call    cs:__imp_ZwOpenPartition
0x1400a7a94  nop     dword ptr [rax+rax+00h]
0x1400a7a99  lea     rcx, [rdi+60h]
0x1400a7a9d  cmp     qword ptr [rcx], 0
0x1400a7aa1  jnz     loc_1400A7B2C
0x1400a7aa7  call    VsmmMemPartOpenSystemMemoryPartition
0x1400a7aac  mov     ebx, eax
0x1400a7aae  test    eax, eax
0x1400a7ab0  jns     short loc_1400A7B2C
0x1400a7ab2  mov     ecx, cs:dword_140065110
0x1400a7ab8  cmp     ecx, 2
0x1400a7abb  jbe     loc_1400A7C06
0x1400a7ac1  mov     edx, 100h
0x1400a7ac6  lea     rcx, dword_140065110
0x1400a7acd  call    _tlgKeywordOn
0x1400a7ad2  test    al, al
0x1400a7ad4  jz      loc_1400A7C06
0x1400a7ada  lea     rdx, aVsmmmempartset_3; "VsmmMemPartSetupPhase0"
0x1400a7ae1  lea     rcx, [rbp+57h+var_70]
0x1400a7ae5  call    _tlgCreate1Sz_char
0x1400a7aea  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a7af1  lea     rcx, [rbp+57h+var_60]
0x1400a7af5  call    _tlgCreate1Sz_char
0x1400a7afa  lea     rax, [rsp+110h+var_E0]
0x1400a7aff  mov     [rsp+110h+var_E0], 32Dh
0x1400a7b07  mov     [rbp+57h+var_50], rax
0x1400a7b0b  lea     rdx, unk_14004CA7B
0x1400a7b12  lea     rax, [rsp+110h+var_DC]
0x1400a7b17  mov     [rbp+57h+var_40], rax
0x1400a7b1b  mov     eax, [rdi+1Ch]
0x1400a7b1e  mov     [rsp+110h+var_D8], eax
0x1400a7b22  lea     rax, [rsp+110h+var_D8]
0x1400a7b27  jmp     loc_1400A7BC3
0x1400a7b2c  lea     r8, [rdi+0E0h]; StringOut
0x1400a7b33  mov     rdx, rsi; StringIn
0x1400a7b36  xor     ecx, ecx; Flags
0x1400a7b38  call    cs:__imp_RtlDuplicateUnicodeString
0x1400a7b3f  nop     dword ptr [rax+rax+00h]
0x1400a7b44  mov     ebx, eax
0x1400a7b46  test    eax, eax
0x1400a7b48  jns     loc_1400A7C10
0x1400a7b4e  mov     eax, cs:dword_140065110
0x1400a7b54  cmp     eax, 2
0x1400a7b57  jbe     loc_1400A7C06
0x1400a7b5d  mov     edx, 100h
0x1400a7b62  lea     rcx, dword_140065110
0x1400a7b69  call    _tlgKeywordOn
0x1400a7b6e  test    al, al
0x1400a7b70  jz      loc_1400A7C06
0x1400a7b76  lea     rdx, aVsmmmempartset_3; "VsmmMemPartSetupPhase0"
0x1400a7b7d  lea     rcx, [rbp+57h+var_70]
0x1400a7b81  call    _tlgCreate1Sz_char
0x1400a7b86  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a7b8d  lea     rcx, [rbp+57h+var_60]
0x1400a7b91  call    _tlgCreate1Sz_char
0x1400a7b96  lea     rax, [rsp+110h+var_D8]
0x1400a7b9b  mov     [rsp+110h+var_D8], 33Bh
0x1400a7ba3  mov     [rbp+57h+var_50], rax
0x1400a7ba7  lea     rdx, unk_14004C9CF
0x1400a7bae  lea     rax, [rsp+110h+var_DC]
0x1400a7bb3  mov     [rbp+57h+var_40], rax
0x1400a7bb7  mov     eax, [rdi+1Ch]
0x1400a7bba  mov     [rsp+110h+var_E0], eax
0x1400a7bbe  lea     rax, [rsp+110h+var_E0]
0x1400a7bc3  mov     [rbp+57h+var_30], rax
0x1400a7bc7  lea     rcx, dword_140065110
0x1400a7bce  lea     rax, [rbp+57h+var_90]
0x1400a7bd2  mov     [rbp+57h+var_48], 4
0x1400a7bda  mov     [rsp+110h+var_E8], rax
0x1400a7bdf  xor     r9d, r9d
0x1400a7be2  xor     r8d, r8d
0x1400a7be5  mov     [rsp+110h+var_F0], 7
0x1400a7bed  mov     [rsp+110h+var_DC], ebx
0x1400a7bf1  mov     [rbp+57h+var_38], 4
0x1400a7bf9  mov     [rbp+57h+var_28], 4
0x1400a7c01  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400a7c06  mov     rcx, rdi
0x1400a7c09  call    VsmmMemPartTeardown
0x1400a7c0e  jmp     short loc_1400A7C12
0x1400a7c10  xor     ebx, ebx
0x1400a7c12  mov     eax, ebx
0x1400a7c14  mov     rcx, [rbp+57h+var_20]
0x1400a7c18  xor     rcx, rsp; StackCookie
0x1400a7c1b  call    __security_check_cookie
0x1400a7c20  mov     rbx, [rsp+110h+arg_10]
0x1400a7c28  add     rsp, 100h
0x1400a7c2f  pop     rdi
0x1400a7c30  pop     rsi
0x1400a7c31  pop     rbp
0x1400a7c32  retn
```
