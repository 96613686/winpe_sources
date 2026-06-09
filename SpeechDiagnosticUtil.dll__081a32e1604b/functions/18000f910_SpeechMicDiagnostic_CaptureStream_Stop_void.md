# SpeechMicDiagnostic::CaptureStream::Stop(void)

- ea: `0x18000f910`
- end: `0x18000fa95`
- name: `?Stop@CaptureStream@SpeechMicDiagnostic@@QEAAJXZ`
- size: `389`
- prototype: `__int64 __fastcall(SpeechMicDiagnostic::CaptureStream *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180008fe0`
- `0x18000dc0c`
- `0x18000f5f0`

## callees

- `0x180005b28`
- `0x18000d5fc`
- `0x18000dd84`
- `0x18000f910`
- `0x18000fa9c`
- `0x18000fcd4`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18000f93b`
- `KERNEL32!SetEvent` at `0x18000f93b`
- `KERNEL32!TerminateThread` at `0x18000f98d`
- `KERNEL32!TerminateThread` at `0x18000f98d`
- `KERNEL32!CloseHandle` at `0x18000f9b3`
- `KERNEL32!CloseHandle` at `0x18000f9e5`
- `KERNEL32!CloseHandle` at `0x18000f9b3`
- `KERNEL32!CloseHandle` at `0x18000f9e5`
- `KERNEL32!WaitForSingleObject` at `0x18000f953`
- `KERNEL32!WaitForSingleObject` at `0x18000f953`

## pseudocode

```c
__int64 __fastcall SpeechMicDiagnostic::CaptureStream::Stop(HANDLE *this)
{
  int v1; // esi
  HANDLE *v2; // rdi
  unsigned int v4; // r8d
  const char *v5; // r9
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int v8; // r8d
  const char *v9; // r9
  int v11; // eax
  unsigned int v12; // edi
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = 0;
  v2 = this + 23;
  if ( this[24] )
  {
    SetEvent(*v2);
    if ( WaitForSingleObject(this[24], 0x2710u) )
    {
      v1 = -2147023436;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x128,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
        (const char *)0x800705B4LL,
        v15);
      if ( !TerminateThread(this[24], 0x5B4u) )
        wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x12D, v4, v5);
    }
    if ( !CloseHandle(this[24]) )
      wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x130, v6, v7);
    this[24] = 0;
  }
  if ( *v2 )
  {
    if ( !CloseHandle(*v2) )
      wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x136, v8, v9);
    *v2 = 0;
  }
  if ( v1 >= 0 )
  {
    v11 = SpeechMicDiagnostic::CaptureStream::StopAudioInput((SpeechMicDiagnostic::CaptureStream *)this);
    v12 = v11;
    if ( v11 >= 0 )
    {
      v13 = SpeechMicDiagnostic::CaptureStream::DestroyCaptureTargets((SpeechMicDiagnostic::CaptureStream *)this);
      v14 = v13;
      if ( v13 >= 0 )
      {
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x52,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
          (const char *)(unsigned int)v13,
          v15);
        return v14;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4F,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
        (const char *)(unsigned int)v11,
        v15);
      return v12;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
      (const char *)(unsigned int)v1,
      v15);
    return (unsigned int)v1;
  }
}

