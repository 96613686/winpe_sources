# JsonHelpersInternal::JsonReader::ReadStringFromStreamAlloc(ushort const * *)

- ea: `0x1800209f8`
- end: `0x180020cfd`
- name: `?ReadStringFromStreamAlloc@JsonReader@JsonHelpersInternal@@AEAAJPEAPEBG@Z`
- size: `773`
- prototype: `__int64 __fastcall(JsonHelpersInternal::JsonReader *__hidden this, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001faec`
- `0x18001ff90`

## callees

- `0x180002746`
- `0x1800209f8`
- `0x18002443c`
- `0x180032310`

## import_xrefs

- `msvcrt!_wtoi` at `0x180020c70`
- `msvcrt!_wtoi` at `0x180020c70`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020cbe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020cbe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020a36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020a96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020caf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020a36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020a96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020caf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020a90`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020ae8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020a90`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020ae8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall JsonHelpersInternal::JsonReader::ReadStringFromStreamAlloc(
        JsonHelpersInternal::JsonReader *this,
        const unsigned __int16 **a2)
{
  HANDLE ProcessHeap; // rax
  __int64 v5; // r10
  __int64 v6; // r8
  __int16 v7; // r9
  void *v8; // r8
  __int64 v9; // rcx
  __int16 v10; // dx
  int v11; // ebx
  unsigned __int64 v13; // rdx
  __int64 v14; // r9
  unsigned __int64 v15; // r8
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  wchar_t v28; // r8
  wchar_t v29; // r8
  wchar_t v30; // r8
  wchar_t v31; // cx
  __int16 v32; // ax
  size_t v33; // rdi
  HANDLE v34; // rax
  unsigned __int16 *v35; // rax
  const unsigned __int16 *v36; // rbx
  __int16 v37; // [rsp+20h] [rbp-60h] BYREF
  HANDLE hHeap[4]; // [rsp+28h] [rbp-58h] BYREF
  LPVOID lpMem[2]; // [rsp+48h] [rbp-38h]
  wchar_t String[8]; // [rsp+58h] [rbp-28h] BYREF

  memset(hHeap, 0, sizeof(hHeap));
  ProcessHeap = GetProcessHeap();
  v5 = *((_QWORD *)this + 1);
  while ( 1 )
  {
    v6 = *(_QWORD *)this;
    v7 = *(_WORD *)(v5 + 2LL * *(_QWORD *)this);
    if ( v7 != 9
      && *(_WORD *)(v5 + 2LL * *(_QWORD *)this) != 10
      && *(_WORD *)(v5 + 2LL * *(_QWORD *)this) != 13
      && *(_WORD *)(v5 + 2LL * *(_QWORD *)this) != 32 )
    {
      break;
    }
    *(_QWORD *)this = v6 + 1;
    if ( !v7 )
      *(_QWORD *)this = v6;
  }
  v8 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  if ( v8 )
    HeapFree(ProcessHeap, 0, v8);
  hHeap[3] = (HANDLE)4096;
  hHeap[0] = GetProcessHeap();
  *(_OWORD *)&hHeap[1] = 0;
  *(_OWORD *)lpMem = 0;
  v9 = *(_QWORD *)this;
  v10 = *(_WORD *)(*((_QWORD *)this + 1) + 2LL * (*(_QWORD *)this)++);
  if ( v10 )
  {
    if ( v10 != 34 )
      goto LABEL_12;
    while ( 1 )
    {
      v13 = *(_QWORD *)this;
      v14 = *((_QWORD *)this + 1);
      v15 = *(_QWORD *)this + 1LL;
      v16 = *(unsigned __int16 *)(v14 + 2LL * *(_QWORD *)this);
      *(_QWORD *)this = v15;
      if ( (_WORD)v16 )
        v13 = v15;
      else
        *(_QWORD *)this = v13;
      v37 = v16;
      if ( !v16 )
        goto LABEL_12;
      v17 = v16 - 1;
      if ( !v17 )
        goto LABEL_12;
      v18 = v17 - 33;
      if ( !v18 )
      {
        v33 = (size_t)hHeap[1];
        v34 = GetProcessHeap();
        v35 = (unsigned __int16 *)HeapAlloc(v34, 0, v33 + 2);
        v36 = v35;
        if ( v35 )
        {
          if ( v33 )
            memcpy_0(v35, lpMem[1], v33);
          v36[v33 >> 1] = 0;
          *a2 = v36;
          v11 = 0;
        }
        else
        {
          v11 = -2147024882;
        }
        goto LABEL_13;
      }
      if ( v18 == 58 )
      {
        v19 = *(unsigned __int16 *)(v14 + 2 * v13);
        v15 = v13 + 1;
        *(_QWORD *)this = v13 + 1;
        if ( (_WORD)v19 )
          ++v13;
        else
          *(_QWORD *)this = v13;
        v37 = v19;
        v20 = v19 - 34;
        if ( v20 )
        {
          v21 = v20 - 13;
          if ( v21 )
          {
            v22 = v21 - 45;
            if ( v22 )
            {
              v23 = v22 - 6;
              if ( !v23 )
              {
                v37 = 8;
                goto LABEL_24;
              }
              v24 = v23 - 4;
              if ( !v24 )
              {
                v32 = 12;
                goto LABEL_54;
              }
              v25 = v24 - 8;
              if ( !v25 )
              {
                v32 = 10;
LABEL_54:
                v37 = v32;
                goto LABEL_24;
              }
              v26 = v25 - 4;
              if ( v26 )
              {
                v27 = v26 - 2;
                if ( v27 )
                {
                  if ( v27 != 1 )
                    goto LABEL_12;
                  v28 = *(_WORD *)(v14 + 2 * v13);
                  *(_QWORD *)this = v13 + 1;
                  if ( v28 )
                    ++v13;
                  else
                    *(_QWORD *)this = v13;
                  String[0] = v28;
                  v29 = *(_WORD *)(v14 + 2 * v13);
                  *(_QWORD *)this = v13 + 1;
                  if ( v29 )
                    ++v13;
                  else
                    *(_QWORD *)this = v13;
                  String[1] = v29;
                  v30 = *(_WORD *)(v14 + 2 * v13);
                  *(_QWORD *)this = v13 + 1;
                  if ( v30 )
                    ++v13;
                  else
                    *(_QWORD *)this = v13;
                  String[2] = v30;
                  v31 = *(_WORD *)(v14 + 2 * v13);
                  *(_QWORD *)this = v13 + 1;
                  if ( !v31 )
                    *(_QWORD *)this = v13;
                  String[3] = v31;
                  String[4] = 0;
                  v32 = _wtoi(String);
                  goto LABEL_54;
                }
                v37 = 9;
              }
              else
              {
                v37 = 13;
              }
            }
          }
        }
      }
LABEL_24:
      v11 = RtlMemoryStream::Write((RtlMemoryStream *)hHeap, &v37, v15);
      if ( v11 < 0 )
        goto LABEL_13;
    }
  }
  *(_QWORD *)this = v9;
LABEL_12:
  v11 = -2147024883;
LABEL_13:
  if ( lpMem[1] )
    HeapFree(hHeap[0], 0, lpMem[1]);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800209f8  mov     [rsp-38h+arg_10], rbx
0x1800209fd  push    rbp
0x1800209fe  push    rsi
0x1800209ff  push    rdi
0x180020a00  push    r12
0x180020a02  push    r13
0x180020a04  push    r14
0x180020a06  push    r15
0x180020a08  mov     rbp, rsp
0x180020a0b  sub     rsp, 80h
0x180020a12  movaps  [rsp+80h+var_10], xmm6
0x180020a17  mov     rax, cs:__security_cookie
0x180020a1e  xor     rax, rsp
0x180020a21  mov     [rbp+var_18], rax
0x180020a25  xorps   xmm6, xmm6
0x180020a28  mov     rsi, rdx
0x180020a2b  movups  xmmword ptr [rbp+hHeap], xmm6
0x180020a2f  mov     rdi, rcx
0x180020a32  movups  [rbp+var_48], xmm6
0x180020a36  call    cs:__imp_GetProcessHeap
0x180020a3c  mov     r10, [rdi+8]
0x180020a40  mov     r13d, 9
0x180020a46  mov     r11, rax
0x180020a49  mov     r8, [rdi]
0x180020a4c  movzx   r9d, word ptr [r10+r8*2]
0x180020a51  mov     edx, r9d
0x180020a54  sub     edx, r13d
0x180020a57  jz      short loc_180020A68
0x180020a59  sub     edx, 1
0x180020a5c  jz      short loc_180020A68
0x180020a5e  sub     edx, 3
0x180020a61  jz      short loc_180020A68
0x180020a63  cmp     edx, 13h
0x180020a66  jnz     short loc_180020A7C
0x180020a68  lea     rax, [r8+1]
0x180020a6c  mov     [rdi], rax
0x180020a6f  xor     eax, eax
0x180020a71  cmp     ax, r9w
0x180020a75  jnz     short loc_180020A49
0x180020a77  mov     [rdi], r8
0x180020a7a  jmp     short loc_180020A49
0x180020a7c  psrldq  xmm6, 8
0x180020a81  movq    r8, xmm6; lpMem
0x180020a86  test    r8, r8
0x180020a89  jz      short loc_180020A96
0x180020a8b  xor     edx, edx; dwFlags
0x180020a8d  mov     rcx, r11; hHeap
0x180020a90  call    cs:__imp_HeapFree
0x180020a96  call    cs:__imp_GetProcessHeap
0x180020a9c  xorps   xmm0, xmm0
0x180020a9f  mov     qword ptr [rbp+var_48+8], 1000h
0x180020aa7  xorps   xmm1, xmm1
0x180020aaa  mov     [rbp+hHeap], rax
0x180020aae  movdqu  xmmword ptr [rbp+hHeap+8], xmm0
0x180020ab3  movdqu  xmmword ptr [rbp+lpMem], xmm1
0x180020ab8  mov     rcx, [rdi]
0x180020abb  mov     rax, [rdi+8]
0x180020abf  movzx   edx, word ptr [rax+rcx*2]
0x180020ac3  lea     rax, [rcx+1]
0x180020ac7  mov     [rdi], rax
0x180020aca  xor     eax, eax
0x180020acc  cmp     ax, dx
0x180020acf  jnz     short loc_180020B1C
0x180020ad1  mov     [rdi], rcx
0x180020ad4  mov     ebx, 8007000Dh
0x180020ad9  mov     r8, [rbp+lpMem+8]; lpMem
0x180020add  test    r8, r8
0x180020ae0  jz      short loc_180020AEE
0x180020ae2  mov     rcx, [rbp+hHeap]; hHeap
0x180020ae6  xor     edx, edx; dwFlags
0x180020ae8  call    cs:__imp_HeapFree
0x180020aee  mov     eax, ebx
0x180020af0  mov     rcx, [rbp+var_18]
0x180020af4  xor     rcx, rsp; StackCookie
0x180020af7  call    __security_check_cookie
0x180020afc  mov     rbx, [rsp+80h+arg_10]
0x180020b04  movaps  xmm6, [rsp+80h+var_10]
0x180020b09  add     rsp, 80h
0x180020b10  pop     r15
0x180020b12  pop     r14
0x180020b14  pop     r13
0x180020b16  pop     r12
0x180020b18  pop     rdi
0x180020b19  pop     rsi
0x180020b1a  pop     rbp
0x180020b1b  retn
0x180020b1c  mov     r12d, 22h ; '"'
0x180020b22  cmp     r12w, dx
0x180020b26  jnz     short loc_180020AD4
0x180020b28  lea     r14d, [r12-15h]
0x180020b2d  lea     r15d, [r12-1Ah]
0x180020b32  mov     rdx, [rdi]
0x180020b35  xor     eax, eax
0x180020b37  mov     r9, [rdi+8]
0x180020b3b  lea     r8, [rdx+1]; unsigned __int64
0x180020b3f  movzx   ecx, word ptr [r9+rdx*2]
0x180020b44  mov     [rdi], r8
0x180020b47  cmp     ax, cx
0x180020b4a  jnz     short loc_180020B51
0x180020b4c  mov     [rdi], rdx
0x180020b4f  jmp     short loc_180020B54
0x180020b51  mov     rdx, r8
0x180020b54  mov     [rbp+var_60], cx
0x180020b58  test    ecx, ecx
0x180020b5a  jz      loc_180020AD4
0x180020b60  sub     ecx, 1
0x180020b63  jz      loc_180020AD4
0x180020b69  sub     ecx, 21h ; '!'
0x180020b6c  jz      loc_180020CAB
0x180020b72  cmp     ecx, 3Ah ; ':'
0x180020b75  jz      short loc_180020B8F
0x180020b77  lea     rdx, [rbp+var_60]; void *
0x180020b7b  lea     rcx, [rbp+hHeap]; this
0x180020b7f  call    ?Write@RtlMemoryStream@@QEAAJPEBX_K@Z; RtlMemoryStream::Write(void const *,unsigned __int64)
0x180020b84  mov     ebx, eax
0x180020b86  test    eax, eax
0x180020b88  jns     short loc_180020B32
0x180020b8a  jmp     loc_180020AD9
0x180020b8f  movzx   ecx, word ptr [r9+rdx*2]
0x180020b94  lea     r8, [rdx+1]
0x180020b98  mov     [rdi], r8
0x180020b9b  cmp     ax, cx
0x180020b9e  jnz     short loc_180020BA5
0x180020ba0  mov     [rdi], rdx
0x180020ba3  jmp     short loc_180020BA8
0x180020ba5  mov     rdx, r8
0x180020ba8  mov     [rbp+var_60], cx
0x180020bac  sub     ecx, r12d
0x180020baf  jz      short loc_180020B77
0x180020bb1  sub     ecx, r14d
0x180020bb4  jz      short loc_180020B77
0x180020bb6  sub     ecx, 2Dh ; '-'
0x180020bb9  jz      short loc_180020B77
0x180020bbb  sub     ecx, 6
0x180020bbe  jz      loc_180020CA1
0x180020bc4  sub     ecx, 4
0x180020bc7  jz      loc_180020C93
0x180020bcd  sub     ecx, r15d
0x180020bd0  jz      loc_180020C8C
0x180020bd6  sub     ecx, 4
0x180020bd9  jz      loc_180020C82
0x180020bdf  sub     ecx, 2
0x180020be2  jz      loc_180020C78
0x180020be8  cmp     ecx, 1
0x180020beb  jnz     loc_180020AD4
0x180020bf1  movzx   r8d, word ptr [r9+rdx*2]
0x180020bf6  lea     rcx, [rdx+1]
0x180020bfa  mov     [rdi], rcx
0x180020bfd  cmp     ax, r8w
0x180020c01  jnz     short loc_180020C08
0x180020c03  mov     [rdi], rdx
0x180020c06  jmp     short loc_180020C0B
0x180020c08  mov     rdx, rcx
0x180020c0b  mov     [rbp+String], r8w
0x180020c10  lea     rcx, [rdx+1]
0x180020c14  movzx   r8d, word ptr [r9+rdx*2]
0x180020c19  mov     [rdi], rcx
0x180020c1c  cmp     ax, r8w
0x180020c20  jnz     short loc_180020C27
0x180020c22  mov     [rdi], rdx
0x180020c25  jmp     short loc_180020C2A
0x180020c27  mov     rdx, rcx
0x180020c2a  mov     [rbp+var_26], r8w
0x180020c2f  lea     rcx, [rdx+1]
0x180020c33  movzx   r8d, word ptr [r9+rdx*2]
0x180020c38  mov     [rdi], rcx
0x180020c3b  cmp     ax, r8w
0x180020c3f  jnz     short loc_180020C46
0x180020c41  mov     [rdi], rdx
0x180020c44  jmp     short loc_180020C49
0x180020c46  mov     rdx, rcx
0x180020c49  lea     rax, [rdx+1]
0x180020c4d  mov     [rbp+var_24], r8w
0x180020c52  movzx   ecx, word ptr [r9+rdx*2]
0x180020c57  mov     [rdi], rax
0x180020c5a  xor     eax, eax
0x180020c5c  cmp     ax, cx
0x180020c5f  jnz     short loc_180020C64
0x180020c61  mov     [rdi], rdx
0x180020c64  mov     [rbp+var_22], cx
0x180020c68  lea     rcx, [rbp+String]; String
0x180020c6c  mov     [rbp+var_20], ax
0x180020c70  call    cs:__imp__wtoi
0x180020c76  jmp     short loc_180020C98
0x180020c78  mov     [rbp+var_60], r13w
0x180020c7d  jmp     loc_180020B77
0x180020c82  mov     [rbp+var_60], r14w
0x180020c87  jmp     loc_180020B77
0x180020c8c  mov     eax, 0Ah
0x180020c91  jmp     short loc_180020C98
0x180020c93  mov     eax, 0Ch
0x180020c98  mov     [rbp+var_60], ax
0x180020c9c  jmp     loc_180020B77
0x180020ca1  mov     [rbp+var_60], r15w
0x180020ca6  jmp     loc_180020B77
0x180020cab  mov     rdi, [rbp+hHeap+8]
0x180020caf  call    cs:__imp_GetProcessHeap
0x180020cb5  lea     r8, [rdi+2]; dwBytes
0x180020cb9  xor     edx, edx; dwFlags
0x180020cbb  mov     rcx, rax; hHeap
0x180020cbe  call    cs:__imp_HeapAlloc
0x180020cc4  mov     rbx, rax
0x180020cc7  test    rax, rax
0x180020cca  jnz     short loc_180020CD6
0x180020ccc  mov     ebx, 8007000Eh
0x180020cd1  jmp     loc_180020AD9
0x180020cd6  test    rdi, rdi
0x180020cd9  jz      short loc_180020CEA
0x180020cdb  mov     rdx, [rbp+lpMem+8]; Src
0x180020cdf  mov     r8, rdi; Size
0x180020ce2  mov     rcx, rbx; void *
0x180020ce5  call    memcpy_0
0x180020cea  shr     rdi, 1
0x180020ced  xor     eax, eax
0x180020cef  mov     [rbx+rdi*2], ax
0x180020cf3  mov     [rsi], rbx
0x180020cf6  xor     ebx, ebx
0x180020cf8  jmp     loc_180020AD9
```
