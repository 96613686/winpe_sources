# _tlgWriteAgg

- ea: `0x18000b0d0`
- end: `0x18000b650`
- name: `_tlgWriteAgg`
- size: `1408`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180001c14`

## callees

- `0x18000b0d0`
- `0x18000b658`
- `0x18000b6b0`
- `0x18000bf3c`
- `0x1800139d8`
- `0x180019d3b`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b40d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b40d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b36d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b36d`

## pseudocode

```c
ULONG __fastcall tlgWriteAgg(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        unsigned __int8 a4,
        PEVENT_DATA_DESCRIPTOR a5)
{
  __int64 v7; // r15
  ULONGLONG v9; // rax
  unsigned __int16 *v10; // rdx
  ULONGLONG Ptr; // rax
  unsigned __int8 v12; // si
  ULONGLONG v13; // r9
  char *v14; // rcx
  char v15; // al
  char *v18; // rax
  char v19; // dl
  UCHAR v20; // r8
  __int64 v21; // rax
  __int64 v22; // r14
  unsigned int v23; // r13d
  unsigned int v24; // edx
  unsigned int v25; // eax
  unsigned int v26; // et2
  unsigned int v27; // eax
  unsigned __int8 i; // bl
  unsigned __int64 j; // r8
  int v30; // ecx
  RTL_SRWLOCK *v31; // rdi
  unsigned int v32; // ebp
  volatile signed __int64 *v33; // rbx
  volatile signed __int64 v34; // rsi
  int v35; // ecx
  __int64 v36; // r14
  int v37; // eax
  unsigned int k; // ebx
  __int64 v39; // rdx
  int v40; // ebx
  unsigned __int8 m; // dl
  signed __int64 v43; // r10
  __int64 v44; // rax
  int v45; // r8d
  volatile signed __int64 *v46; // r9
  signed __int64 v47; // rax
  unsigned int v48; // eax
  volatile signed __int64 v49; // rtt
  signed __int64 v50; // [rsp+30h] [rbp-68h]
  signed __int64 v51; // [rsp+38h] [rbp-60h] BYREF
  __int64 v52; // [rsp+40h] [rbp-58h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-50h] BYREF
  unsigned __int8 v54; // [rsp+A0h] [rbp+8h]
  int NewEventEntry; // [rsp+A8h] [rbp+10h]
  unsigned __int8 v56; // [rsp+C0h] [rbp+28h]

  v7 = 2;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v9 = *(_QWORD *)(a2 + 3);
  v10 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v9;
  a5->Ptr = *(_QWORD *)(a1 + 8);
  a5->Size = **(unsigned __int16 **)(a1 + 8);
  a5->Reserved = 2;
  a5[1].Ptr = (ULONGLONG)v10;
  a5[1].Size = *v10;
  a5[1].Reserved = 1;
  if ( *(void (__fastcall **)(const struct _GUID *, __int64, char, __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, _QWORD *))(a1 + 40) != TlgAggregateInternalRegisteredProviderEtwCallback )
    return -1073741811;
  Ptr = a5[1].Ptr;
  v12 = 0;
  v13 = Ptr + a5[1].Size;
  v14 = (char *)(Ptr + 2);
  do
    v15 = *v14++;
  while ( v15 < 0 );
  while ( *v14++ )
    ;
  while ( (unsigned __int64)v14 < v13 )
  {
    while ( *v14++ )
      ;
    if ( *v14 >= 0 )
      break;
    v18 = v14 + 1;
    v19 = *v14 & 0x7F;
    v14 += 2;
    if ( *v18 >= 0 )
      break;
    while ( 1 )
    {
      v20 = *v14;
      if ( *v14 >= 0 )
        break;
      if ( v20 != 0x80 )
        goto LABEL_15;
      ++v14;
    }
    if ( v19 != 9 || (unsigned __int8)(v20 - 113) > 2u )
      break;
    v21 = v12++;
    a5[v21 + 2].Reserved1 = v20;
  }
LABEL_15:
  v56 = v12;
  if ( !v12 )
    return EventWriteTransfer_0(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, a4, a5);
  v22 = *(_QWORD *)(a1 + 48);
  v52 = v22;
  v50 = 0;
  v51 = 0;
  NewEventEntry = 0;
  _mm_lfence();
  v23 = a4;
  v24 = BYTE1(a5[1].Ptr) + ((1025 * LOBYTE(a5[1].Ptr)) ^ ((1025 * (unsigned int)LOBYTE(a5[1].Ptr)) >> 6));
  v25 = 1025
      * (BYTE5(a5[1].Ptr)
       + ((1025
         * (BYTE4(a5[1].Ptr)
          + ((1025
            * (BYTE3(a5[1].Ptr)
             + ((1025 * (BYTE2(a5[1].Ptr) + ((1025 * v24) ^ ((1025 * v24) >> 6))))
              ^ ((1025 * (BYTE2(a5[1].Ptr) + ((1025 * v24) ^ ((1025 * v24) >> 6)))) >> 6))))
           ^ ((1025
             * (BYTE3(a5[1].Ptr)
              + ((1025 * (BYTE2(a5[1].Ptr) + ((1025 * v24) ^ ((1025 * v24) >> 6))))
               ^ ((1025 * (BYTE2(a5[1].Ptr) + ((1025 * v24) ^ ((1025 * v24) >> 6)))) >> 6)))) >> 6))))
        ^ ((1025
          * (BYTE4(a5[1].Ptr)
           + ((1025
             * (BYTE3(a5[1].Ptr)
              + ((1025 * (BYTE2(a5[1].Ptr) + ((1025 * v24) ^ ((1025 * v24) >> 6))))
               ^ ((1025 * (BYTE2(a5[1].Ptr) + ((1025 * v24) ^ ((1025 * v24) >> 6)))) >> 6))))
            ^ ((1025
              * (BYTE3(a5[1].Ptr)
               + ((1025 * (BYTE2(a5[1].Ptr) + ((1025 * v24) ^ ((1025 * v24) >> 6))))
                ^ ((1025 * (BYTE2(a5[1].Ptr) + ((1025 * v24) ^ ((1025 * v24) >> 6)))) >> 6)))) >> 6)))) >> 6)));
  v26 = 1025 * (BYTE6(a5[1].Ptr) + (v25 ^ (v25 >> 6)));
  v27 = (1025 * (HIBYTE(a5[1].Ptr) + (v26 ^ (v26 >> 6)))) ^ ((1025 * (HIBYTE(a5[1].Ptr) + (v26 ^ (v26 >> 6)))) >> 6);
  v54 = v12 + 2;
  for ( i = v12 + 2; i < a4; ++i )
  {
    for ( j = 0; j < a5[i].Size; v27 = (1025 * (v27 + v30)) ^ ((1025 * (v27 + v30)) >> 6) )
      v30 = *(unsigned __int8 *)(a5[i].Ptr + j++);
  }
  v31 = (RTL_SRWLOCK *)(v22 + 264);
  v32 = 32769 * ((9 * v27) ^ ((9 * v27) >> 11));
  AcquireSRWLockShared((PSRWLOCK)(v22 + 264));
  v33 = (volatile signed __int64 *)(v22 + 8LL * (v32 & 0x1F));
  while ( 1 )
  {
    if ( !*v33 )
    {
      if ( *(_DWORD *)(v22 + 256) >= 0x400u )
      {
        ++*(_DWORD *)(v22 + 300);
        v40 = 234;
        goto LABEL_31;
      }
      if ( !v50 )
      {
        NewEventEntry = CreateNewEventEntry(
                          (unsigned int)&EventDescriptor,
                          (unsigned __int8)v23,
                          (_DWORD)a5,
                          v12,
                          v32,
                          (__int64)&v51);
        v50 = v51;
        if ( !v51 )
        {
          v40 = NewEventEntry;
          if ( NewEventEntry == 8 )
            ++*(_DWORD *)(v22 + 304);
          else
            ++*(_DWORD *)(v22 + 308);
          goto LABEL_31;
        }
      }
      if ( !_InterlockedCompareExchange64(v33, v50, 0) )
      {
        v50 = 0;
        if ( _InterlockedIncrement((volatile signed __int32 *)(v22 + 256)) == 1 )
          EnableFlushTimer(*(struct _TP_TIMER **)(v22 + 344), *(_DWORD *)(v22 + 352));
        v48 = *(_DWORD *)(v22 + 256);
        v40 = NewEventEntry;
        if ( *(_DWORD *)(v22 + 288) < v48 )
          *(_DWORD *)(v22 + 288) = v48;
        goto LABEL_31;
      }
    }
    v34 = *v33;
    v35 = *(_DWORD *)(*v33 + 40);
    if ( v32 == v35 )
    {
      v36 = *(_QWORD *)(v34 + 16);
      v37 = memcmp_0(&a5[1], (const void *)(v36 + 16), 8u);
      if ( !v37 )
      {
        for ( k = *(unsigned __int8 *)(v34 + 45) + 2; k < v23; ++k )
        {
          v39 = v36 + 16LL * k;
          v37 = a5[k].Size - *(_DWORD *)(v39 + 8);
          if ( v37 )
            goto LABEL_34;
          v37 = memcmp_0((const void *)a5[k].Ptr, *(const void **)v39, a5[k].Size);
          if ( v37 )
            goto LABEL_34;
        }
        v37 = 0;
LABEL_34:
        v7 = 2;
      }
      v22 = v52;
    }
    else
    {
      v37 = v32 - v35;
    }
    if ( !v37 )
      break;
    v33 = (volatile signed __int64 *)(v34 + (((__int64)v37 >> 63) & 0xFFFFFFFFFFFFFFF8uLL) + 32);
    v12 = v56;
  }
  if ( v34 )
  {
    for ( m = 2; m < v54; ++v7 )
    {
      v43 = *(_QWORD *)a5[v7].Ptr;
      v44 = *(_QWORD *)(v34 + 16);
      v45 = *(unsigned __int8 *)(v44 + 16 * v7 + 13);
      v46 = *(volatile signed __int64 **)(v44 + 16 * v7);
      if ( (_BYTE)v45 == 115 )
        goto LABEL_40;
      if ( v45 == 113 )
      {
        _InterlockedAdd64(v46, v43);
      }
      else if ( v45 == 114 )
      {
        do
        {
LABEL_40:
          v47 = *v46;
          if ( (_BYTE)v45 == 114 )
          {
            if ( v43 >= v47 )
              break;
          }
          else if ( v43 <= v47 )
          {
            break;
          }
          v49 = *v46;
        }
        while ( v49 != _InterlockedCompareExchange64(v46, v43, v47) );
      }
      ++m;
    }
  }
  v40 = NewEventEntry;
LABEL_31:
  ReleaseSRWLockShared(v31);
  if ( v50 )
    DestroyEventEntry(v50);
  return v40;
}

```

