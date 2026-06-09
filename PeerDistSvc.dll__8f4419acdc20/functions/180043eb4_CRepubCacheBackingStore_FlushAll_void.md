# CRepubCacheBackingStore::FlushAll(void)

- ea: `0x180043eb4`
- end: `0x18004438a`
- name: `?FlushAll@CRepubCacheBackingStore@@AEAAKXZ`
- size: `1238`
- prototype: `unsigned int __fastcall(CRepubCacheBackingStore *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x180043bf0`

## callees

- `0x180004374`
- `0x180008290`
- `0x18000cf48`
- `0x180015330`
- `0x180015c28`
- `0x180018170`
- `0x180018efc`
- `0x180018f48`
- `0x18003af30`
- `0x1800429b4`
- `0x180042a74`
- `0x180043eb4`
- `0x180047cf4`
- `0x18004d7d0`
- `0x18005104c`
- `0x180114fd4`
- `0x18013ab7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004406d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800442a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004406d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800442a4`
- `ktmw32!CommitTransaction` at `0x18004429a`
- `ktmw32!CommitTransaction` at `0x18004429a`
- `ktmw32!CreateTransaction` at `0x18004404f`
- `ktmw32!CreateTransaction` at `0x18004404f`
- `ESENT!JetTerm2` at `0x180043fbc`
- `ESENT!JetTerm2` at `0x180043fbc`

## string_xrefs

