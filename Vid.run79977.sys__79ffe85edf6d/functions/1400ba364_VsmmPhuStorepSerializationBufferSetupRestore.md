# VsmmPhuStorepSerializationBufferSetupRestore

- ea: `0x1400ba364`
- end: `0x1400ba6d0`
- name: `VsmmPhuStorepSerializationBufferSetupRestore`
- size: `876`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1400b5f8c`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x14002f724`
- `0x1400ba364`
- `0x1400ba6d8`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400ba661`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400ba661`
- `ntoskrnl!ExAllocatePool2` at `0x1400ba41b`
- `ntoskrnl!ExAllocatePool2` at `0x1400ba581`
- `ntoskrnl!ExAllocatePool2` at `0x1400ba41b`
- `ntoskrnl!ExAllocatePool2` at `0x1400ba581`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrClaimPersistedMemory` at `0x1400ba3c8`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrClaimPersistedMemory` at `0x1400ba473`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrClaimPersistedMemory` at `0x1400ba3c8`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrClaimPersistedMemory` at `0x1400ba473`

## pseudocode

```c
__int64 __fastcall VsmmPhuStorepSerializationBufferSetupRestore(__int64 a1, __int64 a2, __int64 a3)
{
  int v5; // eax
  int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 Pool2; // rax
  unsigned int v10; // r8d
  unsigned int i; // edx
  __int64 v12; // rax
  unsigned int v13; // ebx
  __int64 v14; // rax
  unsigned int v15; // edx
  unsigned int v16; // r10d
  _QWORD *j; // r8
  unsigned int v18; // ecx
  __int64 v19; // r11
  __int64 v20; // r9
  __int64 v21; // rax
  PVOID v22; // rax
  unsigned int v24; // [rsp+30h] [rbp-49h] BYREF
  int v25; // [rsp+34h] [rbp-45h] BYREF
  int v26; // [rsp+38h] [rbp-41h] BYREF
  unsigned int v27; // [rsp+3Ch] [rbp-3Dh] BYREF
  struct _EVENT_DATA_DESCRIPTOR v28; // [rsp+40h] [rbp-39h] BYREF
  char v29[16]; // [rsp+60h] [rbp-19h] BYREF
  char v30[16]; // [rsp+70h] [rbp-9h] BYREF
  int *v31; // [rsp+80h] [rbp+7h]
  __int64 v32; // [rsp+88h] [rbp+Fh]
  int *v33; // [rsp+90h] [rbp+17h]
  __int64 v34; // [rsp+98h] [rbp+1Fh]
  int *v35; // [rsp+A0h] [rbp+27h]
  __int64 v36; // [rsp+A8h] [rbp+2Fh]

  *(_OWORD *)a3 = 0;
  *(_OWORD *)(a3 + 16) = 0;
  *(_OWORD *)(a3 + 32) = 0;
  *(_QWORD *)(a3 + 48) = 0;
  *(_QWORD *)(a3 + 8) = a2;
  v24 = 0;
  v5 = KsrClaimPersistedMemory(a1, a2, 0, 0, 0, &v24);
  v6 = 0;
  if ( v5 != -1073741789 )
    v6 = v5;
  if ( v6 >= 0 )
  {
    v8 = v24;
    *(_DWORD *)(a3 + 32) = v24;
    Pool2 = ExAllocatePool2(258, 8 * v8, 1833788502);
    *(_QWORD *)(a3 + 24) = Pool2;
    if ( Pool2 )
    {
      v6 = KsrClaimPersistedMemory(a1, *(_QWORD *)(a3 + 8), Pool2, v24, 0, &v24);
      if ( v6 >= 0 )
      {
        v10 = 0;
        if ( v24 )
        {
          for ( i = 0; i < v24; ++i )
          {
            v12 = i;
            v10 += *(_QWORD *)(*(_QWORD *)(a3 + 24) + 8 * v12) >> 40;
          }
        }
        v13 = v10;
        v14 = ExAllocatePool2(256, 8LL * v10 + 48, 1833788502);
        *(_QWORD *)(a3 + 16) = v14;
        if ( v14 )
        {
          *(_QWORD *)(v14 + 12) = 0;
          v15 = 0;
          *(_QWORD *)(v14 + 20) = 0;
          *(_DWORD *)(v14 + 28) = 0;
          *(_QWORD *)v14 = 0;
          *(_WORD *)(v14 + 8) = 8 * (v13 + 6);
          *(_QWORD *)(v14 + 32) = 0;
          *(_QWORD *)(v14 + 40) = v13 << 12;
          *(_WORD *)(v14 + 10) = 2;
          v16 = v24;
          for ( j = (_QWORD *)(*(_QWORD *)(a3 + 16) + 48LL); v15 < v16; ++v15 )
          {
            v18 = 0;
            v19 = *(_QWORD *)(*(_QWORD *)(a3 + 24) + 8LL * v15) & 0xFFFFFFFFFFLL;
            v20 = *(_QWORD *)(*(_QWORD *)(a3 + 24) + 8LL * v15) >> 40;
            if ( (_DWORD)v20 )
            {
              do
              {
                v21 = v18++;
                *j++ = v19 + v21;
              }
              while ( v18 < (unsigned int)v20 );
              v16 = v24;
            }
          }
          v22 = MmMapLockedPagesSpecifyCache(*(PMDL *)(a3 + 16), 0, MmCached, 0, 0, 0x40000010u);
          *(_QWORD *)a3 = v22;
          if ( v22 )
            return 0;
          v6 = -1073741670;
          VidTraceErrorStatusInternal0(
            "VsmmPhuStorepSerializationBufferSetupRestore",
            "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
            10530,
            3221225626LL);
        }
        else
        {
          v6 = -1073741670;
          VidTraceErrorStatusInternal0(
            "VsmmPhuStorepSerializationBufferSetupRestore",
            "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
            10494,
            3221225626LL);
        }
      }
      else if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v29, "VsmmPhuStorepSerializationBufferSetupRestore");
        tlgCreate1Sz_char(v30, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
        v25 = 10472;
        v31 = &v25;
        v32 = 4;
        v33 = &v26;
        v27 = v24;
        v26 = v6;
        v35 = (int *)&v27;
        v34 = 4;
        v36 = 4;
        tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140065110, byte_14004F3A9, 0, 0, 7u, &v28);
      }
    }
    else
    {
      v6 = -1073741670;
      VidTraceErrorStatusInternal0(
        "VsmmPhuStorepSerializationBufferSetupRestore",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
        10457,
        3221225626LL);
    }
  }
  else
  {
    VidTraceErrorStatusInternal0(
      "VsmmPhuStorepSerializationBufferSetupRestore",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
      10438,
      (unsigned int)v6);
  }
  LOBYTE(v7) = 1;
  VsmmPhuStorepSerializationBufferTeardown(a1, v7, a3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400ba364  mov     [rsp-8+arg_8], rbx
0x1400ba369  mov     [rsp-8+arg_18], rsi
0x1400ba36e  push    rbp
0x1400ba36f  push    rdi
0x1400ba370  push    r14
0x1400ba372  lea     rbp, [rsp-47h]
0x1400ba377  sub     rsp, 0C0h
0x1400ba37e  mov     rax, cs:__security_cookie
0x1400ba385  xor     rax, rsp
0x1400ba388  mov     [rbp+57h+var_20], rax
0x1400ba38c  xorps   xmm0, xmm0
0x1400ba38f  xor     eax, eax
0x1400ba391  movups  xmmword ptr [r8], xmm0
0x1400ba395  mov     rdi, r8
0x1400ba398  xor     r14d, r14d
0x1400ba39b  movups  xmmword ptr [r8+10h], xmm0
0x1400ba3a0  xor     r9d, r9d
0x1400ba3a3  mov     rsi, rcx
0x1400ba3a6  movups  xmmword ptr [r8+20h], xmm0
0x1400ba3ab  mov     [r8+30h], rax
0x1400ba3af  lea     rax, [rbp+57h+var_A0]
0x1400ba3b3  mov     [r8+8], rdx
0x1400ba3b7  xor     r8d, r8d
0x1400ba3ba  mov     qword ptr [rsp+0D0h+Priority], rax
0x1400ba3bf  mov     [rsp+0D0h+BugCheckOnFailure], r14d
0x1400ba3c4  mov     [rbp+57h+var_A0], r14d
0x1400ba3c8  call    cs:__imp_KsrClaimPersistedMemory
0x1400ba3cf  nop     dword ptr [rax+rax+00h]
0x1400ba3d4  cmp     eax, 0C0000023h
0x1400ba3d9  mov     ebx, r14d
0x1400ba3dc  cmovnz  ebx, eax
0x1400ba3df  test    ebx, ebx
0x1400ba3e1  jns     short loc_1400BA404
0x1400ba3e3  mov     r9d, ebx
0x1400ba3e6  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400ba3ed  mov     r8d, 28C6h
0x1400ba3f3  lea     rcx, aVsmmphustoreps_0; "VsmmPhuStorepSerializationBufferSetupRe"...
0x1400ba3fa  call    VidTraceErrorStatusInternal0
0x1400ba3ff  jmp     loc_1400BA697
0x1400ba404  mov     eax, [rbp+57h+var_A0]
0x1400ba407  mov     ecx, 102h
0x1400ba40c  mov     edx, eax
0x1400ba40e  mov     [rdi+20h], eax
0x1400ba411  shl     rdx, 3
0x1400ba415  mov     r8d, 6D4D6456h
0x1400ba41b  call    cs:__imp_ExAllocatePool2
0x1400ba422  nop     dword ptr [rax+rax+00h]
0x1400ba427  mov     [rdi+18h], rax
0x1400ba42b  test    rax, rax
0x1400ba42e  jnz     short loc_1400BA457
0x1400ba430  mov     r9d, 0C000009Ah
0x1400ba436  mov     ebx, r9d
0x1400ba439  mov     r8d, 28D9h
0x1400ba43f  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400ba446  lea     rcx, aVsmmphustoreps_0; "VsmmPhuStorepSerializationBufferSetupRe"...
0x1400ba44d  call    VidTraceErrorStatusInternal0
0x1400ba452  jmp     loc_1400BA697
0x1400ba457  mov     r9d, [rbp+57h+var_A0]
0x1400ba45b  lea     rcx, [rbp+57h+var_A0]
0x1400ba45f  mov     rdx, [rdi+8]
0x1400ba463  mov     r8, rax
0x1400ba466  mov     qword ptr [rsp+0D0h+Priority], rcx
0x1400ba46b  mov     rcx, rsi
0x1400ba46e  mov     [rsp+0D0h+BugCheckOnFailure], r14d
0x1400ba473  call    cs:__imp_KsrClaimPersistedMemory
0x1400ba47a  nop     dword ptr [rax+rax+00h]
0x1400ba47f  mov     ebx, eax
0x1400ba481  test    eax, eax
0x1400ba483  jns     loc_1400BA544
0x1400ba489  mov     ecx, cs:dword_140065110
0x1400ba48f  mov     eax, 2
0x1400ba494  cmp     ecx, eax
0x1400ba496  jbe     loc_1400BA697
0x1400ba49c  mov     edx, 100h
0x1400ba4a1  lea     rcx, dword_140065110
0x1400ba4a8  call    _tlgKeywordOn
0x1400ba4ad  test    al, al
0x1400ba4af  jz      loc_1400BA697
0x1400ba4b5  lea     rdx, aVsmmphustoreps_0; "VsmmPhuStorepSerializationBufferSetupRe"...
0x1400ba4bc  lea     rcx, [rbp+57h+var_70]
0x1400ba4c0  call    _tlgCreate1Sz_char
0x1400ba4c5  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400ba4cc  lea     rcx, [rbp+57h+var_60]
0x1400ba4d0  call    _tlgCreate1Sz_char
0x1400ba4d5  lea     rax, [rbp+57h+var_9C]
0x1400ba4d9  mov     [rbp+57h+var_9C], 28E8h
0x1400ba4e0  mov     [rbp+57h+var_50], rax
0x1400ba4e4  lea     rdx, byte_14004F3A9
0x1400ba4eb  lea     rax, [rbp+57h+var_98]
0x1400ba4ef  mov     [rbp+57h+var_48], 4
0x1400ba4f7  mov     [rbp+57h+var_40], rax
0x1400ba4fb  lea     rcx, dword_140065110
0x1400ba502  mov     eax, [rbp+57h+var_A0]
0x1400ba505  xor     r9d, r9d
0x1400ba508  mov     [rbp+57h+var_94], eax
0x1400ba50b  xor     r8d, r8d
0x1400ba50e  lea     rax, [rbp+57h+var_94]
0x1400ba512  mov     [rbp+57h+var_98], ebx
0x1400ba515  mov     [rbp+57h+var_30], rax
0x1400ba519  lea     rax, [rbp+57h+var_90]
0x1400ba51d  mov     qword ptr [rsp+0D0h+Priority], rax
0x1400ba522  mov     [rsp+0D0h+BugCheckOnFailure], 7
0x1400ba52a  mov     [rbp+57h+var_38], 4
0x1400ba532  mov     [rbp+57h+var_28], 4
0x1400ba53a  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400ba53f  jmp     loc_1400BA697
0x1400ba544  mov     r9d, [rbp+57h+var_A0]
0x1400ba548  mov     r8d, r14d
0x1400ba54b  test    r9d, r9d
0x1400ba54e  jz      short loc_1400BA56B
0x1400ba550  mov     r10, [rdi+18h]
0x1400ba554  mov     edx, r14d
0x1400ba557  mov     eax, edx
0x1400ba559  inc     edx
0x1400ba55b  mov     rcx, [r10+rax*8]
0x1400ba55f  shr     rcx, 28h
0x1400ba563  add     r8d, ecx
0x1400ba566  cmp     edx, r9d
0x1400ba569  jb      short loc_1400BA557
0x1400ba56b  mov     ebx, r8d
0x1400ba56e  mov     ecx, 100h
0x1400ba573  mov     r8d, 6D4D6456h
0x1400ba579  lea     rdx, ds:30h[rbx*8]
0x1400ba581  call    cs:__imp_ExAllocatePool2
0x1400ba588  nop     dword ptr [rax+rax+00h]
0x1400ba58d  mov     [rdi+10h], rax
0x1400ba591  mov     rcx, rax
0x1400ba594  test    rax, rax
0x1400ba597  jnz     short loc_1400BA5C0
0x1400ba599  mov     r9d, 0C000009Ah
0x1400ba59f  mov     ebx, r9d
0x1400ba5a2  mov     r8d, 28FEh
0x1400ba5a8  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400ba5af  lea     rcx, aVsmmphustoreps_0; "VsmmPhuStorepSerializationBufferSetupRe"...
0x1400ba5b6  call    VidTraceErrorStatusInternal0
0x1400ba5bb  jmp     loc_1400BA697
0x1400ba5c0  mov     [rax+0Ch], r14
0x1400ba5c4  mov     edx, r14d
0x1400ba5c7  mov     [rax+14h], r14
0x1400ba5cb  mov     [rax+1Ch], r14d
0x1400ba5cf  mov     [rax], r14
0x1400ba5d2  lea     eax, [rbx+6]
0x1400ba5d5  shl     ax, 3
0x1400ba5d9  shl     rbx, 0Ch
0x1400ba5dd  mov     [rcx+8], ax
0x1400ba5e1  mov     [rcx+20h], r14
0x1400ba5e5  mov     [rcx+2Ch], r14d
0x1400ba5e9  mov     [rcx+28h], ebx
0x1400ba5ec  mov     word ptr [rcx+0Ah], 2
0x1400ba5f2  mov     r8, [rdi+10h]
0x1400ba5f6  mov     r10d, [rbp+57h+var_A0]
0x1400ba5fa  add     r8, 30h ; '0'
0x1400ba5fe  test    r10d, r10d
0x1400ba601  jz      short loc_1400BA647
0x1400ba603  mov     rax, [rdi+18h]
0x1400ba607  mov     ecx, edx
0x1400ba609  mov     r9, [rax+rcx*8]
0x1400ba60d  mov     rax, 0FFFFFFFFFFh
0x1400ba617  mov     r11, r9
0x1400ba61a  mov     ecx, r14d
0x1400ba61d  and     r11, rax
0x1400ba620  shr     r9, 28h
0x1400ba624  test    r9d, r9d
0x1400ba627  jz      short loc_1400BA640
0x1400ba629  mov     eax, ecx
0x1400ba62b  inc     ecx
0x1400ba62d  add     rax, r11
0x1400ba630  mov     [r8], rax
0x1400ba633  add     r8, 8
0x1400ba637  cmp     ecx, r9d
0x1400ba63a  jb      short loc_1400BA629
0x1400ba63c  mov     r10d, [rbp+57h+var_A0]
0x1400ba640  inc     edx
0x1400ba642  cmp     edx, r10d
0x1400ba645  jb      short loc_1400BA603
0x1400ba647  mov     rcx, [rdi+10h]; MemoryDescriptorList
0x1400ba64b  xor     r9d, r9d; RequestedAddress
0x1400ba64e  mov     [rsp+0D0h+Priority], 40000010h; Priority
0x1400ba656  xor     edx, edx; AccessMode
0x1400ba658  mov     [rsp+0D0h+BugCheckOnFailure], r14d; BugCheckOnFailure
0x1400ba65d  lea     r8d, [r9+1]; CacheType
0x1400ba661  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400ba668  nop     dword ptr [rax+rax+00h]
0x1400ba66d  mov     [rdi], rax
0x1400ba670  test    rax, rax
0x1400ba673  jnz     short loc_1400BA6A6
0x1400ba675  mov     r9d, 0C000009Ah
0x1400ba67b  mov     ebx, r9d
0x1400ba67e  mov     r8d, 2922h
0x1400ba684  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400ba68b  lea     rcx, aVsmmphustoreps_0; "VsmmPhuStorepSerializationBufferSetupRe"...
0x1400ba692  call    VidTraceErrorStatusInternal0
0x1400ba697  mov     r8, rdi
0x1400ba69a  mov     dl, 1
0x1400ba69c  mov     rcx, rsi
0x1400ba69f  call    VsmmPhuStorepSerializationBufferTeardown
0x1400ba6a4  jmp     short loc_1400BA6A9
0x1400ba6a6  mov     ebx, r14d
0x1400ba6a9  mov     eax, ebx
0x1400ba6ab  mov     rcx, [rbp+57h+var_20]
0x1400ba6af  xor     rcx, rsp; StackCookie
0x1400ba6b2  call    __security_check_cookie
0x1400ba6b7  lea     r11, [rsp+0D0h+var_10]
0x1400ba6bf  mov     rbx, [r11+28h]
0x1400ba6c3  mov     rsi, [r11+38h]
0x1400ba6c7  mov     rsp, r11
0x1400ba6ca  pop     r14
0x1400ba6cc  pop     rdi
0x1400ba6cd  pop     rbp
0x1400ba6ce  retn
```
