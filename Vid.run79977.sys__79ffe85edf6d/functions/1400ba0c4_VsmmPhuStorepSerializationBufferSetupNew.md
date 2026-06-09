# VsmmPhuStorepSerializationBufferSetupNew

- ea: `0x1400ba0c4`
- end: `0x1400ba35e`
- name: `VsmmPhuStorepSerializationBufferSetupNew`
- size: `666`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1400b5f8c`
- `0x1400ba804`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x14002f724`
- `0x1400ba0c4`
- `0x1400ba6d8`

## import_xrefs

- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x1400ba12a`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x1400ba12a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400ba2fa`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400ba2fa`
- `ntoskrnl!ExAllocatePool2` at `0x1400ba192`
- `ntoskrnl!ExAllocatePool2` at `0x1400ba192`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrMdlToMemoryRuns` at `0x1400ba175`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrMdlToMemoryRuns` at `0x1400ba1db`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrMdlToMemoryRuns` at `0x1400ba175`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrMdlToMemoryRuns` at `0x1400ba1db`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrPersistMemoryWithMetadata` at `0x1400ba214`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrPersistMemoryWithMetadata` at `0x1400ba214`

## pseudocode

```c
__int64 __fastcall VsmmPhuStorepSerializationBufferSetupNew(__int64 a1, __int64 a2, __int64 a3)
{
  PMDL PagesForMdl; // rax
  int v6; // ebx
  unsigned int *v7; // rsi
  __int64 Pool2; // rax
  __int64 v9; // r8
  __int64 v10; // rdx
  PVOID v11; // rax
  int v13; // [rsp+30h] [rbp-69h] BYREF
  int v14; // [rsp+34h] [rbp-65h] BYREF
  int v15; // [rsp+38h] [rbp-61h] BYREF
  __int64 v16; // [rsp+40h] [rbp-59h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+50h] [rbp-49h] BYREF
  char v18[16]; // [rsp+70h] [rbp-29h] BYREF
  char v19[16]; // [rsp+80h] [rbp-19h] BYREF
  int *v20; // [rsp+90h] [rbp-9h]
  __int64 v21; // [rsp+98h] [rbp-1h]
  int *v22; // [rsp+A0h] [rbp+7h]
  __int64 v23; // [rsp+A8h] [rbp+Fh]
  int *v24; // [rsp+B0h] [rbp+17h]
  __int64 v25; // [rsp+B8h] [rbp+1Fh]

  *(_OWORD *)a3 = 0;
  *(_OWORD *)(a3 + 16) = 0;
  *(_OWORD *)(a3 + 32) = 0;
  *(_QWORD *)(a3 + 48) = 0;
  v16 = 0;
  PagesForMdl = MmAllocatePagesForMdlEx(0, (PHYSICAL_ADDRESS)-1LL, 0, a2 << 12, MmCached, 0x15u);
  *(_QWORD *)(a3 + 16) = PagesForMdl;
  if ( PagesForMdl )
  {
    v7 = (unsigned int *)(a3 + 32);
    KsrMdlToMemoryRuns(PagesForMdl, 0, 0, a3 + 32);
    Pool2 = ExAllocatePool2(256, 8LL * *(unsigned int *)(a3 + 32), 1833788502);
    *(_QWORD *)(a3 + 24) = Pool2;
    if ( Pool2 )
    {
      KsrMdlToMemoryRuns(*(_QWORD *)(a3 + 16), Pool2, *v7, a3 + 32);
      v9 = *v7;
      v10 = *(_QWORD *)(a3 + 24);
      v16 = 0x14B646956LL;
      v6 = KsrPersistMemoryWithMetadata(a1, v10, v9, &v16, 8, a3 + 8);
      if ( v6 >= 0 )
      {
        v11 = MmMapLockedPagesSpecifyCache(*(PMDL *)(a3 + 16), 0, MmCached, 0, 0, 0x40000010u);
        *(_QWORD *)a3 = v11;
        if ( v11 )
          return 0;
        v6 = -1073741670;
        VidTraceErrorStatusInternal0(
          "VsmmPhuStorepSerializationBufferSetupNew",
          "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
          10360,
          3221225626LL);
      }
      else if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v18, "VsmmPhuStorepSerializationBufferSetupNew");
        tlgCreate1Sz_char(v19, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
        v13 = 10342;
        v20 = &v13;
        v21 = 4;
        v22 = &v14;
        v15 = *v7;
        v14 = v6;
        v24 = &v15;
        v23 = 4;
        v25 = 4;
        tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140065110, byte_14004F3F1, 0, 0, 7u, &v17);
      }
    }
    else
    {
      v6 = -1073741670;
      VidTraceErrorStatusInternal0(
        "VsmmPhuStorepSerializationBufferSetupNew",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
        10315,
        3221225626LL);
    }
  }
  else
  {
    v6 = -1073741670;
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorepSerializationBufferSetupNew",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      10292,
      3221225626LL);
  }
  VsmmPhuStorepSerializationBufferTeardown(a1, 0, a3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400ba0c4  push    rbp
0x1400ba0c6  push    rbx
0x1400ba0c7  push    rsi
0x1400ba0c8  push    rdi
0x1400ba0c9  push    r14
0x1400ba0cb  lea     rbp, [rsp-37h]
0x1400ba0d0  sub     rsp, 0D0h
0x1400ba0d7  mov     rax, cs:__security_cookie
0x1400ba0de  xor     rax, rsp
0x1400ba0e1  mov     [rbp+57h+var_30], rax
0x1400ba0e5  xorps   xmm0, xmm0
0x1400ba0e8  shl     rdx, 0Ch
0x1400ba0ec  movups  xmmword ptr [r8], xmm0
0x1400ba0f0  xor     eax, eax
0x1400ba0f2  mov     rdi, r8
0x1400ba0f5  movups  xmmword ptr [r8+10h], xmm0
0x1400ba0fa  mov     r14, rcx
0x1400ba0fd  mov     r9, rdx; TotalBytes
0x1400ba100  movups  xmmword ptr [r8+20h], xmm0
0x1400ba105  mov     [r8+30h], rax
0x1400ba109  xor     ecx, ecx; LowAddress
0x1400ba10b  xor     r8d, r8d; SkipBytes
0x1400ba10e  mov     [rsp+0F0h+Flags], 15h; Flags
0x1400ba116  or      rdx, 0FFFFFFFFFFFFFFFFh; HighAddress
0x1400ba11a  mov     [rbp+57h+var_B0], 0
0x1400ba122  mov     [rsp+0F0h+CacheType], 1; CacheType
0x1400ba12a  call    cs:__imp_MmAllocatePagesForMdlEx
0x1400ba131  nop     dword ptr [rax+rax+00h]
0x1400ba136  mov     [rdi+10h], rax
0x1400ba13a  test    rax, rax
0x1400ba13d  jnz     short loc_1400BA166
0x1400ba13f  mov     r9d, 0C000009Ah
0x1400ba145  mov     ebx, r9d
0x1400ba148  mov     r8d, 2834h
0x1400ba14e  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400ba155  lea     rcx, aVsmmphustoreps_4; "VsmmPhuStorepSerializationBufferSetupNe"...
0x1400ba15c  call    VidTraceErrorStatusInternal0
0x1400ba161  jmp     loc_1400BA330
0x1400ba166  lea     rsi, [rdi+20h]
0x1400ba16a  xor     r8d, r8d
0x1400ba16d  mov     r9, rsi
0x1400ba170  xor     edx, edx
0x1400ba172  mov     rcx, rax
0x1400ba175  call    cs:__imp_KsrMdlToMemoryRuns
0x1400ba17c  nop     dword ptr [rax+rax+00h]
0x1400ba181  mov     edx, [rsi]
0x1400ba183  mov     ecx, 100h
0x1400ba188  shl     rdx, 3
0x1400ba18c  mov     r8d, 6D4D6456h
0x1400ba192  call    cs:__imp_ExAllocatePool2
0x1400ba199  nop     dword ptr [rax+rax+00h]
0x1400ba19e  mov     [rdi+18h], rax
0x1400ba1a2  test    rax, rax
0x1400ba1a5  jnz     short loc_1400BA1CE
0x1400ba1a7  mov     r9d, 0C000009Ah
0x1400ba1ad  mov     ebx, r9d
0x1400ba1b0  mov     r8d, 284Bh
0x1400ba1b6  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400ba1bd  lea     rcx, aVsmmphustoreps_4; "VsmmPhuStorepSerializationBufferSetupNe"...
0x1400ba1c4  call    VidTraceErrorStatusInternal0
0x1400ba1c9  jmp     loc_1400BA330
0x1400ba1ce  mov     r8d, [rsi]
0x1400ba1d1  mov     r9, rsi
0x1400ba1d4  mov     rcx, [rdi+10h]
0x1400ba1d8  mov     rdx, rax
0x1400ba1db  call    cs:__imp_KsrMdlToMemoryRuns
0x1400ba1e2  nop     dword ptr [rax+rax+00h]
0x1400ba1e7  mov     r8d, [rsi]
0x1400ba1ea  lea     rax, [rdi+8]
0x1400ba1ee  mov     rdx, [rdi+18h]
0x1400ba1f2  lea     r9, [rbp+57h+var_B0]
0x1400ba1f6  mov     qword ptr [rsp+0F0h+Flags], rax
0x1400ba1fb  mov     rcx, r14
0x1400ba1fe  mov     [rsp+0F0h+CacheType], 8
0x1400ba206  mov     dword ptr [rbp+57h+var_B0], 4B646956h
0x1400ba20d  mov     dword ptr [rbp+57h+var_B0+4], 1
0x1400ba214  call    cs:__imp_KsrPersistMemoryWithMetadata
0x1400ba21b  nop     dword ptr [rax+rax+00h]
0x1400ba220  mov     ebx, eax
0x1400ba222  test    eax, eax
0x1400ba224  jns     loc_1400BA2DD
0x1400ba22a  mov     ecx, cs:dword_140065110
0x1400ba230  cmp     ecx, 2
0x1400ba233  jbe     loc_1400BA330
0x1400ba239  mov     edx, 100h
0x1400ba23e  lea     rcx, dword_140065110
0x1400ba245  call    _tlgKeywordOn
0x1400ba24a  test    al, al
0x1400ba24c  jz      loc_1400BA330
0x1400ba252  lea     rdx, aVsmmphustoreps_4; "VsmmPhuStorepSerializationBufferSetupNe"...
0x1400ba259  lea     rcx, [rbp+57h+var_80]
0x1400ba25d  call    _tlgCreate1Sz_char
0x1400ba262  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400ba269  lea     rcx, [rbp+57h+var_70]
0x1400ba26d  call    _tlgCreate1Sz_char
0x1400ba272  lea     rax, [rbp+57h+var_C0]
0x1400ba276  mov     [rbp+57h+var_C0], 2866h
0x1400ba27d  mov     [rbp+57h+var_60], rax
0x1400ba281  lea     rdx, byte_14004F3F1
0x1400ba288  lea     rax, [rbp+57h+var_BC]
0x1400ba28c  mov     [rbp+57h+var_58], 4
0x1400ba294  mov     [rbp+57h+var_50], rax
0x1400ba298  lea     rcx, dword_140065110
0x1400ba29f  mov     eax, [rsi]
0x1400ba2a1  xor     r9d, r9d
0x1400ba2a4  mov     [rbp+57h+var_B8], eax
0x1400ba2a7  xor     r8d, r8d
0x1400ba2aa  lea     rax, [rbp+57h+var_B8]
0x1400ba2ae  mov     [rbp+57h+var_BC], ebx
0x1400ba2b1  mov     [rbp+57h+var_40], rax
0x1400ba2b5  lea     rax, [rbp+57h+var_A0]
0x1400ba2b9  mov     qword ptr [rsp+0F0h+Flags], rax
0x1400ba2be  mov     [rsp+0F0h+CacheType], 7
0x1400ba2c6  mov     [rbp+57h+var_48], 4
0x1400ba2ce  mov     [rbp+57h+var_38], 4
0x1400ba2d6  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400ba2db  jmp     short loc_1400BA330
0x1400ba2dd  mov     rcx, [rdi+10h]; MemoryDescriptorList
0x1400ba2e1  xor     r9d, r9d; RequestedAddress
0x1400ba2e4  mov     [rsp+0F0h+Flags], 40000010h; Priority
0x1400ba2ec  xor     edx, edx; AccessMode
0x1400ba2ee  mov     [rsp+0F0h+CacheType], 0; BugCheckOnFailure
0x1400ba2f6  lea     r8d, [r9+1]; CacheType
0x1400ba2fa  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400ba301  nop     dword ptr [rax+rax+00h]
0x1400ba306  mov     [rdi], rax
0x1400ba309  test    rax, rax
0x1400ba30c  jnz     short loc_1400BA33F
0x1400ba30e  mov     r9d, 0C000009Ah
0x1400ba314  mov     ebx, r9d
0x1400ba317  mov     r8d, 2878h
0x1400ba31d  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400ba324  lea     rcx, aVsmmphustoreps_4; "VsmmPhuStorepSerializationBufferSetupNe"...
0x1400ba32b  call    VidTraceErrorStatusInternal0
0x1400ba330  mov     r8, rdi
0x1400ba333  xor     edx, edx
0x1400ba335  mov     rcx, r14
0x1400ba338  call    VsmmPhuStorepSerializationBufferTeardown
0x1400ba33d  jmp     short loc_1400BA341
0x1400ba33f  xor     ebx, ebx
0x1400ba341  mov     eax, ebx
0x1400ba343  mov     rcx, [rbp+57h+var_30]
0x1400ba347  xor     rcx, rsp; StackCookie
0x1400ba34a  call    __security_check_cookie
0x1400ba34f  add     rsp, 0D0h
0x1400ba356  pop     r14
0x1400ba358  pop     rdi
0x1400ba359  pop     rsi
0x1400ba35a  pop     rbx
0x1400ba35b  pop     rbp
0x1400ba35c  retn
```
