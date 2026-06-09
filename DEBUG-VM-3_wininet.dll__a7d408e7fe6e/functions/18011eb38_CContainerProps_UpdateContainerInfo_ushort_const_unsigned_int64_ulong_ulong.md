# CContainerProps::UpdateContainerInfo(ushort const *,unsigned __int64,ulong,ulong)

- ea: `0x18011eb38`
- end: `0x18011ee4a`
- name: `?UpdateContainerInfo@CContainerProps@@QEAAJPEBG_KKK@Z`
- size: `786`
- prototype: `int(CContainerProps *__hidden this, const unsigned __int16 *, unsigned __int64, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001f5fc`

## callees

- `0x180021360`
- `0x18007ec9c`
- `0x180086300`
- `0x1800e28e0`
- `0x1800ee168`
- `0x1800eed94`
- `0x1800fa844`
- `0x18011eb38`
- `0x18012ad34`
- `0x18014a7a0`
- `0x1801e1790`
- `0x1801e5934`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18011ebc9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18011edb7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18011ebc9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18011edb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18011ebff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18011ebff`
- `ESENT!JetCommitTransaction` at `0x18011ee21`
- `ESENT!JetCommitTransaction` at `0x18011ee21`
- `ESENT!JetUpdate` at `0x18011edfa`
- `ESENT!JetUpdate` at `0x18011edfa`
- `ESENT!JetPrepareUpdate` at `0x18011ecf7`
- `ESENT!JetPrepareUpdate` at `0x18011ed49`
- `ESENT!JetPrepareUpdate` at `0x18011ecf7`
- `ESENT!JetPrepareUpdate` at `0x18011ed49`
- `ESENT!JetRollback` at `0x18011eccc`
- `ESENT!JetRollback` at `0x18011eccc`
- `ESENT!JetBeginTransaction` at `0x18011ec93`
- `ESENT!JetBeginTransaction` at `0x18011ec93`

## pseudocode

```c
__int64 __fastcall CContainerProps::UpdateContainerInfo(
        CContainerProps *this,
        const unsigned __int16 *a2,
        __int64 a3,
        int a4,
        unsigned int a5)
{
  int v7; // ebx
  CCacheStore **v8; // rsi
  unsigned int v9; // edi
  int v11; // eax
  unsigned int v12; // r9d
  JET_SESID *v13; // r14
  JET_ERR v14; // eax
  int v15; // eax
  JET_ERR v16; // eax
  JET_ERR v17; // eax
  JET_ERR v18; // eax
  CJetContext *v19; // [rsp+48h] [rbp-19h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+50h] [rbp-11h] BYREF
  __int64 v21; // [rsp+58h] [rbp-9h]
  int v22; // [rsp+60h] [rbp-1h] BYREF
  __int64 v23; // [rsp+68h] [rbp+7h] BYREF

  v23 = a3;
  v22 = a4;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 32);
  v21 = 0;
  v19 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
  {
    WPP_SF_Sidd((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a2, a3, a4, a5);
    a3 = v23;
    a4 = v22;
  }
  if ( *((_QWORD *)this + 10) == a3
    && *((_DWORD *)this + 23) == a4
    && !(unsigned int)_o__wcsicmp(*((_QWORD *)this + 13), a2) )
  {
    v7 = 0;
    v8 = (CCacheStore **)((char *)this + 24);
    v9 = 0;
    goto LABEL_7;
  }
  AutoCritSec::Lock((AutoCritSec *)&lpCriticalSection);
  v8 = (CCacheStore **)((char *)this + 24);
  v11 = CCacheStore::AcquireContainerContext(*((CCacheStore **)this + 3), &v19);
  v7 = v11;
  if ( v11 < 0
    || (v13 = (JET_SESID *)v19, v11 = CJetContext::SetCurrentIndex(v19, 0, L"ContainerIdIndex", v12), v7 = v11, v11 < 0)
    || (v14 = JetBeginTransaction(v13[2]), v11 = HRESULTFromJET_ERR(v14, 1), v7 = v11, v11 < 0) )
  {
    v9 = v11;
    goto LABEL_7;
  }
  v15 = SeekToContainer((struct CJetContext *)v13, *((_QWORD *)this + 1));
  v7 = v15;
  if ( v15 < 0 )
    goto LABEL_18;
  if ( v15 )
  {
    v7 = -2147418113;
    goto LABEL_22;
  }
  v16 = JetPrepareUpdate(v13[2], v13[4], 2u);
  v15 = HRESULTFromJET_ERR(v16, 1);
  v7 = v15;
  if ( v15 < 0 )
  {
LABEL_18:
    v9 = v15;
LABEL_19:
    JetRollback(v13[2], 0);
    goto LABEL_7;
  }
  if ( v22 != *((_DWORD *)this + 23) && (v7 = CJetContext::SetBasicColumn((CJetContext *)v13, 4u, &v22, 4u), v7 < 0)
    || a5 != *((_DWORD *)this + 24) && (v7 = CJetContext::SetBasicColumn((CJetContext *)v13, 0xCu, &a5, 4u), v7 < 0)
    || v23 != *((_QWORD *)this + 10) && (v7 = CJetContext::SetBasicColumn((CJetContext *)v13, 6u, &v23, 8u), v7 < 0)
    || (unsigned int)_o__wcsicmp(*((_QWORD *)this + 13), a2)
    && (v7 = CJetContext::SetStringColumn((CJetContext *)v13, 7u, a2), v7 < 0)
    || (v17 = JetUpdate(v13[2], v13[4], 0, 0, 0), v7 = HRESULTFromJET_ERR(v17, 1), v7 < 0) )
  {
    v9 = v7;
    JetPrepareUpdate(v13[2], v13[4], 3u);
    goto LABEL_19;
  }
  v18 = JetCommitTransaction(v13[2], 1u);
  v7 = HRESULTFromJET_ERR(v18, 1);
  if ( v7 < 0 )
  {
LABEL_22:
    v9 = v7;
    goto LABEL_19;
  }
  *((_QWORD *)this + 10) = v23;
  v9 = v7;
LABEL_7:
  CCacheStore::ReleaseContainerContext(*v8, &v19);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 30, &WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids, (unsigned int)v7);
  if ( (_DWORD)v21 && lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  return v9;
}

