# _tlgWriteAgg

- ea: `0x180010e54`
- end: `0x18001125a`
- name: `_tlgWriteAgg`
- size: `1030`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `37`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180001614`
- `0x180001878`
- `0x18000190c`
- `0x180001d50`
- `0x1800023a0`
- `0x180002e44`
- `0x1800034d4`
- `0x180003cdc`
- `0x180003da0`
- `0x180003ef8`
- `0x180003f8c`
- `0x1800048ec`
- `0x1800050ec`
- `0x1800052e0`
- `0x1800053cc`
- `0x180005594`
- `0x180006134`
- `0x18000639c`
- `0x180006510`
- `0x1800065d4`
- `0x180006c24`
- `0x180006d08`
- `0x180006f60`
- `0x1800071a4`
- `0x180007d8c`
- `0x180007e70`
- `0x180007fa4`
- `0x180008130`
- `0x1800081d4`
- `0x180008758`
- `0x180008924`
- `0x180009020`
- `0x180009410`
- `0x1800103fc`
- `0x180010568`
- `0x180010678`
- `0x1800dce00`

## callees

- `0x180010e54`
- `0x180011260`
- `0x18004d68c`
- `0x1800633e0`
- `0x1800aa588`
- `0x1800f3784`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180011036`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180011036`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800110e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800110e0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180011210`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180011210`

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
  __int64 v23; // rax
  __int64 v24; // rbx
  signed __int64 v25; // rsi
  unsigned int v26; // edx
  unsigned __int64 i; // r8
  int v28; // eax
  unsigned __int8 v29; // r8
  unsigned __int64 k; // r9
  int v31; // eax
  unsigned int v32; // r13d
  int v33; // edx
  int v34; // r9d
  volatile signed __int64 *v35; // rdi
  volatile signed __int64 v36; // rbp
  __int64 v37; // r13
  int v38; // eax
  unsigned int v39; // eax
  unsigned int m; // edi
  __int64 v42; // r10
  __int64 v43; // r10
  unsigned __int8 v44; // r11
  unsigned int NewEventEntry; // eax
  unsigned int v46; // eax
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
          goto LABEL_15;
        ++v16;
      }
      if ( v20 != 9 || (unsigned __int8)(v22 - 113) > 2u )
        break;
      v23 = v14++;
      a5[v23 + 2].Reserved1 = v22;
    }
LABEL_15:
    v53 = v14;
    if ( v14 )
    {
      v24 = *(_QWORD *)(a1 + 48);
      v25 = 0;
      v9 = 0;
      v48 = 0;
      v26 = 0;
      for ( i = 0; i < 8; ++i )
      {
        v28 = *((unsigned __int8 *)&a5[1].Ptr + i);
        v26 = (1025 * (v26 + v28)) ^ ((1025 * (v26 + v28)) >> 6);
      }
      v51 = v14 + 2;
      v29 = v14 + 2;
      for ( j = a4; v29 < a4; ++v29 )
      {
        for ( k = 0; k < a5[v29].Size; v26 = (1025 * (v26 + v31)) ^ ((1025 * (v26 + v31)) >> 6) )
          v31 = *(unsigned __int8 *)(a5[v29].Ptr + k++);
      }
      v32 = 32769 * ((9 * v26) ^ ((9 * v26) >> 11));
      SRWLock = (PSRWLOCK)(v24 + 264);
      v47 = v32;
      AcquireSRWLockShared((PSRWLOCK)(v24 + 264));
      v35 = (volatile signed __int64 *)(v24 + 8LL * (v32 & 0x1F));
      while ( 1 )
      {
        if ( !*v35 )
        {
          if ( *(_DWORD *)(v24 + 256) >= 0x400u )
          {
            ++*(_DWORD *)(v24 + 300);
            v9 = 234;
            goto LABEL_33;
          }
          if ( !v25 )
          {
            LOBYTE(v33) = j;
            LOBYTE(v34) = v14;
            NewEventEntry = CreateNewEventEntry(
                              (unsigned int)&EventDescriptor,
                              v33,
                              (_DWORD)a5,
                              v34,
                              v32,
                              (__int64)&v48);
            v25 = v48;
            v9 = NewEventEntry;
            if ( !v48 )
            {
              if ( NewEventEntry == 8 )
                ++*(_DWORD *)(v24 + 304);
              else
                ++*(_DWORD *)(v24 + 308);
              goto LABEL_33;
            }
          }
          if ( !_InterlockedCompareExchange64(v35, v25, 0) )
            break;
        }
        v36 = *v35;
        if ( v32 == *(_DWORD *)(*v35 + 40) )
        {
          v37 = *(_QWORD *)(v36 + 16);
          v38 = memcmp_0(&a5[1], (const void *)(v37 + 16), 8u);
          if ( !v38 )
          {
            v39 = j;
            for ( m = *(unsigned __int8 *)(v36 + 45) + 2; m < v39; ++m )
            {
              v38 = a5[m].Size - *(_DWORD *)(16LL * m + v37 + 8);
              if ( v38 )
                goto LABEL_37;
              v38 = memcmp_0((const void *)a5[m].Ptr, *(const void **)(16LL * m + v37), a5[m].Size);
              if ( v38 )
                goto LABEL_37;
              v39 = j;
            }
            v38 = 0;
          }
LABEL_37:
          v32 = v47;
        }
        else
        {
          v38 = v32 - *(_DWORD *)(v36 + 40);
        }
        if ( !v38 )
        {
          if ( v36 && v51 > 2u )
          {
            v42 = 2;
            do
            {
              AggregateField(
                *(_QWORD *)(*(_QWORD *)(v36 + 16) + 16 * v42),
                *(_QWORD *)a5[v42].Ptr,
                *(unsigned __int8 *)(*(_QWORD *)(v36 + 16) + 16 * v42 + 13));
              ++v7;
              v42 = v43 + 1;
            }
            while ( v7 < v44 );
          }
          goto LABEL_33;
        }
        v35 = (volatile signed __int64 *)(v36 + (((__int64)v38 >> 63) & 0xFFFFFFFFFFFFFFF8uLL) + 32);
        v14 = v53;
      }
      v25 = 0;
      if ( _InterlockedIncrement((volatile signed __int32 *)(v24 + 256)) == 1 )
        EnableFlushTimer(*(_QWORD *)(v24 + 344), *(unsigned int *)(v24 + 352));
      v46 = *(_DWORD *)(v24 + 256);
      if ( *(_DWORD *)(v24 + 288) < v46 )
        *(_DWORD *)(v24 + 288) = v46;
LABEL_33:
      ReleaseSRWLockShared(SRWLock);
      if ( v25 )
        DestroyEventEntry(v25);
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
0x180010e54  mov     [rsp+arg_10], rbx
0x180010e59  push    rbp
0x180010e5a  push    rsi
0x180010e5b  push    rdi
0x180010e5c  push    r12
0x180010e5e  push    r13
0x180010e60  push    r14
0x180010e62  push    r15
0x180010e64  sub     rsp, 60h
0x180010e68  movzx   eax, byte ptr [rdx]
0x180010e6b  mov     r10, rcx
0x180010e6e  mov     r14, [rsp+98h+arg_20]
0x180010e76  mov     r12d, 2
0x180010e7c  shl     eax, 18h
0x180010e7f  mov     r11d, r9d
0x180010e82  mov     dword ptr [rsp+98h+EventDescriptor.Id], eax
0x180010e86  mov     r15d, 0C000000Dh
0x180010e8c  movzx   eax, word ptr [rdx+1]
0x180010e90  mov     dword ptr [rsp+98h+EventDescriptor.Level], eax
0x180010e94  lea     r13d, [r12-1]
0x180010e99  mov     rax, [rdx+3]
0x180010e9d  add     rdx, 0Bh
0x180010ea1  mov     [rsp+98h+EventDescriptor.Keyword], rax
0x180010ea6  mov     rax, [rcx+8]
0x180010eaa  mov     [r14], rax
0x180010ead  mov     rax, [rcx+8]
0x180010eb1  movzx   ecx, word ptr [rax]
0x180010eb4  mov     [r14+10h], rdx
0x180010eb8  mov     [r14+8], ecx
0x180010ebc  mov     [r14+0Ch], r12d
0x180010ec0  movzx   eax, word ptr [rdx]
0x180010ec3  lea     rdx, _TraceLoggingMetadata
0x180010eca  mov     [r14+18h], eax
0x180010ece  lea     rax, _TraceLoggingMetadataEnd
0x180010ed5  sub     eax, edx
0x180010ed7  mov     [r14+1Ch], r13d
0x180010edb  mov     dword ptr [rsp+98h+arg_20], eax
0x180010ee2  mov     eax, dword ptr [rsp+98h+arg_20]
0x180010ee9  lea     rax, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x180010ef0  cmp     [r10+28h], rax
0x180010ef4  jnz     loc_1800110EF
0x180010efa  mov     rax, [r14+10h]
0x180010efe  xor     bpl, bpl
0x180010f01  mov     r9d, [r14+18h]
0x180010f05  add     r9, rax
0x180010f08  lea     rcx, [rax+2]
0x180010f0c  movzx   eax, byte ptr [rcx]
0x180010f0f  add     rcx, r13
0x180010f12  test    al, al
0x180010f14  js      short loc_180010F0C
0x180010f16  mov     al, [rcx]
0x180010f18  add     rcx, r13
0x180010f1b  test    al, al
0x180010f1d  jnz     short loc_180010F16
0x180010f1f  cmp     rcx, r9
0x180010f22  jnb     short loc_180010F76
0x180010f24  mov     al, [rcx]
0x180010f26  add     rcx, r13
0x180010f29  test    al, al
0x180010f2b  jnz     short loc_180010F24
0x180010f2d  mov     r8b, [rcx]
0x180010f30  test    r8b, r8b
0x180010f33  jns     short loc_180010F76
0x180010f35  add     rcx, r13
0x180010f38  and     r8b, 7Fh
0x180010f3c  mov     rax, rcx
0x180010f3f  inc     rcx
0x180010f42  cmp     byte ptr [rax], 0
0x180010f45  jge     short loc_180010F76
0x180010f47  mov     dl, [rcx]
0x180010f49  test    dl, dl
0x180010f4b  jns     short loc_180010F57
0x180010f4d  cmp     dl, 80h
0x180010f50  jnz     short loc_180010F76
0x180010f52  add     rcx, r13
0x180010f55  jmp     short loc_180010F47
0x180010f57  cmp     r8b, 9
0x180010f5b  jnz     short loc_180010F76
0x180010f5d  lea     eax, [rdx-71h]
0x180010f60  cmp     al, r12b
0x180010f63  ja      short loc_180010F76
0x180010f65  movzx   eax, bpl
0x180010f69  add     rax, rax
0x180010f6c  add     bpl, r13b
0x180010f6f  mov     [r14+rax*8+2Dh], dl
0x180010f74  jmp     short loc_180010F1F
0x180010f76  mov     byte ptr [rsp+98h+arg_20], bpl
0x180010f7e  test    bpl, bpl
0x180010f81  jz      loc_1800111F4
0x180010f87  mov     rbx, [r10+30h]
0x180010f8b  xor     esi, esi
0x180010f8d  xor     r15d, r15d
0x180010f90  mov     [rsp+98h+var_60], rsi
0x180010f95  xor     edx, edx
0x180010f97  xor     r8d, r8d
0x180010f9a  movzx   eax, byte ptr [r14+r8+10h]
0x180010fa0  add     r8, r13
0x180010fa3  add     eax, edx
0x180010fa5  imul    ecx, eax, 401h
0x180010fab  mov     edx, ecx
0x180010fad  shr     edx, 6
0x180010fb0  xor     edx, ecx
0x180010fb2  cmp     r8, 8
0x180010fb6  jb      short loc_180010F9A
0x180010fb8  lea     eax, [r12+rbp]
0x180010fbc  mov     dil, r11b
0x180010fbf  mov     [rsp+98h+arg_0], al
0x180010fc6  mov     r8b, al
0x180010fc9  mov     [rsp+98h+arg_8], edi
0x180010fd0  cmp     al, r11b
0x180010fd3  jnb     short loc_180011011
0x180010fd5  movzx   eax, r8b
0x180010fd9  xor     r9d, r9d
0x180010fdc  add     rax, rax
0x180010fdf  mov     r10d, [r14+rax*8+8]
0x180010fe4  mov     r11, [r14+rax*8]
0x180010fe8  test    r10, r10
0x180010feb  jz      short loc_180011009
0x180010fed  movzx   eax, byte ptr [r11+r9]
0x180010ff2  add     r9, r13
0x180010ff5  add     eax, edx
0x180010ff7  imul    ecx, eax, 401h
0x180010ffd  mov     edx, ecx
0x180010fff  shr     edx, 6
0x180011002  xor     edx, ecx
0x180011004  cmp     r9, r10
0x180011007  jb      short loc_180010FED
0x180011009  add     r8b, r13b
0x18001100c  cmp     r8b, dil
0x18001100f  jb      short loc_180010FD5
0x180011011  lea     eax, [rdx+rdx*8]
0x180011014  mov     ecx, eax
0x180011016  shr     ecx, 0Bh
0x180011019  xor     ecx, eax
0x18001101b  lea     rax, [rbx+108h]
0x180011022  imul    r13d, ecx, 8001h
0x180011029  mov     rcx, rax; SRWLock
0x18001102c  mov     [rsp+98h+SRWLock], rax
0x180011031  mov     [rsp+98h+var_64], r13d
0x180011036  call    cs:__imp_AcquireSRWLockShared
0x18001103c  mov     eax, r13d
0x18001103f  and     eax, 1Fh
0x180011042  lea     rdi, [rbx+rax*8]
0x180011046  cmp     qword ptr [rdi], 0
0x18001104a  jz      short loc_1800110BF
0x18001104c  mov     rbp, [rdi]
0x18001104f  cmp     r13d, [rbp+28h]
0x180011053  jnz     loc_180011176
0x180011059  mov     r13, [rbp+10h]
0x18001105d  lea     rcx, [r14+10h]; Buf1
0x180011061  mov     r8d, 8; Size
0x180011067  lea     rdx, [r13+10h]; Buf2
0x18001106b  call    memcmp_0
0x180011070  test    eax, eax
0x180011072  jnz     loc_18001110C
0x180011078  movzx   edi, byte ptr [rbp+2Dh]
0x18001107c  movzx   eax, byte ptr [rsp+98h+arg_8]
0x180011084  add     edi, r12d
0x180011087  mov     [rsp+98h+var_68], eax
0x18001108b  cmp     edi, eax
0x18001108d  jnb     short loc_18001110A
0x18001108f  mov     ecx, edi
0x180011091  shl     rcx, 4
0x180011095  mov     eax, [r14+rcx+8]
0x18001109a  sub     eax, [rcx+r13+8]
0x18001109f  jnz     short loc_18001110C
0x1800110a1  mov     r8d, [r14+rcx+8]; Size
0x1800110a6  mov     rdx, [rcx+r13]; Buf2
0x1800110aa  mov     rcx, [r14+rcx]; Buf1
0x1800110ae  call    memcmp_0
0x1800110b3  test    eax, eax
0x1800110b5  jnz     short loc_18001110C
0x1800110b7  mov     eax, [rsp+98h+var_68]
0x1800110bb  inc     edi
0x1800110bd  jmp     short loc_18001108B
0x1800110bf  cmp     dword ptr [rbx+100h], 400h
0x1800110c9  jb      loc_18001117E
0x1800110cf  inc     dword ptr [rbx+12Ch]
0x1800110d5  mov     r15d, 0EAh
0x1800110db  mov     rcx, [rsp+98h+SRWLock]; SRWLock
0x1800110e0  call    cs:__imp_ReleaseSRWLockShared
0x1800110e6  test    rsi, rsi
0x1800110e9  jnz     loc_18001124D
0x1800110ef  mov     rbx, [rsp+98h+arg_10]
0x1800110f7  mov     eax, r15d
0x1800110fa  add     rsp, 60h
0x1800110fe  pop     r15
0x180011100  pop     r14
0x180011102  pop     r13
0x180011104  pop     r12
0x180011106  pop     rdi
0x180011107  pop     rsi
0x180011108  pop     rbp
0x180011109  retn
0x18001110a  xor     eax, eax
0x18001110c  mov     r13d, [rsp+98h+var_64]
0x180011111  test    eax, eax
0x180011113  jnz     short loc_180011157
0x180011115  test    rbp, rbp
0x180011118  jz      short loc_1800110DB
0x18001111a  mov     r11b, [rsp+98h+arg_0]
0x180011122  cmp     r11b, r12b
0x180011125  jbe     short loc_1800110DB
0x180011127  mov     r10, r12
0x18001112a  mov     rcx, [rbp+10h]
0x18001112e  mov     rax, r10
0x180011131  add     rax, rax
0x180011134  mov     rdx, [r14+rax*8]
0x180011138  movzx   r8d, byte ptr [rcx+rax*8+0Dh]
0x18001113e  mov     rcx, [rcx+rax*8]
0x180011142  mov     rdx, [rdx]
0x180011145  call    AggregateField
0x18001114a  inc     r12b
0x18001114d  inc     r10
0x180011150  cmp     r12b, r11b
0x180011153  jb      short loc_18001112A
0x180011155  jmp     short loc_1800110DB
0x180011157  movsxd  rdi, eax
0x18001115a  sar     rdi, 3Fh
0x18001115e  and     rdi, 0FFFFFFFFFFFFFFF8h
0x180011162  add     rdi, 20h ; ' '
0x180011166  add     rdi, rbp
0x180011169  mov     bpl, byte ptr [rsp+98h+arg_20]
0x180011171  jmp     loc_180011046
0x180011176  mov     eax, r13d
0x180011179  sub     eax, [rbp+28h]
0x18001117c  jmp     short loc_180011111
0x18001117e  test    rsi, rsi
0x180011181  jnz     short loc_1800111B6
0x180011183  mov     dl, byte ptr [rsp+98h+arg_8]
0x18001118a  lea     rax, [rsp+98h+var_60]
0x18001118f  mov     [rsp+98h+UserData], rax
0x180011194  lea     rcx, [rsp+98h+EventDescriptor]
0x180011199  mov     r9b, bpl
0x18001119c  mov     [rsp+98h+UserDataCount], r13d
0x1800111a1  mov     r8, r14
0x1800111a4  call    CreateNewEventEntry
0x1800111a9  mov     rsi, [rsp+98h+var_60]
0x1800111ae  mov     r15d, eax
0x1800111b1  test    rsi, rsi
0x1800111b4  jz      short loc_18001121E
0x1800111b6  xor     eax, eax
0x1800111b8  lock cmpxchg [rdi], rsi
0x1800111bd  jnz     loc_18001104C
0x1800111c3  xor     esi, esi
0x1800111c5  lea     eax, [rsi+1]
0x1800111c8  lock xadd [rbx+100h], eax
0x1800111d0  inc     eax
0x1800111d2  cmp     eax, 1
0x1800111d5  jz      short loc_180011239
0x1800111d7  mov     eax, [rbx+100h]
0x1800111dd  cmp     [rbx+120h], eax
0x1800111e3  jnb     loc_1800110DB
0x1800111e9  mov     [rbx+120h], eax
0x1800111ef  jmp     loc_1800110DB
0x1800111f4  mov     rcx, [r10+20h]; RegHandle
0x1800111f8  lea     rdx, [rsp+98h+EventDescriptor]; EventDescriptor
0x1800111fd  movzx   eax, r11b
0x180011201  xor     r9d, r9d; RelatedActivityId
0x180011204  mov     [rsp+98h+UserData], r14; UserData
0x180011209  xor     r8d, r8d; ActivityId
0x18001120c  mov     [rsp+98h+UserDataCount], eax; UserDataCount
0x180011210  call    cs:__imp_EventWriteTransfer
0x180011216  mov     r15d, eax
0x180011219  jmp     loc_1800110EF
0x18001121e  cmp     eax, 8
0x180011221  jnz     short loc_18001122E
0x180011223  inc     dword ptr [rbx+130h]
0x180011229  jmp     loc_1800110DB
0x18001122e  inc     dword ptr [rbx+134h]
0x180011234  jmp     loc_1800110DB
0x180011239  mov     edx, [rbx+160h]
0x18001123f  mov     rcx, [rbx+158h]
0x180011246  call    EnableFlushTimer
0x18001124b  jmp     short loc_1800111D7
0x18001124d  mov     rcx, rsi
0x180011250  call    DestroyEventEntry
0x180011255  jmp     loc_1800110EF
```
