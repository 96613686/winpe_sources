# CreateCacheDatabaseIfNeeded(unsigned __int64,ushort const *)

- ea: `0x1800afc90`
- end: `0x1800afe17`
- name: `?CreateCacheDatabaseIfNeeded@@YAJ_KPEBG@Z`
- size: `391`
- prototype: `__int64 __fastcall(JET_INSTANCE instance, JET_PCWSTR szFilename)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1800b0660`

## callees

- `0x18007ec9c`
- `0x1800afc90`
- `0x18014a7a0`
- `0x1801e1790`
- `0x1801e7ec4`

## import_xrefs

- `ESENT!JetCreateDatabaseW` at `0x1800afd1b`
- `ESENT!JetCreateDatabaseW` at `0x1800afd1b`
- `ESENT!JetCreateTableW` at `0x1800afd63`
- `ESENT!JetCreateTableW` at `0x1800afd63`
- `ESENT!JetCloseTable` at `0x1800afd88`
- `ESENT!JetCloseTable` at `0x1800afd88`
- `ESENT!JetCloseDatabase` at `0x1800afdb5`
- `ESENT!JetCloseDatabase` at `0x1800afdb5`
- `ESENT!JetBeginSessionA` at `0x1800afcf0`
- `ESENT!JetBeginSessionA` at `0x1800afcf0`
- `ESENT!JetDeleteTableW` at `0x1800afda0`
- `ESENT!JetDeleteTableW` at `0x1800afda0`
- `ESENT!JetEndSession` at `0x1800afdcd`
- `ESENT!JetEndSession` at `0x1800afdcd`

## pseudocode

