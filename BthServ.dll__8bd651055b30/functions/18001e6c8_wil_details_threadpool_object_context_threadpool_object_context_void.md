# wil::details::threadpool_object_context::~threadpool_object_context(void)

- ea: `0x18001e6c8`
- end: `0x18001e745`
- name: `??1threadpool_object_context@details@wil@@QEAA@XZ`
- size: `125`
- prototype: `void __fastcall(wil::details::threadpool_object_context *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18001e4bc`
- `0x18001e74c`
- `0x18001f99c`

## callees

- `0x18000944c`
- `0x18001e6c8`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001e6e5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001e6e5`

## pseudocode

```c
void __fastcall wil::details::threadpool_object_context::~threadpool_object_context(
        wil::details::threadpool_object_context *this)
{
  __int64 v2; // rcx
  unsigned int v3; // r8d
  const char *v4; // r9
  volatile signed __int32 *v5; // rbx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *(_QWORD *)this;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 8), 0xFFFFFFFF) == 1 && !SetEvent(*(HANDLE *)(v2 + 16)) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v3, v4);
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 1);
  if ( v5 && _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
    if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
  }
}

```

## disassembly

```asm
0x18001e6c8  push    rbx
0x18001e6ca  sub     rsp, 20h
0x18001e6ce  mov     rbx, rcx
0x18001e6d1  or      eax, 0FFFFFFFFh
0x18001e6d4  mov     rcx, [rcx]
0x18001e6d7  lock xadd [rcx+8], eax
0x18001e6dc  cmp     eax, 1
0x18001e6df  jnz     short loc_18001E6EF
0x18001e6e1  mov     rcx, [rcx+10h]; hEvent
0x18001e6e5  call    cs:__imp_SetEvent
0x18001e6eb  test    eax, eax
0x18001e6ed  jz      short loc_18001E735
0x18001e6ef  mov     rbx, [rbx+8]
0x18001e6f3  test    rbx, rbx
0x18001e6f6  jz      short loc_18001E72F
0x18001e6f8  or      eax, 0FFFFFFFFh
0x18001e6fb  lock xadd [rbx+8], eax
0x18001e700  cmp     eax, 1
0x18001e703  jnz     short loc_18001E72F
0x18001e705  mov     rax, [rbx]
0x18001e708  mov     rcx, rbx
0x18001e70b  mov     rax, [rax]
0x18001e70e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e713  or      eax, 0FFFFFFFFh
0x18001e716  lock xadd [rbx+0Ch], eax
0x18001e71b  cmp     eax, 1
0x18001e71e  jnz     short loc_18001E72F
0x18001e720  mov     rax, [rbx]
0x18001e723  mov     rcx, rbx
0x18001e726  mov     rax, [rax+8]
0x18001e72a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e72f  add     rsp, 20h
0x18001e733  pop     rbx
0x18001e734  retn
0x18001e735  mov     rcx, [rsp+28h]; this
0x18001e73a  mov     edx, 0A01h; void *
0x18001e73f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
