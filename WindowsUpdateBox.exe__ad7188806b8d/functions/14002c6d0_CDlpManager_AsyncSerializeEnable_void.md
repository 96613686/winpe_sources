# CDlpManager::AsyncSerializeEnable(void)

- ea: `0x14002c6d0`
- end: `0x14002ca4e`
- name: `?AsyncSerializeEnable@CDlpManager@@UEAAJXZ`
- size: `894`
- prototype: `__int64 __fastcall(CDlpManager *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1400076c8`
- `0x1400110a4`
- `0x1400135b8`
- `0x14002c6d0`
- `0x140034ab4`
- `0x140082010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14002c7e7`
- `KERNEL32!CloseHandle` at `0x14002c8a1`
- `KERNEL32!CloseHandle` at `0x14002c983`
- `KERNEL32!CloseHandle` at `0x14002c7e7`
- `KERNEL32!CloseHandle` at `0x14002c8a1`
- `KERNEL32!CloseHandle` at `0x14002c983`
- `KERNEL32!CreateThread` at `0x14002c968`
- `KERNEL32!CreateThread` at `0x14002c968`
- `KERNEL32!GetLastError` at `0x14002c7ff`
- `KERNEL32!GetLastError` at `0x14002c8b9`
- `KERNEL32!GetLastError` at `0x14002c99b`
- `KERNEL32!GetLastError` at `0x14002c7ff`
- `KERNEL32!GetLastError` at `0x14002c8b9`
- `KERNEL32!GetLastError` at `0x14002c99b`
- `KERNEL32!CreateEventW` at `0x14002c7cc`
- `KERNEL32!CreateEventW` at `0x14002c886`
- `KERNEL32!CreateEventW` at `0x14002c7cc`
- `KERNEL32!CreateEventW` at `0x14002c886`
- `KERNEL32!LeaveCriticalSection` at `0x14002ca25`
- `KERNEL32!LeaveCriticalSection` at `0x14002ca25`
- `KERNEL32!EnterCriticalSection` at `0x14002c6f8`
- `KERNEL32!EnterCriticalSection` at `0x14002c6f8`

## pseudocode

