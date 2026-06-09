# CSyncReadWrite::GetWriteAccess(void)

- ea: `0x14004ff64`
- end: `0x14004fff0`
- name: `?GetWriteAccess@CSyncReadWrite@@QEAAXXZ`
- size: `140`
- prototype: `void __fastcall(CSyncReadWrite *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400501b0`
- `0x140050880`

## callees

- `0x140020090`
- `0x14004ff64`
- `0x140050304`
- `0x1400505f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14004ff84`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14004ffa7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14004ff84`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14004ffa7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004ffcd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14004ffcd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004ff92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004ff92`

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
0x14004ff64  push    rdi
0x14004ff66  sub     rsp, 30h
0x14004ff6a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x14004ff73  mov     [rsp+38h+arg_8], rbx
0x14004ff78  mov     [rsp+38h+arg_10], rsi
0x14004ff7d  mov     rbx, rcx
0x14004ff80  add     rcx, 10h; lpCriticalSection
0x14004ff84  call    cs:__imp_EnterCriticalSection
0x14004ff8a  mov     edi, 1
0x14004ff8f  lock add [rbx], edi
0x14004ff92  call    cs:__imp_GetCurrentThreadId
0x14004ff98  mov     [rbx+4], eax
0x14004ff9b  lea     rsi, [rbx+38h]
0x14004ff9f  mov     [rsp+38h+arg_0], rsi
0x14004ffa4  mov     rcx, rsi; lpCriticalSection
0x14004ffa7  call    cs:__imp_EnterCriticalSection
0x14004ffad  nop
0x14004ffae  cmp     dword ptr [rbx+8], 0
0x14004ffb2  jnz     short loc_14004FFB8
0x14004ffb4  xor     edi, edi
0x14004ffb6  jmp     short loc_14004FFCA
0x14004ffb8  mov     rcx, rbx; this
0x14004ffbb  call    ?LokInitWriteEvent@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::LokInitWriteEvent(void)
0x14004ffc0  mov     rcx, [rbx+68h]; this
0x14004ffc4  call    ?Reset@CEventSem@@QEAAXXZ; CEventSem::Reset(void)
0x14004ffc9  nop
0x14004ffca  mov     rcx, rsi; lpCriticalSection
0x14004ffcd  call    cs:__imp_LeaveCriticalSection
0x14004ffd3  test    edi, edi
0x14004ffd5  jz      short loc_14004FFE0
0x14004ffd7  mov     rcx, [rbx+68h]; this
0x14004ffdb  call    ?Wait@CEventSem@@QEAAKKH@Z; CEventSem::Wait(ulong,int)
0x14004ffe0  mov     rbx, [rsp+38h+arg_8]
0x14004ffe5  mov     rsi, [rsp+38h+arg_10]
0x14004ffea  add     rsp, 30h
0x14004ffee  pop     rdi
0x14004ffef  retn
```
