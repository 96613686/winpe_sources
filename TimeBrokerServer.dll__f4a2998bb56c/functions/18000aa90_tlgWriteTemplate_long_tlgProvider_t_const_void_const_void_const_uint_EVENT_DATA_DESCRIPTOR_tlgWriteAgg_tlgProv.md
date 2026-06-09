# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000aa90`
- end: `0x18000b0c4`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U1@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@2222AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@33@Z`
- size: `1588`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, __int64, __int64, __int64, __int64, __int64, int **, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000ef50`

## callees

- `0x18000aa90`
- `0x18000b658`
- `0x18000b6b0`
- `0x18000bf3c`
- `0x180012dd0`
- `0x1800139d8`
- `0x180019d3b`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000af00`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000af00`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000addd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000addd`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        int **a10,
        __int64 a11,
        __int64 a12)
{
  int *v12; // rcx
  __int64 v13; // rax
  int v15; // eax
  unsigned __int8 v16; // r12
  unsigned __int64 v17; // r9
  char *v18; // rcx
  char v19; // al
  char *v22; // rax
  char v23; // dl
  char v24; // r8
  __int64 v25; // rax
  __int64 v26; // r13
  unsigned __int8 v27; // r11
  unsigned int v28; // edx
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int i; // eax
  unsigned __int64 j; // r8
  int v33; // ecx
  unsigned int v34; // r14d
  int v35; // edx
  volatile signed __int64 *k; // rbx
  volatile signed __int64 v37; // rsi
  int v38; // ecx
  __int64 v39; // r15
  int v40; // eax
  unsigned int m; // ebx
  unsigned __int8 v42; // dl
  __int64 v43; // r15
  signed __int64 v44; // r10
  __int64 v45; // rax
  int v46; // r8d
  volatile signed __int64 *v47; // r9
  signed __int64 v48; // rax
  int v49; // ebx
  unsigned int v51; // eax
  volatile signed __int64 v52; // rtt
  int NewEventEntry; // [rsp+30h] [rbp-D0h]
  unsigned __int8 v54; // [rsp+34h] [rbp-CCh]
  signed __int64 v55; // [rsp+38h] [rbp-C8h]
  signed __int64 v56; // [rsp+40h] [rbp-C0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int8 *Buf1; // [rsp+70h] [rbp-90h] BYREF
  int v60; // [rsp+78h] [rbp-88h]
  int v61; // [rsp+7Ch] [rbp-84h]
  __int64 v62; // [rsp+80h] [rbp-80h]
  _QWORD v63[12]; // [rsp+88h] [rbp-78h]
  int v64; // [rsp+E8h] [rbp-18h]
  int v65; // [rsp+ECh] [rbp-14h]
  __int64 v66; // [rsp+F0h] [rbp-10h]
  __int64 v67; // [rsp+F8h] [rbp-8h]
  __int64 v68; // [rsp+100h] [rbp+0h]
  __int64 v69; // [rsp+108h] [rbp+8h]

  v68 = a12;
  v66 = a11;
  v69 = 4;
  v67 = 4;
  v12 = *a10;
  if ( *a10 )
  {
    v13 = -1;
    while ( *((_WORD *)v12 + ++v13) != 0 )
      ;
    v15 = 2 * v13 + 2;
  }
  else
  {
    v12 = &dword_18001EDEC;
    v15 = 2;
  }
  v64 = v15;
  v63[9] = a9;
  v63[7] = a8;
  v63[5] = a7;
  v63[3] = a6;
  v63[1] = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180026060;
  v63[11] = v12;
  v65 = 0;
  v63[10] = 4;
  v63[8] = 8;
  v63[6] = 8;
  v63[4] = 8;
  v63[2] = 8;
  v62 = a4;
  v63[0] = 8;
  UserData.Size = *(unsigned __int16 *)off_180026060;
  v60 = *(unsigned __int16 *)(a2 + 11);
  Buf1 = a2 + 11;
  UserData.Reserved = 2;
  v61 = 1;
  if ( (void (__fastcall *)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))qword_180026080 != TlgAggregateInternalRegisteredProviderEtwCallback )
    return -1073741811;
  v16 = 0;
  v17 = (unsigned __int64)&Buf1[v60];
  v18 = (char *)(Buf1 + 2);
  do
    v19 = *v18++;
  while ( v19 < 0 );
  while ( *v18++ )
    ;
  while ( (unsigned __int64)v18 < v17 )
  {
    while ( *v18++ )
      ;
    if ( *v18 >= 0 )
      break;
    v22 = v18 + 1;
    v23 = *v18 & 0x7F;
    v18 += 2;
    if ( *v22 >= 0 )
      break;
    while ( 1 )
    {
      v24 = *v18;
      if ( *v18 >= 0 )
        break;
      if ( v24 != (char)0x80 )
        goto LABEL_19;
      ++v18;
    }
    if ( v23 != 9 || (unsigned __int8)(v24 - 113) > 2u )
      break;
    v25 = 2LL * v16++;
    BYTE5(v63[v25]) = v24;
  }
LABEL_19:
  if ( !v16 )
    return EventWriteTransfer_0(RegHandle, &EventDescriptor, 0, 0, 0xBu, &UserData);
  v26 = qword_180026088;
  v55 = 0;
  v56 = 0;
  NewEventEntry = 0;
  _mm_lfence();
  v27 = v16 + 2;
  v54 = v16 + 2;
  v28 = BYTE1(Buf1) + ((1025 * (unsigned __int8)Buf1) ^ ((1025 * (unsigned int)(unsigned __int8)Buf1) >> 6));
  v29 = 1025
      * (BYTE5(Buf1)
       + ((1025
         * (BYTE4(Buf1)
          + ((1025
            * (BYTE3(Buf1)
             + ((1025 * (BYTE2(Buf1) + ((1025 * v28) ^ ((1025 * v28) >> 6))))
              ^ ((1025 * (BYTE2(Buf1) + ((1025 * v28) ^ ((1025 * v28) >> 6)))) >> 6))))
           ^ ((1025
             * (BYTE3(Buf1)
              + ((1025 * (BYTE2(Buf1) + ((1025 * v28) ^ ((1025 * v28) >> 6))))
               ^ ((1025 * (BYTE2(Buf1) + ((1025 * v28) ^ ((1025 * v28) >> 6)))) >> 6)))) >> 6))))
        ^ ((1025
          * (BYTE4(Buf1)
           + ((1025
             * (BYTE3(Buf1)
              + ((1025 * (BYTE2(Buf1) + ((1025 * v28) ^ ((1025 * v28) >> 6))))
               ^ ((1025 * (BYTE2(Buf1) + ((1025 * v28) ^ ((1025 * v28) >> 6)))) >> 6))))
            ^ ((1025
              * (BYTE3(Buf1)
               + ((1025 * (BYTE2(Buf1) + ((1025 * v28) ^ ((1025 * v28) >> 6))))
                ^ ((1025 * (BYTE2(Buf1) + ((1025 * v28) ^ ((1025 * v28) >> 6)))) >> 6)))) >> 6)))) >> 6)));
  v30 = 1025 * (BYTE6(Buf1) + (v29 ^ (v29 >> 6)));
  for ( i = (1025 * (HIBYTE(Buf1) + (v30 ^ (v30 >> 6)))) ^ ((1025 * (HIBYTE(Buf1) + (v30 ^ (v30 >> 6)))) >> 6);
        v27 < 0xBu;
        ++v27 )
  {
    for ( j = 0; j < *(&UserData.Size + 4 * v27); i = (1025 * (i + v33)) ^ ((1025 * (i + v33)) >> 6) )
      v33 = *(unsigned __int8 *)(*(&UserData.Ptr + 2 * v27) + j++);
  }
  v34 = 32769 * ((9 * i) ^ ((9 * i) >> 11));
  AcquireSRWLockShared((PSRWLOCK)(qword_180026088 + 264));
  for ( k = (volatile signed __int64 *)(v26 + 8LL * (v34 & 0x1F));
        ;
        k = (volatile signed __int64 *)(v37 + (((__int64)v40 >> 63) & 0xFFFFFFFFFFFFFFF8uLL) + 32) )
  {
    if ( !*k )
    {
      if ( *(_DWORD *)(v26 + 256) >= 0x400u )
      {
        ++*(_DWORD *)(v26 + 300);
        v49 = 234;
        goto LABEL_45;
      }
      if ( !v55 )
      {
        LOBYTE(v35) = 11;
        NewEventEntry = CreateNewEventEntry(
                          (unsigned int)&EventDescriptor,
                          v35,
                          (unsigned int)&UserData,
                          v16,
                          v34,
                          (__int64)&v56);
        v55 = v56;
        if ( !v56 )
        {
          v49 = NewEventEntry;
          if ( NewEventEntry == 8 )
            ++*(_DWORD *)(v26 + 304);
          else
            ++*(_DWORD *)(v26 + 308);
          goto LABEL_45;
        }
      }
      if ( !_InterlockedCompareExchange64(k, v55, 0) )
      {
        v55 = 0;
        if ( _InterlockedIncrement((volatile signed __int32 *)(v26 + 256)) == 1 )
          EnableFlushTimer(*(_QWORD *)(v26 + 344), *(unsigned int *)(v26 + 352));
        v51 = *(_DWORD *)(v26 + 256);
        v49 = NewEventEntry;
        if ( *(_DWORD *)(v26 + 288) < v51 )
          *(_DWORD *)(v26 + 288) = v51;
        goto LABEL_45;
      }
    }
    v37 = *k;
    v38 = *(_DWORD *)(*k + 40);
    if ( v34 == v38 )
    {
      v39 = *(_QWORD *)(v37 + 16);
      v40 = memcmp_0(&Buf1, (const void *)(v39 + 16), 8u);
      if ( v40 )
        continue;
      for ( m = *(unsigned __int8 *)(v37 + 45) + 2; m < 0xB; ++m )
      {
        v40 = *(&UserData.Size + 4 * m) - *(_DWORD *)(v39 + 16LL * m + 8);
        if ( v40 )
          goto LABEL_34;
        v40 = memcmp_0(
                *((const void **)&UserData.Ptr + 2 * m),
                *(const void **)(v39 + 16LL * m),
                *(&UserData.Size + 4 * m));
        if ( v40 )
          goto LABEL_48;
      }
      v40 = 0;
    }
    else
    {
      v40 = v34 - v38;
    }
LABEL_34:
    if ( !v40 )
      break;
LABEL_48:
    ;
  }
  if ( v37 )
  {
    v42 = 2;
    if ( v54 > 2u )
    {
      v43 = 2;
      do
      {
        v44 = **((_QWORD **)&UserData.Ptr + 2 * v43);
        v45 = *(_QWORD *)(v37 + 16);
        v46 = *(unsigned __int8 *)(v45 + 16 * v43 + 13);
        v47 = *(volatile signed __int64 **)(v45 + 16 * v43);
        if ( (_BYTE)v46 == 115 )
          goto LABEL_39;
        if ( v46 == 113 )
        {
          _InterlockedAdd64(v47, v44);
        }
        else if ( v46 == 114 )
        {
          do
          {
LABEL_39:
            v48 = *v47;
            if ( (_BYTE)v46 == 114 )
            {
              if ( v44 >= v48 )
                break;
            }
            else if ( v44 <= v48 )
            {
              break;
            }
            v52 = *v47;
          }
          while ( v52 != _InterlockedCompareExchange64(v47, v44, v48) );
        }
        ++v42;
        ++v43;
      }
      while ( v42 < v54 );
    }
  }
  v49 = NewEventEntry;
LABEL_45:
  ReleaseSRWLockShared((PSRWLOCK)(v26 + 264));
  if ( v55 )
    DestroyEventEntry(v55);
  return v49;
}

```

