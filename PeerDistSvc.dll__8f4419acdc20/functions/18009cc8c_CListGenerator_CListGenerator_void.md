# CListGenerator::~CListGenerator(void)

- ea: `0x18009cc8c`
- end: `0x18009cef4`
- name: `??1CListGenerator@@UEAA@XZ`
- size: `616`
- prototype: `void __fastcall(CListGenerator *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x18009d0a0`

## callees

- `0x1800024f0`
- `0x180004374`
- `0x1800082d0`
- `0x18000e58c`
- `0x18000ecf4`
- `0x180018f48`
- `0x18001911c`
- `0x18001edc0`
- `0x18001f130`
- `0x18001f2e0`
- `0x18001fc30`
- `0x18002a878`
- `0x18009cc70`
- `0x18009cc8c`
- `0x180159010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009ce53`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009ced3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009ce53`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009ced3`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall CListGenerator::~CListGenerator(CListGenerator *this)
{
  CListGenerator *v1; // rbx
  CThreadpoolEnvironment *v2; // r12
  CThreadpoolEnvironment *v3; // r13
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 (__fastcall ****v6)(_QWORD, __int64); // r15
  char *v7; // rdi
  __int64 v8; // rsi
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 (__fastcall ****v11)(_QWORD, __int64); // [rsp+30h] [rbp-48h]
  char *v15; // [rsp+88h] [rbp+10h]
  CThreadpoolEnvironment *v17; // [rsp+90h] [rbp+18h]
  CThreadpoolEnvironment *v19; // [rsp+98h] [rbp+20h]

  v1 = this;
  *(_QWORD *)this = &CListGenerator::`vftable';
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 25, WPP_2322ab784b0930308c827d565065ffd4_Traceguids);
  }
  v2 = (CListGenerator *)((char *)v1 + 88);
  v17 = (CListGenerator *)((char *)v1 + 88);
  CThreadpoolEnvironment::CleanupGroupMembers((CListGenerator *)((char *)v1 + 88), 1);
  v3 = (CListGenerator *)((char *)v1 + 200);
  v19 = (CListGenerator *)((char *)v1 + 200);
  CThreadpoolEnvironment::CleanupGroupMembers((CListGenerator *)((char *)v1 + 200), 1);
  v6 = (__int64 (__fastcall ****)(_QWORD, __int64))((char *)v1 + 544);
  v11 = (__int64 (__fastcall ****)(_QWORD, __int64))((char *)v1 + 544);
  if ( *((_QWORD *)v1 + 68) )
    std::auto_ptr<TnoHashKey>::reset((char *)v1 + 544, 0, v4, v5);
  if ( *((_BYTE *)v1 + 384) )
  {
    v7 = (char *)v1 + 376;
    v15 = (char *)v1 + 376;
    v8 = *((_QWORD *)v1 + 47);
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_qq(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        23,
        WPP_2322ab784b0930308c827d565065ffd4_Traceguids,
        v8,
        *(_QWORD *)(v8 + 232));
    }
    try
    {
      ObjectHandle::Wait((ObjectHandle *)(v8 + 152), 0xFFFFFFFF);
      SingleObjectWaiter::Cancel((PTP_WAIT *)v8);
    }
    catch ( ... )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 105) )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 26, WPP_2322ab784b0930308c827d565065ffd4_Traceguids);
      }
      v1 = this;
      v7 = v15;
      v2 = v17;
      v3 = v19;
      v6 = v11;
    }
    std::auto_ptr<TnoHashKey>::reset(v7, 0, v9, v10);
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v1 + 10) + 160LL))(*((_QWORD *)v1 + 10));
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 27, WPP_2322ab784b0930308c827d565065ffd4_Traceguids);
  }
  std::auto_ptr<CRepubCacheMigrateWorkItem>::~auto_ptr<CRepubCacheMigrateWorkItem>(v6);
  operator delete(*((void **)v1 + 62));
  operator delete(*((void **)v1 + 59));
  *((_QWORD *)v1 + 53) = &CritSec::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v1 + 432));
  operator delete(*((void **)v1 + 50));
  std::auto_ptr<CRepubCacheMigrateWorkItem>::~auto_ptr<CRepubCacheMigrateWorkItem>((__int64 (__fastcall ****)(_QWORD, __int64))v1 + 47);
  SmartPointer<CRepubJetSessionContext>::Release((char *)v1 + 360);
  std::auto_ptr<std::vector<sChunk>>::~auto_ptr<std::vector<sChunk>>((char *)v1 + 336);
  *((_QWORD *)v1 + 39) = &ObjectHandle::`vftable';
  ObjectHandle::CloseNoThrow((CListGenerator *)((char *)v1 + 312));
  CThreadpoolEnvironment::~CThreadpoolEnvironment(v3);
  CThreadpoolEnvironment::~CThreadpoolEnvironment(v2);
  SmartPointer<CRepubJetSessionContext>::Release((char *)v1 + 80);
  SmartPointer<CRepubJetSessionContext>::Release((char *)v1 + 56);
  *((_QWORD *)v1 + 1) = &CritSec::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v1 + 16));
  *(_QWORD *)v1 = &CContentInfoV20Parser::CContentInfoV20ChunkParserBase::`vftable';
}

```

