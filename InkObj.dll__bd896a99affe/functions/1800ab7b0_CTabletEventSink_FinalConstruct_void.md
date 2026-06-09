# CTabletEventSink::FinalConstruct(void)

- ea: `0x1800ab7b0`
- end: `0x1800ab9d9`
- name: `?FinalConstruct@CTabletEventSink@@QEAAJXZ`
- size: `553`
- prototype: `__int64 __fastcall(CTabletEventSink *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800aa33c`

## callees

- `0x1800ab7b0`
- `0x18010c010`

## import_xrefs

- `msvcrt!_beginthreadex` at `0x1800ab8d8`
- `msvcrt!_beginthreadex` at `0x1800ab99c`
- `msvcrt!_beginthreadex` at `0x1800ab8d8`
- `msvcrt!_beginthreadex` at `0x1800ab99c`
- `msvcrt!_errno` at `0x1800ab8e7`
- `msvcrt!_errno` at `0x1800ab9ab`
- `msvcrt!_errno` at `0x1800ab8e7`
- `msvcrt!_errno` at `0x1800ab9ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab82e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab865`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab89c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab969`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab82e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab865`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab89c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab969`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800ab7f0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800ab7f0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ab80d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ab853`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ab88a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ab95a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ab80d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ab853`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ab88a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ab95a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ab93e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ab93e`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800ab7d4`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800ab7d4`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800ab926`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800ab926`

## pseudocode

