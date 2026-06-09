# StateRepository::ResourcePriority::AutoPriority::~AutoPriority(void)

- ea: `0x1800f85a8`
- end: `0x1800f8754`
- name: `??1AutoPriority@ResourcePriority@StateRepository@@QEAA@XZ`
- size: `428`
- prototype: `void __fastcall(StateRepository::ResourcePriority::AutoPriority *this)`
- caller_count: `6`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800f8b68`
- `0x1800fc9e8`
- `0x1800fce08`
- `0x1800ff438`
- `0x180100268`
- `0x180103210`

## callees

- `0x1800f7630`
- `0x1800f853c`
- `0x1800f85a8`
- `0x1800fb814`
- `0x1800fb8a8`
- `0x1800fb93c`
- `0x1800fcde4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f864f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f864f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f86e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f8711`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f8742`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f86e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f8711`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f8742`
- `ntdll!NtSetInformationThread` at `0x1800f8665`
- `ntdll!NtSetInformationThread` at `0x1800f8665`

## string_xrefs

- `0x1800f8689`: `onecore\base\appmodel\StateRepository\DataAccessLayer\ResourcePriority.hpp`
- `0x1800f85c7`: `onecore\base\appmodel\staterepository\dataaccesslayer\resourcepriority.cpp`
- `0x1800f85f2`: `onecore\base\appmodel\staterepository\dataaccesslayer\resourcepriority.cpp`
- `0x1800f8622`: `onecore\base\appmodel\staterepository\dataaccesslayer\resourcepriority.cpp`

## pseudocode

```c
void __fastcall StateRepository::ResourcePriority::AutoPriority::~AutoPriority(
        StateRepository::ResourcePriority::AutoPriority *this)
{
  int v2; // eax
  int v3; // ebx
  HANDLE *v4; // r14
  int v5; // eax
  int v6; // esi
  HANDLE *v7; // r15
  int v8; // eax
  int v9; // esi
  char *CurrentThread; // rcx
  NTSTATUS v11; // eax
  void *v12; // rdx
  unsigned int v13; // r8d
  const char *v14; // r9
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = ((__int64 (*)(void))StateRepository::ResourcePriority::AutoThreadPriority<25,long,long>::Revert)();
  v3 = v2;
  if ( v2 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x78,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\resourcepriority.cpp",
      (const char *)(unsigned int)v2,
      v18);
  v4 = (HANDLE *)((char *)this + 16);
  v5 = StateRepository::ResourcePriority::AutoThreadPriority<24,unsigned long,_MEMORY_PRIORITY_INFORMATION>::Revert((char *)this + 16);
  v6 = v5;
  if ( v5 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\resourcepriority.cpp",
      (const char *)(unsigned int)v5,
      v18);
  v7 = (HANDLE *)((char *)this + 32);
  if ( v3 >= 0 )
    v3 = v6;
  v8 = StateRepository::ResourcePriority::AutoThreadPriority<22,enum _IO_PRIORITY_HINT,_FILE_IO_PRIORITY_HINT_INFORMATION>::Revert((char *)this + 32);
  v9 = v8;
  if ( v8 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x7A,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\resourcepriority.cpp",
      (const char *)(unsigned int)v8,
      v18);
  if ( v3 >= 0 )
    v3 = v9;
  if ( *((_BYTE *)this + 56) )
  {
    CurrentThread = (char *)*((_QWORD *)this + 6);
    if ( (unsigned __int64)(CurrentThread - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      CurrentThread = (char *)GetCurrentThread();
    v11 = NtSetInformationThread(CurrentThread, ThreadHideFromDebugger|0x20, (char *)this + 60, 0xCu);
    if ( v11 < 0 )
      wil::details::in1diag3::_Log_NtStatus(retaddr, v12, v13, (const char *)(unsigned int)v11, v18);
    *((_BYTE *)this + 56) = 0;
  }
  v14 = 0;
  if ( v3 < 0 )
    v14 = (const char *)(unsigned int)v3;
  if ( (int)v14 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xB9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\ResourcePriority.hpp",
      v14,
      v18);
  StateRepository::ResourcePriority::AutoThreadPriority<49,bool,_THREAD_POWER_THROTTLING_STATE>::~AutoThreadPriority<49,bool,_THREAD_POWER_THROTTLING_STATE>((char **)this + 6);
  v15 = StateRepository::ResourcePriority::AutoThreadPriority<22,enum _IO_PRIORITY_HINT,_FILE_IO_PRIORITY_HINT_INFORMATION>::Revert((char *)this + 32);
  if ( v15 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1A,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\ResourcePriority.hpp",
      (const char *)(unsigned int)v15,
      v18);
  if ( (char *)*v7 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(*v7);
  v16 = StateRepository::ResourcePriority::AutoThreadPriority<24,unsigned long,_MEMORY_PRIORITY_INFORMATION>::Revert((char *)this + 16);
  if ( v16 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1A,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\ResourcePriority.hpp",
      (const char *)(unsigned int)v16,
      v18);
  if ( (char *)*v4 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(*v4);
  v17 = StateRepository::ResourcePriority::AutoThreadPriority<25,long,long>::Revert(this);
  if ( v17 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1A,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\ResourcePriority.hpp",
      (const char *)(unsigned int)v17,
      v18);
  if ( (unsigned __int64)(*(_QWORD *)this - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(*(HANDLE *)this);
}

```

