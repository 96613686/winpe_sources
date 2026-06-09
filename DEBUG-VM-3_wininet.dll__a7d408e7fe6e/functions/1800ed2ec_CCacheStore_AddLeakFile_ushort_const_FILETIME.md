# CCacheStore::AddLeakFile(ushort const *,_FILETIME)

- ea: `0x1800ed2ec`
- end: `0x1800ed5e1`
- name: `?AddLeakFile@CCacheStore@@QEAAJPEBGU_FILETIME@@@Z`
- size: `757`
- prototype: `__int64 __fastcall(CCacheStore *__hidden this, const unsigned __int16 *, struct _FILETIME)`
- caller_count: `3`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800b58e4`
- `0x1800b5bdc`
- `0x1800f08f0`

## callees

- `0x18003fc40`
- `0x180040770`
- `0x180041814`
- `0x18007ec9c`
- `0x180085898`
- `0x180086aa4`
- `0x1800ed2ec`
- `0x1800ee168`
- `0x18011a3e4`
- `0x18014a7a0`
- `0x1801e0f30`
- `0x1801e1790`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ed3e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ed3e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ed366`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ed366`
- `ESENT!JetSetColumn` at `0x1800ed511`
- `ESENT!JetSetColumn` at `0x1800ed511`
- `ESENT!JetCommitTransaction` at `0x1800ed56d`
- `ESENT!JetCommitTransaction` at `0x1800ed56d`
- `ESENT!JetUpdate` at `0x1800ed545`
- `ESENT!JetUpdate` at `0x1800ed545`
- `ESENT!JetPrepareUpdate` at `0x1800ed47c`
- `ESENT!JetPrepareUpdate` at `0x1800ed4cd`
- `ESENT!JetPrepareUpdate` at `0x1800ed47c`
- `ESENT!JetPrepareUpdate` at `0x1800ed4cd`
- `ESENT!JetRollback` at `0x1800ed5d6`
- `ESENT!JetRollback` at `0x1800ed5d6`
- `ESENT!JetBeginTransaction` at `0x1800ed450`
- `ESENT!JetBeginTransaction` at `0x1800ed450`

## pseudocode

```c
__int64 __fastcall CCacheStore::AddLeakFile(CCacheStore *this, const unsigned __int16 *a2, struct _FILETIME a3)
{
  int v3; // r15d
  CJetContext *v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // r14
  CJetContext *v8; // rcx
  int v9; // eax
  JET_ERR v10; // edi
  unsigned int v11; // esi
  JET_ERR v13; // eax
  JET_ERR v14; // eax
  int v15; // eax
  JET_ERR v16; // eax
  JET_ERR v17; // eax
  struct CJetContext *v18; // [rsp+48h] [rbp-50h] BYREF
  struct _FILETIME pvData; // [rsp+50h] [rbp-48h] BYREF

  v3 = 0;
  pvData = a3;
  v4 = 0;
  v18 = 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qSi(
      (_DWORD)this,
      32,
      (unsigned int)&WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids,
      (_DWORD)this,
      (__int64)a2,
      a3.dwLowDateTime);
  CCacheStore::StartActivity(this);
  if ( v5 )
  {
    EnterCriticalSection(v5);
    v3 = 1;
  }
  v8 = (CJetContext *)*((_QWORD *)this + 16);
  if ( !v8 )
  {
    v9 = CJetContext::CreateInstance(&v18);
    v10 = v9;
    if ( v9 < 0 )
    {
      v4 = v18;
LABEL_8:
      v11 = v9;
      goto LABEL_9;
    }
    v4 = v18;
    v9 = CJetContext::Initialize(v18, this, L"LeakFiles", 3u, 0, 0);
    v10 = v9;
    if ( v9 < 0 )
      goto LABEL_8;
    *((_QWORD *)this + 16) = v4;
    v8 = v4;
    v4 = 0;
  }
  v13 = JetBeginTransaction(*((_QWORD *)v8 + 2));
  v9 = HRESULTFromJET_ERR(v13, 1);
  v10 = v9;
  if ( v9 < 0 )
    goto LABEL_8;
  v14 = JetPrepareUpdate(*(_QWORD *)(*((_QWORD *)this + 16) + 16LL), *(_QWORD *)(*((_QWORD *)this + 16) + 32LL), 0);
  v15 = HRESULTFromJET_ERR(v14, 1);
  v10 = v15;
  if ( v15 < 0 )
  {
LABEL_27:
    v11 = v15;
    goto LABEL_28;
  }
  v10 = CJetContext::SetStringColumn(*((CJetContext **)this + 16), 1u, a2);
  if ( v10 >= 0 )
  {
    v10 = JetSetColumn(
            *(_QWORD *)(*((_QWORD *)this + 16) + 16LL),
            *(_QWORD *)(*((_QWORD *)this + 16) + 32LL),
            *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 16) + 40LL) + 8LL) + 8LL),
            &pvData,
            8u,
            0,
            0);
    if ( v10 >= 0 )
    {
      v16 = JetUpdate(*(_QWORD *)(*((_QWORD *)this + 16) + 16LL), *(_QWORD *)(*((_QWORD *)this + 16) + 32LL), 0, 0, 0);
      v10 = HRESULTFromJET_ERR(v16, 1);
      if ( v10 >= 0 )
      {
        v17 = JetCommitTransaction(*(_QWORD *)(*((_QWORD *)this + 16) + 16LL), 1u);
        v15 = HRESULTFromJET_ERR(v17, 1);
        v10 = v15;
        if ( v15 >= 0 )
        {
          v10 = CWxWorker::Queue(
                  *((CWxWorker **)this + 30),
                  (int (*)(struct CWxWorker *, struct CWxWorkContext *, unsigned __int64, void *))CCacheStore::DeleteLeakedFilesCallback,
                  0,
                  0,
                  *((_DWORD *)this + 86),
                  0xA4CB800u);
          v11 = v10;
          goto LABEL_9;
        }
        goto LABEL_27;
      }
    }
  }
  v11 = v10;
  JetPrepareUpdate(*(_QWORD *)(*((_QWORD *)this + 16) + 16LL), *(_QWORD *)(*((_QWORD *)this + 16) + 32LL), 3u);
