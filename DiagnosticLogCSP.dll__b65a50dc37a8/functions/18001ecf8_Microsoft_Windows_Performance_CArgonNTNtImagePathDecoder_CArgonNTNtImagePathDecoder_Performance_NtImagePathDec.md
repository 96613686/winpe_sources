# Microsoft::Windows::Performance::CArgonNTNtImagePathDecoder::CArgonNTNtImagePathDecoder(Performance::NtImagePathDecoder::CLocalNtImagePathDecoder *)

- ea: `0x18001ecf8`
- end: `0x18001ee42`
- name: `??0CArgonNTNtImagePathDecoder@Performance@Windows@Microsoft@@QEAA@PEAVCLocalNtImagePathDecoder@NtImagePathDecoder@1@@Z`
- size: `330`
- prototype: `_QWORD(Microsoft::Windows::Performance::CArgonNTNtImagePathDecoder *__hidden this, struct Performance::NtImagePathDecoder::CLocalNtImagePathDecoder *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800258d4`

## callees

- `0x180002d31`
- `0x180012afc`
- `0x18001ecf8`
- `0x180024494`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18001ecf8  mov     [rsp+arg_8], rbx
0x18001ecfd  mov     [rsp+arg_10], rbp
0x18001ed02  mov     [rsp+arg_0], rcx
0x18001ed07  push    rsi
0x18001ed08  push    rdi
0x18001ed09  push    r12
0x18001ed0b  push    r14
0x18001ed0d  push    r15
0x18001ed0f  sub     rsp, 20h
0x18001ed13  mov     r15, rcx
0x18001ed16  xor     r12d, r12d
0x18001ed19  mov     [rcx], r12
0x18001ed1c  mov     [rcx+8], r12
0x18001ed20  mov     [rcx+10h], r12
0x18001ed24  mov     [rcx+18h], r12
0x18001ed28  mov     [rcx+20h], r12
0x18001ed2c  mov     [rcx+28h], r12
0x18001ed30  lea     r14, [rcx+30h]
0x18001ed34  xorps   xmm0, xmm0
0x18001ed37  movups  xmmword ptr [r14], xmm0
0x18001ed3b  lea     rbx, [r14+10h]
0x18001ed3f  mov     [rbx], r12
0x18001ed42  mov     qword ptr [r14+18h], 7
0x18001ed4a  mov     [r14], r12w
0x18001ed4e  lea     rsi, [rcx+50h]
0x18001ed52  movups  xmmword ptr [rsi], xmm0
0x18001ed55  lea     rbp, [rsi+10h]
0x18001ed59  mov     [rbp+0], r12
0x18001ed5d  mov     qword ptr [rsi+18h], 7
0x18001ed65  mov     [rsi], r12w
0x18001ed69  mov     [rcx+70h], rdx
0x18001ed6d  cmp     [rdx+70h], r12b
0x18001ed71  jnz     short loc_18001ED7B
0x18001ed73  mov     rcx, rdx; this
0x18001ed76  call    ?Initialize@CLocalNtImagePathDecoder@NtImagePathDecoder@Performance@@AEAAXXZ; Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::Initialize(void)
0x18001ed7b  mov     r9, [r15+70h]
0x18001ed7f  add     r9, 30h ; '0'
0x18001ed83  cmp     qword ptr [r9+18h], 7
0x18001ed88  jbe     short loc_18001ED8D
0x18001ed8a  mov     r9, [r9]
0x18001ed8d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001ed91  mov     rdx, rdi
0x18001ed94  inc     rdx
0x18001ed97  cmp     [r9+rdx*2], r12w
0x18001ed9c  jnz     short loc_18001ED94
0x18001ed9e  cmp     rdx, [r14+18h]
0x18001eda2  ja      short loc_18001EDCA
0x18001eda4  cmp     qword ptr [r14+18h], 7
0x18001eda9  jbe     short loc_18001EDAE
0x18001edab  mov     r14, [r14]
0x18001edae  mov     [rbx], rdx
0x18001edb1  lea     rbx, [rdx+rdx]
0x18001edb5  mov     r8, rbx; Size
0x18001edb8  mov     rdx, r9; Src
0x18001edbb  mov     rcx, r14; void *
0x18001edbe  call    memmove_0
0x18001edc3  mov     [rbx+r14], r12w
0x18001edc8  jmp     short loc_18001EDD2
0x18001edca  mov     rcx, r14
0x18001edcd  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001edd2  mov     r9, [r15+70h]
0x18001edd6  add     r9, 50h ; 'P'
0x18001edda  cmp     qword ptr [r9+18h], 7
0x18001eddf  jbe     short loc_18001EDE4
0x18001ede1  mov     r9, [r9]
0x18001ede4  inc     rdi
0x18001ede7  cmp     [r9+rdi*2], r12w
0x18001edec  jnz     short loc_18001EDE4
0x18001edee  cmp     rdi, [rsi+18h]
0x18001edf2  ja      short loc_18001EE1B
0x18001edf4  cmp     qword ptr [rsi+18h], 7
0x18001edf9  jbe     short loc_18001EDFE
0x18001edfb  mov     rsi, [rsi]
0x18001edfe  mov     [rbp+0], rdi
0x18001ee02  lea     rbx, [rdi+rdi]
0x18001ee06  mov     r8, rbx; Size
0x18001ee09  mov     rdx, r9; Src
0x18001ee0c  mov     rcx, rsi; void *
0x18001ee0f  call    memmove_0
0x18001ee14  mov     [rbx+rsi], r12w
0x18001ee19  jmp     short loc_18001EE27
0x18001ee1b  mov     rdx, rdi
0x18001ee1e  mov     rcx, rsi
0x18001ee21  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001ee26  nop
0x18001ee27  mov     rax, r15
0x18001ee2a  mov     rbx, [rsp+48h+arg_8]
0x18001ee2f  mov     rbp, [rsp+48h+arg_10]
0x18001ee34  add     rsp, 20h
0x18001ee38  pop     r15
0x18001ee3a  pop     r14
0x18001ee3c  pop     r12
0x18001ee3e  pop     rdi
0x18001ee3f  pop     rsi
0x18001ee40  retn
```