## disassembly

```asm
0x18000b0d0  push    r12
0x18000b0d2  push    r15
0x18000b0d4  sub     rsp, 88h
0x18000b0db  movzx   eax, byte ptr [rdx]
0x18000b0de  mov     r10, rcx
0x18000b0e1  mov     r12, [rsp+98h+arg_20]
0x18000b0e9  mov     r15d, 2
0x18000b0ef  shl     eax, 18h
0x18000b0f2  mov     r11d, r9d
0x18000b0f5  mov     dword ptr [rsp+98h+EventDescriptor.Id], eax
0x18000b0f9  movzx   eax, word ptr [rdx+1]
0x18000b0fd  mov     dword ptr [rsp+98h+EventDescriptor.Level], eax
0x18000b101  mov     rax, [rdx+3]
0x18000b105  add     rdx, 0Bh
0x18000b109  mov     [rsp+98h+EventDescriptor.Keyword], rax
0x18000b10e  mov     rax, [rcx+8]
0x18000b112  mov     [r12], rax
0x18000b116  mov     rax, [rcx+8]
0x18000b11a  movzx   ecx, word ptr [rax]
0x18000b11d  mov     [r12+8], ecx
0x18000b122  lea     rcx, _TraceLoggingMetadata
0x18000b129  mov     [r12+0Ch], r15d
0x18000b12e  mov     [r12+10h], rdx
0x18000b133  movzx   eax, word ptr [rdx]
0x18000b136  mov     [r12+18h], eax
0x18000b13b  lea     rax, _TraceLoggingMetadataEnd
0x18000b142  sub     eax, ecx
0x18000b144  mov     dword ptr [r12+1Ch], 1
0x18000b14d  mov     dword ptr [rsp+98h+arg_20], eax
0x18000b154  mov     eax, dword ptr [rsp+98h+arg_20]
0x18000b15b  lea     rax, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x18000b162  cmp     [r10+28h], rax
0x18000b166  jnz     loc_18000B646
0x18000b16c  mov     rax, [r12+10h]
0x18000b171  mov     r9d, [r12+18h]
0x18000b176  mov     [rsp+98h+var_20], rsi
0x18000b17b  xor     sil, sil
0x18000b17e  add     r9, rax
0x18000b181  lea     rcx, [rax+2]
0x18000b185  movzx   eax, byte ptr [rcx]
0x18000b188  inc     rcx
0x18000b18b  test    al, al
0x18000b18d  js      short loc_18000B185
0x18000b18f  nop
0x18000b190  movzx   eax, byte ptr [rcx]
0x18000b193  inc     rcx
0x18000b196  test    al, al
0x18000b198  jnz     short loc_18000B190
0x18000b19a  nop     word ptr [rax+rax+00h]
0x18000b1a0  cmp     rcx, r9
0x18000b1a3  jnb     short loc_18000B1F8
0x18000b1a5  movzx   eax, byte ptr [rcx]
0x18000b1a8  inc     rcx
0x18000b1ab  test    al, al
0x18000b1ad  jnz     short loc_18000B1A5
0x18000b1af  movzx   edx, byte ptr [rcx]
0x18000b1b2  test    dl, dl
0x18000b1b4  jns     short loc_18000B1F8
0x18000b1b6  lea     rax, [rcx+1]
0x18000b1ba  and     dl, 7Fh
0x18000b1bd  add     rcx, r15
0x18000b1c0  cmp     byte ptr [rax], 0
0x18000b1c3  jge     short loc_18000B1F8
0x18000b1c5  movzx   r8d, byte ptr [rcx]
0x18000b1c9  test    r8b, r8b
0x18000b1cc  jns     short loc_18000B1D9
0x18000b1ce  cmp     r8b, 80h
0x18000b1d2  jnz     short loc_18000B1F8
0x18000b1d4  inc     rcx
0x18000b1d7  jmp     short loc_18000B1C5
0x18000b1d9  cmp     dl, 9
0x18000b1dc  jnz     short loc_18000B1F8
0x18000b1de  lea     eax, [r8-71h]
0x18000b1e2  cmp     al, r15b
0x18000b1e5  ja      short loc_18000B1F8
0x18000b1e7  movzx   eax, sil
0x18000b1eb  add     rax, rax
0x18000b1ee  inc     sil
0x18000b1f1  mov     [r12+rax*8+2Dh], r8b
0x18000b1f6  jmp     short loc_18000B1A0
0x18000b1f8  mov     byte ptr [rsp+98h+arg_20], sil
0x18000b200  test    sil, sil
0x18000b203  jz      loc_18000B4F0
0x18000b209  mov     [rsp+98h+arg_10], rbx
0x18000b211  xor     eax, eax
0x18000b213  mov     [rsp+98h+var_18], rbp
0x18000b21b  mov     [rsp+98h+var_28], rdi
0x18000b220  mov     [rsp+98h+var_30], r13
0x18000b225  mov     [rsp+98h+var_38], r14
0x18000b22a  mov     r14, [r10+30h]
0x18000b22e  mov     [rsp+98h+var_58], r14
0x18000b233  mov     [rsp+98h+var_68], rax
0x18000b238  mov     [rsp+98h+var_60], rax
0x18000b23d  mov     [rsp+98h+arg_8], eax
0x18000b244  lfence
0x18000b247  movzx   eax, byte ptr [r12+10h]
0x18000b24d  imul    ecx, eax, 401h
0x18000b253  movzx   eax, byte ptr [r12+11h]
0x18000b259  movzx   r13d, r11b
0x18000b25d  mov     edx, ecx
0x18000b25f  shr     edx, 6
0x18000b262  xor     edx, ecx
0x18000b264  add     edx, eax
0x18000b266  imul    eax, edx, 401h
0x18000b26c  mov     ecx, eax
0x18000b26e  shr     ecx, 6
0x18000b271  xor     ecx, eax
0x18000b273  movzx   eax, byte ptr [r12+12h]
0x18000b279  add     ecx, eax
0x18000b27b  imul    eax, ecx, 401h
0x18000b281  mov     ecx, eax
0x18000b283  shr     ecx, 6
0x18000b286  xor     ecx, eax
0x18000b288  movzx   eax, byte ptr [r12+13h]
0x18000b28e  add     ecx, eax
0x18000b290  imul    eax, ecx, 401h
0x18000b296  mov     ecx, eax
0x18000b298  shr     ecx, 6
0x18000b29b  xor     ecx, eax
0x18000b29d  movzx   eax, byte ptr [r12+14h]
0x18000b2a3  add     ecx, eax
0x18000b2a5  imul    eax, ecx, 401h
0x18000b2ab  mov     ecx, eax
0x18000b2ad  shr     ecx, 6
0x18000b2b0  xor     ecx, eax
0x18000b2b2  movzx   eax, byte ptr [r12+15h]
0x18000b2b8  add     ecx, eax
0x18000b2ba  imul    eax, ecx, 401h
0x18000b2c0  mov     ecx, eax
0x18000b2c2  shr     ecx, 6
0x18000b2c5  xor     ecx, eax
0x18000b2c7  movzx   eax, byte ptr [r12+16h]
0x18000b2cd  add     ecx, eax
0x18000b2cf  imul    eax, ecx, 401h
0x18000b2d5  mov     ecx, eax
0x18000b2d7  shr     ecx, 6
0x18000b2da  xor     ecx, eax
0x18000b2dc  movzx   eax, byte ptr [r12+17h]
0x18000b2e2  add     ecx, eax
0x18000b2e4  imul    ecx, 401h
0x18000b2ea  mov     eax, ecx
0x18000b2ec  shr     eax, 6
0x18000b2ef  xor     eax, ecx
0x18000b2f1  lea     ecx, [rsi+2]
0x18000b2f4  mov     [rsp+98h+arg_0], cl
0x18000b2fb  movzx   ebx, cl
0x18000b2fe  cmp     cl, r13b
0x18000b301  jnb     short loc_18000B353
0x18000b303  nop     dword ptr [rax+00h]
0x18000b307  nop     word ptr [rax+rax+00000000h]
0x18000b310  movzx   ecx, bl
0x18000b313  xor     r8d, r8d
0x18000b316  add     rcx, rcx
0x18000b319  mov     r9d, [r12+rcx*8+8]
0x18000b31e  mov     r10, [r12+rcx*8]
0x18000b322  test    r9, r9
0x18000b325  jz      short loc_18000B34C
0x18000b327  nop     word ptr [rax+rax+00000000h]
0x18000b330  movzx   ecx, byte ptr [r10+r8]
0x18000b335  inc     r8
0x18000b338  add     ecx, eax
0x18000b33a  imul    edx, ecx, 401h
0x18000b340  mov     eax, edx
0x18000b342  shr     eax, 6
0x18000b345  xor     eax, edx
0x18000b347  cmp     r8, r9
0x18000b34a  jb      short loc_18000B330
0x18000b34c  inc     bl
0x18000b34e  cmp     bl, r13b
0x18000b351  jb      short loc_18000B310
0x18000b353  lea     ecx, [rax+rax*8]
0x18000b356  mov     eax, ecx
0x18000b358  lea     rdi, [r14+108h]
0x18000b35f  shr     eax, 0Bh
0x18000b362  xor     eax, ecx
0x18000b364  mov     rcx, rdi; SRWLock
0x18000b367  imul    ebp, eax, 8001h
0x18000b36d  call    cs:__imp_AcquireSRWLockShared
0x18000b373  mov     eax, ebp
0x18000b375  and     eax, 1Fh
0x18000b378  lea     rbx, [r14+rax*8]
0x18000b37c  cmp     qword ptr [rbx], 0
0x18000b380  jz      short loc_18000B3ED
0x18000b382  mov     rsi, [rbx]
0x18000b385  mov     ecx, [rsi+28h]
0x18000b388  cmp     ebp, ecx
0x18000b38a  jnz     loc_18000B522
0x18000b390  mov     r14, [rsi+10h]
0x18000b394  lea     rcx, [r12+10h]; Buf1
0x18000b399  mov     r8d, 8; Size
0x18000b39f  lea     rdx, [r14+10h]; Buf2
0x18000b3a3  call    memcmp_0
0x18000b3a8  test    eax, eax
0x18000b3aa  jnz     loc_18000B459
0x18000b3b0  movzx   ebx, byte ptr [rsi+2Dh]
0x18000b3b4  add     ebx, 2
0x18000b3b7  cmp     ebx, r13d
0x18000b3ba  jnb     loc_18000B5D6
0x18000b3c0  mov     eax, ebx
0x18000b3c2  add     rax, rax
0x18000b3c5  mov     r8d, [r12+rax*8+8]; Size
0x18000b3ca  lea     rcx, [r12+rax*8]
0x18000b3ce  lea     rdx, [r14+rax*8]
0x18000b3d2  mov     eax, r8d
0x18000b3d5  sub     eax, [rdx+8]
0x18000b3d8  jnz     short loc_18000B453
0x18000b3da  mov     rdx, [rdx]; Buf2
0x18000b3dd  mov     rcx, [rcx]; Buf1
0x18000b3e0  call    memcmp_0
0x18000b3e5  test    eax, eax
0x18000b3e7  jnz     short loc_18000B453
0x18000b3e9  inc     ebx
0x18000b3eb  jmp     short loc_18000B3B7
0x18000b3ed  cmp     dword ptr [r14+100h], 400h
0x18000b3f8  jb      loc_18000B52B
0x18000b3fe  inc     dword ptr [r14+12Ch]
0x18000b405  mov     ebx, 0EAh
0x18000b40a  mov     rcx, rdi; SRWLock
0x18000b40d  call    cs:__imp_ReleaseSRWLockShared
0x18000b413  mov     rax, [rsp+98h+var_68]
0x18000b418  mov     r14, [rsp+98h+var_38]
0x18000b41d  mov     r13, [rsp+98h+var_30]
0x18000b422  mov     rdi, [rsp+98h+var_28]
0x18000b427  mov     rbp, [rsp+98h+var_18]
0x18000b42f  test    rax, rax
0x18000b432  jnz     loc_18000B639
0x18000b438  mov     rsi, [rsp+98h+var_20]
0x18000b43d  mov     eax, ebx
0x18000b43f  mov     rbx, [rsp+98h+arg_10]
0x18000b447  add     rsp, 88h
0x18000b44e  pop     r15
0x18000b450  pop     r12
0x18000b452  retn
0x18000b453  mov     r15d, 2
0x18000b459  mov     r14, [rsp+98h+var_58]
0x18000b45e  test    eax, eax
0x18000b460  jnz     short loc_18000B4D1
0x18000b462  test    rsi, rsi
0x18000b465  jz      short loc_18000B4C5
0x18000b467  movzx   r11d, [rsp+98h+arg_0]
0x18000b470  mov     dl, 2
0x18000b472  cmp     r11b, dl
0x18000b475  jbe     short loc_18000B4C5
0x18000b477  nop     word ptr [rax+rax+00000000h]
0x18000b480  mov     rcx, r15
0x18000b483  add     rcx, rcx
0x18000b486  mov     rax, [r12+rcx*8]
0x18000b48a  mov     r10, [rax]
0x18000b48d  mov     rax, [rsi+10h]
0x18000b491  movzx   r8d, byte ptr [rax+rcx*8+0Dh]
0x18000b497  mov     r9, [rax+rcx*8]
0x18000b49b  cmp     r8b, 73h ; 's'
0x18000b49f  jnz     loc_18000B601
0x18000b4a5  mov     rax, [r9]
0x18000b4a8  cmp     r8b, 72h ; 'r'
0x18000b4ac  jnz     loc_18000B620
0x18000b4b2  cmp     r10, rax
0x18000b4b5  jl      loc_18000B629
0x18000b4bb  inc     dl
0x18000b4bd  inc     r15
0x18000b4c0  cmp     dl, r11b
0x18000b4c3  jb      short loc_18000B480
0x18000b4c5  mov     ebx, [rsp+98h+arg_8]
0x18000b4cc  jmp     loc_18000B40A
0x18000b4d1  movsxd  rbx, eax
0x18000b4d4  sar     rbx, 3Fh
0x18000b4d8  and     rbx, 0FFFFFFFFFFFFFFF8h
0x18000b4dc  add     rbx, 20h ; ' '
0x18000b4e0  add     rbx, rsi
0x18000b4e3  movzx   esi, byte ptr [rsp+98h+arg_20]
0x18000b4eb  jmp     loc_18000B37C
0x18000b4f0  mov     rcx, [r10+20h]; RegHandle
0x18000b4f4  lea     rdx, [rsp+98h+EventDescriptor]; EventDescriptor
0x18000b4f9  movzx   eax, r11b
0x18000b4fd  xor     r9d, r9d; RelatedActivityId
0x18000b500  mov     [rsp+98h+UserData], r12; UserData
0x18000b505  xor     r8d, r8d; ActivityId
0x18000b508  mov     [rsp+98h+UserDataCount], eax; UserDataCount
0x18000b50c  call    EventWriteTransfer_0
0x18000b511  mov     rsi, [rsp+98h+var_20]
0x18000b516  add     rsp, 88h
0x18000b51d  pop     r15
0x18000b51f  pop     r12
0x18000b521  retn
0x18000b522  mov     eax, ebp
0x18000b524  sub     eax, ecx
0x18000b526  jmp     loc_18000B45E
0x18000b52b  cmp     [rsp+98h+var_68], 0
0x18000b531  jnz     short loc_18000B56C
0x18000b533  lea     rax, [rsp+98h+var_60]
0x18000b538  movzx   r9d, sil
0x18000b53c  mov     [rsp+98h+UserData], rax
0x18000b541  lea     rcx, [rsp+98h+EventDescriptor]
0x18000b546  mov     r8, r12
0x18000b549  mov     [rsp+98h+UserDataCount], ebp
0x18000b54d  movzx   edx, r13b
0x18000b551  call    CreateNewEventEntry
0x18000b556  mov     [rsp+98h+arg_8], eax
0x18000b55d  mov     rax, [rsp+98h+var_60]
0x18000b562  mov     [rsp+98h+var_68], rax
  ... truncated ...
```