## disassembly

```asm
0x1800f85a8  push    rbx
0x1800f85aa  push    rsi
0x1800f85ab  push    rdi
0x1800f85ac  push    r14
0x1800f85ae  push    r15; int
0x1800f85b0  sub     rsp, 20h
0x1800f85b4  mov     rdi, rcx
0x1800f85b7  call    ?Revert@?$AutoThreadPriority@$0BJ@JJ@ResourcePriority@StateRepository@@QEAAJXZ; StateRepository::ResourcePriority::AutoThreadPriority<25,long,long>::Revert(void)
0x1800f85bc  mov     ebx, eax
0x1800f85be  test    eax, eax
0x1800f85c0  jns     short loc_1800F85DB
0x1800f85c2  mov     rcx, [rsp+48h]; this
0x1800f85c7  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\staterepositor"...
0x1800f85ce  mov     r9d, eax; char *
0x1800f85d1  mov     edx, 78h ; 'x'; void *
0x1800f85d6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f85db  lea     r14, [rdi+10h]
0x1800f85df  mov     rcx, r14
0x1800f85e2  call    ?Revert@?$AutoThreadPriority@$0BI@KU_MEMORY_PRIORITY_INFORMATION@@@ResourcePriority@StateRepository@@QEAAJXZ; StateRepository::ResourcePriority::AutoThreadPriority<24,ulong,_MEMORY_PRIORITY_INFORMATION>::Revert(void)
0x1800f85e7  mov     esi, eax
0x1800f85e9  test    eax, eax
0x1800f85eb  jns     short loc_1800F8606
0x1800f85ed  mov     rcx, [rsp+48h]; this
0x1800f85f2  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\staterepositor"...
0x1800f85f9  mov     r9d, eax; char *
0x1800f85fc  mov     edx, 79h ; 'y'; void *
0x1800f8601  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f8606  test    ebx, ebx
0x1800f8608  lea     r15, [rdi+20h]
0x1800f860c  mov     rcx, r15
0x1800f860f  cmovns  ebx, esi
0x1800f8612  call    ?Revert@?$AutoThreadPriority@$0BG@W4_IO_PRIORITY_HINT@@U_FILE_IO_PRIORITY_HINT_INFORMATION@@@ResourcePriority@StateRepository@@QEAAJXZ; StateRepository::ResourcePriority::AutoThreadPriority<22,_IO_PRIORITY_HINT,_FILE_IO_PRIORITY_HINT_INFORMATION>::Revert(void)
0x1800f8617  mov     esi, eax
0x1800f8619  test    eax, eax
0x1800f861b  jns     short loc_1800F8636
0x1800f861d  mov     rcx, [rsp+48h]; this
0x1800f8622  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\staterepositor"...
0x1800f8629  mov     r9d, eax; char *
0x1800f862c  mov     edx, 7Ah ; 'z'; void *
0x1800f8631  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f8636  test    ebx, ebx
0x1800f8638  cmovns  ebx, esi
0x1800f863b  cmp     byte ptr [rdi+38h], 0
0x1800f863f  jz      short loc_1800F8680
0x1800f8641  mov     rcx, [rdi+30h]
0x1800f8645  lea     rax, [rcx-1]
0x1800f8649  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800f864d  jbe     short loc_1800F8658
0x1800f864f  call    cs:__imp_GetCurrentThread
0x1800f8655  mov     rcx, rax; ThreadHandle
0x1800f8658  mov     edx, 31h ; '1'; ThreadInformationClass
0x1800f865d  lea     r8, [rdi+3Ch]; ThreadInformation
0x1800f8661  lea     r9d, [rdx-25h]; ThreadInformationLength
0x1800f8665  call    cs:__imp_NtSetInformationThread
0x1800f866b  test    eax, eax
0x1800f866d  jns     short loc_1800F867C
0x1800f866f  mov     rcx, [rsp+48h]; this
0x1800f8674  mov     r9d, eax; char *
0x1800f8677  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x1800f867c  mov     byte ptr [rdi+38h], 0
0x1800f8680  xor     r9d, r9d
0x1800f8683  test    ebx, ebx
0x1800f8685  cmovs   r9d, ebx; char *
0x1800f8689  lea     rbx, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\StateRepositor"...
0x1800f8690  test    r9d, r9d
0x1800f8693  jns     short loc_1800F86A7
0x1800f8695  mov     rcx, [rsp+48h]; this
0x1800f869a  mov     r8, rbx; unsigned int
0x1800f869d  mov     edx, 0B9h; void *
0x1800f86a2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f86a7  lea     rcx, [rdi+30h]
0x1800f86ab  call    ??1?$AutoThreadPriority@$0DB@_NU_THREAD_POWER_THROTTLING_STATE@@@ResourcePriority@StateRepository@@QEAA@XZ; StateRepository::ResourcePriority::AutoThreadPriority<49,bool,_THREAD_POWER_THROTTLING_STATE>::~AutoThreadPriority<49,bool,_THREAD_POWER_THROTTLING_STATE>(void)
0x1800f86b0  mov     rcx, r15
0x1800f86b3  call    ?Revert@?$AutoThreadPriority@$0BG@W4_IO_PRIORITY_HINT@@U_FILE_IO_PRIORITY_HINT_INFORMATION@@@ResourcePriority@StateRepository@@QEAAJXZ; StateRepository::ResourcePriority::AutoThreadPriority<22,_IO_PRIORITY_HINT,_FILE_IO_PRIORITY_HINT_INFORMATION>::Revert(void)
0x1800f86b8  mov     esi, 1Ah
0x1800f86bd  test    eax, eax
0x1800f86bf  jns     short loc_1800F86D3
0x1800f86c1  mov     rcx, [rsp+48h]; this
0x1800f86c6  mov     r9d, eax; char *
0x1800f86c9  mov     r8, rbx; unsigned int
0x1800f86cc  mov     edx, esi; void *
0x1800f86ce  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f86d3  mov     rcx, [r15]; hObject
0x1800f86d6  lea     rax, [rcx-1]
0x1800f86da  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800f86de  ja      short loc_1800F86E6
0x1800f86e0  call    cs:__imp_CloseHandle
0x1800f86e6  mov     rcx, r14
0x1800f86e9  call    ?Revert@?$AutoThreadPriority@$0BI@KU_MEMORY_PRIORITY_INFORMATION@@@ResourcePriority@StateRepository@@QEAAJXZ; StateRepository::ResourcePriority::AutoThreadPriority<24,ulong,_MEMORY_PRIORITY_INFORMATION>::Revert(void)
0x1800f86ee  test    eax, eax
0x1800f86f0  jns     short loc_1800F8704
0x1800f86f2  mov     rcx, [rsp+48h]; this
0x1800f86f7  mov     r9d, eax; char *
0x1800f86fa  mov     r8, rbx; unsigned int
0x1800f86fd  mov     edx, esi; void *
0x1800f86ff  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f8704  mov     rcx, [r14]; hObject
0x1800f8707  lea     rax, [rcx-1]
0x1800f870b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800f870f  ja      short loc_1800F8717
0x1800f8711  call    cs:__imp_CloseHandle
0x1800f8717  mov     rcx, rdi
0x1800f871a  call    ?Revert@?$AutoThreadPriority@$0BJ@JJ@ResourcePriority@StateRepository@@QEAAJXZ; StateRepository::ResourcePriority::AutoThreadPriority<25,long,long>::Revert(void)
0x1800f871f  test    eax, eax
0x1800f8721  jns     short loc_1800F8735
0x1800f8723  mov     rcx, [rsp+48h]; this
0x1800f8728  mov     r9d, eax; char *
0x1800f872b  mov     r8, rbx; unsigned int
0x1800f872e  mov     edx, esi; void *
0x1800f8730  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f8735  mov     rcx, [rdi]; hObject
0x1800f8738  lea     rax, [rcx-1]
0x1800f873c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800f8740  ja      short loc_1800F8748
0x1800f8742  call    cs:__imp_CloseHandle
0x1800f8748  add     rsp, 20h
0x1800f874c  pop     r15
0x1800f874e  pop     r14
0x1800f8750  pop     rdi
0x1800f8751  pop     rsi
0x1800f8752  pop     rbx
0x1800f8753  retn
```
