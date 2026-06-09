# VsmmPhuStorepHvPartitionFree

- ea: `0x1400b82a0`
- end: `0x1400b8564`
- name: `VsmmPhuStorepHvPartitionFree`
- size: `708`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400b6858`
- `0x1400b7fc8`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x140024f68`
- `0x1400b82a0`
- `0x1400ba7e4`

## import_xrefs

- `winhvr!WinHvSetPartitionProperty` at `0x1400b82eb`
- `winhvr!WinHvSetPartitionProperty` at `0x1400b834d`
- `winhvr!WinHvSetPartitionProperty` at `0x1400b82eb`
- `winhvr!WinHvSetPartitionProperty` at `0x1400b834d`
- `winhvr!WinHvDeletePartition` at `0x1400b8511`
- `winhvr!WinHvDeletePartition` at `0x1400b8511`
- `winhvr!WinHvDeletePartitionRemote` at `0x1400b8430`
- `winhvr!WinHvDeletePartitionRemote` at `0x1400b8430`

## pseudocode

```c
__int64 __fastcall VsmmPhuStorepHvPartitionFree(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  int v5; // eax
  int v6; // edx
  int v7; // ecx
  unsigned __int64 v8; // rcx
  int v9; // r8d
  int v10; // r8d
  int v11; // eax
  int v12; // edx
  int v13; // ecx
  int v15; // [rsp+30h] [rbp-69h] BYREF
  int v16; // [rsp+34h] [rbp-65h] BYREF
  __int64 v17; // [rsp+38h] [rbp-61h] BYREF
  __int64 v18; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v19[32]; // [rsp+50h] [rbp-49h] BYREF
  _BYTE v20[16]; // [rsp+70h] [rbp-29h] BYREF
  _BYTE v21[16]; // [rsp+80h] [rbp-19h] BYREF
  int *v22; // [rsp+90h] [rbp-9h]
  __int64 v23; // [rsp+98h] [rbp-1h]
  int *v24; // [rsp+A0h] [rbp+7h]
  __int64 v25; // [rsp+A8h] [rbp+Fh]
  __int64 *v26; // [rsp+B0h] [rbp+17h]
  __int64 v27; // [rsp+B8h] [rbp+1Fh]
  __int64 *v28; // [rsp+C0h] [rbp+27h]
  __int64 v29; // [rsp+C8h] [rbp+2Fh]

  v3 = *(_QWORD *)(a2 + 56);
  if ( (unsigned __int64)((*(_DWORD *)(a2 + 40) >> 10) & 0xF) - 2 <= 2 )
  {
    v5 = WinHvSetPartitionProperty(v3);
    if ( v5 < 0 )
      VidTracePartitionIdErrorInternal0(v7, v6, 7268, v3, v5);
  }
  v8 = *(_QWORD *)(a2 + 40);
  if ( (((v8 >> 10) & 0xF) - 2 <= 2 || ((((unsigned __int16)v8 & 0xC000) - 0x4000LL) & 0xFFFFFFFFFFFFBFFFuLL) == 0)
    && (int)WinHvSetPartitionProperty(v3) < 0
    && (unsigned int)dword_140065110 > 2
    && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v20, "VsmmPhuStorepHvPartitionFree");
    tlgCreate1Sz_char(v21, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
    v16 = v9;
    v29 = 8;
    v22 = &v15;
    v15 = 7286;
    v24 = &v16;
    v23 = 4;
    v26 = (__int64 *)(a1 + 48);
    v25 = 4;
    v28 = &v17;
    v27 = 16;
    v17 = v3;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_14004F5EA, 0, 0, 8, v19);
  }
  if ( *(_QWORD *)(a2 + 104)
    && (int)WinHvDeletePartitionRemote(v3) < 0
    && (unsigned int)dword_140065110 > 2
    && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v20, "VsmmPhuStorepHvPartitionFree");
    tlgCreate1Sz_char(v21, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
    v15 = v10;
    v27 = 8;
    v22 = &v16;
    v29 = 8;
    v24 = &v15;
    v16 = 7301;
    v26 = &v17;
    v18 = *(_QWORD *)(a2 + 104);
    v28 = &v18;
    v23 = 4;
    v25 = 4;
    v17 = v3;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_14004F649, 0, 0, 8, v19);
  }
  if ( v3 )
  {
    v11 = WinHvDeletePartition(v3);
    if ( v11 < 0 )
      VidTracePartitionIdErrorInternal0(v13, v12, 7317, v3, v11);
  }
  *(_BYTE *)(a2 + 48) = 0;
  return VsmmPhuStorepSerializationChargeDecrease(a1, 144);
}

```

