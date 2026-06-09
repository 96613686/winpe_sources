# std::unique_ptr<wil::details::threadpool_timer_context,std::default_delete<wil::details::threadpool_timer_context>>::~unique_ptr<wil::details::threadpool_timer_context,std::default_delete<wil::details::threadpool_timer_context>>(void)

- ea: `0x18001e4bc`
- end: `0x18001e524`
- name: `??1?$unique_ptr@Uthreadpool_timer_context@details@wil@@U?$default_delete@Uthreadpool_timer_context@details@wil@@@std@@@std@@QEAA@XZ`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001f1c8`

## callees

- `0x180001b60`
- `0x18001e4bc`
- `0x18001e6c8`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001e4d7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001e4d7`

## pseudocode

```c
void __fastcall std::unique_ptr<wil::details::threadpool_timer_context>::~unique_ptr<wil::details::threadpool_timer_context>(
        wil::details::threadpool_object_context **a1,
        __int64 a2)
{
  wil::details::threadpool_object_context *v2; // rbx
  struct _TP_TIMER *v3; // rcx
  _QWORD *v4; // rcx

  v2 = *a1;
  if ( *a1 )
  {
    v3 = (struct _TP_TIMER *)*((_QWORD *)v2 + 10);
    if ( v3 )
      CloseThreadpoolTimer(v3);
    v4 = (_QWORD *)*((_QWORD *)v2 + 9);
    if ( v4 )
    {
      LOBYTE(a2) = v4 != (_QWORD *)((char *)v2 + 16);
      (*(void (__fastcall **)(_QWORD *, __int64))(*v4 + 32LL))(v4, a2);
      *((_QWORD *)v2 + 9) = 0;
    }
    wil::details::threadpool_object_context::~threadpool_object_context(v2);
    operator delete(v2, (const struct std::nothrow_t *)0x68);
  }
}

```

## disassembly

```asm
0x18001e4bc  mov     [rsp+arg_0], rbx
0x18001e4c1  push    rdi
0x18001e4c2  sub     rsp, 20h
0x18001e4c6  mov     rbx, [rcx]
0x18001e4c9  test    rbx, rbx
0x18001e4cc  jz      short loc_18001E519
0x18001e4ce  mov     rcx, [rbx+50h]; pti
0x18001e4d2  test    rcx, rcx
0x18001e4d5  jz      short loc_18001E4DD
0x18001e4d7  call    cs:__imp_CloseThreadpoolTimer
0x18001e4dd  lea     rdi, [rbx+10h]
0x18001e4e1  mov     rcx, [rdi+38h]
0x18001e4e5  test    rcx, rcx
0x18001e4e8  jz      short loc_18001E504
0x18001e4ea  mov     rax, [rcx]
0x18001e4ed  cmp     rcx, rdi
0x18001e4f0  setnz   dl
0x18001e4f3  mov     rax, [rax+20h]
0x18001e4f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4fc  mov     qword ptr [rdi+38h], 0
0x18001e504  mov     rcx, rbx; this
0x18001e507  call    ??1threadpool_object_context@details@wil@@QEAA@XZ; wil::details::threadpool_object_context::~threadpool_object_context(void)
0x18001e50c  mov     edx, 68h ; 'h'; struct std::nothrow_t *
0x18001e511  mov     rcx, rbx; void *
0x18001e514  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001e519  mov     rbx, [rsp+28h+arg_0]
0x18001e51e  add     rsp, 20h
0x18001e522  pop     rdi
0x18001e523  retn
```
