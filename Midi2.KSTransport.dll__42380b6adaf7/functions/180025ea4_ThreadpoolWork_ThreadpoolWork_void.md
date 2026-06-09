# ThreadpoolWork::~ThreadpoolWork(void)

- ea: `0x180025ea4`
- end: `0x180025f72`
- name: `??1ThreadpoolWork@@QEAA@XZ`
- size: `206`
- prototype: `void __fastcall(ThreadpoolWork *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180025c10`
- `0x180025cfc`
- `0x180026b64`
- `0x180026e84`

## callees

- `0x180025c40`
- `0x180025ea4`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025ecf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025ecf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025f6b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025eb7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025eb7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180025ee8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180025ee8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180025edf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180025edf`

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
0x180025ea4  push    rbx
0x180025ea6  push    rbp
0x180025ea7  push    rsi
0x180025ea8  push    rdi
0x180025ea9  sub     rsp, 28h
0x180025ead  mov     rbx, rcx
0x180025eb0  lea     rsi, [rcx+8]
0x180025eb4  mov     rcx, rsi; lpCriticalSection
0x180025eb7  call    cs:__imp_EnterCriticalSection
0x180025ebd  mov     rdi, [rbx]
0x180025ec0  mov     qword ptr [rbx], 0
0x180025ec7  test    rsi, rsi
0x180025eca  jz      short loc_180025ED5
0x180025ecc  mov     rcx, rsi; lpCriticalSection
0x180025ecf  call    cs:__imp_LeaveCriticalSection
0x180025ed5  test    rdi, rdi
0x180025ed8  jz      short loc_180025EEE
0x180025eda  xor     edx, edx; fCancelPendingCallbacks
0x180025edc  mov     rcx, rdi; pwk
0x180025edf  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180025ee5  mov     rcx, rdi; pwk
0x180025ee8  call    cs:__imp_CloseThreadpoolWork
0x180025eee  mov     rdi, [rbx+30h]
0x180025ef2  mov     rbp, [rbx+38h]
0x180025ef6  jmp     short loc_180025F11
0x180025ef8  mov     rcx, [rdi+38h]
0x180025efc  test    rcx, rcx
0x180025eff  jz      short loc_180025F0D
0x180025f01  mov     rax, [rcx]
0x180025f04  mov     rax, [rax+10h]
0x180025f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f0d  add     rdi, 40h ; '@'
0x180025f11  cmp     rdi, rbp
0x180025f14  jnz     short loc_180025EF8
0x180025f16  mov     rbp, [rbx+38h]
0x180025f1a  mov     rdi, [rbx+30h]
0x180025f1e  cmp     rdi, rbp
0x180025f21  jz      short loc_180025F57
0x180025f23  mov     rcx, [rdi+38h]
0x180025f27  test    rcx, rcx
0x180025f2a  jz      short loc_180025F46
0x180025f2c  mov     rax, [rcx]
0x180025f2f  cmp     rcx, rdi
0x180025f32  setnz   dl
0x180025f35  mov     rax, [rax+20h]
0x180025f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f3e  mov     qword ptr [rdi+38h], 0
0x180025f46  add     rdi, 40h ; '@'
0x180025f4a  cmp     rdi, rbp
0x180025f4d  jnz     short loc_180025F23
0x180025f4f  mov     rax, [rbx+30h]
0x180025f53  mov     [rbx+38h], rax
0x180025f57  lea     rcx, [rbx+30h]
0x180025f5b  call    ??1?$vector@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAA@XZ; std::vector<std::function<void (void)>>::~vector<std::function<void (void)>>(void)
0x180025f60  mov     rcx, rsi
0x180025f63  add     rsp, 28h
0x180025f67  pop     rdi
0x180025f68  pop     rsi
0x180025f69  pop     rbp
0x180025f6a  pop     rbx
0x180025f6b  jmp     cs:__imp_DeleteCriticalSection
```
