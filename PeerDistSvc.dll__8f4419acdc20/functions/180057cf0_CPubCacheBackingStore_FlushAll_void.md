# CPubCacheBackingStore::FlushAll(void)

- ea: `0x180057cf0`
- end: `0x180058182`
- name: `?FlushAll@CPubCacheBackingStore@@AEAAKXZ`
- size: `1170`
- prototype: `unsigned int __fastcall(CPubCacheBackingStore *__hidden this)`
- caller_count: `3`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x180057c10`
- `0x18005a170`
- `0x18005c500`

## callees

- `0x180004374`
- `0x180008290`
- `0x18000ceac`
- `0x18000cf48`
- `0x180015330`
- `0x180015c28`
- `0x180018170`
- `0x180018efc`
- `0x180018f48`
- `0x18005104c`
- `0x180052b78`
- `0x180053ef0`
- `0x1800576ac`
- `0x180057cf0`
- `0x180058188`
- `0x180059c0c`
- `0x18005c4d0`
- `0x18005cfbc`
- `0x180114fd4`
- `0x18013ab7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057eb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058011`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057eb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058011`
- `ktmw32!CommitTransaction` at `0x180058007`
- `ktmw32!CommitTransaction` at `0x180058007`
- `ktmw32!CreateTransaction` at `0x180057e96`
- `ktmw32!CreateTransaction` at `0x180057e96`
- `ESENT!JetTerm2` at `0x180057dfd`
- `ESENT!JetTerm2` at `0x180057dfd`

## string_xrefs