- `0x180044028`: `PeerDistTransaction for republication cache mgmt`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRepubCacheBackingStore::FlushAll(CRepubCacheBackingStore *this)
{
  unsigned int v2; // eax
  unsigned int v3; // edi
  CHostedCacheMsgEncoding *v4; // r10
  unsigned int v5; // eax
  int v6; // ebx
  char v7; // r12
  HANDLE Transaction; // r14
  DWORD LastError; // eax
  __int64 v10; // rdx
  unsigned int v11; // eax
  CRepubCacheBackingStore *v12; // rcx
  __int64 i; // rbp
  __int64 v14; // rbx
  unsigned __int16 *v15; // r15
  unsigned int v16; // eax
  unsigned int v17; // ebx
  unsigned int v19; // edx
  _QWORD *v20; // rbx
  _RepubSegmentMapContext *v21; // rcx
  bool IsolationFlags; // [rsp+20h] [rbp-88h]
  void **v23; // [rsp+40h] [rbp-68h] BYREF
  HANDLE v24; // [rsp+48h] [rbp-60h]
  _BYTE v25[88]; // [rsp+50h] [rbp-58h] BYREF

  v23 = &ObjectHandle::`vftable';
  v24 = 0;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 347, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
  }
  if ( *((_QWORD *)this + 27) == -1 )
  {
    v7 = 0;
    goto LABEL_23;
  }
  v2 = CRepubCacheBackingStore::DetachAllDatabases(this);
  v3 = v2;
  if ( !v2 )
  {
    ++*((_QWORD *)this + 6290);
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 349, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
    }
    v5 = JetTerm2(*((_QWORD *)this + 27), 1u);
    v6 = v5;
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 350, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v5);
      }
      v3 = TranslateJetError(v6);
      goto LABEL_52;
    }
    *((_QWORD *)this + 27) = -1;
    *((_DWORD *)this + 44) = 4;
    v7 = 1;
LABEL_23:
    Transaction = CreateTransaction(0, 0, 1u, 0, 0, 0, (LPWSTR)L"PeerDistTransaction for republication cache mgmt");
    ObjectHandle::Close((ObjectHandle *)&v23);
    v24 = Transaction;
    if ( Transaction == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v3 = LastError;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v10 = 351;
LABEL_28:
        WPP_SF_d(*((_QWORD *)v4 + 12), v10, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, LastError);
        goto LABEL_29;
      }
LABEL_43:
      if ( !v7 )
        goto LABEL_52;
      v16 = CRepubCacheBackingStore::InitializeInstance(this);
      v17 = v16;
      if ( v16 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
LABEL_50:
          if ( !v3 )
            v3 = v17;
          goto LABEL_52;
        }
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 356, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v16);
      }
      v4 = WPP_GLOBAL_Control;
      goto LABEL_50;
    }
    v11 = DestroyCacheStore((const unsigned __int16 *)this + 1136, 0, 0, 0, 0);
    v3 = v11;
    if ( v11 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_43;
      }
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        352,
        (unsigned int)WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
        (_DWORD)this + 2272,
        v11);
    }
    else
    {
      for ( i = 0; (unsigned int)i < *((_DWORD *)this + 1968); i = (unsigned int)(i + 1) )
      {
        v14 = 768 * i;
        v15 = (unsigned __int16 *)((char *)this + 768 * i);
        v3 = CRepubCacheBackingStore::DestroyFileStore(
               v12,
               Transaction,
               (CRepubCacheBackingStore *)((char *)this + 240 * (unsigned int)i + 7880),
               v15 + 2026,
               IsolationFlags);
        if ( v3 )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              353,
              (unsigned int)WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
              (_DWORD)v15 + 4052,
              v3);
            v4 = WPP_GLOBAL_Control;
          }
          goto LABEL_43;
        }
        *(_QWORD *)((char *)this + v14 + 4632) = 0;
        *(_DWORD *)((char *)this + v14 + 4640) = 0;
        *(_QWORD *)((char *)this + v14 + 4648) = -1;
        *(_QWORD *)((char *)this + v14 + 4656) = -1;
        *(_QWORD *)((char *)this + v14 + 4600) = 0;
      }
      if ( !CommitTransaction(Transaction) )
      {
        LastError = GetLastError();
        v3 = LastError;
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          v10 = 354;
          goto LABEL_28;
        }
        goto LABEL_43;
      }
      CRepubCacheBackingStore::SetUlongPerfCounter(this, 0x10u, 0);
      CRepubCacheBackingStore::SetUlongPerfCounter(this, 0x11u, 0);
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 355, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
      }
      LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>((__int64)v25, (RTL_SRWLOCK *)this + 3);
      v20 = (_QWORD *)*((_QWORD *)this + 6305);
      while ( 1 )
      {
        v20 = (_QWORD *)*v20;
        if ( v20 == *((_QWORD **)this + 6305) )
          break;
        v21 = (_RepubSegmentMapContext *)v20[3];
        if ( v21 )
          _RepubSegmentMapContext::`scalar deleting destructor'(v21, v19);
      }
      std::list<unsigned short const *>::clear((char *)this + 50440);
      std::_Hash<stdext::_Hset_traits<unsigned __int64,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Init(
        (char *)this + 50440,
        8);
      LockSentry<ReadersWriterLock,0>::Unlock(v25);
    }
LABEL_29:
    v4 = WPP_GLOBAL_Control;
    goto LABEL_43;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    goto LABEL_56;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 348, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v2);
    v4 = WPP_GLOBAL_Control;
  }
LABEL_52:
  if ( v4 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)v4 + 108) & 4) != 0
    && *((_BYTE *)v4 + 105) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)v4 + 12), 357, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v3);
  }
LABEL_56:
  v23 = &ObjectHandle::`vftable';
  ObjectHandle::CloseNoThrow((ObjectHandle *)&v23);
  return v3;
}

```

## disassembly

