# CContainerProps::SetLimit(unsigned __int64)

- ea: `0x1801aa824`
- end: `0x1801aaaf2`
- name: `?SetLimit@CContainerProps@@QEAAJ_K@Z`
- size: `718`
- prototype: `__int64 __fastcall(CContainerProps *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1801a5e74`

## callees

- `0x180021360`
- `0x18003fc00`
- `0x18007ec9c`
- `0x180086300`
- `0x180097e10`
- `0x1800e28e0`
- `0x1800eed94`
- `0x1800fa844`
- `0x180112d08`
- `0x18012ad34`
- `0x18014a7a0`
- `0x1801aa824`
- `0x1801e1790`
- `0x1801e3048`

## import_xrefs

- `ESENT!JetCommitTransaction` at `0x1801aaa71`
- `ESENT!JetCommitTransaction` at `0x1801aaa71`
- `ESENT!JetUpdate` at `0x1801aaa54`
- `ESENT!JetUpdate` at `0x1801aaa54`
- `ESENT!JetPrepareUpdate` at `0x1801aa9e9`
- `ESENT!JetPrepareUpdate` at `0x1801aaa32`
- `ESENT!JetPrepareUpdate` at `0x1801aa9e9`
- `ESENT!JetPrepareUpdate` at `0x1801aaa32`
- `ESENT!JetRollback` at `0x1801aa9be`
- `ESENT!JetRollback` at `0x1801aa9be`
- `ESENT!JetBeginTransaction` at `0x1801aa97d`
- `ESENT!JetBeginTransaction` at `0x1801aa97d`

## pseudocode

```c
__int64 __fastcall CContainerProps::SetLimit(CContainerProps *this, __int64 a2)
{
  unsigned __int64 v3; // r8
  CCacheStore **v4; // rsi
  int v5; // ebx
  unsigned int v6; // edi
  int EffectiveLimit; // eax
  unsigned int v9; // r9d
  JET_SESID *v10; // r14
  JET_ERR v11; // eax
  int v12; // eax
  JET_ERR v13; // eax
  JET_ERR v14; // eax
  JET_ERR v15; // eax
  unsigned int v16; // edx
  CCacheStore *v17; // rcx
  unsigned __int64 v18; // r8
  unsigned __int64 v19; // [rsp+30h] [rbp-40h] BYREF
  unsigned __int64 v20; // [rsp+38h] [rbp-38h] BYREF
  CJetContext *v21; // [rsp+40h] [rbp-30h] BYREF
  char *v22; // [rsp+48h] [rbp-28h] BYREF
  __int64 v23; // [rsp+50h] [rbp-20h]
  __int64 v24; // [rsp+58h] [rbp-18h] BYREF

  v24 = a2;
  v22 = (char *)this + 32;
  v19 = 0;
  v23 = 0;
  v21 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qP(1036, 23, &WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids, this, a2);
  AutoCritSec::Lock((AutoCritSec *)&v22);
  v3 = *((_QWORD *)this + 10);
  v4 = (CCacheStore **)((char *)this + 24);
  if ( v24 == v3 )
  {
    v5 = 0;
    v6 = 0;
    goto LABEL_8;
  }
  EffectiveLimit = CCacheStore::GetEffectiveLimit(*v4, *((_DWORD *)this + 22), v3, &v19);
  v5 = EffectiveLimit;
  if ( EffectiveLimit < 0 )
  {
    HIDWORD(v19) = 630;
LABEL_7:
    v6 = EffectiveLimit;
    goto LABEL_8;
  }
  EffectiveLimit = CCacheStore::AcquireContainerContext(*v4, &v21);
  v5 = EffectiveLimit;
  if ( EffectiveLimit < 0 )
  {
    HIDWORD(v19) = 632;
    goto LABEL_7;
  }
  v10 = (JET_SESID *)v21;
  EffectiveLimit = CJetContext::SetCurrentIndex(v21, 0, L"ContainerIdIndex", v9);
  v5 = EffectiveLimit;
  if ( EffectiveLimit < 0 )
  {
    HIDWORD(v19) = 634;
    goto LABEL_7;
  }
  v11 = JetBeginTransaction(v10[2]);
  EffectiveLimit = HRESULTFromJET_ERR(v11, 1);
  v5 = EffectiveLimit;
  if ( EffectiveLimit < 0 )
    goto LABEL_7;
  v12 = SeekToContainer((struct CJetContext *)v10, *((_QWORD *)this + 1));
  v5 = v12;
  if ( v12 < 0 )
  {
    HIDWORD(v19) = 644;
LABEL_20:
    v6 = v12;
LABEL_21:
    JetRollback(v10[2], 0);
    goto LABEL_8;
  }
  if ( v12 )
  {
    v5 = -2147418113;
    HIDWORD(v19) = 646;
LABEL_24:
    v6 = v5;
    goto LABEL_21;
  }
  v13 = JetPrepareUpdate(v10[2], v10[4], 2u);
  v12 = HRESULTFromJET_ERR(v13, 1);
  v5 = v12;
  if ( v12 < 0 )
    goto LABEL_20;
  v5 = CJetContext::SetBasicColumn((CJetContext *)v10, 6u, &v24, 8u);
  if ( v5 < 0 )
  {
    HIDWORD(v19) = 651;
LABEL_28:
    v6 = v5;
    JetPrepareUpdate(v10[2], v10[4], 3u);
    goto LABEL_21;
  }
  v14 = JetUpdate(v10[2], v10[4], 0, 0, 0);
  v5 = HRESULTFromJET_ERR(v14, 1);
  if ( v5 < 0 )
    goto LABEL_28;
  v15 = JetCommitTransaction(v10[2], 1u);
  v5 = HRESULTFromJET_ERR(v15, 1);
  if ( v5 < 0 )
    goto LABEL_24;
  v16 = *((_DWORD *)this + 22);
  v17 = *v4;
  *((_QWORD *)this + 10) = v24;
  v18 = *((_QWORD *)this + 10);
  v20 = 0;
  if ( (int)CCacheStore::GetEffectiveLimit(v17, v16, v18, &v20) >= 0 )
  {
    if ( v20 < v19 && (int)CCacheStore::QueueCleanup(*v4, 1) < 0 )
      HIDWORD(v20) = 598;
  }
  else
  {
    HIDWORD(v20) = 595;
  }
  AutoCritSec::Unlock((AutoCritSec *)&v22);
  v6 = v5;
LABEL_8:
  CCacheStore::ReleaseContainerContext(*v4, &v21);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 24, &WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids, (unsigned int)v5);
  if ( (_DWORD)v23 )
    AutoCritSec::Unlock((AutoCritSec *)&v22);
  return v6;
}

```

