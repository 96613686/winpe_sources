# SendControlToService(SC_HANDLE__ *,ulong,ulong *)

- ea: `0x18002d974`
- end: `0x18002da93`
- name: `?SendControlToService@@YAJPEAUSC_HANDLE__@@KPEAK@Z`
- size: `287`
- prototype: `__int64 __fastcall(struct SC_HANDLE__ *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x18002dc60`

## callees

- `0x180001044`
- `0x180001084`
- `0x18002d974`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002da68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002da68`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002da0e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002da0e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002d9fa`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002d9fa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002d9d2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002da3f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002d9d2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002da3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002da24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002da24`

## pseudocode

```c
__int64 __fastcall SendControlToService(struct SC_HANDLE__ *a1, __int64 a2, unsigned int *a3)
{
  DWORD v6; // r14d
  volatile signed __int32 *v7; // rax
  volatile signed __int32 *v8; // rdi
  DWORD TickCount; // ebp
  HANDLE v10; // rax
  void *v11; // r15
  unsigned int v12; // ebx
  DWORD v13; // eax
  signed int LastError; // eax
  DWORD ThreadId; // [rsp+78h] [rbp+10h] BYREF

  ThreadId = 0;
  if ( !a3 )
    return 2147942487LL;
  v6 = *a3;
  v7 = (volatile signed __int32 *)operator new(0x18u);
  v8 = v7;
  if ( v7 )
  {
    *((_DWORD *)v7 + 1) = 2;
    *((_DWORD *)v7 + 2) = 1;
    *((_QWORD *)v7 + 2) = a1;
    *v7 = 0;
    TickCount = GetTickCount();
    v10 = CreateThread(0, 0, ControlServiceThread, (LPVOID)v8, 0, &ThreadId);
    v11 = v10;
    if ( v10 )
    {
      if ( WaitForSingleObject(v10, v6) )
        v12 = -2147023843;
      else
        v12 = *v8;
      CloseHandle(v11);
      if ( _InterlockedExchangeAdd(v8 + 1, 0xFFFFFFFF) == 1 )
        operator delete((void *)v8);
      v13 = GetTickCount();
      if ( v13 > TickCount )
      {
        if ( v13 - TickCount > v6 )
          *a3 = 0;
        else
          *a3 += TickCount - v13;
      }
    }
    else
    {
      operator delete((void *)v8);
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    return (unsigned int)-2147024888;
  }
  return v12;
}

```

## disassembly

```asm
0x18002d974  mov     [rsp+ThreadId], edx
0x18002d978  push    rbx
0x18002d979  push    rbp
0x18002d97a  push    rsi
0x18002d97b  push    rdi
0x18002d97c  push    r14
0x18002d97e  push    r15
0x18002d980  sub     rsp, 38h
0x18002d984  mov     [rsp+68h+ThreadId], 0
0x18002d98c  mov     rsi, r8
0x18002d98f  mov     rbx, rcx
0x18002d992  test    r8, r8
0x18002d995  jnz     short loc_18002D9A1
0x18002d997  mov     eax, 80070057h
0x18002d99c  jmp     loc_18002DA86
0x18002d9a1  mov     r14d, [r8]
0x18002d9a4  mov     ecx, 18h; Size
0x18002d9a9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002d9ae  mov     rdi, rax
0x18002d9b1  test    rax, rax
0x18002d9b4  jz      loc_18002DA7F
0x18002d9ba  mov     dword ptr [rax+4], 2
0x18002d9c1  mov     dword ptr [rax+8], 1
0x18002d9c8  mov     [rax+10h], rbx
0x18002d9cc  mov     dword ptr [rax], 0
0x18002d9d2  call    cs:__imp_GetTickCount
0x18002d9d8  mov     r9, rdi; lpParameter
0x18002d9db  lea     r8, ?ControlServiceThread@@YAKPEAX@Z; lpStartAddress
0x18002d9e2  mov     ebp, eax
0x18002d9e4  xor     edx, edx; dwStackSize
0x18002d9e6  lea     rax, [rsp+68h+ThreadId]
0x18002d9eb  xor     ecx, ecx; lpThreadAttributes
0x18002d9ed  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x18002d9f2  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x18002d9fa  call    cs:__imp_CreateThread
0x18002da00  mov     r15, rax
0x18002da03  test    rax, rax
0x18002da06  jz      short loc_18002DA60
0x18002da08  mov     edx, r14d; dwMilliseconds
0x18002da0b  mov     rcx, rax; hHandle
0x18002da0e  call    cs:__imp_WaitForSingleObject
0x18002da14  test    eax, eax
0x18002da16  jnz     short loc_18002DA1C
0x18002da18  mov     ebx, [rdi]
0x18002da1a  jmp     short loc_18002DA21
0x18002da1c  mov     ebx, 8007041Dh
0x18002da21  mov     rcx, r15; hObject
0x18002da24  call    cs:__imp_CloseHandle
0x18002da2a  or      eax, 0FFFFFFFFh
0x18002da2d  lock xadd [rdi+4], eax
0x18002da32  cmp     eax, 1
0x18002da35  jnz     short loc_18002DA3F
0x18002da37  mov     rcx, rdi; Block
0x18002da3a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002da3f  call    cs:__imp_GetTickCount
0x18002da45  cmp     eax, ebp
0x18002da47  jbe     short loc_18002DA84
0x18002da49  mov     ecx, eax
0x18002da4b  sub     ecx, ebp
0x18002da4d  cmp     ecx, r14d
0x18002da50  ja      short loc_18002DA58
0x18002da52  sub     ebp, eax
0x18002da54  add     [rsi], ebp
0x18002da56  jmp     short loc_18002DA84
0x18002da58  mov     dword ptr [rsi], 0
0x18002da5e  jmp     short loc_18002DA84
0x18002da60  mov     rcx, rdi; Block
0x18002da63  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002da68  call    cs:__imp_GetLastError
0x18002da6e  mov     ebx, eax
0x18002da70  test    eax, eax
0x18002da72  jle     short loc_18002DA84
0x18002da74  movzx   ebx, ax
0x18002da77  or      ebx, 80070000h
0x18002da7d  jmp     short loc_18002DA84
0x18002da7f  mov     ebx, 80070008h
0x18002da84  mov     eax, ebx
0x18002da86  add     rsp, 38h
0x18002da8a  pop     r15
0x18002da8c  pop     r14
0x18002da8e  pop     rdi
0x18002da8f  pop     rsi
0x18002da90  pop     rbp
0x18002da91  pop     rbx
0x18002da92  retn
```
