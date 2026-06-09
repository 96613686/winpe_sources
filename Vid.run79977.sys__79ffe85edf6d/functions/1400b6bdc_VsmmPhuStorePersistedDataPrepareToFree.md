# VsmmPhuStorePersistedDataPrepareToFree

- ea: `0x1400b6bdc`
- end: `0x1400b7067`
- name: `VsmmPhuStorePersistedDataPrepareToFree`
- size: `1163`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400a18c0`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x14002f724`
- `0x1400b6bdc`
- `0x1400b7490`
- `0x1400b7550`
- `0x1400b95f0`
- `0x1400b9fac`
- `0x1400e9394`
- `0x1400f4f7c`

## import_xrefs

- `ntoskrnl!RtlRbInsertNodeEx` at `0x1400b6ea1`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x1400b6ea1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b6f39`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b6f39`
- `ntoskrnl!ExAllocatePool2` at `0x1400b6df4`
- `ntoskrnl!ExAllocatePool2` at `0x1400b6df4`
- `winhvr!WinHvUnlinkPreExistingPartition` at `0x1400b6f7a`
- `winhvr!WinHvUnlinkPreExistingPartition` at `0x1400b6f7a`
- `winhvr!WinHvCreatePartition` at `0x1400b6ca3`
- `winhvr!WinHvCreatePartition` at `0x1400b6ca3`

## pseudocode