## disassembly

```asm
0x1801aa824  mov     [rsp-28h+arg_10], rbx
0x1801aa829  push    rbp
0x1801aa82a  push    rsi
0x1801aa82b  push    rdi
0x1801aa82c  push    r12
0x1801aa82e  push    r14
0x1801aa830  mov     rbp, rsp
0x1801aa833  sub     rsp, 70h
0x1801aa837  mov     rax, cs:__security_cookie
0x1801aa83e  xor     rax, rsp
0x1801aa841  mov     [rbp+var_10], rax
0x1801aa845  mov     [rbp+var_18], rdx
0x1801aa849  lea     rax, [rcx+20h]
0x1801aa84d  mov     dword ptr [rbp+var_40+4], 0
0x1801aa854  mov     r8, rdx
0x1801aa857  mov     [rbp+var_28], rax
0x1801aa85b  mov     rdi, rcx
0x1801aa85e  mov     qword ptr [rbp-40h], 0
0x1801aa866  mov     [rbp+var_20], 0
0x1801aa86e  mov     [rbp+var_30], 0
0x1801aa876  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801aa87d  jz      short loc_1801AA89D
0x1801aa87f  mov     [rsp+70h+pcbActual], r8
0x1801aa884  mov     edx, 17h
0x1801aa889  lea     r8, WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids
0x1801aa890  mov     ecx, 40Ch
0x1801aa895  mov     r9, rdi
0x1801aa898  call    WPP_SF_qP
0x1801aa89d  lea     rcx, [rbp+var_28]; this
0x1801aa8a1  call    ?Lock@AutoCritSec@@QEAAXXZ; AutoCritSec::Lock(void)
0x1801aa8a6  mov     r8, [rdi+50h]; unsigned __int64
0x1801aa8aa  lea     rsi, [rdi+18h]
0x1801aa8ae  cmp     [rbp+var_18], r8
0x1801aa8b2  jnz     short loc_1801AA8BA
0x1801aa8b4  xor     ebx, ebx
0x1801aa8b6  xor     edi, edi
0x1801aa8b8  jmp     short loc_1801AA8D8
0x1801aa8ba  mov     edx, [rdi+58h]; unsigned int
0x1801aa8bd  lea     r9, [rbp+var_40]; unsigned __int64 *
0x1801aa8c1  mov     rcx, [rsi]; this
0x1801aa8c4  call    ?GetEffectiveLimit@CCacheStore@@QEAAJK_KPEA_K@Z; CCacheStore::GetEffectiveLimit(ulong,unsigned __int64,unsigned __int64 *)
0x1801aa8c9  mov     ebx, eax
0x1801aa8cb  test    eax, eax
0x1801aa8cd  jns     short loc_1801AA937
0x1801aa8cf  mov     dword ptr [rbp+var_40+4], 276h
0x1801aa8d6  mov     edi, eax
0x1801aa8d8  mov     rcx, [rsi]; this
0x1801aa8db  lea     rdx, [rbp+var_30]; struct CJetContext **
0x1801aa8df  call    ?ReleaseContainerContext@CCacheStore@@QEAAXPEAPEAVCJetContext@@@Z; CCacheStore::ReleaseContainerContext(CJetContext * *)
0x1801aa8e4  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801aa8eb  jz      short loc_1801AA906
0x1801aa8ed  mov     edx, 18h
0x1801aa8f2  lea     r8, WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids
0x1801aa8f9  mov     ecx, 40Ch
0x1801aa8fe  mov     r9d, ebx
0x1801aa901  call    WPP_SF_d
0x1801aa906  cmp     dword ptr [rbp+var_20], 0
0x1801aa90a  jz      short loc_1801AA915
0x1801aa90c  lea     rcx, [rbp+var_28]; this
0x1801aa910  call    ?Unlock@AutoCritSec@@QEAAXXZ; AutoCritSec::Unlock(void)
0x1801aa915  mov     eax, edi
0x1801aa917  mov     rcx, [rbp+var_10]
0x1801aa91b  xor     rcx, rsp; StackCookie
0x1801aa91e  call    __security_check_cookie
0x1801aa923  mov     rbx, [rsp+70h+arg_10]
0x1801aa92b  add     rsp, 70h
0x1801aa92f  pop     r14
0x1801aa931  pop     r12
0x1801aa933  pop     rdi
0x1801aa934  pop     rsi
0x1801aa935  pop     rbp
0x1801aa936  retn
0x1801aa937  mov     rcx, [rsi]; this
0x1801aa93a  lea     rdx, [rbp+var_30]; struct CJetContext **
0x1801aa93e  call    ?AcquireContainerContext@CCacheStore@@QEAAJPEAPEAVCJetContext@@@Z; CCacheStore::AcquireContainerContext(CJetContext * *)
0x1801aa943  mov     ebx, eax
0x1801aa945  test    eax, eax
0x1801aa947  jns     short loc_1801AA952
0x1801aa949  mov     dword ptr [rbp+var_40+4], 278h
0x1801aa950  jmp     short loc_1801AA8D6
0x1801aa952  mov     r14, [rbp+var_30]
0x1801aa956  lea     r8, aContaineridind; "ContainerIdIndex"
0x1801aa95d  mov     rcx, r14; this
0x1801aa960  xor     edx, edx; unsigned int
0x1801aa962  call    ?SetCurrentIndex@CJetContext@@QEAAJKPEBGK@Z; CJetContext::SetCurrentIndex(ulong,ushort const *,ulong)
0x1801aa967  mov     ebx, eax
0x1801aa969  test    eax, eax
0x1801aa96b  jns     short loc_1801AA979
0x1801aa96d  mov     dword ptr [rbp+var_40+4], 27Ah
0x1801aa974  jmp     loc_1801AA8D6
0x1801aa979  mov     rcx, [r14+10h]; sesid
0x1801aa97d  call    cs:__imp_JetBeginTransaction
0x1801aa983  mov     r12d, 1
0x1801aa989  mov     ecx, eax; int
0x1801aa98b  mov     edx, r12d; int
0x1801aa98e  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801aa993  mov     ebx, eax
0x1801aa995  test    eax, eax
0x1801aa997  js      loc_1801AA8D6
0x1801aa99d  mov     rdx, [rdi+8]; unsigned __int64
0x1801aa9a1  mov     rcx, r14; struct CJetContext *
0x1801aa9a4  call    ?SeekToContainer@@YAJPEAVCJetContext@@_K@Z; SeekToContainer(CJetContext *,unsigned __int64)
0x1801aa9a9  mov     ebx, eax
0x1801aa9ab  test    eax, eax
0x1801aa9ad  jns     short loc_1801AA9C9
0x1801aa9af  mov     dword ptr [rbp+var_40+4], 284h
0x1801aa9b6  mov     edi, eax
0x1801aa9b8  mov     rcx, [r14+10h]; sesid
0x1801aa9bc  xor     edx, edx; grbit
0x1801aa9be  call    cs:__imp_JetRollback
0x1801aa9c4  jmp     loc_1801AA8D8
0x1801aa9c9  jz      short loc_1801AA9DB
0x1801aa9cb  mov     ebx, 8000FFFFh
0x1801aa9d0  mov     dword ptr [rbp+var_40+4], 286h
0x1801aa9d7  mov     edi, ebx
0x1801aa9d9  jmp     short loc_1801AA9B8
0x1801aa9db  mov     rdx, [r14+20h]; tableid
0x1801aa9df  mov     r8d, 2; prep
0x1801aa9e5  mov     rcx, [r14+10h]; sesid
0x1801aa9e9  call    cs:__imp_JetPrepareUpdate
0x1801aa9ef  mov     ecx, eax; int
0x1801aa9f1  mov     edx, r12d; int
0x1801aa9f4  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801aa9f9  mov     ebx, eax
0x1801aa9fb  test    eax, eax
0x1801aa9fd  js      short loc_1801AA9B6
0x1801aa9ff  mov     r9d, 8; unsigned int
0x1801aaa05  lea     r8, [rbp+var_18]; void *
0x1801aaa09  mov     rcx, r14; this
0x1801aaa0c  lea     edx, [r9-2]; unsigned int
0x1801aaa10  call    ?SetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::SetBasicColumn(ulong,void *,ulong)
0x1801aaa15  mov     ebx, eax
0x1801aaa17  test    eax, eax
0x1801aaa19  jns     short loc_1801AAA3D
0x1801aaa1b  mov     dword ptr [rbp+var_40+4], 28Bh
0x1801aaa22  mov     rdx, [r14+20h]; tableid
0x1801aaa26  mov     r8d, 3; prep
0x1801aaa2c  mov     rcx, [r14+10h]; sesid
0x1801aaa30  mov     edi, ebx
0x1801aaa32  call    cs:__imp_JetPrepareUpdate
0x1801aaa38  jmp     loc_1801AA9B8
0x1801aaa3d  mov     rdx, [r14+20h]; tableid
0x1801aaa41  xor     r9d, r9d; cbBookmark
0x1801aaa44  mov     rcx, [r14+10h]; sesid
0x1801aaa48  xor     r8d, r8d; pvBookmark
0x1801aaa4b  mov     [rsp+70h+pcbActual], 0; pcbActual
0x1801aaa54  call    cs:__imp_JetUpdate
0x1801aaa5a  mov     ecx, eax; int
0x1801aaa5c  mov     edx, r12d; int
0x1801aaa5f  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801aaa64  mov     ebx, eax
0x1801aaa66  test    eax, eax
0x1801aaa68  js      short loc_1801AAA22
0x1801aaa6a  mov     rcx, [r14+10h]; sesid
0x1801aaa6e  mov     edx, r12d; grbit
0x1801aaa71  call    cs:__imp_JetCommitTransaction
0x1801aaa77  mov     ecx, eax; int
0x1801aaa79  mov     edx, r12d; int
0x1801aaa7c  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801aaa81  mov     ebx, eax
0x1801aaa83  test    eax, eax
0x1801aaa85  js      loc_1801AA9D7
0x1801aaa8b  mov     rax, [rbp+var_18]
0x1801aaa8f  lea     r9, [rbp+var_38]; unsigned __int64 *
0x1801aaa93  mov     edx, [rdi+58h]; unsigned int
0x1801aaa96  mov     rcx, [rsi]; this
0x1801aaa99  mov     [rdi+50h], rax
0x1801aaa9d  mov     r8, [rdi+50h]; unsigned __int64
0x1801aaaa1  mov     dword ptr [rbp+var_38+4], 0
0x1801aaaa8  mov     [rbp+var_38], 0
0x1801aaab0  call    ?GetEffectiveLimit@CCacheStore@@QEAAJK_KPEA_K@Z; CCacheStore::GetEffectiveLimit(ulong,unsigned __int64,unsigned __int64 *)
0x1801aaab5  test    eax, eax
0x1801aaab7  jns     short loc_1801AAAC2
0x1801aaab9  mov     dword ptr [rbp+var_38+4], 253h
0x1801aaac0  jmp     short loc_1801AAAE2
0x1801aaac2  mov     rax, [rbp+var_40]
0x1801aaac6  cmp     [rbp+var_38], rax
0x1801aaaca  jnb     short loc_1801AAAE2
0x1801aaacc  mov     rcx, [rsi]; this
0x1801aaacf  mov     edx, r12d; int
0x1801aaad2  call    ?QueueCleanup@CCacheStore@@QEAAJH@Z; CCacheStore::QueueCleanup(int)
0x1801aaad7  test    eax, eax
0x1801aaad9  jns     short loc_1801AAAE2
0x1801aaadb  mov     dword ptr [rbp+var_38+4], 256h
0x1801aaae2  lea     rcx, [rbp+var_28]; this
0x1801aaae6  call    ?Unlock@AutoCritSec@@QEAAXXZ; AutoCritSec::Unlock(void)
0x1801aaaeb  mov     edi, ebx
0x1801aaaed  jmp     loc_1801AA8D8
```
