# CPubCacheBackingStore::CreateNewSessions(SmartPointer<CPubJetSessionContext> *)

- ea: `0x180056464`
- end: `0x180056818`
- name: `?CreateNewSessions@CPubCacheBackingStore@@AEAAKPEAV?$SmartPointer@VCPubJetSessionContext@@@@@Z`
- size: `948`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180058d00`
- `0x1800596e8`

## callees

- `0x1800024a4`
- `0x180004510`
- `0x180004874`
- `0x180008290`
- `0x18000ceac`
- `0x18000ecf4`
- `0x180015e38`
- `0x18001fc30`
- `0x180039174`
- `0x18005214c`
- `0x180056464`
- `0x18013ab7c`

## import_xrefs

- `ESENT!JetBeginSessionW` at `0x180056581`
- `ESENT!JetBeginSessionW` at `0x180056581`
- `ESENT!JetOpenDatabaseW` at `0x180056637`
- `ESENT!JetOpenDatabaseW` at `0x180056637`
- `ESENT!JetSetSessionContext` at `0x1800566aa`
- `ESENT!JetSetSessionContext` at `0x1800566aa`
- `ESENT!JetResetSessionContext` at `0x180056706`
- `ESENT!JetResetSessionContext` at `0x180056706`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CPubCacheBackingStore::CreateNewSessions(__int64 a1, __int64 a2)
{
  unsigned int v3; // edi
  unsigned int i; // eax
  char *v5; // rax
  char *v6; // rbx
  JET_SESID *v8; // r13
  JET_ERR v9; // eax
  JET_ERR v10; // eax
  unsigned int v11; // eax
  char v12; // r8
  JET_ERR v13; // eax
  unsigned int v14; // eax
  __int64 v15; // r8
  __int64 result; // rax
  char *v17; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v18[64]; // [rsp+38h] [rbp-40h] BYREF
  bool v19; // [rsp+80h] [rbp+8h]
  unsigned int v21; // [rsp+90h] [rbp+18h]

  v3 = 0;
  v17 = 0;
  v19 = a2 == 0;
  InCritSec::InCritSec((InCritSec *)v18, (struct CritSec *)(a1 + 4880), 1);
  try
  {
    if ( *(_BYTE *)(a1 + 4948) )
    {
      v3 = 4057;
      InCritSec::~InCritSec((InCritSec *)v18);
    }
    else
    {
      for ( i = 0; ; i = v21 + 1 )
      {
        v21 = i;
        if ( i >= 0x20 )
          break;
        v5 = (char *)operator new(0x38u);
        v6 = v5;
        if ( v5 )
        {
          *((_DWORD *)v5 + 2) = 0;
          *(_QWORD *)v5 = &CPubJetSessionContext::`vftable';
          _InterlockedIncrement((volatile signed __int32 *)v5 + 2);
          *((_QWORD *)v5 + 2) = -1;
          *((_QWORD *)v5 + 3) = -1;
          *((_DWORD *)v5 + 8) = -1;
          *(_QWORD *)(v5 + 36) = 0;
        }
        else
        {
          v6 = 0;
        }
        SmartPointer<CRepubJetSessionContext>::Release(&v17);
        v17 = v6;
        if ( (*(_DWORD *)(a1 + 4944))++ == -1 )
          *(_DWORD *)(a1 + 4944) = 1;
        *((_QWORD *)v6 + 2) = *(_QWORD *)(a1 + 264);
        *((_DWORD *)v6 + 10) = *(_DWORD *)(a1 + 4944);
        *((_QWORD *)v6 + 6) = *(_QWORD *)(a1 + 256);
        v8 = (JET_SESID *)(v6 + 24);
        v9 = JetBeginSessionW(*(_QWORD *)(a1 + 264), (JET_SESID *)v6 + 3, 0, 0);
        if ( v9 )
        {
          v3 = TranslateJetError(v9);
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 12), 365, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
          }
          break;
        }
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
        {
          WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 12), 366, WPP_817cd87503153d87380e6127cb13644a_Traceguids, v6, *v8);
        }
        v10 = JetOpenDatabaseW(*v8, (JET_PCWSTR)(a1 + 3888), 0, (JET_DBID *)v6 + 8, 0);
        if ( v10 )
        {
          v11 = TranslateJetError(v10);
          v3 = v11;
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_SdD(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              367,
              (unsigned int)WPP_817cd87503153d87380e6127cb13644a_Traceguids,
              a1 + 3888,
              v12,
              v11,
              v17);
          }
          break;
        }
        *((_DWORD *)v6 + 9) = 0;
        v13 = JetSetSessionContext(*v8, *((unsigned int *)v6 + 10));
        if ( v13 )
        {
          v3 = TranslateJetError(v13);
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 12), 368, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
          }
          break;
        }
        v14 = JetResetSessionContext(*v8);
        if ( v14 )
        {
          v3 = TranslateJetError(v14);
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 12), 369, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
          }
          break;
        }
        if ( v19 )
        {
          std::list<SmartPointer<CNotification>>::push_back(a1 + 4928, &v17, v15, v14);
        }
        else
        {
          SmartPointer<INotification>::operator=(a2, v6, v15, v14);
          v19 = 1;
        }
      }
      InCritSec::~InCritSec((InCritSec *)v18);
    }
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 370, WPP_817cd87503153d87380e6127cb13644a_Traceguids, v3);
    }
    SmartPointer<CRepubJetSessionContext>::Release(&v17);
    result = v3;
  }
  catch ( std::bad_alloc )
  {
    SmartPointer<CRepubJetSessionContext>::Release(&v17);
    return 14;
  }
  catch ( ... )
  {
    SmartPointer<CRepubJetSessionContext>::Release(&v17);
    return 774;
  }
  return result;
}

