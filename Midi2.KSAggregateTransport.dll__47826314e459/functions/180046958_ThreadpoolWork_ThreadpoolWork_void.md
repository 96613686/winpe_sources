# ThreadpoolWork::~ThreadpoolWork(void)

- ea: `0x180046958`
- end: `0x180046a26`
- name: `??1ThreadpoolWork@@QEAA@XZ`
- size: `206`
- prototype: `void __fastcall(ThreadpoolWork *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800466c4`
- `0x1800467b0`
- `0x180047614`
- `0x180047934`

## callees

- `0x1800466f4`
- `0x180046958`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180046a1f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004696b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004696b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046983`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046983`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004699c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004699c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180046993`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180046993`

## pseudocode

```c
void __fastcall ThreadpoolWork::~ThreadpoolWork(struct _TP_WORK **this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  __int64 v3; // rdx
  struct _TP_WORK *v4; // rdi
  struct _TP_WORK *v5; // rdi
  struct _TP_WORK *v6; // rbp
  __int64 v7; // rcx
  struct _TP_WORK *v8; // rbp
  struct _TP_WORK *v9; // rdi
  struct _TP_WORK *v10; // rcx

  v2 = (struct _RTL_CRITICAL_SECTION *)(this + 1);
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 1));
  v4 = *this;
  *this = 0;
  if ( v2 )
    LeaveCriticalSection(v2);
  if ( v4 )
  {
    WaitForThreadpoolWorkCallbacks(v4, 0);
    CloseThreadpoolWork(v4);
  }
  v5 = this[6];
  v6 = this[7];
  while ( v5 != v6 )
  {
    v7 = *((_QWORD *)v5 + 7);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    v5 = (struct _TP_WORK *)((char *)v5 + 64);
  }
  v8 = this[7];
  v9 = this[6];
  if ( v9 != v8 )
  {
    do
    {
      v10 = (struct _TP_WORK *)*((_QWORD *)v9 + 7);
      if ( v10 )
      {
        LOBYTE(v3) = v10 != v9;
        (*(void (__fastcall **)(struct _TP_WORK *, __int64))(*(_QWORD *)v10 + 32LL))(v10, v3);
        *((_QWORD *)v9 + 7) = 0;
      }
      v9 = (struct _TP_WORK *)((char *)v9 + 64);
    }
    while ( v9 != v8 );
    this[7] = this[6];
  }
  std::vector<std::function<void (void)>>::~vector<std::function<void (void)>>(this + 6);
  DeleteCriticalSection(v2);
}

```

## disassembly

```asm
0x180046958  push    rbx
0x18004695a  push    rbp
0x18004695b  push    rsi
0x18004695c  push    rdi
0x18004695d  sub     rsp, 28h
0x180046961  mov     rbx, rcx
0x180046964  lea     rsi, [rcx+8]
0x180046968  mov     rcx, rsi; lpCriticalSection
0x18004696b  call    cs:__imp_EnterCriticalSection
0x180046971  mov     rdi, [rbx]
0x180046974  mov     qword ptr [rbx], 0
0x18004697b  test    rsi, rsi
0x18004697e  jz      short loc_180046989
0x180046980  mov     rcx, rsi; lpCriticalSection
0x180046983  call    cs:__imp_LeaveCriticalSection
0x180046989  test    rdi, rdi
0x18004698c  jz      short loc_1800469A2
0x18004698e  xor     edx, edx; fCancelPendingCallbacks
0x180046990  mov     rcx, rdi; pwk
0x180046993  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180046999  mov     rcx, rdi; pwk
0x18004699c  call    cs:__imp_CloseThreadpoolWork
0x1800469a2  mov     rdi, [rbx+30h]
0x1800469a6  mov     rbp, [rbx+38h]
0x1800469aa  jmp     short loc_1800469C5
0x1800469ac  mov     rcx, [rdi+38h]
0x1800469b0  test    rcx, rcx
0x1800469b3  jz      short loc_1800469C1
0x1800469b5  mov     rax, [rcx]
0x1800469b8  mov     rax, [rax+10h]
0x1800469bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800469c1  add     rdi, 40h ; '@'
0x1800469c5  cmp     rdi, rbp
0x1800469c8  jnz     short loc_1800469AC
0x1800469ca  mov     rbp, [rbx+38h]
0x1800469ce  mov     rdi, [rbx+30h]
0x1800469d2  cmp     rdi, rbp
0x1800469d5  jz      short loc_180046A0B
0x1800469d7  mov     rcx, [rdi+38h]
0x1800469db  test    rcx, rcx
0x1800469de  jz      short loc_1800469FA
0x1800469e0  mov     rax, [rcx]
0x1800469e3  cmp     rcx, rdi
0x1800469e6  setnz   dl
0x1800469e9  mov     rax, [rax+20h]
0x1800469ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800469f2  mov     qword ptr [rdi+38h], 0
0x1800469fa  add     rdi, 40h ; '@'
0x1800469fe  cmp     rdi, rbp
0x180046a01  jnz     short loc_1800469D7
0x180046a03  mov     rax, [rbx+30h]
0x180046a07  mov     [rbx+38h], rax
0x180046a0b  lea     rcx, [rbx+30h]
0x180046a0f  call    ??1?$vector@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAA@XZ; std::vector<std::function<void (void)>>::~vector<std::function<void (void)>>(void)
0x180046a14  mov     rcx, rsi
0x180046a17  add     rsp, 28h
0x180046a1b  pop     rdi
0x180046a1c  pop     rsi
0x180046a1d  pop     rbp
0x180046a1e  pop     rbx
0x180046a1f  jmp     cs:__imp_DeleteCriticalSection
```
