# CTpWaiterThreadManagerLegacy::HrCreateNewThread(void)

- ea: `0x18014d840`
- end: `0x18014da28`
- name: `?HrCreateNewThread@CTpWaiterThreadManagerLegacy@@AEAAJXZ`
- size: `488`
- prototype: `__int64 __fastcall(CTpWaiterThreadManagerLegacy *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18014d730`
- `0x18014d7e0`

## callees

- `0x18001399c`
- `0x18014d5e0`
- `0x18014d6dc`
- `0x18014d840`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18014d8f8`
- `KERNEL32!GetLastError` at `0x18014d8f8`
- `KERNEL32!DeleteCriticalSection` at `0x18014d94b`
- `KERNEL32!DeleteCriticalSection` at `0x18014d94b`
- `KERNEL32!GetTickCount64` at `0x18014d968`
- `KERNEL32!GetTickCount64` at `0x18014d968`
- `KERNEL32!CloseHandle` at `0x18014d8e6`
- `KERNEL32!CloseHandle` at `0x18014d941`
- `KERNEL32!CloseHandle` at `0x18014d8e6`
- `KERNEL32!CloseHandle` at `0x18014d941`
- `KERNEL32!CreateEventExW` at `0x18014d8ca`
- `KERNEL32!CreateEventExW` at `0x18014d8ca`
- `KERNEL32!CreateThread` at `0x18014d998`
- `KERNEL32!CreateThread` at `0x18014d998`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18014d88d`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18014d88d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18014d954`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18014d9c3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18014da0d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18014d954`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18014d9c3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18014da0d`

## pseudocode

```c
__int64 __fastcall CTpWaiterThreadManagerLegacy::HrCreateNewThread(
        CTpWaiterThreadManagerLegacy *this,
        __int64 a2,
        unsigned __int64 a3)
{
  signed int v4; // edi
  unsigned int v5; // eax
  CTpWaiterThreadState *v6; // rax
  struct IEventPool *v7; // r8
  CTpWaiterThreadState *v8; // rbx
  HANDLE Event; // rax
  void *v10; // rcx
  HANDLE v11; // rbp
  signed int LastError; // eax
  CTpWaiterThreadState *v13; // rbp
  void *v14; // rcx
  HANDLE Thread; // rax

  if ( *((_BYTE *)this + 16) )
    return (unsigned int)-2147467259;
  v5 = *((_DWORD *)this + 22);
  if ( v5 <= *((_DWORD *)this + 21) )
  {
    if ( !Mso::Memory::TryReallocateRawBytes(
            (CTpWaiterThreadManagerLegacy *)((char *)this + 72),
            (void **)(8LL * (v5 + 5)),
            a3) )
      return (unsigned int)-2147467259;
    *((_DWORD *)this + 22) += 5;
  }
  v6 = (CTpWaiterThreadState *)malloc(0xC28u);
  if ( v6 )
    v8 = CTpWaiterThreadState::CTpWaiterThreadState(v6, this, v7);
  else
    v8 = 0;
  if ( v8 )
  {
    v4 = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    v10 = (void *)*((_QWORD *)v8 + 384);
    v11 = Event;
    if ( v10 )
    {
      *((_QWORD *)v8 + 384) = 0;
      CloseHandle(v10);
    }
    *((_QWORD *)v8 + 384) = v11;
    if ( !v11 )
    {
      LastError = GetLastError();
      v4 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v4 = LastError;
    }
    v13 = 0;
    if ( v4 < 0 )
    {
      v13 = v8;
      v8 = 0;
    }
    if ( v13 && _InterlockedExchangeAdd((volatile signed __int32 *)v13 + 777, 0xFFFFFFFF) == 1 )
    {
      v14 = (void *)*((_QWORD *)v13 + 384);
      if ( v14 )
      {
        *((_QWORD *)v13 + 384) = 0;
        CloseHandle(v14);
      }
      DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v13 + 8));
      free(v13);
    }
    if ( v4 >= 0 )
    {
      if ( !*((_QWORD *)this + 12) )
        *((_QWORD *)this + 12) = GetTickCount64();
      _InterlockedIncrement((volatile signed __int32 *)v8 + 777);
      Thread = CreateThread(0, 0, CTpWaiterThreadManagerLegacy::WaiterThreadProc, v8, 0, (LPDWORD)v8 + 766);
      if ( Thread )
      {
        *((_QWORD *)v8 + 382) = Thread;
        *(_QWORD *)(*((_QWORD *)this + 9) + 8LL * *((unsigned int *)this + 21)) = v8;
        v8 = 0;
        ++*((_DWORD *)this + 21);
        _InterlockedAdd((volatile signed __int32 *)this + 20, 0x3Eu);
      }
      else
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 777, 0xFFFFFFFF) == 1 && v8 )
        {
          CTpWaiterThreadState::~CTpWaiterThreadState(v8);
          free(v8);
        }
        v4 = -2147467259;
      }
    }
    if ( v8 && _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 777, 0xFFFFFFFF) == 1 )
    {
      CTpWaiterThreadState::~CTpWaiterThreadState(v8);
      free(v8);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18014d840  mov     [rsp+arg_8], rbx
0x18014d845  mov     [rsp+arg_10], rbp
0x18014d84a  push    rsi
0x18014d84b  push    rdi
0x18014d84c  push    r14
0x18014d84e  sub     rsp, 30h
0x18014d852  xor     r14d, r14d
0x18014d855  mov     rsi, rcx
0x18014d858  cmp     [rcx+10h], r14b
0x18014d85c  jz      short loc_18014D868
0x18014d85e  mov     edi, 80004005h
0x18014d863  jmp     loc_18014DA13
0x18014d868  mov     eax, [rcx+58h]
0x18014d86b  cmp     eax, [rcx+54h]
0x18014d86e  ja      short loc_18014D888
0x18014d870  lea     edx, [rax+5]
0x18014d873  add     rcx, 48h ; 'H'; this
0x18014d877  shl     rdx, 3; void **
0x18014d87b  call    ?TryReallocateRawBytes@Memory@Mso@@YA_NAEAPEAX_K@Z; Mso::Memory::TryReallocateRawBytes(void * &,unsigned __int64)
0x18014d880  test    al, al
0x18014d882  jz      short loc_18014D85E
0x18014d884  add     dword ptr [rsi+58h], 5
0x18014d888  mov     ecx, 0C28h; Size
0x18014d88d  call    cs:__imp_malloc
0x18014d893  test    rax, rax
0x18014d896  jz      short loc_18014D8A8
0x18014d898  mov     rdx, rsi; struct CTpWaiterThreadManager *
0x18014d89b  mov     rcx, rax; this
0x18014d89e  call    ??0CTpWaiterThreadState@@QEAA@PEAVCTpWaiterThreadManager@@PEAUIEventPool@@@Z; CTpWaiterThreadState::CTpWaiterThreadState(CTpWaiterThreadManager *,IEventPool *)
0x18014d8a3  mov     rbx, rax
0x18014d8a6  jmp     short loc_18014D8AB
0x18014d8a8  mov     rbx, r14
0x18014d8ab  test    rbx, rbx
0x18014d8ae  jnz     short loc_18014D8BA
0x18014d8b0  mov     edi, 8007000Eh
0x18014d8b5  jmp     loc_18014DA13
0x18014d8ba  mov     r9d, 1F0003h; dwDesiredAccess
0x18014d8c0  xor     r8d, r8d; dwFlags
0x18014d8c3  xor     edx, edx; lpName
0x18014d8c5  xor     ecx, ecx; lpEventAttributes
0x18014d8c7  mov     edi, r14d
0x18014d8ca  call    cs:__imp_CreateEventExW
0x18014d8d0  mov     rcx, [rbx+0C00h]; hObject
0x18014d8d7  mov     rbp, rax
0x18014d8da  test    rcx, rcx
0x18014d8dd  jz      short loc_18014D8EC
0x18014d8df  mov     [rbx+0C00h], r14
0x18014d8e6  call    cs:__imp_CloseHandle
0x18014d8ec  mov     [rbx+0C00h], rbp
0x18014d8f3  test    rbp, rbp
0x18014d8f6  jnz     short loc_18014D90C
0x18014d8f8  call    cs:__imp_GetLastError
0x18014d8fe  movzx   edi, ax
0x18014d901  or      edi, 80070000h
0x18014d907  test    eax, eax
0x18014d909  cmovle  edi, eax
0x18014d90c  test    edi, edi
0x18014d90e  mov     rbp, r14
0x18014d911  cmovs   rbp, rbx
0x18014d915  cmovs   rbx, r14
0x18014d919  test    rbp, rbp
0x18014d91c  jz      short loc_18014D95A
0x18014d91e  or      eax, 0FFFFFFFFh
0x18014d921  lock xadd [rbp+0C24h], eax
0x18014d929  cmp     eax, 1
0x18014d92c  jnz     short loc_18014D95A
0x18014d92e  mov     rcx, [rbp+0C00h]; hObject
0x18014d935  test    rcx, rcx
0x18014d938  jz      short loc_18014D947
0x18014d93a  mov     [rbp+0C00h], r14
0x18014d941  call    cs:__imp_CloseHandle
0x18014d947  lea     rcx, [rbp+8]; lpCriticalSection
0x18014d94b  call    cs:__imp_DeleteCriticalSection
0x18014d951  mov     rcx, rbp; Block
0x18014d954  call    cs:__imp_free
0x18014d95a  test    edi, edi
0x18014d95c  js      loc_18014D9ED
0x18014d962  cmp     [rsi+60h], r14
0x18014d966  jnz     short loc_18014D972
0x18014d968  call    cs:__imp_GetTickCount64
0x18014d96e  mov     [rsi+60h], rax
0x18014d972  lock inc dword ptr [rbx+0C24h]
0x18014d979  lea     rax, [rbx+0BF8h]
0x18014d980  mov     r9, rbx; lpParameter
0x18014d983  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x18014d988  lea     r8, ?WaiterThreadProc@CTpWaiterThreadManagerLegacy@@CAKPEAX@Z; lpStartAddress
0x18014d98f  xor     edx, edx; dwStackSize
0x18014d991  mov     [rsp+48h+dwCreationFlags], r14d; dwCreationFlags
0x18014d996  xor     ecx, ecx; lpThreadAttributes
0x18014d998  call    cs:__imp_CreateThread
0x18014d99e  test    rax, rax
0x18014d9a1  jnz     short loc_18014D9D0
0x18014d9a3  or      eax, 0FFFFFFFFh
0x18014d9a6  lock xadd [rbx+0C24h], eax
0x18014d9ae  cmp     eax, 1
0x18014d9b1  jnz     short loc_18014D9C9
0x18014d9b3  test    rbx, rbx
0x18014d9b6  jz      short loc_18014D9C9
0x18014d9b8  mov     rcx, rbx; this
0x18014d9bb  call    ??1CTpWaiterThreadState@@AEAA@XZ; CTpWaiterThreadState::~CTpWaiterThreadState(void)
0x18014d9c0  mov     rcx, rbx; Block
0x18014d9c3  call    cs:__imp_free
0x18014d9c9  mov     edi, 80004005h
0x18014d9ce  jmp     short loc_18014D9ED
0x18014d9d0  mov     [rbx+0BF0h], rax
0x18014d9d7  mov     ecx, [rsi+54h]
0x18014d9da  mov     rax, [rsi+48h]
0x18014d9de  mov     [rax+rcx*8], rbx
0x18014d9e2  mov     rbx, r14
0x18014d9e5  inc     dword ptr [rsi+54h]
0x18014d9e8  lock add dword ptr [rsi+50h], 3Eh ; '>'
0x18014d9ed  test    rbx, rbx
0x18014d9f0  jz      short loc_18014DA13
0x18014d9f2  or      edx, 0FFFFFFFFh
0x18014d9f5  lock xadd [rbx+0C24h], edx
0x18014d9fd  cmp     edx, 1
0x18014da00  jnz     short loc_18014DA13
0x18014da02  mov     rcx, rbx; this
0x18014da05  call    ??1CTpWaiterThreadState@@AEAA@XZ; CTpWaiterThreadState::~CTpWaiterThreadState(void)
0x18014da0a  mov     rcx, rbx; Block
0x18014da0d  call    cs:__imp_free
0x18014da13  mov     rbx, [rsp+48h+arg_8]
0x18014da18  mov     eax, edi
0x18014da1a  mov     rbp, [rsp+48h+arg_10]
0x18014da1f  add     rsp, 30h
0x18014da23  pop     r14
0x18014da25  pop     rdi
0x18014da26  pop     rsi
0x18014da27  retn
```