```

## disassembly

```asm
0x180056464  mov     [rsp+arg_8], rdx
0x180056469  push    rbx
0x18005646a  push    rdi
0x18005646b  push    r13
0x18005646d  push    r14
0x18005646f  push    r15
0x180056471  sub     rsp, 50h
0x180056475  mov     rax, rdx
0x180056478  mov     r14, rcx
0x18005647b  xor     r13d, r13d
0x18005647e  mov     edi, r13d
0x180056481  mov     [rsp+78h+var_48], r13
0x180056486  test    rax, rax
0x180056489  setz    [rsp+78h+arg_0]
0x180056491  lea     rdx, [rcx+1310h]; struct CritSec *
0x180056498  mov     r8b, 1; bool
0x18005649b  lea     rcx, [rsp+78h+var_40]; this
0x1800564a0  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x1800564a5  nop
0x1800564a6  cmp     [r14+1354h], r13b
0x1800564ad  jz      short loc_1800564CB
0x1800564af  mov     edi, 0FD9h
0x1800564b4  lea     rcx, [rsp+78h+var_40]; this
0x1800564b9  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x1800564be  nop
0x1800564bf  lea     r15, WPP_GLOBAL_Control
0x1800564c6  jmp     loc_1800567AC
0x1800564cb  mov     eax, r13d
0x1800564ce  lea     r15, WPP_GLOBAL_Control
0x1800564d5  mov     [rsp+78h+arg_10], eax
0x1800564dc  cmp     eax, 20h ; ' '
0x1800564df  jnb     loc_1800567A1
0x1800564e5  mov     ecx, 38h ; '8'; Size
0x1800564ea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800564ef  mov     rbx, rax
0x1800564f2  test    rax, rax
0x1800564f5  jz      short loc_180056526
0x1800564f7  mov     [rax+8], r13d
0x1800564fb  lea     rax, ??_7CPubJetSessionContext@@6B@; const CPubJetSessionContext::`vftable'
0x180056502  mov     [rbx], rax
0x180056505  lock inc dword ptr [rbx+8]
0x180056509  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005650d  mov     [rbx+10h], rax
0x180056511  mov     [rbx+18h], rax
0x180056515  mov     dword ptr [rbx+20h], 0FFFFFFFFh
0x18005651c  mov     qword ptr [rbx+24h], 0
0x180056524  jmp     short loc_180056529
0x180056526  mov     rbx, r13
0x180056529  lea     rcx, [rsp+78h+var_48]
0x18005652e  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x180056533  mov     [rsp+78h+var_48], rbx
0x180056538  add     dword ptr [r14+1350h], 1
0x180056540  jnz     short loc_18005654D
0x180056542  mov     dword ptr [r14+1350h], 1
0x18005654d  mov     rax, [r14+108h]
0x180056554  mov     [rbx+10h], rax
0x180056558  mov     eax, [r14+1350h]
0x18005655f  mov     [rbx+28h], eax
0x180056562  mov     rax, [r14+100h]
0x180056569  mov     [rbx+30h], rax
0x18005656d  lea     r13, [rbx+18h]
0x180056571  xor     r9d, r9d; szPassword
0x180056574  xor     r8d, r8d; szUserName
0x180056577  mov     rdx, r13; psesid
0x18005657a  mov     rcx, [r14+108h]; instance
0x180056581  call    cs:__imp_JetBeginSessionW
0x180056587  mov     r9d, eax
0x18005658a  test    eax, eax
0x18005658c  jz      short loc_1800565D9
0x18005658e  mov     ecx, eax; int
0x180056590  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180056595  mov     edi, eax
0x180056597  mov     rcx, cs:WPP_GLOBAL_Control
0x18005659e  cmp     rcx, r15
0x1800565a1  jz      short loc_1800565C9
0x1800565a3  test    byte ptr [rcx+6Ch], 4
0x1800565a7  jz      short loc_1800565C9
0x1800565a9  cmp     byte ptr [rcx+69h], 1
0x1800565ad  jb      short loc_1800565C9
0x1800565af  mov     edx, 16Dh
0x1800565b4  mov     [rsp+78h+grbit], eax
0x1800565b8  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x1800565bf  mov     rcx, [rcx+60h]
0x1800565c3  call    WPP_SF_Dd
0x1800565c8  nop
0x1800565c9  lea     rcx, [rsp+78h+var_40]; this
0x1800565ce  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x1800565d3  nop
0x1800565d4  jmp     loc_1800567AC
0x1800565d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800565e0  cmp     rcx, r15
0x1800565e3  jz      short loc_180056612
0x1800565e5  test    byte ptr [rcx+6Ch], 4
0x1800565e9  jz      short loc_180056612
0x1800565eb  cmp     byte ptr [rcx+69h], 4
0x1800565ef  jb      short loc_180056612
0x1800565f1  mov     edx, 16Eh
0x1800565f6  mov     rax, [r13+0]
0x1800565fa  mov     qword ptr [rsp+78h+grbit], rax
0x1800565ff  mov     r9, rbx
0x180056602  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x180056609  mov     rcx, [rcx+60h]
0x18005660d  call    WPP_SF_qq
0x180056612  lea     rax, [r14+0F30h]
0x180056619  mov     [rsp+78h+arg_18], rax
0x180056621  lea     r9, [rbx+20h]; pdbid
0x180056625  mov     [rsp+78h+grbit], 0; grbit
0x18005662d  xor     r8d, r8d; szConnect
0x180056630  mov     rdx, rax; szFilename
0x180056633  mov     rcx, [r13+0]; sesid
0x180056637  call    cs:__imp_JetOpenDatabaseW
0x18005663d  mov     r8d, eax
0x180056640  test    eax, eax
0x180056642  jz      short loc_18005669C
0x180056644  mov     ecx, eax; int
0x180056646  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18005664b  mov     edi, eax
0x18005664d  mov     rcx, cs:WPP_GLOBAL_Control
0x180056654  cmp     rcx, r15
0x180056657  jz      short loc_18005668C
0x180056659  test    byte ptr [rcx+6Ch], 4
0x18005665d  jz      short loc_18005668C
0x18005665f  cmp     byte ptr [rcx+69h], 1
0x180056663  jb      short loc_18005668C
0x180056665  mov     edx, 16Fh
0x18005666a  mov     [rsp+78h+var_50], eax
0x18005666e  mov     [rsp+78h+grbit], r8d
0x180056673  mov     r9, [rsp+78h+arg_18]
0x18005667b  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x180056682  mov     rcx, [rcx+60h]
0x180056686  call    WPP_SF_SdD
0x18005668b  nop
0x18005668c  lea     rcx, [rsp+78h+var_40]; this
0x180056691  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x180056696  nop
0x180056697  jmp     loc_1800567AC
0x18005669c  mov     dword ptr [rbx+24h], 0
0x1800566a3  mov     edx, [rbx+28h]; ulContext
0x1800566a6  mov     rcx, [r13+0]; sesid
0x1800566aa  call    cs:__imp_JetSetSessionContext
0x1800566b0  mov     r9d, eax
0x1800566b3  test    eax, eax
0x1800566b5  jz      short loc_180056702
0x1800566b7  mov     ecx, eax; int
0x1800566b9  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x1800566be  mov     edi, eax
0x1800566c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800566c7  cmp     rcx, r15
0x1800566ca  jz      short loc_1800566F2
0x1800566cc  test    byte ptr [rcx+6Ch], 4
0x1800566d0  jz      short loc_1800566F2
0x1800566d2  cmp     byte ptr [rcx+69h], 1
0x1800566d6  jb      short loc_1800566F2
0x1800566d8  mov     edx, 170h
0x1800566dd  mov     [rsp+78h+grbit], eax
0x1800566e1  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x1800566e8  mov     rcx, [rcx+60h]
0x1800566ec  call    WPP_SF_Dd
0x1800566f1  nop
0x1800566f2  lea     rcx, [rsp+78h+var_40]; this
0x1800566f7  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x1800566fc  nop
0x1800566fd  jmp     loc_1800567AC
0x180056702  mov     rcx, [r13+0]; sesid
0x180056706  call    cs:__imp_JetResetSessionContext
0x18005670c  mov     r9d, eax
0x18005670f  xor     r13d, r13d
0x180056712  test    eax, eax
0x180056714  jz      short loc_18005675E
0x180056716  mov     ecx, eax; int
0x180056718  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18005671d  mov     edi, eax
0x18005671f  mov     rcx, cs:WPP_GLOBAL_Control
0x180056726  cmp     rcx, r15
0x180056729  jz      short loc_180056751
0x18005672b  test    byte ptr [rcx+6Ch], 4
0x18005672f  jz      short loc_180056751
0x180056731  cmp     byte ptr [rcx+69h], 1
0x180056735  jb      short loc_180056751
0x180056737  mov     edx, 171h
0x18005673c  mov     [rsp+78h+grbit], eax
0x180056740  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x180056747  mov     rcx, [rcx+60h]
0x18005674b  call    WPP_SF_Dd
0x180056750  nop
0x180056751  lea     rcx, [rsp+78h+var_40]; this
0x180056756  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x18005675b  nop
0x18005675c  jmp     short loc_1800567AC
0x18005675e  cmp     [rsp+78h+arg_0], r13b
0x180056766  jz      short loc_18005677B
0x180056768  lea     rcx, [r14+1340h]
0x18005676f  lea     rdx, [rsp+78h+var_48]
0x180056774  call    ?push_back@?$list@V?$SmartPointer@VCNotification@@@@V?$allocator@V?$SmartPointer@VCNotification@@@@@std@@@std@@QEAAXAEBV?$SmartPointer@VCNotification@@@@@Z; std::list<SmartPointer<CNotification>>::push_back(SmartPointer<CNotification> const &)
0x180056779  jmp     short loc_180056793
0x18005677b  mov     rdx, rbx
0x18005677e  mov     rcx, [rsp+78h+arg_8]
0x180056786  call    ??4?$SmartPointer@VINotification@@@@QEAAAEAV0@PEAVINotification@@@Z; SmartPointer<INotification>::operator=(INotification *)
0x18005678b  mov     [rsp+78h+arg_0], 1
0x180056793  mov     eax, [rsp+78h+arg_10]
0x18005679a  inc     eax
0x18005679c  jmp     loc_1800564D5
0x1800567a1  lea     rcx, [rsp+78h+var_40]; this
0x1800567a6  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x1800567ab  nop
0x1800567ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800567b3  cmp     rcx, r15
0x1800567b6  jz      short loc_1800567DD
0x1800567b8  test    byte ptr [rcx+6Ch], 4
0x1800567bc  jz      short loc_1800567DD
0x1800567be  cmp     byte ptr [rcx+69h], 4
0x1800567c2  jb      short loc_1800567DD
0x1800567c4  mov     edx, 172h
0x1800567c9  mov     r9d, edi
0x1800567cc  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x1800567d3  mov     rcx, [rcx+60h]
0x1800567d7  call    WPP_SF_d
0x1800567dc  nop
0x1800567dd  lea     rcx, [rsp+78h+var_48]
0x1800567e2  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x1800567e7  mov     eax, edi
0x1800567e9  jmp     short loc_18005680B
0x1800567eb  lea     rcx, [rsp+78h+var_48]
0x1800567f0  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x1800567f5  mov     eax, 306h
0x1800567fa  jmp     short loc_18005680B
0x1800567fc  lea     rcx, [rsp+78h+var_48]
0x180056801  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x180056806  mov     eax, 0Eh
0x18005680b  add     rsp, 50h
0x18005680f  pop     r15
0x180056811  pop     r14
0x180056813  pop     r13
0x180056815  pop     rdi
0x180056816  pop     rbx
0x180056817  retn
```
