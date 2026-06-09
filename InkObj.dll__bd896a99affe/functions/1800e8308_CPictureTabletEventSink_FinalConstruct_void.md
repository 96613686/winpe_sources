# CPictureTabletEventSink::FinalConstruct(void)

- ea: `0x1800e8308`
- end: `0x1800e8531`
- name: `?FinalConstruct@CPictureTabletEventSink@@QEAAJXZ`
- size: `553`
- prototype: `__int64 __fastcall(CPictureTabletEventSink *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800e62a0`

## callees

- `0x1800e8308`
- `0x18010c010`

## import_xrefs

- `msvcrt!_beginthreadex` at `0x1800e8430`
- `msvcrt!_beginthreadex` at `0x1800e84f4`
- `msvcrt!_beginthreadex` at `0x1800e8430`
- `msvcrt!_beginthreadex` at `0x1800e84f4`
- `msvcrt!_errno` at `0x1800e843f`
- `msvcrt!_errno` at `0x1800e8503`
- `msvcrt!_errno` at `0x1800e843f`
- `msvcrt!_errno` at `0x1800e8503`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e8386`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e83bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e83f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e84c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e8386`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e83bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e83f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e84c1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800e8348`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800e8348`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e8365`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e83ab`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e83e2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e84b2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e8365`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e83ab`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e83e2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e84b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e8496`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e8496`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800e832c`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800e832c`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800e847e`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800e847e`

## pseudocode

