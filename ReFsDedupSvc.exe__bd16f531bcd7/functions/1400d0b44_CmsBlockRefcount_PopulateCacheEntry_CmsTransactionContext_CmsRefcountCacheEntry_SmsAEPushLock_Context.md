# CmsBlockRefcount::PopulateCacheEntry(CmsTransactionContext *,CmsRefcountCacheEntry *,SmsAEPushLock::Context *)

- ea: `0x1400d0b44`
- end: `0x1400d10bb`
- name: `?PopulateCacheEntry@CmsBlockRefcount@@AEAAJPEAVCmsTransactionContext@@PEAVCmsRefcountCacheEntry@@PEAUContext@SmsAEPushLock@@@Z`
- size: `1399`
- prototype: `int(CmsBlockRefcount *__hidden this, struct CmsTransactionContext *, struct CmsRefcountCacheEntry *, struct SmsAEPushLock::Context *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1400cfcf8`

## callees

- `0x14007ec4c`
- `0x1400854bc`
- `0x1400a2a8c`
- `0x1400a9fa4`
- `0x1400cf414`
- `0x1400d0b44`
- `0x1400d1ac0`

## import_xrefs

- `ntdll!RtlCopyMemoryNonTemporal` at `0x1400d0f7b`
- `ntdll!RtlCopyMemoryNonTemporal` at `0x1400d0f7b`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400d0cdc`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400d0cdc`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400d0cea`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400d0cea`

## pseudocode