LABEL_28:
  JetRollback(*(_QWORD *)(*((_QWORD *)this + 16) + 16LL), 0);
LABEL_9:
  CCacheStore::EndActivity(this);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 33, &WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids, (unsigned int)v10);
  if ( v4 )
    CJetContext::Release(v4);
  if ( v3 && v5 )
    LeaveCriticalSection(v5);
  return v11;
}

```

## disassembly

```asm
0x1800ed2ec  push    rbx
0x1800ed2ee  push    rbp
0x1800ed2ef  push    rsi
0x1800ed2f0  push    rdi
0x1800ed2f1  push    r13
0x1800ed2f3  push    r14
0x1800ed2f5  push    r15
0x1800ed2f7  sub     rsp, 60h
0x1800ed2fb  mov     rax, cs:__security_cookie
0x1800ed302  xor     rax, rsp
0x1800ed305  mov     [rsp+98h+var_40], rax
0x1800ed30a  xor     r15d, r15d
0x1800ed30d  mov     [rsp+98h+pvData], r8
0x1800ed312  xor     ebx, ebx
0x1800ed314  mov     [rsp+98h+var_54], 0
0x1800ed31c  mov     [rsp+98h+var_50], rbx
0x1800ed321  lea     r14, [rcx+58h]
0x1800ed325  mov     rsi, rdx
0x1800ed328  mov     rbp, rcx
0x1800ed32b  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800ed332  jz      short loc_1800ED350
0x1800ed334  mov     qword ptr [rsp+98h+grbit], r8
0x1800ed339  lea     edx, [rbx+20h]
0x1800ed33c  lea     r8, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids
0x1800ed343  mov     qword ptr [rsp+98h+cbData], rsi
0x1800ed348  mov     r9, rcx
0x1800ed34b  call    WPP_SF_qSi
0x1800ed350  mov     rcx, rbp; this
0x1800ed353  call    ?StartActivity@CCacheStore@@QEAAXXZ; CCacheStore::StartActivity(void)
0x1800ed358  mov     r13d, 1
0x1800ed35e  test    r14, r14
0x1800ed361  jz      short loc_1800ED36F
0x1800ed363  mov     rcx, r14; lpCriticalSection
0x1800ed366  call    cs:__imp_EnterCriticalSection
0x1800ed36c  mov     r15d, r13d
0x1800ed36f  mov     rcx, [rbp+80h]
0x1800ed376  test    rcx, rcx
0x1800ed379  jnz     loc_1800ED44C
0x1800ed37f  lea     rcx, [rsp+98h+var_50]; struct CJetContext **
0x1800ed384  call    ?CreateInstance@CJetContext@@SAJPEAPEAV1@@Z; CJetContext::CreateInstance(CJetContext * *)
0x1800ed389  mov     edi, eax
0x1800ed38b  test    eax, eax
0x1800ed38d  jns     short loc_1800ED406
0x1800ed38f  mov     rbx, [rsp+98h+var_50]
0x1800ed394  mov     [rsp+98h+var_54], 62Bh
0x1800ed39c  mov     esi, eax
0x1800ed39e  mov     rcx, rbp; this
0x1800ed3a1  call    ?EndActivity@CCacheStore@@QEAAXXZ; CCacheStore::EndActivity(void)
0x1800ed3a6  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800ed3ad  jz      short loc_1800ED3C8
0x1800ed3af  mov     edx, 21h ; '!'
0x1800ed3b4  lea     r8, WPP_d2eb1eb319bd39627e3f05ba48018899_Traceguids
0x1800ed3bb  mov     ecx, 40Ch
0x1800ed3c0  mov     r9d, edi
0x1800ed3c3  call    WPP_SF_d
0x1800ed3c8  test    rbx, rbx
0x1800ed3cb  jz      short loc_1800ED3D5
0x1800ed3cd  mov     rcx, rbx; this
0x1800ed3d0  call    ?Release@CJetContext@@QEAAKXZ; CJetContext::Release(void)
0x1800ed3d5  test    r15d, r15d
0x1800ed3d8  jz      short loc_1800ED3E8
0x1800ed3da  test    r14, r14
0x1800ed3dd  jz      short loc_1800ED3E8
0x1800ed3df  mov     rcx, r14; lpCriticalSection
0x1800ed3e2  call    cs:__imp_LeaveCriticalSection
0x1800ed3e8  mov     eax, esi
0x1800ed3ea  mov     rcx, [rsp+98h+var_40]
0x1800ed3ef  xor     rcx, rsp; StackCookie
0x1800ed3f2  call    __security_check_cookie
0x1800ed3f7  add     rsp, 60h
0x1800ed3fb  pop     r15
0x1800ed3fd  pop     r14
0x1800ed3ff  pop     r13
0x1800ed401  pop     rdi
0x1800ed402  pop     rsi
0x1800ed403  pop     rbp
0x1800ed404  pop     rbx
0x1800ed405  retn
0x1800ed406  mov     qword ptr [rsp+98h+grbit], rbx; int *
0x1800ed40b  lea     r8, ?c_wszLeakTable@@3QBGB; "LeakFiles"
0x1800ed412  mov     qword ptr [rsp+98h+cbData], rbx; struct CJetColumns *
0x1800ed417  mov     r9d, 3; unsigned int
0x1800ed41d  mov     rbx, [rsp+98h+var_50]
0x1800ed422  mov     rdx, rbp; struct CCacheStore *
0x1800ed425  mov     rcx, rbx; this
0x1800ed428  call    ?Initialize@CJetContext@@QEAAJPEAVCCacheStore@@PEBGKPEAVCJetColumns@@PEAH@Z; CJetContext::Initialize(CCacheStore *,ushort const *,ulong,CJetColumns *,int *)
0x1800ed42d  mov     edi, eax
0x1800ed42f  test    eax, eax
0x1800ed431  jns     short loc_1800ED440
0x1800ed433  mov     [rsp+98h+var_54], 62Ch
0x1800ed43b  jmp     loc_1800ED39C
0x1800ed440  mov     [rbp+80h], rbx
0x1800ed447  mov     rcx, rbx
0x1800ed44a  xor     ebx, ebx
0x1800ed44c  mov     rcx, [rcx+10h]; sesid
0x1800ed450  call    cs:__imp_JetBeginTransaction
0x1800ed456  mov     ecx, eax; int
0x1800ed458  mov     edx, r13d; int
0x1800ed45b  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ed460  mov     edi, eax
0x1800ed462  test    eax, eax
0x1800ed464  js      loc_1800ED39C
0x1800ed46a  mov     rcx, [rbp+80h]
0x1800ed471  xor     r8d, r8d; prep
0x1800ed474  mov     rdx, [rcx+20h]; tableid
0x1800ed478  mov     rcx, [rcx+10h]; sesid
0x1800ed47c  call    cs:__imp_JetPrepareUpdate
0x1800ed482  mov     ecx, eax; int
0x1800ed484  mov     edx, r13d; int
0x1800ed487  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ed48c  mov     edi, eax
0x1800ed48e  test    eax, eax
0x1800ed490  js      loc_1800ED5C7
0x1800ed496  mov     rcx, [rbp+80h]; this
0x1800ed49d  mov     r8, rsi; unsigned __int16 *
0x1800ed4a0  mov     edx, r13d; unsigned int
0x1800ed4a3  call    ?SetStringColumn@CJetContext@@QEAAJKPEBG@Z; CJetContext::SetStringColumn(ulong,ushort const *)
0x1800ed4a8  mov     edi, eax
0x1800ed4aa  test    eax, eax
0x1800ed4ac  jns     short loc_1800ED4D8
0x1800ed4ae  mov     [rsp+98h+var_54], 636h
0x1800ed4b6  mov     rcx, [rbp+80h]
0x1800ed4bd  mov     r8d, 3; prep
0x1800ed4c3  mov     esi, edi
0x1800ed4c5  mov     rdx, [rcx+20h]; tableid
0x1800ed4c9  mov     rcx, [rcx+10h]; sesid
0x1800ed4cd  call    cs:__imp_JetPrepareUpdate
0x1800ed4d3  jmp     loc_1800ED5C9
0x1800ed4d8  mov     rcx, [rbp+80h]
0x1800ed4df  lea     r9, [rsp+98h+pvData]; pvData
0x1800ed4e4  mov     [rsp+98h+psetinfo], 0; psetinfo
0x1800ed4ed  mov     [rsp+98h+grbit], 0; grbit
0x1800ed4f5  mov     [rsp+98h+cbData], 8; cbData
0x1800ed4fd  mov     rax, [rcx+28h]
0x1800ed501  mov     rdx, [rcx+20h]; tableid
0x1800ed505  mov     rcx, [rcx+10h]; sesid
0x1800ed509  mov     r8, [rax+8]
0x1800ed50d  mov     r8d, [r8+8]; columnid
0x1800ed511  call    cs:__imp_JetSetColumn
0x1800ed517  mov     edi, eax
0x1800ed519  test    eax, eax
0x1800ed51b  jns     short loc_1800ED527
0x1800ed51d  mov     [rsp+98h+var_54], 637h
0x1800ed525  jmp     short loc_1800ED4B6
0x1800ed527  mov     rcx, [rbp+80h]
0x1800ed52e  xor     r9d, r9d; cbBookmark
0x1800ed531  xor     r8d, r8d; pvBookmark
0x1800ed534  mov     qword ptr [rsp+98h+cbData], 0; pcbActual
0x1800ed53d  mov     rdx, [rcx+20h]; tableid
0x1800ed541  mov     rcx, [rcx+10h]; sesid
0x1800ed545  call    cs:__imp_JetUpdate
0x1800ed54b  mov     ecx, eax; int
0x1800ed54d  mov     edx, r13d; int
0x1800ed550  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ed555  mov     edi, eax
0x1800ed557  test    eax, eax
0x1800ed559  js      loc_1800ED4B6
0x1800ed55f  mov     rcx, [rbp+80h]
0x1800ed566  mov     edx, r13d; grbit
0x1800ed569  mov     rcx, [rcx+10h]; sesid
0x1800ed56d  call    cs:__imp_JetCommitTransaction
0x1800ed573  mov     ecx, eax; int
0x1800ed575  mov     edx, r13d; int
0x1800ed578  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ed57d  mov     edi, eax
0x1800ed57f  test    eax, eax
0x1800ed581  js      short loc_1800ED5C7
0x1800ed583  mov     eax, [rbp+158h]
0x1800ed589  lea     rdx, ?DeleteLeakedFilesCallback@CCacheStore@@CAJPEAVCWxWorker@@PEAVCWxWorkContext@@_KPEAX@Z; int (*)(struct CWxWorker *, struct CWxWorkContext *, unsigned __int64, void *)
0x1800ed590  mov     rcx, [rbp+0F0h]; this
0x1800ed597  xor     r9d, r9d; unsigned __int64
0x1800ed59a  mov     [rsp+98h+grbit], 0A4CB800h; unsigned int
0x1800ed5a2  xor     r8d, r8d; struct CWxWorkContext *
0x1800ed5a5  mov     [rsp+98h+cbData], eax; unsigned int
0x1800ed5a9  call    ?Queue@CWxWorker@@QEAAJP6AJPEAV1@PEAVCWxWorkContext@@_KPEAX@Z12KK@Z; CWxWorker::Queue(long (*)(CWxWorker *,CWxWorkContext *,unsigned __int64,void *),CWxWorkContext *,unsigned __int64,ulong,ulong)
0x1800ed5ae  mov     edi, eax
0x1800ed5b0  mov     esi, eax
0x1800ed5b2  test    eax, eax
0x1800ed5b4  jns     loc_1800ED39E
0x1800ed5ba  mov     [rsp+98h+var_54], 646h
0x1800ed5c2  jmp     loc_1800ED39E
0x1800ed5c7  mov     esi, eax
0x1800ed5c9  mov     rcx, [rbp+80h]
0x1800ed5d0  xor     edx, edx; grbit
0x1800ed5d2  mov     rcx, [rcx+10h]; sesid
0x1800ed5d6  call    cs:__imp_JetRollback
0x1800ed5dc  jmp     loc_1800ED39E
```