```c
__int64 __fastcall CTabletEventSink::FinalConstruct(LPUNKNOWN *this)
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
        v11 = _beginthreadex(0, 0, CTabletEventSink::EventQueueThread, this, 0, (unsigned int *)this + 34);
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
    v15 = _beginthreadex(0, 0, CTabletEventSink::MessagePump, this, 0, 0);
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
0x1800ab7b0  push    rbx
0x1800ab7b2  push    rsi
0x1800ab7b3  push    rdi
0x1800ab7b4  push    r13
0x1800ab7b6  push    r14
0x1800ab7b8  push    r15
0x1800ab7ba  sub     rsp, 38h
0x1800ab7be  mov     rax, [rcx]
0x1800ab7c1  mov     rdi, rcx
0x1800ab7c4  mov     rax, [rax+18h]
0x1800ab7c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab7cd  lea     rdx, [rdi+58h]; ppunkMarshal
0x1800ab7d1  mov     rcx, rax; punkOuter
0x1800ab7d4  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800ab7da  mov     ebx, eax
0x1800ab7dc  test    eax, eax
0x1800ab7de  js      loc_1800AB9C9
0x1800ab7e4  lea     rcx, [rdi+0C0h]; lpCriticalSection
0x1800ab7eb  mov     edx, 8001FA0h; dwSpinCount
0x1800ab7f0  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800ab7f6  test    eax, eax
0x1800ab7f8  jz      loc_1800AB9C4
0x1800ab7fe  xor     r9d, r9d; lpName
0x1800ab801  xor     r8d, r8d; bInitialState
0x1800ab804  xor     ecx, ecx; lpEventAttributes
0x1800ab806  lea     r15d, [r9+1]
0x1800ab80a  mov     edx, r15d; bManualReset
0x1800ab80d  call    cs:__imp_CreateEventW
0x1800ab813  lea     rsi, [rdi+0A0h]
0x1800ab81a  mov     r13d, 80004005h
0x1800ab820  mov     [rsi], rax
0x1800ab823  mov     r14d, 80070000h
0x1800ab829  test    rax, rax
0x1800ab82c  jnz     short loc_1800AB848
0x1800ab82e  call    cs:__imp_GetLastError
0x1800ab834  mov     ebx, eax
0x1800ab836  test    eax, eax
0x1800ab838  jle     short loc_1800AB840
0x1800ab83a  movzx   ebx, ax
0x1800ab83d  or      ebx, r14d
0x1800ab840  test    ebx, ebx
0x1800ab842  js      loc_1800AB936
0x1800ab848  xor     r9d, r9d; lpName
0x1800ab84b  xor     r8d, r8d; bInitialState
0x1800ab84e  mov     edx, r15d; bManualReset
0x1800ab851  xor     ecx, ecx; lpEventAttributes
0x1800ab853  call    cs:__imp_CreateEventW
0x1800ab859  mov     [rdi+90h], rax
0x1800ab860  test    rax, rax
0x1800ab863  jnz     short loc_1800AB87F
0x1800ab865  call    cs:__imp_GetLastError
0x1800ab86b  mov     ebx, eax
0x1800ab86d  test    eax, eax
0x1800ab86f  jle     short loc_1800AB877
0x1800ab871  movzx   ebx, ax
0x1800ab874  or      ebx, r14d
0x1800ab877  test    ebx, ebx
0x1800ab879  js      loc_1800AB936
0x1800ab87f  xor     r9d, r9d; lpName
0x1800ab882  xor     r8d, r8d; bInitialState
0x1800ab885  mov     edx, r15d; bManualReset
0x1800ab888  xor     ecx, ecx; lpEventAttributes
0x1800ab88a  call    cs:__imp_CreateEventW
0x1800ab890  mov     [rdi+98h], rax
0x1800ab897  test    rax, rax
0x1800ab89a  jnz     short loc_1800AB8B6
0x1800ab89c  call    cs:__imp_GetLastError
0x1800ab8a2  mov     ebx, eax
0x1800ab8a4  test    eax, eax
0x1800ab8a6  jle     short loc_1800AB8AE
0x1800ab8a8  movzx   ebx, ax
0x1800ab8ab  or      ebx, r14d
0x1800ab8ae  test    ebx, ebx
0x1800ab8b0  js      loc_1800AB936
0x1800ab8b6  lea     rax, [rdi+88h]
0x1800ab8bd  mov     r9, rdi; ArgList
0x1800ab8c0  mov     [rsp+68h+ThrdAddr], rax; ThrdAddr
0x1800ab8c5  lea     r8, ?EventQueueThread@CTabletEventSink@@SAIPEAX@Z; StartAddress
0x1800ab8cc  xor     edx, edx; StackSize
0x1800ab8ce  mov     [rsp+68h+InitFlag], 0; InitFlag
0x1800ab8d6  xor     ecx, ecx; Security
0x1800ab8d8  call    cs:__imp__beginthreadex
0x1800ab8de  mov     [rdi+78h], rax
0x1800ab8e2  test    rax, rax
0x1800ab8e5  jnz     short loc_1800AB907
0x1800ab8e7  call    cs:__imp__errno
0x1800ab8ed  cmp     dword ptr [rax], 0Bh
0x1800ab8f0  jz      short loc_1800AB900
0x1800ab8f2  cmp     dword ptr [rax], 16h
0x1800ab8f5  mov     ebx, 80070057h
0x1800ab8fa  cmovnz  ebx, r13d
0x1800ab8fe  jmp     short loc_1800AB936
0x1800ab900  mov     ebx, 8007000Eh
0x1800ab905  jmp     short loc_1800AB936
0x1800ab907  lea     rax, [rsp+68h+dwindex]
0x1800ab90c  mov     [rsp+68h+dwindex], 0
0x1800ab914  mov     r9, rsi; pHandles
0x1800ab917  mov     qword ptr [rsp+68h+InitFlag], rax; lpdwindex
0x1800ab91c  mov     r8d, r15d; cHandles
0x1800ab91f  mov     edx, 0EA60h; dwTimeout
0x1800ab924  xor     ecx, ecx; dwFlags
0x1800ab926  call    cs:__imp_CoWaitForMultipleHandles
0x1800ab92c  test    eax, eax
0x1800ab92e  mov     ecx, 8000FFFFh
0x1800ab933  cmovs   ebx, ecx
0x1800ab936  mov     rcx, [rsi]; hObject
0x1800ab939  test    rcx, rcx
0x1800ab93c  jz      short loc_1800AB94B
0x1800ab93e  call    cs:__imp_CloseHandle
0x1800ab944  mov     qword ptr [rsi], 0
0x1800ab94b  test    ebx, ebx
0x1800ab94d  js      short loc_1800AB9C9
0x1800ab94f  xor     r9d, r9d; lpName
0x1800ab952  xor     r8d, r8d; bInitialState
0x1800ab955  mov     edx, r15d; bManualReset
0x1800ab958  xor     ecx, ecx; lpEventAttributes
0x1800ab95a  call    cs:__imp_CreateEventW
0x1800ab960  mov     [rdi+70h], rax
0x1800ab964  test    rax, rax
0x1800ab967  jnz     short loc_1800AB97D
0x1800ab969  call    cs:__imp_GetLastError
0x1800ab96f  mov     ebx, eax
0x1800ab971  test    eax, eax
0x1800ab973  jle     short loc_1800AB9C9
0x1800ab975  movzx   ebx, ax
0x1800ab978  or      ebx, r14d
0x1800ab97b  jmp     short loc_1800AB9C9
0x1800ab97d  mov     [rsp+68h+ThrdAddr], 0; ThrdAddr
0x1800ab986  lea     r8, ?MessagePump@CTabletEventSink@@SAIPEAX@Z; StartAddress
0x1800ab98d  mov     r9, rdi; ArgList
0x1800ab990  mov     [rsp+68h+InitFlag], 0; InitFlag
0x1800ab998  xor     edx, edx; StackSize
0x1800ab99a  xor     ecx, ecx; Security
0x1800ab99c  call    cs:__imp__beginthreadex
0x1800ab9a2  mov     [rdi+68h], rax
0x1800ab9a6  test    rax, rax
0x1800ab9a9  jnz     short loc_1800AB9C9
0x1800ab9ab  call    cs:__imp__errno
0x1800ab9b1  cmp     dword ptr [rax], 0Bh
0x1800ab9b4  jz      short loc_1800AB9C4
0x1800ab9b6  cmp     dword ptr [rax], 16h
0x1800ab9b9  mov     ebx, 80070057h
0x1800ab9be  cmovnz  ebx, r13d
0x1800ab9c2  jmp     short loc_1800AB9C9
0x1800ab9c4  mov     ebx, 8007000Eh
0x1800ab9c9  mov     eax, ebx
0x1800ab9cb  add     rsp, 38h
0x1800ab9cf  pop     r15
0x1800ab9d1  pop     r14
0x1800ab9d3  pop     r13
0x1800ab9d5  pop     rdi
0x1800ab9d6  pop     rsi
0x1800ab9d7  pop     rbx
0x1800ab9d8  retn
```
