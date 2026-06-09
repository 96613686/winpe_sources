# COverlayTabletEventSink::FinalConstruct(void)

- ea: `0x1800da0d8`
- end: `0x1800da301`
- name: `?FinalConstruct@COverlayTabletEventSink@@QEAAJXZ`
- size: `553`
- prototype: `__int64 __fastcall(COverlayTabletEventSink *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800d7f3c`

## callees

- `0x1800da0d8`
- `0x18010c010`

## import_xrefs

- `msvcrt!_beginthreadex` at `0x1800da200`
- `msvcrt!_beginthreadex` at `0x1800da2c4`
- `msvcrt!_beginthreadex` at `0x1800da200`
- `msvcrt!_beginthreadex` at `0x1800da2c4`
- `msvcrt!_errno` at `0x1800da20f`
- `msvcrt!_errno` at `0x1800da2d3`
- `msvcrt!_errno` at `0x1800da20f`
- `msvcrt!_errno` at `0x1800da2d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da156`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da18d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da1c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da291`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da156`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da18d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da1c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da291`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800da118`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800da118`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800da135`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800da17b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800da1b2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800da282`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800da135`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800da17b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800da1b2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800da282`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800da266`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800da266`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800da0fc`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800da0fc`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800da24e`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800da24e`

## pseudocode

```c
__int64 __fastcall COverlayTabletEventSink::FinalConstruct(LPUNKNOWN *this)
{
  IUnknown *v2; // rax
  int FreeThreadedMarshaler; // ebx
  IUnknown *EventW; // rax
  HANDLE *v5; // rsi
  signed int LastError; // eax
  IUnknown *v7; // rax
  signed int v8; // eax
  IUnknown *v9; // rax
  signed int v10; // eax
  uintptr_t v11; // rax
  int *v12; // rax
  IUnknown *v13; // rax
  signed int v14; // eax
  uintptr_t v15; // rax
  int *v16; // rax
  DWORD dwindex; // [rsp+70h] [rbp+8h] BYREF

  v2 = (IUnknown *)((__int64 (__fastcall *)(LPUNKNOWN *))(*this)[3].lpVtbl)(this);
  FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler(v2, this + 11);
  if ( FreeThreadedMarshaler < 0 )
    return (unsigned int)FreeThreadedMarshaler;
  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(this + 24), 0x8001FA0u) )
    return (unsigned int)-2147024882;
  EventW = (IUnknown *)CreateEventW(0, 1, 0, 0);
  v5 = (HANDLE *)(this + 20);
  this[20] = EventW;
  if ( EventW )
    goto LABEL_7;
  LastError = GetLastError();
  FreeThreadedMarshaler = LastError;
  if ( LastError > 0 )
    FreeThreadedMarshaler = (unsigned __int16)LastError | 0x80070000;
  if ( FreeThreadedMarshaler >= 0 )
  {
LABEL_7:
    v7 = (IUnknown *)CreateEventW(0, 1, 0, 0);
    this[18] = v7;
    if ( v7 )
      goto LABEL_11;
    v8 = GetLastError();
    FreeThreadedMarshaler = v8;
    if ( v8 > 0 )
      FreeThreadedMarshaler = (unsigned __int16)v8 | 0x80070000;
    if ( FreeThreadedMarshaler >= 0 )
    {
LABEL_11:
      v9 = (IUnknown *)CreateEventW(0, 1, 0, 0);
      this[19] = v9;
      if ( v9 )
        goto LABEL_15;
      v10 = GetLastError();
      FreeThreadedMarshaler = v10;
      if ( v10 > 0 )
        FreeThreadedMarshaler = (unsigned __int16)v10 | 0x80070000;
      if ( FreeThreadedMarshaler >= 0 )
      {
LABEL_15:
        v11 = _beginthreadex(0, 0, COverlayTabletEventSink::EventQueueThread, this, 0, (unsigned int *)this + 34);
        this[15] = (LPUNKNOWN)v11;
        if ( v11 )
        {
          dwindex = 0;
          if ( CoWaitForMultipleHandles(0, 0xEA60u, 1u, (LPHANDLE)this + 20, &dwindex) < 0 )
            FreeThreadedMarshaler = -2147418113;
        }
        else
        {
          v12 = _errno();
          if ( *v12 == 11 )
          {
            FreeThreadedMarshaler = -2147024882;
          }
          else
          {
            FreeThreadedMarshaler = -2147024809;
            if ( *v12 != 22 )
              FreeThreadedMarshaler = -2147467259;
          }
        }
      }
    }
  }
  if ( *v5 )
  {
    CloseHandle(*v5);
    *v5 = 0;
  }
  if ( FreeThreadedMarshaler >= 0 )
  {
    v13 = (IUnknown *)CreateEventW(0, 1, 0, 0);
    this[14] = v13;
    if ( !v13 )
    {
      v14 = GetLastError();
      FreeThreadedMarshaler = v14;
      if ( v14 > 0 )
        return (unsigned __int16)v14 | 0x80070000;
      return (unsigned int)FreeThreadedMarshaler;
    }
    v15 = _beginthreadex(0, 0, COverlayTabletEventSink::MessagePump, this, 0, 0);
    this[13] = (LPUNKNOWN)v15;
    if ( v15 )
      return (unsigned int)FreeThreadedMarshaler;
    v16 = _errno();
    if ( *v16 != 11 )
    {
      FreeThreadedMarshaler = -2147024809;
      if ( *v16 != 22 )
        return (unsigned int)-2147467259;
      return (unsigned int)FreeThreadedMarshaler;
    }
    return (unsigned int)-2147024882;
  }
  return (unsigned int)FreeThreadedMarshaler;
}

