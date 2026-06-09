# SpeechMicDiagnostic::CaptureStream::HandleIncomingData(void)

- ea: `0x18000df50`
- end: `0x18000e2c0`
- name: `?HandleIncomingData@CaptureStream@SpeechMicDiagnostic@@AEAAJXZ`
- size: `880`
- prototype: `__int64 __fastcall(SpeechMicDiagnostic::CaptureStream *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000f4b0`

## callees

- `0x180005b28`
- `0x180007c38`
- `0x18000dd84`
- `0x18000ddf4`
- `0x18000df50`
- `0x18000fa9c`
- `0x18000fba4`
- `0x18000ff2c`
- `0x180011010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000dfd1`
- `KERNEL32!LeaveCriticalSection` at `0x18000dfec`
- `KERNEL32!LeaveCriticalSection` at `0x18000e200`
- `KERNEL32!LeaveCriticalSection` at `0x18000e21f`
- `KERNEL32!LeaveCriticalSection` at `0x18000dfd1`
- `KERNEL32!LeaveCriticalSection` at `0x18000dfec`
- `KERNEL32!LeaveCriticalSection` at `0x18000e200`
- `KERNEL32!LeaveCriticalSection` at `0x18000e21f`
- `KERNEL32!SetEvent` at `0x18000e29f`
- `KERNEL32!SetEvent` at `0x18000e29f`
- `KERNEL32!EnterCriticalSection` at `0x18000df7c`
- `KERNEL32!EnterCriticalSection` at `0x18000e195`
- `KERNEL32!EnterCriticalSection` at `0x18000df7c`
- `KERNEL32!EnterCriticalSection` at `0x18000e195`
- `KERNEL32!GetTickCount` at `0x18000e244`
- `KERNEL32!GetTickCount` at `0x18000e244`

## string_xrefs

