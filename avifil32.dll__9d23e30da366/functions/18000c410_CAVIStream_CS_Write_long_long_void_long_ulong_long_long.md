# CAVIStream::CS::Write(long,long,void *,long,ulong,long *,long *)

- ea: `0x18000c410`
- end: `0x18000c8b3`
- name: `?Write@CS@CAVIStream@@UEAAJJJPEAXJKPEAJ1@Z`
- size: `1187`
- prototype: `__int64 __fastcall(CAVIStream::CS *__hidden this, int, int, void *, unsigned int, unsigned int, int *, int *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18000bed0`
- `0x18000c410`

## callees

- `0x180001460`
- `0x180009110`
- `0x18000c410`
- `0x180014468`
- `0x180014600`
- `0x180014928`
- `0x180014960`
- `0x180015144`

## import_xrefs

- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000c810`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000c82f`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000c84e`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000c810`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000c82f`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000c84e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c47b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c47b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c4a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c4cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c60b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c623`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c639`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c718`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c7cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c881`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c4a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c4cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c60b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c623`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c639`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c718`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c7cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c881`
- `WINMM!mmioSeek` at `0x18000c6c5`
- `WINMM!mmioSeek` at `0x18000c6c5`

## pseudocode

```c
__int64 __fastcall CAVIStream::CS::Write(
        CAVIStream::CS *this,
        int a2,
        int a3,
        char *a4,
        signed int a5,
        unsigned int a6,
        int *a7,
        int *a8)
{
  CAVIStream::CS *v8; // r15
  __int64 v11; // rdi
  struct _RTL_CRITICAL_SECTION *v12; // rbx
  __int64 v14; // rax
  int v15; // r10d
  int v16; // ecx
  int v17; // edx
  int v18; // r9d
  unsigned int v19; // r8d
  int v20; // r9d
  int v21; // ecx
  int v22; // edx
  int v23; // r15d
  __int64 v24; // rcx
  __int64 v25; // rcx
  LONG v26; // edx
  __int64 v27; // rax
  __int64 StreamIndex; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  int v31; // r14d
  unsigned int v32; // eax
  __int64 v33; // r8
  unsigned int v34; // edx
  unsigned int v37[4]; // [rsp+60h] [rbp-48h] BYREF
  int v38; // [rsp+70h] [rbp-38h]

  v8 = this;
  v11 = *((_QWORD *)this + 1);
  v12 = (struct _RTL_CRITICAL_SECTION *)(*(_QWORD *)(v11 + 272) + 1264LL);
  EnterCriticalSection(v12);
  *(_OWORD *)v37 = 0;
  v38 = 0;
  if ( (*(_BYTE *)(*(_QWORD *)(v11 + 272) + 660LL) & 3) == 0 )
  {
    if ( v12 )
      LeaveCriticalSection(v12);
    return 2147762290LL;
  }
  v14 = *(_QWORD *)(v11 + 1336);
  if ( !v14 )
  {
    if ( v12 )
      LeaveCriticalSection(v12);
    return 2147549183LL;
  }
  if ( *(_DWORD *)(v11 + 64) == 1935963489 )
  {
    v15 = 25207;
    goto LABEL_19;
  }
  if ( *(_DWORD *)(v11 + 64) != 1935960438 )
    goto LABEL_18;
  if ( (a6 & 0x100) != 0 )
  {
    v15 = 25456;
    goto LABEL_19;
  }
  if ( (a6 & 0x10) != 0 || *(_DWORD *)(v14 + 16) <= 1u && a5 == *(_DWORD *)(v14 + 20) )
    v15 = 25188;
  else
LABEL_18:
    v15 = 25444;
LABEL_19:
  v16 = *(_DWORD *)(v11 + 280);
  v17 = 55;
  v18 = 55;
  v37[1] = a5;
  v19 = v16 & 0xF;
  if ( (v16 & 0xF0u) <= 0x90 )
    v18 = 48;
  v20 = ((v16 >> 4) & 0xF) + v18;
  if ( v19 <= 9 )
    v17 = 48;
  v37[0] = (v15 << 16) | ((v19 << 8) + (v17 << 8)) | v20;
  if ( a2 < 0 )
    a2 = *(_DWORD *)(v11 + 92) + *(_DWORD *)(v11 + 96);
  v21 = *(_DWORD *)(v11 + 96);
  v22 = *(_DWORD *)(v11 + 92);
  if ( a2 <= v22 + v21 )
  {
LABEL_29:
    if ( a2 >= v22 + v21 )
    {
      *(_DWORD *)(*(_QWORD *)(v11 + 272) + 728LL) = 1;
      v24 = *(_QWORD *)(v11 + 272);
      if ( !*(_DWORD *)(v24 + 704) )
      {
        *(_DWORD *)(v24 + 704) = (*(_DWORD *)(v24 + 136) + 3071) & 0xFFFFF800;
        *(_DWORD *)(*(_QWORD *)(v11 + 272) + 672LL) = *(_DWORD *)(*(_QWORD *)(v11 + 272) + 704LL) - 12;
      }
      v25 = *(_QWORD *)(v11 + 296);
      v26 = *(_DWORD *)(*(_QWORD *)(v11 + 272) + 704LL);
      v27 = *(_QWORD *)(v25 + 16);
      if ( v27 )
        *(_DWORD *)(v27 + 372) = v26;
      else
        mmioSeek(*(HMMIO *)(v25 + 8), v26, 0);
      shfileCreateChunk(*(_QWORD *)(v11 + 296), v37, 0);
      if ( a5 && shfileWrite(*(_QWORD *)(v11 + 296), a4, a5) != a5
        || (unsigned int)shfileAscend(*(_QWORD *)(v11 + 296), v37) )
      {
        if ( v12 )
          LeaveCriticalSection(v12);
        return 2147762286LL;
      }
      else
      {
        *(_DWORD *)(*(_QWORD *)(v11 + 272) + 704LL) = shfileSeek(*(_QWORD *)(v11 + 296), 0, 1);
        if ( !(unsigned int)AddToIndex(*(struct CAVIFile **)(v11 + 272), v37[0], a5, v37[3] - 8, a6) )
          goto LABEL_55;
        if ( !*(_QWORD *)(v11 + 1400) )
        {
          StreamIndex = MakeStreamIndex(
                          *(_QWORD *)(*(_QWORD *)(v11 + 272) + 1248LL),
                          *(_DWORD *)(v11 + 280),
                          *(_DWORD *)(v11 + 92) - *(_DWORD *)(v11 + 100),
                          *(_DWORD *)(v11 + 112),
                          *(_QWORD *)(*(_QWORD *)(v11 + 272) + 664LL));
          *(_QWORD *)(v11 + 1400) = StreamIndex;
          if ( (a6 & 0x100) == 0 )
            *(_DWORD *)(StreamIndex + 32) -= a3;
        }
        v29 = *(_QWORD *)(v11 + 1400);
        if ( v29 )
        {
          if ( (a6 & 0x100) == 0 )
          {
            *(_DWORD *)(v11 + 96) += a3;
            *(_DWORD *)(v29 + 32) += a3;
          }
          if ( a5 > *(_DWORD *)(v11 + 104) )
            *(_DWORD *)(v11 + 104) = a5;
          v30 = *(_QWORD *)(v11 + 272);
          if ( a5 > *(_DWORD *)(v30 + 108) )
            *(_DWORD *)(v30 + 108) = a5;
          v31 = MulDiv(*(_DWORD *)(v11 + 96), 1000 * *(_DWORD *)(v11 + 84), *(_DWORD *)(v11 + 88));
          v32 = MulDiv(v31, 1000, *(_DWORD *)(*(_QWORD *)(v11 + 272) + 80LL));
          v33 = *(_QWORD *)(v11 + 272);
          v34 = *(_DWORD *)(v33 + 96);
          if ( v34 <= v32 )
            v34 = MulDiv(v31, 1000, *(_DWORD *)(v33 + 80));
          *(_DWORD *)(*(_QWORD *)(v11 + 272) + 96LL) = v34;
          if ( a8 )
            *a8 = a5;
          if ( a7 )
            *a7 = a3;
          if ( v12 )
            LeaveCriticalSection(v12);
          return 0;
        }
        else
        {
LABEL_55:
          if ( v12 )
            LeaveCriticalSection(v12);
          return 2147762279LL;
        }
      }
    }
    else
    {
      if ( v12 )
        LeaveCriticalSection(v12);
      return 2147762277LL;
    }
  }
  else if ( *(_DWORD *)(v11 + 112) )
  {
    if ( v12 )
      LeaveCriticalSection(v12);
    return 2147762282LL;
  }
  else
  {
    while ( 1 )
    {
      v23 = CAVIStream::CS::Write(v8, v21 + v22, 1, 0, 0, 0, 0, 0);
      if ( v23 < 0 )
        break;
      v21 = *(_DWORD *)(v11 + 96);
      v22 = *(_DWORD *)(v11 + 92);
      v8 = this;
      if ( a2 <= v22 + v21 )
        goto LABEL_29;
    }
    if ( v12 )
      LeaveCriticalSection(v12);
    return (unsigned int)v23;
  }
}

