# WinMain_CompileHealth_CreateEventIfPrimary

- ea: `0x1400029a4`
- end: `0x140002aae`
- name: `WinMain_CompileHealth_CreateEventIfPrimary`
- size: `266`
- prototype: `__int64 __fastcall(HANDLE hMutex, __int64, _QWORD *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140002868`

## callees

- `0x1400029a4`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x140002a5f`
- `KERNEL32!ReleaseMutex` at `0x140002a5f`
- `KERNEL32!CloseHandle` at `0x140002a46`
- `KERNEL32!CloseHandle` at `0x140002a84`
- `KERNEL32!CloseHandle` at `0x140002a46`
- `KERNEL32!CloseHandle` at `0x140002a84`
- `KERNEL32!SetEvent` at `0x140002a35`
- `KERNEL32!SetEvent` at `0x140002a35`
- `KERNEL32!CreateEventExW` at `0x140002a02`
- `KERNEL32!CreateEventExW` at `0x140002a02`
- `KERNEL32!SetLastError` at `0x1400029e8`
- `KERNEL32!SetLastError` at `0x140002a97`
- `KERNEL32!SetLastError` at `0x1400029e8`
- `KERNEL32!SetLastError` at `0x140002a97`
- `KERNEL32!WaitForSingleObjectEx` at `0x1400029c4`
- `KERNEL32!WaitForSingleObjectEx` at `0x1400029c4`
- `KERNEL32!GetLastError` at `0x1400029d0`
- `KERNEL32!GetLastError` at `0x140002a14`
- `KERNEL32!GetLastError` at `0x140002a1c`
- `KERNEL32!GetLastError` at `0x140002a52`
- `KERNEL32!GetLastError` at `0x140002a6c`
- `KERNEL32!GetLastError` at `0x1400029d0`
- `KERNEL32!GetLastError` at `0x140002a14`
- `KERNEL32!GetLastError` at `0x140002a1c`
- `KERNEL32!GetLastError` at `0x140002a52`
- `KERNEL32!GetLastError` at `0x140002a6c`

## pseudocode

```c
__int64 __fastcall WinMain_CompileHealth_CreateEventIfPrimary(HANDLE hMutex, __int64 a2, _QWORD *a3, int *a4)
{
  DWORD v7; // eax
  unsigned int v8; // ebx
  DWORD LastError; // esi
  HANDLE Event; // rdi
  int v11; // ebp
  DWORD v12; // eax
  BOOL v13; // r14d

  v7 = WaitForSingleObjectEx(hMutex, 0xFFFFFFFF, 0);
  if ( v7 == -1 )
  {
    v8 = 0;
LABEL_3:
    LastError = GetLastError();
LABEL_18:
    v11 = 0;
    Event = 0;
    goto LABEL_19;
  }
  if ( v7 )
  {
    v8 = 0;
    SetLastError(0x54Fu);
    goto LABEL_3;
  }
  Event = CreateEventExW(0, L"Global\\SpaceWorker_Event", 0, 0x1F0003u);
  if ( Event )
  {
    if ( GetLastError() == 183 )
    {
      v8 = SetEvent(Event);
      if ( !v8 )
      {
        v12 = GetLastError();
        v11 = 0;
        goto LABEL_14;
      }
      v11 = 0;
      v8 = CloseHandle(Event);
      Event = 0;
    }
    else
    {
      v8 = 1;
      v11 = 1;
    }
  }
  else
  {
    v11 = 0;
    v8 = 0;
  }
  v12 = GetLastError();
LABEL_14:
  LastError = v12;
  v13 = ReleaseMutex(hMutex);
  if ( !v8 || (v8 = v13, LastError = GetLastError(), !v13) )
  {
    if ( Event )
      CloseHandle(Event);
    goto LABEL_18;
  }
LABEL_19:
  *a3 = Event;
  *a4 = v11;
  SetLastError(LastError);
  return v8;
}

