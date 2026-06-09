# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1800107b8`
- end: `0x180010e4e`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U?$_tlgWrapSz@G@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@2222222222222222222222AEBU?$_tlgWrapSz@G@@32@Z`
- size: `1686`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180038aa0`

## callees

- `0x1800107b8`
- `0x180011260`
- `0x18004d68c`
- `0x1800633e0`
- `0x1800a98c0`
- `0x1800aa588`
- `0x1800f3784`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180010c00`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180010c00`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180010ca7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180010ca7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180010de5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180010de5`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        __int64 a20,
        __int64 a21,
        __int64 a22,
        __int64 a23,
        __int64 a24,
        __int64 a25,
        __int64 a26,
        const OLECHAR **a27,
        const OLECHAR **a28,
        __int64 a29)
{
  __int64 v30; // rcx
  unsigned __int8 v32; // di
  const OLECHAR *v33; // r8
  __int64 v34; // rax
  int v35; // eax
  const OLECHAR *v36; // rdx
  int v37; // ecx
  unsigned __int16 *v38; // rax
  unsigned int v39; // r13d
  unsigned __int8 v40; // r12
  unsigned __int64 v41; // r9
  char *v42; // rcx
  char v43; // al
  char v46; // r8
  char *v47; // rax
  char v48; // dl
  __int64 v49; // rax
  __int64 v50; // rbx
  signed __int64 v51; // rsi
  unsigned int v52; // edx
  unsigned __int64 i; // r8
  int v54; // eax
  unsigned __int8 j; // r8
  unsigned __int64 k; // r9
  int v57; // eax
  unsigned int v58; // r14d
  __int64 v59; // rdx
  int v60; // r9d
  volatile signed __int64 *m; // r15
  volatile signed __int64 v62; // r15
  int v63; // eax
  unsigned int n; // r14d
  __int64 v66; // r11
  __int64 v67; // r11
  unsigned __int8 v68; // r10
  unsigned int NewEventEntry; // eax
  unsigned int v70; // eax
  unsigned int v71; // [rsp+34h] [rbp-CCh]
  signed __int64 v72; // [rsp+38h] [rbp-C8h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-C0h] BYREF
  PSRWLOCK SRWLock; // [rsp+50h] [rbp-B0h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int8 *Buf1; // [rsp+70h] [rbp-90h] BYREF
  int v77; // [rsp+78h] [rbp-88h]
  int v78; // [rsp+7Ch] [rbp-84h]
  __int64 v79; // [rsp+80h] [rbp-80h]
  _QWORD v80[46]; // [rsp+88h] [rbp-78h]
  int v81; // [rsp+1F8h] [rbp+F8h]
  int v82; // [rsp+1FCh] [rbp+FCh]
  const OLECHAR *v83; // [rsp+200h] [rbp+100h]
  int v84; // [rsp+208h] [rbp+108h]
  int v85; // [rsp+20Ch] [rbp+10Ch]
  __int64 v86; // [rsp+210h] [rbp+110h]
  __int64 v87; // [rsp+218h] [rbp+118h]

  v86 = a29;
  v30 = -1;
  v87 = 8;
  v32 = 2;
  v33 = *a28;
  if ( *a28 )
  {
    v34 = -1;
    do
      ++v34;
    while ( v33[v34] );
    v35 = 2 * v34 + 2;
  }
  else
  {
    v33 = &word_18016FF04;
    v35 = 2;
  }
  v84 = v35;
  v83 = v33;
  v85 = 0;
  v36 = *a27;
  if ( *a27 )
  {
    do
      ++v30;
    while ( v36[v30] );
    v37 = 2 * v30 + 2;
  }
  else
  {
    v36 = &word_18016FF04;
    v37 = 2;
  }
  v80[43] = a26;
  v80[41] = a25;
  v80[39] = a24;
  v80[37] = a23;
  v80[35] = a22;
  v80[33] = a21;
  v80[31] = a20;
  v80[29] = a19;
  v80[27] = a18;
  v80[25] = a17;
  v80[23] = a16;
  v80[21] = a15;
  v80[19] = a14;
  v80[17] = a13;
  v80[15] = a12;
  v80[13] = a11;
  v80[11] = a10;
  v80[9] = a9;
  v80[7] = a8;
  v80[5] = a7;
  v80[3] = a6;
  v80[1] = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  v38 = *(unsigned __int16 **)(a1 + 8);
  v81 = v37;
  UserData.Ptr = (ULONGLONG)v38;
  v80[45] = v36;
  v82 = 0;
  v80[44] = 8;
  v80[42] = 8;
  v80[40] = 8;
  v80[38] = 8;
  v80[36] = 8;
  v80[34] = 8;
  v80[32] = 8;
  v80[30] = 8;
  v80[28] = 8;
  v80[26] = 8;
  v80[24] = 8;
  v80[22] = 8;
  v80[20] = 8;
  v80[18] = 8;
  v80[16] = 8;
  v80[14] = 8;
  v80[12] = 8;
  v80[10] = 8;
  v80[8] = 8;
  v80[6] = 8;
  v80[4] = 8;
  v80[2] = 8;
  v79 = a4;
  v80[0] = 8;
  UserData.Size = *v38;
  v39 = -1073741811;
  v77 = *(unsigned __int16 *)(a2 + 11);
  Buf1 = a2 + 11;
  UserData.Reserved = 2;
  v78 = 1;
  if ( *(void (__fastcall **)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))(a1 + 40) != TlgAggregateInternalRegisteredProviderEtwCallback )
    return v39;
  v40 = 0;
  v41 = (unsigned __int64)&Buf1[v77];
  v42 = (char *)(Buf1 + 2);
  do
    v43 = *v42++;
  while ( v43 < 0 );
  while ( *v42++ )
    ;
  while ( (unsigned __int64)v42 < v41 )
  {
    while ( *v42++ )
      ;
    if ( *v42 >= 0 )
      break;
    v46 = *v42 & 0x7F;
    v47 = v42 + 1;
    v42 += 2;
    if ( *v47 >= 0 )
      break;
    while ( 1 )
    {
      v48 = *v42;
      if ( *v42 >= 0 )
        break;
      if ( v48 != (char)0x80 )
        goto LABEL_22;
      ++v42;
    }
    if ( v46 != 9 || (unsigned __int8)(v48 - 113) > 2u )
      break;
    v49 = 2LL * v40++;
    BYTE5(v80[v49]) = v48;
  }
LABEL_22:
  if ( !v40 )
    return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, 0x1Cu, &UserData);
  v50 = *(_QWORD *)(a1 + 48);
  v51 = 0;
  v72 = 0;
  v39 = 0;
  v52 = 0;
  for ( i = 0; i < 8; ++i )
  {
    v54 = *((unsigned __int8 *)&Buf1 + i);
    v52 = (1025 * (v52 + v54)) ^ ((1025 * (v52 + v54)) >> 6);
  }
  for ( j = v40 + 2; j < 0x1Cu; ++j )
  {
    for ( k = 0; k < *(&UserData.Size + 4 * j); v52 = (1025 * (v52 + v57)) ^ ((1025 * (v52 + v57)) >> 6) )
    {
      v57 = *(unsigned __int8 *)(k + *(&UserData.Ptr + 2 * j));
      ++k;
    }
  }
  v58 = 32769 * ((9 * v52) ^ ((9 * v52) >> 11));
  SRWLock = (PSRWLOCK)(v50 + 264);
  v71 = v58;
  AcquireSRWLockShared((PSRWLOCK)(v50 + 264));
  for ( m = (volatile signed __int64 *)(v50 + 8LL * (v58 & 0x1F));
        ;
        m = (volatile signed __int64 *)((((__int64)v63 >> 63) & 0xFFFFFFFFFFFFFFF8uLL) + v62 + 32) )
  {
    if ( !*m )
    {
      if ( *(_DWORD *)(v50 + 256) >= 0x400u )
      {
        ++*(_DWORD *)(v50 + 300);
        v39 = 234;
        goto LABEL_40;
      }
      if ( !v51 )
      {
        LOBYTE(v60) = v40;
        LOBYTE(v59) = 28;
        NewEventEntry = CreateNewEventEntry(
                          (unsigned int)&EventDescriptor,
                          v59,
                          (unsigned int)&UserData,
                          v60,
                          v58,
                          (__int64)&v72);
        v51 = v72;
        v39 = NewEventEntry;
        if ( !v72 )
        {
          if ( NewEventEntry == 8 )
            ++*(_DWORD *)(v50 + 304);
          else
            ++*(_DWORD *)(v50 + 308);
          goto LABEL_40;
        }
      }
      if ( !_InterlockedCompareExchange64(m, v51, 0) )
        break;
    }
    v62 = *m;
    if ( v58 == *(_DWORD *)(v62 + 40) )
    {
      v63 = memcmp_0(&Buf1, (const void *)(*(_QWORD *)(v62 + 16) + 16LL), 8u);
      if ( v63 )
        continue;
      for ( n = *(unsigned __int8 *)(v62 + 45) + 2; n < 0x1C; ++n )
      {
        v59 = *(_QWORD *)(v62 + 16);
        v63 = *(&UserData.Size + 4 * n) - *(_DWORD *)(16LL * n + v59 + 8);
        if ( v63 )
          goto LABEL_44;
        v63 = memcmp_0(
                *((const void **)&UserData.Ptr + 2 * n),
                *(const void **)(16LL * n + v59),
                *(&UserData.Size + 4 * n));
        if ( v63 )
          goto LABEL_44;
      }
      v63 = 0;
LABEL_44:
      v58 = v71;
    }
    else
    {
      v63 = v58 - *(_DWORD *)(v62 + 40);
    }
    if ( !v63 )
    {
      if ( v62 && (unsigned __int8)(v40 + 2) > 2u )
      {
        v66 = 2;
        do
        {
          AggregateField(
            *(_QWORD *)(*(_QWORD *)(v62 + 16) + 16 * v66),
            **((_QWORD **)&UserData.Ptr + 2 * v66),
            *(unsigned __int8 *)(*(_QWORD *)(v62 + 16) + 16 * v66 + 13));
          ++v32;
          v66 = v67 + 1;
        }
        while ( v32 < v68 );
      }
      goto LABEL_40;
    }
  }
  v51 = 0;
  if ( _InterlockedIncrement((volatile signed __int32 *)(v50 + 256)) == 1 )
    EnableFlushTimer(*(_QWORD *)(v50 + 344), *(unsigned int *)(v50 + 352));
  v70 = *(_DWORD *)(v50 + 256);
  if ( *(_DWORD *)(v50 + 288) < v70 )
    *(_DWORD *)(v50 + 288) = v70;
LABEL_40:
  ReleaseSRWLockShared(SRWLock);
  if ( v51 )
    DestroyEventEntry(v51);
  return v39;
}

```

