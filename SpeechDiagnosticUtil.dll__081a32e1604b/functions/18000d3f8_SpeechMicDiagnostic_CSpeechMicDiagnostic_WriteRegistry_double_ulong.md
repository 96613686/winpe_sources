# SpeechMicDiagnostic::CSpeechMicDiagnostic::WriteRegistry(double,ulong)

- ea: `0x18000d3f8`
- end: `0x18000d4a9`
- name: `?WriteRegistry@CSpeechMicDiagnostic@SpeechMicDiagnostic@@QEAAJNK@Z`
- size: `177`
- prototype: `int(SpeechMicDiagnostic::CSpeechMicDiagnostic *__hidden this, double, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d2a0`

## callees

- `0x180005b28`
- `0x18000d3f8`
- `0x18000d4b0`

## pseudocode

```c
__int64 __fastcall SpeechMicDiagnostic::CSpeechMicDiagnostic::WriteRegistry(
        SpeechMicDiagnostic::CSpeechMicDiagnostic *this,
        double a2,
        int a3)
{
  __int64 v3; // rax
  const unsigned __int16 *v5; // rsi
  int v6; // ebx
  __int64 v7; // rdx
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = *((_QWORD *)this + 1);
  v5 = *(const unsigned __int16 **)(v3 + 144);
  if ( !v5 )
  {
    v6 = -2147024809;
    v7 = 433;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\speechmicdiagnostic.cpp",
      (const char *)(unsigned int)v6,
      v9);
    return (unsigned int)v6;
  }
  if ( a2 >= 0.0 )
  {
    v6 = SpeechMicDiagnostic::CSpeechMicDiagnostic::WriteRegistryDwordValue(
           this,
           L"SOFTWARE\\Microsoft\\Speech_OneCore\\AudioInput\\MicWiz\\Snr",
           *(const unsigned __int16 **)(v3 + 144),
           (int)(a2 + 0.5));
    if ( v6 < 0 )
    {
      v7 = 438;
      goto LABEL_3;
    }
  }
  if ( a3 != 10001 )
  {
    v6 = SpeechMicDiagnostic::CSpeechMicDiagnostic::WriteRegistryDwordValue(
           this,
           L"SOFTWARE\\Microsoft\\Speech_OneCore\\AudioInput\\MicWiz\\Volume",
           v5,
           a3);
    if ( v6 < 0 )
    {
      v7 = 444;
      goto LABEL_3;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000d3f8  mov     [rsp+arg_0], rbx
0x18000d3fd  mov     [rsp+arg_8], rsi
0x18000d402  push    rdi; int
0x18000d403  sub     rsp, 20h
0x18000d407  mov     rax, [rcx+8]
0x18000d40b  mov     edi, r8d
0x18000d40e  mov     rsi, [rax+90h]
0x18000d415  test    rsi, rsi
0x18000d418  jnz     short loc_18000D43C
0x18000d41a  mov     ebx, 80070057h
0x18000d41f  mov     edx, 1B1h; void *
0x18000d424  mov     rcx, [rsp+28h]; this
0x18000d429  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000d430  mov     r9d, ebx; char *
0x18000d433  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d438  mov     eax, ebx
0x18000d43a  jmp     short loc_18000D498
0x18000d43c  comisd  xmm1, cs:__real@0000000000000000
0x18000d444  jb      short loc_18000D46F
0x18000d446  addsd   xmm1, cs:__real@3fe0000000000000
0x18000d44e  mov     r8, rsi; unsigned __int16 *
0x18000d451  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Speech_OneCore\\Au"...
0x18000d458  cvttsd2si r9, xmm1; unsigned int
0x18000d45d  call    ?WriteRegistryDwordValue@CSpeechMicDiagnostic@SpeechMicDiagnostic@@AEAAJPEBG0K@Z; SpeechMicDiagnostic::CSpeechMicDiagnostic::WriteRegistryDwordValue(ushort const *,ushort const *,ulong)
0x18000d462  mov     ebx, eax
0x18000d464  test    eax, eax
0x18000d466  jns     short loc_18000D46F
0x18000d468  mov     edx, 1B6h
0x18000d46d  jmp     short loc_18000D424
0x18000d46f  cmp     edi, 2711h
0x18000d475  jz      short loc_18000D496
0x18000d477  mov     r9d, edi; unsigned int
0x18000d47a  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Speech_OneCore\\Au"...
0x18000d481  mov     r8, rsi; unsigned __int16 *
0x18000d484  call    ?WriteRegistryDwordValue@CSpeechMicDiagnostic@SpeechMicDiagnostic@@AEAAJPEBG0K@Z; SpeechMicDiagnostic::CSpeechMicDiagnostic::WriteRegistryDwordValue(ushort const *,ushort const *,ulong)
0x18000d489  mov     ebx, eax
0x18000d48b  test    eax, eax
0x18000d48d  jns     short loc_18000D496
0x18000d48f  mov     edx, 1BCh
0x18000d494  jmp     short loc_18000D424
0x18000d496  xor     eax, eax
0x18000d498  mov     rbx, [rsp+28h+arg_0]
0x18000d49d  mov     rsi, [rsp+28h+arg_8]
0x18000d4a2  add     rsp, 20h
0x18000d4a6  pop     rdi
0x18000d4a7  retn
```