- `0x18000e05e`: `onecoreuap\enduser\nui\onecore\speechmicdiagnostic\lib\filewriter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SpeechMicDiagnostic::CaptureStream::HandleIncomingData(SpeechMicDiagnostic::CaptureStream *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  int v3; // eax
  unsigned int v4; // r8d
  unsigned int v5; // esi
  unsigned int v7; // edx
  __int64 v8; // rdx
  int v9; // ebx
  _QWORD *v10; // rcx
  int v11; // eax
  __int64 v12; // rdx
  DWORD v13; // esi
  __int64 v14; // rdx
  double v15; // xmm6_8
  int updated; // eax
  int v17; // eax
  unsigned int v18; // edi
  int v19; // ebx
  int v20; // [rsp+20h] [rbp-20h]
  int v21; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  unsigned int v23; // [rsp+60h] [rbp+20h] BYREF
  struct _RTL_CRITICAL_SECTION *v24; // [rsp+68h] [rbp+28h] BYREF
  unsigned int v25; // [rsp+70h] [rbp+30h] BYREF

  v25 = 0;
  v23 = 0;
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v24 = v2;
  v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, unsigned int *))(**(_QWORD **)this + 24LL))(
         *(_QWORD *)this,
         *((_QWORD *)this + 12),
         *((unsigned int *)this + 38),
         &v23);
  v5 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14A,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
      (const char *)(unsigned int)v3,
      v20);
    goto LABEL_3;
  }
  if ( v2 )
    LeaveCriticalSection(v2);
  v7 = v23;
  if ( v23 != *((_DWORD *)this + 38) )
  {
    v8 = 333;
LABEL_10:
    v9 = -2147418113;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
      (const char *)(unsigned int)v9,
      v20);
    return (unsigned int)v9;
  }
  v10 = (_QWORD *)*((_QWORD *)this + 10);
  if ( v10 )
  {
    LODWORD(v24) = 0;
    v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, struct _RTL_CRITICAL_SECTION **))(*(_QWORD *)*v10 + 32LL))(
            *v10,
            *((_QWORD *)this + 12),
            v23,
            &v24);
    v5 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x28,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\filewriter.cpp",
        (const char *)(unsigned int)v11,
        v20);
      v12 = 338;
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
        (const char *)v5,
        v21);
      return v5;
    }
    v7 = v23;
  }
  v13 = *((_DWORD *)this + 40);
  if ( v13 )
  {
    v15 = 0.0;
    v19 = *((_DWORD *)this + 44);
    if ( GetTickCount() - v19 > v13 )
    {
LABEL_41:
      v9 = SpeechMicDiagnostic::CaptureStream::StopAudioInput(this);
      if ( v9 < 0 )
      {
        v8 = 389;
        goto LABEL_11;
      }
      v9 = SpeechMicDiagnostic::CaptureStream::DestroyCaptureTargets(this);
      if ( v9 < 0 )
      {
        v8 = 392;
        goto LABEL_11;
      }
      SpeechMicDiagnostic::DiagnosticStatus::CompleteDiagnostic(
        *((SpeechMicDiagnostic::DiagnosticStatus **)this + 8),
        v25,
        v15,
        0);
      SetEvent(*((HANDLE *)this + 23));
    }
    return 0;
  }
  LODWORD(v24) = 0;
  if ( v7 != 1024 )
  {
    v5 = -2147024809;
    v14 = 111;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\levelmonitor.cpp",
      (const char *)v5,
      v20);
    v12 = 345;
    goto LABEL_15;
  }
  v5 = SpeechMicDiagnostic::LevelMonitor::ProcessVad(
         *((SpeechMicDiagnostic::LevelMonitor **)this + 11),
         *((float **)this + 12),
         v4,
         (int *)&v24);
  if ( (v5 & 0x80000000) != 0 )
  {
    v14 = 112;
    goto LABEL_22;
  }
  if ( (_DWORD)v24 == 2 )
  {
    v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 1) + 48LL))(
           *((_QWORD *)this + 1),
           **((_QWORD **)this + 1),
           0);
    if ( v9 < 0 )
    {
      v8 = 354;
      goto LABEL_11;
    }
    v9 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)this + 176LL))(*(_QWORD *)this, &v25);
    if ( v9 < 0 )
    {
      v8 = 355;
      goto LABEL_11;
    }
    v15 = fmax(0.0, *(double *)(*((_QWORD *)this + 11) + 16LL));
    goto LABEL_41;
  }
  if ( (_DWORD)v24 != 1 )
  {
    if ( (_DWORD)v24 )
    {
      v8 = 370;
      goto LABEL_10;
    }
    return 0;
  }
  EnterCriticalSection(v2);
  v24 = v2;
  updated = SpeechMicDiagnostic::CaptureStream::UpdateVolumeLevel(this);
  v5 = updated;
  if ( updated < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16C,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
      (const char *)(unsigned int)updated,
      v20);
LABEL_3:
    if ( v2 )
      LeaveCriticalSection(v2);
    return v5;
  }
  v17 = SpeechMicDiagnostic::CaptureStream::DiscardAudioInputData(this);
  v18 = v17;
  if ( v17 >= 0 )
  {
    if ( v2 )
      LeaveCriticalSection(v2);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x16E,
    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
    (const char *)(unsigned int)v17,
    v20);
  if ( v2 )
    LeaveCriticalSection(v2);
  return v18;
}

```

## disassembly