```

## disassembly

```asm
0x18011eb38  push    rbp
0x18011eb3a  push    rbx
0x18011eb3b  push    rsi
0x18011eb3c  push    rdi
0x18011eb3d  push    r14
0x18011eb3f  push    r15
0x18011eb41  lea     rbp, [rsp-27h]
0x18011eb46  sub     rsp, 88h
0x18011eb4d  mov     rax, cs:__security_cookie
0x18011eb54  xor     rax, rsp
0x18011eb57  mov     [rbp+4Fh+var_40], rax
0x18011eb5b  lea     rax, [rcx+20h]
0x18011eb5f  mov     [rbp+4Fh+var_48], r8
0x18011eb63  mov     [rbp+4Fh+var_50], r9d
0x18011eb67  mov     r15, rdx
0x18011eb6a  mov     [rbp+4Fh+lpCriticalSection], rax
0x18011eb6e  mov     rdi, rcx
0x18011eb71  mov     [rbp+4Fh+var_6C], 0
0x18011eb78  mov     [rbp+4Fh+var_58], 0
0x18011eb80  mov     [rbp+4Fh+var_68], 0
0x18011eb88  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18011eb8f  jz      short loc_18011EBB2
0x18011eb91  mov     eax, [rbp+4Fh+arg_20]
0x18011eb94  mov     [rsp+0B0h+var_80], eax
0x18011eb98  mov     [rsp+0B0h+var_88], r9d
0x18011eb9d  mov     r9, rdx
0x18011eba0  mov     [rsp+0B0h+pcbActual], r8
0x18011eba5  call    WPP_SF_Sidd
0x18011ebaa  mov     r8, [rbp+4Fh+var_48]
0x18011ebae  mov     r9d, [rbp+4Fh+var_50]
0x18011ebb2  cmp     [rdi+50h], r8
0x18011ebb6  jnz     loc_18011EC3E
0x18011ebbc  cmp     [rdi+5Ch], r9d
0x18011ebc0  jnz     short loc_18011EC3E
0x18011ebc2  mov     rcx, [rdi+68h]
0x18011ebc6  mov     rdx, r15
0x18011ebc9  call    cs:__imp__o__wcsicmp
0x18011ebcf  test    eax, eax
0x18011ebd1  jnz     short loc_18011EC3E
0x18011ebd3  xor     ebx, ebx
0x18011ebd5  lea     rsi, [rdi+18h]
0x18011ebd9  xor     edi, edi
0x18011ebdb  mov     rcx, [rsi]; this
0x18011ebde  lea     rdx, [rbp+4Fh+var_68]; struct CJetContext **
0x18011ebe2  call    ?ReleaseContainerContext@CCacheStore@@QEAAXPEAPEAVCJetContext@@@Z; CCacheStore::ReleaseContainerContext(CJetContext * *)
0x18011ebe7  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18011ebee  jnz     short loc_18011EC23
0x18011ebf0  cmp     dword ptr [rbp+4Fh+var_58], 0
0x18011ebf4  jz      short loc_18011EC05
0x18011ebf6  mov     rcx, [rbp+4Fh+lpCriticalSection]; lpCriticalSection
0x18011ebfa  test    rcx, rcx
0x18011ebfd  jz      short loc_18011EC05
0x18011ebff  call    cs:__imp_LeaveCriticalSection
0x18011ec05  mov     eax, edi
0x18011ec07  mov     rcx, [rbp+4Fh+var_40]
0x18011ec0b  xor     rcx, rsp; StackCookie
0x18011ec0e  call    __security_check_cookie
0x18011ec13  add     rsp, 88h
0x18011ec1a  pop     r15
0x18011ec1c  pop     r14
0x18011ec1e  pop     rdi
0x18011ec1f  pop     rsi
0x18011ec20  pop     rbx
0x18011ec21  pop     rbp
0x18011ec22  retn
0x18011ec23  mov     edx, 1Eh
0x18011ec28  lea     r8, WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids
0x18011ec2f  mov     ecx, 40Ch
0x18011ec34  mov     r9d, ebx
0x18011ec37  call    WPP_SF_d
0x18011ec3c  jmp     short loc_18011EBF0
0x18011ec3e  lea     rcx, [rbp+4Fh+lpCriticalSection]; this
0x18011ec42  call    ?Lock@AutoCritSec@@QEAAXXZ; AutoCritSec::Lock(void)
0x18011ec47  lea     rsi, [rdi+18h]
0x18011ec4b  mov     rcx, [rsi]; this
0x18011ec4e  lea     rdx, [rbp+4Fh+var_68]; struct CJetContext **
0x18011ec52  call    ?AcquireContainerContext@CCacheStore@@QEAAJPEAPEAVCJetContext@@@Z; CCacheStore::AcquireContainerContext(CJetContext * *)
0x18011ec57  mov     ebx, eax
0x18011ec59  test    eax, eax
0x18011ec5b  jns     short loc_18011EC6B
0x18011ec5d  mov     [rbp+4Fh+var_6C], 3BAh
0x18011ec64  mov     edi, eax
0x18011ec66  jmp     loc_18011EBDB
0x18011ec6b  mov     r14, [rbp+4Fh+var_68]
0x18011ec6f  lea     r8, aContaineridind; "ContainerIdIndex"
0x18011ec76  mov     rcx, r14; this
0x18011ec79  xor     edx, edx; unsigned int
0x18011ec7b  call    ?SetCurrentIndex@CJetContext@@QEAAJKPEBGK@Z; CJetContext::SetCurrentIndex(ulong,ushort const *,ulong)
0x18011ec80  mov     ebx, eax
0x18011ec82  test    eax, eax
0x18011ec84  jns     short loc_18011EC8F
0x18011ec86  mov     [rbp+4Fh+var_6C], 3BCh
0x18011ec8d  jmp     short loc_18011EC64
0x18011ec8f  mov     rcx, [r14+10h]; sesid
0x18011ec93  call    cs:__imp_JetBeginTransaction
0x18011ec99  mov     ecx, eax; int
0x18011ec9b  mov     edx, 1; int
0x18011eca0  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x18011eca5  mov     ebx, eax
0x18011eca7  test    eax, eax
0x18011eca9  js      short loc_18011EC64
0x18011ecab  mov     rdx, [rdi+8]; unsigned __int64
0x18011ecaf  mov     rcx, r14; struct CJetContext *
0x18011ecb2  call    ?SeekToContainer@@YAJPEAVCJetContext@@_K@Z; SeekToContainer(CJetContext *,unsigned __int64)
0x18011ecb7  mov     ebx, eax
0x18011ecb9  test    eax, eax
0x18011ecbb  jns     short loc_18011ECD7
0x18011ecbd  mov     [rbp+4Fh+var_6C], 3C6h
0x18011ecc4  mov     edi, eax
0x18011ecc6  mov     rcx, [r14+10h]; sesid
0x18011ecca  xor     edx, edx; grbit
0x18011eccc  call    cs:__imp_JetRollback
0x18011ecd2  jmp     loc_18011EBDB
0x18011ecd7  jz      short loc_18011ECE9
0x18011ecd9  mov     ebx, 8000FFFFh
0x18011ecde  mov     [rbp+4Fh+var_6C], 3C8h
0x18011ece5  mov     edi, ebx
0x18011ece7  jmp     short loc_18011ECC6
0x18011ece9  mov     rdx, [r14+20h]; tableid
0x18011eced  mov     r8d, 2; prep
0x18011ecf3  mov     rcx, [r14+10h]; sesid
0x18011ecf7  call    cs:__imp_JetPrepareUpdate
0x18011ecfd  mov     ecx, eax; int
0x18011ecff  mov     edx, 1; int
0x18011ed04  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x18011ed09  mov     ebx, eax
0x18011ed0b  test    eax, eax
0x18011ed0d  js      short loc_18011ECC4
0x18011ed0f  mov     eax, [rdi+5Ch]
0x18011ed12  cmp     [rbp+4Fh+var_50], eax
0x18011ed15  jz      short loc_18011ED54
0x18011ed17  mov     r9d, 4; unsigned int
0x18011ed1d  lea     r8, [rbp+4Fh+var_50]; void *
0x18011ed21  mov     edx, r9d; unsigned int
0x18011ed24  mov     rcx, r14; this
0x18011ed27  call    ?SetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::SetBasicColumn(ulong,void *,ulong)
0x18011ed2c  mov     ebx, eax
0x18011ed2e  test    eax, eax
0x18011ed30  jns     short loc_18011ED54
0x18011ed32  mov     [rbp+4Fh+var_6C], 3CFh
0x18011ed39  mov     rdx, [r14+20h]; tableid
0x18011ed3d  mov     r8d, 3; prep
0x18011ed43  mov     rcx, [r14+10h]; sesid
0x18011ed47  mov     edi, ebx
0x18011ed49  call    cs:__imp_JetPrepareUpdate
0x18011ed4f  jmp     loc_18011ECC6
0x18011ed54  mov     eax, [rdi+60h]
0x18011ed57  cmp     [rbp+4Fh+arg_20], eax
0x18011ed5a  jz      short loc_18011ED81
0x18011ed5c  mov     r9d, 4; unsigned int
0x18011ed62  lea     r8, [rbp+4Fh+arg_20]; void *
0x18011ed66  mov     rcx, r14; this
0x18011ed69  lea     edx, [r9+8]; unsigned int
0x18011ed6d  call    ?SetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::SetBasicColumn(ulong,void *,ulong)
0x18011ed72  mov     ebx, eax
0x18011ed74  test    eax, eax
0x18011ed76  jns     short loc_18011ED81
0x18011ed78  mov     [rbp+4Fh+var_6C], 3D4h
0x18011ed7f  jmp     short loc_18011ED39
0x18011ed81  mov     rax, [rdi+50h]
0x18011ed85  cmp     [rbp+4Fh+var_48], rax
0x18011ed89  jz      short loc_18011EDB0
0x18011ed8b  mov     r9d, 8; unsigned int
0x18011ed91  lea     r8, [rbp+4Fh+var_48]; void *
0x18011ed95  mov     rcx, r14; this
0x18011ed98  lea     edx, [r9-2]; unsigned int
0x18011ed9c  call    ?SetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::SetBasicColumn(ulong,void *,ulong)
0x18011eda1  mov     ebx, eax
0x18011eda3  test    eax, eax
0x18011eda5  jns     short loc_18011EDB0
0x18011eda7  mov     [rbp+4Fh+var_6C], 3D9h
0x18011edae  jmp     short loc_18011ED39
0x18011edb0  mov     rcx, [rdi+68h]
0x18011edb4  mov     rdx, r15
0x18011edb7  call    cs:__imp__o__wcsicmp
0x18011edbd  test    eax, eax
0x18011edbf  jz      short loc_18011EDE3
0x18011edc1  mov     r8, r15; unsigned __int16 *
0x18011edc4  mov     edx, 7; unsigned int
0x18011edc9  mov     rcx, r14; this
0x18011edcc  call    ?SetStringColumn@CJetContext@@QEAAJKPEBG@Z; CJetContext::SetStringColumn(ulong,ushort const *)
0x18011edd1  mov     ebx, eax
0x18011edd3  test    eax, eax
0x18011edd5  jns     short loc_18011EDE3
0x18011edd7  mov     [rbp+4Fh+var_6C], 3DEh
0x18011edde  jmp     loc_18011ED39
0x18011ede3  mov     rdx, [r14+20h]; tableid
0x18011ede7  xor     r9d, r9d; cbBookmark
0x18011edea  mov     rcx, [r14+10h]; sesid
0x18011edee  xor     r8d, r8d; pvBookmark
0x18011edf1  mov     [rsp+0B0h+pcbActual], 0; pcbActual
0x18011edfa  call    cs:__imp_JetUpdate
0x18011ee00  mov     r15d, 1
0x18011ee06  mov     ecx, eax; int
0x18011ee08  mov     edx, r15d; int
0x18011ee0b  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x18011ee10  mov     ebx, eax
0x18011ee12  test    eax, eax
0x18011ee14  js      loc_18011ED39
0x18011ee1a  mov     rcx, [r14+10h]; sesid
0x18011ee1e  mov     edx, r15d; grbit
0x18011ee21  call    cs:__imp_JetCommitTransaction
0x18011ee27  mov     ecx, eax; int
0x18011ee29  mov     edx, r15d; int
0x18011ee2c  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x18011ee31  mov     ebx, eax
0x18011ee33  test    eax, eax
0x18011ee35  js      loc_18011ECE5
0x18011ee3b  mov     rax, [rbp+4Fh+var_48]
0x18011ee3f  mov     [rdi+50h], rax
0x18011ee43  mov     edi, ebx
0x18011ee45  jmp     loc_18011EBDB
```