## disassembly

```asm
0x1400b82a0  mov     [rsp-8+arg_10], rbx
0x1400b82a5  push    rbp
0x1400b82a6  push    rsi
0x1400b82a7  push    rdi
0x1400b82a8  lea     rbp, [rsp-47h]
0x1400b82ad  sub     rsp, 0E0h
0x1400b82b4  mov     rax, cs:__security_cookie
0x1400b82bb  xor     rax, rsp
0x1400b82be  mov     [rbp+57h+var_20], rax
0x1400b82c2  mov     eax, [rdx+28h]
0x1400b82c5  mov     rdi, rdx
0x1400b82c8  mov     rbx, [rdx+38h]
0x1400b82cc  mov     rsi, rcx
0x1400b82cf  shr     rax, 0Ah
0x1400b82d3  and     eax, 0Fh
0x1400b82d6  sub     rax, 2
0x1400b82da  cmp     rax, 2
0x1400b82de  ja      short loc_1400B830D
0x1400b82e0  xor     r8d, r8d
0x1400b82e3  mov     edx, 5000Dh
0x1400b82e8  mov     rcx, rbx
0x1400b82eb  call    cs:__imp_WinHvSetPartitionProperty
0x1400b82f2  nop     dword ptr [rax+rax+00h]
0x1400b82f7  test    eax, eax
0x1400b82f9  jns     short loc_1400B830D
0x1400b82fb  mov     r9, rbx
0x1400b82fe  mov     [rsp+0F0h+var_D0], eax
0x1400b8302  mov     r8d, 1C64h
0x1400b8308  call    VidTracePartitionIdErrorInternal0
0x1400b830d  mov     rcx, [rdi+28h]
0x1400b8311  mov     rax, rcx
0x1400b8314  shr     rax, 0Ah
0x1400b8318  and     eax, 0Fh
0x1400b831b  sub     rax, 2
0x1400b831f  cmp     rax, 2
0x1400b8323  jbe     short loc_1400B833F
0x1400b8325  and     ecx, 0C000h
0x1400b832b  sub     rcx, 4000h
0x1400b8332  test    rcx, 0FFFFFFFFFFFFBFFFh
0x1400b8339  jnz     loc_1400B8422
0x1400b833f  mov     edx, 5000Ch
0x1400b8344  mov     r8d, 2
0x1400b834a  mov     rcx, rbx
0x1400b834d  call    cs:__imp_WinHvSetPartitionProperty
0x1400b8354  nop     dword ptr [rax+rax+00h]
0x1400b8359  mov     r8d, eax
0x1400b835c  test    eax, eax
0x1400b835e  jns     loc_1400B8422
0x1400b8364  mov     ecx, cs:dword_140065110
0x1400b836a  cmp     ecx, 2
0x1400b836d  jbe     loc_1400B8422
0x1400b8373  mov     edx, 100h
0x1400b8378  lea     rcx, dword_140065110
0x1400b837f  call    _tlgKeywordOn
0x1400b8384  test    al, al
0x1400b8386  jz      loc_1400B8422
0x1400b838c  lea     rdx, aVsmmphustoreph_1; "VsmmPhuStorepHvPartitionFree"
0x1400b8393  lea     rcx, [rbp+57h+var_80]
0x1400b8397  call    _tlgCreate1Sz_char
0x1400b839c  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b83a3  lea     rcx, [rbp+57h+var_70]
0x1400b83a7  call    _tlgCreate1Sz_char
0x1400b83ac  mov     ecx, 8
0x1400b83b1  mov     [rbp+57h+var_BC], r8d
0x1400b83b5  lea     rax, [rbp+57h+var_C0]
0x1400b83b9  mov     [rbp+57h+var_28], rcx
0x1400b83bd  mov     [rbp+57h+var_60], rax
0x1400b83c1  lea     rdx, unk_14004F5EA
0x1400b83c8  lea     rax, [rbp+57h+var_BC]
0x1400b83cc  mov     [rbp+57h+var_C0], 1C76h
0x1400b83d3  mov     [rbp+57h+var_50], rax
0x1400b83d7  xor     r9d, r9d
0x1400b83da  lea     rax, [rsi+30h]
0x1400b83de  mov     [rbp+57h+var_58], 4
0x1400b83e6  mov     [rbp+57h+var_40], rax
0x1400b83ea  xor     r8d, r8d
0x1400b83ed  lea     rax, [rbp+57h+var_B8]
0x1400b83f1  mov     [rbp+57h+var_48], 4
0x1400b83f9  mov     [rbp+57h+var_30], rax
0x1400b83fd  lea     rax, [rbp+57h+var_A0]
0x1400b8401  mov     [rsp+0F0h+var_C8], rax
0x1400b8406  mov     [rsp+0F0h+var_D0], ecx
0x1400b840a  lea     rcx, dword_140065110
0x1400b8411  mov     [rbp+57h+var_38], 10h
0x1400b8419  mov     [rbp+57h+var_B8], rbx
0x1400b841d  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400b8422  cmp     qword ptr [rdi+68h], 0
0x1400b8427  jz      loc_1400B8509
0x1400b842d  mov     rcx, rbx
0x1400b8430  call    cs:__imp_WinHvDeletePartitionRemote
0x1400b8437  nop     dword ptr [rax+rax+00h]
0x1400b843c  mov     r8d, eax
0x1400b843f  test    eax, eax
0x1400b8441  jns     loc_1400B8509
0x1400b8447  mov     ecx, cs:dword_140065110
0x1400b844d  cmp     ecx, 2
0x1400b8450  jbe     loc_1400B8509
0x1400b8456  mov     edx, 100h
0x1400b845b  lea     rcx, dword_140065110
0x1400b8462  call    _tlgKeywordOn
0x1400b8467  test    al, al
0x1400b8469  jz      loc_1400B8509
0x1400b846f  lea     rdx, aVsmmphustoreph_1; "VsmmPhuStorepHvPartitionFree"
0x1400b8476  lea     rcx, [rbp+57h+var_80]
0x1400b847a  call    _tlgCreate1Sz_char
0x1400b847f  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b8486  lea     rcx, [rbp+57h+var_70]
0x1400b848a  call    _tlgCreate1Sz_char
0x1400b848f  mov     ecx, 8
0x1400b8494  mov     [rbp+57h+var_C0], r8d
0x1400b8498  lea     rax, [rbp+57h+var_BC]
0x1400b849c  mov     [rbp+57h+var_38], rcx
0x1400b84a0  mov     [rbp+57h+var_60], rax
0x1400b84a4  lea     rdx, unk_14004F649
0x1400b84ab  lea     rax, [rbp+57h+var_C0]
0x1400b84af  mov     [rbp+57h+var_28], rcx
0x1400b84b3  mov     [rbp+57h+var_50], rax
0x1400b84b7  xor     r9d, r9d
0x1400b84ba  lea     rax, [rbp+57h+var_B8]
0x1400b84be  mov     [rbp+57h+var_BC], 1C85h
0x1400b84c5  mov     [rbp+57h+var_40], rax
0x1400b84c9  xor     r8d, r8d
0x1400b84cc  mov     rax, [rdi+68h]
0x1400b84d0  mov     [rbp+57h+var_B0], rax
0x1400b84d4  lea     rax, [rbp+57h+var_B0]
0x1400b84d8  mov     [rbp+57h+var_30], rax
0x1400b84dc  lea     rax, [rbp+57h+var_A0]
0x1400b84e0  mov     [rsp+0F0h+var_C8], rax
0x1400b84e5  mov     [rsp+0F0h+var_D0], ecx
0x1400b84e9  lea     rcx, dword_140065110
0x1400b84f0  mov     [rbp+57h+var_58], 4
0x1400b84f8  mov     [rbp+57h+var_48], 4
0x1400b8500  mov     [rbp+57h+var_B8], rbx
0x1400b8504  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400b8509  test    rbx, rbx
0x1400b850c  jz      short loc_1400B8533
0x1400b850e  mov     rcx, rbx
0x1400b8511  call    cs:__imp_WinHvDeletePartition
0x1400b8518  nop     dword ptr [rax+rax+00h]
0x1400b851d  test    eax, eax
0x1400b851f  jns     short loc_1400B8533
0x1400b8521  mov     r9, rbx
0x1400b8524  mov     [rsp+0F0h+var_D0], eax
0x1400b8528  mov     r8d, 1C95h
0x1400b852e  call    VidTracePartitionIdErrorInternal0
0x1400b8533  mov     edx, 90h
0x1400b8538  mov     byte ptr [rdi+30h], 0
0x1400b853c  mov     rcx, rsi
0x1400b853f  call    VsmmPhuStorepSerializationChargeDecrease
0x1400b8544  mov     rcx, [rbp+57h+var_20]
0x1400b8548  xor     rcx, rsp; StackCookie
0x1400b854b  call    __security_check_cookie
0x1400b8550  mov     rbx, [rsp+0F0h+arg_10]
0x1400b8558  add     rsp, 0E0h
0x1400b855f  pop     rdi
0x1400b8560  pop     rsi
0x1400b8561  pop     rbp
0x1400b8562  retn
```