```c
__int64 __fastcall CmsBlockRefcount::PopulateCacheEntry(
        CmsBlockRefcount *this,
        CmsVolume **a2,
        struct CmsRefcountCacheEntry *a3,
        struct SmsAEPushLock::Context *a4)
{
  struct CmsRefcountCacheEntry *v5; // r15
  CmsBlockRefcount *v6; // r14
  __int64 v7; // rcx
  unsigned int v9; // ebx
  int Array; // esi
  struct SmsPage *v11; // r8
  CmsVolume *v12; // r14
  unsigned int v13; // r9d
  struct SmsPage *v14; // rsi
  unsigned int v15; // edi
  int *v16; // rcx
  int v17; // r10d
  int *v18; // rdx
  int v19; // eax
  struct _SmsTriageContext *v20; // rdi
  _QWORD *v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // r12
  CmsVolume *v24; // r14
  struct SmsPage *v25; // rsi
  unsigned int v26; // edi
  _DWORD *v27; // rcx
  int v28; // eax
  bool v29; // zf
  CmsVolume *v30; // r15
  struct SmsPage *v31; // r14
  unsigned int v32; // edi
  int v33; // eax
  unsigned __int64 v34; // rdi
  unsigned __int64 v35; // r14
  int v36; // r12d
  unsigned __int64 v37; // rdx
  struct SmsPage *v38; // r8
  CmsVolume *v39; // r12
  struct SmsPage *v40; // r14
  unsigned int v41; // edi
  int *v42; // rcx
  int v43; // r9d
  int *v44; // rdx
  int v45; // eax
  int v47; // [rsp+50h] [rbp-51h] BYREF
  __int16 v48; // [rsp+54h] [rbp-4Dh]
  unsigned __int64 *v49; // [rsp+58h] [rbp-49h]
  unsigned __int64 v50; // [rsp+60h] [rbp-41h] BYREF
  __int64 v51; // [rsp+68h] [rbp-39h]
  struct SmsPage *v52[2]; // [rsp+70h] [rbp-31h] BYREF
  __int128 v53; // [rsp+80h] [rbp-21h]
  __int64 v54; // [rsp+90h] [rbp-11h]
  __int128 v55; // [rsp+98h] [rbp-9h] BYREF
  int v56; // [rsp+A8h] [rbp+7h]
  __int64 v57; // [rsp+B0h] [rbp+Fh]
  _BYTE v58[64]; // [rsp+B8h] [rbp+17h] BYREF
  int v60; // [rsp+108h] [rbp+67h]

  v50 = *((_QWORD *)a3 + 2);
  v56 = 0;
  v48 = 0;
  v5 = a3;
  v57 = 0;
  v49 = &v50;
  v51 = 1024;
  v6 = this;
  v7 = *((_QWORD *)this + 1);
  v54 = 0;
  v47 = 16;
  v55 = 0;
  *(_OWORD *)v52 = 0;
  v53 = 0;
  v9 = 3;
  Array = CmsTable::PinRow(v7, a2, &v47, 0, &v55, v52, 0);
  if ( Array >= 0 )
  {
LABEL_24:
    v23 = v57;
    if ( *(_BYTE *)(v57 + 16) != 1 )
      return (unsigned int)-1073741637;
    v34 = 0;
    if ( *(_QWORD *)v57 > v50 )
      v34 = *(_QWORD *)v57 - v50;
    v35 = v51 - v34;
    if ( *(_QWORD *)(v57 + 8) < v51 - v34 )
      v35 = *(_QWORD *)(v57 + 8);
    if ( (*(_BYTE *)(v57 + 20) & 1) != 0 )
    {
      v60 = *(_DWORD *)(v57 + 24);
      Array = CmsRefcountCacheEntry::AllocateArray(v5);
      if ( Array >= 0 )
      {
        RtlCopyMemoryNonTemporal(*((_QWORD *)v5 + 9) + 2 * v34, v23 + 28 + 4 * v34, 2 * v35);
        *((_DWORD *)v5 + 16) += v60;
      }
    }
    else
    {
      v36 = *(unsigned __int16 *)(v57 + 28);
      Array = CmsRefcountCacheEntry::AllocateArray(v5);
      if ( Array >= 0 )
      {
        v37 = v35 + v34;
        while ( v34 < v37 )
        {
          *(_WORD *)(*((_QWORD *)v5 + 9) + 2 * v34) = v36 | *(_WORD *)(*((_QWORD *)v5 + 9) + 2 * v34) & 0xE000;
          ++v34;
        }
        *((_DWORD *)v5 + 16) = v36 * v35;
      }
    }
    v38 = v52[0];
    if ( !v52[0] )
    {
LABEL_92:
      if ( Array >= 0 && (*((_BYTE *)v5 + 50) & 1) == 0 )
        _InterlockedOr16((volatile signed __int16 *)v5 + 25, 1u);
      return (unsigned int)Array;
    }
    v39 = a2[1];
    while ( 1 )
    {
      v40 = 0;
      v41 = v9;
      if ( *((_QWORD *)v38 + 38) )
      {
        v42 = (int *)((char *)v38 + 312);
        if ( (v9 & 1) != 0 )
        {
          v43 = *v42;
          if ( *((_DWORD *)v38 + 96) == *v42 )
          {
            v44 = (int *)((char *)v38 + 316);
            v40 = (struct SmsPage *)*((_QWORD *)v38 + 38);
            if ( (v9 & 4) == 0 )
              goto LABEL_88;
            v45 = *v44;
            if ( *((_DWORD *)v38 + 97) != *v44 )
            {
              v41 = v9 & 0xFFFFFFFB;
              goto LABEL_88;
            }
LABEL_87:
            *v44 = v45 - 1;
LABEL_88:
            *v42 = v43 - 1;
            if ( v43 == 1 )
              *((_QWORD *)v38 + 38) = 0;
            goto LABEL_90;
          }
        }
        if ( (v9 & 4) != 0 )
        {
          v44 = (int *)((char *)v38 + 316);
          v45 = *((_DWORD *)v38 + 79);
          if ( *((_DWORD *)v38 + 97) == v45 )
          {
            v43 = *v42;
            v40 = (struct SmsPage *)*((_QWORD *)v38 + 38);
            goto LABEL_87;
          }
        }
      }
LABEL_90:
      CmsVolume::UnpinInternal(v39, (struct CmsTransactionCore *)a2, v38, v9);
      v38 = v40;
      v9 = v41;
      if ( !v40 )
      {
        v5 = a3;
        v52[0] = 0;
        goto LABEL_92;
      }
    }
  }
  while ( 1 )
  {
    v11 = v52[0];
    if ( Array != -1073741400 )
      break;
    if ( !v52[0] )
      goto LABEL_19;
    v12 = a2[1];
    v13 = 3;
    do
    {
      v14 = 0;
      v15 = v13;
      if ( !*((_QWORD *)v11 + 38) )
        goto LABEL_17;
      v16 = (int *)((char *)v11 + 312);
      if ( (v13 & 1) != 0 && (v17 = *v16, *((_DWORD *)v11 + 96) == *v16) )
      {
        v18 = (int *)((char *)v11 + 316);
        v14 = (struct SmsPage *)*((_QWORD *)v11 + 38);
        if ( (v13 & 4) == 0 )
          goto LABEL_15;
        v19 = *v18;
        if ( *((_DWORD *)v11 + 97) != *v18 )
        {
          v15 = v13 & 0xFFFFFFFB;
          goto LABEL_15;
        }
      }
      else
      {
        if ( (v13 & 4) == 0 )
          goto LABEL_17;
        v18 = (int *)((char *)v11 + 316);
        v19 = *((_DWORD *)v11 + 79);
        if ( *((_DWORD *)v11 + 97) != v19 )
          goto LABEL_17;
        v17 = *v16;
        v14 = (struct SmsPage *)*((_QWORD *)v11 + 38);
      }
      *v18 = v19 - 1;
LABEL_15:
      *v16 = v17 - 1;
      if ( v17 == 1 )
        *((_QWORD *)v11 + 38) = 0;
LABEL_17:
      CmsVolume::UnpinInternal(v12, (struct CmsTransactionCore *)a2, v11, v13);
      v11 = v14;
      v13 = v15;
    }
    while ( v14 );
    v5 = a3;
    v6 = this;
    v52[0] = 0;
LABEL_19:
    v20 = a2[23];
    a2[23] = 0;
    v21 = *(_QWORD **)a4;
    if ( **(_QWORD **)a4 < 0x10u )
      RtlReleaseSRWLockExclusive(v21);
    else
      RtlReleaseSRWLockShared(v21);
    *(_QWORD *)a4 = 0;
    Array = CmsBlockRefcount::TriageCorruptChildRef(v6, (struct CmsTransactionContext *)a2, v20);
    MsTriageDeleteContext(v20);
    *(_QWORD *)a4 = *(_QWORD *)SmsAEPushLock::LockShared((char *)v6 + 96, v58);
    if ( Array < 0 )
      return (unsigned int)Array;
    v22 = *((_QWORD *)v6 + 1);
    v47 = 16;
    v48 = 0;
    v49 = &v50;
    v54 = 0;
    *(_OWORD *)v52 = 0;
    v53 = 0;
    Array = CmsTable::PinRow(v22, a2, &v47, 0, &v55, v52, 0);
    if ( Array >= 0 )
      goto LABEL_24;
  }
  if ( Array != -1073741772 )
  {
    if ( !v52[0] )
      return (unsigned int)Array;
    v30 = a2[1];
    while ( 1 )
    {
      v31 = 0;
      v32 = v9;
      if ( *((_QWORD *)v11 + 38) )
      {
        if ( (v9 & 1) != 0 && *((_DWORD *)v11 + 96) == *((_DWORD *)v11 + 78) )
        {
          v31 = (struct SmsPage *)*((_QWORD *)v11 + 38);
          if ( (v9 & 4) != 0 )
            goto LABEL_57;
          goto LABEL_60;
        }
        if ( (v9 & 4) != 0 && *((_DWORD *)v11 + 97) == *((_DWORD *)v11 + 79) )
        {
          v31 = (struct SmsPage *)*((_QWORD *)v11 + 38);
LABEL_57:
          v33 = *((_DWORD *)v11 + 79);
          if ( *((_DWORD *)v11 + 97) == v33 )
            *((_DWORD *)v11 + 79) = v33 - 1;
          else
            v32 = v9 & 0xFFFFFFFB;
LABEL_60:
          v29 = (*((_DWORD *)v11 + 78))-- == 1;
          if ( v29 )
            *((_QWORD *)v11 + 38) = 0;
        }
      }
      CmsVolume::UnpinInternal(v30, (struct CmsTransactionCore *)a2, v11, v9);
      v11 = v31;
      v9 = v32;
      if ( !v31 )
        return (unsigned int)Array;
    }
  }
  if ( !v52[0] )
    goto LABEL_44;
  v24 = a2[1];
  while ( 2 )
  {
    v25 = 0;
    v26 = v9;
    if ( *((_QWORD *)v11 + 38) )
    {
      if ( (v9 & 1) != 0 )
      {
        v27 = (_DWORD *)((char *)v11 + 312);
        if ( *((_DWORD *)v11 + 96) == *((_DWORD *)v11 + 78) )
        {
          v25 = (struct SmsPage *)*((_QWORD *)v11 + 38);
          if ( (v9 & 4) != 0 )
            goto LABEL_37;
          goto LABEL_40;
        }
      }
      if ( (v9 & 4) != 0 && *((_DWORD *)v11 + 97) == *((_DWORD *)v11 + 79) )
      {
        v27 = (_DWORD *)((char *)v11 + 312);
        v25 = (struct SmsPage *)*((_QWORD *)v11 + 38);
LABEL_37:
        v28 = *((_DWORD *)v11 + 79);
        if ( *((_DWORD *)v11 + 97) == v28 )
          *((_DWORD *)v11 + 79) = v28 - 1;
        else
          v26 = v9 & 0xFFFFFFFB;
LABEL_40:
        v29 = (*v27)-- == 1;
        if ( v29 )
          *((_QWORD *)v11 + 38) = 0;
      }
    }
    CmsVolume::UnpinInternal(v24, (struct CmsTransactionCore *)a2, v11, v9);
    v11 = v25;
    v9 = v26;
    if ( v25 )
      continue;
    break;
  }
  v52[0] = 0;
LABEL_44:
  if ( (*((_BYTE *)v5 + 50) & 1) == 0 )
    _InterlockedOr16((volatile signed __int16 *)v5 + 25, 1u);
  return 0;
}

```

