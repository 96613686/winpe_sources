# Database::Initialize(ushort const *)

- ea: `0x180010844`
- end: `0x1800109d0`
- name: `?Initialize@Database@@QEAAJPEBG@Z`
- size: `396`
- prototype: `__int64 __fastcall(Database *this, Common *pszPathIn)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180017a68`

## callees

- `0x180006f78`
- `0x18000c040`
- `0x180010844`
- `0x1800109d8`
- `0x1800111c0`
- `0x1800194d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800109bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800109bf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001085a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001085a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180010901`

## pseudocode

```c
__int64 __fastcall Database::Initialize(Database *this, Common *pszPathIn)
{
  RTL_SRWLOCK *v2; // rsi
  DSLogger *v5; // rax
  __int64 i; // rax
  __int64 v7; // rcx
  signed int v8; // ebx
  DSLogger *v9; // rax
  unsigned int v10; // r8d
  int v11; // eax
  int v12; // eax
  DSLogger *v13; // rax
  int (*v15)(void *, unsigned __int16 *, void **, struct _WIN32_FIND_DATAW *); // [rsp+28h] [rbp-60h]
  int (*v16)(void *, void *, struct _WIN32_FIND_DATAW *); // [rsp+30h] [rbp-58h]
  int (*v17)(void *, void *); // [rsp+38h] [rbp-50h]
  _QWORD v18[9]; // [rsp+40h] [rbp-48h] BYREF

  v2 = (RTL_SRWLOCK *)((char *)this + 104);
  AcquireSRWLockExclusive((PSRWLOCK)this + 13);
  v5 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
  LODWORD(v16) = *((_DWORD *)this + 10);
  HIDWORD(v15) = HIDWORD(pszPathIn);
  DSLogger::LogInformation(v5, L"Database::Initialize", 0x4Eu, L"DBInitialize %x: Root: %s EntryState: %d", this);
  if ( *((_DWORD *)this + 10) != 2 )
  {
    if ( *((_DWORD *)this + 10) )
    {
      v8 = 0;
      goto LABEL_20;
    }
    goto LABEL_14;
  }
  for ( i = *((_QWORD *)this + 2); i != *((_QWORD *)this + 3); i += 16 )
  {
    v7 = *(_QWORD *)(i + 8);
    if ( !v7 || *(_DWORD *)(v7 + 8) != 1 )
    {
      v8 = -1055719420;
      goto LABEL_20;
    }
  }
  v8 = Database::InternalUninitialize(this);
  if ( v8 >= 0 )
  {
    v9 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    DSLogger::LogInformation(v9, L"CleanupDatabaseFiles", 0x32u, L"CleanupDatabaseFiles %s");
    v18[0] = DeleteFileW;
    v18[1] = 0;
    v18[2] = 0;
    v11 = Common::WalkDirectoryTree(
            pszPathIn,
            (const unsigned __int16 *)0x40,
            v10,
            (int (*)(void *, const unsigned __int16 *, const struct _WIN32_FIND_DATAW *))v18,
            pszPathIn,
            (int (*)(void *, unsigned __int16 *, void **, struct _WIN32_FIND_DATAW *))pszPathIn,
            v16,
            v17);
    v8 = v11;
    if ( v11 > 0 )
      v8 = (unsigned __int16)v11 | 0x80070000;
    if ( v8 >= 0 )
    {
      *((_DWORD *)this + 10) = 0;
LABEL_14:
      v12 = Database::InternalInitialize(this, (PCWSTR)pszPathIn);
      v8 = v12;
      if ( v12 == -1055719420 || v12 == -1906441232 )
        *((_DWORD *)this + 10) = 2;
      if ( v12 >= 0 )
        *((_DWORD *)this + 10) = 1;
    }
  }
LABEL_20:
  v13 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
  LODWORD(v16) = *((_DWORD *)this + 10);
  LODWORD(v15) = v8;
  DSLogger::LogInformation(
    v13,
    L"Database::Initialize",
    0x6Bu,
    L"DBInitialize %x: Result: 0x%08x ExitState: %d",
    this,
    v15,
    v16);
  if ( v2 )
    ReleaseSRWLockExclusive(v2);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180010844  push    rbx
0x180010846  push    rbp
0x180010847  push    rsi
0x180010848  push    rdi
0x180010849  sub     rsp, 68h
0x18001084d  lea     rsi, [rcx+68h]
0x180010851  mov     rdi, rcx
0x180010854  mov     rcx, rsi; SRWLock
0x180010857  mov     rbp, rdx
0x18001085a  call    cs:__imp_AcquireSRWLockExclusive
0x180010860  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180010865  mov     r8d, [rdi+28h]
0x180010869  lea     r9, aDbinitializeXR_0; "DBInitialize %x: Root: %s EntryState: %"...
0x180010870  mov     dword ptr [rsp+88h+var_58], r8d; int (*)(void *, void *, struct _WIN32_FIND_DATAW *)
0x180010875  lea     rdx, aDatabaseInitia; "Database::Initialize"
0x18001087c  mov     [rsp+88h+var_60], rbp; int (*)(void *, unsigned __int16 *, void **, struct _WIN32_FIND_DATAW *)
0x180010881  mov     r8d, 4Eh ; 'N'; unsigned int
0x180010887  mov     rcx, rax; this
0x18001088a  mov     [rsp+88h+var_68], rdi
0x18001088f  call    ?LogInformation@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogInformation(ushort const *,ulong,ushort const *,...)
0x180010894  cmp     dword ptr [rdi+28h], 2
0x180010898  jnz     loc_18001094D
0x18001089e  mov     rax, [rdi+10h]
0x1800108a2  cmp     rax, [rdi+18h]
0x1800108a6  jz      short loc_1800108C9
0x1800108a8  mov     rcx, [rax+8]
0x1800108ac  test    rcx, rcx
0x1800108af  jz      short loc_1800108BF
0x1800108b1  mov     ecx, [rcx+8]
0x1800108b4  cmp     ecx, 1
0x1800108b7  jnz     short loc_1800108BF
0x1800108b9  add     rax, 10h
0x1800108bd  jmp     short loc_1800108A2
0x1800108bf  mov     ebx, 0C1130004h
0x1800108c4  jmp     loc_180010984
0x1800108c9  mov     rcx, rdi; this
0x1800108cc  call    ?InternalUninitialize@Database@@AEAAJXZ; Database::InternalUninitialize(void)
0x1800108d1  mov     ebx, eax
0x1800108d3  test    eax, eax
0x1800108d5  js      loc_180010984
0x1800108db  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800108e0  lea     r9, aCleanupdatabas_0; "CleanupDatabaseFiles %s"
0x1800108e7  mov     [rsp+88h+var_68], rbp; void *
0x1800108ec  mov     r8d, 32h ; '2'; unsigned int
0x1800108f2  lea     rdx, aCleanupdatabas; "CleanupDatabaseFiles"
0x1800108f9  mov     rcx, rax; this
0x1800108fc  call    ?LogInformation@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogInformation(ushort const *,ulong,ushort const *,...)
0x180010901  mov     rax, cs:__imp_DeleteFileW
0x180010908  lea     r9, [rsp+88h+var_48]; int (*)(void *, const unsigned __int16 *, const struct _WIN32_FIND_DATAW *)
0x18001090d  mov     edx, 40h ; '@'; unsigned __int16 *
0x180010912  mov     [rsp+88h+var_48], rax
0x180010917  mov     rcx, rbp; this
0x18001091a  mov     [rsp+88h+var_40], 0
0x180010923  mov     [rsp+88h+var_38], 0
0x18001092c  call    ?WalkDirectoryTree@Common@@YAJPEBGIP6AJPEAX0PEBU_WIN32_FIND_DATAW@@@Z1P6AJ1PEAGPEAPEAXPEAU2@@ZP6AJ116@ZP6AJ11@Z@Z; Common::WalkDirectoryTree(ushort const *,uint,long (*)(void *,ushort const *,_WIN32_FIND_DATAW const *),void *,long (*)(void *,ushort *,void * *,_WIN32_FIND_DATAW *),long (*)(void *,void *,_WIN32_FIND_DATAW *),long (*)(void *,void *))
0x180010931  mov     ebx, eax
0x180010933  test    eax, eax
0x180010935  jle     short loc_180010940
0x180010937  movzx   ebx, ax
0x18001093a  or      ebx, 80070000h
0x180010940  test    ebx, ebx
0x180010942  js      short loc_180010984
0x180010944  mov     dword ptr [rdi+28h], 0
0x18001094b  jmp     short loc_180010953
0x18001094d  cmp     dword ptr [rdi+28h], 0
0x180010951  jnz     short loc_180010982
0x180010953  mov     rdx, rbp; pszPathIn
0x180010956  mov     rcx, rdi; this
0x180010959  call    ?InternalInitialize@Database@@AEAAJPEBG@Z; Database::InternalInitialize(ushort const *)
0x18001095e  mov     ebx, eax
0x180010960  cmp     eax, 0C1130004h
0x180010965  jz      short loc_18001096E
0x180010967  cmp     eax, 8E5E03F0h
0x18001096c  jnz     short loc_180010975
0x18001096e  mov     dword ptr [rdi+28h], 2
0x180010975  test    eax, eax
0x180010977  js      short loc_180010984
0x180010979  mov     dword ptr [rdi+28h], 1
0x180010980  jmp     short loc_180010984
0x180010982  xor     ebx, ebx
0x180010984  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180010989  mov     r8d, [rdi+28h]
0x18001098d  lea     r9, aDbinitializeXR; "DBInitialize %x: Result: 0x%08x ExitSta"...
0x180010994  mov     dword ptr [rsp+88h+var_58], r8d
0x180010999  lea     rdx, aDatabaseInitia; "Database::Initialize"
0x1800109a0  mov     dword ptr [rsp+88h+var_60], ebx
0x1800109a4  mov     r8d, 6Bh ; 'k'; unsigned int
0x1800109aa  mov     rcx, rax; this
0x1800109ad  mov     [rsp+88h+var_68], rdi
0x1800109b2  call    ?LogInformation@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogInformation(ushort const *,ulong,ushort const *,...)
0x1800109b7  test    rsi, rsi
0x1800109ba  jz      short loc_1800109C5
0x1800109bc  mov     rcx, rsi; SRWLock
0x1800109bf  call    cs:__imp_ReleaseSRWLockExclusive
0x1800109c5  mov     eax, ebx
0x1800109c7  add     rsp, 68h
0x1800109cb  pop     rdi
0x1800109cc  pop     rsi
0x1800109cd  pop     rbp
0x1800109ce  pop     rbx
0x1800109cf  retn
```
