# __security_init_cookie

- ea: `0x140001604`
- end: `0x1400016e1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001150`

## callees

- `0x140001604`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001657`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001657`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000164b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000164b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000168e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000168e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001663`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001673`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001663`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001673`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000163d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000163d`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (_FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    v1 = v0;
    if ( v0 == 0x2B992DDFA232LL )
    {
      v0 = 0x2B992DDFA233LL;
      v1 = 0x2B992DDFA233LL;
    }
    _security_cookie = v1;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x140001604  mov     [rsp-8+arg_18], rbx
0x140001609  push    rbp
0x14000160a  mov     rbp, rsp
0x14000160d  sub     rsp, 20h
0x140001611  xor     eax, eax
0x140001613  mov     rbx, 2B992DDFA232h
0x14000161d  mov     [rbp+arg_0], rax
0x140001621  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001625  mov     qword ptr [rbp+PerformanceCount], rax
0x140001629  mov     rax, cs:__security_cookie
0x140001630  cmp     rax, rbx
0x140001633  jnz     loc_1400016CC
0x140001639  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000163d  call    cs:__imp_GetSystemTimeAsFileTime
0x140001643  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140001647  mov     [rbp+arg_0], rax
0x14000164b  call    cs:__imp_GetCurrentProcessId
0x140001651  mov     eax, eax
0x140001653  xor     [rbp+arg_0], rax
0x140001657  call    cs:__imp_GetCurrentThreadId
0x14000165d  mov     eax, eax
0x14000165f  xor     [rbp+arg_0], rax
0x140001663  call    cs:__imp_GetTickCount
0x140001669  mov     eax, eax
0x14000166b  shl     rax, 18h
0x14000166f  xor     [rbp+arg_0], rax
0x140001673  call    cs:__imp_GetTickCount
0x140001679  mov     eax, eax
0x14000167b  lea     rcx, [rbp+arg_0]
0x14000167f  xor     rax, [rbp+arg_0]
0x140001683  xor     rax, rcx
0x140001686  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000168a  mov     [rbp+arg_0], rax
0x14000168e  call    cs:__imp_QueryPerformanceCounter
0x140001694  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001697  mov     rcx, 0FFFFFFFFFFFFh
0x1400016a1  shl     rax, 20h
0x1400016a5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400016a9  xor     rax, [rbp+arg_0]
0x1400016ad  and     rax, rcx
0x1400016b0  mov     rcx, rax
0x1400016b3  cmp     rax, rbx
0x1400016b6  jnz     short loc_1400016C5
0x1400016b8  mov     rax, 2B992DDFA233h
0x1400016c2  mov     rcx, rax
0x1400016c5  mov     cs:__security_cookie, rcx
0x1400016cc  mov     rbx, [rsp+20h+arg_18]
0x1400016d1  not     rax
0x1400016d4  mov     cs:__security_cookie_complement, rax
0x1400016db  add     rsp, 20h
0x1400016df  pop     rbp
0x1400016e0  retn
```
