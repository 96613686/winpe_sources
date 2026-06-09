# Microsoft::Windows::Performance::CArgonNTNtImagePathDecoder::CArgonNTNtImagePathDecoder(Performance::NtImagePathDecoder::CLocalNtImagePathDecoder *)

- ea: `0x18001dd5c`
- end: `0x18001dea5`
- name: `??0CArgonNTNtImagePathDecoder@Performance@Windows@Microsoft@@QEAA@PEAVCLocalNtImagePathDecoder@NtImagePathDecoder@1@@Z`
- size: `329`
- prototype: `Microsoft::Windows::Performance::CArgonNTNtImagePathDecoder *__fastcall(Microsoft::Windows::Performance::CArgonNTNtImagePathDecoder *this, struct Performance::NtImagePathDecoder::CLocalNtImagePathDecoder *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002476c`

## callees

- `0x180002d01`
- `0x180012140`
- `0x18001dd5c`
- `0x1800233b4`

## pseudocode

```c
Microsoft::Windows::Performance::CArgonNTNtImagePathDecoder *__fastcall Microsoft::Windows::Performance::CArgonNTNtImagePathDecoder::CArgonNTNtImagePathDecoder(
        Microsoft::Windows::Performance::CArgonNTNtImagePathDecoder *this,
        struct Performance::NtImagePathDecoder::CLocalNtImagePathDecoder *a2)
{
  _QWORD *v3; // r14
  unsigned __int64 *v4; // rbx
  _QWORD *v5; // rsi
  unsigned __int64 *v6; // rbp
  _QWORD *v7; // r9
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rdx
  __int64 v10; // rbx
  _QWORD *v11; // r9

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  v3 = (_QWORD *)((char *)this + 48);
  *((_OWORD *)this + 3) = 0;
  v4 = (unsigned __int64 *)((char *)this + 64);
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 7;
  *((_WORD *)this + 24) = 0;
  v5 = (_QWORD *)((char *)this + 80);
  *((_OWORD *)this + 5) = 0;
  v6 = (unsigned __int64 *)((char *)this + 96);
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 7;
  *((_WORD *)this + 40) = 0;
  *((_QWORD *)this + 14) = a2;
  if ( !*((_BYTE *)a2 + 112) )
    Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::Initialize(a2);
  v7 = (_QWORD *)(*((_QWORD *)this + 14) + 48LL);
  if ( *(_QWORD *)(*((_QWORD *)this + 14) + 72LL) > 7u )
    v7 = (_QWORD *)*v7;
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( *((_WORD *)v7 + v9) );
  if ( v9 > v3[3] )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v3);
  }
  else
  {
    if ( v3[3] > 7u )
      v3 = (_QWORD *)*v3;
    *v4 = v9;
    v10 = 2 * v9;
    memmove_0(v3, v7, 2 * v9);
    *(_WORD *)((char *)v3 + v10) = 0;
  }
  v11 = (_QWORD *)(*((_QWORD *)this + 14) + 80LL);
  if ( *(_QWORD *)(*((_QWORD *)this + 14) + 104LL) > 7u )
    v11 = (_QWORD *)*v11;
  do
    ++v8;
  while ( *((_WORD *)v11 + v8) );
  if ( v8 > v5[3] )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v5);
  }
  else
  {
    if ( v5[3] > 7u )
      v5 = (_QWORD *)*v5;
    *v6 = v8;
    memmove_0(v5, v11, 2 * v8);
    *((_WORD *)v5 + v8) = 0;
  }
  return this;
}

```

## disassembly