## disassembly

```asm
0x1800107b8  push    rbp
0x1800107ba  push    rbx
0x1800107bb  push    rsi
0x1800107bc  push    rdi
0x1800107bd  push    r12
0x1800107bf  push    r13
0x1800107c1  push    r14
0x1800107c3  push    r15
0x1800107c5  lea     rbp, [rsp-138h]
0x1800107cd  sub     rsp, 238h
0x1800107d4  mov     rax, cs:__security_cookie
0x1800107db  xor     rax, rsp
0x1800107de  mov     [rbp+170h+var_50], rax
0x1800107e5  mov     rax, [rbp+170h+arg_E0]
0x1800107ec  xor     r14d, r14d
0x1800107ef  mov     [rbp+170h+var_60], rax
0x1800107f6  mov     r10, rcx
0x1800107f9  mov     rax, [rbp+170h+arg_D8]
0x180010800  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180010804  mov     r11, rdx
0x180010807  mov     [rbp+170h+var_58], 8
0x180010812  lea     edi, [r14+2]
0x180010816  mov     r8, [rax]
0x180010819  test    r8, r8
0x18001081c  jz      loc_180010DF3
0x180010822  mov     rax, rcx
0x180010825  inc     rax
0x180010828  cmp     [r8+rax*2], r14w
0x18001082d  jnz     short loc_180010825
0x18001082f  lea     eax, ds:2[rax*2]
0x180010836  mov     [rbp+170h+var_68], eax
0x18001083c  mov     rax, [rbp+170h+arg_D0]
0x180010843  mov     [rbp+170h+var_70], r8
0x18001084a  mov     [rbp+170h+var_64], r14d
0x180010851  mov     rdx, [rax]
0x180010854  test    rdx, rdx
0x180010857  jz      loc_180010E01
0x18001085d  inc     rcx
0x180010860  cmp     [rdx+rcx*2], r14w
0x180010865  jnz     short loc_18001085D
0x180010867  lea     ecx, ds:2[rcx*2]
0x18001086e  mov     rax, [rbp+170h+arg_C8]
0x180010875  mov     [rbp+170h+var_90], rax
0x18001087c  mov     rax, [rbp+170h+arg_C0]
0x180010883  mov     [rbp+170h+var_A0], rax
0x18001088a  mov     rax, [rbp+170h+arg_B8]
0x180010891  mov     [rbp+170h+var_B0], rax
0x180010898  mov     rax, [rbp+170h+arg_B0]
0x18001089f  mov     [rbp+170h+var_C0], rax
0x1800108a6  mov     rax, [rbp+170h+arg_A8]
0x1800108ad  mov     [rbp+170h+var_D0], rax
0x1800108b4  mov     rax, [rbp+170h+arg_A0]
0x1800108bb  mov     [rbp+170h+var_E0], rax
0x1800108c2  mov     rax, [rbp+170h+arg_98]
0x1800108c9  mov     [rbp+170h+var_F0], rax
0x1800108d0  mov     rax, [rbp+170h+arg_90]
0x1800108d7  mov     [rbp+170h+var_100], rax
0x1800108db  mov     rax, [rbp+170h+arg_88]
0x1800108e2  mov     [rbp+170h+var_110], rax
0x1800108e6  mov     rax, [rbp+170h+arg_80]
0x1800108ed  mov     [rbp+170h+var_120], rax
0x1800108f1  mov     rax, [rbp+170h+arg_78]
0x1800108f8  mov     [rbp+170h+var_130], rax
0x1800108fc  mov     rax, [rbp+170h+arg_70]
0x180010903  mov     [rbp+170h+var_140], rax
0x180010907  mov     rax, [rbp+170h+arg_68]
0x18001090e  mov     [rbp+170h+var_150], rax
0x180010912  mov     rax, [rbp+170h+arg_60]
0x180010919  mov     [rbp+170h+var_160], rax
0x18001091d  mov     rax, [rbp+170h+arg_58]
0x180010924  mov     [rbp+170h+var_170], rax
0x180010928  mov     rax, [rbp+170h+arg_50]
0x18001092f  mov     [rbp+170h+var_180], rax
0x180010933  mov     rax, [rbp+170h+arg_48]
0x18001093a  mov     [rbp+170h+var_190], rax
0x18001093e  mov     rax, [rbp+170h+arg_40]
0x180010945  mov     [rbp+170h+var_1A0], rax
0x180010949  mov     rax, [rbp+170h+arg_38]
0x180010950  mov     [rbp+170h+var_1B0], rax
0x180010954  mov     rax, [rbp+170h+arg_30]
0x18001095b  mov     [rbp+170h+var_1C0], rax
0x18001095f  mov     rax, [rbp+170h+arg_28]
0x180010966  mov     [rbp+170h+var_1D0], rax
0x18001096a  mov     rax, [rbp+170h+arg_20]
0x180010971  mov     [rbp+170h+var_1E0], rax
0x180010975  movzx   eax, byte ptr [r11]
0x180010979  shl     eax, 18h
0x18001097c  mov     dword ptr [rsp+270h+EventDescriptor.Id], eax
0x180010980  movzx   eax, word ptr [r11+1]
0x180010985  mov     dword ptr [rsp+270h+EventDescriptor.Level], eax
0x180010989  mov     rax, [r11+3]
0x18001098d  mov     [rsp+270h+EventDescriptor.Keyword], rax
0x180010992  mov     rax, [r10+8]
0x180010996  mov     [rbp+170h+var_78], ecx
0x18001099c  lea     rcx, [r11+0Bh]
0x1800109a0  mov     [rsp+270h+var_210.Ptr], rax
0x1800109a5  mov     [rbp+170h+var_80], rdx
0x1800109ac  mov     [rbp+170h+var_74], r14d
0x1800109b3  mov     [rbp+170h+var_88], 8
0x1800109be  mov     [rbp+170h+var_98], 8
0x1800109c9  mov     [rbp+170h+var_A8], 8
0x1800109d4  mov     [rbp+170h+var_B8], 8
0x1800109df  mov     [rbp+170h+var_C8], 8
0x1800109ea  mov     [rbp+170h+var_D8], 8
0x1800109f5  mov     [rbp+170h+var_E8], 8
0x180010a00  mov     [rbp+170h+var_F8], 8
0x180010a08  mov     [rbp+170h+var_108], 8
0x180010a10  mov     [rbp+170h+var_118], 8
0x180010a18  mov     [rbp+170h+var_128], 8
0x180010a20  mov     [rbp+170h+var_138], 8
0x180010a28  mov     [rbp+170h+var_148], 8
0x180010a30  mov     [rbp+170h+var_158], 8
0x180010a38  mov     [rbp+170h+var_168], 8
0x180010a40  mov     [rbp+170h+var_178], 8
0x180010a48  mov     [rbp+170h+var_188], 8
0x180010a50  mov     [rbp+170h+var_198], 8
0x180010a58  mov     [rbp+170h+var_1A8], 8
0x180010a60  mov     [rbp+170h+var_1B8], 8
0x180010a68  mov     [rbp+170h+var_1C8], 8
0x180010a70  mov     [rbp+170h+var_1D8], 8
0x180010a78  mov     [rbp+170h+var_1F0], r9
0x180010a7c  mov     [rbp+170h+var_1E8], 8
0x180010a84  movzx   eax, word ptr [rax]
0x180010a87  mov     r15d, 1
0x180010a8d  mov     [rsp+270h+var_210.Size], eax
0x180010a91  mov     r13d, 0C000000Dh
0x180010a97  movzx   eax, word ptr [rcx]
0x180010a9a  mov     [rsp+270h+var_1F8], eax
0x180010a9e  lea     rax, _TraceLoggingMetadataEnd
0x180010aa5  mov     [rsp+270h+Buf1], rcx
0x180010aaa  lea     rcx, _TraceLoggingMetadata
0x180010ab1  sub     eax, ecx
0x180010ab3  mov     dword ptr [rsp+270h+var_210.0Ch], edi
0x180010ab7  mov     [rsp+270h+var_1F4], r15d
0x180010abc  mov     [rsp+270h+var_23C], eax
0x180010ac0  mov     eax, [rsp+270h+var_23C]
0x180010ac4  lea     rax, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x180010acb  cmp     [r10+28h], rax
0x180010acf  jnz     loc_180010CB6
0x180010ad5  mov     rax, [rsp+270h+Buf1]
0x180010ada  mov     r12b, r14b
0x180010add  mov     r9d, [rsp+270h+var_1F8]
0x180010ae2  add     r9, rax
0x180010ae5  lea     rcx, [rax+2]
0x180010ae9  movzx   eax, byte ptr [rcx]
0x180010aec  add     rcx, r15
0x180010aef  test    al, al
0x180010af1  js      short loc_180010AE9
0x180010af3  mov     al, [rcx]
0x180010af5  add     rcx, r15
0x180010af8  test    al, al
0x180010afa  jnz     short loc_180010AF3
0x180010afc  cmp     rcx, r9
0x180010aff  jnb     short loc_180010B52
0x180010b01  mov     al, [rcx]
0x180010b03  add     rcx, r15
0x180010b06  test    al, al
0x180010b08  jnz     short loc_180010B01
0x180010b0a  mov     r8b, [rcx]
0x180010b0d  test    r8b, r8b
0x180010b10  jns     short loc_180010B52
0x180010b12  add     rcx, r15
0x180010b15  and     r8b, 7Fh
0x180010b19  mov     rax, rcx
0x180010b1c  inc     rcx
0x180010b1f  cmp     [rax], r14b
0x180010b22  jge     short loc_180010B52
0x180010b24  mov     dl, [rcx]
0x180010b26  test    dl, dl
0x180010b28  jns     short loc_180010B34
0x180010b2a  cmp     dl, 80h
0x180010b2d  jnz     short loc_180010B52
0x180010b2f  add     rcx, r15
0x180010b32  jmp     short loc_180010B24
0x180010b34  cmp     r8b, 9
0x180010b38  jnz     short loc_180010B52
0x180010b3a  lea     eax, [rdx-71h]
0x180010b3d  cmp     al, dil
0x180010b40  ja      short loc_180010B52
0x180010b42  movzx   eax, r12b
0x180010b46  add     rax, rax
0x180010b49  add     r12b, r15b
0x180010b4c  mov     byte ptr [rbp+rax*8+170h+var_1E8+5], dl
0x180010b50  jmp     short loc_180010AFC
0x180010b52  test    r12b, r12b
0x180010b55  jz      loc_180010DC4
0x180010b5b  mov     rbx, [r10+30h]
0x180010b5f  mov     rsi, r14
0x180010b62  mov     [rsp+270h+var_238], r14
0x180010b67  mov     r13d, r14d
0x180010b6a  mov     edx, r14d
0x180010b6d  mov     r8, r14
0x180010b70  movzx   eax, byte ptr [rsp+r8+270h+Buf1]
0x180010b76  add     r8, r15
0x180010b79  add     eax, edx
0x180010b7b  imul    ecx, eax, 401h
0x180010b81  mov     edx, ecx
0x180010b83  shr     edx, 6
0x180010b86  xor     edx, ecx
0x180010b88  cmp     r8, 8
0x180010b8c  jb      short loc_180010B70
0x180010b8e  lea     eax, [rdi+r12]
0x180010b92  mov     [rsp+270h+var_240], al
0x180010b96  mov     r8b, al
0x180010b99  cmp     al, 1Ch
0x180010b9b  jnb     short loc_180010BDB
0x180010b9d  movzx   eax, r8b
0x180010ba1  mov     r9, r14
0x180010ba4  add     rax, rax
0x180010ba7  mov     r10d, [rsp+rax*8+270h+var_210.Size]
0x180010bac  mov     r11, [rsp+rax*8+270h+var_210.Ptr]
0x180010bb1  test    r10, r10
0x180010bb4  jz      short loc_180010BD2
0x180010bb6  movzx   eax, byte ptr [r9+r11]
0x180010bbb  add     r9, r15
0x180010bbe  add     eax, edx
0x180010bc0  imul    ecx, eax, 401h
0x180010bc6  mov     edx, ecx
0x180010bc8  shr     edx, 6
0x180010bcb  xor     edx, ecx
0x180010bcd  cmp     r9, r10
0x180010bd0  jb      short loc_180010BB6
0x180010bd2  add     r8b, r15b
0x180010bd5  cmp     r8b, 1Ch
0x180010bd9  jb      short loc_180010B9D
0x180010bdb  lea     eax, [rdx+rdx*8]
0x180010bde  mov     ecx, eax
0x180010be0  shr     ecx, 0Bh
0x180010be3  xor     ecx, eax
0x180010be5  lea     rax, [rbx+108h]
0x180010bec  imul    r14d, ecx, 8001h
0x180010bf3  mov     rcx, rax; SRWLock
0x180010bf6  mov     [rsp+270h+SRWLock], rax
0x180010bfb  mov     [rsp+270h+var_23C], r14d
0x180010c00  call    cs:__imp_AcquireSRWLockShared
0x180010c06  mov     eax, r14d
0x180010c09  and     eax, 1Fh
0x180010c0c  lea     r15, [rbx+rax*8]
0x180010c10  cmp     qword ptr [r15], 0
0x180010c14  jz      short loc_180010C86
0x180010c16  mov     r15, [r15]
0x180010c19  cmp     r14d, [r15+28h]
0x180010c1d  jnz     loc_180010D40
0x180010c23  mov     rdx, [r15+10h]
0x180010c27  lea     rcx, [rsp+270h+Buf1]; Buf1
0x180010c2c  add     rdx, 10h; Buf2
0x180010c30  mov     r8d, 8; Size
0x180010c36  call    memcmp_0
0x180010c3b  test    eax, eax
0x180010c3d  jnz     loc_180010D2A
0x180010c43  movzx   r14d, byte ptr [r15+2Dh]
0x180010c48  add     r14d, edi
0x180010c4b  cmp     r14d, 1Ch
0x180010c4f  jnb     loc_180010CDC
0x180010c55  mov     rdx, [r15+10h]
0x180010c59  mov     ecx, r14d
0x180010c5c  shl     rcx, 4
0x180010c60  mov     eax, [rsp+rcx+270h+var_210.Size]
0x180010c64  sub     eax, [rcx+rdx+8]
0x180010c68  jnz     short loc_180010CDE
0x180010c6a  mov     r8d, [rsp+rcx+270h+var_210.Size]; Size
0x180010c6f  mov     rdx, [rcx+rdx]; Buf2
0x180010c73  mov     rcx, [rsp+rcx+270h+var_210.Ptr]; Buf1
0x180010c78  call    memcmp_0
0x180010c7d  test    eax, eax
0x180010c7f  jnz     short loc_180010CDE
0x180010c81  inc     r14d
0x180010c84  jmp     short loc_180010C4B
0x180010c86  cmp     dword ptr [rbx+100h], 400h
0x180010c90  jb      loc_180010D49
0x180010c96  inc     dword ptr [rbx+12Ch]
0x180010c9c  mov     r13d, 0EAh
0x180010ca2  mov     rcx, [rsp+270h+SRWLock]; SRWLock
0x180010ca7  call    cs:__imp_ReleaseSRWLockShared
0x180010cad  test    rsi, rsi
0x180010cb0  jnz     loc_180010E41
0x180010cb6  mov     eax, r13d
0x180010cb9  mov     rcx, [rbp+170h+var_50]
0x180010cc0  xor     rcx, rsp; StackCookie
0x180010cc3  call    __security_check_cookie
0x180010cc8  add     rsp, 238h
0x180010ccf  pop     r15
0x180010cd1  pop     r14
0x180010cd3  pop     r13
0x180010cd5  pop     r12
0x180010cd7  pop     rdi
0x180010cd8  pop     rsi
0x180010cd9  pop     rbx
0x180010cda  pop     rbp
0x180010cdb  retn
0x180010cdc  xor     eax, eax
0x180010cde  mov     r14d, [rsp+270h+var_23C]
0x180010ce3  test    eax, eax
0x180010ce5  jnz     short loc_180010D2A
0x180010ce7  test    r15, r15
0x180010cea  jz      short loc_180010CA2
0x180010cec  mov     r10b, [rsp+270h+var_240]
0x180010cf1  cmp     r10b, dil
0x180010cf4  jbe     short loc_180010CA2
0x180010cf6  mov     r11, rdi
  ... truncated ...
```
