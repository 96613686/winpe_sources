# VidResourcePartitionStateKsrRestore

- ea: `0x14009522c`
- end: `0x14009563e`
- name: `VidResourcePartitionStateKsrRestore`
- size: `1042`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400d216c`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x14002f724`
- `0x140077958`
- `0x14009522c`
- `0x140095644`
- `0x140095724`

## import_xrefs

- `ntoskrnl!RtlRbInsertNodeEx` at `0x140095571`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x140095571`
- `ntoskrnl!MmSizeOfMdl` at `0x1400952e8`
- `ntoskrnl!MmSizeOfMdl` at `0x1400952e8`
- `ntoskrnl!MmUnmapLockedPages` at `0x14009559d`
- `ntoskrnl!MmUnmapLockedPages` at `0x14009559d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140095479`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140095479`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400955b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400955cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400955b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400955cf`
- `ntoskrnl!ExAllocatePool2` at `0x140095302`
- `ntoskrnl!ExAllocatePool2` at `0x140095302`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrFreePersistedMemoryBlock` at `0x1400955e8`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrFreePersistedMemoryBlock` at `0x1400955e8`

## pseudocode

```c
__int64 __fastcall VidResourcePartitionStateKsrRestore(__int64 a1, __int64 a2)
{
  _QWORD *v2; // r15
  __int64 v3; // r12
  __int64 v4; // rdi
  int v5; // eax
  __int64 v6; // r8
  _QWORD *v7; // r13
  unsigned int v8; // ebx
  unsigned int v9; // ebx
  char *v10; // rsi
  unsigned int i; // edx
  __int64 v12; // rax
  SIZE_T v13; // rax
  __int64 Pool2; // rax
  struct _MDL *v15; // rdi
  int v16; // r9d
  unsigned __int64 *v17; // r8
  unsigned int v18; // ecx
  __int64 v19; // r9
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // rax
  _QWORD *v22; // rax
  _QWORD *v23; // rsi
  _QWORD *v24; // rax
  char *v25; // rax
  __int64 v26; // r8
  unsigned __int64 v27; // r14
  unsigned __int64 v28; // rbx
  int v29; // r15d
  char *v30; // rax
  unsigned __int64 v31; // rax
  unsigned int v33; // [rsp+30h] [rbp-99h] BYREF
  PVOID P; // [rsp+38h] [rbp-91h] BYREF
  __int64 v35; // [rsp+40h] [rbp-89h]
  char *j; // [rsp+48h] [rbp-81h] BYREF
  _QWORD *v37; // [rsp+50h] [rbp-79h]
  char v38[32]; // [rsp+60h] [rbp-69h] BYREF
  char v39[16]; // [rsp+80h] [rbp-49h] BYREF
  char v40[16]; // [rsp+90h] [rbp-39h] BYREF
  unsigned int *v41; // [rsp+A0h] [rbp-29h]
  __int64 v42; // [rsp+A8h] [rbp-21h]
  PVOID *p_P; // [rsp+B0h] [rbp-19h]
  __int64 v44; // [rsp+B8h] [rbp-11h]
  char **p_j; // [rsp+C0h] [rbp-9h]
  __int64 v46; // [rsp+C8h] [rbp-1h]

  v2 = VidDeviceExtension;
  v3 = 0;
  v37 = VidDeviceExtension;
  v33 = 0;
  P = 0;
  v4 = a2;
  v35 = a2;
  v5 = VidResourcePartitionpClaimPersistedMemory(a1, a2, &P, &v33);
  v7 = P;
  v8 = v5;
  if ( v5 >= 0 )
  {
    v9 = v33;
    if ( v33 )
    {
      v10 = 0;
      for ( i = 0; i < v33; ++i )
      {
        v12 = i;
        v10 += *((_QWORD *)P + v12) >> 40;
      }
      v13 = MmSizeOfMdl(0, (_QWORD)v10 << 12);
      Pool2 = ExAllocatePool2(256, v13, 1917084758);
      v15 = (struct _MDL *)Pool2;
      if ( Pool2 )
      {
        *(_QWORD *)Pool2 = 0;
        v17 = (unsigned __int64 *)(Pool2 + 48);
        *(_QWORD *)(Pool2 + 32) = 0;
        v18 = 0;
        *(_DWORD *)(Pool2 + 44) = 0;
        *(_WORD *)(Pool2 + 8) = 8 * ((_WORD)v10 + 6);
        *(_DWORD *)(Pool2 + 40) = (_DWORD)v10 << 12;
        for ( *(_WORD *)(Pool2 + 10) = 2; v18 < v9; ++v18 )
        {
          v19 = v7[v18] & 0xFFFFFFFFFFLL;
          v20 = 0;
          if ( (v7[v18] & 0xFFFFFF0000000000uLL) != 0 )
          {
            do
            {
              v21 = v20 + v19;
              ++v20;
              *v17++ = v21;
            }
            while ( v20 < v7[v18] >> 40 );
          }
        }
        v22 = MmMapLockedPagesSpecifyCache(v15, 0, MmCached, 0, 0, 0x40000010u);
        v23 = v22;
        if ( !v22 )
        {
          v8 = -1073741670;
          VidTraceErrorStatusInternal0(
            "VidResourcePartitionStateKsrRestore",
            "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c",
            2517,
            3221225626LL);
          goto LABEL_41;
        }
        if ( !*v22 )
          goto LABEL_39;
        v24 = v22 + 1;
LABEL_19:
        v25 = (char *)VidResourcePartitionpAllocate(&v24[2 * v3], 0);
        P = v25;
        if ( v25 )
        {
          v27 = (unsigned __int64)(v2 + 276);
          v28 = v2[276];
          if ( (v2[277] & 1) != 0 && v28 )
            v28 ^= v27;
          LOBYTE(v26) = 0;
          v29 = v2[277] & 1;
          if ( !v28 )
            goto LABEL_38;
          v30 = v25 + 8;
          for ( j = v30; ; v30 = j )
          {
            if ( (int)VidResourcePartitionCompareById(v30, v28, v26) < 0 )
            {
              v31 = *(_QWORD *)v28;
              if ( v29 )
              {
                if ( !v31 )
                  goto LABEL_36;
                v31 ^= v28;
              }
              if ( !v31 )
              {
LABEL_36:
                LOBYTE(v26) = 0;
LABEL_37:
                v25 = (char *)P;
LABEL_38:
                RtlRbInsertNodeEx(v27, v28, v26, v25 + 32);
                v2 = v37;
                v24 = v23 + 1;
                if ( (unsigned __int64)++v3 >= *v23 )
                {
LABEL_39:
                  v8 = 0;
                  goto LABEL_40;
                }
                goto LABEL_19;
              }
            }
            else
            {
              v31 = *(_QWORD *)(v28 + 8);
              if ( v29 )
              {
                if ( !v31 )
                  goto LABEL_30;
                v31 ^= v28;
              }
              if ( !v31 )
              {
LABEL_30:
                LOBYTE(v26) = 1;
                goto LABEL_37;
              }
            }
            v28 = v31;
          }
        }
        v8 = -1073741670;
        VidTraceErrorStatusInternal0(
          "VidResourcePartitionStateKsrRestore",
          "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c",
          2532,
          3221225626LL);
LABEL_40:
        MmUnmapLockedPages(v23, v15);
LABEL_41:
        ExFreePoolWithTag(v15, 0x72446456u);
      }
      else
      {
        v8 = -1073741670;
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v39, "VidResourcePartitionStateKsrRestore");
          tlgCreate1Sz_char(v40, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
          LODWORD(P) = v16;
          v41 = &v33;
          v33 = 2477;
          p_P = &P;
          v42 = 4;
          p_j = &j;
          v44 = 4;
          j = v10;
          v46 = 8;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_14004820A, 0, 0, 7, v38);
        }
      }
      v4 = v35;
    }
    else
    {
      v8 = 0;
    }
  }
  else
  {
    VidTraceErrorStatusInternal0(
      "VidResourcePartitionStateKsrRestore",
      "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c",
      2450,
      (unsigned int)v5);
  }
  if ( v7 )
    ExFreePoolWithTag(v7, 0x72446456u);
  LOBYTE(v6) = 1;
  KsrFreePersistedMemoryBlock(&VSMM_KSR_GLOBAL_STATE_GUID, v4, v6);
  return v8;
}

