# CCacheContainer::DeleteGroup(unsigned __int64,ulong)

- ea: `0x1801a5788`
- end: `0x1801a5af1`
- name: `?DeleteGroup@CCacheContainer@@QEAAJ_KK@Z`
- size: `873`
- prototype: `__int64 __fastcall(CCacheContainer *__hidden this, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1801a6e50`

## callees

- `0x180023514`
- `0x180023850`
- `0x180025910`
- `0x18007ec9c`
- `0x180083d00`
- `0x180083dac`
- `0x180085460`
- `0x1800b48c0`
- `0x1800b5bdc`
- `0x1800f0e58`
- `0x1801454d4`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801a5788`
- `0x1801a64d0`
- `0x1801ac950`
- `0x1801cc8ec`
- `0x1801e1790`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801a5a8c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801a5a8c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801a586a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801a586a`
- `ESENT!JetCommitTransaction` at `0x1801a59ab`
- `ESENT!JetCommitTransaction` at `0x1801a59fb`
- `ESENT!JetCommitTransaction` at `0x1801a59ab`
- `ESENT!JetCommitTransaction` at `0x1801a59fb`
- `ESENT!JetRollback` at `0x1801a5a67`
- `ESENT!JetRollback` at `0x1801a5a67`
- `ESENT!JetBeginTransaction` at `0x1801a58fc`
- `ESENT!JetBeginTransaction` at `0x1801a58fc`
- `ESENT!JetMove` at `0x1801a58cf`
- `ESENT!JetMove` at `0x1801a58cf`

## pseudocode

