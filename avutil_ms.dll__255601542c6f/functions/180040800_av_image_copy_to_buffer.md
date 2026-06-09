# av_image_copy_to_buffer

- ea: `0x180040800`
- end: `0x180040a38`
- name: `av_image_copy_to_buffer`
- size: `568`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180040800`
- `0x180041120`
- `0x1800414c0`
- `0x180042ad0`
- `0x18004c700`
- `0x180078c2c`
- `0x180078e90`
- `0x18007a960`

## pseudocode

```c
__int64 __fastcall av_image_copy_to_buffer(
        __m128i *a1,
        int a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        int a8)
{
  __m128i *v10; // r12
  __int64 v11; // rdi
  int v12; // esi
  unsigned int v13; // r15d
  __int64 v14; // rax
  __int64 v15; // rbp
  __int64 v16; // rcx
  int *v17; // r9
  int v18; // eax
  __int64 v19; // r14
  __int64 v20; // rbx
  int *v21; // rsi
  char v22; // cl
  const __m128i *v23; // r15
  int v24; // edx
  int v25; // r8d
  __m128i *v26; // r14
  __int64 v27; // r12
  int buffer_size; // [rsp+30h] [rbp-88h]
  __m128i *v30; // [rsp+38h] [rbp-80h]
  __int64 v32; // [rsp+50h] [rbp-68h]
  __int64 v33; // [rsp+58h] [rbp-60h]
  _BYTE v34[16]; // [rsp+60h] [rbp-58h] BYREF

  v10 = a1;
  v11 = 0;
  v30 = a1;
  v12 = 0;
  buffer_size = av_image_get_buffer_size(a5, a6, a7, a8);
  v13 = buffer_size;
  v14 = av_pix_fmt_desc_get(a5);
  v32 = v14;
  v15 = v14;
  if ( buffer_size > a2 || buffer_size < 0 || !v14 )
    return 4294967274LL;
  _mm_lfence();
  v16 = *(unsigned __int8 *)(v14 + 8);
  if ( *(_BYTE *)(v14 + 8) )
  {
    v17 = (int *)(v14 + 24);
    do
    {
      v18 = *v17;
      v17 += 5;
      if ( v18 <= v12 )
        v18 = v12;
      v12 = v18;
      --v16;
    }
    while ( v16 );
  }
  if ( (int)av_image_fill_linesizes((__int64)v34, a5, a6) < 0 )
  {
    av_log(
      0,
      0,
      "Assertion %s failed at %s:%d\n",
      "ret >= 0",
      "C:/__w/1/s/FFmpegInterop/ffmpeg/libavutil/imgutils.c",
      521);
    abort();
  }
  _mm_lfence();
  v19 = v12 + 1;
  v33 = v19;
  if ( v12 + 1 > 0 )
  {
    v20 = 0;
    v21 = (int *)v34;
    do
    {
      if ( v20 == 1 || (v22 = 0, v20 == 2) )
        v22 = *(_BYTE *)(v15 + 10);
      v23 = *(const __m128i **)(a3 + 8 * v20);
      v24 = (int)((1 << v22) + a7 - 1) >> v22;
      if ( v24 > 0 )
      {
        v25 = *v21;
        v26 = v30;
        v27 = (unsigned int)v24;
        do
        {
          sub_18007A960(v26, v23, v25);
          v25 = *v21;
          v26 = (__m128i *)((char *)v26 + (-a8 & (unsigned __int64)(*v21 + a8 - 1)));
          v23 = (const __m128i *)((char *)v23 + *(int *)((char *)v21 + a4 - (_QWORD)v34));
          --v27;
        }
        while ( v27 );
        v15 = v32;
        v11 = 0;
        v30 = v26;
        v19 = v33;
      }
      ++v20;
      ++v21;
    }
    while ( v20 < v19 );
    v13 = buffer_size;
    v10 = v30;
  }
  if ( (*(_BYTE *)(v15 + 16) & 2) != 0 )
  {
    do
    {
      v10->m128i_i32[v11] = *(_DWORD *)(v11 * 4 + *(_QWORD *)(a3 + 8));
      ++v11;
    }
    while ( v11 < 256 );
    return (unsigned int)buffer_size;
  }
  return v13;
}

