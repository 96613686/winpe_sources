# WaasMedic::MiscUtil::SetBelowNormalPriorityState(void *)

- ea: `0x18002b42c`
- end: `0x18002b536`
- name: `?SetBelowNormalPriorityState@MiscUtil@WaasMedic@@SAJPEAX@Z`
- size: `266`
- prototype: `__int64 __fastcall(HANDLE ThreadHandle)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180015c90`
- `0x1800487ec`
- `0x180067bb0`

## callees

- `0x18002a7b4`
- `0x18002b42c`
- `0x18002e81c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b477`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b4bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b477`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b4bd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18002b46d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18002b46d`
- `ntdll!NtSetInformationThread` at `0x18002b4fd`
- `ntdll!NtSetInformationThread` at `0x18002b4fd`
- `api-ms-win-core-processthreads-l1-1-2!SetThreadInformation` at `0x18002b4b3`
- `api-ms-win-core-processthreads-l1-1-2!SetThreadInformation` at `0x18002b4b3`

## string_xrefs

- `0x18002b490`: `Attempt to move thread to CPU priority %d failed with GetLastError=0x%08x`
- `0x18002b43f`: `SetBelowNormalPriorityState was passed invalid thread handle. Will not attempt to adjust priority.`
- `0x18002b513`: `Attempt to move thread to IO priority %d failed with hr=0x%08x`
- `0x18002b4d7`: `Attempt to move thread to memory priority %d failed with GetLastError=0x%08x`

## pseudocode

```c
__int64 __fastcall WaasMedic::MiscUtil::SetBelowNormalPriorityState(HANDLE ThreadHandle)
{
  __int64 v3; // rbx
  signed int LastError; // eax
  signed int v5; // eax
  NTSTATUS v6; // eax
  unsigned int v7; // [rsp+30h] [rbp+8h] BYREF
  unsigned int ThreadInformation; // [rsp+38h] [rbp+10h] BYREF

  if ( ThreadHandle == (HANDLE)-1LL )
  {
    LogLevelW(3u, L"SetBelowNormalPriorityState was passed invalid thread handle. Will not attempt to adjust priority.");
    return 2147942487LL;
  }
  else
  {
    v7 = 4;
    LODWORD(v3) = 0;
    ThreadInformation = 1;
    if ( !SetThreadPriority(ThreadHandle, -1) )
    {
      LastError = GetLastError();
      LODWORD(v3) = LastError;
      if ( LastError > 0 )
        LODWORD(v3) = (unsigned __int16)LastError | 0x80070000;
      LogLevelW(
        3u,
        L"Attempt to move thread to CPU priority %d failed with GetLastError=0x%08x",
        0xFFFFFFFFLL,
        (unsigned int)v3);
    }
    if ( !(unsigned int)SetThreadInformation(ThreadHandle, 0, &v7, 4) )
    {
      v5 = GetLastError();
      LODWORD(v3) = v5;
      if ( v5 > 0 )
        LODWORD(v3) = (unsigned __int16)v5 | 0x80070000;
      LogLevelW(
        3u,
        L"Attempt to move thread to memory priority %d failed with GetLastError=0x%08x",
        v7,
        (unsigned int)v3);
    }
    v6 = NtSetInformationThread(ThreadHandle, ThreadIoPriority, &ThreadInformation, 4u);
    if ( v6 < 0 )
    {
      v3 = (unsigned int)WaasMedic::MiscUtil::HRESULT_FROM_NTSTATUS(v6);
      LogLevelW(3u, L"Attempt to move thread to IO priority %d failed with hr=0x%08x", ThreadInformation, v3);
    }
    return (unsigned int)v3;
  }
}

```

## disassembly

```asm
0x18002b42c  mov     [rsp+arg_10], rbx
0x18002b431  push    rsi
0x18002b432  sub     rsp, 20h
0x18002b436  mov     rsi, rcx
0x18002b439  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002b43d  jnz     short loc_18002B458
0x18002b43f  lea     rdx, aSetbelownormal; "SetBelowNormalPriorityState was passed "...
0x18002b446  lea     ecx, [rsi+4]; unsigned __int8
0x18002b449  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002b44e  mov     eax, 80070057h
0x18002b453  jmp     loc_18002B52B
0x18002b458  or      edx, 0FFFFFFFFh; nPriority
0x18002b45b  mov     [rsp+28h+arg_0], 4
0x18002b463  xor     ebx, ebx
0x18002b465  mov     [rsp+28h+ThreadInformation], 1
0x18002b46d  call    cs:__imp_SetThreadPriority
0x18002b473  test    eax, eax
0x18002b475  jnz     short loc_18002B4A3
0x18002b477  call    cs:__imp_GetLastError
0x18002b47d  mov     ebx, eax
0x18002b47f  test    eax, eax
0x18002b481  jle     short loc_18002B48C
0x18002b483  movzx   ebx, ax
0x18002b486  or      ebx, 80070000h
0x18002b48c  or      r8d, 0FFFFFFFFh
0x18002b490  lea     rdx, aAttemptToMoveT_0; "Attempt to move thread to CPU priority "...
0x18002b497  mov     r9d, ebx
0x18002b49a  lea     ecx, [r8+4]; unsigned __int8
0x18002b49e  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002b4a3  mov     r9d, 4
0x18002b4a9  lea     r8, [rsp+28h+arg_0]
0x18002b4ae  xor     edx, edx
0x18002b4b0  mov     rcx, rsi
0x18002b4b3  call    cs:__imp_SetThreadInformation
0x18002b4b9  test    eax, eax
0x18002b4bb  jnz     short loc_18002B4EB
0x18002b4bd  call    cs:__imp_GetLastError
0x18002b4c3  mov     ebx, eax
0x18002b4c5  test    eax, eax
0x18002b4c7  jle     short loc_18002B4D2
0x18002b4c9  movzx   ebx, ax
0x18002b4cc  or      ebx, 80070000h
0x18002b4d2  mov     r8d, [rsp+28h+arg_0]
0x18002b4d7  lea     rdx, aAttemptToMoveT_1; "Attempt to move thread to memory priori"...
0x18002b4de  mov     r9d, ebx
0x18002b4e1  mov     ecx, 3; unsigned __int8
0x18002b4e6  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002b4eb  mov     r9d, 4; ThreadInformationLength
0x18002b4f1  lea     r8, [rsp+28h+ThreadInformation]; ThreadInformation
0x18002b4f6  mov     rcx, rsi; ThreadHandle
0x18002b4f9  lea     edx, [r9+12h]; ThreadInformationClass
0x18002b4fd  call    cs:__imp_NtSetInformationThread
0x18002b503  test    eax, eax
0x18002b505  jns     short loc_18002B529
0x18002b507  mov     ecx, eax; int
0x18002b509  call    ?HRESULT_FROM_NTSTATUS@MiscUtil@WaasMedic@@SAJJ@Z; WaasMedic::MiscUtil::HRESULT_FROM_NTSTATUS(long)
0x18002b50e  mov     r8d, [rsp+28h+ThreadInformation]
0x18002b513  lea     rdx, aAttemptToMoveT; "Attempt to move thread to IO priority %"...
0x18002b51a  mov     r9d, eax
0x18002b51d  mov     ecx, 3; unsigned __int8
0x18002b522  mov     ebx, eax
0x18002b524  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002b529  mov     eax, ebx
0x18002b52b  mov     rbx, [rsp+28h+arg_10]
0x18002b530  add     rsp, 20h
0x18002b534  pop     rsi
0x18002b535  retn
```