```c
__int64 __fastcall CCacheContainer::DeleteGroup(CCacheContainer *this, unsigned __int64 a2, int a3)
{
  int v4; // esi
  __int64 v7; // rcx
  CContainerProps **v8; // rbx
  int updated; // edi
  JET_SESID *v10; // r15
  int v11; // r14d
  int i; // r8d
  JET_ERR v13; // eax
  JET_ERR v14; // eax
  int v15; // eax
  JET_ERR v16; // eax
  JET_ERR v17; // eax
  char v19; // [rsp+38h] [rbp-C8h]
  struct CJetContext *v20; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v21[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v22; // [rsp+58h] [rbp-A8h] BYREF
  int v23; // [rsp+5Ch] [rbp-A4h] BYREF
  _BYTE v24[192]; // [rsp+60h] [rbp-A0h] BYREF

  v4 = 0;
  v19 = a3;
  v21[1] = 0;
  v20 = 0;
  v21[0] = &Data;
  memset_0(v24, 0, sizeof(v24));
  v22 = 0;
  v23 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qid(v7, 59, &WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids, this, a2, a3);
  v8 = (CContainerProps **)((char *)this + 40);
  updated = CCacheContainer::RequireAccess(this, 2u);
  if ( updated >= 0 )
  {
    updated = CContainerProps::UpdateLastAccessTime(*v8);
    if ( updated >= 0 )
    {
      AcquireSRWLockExclusive((PSRWLOCK)(*((_QWORD *)*v8 + 18) + 8LL));
      v4 = 1;
      if ( !(unsigned int)CContainerProps::IsGroupValid(*v8, a2) )
      {
        updated = -2147024894;
        goto LABEL_34;
      }
      updated = CContainerProps::AcquireEntryContext(*v8, &v20);
      if ( updated >= 0 )
      {
        v10 = (JET_SESID *)v20;
        v11 = 0;
        for ( i = 0x80000000; ; i = 1 )
        {
          v13 = JetMove(v10[2], v10[4], i, 0);
          if ( v13 == -1603 )
          {
            updated = CContainerProps::DeleteGroup(*v8, a2);
LABEL_32:
            if ( v11 )
              JetRollback(v10[2], 0);
            goto LABEL_34;
          }
          updated = HRESULTFromJET_ERR(v13, 1);
          if ( updated < 0 )
            goto LABEL_32;
          if ( !v11 )
          {
            v14 = JetBeginTransaction(v10[2]);
            updated = HRESULTFromJET_ERR(v14, 1);
            if ( updated < 0 )
              goto LABEL_34;
            v11 = 1;
          }
          Free_ENTRY_INFO((struct ENTRY_INFO *)v24);
          updated = GetEntryInfoAtCursor(v10[2], v10[4], *(unsigned int **)(v10[5] + 8), (struct ENTRY_INFO *)v24);
          if ( updated < 0 )
            goto LABEL_32;
          v15 = CCacheContainer::UnsetUrlGroupAtCursor(
                  this,
                  (struct CJetContext *)v10,
                  (struct ENTRY_INFO *)v24,
                  a2,
                  &v22);
          updated = v15;
          if ( v15 != -2147024894 )
          {
            if ( v15 < 0 )
              goto LABEL_32;
            if ( (v19 & 1) == 0 || !v22 )
              goto LABEL_23;
            updated = CCacheContainer::DeleteEntryAtCursor(
                        this,
                        (struct CJetContext *)v10,
                        (struct ENTRY_INFO *)v24,
                        &v23);
            if ( updated < 0 )
              goto LABEL_32;
            v16 = JetCommitTransaction(v10[2], 1u);
            updated = HRESULTFromJET_ERR(v16, 1);
            if ( updated < 0 )
              goto LABEL_32;
            v11 = 0;
            if ( v23 )
              break;
          }
LABEL_26:
          ;
        }
        updated = CContainerProps::DeleteEntryFile(*v8, (struct ENTRY_INFO *)v24, 1, 1, 1, 0);
        if ( updated < 0 )
          goto LABEL_34;
LABEL_23:
        if ( v11 )
        {
          v17 = JetCommitTransaction(v10[2], 1u);
          updated = HRESULTFromJET_ERR(v17, 1);
          if ( updated < 0 )
            goto LABEL_32;
          v11 = 0;
        }
        goto LABEL_26;
      }
    }
  }
LABEL_34:
  CContainerProps::ReleaseEntryContext(*v8, &v20);
  if ( v4 )
    ReleaseSRWLockExclusive((PSRWLOCK)(*((_QWORD *)*v8 + 18) + 8LL));
  Free_ENTRY_INFO((struct ENTRY_INFO *)v24);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 60, &WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids, (unsigned int)updated);
  CWxString::_Release((CWxString *)v21);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1801a5788  mov     [rsp-8+arg_10], rbx
0x1801a578d  push    rbp
0x1801a578e  push    rsi
0x1801a578f  push    rdi
0x1801a5790  push    r12
0x1801a5792  push    r13
0x1801a5794  push    r14
0x1801a5796  push    r15
0x1801a5798  lea     rbp, [rsp-30h]
0x1801a579d  sub     rsp, 130h
0x1801a57a4  mov     rax, cs:__security_cookie
0x1801a57ab  xor     rax, rsp
0x1801a57ae  mov     [rbp+60h+var_40], rax
0x1801a57b2  mov     ebx, r8d
0x1801a57b5  mov     [rsp+160h+var_12C], 0
0x1801a57bd  xor     esi, esi
0x1801a57bf  mov     dword ptr [rsp+160h+var_128], ebx
0x1801a57c3  mov     r12, rdx
0x1801a57c6  mov     [rsp+160h+var_110], rsi
0x1801a57cb  mov     r13, rcx
0x1801a57ce  mov     [rsp+160h+var_120], rsi
0x1801a57d3  lea     rax, Data
0x1801a57da  xor     edx, edx; Val
0x1801a57dc  mov     r8d, 0C0h; Size
0x1801a57e2  mov     [rsp+160h+var_118], rax
0x1801a57e7  lea     rcx, [rsp+160h+var_100]; void *
0x1801a57ec  call    memset_0
0x1801a57f1  mov     [rsp+160h+var_108], esi
0x1801a57f5  mov     [rsp+160h+var_104], esi
0x1801a57f9  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801a5800  jz      short loc_1801A581D
0x1801a5802  lea     edx, [rsi+3Bh]
0x1801a5805  mov     [rsp+160h+var_138], ebx
0x1801a5809  mov     r9, r13
0x1801a580c  mov     [rsp+160h+var_140], r12
0x1801a5811  lea     r8, WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids
0x1801a5818  call    WPP_SF_qid
0x1801a581d  mov     edx, 2; unsigned int
0x1801a5822  mov     rcx, r13; this
0x1801a5825  call    ?RequireAccess@CCacheContainer@@AEAAJK@Z; CCacheContainer::RequireAccess(ulong)
0x1801a582a  lea     rbx, [r13+28h]
0x1801a582e  mov     edi, eax
0x1801a5830  test    eax, eax
0x1801a5832  jns     short loc_1801A5841
0x1801a5834  mov     [rsp+160h+var_12C], 80Fh
0x1801a583c  jmp     loc_1801A5A6D
0x1801a5841  mov     rcx, [rbx]; this
0x1801a5844  call    ?UpdateLastAccessTime@CContainerProps@@QEAAJXZ; CContainerProps::UpdateLastAccessTime(void)
0x1801a5849  mov     edi, eax
0x1801a584b  test    eax, eax
0x1801a584d  jns     short loc_1801A585C
0x1801a584f  mov     [rsp+160h+var_12C], 814h
0x1801a5857  jmp     loc_1801A5A6D
0x1801a585c  mov     rax, [rbx]
0x1801a585f  mov     rcx, [rax+90h]
0x1801a5866  add     rcx, 8; SRWLock
0x1801a586a  call    cs:__imp_AcquireSRWLockExclusive
0x1801a5870  mov     rcx, [rbx]; this
0x1801a5873  mov     rdx, r12; unsigned __int64
0x1801a5876  mov     esi, 1
0x1801a587b  call    ?IsGroupValid@CContainerProps@@QEAAH_K@Z; CContainerProps::IsGroupValid(unsigned __int64)
0x1801a5880  test    eax, eax
0x1801a5882  jnz     short loc_1801A5896
0x1801a5884  mov     edi, 80070002h
0x1801a5889  mov     [rsp+160h+var_12C], 81Fh
0x1801a5891  jmp     loc_1801A5A6D
0x1801a5896  mov     rcx, [rbx]; this
0x1801a5899  lea     rdx, [rsp+160h+var_120]; struct CJetContext **
0x1801a589e  call    ?AcquireEntryContext@CContainerProps@@QEAAJPEAPEAVCJetContext@@@Z; CContainerProps::AcquireEntryContext(CJetContext * *)
0x1801a58a3  mov     edi, eax
0x1801a58a5  test    eax, eax
0x1801a58a7  jns     short loc_1801A58B6
0x1801a58a9  mov     [rsp+160h+var_12C], 824h
0x1801a58b1  jmp     loc_1801A5A6D
0x1801a58b6  mov     r15, [rsp+160h+var_120]
0x1801a58bb  xor     r14d, r14d
0x1801a58be  mov     r8d, 80000000h; cRow
0x1801a58c4  mov     rdx, [r15+20h]; tableid
0x1801a58c8  xor     r9d, r9d; grbit
0x1801a58cb  mov     rcx, [r15+10h]; sesid
0x1801a58cf  call    cs:__imp_JetMove
0x1801a58d5  cmp     eax, 0FFFFF9BDh
0x1801a58da  jz      loc_1801A5A43
0x1801a58e0  mov     edx, esi; int
0x1801a58e2  mov     ecx, eax; int
0x1801a58e4  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801a58e9  mov     edi, eax
0x1801a58eb  test    eax, eax
0x1801a58ed  js      loc_1801A5A5C
0x1801a58f3  test    r14d, r14d
0x1801a58f6  jnz     short loc_1801A5918
0x1801a58f8  mov     rcx, [r15+10h]; sesid
0x1801a58fc  call    cs:__imp_JetBeginTransaction
0x1801a5902  mov     ecx, eax; int
0x1801a5904  mov     edx, esi; int
0x1801a5906  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801a590b  mov     edi, eax
0x1801a590d  test    eax, eax
0x1801a590f  js      loc_1801A5A6D
0x1801a5915  mov     r14d, esi
0x1801a5918  lea     rcx, [rsp+160h+var_100]; struct ENTRY_INFO *
0x1801a591d  call    ?Free_ENTRY_INFO@@YAXPEAUENTRY_INFO@@@Z; Free_ENTRY_INFO(ENTRY_INFO *)
0x1801a5922  mov     r8, [r15+28h]
0x1801a5926  lea     r9, [rsp+160h+var_100]; struct ENTRY_INFO *
0x1801a592b  mov     rdx, [r15+20h]; tableid
0x1801a592f  mov     rcx, [r15+10h]; sesid
0x1801a5933  mov     r8, [r8+8]; unsigned int *
0x1801a5937  call    ?GetEntryInfoAtCursor@@YAJ_K0PEAKPEAUENTRY_INFO@@@Z; GetEntryInfoAtCursor(unsigned __int64,unsigned __int64,ulong *,ENTRY_INFO *)
0x1801a593c  mov     edi, eax
0x1801a593e  test    eax, eax
0x1801a5940  js      loc_1801A5A39
0x1801a5946  lea     rax, [rsp+160h+var_108]
0x1801a594b  mov     r9, r12; unsigned __int64
0x1801a594e  lea     r8, [rsp+160h+var_100]; struct ENTRY_INFO *
0x1801a5953  mov     [rsp+160h+var_140], rax; int *
0x1801a5958  mov     rdx, r15; struct CJetContext *
0x1801a595b  mov     rcx, r13; this
0x1801a595e  call    ?UnsetUrlGroupAtCursor@CCacheContainer@@AEAAJPEAVCJetContext@@PEAUENTRY_INFO@@_KPEAH@Z; CCacheContainer::UnsetUrlGroupAtCursor(CJetContext *,ENTRY_INFO *,unsigned __int64,int *)
0x1801a5963  mov     edi, eax
0x1801a5965  cmp     eax, 80070002h
0x1801a596a  jz      loc_1801A5A13
0x1801a5970  test    eax, eax
0x1801a5972  js      loc_1801A5A2F
0x1801a5978  test    [rsp+160h+var_128], sil
0x1801a597d  jz      short loc_1801A59F0
0x1801a597f  cmp     [rsp+160h+var_108], 0
0x1801a5984  jz      short loc_1801A59F0
0x1801a5986  lea     r9, [rsp+160h+var_104]; int *
0x1801a598b  mov     rdx, r15; struct CJetContext *
0x1801a598e  lea     r8, [rsp+160h+var_100]; struct ENTRY_INFO *
0x1801a5993  mov     rcx, r13; this
0x1801a5996  call    ?DeleteEntryAtCursor@CCacheContainer@@AEAAJPEAVCJetContext@@PEAUENTRY_INFO@@PEAH@Z; CCacheContainer::DeleteEntryAtCursor(CJetContext *,ENTRY_INFO *,int *)
0x1801a599b  mov     edi, eax
0x1801a599d  test    eax, eax
0x1801a599f  js      loc_1801A5A25
0x1801a59a5  mov     rcx, [r15+10h]; sesid
0x1801a59a9  mov     edx, esi; grbit
0x1801a59ab  call    cs:__imp_JetCommitTransaction
0x1801a59b1  mov     ecx, eax; int
0x1801a59b3  mov     edx, esi; int
0x1801a59b5  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801a59ba  mov     edi, eax
0x1801a59bc  test    eax, eax
0x1801a59be  js      loc_1801A5A5C
0x1801a59c4  xor     r14d, r14d
0x1801a59c7  cmp     [rsp+160h+var_104], r14d
0x1801a59cc  jz      short loc_1801A5A13
0x1801a59ce  mov     rcx, [rbx]; this
0x1801a59d1  lea     rdx, [rsp+160h+var_100]; struct ENTRY_INFO *
0x1801a59d6  mov     [rsp+160h+var_138], r14d; int
0x1801a59db  mov     r9d, esi; int
0x1801a59de  mov     r8d, esi; int
0x1801a59e1  mov     dword ptr [rsp+160h+var_140], esi; int
0x1801a59e5  call    ?DeleteEntryFile@CContainerProps@@QEAAJPEAUENTRY_INFO@@HHHH@Z; CContainerProps::DeleteEntryFile(ENTRY_INFO *,int,int,int,int)
0x1801a59ea  mov     edi, eax
0x1801a59ec  test    eax, eax
0x1801a59ee  js      short loc_1801A5A1B
0x1801a59f0  test    r14d, r14d
0x1801a59f3  jz      short loc_1801A5A13
0x1801a59f5  mov     rcx, [r15+10h]; sesid
0x1801a59f9  mov     edx, esi; grbit
0x1801a59fb  call    cs:__imp_JetCommitTransaction
0x1801a5a01  mov     ecx, eax; int
0x1801a5a03  mov     edx, esi; int
0x1801a5a05  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801a5a0a  mov     edi, eax
0x1801a5a0c  test    eax, eax
0x1801a5a0e  js      short loc_1801A5A5C
0x1801a5a10  xor     r14d, r14d
0x1801a5a13  mov     r8d, esi
0x1801a5a16  jmp     loc_1801A58C4
0x1801a5a1b  mov     [rsp+160h+var_12C], 85Dh
0x1801a5a23  jmp     short loc_1801A5A6D
0x1801a5a25  mov     [rsp+160h+var_12C], 850h
0x1801a5a2d  jmp     short loc_1801A5A5C
0x1801a5a2f  mov     [rsp+160h+var_12C], 843h
0x1801a5a37  jmp     short loc_1801A5A5C
0x1801a5a39  mov     [rsp+160h+var_12C], 836h
0x1801a5a41  jmp     short loc_1801A5A5C
0x1801a5a43  mov     rcx, [rbx]; this
0x1801a5a46  mov     rdx, r12; unsigned __int64
0x1801a5a49  call    ?DeleteGroup@CContainerProps@@QEAAJ_K@Z; CContainerProps::DeleteGroup(unsigned __int64)
0x1801a5a4e  mov     edi, eax
0x1801a5a50  test    eax, eax
0x1801a5a52  jns     short loc_1801A5A5C
0x1801a5a54  mov     [rsp+160h+var_12C], 86Bh
0x1801a5a5c  test    r14d, r14d
0x1801a5a5f  jz      short loc_1801A5A6D
0x1801a5a61  mov     rcx, [r15+10h]; sesid
0x1801a5a65  xor     edx, edx; grbit
0x1801a5a67  call    cs:__imp_JetRollback
0x1801a5a6d  mov     rcx, [rbx]; this
0x1801a5a70  lea     rdx, [rsp+160h+var_120]; struct CJetContext **
0x1801a5a75  call    ?ReleaseEntryContext@CContainerProps@@QEAAXPEAPEAVCJetContext@@@Z; CContainerProps::ReleaseEntryContext(CJetContext * *)
0x1801a5a7a  test    esi, esi
0x1801a5a7c  jz      short loc_1801A5A92
0x1801a5a7e  mov     rax, [rbx]
0x1801a5a81  mov     rcx, [rax+90h]
0x1801a5a88  add     rcx, 8; SRWLock
0x1801a5a8c  call    cs:__imp_ReleaseSRWLockExclusive
0x1801a5a92  lea     rcx, [rsp+160h+var_100]; struct ENTRY_INFO *
0x1801a5a97  call    ?Free_ENTRY_INFO@@YAXPEAUENTRY_INFO@@@Z; Free_ENTRY_INFO(ENTRY_INFO *)
0x1801a5a9c  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801a5aa3  jz      short loc_1801A5ABE
0x1801a5aa5  mov     edx, 3Ch ; '<'
0x1801a5aaa  lea     r8, WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids
0x1801a5ab1  mov     ecx, 40Ch
0x1801a5ab6  mov     r9d, edi
0x1801a5ab9  call    WPP_SF_d
0x1801a5abe  lea     rcx, [rsp+160h+var_118]; this
0x1801a5ac3  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1801a5ac8  mov     eax, edi
0x1801a5aca  mov     rcx, [rbp+60h+var_40]
0x1801a5ace  xor     rcx, rsp; StackCookie
0x1801a5ad1  call    __security_check_cookie
0x1801a5ad6  mov     rbx, [rsp+160h+arg_10]
0x1801a5ade  add     rsp, 130h
0x1801a5ae5  pop     r15
0x1801a5ae7  pop     r14
0x1801a5ae9  pop     r13
0x1801a5aeb  pop     r12
0x1801a5aed  pop     rdi
0x1801a5aee  pop     rsi
0x1801a5aef  pop     rbp
0x1801a5af0  retn
```