- `0x180057e6f`: `PeerDistTransaction for publication cache mgmt`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CPubCacheBackingStore::FlushAll(CPubCacheBackingStore *this)
{
  unsigned int v2; // eax
  unsigned int v3; // edi
  CHostedCacheMsgEncoding *v4; // rcx
  JET_ERR v5; // eax
  char v6; // r15
  char *Transaction; // rbx
  CPubCacheBackingStore *v8; // rcx
  DWORD LastError; // eax
  __int64 v10; // rdx
  int v11; // r14d
  CPubCacheBackingStore *v12; // rcx
  int v13; // edx
  unsigned int v14; // edx
  _QWORD *v15; // rbx
  unsigned int v16; // eax
  unsigned int v17; // ebx
  void **v19; // [rsp+40h] [rbp-20h] BYREF
  char *v20; // [rsp+48h] [rbp-18h]
  _BYTE v21[16]; // [rsp+50h] [rbp-10h] BYREF
  CPublicationQueue *v22; // [rsp+90h] [rbp+30h] BYREF

  v19 = &ObjectHandle::`vftable';
  v20 = 0;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 205, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
  }
  if ( *((_QWORD *)this + 33) == -1 )
  {
    v6 = 0;
    goto LABEL_23;
  }
  v2 = CPubCacheBackingStore::DetachAllDatabases(this);
  v3 = v2;
  if ( !v2 )
  {
    ++*((_QWORD *)this + 32);
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 207, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
    }
    v5 = JetTerm2(*((_QWORD *)this + 33), 2u);
    if ( v5 )
    {
      v3 = TranslateJetError(v5);
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
        goto LABEL_69;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0 || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        goto LABEL_65;
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 12), 208, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
      goto LABEL_11;
    }
    *((_QWORD *)this + 33) = -1;
    *((_DWORD *)this + 49) = 4;
    v6 = 1;
LABEL_23:
    Transaction = (char *)CreateTransaction(
                            0,
                            0,
                            1u,
                            0,
                            0,
                            0,
                            (LPWSTR)L"PeerDistTransaction for publication cache mgmt");
    ObjectHandle::Close((ObjectHandle *)&v19);
    v20 = Transaction;
    if ( Transaction == (char *)-1LL )
    {
      LastError = GetLastError();
      v3 = LastError;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v10 = 209;
LABEL_28:
        WPP_SF_d(*((_QWORD *)v4 + 12), v10, WPP_817cd87503153d87380e6127cb13644a_Traceguids, LastError);
        v4 = WPP_GLOBAL_Control;
        goto LABEL_55;
      }
      goto LABEL_55;
    }
    v11 = (_DWORD)this + 2840;
    v3 = CPubCacheBackingStore::FlushHashStore(v8, (unsigned __int16 *)this + 1420);
    if ( v3 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_55;
      }
      v13 = 210;
    }
    else
    {
      v11 = (_DWORD)this + 3360;
      v3 = CPubCacheBackingStore::FlushHashStore(v12, (unsigned __int16 *)this + 1680);
      if ( v3 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          goto LABEL_55;
        }
        v13 = 211;
      }
      else
      {
        v11 = (_DWORD)this + 2320;
        v3 = DestroyCacheStore((const unsigned __int16 *)this + 1160, 0, Transaction, 1, 0);
        if ( !v3 )
        {
          if ( !CommitTransaction(Transaction) )
          {
            LastError = GetLastError();
            v3 = LastError;
            v4 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              v10 = 213;
              goto LABEL_28;
            }
LABEL_55:
            if ( !v6 || *((_BYTE *)this + 200) )
              goto LABEL_65;
            v16 = CPubCacheBackingStore::InitializeInstance(this);
            v17 = v16;
            if ( v16 )
            {
              v4 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
                || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
              {
LABEL_63:
                if ( !v3 )
                  v3 = v17;
                goto LABEL_65;
              }
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 214, WPP_817cd87503153d87380e6127cb13644a_Traceguids, v16);
            }
            v4 = WPP_GLOBAL_Control;
            goto LABEL_63;
          }
          CPubCacheBackingStore::SetUlongPerfCounter(this, v14, 0);
          LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>((__int64)v21, (RTL_SRWLOCK *)this + 4);
          v15 = (_QWORD *)**((_QWORD **)this + 602);
          while ( v15 != *((_QWORD **)this + 602) )
          {
            v22 = 0;
            std::auto_ptr<CPublicationQueue>::reset(&v22, v15[3]);
            CPublicationQueue::CancelAll(v22);
            v15 = (_QWORD *)*v15;
            std::auto_ptr<CPublicationQueue>::~auto_ptr<CPublicationQueue>(&v22);
          }
          std::list<unsigned short const *>::clear((char *)this + 4816);
          std::_Hash<stdext::_Hset_traits<unsigned __int64,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Init(
            (char *)this + 4816,
            8);
          LockSentry<ReadersWriterLock,0>::Unlock(v21);
LABEL_54:
          v4 = WPP_GLOBAL_Control;
          goto LABEL_55;
        }
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          goto LABEL_55;
        }
        v13 = 212;
      }
    }
    WPP_SF_Sd(*((_QWORD *)v4 + 12), v13, (unsigned int)WPP_817cd87503153d87380e6127cb13644a_Traceguids, v11, v3);
    goto LABEL_54;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    goto LABEL_69;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 206, WPP_817cd87503153d87380e6127cb13644a_Traceguids, v2);
LABEL_11:
    v4 = WPP_GLOBAL_Control;
  }
LABEL_65:
  if ( v4 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)v4 + 108) & 4) != 0
    && *((_BYTE *)v4 + 105) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)v4 + 12), 215, WPP_817cd87503153d87380e6127cb13644a_Traceguids, v3);
  }
LABEL_69:
  v19 = &ObjectHandle::`vftable';
  ObjectHandle::CloseNoThrow((ObjectHandle *)&v19);
  return v3;
}

