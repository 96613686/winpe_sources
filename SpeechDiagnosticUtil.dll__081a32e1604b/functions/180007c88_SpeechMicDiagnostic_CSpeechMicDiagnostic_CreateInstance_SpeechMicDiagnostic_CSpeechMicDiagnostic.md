# SpeechMicDiagnostic::CSpeechMicDiagnostic::CreateInstance(SpeechMicDiagnostic::CSpeechMicDiagnostic * *)

- ea: `0x180007c88`
- end: `0x180007e32`
- name: `?CreateInstance@CSpeechMicDiagnostic@SpeechMicDiagnostic@@SAJPEAPEAV12@@Z`
- size: `426`
- prototype: `__int64 __fastcall(struct SpeechMicDiagnostic::CSpeechMicDiagnostic **)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007e38`

## callees

- `0x180001640`
- `0x180002910`
- `0x180002ce0`
- `0x1800032f0`
- `0x180005b28`
- `0x1800068cc`
- `0x180007c88`
- `0x180008a9c`
- `0x1800095fc`
- `0x18000dadc`
- `0x18000dc0c`
- `0x18000e2c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SpeechMicDiagnostic::CSpeechMicDiagnostic::CreateInstance(
        struct SpeechMicDiagnostic::CSpeechMicDiagnostic **a1)
{
  int DeviceInfo; // ebx
  __int64 v3; // rdx
  void *v5; // rdi
  _DWORD *v6; // rcx
  __int64 v7; // rax
  SpeechMicDiagnostic::CaptureStream *v8; // rbx
  wchar_t **v9; // rcx
  __int64 v10; // rdx
  int v11; // eax
  int v12; // [rsp+20h] [rbp-48h]
  SpeechMicDiagnostic::CaptureStream *v13; // [rsp+30h] [rbp-38h]
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( !a1 )
  {
    DeviceInfo = -2147467261;
    v3 = 91;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\speechmicdiagnostic.cpp",
      (const char *)(unsigned int)DeviceInfo,
      v12);
    return (unsigned int)DeviceInfo;
  }
  v5 = operator new(0x38u);
  *(_QWORD *)v5 = &SpeechMicDiagnostic::CSpeechMicDiagnostic::`vftable';
  *((_QWORD *)v5 + 1) = 0;
  *((_QWORD *)v5 + 2) = 0;
  *((_QWORD *)v5 + 3) = 0;
  *((_QWORD *)v5 + 4) = 0;
  *((_QWORD *)v5 + 5) = 10001;
  *((_BYTE *)v5 + 48) = 0;
  v6 = (_DWORD *)*((_QWORD *)SpeechMicDiagnostic::SmdTraceProvider::Instance() + 1);
  if ( *v6 > 5u )
    tlgWriteTransfer_EventWriteTransfer((__int64)v6, (unsigned __int8 *)byte_18001419B, 0, 0, 2u, &v14);
  v13 = (SpeechMicDiagnostic::CaptureStream *)operator new(0xD0u);
  v7 = SpeechMicDiagnostic::CaptureStream::CaptureStream(v13);
  v8 = (SpeechMicDiagnostic::CaptureStream *)*((_QWORD *)v5 + 1);
  *((_QWORD *)v5 + 1) = v7;
  if ( v8 )
  {
    SpeechMicDiagnostic::CaptureStream::~CaptureStream(v8);
    operator delete(v8);
  }
  v9 = (wchar_t **)*((_QWORD *)v5 + 1);
  if ( !v9 )
  {
    DeviceInfo = -2147024882;
    v10 = 349;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\speechmicdiagnostic.cpp",
      (const char *)(unsigned int)DeviceInfo,
      v12);
    v3 = 95;
    goto LABEL_3;
  }
  v11 = SpeechMicDiagnostic::CaptureStream::InitializeAudioInput(v9);
  DeviceInfo = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
      (const char *)(unsigned int)v11,
      v12);
    v10 = 351;
    goto LABEL_16;
  }
  DeviceInfo = SpeechMicDiagnostic::CSpeechMicDiagnostic::QueryDeviceInfo((SpeechMicDiagnostic::CSpeechMicDiagnostic *)v5);
  if ( DeviceInfo < 0 )
  {
    v10 = 353;
    goto LABEL_16;
  }
  DeviceInfo = SpeechMicDiagnostic::CSpeechMicDiagnostic::IsSaveWaveOutIsNeeded((SpeechMicDiagnostic::CSpeechMicDiagnostic *)v5);
  if ( DeviceInfo < 0 )
  {
    v10 = 355;
    goto LABEL_16;
  }
  *a1 = (struct SpeechMicDiagnostic::CSpeechMicDiagnostic *)v5;
  return 0;
}