```asm
0x180043eb4  push    rbx
0x180043eb6  push    rbp
0x180043eb7  push    rsi
0x180043eb8  push    rdi
0x180043eb9  push    r12
0x180043ebb  push    r13
0x180043ebd  push    r14
0x180043ebf  push    r15
0x180043ec1  sub     rsp, 68h
0x180043ec5  mov     rsi, rcx
0x180043ec8  lea     rbx, ??_7ObjectHandle@@6B@; const ObjectHandle::`vftable'
0x180043ecf  mov     [rsp+0A8h+var_68], rbx
0x180043ed4  mov     [rsp+0A8h+var_60], 0
0x180043edd  lea     r15, WPP_GLOBAL_Control
0x180043ee4  mov     r13d, 4
0x180043eea  mov     rcx, cs:WPP_GLOBAL_Control
0x180043ef1  cmp     rcx, r15
0x180043ef4  jz      short loc_180043F17
0x180043ef6  test    [rcx+6Ch], r13b
0x180043efa  jz      short loc_180043F17
0x180043efc  cmp     [rcx+69h], r13b
0x180043f00  jb      short loc_180043F17
0x180043f02  mov     edx, 15Bh
0x180043f07  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x180043f0e  mov     rcx, [rcx+60h]
0x180043f12  call    WPP_SF_
0x180043f17  cmp     qword ptr [rsi+0D8h], 0FFFFFFFFFFFFFFFFh
0x180043f1f  jz      loc_180044025
0x180043f25  mov     rcx, rsi; this
0x180043f28  call    ?DetachAllDatabases@CRepubCacheBackingStore@@AEAAKXZ; CRepubCacheBackingStore::DetachAllDatabases(void)
0x180043f2d  mov     edi, eax
0x180043f2f  test    eax, eax
0x180043f31  jz      short loc_180043F7C
0x180043f33  mov     r10, cs:WPP_GLOBAL_Control
0x180043f3a  cmp     r10, r15
0x180043f3d  jz      loc_180044275
0x180043f43  test    [r10+6Ch], r13b
0x180043f47  jz      loc_18004424B
0x180043f4d  cmp     byte ptr [r10+69h], 1
0x180043f52  jb      loc_18004424B
0x180043f58  mov     edx, 15Ch
0x180043f5d  mov     r9d, eax
0x180043f60  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x180043f67  mov     rcx, [r10+60h]
0x180043f6b  call    WPP_SF_d
0x180043f70  mov     r10, cs:WPP_GLOBAL_Control
0x180043f77  jmp     loc_18004424B
0x180043f7c  inc     qword ptr [rsi+0C490h]
0x180043f83  mov     rcx, cs:WPP_GLOBAL_Control
0x180043f8a  cmp     rcx, r15
0x180043f8d  jz      short loc_180043FB0
0x180043f8f  test    [rcx+6Ch], r13b
0x180043f93  jz      short loc_180043FB0
0x180043f95  cmp     [rcx+69h], r13b
0x180043f99  jb      short loc_180043FB0
0x180043f9b  mov     edx, 15Dh
0x180043fa0  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x180043fa7  mov     rcx, [rcx+60h]
0x180043fab  call    WPP_SF_
0x180043fb0  mov     edx, 1; grbit
0x180043fb5  mov     rcx, [rsi+0D8h]; instance
0x180043fbc  call    cs:__imp_JetTerm2
0x180043fc2  mov     ebx, eax
0x180043fc4  test    eax, eax
0x180043fc6  jz      short loc_18004400E
0x180043fc8  mov     r10, cs:WPP_GLOBAL_Control
0x180043fcf  cmp     r10, r15
0x180043fd2  jz      short loc_180044000
0x180043fd4  test    [r10+6Ch], r13b
0x180043fd8  jz      short loc_180044000
0x180043fda  cmp     byte ptr [r10+69h], 1
0x180043fdf  jb      short loc_180044000
0x180043fe1  mov     edx, 15Eh
0x180043fe6  mov     r9d, eax
0x180043fe9  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x180043ff0  mov     rcx, [r10+60h]
0x180043ff4  call    WPP_SF_d
0x180043ff9  mov     r10, cs:WPP_GLOBAL_Control
0x180044000  mov     ecx, ebx; int
0x180044002  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180044007  mov     edi, eax
0x180044009  jmp     loc_180044244
0x18004400e  mov     qword ptr [rsi+0D8h], 0FFFFFFFFFFFFFFFFh
0x180044019  mov     [rsi+0B0h], r13d
0x180044020  mov     r12b, 1
0x180044023  jmp     short loc_180044028
0x180044025  xor     r12b, r12b
0x180044028  lea     rax, Description; "PeerDistTransaction for republication c"...
0x18004402f  mov     [rsp+0A8h+Description], rax; Description
0x180044034  mov     [rsp+0A8h+Timeout], 0; Timeout
0x18004403c  mov     dword ptr [rsp+0A8h+IsolationFlags], 0; IsolationFlags
0x180044044  xor     r9d, r9d; IsolationLevel
0x180044047  xor     edx, edx; UOW
0x180044049  xor     ecx, ecx; lpTransactionAttributes
0x18004404b  lea     r8d, [r9+1]; CreateOptions
0x18004404f  call    cs:__imp_CreateTransaction
0x180044055  mov     r14, rax
0x180044058  lea     rcx, [rsp+0A8h+var_68]; this
0x18004405d  call    ?Close@ObjectHandle@@QEAAXXZ; ObjectHandle::Close(void)
0x180044062  mov     [rsp+0A8h+var_60], r14
0x180044067  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18004406b  jnz     short loc_1800440BE
0x18004406d  call    cs:__imp_GetLastError
0x180044073  mov     edi, eax
0x180044075  mov     r10, cs:WPP_GLOBAL_Control
0x18004407c  cmp     r10, r15
0x18004407f  jz      loc_1800441F4
0x180044085  test    [r10+6Ch], r13b
0x180044089  jz      loc_1800441F4
0x18004408f  cmp     byte ptr [r10+69h], 1
0x180044094  jb      loc_1800441F4
0x18004409a  mov     edx, 15Fh
0x18004409f  mov     r9d, eax
0x1800440a2  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x1800440a9  mov     rcx, [r10+60h]
0x1800440ad  call    WPP_SF_d
0x1800440b2  mov     r10, cs:WPP_GLOBAL_Control
0x1800440b9  jmp     loc_1800441F4
0x1800440be  lea     rbx, [rsi+8E0h]
0x1800440c5  mov     dword ptr [rsp+0A8h+IsolationFlags], 0; bool
0x1800440cd  xor     r9d, r9d; bool
0x1800440d0  xor     r8d, r8d; void *
0x1800440d3  xor     edx, edx; bool
0x1800440d5  mov     rcx, rbx; unsigned __int16 *
0x1800440d8  call    ?DestroyCacheStore@@YAKPEBG_NPEAX1K@Z; DestroyCacheStore(ushort const *,bool,void *,bool,ulong)
0x1800440dd  mov     edi, eax
0x1800440df  test    eax, eax
0x1800440e1  jz      short loc_180044126
0x1800440e3  mov     r10, cs:WPP_GLOBAL_Control
0x1800440ea  cmp     r10, r15
0x1800440ed  jz      loc_1800441F4
0x1800440f3  test    [r10+6Ch], r13b
0x1800440f7  jz      loc_1800441F4
0x1800440fd  cmp     byte ptr [r10+69h], 1
0x180044102  jb      loc_1800441F4
0x180044108  mov     edx, 160h
0x18004410d  mov     dword ptr [rsp+0A8h+IsolationFlags], eax
0x180044111  mov     r9, rbx
0x180044114  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004411b  mov     rcx, [r10+60h]
0x18004411f  call    WPP_SF_Sd
0x180044124  jmp     short loc_1800440B2
0x180044126  xor     ebp, ebp
0x180044128  cmp     ebp, [rsi+1EC0h]
0x18004412e  jnb     loc_180044297
0x180044134  mov     eax, ebp
0x180044136  lea     rbx, ds:0[rbp*2]
0x18004413e  add     rbx, rbp
0x180044141  shl     rbx, 8
0x180044145  lea     r15, [rbx+rsi]
0x180044149  imul    r8, rax, 0F0h
0x180044150  add     r8, 1EC8h
0x180044157  add     r8, rsi; struct CRepubFileStore *
0x18004415a  lea     r9, [r15+0FD4h]; unsigned __int16 *
0x180044161  mov     rdx, r14; void *
0x180044164  call    ?DestroyFileStore@CRepubCacheBackingStore@@AEAAKPEAXPEAVCRepubFileStore@@PEAG_N@Z; CRepubCacheBackingStore::DestroyFileStore(void *,CRepubFileStore *,ushort *,bool)
0x180044169  mov     edi, eax
0x18004416b  test    eax, eax
0x18004416d  jnz     short loc_1800441A6
0x18004416f  mov     qword ptr [rbx+rsi+1218h], 0
0x18004417b  mov     [rbx+rsi+1220h], eax
0x180044182  or      rax, 0FFFFFFFFFFFFFFFFh
0x180044186  mov     [rbx+rsi+1228h], rax
0x18004418e  mov     [rbx+rsi+1230h], rax
0x180044196  mov     qword ptr [rbx+rsi+11F8h], 0
0x1800441a2  inc     ebp
0x1800441a4  jmp     short loc_180044128
0x1800441a6  mov     r10, cs:WPP_GLOBAL_Control
0x1800441ad  lea     rax, WPP_GLOBAL_Control
0x1800441b4  cmp     r10, rax
0x1800441b7  jz      short loc_1800441ED
0x1800441b9  test    [r10+6Ch], r13b
0x1800441bd  jz      short loc_1800441ED
0x1800441bf  cmp     byte ptr [r10+69h], 1
0x1800441c4  jb      short loc_1800441ED
0x1800441c6  mov     edx, 161h
0x1800441cb  mov     dword ptr [rsp+0A8h+IsolationFlags], edi
0x1800441cf  lea     r9, [r15+0FD4h]
0x1800441d6  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x1800441dd  mov     rcx, [r10+60h]
0x1800441e1  call    WPP_SF_Sd
0x1800441e6  mov     r10, cs:WPP_GLOBAL_Control
0x1800441ed  lea     r15, WPP_GLOBAL_Control
0x1800441f4  test    r12b, r12b
0x1800441f7  jz      short loc_180044244
0x1800441f9  mov     rcx, rsi; this
0x1800441fc  call    ?InitializeInstance@CRepubCacheBackingStore@@AEAAKXZ; CRepubCacheBackingStore::InitializeInstance(void)
0x180044201  mov     ebx, eax
0x180044203  test    eax, eax
0x180044205  jz      short loc_180044238
0x180044207  mov     r10, cs:WPP_GLOBAL_Control
0x18004420e  cmp     r10, r15
0x180044211  jz      short loc_18004423F
0x180044213  test    [r10+6Ch], r13b
0x180044217  jz      short loc_18004423F
0x180044219  cmp     byte ptr [r10+69h], 1
0x18004421e  jb      short loc_18004423F
0x180044220  mov     edx, 164h
0x180044225  mov     r9d, eax
0x180044228  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004422f  mov     rcx, [r10+60h]
0x180044233  call    WPP_SF_d
0x180044238  mov     r10, cs:WPP_GLOBAL_Control
0x18004423f  test    edi, edi
0x180044241  cmovz   edi, ebx
0x180044244  lea     rbx, ??_7ObjectHandle@@6B@; const ObjectHandle::`vftable'
0x18004424b  cmp     r10, r15
0x18004424e  jz      short loc_180044275
0x180044250  test    [r10+6Ch], r13b
0x180044254  jz      short loc_180044275
0x180044256  cmp     [r10+69h], r13b
0x18004425a  jb      short loc_180044275
0x18004425c  mov     edx, 165h
0x180044261  mov     r9d, edi
0x180044264  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004426b  mov     rcx, [r10+60h]
0x18004426f  call    WPP_SF_d
0x180044274  nop
0x180044275  mov     [rsp+0A8h+var_68], rbx
0x18004427a  lea     rcx, [rsp+0A8h+var_68]; this
0x18004427f  call    ?CloseNoThrow@ObjectHandle@@IEAAKXZ; ObjectHandle::CloseNoThrow(void)
0x180044284  mov     eax, edi
0x180044286  add     rsp, 68h
0x18004428a  pop     r15
0x18004428c  pop     r14
0x18004428e  pop     r13
0x180044290  pop     r12
0x180044292  pop     rdi
0x180044293  pop     rsi
0x180044294  pop     rbp
0x180044295  pop     rbx
0x180044296  retn
0x180044297  mov     rcx, r14; TransactionHandle
0x18004429a  call    cs:__imp_CommitTransaction
0x1800442a0  test    eax, eax
0x1800442a2  jnz     short loc_1800442E2
0x1800442a4  call    cs:__imp_GetLastError
0x1800442aa  mov     edi, eax
0x1800442ac  mov     r10, cs:WPP_GLOBAL_Control
0x1800442b3  lea     r15, WPP_GLOBAL_Control
0x1800442ba  cmp     r10, r15
0x1800442bd  jz      loc_1800441F4
0x1800442c3  test    [r10+6Ch], r13b
0x1800442c7  jz      loc_1800441F4
0x1800442cd  cmp     byte ptr [r10+69h], 1
0x1800442d2  jb      loc_1800441F4
0x1800442d8  mov     edx, 162h
0x1800442dd  jmp     loc_18004409F
0x1800442e2  xor     r8d, r8d; unsigned int
0x1800442e5  lea     edx, [r8+10h]; unsigned int
0x1800442e9  mov     rcx, rsi; this
0x1800442ec  call    ?SetUlongPerfCounter@CRepubCacheBackingStore@@QEAAXKK@Z; CRepubCacheBackingStore::SetUlongPerfCounter(ulong,ulong)
0x1800442f1  xor     r8d, r8d; unsigned int
0x1800442f4  lea     edx, [r8+11h]; unsigned int
0x1800442f8  mov     rcx, rsi; this
0x1800442fb  call    ?SetUlongPerfCounter@CRepubCacheBackingStore@@QEAAXKK@Z; CRepubCacheBackingStore::SetUlongPerfCounter(ulong,ulong)
0x180044300  mov     rcx, cs:WPP_GLOBAL_Control
0x180044307  lea     r15, WPP_GLOBAL_Control
0x18004430e  cmp     rcx, r15
0x180044311  jz      short loc_180044334
0x180044313  test    [rcx+6Ch], r13b
0x180044317  jz      short loc_180044334
0x180044319  cmp     [rcx+69h], r13b
0x18004431d  jb      short loc_180044334
0x18004431f  mov     edx, 163h
0x180044324  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004432b  mov     rcx, [rcx+60h]
0x18004432f  call    WPP_SF_
0x180044334  lea     rdx, [rsi+18h]
0x180044338  lea     rcx, [rsp+0A8h+var_58]
0x18004433d  call    ??0?$LockSentry@VReadersWriterLock@@$0A@@@QEAA@AEAVReadersWriterLock@@@Z; LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>(ReadersWriterLock &)
0x180044342  lea     r14, [rsi+0C508h]
0x180044349  mov     rbx, [r14]
0x18004434c  mov     rbx, [rbx]
0x18004434f  cmp     rbx, [r14]
0x180044352  jz      short loc_180044364
0x180044354  mov     rcx, [rbx+18h]; this
0x180044358  test    rcx, rcx
0x18004435b  jz      short loc_18004434C
0x18004435d  call    ??_G_RepubSegmentMapContext@@QEAAPEAXI@Z; _RepubSegmentMapContext::`scalar deleting destructor'(uint)
0x180044362  jmp     short loc_18004434C
0x180044364  mov     rcx, r14
0x180044367  call    ?clear@?$list@PEBGV?$allocator@PEBG@std@@@std@@QEAAXXZ; std::list<ushort const *>::clear(void)
0x18004436c  mov     edx, 8
0x180044371  mov     rcx, r14
0x180044374  call    ?_Init@?$_Hash@V?$_Hset_traits@_KV?$hash_compare@_KU?$less@_K@std@@@stdext@@V?$allocator@_K@std@@$0A@@stdext@@@std@@IEAAX_K@Z; std::_Hash<stdext::_Hset_traits<unsigned __int64,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Init(unsigned __int64)
0x180044379  nop
0x18004437a  lea     rcx, [rsp+0A8h+var_58]
0x18004437f  call    ?Unlock@?$LockSentry@VReadersWriterLock@@$0A@@@QEAAXXZ; LockSentry<ReadersWriterLock,0>::Unlock(void)
0x180044384  jmp     loc_1800440B2
```
