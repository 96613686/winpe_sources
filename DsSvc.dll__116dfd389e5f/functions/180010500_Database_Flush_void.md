# Database::Flush(void)

- ea: `0x180010500`
- end: `0x1800105b4`
- name: `?Flush@Database@@QEAAJXZ`
- size: `180`
- prototype: `__int64 __fastcall(Database *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800083c0`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x18000f120`
- `0x180010500`
- `0x1800107c4`
- `0x1800114e4`

## import_xrefs

- `ESENT!JetCommitTransaction` at `0x180010535`
- `ESENT!JetCommitTransaction` at `0x180010535`

## pseudocode

```c
__int64 __fastcall Database::Flush(Database *this)
{
  __int64 v1; // rcx
  int SessionFromPool; // ebx
  __int64 v3; // rcx
  JET_ERR v4; // edi
  int *v5; // rax
  int *v6; // rax
  __int64 v8; // [rsp+20h] [rbp-28h]
  JET_ERR v9; // [rsp+20h] [rbp-28h]
  utl::_RefCountBase *v10[2]; // [rsp+30h] [rbp-18h] BYREF

  *((_BYTE *)this + 44) = 1;
  *(_OWORD *)v10 = 0;
  SessionFromPool = Database::GetSessionFromPool(this, v10);
  if ( SessionFromPool < 0
    || (v4 = JetCommitTransaction(*((_QWORD *)v10[0] + 5), 8u), v4 < 0)
    && (v5 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v3),
        v9 = v4,
        DSLogger::LogError((DSLogger *)v5, L"Database::Flush", 294, L"JET_ERR : %d", v9),
        SessionFromPool = JetToHResult(v4),
        SessionFromPool < 0) )
  {
    v6 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v1);
    LODWORD(v8) = SessionFromPool;
    DSLogger::LogError((DSLogger *)v6, L"Database::Flush", 300, L"Database::Flush failed! hr=0x%x.", v8);
  }
  if ( v10[1] )
    utl::_RefCountBase::_DecStrong(v10[1]);
  return (unsigned int)SessionFromPool;
}

```

## disassembly

```asm
0x180010500  mov     [rsp+arg_0], rbx
0x180010505  push    rdi
0x180010506  sub     rsp, 40h
0x18001050a  xorps   xmm0, xmm0
0x18001050d  mov     byte ptr [rcx+2Ch], 1
0x180010511  lea     rdx, [rsp+48h+var_18]
0x180010516  movdqu  xmmword ptr [rsp+48h+var_18], xmm0
0x18001051c  call    ?GetSessionFromPool@Database@@QEAAJAEAV?$smart_ptr@VDbSession@@$1??$_delete@VDbSession@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@Z; Database::GetSessionFromPool(tlx::smart_ptr<DbSession,&tlx::_delete<DbSession>(DbSession *),utl::allocator<int>> &)
0x180010521  mov     ebx, eax
0x180010523  test    eax, eax
0x180010525  js      short loc_180010573
0x180010527  mov     rcx, [rsp+48h+var_18]
0x18001052c  mov     edx, 8; grbit
0x180010531  mov     rcx, [rcx+28h]; sesid
0x180010535  call    cs:__imp_JetCommitTransaction
0x18001053b  mov     edi, eax
0x18001053d  test    eax, eax
0x18001053f  jns     short loc_180010598
0x180010541  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180010546  lea     r9, aJetErrD; "JET_ERR : %d"
0x18001054d  mov     [rsp+48h+var_28], edi
0x180010551  mov     r8d, 126h; unsigned int
0x180010557  lea     rdx, aDatabaseFlush; "Database::Flush"
0x18001055e  mov     rcx, rax; this
0x180010561  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180010566  mov     ecx, edi; int
0x180010568  call    ?JetToHResult@@YAJJ@Z; JetToHResult(long)
0x18001056d  mov     ebx, eax
0x18001056f  test    eax, eax
0x180010571  jns     short loc_180010598
0x180010573  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180010578  lea     r9, aDatabaseFlushF; "Database::Flush failed! hr=0x%x."
0x18001057f  mov     [rsp+48h+var_28], ebx
0x180010583  mov     r8d, 12Ch; unsigned int
0x180010589  lea     rdx, aDatabaseFlush; "Database::Flush"
0x180010590  mov     rcx, rax; this
0x180010593  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180010598  mov     rcx, [rsp+48h+var_18+8]; this
0x18001059d  test    rcx, rcx
0x1800105a0  jz      short loc_1800105A7
0x1800105a2  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800105a7  mov     eax, ebx
0x1800105a9  mov     rbx, [rsp+48h+arg_0]
0x1800105ae  add     rsp, 40h
0x1800105b2  pop     rdi
0x1800105b3  retn
```
