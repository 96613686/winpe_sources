# WofMungeDirectoryEnumerateWithShortname

- ea: `0x14003e0b8`
- end: `0x14003e308`
- name: `WofMungeDirectoryEnumerateWithShortname`
- size: `592`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140036e70`

## callees

- `0x140011590`
- `0x1400115b0`
- `0x140022fcc`
- `0x1400230a8`
- `0x140023198`
- `0x140035ed0`
- `0x14003e0b8`

## pseudocode

```c
__int64 __fastcall WofMungeDirectoryEnumerateWithShortname(
        int a1,
        _DWORD *a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        char a6,
        _DWORD *a7)
{
  _DWORD *v7; // rdi
  int v8; // r10d
  __int64 v9; // rbx
  unsigned int v10; // edx
  _DWORD *v11; // r14
  unsigned int v12; // r13d
  unsigned int *v13; // rsi
  void *v14; // rcx
  void *v15; // rcx
  __int64 v16; // r8
  int v17; // eax
  int *v18; // rcx
  size_t v19; // r8
  void *v20; // rdx
  void *v21; // rcx
  void *v22; // rdx
  void *v23; // rcx
  unsigned int v24; // eax
  unsigned int v25; // esi
  unsigned int v26; // r8d
  SIZE_T v27; // r8
  void *v28; // rcx
  unsigned __int64 v30; // [rsp+30h] [rbp-48h]
  unsigned int v32; // [rsp+90h] [rbp+18h]
  __int64 v33; // [rsp+98h] [rbp+20h]

  v33 = a4;
  v7 = a2;
  v8 = a1;
  v30 = (unsigned __int64)a2 + a3;
  v9 = 0;
  v10 = 0;
  v32 = 0;
  v11 = v7;
  while ( 1 )
  {
    v12 = v11[15];
    if ( v12 >= a3 - 114 )
      v12 = a3 - 114;
    if ( v8 == 63 )
    {
      v13 = (unsigned int *)(v9 + a4);
      v32 = v12 + 114;
      v14 = (void *)(v9 + a4);
      if ( a6 )
        RtlCopyToUser(v14, v7, 0x5Au);
      else
        RtlCopyVolatileMemory(v14, v7, 0x5Au);
      v15 = (char *)v13 + 89;
      if ( a6 )
        RtlSetUserMemory(v15, 0, 0x19u);
      else
        RtlSetVolatileMemory(v15, 0, 0x19u);
      if ( v11[17] == FileTag )
      {
        v17 = WofSanitizeAttributes((unsigned int)v11[14], 0, v16);
        v18 = (int *)(v13 + 14);
        if ( a6 )
          RtlWriteULongToUser(v18, v17);
        else
          *v18 = v17;
        if ( byte_140018454 )
        {
          if ( a6 )
            RtlWriteULongToUser(v13 + 17, 0);
          else
            v13[17] = 0;
        }
      }
      v19 = *((char *)v11 + 88);
      v20 = (char *)v11 + 90;
      v21 = (char *)v13 + 90;
      if ( a6 )
        RtlCopyToUser(v21, v20, v19);
      else
        RtlCopyVolatileMemory(v21, v20, v19);
      v22 = (char *)v11 + 114;
      v23 = (char *)v13 + 114;
      if ( a6 )
        RtlCopyToUser(v23, v22, v12);
      else
        RtlCopyVolatileMemory(v23, v22, v12);
      v10 = v12 + 114;
      v24 = (v12 + 121) & 0xFFFFFFF8;
      if ( a6 )
      {
        RtlWriteULongToUser(v13, v24);
        v10 = v12 + 114;
      }
      else
      {
        *v13 = v24;
      }
      a4 = v33;
    }
    if ( !*v7 )
      break;
    v25 = (v10 + 7) & 0xFFFFFFF8;
    v26 = v25;
    if ( v25 >= a5 - (unsigned int)v9 )
      v26 = a5 - v9;
    v27 = v26 - v10;
    v28 = (void *)(a4 + v10 + (unsigned int)v9);
    if ( a6 )
      RtlSetUserMemory(v28, 0, v27);
    else
      RtlSetVolatileMemory(v28, 0, v27);
    v9 = v25 + (unsigned int)v9;
    v7 = (_DWORD *)((char *)v7 + (unsigned int)*v7);
    v11 = v7;
    if ( (unsigned __int64)v7 >= v30 || (unsigned int)v9 >= a5 )
      goto LABEL_42;
    a3 = v30 - (_DWORD)v7;
    v10 = v32;
    a4 = v33;
    v8 = a1;
  }
  if ( a6 )
    RtlWriteULongToUser((_DWORD *)(v9 + a4), 0);
  else
    *(_DWORD *)(v9 + a4) = 0;
  LODWORD(v9) = v32 + v9;
LABEL_42:
  *a7 = v9;
  return 0;
}

