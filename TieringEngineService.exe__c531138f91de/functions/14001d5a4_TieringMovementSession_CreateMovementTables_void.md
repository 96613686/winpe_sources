# TieringMovementSession::CreateMovementTables(void)

- ea: `0x14001d5a4`
- end: `0x14001d7e3`
- name: `?CreateMovementTables@TieringMovementSession@@QEAAJXZ`
- size: `575`
- prototype: `__int64 __fastcall(TieringMovementSession *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x140031e04`

## callees

- `0x140004a68`
- `0x140004ef0`
- `0x140005420`
- `0x14000a700`
- `0x14000b7f8`
- `0x14001d534`
- `0x14001d5a4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001d7c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001d7c7`
- `ESENT!JetCloseTable` at `0x14001d724`
- `ESENT!JetCloseTable` at `0x14001d724`
- `ESENT!JetOpenTempTable` at `0x14001d666`
- `ESENT!JetOpenTempTable` at `0x14001d6cc`
- `ESENT!JetOpenTempTable` at `0x14001d666`
- `ESENT!JetOpenTempTable` at `0x14001d6cc`

## string_xrefs

- `0x14001d5c2`: `TieringMovementSession::CreateMovementTables`

## pseudocode

```c
__int64 __fastcall TieringMovementSession::CreateMovementTables(TieringMovementSession *this)
{
  unsigned int v2; // ebx
  JET_TABLEID *v3; // rbx
  JET_ERR v4; // eax
  _QWORD *v5; // rcx
  int v6; // edx
  JET_ERR v7; // eax
  JET_TABLEID v8; // rdx
  JET_SESID v9; // rcx
  int v10; // eax
  _BYTE v12[8]; // [rsp+30h] [rbp-68h] BYREF
  int v13; // [rsp+38h] [rbp-60h]
  HANDLE hObject[11]; // [rsp+40h] [rbp-58h] BYREF

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "TieringMovementSession::CreateMovementTables";
  CHResultImp::CHResultImp((CHResultImp *)v12);
  if ( TieringMovementSession::AreMovementTablesPresent(this) )
  {
    v2 = -2147019886;
    v13 = -2147019886;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        (unsigned int)&WPP_4dbeaefa85fc3f1a8f6f9e3221495bc3_Traceguids,
        *(_DWORD *)this + 696,
        146);
    }
    goto LABEL_30;
  }
  v3 = (JET_TABLEID *)((char *)this + 16);
  v4 = JetOpenTempTable(
         *((_QWORD *)this + 1),
         &g_FlashToDiskMovementColumnDefs,
         3u,
         2u,
         (JET_TABLEID *)this + 2,
         (JET_COLUMNID *)this + 8);
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_22;
    }
    v6 = 17;
    goto LABEL_21;
  }
  v7 = JetOpenTempTable(
         *((_QWORD *)this + 1),
         &g_DiskToFlashMovementColumnDefs,
         3u,
         2u,
         (JET_TABLEID *)this + 3,
         (JET_COLUMNID *)this + 11);
  if ( !v7 )
    goto LABEL_23;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Zd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      (unsigned int)&WPP_4dbeaefa85fc3f1a8f6f9e3221495bc3_Traceguids,
      *(_DWORD *)this + 696,
      v7);
  }
  v8 = *v3;
  v9 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 3) = -1;
  v4 = JetCloseTable(v9, v8);
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 19;
LABEL_21:
      WPP_SF_Zd(v5[2], v6, (unsigned int)&WPP_4dbeaefa85fc3f1a8f6f9e3221495bc3_Traceguids, *(_DWORD *)this + 696, v4);
    }
  }
LABEL_22:
  *v3 = -1;
LABEL_23:
  hObject[0] = 0;
  v10 = EnablePrivilegesInProcess((struct _BACKUP_PRIVILEGE_CONTEXT *)hObject);
  v13 = v10;
  v2 = v10;
  if ( v10 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      &WPP_4dbeaefa85fc3f1a8f6f9e3221495bc3_Traceguids,
      (unsigned int)v10);
  }
  if ( hObject[0] )
    CloseHandle(hObject[0]);
LABEL_30:
  CHResultImp::~CHResultImp((CHResultImp *)v12);
  return v2;
}

```

