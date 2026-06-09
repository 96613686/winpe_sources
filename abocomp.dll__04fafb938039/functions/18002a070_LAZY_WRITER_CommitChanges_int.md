# LAZY_WRITER::CommitChanges(int)

- ea: `0x18002a070`
- end: `0x18002a2a1`
- name: `?CommitChanges@LAZY_WRITER@@QEAAJH@Z`
- size: `561`
- prototype: `__int64 __fastcall(LAZY_WRITER *__hidden this, int)`
- caller_count: `5`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003d18`
- `0x18000f330`
- `0x18000f390`
- `0x18000f65c`
- `0x18002a2b0`

## callees

- `0x180001f90`
- `0x180005c1c`
- `0x180005ec0`
- `0x180005f68`
- `0x18000d544`
- `0x18000ef20`
- `0x18002a004`
- `0x18002a070`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a285`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a285`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a0ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a15e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a1a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a206`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a0ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a15e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a1a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a206`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18002a0e0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18002a0e0`

## string_xrefs

- `0x18002a09f`: ` Commit Changes called with invalid tree. Tree not commited. `
- `0x18002a105`: `Could not create Lazy Write Timer %X, committing right now`
- `0x18002a13c`: `Failed to commit changes because configuration has changed`
- `0x18002a175`: `Failed to Persist Custom properties during CommitChanges = %X`
- `0x18002a1bf`: `Failed to commit changes due to Error = %X`
- `0x18002a21d`: `Failed to commit changes due to Error = %X`
- `0x18002a242`: `Commit changes called on a tree that has not been modified`
- `0x18002a26e`: `Commit changes returned an error. %X`

## pseudocode

