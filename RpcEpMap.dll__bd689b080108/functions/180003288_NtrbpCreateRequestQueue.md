# NtrbpCreateRequestQueue

- ea: `0x180003288`
- end: `0x18000332b`
- name: `NtrbpCreateRequestQueue`
- size: `163`
- prototype: `volatile __int64 *__fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800013f8`

## callees

- `0x180002a00`
- `0x180003288`
- `0x180003334`
- `0x1800033a4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800032b8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800032b8`

## pseudocode

```c
volatile __int64 *__fastcall NtrbpCreateRequestQueue(__int64 a1)
{
  volatile __int64 *v2; // rax
  volatile __int64 *v3; // rbx
  PTP_TIMER ThreadpoolTimer; // rax
  __int64 v5; // rax

  v2 = (volatile __int64 *)NtrbpAllocate(56);
  v3 = v2;
  if ( !v2 )
    return 0;
  ThreadpoolTimer = CreateThreadpoolTimer(NtrbpRequestQueueTimeoutCallback, (PVOID)v2, &NtrbTimeoutTimerTpEnvironment);
  *((_QWORD *)v3 + 3) = ThreadpoolTimer;
  if ( !ThreadpoolTimer )
  {
    operator delete((void *)v3);
    return 0;
  }
  *((_QWORD *)v3 + 5) = v3 + 4;
  *((_QWORD *)v3 + 4) = v3 + 4;
  v5 = NtrbRequestQueueListHead;
  if ( *(__int128 **)(NtrbRequestQueueListHead + 8) != &NtrbRequestQueueListHead )
    __fastfail(3u);
  *v3 = NtrbRequestQueueListHead;
  *((_QWORD *)v3 + 1) = &NtrbRequestQueueListHead;
  *(_QWORD *)(v5 + 8) = v3;
  *(_QWORD *)&NtrbRequestQueueListHead = v3;
  *((_QWORD *)v3 + 2) = a1;
  _InterlockedExchange64(v3 + 6, 0);
  NtrbStartRequestQueueTimer(v3);
  return v3;
}

```

## disassembly

```asm
0x180003288  mov     [rsp+arg_0], rbx
0x18000328d  push    rdi
0x18000328e  sub     rsp, 20h
0x180003292  mov     rdi, rcx
0x180003295  mov     ecx, 38h ; '8'
0x18000329a  call    NtrbpAllocate
0x18000329f  mov     rbx, rax
0x1800032a2  test    rax, rax
0x1800032a5  jz      short loc_180003320
0x1800032a7  lea     r8, NtrbTimeoutTimerTpEnvironment; pcbe
0x1800032ae  mov     rdx, rax; pv
0x1800032b1  lea     rcx, NtrbpRequestQueueTimeoutCallback; pfnti
0x1800032b8  call    cs:__imp_CreateThreadpoolTimer
0x1800032be  mov     [rbx+18h], rax
0x1800032c2  test    rax, rax
0x1800032c5  jz      short loc_180003318
0x1800032c7  lea     rax, [rbx+20h]
0x1800032cb  mov     [rax+8], rax
0x1800032cf  lea     rcx, NtrbRequestQueueListHead
0x1800032d6  mov     [rax], rax
0x1800032d9  mov     rax, qword ptr cs:NtrbRequestQueueListHead
0x1800032e0  cmp     [rax+8], rcx
0x1800032e4  jnz     short loc_180003324
0x1800032e6  mov     [rbx], rax
0x1800032e9  mov     [rbx+8], rcx
0x1800032ed  mov     rcx, rbx
0x1800032f0  mov     [rax+8], rbx
0x1800032f4  xor     eax, eax
0x1800032f6  mov     qword ptr cs:NtrbRequestQueueListHead, rbx
0x1800032fd  mov     [rbx+10h], rdi
0x180003301  xchg    rax, [rbx+30h]
0x180003305  call    NtrbStartRequestQueueTimer
0x18000330a  mov     rax, rbx
0x18000330d  mov     rbx, [rsp+28h+arg_0]
0x180003312  add     rsp, 20h
0x180003316  pop     rdi
0x180003317  retn
0x180003318  mov     rcx, rbx; void *
0x18000331b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003320  xor     ebx, ebx
0x180003322  jmp     short loc_18000330A
0x180003324  mov     ecx, 3
0x180003329  int     29h; Win8: RtlFailFast(ecx)
```