## disassembly

```asm
0x14001d5a4  push    rbx
0x14001d5a6  push    rbp
0x14001d5a7  push    rsi
0x14001d5a8  push    r13
0x14001d5aa  sub     rsp, 78h
0x14001d5ae  mov     rax, gs:58h
0x14001d5b7  mov     rsi, rcx
0x14001d5ba  mov     ecx, 8
0x14001d5bf  mov     rdx, [rax]
0x14001d5c2  lea     rax, aTieringmovemen_1; "TieringMovementSession::CreateMovementT"...
0x14001d5c9  mov     [rcx+rdx], rax
0x14001d5cd  lea     rcx, [rsp+98h+var_68]; this
0x14001d5d2  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14001d5d7  mov     rcx, rsi; this
0x14001d5da  call    ?AreMovementTablesPresent@TieringMovementSession@@QEAA_NXZ; TieringMovementSession::AreMovementTablesPresent(void)
0x14001d5df  test    al, al
0x14001d5e1  jz      short loc_14001D63F
0x14001d5e3  mov     ebx, 80071392h
0x14001d5e8  mov     [rsp+98h+var_60], ebx
0x14001d5ec  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d5f3  lea     rbp, WPP_GLOBAL_Control
0x14001d5fa  cmp     rcx, rbp
0x14001d5fd  jz      loc_14001D7CD
0x14001d603  test    byte ptr [rcx+1Ch], 1
0x14001d607  jz      loc_14001D7CD
0x14001d60d  cmp     byte ptr [rcx+19h], 2
0x14001d611  jb      loc_14001D7CD
0x14001d617  mov     r9, [rsi]
0x14001d61a  lea     r8, WPP_4dbeaefa85fc3f1a8f6f9e3221495bc3_Traceguids
0x14001d621  mov     rcx, [rcx+10h]
0x14001d625  add     r9, 2B8h
0x14001d62c  mov     edx, 10h
0x14001d631  mov     dword ptr [rsp+98h+ptableid], ebx
0x14001d635  call    WPP_SF_Zd
0x14001d63a  jmp     loc_14001D7CD
0x14001d63f  mov     rcx, [rsi+8]; sesid
0x14001d643  lea     rax, [rsi+20h]
0x14001d647  mov     r9d, 2; grbit
0x14001d64d  mov     [rsp+98h+prgcolumnid], rax; prgcolumnid
0x14001d652  lea     rbx, [rsi+10h]
0x14001d656  lea     rdx, ?g_FlashToDiskMovementColumnDefs@@3QBUJET_COLUMNDEF@@B; prgcolumndef
0x14001d65d  mov     [rsp+98h+ptableid], rbx; ptableid
0x14001d662  lea     r8d, [r9+1]; ccolumn
0x14001d666  call    cs:__imp_JetOpenTempTable
0x14001d66c  lea     rbp, WPP_GLOBAL_Control
0x14001d673  test    eax, eax
0x14001d675  jz      short loc_14001D6A5
0x14001d677  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d67e  cmp     rcx, rbp
0x14001d681  jz      loc_14001D769
0x14001d687  test    byte ptr [rcx+1Ch], 1
0x14001d68b  jz      loc_14001D769
0x14001d691  cmp     byte ptr [rcx+19h], 2
0x14001d695  jb      loc_14001D769
0x14001d69b  mov     edx, 11h
0x14001d6a0  jmp     loc_14001D74B
0x14001d6a5  mov     rcx, [rsi+8]; sesid
0x14001d6a9  lea     rax, [rsi+2Ch]
0x14001d6ad  mov     r9d, 2; grbit
0x14001d6b3  mov     [rsp+98h+prgcolumnid], rax; prgcolumnid
0x14001d6b8  lea     r13, [rsi+18h]
0x14001d6bc  lea     rdx, ?g_DiskToFlashMovementColumnDefs@@3QBUJET_COLUMNDEF@@B; prgcolumndef
0x14001d6c3  mov     [rsp+98h+ptableid], r13; ptableid
0x14001d6c8  lea     r8d, [r9+1]; ccolumn
0x14001d6cc  call    cs:__imp_JetOpenTempTable
0x14001d6d2  test    eax, eax
0x14001d6d4  jz      loc_14001D770
0x14001d6da  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d6e1  cmp     rcx, rbp
0x14001d6e4  jz      short loc_14001D715
0x14001d6e6  test    byte ptr [rcx+1Ch], 1
0x14001d6ea  jz      short loc_14001D715
0x14001d6ec  cmp     byte ptr [rcx+19h], 2
0x14001d6f0  jb      short loc_14001D715
0x14001d6f2  mov     r9, [rsi]
0x14001d6f5  lea     r8, WPP_4dbeaefa85fc3f1a8f6f9e3221495bc3_Traceguids
0x14001d6fc  mov     rcx, [rcx+10h]
0x14001d700  add     r9, 2B8h
0x14001d707  mov     edx, 12h
0x14001d70c  mov     dword ptr [rsp+98h+ptableid], eax
0x14001d710  call    WPP_SF_Zd
0x14001d715  mov     rdx, [rbx]; tableid
0x14001d718  mov     rcx, [rsi+8]; sesid
0x14001d71c  mov     qword ptr [r13+0], 0FFFFFFFFFFFFFFFFh
0x14001d724  call    cs:__imp_JetCloseTable
0x14001d72a  test    eax, eax
0x14001d72c  jz      short loc_14001D769
0x14001d72e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d735  cmp     rcx, rbp
0x14001d738  jz      short loc_14001D769
0x14001d73a  test    byte ptr [rcx+1Ch], 1
0x14001d73e  jz      short loc_14001D769
0x14001d740  cmp     byte ptr [rcx+19h], 2
0x14001d744  jb      short loc_14001D769
0x14001d746  mov     edx, 13h
0x14001d74b  mov     r9, [rsi]
0x14001d74e  lea     r8, WPP_4dbeaefa85fc3f1a8f6f9e3221495bc3_Traceguids
0x14001d755  mov     rcx, [rcx+10h]
0x14001d759  add     r9, 2B8h
0x14001d760  mov     dword ptr [rsp+98h+ptableid], eax
0x14001d764  call    WPP_SF_Zd
0x14001d769  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x14001d770  lea     rcx, [rsp+98h+hObject]; struct _BACKUP_PRIVILEGE_CONTEXT *
0x14001d775  mov     [rsp+98h+hObject], 0
0x14001d77e  call    ?EnablePrivilegesInProcess@@YAJPEAU_BACKUP_PRIVILEGE_CONTEXT@@@Z; EnablePrivilegesInProcess(_BACKUP_PRIVILEGE_CONTEXT *)
0x14001d783  mov     [rsp+98h+var_60], eax
0x14001d787  mov     ebx, eax
0x14001d789  test    eax, eax
0x14001d78b  jns     short loc_14001D7BD
0x14001d78d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d794  cmp     rcx, rbp
0x14001d797  jz      short loc_14001D7BD
0x14001d799  test    byte ptr [rcx+1Ch], 1
0x14001d79d  jz      short loc_14001D7BD
0x14001d79f  cmp     byte ptr [rcx+19h], 2
0x14001d7a3  jb      short loc_14001D7BD
0x14001d7a5  mov     rcx, [rcx+10h]
0x14001d7a9  lea     r8, WPP_4dbeaefa85fc3f1a8f6f9e3221495bc3_Traceguids
0x14001d7b0  mov     edx, 14h
0x14001d7b5  mov     r9d, eax
0x14001d7b8  call    WPP_SF_d
0x14001d7bd  mov     rcx, [rsp+98h+hObject]; hObject
0x14001d7c2  test    rcx, rcx
0x14001d7c5  jz      short loc_14001D7CD
0x14001d7c7  call    cs:__imp_CloseHandle
0x14001d7cd  lea     rcx, [rsp+98h+var_68]; this
0x14001d7d2  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x14001d7d7  mov     eax, ebx
0x14001d7d9  add     rsp, 78h
0x14001d7dd  pop     r13
0x14001d7df  pop     rsi
0x14001d7e0  pop     rbp
0x14001d7e1  pop     rbx
0x14001d7e2  retn
```
