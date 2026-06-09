# wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)

- ea: `0x18000744c`
- end: `0x180007507`
- name: `??0?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z`
- size: `187`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007e38`
- `0x180008040`
- `0x180008190`
- `0x1800082d0`
- `0x1800084a0`
- `0x180008d10`
- `0x180008fe0`
- `0x180009330`
- `0x18000d2a0`

## callees

- `0x180003290`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rbx
  _QWORD *v4; // rcx

  *(_QWORD *)a1 = &wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable';
  v3 = a1 + 8;
  *(_DWORD *)(a1 + 8) = 0;
  *(_BYTE *)(a1 + 12) = 0;
  *(_BYTE *)(a1 + 72) = 0;
  *(_DWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = a2;
  *(_QWORD *)(a1 + 64) = 0;
  *(_DWORD *)(a1 + 80) = 0;
  v4 = (_QWORD *)(a1 + 88);
  v4[19] = 0;
  v4[20] = 0;
  memset_0(v4, 0, 0x98u);
  *(_DWORD *)(v3 + 248) = 1;
  *(_QWORD *)(v3 + 256) = 0;
  *(_QWORD *)(a1 + 272) = v3;
  *(_QWORD *)(a1 + 280) = 0;
  *(_QWORD *)(a1 + 288) = 0;
  *(_QWORD *)(a1 + 296) = a1;
  *(_QWORD *)(a1 + 304) = 0;
  *(_DWORD *)(a1 + 312) = 0;
  *(_QWORD *)(a1 + 320) = a1 + 48;
  *(_BYTE *)(a1 + 328) = 0;
  return a1;
}

```

## disassembly

```asm
0x18000744c  mov     [rsp+arg_0], rbx
0x180007451  mov     [rsp+arg_8], rsi
0x180007456  push    rdi
0x180007457  sub     rsp, 20h
0x18000745b  mov     rdi, rcx
0x18000745e  lea     rax, ??_7?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@6B@; const wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::`vftable'
0x180007465  mov     [rcx], rax
0x180007468  lea     rbx, [rcx+8]
0x18000746c  xor     esi, esi
0x18000746e  mov     [rbx], esi
0x180007470  mov     [rbx+4], sil
0x180007474  mov     [rbx+40h], sil
0x180007478  mov     [rbx+28h], esi
0x18000747b  mov     [rbx+30h], rdx
0x18000747f  mov     [rbx+38h], rsi
0x180007483  mov     [rbx+48h], esi
0x180007486  lea     rcx, [rbx+50h]; void *
0x18000748a  mov     [rcx+98h], rsi
0x180007491  mov     [rcx+0A0h], rsi
0x180007498  xor     edx, edx; Val
0x18000749a  mov     r8d, 98h; Size
0x1800074a0  call    memset_0
0x1800074a5  mov     dword ptr [rbx+0F8h], 1
0x1800074af  xor     eax, eax
0x1800074b1  mov     [rbx+100h], rax
0x1800074b8  mov     [rdi+110h], rbx
0x1800074bf  mov     [rdi+118h], rsi
0x1800074c6  mov     [rdi+120h], rsi
0x1800074cd  mov     [rdi+128h], rdi
0x1800074d4  mov     [rdi+130h], rsi
0x1800074db  mov     [rdi+138h], esi
0x1800074e1  lea     rax, [rdi+30h]
0x1800074e5  mov     [rdi+140h], rax
0x1800074ec  mov     [rdi+148h], sil
0x1800074f3  mov     rax, rdi
0x1800074f6  mov     rbx, [rsp+28h+arg_0]
0x1800074fb  mov     rsi, [rsp+28h+arg_8]
0x180007500  add     rsp, 20h
0x180007504  pop     rdi
0x180007505  retn
```