```c
__int64 __fastcall CPictureTabletEventSink::FinalConstruct(LPUNKNOWN *this)
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
        v11 = _beginthreadex(0, 0, CPictureTabletEventSink::EventQueueThread, this, 0, (unsigned int *)this + 34);
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
    v15 = _beginthreadex(0, 0, CPictureTabletEventSink::MessagePump, this, 0, 0);
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
0x1800e8308  push    rbx
0x1800e830a  push    rsi
0x1800e830b  push    rdi
0x1800e830c  push    r13
0x1800e830e  push    r14
0x1800e8310  push    r15
0x1800e8312  sub     rsp, 38h
0x1800e8316  mov     rax, [rcx]
0x1800e8319  mov     rdi, rcx
0x1800e831c  mov     rax, [rax+18h]
0x1800e8320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8325  lea     rdx, [rdi+58h]; ppunkMarshal
0x1800e8329  mov     rcx, rax; punkOuter
0x1800e832c  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800e8332  mov     ebx, eax
0x1800e8334  test    eax, eax
0x1800e8336  js      loc_1800E8521
0x1800e833c  lea     rcx, [rdi+0C0h]; lpCriticalSection
0x1800e8343  mov     edx, 8001FA0h; dwSpinCount
0x1800e8348  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800e834e  test    eax, eax
0x1800e8350  jz      loc_1800E851C
0x1800e8356  xor     r9d, r9d; lpName
0x1800e8359  xor     r8d, r8d; bInitialState
0x1800e835c  xor     ecx, ecx; lpEventAttributes
0x1800e835e  lea     r15d, [r9+1]
0x1800e8362  mov     edx, r15d; bManualReset
0x1800e8365  call    cs:__imp_CreateEventW
0x1800e836b  lea     rsi, [rdi+0A0h]
0x1800e8372  mov     r13d, 80004005h
0x1800e8378  mov     [rsi], rax
0x1800e837b  mov     r14d, 80070000h
0x1800e8381  test    rax, rax
0x1800e8384  jnz     short loc_1800E83A0
0x1800e8386  call    cs:__imp_GetLastError
0x1800e838c  mov     ebx, eax
0x1800e838e  test    eax, eax
0x1800e8390  jle     short loc_1800E8398
0x1800e8392  movzx   ebx, ax
0x1800e8395  or      ebx, r14d
0x1800e8398  test    ebx, ebx
0x1800e839a  js      loc_1800E848E
0x1800e83a0  xor     r9d, r9d; lpName
0x1800e83a3  xor     r8d, r8d; bInitialState
0x1800e83a6  mov     edx, r15d; bManualReset
0x1800e83a9  xor     ecx, ecx; lpEventAttributes
0x1800e83ab  call    cs:__imp_CreateEventW
0x1800e83b1  mov     [rdi+90h], rax
0x1800e83b8  test    rax, rax
0x1800e83bb  jnz     short loc_1800E83D7
0x1800e83bd  call    cs:__imp_GetLastError
0x1800e83c3  mov     ebx, eax
0x1800e83c5  test    eax, eax
0x1800e83c7  jle     short loc_1800E83CF
0x1800e83c9  movzx   ebx, ax
0x1800e83cc  or      ebx, r14d
0x1800e83cf  test    ebx, ebx
0x1800e83d1  js      loc_1800E848E
0x1800e83d7  xor     r9d, r9d; lpName
0x1800e83da  xor     r8d, r8d; bInitialState
0x1800e83dd  mov     edx, r15d; bManualReset
0x1800e83e0  xor     ecx, ecx; lpEventAttributes
0x1800e83e2  call    cs:__imp_CreateEventW
0x1800e83e8  mov     [rdi+98h], rax
0x1800e83ef  test    rax, rax
0x1800e83f2  jnz     short loc_1800E840E
0x1800e83f4  call    cs:__imp_GetLastError
0x1800e83fa  mov     ebx, eax
0x1800e83fc  test    eax, eax
0x1800e83fe  jle     short loc_1800E8406
0x1800e8400  movzx   ebx, ax
0x1800e8403  or      ebx, r14d
0x1800e8406  test    ebx, ebx
0x1800e8408  js      loc_1800E848E
0x1800e840e  lea     rax, [rdi+88h]
0x1800e8415  mov     r9, rdi; ArgList
0x1800e8418  mov     [rsp+68h+ThrdAddr], rax; ThrdAddr
0x1800e841d  lea     r8, ?EventQueueThread@CPictureTabletEventSink@@SAIPEAX@Z; StartAddress
0x1800e8424  xor     edx, edx; StackSize
0x1800e8426  mov     [rsp+68h+InitFlag], 0; InitFlag
0x1800e842e  xor     ecx, ecx; Security
0x1800e8430  call    cs:__imp__beginthreadex
0x1800e8436  mov     [rdi+78h], rax
0x1800e843a  test    rax, rax
0x1800e843d  jnz     short loc_1800E845F
0x1800e843f  call    cs:__imp__errno
0x1800e8445  cmp     dword ptr [rax], 0Bh
0x1800e8448  jz      short loc_1800E8458
0x1800e844a  cmp     dword ptr [rax], 16h
0x1800e844d  mov     ebx, 80070057h
0x1800e8452  cmovnz  ebx, r13d
0x1800e8456  jmp     short loc_1800E848E
0x1800e8458  mov     ebx, 8007000Eh
0x1800e845d  jmp     short loc_1800E848E
0x1800e845f  lea     rax, [rsp+68h+dwindex]
0x1800e8464  mov     [rsp+68h+dwindex], 0
0x1800e846c  mov     r9, rsi; pHandles
0x1800e846f  mov     qword ptr [rsp+68h+InitFlag], rax; lpdwindex
0x1800e8474  mov     r8d, r15d; cHandles
0x1800e8477  mov     edx, 0EA60h; dwTimeout
0x1800e847c  xor     ecx, ecx; dwFlags
0x1800e847e  call    cs:__imp_CoWaitForMultipleHandles
0x1800e8484  test    eax, eax
0x1800e8486  mov     ecx, 8000FFFFh
0x1800e848b  cmovs   ebx, ecx
0x1800e848e  mov     rcx, [rsi]; hObject
0x1800e8491  test    rcx, rcx
0x1800e8494  jz      short loc_1800E84A3
0x1800e8496  call    cs:__imp_CloseHandle
0x1800e849c  mov     qword ptr [rsi], 0
0x1800e84a3  test    ebx, ebx
0x1800e84a5  js      short loc_1800E8521
0x1800e84a7  xor     r9d, r9d; lpName
0x1800e84aa  xor     r8d, r8d; bInitialState
0x1800e84ad  mov     edx, r15d; bManualReset
0x1800e84b0  xor     ecx, ecx; lpEventAttributes
0x1800e84b2  call    cs:__imp_CreateEventW
0x1800e84b8  mov     [rdi+70h], rax
0x1800e84bc  test    rax, rax
0x1800e84bf  jnz     short loc_1800E84D5
0x1800e84c1  call    cs:__imp_GetLastError
0x1800e84c7  mov     ebx, eax
0x1800e84c9  test    eax, eax
0x1800e84cb  jle     short loc_1800E8521
0x1800e84cd  movzx   ebx, ax
0x1800e84d0  or      ebx, r14d
0x1800e84d3  jmp     short loc_1800E8521
0x1800e84d5  mov     [rsp+68h+ThrdAddr], 0; ThrdAddr
0x1800e84de  lea     r8, ?MessagePump@CPictureTabletEventSink@@SAIPEAX@Z; StartAddress
0x1800e84e5  mov     r9, rdi; ArgList
0x1800e84e8  mov     [rsp+68h+InitFlag], 0; InitFlag
0x1800e84f0  xor     edx, edx; StackSize
0x1800e84f2  xor     ecx, ecx; Security
0x1800e84f4  call    cs:__imp__beginthreadex
0x1800e84fa  mov     [rdi+68h], rax
0x1800e84fe  test    rax, rax
0x1800e8501  jnz     short loc_1800E8521
0x1800e8503  call    cs:__imp__errno
0x1800e8509  cmp     dword ptr [rax], 0Bh
0x1800e850c  jz      short loc_1800E851C
0x1800e850e  cmp     dword ptr [rax], 16h
0x1800e8511  mov     ebx, 80070057h
0x1800e8516  cmovnz  ebx, r13d
0x1800e851a  jmp     short loc_1800E8521
0x1800e851c  mov     ebx, 8007000Eh
0x1800e8521  mov     eax, ebx
0x1800e8523  add     rsp, 38h
0x1800e8527  pop     r15
0x1800e8529  pop     r14
0x1800e852b  pop     r13
0x1800e852d  pop     rdi
0x1800e852e  pop     rsi
0x1800e852f  pop     rbx
0x1800e8530  retn
```
