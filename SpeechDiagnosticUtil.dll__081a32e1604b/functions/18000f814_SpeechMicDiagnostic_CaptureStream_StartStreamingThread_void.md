# SpeechMicDiagnostic::CaptureStream::StartStreamingThread(void)

- ea: `0x18000f814`
- end: `0x18000f907`
- name: `?StartStreamingThread@CaptureStream@SpeechMicDiagnostic@@AEAAJXZ`
- size: `243`
- prototype: `__int64 __fastcall(SpeechMicDiagnostic::CaptureStream *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000f5f0`

## callees

- `0x180002ce0`
- `0x180003334`
- `0x180005b08`
- `0x180005b28`
- `0x18000f814`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18000f886`
- `KERNEL32!CreateEventW` at `0x18000f886`
- `KERNEL32!CreateThread` at `0x18000f8d5`
- `KERNEL32!CreateThread` at `0x18000f8d5`

## pseudocode

```c
__int64 __fastcall SpeechMicDiagnostic::CaptureStream::StartStreamingThread(SpeechMicDiagnostic::CaptureStream *this)
{
  void *v2; // rax
  unsigned __int64 v3; // rdx
  void **v4; // rbx
  void *v5; // rcx
  HANDLE EventW; // rax
  const char *v8; // r9
  __int64 v9; // rdx
  HANDLE Thread; // rax
  bool v11; // zf
  DWORD dwCreationFlags; // [rsp+20h] [rbp-28h]
  char v13; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = operator new[](*((unsigned int *)this + 38));
  v4 = (void **)((char *)this + 96);
  if ( (char *)this + 96 == &v13 )
  {
    if ( !v2 )
      goto LABEL_7;
    v5 = v2;
  }
  else
  {
    v5 = *v4;
    *v4 = v2;
    if ( !v5 )
      goto LABEL_7;
  }
  operator delete(v5, v3);
LABEL_7:
  if ( !*v4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x112,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
      (const char *)0x8007000ELL,
      dwCreationFlags);
    return 2147942414LL;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 23) = EventW;
  if ( !EventW )
  {
    v9 = 277;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v9,
             (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
             v8);
  }
  Thread = CreateThread(0, 0, SpeechMicDiagnostic::CaptureStream::ReceiveThread, this, 0, 0);
  v11 = *((_QWORD *)this + 23) == 0;
  *((_QWORD *)this + 24) = Thread;
  if ( v11 )
  {
    v9 = 280;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v9,
             (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
             v8);
  }
  return 0;
}

```

## disassembly

```asm
0x18000f814  mov     [rsp+arg_0], rbx
0x18000f819  push    rdi
0x18000f81a  sub     rsp, 40h
0x18000f81e  mov     rdi, rcx
0x18000f821  mov     ecx, [rcx+98h]; unsigned __int64
0x18000f827  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000f82c  lea     rcx, [rsp+48h+var_18]
0x18000f831  lea     rbx, [rdi+60h]
0x18000f835  cmp     rbx, rcx
0x18000f838  jz      short loc_18000F847
0x18000f83a  mov     rcx, [rbx]
0x18000f83d  mov     [rbx], rax
0x18000f840  test    rcx, rcx
0x18000f843  jz      short loc_18000F854
0x18000f845  jmp     short loc_18000F84F
0x18000f847  test    rax, rax
0x18000f84a  jz      short loc_18000F854
0x18000f84c  mov     rcx, rax; void *
0x18000f84f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f854  cmp     qword ptr [rbx], 0
0x18000f858  jnz     short loc_18000F87C
0x18000f85a  mov     rcx, [rsp+48h]; this
0x18000f85f  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000f866  mov     ebx, 8007000Eh
0x18000f86b  mov     edx, 112h; void *
0x18000f870  mov     r9d, ebx; char *
0x18000f873  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f878  mov     eax, ebx
0x18000f87a  jmp     short loc_18000F8FB
0x18000f87c  xor     r9d, r9d; lpName
0x18000f87f  xor     r8d, r8d; bInitialState
0x18000f882  xor     edx, edx; bManualReset
0x18000f884  xor     ecx, ecx; lpEventAttributes
0x18000f886  call    cs:__imp_CreateEventW
0x18000f88d  nop     dword ptr [rax+rax+00h]
0x18000f892  mov     [rdi+0B8h], rax
0x18000f899  test    rax, rax
0x18000f89c  jnz     short loc_18000F8B6
0x18000f89e  mov     edx, 115h; void *
0x18000f8a3  mov     rcx, [rsp+48h]; this
0x18000f8a8  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000f8af  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f8b4  jmp     short loc_18000F8FB
0x18000f8b6  mov     [rsp+48h+lpThreadId], 0; lpThreadId
0x18000f8bf  lea     r8, ?ReceiveThread@CaptureStream@SpeechMicDiagnostic@@CAKPEAX@Z; lpStartAddress
0x18000f8c6  mov     r9, rdi; lpParameter
0x18000f8c9  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x18000f8d1  xor     edx, edx; dwStackSize
0x18000f8d3  xor     ecx, ecx; lpThreadAttributes
0x18000f8d5  call    cs:__imp_CreateThread
0x18000f8dc  nop     dword ptr [rax+rax+00h]
0x18000f8e1  cmp     qword ptr [rdi+0B8h], 0
0x18000f8e9  mov     [rdi+0C0h], rax
0x18000f8f0  jnz     short loc_18000F8F9
0x18000f8f2  mov     edx, 118h
0x18000f8f7  jmp     short loc_18000F8A3
0x18000f8f9  xor     eax, eax
0x18000f8fb  mov     rbx, [rsp+48h+arg_0]
0x18000f900  add     rsp, 40h
0x18000f904  pop     rdi
0x18000f905  retn
```
