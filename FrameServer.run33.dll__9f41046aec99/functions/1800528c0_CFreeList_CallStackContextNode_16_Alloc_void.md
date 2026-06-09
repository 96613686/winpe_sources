# CFreeList<CallStackContextNode,16>::Alloc<>(void)

- ea: `0x1800528c0`
- end: `0x180052977`
- name: `??$Alloc@$$V@?$CFreeList@VCallStackContextNode@@$0BA@@@QEAAPEAVCallStackContextNode@@XZ`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180052bd0`

## callees

- `0x1800039f0`
- `0x1800528c0`
- `0x180052980`
- `0x180052f98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005295e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005295e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800528d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800528d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800528fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052937`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800528fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052937`

## pseudocode

```c
CallStackContext *__fastcall CFreeList<CallStackContextNode,16>::Alloc<>(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  CallStackContext *v3; // rdi
  CallStackContext *v4; // rbx
  DWORD v5; // eax
  DWORD CurrentThreadId; // eax

  v1 = (struct _RTL_CRITICAL_SECTION *)(a1 + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v3 = *(CallStackContext **)(a1 + 56);
  if ( v3 )
  {
    *(_QWORD *)(a1 + 56) = *((_QWORD *)v3 + 254);
    *((_QWORD *)v3 + 254) = 0;
    --*(_DWORD *)(a1 + 64);
    CurrentThreadId = GetCurrentThreadId();
    CallStackContext::Init(v3, CurrentThreadId, 0x7Cu);
    *((_QWORD *)v3 + 254) = 0;
    v4 = v3;
  }
  else
  {
    ++*(_DWORD *)(a1 + 68);
    v4 = (CallStackContext *)operator new(0x7F8u);
    if ( v4 )
    {
      v5 = GetCurrentThreadId();
      CallStackContext::CallStackContext(v4, v5, 0x7Cu);
      *((_QWORD *)v4 + 254) = 0;
    }
    else
    {
      v4 = 0;
    }
  }
  LeaveCriticalSection(v1);
  return v4;
}

```

## disassembly

```asm
0x1800528c0  mov     [rsp+arg_0], rbx
0x1800528c5  mov     [rsp+arg_8], rsi
0x1800528ca  push    rdi
0x1800528cb  sub     rsp, 20h
0x1800528cf  lea     rsi, [rcx+10h]
0x1800528d3  mov     rbx, rcx
0x1800528d6  mov     rcx, rsi; lpCriticalSection
0x1800528d9  call    cs:__imp_EnterCriticalSection
0x1800528df  mov     rdi, [rbx+38h]
0x1800528e3  test    rdi, rdi
0x1800528e6  jnz     short loc_18005291E
0x1800528e8  inc     dword ptr [rbx+44h]
0x1800528eb  mov     ecx, 7F8h; Size
0x1800528f0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800528f5  mov     rbx, rax
0x1800528f8  test    rax, rax
0x1800528fb  jz      short loc_18005291A
0x1800528fd  call    cs:__imp_GetCurrentThreadId
0x180052903  lea     r8d, [rdi+7Ch]; unsigned int
0x180052907  mov     rcx, rbx; this
0x18005290a  mov     edx, eax; unsigned int
0x18005290c  call    ??0CallStackContext@@QEAA@KK@Z; CallStackContext::CallStackContext(ulong,ulong)
0x180052911  mov     [rbx+7F0h], rdi
0x180052918  jmp     short loc_18005295B
0x18005291a  xor     ebx, ebx
0x18005291c  jmp     short loc_18005295B
0x18005291e  mov     rax, [rdi+7F0h]
0x180052925  mov     [rbx+38h], rax
0x180052929  mov     qword ptr [rdi+7F0h], 0
0x180052934  dec     dword ptr [rbx+40h]
0x180052937  call    cs:__imp_GetCurrentThreadId
0x18005293d  mov     r8d, 7Ch ; '|'; unsigned int
0x180052943  mov     rcx, rdi; this
0x180052946  mov     edx, eax; unsigned int
0x180052948  call    ?Init@CallStackContext@@QEAAXKK@Z; CallStackContext::Init(ulong,ulong)
0x18005294d  mov     qword ptr [rdi+7F0h], 0
0x180052958  mov     rbx, rdi
0x18005295b  mov     rcx, rsi; lpCriticalSection
0x18005295e  call    cs:__imp_LeaveCriticalSection
0x180052964  mov     rsi, [rsp+28h+arg_8]
0x180052969  mov     rax, rbx
0x18005296c  mov     rbx, [rsp+28h+arg_0]
0x180052971  add     rsp, 20h
0x180052975  pop     rdi
0x180052976  retn
```