```

## disassembly

```asm
0x18000f910  mov     [rsp+arg_0], rbx
0x18000f915  mov     [rsp+arg_8], rsi
0x18000f91a  push    rdi; int
0x18000f91b  sub     rsp, 20h
0x18000f91f  xor     esi, esi
0x18000f921  lea     rdi, [rcx+0B8h]
0x18000f928  mov     rbx, rcx
0x18000f92b  cmp     [rcx+0C0h], rsi
0x18000f932  jz      loc_18000F9DD
0x18000f938  mov     rcx, [rdi]; hEvent
0x18000f93b  call    cs:__imp_SetEvent
0x18000f942  nop     dword ptr [rax+rax+00h]
0x18000f947  mov     rcx, [rbx+0C0h]; hHandle
0x18000f94e  mov     edx, 2710h; dwMilliseconds
0x18000f953  call    cs:__imp_WaitForSingleObject
0x18000f95a  nop     dword ptr [rax+rax+00h]
0x18000f95f  test    eax, eax
0x18000f961  jz      short loc_18000F9AC
0x18000f963  mov     rcx, [rsp+28h]; this
0x18000f968  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000f96f  mov     esi, 800705B4h
0x18000f974  mov     edx, 128h; void *
0x18000f979  mov     r9d, esi; char *
0x18000f97c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000f981  mov     rcx, [rbx+0C0h]; hThread
0x18000f988  mov     edx, 5B4h; dwExitCode
0x18000f98d  call    cs:__imp_TerminateThread
0x18000f994  nop     dword ptr [rax+rax+00h]
0x18000f999  test    eax, eax
0x18000f99b  jnz     short loc_18000F9AC
0x18000f99d  mov     rcx, [rsp+28h]; this
0x18000f9a2  mov     edx, 12Dh; void *
0x18000f9a7  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18000f9ac  mov     rcx, [rbx+0C0h]; hObject
0x18000f9b3  call    cs:__imp_CloseHandle
0x18000f9ba  nop     dword ptr [rax+rax+00h]
0x18000f9bf  test    eax, eax
0x18000f9c1  jnz     short loc_18000F9D2
0x18000f9c3  mov     rcx, [rsp+28h]; this
0x18000f9c8  mov     edx, 130h; void *
0x18000f9cd  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18000f9d2  mov     qword ptr [rbx+0C0h], 0
0x18000f9dd  mov     rcx, [rdi]; hObject
0x18000f9e0  test    rcx, rcx
0x18000f9e3  jz      short loc_18000FA0B
0x18000f9e5  call    cs:__imp_CloseHandle
0x18000f9ec  nop     dword ptr [rax+rax+00h]
0x18000f9f1  test    eax, eax
0x18000f9f3  jnz     short loc_18000FA04
0x18000f9f5  mov     rcx, [rsp+28h]; this
0x18000f9fa  mov     edx, 136h; void *
0x18000f9ff  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18000fa04  mov     qword ptr [rdi], 0
0x18000fa0b  test    esi, esi
0x18000fa0d  jns     short loc_18000FA2C
0x18000fa0f  mov     rcx, [rsp+28h]; this
0x18000fa14  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000fa1b  mov     r9d, esi; char *
0x18000fa1e  mov     edx, 4Ch ; 'L'; void *
0x18000fa23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fa28  mov     eax, esi
0x18000fa2a  jmp     short loc_18000FA84
0x18000fa2c  mov     rcx, rbx; this
0x18000fa2f  call    ?StopAudioInput@CaptureStream@SpeechMicDiagnostic@@AEAAJXZ; SpeechMicDiagnostic::CaptureStream::StopAudioInput(void)
0x18000fa34  mov     edi, eax
0x18000fa36  test    eax, eax
0x18000fa38  jns     short loc_18000FA57
0x18000fa3a  mov     rcx, [rsp+28h]; this
0x18000fa3f  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000fa46  mov     r9d, eax; char *
0x18000fa49  mov     edx, 4Fh ; 'O'; void *
0x18000fa4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fa53  mov     eax, edi
0x18000fa55  jmp     short loc_18000FA84
0x18000fa57  mov     rcx, rbx; this
0x18000fa5a  call    ?DestroyCaptureTargets@CaptureStream@SpeechMicDiagnostic@@AEAAJXZ; SpeechMicDiagnostic::CaptureStream::DestroyCaptureTargets(void)
0x18000fa5f  mov     ebx, eax
0x18000fa61  test    eax, eax
0x18000fa63  jns     short loc_18000FA82
0x18000fa65  mov     rcx, [rsp+28h]; this
0x18000fa6a  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000fa71  mov     r9d, eax; char *
0x18000fa74  mov     edx, 52h ; 'R'; void *
0x18000fa79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fa7e  mov     eax, ebx
0x18000fa80  jmp     short loc_18000FA84
0x18000fa82  xor     eax, eax
0x18000fa84  mov     rbx, [rsp+28h+arg_0]
0x18000fa89  mov     rsi, [rsp+28h+arg_8]
0x18000fa8e  add     rsp, 20h
0x18000fa92  pop     rdi
0x18000fa93  retn
```
