# CPimcManager::UninstallWindowHook(CPimcContext *)

- ea: `0x18000b39c`
- end: `0x18000b5cd`
- name: `?UninstallWindowHook@CPimcManager@@QEAAJPEAVCPimcContext@@@Z`
- size: `561`
- prototype: `__int64 __fastcall(CPimcManager *__hidden this, struct CPimcContext *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x1800062a0`
- `0x180009f28`

## callees

- `0x18000ac94`
- `0x18000b39c`
- `0x18000ce0c`
- `0x18000e484`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18000b3ca`
- `KERNEL32!WaitForSingleObject` at `0x18000b3ca`
- `KERNEL32!ReleaseMutex` at `0x18000b579`
- `KERNEL32!ReleaseMutex` at `0x18000b579`
- `KERNEL32!CancelWaitableTimer` at `0x18000b517`
- `KERNEL32!CancelWaitableTimer` at `0x18000b517`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CPimcManager::UninstallWindowHook(CPimcManager *this, struct CPimcContext *a2)
{
  char v4; // r15
  DWORD v5; // ebx
  __int64 v6; // rdi
  __int64 v7; // rsi
  __int64 v8; // rdx
  int v9; // ecx
  __int64 v10; // r10
  struct CPimcContext **v11; // r9
  int v12; // r14d
  __int64 v13; // rcx
  __int64 v14; // rax
  void *v15; // rcx
  __int64 v16; // rcx
  int v17; // edx
  __int64 v18; // r10
  __int64 i; // rdx
  __int64 j; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rax
  void *v26; // rcx

  v4 = 0;
  v5 = 0;
  if ( g_hMutexHook )
    v5 = WaitForSingleObject(g_hMutexHook, 0xFFFFFFFF);
  v6 = *((_QWORD *)a2 + 21);
  v7 = *((_QWORD *)a2 + 22);
  v8 = 0;
  v9 = *(_DWORD *)(v7 + 60);
  if ( v9 )
  {
    v10 = *(_QWORD *)(v7 + 48);
    while ( 1 )
    {
      v11 = (struct CPimcContext **)(v10 + 8 * v8);
      if ( *v11 == a2 )
        break;
      v8 = (unsigned int)(v8 + 1);
    }
    if ( (unsigned int)v8 < v9 - 1 )
    {
      memcpy_0(v11, (const void *)(v10 + 8LL * (unsigned int)(v8 + 1)), (unsigned int)(8 * (v9 - v8) - 8));
      v9 = *(_DWORD *)(v7 + 60);
    }
    *(_DWORD *)(v7 + 60) = --v9;
  }
  v12 = *(_DWORD *)(v7 + 8);
  if ( !v9 )
  {
    v13 = *(_QWORD *)(v7 + 64);
    v14 = *(_QWORD *)(v7 + 72);
    if ( v13 )
      *(_QWORD *)(v13 + 72) = v14;
    if ( v14 )
      *(_QWORD *)(v14 + 64) = v13;
    if ( *((_QWORD *)this + 2) == v7 )
      *((_QWORD *)this + 2) = v14;
    if ( *((_QWORD *)this + 3) == v7 )
      *((_QWORD *)this + 3) = v13;
    v15 = *(void **)(v7 + 48);
    if ( v15 && v15 != (void *)(v7 + 32) )
      operator delete(v15);
    operator delete((void *)v7);
    if ( !*((_QWORD *)this + 2) )
    {
      v16 = 0;
      v17 = *(_DWORD *)(v6 + 52);
      if ( v17 )
      {
        v18 = *(_QWORD *)(v6 + 40);
        while ( *(CPimcManager **)(v18 + 8 * v16) != this )
          v16 = (unsigned int)(v16 + 1);
        if ( (unsigned int)v16 < v17 - 1 )
        {
          memcpy_0(
            (void *)(v18 + 8 * v16),
            (const void *)(v18 + 8LL * (unsigned int)(v16 + 1)),
            (unsigned int)(8 * (v17 - v16) - 8));
          v17 = *(_DWORD *)(v6 + 52);
        }
        *(_DWORD *)(v6 + 52) = v17 - 1;
      }
    }
  }
  if ( v12 && (*(_BYTE *)(v6 + 96) & 1) != 0 )
  {
    for ( i = 0; (int)i < *(_DWORD *)(v6 + 52); i = (unsigned int)(i + 1) )
    {
      for ( j = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v6 + 40) + 8 * i) + 16LL); j; j = *(_QWORD *)(j + 72) )
      {
        if ( *(_DWORD *)(j + 8) )
          goto LABEL_39;
      }
    }
    CancelWaitableTimer(*(HANDLE *)(v6 + 88));
    *(_DWORD *)(v6 + 96) &= ~1u;
  }
LABEL_39:
  if ( (*(_DWORD *)(v6 + 16))-- == 1 )
  {
    v22 = *(_QWORD *)(v6 + 104);
    v23 = *(_QWORD *)(v6 + 112);
    if ( v22 )
      *(_QWORD *)(v22 + 112) = v23;
    if ( v23 )
      *(_QWORD *)(v23 + 104) = v22;
    v24 = g_HookThreadMap;
    if ( g_HookThreadMap == v6 )
      v24 = v23;
    g_HookThreadMap = v24;
    v25 = qword_180018A50;
    if ( qword_180018A50 == v6 )
      v25 = v22;
    qword_180018A50 = v25;
    v4 = 1;
  }
  if ( !v5 )
    ReleaseMutex(g_hMutexHook);
  if ( v4 )
  {
    CPimcManager::TerminateHookThread((struct CHookThreadItem *)v6);
    v26 = *(void **)(v6 + 40);
    if ( v26 && v26 != (void *)(v6 + 24) )
      operator delete(v26);
    operator delete((void *)v6);
  }
  return 0;
}

```

