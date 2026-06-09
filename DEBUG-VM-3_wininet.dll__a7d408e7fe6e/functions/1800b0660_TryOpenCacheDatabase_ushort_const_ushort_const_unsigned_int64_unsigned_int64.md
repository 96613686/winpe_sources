# TryOpenCacheDatabase(ushort const *,ushort const *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x1800b0660`
- end: `0x1800b08aa`
- name: `?TryOpenCacheDatabase@@YAJPEBG0PEA_K1@Z`
- size: `586`
- prototype: `__int64 __fastcall(const unsigned __int16 *, JET_PCWSTR szFilename, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x1800b18d4`

## callees

- `0x18007ec9c`
- `0x1800afc90`
- `0x1800afe20`
- `0x1800b0660`
- `0x1800b08b0`
- `0x1800b098c`
- `0x18013f5f8`
- `0x18014a7a0`
- `0x1801e1790`
- `0x1801e6810`

## import_xrefs

- `ESENT!JetCloseDatabase` at `0x1800b071b`
- `ESENT!JetCloseDatabase` at `0x1800b0884`
- `ESENT!JetCloseDatabase` at `0x1800b071b`
- `ESENT!JetCloseDatabase` at `0x1800b0884`
- `ESENT!JetAttachDatabaseW` at `0x1800b081e`
- `ESENT!JetAttachDatabaseW` at `0x1800b081e`
- `ESENT!JetOpenDatabaseW` at `0x1800b084d`
- `ESENT!JetOpenDatabaseW` at `0x1800b084d`
- `ESENT!JetBeginSessionA` at `0x1800b07fb`
- `ESENT!JetBeginSessionA` at `0x1800b07fb`
- `ESENT!JetTerm2` at `0x1800b074b`
- `ESENT!JetTerm2` at `0x1800b074b`
- `ESENT!JetDeleteTableW` at `0x1800b0874`
- `ESENT!JetDeleteTableW` at `0x1800b0874`
- `ESENT!JetEndSession` at `0x1800b0733`
- `ESENT!JetEndSession` at `0x1800b0733`

## pseudocode

```c
__int64 __fastcall TryOpenCacheDatabase(
        const unsigned __int16 *a1,
        JET_PCWSTR szFilename,
        unsigned __int64 *a3,
        unsigned __int64 *a4)
{
  int CacheDatabaseJetInstance; // ebx
  unsigned int v9; // edi
  const unsigned __int16 *v11; // rdx
  int v12; // r8d
  JET_ERR v13; // eax
  JET_ERR v14; // eax
  JET_ERR v15; // eax
  JET_DBID dbid; // [rsp+48h] [rbp-28h] BYREF
  JET_SESID sesid; // [rsp+50h] [rbp-20h] BYREF
  JET_INSTANCE instance; // [rsp+58h] [rbp-18h] BYREF

  instance = -1;
  sesid = -1;
  dbid = -1;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_SSqq(
      (_DWORD)a1,
      47,
      (unsigned int)&WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids,
      (_DWORD)a1,
      (__int64)szFilename,
      (__int64)a3,
      (__int64)a4);
  *a3 = 0;
  *a4 = 0;
  if ( !(unsigned int)IsDatabaseCorrupt()
    || (CacheDatabaseJetInstance = DeleteCacheDatabaseDirectory(a1), CacheDatabaseJetInstance >= 0) )
  {
    CacheDatabaseJetInstance = VerifyAdequateDiskSpace(a1);
    if ( CacheDatabaseJetInstance >= 0 )
    {
      CacheDatabaseJetInstance = CreateCacheDatabaseJetInstance(a1, v11, 0, (unsigned __int16 *)&instance);
      if ( CacheDatabaseJetInstance >= 0 )
      {
        CacheDatabaseJetInstance = CreateCacheDatabaseIfNeeded(instance, szFilename, v12);
        if ( CacheDatabaseJetInstance >= 0 )
        {
          v13 = JetBeginSessionA(instance, &sesid, 0, 0);
          CacheDatabaseJetInstance = HRESULTFromJET_ERR(v13, 0);
          if ( CacheDatabaseJetInstance >= 0 )
          {
            v14 = JetAttachDatabaseW(sesid, szFilename, 0);
            CacheDatabaseJetInstance = HRESULTFromJET_ERR(v14, 0);
            if ( CacheDatabaseJetInstance >= 0 )
            {
              v15 = JetOpenDatabaseW(sesid, szFilename, 0, &dbid, 0);
              CacheDatabaseJetInstance = HRESULTFromJET_ERR(v15, 0);
              if ( CacheDatabaseJetInstance >= 0 )
              {
                JetDeleteTableW(sesid, dbid, L"PreGrow");
                JetCloseDatabase(sesid, dbid, 0);
                v9 = CacheDatabaseJetInstance;
                *a3 = instance;
                *a4 = sesid;
                dbid = -1;
                sesid = -1;
                goto LABEL_12;
              }
            }
          }
        }
      }
    }
  }
  v9 = CacheDatabaseJetInstance;
  if ( dbid == -1 )
    goto LABEL_8;
  if ( sesid != -1 )
  {
    JetCloseDatabase(sesid, dbid, 0);
    dbid = -1;
LABEL_8:
    if ( sesid != -1 )
    {
      JetEndSession(sesid, 0);
      sesid = -1;
    }
  }
  if ( instance == -1 )
    goto LABEL_13;
  JetTerm2(instance, 1u);
LABEL_12:
  instance = -1;
LABEL_13:
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 48, &WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids, (unsigned int)CacheDatabaseJetInstance);
  return v9;
}

```

