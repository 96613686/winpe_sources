# _tlgWriteAgg

- ea: `0x180024df0`
- end: `0x18002520b`
- name: `_tlgWriteAgg`
- size: `1051`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `7`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180002190`
- `0x180004bf4`
- `0x180024cac`
- `0x180024d38`
- `0x18003cfb0`
- `0x180050bb0`
- `0x1800a8a9c`

## callees

- `0x180024df0`
- `0x180025214`
- `0x18002526c`
- `0x18003c43c`
- `0x180085ba0`
- `0x1800b1e54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002507f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002507f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180024fb7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180024fb7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800251e5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800251e5`

## pseudocode

```c
__int64 __fastcall tlgWriteAgg(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        unsigned __int8 a4,
        PEVENT_DATA_DESCRIPTOR a5)
{
  unsigned __int8 v7; // r12
  unsigned int v9; // r15d
  ULONGLONG v10; // rax
  unsigned __int16 *v11; // rdx
  ULONG v12; // ecx
  ULONGLONG Ptr; // rax
  unsigned __int8 v14; // bp
  ULONGLONG v15; // r9
  char *v16; // rcx
  char v17; // al
  char v20; // r8
  char *v21; // rax
  UCHAR v22; // dl
  __int64 v23; // rbx
  signed __int64 v24; // rsi
  unsigned int v25; // edx
  unsigned __int64 i; // r8
  int v27; // eax
  unsigned __int8 v28; // r8
  unsigned __int64 k; // r9
  int v30; // eax
  unsigned int v31; // r13d
  int v32; // edx
  int v33; // r9d
  volatile signed __int64 *v34; // rdi
  volatile signed __int64 v35; // rbp
  __int64 v36; // r13
  int v37; // eax
  unsigned int v38; // eax
  unsigned int m; // edi
  __int64 v40; // rax
  __int64 v42; // r10
  __int64 v43; // r10
  unsigned __int8 v44; // r11
  unsigned int v45; // eax
  unsigned int NewEventEntry; // eax
  unsigned int v47; // [rsp+34h] [rbp-64h]
  signed __int64 v48; // [rsp+38h] [rbp-60h] BYREF
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-58h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-50h] BYREF
  unsigned __int8 v51; // [rsp+A0h] [rbp+8h]
  unsigned __int8 j; // [rsp+A8h] [rbp+10h]
  unsigned __int8 v53; // [rsp+C0h] [rbp+28h]

  v7 = 2;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  v9 = -1073741811;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v10 = *(_QWORD *)(a2 + 3);
  v11 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v10;
  a5->Ptr = *(_QWORD *)(a1 + 8);
  v12 = **(unsigned __int16 **)(a1 + 8);
  a5[1].Ptr = (ULONGLONG)v11;
  a5->Size = v12;
  a5->Reserved = 2;
  a5[1].Size = *v11;
  a5[1].Reserved = 1;
  if ( *(void (__fastcall **)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))(a1 + 40) == TlgAggregateInternalRegisteredProviderEtwCallback )
  {
    Ptr = a5[1].Ptr;
    v14 = 0;
    v15 = Ptr + a5[1].Size;
    v16 = (char *)(Ptr + 2);
    do
      v17 = *v16++;
    while ( v17 < 0 );
    while ( *v16++ )
      ;
    while ( (unsigned __int64)v16 < v15 )
    {
      while ( *v16++ )
        ;
      if ( *v16 >= 0 )
        break;
      v20 = *v16 & 0x7F;
      v21 = v16 + 1;
      v16 += 2;
      if ( *v21 >= 0 )
        break;
      while ( 1 )
      {
        v22 = *v16;
        if ( *v16 >= 0 )
          break;
        if ( v22 != 0x80 )
          goto LABEL_12;
        ++v16;
      }
      if ( v20 != 9 || (unsigned __int8)(v22 - 113) > 2u )
        break;
      v40 = v14++;
      a5[v40 + 2].Reserved1 = v22;
    }
LABEL_12:
    v53 = v14;
    if ( v14 )
    {
      v23 = *(_QWORD *)(a1 + 48);
      v24 = 0;
      v9 = 0;
      v48 = 0;
      v25 = 0;
      for ( i = 0; i < 8; ++i )
      {
        v27 = *((unsigned __int8 *)&a5[1].Ptr + i);
        v25 = (1025 * (v25 + v27)) ^ ((1025 * (v25 + v27)) >> 6);
      }
      v51 = v14 + 2;
      v28 = v14 + 2;
      for ( j = a4; v28 < a4; ++v28 )
      {
        for ( k = 0; k < a5[v28].Size; v25 = (1025 * (v25 + v30)) ^ ((1025 * (v25 + v30)) >> 6) )
          v30 = *(unsigned __int8 *)(a5[v28].Ptr + k++);
      }
      v31 = 32769 * ((9 * v25) ^ ((9 * v25) >> 11));
      SRWLock = (PSRWLOCK)(v23 + 264);
      v47 = v31;
      AcquireSRWLockShared((PSRWLOCK)(v23 + 264));
      v34 = (volatile signed __int64 *)(v23 + 8LL * (v31 & 0x1F));
      while ( 1 )
      {
        if ( !*v34 )
        {
          if ( *(_DWORD *)(v23 + 256) >= 0x400u )
          {
            ++*(_DWORD *)(v23 + 300);
            v9 = 234;
            goto LABEL_35;
          }
          if ( !v24 )
          {
            LOBYTE(v32) = j;
            LOBYTE(v33) = v14;
            NewEventEntry = CreateNewEventEntry(
                              (unsigned int)&EventDescriptor,
                              v32,
                              (_DWORD)a5,
                              v33,
                              v31,
                              (__int64)&v48);
            v24 = v48;
            v9 = NewEventEntry;
            if ( !v48 )
            {
              if ( NewEventEntry == 8 )
                ++*(_DWORD *)(v23 + 304);
              else
                ++*(_DWORD *)(v23 + 308);
              goto LABEL_35;
            }
          }
          if ( !_InterlockedCompareExchange64(v34, v24, 0) )
            break;
        }
        v35 = *v34;
        if ( v31 == *(_DWORD *)(*v34 + 40) )
        {
          v36 = *(_QWORD *)(v35 + 16);
          v37 = memcmp_0(&a5[1], (const void *)(v36 + 16), 8u);
          if ( !v37 )
          {
            v38 = j;
            for ( m = *(unsigned __int8 *)(v35 + 45) + 2; m < v38; ++m )
            {
              v37 = a5[m].Size - *(_DWORD *)(16LL * m + v36 + 8);
              if ( v37 )
                goto LABEL_32;
              v37 = memcmp_0((const void *)a5[m].Ptr, *(const void **)(16LL * m + v36), a5[m].Size);
              if ( v37 )
                goto LABEL_32;
              v38 = j;
            }
            v37 = 0;
          }
LABEL_32:
          v31 = v47;
        }
        else
        {
          v37 = v31 - *(_DWORD *)(v35 + 40);
        }
        if ( !v37 )
        {
          if ( v35 && v51 > 2u )
          {
            v42 = 2;
            do
            {
              AggregateField(
                *(_QWORD *)(*(_QWORD *)(v35 + 16) + 16 * v42),
                *(_QWORD *)a5[v42].Ptr,
                *(unsigned __int8 *)(*(_QWORD *)(v35 + 16) + 16 * v42 + 13));
              ++v7;
              v42 = v43 + 1;
            }
            while ( v7 < v44 );
          }
          goto LABEL_35;
        }
        v34 = (volatile signed __int64 *)(v35 + (((__int64)v37 >> 63) & 0xFFFFFFFFFFFFFFF8uLL) + 32);
        v14 = v53;
      }
      v24 = 0;
      if ( _InterlockedIncrement((volatile signed __int32 *)(v23 + 256)) == 1 )
        EnableFlushTimer(*(_QWORD *)(v23 + 344), *(unsigned int *)(v23 + 352));
      v45 = *(_DWORD *)(v23 + 256);
      if ( *(_DWORD *)(v23 + 288) < v45 )
        *(_DWORD *)(v23 + 288) = v45;
LABEL_35:
      ReleaseSRWLockShared(SRWLock);
      if ( v24 )
        DestroyEventEntry(v24);
    }
    else
    {
      return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, a4, a5);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180024df0  mov     [rsp+arg_10], rbx
0x180024df5  push    rbp
0x180024df6  push    rsi
0x180024df7  push    rdi
0x180024df8  push    r12
0x180024dfa  push    r13
0x180024dfc  push    r14
0x180024dfe  push    r15
0x180024e00  sub     rsp, 60h
0x180024e04  movzx   eax, byte ptr [rdx]
0x180024e07  mov     r10, rcx
0x180024e0a  mov     r14, [rsp+98h+arg_20]
0x180024e12  mov     r12d, 2
0x180024e18  shl     eax, 18h
0x180024e1b  mov     r11d, r9d
0x180024e1e  mov     dword ptr [rsp+98h+EventDescriptor.Id], eax
0x180024e22  mov     r15d, 0C000000Dh
0x180024e28  movzx   eax, word ptr [rdx+1]
0x180024e2c  mov     dword ptr [rsp+98h+EventDescriptor.Level], eax
0x180024e30  lea     r13d, [r12-1]
0x180024e35  mov     rax, [rdx+3]
0x180024e39  add     rdx, 0Bh
0x180024e3d  mov     [rsp+98h+EventDescriptor.Keyword], rax
0x180024e42  mov     rax, [rcx+8]
0x180024e46  mov     [r14], rax
0x180024e49  mov     rax, [rcx+8]
0x180024e4d  movzx   ecx, word ptr [rax]
0x180024e50  mov     [r14+10h], rdx
0x180024e54  mov     [r14+8], ecx
0x180024e58  mov     [r14+0Ch], r12d
0x180024e5c  movzx   eax, word ptr [rdx]
0x180024e5f  lea     rdx, _TraceLoggingMetadata
0x180024e66  mov     [r14+18h], eax
0x180024e6a  lea     rax, _TraceLoggingMetadataEnd
0x180024e71  sub     eax, edx
0x180024e73  mov     [r14+1Ch], r13d
0x180024e77  mov     dword ptr [rsp+98h+arg_20], eax
0x180024e7e  mov     eax, dword ptr [rsp+98h+arg_20]
0x180024e85  lea     rax, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x180024e8c  cmp     [r10+28h], rax
0x180024e90  jnz     loc_18002508E
0x180024e96  mov     rax, [r14+10h]
0x180024e9a  xor     bpl, bpl
0x180024e9d  mov     r9d, [r14+18h]
0x180024ea1  add     r9, rax
0x180024ea4  lea     rcx, [rax+2]
0x180024ea8  movzx   eax, byte ptr [rcx]
0x180024eab  add     rcx, r13
0x180024eae  test    al, al
0x180024eb0  js      short loc_180024EA8
0x180024eb2  mov     al, [rcx]
0x180024eb4  add     rcx, r13
0x180024eb7  test    al, al
0x180024eb9  jnz     short loc_180024EB2
0x180024ebb  cmp     rcx, r9
0x180024ebe  jnb     short loc_180024EF7
0x180024ec0  mov     al, [rcx]
0x180024ec2  add     rcx, r13
0x180024ec5  test    al, al
0x180024ec7  jnz     short loc_180024EC0
0x180024ec9  mov     r8b, [rcx]
0x180024ecc  test    r8b, r8b
0x180024ecf  jns     short loc_180024EF7
0x180024ed1  add     rcx, r13
0x180024ed4  and     r8b, 7Fh
0x180024ed8  mov     rax, rcx
0x180024edb  inc     rcx
0x180024ede  cmp     byte ptr [rax], 0
0x180024ee1  jge     short loc_180024EF7
0x180024ee3  mov     dl, [rcx]
0x180024ee5  test    dl, dl
0x180024ee7  jns     loc_180025040
0x180024eed  cmp     dl, 80h
0x180024ef0  jnz     short loc_180024EF7
0x180024ef2  add     rcx, r13
0x180024ef5  jmp     short loc_180024EE3
0x180024ef7  mov     byte ptr [rsp+98h+arg_20], bpl
0x180024eff  test    bpl, bpl
0x180024f02  jz      loc_1800251C9
0x180024f08  mov     rbx, [r10+30h]
0x180024f0c  xor     esi, esi
0x180024f0e  xor     r15d, r15d
0x180024f11  mov     [rsp+98h+var_60], rsi
0x180024f16  xor     edx, edx
0x180024f18  xor     r8d, r8d
0x180024f1b  movzx   eax, byte ptr [r14+r8+10h]
0x180024f21  add     r8, r13
0x180024f24  add     eax, edx
0x180024f26  imul    ecx, eax, 401h
0x180024f2c  mov     edx, ecx
0x180024f2e  shr     edx, 6
0x180024f31  xor     edx, ecx
0x180024f33  cmp     r8, 8
0x180024f37  jb      short loc_180024F1B
0x180024f39  lea     eax, [r12+rbp]
0x180024f3d  mov     dil, r11b
0x180024f40  mov     [rsp+98h+arg_0], al
0x180024f47  mov     r8b, al
0x180024f4a  mov     [rsp+98h+arg_8], edi
0x180024f51  cmp     al, r11b
0x180024f54  jnb     short loc_180024F92
0x180024f56  movzx   eax, r8b
0x180024f5a  xor     r9d, r9d
0x180024f5d  add     rax, rax
0x180024f60  mov     r10d, [r14+rax*8+8]
0x180024f65  mov     r11, [r14+rax*8]
0x180024f69  test    r10, r10
0x180024f6c  jz      short loc_180024F8A
0x180024f6e  movzx   eax, byte ptr [r11+r9]
0x180024f73  add     r9, r13
0x180024f76  add     eax, edx
0x180024f78  imul    ecx, eax, 401h
0x180024f7e  mov     edx, ecx
0x180024f80  shr     edx, 6
0x180024f83  xor     edx, ecx
0x180024f85  cmp     r9, r10
0x180024f88  jb      short loc_180024F6E
0x180024f8a  add     r8b, r13b
0x180024f8d  cmp     r8b, dil
0x180024f90  jb      short loc_180024F56
0x180024f92  lea     eax, [rdx+rdx*8]
0x180024f95  mov     ecx, eax
0x180024f97  shr     ecx, 0Bh
0x180024f9a  xor     ecx, eax
0x180024f9c  lea     rax, [rbx+108h]
0x180024fa3  imul    r13d, ecx, 8001h
0x180024faa  mov     rcx, rax; SRWLock
0x180024fad  mov     [rsp+98h+SRWLock], rax
0x180024fb2  mov     [rsp+98h+var_64], r13d
0x180024fb7  call    cs:__imp_AcquireSRWLockShared
0x180024fbd  mov     eax, r13d
0x180024fc0  and     eax, 1Fh
0x180024fc3  lea     rdi, [rbx+rax*8]
0x180024fc7  cmp     qword ptr [rdi], 0
0x180024fcb  jz      loc_1800250A9
0x180024fd1  mov     rbp, [rdi]
0x180024fd4  cmp     r13d, [rbp+28h]
0x180024fd8  jnz     loc_180025122
0x180024fde  mov     r13, [rbp+10h]
0x180024fe2  lea     rcx, [r14+10h]; Buf1
0x180024fe6  mov     r8d, 8; Size
0x180024fec  lea     rdx, [r13+10h]; Buf2
0x180024ff0  call    memcmp_0
0x180024ff5  test    eax, eax
0x180024ff7  jnz     short loc_18002506C
0x180024ff9  movzx   edi, byte ptr [rbp+2Dh]
0x180024ffd  movzx   eax, byte ptr [rsp+98h+arg_8]
0x180025005  add     edi, r12d
0x180025008  mov     [rsp+98h+var_68], eax
0x18002500c  cmp     edi, eax
0x18002500e  jnb     short loc_18002506A
0x180025010  mov     ecx, edi
0x180025012  shl     rcx, 4
0x180025016  mov     eax, [r14+rcx+8]
0x18002501b  sub     eax, [rcx+r13+8]
0x180025020  jnz     short loc_18002506C
0x180025022  mov     r8d, [r14+rcx+8]; Size
0x180025027  mov     rdx, [rcx+r13]; Buf2
0x18002502b  mov     rcx, [r14+rcx]; Buf1
0x18002502f  call    memcmp_0
0x180025034  test    eax, eax
0x180025036  jnz     short loc_18002506C
0x180025038  mov     eax, [rsp+98h+var_68]
0x18002503c  inc     edi
0x18002503e  jmp     short loc_18002500C
0x180025040  cmp     r8b, 9
0x180025044  jnz     loc_180024EF7
0x18002504a  lea     eax, [rdx-71h]
0x18002504d  cmp     al, r12b
0x180025050  ja      loc_180024EF7
0x180025056  movzx   eax, bpl
0x18002505a  add     rax, rax
0x18002505d  add     bpl, r13b
0x180025060  mov     [r14+rax*8+2Dh], dl
0x180025065  jmp     loc_180024EBB
0x18002506a  xor     eax, eax
0x18002506c  mov     r13d, [rsp+98h+var_64]
0x180025071  test    eax, eax
0x180025073  jnz     short loc_1800250C3
0x180025075  test    rbp, rbp
0x180025078  jnz     short loc_1800250E2
0x18002507a  mov     rcx, [rsp+98h+SRWLock]; SRWLock
0x18002507f  call    cs:__imp_ReleaseSRWLockShared
0x180025085  test    rsi, rsi
0x180025088  jnz     loc_1800251FE
0x18002508e  mov     rbx, [rsp+98h+arg_10]
0x180025096  mov     eax, r15d
0x180025099  add     rsp, 60h
0x18002509d  pop     r15
0x18002509f  pop     r14
0x1800250a1  pop     r13
0x1800250a3  pop     r12
0x1800250a5  pop     rdi
0x1800250a6  pop     rsi
0x1800250a7  pop     rbp
0x1800250a8  retn
0x1800250a9  cmp     dword ptr [rbx+100h], 400h
0x1800250b3  jb      short loc_18002512D
0x1800250b5  inc     dword ptr [rbx+12Ch]
0x1800250bb  mov     r15d, 0EAh
0x1800250c1  jmp     short loc_18002507A
0x1800250c3  movsxd  rdi, eax
0x1800250c6  sar     rdi, 3Fh
0x1800250ca  and     rdi, 0FFFFFFFFFFFFFFF8h
0x1800250ce  add     rdi, 20h ; ' '
0x1800250d2  add     rdi, rbp
0x1800250d5  mov     bpl, byte ptr [rsp+98h+arg_20]
0x1800250dd  jmp     loc_180024FC7
0x1800250e2  mov     r11b, [rsp+98h+arg_0]
0x1800250ea  cmp     r11b, r12b
0x1800250ed  jbe     short loc_18002507A
0x1800250ef  mov     r10, r12
0x1800250f2  mov     rcx, [rbp+10h]
0x1800250f6  mov     rax, r10
0x1800250f9  add     rax, rax
0x1800250fc  mov     rdx, [r14+rax*8]
0x180025100  movzx   r8d, byte ptr [rcx+rax*8+0Dh]
0x180025106  mov     rcx, [rcx+rax*8]
0x18002510a  mov     rdx, [rdx]
0x18002510d  call    AggregateField
0x180025112  inc     r12b
0x180025115  inc     r10
0x180025118  cmp     r12b, r11b
0x18002511b  jb      short loc_1800250F2
0x18002511d  jmp     loc_18002507A
0x180025122  mov     eax, r13d
0x180025125  sub     eax, [rbp+28h]
0x180025128  jmp     loc_180025071
0x18002512d  test    rsi, rsi
0x180025130  jz      short loc_180025182
0x180025132  xor     eax, eax
0x180025134  lock cmpxchg [rdi], rsi
0x180025139  jnz     loc_180024FD1
0x18002513f  xor     esi, esi
0x180025141  lea     eax, [rsi+1]
0x180025144  lock xadd [rbx+100h], eax
0x18002514c  inc     eax
0x18002514e  cmp     eax, 1
0x180025151  jnz     short loc_180025165
0x180025153  mov     edx, [rbx+160h]
0x180025159  mov     rcx, [rbx+158h]
0x180025160  call    EnableFlushTimer
0x180025165  mov     eax, [rbx+100h]
0x18002516b  cmp     [rbx+120h], eax
0x180025171  jnb     loc_18002507A
0x180025177  mov     [rbx+120h], eax
0x18002517d  jmp     loc_18002507A
0x180025182  mov     dl, byte ptr [rsp+98h+arg_8]
0x180025189  lea     rax, [rsp+98h+var_60]
0x18002518e  mov     [rsp+98h+UserData], rax
0x180025193  lea     rcx, [rsp+98h+EventDescriptor]
0x180025198  mov     r9b, bpl
0x18002519b  mov     [rsp+98h+UserDataCount], r13d
0x1800251a0  mov     r8, r14
0x1800251a3  call    CreateNewEventEntry
0x1800251a8  mov     rsi, [rsp+98h+var_60]
0x1800251ad  mov     r15d, eax
0x1800251b0  test    rsi, rsi
0x1800251b3  jnz     loc_180025132
0x1800251b9  cmp     eax, 8
0x1800251bc  jnz     short loc_1800251F3
0x1800251be  inc     dword ptr [rbx+130h]
0x1800251c4  jmp     loc_18002507A
0x1800251c9  mov     rcx, [r10+20h]; RegHandle
0x1800251cd  lea     rdx, [rsp+98h+EventDescriptor]; EventDescriptor
0x1800251d2  movzx   eax, r11b
0x1800251d6  xor     r9d, r9d; RelatedActivityId
0x1800251d9  mov     [rsp+98h+UserData], r14; UserData
0x1800251de  xor     r8d, r8d; ActivityId
0x1800251e1  mov     [rsp+98h+UserDataCount], eax; UserDataCount
0x1800251e5  call    cs:__imp_EventWriteTransfer
0x1800251eb  mov     r15d, eax
0x1800251ee  jmp     loc_18002508E
0x1800251f3  inc     dword ptr [rbx+134h]
0x1800251f9  jmp     loc_18002507A
0x1800251fe  mov     rcx, rsi
0x180025201  call    DestroyEventEntry
0x180025206  jmp     loc_18002508E
```
