# SetEngineThreadPriority(ulong *,void * *)

- ea: `0x140090e80`
- end: `0x140090f62`
- name: `?SetEngineThreadPriority@@YAJPEAKPEAPEAX@Z`
- size: `226`
- prototype: `__int64 __fastcall(LPDWORD TaskIndex, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x14008f830`

## callees

- `0x14000c33c`
- `0x14004c130`
- `0x140090630`
- `0x140090e80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140090f13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140090f13`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140090f21`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140090f21`
- `AVRT!AvQuerySystemResponsiveness` at `0x140090ed0`
- `AVRT!AvQuerySystemResponsiveness` at `0x140090ed0`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x140090e97`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x140090e97`
- `AVRT!AvSetMmThreadPriority` at `0x140090f50`
- `AVRT!AvSetMmThreadPriority` at `0x140090f50`

## pseudocode

```c
__int64 __fastcall SetEngineThreadPriority(LPDWORD TaskIndex, void **a2)
{
  HANDLE v3; // rax
  const char *v4; // r9
  void *v5; // rbx
  __int64 v6; // rdx
  int v8; // eax
  unsigned int v9; // ebx
  HANDLE CurrentThread; // rax
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  ULONG SystemResponsivenessValue; // [rsp+40h] [rbp+18h] BYREF
  void *v14; // [rsp+48h] [rbp+20h] BYREF

  v3 = AvSetMmThreadCharacteristicsW(L"Audio", TaskIndex);
  v14 = v3;
  v5 = v3;
  if ( !v3 )
  {
    v6 = 28;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v6,
             (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\AudioPumpDspInterruptHandler.inl",
             v4);
  }
  SystemResponsivenessValue = 0;
  if ( !AvQuerySystemResponsiveness(v3, &SystemResponsivenessValue) )
  {
    v6 = 34;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v6,
             (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\AudioPumpDspInterruptHandler.inl",
             v4);
  }
  if ( SystemResponsivenessValue <= 0x32 )
  {
    if ( !AvSetMmThreadPriority(v5, AVRT_PRIORITY_HIGH) )
    {
      v6 = 47;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v6,
               (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\AudioPumpDspInterruptHandler.inl",
               v4);
    }
  }
  else
  {
    v8 = ResetEngineThreadPriority(&v14);
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x27,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\AudioPumpDspInterruptHandler.inl",
        (const char *)(unsigned int)v8,
        v11);
      return v9;
    }
    CurrentThread = GetCurrentThread();
    if ( !SetThreadPriority(CurrentThread, 15) )
    {
      v6 = 42;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v6,
               (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\AudioPumpDspInterruptHandler.inl",
               v4);
    }
    v5 = v14;
  }
  *a2 = v5;
  return 0;
}

```

## disassembly

```asm
0x140090e80  mov     [rsp+arg_0], rbx
0x140090e85  push    rdi; int
0x140090e86  sub     rsp, 20h
0x140090e8a  mov     rdi, rdx
0x140090e8d  mov     rdx, rcx; TaskIndex
0x140090e90  lea     rcx, aAudio_1; "Audio"
0x140090e97  call    cs:__imp_AvSetMmThreadCharacteristicsW
0x140090e9d  mov     [rsp+28h+arg_18], rax
0x140090ea2  mov     rbx, rax
0x140090ea5  test    rax, rax
0x140090ea8  jnz     short loc_140090EC0
0x140090eaa  lea     edx, [rax+1Ch]; void *
0x140090ead  mov     rcx, [rsp+28h]; this
0x140090eb2  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140090eb9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140090ebe  jmp     short loc_140090F3D
0x140090ec0  lea     rdx, [rsp+28h+SystemResponsivenessValue]; SystemResponsivenessValue
0x140090ec5  mov     [rsp+28h+SystemResponsivenessValue], 0
0x140090ecd  mov     rcx, rbx; AvrtHandle
0x140090ed0  call    cs:__imp_AvQuerySystemResponsiveness
0x140090ed6  test    eax, eax
0x140090ed8  jnz     short loc_140090EDF
0x140090eda  lea     edx, [rax+22h]
0x140090edd  jmp     short loc_140090EAD
0x140090edf  cmp     [rsp+28h+SystemResponsivenessValue], 32h ; '2'
0x140090ee4  jbe     short loc_140090F48
0x140090ee6  lea     rcx, [rsp+28h+arg_18]; void **
0x140090eeb  call    ?ResetEngineThreadPriority@@YAJPEAPEAX@Z; ResetEngineThreadPriority(void * *)
0x140090ef0  mov     ebx, eax
0x140090ef2  test    eax, eax
0x140090ef4  jns     short loc_140090F13
0x140090ef6  mov     rcx, [rsp+28h]; this
0x140090efb  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140090f02  mov     r9d, eax; char *
0x140090f05  mov     edx, 27h ; '''; void *
0x140090f0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140090f0f  mov     eax, ebx
0x140090f11  jmp     short loc_140090F3D
0x140090f13  call    cs:__imp_GetCurrentThread
0x140090f19  mov     rcx, rax; hThread
0x140090f1c  mov     edx, 0Fh; nPriority
0x140090f21  call    cs:__imp_SetThreadPriority
0x140090f27  test    eax, eax
0x140090f29  jnz     short loc_140090F33
0x140090f2b  lea     edx, [rax+2Ah]
0x140090f2e  jmp     loc_140090EAD
0x140090f33  mov     rbx, [rsp+28h+arg_18]
0x140090f38  mov     [rdi], rbx
0x140090f3b  xor     eax, eax
0x140090f3d  mov     rbx, [rsp+28h+arg_0]
0x140090f42  add     rsp, 20h
0x140090f46  pop     rdi
0x140090f47  retn
0x140090f48  mov     edx, 1; Priority
0x140090f4d  mov     rcx, rbx; AvrtHandle
0x140090f50  call    cs:__imp_AvSetMmThreadPriority
0x140090f56  test    eax, eax
0x140090f58  jnz     short loc_140090F38
0x140090f5a  lea     edx, [rax+2Fh]
0x140090f5d  jmp     loc_140090EAD
```