## disassembly

```asm
0x18000b39c  mov     [rsp+arg_0], rbx
0x18000b3a1  push    rbp
0x18000b3a2  push    rsi
0x18000b3a3  push    rdi
0x18000b3a4  push    r14
0x18000b3a6  push    r15
0x18000b3a8  sub     rsp, 20h
0x18000b3ac  mov     r14, rdx
0x18000b3af  mov     rbp, rcx
0x18000b3b2  xor     r15b, r15b
0x18000b3b5  xor     ebx, ebx
0x18000b3b7  mov     dword ptr [rsp+48h+arg_8], ebx
0x18000b3bb  mov     rcx, cs:?g_hMutexHook@@3PEAXEA; hHandle
0x18000b3c2  test    rcx, rcx
0x18000b3c5  jz      short loc_18000B3D6
0x18000b3c7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000b3ca  call    cs:__imp_WaitForSingleObject
0x18000b3d0  mov     ebx, eax
0x18000b3d2  mov     dword ptr [rsp+48h+arg_8], eax
0x18000b3d6  mov     rdi, [r14+0A8h]
0x18000b3dd  mov     rsi, [r14+0B0h]
0x18000b3e4  xor     edx, edx
0x18000b3e6  mov     ecx, [rsi+3Ch]
0x18000b3e9  test    ecx, ecx
0x18000b3eb  jz      short loc_18000B426
0x18000b3ed  mov     r10, [rsi+30h]
0x18000b3f1  lea     r9, [r10+rdx*8]
0x18000b3f5  cmp     [r9], r14
0x18000b3f8  jz      short loc_18000B3FE
0x18000b3fa  inc     edx
0x18000b3fc  jmp     short loc_18000B3F1
0x18000b3fe  lea     eax, [rcx-1]
0x18000b401  cmp     edx, eax
0x18000b403  jnb     short loc_18000B421
0x18000b405  sub     ecx, edx
0x18000b407  lea     r8d, ds:0FFFFFFFFFFFFFFF8h[rcx*8]; Size
0x18000b40f  lea     eax, [rdx+1]
0x18000b412  lea     rdx, [r10+rax*8]; Src
0x18000b416  mov     rcx, r9; void *
0x18000b419  call    memcpy_0
0x18000b41e  mov     ecx, [rsi+3Ch]
0x18000b421  dec     ecx
0x18000b423  mov     [rsi+3Ch], ecx
0x18000b426  mov     r14d, [rsi+8]
0x18000b42a  test    ecx, ecx
0x18000b42c  jnz     loc_18000B4DD
0x18000b432  mov     rcx, [rsi+40h]
0x18000b436  mov     rax, [rsi+48h]
0x18000b43a  test    rcx, rcx
0x18000b43d  jz      short loc_18000B443
0x18000b43f  mov     [rcx+48h], rax
0x18000b443  test    rax, rax
0x18000b446  jz      short loc_18000B44C
0x18000b448  mov     [rax+40h], rcx
0x18000b44c  cmp     [rbp+10h], rsi
0x18000b450  jnz     short loc_18000B456
0x18000b452  mov     [rbp+10h], rax
0x18000b456  cmp     [rbp+18h], rsi
0x18000b45a  jnz     short loc_18000B460
0x18000b45c  mov     [rbp+18h], rcx
0x18000b460  mov     [rsp+48h+arg_10], rsi
0x18000b465  mov     [rsp+48h+arg_18], rsi
0x18000b46a  lea     rax, [rsi+20h]
0x18000b46e  mov     rcx, [rax+10h]; Block
0x18000b472  test    rcx, rcx
0x18000b475  jz      short loc_18000B486
0x18000b477  cmp     rcx, rax
0x18000b47a  jz      short loc_18000B486
0x18000b47c  mov     edx, 8
0x18000b481  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000b486  mov     edx, 50h ; 'P'
0x18000b48b  mov     rcx, rsi; Block
0x18000b48e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000b493  cmp     qword ptr [rbp+10h], 0
0x18000b498  jnz     short loc_18000B4DD
0x18000b49a  xor     ecx, ecx
0x18000b49c  mov     edx, [rdi+34h]
0x18000b49f  test    edx, edx
0x18000b4a1  jz      short loc_18000B4DD
0x18000b4a3  mov     r10, [rdi+28h]
0x18000b4a7  lea     r9, [r10+rcx*8]
0x18000b4ab  cmp     [r9], rbp
0x18000b4ae  jz      short loc_18000B4B4
0x18000b4b0  inc     ecx
0x18000b4b2  jmp     short loc_18000B4A7
0x18000b4b4  lea     eax, [rdx-1]
0x18000b4b7  cmp     ecx, eax
0x18000b4b9  jnb     short loc_18000B4D7
0x18000b4bb  sub     edx, ecx
0x18000b4bd  lea     r8d, ds:0FFFFFFFFFFFFFFF8h[rdx*8]; Size
0x18000b4c5  lea     eax, [rcx+1]
0x18000b4c8  lea     rdx, [r10+rax*8]; Src
0x18000b4cc  mov     rcx, r9; void *
0x18000b4cf  call    memcpy_0
0x18000b4d4  mov     edx, [rdi+34h]
0x18000b4d7  lea     eax, [rdx-1]
0x18000b4da  mov     [rdi+34h], eax
0x18000b4dd  test    r14d, r14d
0x18000b4e0  jz      short loc_18000B521
0x18000b4e2  test    byte ptr [rdi+60h], 1
0x18000b4e6  jz      short loc_18000B521
0x18000b4e8  xor     edx, edx
0x18000b4ea  cmp     [rdi+34h], edx
0x18000b4ed  jle     short loc_18000B513
0x18000b4ef  mov     r8, [rdi+28h]
0x18000b4f3  mov     rcx, [r8+rdx*8]
0x18000b4f7  mov     rax, [rcx+10h]
0x18000b4fb  jmp     short loc_18000B507
0x18000b4fd  cmp     dword ptr [rax+8], 0
0x18000b501  jnz     short loc_18000B521
0x18000b503  mov     rax, [rax+48h]
0x18000b507  test    rax, rax
0x18000b50a  jnz     short loc_18000B4FD
0x18000b50c  inc     edx
0x18000b50e  cmp     edx, [rdi+34h]
0x18000b511  jl      short loc_18000B4F3
0x18000b513  mov     rcx, [rdi+58h]; hTimer
0x18000b517  call    cs:__imp_CancelWaitableTimer
0x18000b51d  and     dword ptr [rdi+60h], 0FFFFFFFEh
0x18000b521  add     dword ptr [rdi+10h], 0FFFFFFFFh
0x18000b525  jnz     short loc_18000B56E
0x18000b527  mov     rdx, [rdi+68h]
0x18000b52b  mov     rcx, [rdi+70h]
0x18000b52f  test    rdx, rdx
0x18000b532  jz      short loc_18000B538
0x18000b534  mov     [rdx+70h], rcx
0x18000b538  test    rcx, rcx
0x18000b53b  jz      short loc_18000B541
0x18000b53d  mov     [rcx+68h], rdx
0x18000b541  mov     rax, cs:?g_HookThreadMap@@3V?$CPbList@UCHookThreadItem@@@@A; CPbList<CHookThreadItem> g_HookThreadMap
0x18000b548  cmp     rax, rdi
0x18000b54b  cmovz   rax, rcx
0x18000b54f  mov     cs:?g_HookThreadMap@@3V?$CPbList@UCHookThreadItem@@@@A, rax; CPbList<CHookThreadItem> g_HookThreadMap
0x18000b556  mov     rax, cs:qword_180018A50
0x18000b55d  cmp     rax, rdi
0x18000b560  cmovz   rax, rdx
0x18000b564  mov     cs:qword_180018A50, rax
0x18000b56b  mov     r15b, 1
0x18000b56e  test    ebx, ebx
0x18000b570  jnz     short loc_18000B57F
0x18000b572  mov     rcx, cs:?g_hMutexHook@@3PEAXEA; hMutex
0x18000b579  call    cs:__imp_ReleaseMutex
0x18000b57f  test    r15b, r15b
0x18000b582  jz      short loc_18000B5BA
0x18000b584  mov     rcx, rdi; struct CHookThreadItem *
0x18000b587  call    ?TerminateHookThread@CPimcManager@@SAXPEAUCHookThreadItem@@@Z; CPimcManager::TerminateHookThread(CHookThreadItem *)
0x18000b58c  mov     [rsp+48h+arg_8], rdi
0x18000b591  lea     rax, [rdi+18h]
0x18000b595  mov     rcx, [rax+10h]; Block
0x18000b599  test    rcx, rcx
0x18000b59c  jz      short loc_18000B5AD
0x18000b59e  cmp     rcx, rax
0x18000b5a1  jz      short loc_18000B5AD
0x18000b5a3  mov     edx, 8
0x18000b5a8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000b5ad  mov     edx, 68h ; 'h'
0x18000b5b2  mov     rcx, rdi; Block
0x18000b5b5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000b5ba  xor     eax, eax
0x18000b5bc  mov     rbx, [rsp+48h+arg_0]
0x18000b5c1  add     rsp, 20h
0x18000b5c5  pop     r15
0x18000b5c7  pop     r14
0x18000b5c9  pop     rdi
0x18000b5ca  pop     rsi
0x18000b5cb  pop     rbp
0x18000b5cc  retn
```