```

## disassembly

```asm
0x1400029a4  push    rbx
0x1400029a6  push    rbp
0x1400029a7  push    rsi
0x1400029a8  push    rdi
0x1400029a9  push    r12
0x1400029ab  push    r14
0x1400029ad  push    r15
0x1400029af  sub     rsp, 20h
0x1400029b3  mov     r12, r8
0x1400029b6  or      ebx, 0FFFFFFFFh
0x1400029b9  mov     edx, ebx; dwMilliseconds
0x1400029bb  xor     r8d, r8d; bAlertable
0x1400029be  mov     r15, r9
0x1400029c1  mov     r14, rcx
0x1400029c4  call    cs:__imp_WaitForSingleObjectEx
0x1400029ca  cmp     eax, ebx
0x1400029cc  jnz     short loc_1400029DD
0x1400029ce  xor     ebx, ebx
0x1400029d0  call    cs:__imp_GetLastError
0x1400029d6  mov     esi, eax
0x1400029d8  jmp     loc_140002A8A
0x1400029dd  test    eax, eax
0x1400029df  jz      short loc_1400029F0
0x1400029e1  xor     ebx, ebx
0x1400029e3  mov     ecx, 54Fh; dwErrCode
0x1400029e8  call    cs:__imp_SetLastError
0x1400029ee  jmp     short loc_1400029D0
0x1400029f0  mov     r9d, 1F0003h; dwDesiredAccess
0x1400029f6  lea     rdx, aGlobalSpacewor; "Global\\SpaceWorker_Event"
0x1400029fd  xor     r8d, r8d; dwFlags
0x140002a00  xor     ecx, ecx; lpEventAttributes
0x140002a02  call    cs:__imp_CreateEventExW
0x140002a08  mov     rdi, rax
0x140002a0b  test    rax, rax
0x140002a0e  jnz     short loc_140002A1C
0x140002a10  xor     ebp, ebp
0x140002a12  xor     ebx, ebx
0x140002a14  call    cs:__imp_GetLastError
0x140002a1a  jmp     short loc_140002A5A
0x140002a1c  call    cs:__imp_GetLastError
0x140002a22  cmp     eax, 0B7h
0x140002a27  jz      short loc_140002A32
0x140002a29  mov     ebx, 1
0x140002a2e  mov     ebp, ebx
0x140002a30  jmp     short loc_140002A14
0x140002a32  mov     rcx, rdi; hEvent
0x140002a35  call    cs:__imp_SetEvent
0x140002a3b  mov     ebx, eax
0x140002a3d  test    eax, eax
0x140002a3f  jz      short loc_140002A52
0x140002a41  mov     rcx, rdi; hObject
0x140002a44  xor     ebp, ebp
0x140002a46  call    cs:__imp_CloseHandle
0x140002a4c  mov     ebx, eax
0x140002a4e  xor     edi, edi
0x140002a50  jmp     short loc_140002A14
0x140002a52  call    cs:__imp_GetLastError
0x140002a58  xor     ebp, ebp
0x140002a5a  mov     rcx, r14; hMutex
0x140002a5d  mov     esi, eax
0x140002a5f  call    cs:__imp_ReleaseMutex
0x140002a65  mov     r14d, eax
0x140002a68  test    ebx, ebx
0x140002a6a  jz      short loc_140002A7C
0x140002a6c  call    cs:__imp_GetLastError
0x140002a72  mov     ebx, r14d
0x140002a75  mov     esi, eax
0x140002a77  test    r14d, r14d
0x140002a7a  jnz     short loc_140002A8E
0x140002a7c  test    rdi, rdi
0x140002a7f  jz      short loc_140002A8A
0x140002a81  mov     rcx, rdi; hObject
0x140002a84  call    cs:__imp_CloseHandle
0x140002a8a  xor     ebp, ebp
0x140002a8c  xor     edi, edi
0x140002a8e  mov     [r12], rdi
0x140002a92  mov     ecx, esi; dwErrCode
0x140002a94  mov     [r15], ebp
0x140002a97  call    cs:__imp_SetLastError
0x140002a9d  mov     eax, ebx
0x140002a9f  add     rsp, 20h
0x140002aa3  pop     r15
0x140002aa5  pop     r14
0x140002aa7  pop     r12
0x140002aa9  pop     rdi
0x140002aaa  pop     rsi
0x140002aab  pop     rbp
0x140002aac  pop     rbx
0x140002aad  retn
```
