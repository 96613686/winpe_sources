# CThreadChasing::Init(void)

- ea: `0x14001c7f8`
- end: `0x14001c901`
- name: `?Init@CThreadChasing@@QEAAJXZ`
- size: `265`
- prototype: `__int64 __fastcall(CThreadChasing *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140026410`
- `0x1400280fc`
- `0x140028378`

## callees

- `0x140014474`
- `0x14001c7f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001c80d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001c894`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001c80d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001c894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c838`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c8bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c838`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c8bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001c825`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001c8ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001c825`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001c8ac`

## pseudocode

```c
__int64 __fastcall CThreadChasing::Init(CThreadChasing *this)
{
  HANDLE EventW; // rax
  void *v3; // rcx
  signed int LastError; // eax
  unsigned int v5; // ebx
  CUserModeHangReport *v6; // rcx
  __int64 v7; // rdx
  HANDLE v8; // rax
  void *v9; // rcx
  signed int v10; // eax

  EventW = CreateEventW(0, 1, 0, 0);
  v3 = (void *)*((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = EventW;
  if ( (unsigned __int64)v3 + 1 > 1 )
    CloseHandle(v3);
  if ( *((_QWORD *)this + 1) == -1 || *((_QWORD *)this + 1) == 0 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 14;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids, v5);
    }
  }
  else
  {
    v8 = CreateEventW(0, 1, 0, 0);
    v9 = (void *)*((_QWORD *)this + 2);
    *((_QWORD *)this + 2) = v8;
    if ( (unsigned __int64)v9 + 1 > 1 )
      CloseHandle(v9);
    if ( *((_QWORD *)this + 2) != -1 && *((_QWORD *)this + 2) != 0 )
      return 0;
    v10 = GetLastError();
    v5 = v10;
    if ( v10 > 0 )
      v5 = (unsigned __int16)v10 | 0x80070000;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 15;
      goto LABEL_9;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x14001c7f8  push    rbx
0x14001c7fa  sub     rsp, 20h
0x14001c7fe  xor     r9d, r9d; lpName
0x14001c801  mov     rbx, rcx
0x14001c804  xor     r8d, r8d; bInitialState
0x14001c807  xor     ecx, ecx; lpEventAttributes
0x14001c809  lea     edx, [r9+1]; bManualReset
0x14001c80d  call    cs:__imp_CreateEventW
0x14001c813  mov     rcx, [rbx+8]; hObject
0x14001c817  mov     [rbx+8], rax
0x14001c81b  lea     rax, [rcx+1]
0x14001c81f  cmp     rax, 1
0x14001c823  jbe     short loc_14001C82B
0x14001c825  call    cs:__imp_CloseHandle
0x14001c82b  mov     rax, [rbx+8]
0x14001c82f  inc     rax
0x14001c832  cmp     rax, 1
0x14001c836  ja      short loc_14001C888
0x14001c838  call    cs:__imp_GetLastError
0x14001c83e  mov     ebx, eax
0x14001c840  test    eax, eax
0x14001c842  jle     short loc_14001C84D
0x14001c844  movzx   ebx, ax
0x14001c847  or      ebx, 80070000h
0x14001c84d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c854  lea     rax, WPP_GLOBAL_Control
0x14001c85b  cmp     rcx, rax
0x14001c85e  jz      loc_14001C8F9
0x14001c864  test    byte ptr [rcx+1Ch], 1
0x14001c868  jz      loc_14001C8F9
0x14001c86e  mov     edx, 0Eh
0x14001c873  mov     rcx, [rcx+10h]
0x14001c877  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001c87e  mov     r9d, ebx
0x14001c881  call    WPP_SF_d
0x14001c886  jmp     short loc_14001C8F9
0x14001c888  xor     r9d, r9d; lpName
0x14001c88b  xor     r8d, r8d; bInitialState
0x14001c88e  xor     ecx, ecx; lpEventAttributes
0x14001c890  lea     edx, [r9+1]; bManualReset
0x14001c894  call    cs:__imp_CreateEventW
0x14001c89a  mov     rcx, [rbx+10h]; hObject
0x14001c89e  mov     [rbx+10h], rax
0x14001c8a2  lea     rax, [rcx+1]
0x14001c8a6  cmp     rax, 1
0x14001c8aa  jbe     short loc_14001C8B2
0x14001c8ac  call    cs:__imp_CloseHandle
0x14001c8b2  mov     rax, [rbx+10h]
0x14001c8b6  inc     rax
0x14001c8b9  cmp     rax, 1
0x14001c8bd  ja      short loc_14001C8F7
0x14001c8bf  call    cs:__imp_GetLastError
0x14001c8c5  mov     ebx, eax
0x14001c8c7  test    eax, eax
0x14001c8c9  jle     short loc_14001C8D4
0x14001c8cb  movzx   ebx, ax
0x14001c8ce  or      ebx, 80070000h
0x14001c8d4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c8db  lea     rax, WPP_GLOBAL_Control
0x14001c8e2  cmp     rcx, rax
0x14001c8e5  jz      short loc_14001C8F9
0x14001c8e7  test    byte ptr [rcx+1Ch], 1
0x14001c8eb  jz      short loc_14001C8F9
0x14001c8ed  mov     edx, 0Fh
0x14001c8f2  jmp     loc_14001C873
0x14001c8f7  xor     ebx, ebx
0x14001c8f9  mov     eax, ebx
0x14001c8fb  add     rsp, 20h
0x14001c8ff  pop     rbx
0x14001c900  retn
```
