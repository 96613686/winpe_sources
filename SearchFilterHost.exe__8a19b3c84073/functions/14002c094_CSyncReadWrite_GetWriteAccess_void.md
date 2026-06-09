# CSyncReadWrite::GetWriteAccess(void)

- ea: `0x14002c094`
- end: `0x14002c120`
- name: `?GetWriteAccess@CSyncReadWrite@@QEAAXXZ`
- size: `140`
- prototype: `void __fastcall(CSyncReadWrite *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14002c210`
- `0x14002c8dc`

## callees

- `0x140021c20`
- `0x14002c094`
- `0x14002c360`
- `0x14002c650`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002c0fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002c0fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14002c0b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14002c0d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14002c0b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14002c0d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002c0c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002c0c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSyncReadWrite::GetWriteAccess(CSyncReadWrite *this)
{
  int v2; // edi
  unsigned int v3; // edx
  int v4; // r8d

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v2 = 1;
  _InterlockedAdd((volatile signed __int32 *)this, 1u);
  *((_DWORD *)this + 1) = GetCurrentThreadId();
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  if ( *((_DWORD *)this + 2) )
  {
    CSyncReadWrite::LokInitWriteEvent(this);
    CEventSem::Reset(*((CEventSem **)this + 13));
  }
  else
  {
    v2 = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  if ( v2 )
    CEventSem::Wait(*((CEventSem **)this + 13), v3, v4);
}

```

## disassembly

```asm
0x14002c094  push    rdi
0x14002c096  sub     rsp, 30h
0x14002c09a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x14002c0a3  mov     [rsp+38h+arg_8], rbx
0x14002c0a8  mov     [rsp+38h+arg_10], rsi
0x14002c0ad  mov     rbx, rcx
0x14002c0b0  add     rcx, 10h; lpCriticalSection
0x14002c0b4  call    cs:__imp_EnterCriticalSection
0x14002c0ba  mov     edi, 1
0x14002c0bf  lock add [rbx], edi
0x14002c0c2  call    cs:__imp_GetCurrentThreadId
0x14002c0c8  mov     [rbx+4], eax
0x14002c0cb  lea     rsi, [rbx+38h]
0x14002c0cf  mov     [rsp+38h+arg_0], rsi
0x14002c0d4  mov     rcx, rsi; lpCriticalSection
0x14002c0d7  call    cs:__imp_EnterCriticalSection
0x14002c0dd  nop
0x14002c0de  cmp     dword ptr [rbx+8], 0
0x14002c0e2  jnz     short loc_14002C0E8
0x14002c0e4  xor     edi, edi
0x14002c0e6  jmp     short loc_14002C0FA
0x14002c0e8  mov     rcx, rbx; this
0x14002c0eb  call    ?LokInitWriteEvent@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::LokInitWriteEvent(void)
0x14002c0f0  mov     rcx, [rbx+68h]; this
0x14002c0f4  call    ?Reset@CEventSem@@QEAAXXZ; CEventSem::Reset(void)
0x14002c0f9  nop
0x14002c0fa  mov     rcx, rsi; lpCriticalSection
0x14002c0fd  call    cs:__imp_LeaveCriticalSection
0x14002c103  test    edi, edi
0x14002c105  jz      short loc_14002C110
0x14002c107  mov     rcx, [rbx+68h]; this
0x14002c10b  call    ?Wait@CEventSem@@QEAAKKH@Z; CEventSem::Wait(ulong,int)
0x14002c110  mov     rbx, [rsp+38h+arg_8]
0x14002c115  mov     rsi, [rsp+38h+arg_10]
0x14002c11a  add     rsp, 30h
0x14002c11e  pop     rdi
0x14002c11f  retn
```