```c
__int64 __fastcall VsmmPhuStorePersistedDataPrepareToFree(__int64 a1)
{
  __int64 v2; // rcx
  unsigned __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 *v5; // rdi
  int Partition; // ebx
  void *v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rcx
  unsigned __int64 v11; // rdi
  _QWORD *v12; // rdx
  __int64 v13; // rdi
  unsigned __int64 v14; // rax
  __int64 v15; // rbx
  __int64 Pool2; // r13
  __int64 v17; // r9
  int v18; // eax
  __int64 v19; // r8
  unsigned __int64 v20; // rbx
  int v21; // r15d
  unsigned __int64 v22; // rax
  __int128 *v24; // [rsp+20h] [rbp-E0h]
  char v25; // [rsp+50h] [rbp-B0h]
  int v26; // [rsp+54h] [rbp-ACh] BYREF
  int v27; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v29; // [rsp+68h] [rbp-98h] BYREF
  __int64 v30; // [rsp+78h] [rbp-88h]
  char v31[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v32[16]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v33[16]; // [rsp+B0h] [rbp-50h] BYREF
  int *v34; // [rsp+C0h] [rbp-40h]
  __int64 v35; // [rsp+C8h] [rbp-38h]
  int *v36; // [rsp+D0h] [rbp-30h]
  __int64 v37; // [rsp+D8h] [rbp-28h]
  __int64 v38; // [rsp+E0h] [rbp-20h]
  __int64 v39; // [rsp+E8h] [rbp-18h]
  __int64 *v40; // [rsp+F0h] [rbp-10h]
  __int64 v41; // [rsp+F8h] [rbp-8h]

  v30 = 0;
  v2 = a1 + 1128;
  v25 = 0;
  v29 = 0;
  if ( *(_BYTE *)(v2 + 48) )
  {
    v3 = *(_QWORD *)(v2 + 40);
    if ( ((v3 >> 10) & 0xF) - 2 <= 2 || (v3 & 0xC000) == 0x4000 )
    {
      VsmmPhuStorepCreationPropertiesDeserialize(v2, &v29);
      v5 = (__int64 *)(v4 + 56);
      v24 = &v29;
      Partition = WinHvCreatePartition(*(_QWORD *)v4, 4, 0x80000000LL, *(unsigned int *)(v4 + 8));
      if ( Partition < 0 )
      {
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v32, "VsmmPhuStorePersistedDataPrepareToFree");
          tlgCreate1Sz_char(v33, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
          v26 = 2593;
          v34 = &v26;
          v7 = &unk_14005026E;
          v35 = 4;
          v36 = &v27;
          v38 = a1 + 48;
          v8 = *v5;
          v27 = Partition;
          v37 = 4;
          goto LABEL_57;
        }
        goto LABEL_58;
      }
      v25 = 1;
    }
  }
  v9 = *(_QWORD *)(a1 + 1256);
  if ( (v9 & 1) != 0 )
  {
    if ( v9 == 1 )
      return 0;
    v10 = v9 ^ ((a1 + 1248) | 1);
  }
  else
  {
    v10 = *(_QWORD *)(a1 + 1256);
  }
  if ( !v10 )
    return 0;
  while ( 1 )
  {
    v11 = *(_QWORD *)(v10 + 8);
    if ( v11 )
    {
      v12 = *(_QWORD **)v11;
      if ( *(_QWORD *)v11 )
      {
        do
        {
          v11 = (unsigned __int64)v12;
          v12 = (_QWORD *)*v12;
        }
        while ( v12 );
      }
    }
    else
    {
      v13 = *(_QWORD *)(v10 + 16);
      v14 = v10;
      while ( 1 )
      {
        v11 = v13 & 0xFFFFFFFFFFFFFFFCuLL;
        if ( !v11 || *(_QWORD *)v11 == v14 )
          break;
        v14 = v11;
        v13 = *(_QWORD *)(v11 + 16);
      }
    }
    if ( *(_DWORD *)(v10 + 32) != 2 )
      goto LABEL_41;
    v15 = v10 + 40;
    if ( (*(_BYTE *)(v10 + 73) & 1) == 0 )
      goto LABEL_41;
    if ( ((*(_BYTE *)(v10 + 64) & 0x10) == 0 || !*(_QWORD *)(v10 + 152))
      && !(unsigned __int8)VsmmPhuStorepMemoryFreeNeedsPreprocessing(a1, v10 + 40) )
    {
      goto LABEL_41;
    }
    Pool2 = ExAllocatePool2(256, 88, 1833788502);
    if ( !Pool2 )
      break;
    v17 = *(_QWORD *)(v15 + 40);
    v28 = v15 + 40;
    v18 = VsmmPhysicalBufferSetupRestore(0, (int)a1 + 48, 2, v17, (int)v24, (void *)(Pool2 + 24));
    Partition = v18;
    if ( v18 < 0 )
    {
      VidTraceErrorStatusInternal0(
        "VsmmPhuStorePersistedDataPrepareToFree",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
        2644,
        (unsigned int)v18);
      VsmmPhysicalBufferTeardown(Pool2 + 24);
      ExFreePoolWithTag((PVOID)Pool2, 0x6D4D6456u);
      goto LABEL_52;
    }
    v20 = *(_QWORD *)(a1 + 1360);
    if ( (*(_BYTE *)(a1 + 1368) & 1) != 0 )
    {
      if ( v20 )
        v20 ^= a1 + 1360;
      else
        v20 = 0;
    }
    LOBYTE(v19) = 0;
    v21 = *(_BYTE *)(a1 + 1368) & 1;
    if ( v20 )
    {
      while ( 1 )
      {
        if ( (int)VsmmPhuStorepPhysicalBufferCompareByBlockId(v28, v20, v19) < 0 )
        {
          v22 = *(_QWORD *)v20;
          if ( v21 )
          {
            if ( !v22 )
              goto LABEL_49;
            v22 ^= v20;
          }
          if ( !v22 )
          {
LABEL_49:
            LOBYTE(v19) = 0;
            break;
          }
        }
        else
        {
          v22 = *(_QWORD *)(v20 + 8);
          if ( v21 )
          {
            if ( !v22 )
              goto LABEL_39;
            v22 ^= v20;
          }
          if ( !v22 )
          {
LABEL_39:
            LOBYTE(v19) = 1;
            break;
          }
        }
        v20 = v22;
      }
    }
    RtlRbInsertNodeEx(a1 + 1360, v20, v19, Pool2);
LABEL_41:
    v10 = v11;
    if ( !v11 )
      return 0;
  }
  Partition = -1073741670;
  VidTraceErrorStatusInternal0(
    "VsmmPhuStorePersistedDataPrepareToFree",
    "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
    2630,
    3221225626LL);
LABEL_52:
  if ( v25 )
  {
    Partition = WinHvUnlinkPreExistingPartition(*(_QWORD *)(a1 + 1184));
    if ( Partition < 0 && (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v32, "VsmmPhuStorePersistedDataPrepareToFree");
      tlgCreate1Sz_char(v33, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
      v27 = 2679;
      v34 = &v27;
      v7 = &unk_140050214;
      v35 = 4;
      v36 = &v26;
      v38 = a1 + 48;
      v8 = *(_QWORD *)(a1 + 1184);
      v26 = Partition;
      v37 = 4;
LABEL_57:
      v28 = v8;
      v40 = &v28;
      v39 = 16;
      v41 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v7, 0, 0, 8, v31);
    }
  }
LABEL_58:
  VsmmPhuStorepCleanupPhysicalMemoryTable(a1);
  return (unsigned int)Partition;
}

```

