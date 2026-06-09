# SetEngineThreadPriority(AudioThreadPriorityLevel,ulong *,void * *)

- ea: `0x140005eac`
- end: `0x140006008`
- name: `?SetEngineThreadPriority@@YAJW4AudioThreadPriorityLevel@@PEAKPEAPEAX@Z`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140005b6c`

## callees

- `0x140005c6c`
- `0x140005eac`
- `0x14000c33c`
- `0x14007104c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005f3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005f5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005f7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005f3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005f5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005f7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140005fea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140005fea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005fb4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005fb4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140005ff8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140005ff8`
- `AVRT!AvQuerySystemResponsiveness` at `0x140005eef`
- `AVRT!AvQuerySystemResponsiveness` at `0x140005eef`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x140005ecc`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x140005ecc`
- `AVRT!AvSetMmThreadPriority` at `0x140005f19`
- `AVRT!AvSetMmThreadPriority` at `0x140005f19`

## pseudocode

```c
__int64 __fastcall SetEngineThreadPriority(ULONG a1, DWORD *a2, _QWORD *a3)
{
  HANDLE v5; // rax
  void *v6; // rbx
  BOOL v7; // eax
  signed int LastError; // eax
  signed int v10; // ebx
  __int64 v11; // rdx
  signed int v12; // eax
  signed int v13; // eax
  DWORD CurrentThreadId; // eax
  __int64 v15; // rcx
  HANDLE CurrentThread; // rax
  int v17; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  ULONG SystemResponsivenessValue; // [rsp+30h] [rbp+8h] BYREF
  void *v20; // [rsp+48h] [rbp+20h] BYREF

  SystemResponsivenessValue = a1;
  v5 = AvSetMmThreadCharacteristicsW(L"Audio", a2);
  v20 = v5;
  v6 = v5;
  if ( !v5 )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( v10 >= 0 )
      return (unsigned int)v10;
    v11 = 2327;
    goto LABEL_21;
  }
  SystemResponsivenessValue = 0;
  if ( !AvQuerySystemResponsiveness(v5, &SystemResponsivenessValue) )
  {
    v12 = GetLastError();
    v10 = v12;
    if ( v12 > 0 )
      v10 = (unsigned __int16)v12 | 0x80070000;
    if ( v10 >= 0 )
      return (unsigned int)v10;
    v11 = 2334;
    goto LABEL_21;
  }
  if ( (byte_1400E7E41 & 8) != 0 )
  {
    CurrentThreadId = GetCurrentThreadId();
    McTemplateU0qq_EtwEventWriteTransfer(v15, AudioCore_Pump_AttachToMMCSS_Start, *a2, CurrentThreadId);
  }
  if ( SystemResponsivenessValue > 0x32 )
  {
    v10 = ResetEngineThreadPriority(&v20, *a2);
    if ( v10 < 0 )
    {
      v11 = 2342;
      goto LABEL_21;
    }
    CurrentThread = GetCurrentThread();
    v7 = SetThreadPriority(CurrentThread, 15);
    v6 = v20;
  }
  else
  {
    v7 = AvSetMmThreadPriority(v6, AVRT_PRIORITY_HIGH);
    *a3 = v6;
  }
  if ( v7 )
  {
    *a3 = v6;
    return 0;
  }
  v13 = GetLastError();
  v10 = v13;
  if ( v13 > 0 )
    v10 = (unsigned __int16)v13 | 0x80070000;
  if ( v10 < 0 )
  {
    v11 = 2354;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiopump.cpp",
      (const char *)(unsigned int)v10,
      v17);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140005eac  mov     [rsp+arg_8], rbx