```

## disassembly

```asm
0x14003e0b8  mov     rax, rsp
0x14003e0bb  mov     [rax+20h], r9
0x14003e0bf  mov     [rax+8], ecx
0x14003e0c2  push    rbx
0x14003e0c3  push    rsi
0x14003e0c4  push    rdi
0x14003e0c5  push    r12
0x14003e0c7  push    r13
0x14003e0c9  push    r14
0x14003e0cb  push    r15
0x14003e0cd  sub     rsp, 40h
0x14003e0d1  mov     rdi, rdx
0x14003e0d4  mov     r10d, ecx
0x14003e0d7  mov     byte ptr [rax-58h], 0
0x14003e0db  mov     [rsp+78h+arg_8], 0
0x14003e0e6  mov     ecx, r8d
0x14003e0e9  add     rcx, rdx
0x14003e0ec  mov     [rsp+78h+var_48], rcx
0x14003e0f1  xor     ebx, ebx
0x14003e0f3  xor     edx, edx
0x14003e0f5  mov     [rax+18h], edx
0x14003e0f8  mov     r14, rdi
0x14003e0fb  mov     r15b, [rsp+78h+arg_28]
0x14003e103  mov     r13d, [r14+3Ch]
0x14003e107  lea     eax, [r8-72h]
0x14003e10b  cmp     r13d, eax
0x14003e10e  cmovnb  r13d, eax
0x14003e112  cmp     r10d, 3Fh ; '?'
0x14003e116  jnz     loc_14003E225
0x14003e11c  lea     rsi, [rbx+r9]
0x14003e120  lea     eax, [r13+72h]
0x14003e124  mov     [rsp+78h+arg_10], eax
0x14003e12b  mov     [rsp+78h+var_50], eax
0x14003e12f  mov     [rsp+78h+var_58], 1
0x14003e134  lea     r8d, [r10+1Bh]; Size
0x14003e138  mov     rdx, rdi; Src
0x14003e13b  mov     rcx, rsi; void *
0x14003e13e  test    r15b, r15b
0x14003e141  jz      short loc_14003E14A
0x14003e143  call    RtlCopyToUser
0x14003e148  jmp     short loc_14003E14F
0x14003e14a  call    RtlCopyVolatileMemory
0x14003e14f  lea     rcx, [rsi+59h]; void *
0x14003e153  xor     edx, edx; Val
0x14003e155  lea     r8d, [rdx+19h]; Size
0x14003e159  test    r15b, r15b
0x14003e15c  jz      short loc_14003E165
0x14003e15e  call    RtlSetUserMemory
0x14003e163  jmp     short loc_14003E16A
0x14003e165  call    RtlSetVolatileMemory
0x14003e16a  mov     eax, cs:FileTag
0x14003e170  cmp     [r14+44h], eax
0x14003e174  jnz     short loc_14003E1B7
0x14003e176  xor     edx, edx
0x14003e178  mov     ecx, [r14+38h]
0x14003e17c  call    WofSanitizeAttributes
0x14003e181  lea     rcx, [rsi+38h]
0x14003e185  test    r15b, r15b
0x14003e188  jz      short loc_14003E193
0x14003e18a  mov     edx, eax
0x14003e18c  call    RtlWriteULongToUser
0x14003e191  jmp     short loc_14003E195
0x14003e193  mov     [rcx], eax
0x14003e195  cmp     cs:byte_140018454, 0
0x14003e19c  jz      short loc_14003E1B7
0x14003e19e  test    r15b, r15b
0x14003e1a1  jz      short loc_14003E1B0
0x14003e1a3  xor     edx, edx
0x14003e1a5  lea     rcx, [rsi+44h]
0x14003e1a9  call    RtlWriteULongToUser
0x14003e1ae  jmp     short loc_14003E1B7
0x14003e1b0  mov     dword ptr [rsi+44h], 0
0x14003e1b7  movsx   r8, byte ptr [r14+58h]; Size
0x14003e1bc  lea     rdx, [r14+5Ah]; Src
0x14003e1c0  lea     rcx, [rsi+5Ah]; void *
0x14003e1c4  test    r15b, r15b
0x14003e1c7  jz      short loc_14003E1D0
0x14003e1c9  call    RtlCopyToUser
0x14003e1ce  jmp     short loc_14003E1D5
0x14003e1d0  call    RtlCopyVolatileMemory
0x14003e1d5  lea     rdx, [r14+72h]; Src
0x14003e1d9  lea     rcx, [rsi+72h]; void *
0x14003e1dd  mov     r8d, r13d; Size
0x14003e1e0  test    r15b, r15b
0x14003e1e3  jz      short loc_14003E1EC
0x14003e1e5  call    RtlCopyToUser
0x14003e1ea  jmp     short loc_14003E1F1
0x14003e1ec  call    RtlCopyVolatileMemory
0x14003e1f1  mov     edx, [rsp+78h+arg_10]
0x14003e1f8  lea     eax, [rdx+7]
0x14003e1fb  and     eax, 0FFFFFFF8h
0x14003e1fe  test    r15b, r15b
0x14003e201  jz      short loc_14003E216
0x14003e203  mov     edx, eax
0x14003e205  mov     rcx, rsi
0x14003e208  call    RtlWriteULongToUser
0x14003e20d  mov     edx, [rsp+78h+arg_10]
0x14003e214  jmp     short loc_14003E218
0x14003e216  mov     [rsi], eax
0x14003e218  mov     [rsp+78h+var_58], 0
0x14003e21d  mov     r9, [rsp+78h+arg_18]
0x14003e225  mov     [rsp+78h+var_58], 1
0x14003e22a  cmp     dword ptr [rdi], 0
0x14003e22d  jz      loc_14003E2B4
0x14003e233  mov     ecx, [rsp+78h+arg_20]
0x14003e23a  sub     ecx, ebx
0x14003e23c  lea     esi, [rdx+7]
0x14003e23f  and     esi, 0FFFFFFF8h
0x14003e242  mov     r8d, esi
0x14003e245  cmp     esi, ecx
0x14003e247  cmovnb  r8d, ecx
0x14003e24b  sub     r8d, edx; Size
0x14003e24e  lea     ecx, [rdx+rbx]
0x14003e251  add     rcx, r9; void *
0x14003e254  xor     edx, edx; Val
0x14003e256  test    r15b, r15b
0x14003e259  jz      short loc_14003E262
0x14003e25b  call    RtlSetUserMemory
0x14003e260  jmp     short loc_14003E267
0x14003e262  call    RtlSetVolatileMemory
0x14003e267  mov     [rsp+78h+var_58], 0
0x14003e26c  add     ebx, esi
0x14003e26e  mov     [rsp+78h+var_54], ebx
0x14003e272  mov     eax, [rdi]
0x14003e274  add     rdi, rax
0x14003e277  mov     [rsp+78h+var_40], rdi
0x14003e27c  mov     r14, rdi
0x14003e27f  mov     rcx, [rsp+78h+var_48]
0x14003e284  cmp     rdi, rcx
0x14003e287  jnb     short loc_14003E2DF
0x14003e289  cmp     ebx, [rsp+78h+arg_20]
0x14003e290  jnb     short loc_14003E2DF
0x14003e292  mov     r8d, ecx
0x14003e295  sub     r8d, edi
0x14003e298  mov     edx, [rsp+78h+arg_10]
0x14003e29f  mov     r9, [rsp+78h+arg_18]
0x14003e2a7  mov     r10d, [rsp+78h+arg_0]
0x14003e2af  jmp     loc_14003E103
0x14003e2b4  lea     rax, [rbx+r9]
0x14003e2b8  test    r15b, r15b
0x14003e2bb  jz      short loc_14003E2C9
0x14003e2bd  xor     edx, edx
0x14003e2bf  mov     rcx, rax
0x14003e2c2  call    RtlWriteULongToUser
0x14003e2c7  jmp     short loc_14003E2CF
0x14003e2c9  mov     dword ptr [rax], 0
0x14003e2cf  mov     [rsp+78h+var_58], 0
0x14003e2d4  add     ebx, [rsp+78h+arg_10]
0x14003e2db  mov     [rsp+78h+var_54], ebx
0x14003e2df  mov     rax, [rsp+78h+arg_30]
0x14003e2e7  mov     [rax], ebx
0x14003e2e9  mov     eax, [rsp+78h+arg_8]
0x14003e2f0  jmp     short loc_14003E2F7
0x14003e2f2  mov     eax, 0C00000E8h
0x14003e2f7  add     rsp, 40h
0x14003e2fb  pop     r15
0x14003e2fd  pop     r14
0x14003e2ff  pop     r13
0x14003e301  pop     r12
0x14003e303  pop     rdi
0x14003e304  pop     rsi
0x14003e305  pop     rbx
0x14003e306  retn
0x14003f0fa  push    rbp
0x14003f0fc  sub     rsp, 20h
0x14003f100  mov     rbp, rdx
0x14003f103  xor     eax, eax
0x14003f105  cmp     [rbp+20h], al
0x14003f108  setnz   al
0x14003f10b  add     rsp, 20h
0x14003f10f  pop     rbp
0x14003f110  retn
```
