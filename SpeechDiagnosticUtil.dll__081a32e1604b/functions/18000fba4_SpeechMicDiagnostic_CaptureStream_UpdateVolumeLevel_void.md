# SpeechMicDiagnostic::CaptureStream::UpdateVolumeLevel(void)

- ea: `0x18000fba4`
- end: `0x18000fccb`
- name: `?UpdateVolumeLevel@CaptureStream@SpeechMicDiagnostic@@AEAAJXZ`
- size: `295`
- prototype: `int(SpeechMicDiagnostic::CaptureStream *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000df50`

## callees

- `0x180005b28`
- `0x18000d93c`
- `0x18000fba4`
- `0x180011010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000fc18`
- `KERNEL32!LeaveCriticalSection` at `0x18000fc66`
- `KERNEL32!LeaveCriticalSection` at `0x18000fcaf`
- `KERNEL32!LeaveCriticalSection` at `0x18000fc18`
- `KERNEL32!LeaveCriticalSection` at `0x18000fc66`
- `KERNEL32!LeaveCriticalSection` at `0x18000fcaf`
- `KERNEL32!EnterCriticalSection` at `0x18000fbba`
- `KERNEL32!EnterCriticalSection` at `0x18000fbba`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SpeechMicDiagnostic::CaptureStream::UpdateVolumeLevel(SpeechMicDiagnostic::CaptureStream *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 v3; // rdx
  char *v4; // rsi
  int v5; // edi
  __int64 v6; // rdx
  int v8; // eax
  unsigned int v9; // ebp
  int v10; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  float v12; // [rsp+40h] [rbp+8h] BYREF
  struct _RTL_CRITICAL_SECTION *v13; // [rsp+48h] [rbp+10h]

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v13 = v2;
  v4 = (char *)this + 164;
  v12 = *((float *)this + 41) - 6.0;
  if ( *((float *)this + 42) > v12 )
  {
    v5 = -2147188731;
    v6 = 498;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
      (const char *)(unsigned int)v5,
      v10);
    if ( v2 )
      LeaveCriticalSection(v2);
    return (unsigned int)v5;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 1) + 48LL))(
         *((_QWORD *)this + 1),
         v3,
         0);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 1) + 64LL))(
           *((_QWORD *)this + 1),
           (char *)this + 164);
    if ( v5 < 0 )
    {
      v6 = 504;
      goto LABEL_3;
    }
    SpeechMicDiagnostic::SmdTraceProvider::VolumeUpdate<float &,float &>(&v12, v4);
    if ( v2 )
      LeaveCriticalSection(v2);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F4,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
      (const char *)(unsigned int)v8,
      v10);
    if ( v2 )
      LeaveCriticalSection(v2);
    return v9;
  }
}

```

## disassembly

```asm
0x18000fba4  mov     [rsp+arg_10], rbx
0x18000fba9  push    rbp
0x18000fbaa  push    rsi
0x18000fbab  push    rdi; int
0x18000fbac  sub     rsp, 20h
0x18000fbb0  mov     rdi, rcx
0x18000fbb3  lea     rbx, [rcx+18h]
0x18000fbb7  mov     rcx, rbx; lpCriticalSection
0x18000fbba  call    cs:__imp_EnterCriticalSection
0x18000fbc1  nop     dword ptr [rax+rax+00h]
0x18000fbc6  mov     [rsp+38h+arg_8], rbx
0x18000fbcb  lea     rsi, [rdi+0A4h]
0x18000fbd2  movss   xmm1, dword ptr [rsi]
0x18000fbd6  subss   xmm1, cs:__real@40c00000
0x18000fbde  movss   [rsp+38h+arg_0], xmm1
0x18000fbe4  movss   xmm0, dword ptr [rdi+0A8h]
0x18000fbec  comiss  xmm0, xmm1
0x18000fbef  jbe     short loc_18000FC2B
0x18000fbf1  mov     edi, 80048005h
0x18000fbf6  mov     edx, 1F2h; void *
0x18000fbfb  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000fc02  mov     r9d, edi; char *
0x18000fc05  mov     rcx, [rsp+38h]; this
0x18000fc0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fc0f  nop
0x18000fc10  test    rbx, rbx
0x18000fc13  jz      short loc_18000FC24
0x18000fc15  mov     rcx, rbx; lpCriticalSection
0x18000fc18  call    cs:__imp_LeaveCriticalSection
0x18000fc1f  nop     dword ptr [rax+rax+00h]
0x18000fc24  mov     eax, edi
0x18000fc26  jmp     loc_18000FCBD
0x18000fc2b  mov     rcx, [rdi+8]
0x18000fc2f  mov     rax, [rcx]
0x18000fc32  xor     r8d, r8d
0x18000fc35  mov     rax, [rax+30h]
0x18000fc39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc3e  mov     ebp, eax
0x18000fc40  test    eax, eax
0x18000fc42  jns     short loc_18000FC76
0x18000fc44  mov     rcx, [rsp+38h]; this
0x18000fc49  mov     r9d, eax; char *
0x18000fc4c  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000fc53  mov     edx, 1F4h; void *
0x18000fc58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fc5d  nop
0x18000fc5e  test    rbx, rbx
0x18000fc61  jz      short loc_18000FC72
0x18000fc63  mov     rcx, rbx; lpCriticalSection
0x18000fc66  call    cs:__imp_LeaveCriticalSection
0x18000fc6d  nop     dword ptr [rax+rax+00h]
0x18000fc72  mov     eax, ebp
0x18000fc74  jmp     short loc_18000FCBD
0x18000fc76  mov     rcx, [rdi+8]
0x18000fc7a  mov     rax, [rcx]
0x18000fc7d  mov     rdx, rsi
0x18000fc80  mov     rax, [rax+40h]
0x18000fc84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc89  mov     edi, eax
0x18000fc8b  test    eax, eax
0x18000fc8d  jns     short loc_18000FC99
0x18000fc8f  mov     edx, 1F8h
0x18000fc94  jmp     loc_18000FBFB
0x18000fc99  mov     rdx, rsi
0x18000fc9c  lea     rcx, [rsp+38h+arg_0]
0x18000fca1  call    ??$VolumeUpdate@AEAMAEAM@SmdTraceProvider@SpeechMicDiagnostic@@SAXAEAM0@Z; SpeechMicDiagnostic::SmdTraceProvider::VolumeUpdate<float &,float &>(float &,float &)
0x18000fca6  nop
0x18000fca7  test    rbx, rbx
0x18000fcaa  jz      short loc_18000FCBB
0x18000fcac  mov     rcx, rbx; lpCriticalSection
0x18000fcaf  call    cs:__imp_LeaveCriticalSection
0x18000fcb6  nop     dword ptr [rax+rax+00h]
0x18000fcbb  xor     eax, eax
0x18000fcbd  mov     rbx, [rsp+38h+arg_10]
0x18000fcc2  add     rsp, 20h
0x18000fcc6  pop     rdi
0x18000fcc7  pop     rsi
0x18000fcc8  pop     rbp
0x18000fcc9  retn
```
