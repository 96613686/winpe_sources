# CViperReqManager::UnInit(void)

- ea: `0x180062c40`
- end: `0x180062d0d`
- name: `?UnInit@CViperReqManager@@QEAAJXZ`
- size: `205`
- prototype: `__int64 __fastcall(CViperReqManager *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003db14`

## callees

- `0x180062c40`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180062c82`
- `KERNEL32!WaitForSingleObject` at `0x180062c82`
- `KERNEL32!CloseHandle` at `0x180062ca9`
- `KERNEL32!CloseHandle` at `0x180062cf4`
- `KERNEL32!CloseHandle` at `0x180062ca9`
- `KERNEL32!CloseHandle` at `0x180062cf4`
- `KERNEL32!SetEvent` at `0x180062c72`
- `KERNEL32!SetEvent` at `0x180062c72`
- `KERNEL32!DeleteCriticalSection` at `0x180062ccb`
- `KERNEL32!DeleteCriticalSection` at `0x180062ce2`
- `KERNEL32!DeleteCriticalSection` at `0x180062ccb`
- `KERNEL32!DeleteCriticalSection` at `0x180062ce2`
- `KERNEL32!GetLastError` at `0x180062c8d`
- `KERNEL32!GetLastError` at `0x180062c8d`

## pseudocode

```c
__int64 __fastcall CViperReqManager::UnInit(CViperReqManager *this)
{
  char v2; // al
  unsigned int v3; // ebx
  signed int LastError; // eax

  if ( (dword_18007D2BC & 8) != 0 )
    return 0;
  v2 = dword_18007D2BC | 4;
  v3 = 0;
  dword_18007D2BC |= 4u;
  if ( qword_18007D320 )
  {
    SetEvent(hEvent);
    if ( WaitForSingleObject(qword_18007D320, 0xFFFFFFFF) == -1 )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    CloseHandle(qword_18007D320);
    v2 = dword_18007D2BC;
    qword_18007D320 = 0;
  }
  if ( (v2 & 1) != 0 )
  {
    DeleteCriticalSection(&stru_18007D2C0);
    v2 = dword_18007D2BC;
  }
  if ( (v2 & 2) != 0 )
    DeleteCriticalSection(&stru_18007D2E8);
  if ( hEvent )
    CloseHandle(hEvent);
  hEvent = 0;
  return v3;
}

```

## disassembly

```asm
0x180062c40  push    rbx
0x180062c42  sub     rsp, 20h
0x180062c46  mov     eax, cs:dword_18007D2BC
0x180062c4c  test    al, 8
0x180062c4e  jz      short loc_180062C57
0x180062c50  xor     eax, eax
0x180062c52  jmp     loc_180062D07
0x180062c57  or      eax, 4
0x180062c5a  xor     ebx, ebx
0x180062c5c  cmp     cs:qword_18007D320, rbx
0x180062c63  mov     cs:dword_18007D2BC, eax
0x180062c69  jz      short loc_180062CC0
0x180062c6b  mov     rcx, cs:hEvent; hEvent
0x180062c72  call    cs:__imp_SetEvent
0x180062c78  mov     rcx, cs:qword_18007D320; hHandle
0x180062c7f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180062c82  call    cs:__imp_WaitForSingleObject
0x180062c88  cmp     eax, 0FFFFFFFFh
0x180062c8b  jnz     short loc_180062CA2
0x180062c8d  call    cs:__imp_GetLastError
0x180062c93  mov     ebx, eax
0x180062c95  test    eax, eax
0x180062c97  jle     short loc_180062CA2
0x180062c99  movzx   ebx, ax
0x180062c9c  or      ebx, 80070000h
0x180062ca2  mov     rcx, cs:qword_18007D320; hObject
0x180062ca9  call    cs:__imp_CloseHandle
0x180062caf  mov     eax, cs:dword_18007D2BC
0x180062cb5  mov     cs:qword_18007D320, 0
0x180062cc0  test    al, 1
0x180062cc2  jz      short loc_180062CD7
0x180062cc4  lea     rcx, stru_18007D2C0; lpCriticalSection
0x180062ccb  call    cs:__imp_DeleteCriticalSection
0x180062cd1  mov     eax, cs:dword_18007D2BC
0x180062cd7  test    al, 2
0x180062cd9  jz      short loc_180062CE8
0x180062cdb  lea     rcx, stru_18007D2E8; lpCriticalSection
0x180062ce2  call    cs:__imp_DeleteCriticalSection
0x180062ce8  mov     rcx, cs:hEvent; hObject
0x180062cef  test    rcx, rcx
0x180062cf2  jz      short loc_180062CFA
0x180062cf4  call    cs:__imp_CloseHandle
0x180062cfa  mov     cs:hEvent, 0
0x180062d05  mov     eax, ebx
0x180062d07  add     rsp, 20h
0x180062d0b  pop     rbx
0x180062d0c  retn
```
