# CLEQClient::SAFE_CreateLEQ(int)

- ea: `0x18001f1a0`
- end: `0x18001f3bf`
- name: `?SAFE_CreateLEQ@CLEQClient@@AEAAJH@Z`
- size: `543`
- prototype: `__int64 __fastcall(CLEQClient *__hidden this, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18001eea0`

## callees

- `0x1800017b0`
- `0x1800021a8`
- `0x18001f1a0`
- `0x18001f3d0`
- `0x18004c070`
- `0x18004c250`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x18001f2a9`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x18001f2a9`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18001f1ef`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18001f1fe`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18001f2f2`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18001f1ef`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18001f1fe`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18001f2f2`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18001f38f`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18001f38f`
- `mfperfhelper!__imp_ippStaticInit` at `0x18001f241`
- `mfperfhelper!__imp_ippStaticInit` at `0x18001f241`
- `mfperfhelper!__imp_ippsFFTFree_R_32f` at `0x18001f1dc`
- `mfperfhelper!__imp_ippsFFTFree_R_32f` at `0x18001f1dc`

## pseudocode

```c
__int64 __fastcall CLEQClient::SAFE_CreateLEQ(CLEQClient *this)
{
  void *v1; // rdi
  int v3; // ebp
  int v4; // r15d
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  int v8; // edi
  int v9; // eax
  int v10; // edi
  void *v11; // rsi
  int v12; // eax
  char *v13; // rcx
  __int128 v15; // xmm1
  __int128 v16; // xmm1
  size_t Size; // [rsp+40h] [rbp-188h] BYREF
  __int128 v18; // [rsp+48h] [rbp-180h]
  __int128 v19; // [rsp+58h] [rbp-170h]
  _BYTE v20[288]; // [rsp+70h] [rbp-158h] BYREF

  v1 = *(void **)this;
  if ( *(_QWORD *)this )
  {
    ippsFFTFree_R_32f(*((_QWORD *)v1 + 29));
    _aligned_free(*((void **)v1 + 30));
    _aligned_free(*(void **)this);
  }
  v3 = *((_DWORD *)this + 12);
  v4 = *((_DWORD *)this + 11);
  memset_0(v20, 0, 0x118u);
  *(_QWORD *)this = 0;
  if ( *((_DWORD *)this + 10) == 1 )
  {
    v9 = ippStaticInit(v6, v5, v7);
    if ( !v9 || v9 == 20 )
    {
      Size = 0x12000000120LL;
      v8 = LEQ_init((int)this + 20, v4, v3, (unsigned int)v20, 0, 0, (__int64)&Size);
      if ( v8 >= 0 )
      {
        v10 = Size;
        v11 = _aligned_malloc((unsigned int)Size, 0x20u);
        if ( v11 )
        {
          v12 = LEQ_init((int)this + 20, v4, v3, (_DWORD)v11, (__int64)v11, v10, (__int64)&Size + 4);
          v8 = v12;
          if ( v12 >= 0 )
          {
            *(_QWORD *)this = v11;
            if ( !v12 )
              goto LABEL_15;
          }
          else
          {
            _aligned_free(v11);
          }
        }
        else
        {
          v8 = -2147024882;
        }
      }
    }
    else
    {
      v8 = -2147467259;
    }
  }
  else
  {
    v8 = -2147221504;
  }
  CLEQClient::SAFE_DeleteLEQ(this);
LABEL_15:
  v13 = *(char **)this;
  if ( !*(_QWORD *)this )
    return 2147500037LL;
  v15 = *(_OWORD *)(v13 + 216);
  *((_QWORD *)&v18 + 1) = *((_QWORD *)v13 + 26);
  *(_QWORD *)&v18 = 0x3F19999A40A00000LL;
  v19 = v15;
  LODWORD(v19) = 0;
  v16 = v19;
  *(_OWORD *)(v13 + 200) = v18;
  *(_OWORD *)(v13 + 216) = v16;
  LEQ_UpdateAttack();
  *((_DWORD *)this + 27) = MulDiv(*(_DWORD *)(*(_QWORD *)this + 68LL), 10000000, *((_DWORD *)this + 5));
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001f1a0  mov     r11, rsp
0x18001f1a3  push    rbx
0x18001f1a4  push    rdi
0x18001f1a5  push    r12
0x18001f1a7  push    r14
0x18001f1a9  sub     rsp, 1A8h
0x18001f1b0  mov     rax, cs:__security_cookie
0x18001f1b7  xor     rax, rsp
0x18001f1ba  mov     [rsp+1C8h+var_38], rax
0x18001f1c2  mov     rdi, [rcx]
0x18001f1c5  mov     rbx, rcx
0x18001f1c8  mov     [r11+10h], rbp
0x18001f1cc  mov     [r11-28h], r15
0x18001f1d0  test    rdi, rdi
0x18001f1d3  jz      short loc_18001F20A
0x18001f1d5  mov     rcx, [rdi+0E8h]
0x18001f1dc  call    cs:__imp_ippsFFTFree_R_32f
0x18001f1e3  nop     dword ptr [rax+rax+00h]
0x18001f1e8  mov     rcx, [rdi+0F0h]; Block
0x18001f1ef  call    cs:__imp__aligned_free
0x18001f1f6  nop     dword ptr [rax+rax+00h]
0x18001f1fb  mov     rcx, [rbx]; Block
0x18001f1fe  call    cs:__imp__aligned_free
0x18001f205  nop     dword ptr [rax+rax+00h]
0x18001f20a  mov     ebp, [rbx+30h]
0x18001f20d  lea     rcx, [rsp+1C8h+var_158]; void *
0x18001f212  mov     r15d, [rbx+2Ch]
0x18001f216  xor     edx, edx; Val
0x18001f218  mov     r8d, 118h; Size
0x18001f21e  mov     [rsp+1C8h+arg_10], rsi
0x18001f226  call    memset_0
0x18001f22b  xor     r12d, r12d
0x18001f22e  mov     [rbx], r12
0x18001f231  cmp     dword ptr [rbx+28h], 1
0x18001f235  jz      short loc_18001F241
0x18001f237  mov     edi, 80040000h
0x18001f23c  jmp     loc_18001F307
0x18001f241  call    cs:__imp_ippStaticInit
0x18001f248  nop     dword ptr [rax+rax+00h]
0x18001f24d  test    eax, eax
0x18001f24f  jz      short loc_18001F260
0x18001f251  cmp     eax, 14h
0x18001f254  jz      short loc_18001F260
0x18001f256  mov     edi, 80004005h
0x18001f25b  jmp     loc_18001F307
0x18001f260  lea     rax, [rsp+1C8h+Size]
0x18001f265  mov     dword ptr [rsp+1C8h+Size], 120h
0x18001f26d  mov     [rsp+1C8h+var_198], rax
0x18001f272  lea     r9, [rsp+1C8h+var_158]
0x18001f277  mov     [rsp+1C8h+var_1A0], r12d
0x18001f27c  lea     rcx, [rbx+14h]
0x18001f280  mov     r8d, ebp
0x18001f283  mov     [rsp+1C8h+var_1A8], r12
0x18001f288  mov     edx, r15d
0x18001f28b  mov     dword ptr [rsp+1C8h+Size+4], 120h
0x18001f293  call    LEQ_init
0x18001f298  mov     edi, eax
0x18001f29a  test    eax, eax
0x18001f29c  js      short loc_18001F307
0x18001f29e  mov     edi, dword ptr [rsp+1C8h+Size]
0x18001f2a2  mov     edx, 20h ; ' '; Alignment
0x18001f2a7  mov     ecx, edi; Size
0x18001f2a9  call    cs:__imp__aligned_malloc
0x18001f2b0  nop     dword ptr [rax+rax+00h]
0x18001f2b5  mov     rsi, rax
0x18001f2b8  test    rax, rax
0x18001f2bb  jnz     short loc_18001F2C4
0x18001f2bd  mov     edi, 8007000Eh
0x18001f2c2  jmp     short loc_18001F307
0x18001f2c4  lea     rax, [rsp+1C8h+Size+4]
0x18001f2c9  mov     r9, rsi
0x18001f2cc  mov     [rsp+1C8h+var_198], rax
0x18001f2d1  lea     rcx, [rbx+14h]
0x18001f2d5  mov     [rsp+1C8h+var_1A0], edi
0x18001f2d9  mov     r8d, ebp
0x18001f2dc  mov     edx, r15d
0x18001f2df  mov     [rsp+1C8h+var_1A8], rsi
0x18001f2e4  call    LEQ_init
0x18001f2e9  mov     edi, eax
0x18001f2eb  test    eax, eax
0x18001f2ed  jns     short loc_18001F300
0x18001f2ef  mov     rcx, rsi; Block
0x18001f2f2  call    cs:__imp__aligned_free
0x18001f2f9  nop     dword ptr [rax+rax+00h]
0x18001f2fe  jmp     short loc_18001F307
0x18001f300  mov     [rbx], rsi
0x18001f303  test    eax, eax
0x18001f305  jz      short loc_18001F30F
0x18001f307  mov     rcx, rbx; this
0x18001f30a  call    ?SAFE_DeleteLEQ@CLEQClient@@AEAAJXZ; CLEQClient::SAFE_DeleteLEQ(void)
0x18001f30f  mov     rcx, [rbx]
0x18001f312  mov     r15, [rsp+1C8h+var_28]
0x18001f31a  mov     rsi, [rsp+1C8h+arg_10]
0x18001f322  mov     rbp, [rsp+1C8h+arg_8]
0x18001f32a  test    rcx, rcx
0x18001f32d  jnz     short loc_18001F336
0x18001f32f  mov     eax, 80004005h
0x18001f334  jmp     short loc_18001F3A0
0x18001f336  movups  xmm0, xmmword ptr [rcx+0C8h]
0x18001f33d  movups  xmm1, xmmword ptr [rcx+0D8h]
0x18001f344  movups  [rsp+1C8h+var_180], xmm0
0x18001f349  mov     dword ptr [rsp+1C8h+var_180], 40A00000h
0x18001f351  movups  [rsp+1C8h+var_170], xmm1
0x18001f356  mov     dword ptr [rsp+1C8h+var_180+4], 3F19999Ah
0x18001f35e  movups  xmm0, [rsp+1C8h+var_180]
0x18001f363  mov     dword ptr [rsp+1C8h+var_170], r12d
0x18001f368  movups  xmm1, [rsp+1C8h+var_170]
0x18001f36d  movups  xmmword ptr [rcx+0C8h], xmm0
0x18001f374  movups  xmmword ptr [rcx+0D8h], xmm1
0x18001f37b  call    LEQ_UpdateAttack
0x18001f380  mov     rcx, [rbx]
0x18001f383  mov     edx, 989680h; nNumerator
0x18001f388  mov     r8d, [rbx+14h]; nDenominator
0x18001f38c  mov     ecx, [rcx+44h]; nNumber
0x18001f38f  call    cs:__imp_MulDiv
0x18001f396  nop     dword ptr [rax+rax+00h]
0x18001f39b  mov     [rbx+6Ch], eax
0x18001f39e  mov     eax, edi
0x18001f3a0  mov     rcx, [rsp+1C8h+var_38]
0x18001f3a8  xor     rcx, rsp; StackCookie
0x18001f3ab  call    __security_check_cookie
0x18001f3b0  add     rsp, 1A8h
0x18001f3b7  pop     r14
0x18001f3b9  pop     r12
0x18001f3bb  pop     rdi
0x18001f3bc  pop     rbx
0x18001f3bd  retn
```
