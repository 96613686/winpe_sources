# av_film_grain_params_create_side_data

- ea: `0x18003a620`
- end: `0x18003a712`
- name: `av_film_grain_params_create_side_data`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x18003a620`
- `0x18003b750`
- `0x180078ec0`
- `0x18007a960`
- `0x18007b020`

## pseudocode

```c
__int64 __fastcall av_film_grain_params_create_side_data(__int64 a1)
{
  int v1; // eax
  __int64 result; // rax
  __m128i *v3; // rbx
  __m128i v4[3]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v5; // [rsp+50h] [rbp-B0h]
  int v6; // [rsp+58h] [rbp-A8h]
  __int128 v7; // [rsp+5Ch] [rbp-A4h]
  __int64 v8; // [rsp+6Ch] [rbp-94h]
  __int64 v9; // [rsp+74h] [rbp-8Ch]
  __int64 v10; // [rsp+7Ch] [rbp-84h]
  __int128 v11; // [rsp+84h] [rbp-7Ch]
  __int128 v12; // [rsp+94h] [rbp-6Ch]
  __int64 v13; // [rsp+A4h] [rbp-5Ch]
  __int64 v14; // [rsp+ACh] [rbp-54h]
  __int128 v15; // [rsp+B4h] [rbp-4Ch]
  __int64 v16; // [rsp+C4h] [rbp-3Ch]
  __int128 v17; // [rsp+CCh] [rbp-34h]
  __int128 v18; // [rsp+DCh] [rbp-24h]
  __int128 v19; // [rsp+ECh] [rbp-14h]
  int v20; // [rsp+FCh] [rbp-4h]
  __int128 v21; // [rsp+100h] [rbp+0h]
  __int64 v22; // [rsp+110h] [rbp+10h]
  __int64 v23; // [rsp+118h] [rbp+18h]
  __int64 v24; // [rsp+120h] [rbp+20h]
  __m128i v25[661]; // [rsp+128h] [rbp+28h] BYREF
  int v26; // [rsp+2A7Ch] [rbp+297Ch]

  result = av_frame_new_side_data(a1, 0x15u, (unsigned int)(v1 - 32));
  if ( result )
  {
    v3 = *(__m128i **)(result + 8);
    v4[2] = _mm_load_si128((const __m128i *)&xmmword_180085B60);
    v4[0].m128i_i32[0] = 0;
    v4[0].m128i_i64[1] = 0;
    v5 = 0;
    v6 = 0;
    v14 = 0;
    v24 = 0;
    v17 = 0;
    v8 = 0;
    v18 = 0;
    v9 = 0;
    v19 = 0;
    v10 = 0;
    v4[1] = 0;
    v7 = 0;
    v13 = 0;
    v11 = 0;
    v16 = 0;
    v12 = 0;
    v20 = 0;
    v15 = 0;
    v22 = 0;
    v21 = 0;
    v23 = 0;
    sub_18007B020(v25, 0, 0x2954u);
    v26 = 0;
    sub_18007A960(v3, v4, 0x2A60u);
    return (__int64)v3;
  }
  return result;
}

```

## disassembly

```asm
0x18003a620  mov     [rsp-8+arg_0], rbx
0x18003a625  push    rbp
0x18003a626  lea     rbp, [rsp-2980h]
0x18003a62e  mov     eax, 2A80h
0x18003a633  call    __alloca_probe
0x18003a638  sub     rsp, rax
0x18003a63b  mov     edx, 15h
0x18003a640  lea     r8d, [rax-20h]
0x18003a644  call    av_frame_new_side_data
0x18003a649  xor     ecx, ecx
0x18003a64b  test    rax, rax
0x18003a64e  jz      loc_18003A701
0x18003a654  movdqa  xmm1, cs:xmmword_180085B60
0x18003a65c  xorps   xmm0, xmm0
0x18003a65f  mov     rbx, [rax+8]
0x18003a663  xor     edx, edx
0x18003a665  xor     eax, eax
0x18003a667  movdqa  [rsp+2A80h+var_2A40], xmm1
0x18003a66d  xorps   xmm1, xmm1
0x18003a670  mov     [rsp+2A80h+var_2A60], ecx
0x18003a674  mov     [rsp+2A80h+var_2A58], rcx
0x18003a679  mov     r8d, 2954h
0x18003a67f  mov     [rsp+2A80h+var_2A30], rcx
0x18003a684  mov     [rsp+2A80h+var_2A28], ecx
0x18003a688  mov     [rbp+2980h+var_29D4], rcx
0x18003a68c  mov     [rbp+2980h+var_2960], rcx
0x18003a690  lea     rcx, [rbp+2980h+var_2958]
0x18003a694  movups  [rbp+2980h+var_29B4], xmm1
0x18003a698  mov     [rsp+2A80h+var_2A14], rax
0x18003a69d  movups  [rbp+2980h+var_29A4], xmm1
0x18003a6a1  mov     [rsp+2A80h+var_2A0C], rax
0x18003a6a6  movups  [rbp+2980h+var_2994], xmm1
0x18003a6aa  mov     [rsp+2A80h+var_2A04], rax
0x18003a6af  movdqa  [rsp+2A80h+var_2A50], xmm0
0x18003a6b5  movups  [rsp+2A80h+var_2A24], xmm0
0x18003a6ba  mov     [rbp+2980h+var_29DC], rax
0x18003a6be  movups  [rbp+2980h+var_29FC], xmm0
0x18003a6c2  mov     [rbp+2980h+var_29BC], rax
0x18003a6c6  movups  [rbp+2980h+var_29EC], xmm0
0x18003a6ca  mov     [rbp+2980h+var_2984], eax
0x18003a6cd  movups  [rbp+2980h+var_29CC], xmm0
0x18003a6d1  mov     [rbp+2980h+var_2970], rax
0x18003a6d5  movdqa  [rbp+2980h+var_2980], xmm0
0x18003a6da  mov     [rbp+2980h+var_2968], rax
0x18003a6de  call    sub_18007B020
0x18003a6e3  xor     eax, eax
0x18003a6e5  lea     rdx, [rsp+2A80h+var_2A60]
0x18003a6ea  mov     r8d, 2A60h
0x18003a6f0  mov     [rbp+2980h+var_4], eax
0x18003a6f6  mov     rcx, rbx
0x18003a6f9  call    sub_18007A960
0x18003a6fe  mov     rax, rbx
0x18003a701  mov     rbx, [rsp+2A80h+arg_0]
0x18003a709  add     rsp, 2A80h
0x18003a710  pop     rbp
0x18003a711  retn
```