0x140005eb1  mov     [rsp+arg_10], rsi
0x140005eb6  mov     [rsp+SystemResponsivenessValue], ecx
0x140005eba  push    rdi; int
0x140005ebb  sub     rsp, 20h
0x140005ebf  lea     rcx, TaskName; "Audio"
0x140005ec6  mov     rsi, r8
0x140005ec9  mov     rdi, rdx
0x140005ecc  call    cs:__imp_AvSetMmThreadCharacteristicsW
0x140005ed2  mov     [rsp+28h+arg_18], rax
0x140005ed7  mov     rbx, rax
0x140005eda  test    rax, rax
0x140005edd  jz      short loc_140005F3B
0x140005edf  lea     rdx, [rsp+28h+SystemResponsivenessValue]; SystemResponsivenessValue
0x140005ee4  mov     [rsp+28h+SystemResponsivenessValue], 0
0x140005eec  mov     rcx, rax; AvrtHandle
0x140005eef  call    cs:__imp_AvQuerySystemResponsiveness
0x140005ef5  test    eax, eax
0x140005ef7  jz      short loc_140005F5B
0x140005ef9  test    cs:byte_1400E7E41, 8
0x140005f00  jnz     loc_140005FB4
0x140005f06  cmp     [rsp+28h+SystemResponsivenessValue], 32h ; '2'
0x140005f0b  ja      loc_140005FD1
0x140005f11  mov     edx, 1; Priority
0x140005f16  mov     rcx, rbx; AvrtHandle
0x140005f19  call    cs:__imp_AvSetMmThreadPriority
0x140005f1f  mov     [rsi], rbx
0x140005f22  test    eax, eax
0x140005f24  jz      short loc_140005F7B
0x140005f26  mov     [rsi], rbx
0x140005f29  xor     eax, eax
0x140005f2b  mov     rbx, [rsp+28h+arg_8]
0x140005f30  mov     rsi, [rsp+28h+arg_10]
0x140005f35  add     rsp, 20h
0x140005f39  pop     rdi
0x140005f3a  retn
0x140005f3b  call    cs:__imp_GetLastError
0x140005f41  mov     ebx, eax
0x140005f43  test    eax, eax
0x140005f45  jle     short loc_140005F50
0x140005f47  movzx   ebx, ax
0x140005f4a  or      ebx, 80070000h
0x140005f50  test    ebx, ebx
0x140005f52  jns     short loc_140005FAD
0x140005f54  mov     edx, 917h
0x140005f59  jmp     short loc_140005F99
0x140005f5b  call    cs:__imp_GetLastError
0x140005f61  mov     ebx, eax
0x140005f63  test    eax, eax
0x140005f65  jle     short loc_140005F70
0x140005f67  movzx   ebx, ax
0x140005f6a  or      ebx, 80070000h
0x140005f70  test    ebx, ebx
0x140005f72  jns     short loc_140005FAD
0x140005f74  mov     edx, 91Eh
0x140005f79  jmp     short loc_140005F99
0x140005f7b  call    cs:__imp_GetLastError
0x140005f81  mov     ebx, eax
0x140005f83  test    eax, eax
0x140005f85  jle     short loc_140005F90
0x140005f87  movzx   ebx, ax
0x140005f8a  or      ebx, 80070000h
0x140005f90  test    ebx, ebx
0x140005f92  jns     short loc_140005FAD
0x140005f94  mov     edx, 932h; void *
0x140005f99  mov     rcx, [rsp+28h]; this
0x140005f9e  lea     r8, aAvcoreAudiocor_16; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140005fa5  mov     r9d, ebx; char *
0x140005fa8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005fad  mov     eax, ebx
0x140005faf  jmp     loc_140005F2B
0x140005fb4  call    cs:__imp_GetCurrentThreadId
0x140005fba  mov     r8d, [rdi]
0x140005fbd  lea     rdx, AudioCore_Pump_AttachToMMCSS_Start
0x140005fc4  mov     r9d, eax
0x140005fc7  call    McTemplateU0qq_EtwEventWriteTransfer
0x140005fcc  jmp     loc_140005F06
0x140005fd1  mov     edx, [rdi]; unsigned int
0x140005fd3  lea     rcx, [rsp+28h+arg_18]; void **
0x140005fd8  call    ?ResetEngineThreadPriority@@YAJPEAPEAXK@Z; ResetEngineThreadPriority(void * *,ulong)
0x140005fdd  mov     ebx, eax
0x140005fdf  test    eax, eax
0x140005fe1  jns     short loc_140005FEA
0x140005fe3  mov     edx, 926h
0x140005fe8  jmp     short loc_140005F99
0x140005fea  call    cs:__imp_GetCurrentThread
0x140005ff0  mov     rcx, rax; hThread
0x140005ff3  mov     edx, 0Fh; nPriority
0x140005ff8  call    cs:__imp_SetThreadPriority
0x140005ffe  mov     rbx, [rsp+28h+arg_18]
0x140006003  jmp     loc_140005F22
```
