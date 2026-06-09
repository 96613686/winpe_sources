# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180024880`
- end: `0x180024ca4`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@2@Z`
- size: `1060`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001f1fc`
- `0x18005db5c`
- `0x18005dc88`

## callees

- `0x180024880`
- `0x180025214`
- `0x18002526c`
- `0x18003c43c`
- `0x180084f50`
- `0x180085ba0`
- `0x1800b1e54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180024b15`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180024b15`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180024a58`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180024a58`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180024c6e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180024c6e`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  unsigned __int8 v6; // r13
  unsigned int v7; // r15d
  unsigned __int8 v8; // r12
  unsigned __int64 v9; // r9
  char *v10; // rcx
  char v11; // al
  char v14; // r8
  char *v15; // rax
  char v16; // dl
  __int64 v17; // rbx
  signed __int64 v18; // rdi
  unsigned int v19; // edx
  unsigned __int64 i; // r8
  int v21; // eax
  unsigned __int8 j; // r8
  unsigned __int64 k; // r9
  int v24; // eax
  __int64 v25; // rdx
  int v26; // r9d
  unsigned int v27; // ecx
  volatile signed __int64 *m; // rsi
  volatile signed __int64 v29; // r14
  int v30; // eax
  unsigned int n; // esi
  __int64 v32; // rax
  __int64 v34; // r10
  __int64 v35; // r10
  unsigned __int8 v36; // r11
  unsigned int v37; // eax
  unsigned int NewEventEntry; // eax
  unsigned int v39; // [rsp+34h] [rbp-85h]
  signed __int64 v40; // [rsp+38h] [rbp-81h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-79h] BYREF
  PSRWLOCK SRWLock; // [rsp+50h] [rbp-69h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-59h] BYREF
  unsigned __int8 *Buf1; // [rsp+70h] [rbp-49h] BYREF
  int v45; // [rsp+78h] [rbp-41h]
  int v46; // [rsp+7Ch] [rbp-3Dh]
  __int64 v47; // [rsp+80h] [rbp-39h]
  _QWORD v48[5]; // [rsp+88h] [rbp-31h]

  v48[3] = a6;
  v6 = 2;
  v7 = -1073741811;
  v48[1] = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_18013A128;
  v48[4] = 8;
  v48[2] = 4;
  v47 = a4;
  v48[0] = 8;
  UserData.Size = *(unsigned __int16 *)off_18013A128;
  v45 = *(unsigned __int16 *)(a2 + 11);
  Buf1 = a2 + 11;
  UserData.Reserved = 2;
  v46 = 1;
  if ( (void (__fastcall *)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))qword_18013A148 == TlgAggregateInternalRegisteredProviderEtwCallback )
  {
    v8 = 0;
    v9 = (unsigned __int64)&Buf1[v45];
    v10 = (char *)(Buf1 + 2);
    do
      v11 = *v10++;
    while ( v11 < 0 );
    while ( *v10++ )
      ;
    while ( (unsigned __int64)v10 < v9 )
    {
      while ( *v10++ )
        ;
      if ( *v10 >= 0 )
        break;
      v14 = *v10 & 0x7F;
      v15 = v10 + 1;
      v10 += 2;
      if ( *v15 >= 0 )
        break;
      while ( 1 )
      {
        v16 = *v10;
        if ( *v10 >= 0 )
          break;
        if ( v16 != (char)0x80 )
          goto LABEL_12;
        ++v10;
      }
      if ( v14 != 9 || (unsigned __int8)(v16 - 113) > 2u )
        break;
      v32 = 2LL * v8++;
      BYTE5(v48[v32]) = v16;
    }
LABEL_12:
    if ( v8 )
    {
      v17 = qword_18013A150;
      v18 = 0;
      v7 = 0;
      v40 = 0;
      v19 = 0;
      for ( i = 0; i < 8; ++i )
      {
        v21 = *((unsigned __int8 *)&Buf1 + i);
        v19 = (1025 * (v19 + v21)) ^ ((1025 * (v19 + v21)) >> 6);
      }
      for ( j = v8 + 2; j < 5u; ++j )
      {
        for ( k = 0; k < *(&UserData.Size + 4 * j); v19 = (1025 * (v19 + v24)) ^ ((1025 * (v19 + v24)) >> 6) )
          v24 = *(unsigned __int8 *)(*(&UserData.Ptr + 2 * j) + k++);
      }
      v39 = 32769 * ((9 * v19) ^ ((9 * v19) >> 11));
      SRWLock = (PSRWLOCK)(qword_18013A150 + 264);
      AcquireSRWLockShared((PSRWLOCK)(qword_18013A150 + 264));
      v27 = v39;
      for ( m = (volatile signed __int64 *)(v17 + 8LL * (v39 & 0x1F));
            ;
            m = (volatile signed __int64 *)(v29 + (((__int64)v30 >> 63) & 0xFFFFFFFFFFFFFFF8uLL) + 32) )
      {
        if ( !*m )
        {
          if ( *(_DWORD *)(v17 + 256) >= 0x400u )
          {
            ++*(_DWORD *)(v17 + 300);
            v7 = 234;
            goto LABEL_35;
          }
          if ( !v18 )
          {
            LOBYTE(v26) = v8;
            LOBYTE(v25) = 5;
            NewEventEntry = CreateNewEventEntry(
                              (unsigned int)&EventDescriptor,
                              v25,
                              (unsigned int)&UserData,
                              v26,
                              v27,
                              (__int64)&v40);
            v18 = v40;
            v7 = NewEventEntry;
            if ( !v40 )
            {
              if ( NewEventEntry == 8 )
                ++*(_DWORD *)(v17 + 304);
              else
                ++*(_DWORD *)(v17 + 308);
              goto LABEL_35;
            }
            v27 = v39;
          }
          if ( !_InterlockedCompareExchange64(m, v18, 0) )
            break;
        }
        v29 = *m;
        if ( v27 == *(_DWORD *)(*m + 40) )
        {
          v30 = memcmp_0(&Buf1, (const void *)(*(_QWORD *)(v29 + 16) + 16LL), 8u);
          if ( !v30 )
          {
            for ( n = *(unsigned __int8 *)(v29 + 45) + 2; n < 5; ++n )
            {
              v25 = *(_QWORD *)(v29 + 16);
              v30 = *(&UserData.Size + 4 * n) - *(_DWORD *)(v25 + 16LL * n + 8);
              if ( v30 )
                goto LABEL_32;
              v30 = memcmp_0(
                      *((const void **)&UserData.Ptr + 2 * n),
                      *(const void **)(v25 + 16LL * n),
                      *(&UserData.Size + 4 * n));
              if ( v30 )
                goto LABEL_32;
            }
            v30 = 0;
          }
LABEL_32:
          v27 = v39;
        }
        else
        {
          v30 = v27 - *(_DWORD *)(v29 + 40);
        }
        if ( !v30 )
        {
          if ( v29 && (unsigned __int8)(v8 + 2) > 2u )
          {
            v34 = 2;
            do
            {
              AggregateField(
                *(_QWORD *)(*(_QWORD *)(v29 + 16) + 16 * v34),
                **((_QWORD **)&UserData.Ptr + 2 * v34),
                *(unsigned __int8 *)(*(_QWORD *)(v29 + 16) + 16 * v34 + 13));
              ++v6;
              v34 = v35 + 1;
            }
            while ( v6 < v36 );
          }
          goto LABEL_35;
        }
      }
      v18 = 0;
      if ( _InterlockedIncrement((volatile signed __int32 *)(v17 + 256)) == 1 )
        EnableFlushTimer(*(_QWORD *)(v17 + 344), *(unsigned int *)(v17 + 352));
      v37 = *(_DWORD *)(v17 + 256);
      if ( *(_DWORD *)(v17 + 288) < v37 )
        *(_DWORD *)(v17 + 288) = v37;
LABEL_35:
      ReleaseSRWLockShared(SRWLock);
      if ( v18 )
        DestroyEventEntry(v18);
    }
    else
    {
      return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180024880  push    rbp
0x180024882  push    rbx
0x180024883  push    rsi
0x180024884  push    rdi
0x180024885  push    r12
0x180024887  push    r13
0x180024889  push    r14
0x18002488b  push    r15
0x18002488d  lea     rbp, [rsp-0Fh]
0x180024892  sub     rsp, 0C8h
0x180024899  mov     rax, cs:__security_cookie
0x1800248a0  xor     rax, rsp
0x1800248a3  mov     [rbp+47h+var_50], rax
0x1800248a7  mov     rax, [rbp+47h+arg_28]
0x1800248ab  lea     rcx, [rdx+0Bh]
0x1800248af  mov     [rbp+47h+var_60], rax
0x1800248b3  mov     r13d, 2
0x1800248b9  mov     rax, [rbp+47h+arg_20]
0x1800248bd  mov     r15d, 0C000000Dh
0x1800248c3  mov     [rbp+47h+var_70], rax
0x1800248c7  movzx   eax, byte ptr [rdx]
0x1800248ca  shl     eax, 18h
0x1800248cd  mov     dword ptr [rbp+47h+EventDescriptor.Id], eax
0x1800248d0  movzx   eax, word ptr [rdx+1]
0x1800248d4  mov     dword ptr [rbp+47h+EventDescriptor.Level], eax
0x1800248d7  mov     rax, [rdx+3]
0x1800248db  mov     [rbp+47h+EventDescriptor.Keyword], rax
0x1800248df  mov     rax, cs:off_18013A128
0x1800248e6  mov     [rbp+47h+var_A0.Ptr], rax
0x1800248ea  mov     [rbp+47h+var_58], 8
0x1800248f2  mov     [rbp+47h+var_68], 4
0x1800248fa  mov     [rbp+47h+var_80], r9
0x1800248fe  mov     [rbp+47h+var_78], 8
0x180024906  movzx   eax, word ptr [rax]
0x180024909  mov     [rbp+47h+var_A0.Size], eax
0x18002490c  movzx   eax, word ptr [rcx]
0x18002490f  mov     [rbp+47h+var_88], eax
0x180024912  lea     rax, _TraceLoggingMetadataEnd
0x180024919  mov     [rbp+47h+Buf1], rcx
0x18002491d  lea     rcx, _TraceLoggingMetadata
0x180024924  sub     eax, ecx
0x180024926  mov     dword ptr [rbp+47h+var_A0.0Ch], r13d
0x18002492a  mov     [rbp+47h+var_84], 1
0x180024931  mov     [rsp+100h+var_CC], eax
0x180024935  mov     eax, [rsp+100h+var_CC]
0x180024939  lea     rax, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x180024940  cmp     cs:qword_18013A148, rax
0x180024947  jnz     loc_180024B24
0x18002494d  mov     rax, [rbp+47h+Buf1]
0x180024951  xor     r12b, r12b
0x180024954  mov     r9d, [rbp+47h+var_88]
0x180024958  add     r9, rax
0x18002495b  lea     rcx, [rax+2]
0x18002495f  movzx   eax, byte ptr [rcx]
0x180024962  inc     rcx
0x180024965  test    al, al
0x180024967  js      short loc_18002495F
0x180024969  mov     al, [rcx]
0x18002496b  inc     rcx
0x18002496e  test    al, al
0x180024970  jnz     short loc_180024969
0x180024972  cmp     rcx, r9
0x180024975  jnb     short loc_1800249AC
0x180024977  mov     al, [rcx]
0x180024979  inc     rcx
0x18002497c  test    al, al
0x18002497e  jnz     short loc_180024977
0x180024980  mov     r8b, [rcx]
0x180024983  test    r8b, r8b
0x180024986  jns     short loc_1800249AC
0x180024988  and     r8b, 7Fh
0x18002498c  lea     rax, [rcx+1]
0x180024990  add     rcx, r13
0x180024993  cmp     byte ptr [rax], 0
0x180024996  jge     short loc_1800249AC
0x180024998  mov     dl, [rcx]
0x18002499a  test    dl, dl
0x18002499c  jns     loc_180024AD9
0x1800249a2  cmp     dl, 80h
0x1800249a5  jnz     short loc_1800249AC
0x1800249a7  inc     rcx
0x1800249aa  jmp     short loc_180024998
0x1800249ac  test    r12b, r12b
0x1800249af  jz      loc_180024C4C
0x1800249b5  mov     rbx, cs:qword_18013A150
0x1800249bc  xor     edi, edi
0x1800249be  xor     r15d, r15d
0x1800249c1  mov     [rsp+100h+var_C8], rdi
0x1800249c6  xor     edx, edx
0x1800249c8  xor     r8d, r8d
0x1800249cb  movzx   eax, byte ptr [rbp+r8+47h+Buf1]
0x1800249d1  inc     r8
0x1800249d4  add     eax, edx
0x1800249d6  imul    ecx, eax, 401h
0x1800249dc  mov     edx, ecx
0x1800249de  shr     edx, 6
0x1800249e1  xor     edx, ecx
0x1800249e3  cmp     r8, 8
0x1800249e7  jb      short loc_1800249CB
0x1800249e9  lea     eax, [r12+r13]
0x1800249ed  mov     [rsp+100h+var_D0], al
0x1800249f1  mov     r8b, al
0x1800249f4  cmp     al, 5
0x1800249f6  jnb     short loc_180024A36
0x1800249f8  movzx   eax, r8b
0x1800249fc  xor     r9d, r9d
0x1800249ff  add     rax, rax
0x180024a02  mov     r10d, [rbp+rax*8+47h+var_A0.Size]
0x180024a07  mov     r11, [rbp+rax*8+47h+var_A0.Ptr]
0x180024a0c  test    r10, r10
0x180024a0f  jz      short loc_180024A2D
0x180024a11  movzx   eax, byte ptr [r11+r9]
0x180024a16  inc     r9
0x180024a19  add     eax, edx
0x180024a1b  imul    ecx, eax, 401h
0x180024a21  mov     edx, ecx
0x180024a23  shr     edx, 6
0x180024a26  xor     edx, ecx
0x180024a28  cmp     r9, r10
0x180024a2b  jb      short loc_180024A11
0x180024a2d  inc     r8b
0x180024a30  cmp     r8b, 5
0x180024a34  jb      short loc_1800249F8
0x180024a36  lea     eax, [rdx+rdx*8]
0x180024a39  mov     ecx, eax
0x180024a3b  shr     ecx, 0Bh
0x180024a3e  xor     ecx, eax
0x180024a40  imul    eax, ecx, 8001h
0x180024a46  mov     [rsp+100h+var_CC], eax
0x180024a4a  lea     rax, [rbx+108h]
0x180024a51  mov     rcx, rax; SRWLock
0x180024a54  mov     [rbp+47h+SRWLock], rax
0x180024a58  call    cs:__imp_AcquireSRWLockShared
0x180024a5e  mov     ecx, [rsp+100h+var_CC]
0x180024a62  mov     eax, ecx
0x180024a64  and     eax, 1Fh
0x180024a67  lea     rsi, [rbx+rax*8]
0x180024a6b  cmp     qword ptr [rsi], 0
0x180024a6f  jz      loc_180024B47
0x180024a75  mov     r14, [rsi]
0x180024a78  cmp     ecx, [r14+28h]
0x180024a7c  jnz     loc_180024BB6
0x180024a82  mov     rdx, [r14+10h]
0x180024a86  lea     rcx, [rbp+47h+Buf1]; Buf1
0x180024a8a  add     rdx, 10h; Buf2
0x180024a8e  mov     r8d, 8; Size
0x180024a94  call    memcmp_0
0x180024a99  test    eax, eax
0x180024a9b  jnz     short loc_180024B04
0x180024a9d  movzx   esi, byte ptr [r14+2Dh]
0x180024aa2  add     esi, r13d
0x180024aa5  cmp     esi, 5
0x180024aa8  jnb     short loc_180024B02
0x180024aaa  mov     rdx, [r14+10h]
0x180024aae  mov     ecx, esi
0x180024ab0  shl     rcx, 4
0x180024ab4  mov     eax, [rbp+rcx+47h+var_A0.Size]
0x180024ab8  sub     eax, [rdx+rcx+8]
0x180024abc  jnz     short loc_180024B04
0x180024abe  mov     r8d, [rbp+rcx+47h+var_A0.Size]; Size
0x180024ac3  mov     rdx, [rdx+rcx]; Buf2
0x180024ac7  mov     rcx, [rbp+rcx+47h+var_A0.Ptr]; Buf1
0x180024acc  call    memcmp_0
0x180024ad1  test    eax, eax
0x180024ad3  jnz     short loc_180024B04
0x180024ad5  inc     esi
0x180024ad7  jmp     short loc_180024AA5
0x180024ad9  cmp     r8b, 9
0x180024add  jnz     loc_1800249AC
0x180024ae3  lea     eax, [rdx-71h]
0x180024ae6  cmp     al, r13b
0x180024ae9  ja      loc_1800249AC
0x180024aef  movzx   eax, r12b
0x180024af3  add     rax, rax
0x180024af6  inc     r12b
0x180024af9  mov     byte ptr [rbp+rax*8+47h+var_78+5], dl
0x180024afd  jmp     loc_180024972
0x180024b02  xor     eax, eax
0x180024b04  mov     ecx, [rsp+100h+var_CC]
0x180024b08  test    eax, eax
0x180024b0a  jnz     short loc_180024B61
0x180024b0c  test    r14, r14
0x180024b0f  jnz     short loc_180024B78
0x180024b11  mov     rcx, [rbp+47h+SRWLock]; SRWLock
0x180024b15  call    cs:__imp_ReleaseSRWLockShared
0x180024b1b  test    rdi, rdi
0x180024b1e  jnz     loc_180024C97
0x180024b24  mov     eax, r15d
0x180024b27  mov     rcx, [rbp+47h+var_50]
0x180024b2b  xor     rcx, rsp; StackCookie
0x180024b2e  call    __security_check_cookie
0x180024b33  add     rsp, 0C8h
0x180024b3a  pop     r15
0x180024b3c  pop     r14
0x180024b3e  pop     r13
0x180024b40  pop     r12
0x180024b42  pop     rdi
0x180024b43  pop     rsi
0x180024b44  pop     rbx
0x180024b45  pop     rbp
0x180024b46  retn
0x180024b47  cmp     dword ptr [rbx+100h], 400h
0x180024b51  jb      short loc_180024BC1
0x180024b53  inc     dword ptr [rbx+12Ch]
0x180024b59  mov     r15d, 0EAh
0x180024b5f  jmp     short loc_180024B11
0x180024b61  movsxd  rsi, eax
0x180024b64  sar     rsi, 3Fh
0x180024b68  and     rsi, 0FFFFFFFFFFFFFFF8h
0x180024b6c  add     rsi, 20h ; ' '
0x180024b70  add     rsi, r14
0x180024b73  jmp     loc_180024A6B
0x180024b78  mov     r11b, [rsp+100h+var_D0]
0x180024b7d  cmp     r11b, r13b
0x180024b80  jbe     short loc_180024B11
0x180024b82  mov     r10, r13
0x180024b85  mov     rcx, [r14+10h]
0x180024b89  mov     rax, r10
0x180024b8c  add     rax, rax
0x180024b8f  mov     rdx, [rbp+rax*8+47h+var_A0.Ptr]
0x180024b94  movzx   r8d, byte ptr [rcx+rax*8+0Dh]
0x180024b9a  mov     rcx, [rcx+rax*8]
0x180024b9e  mov     rdx, [rdx]
0x180024ba1  call    AggregateField
0x180024ba6  inc     r13b
0x180024ba9  inc     r10
0x180024bac  cmp     r13b, r11b
0x180024baf  jb      short loc_180024B85
0x180024bb1  jmp     loc_180024B11
0x180024bb6  mov     eax, ecx
0x180024bb8  sub     eax, [r14+28h]
0x180024bbc  jmp     loc_180024B08
0x180024bc1  test    rdi, rdi
0x180024bc4  jz      short loc_180024C16
0x180024bc6  xor     eax, eax
0x180024bc8  lock cmpxchg [rsi], rdi
0x180024bcd  jnz     loc_180024A75
0x180024bd3  xor     edi, edi
0x180024bd5  lea     eax, [rdi+1]
0x180024bd8  lock xadd [rbx+100h], eax
0x180024be0  inc     eax
0x180024be2  cmp     eax, 1
0x180024be5  jnz     short loc_180024BF9
0x180024be7  mov     edx, [rbx+160h]
0x180024bed  mov     rcx, [rbx+158h]
0x180024bf4  call    EnableFlushTimer
0x180024bf9  mov     eax, [rbx+100h]
0x180024bff  cmp     [rbx+120h], eax
0x180024c05  jnb     loc_180024B11
0x180024c0b  mov     [rbx+120h], eax
0x180024c11  jmp     loc_180024B11
0x180024c16  lea     rax, [rsp+100h+var_C8]
0x180024c1b  mov     r9b, r12b
0x180024c1e  mov     [rsp+100h+UserData], rax
0x180024c23  lea     r8, [rbp+47h+var_A0]
0x180024c27  mov     [rsp+100h+UserDataCount], ecx
0x180024c2b  mov     dl, 5
0x180024c2d  lea     rcx, [rbp+47h+EventDescriptor]
0x180024c31  call    CreateNewEventEntry
0x180024c36  mov     rdi, [rsp+100h+var_C8]
0x180024c3b  mov     r15d, eax
0x180024c3e  test    rdi, rdi
0x180024c41  jz      short loc_180024C7C
0x180024c43  mov     ecx, [rsp+100h+var_CC]
0x180024c47  jmp     loc_180024BC6
0x180024c4c  mov     rcx, cs:RegHandle; RegHandle
0x180024c53  lea     rax, [rbp+47h+var_A0]
0x180024c57  mov     [rsp+100h+UserData], rax; UserData
0x180024c5c  lea     rdx, [rbp+47h+EventDescriptor]; EventDescriptor
0x180024c60  xor     r9d, r9d; RelatedActivityId
0x180024c63  mov     [rsp+100h+UserDataCount], 5; UserDataCount
0x180024c6b  xor     r8d, r8d; ActivityId
0x180024c6e  call    cs:__imp_EventWriteTransfer
0x180024c74  mov     r15d, eax
0x180024c77  jmp     loc_180024B24
0x180024c7c  cmp     eax, 8
0x180024c7f  jnz     short loc_180024C8C
0x180024c81  inc     dword ptr [rbx+130h]
0x180024c87  jmp     loc_180024B11
0x180024c8c  inc     dword ptr [rbx+134h]
0x180024c92  jmp     loc_180024B11
0x180024c97  mov     rcx, rdi
0x180024c9a  call    DestroyEventEntry
0x180024c9f  jmp     loc_180024B24
```