```c
__int64 __fastcall CDlpManager::AsyncSerializeEnable(CDlpManager *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  signed int v3; // edi
  __int64 v4; // rax
  unsigned int v5; // ebx
  int v6; // eax
  HANDLE EventW; // rbx
  void *v8; // rcx
  signed int v9; // eax
  HANDLE v10; // rbx
  void *v11; // rcx
  signed int v12; // eax
  __int64 v13; // rax
  HANDLE Thread; // rbx
  void *v15; // rcx
  signed int LastError; // eax
  __int64 dwCreationFlags; // [rsp+20h] [rbp-58h]
  LPDWORD lpThreadId; // [rsp+28h] [rbp-50h]
  unsigned int v20; // [rsp+80h] [rbp+8h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 256);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 256));
  v20 = 0;
  v3 = 0;
  if ( (*((_BYTE *)this + 856) & 1) == 0 )
    goto LABEL_46;
  v3 = CDword::Increment((CDlpManager *)((char *)this + 760), &v20);
  if ( v3 >= 0 )
  {
    if ( v20 != 1 )
      goto LABEL_46;
    EventW = CreateEventW(0, 0, 0, 0);
    v8 = (void *)*((_QWORD *)this + 84);
    if ( v8 )
      CloseHandle(v8);
    if ( EventW )
    {
      *((_QWORD *)this + 84) = EventW;
      v10 = CreateEventW(0, 1, 0, 0);
      v11 = (void *)*((_QWORD *)this + 85);
      if ( v11 )
        CloseHandle(v11);
      *((_QWORD *)this + 85) = v10;
      if ( v10 )
      {
        *((_QWORD *)this + 103) = this;
        v13 = *((_QWORD *)this + 84);
        if ( !v13 )
          v13 = 0;
        *((_QWORD *)this + 104) = v13;
        *((_QWORD *)this + 105) = v10;
        Thread = CreateThread(0, 0, CDlpManager::SerializeThreadProc, (char *)this + 824, 0, 0);
        v15 = (void *)*((_QWORD *)this + 86);
        if ( v15 )
          CloseHandle(v15);
        if ( Thread )
        {
          *((_QWORD *)this + 86) = Thread;
          goto LABEL_46;
        }
        *((_QWORD *)this + 86) = 0;
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError )
        {
          if ( LastError > 0 )
            v3 = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          v3 = -2147467259;
        }
        if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
          goto LABEL_46;
        v4 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
        v5 = 0;
        if ( v3 >= 0 || !v4 )
          goto LABEL_8;
        LODWORD(lpThreadId) = v3;
        LODWORD(dwCreationFlags) = 488;
      }
      else
      {
        v12 = GetLastError();
        v3 = v12;
        if ( v12 )
        {
          if ( v12 > 0 )
            v3 = (unsigned __int16)v12 | 0x80070000;
        }
        else
        {
          v3 = -2147467259;
        }
        if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
          goto LABEL_46;
        v4 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
        v5 = 0;
        if ( v3 >= 0 || !v4 )
          goto LABEL_8;
        LODWORD(lpThreadId) = v3;
        LODWORD(dwCreationFlags) = 474;
      }
    }
    else
    {
      *((_QWORD *)this + 84) = 0;
      v9 = GetLastError();
      v3 = v9;
      if ( v9 )
      {
        if ( v9 > 0 )
          v3 = (unsigned __int16)v9 | 0x80070000;
      }
      else
      {
        v3 = -2147467259;
      }
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
        goto LABEL_46;
      v4 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
      v5 = 0;
      if ( v3 >= 0 || !v4 )
        goto LABEL_8;
      LODWORD(lpThreadId) = v3;
      LODWORD(dwCreationFlags) = 471;
    }
LABEL_6:
    v6 = CDlpLogT<CEmptyType>::DlpLogFormat(
           v4,
           4,
           L"%s(%d): Result = 0x%X",
           L"CDlpManager::AsyncSerializeEnable",
           dwCreationFlags,
           lpThreadId,
           -2);
    v5 = v6;
    if ( v6 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v6);
    goto LABEL_8;
  }
  if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
  {
    v4 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
    v5 = 0;
    if ( v4 )
    {
      LODWORD(lpThreadId) = v3;
      LODWORD(dwCreationFlags) = 465;
      goto LABEL_6;
    }
LABEL_8:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  }
LABEL_46:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v3);
  LeaveCriticalSection(v2);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14002c6d0  mov     rax, rsp
0x14002c6d3  push    rsi
0x14002c6d4  push    rdi
0x14002c6d5  push    r14
0x14002c6d7  sub     rsp, 60h
0x14002c6db  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x14002c6e3  mov     [rax+10h], rbx
0x14002c6e7  mov     [rax+18h], rbp
0x14002c6eb  mov     rsi, rcx
0x14002c6ee  lea     rbp, [rcx+100h]
0x14002c6f5  mov     rcx, rbp; lpCriticalSection
0x14002c6f8  call    cs:__imp_EnterCriticalSection
0x14002c6ff  nop     dword ptr [rax+rax+00h]
0x14002c704  mov     [rsp+78h+var_30], 1
0x14002c70c  xor     r14d, r14d
0x14002c70f  mov     [rsp+78h+arg_0], r14d
0x14002c717  mov     edi, r14d
0x14002c71a  test    byte ptr [rsi+358h], 1
0x14002c721  jz      loc_14002CA12
0x14002c727  lea     rcx, [rsi+2F8h]; this
0x14002c72e  lea     rdx, [rsp+78h+arg_0]; unsigned int *
0x14002c736  call    ?Increment@CDword@@QEAAJPEAK@Z; CDword::Increment(ulong *)
0x14002c73b  mov     edi, eax
0x14002c73d  test    eax, eax
0x14002c73f  jns     short loc_14002C7B4
0x14002c741  mov     rdx, [rsi+50h]
0x14002c745  lea     rcx, [rsi+50h]
0x14002c749  mov     rax, [rdx+10h]
0x14002c74d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c752  test    rax, rax
0x14002c755  jz      loc_14002CA12
0x14002c75b  mov     rax, [rsi+50h]
0x14002c75f  lea     rcx, [rsi+50h]
0x14002c763  mov     rax, [rax+10h]
0x14002c767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c76c  mov     ebx, r14d
0x14002c76f  test    rax, rax
0x14002c772  jz      short loc_14002C7A8
0x14002c774  mov     dword ptr [rsp+78h+lpThreadId], edi
0x14002c778  mov     dword ptr [rsp+78h+dwCreationFlags], 1D1h
0x14002c780  lea     r9, aCdlpmanagerAsy; "CDlpManager::AsyncSerializeEnable"
0x14002c787  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x14002c78e  mov     edx, 4
0x14002c793  mov     rcx, rax
0x14002c796  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x14002c79b  test    eax, eax
0x14002c79d  mov     ebx, eax
0x14002c79f  jns     short loc_14002C7A8
0x14002c7a1  mov     ecx, eax
0x14002c7a3  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14002c7a8  mov     ecx, ebx
0x14002c7aa  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14002c7af  jmp     loc_14002CA12
0x14002c7b4  cmp     [rsp+78h+arg_0], 1
0x14002c7bc  jnz     loc_14002CA12
0x14002c7c2  xor     r9d, r9d; lpName
0x14002c7c5  xor     r8d, r8d; bInitialState
0x14002c7c8  xor     edx, edx; bManualReset
0x14002c7ca  xor     ecx, ecx; lpEventAttributes
0x14002c7cc  call    cs:__imp_CreateEventW
0x14002c7d3  nop     dword ptr [rax+rax+00h]
0x14002c7d8  mov     rbx, rax
0x14002c7db  mov     rcx, [rsi+2A0h]; hObject
0x14002c7e2  test    rcx, rcx
0x14002c7e5  jz      short loc_14002C7F3
0x14002c7e7  call    cs:__imp_CloseHandle
0x14002c7ee  nop     dword ptr [rax+rax+00h]
0x14002c7f3  test    rbx, rbx
0x14002c7f6  jnz     short loc_14002C873
0x14002c7f8  mov     [rsi+2A0h], r14
0x14002c7ff  call    cs:__imp_GetLastError
0x14002c806  nop     dword ptr [rax+rax+00h]
0x14002c80b  mov     edi, eax
0x14002c80d  test    eax, eax
0x14002c80f  jnz     short loc_14002C818
0x14002c811  mov     edi, 80004005h
0x14002c816  jmp     short loc_14002C823
0x14002c818  jle     short loc_14002C823
0x14002c81a  movzx   edi, ax
0x14002c81d  or      edi, 80070000h
0x14002c823  mov     rax, [rsi+50h]
0x14002c827  lea     rcx, [rsi+50h]
0x14002c82b  mov     rax, [rax+10h]
0x14002c82f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c834  test    rax, rax
0x14002c837  jz      loc_14002CA12
0x14002c83d  mov     rax, [rsi+50h]
0x14002c841  lea     rcx, [rsi+50h]
0x14002c845  mov     rax, [rax+10h]
0x14002c849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c84e  mov     ebx, r14d
0x14002c851  test    edi, edi
0x14002c853  jns     loc_14002C7A8
0x14002c859  test    rax, rax
0x14002c85c  jz      loc_14002C7A8
0x14002c862  mov     dword ptr [rsp+78h+lpThreadId], edi
0x14002c866  mov     dword ptr [rsp+78h+dwCreationFlags], 1D7h
0x14002c86e  jmp     loc_14002C780
0x14002c873  mov     [rsi+2A0h], rbx
0x14002c87a  xor     r9d, r9d; lpName
0x14002c87d  xor     r8d, r8d; bInitialState
0x14002c880  lea     edx, [r9+1]; bManualReset
0x14002c884  xor     ecx, ecx; lpEventAttributes
0x14002c886  call    cs:__imp_CreateEventW
0x14002c88d  nop     dword ptr [rax+rax+00h]
0x14002c892  mov     rbx, rax
0x14002c895  mov     rcx, [rsi+2A8h]; hObject
0x14002c89c  test    rcx, rcx
0x14002c89f  jz      short loc_14002C8AD
0x14002c8a1  call    cs:__imp_CloseHandle
0x14002c8a8  nop     dword ptr [rax+rax+00h]
0x14002c8ad  mov     [rsi+2A8h], rbx
0x14002c8b4  test    rbx, rbx
0x14002c8b7  jnz     short loc_14002C92D
0x14002c8b9  call    cs:__imp_GetLastError
0x14002c8c0  nop     dword ptr [rax+rax+00h]
0x14002c8c5  mov     edi, eax
0x14002c8c7  test    eax, eax
0x14002c8c9  jnz     short loc_14002C8D2
0x14002c8cb  mov     edi, 80004005h
0x14002c8d0  jmp     short loc_14002C8DD
0x14002c8d2  jle     short loc_14002C8DD
0x14002c8d4  movzx   edi, ax
0x14002c8d7  or      edi, 80070000h
0x14002c8dd  mov     rax, [rsi+50h]
0x14002c8e1  lea     rcx, [rsi+50h]
0x14002c8e5  mov     rax, [rax+10h]
0x14002c8e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c8ee  test    rax, rax
0x14002c8f1  jz      loc_14002CA12
0x14002c8f7  mov     rax, [rsi+50h]
0x14002c8fb  lea     rcx, [rsi+50h]
0x14002c8ff  mov     rax, [rax+10h]
0x14002c903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c908  mov     ebx, r14d
0x14002c90b  test    edi, edi
0x14002c90d  jns     loc_14002C7A8
0x14002c913  test    rax, rax
0x14002c916  jz      loc_14002C7A8
0x14002c91c  mov     dword ptr [rsp+78h+lpThreadId], edi
0x14002c920  mov     dword ptr [rsp+78h+dwCreationFlags], 1DAh
0x14002c928  jmp     loc_14002C780
0x14002c92d  lea     r9, [rsi+338h]; lpParameter
0x14002c934  mov     [r9], rsi
0x14002c937  mov     rax, [rsi+2A0h]
0x14002c93e  test    rax, rax
0x14002c941  cmovz   rax, r14
0x14002c945  mov     [rsi+340h], rax
0x14002c94c  mov     [rsi+348h], rbx
0x14002c953  mov     [rsp+78h+lpThreadId], r14; lpThreadId
0x14002c958  mov     dword ptr [rsp+78h+dwCreationFlags], r14d; dwCreationFlags
0x14002c95d  lea     r8, ?SerializeThreadProc@CDlpManager@@SAKPEAX@Z; lpStartAddress
0x14002c964  xor     edx, edx; dwStackSize
0x14002c966  xor     ecx, ecx; lpThreadAttributes
0x14002c968  call    cs:__imp_CreateThread
0x14002c96f  nop     dword ptr [rax+rax+00h]
0x14002c974  mov     rbx, rax
0x14002c977  mov     rcx, [rsi+2B0h]; hObject
0x14002c97e  test    rcx, rcx
0x14002c981  jz      short loc_14002C98F
0x14002c983  call    cs:__imp_CloseHandle
0x14002c98a  nop     dword ptr [rax+rax+00h]
0x14002c98f  test    rbx, rbx
0x14002c992  jnz     short loc_14002CA0B
0x14002c994  mov     [rsi+2B0h], r14
0x14002c99b  call    cs:__imp_GetLastError
0x14002c9a2  nop     dword ptr [rax+rax+00h]
0x14002c9a7  mov     edi, eax
0x14002c9a9  test    eax, eax
0x14002c9ab  jnz     short loc_14002C9B4
0x14002c9ad  mov     edi, 80004005h
0x14002c9b2  jmp     short loc_14002C9BF
0x14002c9b4  jle     short loc_14002C9BF
0x14002c9b6  movzx   edi, ax
0x14002c9b9  or      edi, 80070000h
0x14002c9bf  mov     rax, [rsi+50h]
0x14002c9c3  lea     rcx, [rsi+50h]
0x14002c9c7  mov     rax, [rax+10h]
0x14002c9cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c9d0  test    rax, rax
0x14002c9d3  jz      short loc_14002CA12
0x14002c9d5  mov     rax, [rsi+50h]
0x14002c9d9  lea     rcx, [rsi+50h]
0x14002c9dd  mov     rax, [rax+10h]
0x14002c9e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c9e6  mov     ebx, r14d
0x14002c9e9  test    edi, edi
0x14002c9eb  jns     loc_14002C7A8
0x14002c9f1  test    rax, rax
0x14002c9f4  jz      loc_14002C7A8
0x14002c9fa  mov     dword ptr [rsp+78h+lpThreadId], edi
0x14002c9fe  mov     dword ptr [rsp+78h+dwCreationFlags], 1E8h
0x14002ca06  jmp     loc_14002C780
0x14002ca0b  mov     [rsi+2B0h], rbx
0x14002ca12  mov     ecx, edi
0x14002ca14  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14002ca19  nop
0x14002ca1a  mov     eax, [rsp+78h+var_30]
0x14002ca1e  test    eax, eax
0x14002ca20  jz      short loc_14002CA36
0x14002ca22  mov     rcx, rbp; lpCriticalSection
0x14002ca25  call    cs:__imp_LeaveCriticalSection
0x14002ca2c  nop     dword ptr [rax+rax+00h]
0x14002ca31  mov     [rsp+78h+var_30], r14d
0x14002ca36  mov     eax, edi
0x14002ca38  lea     r11, [rsp+78h+var_18]
0x14002ca3d  mov     rbx, [r11+28h]
0x14002ca41  mov     rbp, [r11+30h]
0x14002ca45  mov     rsp, r11
0x14002ca48  pop     r14
0x14002ca4a  pop     rdi
0x14002ca4b  pop     rsi
0x14002ca4c  retn
```
