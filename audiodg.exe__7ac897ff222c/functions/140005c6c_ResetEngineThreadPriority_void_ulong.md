# ResetEngineThreadPriority(void * *,ulong)

- ea: `0x140005c6c`
- end: `0x140005cf9`
- name: `?ResetEngineThreadPriority@@YAJPEAPEAXK@Z`
- size: `141`
- prototype: `__int64 __fastcall(void **, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140004310`
- `0x140005240`
- `0x140005eac`

## callees

- `0x140005c6c`
- `0x14000c33c`
- `0x14007104c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005caf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005caf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005c8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005c8a`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x140005ca5`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x140005ca5`

## pseudocode

```c
__int64 __fastcall ResetEngineThreadPriority(void **a1, unsigned int a2)
{
  DWORD CurrentThreadId; // eax
  __int64 v5; // rcx
  signed int LastError; // eax
  unsigned int v7; // ebx
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !*a1 )
    return 0;
  if ( (byte_1400E7E41 & 8) != 0 )
  {
    CurrentThreadId = GetCurrentThreadId();
    McTemplateU0qq_EtwEventWriteTransfer(v5, AudioCore_Pump_AttachToMMCSS_Stop, a2, CurrentThreadId);
  }
  if ( AvRevertMmThreadCharacteristics(*a1) )
  {
    *a1 = 0;
    return 0;
  }
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( (v7 & 0x80000000) != 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8E2,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiopump.cpp",
      (const char *)v7,
      v9);
  return v7;
}

```

## disassembly

```asm
0x140005c6c  mov     [rsp+arg_0], rbx
0x140005c71  push    rdi; int
0x140005c72  sub     rsp, 20h
0x140005c76  cmp     qword ptr [rcx], 0
0x140005c7a  mov     edi, edx
0x140005c7c  mov     rbx, rcx
0x140005c7f  jz      short loc_140005CEC
0x140005c81  test    cs:byte_1400E7E41, 8
0x140005c88  jz      short loc_140005CA2
0x140005c8a  call    cs:__imp_GetCurrentThreadId
0x140005c90  mov     r8d, edi
0x140005c93  lea     rdx, AudioCore_Pump_AttachToMMCSS_Stop
0x140005c9a  mov     r9d, eax
0x140005c9d  call    McTemplateU0qq_EtwEventWriteTransfer
0x140005ca2  mov     rcx, [rbx]; AvrtHandle
0x140005ca5  call    cs:__imp_AvRevertMmThreadCharacteristics
0x140005cab  test    eax, eax
0x140005cad  jnz     short loc_140005CE5
0x140005caf  call    cs:__imp_GetLastError
0x140005cb5  mov     ebx, eax
0x140005cb7  test    eax, eax
0x140005cb9  jle     short loc_140005CC4
0x140005cbb  movzx   ebx, ax
0x140005cbe  or      ebx, 80070000h
0x140005cc4  test    ebx, ebx
0x140005cc6  jns     short loc_140005CE1
0x140005cc8  mov     rcx, [rsp+28h]; this
0x140005ccd  lea     r8, aAvcoreAudiocor_16; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140005cd4  mov     r9d, ebx; char *
0x140005cd7  mov     edx, 8E2h; void *
0x140005cdc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005ce1  mov     eax, ebx
0x140005ce3  jmp     short loc_140005CEE
0x140005ce5  mov     qword ptr [rbx], 0
0x140005cec  xor     eax, eax
0x140005cee  mov     rbx, [rsp+28h+arg_0]
0x140005cf3  add     rsp, 20h
0x140005cf7  pop     rdi
0x140005cf8  retn
```