```

## disassembly

```asm
0x180057cf0  mov     [rsp-28h+arg_8], rbx
0x180057cf5  mov     [rsp-28h+arg_10], rsi
0x180057cfa  push    rbp
0x180057cfb  push    rdi
0x180057cfc  push    r12
0x180057cfe  push    r14
0x180057d00  push    r15
0x180057d02  mov     rbp, rsp
0x180057d05  sub     rsp, 60h
0x180057d09  mov     rsi, rcx
0x180057d0c  lea     rbx, ??_7ObjectHandle@@6B@; const ObjectHandle::`vftable'
0x180057d13  mov     [rbp+var_20], rbx
0x180057d17  mov     [rbp+var_18], 0
0x180057d1f  lea     r14, WPP_GLOBAL_Control
0x180057d26  mov     r12d, 4
0x180057d2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180057d33  cmp     rcx, r14
0x180057d36  jz      short loc_180057D59
0x180057d38  test    [rcx+6Ch], r12b
0x180057d3c  jz      short loc_180057D59
0x180057d3e  cmp     [rcx+69h], r12b
0x180057d42  jb      short loc_180057D59
0x180057d44  mov     edx, 0CDh
0x180057d49  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x180057d50  mov     rcx, [rcx+60h]
0x180057d54  call    WPP_SF_
0x180057d59  cmp     qword ptr [rsi+108h], 0FFFFFFFFFFFFFFFFh
0x180057d61  jz      loc_180057E6C
0x180057d67  mov     rcx, rsi; this
0x180057d6a  call    ?DetachAllDatabases@CPubCacheBackingStore@@AEAAKXZ; CPubCacheBackingStore::DetachAllDatabases(void)
0x180057d6f  mov     edi, eax
0x180057d71  test    eax, eax
0x180057d73  jz      short loc_180057DBD
0x180057d75  mov     rcx, cs:WPP_GLOBAL_Control
0x180057d7c  cmp     rcx, r14
0x180057d7f  jz      loc_18005815A
0x180057d85  test    [rcx+6Ch], r12b
0x180057d89  jz      loc_180058130
0x180057d8f  cmp     byte ptr [rcx+69h], 1
0x180057d93  jb      loc_180058130
0x180057d99  mov     edx, 0CEh
0x180057d9e  mov     r9d, eax
0x180057da1  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x180057da8  mov     rcx, [rcx+60h]
0x180057dac  call    WPP_SF_d
0x180057db1  mov     rcx, cs:WPP_GLOBAL_Control
0x180057db8  jmp     loc_180058130
0x180057dbd  inc     qword ptr [rsi+100h]
0x180057dc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180057dcb  cmp     rcx, r14
0x180057dce  jz      short loc_180057DF1
0x180057dd0  test    [rcx+6Ch], r12b
0x180057dd4  jz      short loc_180057DF1
0x180057dd6  cmp     [rcx+69h], r12b
0x180057dda  jb      short loc_180057DF1
0x180057ddc  mov     edx, 0CFh
0x180057de1  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x180057de8  mov     rcx, [rcx+60h]
0x180057dec  call    WPP_SF_
0x180057df1  mov     edx, 2; grbit
0x180057df6  mov     rcx, [rsi+108h]; instance
0x180057dfd  call    cs:__imp_JetTerm2
0x180057e03  mov     r9d, eax
0x180057e06  test    eax, eax
0x180057e08  jz      short loc_180057E55
0x180057e0a  mov     ecx, eax; int
0x180057e0c  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180057e11  mov     edi, eax
0x180057e13  mov     rcx, cs:WPP_GLOBAL_Control
0x180057e1a  cmp     rcx, r14
0x180057e1d  jz      loc_18005815A
0x180057e23  test    [rcx+6Ch], r12b
0x180057e27  jz      loc_180058130
0x180057e2d  cmp     byte ptr [rcx+69h], 1
0x180057e31  jb      loc_180058130
0x180057e37  mov     edx, 0D0h
0x180057e3c  mov     [rsp+60h+IsolationFlags], eax
0x180057e40  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x180057e47  mov     rcx, [rcx+60h]
0x180057e4b  call    WPP_SF_Dd
0x180057e50  jmp     loc_180057DB1
0x180057e55  mov     qword ptr [rsi+108h], 0FFFFFFFFFFFFFFFFh
0x180057e60  mov     [rsi+0C4h], r12d
0x180057e67  mov     r15b, 1
0x180057e6a  jmp     short loc_180057E6F
0x180057e6c  xor     r15b, r15b
0x180057e6f  lea     rax, aPeerdisttransa; "PeerDistTransaction for publication cac"...
0x180057e76  mov     [rsp+60h+Description], rax; Description
0x180057e7b  mov     [rsp+60h+Timeout], 0; Timeout
0x180057e83  mov     [rsp+60h+IsolationFlags], 0; IsolationFlags
0x180057e8b  xor     r9d, r9d; IsolationLevel
0x180057e8e  xor     edx, edx; UOW
0x180057e90  xor     ecx, ecx; lpTransactionAttributes
0x180057e92  lea     r8d, [r9+1]; CreateOptions
0x180057e96  call    cs:__imp_CreateTransaction
0x180057e9c  mov     rbx, rax
0x180057e9f  lea     rcx, [rbp+var_20]; this
0x180057ea3  call    ?Close@ObjectHandle@@QEAAXXZ; ObjectHandle::Close(void)
0x180057ea8  mov     [rbp+var_18], rbx
0x180057eac  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180057eb0  jnz     short loc_180057F02
0x180057eb2  call    cs:__imp_GetLastError
0x180057eb8  mov     edi, eax
0x180057eba  mov     rcx, cs:WPP_GLOBAL_Control
0x180057ec1  cmp     rcx, r14
0x180057ec4  jz      loc_1800580D1
0x180057eca  test    [rcx+6Ch], r12b
0x180057ece  jz      loc_1800580D1
0x180057ed4  cmp     byte ptr [rcx+69h], 1
0x180057ed8  jb      loc_1800580D1
0x180057ede  mov     edx, 0D1h
0x180057ee3  mov     r9d, eax
0x180057ee6  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x180057eed  mov     rcx, [rcx+60h]
0x180057ef1  call    WPP_SF_d
0x180057ef6  mov     rcx, cs:WPP_GLOBAL_Control
0x180057efd  jmp     loc_1800580D1
0x180057f02  lea     r14, [rsi+0B18h]
0x180057f09  mov     rdx, r14; unsigned __int16 *
0x180057f0c  call    ?FlushHashStore@CPubCacheBackingStore@@AEAAKPEAG@Z; CPubCacheBackingStore::FlushHashStore(ushort *)
0x180057f11  mov     edi, eax
0x180057f13  test    eax, eax
0x180057f15  jz      short loc_180057F63
0x180057f17  mov     rcx, cs:WPP_GLOBAL_Control
0x180057f1e  lea     rax, WPP_GLOBAL_Control
0x180057f25  cmp     rcx, rax
0x180057f28  jz      loc_1800580CA
0x180057f2e  test    [rcx+6Ch], r12b
0x180057f32  jz      loc_1800580CA
0x180057f38  cmp     byte ptr [rcx+69h], 1
0x180057f3c  jb      loc_1800580CA
0x180057f42  mov     edx, 0D2h
0x180057f47  mov     [rsp+60h+IsolationFlags], edi
0x180057f4b  mov     r9, r14
0x180057f4e  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x180057f55  mov     rcx, [rcx+60h]
0x180057f59  call    WPP_SF_Sd
0x180057f5e  jmp     loc_1800580C3
0x180057f63  lea     r14, [rsi+0D20h]
0x180057f6a  mov     rdx, r14; unsigned __int16 *
0x180057f6d  call    ?FlushHashStore@CPubCacheBackingStore@@AEAAKPEAG@Z; CPubCacheBackingStore::FlushHashStore(ushort *)
0x180057f72  mov     edi, eax
0x180057f74  test    eax, eax
0x180057f76  jz      short loc_180057FAA
0x180057f78  mov     rcx, cs:WPP_GLOBAL_Control
0x180057f7f  lea     rax, WPP_GLOBAL_Control
0x180057f86  cmp     rcx, rax
0x180057f89  jz      loc_1800580CA
0x180057f8f  test    [rcx+6Ch], r12b
0x180057f93  jz      loc_1800580CA
0x180057f99  cmp     byte ptr [rcx+69h], 1
0x180057f9d  jb      loc_1800580CA
0x180057fa3  mov     edx, 0D3h
0x180057fa8  jmp     short loc_180057F47
0x180057faa  lea     r14, [rsi+910h]
0x180057fb1  mov     [rsp+60h+IsolationFlags], 0; unsigned int
0x180057fb9  mov     r9b, 1; bool
0x180057fbc  mov     r8, rbx; void *
0x180057fbf  xor     edx, edx; bool
0x180057fc1  mov     rcx, r14; unsigned __int16 *
0x180057fc4  call    ?DestroyCacheStore@@YAKPEBG_NPEAX1K@Z; DestroyCacheStore(ushort const *,bool,void *,bool,ulong)
0x180057fc9  mov     edi, eax
0x180057fcb  test    eax, eax
0x180057fcd  jz      short loc_180058004
0x180057fcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180057fd6  lea     rax, WPP_GLOBAL_Control
0x180057fdd  cmp     rcx, rax
0x180057fe0  jz      loc_1800580CA
0x180057fe6  test    [rcx+6Ch], r12b
0x180057fea  jz      loc_1800580CA
0x180057ff0  cmp     byte ptr [rcx+69h], 1
0x180057ff4  jb      loc_1800580CA
0x180057ffa  mov     edx, 0D4h
0x180057fff  jmp     loc_180057F47
0x180058004  mov     rcx, rbx; TransactionHandle
0x180058007  call    cs:__imp_CommitTransaction
0x18005800d  test    eax, eax
0x18005800f  jnz     short loc_18005804E
0x180058011  call    cs:__imp_GetLastError
0x180058017  mov     edi, eax
0x180058019  mov     rcx, cs:WPP_GLOBAL_Control
0x180058020  lea     r14, WPP_GLOBAL_Control
0x180058027  cmp     rcx, r14
0x18005802a  jz      loc_1800580D1
0x180058030  test    [rcx+6Ch], r12b
0x180058034  jz      loc_1800580D1
0x18005803a  cmp     byte ptr [rcx+69h], 1
0x18005803e  jb      loc_1800580D1
0x180058044  mov     edx, 0D5h
0x180058049  jmp     loc_180057EE3
0x18005804e  xor     r8d, r8d; unsigned int
0x180058051  mov     rcx, rsi; this
0x180058054  call    ?SetUlongPerfCounter@CPubCacheBackingStore@@QEAAXKK@Z; CPubCacheBackingStore::SetUlongPerfCounter(ulong,ulong)
0x180058059  lea     rdx, [rsi+20h]
0x18005805d  lea     rcx, [rbp+var_10]
0x180058061  call    ??0?$LockSentry@VReadersWriterLock@@$0A@@@QEAA@AEAVReadersWriterLock@@@Z; LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>(ReadersWriterLock &)
0x180058066  lea     r14, [rsi+12D0h]
0x18005806d  mov     rbx, [r14]
0x180058070  mov     rbx, [rbx]
0x180058073  cmp     rbx, [r14]
0x180058076  jz      short loc_1800580A4
0x180058078  mov     [rbp+arg_0], 0
0x180058080  mov     rdx, [rbx+18h]
0x180058084  lea     rcx, [rbp+arg_0]
0x180058088  call    ?reset@?$auto_ptr@VCPublicationQueue@@@std@@QEAAXPEAVCPublicationQueue@@@Z; std::auto_ptr<CPublicationQueue>::reset(CPublicationQueue *)
0x18005808d  mov     rcx, [rbp+arg_0]; this
0x180058091  call    ?CancelAll@CPublicationQueue@@QEAAXXZ; CPublicationQueue::CancelAll(void)
0x180058096  mov     rbx, [rbx]
0x180058099  lea     rcx, [rbp+arg_0]
0x18005809d  call    ??1?$auto_ptr@VCPublicationQueue@@@std@@QEAA@XZ; std::auto_ptr<CPublicationQueue>::~auto_ptr<CPublicationQueue>(void)
0x1800580a2  jmp     short loc_180058073
0x1800580a4  mov     rcx, r14
0x1800580a7  call    ?clear@?$list@PEBGV?$allocator@PEBG@std@@@std@@QEAAXXZ; std::list<ushort const *>::clear(void)
0x1800580ac  mov     edx, 8
0x1800580b1  mov     rcx, r14
0x1800580b4  call    ?_Init@?$_Hash@V?$_Hset_traits@_KV?$hash_compare@_KU?$less@_K@std@@@stdext@@V?$allocator@_K@std@@$0A@@stdext@@@std@@IEAAX_K@Z; std::_Hash<stdext::_Hset_traits<unsigned __int64,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Init(unsigned __int64)
0x1800580b9  nop
0x1800580ba  lea     rcx, [rbp+var_10]
0x1800580be  call    ?Unlock@?$LockSentry@VReadersWriterLock@@$0A@@@QEAAXXZ; LockSentry<ReadersWriterLock,0>::Unlock(void)
0x1800580c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800580ca  lea     r14, WPP_GLOBAL_Control
0x1800580d1  test    r15b, r15b
0x1800580d4  jz      short loc_180058129
0x1800580d6  cmp     byte ptr [rsi+0C8h], 0
0x1800580dd  jnz     short loc_180058129
0x1800580df  mov     rcx, rsi; this
0x1800580e2  call    ?InitializeInstance@CPubCacheBackingStore@@AEAAKXZ; CPubCacheBackingStore::InitializeInstance(void)
0x1800580e7  mov     ebx, eax
0x1800580e9  test    eax, eax
0x1800580eb  jz      short loc_18005811D
0x1800580ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800580f4  cmp     rcx, r14
0x1800580f7  jz      short loc_180058124
0x1800580f9  test    [rcx+6Ch], r12b
0x1800580fd  jz      short loc_180058124
0x1800580ff  cmp     byte ptr [rcx+69h], 1
0x180058103  jb      short loc_180058124
0x180058105  mov     edx, 0D6h
0x18005810a  mov     r9d, eax
0x18005810d  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x180058114  mov     rcx, [rcx+60h]
0x180058118  call    WPP_SF_d
0x18005811d  mov     rcx, cs:WPP_GLOBAL_Control
0x180058124  test    edi, edi
0x180058126  cmovz   edi, ebx
0x180058129  lea     rbx, ??_7ObjectHandle@@6B@; const ObjectHandle::`vftable'
0x180058130  cmp     rcx, r14
0x180058133  jz      short loc_18005815A
0x180058135  test    [rcx+6Ch], r12b
0x180058139  jz      short loc_18005815A
0x18005813b  cmp     [rcx+69h], r12b
0x18005813f  jb      short loc_18005815A
0x180058141  mov     edx, 0D7h
0x180058146  mov     r9d, edi
0x180058149  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x180058150  mov     rcx, [rcx+60h]
0x180058154  call    WPP_SF_d
0x180058159  nop
0x18005815a  mov     [rbp+var_20], rbx
0x18005815e  lea     rcx, [rbp+var_20]; this
0x180058162  call    ?CloseNoThrow@ObjectHandle@@IEAAKXZ; ObjectHandle::CloseNoThrow(void)
0x180058167  mov     eax, edi
0x180058169  lea     r11, [rsp+60h+var_s0]
0x18005816e  mov     rbx, [r11+38h]
0x180058172  mov     rsi, [r11+40h]
0x180058176  mov     rsp, r11
0x180058179  pop     r15
0x18005817b  pop     r14
0x18005817d  pop     r12
0x18005817f  pop     rdi
0x180058180  pop     rbp
0x180058181  retn
```
