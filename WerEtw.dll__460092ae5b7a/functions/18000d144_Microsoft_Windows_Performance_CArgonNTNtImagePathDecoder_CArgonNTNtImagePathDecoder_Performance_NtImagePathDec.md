# Microsoft::Windows::Performance::CArgonNTNtImagePathDecoder::CArgonNTNtImagePathDecoder(Performance::NtImagePathDecoder::CLocalNtImagePathDecoder *)

- ea: `0x18000d144`
- end: `0x18000d28d`
- name: `??0CArgonNTNtImagePathDecoder@Performance@Windows@Microsoft@@QEAA@PEAVCLocalNtImagePathDecoder@NtImagePathDecoder@1@@Z`
- size: `329`
- prototype: `Microsoft::Windows::Performance::CArgonNTNtImagePathDecoder *__fastcall(Microsoft::Windows::Performance::CArgonNTNtImagePathDecoder *this, struct Performance::NtImagePathDecoder::CLocalNtImagePathDecoder *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180013890`

## callees

- `0x1800027bd`
- `0x18000c5c0`
- `0x18000d144`
- `0x1800127d0`

## pseudocode

```c
Microsoft::Windows::Performance::CArgonNTNtImagePathDecoder *__fastcall Microsoft::Windows::Performance::CArgonNTNtImagePathDecoder::CArgonNTNtImagePathDecoder(
        Microsoft::Windows::Performance::CArgonNTNtImagePathDecoder *this,
        struct Performance::NtImagePathDecoder::CLocalNtImagePathDecoder *a2,
        __int64 a3)
{
  _QWORD *v4; // r14
  unsigned __int64 *v5; // rbx
  _QWORD *v6; // rsi
  unsigned __int64 *v7; // rbp
  _QWORD *v8; // r9
  unsigned __int64 v9; // rdi
  unsigned __int64 v10; // rdx
  __int64 v11; // rbx
  __int64 v12; // r8
  _QWORD *v13; // r9

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  v4 = (_QWORD *)((char *)this + 48);
  *((_OWORD *)this + 3) = 0;
  v5 = (unsigned __int64 *)((char *)this + 64);
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 7;
  *((_WORD *)this + 24) = 0;
  v6 = (_QWORD *)((char *)this + 80);
  *((_OWORD *)this + 5) = 0;
  v7 = (unsigned __int64 *)((char *)this + 96);
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 7;
  *((_WORD *)this + 40) = 0;
  *((_QWORD *)this + 14) = a2;
  if ( !*((_BYTE *)a2 + 112) )
    Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::Initialize(a2);
  v8 = (_QWORD *)(*((_QWORD *)this + 14) + 48LL);
  if ( *(_QWORD *)(*((_QWORD *)this + 14) + 72LL) > 7u )
    v8 = (_QWORD *)*v8;
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( *((_WORD *)v8 + v10) );
  if ( v10 > v4[3] )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v4, v10, a3, v8);
  }
  else
  {
    if ( v4[3] > 7u )
      v4 = (_QWORD *)*v4;
    *v5 = v10;
    v11 = 2 * v10;
    memmove_0(v4, v8, 2 * v10);
    *(_WORD *)((char *)v4 + v11) = 0;
  }
  v13 = (_QWORD *)(*((_QWORD *)this + 14) + 80LL);
  if ( *(_QWORD *)(*((_QWORD *)this + 14) + 104LL) > 7u )
    v13 = (_QWORD *)*v13;
  do
    ++v9;
  while ( *((_WORD *)v13 + v9) );
  if ( v9 > v6[3] )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v6, v9, v12, v13);
  }
  else
  {
    if ( v6[3] > 7u )
      v6 = (_QWORD *)*v6;
    *v7 = v9;
    memmove_0(v6, v13, 2 * v9);
    *((_WORD *)v6 + v9) = 0;
  }
  return this;
}

```

## disassembly

