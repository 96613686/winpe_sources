# ThreadPool::RuntimeClassInitialize(ulong,ulong)

- ea: `0x18004c7a8`
- end: `0x18004c886`
- name: `?RuntimeClassInitialize@ThreadPool@@QEAAJKK@Z`
- size: `222`
- prototype: `int(ThreadPool *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180034538`

## callees

- `0x18004c7a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c81c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c81c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18004c80d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18004c80d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18004c835`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18004c835`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18004c84b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18004c84b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18004c841`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18004c841`

## pseudocode

```c
int __fastcall ThreadPool::RuntimeClassInitialize(ThreadPool *this, DWORD a2, DWORD a3)
{
  struct _TP_POOL *Threadpool; // rax
  int result; // eax
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  PTP_CLEANUP_GROUP v9; // rdx

  *((_DWORD *)this + 4) = 3;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 18) = 0;
  *((_DWORD *)this + 19) = 1;
  *((_DWORD *)this + 20) = 72;
  Threadpool = CreateThreadpool(0);
  *((_QWORD *)this + 11) = Threadpool;
  if ( Threadpool
    && (SetThreadpoolThreadMaximum(Threadpool, a3), SetThreadpoolThreadMinimum(*((PTP_POOL *)this + 11), a2))
    && (ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup(),
        *((_QWORD *)this + 12) = ThreadpoolCleanupGroup,
        (v9 = ThreadpoolCleanupGroup) != 0) )
  {
    result = 0;
    *((_QWORD *)this + 3) = *((_QWORD *)this + 11);
    *((_QWORD *)this + 4) = v9;
    *((_QWORD *)this + 5) = 0;
    *((_DWORD *)this + 26) = 1;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18004c7a8  mov     [rsp+arg_0], rbx
0x18004c7ad  mov     [rsp+arg_8], rsi
0x18004c7b2  push    rdi
0x18004c7b3  sub     rsp, 20h
0x18004c7b7  mov     rbx, rcx
0x18004c7ba  mov     dword ptr [rcx+10h], 3
0x18004c7c1  mov     qword ptr [rcx+18h], 0
0x18004c7c9  mov     edi, r8d
0x18004c7cc  mov     qword ptr [rcx+20h], 0
0x18004c7d4  mov     esi, edx
0x18004c7d6  mov     qword ptr [rcx+28h], 0
0x18004c7de  mov     qword ptr [rcx+30h], 0
0x18004c7e6  mov     qword ptr [rcx+38h], 0
0x18004c7ee  mov     qword ptr [rcx+40h], 0
0x18004c7f6  mov     dword ptr [rcx+48h], 0
0x18004c7fd  mov     dword ptr [rcx+4Ch], 1
0x18004c804  mov     dword ptr [rcx+50h], 48h ; 'H'
0x18004c80b  xor     ecx, ecx; reserved
0x18004c80d  call    cs:__imp_CreateThreadpool
0x18004c813  mov     [rbx+58h], rax
0x18004c817  test    rax, rax
0x18004c81a  jnz     short loc_18004C830
0x18004c81c  call    cs:__imp_GetLastError
0x18004c822  test    eax, eax
0x18004c824  jle     short loc_18004C876
0x18004c826  movzx   eax, ax
0x18004c829  or      eax, 80070000h
0x18004c82e  jmp     short loc_18004C876
0x18004c830  mov     edx, edi; cthrdMost
0x18004c832  mov     rcx, rax; ptpp
0x18004c835  call    cs:__imp_SetThreadpoolThreadMaximum
0x18004c83b  mov     rcx, [rbx+58h]; ptpp
0x18004c83f  mov     edx, esi; cthrdMic
0x18004c841  call    cs:__imp_SetThreadpoolThreadMinimum
0x18004c847  test    eax, eax
0x18004c849  jz      short loc_18004C81C
0x18004c84b  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18004c851  mov     [rbx+60h], rax
0x18004c855  mov     rdx, rax
0x18004c858  test    rax, rax
0x18004c85b  jz      short loc_18004C81C
0x18004c85d  mov     rcx, [rbx+58h]
0x18004c861  xor     eax, eax
0x18004c863  mov     [rbx+18h], rcx
0x18004c867  mov     [rbx+20h], rdx
0x18004c86b  mov     [rbx+28h], rax
0x18004c86f  mov     dword ptr [rbx+68h], 1
0x18004c876  mov     rbx, [rsp+28h+arg_0]
0x18004c87b  mov     rsi, [rsp+28h+arg_8]
0x18004c880  add     rsp, 20h
0x18004c884  pop     rdi
0x18004c885  retn
```
