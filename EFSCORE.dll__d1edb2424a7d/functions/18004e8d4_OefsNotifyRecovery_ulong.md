# OefsNotifyRecovery(ulong)

- ea: `0x18004e8d4`
- end: `0x18004e9df`
- name: `?OefsNotifyRecovery@@YAJK@Z`
- size: `267`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004d6a0`

## callees

- `0x18000b10c`
- `0x18000b12c`
- `0x18000dc68`
- `0x18004e8d4`
- `0x180050898`
- `0x180051820`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004e90c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004e90c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e8fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e9af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e8fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e9af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e9bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e9bd`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18004e972`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18004e972`

## string_xrefs

- `0x18004e91f`: `onecoreuap\ds\security\efs\dll\efsonline.cxx`
- `0x18004e992`: `onecoreuap\ds\security\efs\dll\efsonline.cxx`

## pseudocode

```c
__int64 __fastcall OefsNotifyRecovery(int a1)
{
  HANDLE ProcessHeap; // rax
  _DWORD *v3; // rax
  void *v4; // rdi
  unsigned int LastError; // ebx
  HANDLE v7; // rax
  const char *v8; // r9
  HANDLE v9; // rax
  DWORD dwCreationFlags; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD ThreadId; // [rsp+48h] [rbp+10h] BYREF
  __int64 v13; // [rsp+50h] [rbp+18h] BYREF

  if ( dword_18011739C != 1 && (unsigned __int8)OefspShouldAttemptRecovery() )
  {
    ProcessHeap = GetProcessHeap();
    v3 = HeapAlloc(ProcessHeap, 8u, 4u);
    v4 = v3;
    if ( !v3 )
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5CD,
        (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
        (const char *)0x8007000ELL,
        dwCreationFlags);
      return LastError;
    }
    *v3 = a1;
    v13 = 0;
    ThreadId = 0;
    v7 = CreateThread(0, 0, OefsRecoveryThread, v3, 0, &ThreadId);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v13,
      v7);
    if ( !v13 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x5DA,
                    (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
                    v8);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v13);
      v9 = GetProcessHeap();
      HeapFree(v9, 0, v4);
      return LastError;
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v13);
  }
  return 0;
}

```

## disassembly

```asm
0x18004e8d4  mov     [rsp+arg_0], rbx
0x18004e8d9  push    rdi
0x18004e8da  sub     rsp, 30h
0x18004e8de  cmp     cs:dword_18011739C, 1
0x18004e8e5  mov     ebx, ecx
0x18004e8e7  jz      loc_18004E9D2
0x18004e8ed  call    OefspShouldAttemptRecovery
0x18004e8f2  test    al, al
0x18004e8f4  jz      loc_18004E9D2
0x18004e8fa  call    cs:__imp_GetProcessHeap
0x18004e900  mov     edx, 8; dwFlags
0x18004e905  mov     rcx, rax; hHeap
0x18004e908  lea     r8d, [rdx-4]; dwBytes
0x18004e90c  call    cs:__imp_HeapAlloc
0x18004e912  mov     rdi, rax
0x18004e915  test    rax, rax
0x18004e918  jnz     short loc_18004E93F
0x18004e91a  mov     rcx, [rsp+38h]; this
0x18004e91f  lea     r8, aOnecoreuapDsSe_10; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x18004e926  mov     ebx, 8007000Eh
0x18004e92b  mov     edx, 5CDh; void *
0x18004e930  mov     r9d, ebx; char *
0x18004e933  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e938  mov     eax, ebx
0x18004e93a  jmp     loc_18004E9D4
0x18004e93f  mov     [rax], ebx
0x18004e941  lea     r8, ?OefsRecoveryThread@@YAKPEAX@Z; lpStartAddress
0x18004e948  lea     rax, [rsp+38h+ThreadId]
0x18004e94d  mov     [rsp+38h+arg_10], 0
0x18004e956  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18004e95b  mov     r9, rdi; lpParameter
0x18004e95e  xor     edx, edx; dwStackSize
0x18004e960  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18004e968  xor     ecx, ecx; lpThreadAttributes
0x18004e96a  mov     [rsp+38h+ThreadId], 0
0x18004e972  call    cs:__imp_CreateThread
0x18004e978  mov     rdx, rax
0x18004e97b  lea     rcx, [rsp+38h+arg_10]
0x18004e980  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18004e985  cmp     [rsp+38h+arg_10], 0
0x18004e98b  jnz     short loc_18004E9C8
0x18004e98d  mov     rcx, [rsp+38h]; this
0x18004e992  lea     r8, aOnecoreuapDsSe_10; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x18004e999  mov     edx, 5DAh; void *
0x18004e99e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004e9a3  lea     rcx, [rsp+38h+arg_10]
0x18004e9a8  mov     ebx, eax
0x18004e9aa  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004e9af  call    cs:__imp_GetProcessHeap
0x18004e9b5  mov     r8, rdi; lpMem
0x18004e9b8  xor     edx, edx; dwFlags
0x18004e9ba  mov     rcx, rax; hHeap
0x18004e9bd  call    cs:__imp_HeapFree
0x18004e9c3  jmp     loc_18004E938
0x18004e9c8  lea     rcx, [rsp+38h+arg_10]
0x18004e9cd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004e9d2  xor     eax, eax
0x18004e9d4  mov     rbx, [rsp+38h+arg_0]
0x18004e9d9  add     rsp, 30h
0x18004e9dd  pop     rdi
0x18004e9de  retn
```