```

## disassembly

```asm
0x18000c410  mov     [rsp+arg_8], rbx
0x18000c415  mov     [rsp+arg_10], rbp
0x18000c41a  push    rdi
0x18000c41b  push    r12
0x18000c41d  push    r13
0x18000c41f  push    r14
0x18000c421  push    r15
0x18000c423  sub     rsp, 80h
0x18000c42a  mov     rax, cs:__security_cookie
0x18000c431  xor     rax, rsp
0x18000c434  mov     [rsp+0A8h+var_30], rax
0x18000c439  mov     rax, [rsp+0A8h+arg_30]
0x18000c441  mov     r15, rcx
0x18000c444  mov     [rsp+0A8h+var_68], rcx
0x18000c449  mov     r13d, r8d
0x18000c44c  mov     rcx, [rsp+0A8h+arg_38]
0x18000c454  mov     r14d, edx
0x18000c457  mov     [rsp+0A8h+var_58], rcx
0x18000c45c  mov     rdi, [r15+8]
0x18000c460  mov     [rsp+0A8h+var_60], r9
0x18000c465  mov     [rsp+0A8h+var_50], rax
0x18000c46a  mov     rbx, [rdi+110h]
0x18000c471  add     rbx, 4F0h
0x18000c478  mov     rcx, rbx; lpCriticalSection
0x18000c47b  call    cs:__imp_EnterCriticalSection
0x18000c481  xor     eax, eax
0x18000c483  xorps   xmm0, xmm0
0x18000c486  movups  xmmword ptr [rsp+0A8h+var_48], xmm0
0x18000c48b  mov     [rsp+0A8h+var_38], eax
0x18000c48f  mov     rax, [rdi+110h]
0x18000c496  test    byte ptr [rax+294h], 3
0x18000c49d  jnz     short loc_18000C4B7
0x18000c49f  test    rbx, rbx
0x18000c4a2  jz      short loc_18000C4AD
0x18000c4a4  mov     rcx, rbx; lpCriticalSection
0x18000c4a7  call    cs:__imp_LeaveCriticalSection
0x18000c4ad  mov     eax, 80044072h
0x18000c4b2  jmp     loc_18000C889
0x18000c4b7  mov     rax, [rdi+538h]
0x18000c4be  test    rax, rax
0x18000c4c1  jnz     short loc_18000C4DB
0x18000c4c3  test    rbx, rbx
0x18000c4c6  jz      short loc_18000C4D1
0x18000c4c8  mov     rcx, rbx; lpCriticalSection
0x18000c4cb  call    cs:__imp_LeaveCriticalSection
0x18000c4d1  mov     eax, 8000FFFFh
0x18000c4d6  jmp     loc_18000C889
0x18000c4db  cmp     dword ptr [rdi+40h], 73647561h
0x18000c4e2  mov     r12d, [rsp+0A8h+arg_28]
0x18000c4ea  mov     ebp, [rsp+0A8h+arg_20]
0x18000c4f1  jnz     short loc_18000C4FB
0x18000c4f3  mov     r10d, 6277h
0x18000c4f9  jmp     short loc_18000C532
0x18000c4fb  cmp     dword ptr [rdi+40h], 73646976h
0x18000c502  jnz     short loc_18000C52C
0x18000c504  bt      r12d, 8
0x18000c509  jnb     short loc_18000C513
0x18000c50b  mov     r10d, 6370h
0x18000c511  jmp     short loc_18000C532
0x18000c513  test    r12b, 10h
0x18000c517  jnz     short loc_18000C524
0x18000c519  cmp     dword ptr [rax+10h], 1
0x18000c51d  ja      short loc_18000C52C
0x18000c51f  cmp     ebp, [rax+14h]
0x18000c522  jnz     short loc_18000C52C
0x18000c524  mov     r10d, 6264h
0x18000c52a  jmp     short loc_18000C532
0x18000c52c  mov     r10d, 6364h
0x18000c532  mov     ecx, [rdi+118h]
0x18000c538  mov     edx, 37h ; '7'
0x18000c53d  mov     r9d, edx
0x18000c540  mov     [rsp+0A8h+var_48+4], ebp
0x18000c544  mov     r8d, ecx
0x18000c547  mov     eax, ecx
0x18000c549  and     r8d, 0Fh
0x18000c54d  and     eax, 0F0h
0x18000c552  lea     r11d, [rdx-7]
0x18000c556  cmp     eax, 90h
0x18000c55b  cmovbe  r9d, r11d
0x18000c55f  sar     ecx, 4
0x18000c562  and     ecx, 0Fh
0x18000c565  add     r9d, ecx
0x18000c568  cmp     r8d, 9
0x18000c56c  cmovbe  edx, r11d
0x18000c570  shl     r8d, 8
0x18000c574  shl     edx, 8
0x18000c577  add     edx, r8d
0x18000c57a  shl     r10d, 10h
0x18000c57e  or      r9d, edx
0x18000c581  or      r9d, r10d
0x18000c584  mov     [rsp+0A8h+var_48], r9d
0x18000c589  test    r14d, r14d
0x18000c58c  jns     short loc_18000C596
0x18000c58e  mov     r14d, [rdi+60h]
0x18000c592  add     r14d, [rdi+5Ch]
0x18000c596  mov     ecx, [rdi+60h]
0x18000c599  mov     edx, [rdi+5Ch]
0x18000c59c  lea     eax, [rdx+rcx]
0x18000c59f  cmp     r14d, eax
0x18000c5a2  jle     short loc_18000C5FB
0x18000c5a4  cmp     dword ptr [rdi+70h], 0
0x18000c5a8  jnz     loc_18000C631
0x18000c5ae  mov     [rsp+0A8h+var_70], 0; int *
0x18000c5b7  xor     r9d, r9d; void *
0x18000c5ba  add     edx, ecx; int
0x18000c5bc  mov     [rsp+0A8h+var_78], 0; int *
0x18000c5c5  mov     [rsp+0A8h+var_80], 0; unsigned int
0x18000c5cd  mov     rcx, r15; this
0x18000c5d0  mov     [rsp+0A8h+var_88], 0; unsigned int
0x18000c5d8  lea     r8d, [r9+1]; int
0x18000c5dc  call    ?Write@CS@CAVIStream@@UEAAJJJPEAXJKPEAJ1@Z; CAVIStream::CS::Write(long,long,void *,long,ulong,long *,long *)
0x18000c5e1  mov     r15d, eax
0x18000c5e4  test    eax, eax
0x18000c5e6  js      short loc_18000C61B
0x18000c5e8  mov     ecx, [rdi+60h]
0x18000c5eb  mov     edx, [rdi+5Ch]
0x18000c5ee  mov     r15, [rsp+0A8h+var_68]
0x18000c5f3  lea     eax, [rdx+rcx]
0x18000c5f6  cmp     r14d, eax
0x18000c5f9  jg      short loc_18000C5AE
0x18000c5fb  lea     eax, [rdx+rcx]
0x18000c5fe  cmp     r14d, eax
0x18000c601  jge     short loc_18000C649
0x18000c603  test    rbx, rbx
0x18000c606  jz      short loc_18000C611
0x18000c608  mov     rcx, rbx; lpCriticalSection
0x18000c60b  call    cs:__imp_LeaveCriticalSection
0x18000c611  mov     eax, 80044065h
0x18000c616  jmp     loc_18000C889
0x18000c61b  test    rbx, rbx
0x18000c61e  jz      short loc_18000C629
0x18000c620  mov     rcx, rbx; lpCriticalSection
0x18000c623  call    cs:__imp_LeaveCriticalSection
0x18000c629  mov     eax, r15d
0x18000c62c  jmp     loc_18000C889
0x18000c631  test    rbx, rbx
0x18000c634  jz      short loc_18000C63F
0x18000c636  mov     rcx, rbx; lpCriticalSection
0x18000c639  call    cs:__imp_LeaveCriticalSection
0x18000c63f  mov     eax, 8004406Ah
0x18000c644  jmp     loc_18000C889
0x18000c649  mov     rax, [rdi+110h]
0x18000c650  mov     r14d, 1
0x18000c656  mov     [rax+2D8h], r14d
0x18000c65d  mov     rcx, [rdi+110h]
0x18000c664  cmp     dword ptr [rcx+2C0h], 0
0x18000c66b  jnz     short loc_18000C699
0x18000c66d  mov     eax, [rcx+88h]
0x18000c673  add     eax, 0BFFh
0x18000c678  and     eax, 0FFFFF800h
0x18000c67d  mov     [rcx+2C0h], eax
0x18000c683  mov     rcx, [rdi+110h]
0x18000c68a  mov     eax, [rcx+2C0h]
0x18000c690  sub     eax, 0Ch
0x18000c693  mov     [rcx+2A0h], eax
0x18000c699  mov     rax, [rdi+110h]
0x18000c6a0  mov     rcx, [rdi+128h]
0x18000c6a7  mov     edx, [rax+2C0h]; lOffset
0x18000c6ad  mov     rax, [rcx+10h]
0x18000c6b1  test    rax, rax
0x18000c6b4  jz      short loc_18000C6BE
0x18000c6b6  mov     [rax+174h], edx
0x18000c6bc  jmp     short loc_18000C6CB
0x18000c6be  mov     rcx, [rcx+8]; hmmio
0x18000c6c2  xor     r8d, r8d; iOrigin
0x18000c6c5  call    cs:__imp_mmioSeek
0x18000c6cb  mov     rcx, [rdi+128h]
0x18000c6d2  lea     rdx, [rsp+0A8h+var_48]
0x18000c6d7  xor     r8d, r8d
0x18000c6da  call    shfileCreateChunk
0x18000c6df  test    ebp, ebp
0x18000c6e1  jz      short loc_18000C6FB
0x18000c6e3  mov     rdx, [rsp+0A8h+var_60]
0x18000c6e8  mov     r8d, ebp
0x18000c6eb  mov     rcx, [rdi+128h]
0x18000c6f2  call    shfileWrite
0x18000c6f7  cmp     eax, ebp
0x18000c6f9  jnz     short loc_18000C710
0x18000c6fb  mov     rcx, [rdi+128h]
0x18000c702  lea     rdx, [rsp+0A8h+var_48]
0x18000c707  call    shfileAscend
0x18000c70c  test    eax, eax
0x18000c70e  jz      short loc_18000C728
0x18000c710  test    rbx, rbx
0x18000c713  jz      short loc_18000C71E
0x18000c715  mov     rcx, rbx; lpCriticalSection
0x18000c718  call    cs:__imp_LeaveCriticalSection
0x18000c71e  mov     eax, 8004406Eh
0x18000c723  jmp     loc_18000C889
0x18000c728  mov     rcx, [rdi+128h]
0x18000c72f  mov     r8d, r14d
0x18000c732  xor     edx, edx
0x18000c734  call    shfileSeek
0x18000c739  mov     rcx, [rdi+110h]
0x18000c740  mov     r8d, ebp; unsigned int
0x18000c743  mov     [rsp+0A8h+var_88], r12d; unsigned int
0x18000c748  mov     [rcx+2C0h], eax
0x18000c74e  mov     r9d, [rsp+0A8h+var_48+0Ch]
0x18000c753  mov     edx, [rsp+0A8h+var_48]; unsigned int
0x18000c757  add     r9d, 0FFFFFFF8h; int
0x18000c75b  mov     rcx, [rdi+110h]; struct CAVIFile *
0x18000c762  call    ?AddToIndex@@YAHPEAVCAVIFile@@KKJK@Z; AddToIndex(CAVIFile *,ulong,ulong,long,ulong)
0x18000c767  test    eax, eax
0x18000c769  jz      short loc_18000C7C4
0x18000c76b  cmp     qword ptr [rdi+578h], 0
0x18000c773  jnz     short loc_18000C7B8
0x18000c775  mov     rcx, [rdi+110h]
0x18000c77c  mov     r8d, [rdi+5Ch]
0x18000c780  sub     r8d, [rdi+64h]
0x18000c784  mov     r9d, [rdi+70h]
0x18000c788  mov     rax, [rcx+298h]
0x18000c78f  mov     rcx, [rcx+4E0h]
0x18000c796  mov     edx, [rdi+118h]
0x18000c79c  mov     qword ptr [rsp+0A8h+var_88], rax
0x18000c7a1  call    MakeStreamIndex
0x18000c7a6  mov     [rdi+578h], rax
0x18000c7ad  bt      r12d, 8
0x18000c7b2  jb      short loc_18000C7B8
0x18000c7b4  sub     [rax+20h], r13d
0x18000c7b8  mov     rax, [rdi+578h]
0x18000c7bf  test    rax, rax
0x18000c7c2  jnz     short loc_18000C7DC
0x18000c7c4  test    rbx, rbx
0x18000c7c7  jz      short loc_18000C7D2
0x18000c7c9  mov     rcx, rbx; lpCriticalSection
0x18000c7cc  call    cs:__imp_LeaveCriticalSection
0x18000c7d2  mov     eax, 80044067h
0x18000c7d7  jmp     loc_18000C889
0x18000c7dc  bt      r12d, 8
0x18000c7e1  jb      short loc_18000C7EB
0x18000c7e3  add     [rdi+60h], r13d
0x18000c7e7  add     [rax+20h], r13d
0x18000c7eb  cmp     ebp, [rdi+68h]
0x18000c7ee  jle     short loc_18000C7F3
0x18000c7f0  mov     [rdi+68h], ebp
0x18000c7f3  mov     rax, [rdi+110h]
0x18000c7fa  cmp     ebp, [rax+6Ch]
0x18000c7fd  jle     short loc_18000C802
0x18000c7ff  mov     [rax+6Ch], ebp
0x18000c802  imul    edx, [rdi+54h], 3E8h; nNumerator
0x18000c809  mov     r8d, [rdi+58h]; nDenominator
0x18000c80d  mov     ecx, [rdi+60h]; nNumber
0x18000c810  call    cs:__imp_MulDiv
0x18000c816  mov     r8, [rdi+110h]
0x18000c81d  mov     r15d, 3E8h
0x18000c823  mov     edx, r15d; nNumerator
0x18000c826  mov     ecx, eax; nNumber
0x18000c828  mov     r14d, eax
0x18000c82b  mov     r8d, [r8+50h]; nDenominator
0x18000c82f  call    cs:__imp_MulDiv
0x18000c835  mov     r8, [rdi+110h]
0x18000c83c  mov     edx, [r8+60h]
0x18000c840  cmp     edx, eax
0x18000c842  ja      short loc_18000C856
0x18000c844  mov     r8d, [r8+50h]; nDenominator
0x18000c848  mov     edx, r15d; nNumerator
0x18000c84b  mov     ecx, r14d; nNumber
0x18000c84e  call    cs:__imp_MulDiv
0x18000c854  mov     edx, eax
0x18000c856  mov     rcx, [rdi+110h]
0x18000c85d  mov     rax, [rsp+0A8h+var_58]
0x18000c862  mov     [rcx+60h], edx
0x18000c865  test    rax, rax
0x18000c868  jz      short loc_18000C86C
0x18000c86a  mov     [rax], ebp
0x18000c86c  mov     rax, [rsp+0A8h+var_50]
0x18000c871  test    rax, rax
0x18000c874  jz      short loc_18000C879
0x18000c876  mov     [rax], r13d
0x18000c879  test    rbx, rbx
0x18000c87c  jz      short loc_18000C887
0x18000c87e  mov     rcx, rbx; lpCriticalSection
0x18000c881  call    cs:__imp_LeaveCriticalSection
0x18000c887  xor     eax, eax
0x18000c889  mov     rcx, [rsp+0A8h+var_30]
0x18000c88e  xor     rcx, rsp; StackCookie
0x18000c891  call    __security_check_cookie
0x18000c896  lea     r11, [rsp+0A8h+var_28]
0x18000c89e  mov     rbx, [r11+38h]
0x18000c8a2  mov     rbp, [r11+40h]
0x18000c8a6  mov     rsp, r11
0x18000c8a9  pop     r15
0x18000c8ab  pop     r14
0x18000c8ad  pop     r13
0x18000c8af  pop     r12
0x18000c8b1  pop     rdi
0x18000c8b2  retn
```