```asm
0x18000df50  mov     [rsp-18h+arg_18], rbx
0x18000df55  push    rbp
0x18000df56  push    rsi
0x18000df57  push    rdi
0x18000df58  mov     rbp, rsp
0x18000df5b  sub     rsp, 40h
0x18000df5f  movaps  [rsp+40h+var_10], xmm6
0x18000df64  mov     rdi, rcx
0x18000df67  mov     [rbp+arg_10], 0
0x18000df6e  mov     [rbp+arg_0], 0
0x18000df75  lea     rbx, [rcx+18h]
0x18000df79  mov     rcx, rbx; lpCriticalSection
0x18000df7c  call    cs:__imp_EnterCriticalSection
0x18000df83  nop     dword ptr [rax+rax+00h]
0x18000df88  mov     [rbp+arg_8], rbx
0x18000df8c  mov     rcx, [rdi]
0x18000df8f  mov     rax, [rcx]
0x18000df92  lea     r9, [rbp+arg_0]
0x18000df96  mov     r8d, [rdi+98h]
0x18000df9d  mov     rdx, [rdi+60h]
0x18000dfa1  mov     rax, [rax+18h]
0x18000dfa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfaa  mov     esi, eax
0x18000dfac  test    eax, eax
0x18000dfae  jns     short loc_18000DFE4
0x18000dfb0  mov     rcx, [rbp+18h]; this
0x18000dfb4  mov     r9d, eax; char *
0x18000dfb7  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000dfbe  mov     edx, 14Ah; void *
0x18000dfc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dfc8  nop
0x18000dfc9  test    rbx, rbx
0x18000dfcc  jz      short loc_18000DFDD
0x18000dfce  mov     rcx, rbx; lpCriticalSection
0x18000dfd1  call    cs:__imp_LeaveCriticalSection
0x18000dfd8  nop     dword ptr [rax+rax+00h]
0x18000dfdd  mov     eax, esi
0x18000dfdf  jmp     loc_18000E2AD
0x18000dfe4  test    rbx, rbx
0x18000dfe7  jz      short loc_18000DFF8
0x18000dfe9  mov     rcx, rbx; lpCriticalSection
0x18000dfec  call    cs:__imp_LeaveCriticalSection
0x18000dff3  nop     dword ptr [rax+rax+00h]
0x18000dff8  mov     edx, [rbp+arg_0]
0x18000dffb  cmp     edx, [rdi+98h]
0x18000e001  jz      short loc_18000E027
0x18000e003  mov     edx, 14Dh; void *
0x18000e008  mov     ebx, 8000FFFFh
0x18000e00d  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000e014  mov     r9d, ebx; char *
0x18000e017  mov     rcx, [rbp+18h]; this
0x18000e01b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e020  mov     eax, ebx
0x18000e022  jmp     loc_18000E2AD
0x18000e027  mov     rcx, [rdi+50h]
0x18000e02b  test    rcx, rcx
0x18000e02e  jz      short loc_18000E08F
0x18000e030  mov     dword ptr [rbp+arg_8], 0
0x18000e037  mov     rcx, [rcx]
0x18000e03a  mov     rax, [rcx]
0x18000e03d  lea     r9, [rbp+arg_8]
0x18000e041  mov     r8d, edx
0x18000e044  mov     rdx, [rdi+60h]
0x18000e048  mov     rax, [rax+20h]
0x18000e04c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e051  mov     esi, eax
0x18000e053  test    eax, eax
0x18000e055  jns     short loc_18000E08C
0x18000e057  mov     rcx, [rbp+18h]; this
0x18000e05b  mov     r9d, eax; char *
0x18000e05e  lea     r8, aOnecoreuapEndu; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000e065  mov     edx, 28h ; '('; void *
0x18000e06a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e06f  mov     edx, 152h; void *
0x18000e074  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000e07b  mov     r9d, esi; char *
0x18000e07e  mov     rcx, [rbp+18h]; this
0x18000e082  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e087  jmp     loc_18000DFDD
0x18000e08c  mov     edx, [rbp+arg_0]
0x18000e08f  mov     esi, [rdi+0A0h]
0x18000e095  test    esi, esi
0x18000e097  jnz     loc_18000E23B
0x18000e09d  mov     dword ptr [rbp+arg_8], esi
0x18000e0a0  cmp     edx, 400h
0x18000e0a6  jz      short loc_18000E0B4
0x18000e0a8  mov     esi, 80070057h
0x18000e0ad  mov     edx, 6Fh ; 'o'
0x18000e0b2  jmp     short loc_18000E0D0
0x18000e0b4  lea     r9, [rbp+arg_8]; int *
0x18000e0b8  mov     rdx, [rdi+60h]; float *
0x18000e0bc  mov     rcx, [rdi+58h]; this
0x18000e0c0  call    ?ProcessVad@LevelMonitor@SpeechMicDiagnostic@@AEAAJPEAMIPEAH@Z; SpeechMicDiagnostic::LevelMonitor::ProcessVad(float *,uint,int *)
0x18000e0c5  mov     esi, eax
0x18000e0c7  test    eax, eax
0x18000e0c9  jns     short loc_18000E0EA
0x18000e0cb  mov     edx, 70h ; 'p'; void *
0x18000e0d0  mov     r9d, esi; char *
0x18000e0d3  lea     r8, aOnecoreuapEndu_2; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000e0da  mov     rcx, [rbp+18h]; this
0x18000e0de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e0e3  mov     edx, 159h
0x18000e0e8  jmp     short loc_18000E074
0x18000e0ea  mov     eax, dword ptr [rbp+arg_8]
0x18000e0ed  cmp     eax, 2
0x18000e0f0  jnz     loc_18000E189
0x18000e0f6  mov     rcx, [rdi+8]
0x18000e0fa  mov     rdx, [rcx]
0x18000e0fd  mov     rax, [rdi+58h]
0x18000e101  movsd   xmm0, qword ptr [rax+30h]
0x18000e106  cvtpd2ps xmm0, xmm0
0x18000e10a  movss   xmm1, cs:__real@c1d00000
0x18000e112  subss   xmm1, xmm0
0x18000e116  addss   xmm1, dword ptr [rdi+0A4h]
0x18000e11e  movss   xmm0, dword ptr [rdi+0ACh]
0x18000e126  minss   xmm0, xmm1
0x18000e12a  movss   xmm1, dword ptr [rdi+0A8h]
0x18000e132  maxss   xmm1, xmm0
0x18000e136  xor     r8d, r8d
0x18000e139  mov     rax, [rdx+30h]
0x18000e13d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e142  mov     ebx, eax
0x18000e144  test    eax, eax
0x18000e146  jns     short loc_18000E152
0x18000e148  mov     edx, 162h
0x18000e14d  jmp     loc_18000E00D
0x18000e152  mov     rcx, [rdi]
0x18000e155  mov     rax, [rcx]
0x18000e158  lea     rdx, [rbp+arg_10]
0x18000e15c  mov     rax, [rax+0B0h]
0x18000e163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e168  mov     ebx, eax
0x18000e16a  test    eax, eax
0x18000e16c  jns     short loc_18000E178
0x18000e16e  mov     edx, 163h
0x18000e173  jmp     loc_18000E00D
0x18000e178  mov     rax, [rdi+58h]
0x18000e17c  xorps   xmm6, xmm6
0x18000e17f  maxsd   xmm6, qword ptr [rax+10h]
0x18000e184  jmp     loc_18000E256
0x18000e189  cmp     eax, 1
0x18000e18c  jnz     loc_18000E22D
0x18000e192  mov     rcx, rbx; lpCriticalSection
0x18000e195  call    cs:__imp_EnterCriticalSection
0x18000e19c  nop     dword ptr [rax+rax+00h]
0x18000e1a1  mov     [rbp+arg_8], rbx
0x18000e1a5  mov     rcx, rdi; this
0x18000e1a8  call    ?UpdateVolumeLevel@CaptureStream@SpeechMicDiagnostic@@AEAAJXZ; SpeechMicDiagnostic::CaptureStream::UpdateVolumeLevel(void)
0x18000e1ad  mov     esi, eax
0x18000e1af  test    eax, eax
0x18000e1b1  jns     short loc_18000E1D1
0x18000e1b3  mov     rcx, [rbp+18h]; this
0x18000e1b7  mov     r9d, eax; char *
0x18000e1ba  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000e1c1  mov     edx, 16Ch; void *
0x18000e1c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e1cb  nop
0x18000e1cc  jmp     loc_18000DFC9
0x18000e1d1  mov     rcx, rdi; this
0x18000e1d4  call    ?DiscardAudioInputData@CaptureStream@SpeechMicDiagnostic@@AEAAJXZ; SpeechMicDiagnostic::CaptureStream::DiscardAudioInputData(void)
0x18000e1d9  mov     edi, eax
0x18000e1db  test    eax, eax
0x18000e1dd  jns     short loc_18000E213
0x18000e1df  mov     rcx, [rbp+18h]; this
0x18000e1e3  mov     r9d, eax; char *
0x18000e1e6  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000e1ed  mov     edx, 16Eh; void *
0x18000e1f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e1f7  nop
0x18000e1f8  test    rbx, rbx
0x18000e1fb  jz      short loc_18000E20C
0x18000e1fd  mov     rcx, rbx; lpCriticalSection
0x18000e200  call    cs:__imp_LeaveCriticalSection
0x18000e207  nop     dword ptr [rax+rax+00h]
0x18000e20c  mov     eax, edi
0x18000e20e  jmp     loc_18000E2AD
0x18000e213  test    rbx, rbx
0x18000e216  jz      loc_18000E2AB
0x18000e21c  mov     rcx, rbx; lpCriticalSection
0x18000e21f  call    cs:__imp_LeaveCriticalSection
0x18000e226  nop     dword ptr [rax+rax+00h]
0x18000e22b  jmp     short loc_18000E2AB
0x18000e22d  test    eax, eax
0x18000e22f  jz      short loc_18000E2AB
0x18000e231  mov     edx, 172h
0x18000e236  jmp     loc_18000E008
0x18000e23b  xorps   xmm6, xmm6
0x18000e23e  mov     ebx, [rdi+0B0h]
0x18000e244  call    cs:__imp_GetTickCount
0x18000e24b  nop     dword ptr [rax+rax+00h]
0x18000e250  sub     eax, ebx
0x18000e252  cmp     eax, esi
0x18000e254  jbe     short loc_18000E2AB
0x18000e256  mov     rcx, rdi; this
0x18000e259  call    ?StopAudioInput@CaptureStream@SpeechMicDiagnostic@@AEAAJXZ; SpeechMicDiagnostic::CaptureStream::StopAudioInput(void)
0x18000e25e  mov     ebx, eax
0x18000e260  test    eax, eax
0x18000e262  jns     short loc_18000E26E
0x18000e264  mov     edx, 185h
0x18000e269  jmp     loc_18000E00D
0x18000e26e  mov     rcx, rdi; this
0x18000e271  call    ?DestroyCaptureTargets@CaptureStream@SpeechMicDiagnostic@@AEAAJXZ; SpeechMicDiagnostic::CaptureStream::DestroyCaptureTargets(void)
0x18000e276  mov     ebx, eax
0x18000e278  test    eax, eax
0x18000e27a  jns     short loc_18000E286
0x18000e27c  mov     edx, 188h
0x18000e281  jmp     loc_18000E00D
0x18000e286  xor     r9d, r9d; int
0x18000e289  movaps  xmm2, xmm6; double
0x18000e28c  mov     edx, [rbp+arg_10]; unsigned int
0x18000e28f  mov     rcx, [rdi+40h]; this
0x18000e293  call    ?CompleteDiagnostic@DiagnosticStatus@SpeechMicDiagnostic@@QEAAXKNJ@Z; SpeechMicDiagnostic::DiagnosticStatus::CompleteDiagnostic(ulong,double,long)
0x18000e298  mov     rcx, [rdi+0B8h]; hEvent
0x18000e29f  call    cs:__imp_SetEvent
0x18000e2a6  nop     dword ptr [rax+rax+00h]
0x18000e2ab  xor     eax, eax
0x18000e2ad  mov     rbx, [rsp+40h+arg_18]
0x18000e2b2  movaps  xmm6, [rsp+40h+var_10]
0x18000e2b7  add     rsp, 40h
0x18000e2bb  pop     rdi
0x18000e2bc  pop     rsi
0x18000e2bd  pop     rbp
0x18000e2be  retn
```