```asm
0x18000d144  mov     [rsp+arg_8], rbx
0x18000d149  mov     [rsp+arg_10], rbp
0x18000d14e  mov     [rsp+arg_0], rcx
0x18000d153  push    rsi
0x18000d154  push    rdi
0x18000d155  push    r12
0x18000d157  push    r14
0x18000d159  push    r15
0x18000d15b  sub     rsp, 20h
0x18000d15f  mov     r15, rcx
0x18000d162  xor     r12d, r12d
0x18000d165  mov     [rcx], r12
0x18000d168  mov     [rcx+8], r12
0x18000d16c  mov     [rcx+10h], r12
0x18000d170  mov     [rcx+18h], r12
0x18000d174  mov     [rcx+20h], r12
0x18000d178  mov     [rcx+28h], r12
0x18000d17c  lea     r14, [rcx+30h]
0x18000d180  xorps   xmm0, xmm0
0x18000d183  movups  xmmword ptr [r14], xmm0
0x18000d187  lea     rbx, [r14+10h]
0x18000d18b  mov     [rbx], r12
0x18000d18e  mov     qword ptr [r14+18h], 7
0x18000d196  mov     [r14], r12w
0x18000d19a  lea     rsi, [rcx+50h]
0x18000d19e  movups  xmmword ptr [rsi], xmm0
0x18000d1a1  lea     rbp, [rsi+10h]
0x18000d1a5  mov     [rbp+0], r12
0x18000d1a9  mov     qword ptr [rsi+18h], 7
0x18000d1b1  mov     [rsi], r12w
0x18000d1b5  mov     [rcx+70h], rdx
0x18000d1b9  cmp     [rdx+70h], r12b
0x18000d1bd  jnz     short loc_18000D1C7
0x18000d1bf  mov     rcx, rdx; this
0x18000d1c2  call    ?Initialize@CLocalNtImagePathDecoder@NtImagePathDecoder@Performance@@AEAAXXZ; Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::Initialize(void)
0x18000d1c7  mov     r9, [r15+70h]
0x18000d1cb  add     r9, 30h ; '0'
0x18000d1cf  cmp     qword ptr [r9+18h], 7
0x18000d1d4  jbe     short loc_18000D1D9
0x18000d1d6  mov     r9, [r9]
0x18000d1d9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000d1dd  mov     rdx, rdi
0x18000d1e0  inc     rdx
0x18000d1e3  cmp     [r9+rdx*2], r12w
0x18000d1e8  jnz     short loc_18000D1E0
0x18000d1ea  cmp     rdx, [r14+18h]
0x18000d1ee  ja      short loc_18000D216
0x18000d1f0  cmp     qword ptr [r14+18h], 7
0x18000d1f5  jbe     short loc_18000D1FA
0x18000d1f7  mov     r14, [r14]
0x18000d1fa  mov     [rbx], rdx
0x18000d1fd  lea     rbx, [rdx+rdx]
0x18000d201  mov     r8, rbx; Size
0x18000d204  mov     rdx, r9; Src
0x18000d207  mov     rcx, r14; void *
0x18000d20a  call    memmove_0
0x18000d20f  mov     [rbx+r14], r12w
0x18000d214  jmp     short loc_18000D21E
0x18000d216  mov     rcx, r14
0x18000d219  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000d21e  mov     r9, [r15+70h]
0x18000d222  add     r9, 50h ; 'P'
0x18000d226  cmp     qword ptr [r9+18h], 7
0x18000d22b  jbe     short loc_18000D230
0x18000d22d  mov     r9, [r9]
0x18000d230  inc     rdi
0x18000d233  cmp     [r9+rdi*2], r12w
0x18000d238  jnz     short loc_18000D230
0x18000d23a  cmp     rdi, [rsi+18h]
0x18000d23e  ja      short loc_18000D267
0x18000d240  cmp     qword ptr [rsi+18h], 7
0x18000d245  jbe     short loc_18000D24A
0x18000d247  mov     rsi, [rsi]
0x18000d24a  mov     [rbp+0], rdi
0x18000d24e  lea     rbx, [rdi+rdi]
0x18000d252  mov     r8, rbx; Size
0x18000d255  mov     rdx, r9; Src
0x18000d258  mov     rcx, rsi; void *
0x18000d25b  call    memmove_0
0x18000d260  mov     [rbx+rsi], r12w
0x18000d265  jmp     short loc_18000D273
0x18000d267  mov     rdx, rdi
0x18000d26a  mov     rcx, rsi
0x18000d26d  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000d272  nop
0x18000d273  mov     rax, r15
0x18000d276  mov     rbx, [rsp+48h+arg_8]
0x18000d27b  mov     rbp, [rsp+48h+arg_10]
0x18000d280  add     rsp, 20h
0x18000d284  pop     r15
0x18000d286  pop     r14
0x18000d288  pop     r12
0x18000d28a  pop     rdi
0x18000d28b  pop     rsi
0x18000d28c  retn
```