## disassembly

```asm
0x18009cc8c  mov     [rsp+arg_0], rcx
0x18009cc91  push    rbx
0x18009cc92  push    rsi
0x18009cc93  push    rdi
0x18009cc94  push    r12
0x18009cc96  push    r13
0x18009cc98  push    r14
0x18009cc9a  push    r15
0x18009cc9c  sub     rsp, 40h
0x18009cca0  mov     rbx, rcx
0x18009cca3  lea     rax, ??_7CListGenerator@@6B@; const CListGenerator::`vftable'
0x18009ccaa  mov     [rcx], rax
0x18009ccad  lea     r14, WPP_GLOBAL_Control
0x18009ccb4  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ccbb  cmp     rcx, r14
0x18009ccbe  jz      short loc_18009CCE4
0x18009ccc0  test    byte ptr [rcx+6Ch], 1
0x18009ccc4  jz      short loc_18009CCE4
0x18009ccc6  cmp     byte ptr [rcx+69h], 4
0x18009ccca  jb      short loc_18009CCE4
0x18009cccc  mov     edx, 19h
0x18009ccd1  mov     r9, rbx
0x18009ccd4  lea     r8, WPP_2322ab784b0930308c827d565065ffd4_Traceguids
0x18009ccdb  mov     rcx, [rcx+60h]
0x18009ccdf  call    WPP_SF_q
0x18009cce4  lea     r12, [rbx+58h]
0x18009cce8  mov     [rsp+78h+arg_10], r12
0x18009ccf0  mov     dl, 1; bool
0x18009ccf2  mov     rcx, r12; this
0x18009ccf5  call    ?CleanupGroupMembers@CThreadpoolEnvironment@@QEAAX_N@Z; CThreadpoolEnvironment::CleanupGroupMembers(bool)
0x18009ccfa  lea     r13, [rbx+0C8h]
0x18009cd01  mov     [rsp+78h+arg_18], r13
0x18009cd09  mov     dl, 1; bool
0x18009cd0b  mov     rcx, r13; this
0x18009cd0e  call    ?CleanupGroupMembers@CThreadpoolEnvironment@@QEAAX_N@Z; CThreadpoolEnvironment::CleanupGroupMembers(bool)
0x18009cd13  lea     r15, [rbx+220h]
0x18009cd1a  mov     [rsp+78h+var_48], r15
0x18009cd1f  cmp     qword ptr [r15], 0
0x18009cd23  jz      short loc_18009CD2F
0x18009cd25  xor     edx, edx
0x18009cd27  mov     rcx, r15
0x18009cd2a  call    ?reset@?$auto_ptr@VTnoHashKey@@@std@@QEAAXPEAVTnoHashKey@@@Z; std::auto_ptr<TnoHashKey>::reset(TnoHashKey *)
0x18009cd2f  cmp     byte ptr [rbx+180h], 0
0x18009cd36  jz      loc_18009CDDA
0x18009cd3c  lea     rdi, [rbx+178h]
0x18009cd43  mov     [rsp+78h+arg_8], rdi
0x18009cd4b  mov     rsi, [rdi]
0x18009cd4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18009cd55  cmp     rcx, r14
0x18009cd58  jz      short loc_18009CD8A
0x18009cd5a  test    byte ptr [rcx+6Ch], 1
0x18009cd5e  jz      short loc_18009CD8A
0x18009cd60  cmp     byte ptr [rcx+69h], 4
0x18009cd64  jb      short loc_18009CD8A
0x18009cd66  mov     edx, 17h
0x18009cd6b  mov     rax, [rsi+0E8h]
0x18009cd72  mov     [rsp+78h+var_58], rax
0x18009cd77  mov     r9, rsi
0x18009cd7a  lea     r8, WPP_2322ab784b0930308c827d565065ffd4_Traceguids
0x18009cd81  mov     rcx, [rcx+60h]
0x18009cd85  call    WPP_SF_qq
0x18009cd8a  lea     rcx, [rsi+98h]; this
0x18009cd91  or      edx, 0FFFFFFFFh; unsigned int
0x18009cd94  call    ?Wait@ObjectHandle@@QEAA_NI@Z; ObjectHandle::Wait(uint)
0x18009cd99  mov     rcx, rsi; this
0x18009cd9c  call    ?Cancel@SingleObjectWaiter@@QEAAX_N@Z; SingleObjectWaiter::Cancel(bool)
0x18009cda1  nop
0x18009cda2  jmp     short loc_18009CDD0
0x18009cda4  lea     r14, WPP_GLOBAL_Control
0x18009cdab  mov     rbx, [rsp+78h+arg_0]
0x18009cdb3  mov     rdi, [rsp+78h+arg_8]
0x18009cdbb  mov     r12, [rsp+78h+arg_10]
0x18009cdc3  mov     r13, [rsp+78h+arg_18]
0x18009cdcb  mov     r15, [rsp+78h+var_48]
0x18009cdd0  xor     edx, edx
0x18009cdd2  mov     rcx, rdi
0x18009cdd5  call    ?reset@?$auto_ptr@VTnoHashKey@@@std@@QEAAXPEAVTnoHashKey@@@Z; std::auto_ptr<TnoHashKey>::reset(TnoHashKey *)
0x18009cdda  mov     rcx, [rbx+50h]
0x18009cdde  mov     rax, [rcx]
0x18009cde1  mov     rax, [rax+0A0h]
0x18009cde8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cded  mov     rcx, cs:WPP_GLOBAL_Control
0x18009cdf4  cmp     rcx, r14
0x18009cdf7  jz      short loc_18009CE1B
0x18009cdf9  test    byte ptr [rcx+6Ch], 1
0x18009cdfd  jz      short loc_18009CE1B
0x18009cdff  cmp     byte ptr [rcx+69h], 4
0x18009ce03  jb      short loc_18009CE1B
0x18009ce05  mov     edx, 1Bh
0x18009ce0a  lea     r8, WPP_2322ab784b0930308c827d565065ffd4_Traceguids
0x18009ce11  mov     rcx, [rcx+60h]
0x18009ce15  call    WPP_SF_
0x18009ce1a  nop
0x18009ce1b  mov     rcx, r15
0x18009ce1e  call    ??1?$auto_ptr@VCRepubCacheMigrateWorkItem@@@std@@QEAA@XZ; std::auto_ptr<CRepubCacheMigrateWorkItem>::~auto_ptr<CRepubCacheMigrateWorkItem>(void)
0x18009ce23  nop
0x18009ce24  mov     rcx, [rbx+1F0h]; Block
0x18009ce2b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009ce30  nop
0x18009ce31  mov     rcx, [rbx+1D8h]; Block
0x18009ce38  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009ce3d  nop
0x18009ce3e  lea     rsi, ??_7CritSec@@6B@; const CritSec::`vftable'
0x18009ce45  mov     [rbx+1A8h], rsi
0x18009ce4c  lea     rcx, [rbx+1B0h]; lpCriticalSection
0x18009ce53  call    cs:__imp_DeleteCriticalSection
0x18009ce59  nop
0x18009ce5a  mov     rcx, [rbx+190h]; Block
0x18009ce61  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009ce66  nop
0x18009ce67  lea     rcx, [rbx+178h]
0x18009ce6e  call    ??1?$auto_ptr@VCRepubCacheMigrateWorkItem@@@std@@QEAA@XZ; std::auto_ptr<CRepubCacheMigrateWorkItem>::~auto_ptr<CRepubCacheMigrateWorkItem>(void)
0x18009ce73  nop
0x18009ce74  lea     rcx, [rbx+168h]
0x18009ce7b  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x18009ce80  nop
0x18009ce81  lea     rcx, [rbx+150h]
0x18009ce88  call    ??1?$auto_ptr@V?$vector@UsChunk@@V?$allocator@UsChunk@@@std@@@std@@@std@@QEAA@XZ; std::auto_ptr<std::vector<sChunk>>::~auto_ptr<std::vector<sChunk>>(void)
0x18009ce8d  nop
0x18009ce8e  lea     rcx, [rbx+138h]; this
0x18009ce95  lea     rax, ??_7ObjectHandle@@6B@; const ObjectHandle::`vftable'
0x18009ce9c  mov     [rcx], rax
0x18009ce9f  call    ?CloseNoThrow@ObjectHandle@@IEAAKXZ; ObjectHandle::CloseNoThrow(void)
0x18009cea4  nop
0x18009cea5  mov     rcx, r13; this
0x18009cea8  call    ??1CThreadpoolEnvironment@@UEAA@XZ; CThreadpoolEnvironment::~CThreadpoolEnvironment(void)
0x18009cead  nop
0x18009ceae  mov     rcx, r12; this
0x18009ceb1  call    ??1CThreadpoolEnvironment@@UEAA@XZ; CThreadpoolEnvironment::~CThreadpoolEnvironment(void)
0x18009ceb6  nop
0x18009ceb7  lea     rcx, [rbx+50h]
0x18009cebb  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x18009cec0  nop
0x18009cec1  lea     rcx, [rbx+38h]
0x18009cec5  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x18009ceca  nop
0x18009cecb  mov     [rbx+8], rsi
0x18009cecf  lea     rcx, [rbx+10h]; lpCriticalSection
0x18009ced3  call    cs:__imp_DeleteCriticalSection
0x18009ced9  nop
0x18009ceda  lea     rax, ??_7CContentInfoV20ChunkParserBase@CContentInfoV20Parser@@6B@; const CContentInfoV20Parser::CContentInfoV20ChunkParserBase::`vftable'
0x18009cee1  mov     [rbx], rax
0x18009cee4  add     rsp, 40h
0x18009cee8  pop     r15
0x18009ceea  pop     r14
0x18009ceec  pop     r13
0x18009ceee  pop     r12
0x18009cef0  pop     rdi
0x18009cef1  pop     rsi
0x18009cef2  pop     rbx
0x18009cef3  retn
```
