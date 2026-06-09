# ThreadPool::ThreadPool(void)

- ea: `0x18004f794`
- end: `0x18004f9a4`
- name: `??0ThreadPool@@QEAA@XZ`
- size: `528`
- prototype: `ThreadPool *__fastcall(ThreadPool *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18002818c`

## callees

- `0x1800044b8`
- `0x180011318`
- `0x18004f794`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f863`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f8ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f8de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f863`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f8ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f8de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f86b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f8c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f901`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f86b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f8c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f901`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18004f818`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18004f818`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18004f839`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18004f839`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18004f8b8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18004f956`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18004f8b8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18004f956`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18004f8f9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18004f947`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18004f8f9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18004f947`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18004f8f0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18004f93e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18004f8f0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18004f93e`

## string_xrefs

- `0x18004f980`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\threadpool.cpp`
- `0x18004f992`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\threadpool.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
ThreadPool *__fastcall ThreadPool::ThreadPool(ThreadPool *this)
{
  ThreadPool *v1; // r13
  char *v2; // rsi
  struct _TP_CLEANUP_GROUP **v3; // r15
  struct _TP_POOL **v4; // r12
  const char *v5; // r9
  struct _TP_POOL *Threadpool; // r14
  struct _TP_CLEANUP_GROUP *ThreadpoolCleanupGroup; // rdi
  const char *v8; // r9
  DWORD LastError; // eax
  DWORD v10; // ebx
  struct _TP_CLEANUP_GROUP *v11; // r13
  DWORD v12; // ebx
  struct _TP_CLEANUP_GROUP *v14; // [rsp+28h] [rbp-49h] BYREF
  struct _TP_POOL *v15; // [rsp+30h] [rbp-41h] BYREF
  __int128 v16; // [rsp+38h] [rbp-39h] BYREF
  __int128 v17; // [rsp+48h] [rbp-29h]
  __int128 v18; // [rsp+68h] [rbp-9h]
  __int64 v19; // [rsp+78h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]
  struct _TP_POOL *ptpp; // [rsp+E0h] [rbp+6Fh]

  v1 = this;
  *(_QWORD *)this = &ThreadPool::`vftable';
  v2 = (char *)this + 8;
  memset_0((char *)this + 8, 0, 0x48u);
  v3 = (struct _TP_CLEANUP_GROUP **)((char *)v1 + 80);
  *((_QWORD *)v1 + 10) = 0;
  v4 = (struct _TP_POOL **)((char *)v1 + 88);
  *((_QWORD *)v1 + 11) = 0;
  v16 = 3u;
  v19 = 72;
  v17 = 0u;
  *(_QWORD *)&v18 = 0;
  *((_QWORD *)&v18 + 1) = 0x100000000LL;
  Threadpool = CreateThreadpool(0);
  v15 = Threadpool;
  if ( !Threadpool )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x38,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\threadpool.cpp",
      v5);
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  v14 = ThreadpoolCleanupGroup;
  if ( !ThreadpoolCleanupGroup )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\threadpool.cpp",
      v8);
  if ( v2 != (char *)&v16 )
  {
    LastError = GetLastError();
    SetLastError(LastError);
    *(_OWORD *)v2 = v16;
    *((_OWORD *)v2 + 1) = v17;
    *((_OWORD *)v2 + 2) = 0;
    *((_OWORD *)v2 + 3) = v18;
    *((_QWORD *)v2 + 8) = v19;
  }
  if ( v4 != &v15 )
  {
    ptpp = *v4;
    if ( *v4 )
    {
      v10 = GetLastError();
      CloseThreadpool(ptpp);
      SetLastError(v10);
    }
    *v4 = Threadpool;
    Threadpool = 0;
  }
  if ( v3 != &v14 )
  {
    v11 = *v3;
    if ( *v3 )
    {
      v12 = GetLastError();
      CloseThreadpoolCleanupGroupMembers(v11, 1, 0);
      CloseThreadpoolCleanupGroup(v11);
      SetLastError(v12);
    }
    *v3 = ThreadpoolCleanupGroup;
    v14 = 0;
    ThreadpoolCleanupGroup = 0;
    v1 = this;
  }
  *((_QWORD *)v1 + 2) = *v4;
  *((_QWORD *)v2 + 2) = *v3;
  *((_QWORD *)v2 + 3) = 0;
  if ( ThreadpoolCleanupGroup )
  {
    CloseThreadpoolCleanupGroupMembers(ThreadpoolCleanupGroup, 1, 0);
    CloseThreadpoolCleanupGroup(ThreadpoolCleanupGroup);
  }
  if ( Threadpool )
    CloseThreadpool(Threadpool);
  return v1;
}

```

## disassembly

```asm
0x18004f794  mov     rax, rsp
0x18004f797  mov     [rax+18h], rbx
0x18004f79b  mov     [rax+8], rcx
0x18004f79f  push    rbp
0x18004f7a0  push    rsi
0x18004f7a1  push    rdi
0x18004f7a2  push    r12
0x18004f7a4  push    r13
0x18004f7a6  push    r14
0x18004f7a8  push    r15
0x18004f7aa  lea     rbp, [rax-5Fh]
0x18004f7ae  sub     rsp, 90h
0x18004f7b5  movaps  xmmword ptr [rax-48h], xmm6
0x18004f7b9  mov     r13, rcx
0x18004f7bc  lea     rax, ??_7ThreadPool@@6B@; const ThreadPool::`vftable'
0x18004f7c3  mov     [rcx], rax
0x18004f7c6  lea     rsi, [rcx+8]
0x18004f7ca  xor     edx, edx; Val
0x18004f7cc  lea     r8d, [rdx+48h]; Size
0x18004f7d0  mov     rcx, rsi; void *
0x18004f7d3  call    memset_0
0x18004f7d8  lea     r15, [r13+50h]
0x18004f7dc  xor     edi, edi
0x18004f7de  mov     [r15], rdi
0x18004f7e1  lea     r12, [r13+58h]
0x18004f7e5  mov     [r12], rdi
0x18004f7e9  mov     qword ptr [rbp+57h+var_90], 3
0x18004f7f1  mov     [rbp+57h+var_50], 48h ; 'H'
0x18004f7f9  mov     qword ptr [rbp+57h+var_90+8], rdi
0x18004f7fd  mov     qword ptr [rbp+57h+var_80], rdi
0x18004f801  mov     qword ptr [rbp+57h+var_80+8], rdi
0x18004f805  xorps   xmm6, xmm6
0x18004f808  mov     qword ptr [rbp+57h+var_60], rdi
0x18004f80c  mov     dword ptr [rbp+57h+var_60+8], edi
0x18004f80f  mov     dword ptr [rbp+57h+var_60+0Ch], 1
0x18004f816  xor     ecx, ecx; reserved
0x18004f818  call    cs:__imp_CreateThreadpool
0x18004f81e  mov     r14, rax
0x18004f821  mov     [rbp+57h+var_98], rax
0x18004f825  mov     eax, edi
0x18004f827  test    r14, r14
0x18004f82a  setnz   al
0x18004f82d  mov     rcx, [rbp+5Fh]; this
0x18004f831  test    eax, eax
0x18004f833  jz      loc_18004F992
0x18004f839  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18004f83f  mov     rdi, rax
0x18004f842  mov     [rbp+57h+var_A0], rax
0x18004f846  xor     eax, eax
0x18004f848  test    rdi, rdi
0x18004f84b  setnz   al
0x18004f84e  mov     rcx, [rbp+5Fh]; this
0x18004f852  test    eax, eax
0x18004f854  jz      loc_18004F980
0x18004f85a  lea     rax, [rbp+57h+var_90]
0x18004f85e  cmp     rsi, rax
0x18004f861  jz      short loc_18004F896
0x18004f863  call    cs:__imp_GetLastError
0x18004f869  mov     ecx, eax; dwErrCode
0x18004f86b  call    cs:__imp_SetLastError
0x18004f871  movaps  xmm0, [rbp+57h+var_90]
0x18004f875  movups  xmmword ptr [rsi], xmm0
0x18004f878  movaps  xmm1, [rbp+57h+var_80]
0x18004f87c  movups  xmmword ptr [rsi+10h], xmm1
0x18004f880  movups  xmmword ptr [rsi+20h], xmm6
0x18004f884  movaps  xmm0, [rbp+57h+var_60]
0x18004f888  movups  xmmword ptr [rsi+30h], xmm0
0x18004f88c  movsd   xmm1, [rbp+57h+var_50]
0x18004f891  movsd   qword ptr [rsi+40h], xmm1
0x18004f896  lea     rax, [rbp+57h+var_98]
0x18004f89a  cmp     r12, rax
0x18004f89d  jz      short loc_18004F8CD
0x18004f89f  mov     rax, [r12]
0x18004f8a3  mov     [rbp+57h+ptpp], rax
0x18004f8a7  test    rax, rax
0x18004f8aa  jz      short loc_18004F8C6
0x18004f8ac  call    cs:__imp_GetLastError
0x18004f8b2  mov     ebx, eax
0x18004f8b4  mov     rcx, [rbp+57h+ptpp]; ptpp
0x18004f8b8  call    cs:__imp_CloseThreadpool
0x18004f8be  mov     ecx, ebx; dwErrCode
0x18004f8c0  call    cs:__imp_SetLastError
0x18004f8c6  mov     [r12], r14
0x18004f8ca  xor     r14d, r14d
0x18004f8cd  lea     rax, [rbp+57h+var_A0]
0x18004f8d1  cmp     r15, rax
0x18004f8d4  jz      short loc_18004F918
0x18004f8d6  mov     r13, [r15]
0x18004f8d9  test    r13, r13
0x18004f8dc  jz      short loc_18004F907
0x18004f8de  call    cs:__imp_GetLastError
0x18004f8e4  mov     ebx, eax
0x18004f8e6  xor     r8d, r8d; pvCleanupContext
0x18004f8e9  lea     edx, [r8+1]; fCancelPendingCallbacks
0x18004f8ed  mov     rcx, r13; ptpcg
0x18004f8f0  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18004f8f6  mov     rcx, r13; ptpcg
0x18004f8f9  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18004f8ff  mov     ecx, ebx; dwErrCode
0x18004f901  call    cs:__imp_SetLastError
0x18004f907  mov     [r15], rdi
0x18004f90a  mov     [rbp+57h+var_A0], 0
0x18004f912  xor     edi, edi
0x18004f914  mov     r13, [rbp+57h+arg_0]
0x18004f918  mov     rax, [r12]
0x18004f91c  mov     [r13+10h], rax
0x18004f920  mov     rax, [r15]
0x18004f923  mov     [rsi+10h], rax
0x18004f927  mov     qword ptr [rsi+18h], 0
0x18004f92f  test    rdi, rdi
0x18004f932  jz      short loc_18004F94E
0x18004f934  xor     r8d, r8d; pvCleanupContext
0x18004f937  lea     edx, [r8+1]; fCancelPendingCallbacks
0x18004f93b  mov     rcx, rdi; ptpcg
0x18004f93e  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18004f944  mov     rcx, rdi; ptpcg
0x18004f947  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18004f94d  nop
0x18004f94e  test    r14, r14
0x18004f951  jz      short loc_18004F95D
0x18004f953  mov     rcx, r14; ptpp
0x18004f956  call    cs:__imp_CloseThreadpool
0x18004f95c  nop
0x18004f95d  mov     rax, r13
0x18004f960  lea     r11, [rsp+0C0h+var_30]
0x18004f968  mov     rbx, [r11+50h]
0x18004f96c  movaps  xmm6, xmmword ptr [r11-10h]
0x18004f971  mov     rsp, r11
0x18004f974  pop     r15
0x18004f976  pop     r14
0x18004f978  pop     r13
0x18004f97a  pop     r12
0x18004f97c  pop     rdi
0x18004f97d  pop     rsi
0x18004f97e  pop     rbp
0x18004f97f  retn
0x18004f980  lea     r8, aOnecoreBaseLan_28; "onecore\\base\\languageoverlay\\service"...
0x18004f987  mov     edx, 3Bh ; ';'; void *
0x18004f98c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18004f992  lea     r8, aOnecoreBaseLan_28; "onecore\\base\\languageoverlay\\service"...
0x18004f999  mov     edx, 38h ; '8'; void *
0x18004f99e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