```c
__int64 __fastcall CreateCacheDatabaseIfNeeded(JET_INSTANCE instance, JET_PCWSTR szFilename, int a3)
{
  JET_ERR v5; // eax
  int v6; // ebx
  JET_ERR v7; // eax
  JET_ERR v8; // eax
  JET_DBID pdbid; // [rsp+30h] [rbp-20h] BYREF
  JET_SESID psesid; // [rsp+38h] [rbp-18h] BYREF
  JET_TABLEID tableid; // [rsp+40h] [rbp-10h] BYREF

  psesid = -1;
  tableid = -1;
  pdbid = -1;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_iS(instance, (_DWORD)szFilename, a3, instance, (__int64)szFilename);
  v5 = JetBeginSessionA(instance, &psesid, 0, 0);
  v6 = HRESULTFromJET_ERR(v5, 0);
  if ( v6 >= 0 )
  {
    v7 = JetCreateDatabaseW(psesid, szFilename, 0, &pdbid, 0);
    if ( v7 == -1201 )
    {
      v6 = 1;
    }
    else
    {
      v6 = HRESULTFromJET_ERR(v7, 0);
      if ( v6 >= 0 )
      {
        v8 = JetCreateTableW(psesid, pdbid, L"PreGrow", 0x180u, 0x64u, &tableid);
        v6 = HRESULTFromJET_ERR(v8, 0);
        if ( v6 >= 0 )
          v6 = 0;
      }
    }
  }
  if ( tableid != -1 )
  {
    JetCloseTable(psesid, tableid);
    tableid = -1;
    JetDeleteTableW(psesid, pdbid, L"PreGrow");
  }
  if ( pdbid != -1 )
  {
    JetCloseDatabase(psesid, pdbid, 0);
    pdbid = -1;
  }
  if ( psesid != -1 )
  {
    JetEndSession(psesid, 0);
    psesid = -1;
  }
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 44, &WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids, (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800afc90  mov     [rsp-18h+arg_10], rbx
0x1800afc95  push    rbp
0x1800afc96  push    rsi
0x1800afc97  push    rdi
0x1800afc98  mov     rbp, rsp
0x1800afc9b  sub     rsp, 50h
0x1800afc9f  mov     rax, cs:__security_cookie
0x1800afca6  xor     rax, rsp
0x1800afca9  mov     [rbp+var_8], rax
0x1800afcad  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800afcb1  mov     dword ptr [rbp+tableid+4], 0
0x1800afcb8  mov     [rbp+psesid], rsi
0x1800afcbc  mov     rdi, rdx
0x1800afcbf  mov     [rbp-10h], rsi
0x1800afcc3  mov     rbx, rcx
0x1800afcc6  mov     [rbp+pdbid], 0FFFFFFFFh
0x1800afccd  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800afcd4  jz      short loc_1800AFCE3
0x1800afcd6  mov     r9, rcx
0x1800afcd9  mov     qword ptr [rsp+50h+grbit], rdx
0x1800afcde  call    WPP_SF_iS
0x1800afce3  xor     r9d, r9d; szPassword
0x1800afce6  lea     rdx, [rbp+psesid]; psesid
0x1800afcea  xor     r8d, r8d; szUserName
0x1800afced  mov     rcx, rbx; instance
0x1800afcf0  call    cs:__imp_JetBeginSessionA
0x1800afcf6  mov     ecx, eax; int
0x1800afcf8  xor     edx, edx; int
0x1800afcfa  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800afcff  mov     ebx, eax
0x1800afd01  test    eax, eax
0x1800afd03  js      short loc_1800AFD7B
0x1800afd05  mov     rcx, [rbp+psesid]; sesid
0x1800afd09  lea     r9, [rbp+pdbid]; pdbid
0x1800afd0d  xor     r8d, r8d; szConnect
0x1800afd10  mov     [rsp+50h+grbit], 0; grbit
0x1800afd18  mov     rdx, rdi; szFilename
0x1800afd1b  call    cs:__imp_JetCreateDatabaseW
0x1800afd21  cmp     eax, 0FFFFFB4Fh
0x1800afd26  jnz     short loc_1800AFD2F
0x1800afd28  mov     ebx, 1
0x1800afd2d  jmp     short loc_1800AFD7B
0x1800afd2f  xor     edx, edx; int
0x1800afd31  mov     ecx, eax; int
0x1800afd33  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800afd38  mov     ebx, eax
0x1800afd3a  test    eax, eax
0x1800afd3c  js      short loc_1800AFD7B
0x1800afd3e  mov     edx, [rbp+pdbid]; dbid
0x1800afd41  lea     rax, [rbp+tableid]
0x1800afd45  mov     rcx, [rbp+psesid]; sesid
0x1800afd49  lea     r8, szTableName; "PreGrow"
0x1800afd50  mov     [rsp+50h+ptableid], rax; ptableid
0x1800afd55  mov     r9d, 180h; lPages
0x1800afd5b  mov     [rsp+50h+grbit], 64h ; 'd'; lDensity
0x1800afd63  call    cs:__imp_JetCreateTableW
0x1800afd69  mov     ecx, eax; int
0x1800afd6b  xor     edx, edx; int
0x1800afd6d  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800afd72  mov     ebx, eax
0x1800afd74  xor     eax, eax
0x1800afd76  test    ebx, ebx
0x1800afd78  cmovns  ebx, eax
0x1800afd7b  mov     rdx, [rbp+tableid]; tableid
0x1800afd7f  cmp     rdx, rsi
0x1800afd82  jz      short loc_1800AFDA6
0x1800afd84  mov     rcx, [rbp+psesid]; sesid
0x1800afd88  call    cs:__imp_JetCloseTable
0x1800afd8e  mov     edx, [rbp+pdbid]; dbid
0x1800afd91  lea     r8, szTableName; "PreGrow"
0x1800afd98  mov     rcx, [rbp+psesid]; sesid
0x1800afd9c  mov     [rbp+tableid], rsi
0x1800afda0  call    cs:__imp_JetDeleteTableW
0x1800afda6  mov     edx, [rbp+pdbid]; dbid
0x1800afda9  cmp     edx, 0FFFFFFFFh
0x1800afdac  jz      short loc_1800AFDC2
0x1800afdae  mov     rcx, [rbp+psesid]; sesid
0x1800afdb2  xor     r8d, r8d; grbit
0x1800afdb5  call    cs:__imp_JetCloseDatabase
0x1800afdbb  mov     [rbp+pdbid], 0FFFFFFFFh
0x1800afdc2  mov     rcx, [rbp+psesid]; sesid
0x1800afdc6  cmp     rcx, rsi
0x1800afdc9  jz      short loc_1800AFDD7
0x1800afdcb  xor     edx, edx; grbit
0x1800afdcd  call    cs:__imp_JetEndSession
0x1800afdd3  mov     [rbp+psesid], rsi
0x1800afdd7  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800afdde  jz      short loc_1800AFDF9
0x1800afde0  mov     edx, 2Ch ; ','
0x1800afde5  lea     r8, WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids
0x1800afdec  mov     ecx, 40Ch
0x1800afdf1  mov     r9d, ebx
0x1800afdf4  call    WPP_SF_d
0x1800afdf9  mov     eax, ebx
0x1800afdfb  mov     rcx, [rbp+var_8]
0x1800afdff  xor     rcx, rsp; StackCookie
0x1800afe02  call    __security_check_cookie
0x1800afe07  mov     rbx, [rsp+50h+arg_10]
0x1800afe0f  add     rsp, 50h
0x1800afe13  pop     rdi
0x1800afe14  pop     rsi
0x1800afe15  pop     rbp
0x1800afe16  retn
```