## disassembly

```asm
0x1800b0660  push    rbp
0x1800b0662  push    rbx
0x1800b0663  push    rsi
0x1800b0664  push    rdi
0x1800b0665  push    r13
0x1800b0667  push    r14
0x1800b0669  push    r15
0x1800b066b  mov     rbp, rsp
0x1800b066e  sub     rsp, 70h
0x1800b0672  mov     rax, cs:__security_cookie
0x1800b0679  xor     rax, rsp
0x1800b067c  mov     [rbp+var_10], rax
0x1800b0680  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800b0684  mov     [rbp+var_2C], 0
0x1800b068b  mov     [rbp+instance], r13
0x1800b068f  mov     r15, r9
0x1800b0692  mov     [rbp+sesid], r13
0x1800b0696  mov     r14, r8
0x1800b0699  mov     rsi, rdx
0x1800b069c  mov     [rbp+dbid], 0FFFFFFFFh
0x1800b06a3  mov     rdi, rcx
0x1800b06a6  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800b06ad  jz      short loc_1800B06D1
0x1800b06af  mov     [rsp+70h+var_40], r9
0x1800b06b4  lea     edx, [r13+30h]
0x1800b06b8  mov     [rsp+70h+var_48], r8
0x1800b06bd  mov     r9, rcx
0x1800b06c0  lea     r8, WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids
0x1800b06c7  mov     qword ptr [rsp+70h+grbit], rsi
0x1800b06cc  call    WPP_SF_SSqq
0x1800b06d1  mov     qword ptr [r14], 0
0x1800b06d8  mov     qword ptr [r15], 0
0x1800b06df  call    ?IsDatabaseCorrupt@@YAHXZ; IsDatabaseCorrupt(void)
0x1800b06e4  test    eax, eax
0x1800b06e6  jz      loc_1800B0794
0x1800b06ec  mov     rcx, rdi; unsigned __int16 *
0x1800b06ef  call    ?DeleteCacheDatabaseDirectory@@YAJPEBG@Z; DeleteCacheDatabaseDirectory(ushort const *)
0x1800b06f4  mov     ebx, eax
0x1800b06f6  test    eax, eax
0x1800b06f8  jns     loc_1800B0794
0x1800b06fe  mov     [rbp+var_2C], 40Dh
0x1800b0705  mov     edi, ebx
0x1800b0707  mov     edx, [rbp+dbid]; dbid
0x1800b070a  cmp     edx, 0FFFFFFFFh
0x1800b070d  jz      short loc_1800B0728
0x1800b070f  mov     rcx, [rbp+sesid]; sesid
0x1800b0713  cmp     rcx, r13
0x1800b0716  jz      short loc_1800B073D
0x1800b0718  xor     r8d, r8d; grbit
0x1800b071b  call    cs:__imp_JetCloseDatabase
0x1800b0721  mov     [rbp+dbid], 0FFFFFFFFh
0x1800b0728  mov     rcx, [rbp+sesid]; sesid
0x1800b072c  cmp     rcx, r13
0x1800b072f  jz      short loc_1800B073D
0x1800b0731  xor     edx, edx; grbit
0x1800b0733  call    cs:__imp_JetEndSession
0x1800b0739  mov     [rbp+sesid], r13
0x1800b073d  mov     rcx, [rbp+instance]; instance
0x1800b0741  cmp     rcx, r13
0x1800b0744  jz      short loc_1800B0755
0x1800b0746  mov     edx, 1; grbit
0x1800b074b  call    cs:__imp_JetTerm2
0x1800b0751  mov     [rbp+instance], r13
0x1800b0755  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800b075c  jz      short loc_1800B0777
0x1800b075e  mov     edx, 30h ; '0'
0x1800b0763  lea     r8, WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids
0x1800b076a  mov     ecx, 40Ch
0x1800b076f  mov     r9d, ebx
0x1800b0772  call    WPP_SF_d
0x1800b0777  mov     eax, edi
0x1800b0779  mov     rcx, [rbp+var_10]
0x1800b077d  xor     rcx, rsp; StackCookie
0x1800b0780  call    __security_check_cookie
0x1800b0785  add     rsp, 70h
0x1800b0789  pop     r15
0x1800b078b  pop     r14
0x1800b078d  pop     r13
0x1800b078f  pop     rdi
0x1800b0790  pop     rsi
0x1800b0791  pop     rbx
0x1800b0792  pop     rbp
0x1800b0793  retn
0x1800b0794  mov     rcx, rdi; lpDirectoryName
0x1800b0797  call    ?VerifyAdequateDiskSpace@@YAJPEBG@Z; VerifyAdequateDiskSpace(ushort const *)
0x1800b079c  mov     ebx, eax
0x1800b079e  test    eax, eax
0x1800b07a0  jns     short loc_1800B07AE
0x1800b07a2  mov     [rbp+var_2C], 410h
0x1800b07a9  jmp     loc_1800B0705
0x1800b07ae  lea     r9, [rbp+instance]; unsigned __int64 *
0x1800b07b2  xor     r8d, r8d; int
0x1800b07b5  mov     rcx, rdi; unsigned __int16 *
0x1800b07b8  call    ?CreateCacheDatabaseJetInstance@@YAJPEBG0HPEA_K@Z; CreateCacheDatabaseJetInstance(ushort const *,ushort const *,int,unsigned __int64 *)
0x1800b07bd  mov     ebx, eax
0x1800b07bf  test    eax, eax
0x1800b07c1  jns     short loc_1800B07CF
0x1800b07c3  mov     [rbp+var_2C], 412h
0x1800b07ca  jmp     loc_1800B0705
0x1800b07cf  mov     rcx, [rbp+instance]; instance
0x1800b07d3  mov     rdx, rsi; szFilename
0x1800b07d6  call    ?CreateCacheDatabaseIfNeeded@@YAJ_KPEBG@Z; CreateCacheDatabaseIfNeeded(unsigned __int64,ushort const *)
0x1800b07db  mov     ebx, eax
0x1800b07dd  test    eax, eax
0x1800b07df  jns     short loc_1800B07ED
0x1800b07e1  mov     [rbp+var_2C], 413h
0x1800b07e8  jmp     loc_1800B0705
0x1800b07ed  mov     rcx, [rbp+instance]; instance
0x1800b07f1  lea     rdx, [rbp+sesid]; psesid
0x1800b07f5  xor     r9d, r9d; szPassword
0x1800b07f8  xor     r8d, r8d; szUserName
0x1800b07fb  call    cs:__imp_JetBeginSessionA
0x1800b0801  mov     ecx, eax; int
0x1800b0803  xor     edx, edx; int
0x1800b0805  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800b080a  mov     ebx, eax
0x1800b080c  test    eax, eax
0x1800b080e  js      loc_1800B0705
0x1800b0814  mov     rcx, [rbp+sesid]; sesid
0x1800b0818  xor     r8d, r8d; grbit
0x1800b081b  mov     rdx, rsi; szFilename
0x1800b081e  call    cs:__imp_JetAttachDatabaseW
0x1800b0824  mov     ecx, eax; int
0x1800b0826  xor     edx, edx; int
0x1800b0828  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800b082d  mov     ebx, eax
0x1800b082f  test    eax, eax
0x1800b0831  js      loc_1800B0705
0x1800b0837  mov     rcx, [rbp+sesid]; sesid
0x1800b083b  lea     r9, [rbp+dbid]; pdbid
0x1800b083f  xor     r8d, r8d; szConnect
0x1800b0842  mov     [rsp+70h+grbit], 0; grbit
0x1800b084a  mov     rdx, rsi; szFilename
0x1800b084d  call    cs:__imp_JetOpenDatabaseW
0x1800b0853  mov     ecx, eax; int
0x1800b0855  xor     edx, edx; int
0x1800b0857  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800b085c  mov     ebx, eax
0x1800b085e  test    eax, eax
0x1800b0860  js      loc_1800B0705
0x1800b0866  mov     edx, [rbp+dbid]; dbid
0x1800b0869  lea     r8, szTableName; "PreGrow"
0x1800b0870  mov     rcx, [rbp+sesid]; sesid
0x1800b0874  call    cs:__imp_JetDeleteTableW
0x1800b087a  mov     edx, [rbp+dbid]; dbid
0x1800b087d  xor     r8d, r8d; grbit
0x1800b0880  mov     rcx, [rbp+sesid]; sesid
0x1800b0884  call    cs:__imp_JetCloseDatabase
0x1800b088a  mov     rax, [rbp+instance]
0x1800b088e  mov     edi, ebx
0x1800b0890  mov     [r14], rax
0x1800b0893  mov     rax, [rbp+sesid]
0x1800b0897  mov     [r15], rax
0x1800b089a  mov     [rbp+dbid], 0FFFFFFFFh
0x1800b08a1  mov     [rbp+sesid], r13
0x1800b08a5  jmp     loc_1800B0751
```
