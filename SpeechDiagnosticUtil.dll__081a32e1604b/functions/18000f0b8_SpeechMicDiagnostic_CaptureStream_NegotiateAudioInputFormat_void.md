# SpeechMicDiagnostic::CaptureStream::NegotiateAudioInputFormat(void)

- ea: `0x18000f0b8`
- end: `0x18000f269`
- name: `?NegotiateAudioInputFormat@CaptureStream@SpeechMicDiagnostic@@AEAAJXZ`
- size: `433`
- prototype: `__int64 __fastcall(SpeechMicDiagnostic::CaptureStream *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f5f0`

## callees

- `0x180005b28`
- `0x18000f0b8`
- `0x180011010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000f10a`
- `ole32!CoTaskMemAlloc` at `0x18000f10a`
- `ole32!CoTaskMemFree` at `0x18000f0d0`
- `ole32!CoTaskMemFree` at `0x18000f0d0`

## pseudocode

```c
__int64 __fastcall SpeechMicDiagnostic::CaptureStream::NegotiateAudioInputFormat(LPVOID *this)
{
  GUID *v1; // rsi
  _QWORD *v3; // rbx
  unsigned __int8 *Data4; // r14
  char *v5; // rax
  const GUID *v6; // rax
  int v7; // ebx
  _WORD *v8; // rax
  __int64 v9; // rdx
  unsigned __int16 *v10; // rax
  LPVOID v11; // rcx
  int v13; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v1 = (GUID *)(this + 13);
  v3 = this + 15;
  CoTaskMemFree(this[15]);
  *v3 = 0;
  if ( !v1 || !v3 )
  {
    v7 = -2147024809;
LABEL_20:
    v9 = 203;
    goto LABEL_21;
  }
  Data4 = v1[1].Data4;
  if ( v1 != (GUID *)-24LL )
    *(_DWORD *)Data4 = 0;
  v5 = (char *)CoTaskMemAlloc(0x12u);
  *v3 = v5;
  if ( v5 )
  {
    *(_DWORD *)v5 = 3;
    *((_DWORD *)v5 + 3) = 0x200000;
    *(_QWORD *)(v5 + 4) = 16000;
    *((_WORD *)v5 + 8) = 0;
    v6 = &SPDFID_WaveFormatEx;
    if ( v1 == (GUID *)-24LL )
    {
      v7 = -2147024809;
    }
    else
    {
      v7 = 0;
      *(_DWORD *)Data4 = 1;
    }
  }
  else
  {
    v6 = &GUID_NULL;
    v7 = -2147024882;
  }
  *v1 = *v6;
  if ( v7 < 0 )
    goto LABEL_20;
  if ( *((_DWORD *)this + 32) && (v8 = this[15]) != 0 )
  {
    v8[1] = 1;
    *((_WORD *)this[15] + 6) = *((unsigned __int16 *)this[15] + 1) * *((unsigned __int16 *)this[15] + 7) / 8;
    *((_DWORD *)this[15] + 2) = *((_DWORD *)this[15] + 1) * *((unsigned __int16 *)this[15] + 6);
    *((_DWORD *)this + 32) = 0;
    v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, LPVOID))(*(_QWORD *)*this + 128LL))(*this, v1, this[15]);
    if ( v7 >= 0 )
    {
      v10 = (unsigned __int16 *)this[15];
      v11 = *this;
      *((_DWORD *)this + 38) = 256;
      *((_DWORD *)this + 38) = v10[6] << 8;
      v7 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 200LL))(v11);
      if ( v7 >= 0 )
        return 0;
      v9 = 212;
    }
    else
    {
      v9 = 207;
    }
  }
  else
  {
    v7 = -2147024891;
    v9 = 204;
  }
LABEL_21:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
    (const char *)(unsigned int)v7,
    v13);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000f0b8  push    rbx
0x18000f0ba  push    rsi
0x18000f0bb  push    rdi
0x18000f0bc  push    r14
0x18000f0be  sub     rsp, 28h
0x18000f0c2  lea     rsi, [rcx+68h]
0x18000f0c6  mov     rdi, rcx
0x18000f0c9  lea     rbx, [rsi+10h]
0x18000f0cd  mov     rcx, [rbx]; pv
0x18000f0d0  call    cs:__imp_CoTaskMemFree
0x18000f0d7  nop     dword ptr [rax+rax+00h]
0x18000f0dc  mov     qword ptr [rbx], 0
0x18000f0e3  test    rsi, rsi
0x18000f0e6  jz      loc_18000F23E
0x18000f0ec  test    rbx, rbx
0x18000f0ef  jz      loc_18000F23E
0x18000f0f5  lea     r14, [rsi+18h]
0x18000f0f9  test    r14, r14
0x18000f0fc  jz      short loc_18000F105
0x18000f0fe  mov     dword ptr [r14], 0
0x18000f105  mov     ecx, 12h; cb
0x18000f10a  call    cs:__imp_CoTaskMemAlloc
0x18000f111  nop     dword ptr [rax+rax+00h]
0x18000f116  mov     [rbx], rax
0x18000f119  mov     rdx, rax
0x18000f11c  mov     r8d, 1
0x18000f122  test    rax, rax
0x18000f125  jz      short loc_18000F15C
0x18000f127  mov     dword ptr [rax], 3
0x18000f12d  mov     dword ptr [rax+0Ch], 200000h
0x18000f134  mov     qword ptr [rax+4], 3E80h
0x18000f13c  xor     eax, eax
0x18000f13e  mov     [rdx+10h], ax
0x18000f142  lea     rax, SPDFID_WaveFormatEx
0x18000f149  test    r14, r14
0x18000f14c  jz      short loc_18000F155
0x18000f14e  xor     ebx, ebx
0x18000f150  mov     [r14], r8d
0x18000f153  jmp     short loc_18000F168
0x18000f155  mov     ebx, 80070057h
0x18000f15a  jmp     short loc_18000F168
0x18000f15c  lea     rax, GUID_NULL
0x18000f163  mov     ebx, 8007000Eh
0x18000f168  movups  xmm0, xmmword ptr [rax]
0x18000f16b  movdqu  xmmword ptr [rsi], xmm0
0x18000f16f  test    ebx, ebx
0x18000f171  js      loc_18000F243
0x18000f177  cmp     dword ptr [rdi+80h], 0
0x18000f17e  jz      loc_18000F232
0x18000f184  mov     rax, [rdi+78h]
0x18000f188  test    rax, rax
0x18000f18b  jz      loc_18000F232
0x18000f191  mov     [rax+2], r8w
0x18000f196  mov     r8, [rdi+78h]
0x18000f19a  movzx   eax, word ptr [r8+0Eh]
0x18000f19f  movzx   ecx, word ptr [r8+2]
0x18000f1a4  imul    eax, ecx
0x18000f1a7  cdq
0x18000f1a8  and     edx, 7
0x18000f1ab  add     eax, edx
0x18000f1ad  mov     rdx, rsi
0x18000f1b0  sar     eax, 3
0x18000f1b3  mov     [r8+0Ch], ax
0x18000f1b8  mov     rcx, [rdi+78h]
0x18000f1bc  movzx   eax, word ptr [rcx+0Ch]
0x18000f1c0  imul    eax, [rcx+4]
0x18000f1c4  mov     [rcx+8], eax
0x18000f1c7  mov     dword ptr [rdi+80h], 0
0x18000f1d1  mov     rcx, [rdi]
0x18000f1d4  mov     r8, [rdi+78h]
0x18000f1d8  mov     rax, [rcx]
0x18000f1db  mov     rax, [rax+80h]
0x18000f1e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1e7  mov     ebx, eax
0x18000f1e9  test    eax, eax
0x18000f1eb  jns     short loc_18000F1F4
0x18000f1ed  mov     edx, 0CFh
0x18000f1f2  jmp     short loc_18000F248
0x18000f1f4  mov     rax, [rdi+78h]
0x18000f1f8  mov     rcx, [rdi]
0x18000f1fb  mov     dword ptr [rdi+98h], 100h
0x18000f205  movzx   edx, word ptr [rax+0Ch]
0x18000f209  shl     edx, 8
0x18000f20c  mov     [rdi+98h], edx
0x18000f212  mov     rax, [rcx]
0x18000f215  mov     rax, [rax+0C8h]
0x18000f21c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f221  mov     ebx, eax
0x18000f223  test    eax, eax
0x18000f225  jns     short loc_18000F22E
0x18000f227  mov     edx, 0D4h
0x18000f22c  jmp     short loc_18000F248
0x18000f22e  xor     eax, eax
0x18000f230  jmp     short loc_18000F25E
0x18000f232  mov     ebx, 80070005h
0x18000f237  mov     edx, 0CCh
0x18000f23c  jmp     short loc_18000F248
0x18000f23e  mov     ebx, 80070057h
0x18000f243  mov     edx, 0CBh; void *
0x18000f248  mov     rcx, [rsp+48h]; this
0x18000f24d  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000f254  mov     r9d, ebx; char *
0x18000f257  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f25c  mov     eax, ebx
0x18000f25e  add     rsp, 28h
0x18000f262  pop     r14
0x18000f264  pop     rdi
0x18000f265  pop     rsi
0x18000f266  pop     rbx
0x18000f267  retn
```