```c
__int64 __fastcall LAZY_WRITER::CommitChanges(DWORD *this, int a2)
{
  HANDLE v2; // rdi
  int v3; // ebx
  __int64 v5; // rsi
  DWORD DueTime; // eax
  void **v7; // rcx
  signed int LastError; // eax
  signed int v9; // eax
  int v10; // eax
  signed int v11; // eax
  signed int v12; // eax
  HANDLE hObject; // [rsp+70h] [rbp+18h] BYREF

  v2 = 0;
  v3 = 0;
  hObject = 0;
  v5 = *((_QWORD *)g_pAboWrapper + 3);
  if ( !v5 )
  {
    ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L" Commit Changes called with invalid tree. Tree not commited. ");
    goto LABEL_32;
  }
  DueTime = *this;
  if ( *this && !a2 )
  {
    v7 = (void **)(this + 2);
    if ( *v7 || CreateTimerQueueTimer(v7, 0, LazyTimerCallBack, 0, DueTime, 0, 0) )
      goto LABEL_32;
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    ABO_MAPPER_LOG::WriteLogEntry(
      g_pAboLog,
      L"Could not create Lazy Write Timer %X, committing right now",
      (unsigned int)LastError);
  }
  if ( *(_DWORD *)(v5 + 12) )
  {
    LAZY_WRITER::ClearTimer((LAZY_WRITER *)this);
    if ( !(unsigned int)ABO_WRAPPER::FTreeValid(g_pAboWrapper) )
    {
      ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L"Failed to commit changes because configuration has changed");
      v3 = -2147024864;
      goto LABEL_32;
    }
    if ( (int)ABO_TREE::PersistCustomNodesAndProperties((ABO_TREE *)v5) < 0 )
    {
      v9 = GetLastError();
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      ABO_MAPPER_LOG::WriteLogEntry(
        g_pAboLog,
        L"Failed to Persist Custom properties during CommitChanges = %X",
        (unsigned int)v9);
    }
    v10 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v5 + 32) + 80LL))(*(_QWORD *)(v5 + 32));
    v3 = v10;
    if ( v10 >= 0 )
      goto LABEL_23;
    if ( v10 != -2147023550 && v10 != -2147024891 )
    {
      v11 = GetLastError();
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L"Failed to commit changes due to Error = %X", (unsigned int)v11);
LABEL_23:
      ABO_WRAPPER::ReleaseTree(g_pAboWrapper);
      goto LABEL_32;
    }
    v3 = SetCurrentThreadToken(*(HANDLE *)(v5 + 56), &hObject);
    if ( v3 >= 0 )
    {
      v3 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v5 + 32) + 80LL))(*(_QWORD *)(v5 + 32));
      if ( v3 < 0 )
      {
        v12 = GetLastError();
        if ( v12 > 0 )
          v12 = (unsigned __int16)v12 | 0x80070000;
        ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L"Failed to commit changes due to Error = %X", (unsigned int)v12);
      }
      v2 = hObject;
      RevertThreadToken(hObject);
      goto LABEL_23;
    }
    v2 = hObject;
  }
  else
  {
    ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L"Commit changes called on a tree that has not been modified");
  }
LABEL_32:
  _InterlockedIncrement((volatile signed __int32 *)g_pAboWrapper + 32);
  if ( v3 < 0 )
    ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L"Commit changes returned an error. %X", (unsigned int)v3);
  if ( v2 )
    CloseHandle(v2);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002a070  mov     [rsp+arg_0], rbx
0x18002a075  mov     [rsp+arg_8], rsi
0x18002a07a  push    rdi
0x18002a07b  push    r14
0x18002a07d  push    r15
0x18002a07f  sub     rsp, 40h
0x18002a083  mov     rax, cs:?g_pAboWrapper@@3PEAVABO_WRAPPER@@EA; ABO_WRAPPER * g_pAboWrapper
0x18002a08a  xor     edi, edi
0x18002a08c  xor     ebx, ebx
0x18002a08e  mov     [rsp+58h+hObject], rdi
0x18002a093  mov     r14, rcx
0x18002a096  mov     rsi, [rax+18h]
0x18002a09a  test    rsi, rsi
0x18002a09d  jnz     short loc_18002A0AB
0x18002a09f  lea     rdx, aCommitChangesC_0; " Commit Changes called with invalid tre"...
0x18002a0a6  jmp     loc_18002A249
0x18002a0ab  mov     eax, [rcx]
0x18002a0ad  mov     r15d, 80070000h
0x18002a0b3  test    eax, eax
0x18002a0b5  jz      short loc_18002A114
0x18002a0b7  test    edx, edx
0x18002a0b9  jnz     short loc_18002A114
0x18002a0bb  add     rcx, 8; phNewTimer
0x18002a0bf  cmp     [rcx], rbx
0x18002a0c2  jnz     loc_18002A255
0x18002a0c8  mov     [rsp+58h+Flags], ebx; Flags
0x18002a0cc  lea     r8, LazyTimerCallBack; Callback
0x18002a0d3  mov     [rsp+58h+Period], ebx; Period
0x18002a0d7  xor     r9d, r9d; Parameter
0x18002a0da  xor     edx, edx; TimerQueue
0x18002a0dc  mov     [rsp+58h+DueTime], eax; DueTime
0x18002a0e0  call    cs:__imp_CreateTimerQueueTimer
0x18002a0e6  test    eax, eax
0x18002a0e8  jnz     loc_18002A255
0x18002a0ee  call    cs:__imp_GetLastError
0x18002a0f4  test    eax, eax
0x18002a0f6  jle     short loc_18002A0FE
0x18002a0f8  movzx   eax, ax
0x18002a0fb  or      eax, r15d
0x18002a0fe  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18002a105  lea     rdx, aCouldNotCreate; "Could not create Lazy Write Timer %X, c"...
0x18002a10c  mov     r8d, eax
0x18002a10f  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18002a114  cmp     [rsi+0Ch], ebx
0x18002a117  jz      loc_18002A242
0x18002a11d  mov     rcx, r14; this
0x18002a120  call    ?ClearTimer@LAZY_WRITER@@QEAAXXZ; LAZY_WRITER::ClearTimer(void)
0x18002a125  mov     rcx, cs:?g_pAboWrapper@@3PEAVABO_WRAPPER@@EA; this
0x18002a12c  call    ?FTreeValid@ABO_WRAPPER@@QEAAHXZ; ABO_WRAPPER::FTreeValid(void)
0x18002a131  test    eax, eax
0x18002a133  jnz     short loc_18002A152
0x18002a135  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18002a13c  lea     rdx, aFailedToCommit_1; "Failed to commit changes because config"...
0x18002a143  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18002a148  mov     ebx, 80070020h
0x18002a14d  jmp     loc_18002A255
0x18002a152  mov     rcx, rsi; this
0x18002a155  call    ?PersistCustomNodesAndProperties@ABO_TREE@@QEAAJXZ; ABO_TREE::PersistCustomNodesAndProperties(void)
0x18002a15a  test    eax, eax
0x18002a15c  jns     short loc_18002A184
0x18002a15e  call    cs:__imp_GetLastError
0x18002a164  test    eax, eax
0x18002a166  jle     short loc_18002A16E
0x18002a168  movzx   eax, ax
0x18002a16b  or      eax, r15d
0x18002a16e  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18002a175  lea     rdx, aFailedToPersis; "Failed to Persist Custom properties dur"...
0x18002a17c  mov     r8d, eax
0x18002a17f  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18002a184  mov     rcx, [rsi+20h]
0x18002a188  mov     rax, [rcx]
0x18002a18b  mov     rax, [rax+50h]
0x18002a18f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a194  mov     ebx, eax
0x18002a196  test    eax, eax
0x18002a198  jns     short loc_18002A1CE
0x18002a19a  cmp     eax, 80070542h
0x18002a19f  jz      short loc_18002A1DC
0x18002a1a1  cmp     eax, 80070005h
0x18002a1a6  jz      short loc_18002A1DC
0x18002a1a8  call    cs:__imp_GetLastError
0x18002a1ae  test    eax, eax
0x18002a1b0  jle     short loc_18002A1B8
0x18002a1b2  movzx   eax, ax
0x18002a1b5  or      eax, r15d
0x18002a1b8  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18002a1bf  lea     rdx, aFailedToCommit; "Failed to commit changes due to Error ="...
0x18002a1c6  mov     r8d, eax
0x18002a1c9  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18002a1ce  mov     rcx, cs:?g_pAboWrapper@@3PEAVABO_WRAPPER@@EA; this
0x18002a1d5  call    ?ReleaseTree@ABO_WRAPPER@@QEAAXXZ; ABO_WRAPPER::ReleaseTree(void)
0x18002a1da  jmp     short loc_18002A255
0x18002a1dc  mov     rcx, [rsi+38h]; Token
0x18002a1e0  lea     rdx, [rsp+58h+hObject]; void **
0x18002a1e5  call    ?SetCurrentThreadToken@@YAJPEAXPEAPEAX@Z; SetCurrentThreadToken(void *,void * *)
0x18002a1ea  mov     ebx, eax
0x18002a1ec  test    eax, eax
0x18002a1ee  js      short loc_18002A23B
0x18002a1f0  mov     rcx, [rsi+20h]
0x18002a1f4  mov     rax, [rcx]
0x18002a1f7  mov     rax, [rax+50h]
0x18002a1fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a200  mov     ebx, eax
0x18002a202  test    eax, eax
0x18002a204  jns     short loc_18002A22C
0x18002a206  call    cs:__imp_GetLastError
0x18002a20c  test    eax, eax
0x18002a20e  jle     short loc_18002A216
0x18002a210  movzx   eax, ax
0x18002a213  or      eax, r15d
0x18002a216  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18002a21d  lea     rdx, aFailedToCommit; "Failed to commit changes due to Error ="...
0x18002a224  mov     r8d, eax
0x18002a227  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18002a22c  mov     rdi, [rsp+58h+hObject]
0x18002a231  mov     rcx, rdi; hObject
0x18002a234  call    ?RevertThreadToken@@YAXPEAX@Z; RevertThreadToken(void *)
0x18002a239  jmp     short loc_18002A1CE
0x18002a23b  mov     rdi, [rsp+58h+hObject]
0x18002a240  jmp     short loc_18002A255
0x18002a242  lea     rdx, aCommitChangesC; "Commit changes called on a tree that ha"...
0x18002a249  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18002a250  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18002a255  mov     rax, cs:?g_pAboWrapper@@3PEAVABO_WRAPPER@@EA; ABO_WRAPPER * g_pAboWrapper
0x18002a25c  lock inc dword ptr [rax+80h]
0x18002a263  test    ebx, ebx
0x18002a265  jns     short loc_18002A27D
0x18002a267  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18002a26e  lea     rdx, aCommitChangesR; "Commit changes returned an error. %X"
0x18002a275  mov     r8d, ebx
0x18002a278  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18002a27d  test    rdi, rdi
0x18002a280  jz      short loc_18002A28B
0x18002a282  mov     rcx, rdi; hObject
0x18002a285  call    cs:__imp_CloseHandle
0x18002a28b  mov     rsi, [rsp+58h+arg_8]
0x18002a290  mov     eax, ebx
0x18002a292  mov     rbx, [rsp+58h+arg_0]
0x18002a297  add     rsp, 40h
0x18002a29b  pop     r15
0x18002a29d  pop     r14
0x18002a29f  pop     rdi
0x18002a2a0  retn
```
