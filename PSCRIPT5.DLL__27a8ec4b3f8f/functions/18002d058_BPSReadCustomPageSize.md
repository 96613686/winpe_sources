# BPSReadCustomPageSize

- ea: `0x18002d058`
- end: `0x18002d21a`
- name: `BPSReadCustomPageSize`
- size: `450`
- prototype: `_BOOL8 __fastcall(__int64, int, char *, int, _DWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18002c210`
- `0x18002dcf0`

## callees

- `0x180001f20`
- `0x180002890`
- `0x18002d058`
- `0x18005e0c4`

## import_xrefs

- `KERNEL32!MulDiv` at `0x18002d105`
- `KERNEL32!MulDiv` at `0x18002d105`

## pseudocode

```c
_BOOL8 __fastcall BPSReadCustomPageSize(__int64 a1, int a2, char *a3, int a4, _DWORD *a5)
{
  int v5; // r13d
  __int64 v6; // rbx
  int v7; // esi
  char *v8; // rdi
  int v9; // ebp
  __int64 v10; // r12
  int v11; // r9d
  __int64 v12; // r15
  int v13; // r14d
  char **v14; // rax
  char *v15; // rdx
  unsigned int v16; // r14d
  _BYTE Src[16]; // [rsp+28h] [rbp-50h] BYREF

  v5 = 0;
  v6 = a1 + *(unsigned __int16 *)(a1 + 68);
  v7 = a4;
  v8 = a3;
  if ( a2 )
  {
    if ( a3 && a4 >= 16 )
    {
      v8 = a3 + 16;
      *(_OWORD *)a3 = kstrPSFCustomPS;
    }
    v7 = a4 - 16;
    v5 = 16;
  }
  v9 = 0;
  v10 = -1;
  do
  {
    v11 = 0;
    if ( v9 )
    {
      if ( v9 == 1 )
      {
        v11 = *(_DWORD *)(v6 + 156);
      }
      else if ( (unsigned int)(v9 - 2) <= 1 )
      {
        v11 = *(_DWORD *)(v6 + 160);
      }
    }
    else
    {
      v11 = *(_DWORD *)(v6 + 152);
    }
    MulDiv(v11, 72, 25400);
    o__ultoa_s_0();
    v12 = -1;
    do
      ++v12;
    while ( Src[v12] );
    v13 = v12 + 1;
    if ( v8 && v7 >= v13 )
    {
      memcpy_0(v8, Src, (unsigned int)v13);
      v8[(unsigned int)v12] = 32;
      v8 += (unsigned int)v12 + 1;
    }
    v7 -= v13;
    v5 += v13;
    ++v9;
  }
  while ( v9 < 4 );
  if ( "LongEdge" )
  {
    v14 = &off_180062120;
    while ( *(unsigned __int16 *)(v6 + 168) != *((_DWORD *)v14 + 2) )
    {
      v14 += 2;
      if ( !*v14 )
        goto LABEL_23;
    }
  }
  else
  {
LABEL_23:
    v14 = &off_180062120;
  }
  v15 = *v14;
  do
    ++v10;
  while ( v15[v10] );
  v16 = v10 + 1;
  if ( v8 && v7 >= (int)v16 )
  {
    memcpy_0(v8, v15, v16);
    v8 += v16;
  }
  if ( a5 )
    *a5 = v16 + v5;
  return v8 && (int)(v7 - v16) >= 0;
}

```

## disassembly