```

## disassembly

```asm
0x180007c88  mov     [rsp+arg_8], rbx
0x180007c8d  mov     [rsp+arg_10], rsi
0x180007c92  push    rdi
0x180007c93  sub     rsp, 60h
0x180007c97  mov     rax, cs:__security_cookie
0x180007c9e  xor     rax, rsp
0x180007ca1  mov     [rsp+68h+var_10], rax
0x180007ca6  mov     rsi, rcx
0x180007ca9  test    rcx, rcx
0x180007cac  jnz     short loc_180007CD1
0x180007cae  mov     ebx, 80004003h
0x180007cb3  lea     edx, [rcx+5Bh]; void *
0x180007cb6  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x180007cbd  mov     r9d, ebx; char *
0x180007cc0  mov     rcx, [rsp+68h]; this
0x180007cc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007cca  mov     eax, ebx
0x180007ccc  jmp     loc_180007E12
0x180007cd1  mov     ecx, 38h ; '8'; Size
0x180007cd6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007cdb  mov     rdi, rax
0x180007cde  mov     [rsp+68h+var_38], rax
0x180007ce3  lea     rax, ??_7CSpeechMicDiagnostic@SpeechMicDiagnostic@@6B@; const SpeechMicDiagnostic::CSpeechMicDiagnostic::`vftable'
0x180007cea  mov     [rdi], rax
0x180007ced  mov     qword ptr [rdi+8], 0
0x180007cf5  mov     qword ptr [rdi+10h], 0
0x180007cfd  mov     qword ptr [rdi+18h], 0
0x180007d05  mov     qword ptr [rdi+20h], 0
0x180007d0d  mov     qword ptr [rdi+28h], 2711h
0x180007d15  mov     byte ptr [rdi+30h], 0
0x180007d19  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x180007d1e  mov     rcx, [rax+8]
0x180007d22  mov     eax, [rcx]
0x180007d24  cmp     eax, 5
0x180007d27  jbe     short loc_180007D4E
0x180007d29  lea     rax, [rsp+68h+var_30]
0x180007d2e  mov     [rsp+68h+var_40], rax
0x180007d33  mov     [rsp+68h+var_48], 2; int
0x180007d3b  xor     r9d, r9d
0x180007d3e  xor     r8d, r8d
0x180007d41  lea     rdx, byte_18001419B
0x180007d48  call    _tlgWriteTransfer_EventWriteTransfer
0x180007d4d  nop
0x180007d4e  mov     ecx, 0D0h; Size
0x180007d53  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007d58  mov     [rsp+68h+var_38], rax
0x180007d5d  mov     rcx, rax; this
0x180007d60  call    ??0CaptureStream@SpeechMicDiagnostic@@QEAA@XZ; SpeechMicDiagnostic::CaptureStream::CaptureStream(void)
0x180007d65  mov     rbx, [rdi+8]
0x180007d69  mov     [rdi+8], rax
0x180007d6d  test    rbx, rbx
0x180007d70  jz      short loc_180007D87
0x180007d72  mov     rcx, rbx; this
0x180007d75  call    ??1CaptureStream@SpeechMicDiagnostic@@QEAA@XZ; SpeechMicDiagnostic::CaptureStream::~CaptureStream(void)
0x180007d7a  mov     edx, 0D0h; unsigned __int64
0x180007d7f  mov     rcx, rbx; void *
0x180007d82  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007d87  mov     rcx, [rdi+8]; this
0x180007d8b  test    rcx, rcx
0x180007d8e  jnz     short loc_180007D9C
0x180007d90  mov     ebx, 8007000Eh
0x180007d95  mov     edx, 15Dh
0x180007d9a  jmp     short loc_180007DEF
0x180007d9c  call    ?InitializeAudioInput@CaptureStream@SpeechMicDiagnostic@@AEAAJXZ; SpeechMicDiagnostic::CaptureStream::InitializeAudioInput(void)
0x180007da1  mov     ebx, eax
0x180007da3  test    eax, eax
0x180007da5  jns     short loc_180007DC7
0x180007da7  mov     rcx, [rsp+68h]; this
0x180007dac  mov     r9d, eax; char *
0x180007daf  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x180007db6  mov     edx, 1Bh; void *
0x180007dbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007dc0  mov     edx, 15Fh
0x180007dc5  jmp     short loc_180007DEF
0x180007dc7  mov     rcx, rdi; this
0x180007dca  call    ?QueryDeviceInfo@CSpeechMicDiagnostic@SpeechMicDiagnostic@@AEAAJXZ; SpeechMicDiagnostic::CSpeechMicDiagnostic::QueryDeviceInfo(void)
0x180007dcf  mov     ebx, eax
0x180007dd1  test    eax, eax
0x180007dd3  jns     short loc_180007DDC
0x180007dd5  mov     edx, 161h
0x180007dda  jmp     short loc_180007DEF
0x180007ddc  mov     rcx, rdi; this
0x180007ddf  call    ?IsSaveWaveOutIsNeeded@CSpeechMicDiagnostic@SpeechMicDiagnostic@@AEAAJXZ; SpeechMicDiagnostic::CSpeechMicDiagnostic::IsSaveWaveOutIsNeeded(void)
0x180007de4  mov     ebx, eax
0x180007de6  test    eax, eax
0x180007de8  jns     short loc_180007E0D
0x180007dea  mov     edx, 163h; void *
0x180007def  mov     r9d, ebx; char *
0x180007df2  mov     rcx, [rsp+68h]; this
0x180007df7  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x180007dfe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007e03  mov     edx, 5Fh ; '_'
0x180007e08  jmp     loc_180007CB6
0x180007e0d  mov     [rsi], rdi
0x180007e10  xor     eax, eax
0x180007e12  mov     rcx, [rsp+68h+var_10]
0x180007e17  xor     rcx, rsp; StackCookie
0x180007e1a  call    __security_check_cookie
0x180007e1f  lea     r11, [rsp+68h+var_8]
0x180007e24  mov     rbx, [r11+18h]
0x180007e28  mov     rsi, [r11+20h]
0x180007e2c  mov     rsp, r11
0x180007e2f  pop     rdi
0x180007e30  retn
```