## disassembly

```asm
0x18000aa90  push    rbp
0x18000aa92  push    rsi
0x18000aa93  push    r15
0x18000aa95  lea     rbp, [rsp-30h]
0x18000aa9a  sub     rsp, 130h
0x18000aaa1  mov     rax, cs:__security_cookie
0x18000aaa8  xor     rax, rsp
0x18000aaab  mov     [rbp+40h+var_30], rax
0x18000aaaf  mov     rax, [rbp+40h+arg_58]
0x18000aab6  xor     esi, esi
0x18000aab8  mov     [rbp+40h+var_40], rax
0x18000aabc  mov     r15d, 2
0x18000aac2  mov     rax, [rbp+40h+arg_50]
0x18000aac9  mov     [rbp+40h+var_50], rax
0x18000aacd  mov     rax, [rbp+40h+arg_48]
0x18000aad4  mov     [rbp+40h+var_38], 4
0x18000aadc  mov     [rbp+40h+var_48], 4
0x18000aae4  mov     rcx, [rax]
0x18000aae7  test    rcx, rcx
0x18000aaea  jz      loc_18000B03E
0x18000aaf0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000aaf7  nop     word ptr [rax+rax+00000000h]
0x18000ab00  cmp     [rcx+rax*2+2], si
0x18000ab05  lea     rax, [rax+1]
0x18000ab09  jnz     short loc_18000AB00
0x18000ab0b  lea     eax, ds:2[rax*2]
0x18000ab12  mov     [rbp+40h+var_58], eax
0x18000ab15  mov     rax, [rbp+40h+arg_40]
0x18000ab1c  mov     [rbp+40h+var_70], rax
0x18000ab20  mov     rax, [rbp+40h+arg_38]
0x18000ab27  mov     [rbp+40h+var_80], rax
0x18000ab2b  mov     rax, [rbp+40h+arg_30]
0x18000ab32  mov     [rbp+40h+var_90], rax
0x18000ab36  mov     rax, [rbp+40h+arg_28]
0x18000ab3a  mov     [rbp+40h+var_A0], rax
0x18000ab3e  mov     rax, [rbp+40h+arg_20]
0x18000ab42  mov     [rbp+40h+var_B0], rax
0x18000ab46  movzx   eax, byte ptr [rdx]
0x18000ab49  shl     eax, 18h
0x18000ab4c  mov     dword ptr [rsp+140h+EventDescriptor.Id], eax
0x18000ab50  movzx   eax, word ptr [rdx+1]
0x18000ab54  mov     dword ptr [rsp+140h+EventDescriptor.Level], eax
0x18000ab58  mov     rax, [rdx+3]
0x18000ab5c  mov     [rsp+140h+EventDescriptor.Keyword], rax
0x18000ab61  mov     rax, cs:off_180026060
0x18000ab68  mov     [rsp+140h+var_E0.Ptr], rax
0x18000ab6d  mov     [rbp+40h+var_60], rcx
0x18000ab71  lea     rcx, [rdx+0Bh]
0x18000ab75  mov     [rbp+40h+var_54], esi
0x18000ab78  mov     [rbp+40h+var_68], 4
0x18000ab80  mov     [rbp+40h+var_78], 8
0x18000ab88  mov     [rbp+40h+var_88], 8
0x18000ab90  mov     [rbp+40h+var_98], 8
0x18000ab98  mov     [rbp+40h+var_A8], 8
0x18000aba0  mov     [rbp+40h+var_C0], r9
0x18000aba4  mov     [rbp+40h+var_B8], 8
0x18000abac  movzx   eax, word ptr [rax]
0x18000abaf  mov     [rsp+140h+var_E0.Size], eax
0x18000abb3  movzx   eax, word ptr [rcx]
0x18000abb6  mov     [rsp+140h+var_C8], eax
0x18000abba  lea     rax, _TraceLoggingMetadataEnd
0x18000abc1  mov     [rsp+140h+Buf1], rcx
0x18000abc6  lea     rcx, _TraceLoggingMetadata
0x18000abcd  sub     eax, ecx
0x18000abcf  mov     dword ptr [rsp+140h+var_E0.0Ch], r15d
0x18000abd4  mov     [rsp+140h+var_C4], 1
0x18000abdc  mov     [rsp+140h+var_110], eax
0x18000abe0  mov     eax, [rsp+140h+var_110]
0x18000abe4  lea     rax, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x18000abeb  cmp     cs:qword_180026080, rax
0x18000abf2  jnz     loc_18000B0BA
0x18000abf8  mov     rax, [rsp+140h+Buf1]
0x18000abfd  mov     r9d, [rsp+140h+var_C8]
0x18000ac02  mov     [rsp+140h+arg_10], r12
0x18000ac0a  xor     r12b, r12b
0x18000ac0d  add     r9, rax
0x18000ac10  lea     rcx, [rax+2]
0x18000ac14  movzx   eax, byte ptr [rcx]
0x18000ac17  inc     rcx
0x18000ac1a  test    al, al
0x18000ac1c  js      short loc_18000AC14
0x18000ac1e  xchg    ax, ax
0x18000ac20  movzx   eax, byte ptr [rcx]
0x18000ac23  inc     rcx
0x18000ac26  test    al, al
0x18000ac28  jnz     short loc_18000AC20
0x18000ac2a  nop     word ptr [rax+rax+00h]
0x18000ac30  cmp     rcx, r9
0x18000ac33  jnb     short loc_18000AC88
0x18000ac35  movzx   eax, byte ptr [rcx]
0x18000ac38  inc     rcx
0x18000ac3b  test    al, al
0x18000ac3d  jnz     short loc_18000AC35
0x18000ac3f  movzx   edx, byte ptr [rcx]
0x18000ac42  test    dl, dl
0x18000ac44  jns     short loc_18000AC88
0x18000ac46  lea     rax, [rcx+1]
0x18000ac4a  and     dl, 7Fh
0x18000ac4d  add     rcx, r15
0x18000ac50  cmp     [rax], sil
0x18000ac53  jge     short loc_18000AC88
0x18000ac55  movzx   r8d, byte ptr [rcx]
0x18000ac59  test    r8b, r8b
0x18000ac5c  jns     short loc_18000AC69
0x18000ac5e  cmp     r8b, 80h
0x18000ac62  jnz     short loc_18000AC88
0x18000ac64  inc     rcx
0x18000ac67  jmp     short loc_18000AC55
0x18000ac69  cmp     dl, 9
0x18000ac6c  jnz     short loc_18000AC88
0x18000ac6e  lea     eax, [r8-71h]
0x18000ac72  cmp     al, r15b
0x18000ac75  ja      short loc_18000AC88
0x18000ac77  movzx   eax, r12b
0x18000ac7b  add     rax, rax
0x18000ac7e  inc     r12b
0x18000ac81  mov     byte ptr [rbp+rax*8+40h+var_B8+5], r8b
0x18000ac86  jmp     short loc_18000AC30
0x18000ac88  test    r12b, r12b
0x18000ac8b  jz      loc_18000AF6D
0x18000ac91  mov     [rsp+140h+arg_0], rbx
0x18000ac99  mov     rax, rsi
0x18000ac9c  mov     [rsp+140h+arg_8], rdi
0x18000aca4  mov     [rsp+140h+var_18], r13
0x18000acac  mov     r13, cs:qword_180026088
0x18000acb3  mov     [rsp+140h+var_20], r14
0x18000acbb  mov     [rsp+140h+var_108], rax
0x18000acc0  mov     [rsp+140h+var_100], rax
0x18000acc5  mov     [rsp+140h+var_110], esi
0x18000acc9  lfence
0x18000accc  movzx   eax, byte ptr [rsp+140h+Buf1]
0x18000acd1  lea     r15d, [r12+2]
0x18000acd6  imul    ecx, eax, 401h
0x18000acdc  movzx   r11d, r15b
0x18000ace0  movzx   eax, byte ptr [rsp+140h+Buf1+1]
0x18000ace5  mov     [rsp+140h+var_10C], r15b
0x18000acea  mov     edx, ecx
0x18000acec  shr     edx, 6
0x18000acef  xor     edx, ecx
0x18000acf1  add     edx, eax
0x18000acf3  imul    eax, edx, 401h
0x18000acf9  mov     ecx, eax
0x18000acfb  shr     ecx, 6
0x18000acfe  xor     ecx, eax
0x18000ad00  movzx   eax, byte ptr [rsp+140h+Buf1+2]
0x18000ad05  add     ecx, eax
0x18000ad07  imul    eax, ecx, 401h
0x18000ad0d  mov     ecx, eax
0x18000ad0f  shr     ecx, 6
0x18000ad12  xor     ecx, eax
0x18000ad14  movzx   eax, byte ptr [rsp+140h+Buf1+3]
0x18000ad19  add     ecx, eax
0x18000ad1b  imul    eax, ecx, 401h
0x18000ad21  mov     ecx, eax
0x18000ad23  shr     ecx, 6
0x18000ad26  xor     ecx, eax
0x18000ad28  movzx   eax, byte ptr [rsp+140h+Buf1+4]
0x18000ad2d  add     ecx, eax
0x18000ad2f  imul    eax, ecx, 401h
0x18000ad35  mov     ecx, eax
0x18000ad37  shr     ecx, 6
0x18000ad3a  xor     ecx, eax
0x18000ad3c  movzx   eax, byte ptr [rsp+140h+Buf1+5]
0x18000ad41  add     ecx, eax
0x18000ad43  imul    eax, ecx, 401h
0x18000ad49  mov     ecx, eax
0x18000ad4b  shr     ecx, 6
0x18000ad4e  xor     ecx, eax
0x18000ad50  movzx   eax, byte ptr [rsp+140h+Buf1+6]
0x18000ad55  add     ecx, eax
0x18000ad57  imul    eax, ecx, 401h
0x18000ad5d  mov     ecx, eax
0x18000ad5f  shr     ecx, 6
0x18000ad62  xor     ecx, eax
0x18000ad64  movzx   eax, byte ptr [rsp+140h+Buf1+7]
0x18000ad69  add     ecx, eax
0x18000ad6b  imul    ecx, 401h
0x18000ad71  mov     eax, ecx
0x18000ad73  shr     eax, 6
0x18000ad76  xor     eax, ecx
0x18000ad78  cmp     r15b, 0Bh
0x18000ad7c  jnb     short loc_18000ADC5
0x18000ad7e  xchg    ax, ax
0x18000ad80  movzx   ecx, r11b
0x18000ad84  mov     r8, rsi
0x18000ad87  add     rcx, rcx
0x18000ad8a  mov     r9d, [rsp+rcx*8+140h+var_E0.Size]
0x18000ad8f  mov     r10, [rsp+rcx*8+140h+var_E0.Ptr]
0x18000ad94  test    r9, r9
0x18000ad97  jz      short loc_18000ADBC
0x18000ad99  nop     dword ptr [rax+00000000h]
0x18000ada0  movzx   ecx, byte ptr [r10+r8]
0x18000ada5  inc     r8
0x18000ada8  add     ecx, eax
0x18000adaa  imul    edx, ecx, 401h
0x18000adb0  mov     eax, edx
0x18000adb2  shr     eax, 6
0x18000adb5  xor     eax, edx
0x18000adb7  cmp     r8, r9
0x18000adba  jb      short loc_18000ADA0
0x18000adbc  inc     r11b
0x18000adbf  cmp     r11b, 0Bh
0x18000adc3  jb      short loc_18000AD80
0x18000adc5  lea     ecx, [rax+rax*8]
0x18000adc8  mov     eax, ecx
0x18000adca  shr     eax, 0Bh
0x18000adcd  xor     eax, ecx
0x18000adcf  lea     rcx, [r13+108h]; SRWLock
0x18000add6  imul    r14d, eax, 8001h
0x18000addd  call    cs:__imp_AcquireSRWLockShared
0x18000ade3  mov     eax, r14d
0x18000ade6  and     eax, 1Fh
0x18000ade9  lea     rbx, ds:0[rax*8]
0x18000adf1  add     rbx, r13
0x18000adf4  cmp     qword ptr [rbx], 0
0x18000adf8  jz      loc_18000AEDC
0x18000adfe  mov     rsi, [rbx]
0x18000ae01  mov     ecx, [rsi+28h]
0x18000ae04  cmp     r14d, ecx
0x18000ae07  jnz     short loc_18000AE68
0x18000ae09  mov     r15, [rsi+10h]
0x18000ae0d  lea     rcx, [rsp+140h+Buf1]; Buf1
0x18000ae12  mov     r8d, 8; Size
0x18000ae18  lea     rdx, [r15+10h]; Buf2
0x18000ae1c  call    memcmp_0
0x18000ae21  test    eax, eax
0x18000ae23  jnz     loc_18000AF56
0x18000ae29  movzx   ebx, byte ptr [rsi+2Dh]
0x18000ae2d  add     ebx, 2
0x18000ae30  cmp     ebx, 0Bh
0x18000ae33  jnb     loc_18000B04D
0x18000ae39  mov     ecx, ebx
0x18000ae3b  shl     rcx, 4
0x18000ae3f  mov     r8d, [rsp+rcx+140h+var_E0.Size]; Size
0x18000ae44  mov     eax, r8d
0x18000ae47  sub     eax, [r15+rcx+8]
0x18000ae4c  jnz     short loc_18000AE6D
0x18000ae4e  mov     rdx, [r15+rcx]; Buf2
0x18000ae52  mov     rcx, [rsp+rcx+140h+var_E0.Ptr]; Buf1
0x18000ae57  call    memcmp_0
0x18000ae5c  test    eax, eax
0x18000ae5e  jnz     loc_18000AF56
0x18000ae64  inc     ebx
0x18000ae66  jmp     short loc_18000AE30
0x18000ae68  mov     eax, r14d
0x18000ae6b  sub     eax, ecx
0x18000ae6d  test    eax, eax
0x18000ae6f  jnz     loc_18000AF56
0x18000ae75  test    rsi, rsi
0x18000ae78  jz      short loc_18000AED6
0x18000ae7a  movzx   r11d, [rsp+140h+var_10C]
0x18000ae80  mov     dl, 2
0x18000ae82  cmp     r11b, dl
0x18000ae85  jbe     short loc_18000AED6
0x18000ae87  mov     r15d, 2
0x18000ae8d  nop     dword ptr [rax]
0x18000ae90  mov     rcx, r15
0x18000ae93  add     rcx, rcx
0x18000ae96  mov     rax, [rsp+rcx*8+140h+var_E0.Ptr]
0x18000ae9b  mov     r10, [rax]
0x18000ae9e  mov     rax, [rsi+10h]
0x18000aea2  movzx   r8d, byte ptr [rax+rcx*8+0Dh]
0x18000aea8  mov     r9, [rax+rcx*8]
0x18000aeac  cmp     r8b, 73h ; 's'
0x18000aeb0  jnz     loc_18000B075
0x18000aeb6  mov     rax, [r9]
0x18000aeb9  cmp     r8b, 72h ; 'r'
0x18000aebd  jnz     loc_18000B094
0x18000aec3  cmp     r10, rax
0x18000aec6  jl      loc_18000B09D
0x18000aecc  inc     dl
0x18000aece  inc     r15
0x18000aed1  cmp     dl, r11b
0x18000aed4  jb      short loc_18000AE90
0x18000aed6  mov     ebx, [rsp+140h+var_110]
0x18000aeda  jmp     short loc_18000AEF9
0x18000aedc  cmp     dword ptr [r13+100h], 400h
0x18000aee7  jb      loc_18000AF98
0x18000aeed  inc     dword ptr [r13+12Ch]
0x18000aef4  mov     ebx, 0EAh
0x18000aef9  lea     rcx, [r13+108h]; SRWLock
0x18000af00  call    cs:__imp_ReleaseSRWLockShared
0x18000af06  mov     rax, [rsp+140h+var_108]
0x18000af0b  mov     r14, [rsp+140h+var_20]
0x18000af13  mov     r13, [rsp+140h+var_18]
0x18000af1b  mov     rdi, [rsp+140h+arg_8]
0x18000af23  test    rax, rax
0x18000af26  jnz     loc_18000B0AD
0x18000af2c  mov     eax, ebx
0x18000af2e  mov     rbx, [rsp+140h+arg_0]
0x18000af36  mov     r12, [rsp+140h+arg_10]
0x18000af3e  mov     rcx, [rbp+40h+var_30]
0x18000af42  xor     rcx, rsp; StackCookie
0x18000af45  call    __security_check_cookie
0x18000af4a  add     rsp, 130h
0x18000af51  pop     r15
0x18000af53  pop     rsi
0x18000af54  pop     rbp
0x18000af55  retn
0x18000af56  movsxd  rbx, eax
  ... truncated ...
```