```

## disassembly

```asm
0x180040800  mov     [rsp+arg_8], rbx
0x180040805  push    rbp
0x180040806  push    rsi
0x180040807  push    rdi
0x180040808  push    r12
0x18004080a  push    r13
0x18004080c  push    r14
0x18004080e  push    r15
0x180040810  sub     rsp, 80h
0x180040817  mov     rax, cs:__security_cookie
0x18004081e  xor     rax, rsp
0x180040821  mov     [rsp+0B8h+var_48], rax
0x180040826  mov     eax, [rsp+0B8h+arg_38]
0x18004082d  mov     r13, r9
0x180040830  mov     r14d, [rsp+0B8h+arg_20]
0x180040838  mov     ebx, edx
0x18004083a  mov     edx, [rsp+0B8h+arg_28]
0x180040841  mov     r12, rcx
0x180040844  mov     [rsp+0B8h+var_78], r8
0x180040849  xor     edi, edi
0x18004084b  mov     r8d, [rsp+0B8h+arg_30]
0x180040853  mov     r9d, eax
0x180040856  mov     [rsp+0B8h+var_80], rcx
0x18004085b  mov     esi, edi
0x18004085d  mov     ecx, r14d
0x180040860  mov     [rsp+0B8h+var_84], eax
0x180040864  call    av_image_get_buffer_size
0x180040869  mov     ecx, r14d
0x18004086c  mov     [rsp+0B8h+var_88], eax
0x180040870  mov     r15d, eax
0x180040873  call    av_pix_fmt_desc_get
0x180040878  mov     [rsp+0B8h+var_68], rax
0x18004087d  mov     rbp, rax
0x180040880  cmp     r15d, ebx
0x180040883  jg      loc_1800409DA
0x180040889  test    r15d, r15d
0x18004088c  js      loc_1800409DA
0x180040892  test    rax, rax
0x180040895  jz      loc_1800409DA
0x18004089b  lfence
0x18004089e  movzx   ecx, byte ptr [rax+8]
0x1800408a2  test    rcx, rcx
0x1800408a5  jz      short loc_1800408BF
0x1800408a7  lea     r9, [rax+18h]
0x1800408ab  mov     eax, [r9]
0x1800408ae  cmp     eax, esi
0x1800408b0  lea     r9, [r9+14h]
0x1800408b4  cmovle  eax, esi
0x1800408b7  mov     esi, eax
0x1800408b9  sub     rcx, 1
0x1800408bd  jnz     short loc_1800408AB
0x1800408bf  mov     r8d, [rsp+0B8h+arg_28]
0x1800408c7  lea     rcx, [rsp+0B8h+var_58]
0x1800408cc  mov     edx, r14d
0x1800408cf  call    av_image_fill_linesizes
0x1800408d4  test    eax, eax
0x1800408d6  js      loc_180040A07
0x1800408dc  lfence
0x1800408df  lea     eax, [rsi+1]
0x1800408e2  movsxd  r14, eax
0x1800408e5  mov     [rsp+0B8h+var_60], r14
0x1800408ea  test    eax, eax
0x1800408ec  jle     loc_1800409AD
0x1800408f2  lea     rax, [rsp+0B8h+var_58]
0x1800408f7  mov     rbx, rdi
0x1800408fa  sub     r13, rax
0x1800408fd  lea     rsi, [rsp+0B8h+var_58]
0x180040902  mov     [rsp+0B8h+var_70], r13
0x180040907  cmp     rbx, 1
0x18004090b  jz      short loc_180040915
0x18004090d  mov     ecx, edi
0x18004090f  cmp     rbx, 2
0x180040913  jnz     short loc_180040919
0x180040915  movzx   ecx, byte ptr [rbp+0Ah]
0x180040919  mov     rax, [rsp+0B8h+var_78]
0x18004091e  mov     edx, [rsp+0B8h+arg_30]
0x180040925  dec     edx
0x180040927  mov     r15, [rax+rbx*8]
0x18004092b  mov     eax, 1
0x180040930  shl     eax, cl
0x180040932  add     edx, eax
0x180040934  sar     edx, cl
0x180040936  test    edx, edx
0x180040938  jle     short loc_180040993
0x18004093a  mov     edi, [rsp+0B8h+var_84]
0x18004093e  mov     eax, edi
0x180040940  mov     r8d, [rsi]
0x180040943  neg     eax
0x180040945  mov     r14, [rsp+0B8h+var_80]
0x18004094a  mov     rbp, [rsp+0B8h+var_70]
0x18004094f  movsxd  r13, eax
0x180040952  mov     r12d, edx
0x180040955  movsxd  r8, r8d
0x180040958  mov     rdx, r15
0x18004095b  mov     rcx, r14
0x18004095e  call    sub_18007A960
0x180040963  mov     r8d, [rsi]
0x180040966  lea     eax, [rdi-1]
0x180040969  add     eax, r8d
0x18004096c  movsxd  rcx, eax
0x18004096f  movsxd  rax, dword ptr [rsi+rbp]
0x180040973  and     rcx, r13
0x180040976  add     r14, rcx
0x180040979  add     r15, rax
0x18004097c  sub     r12, 1
0x180040980  jnz     short loc_180040955
0x180040982  mov     rbp, [rsp+0B8h+var_68]
0x180040987  xor     edi, edi
0x180040989  mov     [rsp+0B8h+var_80], r14
0x18004098e  mov     r14, [rsp+0B8h+var_60]
0x180040993  inc     rbx
0x180040996  add     rsi, 4
0x18004099a  cmp     rbx, r14
0x18004099d  jl      loc_180040907
0x1800409a3  mov     r15d, [rsp+0B8h+var_88]
0x1800409a8  mov     r12, [rsp+0B8h+var_80]
0x1800409ad  test    byte ptr [rbp+10h], 2
0x1800409b1  jz      short loc_1800409D5
0x1800409b3  mov     r15, [rsp+0B8h+var_78]
0x1800409b8  mov     rax, [r15+8]
0x1800409bc  mov     ecx, [rdi+rax]
0x1800409bf  mov     [r12+rdi], ecx
0x1800409c3  add     rdi, 4
0x1800409c7  cmp     rdi, 400h
0x1800409ce  jl      short loc_1800409B8
0x1800409d0  mov     r15d, [rsp+0B8h+var_88]
0x1800409d5  mov     eax, r15d
0x1800409d8  jmp     short loc_1800409DF
0x1800409da  mov     eax, 0FFFFFFEAh
0x1800409df  mov     rcx, [rsp+0B8h+var_48]
0x1800409e4  xor     rcx, rsp; StackCookie
0x1800409e7  call    __security_check_cookie
0x1800409ec  mov     rbx, [rsp+0B8h+arg_8]
0x1800409f4  add     rsp, 80h
0x1800409fb  pop     r15
0x1800409fd  pop     r14
0x1800409ff  pop     r13
0x180040a01  pop     r12
0x180040a03  pop     rdi
0x180040a04  pop     rsi
0x180040a05  pop     rbp
0x180040a06  retn
0x180040a07  lea     rax, aCW1SFfmpeginte_10; "C:/__w/1/s/FFmpegInterop/ffmpeg/libavut"...
0x180040a0e  mov     [rsp+0B8h+var_90], 209h
0x180040a16  lea     r9, aRet0_0; "ret >= 0"
0x180040a1d  mov     [rsp+0B8h+var_98], rax
0x180040a22  lea     r8, aAssertionSFail; "Assertion %s failed at %s:%d\n"
0x180040a29  xor     edx, edx
0x180040a2b  xor     ecx, ecx
0x180040a2d  call    av_log
0x180040a32  call    abort
```