## disassembly

```asm
0x1400b6bdc  mov     [rsp-8+arg_8], rbx
0x1400b6be1  mov     [rsp-8+arg_10], rsi
0x1400b6be6  push    rbp
0x1400b6be7  push    rdi
0x1400b6be8  push    r13
0x1400b6bea  push    r14
0x1400b6bec  push    r15
0x1400b6bee  lea     rbp, [rsp-10h]
0x1400b6bf3  sub     rsp, 110h
0x1400b6bfa  mov     rax, cs:__security_cookie
0x1400b6c01  xor     rax, rsp
0x1400b6c04  mov     [rbp+30h+var_30], rax
0x1400b6c08  xor     eax, eax
0x1400b6c0a  xor     r15d, r15d
0x1400b6c0d  mov     rsi, rcx
0x1400b6c10  mov     [rsp+130h+var_B8], rax
0x1400b6c15  add     rcx, 468h
0x1400b6c1c  mov     [rsp+130h+var_E0], r15b
0x1400b6c21  xorps   xmm0, xmm0
0x1400b6c24  movups  [rsp+130h+var_C8], xmm0
0x1400b6c29  lea     r14d, [rax+4]
0x1400b6c2d  cmp     [rcx+30h], r15b
0x1400b6c31  jz      loc_1400B6D43
0x1400b6c37  mov     rdx, [rcx+28h]
0x1400b6c3b  mov     rax, rdx
0x1400b6c3e  shr     rax, 0Ah
0x1400b6c42  and     eax, 0Fh
0x1400b6c45  sub     rax, 2
0x1400b6c49  cmp     rax, 2
0x1400b6c4d  jbe     short loc_1400B6C62
0x1400b6c4f  and     edx, 0C000h
0x1400b6c55  cmp     rdx, 4000h
0x1400b6c5c  jnz     loc_1400B6D43
0x1400b6c62  lea     rdx, [rsp+130h+var_C8]
0x1400b6c67  call    VsmmPhuStorepCreationPropertiesDeserialize
0x1400b6c6c  mov     r9d, [rcx+8]
0x1400b6c70  lea     rdi, [rcx+38h]
0x1400b6c74  mov     rcx, [rcx]
0x1400b6c77  lea     rax, [rsp+130h+var_C8]
0x1400b6c7c  mov     [rsp+130h+var_E8], r15
0x1400b6c81  mov     r8d, 80000000h
0x1400b6c87  mov     [rsp+130h+var_F0], r15
0x1400b6c8c  mov     rdx, r14
0x1400b6c8f  mov     [rsp+130h+var_F8], r15
0x1400b6c94  mov     [rsp+130h+var_100], r15
0x1400b6c99  mov     [rsp+130h+var_108], rdi
0x1400b6c9e  mov     [rsp+130h+var_110], rax
0x1400b6ca3  call    cs:__imp_WinHvCreatePartition
0x1400b6caa  nop     dword ptr [rax+rax+00h]
0x1400b6caf  mov     ebx, eax
0x1400b6cb1  test    eax, eax
0x1400b6cb3  jns     loc_1400B6D3E
0x1400b6cb9  mov     ecx, cs:dword_140065110
0x1400b6cbf  cmp     ecx, 2
0x1400b6cc2  jbe     loc_1400B705A
0x1400b6cc8  mov     edx, 100h
0x1400b6ccd  lea     rcx, dword_140065110
0x1400b6cd4  call    _tlgKeywordOn
0x1400b6cd9  test    al, al
0x1400b6cdb  jz      loc_1400B705A
0x1400b6ce1  lea     rdx, aVsmmphustorepe; "VsmmPhuStorePersistedDataPrepareToFree"
0x1400b6ce8  lea     rcx, [rbp+30h+var_90]
0x1400b6cec  call    _tlgCreate1Sz_char
0x1400b6cf1  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b6cf8  lea     rcx, [rbp+30h+var_80]
0x1400b6cfc  call    _tlgCreate1Sz_char
0x1400b6d01  lea     rax, [rsp+130h+var_DC]
0x1400b6d06  mov     [rsp+130h+var_DC], 0A21h
0x1400b6d0e  mov     [rbp+30h+var_70], rax
0x1400b6d12  lea     rdx, unk_14005026E
0x1400b6d19  lea     rax, [rsp+130h+var_D8]
0x1400b6d1e  mov     [rbp+30h+var_68], r14
0x1400b6d22  mov     [rbp+30h+var_60], rax
0x1400b6d26  lea     rax, [rsi+30h]
0x1400b6d2a  mov     [rbp+30h+var_50], rax
0x1400b6d2e  mov     rax, [rdi]
0x1400b6d31  mov     [rsp+130h+var_D8], ebx
0x1400b6d35  mov     [rbp+30h+var_58], r14
0x1400b6d39  jmp     loc_1400B701C
0x1400b6d3e  mov     [rsp+130h+var_E0], 1
0x1400b6d43  lea     rcx, [rsi+4E0h]
0x1400b6d4a  mov     rax, [rcx+8]
0x1400b6d4e  test    al, 1
0x1400b6d50  jz      short loc_1400B6D65
0x1400b6d52  cmp     rax, 1
0x1400b6d56  jz      loc_1400B6EB9
0x1400b6d5c  or      rcx, 1
0x1400b6d60  xor     rcx, rax
0x1400b6d63  jmp     short loc_1400B6D68
0x1400b6d65  mov     rcx, rax
0x1400b6d68  test    rcx, rcx
0x1400b6d6b  jz      loc_1400B6EB9
0x1400b6d71  mov     rdi, [rcx+8]
0x1400b6d75  test    rdi, rdi
0x1400b6d78  jz      short loc_1400B6D92
0x1400b6d7a  mov     rdx, [rdi]
0x1400b6d7d  test    rdx, rdx
0x1400b6d80  jz      short loc_1400B6DAD
0x1400b6d82  mov     rax, [rdx]
0x1400b6d85  mov     rdi, rdx
0x1400b6d88  mov     rdx, rax
0x1400b6d8b  test    rax, rax
0x1400b6d8e  jnz     short loc_1400B6D82
0x1400b6d90  jmp     short loc_1400B6DAD
0x1400b6d92  mov     rdi, [rcx+10h]
0x1400b6d96  mov     rax, rcx
0x1400b6d99  jmp     short loc_1400B6DA7
0x1400b6d9b  cmp     [rdi], rax
0x1400b6d9e  jz      short loc_1400B6DAD
0x1400b6da0  mov     rax, rdi
0x1400b6da3  mov     rdi, [rdi+10h]
0x1400b6da7  and     rdi, 0FFFFFFFFFFFFFFFCh
0x1400b6dab  jnz     short loc_1400B6D9B
0x1400b6dad  cmp     dword ptr [rcx+20h], 2
0x1400b6db1  jnz     loc_1400B6EAD
0x1400b6db7  lea     rbx, [rcx+28h]
0x1400b6dbb  test    byte ptr [rbx+21h], 1
0x1400b6dbf  jz      loc_1400B6EAD
0x1400b6dc5  test    byte ptr [rbx+18h], 10h
0x1400b6dc9  jz      short loc_1400B6DD1
0x1400b6dcb  cmp     [rbx+70h], r15
0x1400b6dcf  jnz     short loc_1400B6DE4
0x1400b6dd1  mov     rdx, rbx
0x1400b6dd4  mov     rcx, rsi
0x1400b6dd7  call    VsmmPhuStorepMemoryFreeNeedsPreprocessing
0x1400b6ddc  test    al, al
0x1400b6dde  jz      loc_1400B6EAD
0x1400b6de4  mov     edx, 58h ; 'X'
0x1400b6de9  mov     ecx, 100h
0x1400b6dee  mov     r8d, 6D4D6456h
0x1400b6df4  call    cs:__imp_ExAllocatePool2
0x1400b6dfb  nop     dword ptr [rax+rax+00h]
0x1400b6e00  mov     r13, rax
0x1400b6e03  test    rax, rax
0x1400b6e06  jz      loc_1400B6F47
0x1400b6e0c  lea     rax, [rbx+28h]
0x1400b6e10  mov     r9, [rax]; int
0x1400b6e13  lea     rcx, [r13+18h]
0x1400b6e17  mov     [rsp+130h+var_108], rcx; void *
0x1400b6e1c  lea     rdx, [rsi+30h]; int
0x1400b6e20  xor     ecx, ecx; int
0x1400b6e22  mov     [rsp+130h+var_D0], rax
0x1400b6e27  lea     r8d, [rcx+2]; int
0x1400b6e2b  call    VsmmPhysicalBufferSetupRestore
0x1400b6e30  mov     ebx, eax
0x1400b6e32  test    eax, eax
0x1400b6e34  js      loc_1400B6F0C
0x1400b6e3a  test    byte ptr [rsi+558h], 1
0x1400b6e41  lea     r14, [rsi+550h]
0x1400b6e48  mov     rbx, [r14]
0x1400b6e4b  jz      short loc_1400B6E5A
0x1400b6e4d  test    rbx, rbx
0x1400b6e50  jz      short loc_1400B6E57
0x1400b6e52  xor     rbx, r14
0x1400b6e55  jmp     short loc_1400B6E5A
0x1400b6e57  mov     rbx, r15
0x1400b6e5a  movzx   r15d, byte ptr [r14+8]
0x1400b6e5f  xor     r8b, r8b
0x1400b6e62  and     r15d, 1
0x1400b6e66  test    rbx, rbx
0x1400b6e69  jz      short loc_1400B6E95
0x1400b6e6b  mov     rcx, [rsp+130h+var_D0]
0x1400b6e70  mov     rdx, rbx
0x1400b6e73  call    VsmmPhuStorepPhysicalBufferCompareByBlockId
0x1400b6e78  test    eax, eax
0x1400b6e7a  js      short loc_1400B6EE7
0x1400b6e7c  mov     rax, [rbx+8]
0x1400b6e80  test    r15d, r15d
0x1400b6e83  jz      short loc_1400B6E8D
0x1400b6e85  test    rax, rax
0x1400b6e88  jz      short loc_1400B6E92
0x1400b6e8a  xor     rax, rbx
0x1400b6e8d  test    rax, rax
0x1400b6e90  jnz     short loc_1400B6EFC
0x1400b6e92  mov     r8b, 1
0x1400b6e95  xor     r15d, r15d
0x1400b6e98  mov     r9, r13
0x1400b6e9b  mov     rdx, rbx
0x1400b6e9e  mov     rcx, r14
0x1400b6ea1  call    cs:__imp_RtlRbInsertNodeEx
0x1400b6ea8  nop     dword ptr [rax+rax+00h]
0x1400b6ead  mov     rcx, rdi
0x1400b6eb0  test    rdi, rdi
0x1400b6eb3  jnz     loc_1400B6D71
0x1400b6eb9  mov     ebx, r15d
0x1400b6ebc  mov     eax, ebx
0x1400b6ebe  mov     rcx, [rbp+30h+var_30]
0x1400b6ec2  xor     rcx, rsp; StackCookie
0x1400b6ec5  call    __security_check_cookie
0x1400b6eca  lea     r11, [rsp+130h+var_20]
0x1400b6ed2  mov     rbx, [r11+38h]
0x1400b6ed6  mov     rsi, [r11+40h]
0x1400b6eda  mov     rsp, r11
0x1400b6edd  pop     r15
0x1400b6edf  pop     r14
0x1400b6ee1  pop     r13
0x1400b6ee3  pop     rdi
0x1400b6ee4  pop     rbp
0x1400b6ee5  retn
0x1400b6ee7  mov     rax, [rbx]
0x1400b6eea  test    r15d, r15d
0x1400b6eed  jz      short loc_1400B6EF7
0x1400b6eef  test    rax, rax
0x1400b6ef2  jz      short loc_1400B6F04
0x1400b6ef4  xor     rax, rbx
0x1400b6ef7  test    rax, rax
0x1400b6efa  jz      short loc_1400B6F04
0x1400b6efc  mov     rbx, rax
0x1400b6eff  jmp     loc_1400B6E6B
0x1400b6f04  xor     r15d, r15d
0x1400b6f07  mov     r8b, r15b
0x1400b6f0a  jmp     short loc_1400B6E98
0x1400b6f0c  mov     r9d, eax
0x1400b6f0f  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b6f16  mov     r8d, 0A54h
0x1400b6f1c  lea     rcx, aVsmmphustorepe; "VsmmPhuStorePersistedDataPrepareToFree"
0x1400b6f23  call    VidTraceErrorStatusInternal0
0x1400b6f28  lea     rcx, [r13+18h]
0x1400b6f2c  call    VsmmPhysicalBufferTeardown
0x1400b6f31  mov     edx, 6D4D6456h; Tag
0x1400b6f36  mov     rcx, r13; P
0x1400b6f39  call    cs:__imp_ExFreePoolWithTag
0x1400b6f40  nop     dword ptr [rax+rax+00h]
0x1400b6f45  jmp     short loc_1400B6F68
0x1400b6f47  mov     ebx, 0C000009Ah
0x1400b6f4c  mov     r9d, ebx
0x1400b6f4f  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b6f56  mov     r8d, 0A46h
0x1400b6f5c  lea     rcx, aVsmmphustorepe; "VsmmPhuStorePersistedDataPrepareToFree"
0x1400b6f63  call    VidTraceErrorStatusInternal0
0x1400b6f68  cmp     [rsp+130h+var_E0], r15b
0x1400b6f6d  jz      loc_1400B705A
0x1400b6f73  mov     rcx, [rsi+4A0h]
0x1400b6f7a  call    cs:__imp_WinHvUnlinkPreExistingPartition
0x1400b6f81  nop     dword ptr [rax+rax+00h]
0x1400b6f86  mov     ebx, eax
0x1400b6f88  test    eax, eax
0x1400b6f8a  jns     loc_1400B705A
0x1400b6f90  mov     eax, cs:dword_140065110
0x1400b6f96  cmp     eax, 2
0x1400b6f99  jbe     loc_1400B705A
0x1400b6f9f  mov     edx, 100h
0x1400b6fa4  lea     rcx, dword_140065110
0x1400b6fab  call    _tlgKeywordOn
0x1400b6fb0  test    al, al
0x1400b6fb2  jz      loc_1400B705A
0x1400b6fb8  lea     rdx, aVsmmphustorepe; "VsmmPhuStorePersistedDataPrepareToFree"
0x1400b6fbf  lea     rcx, [rbp+30h+var_90]
0x1400b6fc3  call    _tlgCreate1Sz_char
0x1400b6fc8  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b6fcf  lea     rcx, [rbp+30h+var_80]
0x1400b6fd3  call    _tlgCreate1Sz_char
0x1400b6fd8  lea     rax, [rsp+130h+var_D8]
0x1400b6fdd  mov     [rsp+130h+var_D8], 0A77h
0x1400b6fe5  mov     [rbp+30h+var_70], rax
0x1400b6fe9  lea     rdx, unk_140050214
0x1400b6ff0  lea     rax, [rsp+130h+var_DC]
0x1400b6ff5  mov     [rbp+30h+var_68], 4
0x1400b6ffd  mov     [rbp+30h+var_60], rax
0x1400b7001  lea     rax, [rsi+30h]
0x1400b7005  mov     [rbp+30h+var_50], rax
0x1400b7009  mov     rax, [rsi+4A0h]
0x1400b7010  mov     [rsp+130h+var_DC], ebx
0x1400b7014  mov     [rbp+30h+var_58], 4
0x1400b701c  mov     [rsp+130h+var_D0], rax
0x1400b7021  lea     rcx, [rbp+30h+var_B0]
0x1400b7025  lea     rax, [rsp+130h+var_D0]
0x1400b702a  mov     [rsp+130h+var_108], rcx
0x1400b702f  mov     [rbp+30h+var_40], rax
0x1400b7033  lea     rcx, dword_140065110
0x1400b703a  mov     eax, 8
0x1400b703f  mov     [rbp+30h+var_48], 10h
0x1400b7047  xor     r9d, r9d
0x1400b704a  mov     dword ptr [rsp+130h+var_110], eax
0x1400b704e  xor     r8d, r8d
0x1400b7051  mov     [rbp+30h+var_38], rax
0x1400b7055  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400b705a  mov     rcx, rsi
0x1400b705d  call    VsmmPhuStorepCleanupPhysicalMemoryTable
0x1400b7062  jmp     loc_1400B6EBC
```