```asm
0x18002d058  mov     [rsp+arg_8], rbx
0x18002d05d  push    rbp
0x18002d05e  push    rsi
0x18002d05f  push    rdi
0x18002d060  push    r12
0x18002d062  push    r13
0x18002d064  push    r14
0x18002d066  push    r15
0x18002d068  sub     rsp, 40h
0x18002d06c  mov     rax, cs:__security_cookie
0x18002d073  xor     rax, rsp
0x18002d076  mov     [rsp+78h+var_40], rax
0x18002d07b  movzx   ebx, word ptr [rcx+44h]
0x18002d07f  xor     r13d, r13d
0x18002d082  mov     rax, [rsp+78h+arg_20]
0x18002d08a  add     rbx, rcx
0x18002d08d  mov     [rsp+78h+var_58], rax
0x18002d092  mov     esi, r9d
0x18002d095  mov     rdi, r8
0x18002d098  test    edx, edx
0x18002d09a  jz      short loc_18002D0C0
0x18002d09c  test    r8, r8
0x18002d09f  jz      short loc_18002D0B7
0x18002d0a1  cmp     r9d, 10h
0x18002d0a5  jl      short loc_18002D0B7
0x18002d0a7  movups  xmm0, cs:kstrPSFCustomPS
0x18002d0ae  add     rdi, 10h
0x18002d0b2  movdqu  xmmword ptr [r8], xmm0
0x18002d0b7  sub     esi, 10h
0x18002d0ba  mov     r13d, 10h
0x18002d0c0  xor     ebp, ebp
0x18002d0c2  or      r12, 0FFFFFFFFFFFFFFFFh
0x18002d0c6  xor     r9d, r9d
0x18002d0c9  mov     ecx, ebp
0x18002d0cb  test    ebp, ebp
0x18002d0cd  jz      short loc_18002D0F0
0x18002d0cf  sub     ecx, 1
0x18002d0d2  jz      short loc_18002D0E7
0x18002d0d4  sub     ecx, 1
0x18002d0d7  jz      short loc_18002D0DE
0x18002d0d9  cmp     ecx, 1
0x18002d0dc  jnz     short loc_18002D0F7
0x18002d0de  mov     r9d, [rbx+0A0h]
0x18002d0e5  jmp     short loc_18002D0F7
0x18002d0e7  mov     r9d, [rbx+9Ch]
0x18002d0ee  jmp     short loc_18002D0F7
0x18002d0f0  mov     r9d, [rbx+98h]
0x18002d0f7  mov     edx, 48h ; 'H'; nNumerator
0x18002d0fc  mov     r8d, 6338h; nDenominator
0x18002d102  mov     ecx, r9d; nNumber
0x18002d105  call    cs:__imp_MulDiv
0x18002d10c  nop     dword ptr [rax+rax+00h]
0x18002d111  mov     r9d, 0Ah
0x18002d117  lea     rdx, [rsp+78h+Src]
0x18002d11c  mov     ecx, eax
0x18002d11e  lea     r8d, [r9+6]
0x18002d122  call    _o__ultoa_s_0
0x18002d127  lea     rax, [rsp+78h+Src]
0x18002d12c  mov     r15, r12
0x18002d12f  inc     r15
0x18002d132  cmp     byte ptr [rax+r15], 0
0x18002d137  jnz     short loc_18002D12F
0x18002d139  lea     r14d, [r15+1]
0x18002d13d  test    rdi, rdi
0x18002d140  jz      short loc_18002D164
0x18002d142  cmp     esi, r14d
0x18002d145  jl      short loc_18002D164
0x18002d147  mov     r8d, r14d; Size
0x18002d14a  lea     rdx, [rsp+78h+Src]; Src
0x18002d14f  mov     rcx, rdi; void *
0x18002d152  call    memcpy_0
0x18002d157  mov     ecx, r15d
0x18002d15a  mov     byte ptr [rcx+rdi], 20h ; ' '
0x18002d15e  inc     rdi
0x18002d161  add     rdi, rcx
0x18002d164  sub     esi, r14d
0x18002d167  add     r13d, r14d
0x18002d16a  inc     ebp
0x18002d16c  cmp     ebp, 4
0x18002d16f  jl      loc_18002D0C6
0x18002d175  cmp     cs:off_180062120, 0; "LongEdge"
0x18002d17d  jz      short loc_18002D19C
0x18002d17f  movzx   ecx, word ptr [rbx+0A8h]
0x18002d186  lea     rax, off_180062120; "LongEdge"
0x18002d18d  cmp     ecx, [rax+8]
0x18002d190  jz      short loc_18002D1A3
0x18002d192  add     rax, 10h
0x18002d196  cmp     qword ptr [rax], 0
0x18002d19a  jnz     short loc_18002D18D
0x18002d19c  lea     rax, off_180062120; "LongEdge"
0x18002d1a3  mov     rdx, [rax]; Src
0x18002d1a6  inc     r12
0x18002d1a9  cmp     byte ptr [rdx+r12], 0
0x18002d1ae  jnz     short loc_18002D1A6
0x18002d1b0  lea     r14d, [r12+1]
0x18002d1b5  test    rdi, rdi
0x18002d1b8  jz      short loc_18002D1D0
0x18002d1ba  cmp     esi, r14d
0x18002d1bd  jl      short loc_18002D1D0
0x18002d1bf  mov     r8d, r14d; Size
0x18002d1c2  mov     rcx, rdi; void *
0x18002d1c5  mov     ebx, r14d
0x18002d1c8  call    memcpy_0
0x18002d1cd  add     rdi, rbx
0x18002d1d0  mov     rcx, [rsp+78h+var_58]
0x18002d1d5  test    rcx, rcx
0x18002d1d8  jz      short loc_18002D1E0
0x18002d1da  lea     eax, [r14+r13]
0x18002d1de  mov     [rcx], eax
0x18002d1e0  test    rdi, rdi
0x18002d1e3  jz      short loc_18002D1F2
0x18002d1e5  cmp     esi, r14d
0x18002d1e8  mov     eax, 0
0x18002d1ed  setns   al
0x18002d1f0  jmp     short loc_18002D1F4
0x18002d1f2  xor     eax, eax
0x18002d1f4  mov     rcx, [rsp+78h+var_40]
0x18002d1f9  xor     rcx, rsp; StackCookie
0x18002d1fc  call    __security_check_cookie
0x18002d201  mov     rbx, [rsp+78h+arg_8]
0x18002d209  add     rsp, 40h
0x18002d20d  pop     r15
0x18002d20f  pop     r14
0x18002d211  pop     r13
0x18002d213  pop     r12
0x18002d215  pop     rdi
0x18002d216  pop     rsi
0x18002d217  pop     rbp
0x18002d218  retn
```
