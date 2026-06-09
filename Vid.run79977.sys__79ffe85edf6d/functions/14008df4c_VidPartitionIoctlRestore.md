# VidPartitionIoctlRestore

- ea: `0x14008df4c`
- end: `0x14008e24d`
- name: `VidPartitionIoctlRestore`
- size: `769`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140035708`
- `0x14003782c`

## callees

- `0x140011518`
- `0x1400248f4`
- `0x14002f724`
- `0x14008df4c`
- `0x1400fded4`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14008e06a`
- `ntoskrnl!ProbeForRead` at `0x14008e06a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008e1d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008e1d7`
- `ntoskrnl!ExAllocatePool2` at `0x14008e085`
- `ntoskrnl!ExAllocatePool2` at `0x14008e085`

## pseudocode

```c
__int64 __fastcall VidPartitionIoctlRestore(__int64 a1, int a2, volatile void *a3, unsigned int a4)
{
  size_t *v6; // rdi
  int v7; // ebx
  int v8; // edx
  char v9; // r15
  size_t v10; // rbx
  size_t *Pool2; // rax
  size_t v12; // rax
  size_t v13; // rdx
  int v14; // eax

  v6 = 0;
  if ( (a2 & 0xFFFFFFFB) != 0 )
  {
    v7 = -1073741811;
    VidTraceErrorStatusInternal0(
      "VidPartitionIoctlRestore",
      "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
      1318,
      3221225485LL);
    goto LABEL_23;
  }
  v8 = a2 & 4;
  v9 = v8 != 0;
  if ( a1 )
  {
    if ( v8 )
    {
      v7 = -1073741811;
      VidTraceErrorStatusInternal0(
        "VidPartitionIoctlRestore",
        "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        1349,
        3221225485LL);
      goto LABEL_23;
    }
  }
  else if ( !v8 )
  {
    v7 = -1073741811;
    VidTraceErrorStatusInternal0(
      "VidPartitionIoctlRestore",
      "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
      1339,
      3221225485LL);
    goto LABEL_23;
  }
  if ( a3 )
  {
    if ( a4 >= 0x18 )
    {
      v10 = a4;
      ProbeForRead(a3, a4, 1u);
      Pool2 = (size_t *)ExAllocatePool2(65, v10, 1917084758);
      v6 = Pool2;
      if ( Pool2 )
      {
        RtlCopyFromUser(Pool2, (void *)a3, v10);
        v12 = v6[1];
        if ( v12 > v10 || (v13 = v6[2], v13 > v10) )
        {
          v7 = -1073741811;
          VidTraceErrorStatusInternal0(
            "VidPartitionIoctlRestore",
            "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
            1424,
            3221225485LL);
        }
        else if ( *v6 < 0x18 || *v6 > v12 || v12 > v13 )
        {
          v7 = -1070137305;
          VidTraceErrorStatusInternal0(
            "VidPartitionIoctlRestore",
            "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
            1436,
            3224829991LL);
        }
        else
        {
          v14 = VidSaveRestoreSetPartitionState(a1, (__int64)v6, v9);
          v7 = v14;
          if ( v14 < 0 )
            VidTraceErrorStatusInternal0(
              "VidPartitionIoctlRestore",
              "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
              1446,
              (unsigned int)v14);
        }
      }
      else
      {
        v7 = -1073741670;
        VidTraceErrorStatusInternal0(
          "VidPartitionIoctlRestore",
          "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
          1399,
          3221225626LL);
      }
    }
    else
    {
      v7 = -1073741811;
      VidTraceErrorStatusInternal0(
        "VidPartitionIoctlRestore",
        "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        1365,
        3221225485LL);
    }
  }
  else
  {
    v7 = -1073741811;
    VidTraceErrorStatusInternal0(
      "VidPartitionIoctlRestore",
      "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
      1358,
      3221225485LL);
  }
LABEL_23:
  if ( v6 )
    ExFreePoolWithTag(v6, 0x72446456u);
  if ( a1 )
  {
    if ( v7 < 0 )
      VidTraceErrorStatusPartitionInternal0(
        (unsigned int)"VidPartitionIoctlRestore",
        (unsigned int)"onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        1460,
        v7,
        a1 + 656);
  }
  else if ( v7 < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VidPartitionIoctlRestore",
      "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
      1464,
      (unsigned int)v7);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14008df4c  mov     [rsp+arg_8], rbx
0x14008df51  mov     [rsp+arg_10], rsi
0x14008df56  mov     [rsp+arg_0], rcx
0x14008df5b  push    rdi
0x14008df5c  push    r14
0x14008df5e  push    r15
0x14008df60  sub     rsp, 40h
0x14008df64  mov     rsi, r8
0x14008df67  mov     r14, rcx
0x14008df6a  xor     edi, edi
0x14008df6c  mov     [rsp+58h+var_28], rdi
0x14008df71  test    edx, 0FFFFFFFBh
0x14008df77  jz      short loc_14008DFA0
0x14008df79  mov     r9d, 0C000000Dh
0x14008df7f  mov     ebx, r9d
0x14008df82  mov     r8d, 526h
0x14008df88  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008df8f  lea     rcx, aVidpartitionio_13; "VidPartitionIoctlRestore"
0x14008df96  call    VidTraceErrorStatusInternal0
0x14008df9b  jmp     loc_14008E1CA
0x14008dfa0  and     edx, 4
0x14008dfa3  setnz   r15b
0x14008dfa7  test    r14, r14
0x14008dfaa  jnz     short loc_14008DFD7
0x14008dfac  test    edx, edx
0x14008dfae  jnz     short loc_14008E002
0x14008dfb0  mov     r9d, 0C000000Dh
0x14008dfb6  mov     ebx, r9d
0x14008dfb9  mov     r8d, 53Bh
0x14008dfbf  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008dfc6  lea     rcx, aVidpartitionio_13; "VidPartitionIoctlRestore"
0x14008dfcd  call    VidTraceErrorStatusInternal0
0x14008dfd2  jmp     loc_14008E1CA
0x14008dfd7  test    edx, edx
0x14008dfd9  jz      short loc_14008E002
0x14008dfdb  mov     r9d, 0C000000Dh
0x14008dfe1  mov     ebx, r9d
0x14008dfe4  mov     r8d, 545h
0x14008dfea  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008dff1  lea     rcx, aVidpartitionio_13; "VidPartitionIoctlRestore"
0x14008dff8  call    VidTraceErrorStatusInternal0
0x14008dffd  jmp     loc_14008E1CA
0x14008e002  test    rsi, rsi
0x14008e005  jnz     short loc_14008E02E
0x14008e007  mov     r9d, 0C000000Dh
0x14008e00d  mov     ebx, r9d
0x14008e010  mov     r8d, 54Eh
0x14008e016  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008e01d  lea     rcx, aVidpartitionio_13; "VidPartitionIoctlRestore"
0x14008e024  call    VidTraceErrorStatusInternal0
0x14008e029  jmp     loc_14008E1CA
0x14008e02e  cmp     r9d, 18h
0x14008e032  jnb     short loc_14008E05B
0x14008e034  mov     r9d, 0C000000Dh
0x14008e03a  mov     ebx, r9d
0x14008e03d  mov     r8d, 555h
0x14008e043  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008e04a  lea     rcx, aVidpartitionio_13; "VidPartitionIoctlRestore"
0x14008e051  call    VidTraceErrorStatusInternal0
0x14008e056  jmp     loc_14008E1CA
0x14008e05b  mov     ebx, r9d
0x14008e05e  mov     r8d, 1; Alignment
0x14008e064  mov     edx, r9d; Length
0x14008e067  mov     rcx, rsi; Address
0x14008e06a  call    cs:__imp_ProbeForRead
0x14008e071  nop     dword ptr [rax+rax+00h]
0x14008e076  nop
0x14008e077  mov     r8d, 72446456h
0x14008e07d  mov     rdx, rbx
0x14008e080  mov     ecx, 41h ; 'A'
0x14008e085  call    cs:__imp_ExAllocatePool2
0x14008e08c  nop     dword ptr [rax+rax+00h]
0x14008e091  mov     rdi, rax
0x14008e094  mov     [rsp+58h+var_28], rax
0x14008e099  test    rax, rax
0x14008e09c  jnz     short loc_14008E0C4
0x14008e09e  mov     ebx, 0C000009Ah
0x14008e0a3  mov     r9d, ebx
0x14008e0a6  mov     r8d, 577h
0x14008e0ac  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008e0b3  lea     rcx, aVidpartitionio_13; "VidPartitionIoctlRestore"
0x14008e0ba  call    VidTraceErrorStatusInternal0
0x14008e0bf  jmp     loc_14008E1CA
0x14008e0c4  mov     r8, rbx; Size
0x14008e0c7  mov     rdx, rsi; Src
0x14008e0ca  mov     rcx, rdi; void *
0x14008e0cd  call    RtlCopyFromUser
0x14008e0d2  nop
0x14008e0d3  mov     rax, [rdi+8]
0x14008e0d7  cmp     rax, rbx
0x14008e0da  ja      short loc_14008E154
0x14008e0dc  mov     rdx, [rdi+10h]
0x14008e0e0  cmp     rdx, rbx
0x14008e0e3  ja      short loc_14008E154
0x14008e0e5  mov     rcx, [rdi]
0x14008e0e8  cmp     rcx, 18h
0x14008e0ec  jb      short loc_14008E131
0x14008e0ee  cmp     rcx, rax
0x14008e0f1  ja      short loc_14008E131
0x14008e0f3  cmp     rax, rdx
0x14008e0f6  ja      short loc_14008E131
0x14008e0f8  mov     r8b, r15b
0x14008e0fb  mov     rdx, rdi
0x14008e0fe  mov     rcx, r14
0x14008e101  call    VidSaveRestoreSetPartitionState
0x14008e106  mov     ebx, eax
0x14008e108  test    eax, eax
0x14008e10a  jns     loc_14008E1CA
0x14008e110  mov     r9d, eax
0x14008e113  mov     r8d, 5A6h
0x14008e119  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008e120  lea     rcx, aVidpartitionio_13; "VidPartitionIoctlRestore"
0x14008e127  call    VidTraceErrorStatusInternal0
0x14008e12c  jmp     loc_14008E1CA
0x14008e131  mov     ebx, 0C0370027h
0x14008e136  mov     r9d, ebx
0x14008e139  mov     r8d, 59Ch
0x14008e13f  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008e146  lea     rcx, aVidpartitionio_13; "VidPartitionIoctlRestore"
0x14008e14d  call    VidTraceErrorStatusInternal0
0x14008e152  jmp     short loc_14008E1CA
0x14008e154  mov     r9d, 0C000000Dh
0x14008e15a  mov     ebx, r9d
0x14008e15d  mov     r8d, 590h
0x14008e163  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008e16a  lea     rcx, aVidpartitionio_13; "VidPartitionIoctlRestore"
0x14008e171  call    VidTraceErrorStatusInternal0
0x14008e176  jmp     short loc_14008E1CA
0x14008e178  mov     ebx, eax
0x14008e17a  mov     r9d, eax
0x14008e17d  mov     r8d, 585h
0x14008e183  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008e18a  lea     rcx, aVidpartitionio_13; "VidPartitionIoctlRestore"
0x14008e191  call    VidTraceErrorStatusInternal0
0x14008e196  mov     r14, [rsp+58h+arg_0]
0x14008e19b  mov     rdi, [rsp+58h+var_28]
0x14008e1a0  jmp     short loc_14008E1CA
0x14008e1a2  mov     ebx, eax
0x14008e1a4  mov     r9d, eax
0x14008e1a7  mov     r8d, 56Bh
0x14008e1ad  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008e1b4  lea     rcx, aVidpartitionio_13; "VidPartitionIoctlRestore"
0x14008e1bb  call    VidTraceErrorStatusInternal0
0x14008e1c0  mov     r14, [rsp+58h+arg_0]
0x14008e1c5  mov     rdi, [rsp+58h+var_28]
0x14008e1ca  test    rdi, rdi
0x14008e1cd  jz      short loc_14008E1E3
0x14008e1cf  mov     edx, 72446456h; Tag
0x14008e1d4  mov     rcx, rdi; P
0x14008e1d7  call    cs:__imp_ExFreePoolWithTag
0x14008e1de  nop     dword ptr [rax+rax+00h]
0x14008e1e3  test    r14, r14
0x14008e1e6  jz      short loc_14008E216
0x14008e1e8  test    ebx, ebx
0x14008e1ea  jns     short loc_14008E236
0x14008e1ec  lea     rax, [r14+290h]
0x14008e1f3  mov     [rsp+58h+var_38], rax
0x14008e1f8  mov     r9d, ebx
0x14008e1fb  mov     r8d, 5B4h
0x14008e201  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008e208  lea     rcx, aVidpartitionio_13; "VidPartitionIoctlRestore"
0x14008e20f  call    VidTraceErrorStatusPartitionInternal0
0x14008e214  jmp     short loc_14008E236
0x14008e216  test    ebx, ebx
0x14008e218  jns     short loc_14008E236
0x14008e21a  mov     r9d, ebx
0x14008e21d  mov     r8d, 5B8h
0x14008e223  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008e22a  lea     rcx, aVidpartitionio_13; "VidPartitionIoctlRestore"
0x14008e231  call    VidTraceErrorStatusInternal0
0x14008e236  mov     eax, ebx
0x14008e238  mov     rbx, [rsp+58h+arg_8]
0x14008e23d  mov     rsi, [rsp+58h+arg_10]
0x14008e242  add     rsp, 40h
0x14008e246  pop     r15
0x14008e248  pop     r14
0x14008e24a  pop     rdi
0x14008e24b  retn
```