## disassembly

```asm
0x1400d0b44  mov     rax, rsp
0x1400d0b47  mov     [rax+10h], rbx
0x1400d0b4b  mov     [rax+18h], r8
0x1400d0b4f  mov     [rax+8], rcx
0x1400d0b53  push    rbp
0x1400d0b54  push    rsi
0x1400d0b55  push    rdi
0x1400d0b56  push    r12
0x1400d0b58  push    r13
0x1400d0b5a  push    r14
0x1400d0b5c  push    r15
0x1400d0b5e  lea     rbp, [rax-5Fh]
0x1400d0b62  sub     rsp, 0C0h
0x1400d0b69  mov     rax, [r8+10h]
0x1400d0b6d  xorps   xmm0, xmm0
0x1400d0b70  mov     [rbp+57h+var_98], rax
0x1400d0b74  mov     r12, r9
0x1400d0b77  xor     eax, eax
0x1400d0b79  mov     [rbp+57h+var_50], 0
0x1400d0b80  mov     [rbp+57h+var_A4], ax
0x1400d0b84  mov     r15, r8
0x1400d0b87  lea     rax, [rbp+57h+var_98]
0x1400d0b8b  mov     [rbp+57h+var_48], 0
0x1400d0b93  mov     [rbp+57h+var_A0], rax
0x1400d0b97  lea     r8, [rbp+57h+var_A8]
0x1400d0b9b  xor     eax, eax
0x1400d0b9d  mov     [rbp+57h+var_90], 400h
0x1400d0ba5  mov     [rsp+30h], rax
0x1400d0baa  mov     r14, rcx
0x1400d0bad  mov     rcx, [rcx+8]
0x1400d0bb1  xor     r9d, r9d
0x1400d0bb4  mov     [rbp+57h+var_68], rax
0x1400d0bb8  mov     r13, rdx
0x1400d0bbb  lea     rax, [rbp+57h+var_88]
0x1400d0bbf  mov     [rbp+57h+var_A8], 10h
0x1400d0bc6  mov     [rsp+0F0h+var_C8], rax
0x1400d0bcb  lea     rax, [rbp+57h+var_60]
0x1400d0bcf  mov     [rsp+0F0h+var_D0], rax
0x1400d0bd4  movups  [rbp+57h+var_60], xmm0
0x1400d0bd8  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x1400d0bdc  movups  [rbp+57h+var_78], xmm0
0x1400d0be0  call    ?PinRow@CmsTable@@QEAAJPEAVCmsTransactionContext@@AEBU_CmsKey@@W4EmsPinRowFlags@@PEAU_CmsRow@@PEAUSmsLookupStack@@PEAU_SmsQuickIndex@@@Z; CmsTable::PinRow(CmsTransactionContext *,_CmsKey const &,EmsPinRowFlags,_CmsRow *,SmsLookupStack *,_SmsQuickIndex *)
0x1400d0be5  mov     ebx, 3
0x1400d0bea  mov     esi, eax
0x1400d0bec  lea     ecx, [rbx-2]
0x1400d0bef  test    eax, eax
0x1400d0bf1  jns     loc_1400D0D91
0x1400d0bf7  mov     r8, [rbp+57h+var_88]; struct SmsPage *
0x1400d0bfb  cmp     esi, 0C00001A8h
0x1400d0c01  jnz     loc_1400D0DAA
0x1400d0c07  test    r8, r8
0x1400d0c0a  jz      loc_1400D0CC0
0x1400d0c10  mov     r14, [r13+8]
0x1400d0c14  mov     r9d, ebx; unsigned int
0x1400d0c17  mov     r11, [r8+130h]
0x1400d0c1e  xor     esi, esi
0x1400d0c20  mov     edi, r9d
0x1400d0c23  test    r11, r11
0x1400d0c26  jz      short loc_1400D0C9A
0x1400d0c28  lea     rcx, [r8+138h]
0x1400d0c2f  test    r9b, 1
0x1400d0c33  jz      short loc_1400D0C62
0x1400d0c35  mov     r10d, [rcx]
0x1400d0c38  cmp     [r8+180h], r10d
0x1400d0c3f  jnz     short loc_1400D0C62
0x1400d0c41  lea     rdx, [r8+13Ch]
0x1400d0c48  mov     rsi, r11
0x1400d0c4b  bt      r9d, 2
0x1400d0c50  jnb     short loc_1400D0C85
0x1400d0c52  mov     eax, [rdx]
0x1400d0c54  cmp     [r8+184h], eax
0x1400d0c5b  jz      short loc_1400D0C81
0x1400d0c5d  and     edi, 0FFFFFFFBh
0x1400d0c60  jmp     short loc_1400D0C85
0x1400d0c62  bt      r9d, 2
0x1400d0c67  jnb     short loc_1400D0C9A
0x1400d0c69  lea     rdx, [r8+13Ch]
0x1400d0c70  mov     eax, [rdx]
0x1400d0c72  cmp     [r8+184h], eax
0x1400d0c79  jnz     short loc_1400D0C9A
0x1400d0c7b  mov     r10d, [rcx]
0x1400d0c7e  mov     rsi, r11
0x1400d0c81  dec     eax
0x1400d0c83  mov     [rdx], eax
0x1400d0c85  lea     eax, [r10-1]
0x1400d0c89  mov     [rcx], eax
0x1400d0c8b  test    eax, eax
0x1400d0c8d  jnz     short loc_1400D0C9A
0x1400d0c8f  mov     qword ptr [r8+130h], 0
0x1400d0c9a  mov     rdx, r13; struct CmsTransactionCore *
0x1400d0c9d  mov     rcx, r14; this
0x1400d0ca0  call    ?UnpinInternal@CmsVolume@@AEAAXPEAVCmsTransactionCore@@PEAUSmsPage@@K@Z; CmsVolume::UnpinInternal(CmsTransactionCore *,SmsPage *,ulong)
0x1400d0ca5  mov     r8, rsi
0x1400d0ca8  mov     r9d, edi
0x1400d0cab  test    rsi, rsi
0x1400d0cae  jnz     loc_1400D0C17
0x1400d0cb4  mov     r15, [rbp+57h+arg_10]
0x1400d0cb8  mov     r14, [rbp+57h+arg_0]
0x1400d0cbc  mov     [rbp+57h+var_88], rsi
0x1400d0cc0  mov     rdi, [r13+0B8h]
0x1400d0cc7  mov     qword ptr [r13+0B8h], 0
0x1400d0cd2  mov     rcx, [r12]
0x1400d0cd6  cmp     qword ptr [rcx], 10h
0x1400d0cda  jb      short loc_1400D0CEA
0x1400d0cdc  call    cs:__imp_RtlReleaseSRWLockShared
0x1400d0ce3  nop     dword ptr [rax+rax+00h]
0x1400d0ce8  jmp     short loc_1400D0CF6
0x1400d0cea  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1400d0cf1  nop     dword ptr [rax+rax+00h]
0x1400d0cf6  mov     r8, rdi; struct _SmsTriageContext *
0x1400d0cf9  mov     qword ptr [r12], 0
0x1400d0d01  mov     rdx, r13; struct CmsTransactionContext *
0x1400d0d04  mov     rcx, r14; this
0x1400d0d07  call    ?TriageCorruptChildRef@CmsBlockRefcount@@QEAAJPEAVCmsTransactionContext@@PEAU_SmsTriageContext@@@Z; CmsBlockRefcount::TriageCorruptChildRef(CmsTransactionContext *,_SmsTriageContext *)
0x1400d0d0c  mov     rcx, rdi
0x1400d0d0f  mov     esi, eax
0x1400d0d11  call    MsTriageDeleteContext
0x1400d0d16  lea     rcx, [r14+60h]
0x1400d0d1a  lea     rdx, [rbp+57h+var_40]
0x1400d0d1e  call    ?LockShared@SmsAEPushLock@@QEAA?AUContext@1@XZ; SmsAEPushLock::LockShared(void)
0x1400d0d23  mov     rcx, [rax]
0x1400d0d26  mov     [r12], rcx
0x1400d0d2a  test    esi, esi
0x1400d0d2c  js      loc_1400D109D
0x1400d0d32  mov     rcx, [r14+8]
0x1400d0d36  lea     r8, [rbp+57h+var_A8]
0x1400d0d3a  xor     eax, eax
0x1400d0d3c  mov     [rbp+57h+var_A8], 10h
0x1400d0d43  mov     [rbp+57h+var_A4], ax
0x1400d0d47  xorps   xmm0, xmm0
0x1400d0d4a  lea     rax, [rbp+57h+var_98]
0x1400d0d4e  xor     r9d, r9d
0x1400d0d51  mov     [rbp+57h+var_A0], rax
0x1400d0d55  mov     rdx, r13
0x1400d0d58  xor     eax, eax
0x1400d0d5a  mov     [rsp+30h], rax
0x1400d0d5f  mov     [rbp+57h+var_68], rax
0x1400d0d63  lea     rax, [rbp+57h+var_88]
0x1400d0d67  mov     [rsp+0F0h+var_C8], rax
0x1400d0d6c  lea     rax, [rbp+57h+var_60]
0x1400d0d70  mov     [rsp+0F0h+var_D0], rax
0x1400d0d75  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x1400d0d79  movups  [rbp+57h+var_78], xmm0
0x1400d0d7d  call    ?PinRow@CmsTable@@QEAAJPEAVCmsTransactionContext@@AEBU_CmsKey@@W4EmsPinRowFlags@@PEAU_CmsRow@@PEAUSmsLookupStack@@PEAU_SmsQuickIndex@@@Z; CmsTable::PinRow(CmsTransactionContext *,_CmsKey const &,EmsPinRowFlags,_CmsRow *,SmsLookupStack *,_SmsQuickIndex *)
0x1400d0d82  mov     esi, eax
0x1400d0d84  test    eax, eax
0x1400d0d86  js      loc_1400D0BF7
0x1400d0d8c  mov     ecx, 1
0x1400d0d91  mov     r12, [rbp+57h+var_48]
0x1400d0d95  cmp     [r12+10h], cl
0x1400d0d9a  jz      loc_1400D0F24
0x1400d0da0  mov     esi, 0C00000BBh
0x1400d0da5  jmp     loc_1400D109D
0x1400d0daa  cmp     esi, 0C0000034h
0x1400d0db0  jnz     loc_1400D0E7B
0x1400d0db6  test    r8, r8
0x1400d0db9  jz      loc_1400D0E61
0x1400d0dbf  mov     r14, [r13+8]
0x1400d0dc3  mov     rdx, [r8+130h]
0x1400d0dca  xor     esi, esi
0x1400d0dcc  mov     edi, ebx
0x1400d0dce  test    rdx, rdx
0x1400d0dd1  jz      short loc_1400D0E41
0x1400d0dd3  test    bl, 1
0x1400d0dd6  jz      short loc_1400D0DF4
0x1400d0dd8  lea     rcx, [r8+138h]
0x1400d0ddf  mov     eax, [rcx]
0x1400d0de1  cmp     [r8+180h], eax
0x1400d0de8  jnz     short loc_1400D0DF4
0x1400d0dea  mov     rsi, rdx
0x1400d0ded  test    bl, 4
0x1400d0df0  jz      short loc_1400D0E31
0x1400d0df2  jmp     short loc_1400D0E13
0x1400d0df4  test    bl, 4
0x1400d0df7  jz      short loc_1400D0E41
0x1400d0df9  mov     eax, [r8+13Ch]
0x1400d0e00  cmp     [r8+184h], eax
0x1400d0e07  jnz     short loc_1400D0E41
0x1400d0e09  lea     rcx, [r8+138h]
0x1400d0e10  mov     rsi, rdx
0x1400d0e13  mov     eax, [r8+13Ch]
0x1400d0e1a  cmp     [r8+184h], eax
0x1400d0e21  jnz     short loc_1400D0E2E
0x1400d0e23  dec     eax
0x1400d0e25  mov     [r8+13Ch], eax
0x1400d0e2c  jmp     short loc_1400D0E31
0x1400d0e2e  and     edi, 0FFFFFFFBh
0x1400d0e31  sub     dword ptr [rcx], 1
0x1400d0e34  jnz     short loc_1400D0E41
0x1400d0e36  mov     qword ptr [r8+130h], 0
0x1400d0e41  mov     r9d, ebx; unsigned int
0x1400d0e44  mov     rdx, r13; struct CmsTransactionCore *
0x1400d0e47  mov     rcx, r14; this
0x1400d0e4a  call    ?UnpinInternal@CmsVolume@@AEAAXPEAVCmsTransactionCore@@PEAUSmsPage@@K@Z; CmsVolume::UnpinInternal(CmsTransactionCore *,SmsPage *,ulong)
0x1400d0e4f  mov     r8, rsi
0x1400d0e52  mov     ebx, edi
0x1400d0e54  test    rsi, rsi
0x1400d0e57  jnz     loc_1400D0DC3
0x1400d0e5d  mov     [rbp+57h+var_88], rsi
0x1400d0e61  mov     eax, 1
0x1400d0e66  test    [r15+32h], al
0x1400d0e6a  jnz     short loc_1400D0E74
0x1400d0e6c  nop
0x1400d0e6d  lock or [r15+32h], ax
0x1400d0e73  nop
0x1400d0e74  xor     esi, esi
0x1400d0e76  jmp     loc_1400D109D
0x1400d0e7b  test    r8, r8
0x1400d0e7e  jz      loc_1400D109D
0x1400d0e84  mov     r15, [r13+8]
0x1400d0e88  mov     rcx, [r8+130h]
0x1400d0e8f  xor     r14d, r14d
0x1400d0e92  mov     edi, ebx
0x1400d0e94  test    rcx, rcx
0x1400d0e97  jz      short loc_1400D0F03
0x1400d0e99  test    bl, 1
0x1400d0e9c  jz      short loc_1400D0EB8
0x1400d0e9e  mov     eax, [r8+138h]
0x1400d0ea5  cmp     [r8+180h], eax
0x1400d0eac  jnz     short loc_1400D0EB8
0x1400d0eae  mov     r14, rcx
0x1400d0eb1  test    bl, 4
0x1400d0eb4  jz      short loc_1400D0EEE
0x1400d0eb6  jmp     short loc_1400D0ED0
0x1400d0eb8  test    bl, 4
0x1400d0ebb  jz      short loc_1400D0F03
0x1400d0ebd  mov     eax, [r8+13Ch]
0x1400d0ec4  cmp     [r8+184h], eax
0x1400d0ecb  jnz     short loc_1400D0F03
0x1400d0ecd  mov     r14, rcx
0x1400d0ed0  mov     eax, [r8+13Ch]
0x1400d0ed7  cmp     [r8+184h], eax
0x1400d0ede  jnz     short loc_1400D0EEB
0x1400d0ee0  dec     eax
0x1400d0ee2  mov     [r8+13Ch], eax
0x1400d0ee9  jmp     short loc_1400D0EEE
0x1400d0eeb  and     edi, 0FFFFFFFBh
0x1400d0eee  sub     dword ptr [r8+138h], 1
0x1400d0ef6  jnz     short loc_1400D0F03
0x1400d0ef8  mov     qword ptr [r8+130h], 0
0x1400d0f03  mov     r9d, ebx; unsigned int
0x1400d0f06  mov     rdx, r13; struct CmsTransactionCore *
0x1400d0f09  mov     rcx, r15; this
0x1400d0f0c  call    ?UnpinInternal@CmsVolume@@AEAAXPEAVCmsTransactionCore@@PEAUSmsPage@@K@Z; CmsVolume::UnpinInternal(CmsTransactionCore *,SmsPage *,ulong)
0x1400d0f11  mov     r8, r14
0x1400d0f14  mov     ebx, edi
0x1400d0f16  test    r14, r14
0x1400d0f19  jnz     loc_1400D0E88
0x1400d0f1f  jmp     loc_1400D109D
0x1400d0f24  mov     rax, [rbp+57h+var_98]
0x1400d0f28  xor     edi, edi
0x1400d0f2a  cmp     [r12], rax
0x1400d0f2e  jbe     short loc_1400D0F37
0x1400d0f30  mov     rdi, [r12]
0x1400d0f34  sub     rdi, rax
0x1400d0f37  mov     r14, [rbp+57h+var_90]
0x1400d0f3b  sub     r14, rdi
0x1400d0f3e  cmp     [r12+8], r14
0x1400d0f43  cmovb   r14, [r12+8]
0x1400d0f49  test    [r12+14h], cl
0x1400d0f4e  mov     rcx, r15; this
0x1400d0f51  jz      short loc_1400D0F90
0x1400d0f53  mov     eax, [r12+18h]
0x1400d0f58  mov     dword ptr [rbp+57h+arg_0], eax
0x1400d0f5b  call    ?AllocateArray@CmsRefcountCacheEntry@@QEAAJXZ; CmsRefcountCacheEntry::AllocateArray(void)
0x1400d0f60  mov     esi, eax
0x1400d0f62  test    eax, eax
0x1400d0f64  js      short loc_1400D0FD1
0x1400d0f66  lea     rcx, [rdi+rdi]
0x1400d0f6a  lea     rdx, [r12+1Ch]
0x1400d0f6f  lea     rdx, [rdx+rcx*2]
0x1400d0f73  add     rcx, [r15+48h]
0x1400d0f77  lea     r8, [r14+r14]
0x1400d0f7b  call    cs:__imp_RtlCopyMemoryNonTemporal
0x1400d0f82  nop     dword ptr [rax+rax+00h]
0x1400d0f87  mov     eax, dword ptr [rbp+57h+arg_0]
0x1400d0f8a  add     [r15+40h], eax
0x1400d0f8e  jmp     short loc_1400D0FD1
0x1400d0f90  movzx   r12d, word ptr [r12+1Ch]
0x1400d0f96  call    ?AllocateArray@CmsRefcountCacheEntry@@QEAAJXZ; CmsRefcountCacheEntry::AllocateArray(void)
0x1400d0f9b  mov     esi, eax
0x1400d0f9d  test    eax, eax
0x1400d0f9f  js      short loc_1400D0FD1
0x1400d0fa1  lea     rdx, [r14+rdi]
0x1400d0fa5  jmp     short loc_1400D0FC4
0x1400d0fa7  mov     rcx, [r15+48h]
0x1400d0fab  mov     r8d, 0FFFFE000h
0x1400d0fb1  movzx   eax, word ptr [rcx+rdi*2]
0x1400d0fb5  and     ax, r8w
0x1400d0fb9  or      ax, r12w
0x1400d0fbd  mov     [rcx+rdi*2], ax
0x1400d0fc1  inc     rdi
0x1400d0fc4  cmp     rdi, rdx
0x1400d0fc7  jb      short loc_1400D0FA7
0x1400d0fc9  imul    r14d, r12d
0x1400d0fcd  mov     [r15+40h], r14d
0x1400d0fd1  mov     r8, [rbp+57h+var_88]; struct SmsPage *
0x1400d0fd5  test    r8, r8
0x1400d0fd8  jz      loc_1400D1086
0x1400d0fde  mov     r12, [r13+8]
  ... truncated ...
```
