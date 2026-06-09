# VsmmMemPartIoctlOpen

- ea: `0x1400a7260`
- end: `0x1400a748e`
- name: `VsmmMemPartIoctlOpen`
- size: `558`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14003782c`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140016afc`
- `0x140021c60`
- `0x1400a7260`
- `0x1400fe5ec`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x1400a73c1`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400a73c1`
- `ntoskrnl!PsPartitionType` at `0x1400a73a8`
- `ntoskrnl!NtClose` at `0x1400a7465`
- `ntoskrnl!NtClose` at `0x1400a7465`

## string_xrefs

- `0x1400a72f6`: `VsmmMemPartIoctlOpen`
- `0x1400a73f3`: `VsmmMemPartIoctlOpen`

## pseudocode

```c
__int64 __fastcall VsmmMemPartIoctlOpen(__int64 a1, ACCESS_MASK a2, HANDLE *a3)
{
  int v5; // esi
  __int64 v6; // rax
  __int64 v7; // r8
  int v8; // eax
  void *PartitionObject; // r10
  NTSTATUS v10; // ebx
  void *v11; // rdx
  __int64 v12; // r8
  int *v13; // rax
  int v15; // [rsp+40h] [rbp-79h] BYREF
  int v16; // [rsp+44h] [rbp-75h] BYREF
  NTSTATUS v17; // [rsp+48h] [rbp-71h] BYREF
  int v18; // [rsp+4Ch] [rbp-6Dh] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-69h] BYREF
  _BYTE v20[32]; // [rsp+60h] [rbp-59h] BYREF
  _BYTE v21[16]; // [rsp+80h] [rbp-39h] BYREF
  _BYTE v22[16]; // [rsp+90h] [rbp-29h] BYREF
  int *v23; // [rsp+A0h] [rbp-19h]
  __int64 v24; // [rsp+A8h] [rbp-11h]
  int *v25; // [rsp+B0h] [rbp-9h]
  __int64 v26; // [rsp+B8h] [rbp-1h]
  int *v27; // [rsp+C0h] [rbp+7h]
  __int64 v28; // [rsp+C8h] [rbp+Fh]
  int *v29; // [rsp+D0h] [rbp+17h]
  __int64 v30; // [rsp+D8h] [rbp+1Fh]

  Handle = 0;
  v5 = a1;
  v6 = VsmmMemReserveMemPartGet(a1);
  v7 = v6;
  if ( v6 && ((v8 = *(_DWORD *)(v6 + 32), (v8 & 0xFFFFFFFA) != 0) || v8 == 1) )
  {
    PartitionObject = (void *)VsmmMemPartGetPartitionObject(v7);
    if ( PartitionObject )
    {
      v10 = ObOpenObjectByPointer(PartitionObject, 0, 0, a2, PsPartitionType, 1, &Handle);
      if ( v10 >= 0 )
      {
        v10 = 0;
        *a3 = Handle;
        return (unsigned int)v10;
      }
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v21, "VsmmMemPartIoctlOpen");
        tlgCreate1Sz_char(v22, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c");
        v18 = 455;
        v23 = &v18;
        v11 = &unk_14004CB89;
        v17 = v10;
        v25 = &v17;
        v27 = &v16;
        v13 = &v15;
        v16 = v5;
        v15 = a2;
        goto LABEL_8;
      }
    }
    else
    {
      v10 = -1073741661;
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v21, "VsmmMemPartIoctlOpen");
        tlgCreate1Sz_char(v22, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c");
        v15 = 433;
        v23 = &v15;
        v11 = &unk_14004CB2E;
        v16 = -1073741661;
        v25 = &v16;
        v27 = &v17;
        v18 = *(_DWORD *)(v12 + 32);
        v13 = &v18;
        v17 = v5;
LABEL_8:
        v29 = v13;
        v30 = 4;
        v28 = 4;
        v26 = 4;
        v24 = 4;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v11, 0, 0, 8, v20);
      }
    }
  }
  else
  {
    v10 = -1073741275;
  }
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400a7260  push    rbp
0x1400a7262  push    rbx
0x1400a7263  push    rsi
0x1400a7264  push    rdi
0x1400a7265  push    r14
0x1400a7267  lea     rbp, [rsp-37h]
0x1400a726c  sub     rsp, 0F0h
0x1400a7273  mov     rax, cs:__security_cookie
0x1400a727a  xor     rax, rsp
0x1400a727d  mov     [rbp+57h+var_30], rax
0x1400a7281  mov     rdi, r8
0x1400a7284  mov     [rbp+57h+var_C0], 0
0x1400a728c  mov     r14d, edx
0x1400a728f  mov     esi, ecx
0x1400a7291  call    VsmmMemReserveMemPartGet
0x1400a7296  mov     r8, rax
0x1400a7299  test    rax, rax
0x1400a729c  jz      loc_1400A7457
0x1400a72a2  mov     eax, [rax+20h]
0x1400a72a5  test    eax, 0FFFFFFFAh
0x1400a72aa  jnz     short loc_1400A72B5
0x1400a72ac  cmp     eax, 1
0x1400a72af  jnz     loc_1400A7457
0x1400a72b5  mov     rcx, r8
0x1400a72b8  call    VsmmMemPartGetPartitionObject
0x1400a72bd  mov     r10, rax
0x1400a72c0  test    rax, rax
0x1400a72c3  jnz     loc_1400A7399
0x1400a72c9  mov     eax, cs:dword_140065110
0x1400a72cf  mov     ebx, 0C00000A3h
0x1400a72d4  cmp     eax, 2
0x1400a72d7  jbe     loc_1400A745C
0x1400a72dd  mov     edx, 100h
0x1400a72e2  lea     rcx, dword_140065110
0x1400a72e9  call    _tlgKeywordOn
0x1400a72ee  test    al, al
0x1400a72f0  jz      loc_1400A745C
0x1400a72f6  lea     rdx, aVsmmmempartioc_0; "VsmmMemPartIoctlOpen"
0x1400a72fd  lea     rcx, [rbp+57h+var_90]
0x1400a7301  call    _tlgCreate1Sz_char
0x1400a7306  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a730d  lea     rcx, [rbp+57h+var_80]
0x1400a7311  call    _tlgCreate1Sz_char
0x1400a7316  lea     rax, [rbp+57h+var_D0]
0x1400a731a  mov     [rbp+57h+var_D0], 1B1h
0x1400a7321  mov     [rbp+57h+var_70], rax
0x1400a7325  lea     rdx, unk_14004CB2E
0x1400a732c  lea     rax, [rbp+57h+var_CC]
0x1400a7330  mov     [rbp+57h+var_CC], ebx
0x1400a7333  mov     [rbp+57h+var_60], rax
0x1400a7337  lea     rax, [rbp+57h+var_C8]
0x1400a733b  mov     [rbp+57h+var_50], rax
0x1400a733f  mov     eax, [r8+20h]
0x1400a7343  mov     [rbp+57h+var_C4], eax
0x1400a7346  lea     rax, [rbp+57h+var_C4]
0x1400a734a  mov     [rbp+57h+var_C8], esi
0x1400a734d  mov     [rbp+57h+var_40], rax
0x1400a7351  lea     rcx, dword_140065110
0x1400a7358  lea     rax, [rbp+57h+var_B0]
0x1400a735c  mov     [rbp+57h+var_38], 4
0x1400a7364  mov     qword ptr [rsp+110h+AccessMode], rax
0x1400a7369  xor     r9d, r9d
0x1400a736c  xor     r8d, r8d
0x1400a736f  mov     dword ptr [rsp+110h+ObjectType], 8
0x1400a7377  mov     [rbp+57h+var_48], 4
0x1400a737f  mov     [rbp+57h+var_58], 4
0x1400a7387  mov     [rbp+57h+var_68], 4
0x1400a738f  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400a7394  jmp     loc_1400A745C
0x1400a7399  lea     rax, [rbp+57h+var_C0]
0x1400a739d  mov     r9d, r14d; DesiredAccess
0x1400a73a0  mov     [rsp+110h+Handle], rax; Handle
0x1400a73a5  xor     r8d, r8d; PassedAccessState
0x1400a73a8  mov     rax, cs:__imp_PsPartitionType
0x1400a73af  xor     edx, edx; HandleAttributes
0x1400a73b1  mov     [rsp+110h+AccessMode], 1; AccessMode
0x1400a73b6  mov     rcx, [rax]
0x1400a73b9  mov     [rsp+110h+ObjectType], rcx; ObjectType
0x1400a73be  mov     rcx, r10; Object
0x1400a73c1  call    cs:__imp_ObOpenObjectByPointer
0x1400a73c8  nop     dword ptr [rax+rax+00h]
0x1400a73cd  mov     ebx, eax
0x1400a73cf  test    eax, eax
0x1400a73d1  jns     short loc_1400A744C
0x1400a73d3  mov     ecx, cs:dword_140065110
0x1400a73d9  cmp     ecx, 2
0x1400a73dc  jbe     short loc_1400A745C
0x1400a73de  mov     edx, 100h
0x1400a73e3  lea     rcx, dword_140065110
0x1400a73ea  call    _tlgKeywordOn
0x1400a73ef  test    al, al
0x1400a73f1  jz      short loc_1400A745C
0x1400a73f3  lea     rdx, aVsmmmempartioc_0; "VsmmMemPartIoctlOpen"
0x1400a73fa  lea     rcx, [rbp+57h+var_90]
0x1400a73fe  call    _tlgCreate1Sz_char
0x1400a7403  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a740a  lea     rcx, [rbp+57h+var_80]
0x1400a740e  call    _tlgCreate1Sz_char
0x1400a7413  lea     rax, [rbp+57h+var_C4]
0x1400a7417  mov     [rbp+57h+var_C4], 1C7h
0x1400a741e  mov     [rbp+57h+var_70], rax
0x1400a7422  lea     rdx, unk_14004CB89
0x1400a7429  lea     rax, [rbp+57h+var_C8]
0x1400a742d  mov     [rbp+57h+var_C8], ebx
0x1400a7430  mov     [rbp+57h+var_60], rax
0x1400a7434  lea     rax, [rbp+57h+var_CC]
0x1400a7438  mov     [rbp+57h+var_50], rax
0x1400a743c  lea     rax, [rbp+57h+var_D0]
0x1400a7440  mov     [rbp+57h+var_CC], esi
0x1400a7443  mov     [rbp+57h+var_D0], r14d
0x1400a7447  jmp     loc_1400A734D
0x1400a744c  mov     rax, [rbp+57h+var_C0]
0x1400a7450  xor     ebx, ebx
0x1400a7452  mov     [rdi], rax
0x1400a7455  jmp     short loc_1400A7471
0x1400a7457  mov     ebx, 0C0000225h
0x1400a745c  mov     rcx, [rbp+57h+var_C0]; Handle
0x1400a7460  test    rcx, rcx
0x1400a7463  jz      short loc_1400A7471
0x1400a7465  call    cs:__imp_NtClose
0x1400a746c  nop     dword ptr [rax+rax+00h]
0x1400a7471  mov     eax, ebx
0x1400a7473  mov     rcx, [rbp+57h+var_30]
0x1400a7477  xor     rcx, rsp; StackCookie
0x1400a747a  call    __security_check_cookie
0x1400a747f  add     rsp, 0F0h
0x1400a7486  pop     r14
0x1400a7488  pop     rdi
0x1400a7489  pop     rsi
0x1400a748a  pop     rbx
0x1400a748b  pop     rbp
0x1400a748c  retn
```
