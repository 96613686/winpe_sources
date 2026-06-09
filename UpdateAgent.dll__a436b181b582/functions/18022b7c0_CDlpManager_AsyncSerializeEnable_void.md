# CDlpManager::AsyncSerializeEnable(void)

- ea: `0x18022b7c0`
- end: `0x18022bb3d`
- name: `?AsyncSerializeEnable@CDlpManager@@UEAAJXZ`
- size: `893`
- prototype: `__int64 __fastcall(CDlpManager *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800059d0`
- `0x180039f90`
- `0x180077664`
- `0x18022b7c0`
- `0x180233cf0`
- `0x18023f264`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18022b8b3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18022b96c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18022b8b3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18022b96c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18022bb10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18022bb10`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18022b7ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18022b7ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022b8e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022b99f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022ba87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022b8e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022b99f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022ba87`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18022ba54`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18022ba54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18022b8ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18022b987`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18022ba6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18022b8ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18022b987`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18022ba6f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpManager::AsyncSerializeEnable(CDlpManager *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  signed int v3; // edi
  __int64 v4; // rax
  __int64 v5; // rcx
  int v6; // eax
  __int64 v7; // rdx
  HANDLE EventW; // rbx
  void *v9; // rcx
  signed int LastError; // eax
  HANDLE v11; // rbx
  void *v12; // rcx
  signed int v13; // eax
  HANDLE Thread; // rbx
  void *v15; // rcx
  signed int v16; // eax
  __int64 dwCreationFlags; // [rsp+20h] [rbp-78h]
  LPDWORD lpThreadId; // [rsp+28h] [rbp-70h]
  unsigned int v20; // [rsp+30h] [rbp-68h] BYREF
  __int64 v21; // [rsp+38h] [rbp-60h]
  int v22; // [rsp+50h] [rbp-48h]

  v21 = -2;
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 256);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 256));
  v22 = 1;
  v20 = 0;
  v3 = 0;
  if ( (*((_BYTE *)this + 856) & 1) == 0 )
    goto LABEL_44;
  v3 = CDword::Increment((CDlpManager *)((char *)this + 760), &v20);
  if ( v3 < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
      goto LABEL_44;
    v4 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
    v5 = 0;
    if ( !v4 )
      goto LABEL_8;
    LODWORD(lpThreadId) = v3;
    LODWORD(dwCreationFlags) = 465;
    goto LABEL_6;
  }
  if ( v20 != 1 )
    goto LABEL_44;
  EventW = CreateEventW(0, 0, 0, 0);
  v9 = (void *)*((_QWORD *)this + 84);
  if ( v9 )
    CloseHandle(v9);
  if ( !EventW )
  {
    *((_QWORD *)this + 84) = 0;
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
    if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
    {
      v4 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
      v5 = 0;
      if ( v3 < 0 && v4 )
      {
        LODWORD(lpThreadId) = v3;
        LODWORD(dwCreationFlags) = 471;
        goto LABEL_6;
      }
LABEL_8:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
      goto LABEL_44;
    }
    goto LABEL_44;
  }
  *((_QWORD *)this + 84) = EventW;
  v11 = CreateEventW(0, 1, 0, 0);
  v12 = (void *)*((_QWORD *)this + 85);
  if ( v12 )
    CloseHandle(v12);
  if ( !v11 )
  {
    *((_QWORD *)this + 85) = 0;
    v13 = GetLastError();
    v3 = v13;
    if ( v13 )
    {
      if ( v13 > 0 )
        v3 = (unsigned __int16)v13 | 0x80070000;
    }
    else
    {
      v3 = -2147467259;
    }
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
      goto LABEL_44;
    v4 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
    v5 = 0;
    if ( v3 >= 0 || !v4 )
      goto LABEL_8;
    LODWORD(lpThreadId) = v3;
    LODWORD(dwCreationFlags) = 474;
LABEL_6:
    v6 = CDlpLogT<CEmptyType>::DlpLogFormat(
           v4,
           4,
           L"%s(%d): Result = 0x%X",
           L"CDlpManager::AsyncSerializeEnable",
           dwCreationFlags,
           lpThreadId);
    v5 = (unsigned int)v6;
    if ( v6 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v6, v7);
    goto LABEL_8;
  }
  *((_QWORD *)this + 85) = v11;
  *((_QWORD *)this + 103) = this;
  *((_QWORD *)this + 104) = *((_QWORD *)this + 84);
  *((_QWORD *)this + 105) = v11;
  Thread = CreateThread(0, 0, CDlpManager::SerializeThreadProc, (char *)this + 824, 0, 0);
  v15 = (void *)*((_QWORD *)this + 86);
  if ( v15 )
    CloseHandle(v15);
  if ( Thread )
  {
    *((_QWORD *)this + 86) = Thread;
    goto LABEL_44;
  }
  *((_QWORD *)this + 86) = 0;
  v16 = GetLastError();
  v3 = v16;
  if ( v16 )
  {
    if ( v16 > 0 )
      v3 = (unsigned __int16)v16 | 0x80070000;
  }
  else
  {
    v3 = -2147467259;
  }
  if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
  {
    v4 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
    v5 = 0;
    if ( v3 >= 0 || !v4 )
      goto LABEL_8;
    LODWORD(lpThreadId) = v3;
    LODWORD(dwCreationFlags) = 488;
    goto LABEL_6;
  }
LABEL_44:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v3);
  if ( v22 )
  {
    LeaveCriticalSection(v2);
    v22 = 0;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18022b7c0  push    rbx
0x18022b7c2  push    rbp
0x18022b7c3  push    rsi
0x18022b7c4  push    rdi
0x18022b7c5  sub     rsp, 78h
0x18022b7c9  mov     [rsp+98h+var_60], 0FFFFFFFFFFFFFFFEh
0x18022b7d2  mov     rax, cs:__security_cookie
0x18022b7d9  xor     rax, rsp
0x18022b7dc  mov     [rsp+98h+var_38], rax
0x18022b7e1  mov     rsi, rcx
0x18022b7e4  lea     rbp, [rcx+100h]
0x18022b7eb  mov     rcx, rbp; lpCriticalSection
0x18022b7ee  call    cs:__imp_EnterCriticalSection
0x18022b7f5  nop     dword ptr [rax+rax+00h]
0x18022b7fa  mov     [rsp+98h+var_48], 1
0x18022b802  mov     [rsp+98h+var_68], 0
0x18022b80a  xor     edi, edi
0x18022b80c  test    byte ptr [rsi+358h], 1
0x18022b813  jz      loc_18022BAFD
0x18022b819  lea     rcx, [rsi+2F8h]; this
0x18022b820  lea     rdx, [rsp+98h+var_68]; unsigned int *
0x18022b825  call    ?Increment@CDword@@QEAAJPEAK@Z; CDword::Increment(ulong *)
0x18022b82a  mov     edi, eax
0x18022b82c  test    eax, eax
0x18022b82e  jns     short loc_18022B89E
0x18022b830  mov     rdx, [rsi+50h]
0x18022b834  lea     rcx, [rsi+50h]
0x18022b838  mov     rax, [rdx+10h]
0x18022b83c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022b841  test    rax, rax
0x18022b844  jz      loc_18022BAFD
0x18022b84a  mov     rax, [rsi+50h]
0x18022b84e  lea     rcx, [rsi+50h]
0x18022b852  mov     rax, [rax+10h]
0x18022b856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022b85b  xor     ecx, ecx
0x18022b85d  test    rax, rax
0x18022b860  jz      short loc_18022B894
0x18022b862  mov     dword ptr [rsp+98h+lpThreadId], edi
0x18022b866  mov     dword ptr [rsp+98h+dwCreationFlags], 1D1h
0x18022b86e  lea     r9, aCdlpmanagerAsy; "CDlpManager::AsyncSerializeEnable"
0x18022b875  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18022b87c  mov     edx, 4
0x18022b881  mov     rcx, rax
0x18022b884  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18022b889  test    eax, eax
0x18022b88b  mov     ecx, eax
0x18022b88d  jns     short loc_18022B894
0x18022b88f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18022b894  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18022b899  jmp     loc_18022BAFD
0x18022b89e  cmp     [rsp+98h+var_68], 1
0x18022b8a3  jnz     loc_18022BAFD
0x18022b8a9  xor     r9d, r9d; lpName
0x18022b8ac  xor     r8d, r8d; bInitialState
0x18022b8af  xor     edx, edx; bManualReset
0x18022b8b1  xor     ecx, ecx; lpEventAttributes
0x18022b8b3  call    cs:__imp_CreateEventW
0x18022b8ba  nop     dword ptr [rax+rax+00h]
0x18022b8bf  mov     rbx, rax
0x18022b8c2  mov     rcx, [rsi+2A0h]; hObject
0x18022b8c9  test    rcx, rcx
0x18022b8cc  jz      short loc_18022B8DA
0x18022b8ce  call    cs:__imp_CloseHandle
0x18022b8d5  nop     dword ptr [rax+rax+00h]
0x18022b8da  test    rbx, rbx
0x18022b8dd  jnz     short loc_18022B959
0x18022b8df  mov     [rsi+2A0h], rbx
0x18022b8e6  call    cs:__imp_GetLastError
0x18022b8ed  nop     dword ptr [rax+rax+00h]
0x18022b8f2  mov     edi, eax
0x18022b8f4  test    eax, eax
0x18022b8f6  jnz     short loc_18022B8FF
0x18022b8f8  mov     edi, 80004005h
0x18022b8fd  jmp     short loc_18022B90A
0x18022b8ff  jle     short loc_18022B90A
0x18022b901  movzx   edi, ax
0x18022b904  or      edi, 80070000h
0x18022b90a  mov     rax, [rsi+50h]
0x18022b90e  lea     rcx, [rsi+50h]
0x18022b912  mov     rax, [rax+10h]
0x18022b916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022b91b  test    rax, rax
0x18022b91e  jz      loc_18022BAFD
0x18022b924  mov     rax, [rsi+50h]
0x18022b928  lea     rcx, [rsi+50h]
0x18022b92c  mov     rax, [rax+10h]
0x18022b930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022b935  xor     ecx, ecx
0x18022b937  test    edi, edi
0x18022b939  jns     loc_18022B894
0x18022b93f  test    rax, rax
0x18022b942  jz      loc_18022B894
0x18022b948  mov     dword ptr [rsp+98h+lpThreadId], edi
0x18022b94c  mov     dword ptr [rsp+98h+dwCreationFlags], 1D7h
0x18022b954  jmp     loc_18022B86E
0x18022b959  mov     [rsi+2A0h], rbx
0x18022b960  xor     r9d, r9d; lpName
0x18022b963  xor     r8d, r8d; bInitialState
0x18022b966  lea     edx, [r9+1]; bManualReset
0x18022b96a  xor     ecx, ecx; lpEventAttributes
0x18022b96c  call    cs:__imp_CreateEventW
0x18022b973  nop     dword ptr [rax+rax+00h]
0x18022b978  mov     rbx, rax
0x18022b97b  mov     rcx, [rsi+2A8h]; hObject
0x18022b982  test    rcx, rcx
0x18022b985  jz      short loc_18022B993
0x18022b987  call    cs:__imp_CloseHandle
0x18022b98e  nop     dword ptr [rax+rax+00h]
0x18022b993  test    rbx, rbx
0x18022b996  jnz     short loc_18022BA12
0x18022b998  mov     [rsi+2A8h], rbx
0x18022b99f  call    cs:__imp_GetLastError
0x18022b9a6  nop     dword ptr [rax+rax+00h]
0x18022b9ab  mov     edi, eax
0x18022b9ad  test    eax, eax
0x18022b9af  jnz     short loc_18022B9B8
0x18022b9b1  mov     edi, 80004005h
0x18022b9b6  jmp     short loc_18022B9C3
0x18022b9b8  jle     short loc_18022B9C3
0x18022b9ba  movzx   edi, ax
0x18022b9bd  or      edi, 80070000h
0x18022b9c3  mov     rax, [rsi+50h]
0x18022b9c7  lea     rcx, [rsi+50h]
0x18022b9cb  mov     rax, [rax+10h]
0x18022b9cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022b9d4  test    rax, rax
0x18022b9d7  jz      loc_18022BAFD
0x18022b9dd  mov     rax, [rsi+50h]
0x18022b9e1  lea     rcx, [rsi+50h]
0x18022b9e5  mov     rax, [rax+10h]
0x18022b9e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022b9ee  xor     ecx, ecx
0x18022b9f0  test    edi, edi
0x18022b9f2  jns     loc_18022B894
0x18022b9f8  test    rax, rax
0x18022b9fb  jz      loc_18022B894
0x18022ba01  mov     dword ptr [rsp+98h+lpThreadId], edi
0x18022ba05  mov     dword ptr [rsp+98h+dwCreationFlags], 1DAh
0x18022ba0d  jmp     loc_18022B86E
0x18022ba12  mov     [rsi+2A8h], rbx
0x18022ba19  lea     r9, [rsi+338h]; lpParameter
0x18022ba20  mov     [r9], rsi
0x18022ba23  mov     rax, [rsi+2A0h]
0x18022ba2a  mov     [rsi+340h], rax
0x18022ba31  mov     [rsi+348h], rbx
0x18022ba38  mov     [rsp+98h+lpThreadId], 0; lpThreadId
0x18022ba41  mov     dword ptr [rsp+98h+dwCreationFlags], 0; dwCreationFlags
0x18022ba49  lea     r8, ?SerializeThreadProc@CDlpManager@@SAKPEAX@Z; lpStartAddress
0x18022ba50  xor     edx, edx; dwStackSize
0x18022ba52  xor     ecx, ecx; lpThreadAttributes
0x18022ba54  call    cs:__imp_CreateThread
0x18022ba5b  nop     dword ptr [rax+rax+00h]
0x18022ba60  mov     rbx, rax
0x18022ba63  mov     rcx, [rsi+2B0h]; hObject
0x18022ba6a  test    rcx, rcx
0x18022ba6d  jz      short loc_18022BA7B
0x18022ba6f  call    cs:__imp_CloseHandle
0x18022ba76  nop     dword ptr [rax+rax+00h]
0x18022ba7b  test    rbx, rbx
0x18022ba7e  jnz     short loc_18022BAF6
0x18022ba80  mov     [rsi+2B0h], rbx
0x18022ba87  call    cs:__imp_GetLastError
0x18022ba8e  nop     dword ptr [rax+rax+00h]
0x18022ba93  mov     edi, eax
0x18022ba95  test    eax, eax
0x18022ba97  jnz     short loc_18022BAA0
0x18022ba99  mov     edi, 80004005h
0x18022ba9e  jmp     short loc_18022BAAB
0x18022baa0  jle     short loc_18022BAAB
0x18022baa2  movzx   edi, ax
0x18022baa5  or      edi, 80070000h
0x18022baab  mov     rax, [rsi+50h]
0x18022baaf  lea     rcx, [rsi+50h]
0x18022bab3  mov     rax, [rax+10h]
0x18022bab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022babc  test    rax, rax
0x18022babf  jz      short loc_18022BAFD
0x18022bac1  mov     rax, [rsi+50h]
0x18022bac5  lea     rcx, [rsi+50h]
0x18022bac9  mov     rax, [rax+10h]
0x18022bacd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022bad2  xor     ecx, ecx
0x18022bad4  test    edi, edi
0x18022bad6  jns     loc_18022B894
0x18022badc  test    rax, rax
0x18022badf  jz      loc_18022B894
0x18022bae5  mov     dword ptr [rsp+98h+lpThreadId], edi
0x18022bae9  mov     dword ptr [rsp+98h+dwCreationFlags], 1E8h
0x18022baf1  jmp     loc_18022B86E
0x18022baf6  mov     [rsi+2B0h], rbx
0x18022bafd  mov     ecx, edi
0x18022baff  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18022bb04  nop
0x18022bb05  mov     eax, [rsp+98h+var_48]
0x18022bb09  test    eax, eax
0x18022bb0b  jz      short loc_18022BB24
0x18022bb0d  mov     rcx, rbp; lpCriticalSection
0x18022bb10  call    cs:__imp_LeaveCriticalSection
0x18022bb17  nop     dword ptr [rax+rax+00h]
0x18022bb1c  mov     [rsp+98h+var_48], 0
0x18022bb24  mov     eax, edi
0x18022bb26  mov     rcx, [rsp+98h+var_38]
0x18022bb2b  xor     rcx, rsp; StackCookie
0x18022bb2e  call    __security_check_cookie
0x18022bb33  add     rsp, 78h
0x18022bb37  pop     rdi
0x18022bb38  pop     rsi
0x18022bb39  pop     rbp
0x18022bb3a  pop     rbx
0x18022bb3b  retn
```