```asm
0x18001dd5c  mov     [rsp+arg_8], rbx
0x18001dd61  mov     [rsp+arg_10], rbp
0x18001dd66  mov     [rsp+arg_0], rcx
0x18001dd6b  push    rsi
0x18001dd6c  push    rdi
0x18001dd6d  push    r12
0x18001dd6f  push    r14
0x18001dd71  push    r15
0x18001dd73  sub     rsp, 20h
0x18001dd77  mov     r15, rcx
0x18001dd7a  xor     r12d, r12d
0x18001dd7d  mov     [rcx], r12
0x18001dd80  mov     [rcx+8], r12
0x18001dd84  mov     [rcx+10h], r12
0x18001dd88  mov     [rcx+18h], r12
0x18001dd8c  mov     [rcx+20h], r12
0x18001dd90  mov     [rcx+28h], r12
0x18001dd94  lea     r14, [rcx+30h]
0x18001dd98  xorps   xmm0, xmm0
0x18001dd9b  movups  xmmword ptr [r14], xmm0
0x18001dd9f  lea     rbx, [r14+10h]
0x18001dda3  mov     [rbx], r12
0x18001dda6  mov     qword ptr [r14+18h], 7
0x18001ddae  mov     [r14], r12w
0x18001ddb2  lea     rsi, [rcx+50h]
0x18001ddb6  movups  xmmword ptr [rsi], xmm0
0x18001ddb9  lea     rbp, [rsi+10h]
0x18001ddbd  mov     [rbp+0], r12
0x18001ddc1  mov     qword ptr [rsi+18h], 7
0x18001ddc9  mov     [rsi], r12w
0x18001ddcd  mov     [rcx+70h], rdx
0x18001ddd1  cmp     [rdx+70h], r12b
0x18001ddd5  jnz     short loc_18001DDDF
0x18001ddd7  mov     rcx, rdx; this
0x18001ddda  call    ?Initialize@CLocalNtImagePathDecoder@NtImagePathDecoder@Performance@@AEAAXXZ; Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::Initialize(void)
0x18001dddf  mov     r9, [r15+70h]
0x18001dde3  add     r9, 30h ; '0'
0x18001dde7  cmp     qword ptr [r9+18h], 7
0x18001ddec  jbe     short loc_18001DDF1
0x18001ddee  mov     r9, [r9]
0x18001ddf1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001ddf5  mov     rdx, rdi
0x18001ddf8  inc     rdx
0x18001ddfb  cmp     [r9+rdx*2], r12w
0x18001de00  jnz     short loc_18001DDF8
0x18001de02  cmp     rdx, [r14+18h]
0x18001de06  ja      short loc_18001DE2E
0x18001de08  cmp     qword ptr [r14+18h], 7
0x18001de0d  jbe     short loc_18001DE12
0x18001de0f  mov     r14, [r14]
0x18001de12  mov     [rbx], rdx
0x18001de15  lea     rbx, [rdx+rdx]
0x18001de19  mov     r8, rbx; Size
0x18001de1c  mov     rdx, r9; Src
0x18001de1f  mov     rcx, r14; void *
0x18001de22  call    memmove_0
0x18001de27  mov     [rbx+r14], r12w
0x18001de2c  jmp     short loc_18001DE36
0x18001de2e  mov     rcx, r14
0x18001de31  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001de36  mov     r9, [r15+70h]
0x18001de3a  add     r9, 50h ; 'P'
0x18001de3e  cmp     qword ptr [r9+18h], 7
0x18001de43  jbe     short loc_18001DE48
0x18001de45  mov     r9, [r9]
0x18001de48  inc     rdi
0x18001de4b  cmp     [r9+rdi*2], r12w
0x18001de50  jnz     short loc_18001DE48
0x18001de52  cmp     rdi, [rsi+18h]
0x18001de56  ja      short loc_18001DE7F
0x18001de58  cmp     qword ptr [rsi+18h], 7
0x18001de5d  jbe     short loc_18001DE62
0x18001de5f  mov     rsi, [rsi]
0x18001de62  mov     [rbp+0], rdi
0x18001de66  lea     rbx, [rdi+rdi]
0x18001de6a  mov     r8, rbx; Size
0x18001de6d  mov     rdx, r9; Src
0x18001de70  mov     rcx, rsi; void *
0x18001de73  call    memmove_0
0x18001de78  mov     [rbx+rsi], r12w
0x18001de7d  jmp     short loc_18001DE8B
0x18001de7f  mov     rdx, rdi
0x18001de82  mov     rcx, rsi
0x18001de85  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001de8a  nop
0x18001de8b  mov     rax, r15
0x18001de8e  mov     rbx, [rsp+48h+arg_8]
0x18001de93  mov     rbp, [rsp+48h+arg_10]
0x18001de98  add     rsp, 20h
0x18001de9c  pop     r15
0x18001de9e  pop     r14
0x18001dea0  pop     r12
0x18001dea2  pop     rdi
0x18001dea3  pop     rsi
0x18001dea4  retn
```
