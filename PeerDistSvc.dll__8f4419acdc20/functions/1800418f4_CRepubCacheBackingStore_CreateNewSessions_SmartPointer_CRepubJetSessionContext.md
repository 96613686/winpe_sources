# CRepubCacheBackingStore::CreateNewSessions(SmartPointer<CRepubJetSessionContext> *)

- ea: `0x1800418f4`
- end: `0x180041cc3`
- name: `?CreateNewSessions@CRepubCacheBackingStore@@AEAAKPEAV?$SmartPointer@VCRepubJetSessionContext@@@@@Z`
- size: `975`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x180044f54`
- `0x180047224`

## callees

- `0x1800024a4`
- `0x180004510`
- `0x180004874`
- `0x180008290`
- `0x18000cf48`
- `0x18000ecf4`
- `0x180015e38`
- `0x18001fc30`
- `0x180039174`
- `0x1800418f4`
- `0x18013ab7c`

## import_xrefs

- `ESENT!JetBeginSessionW` at `0x180041a34`
- `ESENT!JetBeginSessionW` at `0x180041a34`
- `ESENT!JetOpenDatabaseW` at `0x180041ae9`
- `ESENT!JetOpenDatabaseW` at `0x180041ae9`
- `ESENT!JetSetSessionContext` at `0x180041b57`
- `ESENT!JetSetSessionContext` at `0x180041b57`
- `ESENT!JetResetSessionContext` at `0x180041bb2`
- `ESENT!JetResetSessionContext` at `0x180041bb2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRepubCacheBackingStore::CreateNewSessions(__int64 a1, __int64 a2)
{
  unsigned int v3; // esi
  unsigned int i; // eax
  char *v5; // rax
  char *v6; // rbx
  __int64 j; // rdx
  __int64 v8; // rcx
  unsigned int v10; // eax
  int v11; // r13d
  JET_ERR v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 result; // rax
  char *v18; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v19[64]; // [rsp+38h] [rbp-40h] BYREF
  bool v20; // [rsp+80h] [rbp+8h]
  unsigned int v22; // [rsp+90h] [rbp+18h]

  v3 = 0;
  v18 = 0;
  v20 = a2 == 0;
  InCritSec::InCritSec((InCritSec *)v19, (struct CritSec *)(a1 + 50504), 1);
  try
  {
    if ( *(_BYTE *)(a1 + 50572) )
    {
      v3 = 4057;
      InCritSec::~InCritSec((InCritSec *)v19);
    }
    else
    {
      for ( i = 0; ; i = v22 + 1 )
      {
        v22 = i;
        if ( i >= 0x40 )
          break;
        v5 = (char *)operator new(0x78u);
        v6 = v5;
        if ( v5 )
        {
          *((_DWORD *)v5 + 2) = 0;
          *(_QWORD *)v5 = &CRepubJetSessionContext::`vftable';
          _InterlockedIncrement((volatile signed __int32 *)v5 + 2);
          *((_QWORD *)v5 + 2) = -1;
          *((_QWORD *)v5 + 3) = -1;
          *((_DWORD *)v5 + 8) = -1;
          *(_QWORD *)(v5 + 36) = 0;
          for ( j = 0; j != 5; ++j )
          {
            v8 = 3 * j;
            *(_WORD *)&v5[4 * v8 + 56] = 255;
            *(_DWORD *)&v5[12 * j + 60] = 0;
            *(_DWORD *)&v5[4 * v8 + 64] = -1;
          }
        }
        else
        {
          v6 = 0;
        }
        SmartPointer<CRepubJetSessionContext>::Release(&v18);
        v18 = v6;
        if ( (*(_DWORD *)(a1 + 50568))++ == -1 )
          *(_DWORD *)(a1 + 50568) = 1;
        *((_QWORD *)v6 + 2) = *(_QWORD *)(a1 + 216);
        *((_DWORD *)v6 + 10) = *(_DWORD *)(a1 + 50568);
        *((_QWORD *)v6 + 6) = *(_QWORD *)(a1 + 50320);
        v10 = JetBeginSessionW(*(_QWORD *)(a1 + 216), (JET_SESID *)v6 + 3, 0, 0);
        v11 = v10;
        if ( v10 )
        {
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 655, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v10);
          }
LABEL_37:
          v3 = TranslateJetError(v11);
          InCritSec::~InCritSec((InCritSec *)v19);
          goto LABEL_43;
        }
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
        {
          WPP_SF_qq(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            656,
            WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
            v6,
            *((_QWORD *)v6 + 3));
        }
        v12 = JetOpenDatabaseW(*((_QWORD *)v6 + 3), (JET_PCWSTR)(a1 + 2792), 0, (JET_DBID *)v6 + 8, 0);
        v11 = v12;
        if ( v12 )
        {
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              657,
              (unsigned int)WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
              a1 + 2792,
              v12);
          }
          goto LABEL_37;
        }
        *((_DWORD *)v6 + 9) = 0;
        v13 = JetSetSessionContext(*((_QWORD *)v6 + 3), *((unsigned int *)v6 + 10));
        v11 = v13;
        if ( v13 )
        {
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 658, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v13);
          }
          goto LABEL_37;
        }
        v14 = JetResetSessionContext(*((_QWORD *)v6 + 3));
        v11 = v14;
        if ( v14 )
        {
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 659, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v14);
          }
          goto LABEL_37;
        }
        if ( v20 )
        {
          std::list<SmartPointer<CNotification>>::push_back(a1 + 50552, &v18, v15, v16);
        }
        else
        {
          SmartPointer<INotification>::operator=(a2, v6, v15, v16);
          v20 = 1;
        }
      }
      InCritSec::~InCritSec((InCritSec *)v19);
    }
LABEL_43:
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 660, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v3);
    }
    SmartPointer<CRepubJetSessionContext>::Release(&v18);
    result = v3;
  }
  catch ( std::bad_alloc )
  {
    SmartPointer<CRepubJetSessionContext>::Release(&v18);
    return 14;
  }
  catch ( ... )
  {
    SmartPointer<CRepubJetSessionContext>::Release(&v18);
    return 774;
  }
  return result;
}

```

## disassembly

```asm
0x1800418f4  mov     [rsp+arg_8], rdx
0x1800418f9  push    rbx
0x1800418fa  push    rsi
0x1800418fb  push    r13
0x1800418fd  push    r14
0x1800418ff  push    r15
0x180041901  sub     rsp, 50h
0x180041905  mov     rax, rdx
0x180041908  mov     r14, rcx
0x18004190b  xor     r13d, r13d
0x18004190e  mov     esi, r13d
0x180041911  mov     [rsp+78h+var_48], r13
0x180041916  test    rax, rax
0x180041919  setz    [rsp+78h+arg_0]
0x180041921  lea     rdx, [rcx+0C548h]; struct CritSec *
0x180041928  mov     r8b, 1; bool
0x18004192b  lea     rcx, [rsp+78h+var_40]; this
0x180041930  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x180041935  nop
0x180041936  cmp     [r14+0C58Ch], r13b
0x18004193d  jz      short loc_18004195B
0x18004193f  mov     esi, 0FD9h
0x180041944  lea     rcx, [rsp+78h+var_40]; this
0x180041949  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x18004194e  nop
0x18004194f  lea     r15, WPP_GLOBAL_Control
0x180041956  jmp     loc_180041C57
0x18004195b  mov     eax, r13d
0x18004195e  lea     r15, WPP_GLOBAL_Control
0x180041965  mov     [rsp+78h+arg_10], eax
0x18004196c  cmp     eax, 40h ; '@'
0x18004196f  jnb     loc_180041C4C
0x180041975  mov     ecx, 78h ; 'x'; Size
0x18004197a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004197f  mov     rbx, rax
0x180041982  test    rax, rax
0x180041985  jz      short loc_1800419DC
0x180041987  mov     [rax+8], r13d
0x18004198b  lea     rax, ??_7CRepubJetSessionContext@@6B@; const CRepubJetSessionContext::`vftable'
0x180041992  mov     [rbx], rax
0x180041995  lock inc dword ptr [rbx+8]
0x180041999  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004199d  mov     [rbx+10h], rax
0x1800419a1  mov     [rbx+18h], rax
0x1800419a5  or      r8d, 0FFFFFFFFh
0x1800419a9  mov     [rbx+20h], r8d
0x1800419ad  mov     qword ptr [rbx+24h], 0
0x1800419b5  mov     rdx, r13
0x1800419b8  lea     rcx, [rdx+rdx*2]
0x1800419bc  mov     word ptr [rbx+rcx*4+38h], 0FFh
0x1800419c3  lea     rax, [rdx+rdx*2]
0x1800419c7  mov     [rbx+rax*4+3Ch], r13d
0x1800419cc  mov     [rbx+rcx*4+40h], r8d
0x1800419d1  inc     rdx
0x1800419d4  cmp     rdx, 5
0x1800419d8  jnz     short loc_1800419B8
0x1800419da  jmp     short loc_1800419DF
0x1800419dc  mov     rbx, r13
0x1800419df  lea     rcx, [rsp+78h+var_48]
0x1800419e4  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x1800419e9  mov     [rsp+78h+var_48], rbx
0x1800419ee  add     dword ptr [r14+0C588h], 1
0x1800419f6  jnz     short loc_180041A03
0x1800419f8  mov     dword ptr [r14+0C588h], 1
0x180041a03  mov     rax, [r14+0D8h]
0x180041a0a  mov     [rbx+10h], rax
0x180041a0e  mov     eax, [r14+0C588h]
0x180041a15  mov     [rbx+28h], eax
0x180041a18  mov     rax, [r14+0C490h]
0x180041a1f  mov     [rbx+30h], rax
0x180041a23  lea     rdx, [rbx+18h]; psesid
0x180041a27  xor     r9d, r9d; szPassword
0x180041a2a  xor     r8d, r8d; szUserName
0x180041a2d  mov     rcx, [r14+0D8h]; instance
0x180041a34  call    cs:__imp_JetBeginSessionW
0x180041a3a  mov     r13d, eax
0x180041a3d  test    eax, eax
0x180041a3f  jz      short loc_180041A8B
0x180041a41  mov     rcx, cs:WPP_GLOBAL_Control
0x180041a48  cmp     rcx, r15
0x180041a4b  jz      short loc_180041A71
0x180041a4d  test    byte ptr [rcx+6Ch], 4
0x180041a51  jz      short loc_180041A71
0x180041a53  cmp     byte ptr [rcx+69h], 1
0x180041a57  jb      short loc_180041A71
0x180041a59  mov     edx, 28Fh
0x180041a5e  mov     r9d, eax
0x180041a61  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x180041a68  mov     rcx, [rcx+60h]
0x180041a6c  call    WPP_SF_d
0x180041a71  mov     ecx, r13d; int
0x180041a74  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180041a79  mov     esi, eax
0x180041a7b  lea     rcx, [rsp+78h+var_40]; this
0x180041a80  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x180041a85  nop
0x180041a86  jmp     loc_180041C57
0x180041a8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180041a92  cmp     rcx, r15
0x180041a95  jz      short loc_180041AC4
0x180041a97  test    byte ptr [rcx+6Ch], 4
0x180041a9b  jz      short loc_180041AC4
0x180041a9d  cmp     byte ptr [rcx+69h], 4
0x180041aa1  jb      short loc_180041AC4
0x180041aa3  mov     edx, 290h
0x180041aa8  mov     rax, [rbx+18h]
0x180041aac  mov     qword ptr [rsp+78h+grbit], rax
0x180041ab1  mov     r9, rbx
0x180041ab4  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x180041abb  mov     rcx, [rcx+60h]
0x180041abf  call    WPP_SF_qq
0x180041ac4  lea     rax, [r14+0AE8h]
0x180041acb  mov     [rsp+78h+arg_18], rax
0x180041ad3  lea     r9, [rbx+20h]; pdbid
0x180041ad7  mov     [rsp+78h+grbit], 0; grbit
0x180041adf  xor     r8d, r8d; szConnect
0x180041ae2  mov     rdx, rax; szFilename
0x180041ae5  mov     rcx, [rbx+18h]; sesid
0x180041ae9  call    cs:__imp_JetOpenDatabaseW
0x180041aef  mov     r13d, eax
0x180041af2  test    eax, eax
0x180041af4  jz      short loc_180041B49
0x180041af6  mov     rcx, cs:WPP_GLOBAL_Control
0x180041afd  cmp     rcx, r15
0x180041b00  jz      short loc_180041B2F
0x180041b02  test    byte ptr [rcx+6Ch], 4
0x180041b06  jz      short loc_180041B2F
0x180041b08  cmp     byte ptr [rcx+69h], 1
0x180041b0c  jb      short loc_180041B2F
0x180041b0e  mov     edx, 291h
0x180041b13  mov     [rsp+78h+grbit], eax
0x180041b17  mov     r9, [rsp+78h+arg_18]
0x180041b1f  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x180041b26  mov     rcx, [rcx+60h]
0x180041b2a  call    WPP_SF_Sd
0x180041b2f  mov     ecx, r13d; int
0x180041b32  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180041b37  mov     esi, eax
0x180041b39  lea     rcx, [rsp+78h+var_40]; this
0x180041b3e  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x180041b43  nop
0x180041b44  jmp     loc_180041C57
0x180041b49  mov     dword ptr [rbx+24h], 0
0x180041b50  mov     edx, [rbx+28h]; ulContext
0x180041b53  mov     rcx, [rbx+18h]; sesid
0x180041b57  call    cs:__imp_JetSetSessionContext
0x180041b5d  mov     r13d, eax
0x180041b60  test    eax, eax
0x180041b62  jz      short loc_180041BAE
0x180041b64  mov     rcx, cs:WPP_GLOBAL_Control
0x180041b6b  cmp     rcx, r15
0x180041b6e  jz      short loc_180041B94
0x180041b70  test    byte ptr [rcx+6Ch], 4
0x180041b74  jz      short loc_180041B94
0x180041b76  cmp     byte ptr [rcx+69h], 1
0x180041b7a  jb      short loc_180041B94
0x180041b7c  mov     edx, 292h
0x180041b81  mov     r9d, eax
0x180041b84  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x180041b8b  mov     rcx, [rcx+60h]
0x180041b8f  call    WPP_SF_d
0x180041b94  mov     ecx, r13d; int
0x180041b97  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180041b9c  mov     esi, eax
0x180041b9e  lea     rcx, [rsp+78h+var_40]; this
0x180041ba3  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x180041ba8  nop
0x180041ba9  jmp     loc_180041C57
0x180041bae  mov     rcx, [rbx+18h]; sesid
0x180041bb2  call    cs:__imp_JetResetSessionContext
0x180041bb8  mov     r13d, eax
0x180041bbb  test    eax, eax
0x180041bbd  jz      short loc_180041C06
0x180041bbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180041bc6  cmp     rcx, r15
0x180041bc9  jz      short loc_180041BEF
0x180041bcb  test    byte ptr [rcx+6Ch], 4
0x180041bcf  jz      short loc_180041BEF
0x180041bd1  cmp     byte ptr [rcx+69h], 1
0x180041bd5  jb      short loc_180041BEF
0x180041bd7  mov     edx, 293h
0x180041bdc  mov     r9d, eax
0x180041bdf  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x180041be6  mov     rcx, [rcx+60h]
0x180041bea  call    WPP_SF_d
0x180041bef  mov     ecx, r13d; int
0x180041bf2  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180041bf7  mov     esi, eax
0x180041bf9  lea     rcx, [rsp+78h+var_40]; this
0x180041bfe  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x180041c03  nop
0x180041c04  jmp     short loc_180041C57
0x180041c06  xor     r13d, r13d
0x180041c09  cmp     [rsp+78h+arg_0], r13b
0x180041c11  jz      short loc_180041C26
0x180041c13  lea     rcx, [r14+0C578h]
0x180041c1a  lea     rdx, [rsp+78h+var_48]
0x180041c1f  call    ?push_back@?$list@V?$SmartPointer@VCNotification@@@@V?$allocator@V?$SmartPointer@VCNotification@@@@@std@@@std@@QEAAXAEBV?$SmartPointer@VCNotification@@@@@Z; std::list<SmartPointer<CNotification>>::push_back(SmartPointer<CNotification> const &)
0x180041c24  jmp     short loc_180041C3E
0x180041c26  mov     rdx, rbx
0x180041c29  mov     rcx, [rsp+78h+arg_8]
0x180041c31  call    ??4?$SmartPointer@VINotification@@@@QEAAAEAV0@PEAVINotification@@@Z; SmartPointer<INotification>::operator=(INotification *)
0x180041c36  mov     [rsp+78h+arg_0], 1
0x180041c3e  mov     eax, [rsp+78h+arg_10]
0x180041c45  inc     eax
0x180041c47  jmp     loc_180041965
0x180041c4c  lea     rcx, [rsp+78h+var_40]; this
0x180041c51  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x180041c56  nop
0x180041c57  mov     rcx, cs:WPP_GLOBAL_Control
0x180041c5e  cmp     rcx, r15
0x180041c61  jz      short loc_180041C88
0x180041c63  test    byte ptr [rcx+6Ch], 4
0x180041c67  jz      short loc_180041C88
0x180041c69  cmp     byte ptr [rcx+69h], 4
0x180041c6d  jb      short loc_180041C88
0x180041c6f  mov     edx, 294h
0x180041c74  mov     r9d, esi
0x180041c77  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x180041c7e  mov     rcx, [rcx+60h]
0x180041c82  call    WPP_SF_d
0x180041c87  nop
0x180041c88  lea     rcx, [rsp+78h+var_48]
0x180041c8d  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x180041c92  mov     eax, esi
0x180041c94  jmp     short loc_180041CB6
0x180041c96  lea     rcx, [rsp+78h+var_48]
0x180041c9b  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x180041ca0  mov     eax, 306h
0x180041ca5  jmp     short loc_180041CB6
0x180041ca7  lea     rcx, [rsp+78h+var_48]
0x180041cac  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x180041cb1  mov     eax, 0Eh
0x180041cb6  add     rsp, 50h
0x180041cba  pop     r15
0x180041cbc  pop     r14
0x180041cbe  pop     r13
0x180041cc0  pop     rsi
0x180041cc1  pop     rbx
0x180041cc2  retn
```
