# SpeechMicDiagnostic::CSpeechMicDiagnostic::MicDiagnosticStart(void * *,ushort const *,ulong)

- ea: `0x1800090dc`
- end: `0x18000931e`
- name: `?MicDiagnosticStart@CSpeechMicDiagnostic@SpeechMicDiagnostic@@QEAAJPEAPEAXPEBGK@Z`
- size: `578`
- prototype: `__int64 __fastcall(SpeechMicDiagnostic::CSpeechMicDiagnostic *__hidden this, void **, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180009330`

## callees

- `0x1800032f0`
- `0x180005b08`
- `0x180005b28`
- `0x180008948`
- `0x1800090dc`
- `0x18000f5f0`
- `0x180011010`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180009261`
- `KERNEL32!CreateEventW` at `0x180009261`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SpeechMicDiagnostic::CSpeechMicDiagnostic::MicDiagnosticStart(
        SpeechMicDiagnostic::CSpeechMicDiagnostic *this,
        void **a2,
        const unsigned __int16 *a3,
        int a4)
{
  int LastError; // ebx
  __int64 v7; // rdx
  _QWORD *v9; // rdi
  __int64 v10; // rcx
  _QWORD *v11; // rbx
  volatile signed __int32 *v12; // rbx
  __int64 v13; // rbx
  HANDLE EventW; // rax
  const char *v15; // r9
  void *v16; // rcx
  int v17; // eax
  int v18; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  _DWORD *v20; // [rsp+68h] [rbp+10h]
  int v21; // [rsp+78h] [rbp+20h] BYREF

  v21 = a4;
  if ( !a2 )
  {
    LastError = -2147024809;
    v7 = 244;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\speechmicdiagnostic.cpp",
      (const char *)(unsigned int)LastError,
      v18);
    return (unsigned int)LastError;
  }
  v9 = (_QWORD *)((char *)this + 16);
  v10 = *((_QWORD *)this + 2);
  if ( v10 && *(_DWORD *)(v10 + 12) == -2147188734 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF9,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\speechmicdiagnostic.cpp",
      (const char *)0x80048002LL,
      v18);
    return 2147778562LL;
  }
  else
  {
    v11 = operator new(0x20u);
    v11[2] = 0;
    *v11 = 0xBFF0000000000000uLL;
    *((_DWORD *)v11 + 2) = 10000;
    *((_DWORD *)v11 + 3) = -2147188734;
    *((_DWORD *)v11 + 6) = 0;
    v20 = operator new(0x18u);
    *(_OWORD *)v20 = 0;
    v20[2] = 1;
    v20[3] = 1;
    *(_QWORD *)v20 = &std::_Ref_count<SpeechMicDiagnostic::DiagnosticStatus>::`vftable';
    *((_QWORD *)v20 + 2) = v11;
    *v9 = v11;
    v12 = (volatile signed __int32 *)v9[1];
    v9[1] = v20;
    if ( v12 )
    {
      if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      }
    }
    v13 = *v9;
    if ( !*v9 )
    {
      LastError = -2147024882;
      v7 = 252;
      goto LABEL_3;
    }
    *(_QWORD *)v13 = 0xBFF0000000000000uLL;
    *(_DWORD *)(v13 + 8) = 10000;
    *(_DWORD *)(v13 + 12) = -2147188734;
    *(_DWORD *)(v13 + 24) = 0;
    if ( !*(_QWORD *)(v13 + 16) )
    {
      EventW = CreateEventW(0, 0, 0, 0);
      *(_QWORD *)(v13 + 16) = EventW;
      if ( !EventW )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x22,
                      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\speechmicdiagnostic.cpp",
                      v15);
        if ( LastError < 0 )
        {
          v7 = 254;
          goto LABEL_3;
        }
      }
    }
    v16 = *(void **)(*v9 + 16LL);
    *a2 = v16;
    LOBYTE(v21) = 0;
    LastError = SpeechMicDiagnostic::CSpeechMicDiagnostic::IsKwsEnabled(
                  (SpeechMicDiagnostic::CSpeechMicDiagnostic *)v16,
                  (bool *)&v21);
    if ( LastError < 0 )
    {
      v7 = 259;
      goto LABEL_3;
    }
    v17 = 8500;
    if ( *((_DWORD *)this + 10) != 10001 )
      v17 = *((_DWORD *)this + 10);
    LastError = SpeechMicDiagnostic::CaptureStream::Start(
                  *((SpeechMicDiagnostic::CaptureStream **)this + 1),
                  v17,
                  (_BYTE)v21 == 0);
    if ( LastError < 0 )
    {
      v7 = 262;
      goto LABEL_3;
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1800090dc  mov     [rsp+arg_0], rbx
0x1800090e1  mov     [rsp+arg_10], rbp
0x1800090e6  mov     [rsp+arg_18], r9d
0x1800090eb  push    rsi
0x1800090ec  push    rdi
0x1800090ed  push    r12
0x1800090ef  push    r13
0x1800090f1  push    r14
0x1800090f3  sub     rsp, 30h
0x1800090f7  mov     rbp, r8
0x1800090fa  mov     r14, rdx
0x1800090fd  mov     rsi, rcx
0x180009100  test    rdx, rdx
0x180009103  jnz     short loc_18000912A
0x180009105  mov     ebx, 80070057h
0x18000910a  mov     edx, 0F4h; void *
0x18000910f  mov     rcx, [rsp+58h]; this
0x180009114  mov     r9d, ebx; char *
0x180009117  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000911e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009123  mov     eax, ebx
0x180009125  jmp     loc_180009306
0x18000912a  lea     rdi, [rcx+10h]
0x18000912e  mov     rcx, [rdi]
0x180009131  mov     r12d, 80048002h
0x180009137  test    rcx, rcx
0x18000913a  jz      short loc_180009163
0x18000913c  cmp     [rcx+0Ch], r12d
0x180009140  jnz     short loc_180009163
0x180009142  mov     rcx, [rsp+58h]; this
0x180009147  mov     r9d, r12d; char *
0x18000914a  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x180009151  mov     edx, 0F9h; void *
0x180009156  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000915b  mov     eax, r12d
0x18000915e  jmp     loc_180009306
0x180009163  mov     ecx, 20h ; ' '; Size
0x180009168  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000916d  mov     rbx, rax
0x180009170  mov     [rsp+58h+arg_8], rax
0x180009175  mov     qword ptr [rax+10h], 0
0x18000917d  mov     r13, 0BFF0000000000000h
0x180009187  mov     [rax], r13
0x18000918a  mov     dword ptr [rax+8], 2710h
0x180009191  mov     [rax+0Ch], r12d
0x180009195  mov     dword ptr [rax+18h], 0
0x18000919c  mov     [rsp+58h+arg_8], rax
0x1800091a1  mov     ecx, 18h; Size
0x1800091a6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800091ab  mov     [rsp+58h+arg_8], rax
0x1800091b0  xorps   xmm0, xmm0
0x1800091b3  movups  xmmword ptr [rax], xmm0
0x1800091b6  mov     ecx, 1
0x1800091bb  mov     [rax+8], ecx
0x1800091be  mov     [rax+0Ch], ecx
0x1800091c1  lea     rcx, ??_7?$_Ref_count@VDiagnosticStatus@SpeechMicDiagnostic@@@std@@6B@; const std::_Ref_count<SpeechMicDiagnostic::DiagnosticStatus>::`vftable'
0x1800091c8  mov     [rax], rcx
0x1800091cb  mov     [rax+10h], rbx
0x1800091cf  mov     [rdi], rbx
0x1800091d2  mov     rbx, [rdi+8]
0x1800091d6  mov     [rdi+8], rax
0x1800091da  test    rbx, rbx
0x1800091dd  jz      short loc_180009224
0x1800091df  or      r13d, 0FFFFFFFFh
0x1800091e3  mov     eax, r13d
0x1800091e6  lock xadd [rbx+8], eax
0x1800091eb  add     eax, r13d
0x1800091ee  jnz     short loc_18000921A
0x1800091f0  mov     rax, [rbx]
0x1800091f3  mov     rcx, rbx
0x1800091f6  mov     rax, [rax]
0x1800091f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091fe  mov     eax, r13d
0x180009201  lock xadd [rbx+0Ch], eax
0x180009206  add     eax, r13d
0x180009209  jnz     short loc_18000921A
0x18000920b  mov     rax, [rbx]
0x18000920e  mov     rcx, rbx
0x180009211  mov     rax, [rax+8]
0x180009215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000921a  mov     r13, 0BFF0000000000000h
0x180009224  mov     rbx, [rdi]
0x180009227  test    rbx, rbx
0x18000922a  jnz     short loc_18000923B
0x18000922c  mov     ebx, 8007000Eh
0x180009231  mov     edx, 0FCh
0x180009236  jmp     loc_18000910F
0x18000923b  mov     [rbx], r13
0x18000923e  mov     dword ptr [rbx+8], 2710h
0x180009245  mov     [rbx+0Ch], r12d
0x180009249  mov     dword ptr [rbx+18h], 0
0x180009250  cmp     qword ptr [rbx+10h], 0
0x180009255  jnz     short loc_18000929A
0x180009257  xor     r9d, r9d; lpName
0x18000925a  xor     r8d, r8d; bInitialState
0x18000925d  xor     edx, edx; bManualReset
0x18000925f  xor     ecx, ecx; lpEventAttributes
0x180009261  call    cs:__imp_CreateEventW
0x180009268  nop     dword ptr [rax+rax+00h]
0x18000926d  mov     [rbx+10h], rax
0x180009271  test    rax, rax
0x180009274  jnz     short loc_18000929A
0x180009276  mov     rcx, [rsp+58h]; this
0x18000927b  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x180009282  lea     edx, [rax+22h]; void *
0x180009285  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000928a  mov     ebx, eax
0x18000928c  test    eax, eax
0x18000928e  jns     short loc_18000929A
0x180009290  mov     edx, 0FEh
0x180009295  jmp     loc_18000910F
0x18000929a  mov     rax, [rdi]
0x18000929d  mov     rcx, [rax+10h]; this
0x1800092a1  mov     [r14], rcx
0x1800092a4  mov     byte ptr [rsp+58h+arg_18], 0
0x1800092a9  lea     rdx, [rsp+58h+arg_18]; bool *
0x1800092ae  call    ?IsKwsEnabled@CSpeechMicDiagnostic@SpeechMicDiagnostic@@AEAAJPEA_N@Z; SpeechMicDiagnostic::CSpeechMicDiagnostic::IsKwsEnabled(bool *)
0x1800092b3  mov     ebx, eax
0x1800092b5  test    eax, eax
0x1800092b7  jns     short loc_1800092C3
0x1800092b9  mov     edx, 103h
0x1800092be  jmp     loc_18000910F
0x1800092c3  cmp     byte ptr [rsp+58h+arg_18], 0
0x1800092c8  setz    r8b
0x1800092cc  mov     eax, 2134h
0x1800092d1  cmp     dword ptr [rsi+28h], 2711h
0x1800092d8  cmovnz  eax, [rsi+28h]
0x1800092dc  mov     [rsp+58h+var_30], r8b; char
0x1800092e1  mov     [rsp+58h+var_38], eax; int
0x1800092e5  mov     r8, rbp
0x1800092e8  mov     rdx, rdi
0x1800092eb  mov     rcx, [rsi+8]; this
0x1800092ef  call    ?Start@CaptureStream@SpeechMicDiagnostic@@QEAAJAEAV?$shared_ptr@VDiagnosticStatus@SpeechMicDiagnostic@@@std@@PEBGKK_N@Z; SpeechMicDiagnostic::CaptureStream::Start(std::shared_ptr<SpeechMicDiagnostic::DiagnosticStatus> &,ushort const *,ulong,ulong,bool)
0x1800092f4  mov     ebx, eax
0x1800092f6  test    eax, eax
0x1800092f8  jns     short loc_180009304
0x1800092fa  mov     edx, 106h
0x1800092ff  jmp     loc_18000910F
0x180009304  xor     eax, eax
0x180009306  mov     rbx, [rsp+58h+arg_0]
0x18000930b  mov     rbp, [rsp+58h+arg_10]
0x180009310  add     rsp, 30h
0x180009314  pop     r14
0x180009316  pop     r13
0x180009318  pop     r12
0x18000931a  pop     rdi
0x18000931b  pop     rsi
0x18000931c  retn
```