```

## disassembly

```asm
0x1800da0d8  push    rbx
0x1800da0da  push    rsi
0x1800da0db  push    rdi
0x1800da0dc  push    r13
0x1800da0de  push    r14
0x1800da0e0  push    r15
0x1800da0e2  sub     rsp, 38h
0x1800da0e6  mov     rax, [rcx]
0x1800da0e9  mov     rdi, rcx
0x1800da0ec  mov     rax, [rax+18h]
0x1800da0f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da0f5  lea     rdx, [rdi+58h]; ppunkMarshal
0x1800da0f9  mov     rcx, rax; punkOuter
0x1800da0fc  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800da102  mov     ebx, eax
0x1800da104  test    eax, eax
0x1800da106  js      loc_1800DA2F1
0x1800da10c  lea     rcx, [rdi+0C0h]; lpCriticalSection
0x1800da113  mov     edx, 8001FA0h; dwSpinCount
0x1800da118  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800da11e  test    eax, eax
0x1800da120  jz      loc_1800DA2EC
0x1800da126  xor     r9d, r9d; lpName
0x1800da129  xor     r8d, r8d; bInitialState
0x1800da12c  xor     ecx, ecx; lpEventAttributes
0x1800da12e  lea     r15d, [r9+1]
0x1800da132  mov     edx, r15d; bManualReset
0x1800da135  call    cs:__imp_CreateEventW
0x1800da13b  lea     rsi, [rdi+0A0h]
0x1800da142  mov     r13d, 80004005h
0x1800da148  mov     [rsi], rax
0x1800da14b  mov     r14d, 80070000h
0x1800da151  test    rax, rax
0x1800da154  jnz     short loc_1800DA170
0x1800da156  call    cs:__imp_GetLastError
0x1800da15c  mov     ebx, eax
0x1800da15e  test    eax, eax
0x1800da160  jle     short loc_1800DA168
0x1800da162  movzx   ebx, ax
0x1800da165  or      ebx, r14d
0x1800da168  test    ebx, ebx
0x1800da16a  js      loc_1800DA25E
0x1800da170  xor     r9d, r9d; lpName
0x1800da173  xor     r8d, r8d; bInitialState
0x1800da176  mov     edx, r15d; bManualReset
0x1800da179  xor     ecx, ecx; lpEventAttributes
0x1800da17b  call    cs:__imp_CreateEventW
0x1800da181  mov     [rdi+90h], rax
0x1800da188  test    rax, rax
0x1800da18b  jnz     short loc_1800DA1A7
0x1800da18d  call    cs:__imp_GetLastError
0x1800da193  mov     ebx, eax
0x1800da195  test    eax, eax
0x1800da197  jle     short loc_1800DA19F
0x1800da199  movzx   ebx, ax
0x1800da19c  or      ebx, r14d
0x1800da19f  test    ebx, ebx
0x1800da1a1  js      loc_1800DA25E
0x1800da1a7  xor     r9d, r9d; lpName
0x1800da1aa  xor     r8d, r8d; bInitialState
0x1800da1ad  mov     edx, r15d; bManualReset
0x1800da1b0  xor     ecx, ecx; lpEventAttributes
0x1800da1b2  call    cs:__imp_CreateEventW
0x1800da1b8  mov     [rdi+98h], rax
0x1800da1bf  test    rax, rax
0x1800da1c2  jnz     short loc_1800DA1DE
0x1800da1c4  call    cs:__imp_GetLastError
0x1800da1ca  mov     ebx, eax
0x1800da1cc  test    eax, eax
0x1800da1ce  jle     short loc_1800DA1D6
0x1800da1d0  movzx   ebx, ax
0x1800da1d3  or      ebx, r14d
0x1800da1d6  test    ebx, ebx
0x1800da1d8  js      loc_1800DA25E
0x1800da1de  lea     rax, [rdi+88h]
0x1800da1e5  mov     r9, rdi; ArgList
0x1800da1e8  mov     [rsp+68h+ThrdAddr], rax; ThrdAddr
0x1800da1ed  lea     r8, ?EventQueueThread@COverlayTabletEventSink@@SAIPEAX@Z; StartAddress
0x1800da1f4  xor     edx, edx; StackSize
0x1800da1f6  mov     [rsp+68h+InitFlag], 0; InitFlag
0x1800da1fe  xor     ecx, ecx; Security
0x1800da200  call    cs:__imp__beginthreadex
0x1800da206  mov     [rdi+78h], rax
0x1800da20a  test    rax, rax
0x1800da20d  jnz     short loc_1800DA22F
0x1800da20f  call    cs:__imp__errno
0x1800da215  cmp     dword ptr [rax], 0Bh
0x1800da218  jz      short loc_1800DA228
0x1800da21a  cmp     dword ptr [rax], 16h
0x1800da21d  mov     ebx, 80070057h
0x1800da222  cmovnz  ebx, r13d
0x1800da226  jmp     short loc_1800DA25E
0x1800da228  mov     ebx, 8007000Eh
0x1800da22d  jmp     short loc_1800DA25E
0x1800da22f  lea     rax, [rsp+68h+dwindex]
0x1800da234  mov     [rsp+68h+dwindex], 0
0x1800da23c  mov     r9, rsi; pHandles
0x1800da23f  mov     qword ptr [rsp+68h+InitFlag], rax; lpdwindex
0x1800da244  mov     r8d, r15d; cHandles
0x1800da247  mov     edx, 0EA60h; dwTimeout
0x1800da24c  xor     ecx, ecx; dwFlags
0x1800da24e  call    cs:__imp_CoWaitForMultipleHandles
0x1800da254  test    eax, eax
0x1800da256  mov     ecx, 8000FFFFh
0x1800da25b  cmovs   ebx, ecx
0x1800da25e  mov     rcx, [rsi]; hObject
0x1800da261  test    rcx, rcx
0x1800da264  jz      short loc_1800DA273
0x1800da266  call    cs:__imp_CloseHandle
0x1800da26c  mov     qword ptr [rsi], 0
0x1800da273  test    ebx, ebx
0x1800da275  js      short loc_1800DA2F1
0x1800da277  xor     r9d, r9d; lpName
0x1800da27a  xor     r8d, r8d; bInitialState
0x1800da27d  mov     edx, r15d; bManualReset
0x1800da280  xor     ecx, ecx; lpEventAttributes
0x1800da282  call    cs:__imp_CreateEventW
0x1800da288  mov     [rdi+70h], rax
0x1800da28c  test    rax, rax
0x1800da28f  jnz     short loc_1800DA2A5
0x1800da291  call    cs:__imp_GetLastError
0x1800da297  mov     ebx, eax
0x1800da299  test    eax, eax
0x1800da29b  jle     short loc_1800DA2F1
0x1800da29d  movzx   ebx, ax
0x1800da2a0  or      ebx, r14d
0x1800da2a3  jmp     short loc_1800DA2F1
0x1800da2a5  mov     [rsp+68h+ThrdAddr], 0; ThrdAddr
0x1800da2ae  lea     r8, ?MessagePump@COverlayTabletEventSink@@SAIPEAX@Z; StartAddress
0x1800da2b5  mov     r9, rdi; ArgList
0x1800da2b8  mov     [rsp+68h+InitFlag], 0; InitFlag
0x1800da2c0  xor     edx, edx; StackSize
0x1800da2c2  xor     ecx, ecx; Security
0x1800da2c4  call    cs:__imp__beginthreadex
0x1800da2ca  mov     [rdi+68h], rax
0x1800da2ce  test    rax, rax
0x1800da2d1  jnz     short loc_1800DA2F1
0x1800da2d3  call    cs:__imp__errno
0x1800da2d9  cmp     dword ptr [rax], 0Bh
0x1800da2dc  jz      short loc_1800DA2EC
0x1800da2de  cmp     dword ptr [rax], 16h
0x1800da2e1  mov     ebx, 80070057h
0x1800da2e6  cmovnz  ebx, r13d
0x1800da2ea  jmp     short loc_1800DA2F1
0x1800da2ec  mov     ebx, 8007000Eh
0x1800da2f1  mov     eax, ebx
0x1800da2f3  add     rsp, 38h
0x1800da2f7  pop     r15
0x1800da2f9  pop     r14
0x1800da2fb  pop     r13
0x1800da2fd  pop     rdi
0x1800da2fe  pop     rsi
0x1800da2ff  pop     rbx
0x1800da300  retn
```