```

## disassembly

```asm
0x14009522c  push    rbp
0x14009522e  push    rbx
0x14009522f  push    rsi
0x140095230  push    rdi
0x140095231  push    r12
0x140095233  push    r13
0x140095235  push    r14
0x140095237  push    r15
0x140095239  lea     rbp, [rsp-1Fh]
0x14009523e  sub     rsp, 0E8h
0x140095245  mov     rax, cs:__security_cookie
0x14009524c  xor     rax, rsp
0x14009524f  mov     [rbp+57h+var_50], rax
0x140095253  mov     r15, cs:VidDeviceExtension
0x14009525a  lea     r9, [rsp+120h+var_F0]
0x14009525f  xor     r12d, r12d
0x140095262  mov     [rbp+57h+var_D0], r15
0x140095266  lea     r8, [rsp+120h+P]
0x14009526b  mov     [rsp+120h+var_F0], r12d
0x140095270  mov     [rsp+120h+P], r12
0x140095275  mov     rdi, rdx
0x140095278  mov     [rsp+120h+var_E0], rdx
0x14009527d  call    VidResourcePartitionpClaimPersistedMemory
0x140095282  mov     r13, [rsp+120h+P]
0x140095287  mov     ebx, eax
0x140095289  test    eax, eax
0x14009528b  jns     short loc_1400952AE
0x14009528d  mov     r9d, eax
0x140095290  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140095297  mov     r8d, 992h
0x14009529d  lea     rcx, aVidresourcepar_7; "VidResourcePartitionStateKsrRestore"
0x1400952a4  call    VidTraceErrorStatusInternal0
0x1400952a9  jmp     loc_1400955C2
0x1400952ae  mov     ebx, [rsp+120h+var_F0]
0x1400952b2  test    ebx, ebx
0x1400952b4  jnz     short loc_1400952BE
0x1400952b6  mov     ebx, r12d
0x1400952b9  jmp     loc_1400955C2
0x1400952be  mov     rsi, r12
0x1400952c1  mov     edx, r12d
0x1400952c4  test    ebx, ebx
0x1400952c6  jz      short loc_1400952DC
0x1400952c8  mov     eax, edx
0x1400952ca  inc     edx
0x1400952cc  mov     rcx, [r13+rax*8+0]
0x1400952d1  shr     rcx, 28h
0x1400952d5  add     rsi, rcx
0x1400952d8  cmp     edx, ebx
0x1400952da  jb      short loc_1400952C8
0x1400952dc  mov     r14, rsi
0x1400952df  xor     ecx, ecx; Base
0x1400952e1  shl     r14, 0Ch
0x1400952e5  mov     rdx, r14; Length
0x1400952e8  call    cs:__imp_MmSizeOfMdl
0x1400952ef  nop     dword ptr [rax+rax+00h]
0x1400952f4  mov     ecx, 100h
0x1400952f9  mov     r8d, 72446456h
0x1400952ff  mov     rdx, rax
0x140095302  call    cs:__imp_ExAllocatePool2
0x140095309  nop     dword ptr [rax+rax+00h]
0x14009530e  mov     rdi, rax
0x140095311  test    rax, rax
0x140095314  jnz     loc_1400953E1
0x14009531a  mov     eax, cs:dword_140065110
0x140095320  lea     ecx, [rdi+2]
0x140095323  mov     r9d, 0C000009Ah
0x140095329  mov     ebx, r9d
0x14009532c  cmp     eax, ecx
0x14009532e  jbe     loc_1400955BD
0x140095334  mov     edx, 100h
0x140095339  lea     rcx, dword_140065110
0x140095340  call    _tlgKeywordOn
0x140095345  test    al, al
0x140095347  jz      loc_1400955BD
0x14009534d  lea     rdx, aVidresourcepar_7; "VidResourcePartitionStateKsrRestore"
0x140095354  lea     rcx, [rbp+57h+var_A0]
0x140095358  call    _tlgCreate1Sz_char
0x14009535d  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140095364  lea     rcx, [rbp+57h+var_90]
0x140095368  call    _tlgCreate1Sz_char
0x14009536d  lea     rax, [rsp+120h+var_F0]
0x140095372  mov     dword ptr [rsp+120h+P], r9d
0x140095377  mov     [rbp+57h+var_80], rax
0x14009537b  lea     rdx, unk_14004820A
0x140095382  lea     rax, [rsp+120h+P]
0x140095387  mov     [rsp+120h+var_F0], 9ADh
0x14009538f  mov     [rbp+57h+var_70], rax
0x140095393  lea     rcx, dword_140065110
0x14009539a  lea     rax, [rsp+120h+var_D8]
0x14009539f  mov     [rbp+57h+var_78], 4
0x1400953a7  mov     [rbp+57h+var_60], rax
0x1400953ab  xor     r9d, r9d
0x1400953ae  lea     rax, [rbp+57h+var_C0]
0x1400953b2  mov     [rbp+57h+var_68], 4
0x1400953ba  mov     qword ptr [rsp+120h+Priority], rax
0x1400953bf  xor     r8d, r8d
0x1400953c2  mov     [rsp+120h+BugCheckOnFailure], 7
0x1400953ca  mov     [rsp+120h+var_D8], rsi
0x1400953cf  mov     [rbp+57h+var_58], 8
0x1400953d7  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400953dc  jmp     loc_1400955BD
0x1400953e1  mov     [rax], r12
0x1400953e4  lea     r8, [rdi+30h]
0x1400953e8  mov     rax, r14
0x1400953eb  mov     [rdi+20h], r12
0x1400953ef  shr     rax, 0Ch
0x1400953f3  mov     ecx, r12d
0x1400953f6  add     ax, 6
0x1400953fa  mov     [rdi+2Ch], r12d
0x1400953fe  shl     ax, 3
0x140095402  mov     [rdi+8], ax
0x140095406  mov     [rdi+28h], r14d
0x14009540a  mov     word ptr [rdi+0Ah], 2
0x140095410  test    ebx, ebx
0x140095412  jz      short loc_140095460
0x140095414  mov     rdx, 0FFFFFFFFFFh
0x14009541e  mov     r10d, ecx
0x140095421  mov     r11, 0FFFFFF0000000000h
0x14009542b  mov     rax, [r13+r10*8+0]
0x140095430  mov     r9, rax
0x140095433  and     r9, rdx
0x140095436  mov     rdx, r12
0x140095439  test    r11, rax
0x14009543c  jbe     short loc_14009545A
0x14009543e  lea     rax, [rdx+r9]
0x140095442  inc     rdx
0x140095445  mov     [r8], rax
0x140095448  add     r8, 8
0x14009544c  mov     rax, [r13+r10*8+0]
0x140095451  shr     rax, 28h
0x140095455  cmp     rdx, rax
0x140095458  jb      short loc_14009543E
0x14009545a  inc     ecx
0x14009545c  cmp     ecx, ebx
0x14009545e  jb      short loc_140095414
0x140095460  xor     r9d, r9d; RequestedAddress
0x140095463  mov     [rsp+120h+Priority], 40000010h; Priority
0x14009546b  xor     edx, edx; AccessMode
0x14009546d  mov     [rsp+120h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x140095472  mov     rcx, rdi; MemoryDescriptorList
0x140095475  lea     r8d, [r9+1]; CacheType
0x140095479  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140095480  nop     dword ptr [rax+rax+00h]
0x140095485  mov     rsi, rax
0x140095488  test    rax, rax
0x14009548b  jnz     short loc_1400954B4
0x14009548d  mov     r9d, 0C000009Ah
0x140095493  mov     ebx, r9d
0x140095496  mov     r8d, 9D5h
0x14009549c  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x1400954a3  lea     rcx, aVidresourcepar_7; "VidResourcePartitionStateKsrRestore"
0x1400954aa  call    VidTraceErrorStatusInternal0
0x1400954af  jmp     loc_1400955A9
0x1400954b4  cmp     [rax], r12
0x1400954b7  jbe     loc_140095591
0x1400954bd  add     rax, 8
0x1400954c1  mov     rcx, r12
0x1400954c4  xor     edx, edx
0x1400954c6  shl     rcx, 4
0x1400954ca  add     rcx, rax
0x1400954cd  call    VidResourcePartitionpAllocate
0x1400954d2  mov     [rsp+120h+P], rax
0x1400954d7  test    rax, rax
0x1400954da  jz      loc_140095617
0x1400954e0  test    byte ptr [r15+8A8h], 1
0x1400954e8  lea     r14, [r15+8A0h]
0x1400954ef  mov     rbx, [r14]
0x1400954f2  jz      short loc_1400954FC
0x1400954f4  test    rbx, rbx
0x1400954f7  jz      short loc_1400954FC
0x1400954f9  xor     rbx, r14
0x1400954fc  movzx   r15d, byte ptr [r14+8]
0x140095501  xor     r8b, r8b
0x140095504  and     r15d, 1
0x140095508  test    rbx, rbx
0x14009550b  jz      short loc_140095567
0x14009550d  add     rax, 8
0x140095511  mov     [rsp+120h+var_D8], rax
0x140095516  mov     rdx, rbx
0x140095519  mov     rcx, rax
0x14009551c  call    VidResourcePartitionCompareById
0x140095521  test    eax, eax
0x140095523  js      short loc_140095540
0x140095525  mov     rax, [rbx+8]
0x140095529  test    r15d, r15d
0x14009552c  jz      short loc_140095536
0x14009552e  test    rax, rax
0x140095531  jz      short loc_14009553B
0x140095533  xor     rax, rbx
0x140095536  test    rax, rax
0x140095539  jnz     short loc_140095555
0x14009553b  mov     r8b, 1
0x14009553e  jmp     short loc_140095562
0x140095540  mov     rax, [rbx]
0x140095543  test    r15d, r15d
0x140095546  jz      short loc_140095550
0x140095548  test    rax, rax
0x14009554b  jz      short loc_14009555F
0x14009554d  xor     rax, rbx
0x140095550  test    rax, rax
0x140095553  jz      short loc_14009555F
0x140095555  mov     rbx, rax
0x140095558  mov     rax, [rsp+120h+var_D8]
0x14009555d  jmp     short loc_140095516
0x14009555f  xor     r8b, r8b
0x140095562  mov     rax, [rsp+120h+P]
0x140095567  lea     r9, [rax+20h]
0x14009556b  mov     rdx, rbx
0x14009556e  mov     rcx, r14
0x140095571  call    cs:__imp_RtlRbInsertNodeEx
0x140095578  nop     dword ptr [rax+rax+00h]
0x14009557d  mov     r15, [rbp+57h+var_D0]
0x140095581  lea     rax, [rsi+8]
0x140095585  inc     r12
0x140095588  cmp     r12, [rsi]
0x14009558b  jb      loc_1400954C1
0x140095591  xor     r12d, r12d
0x140095594  mov     ebx, r12d
0x140095597  mov     rdx, rdi; MemoryDescriptorList
0x14009559a  mov     rcx, rsi; BaseAddress
0x14009559d  call    cs:__imp_MmUnmapLockedPages
0x1400955a4  nop     dword ptr [rax+rax+00h]
0x1400955a9  mov     edx, 72446456h; Tag
0x1400955ae  mov     rcx, rdi; P
0x1400955b1  call    cs:__imp_ExFreePoolWithTag
0x1400955b8  nop     dword ptr [rax+rax+00h]
0x1400955bd  mov     rdi, [rsp+120h+var_E0]
0x1400955c2  test    r13, r13
0x1400955c5  jz      short loc_1400955DB
0x1400955c7  mov     edx, 72446456h; Tag
0x1400955cc  mov     rcx, r13; P
0x1400955cf  call    cs:__imp_ExFreePoolWithTag
0x1400955d6  nop     dword ptr [rax+rax+00h]
0x1400955db  mov     r8b, 1
0x1400955de  lea     rcx, VSMM_KSR_GLOBAL_STATE_GUID
0x1400955e5  mov     rdx, rdi
0x1400955e8  call    cs:__imp_KsrFreePersistedMemoryBlock
0x1400955ef  nop     dword ptr [rax+rax+00h]
0x1400955f4  mov     eax, ebx
0x1400955f6  mov     rcx, [rbp+57h+var_50]
0x1400955fa  xor     rcx, rsp; StackCookie
0x1400955fd  call    __security_check_cookie
0x140095602  add     rsp, 0E8h
0x140095609  pop     r15
0x14009560b  pop     r14
0x14009560d  pop     r13
0x14009560f  pop     r12
0x140095611  pop     rdi
0x140095612  pop     rsi
0x140095613  pop     rbx
0x140095614  pop     rbp
0x140095615  retn
0x140095617  mov     r9d, 0C000009Ah
0x14009561d  mov     ebx, r9d
0x140095620  mov     r8d, 9E4h
0x140095626  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x14009562d  lea     rcx, aVidresourcepar_7; "VidResourcePartitionStateKsrRestore"
0x140095634  call    VidTraceErrorStatusInternal0
0x140095639  jmp     loc_140095597
```
