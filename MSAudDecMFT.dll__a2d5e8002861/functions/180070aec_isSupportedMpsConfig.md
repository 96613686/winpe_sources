# isSupportedMpsConfig

- ea: `0x180070aec`
- end: `0x180070c1e`
- name: `isSupportedMpsConfig`
- size: `306`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000a810`

## callees

- `0x18004d320`
- `0x180070aec`
- `0x18007274c`

## pseudocode

```c
__int64 __fastcall isSupportedMpsConfig(unsigned int a1, int a2, int a3)
{
  int v3; // esp
  unsigned __int64 v4; // rsi
  _BYTE *v6; // rbp
  __int64 v8; // rcx
  BOOL v9; // ebx
  __int64 v10; // rax
  int i; // ecx
  int v12; // ecx
  __int64 v13; // rdx
  int v14; // edi
  int v15; // edi
  int v17; // ecx
  _BYTE v18[2912]; // [rsp+20h] [rbp-B98h] BYREF

  v4 = a1;
  v6 = &v18[-(v3 + 32) & 0x1F];
  v8 = 0;
  v9 = 1;
  do
  {
    v10 = 9 * v8++;
    *(_DWORD *)&v6[8 * v10 + 24] = 0;
  }
  while ( v8 != 40 );
  mpegSurroundDecoder_GetLibInfo(&v18[-(v3 + 32) & 0x1F]);
  for ( i = 0; ; ++i )
  {
    if ( i >= 40 )
    {
      LOWORD(v12) = 0;
      goto LABEL_12;
    }
    if ( *(_DWORD *)&v6[72 * i + 24] == 9 )
      break;
  }
  v12 = *(_DWORD *)&v6[72 * i + 32];
  if ( (v12 & 2) == 0 )
  {
LABEL_12:
    v9 = (((_DWORD)v4 - 23) & 0xFFFFFFEF) != 0;
    goto LABEL_13;
  }
  if ( (((_DWORD)v4 - 23) & 0xFFFFFFEF) == 0 && !a3 )
    v9 = 0;
LABEL_13:
  if ( (v12 & 4) == 0 && ((_DWORD)v4 == 42 || (_DWORD)v4 == 50 || (_DWORD)v4 == 150) )
    v9 = 0;
  if ( (v12 & 1) == 0 )
  {
    if ( (unsigned int)v4 > 0x32 || (v13 = 0x4048000800000LL, !_bittest64(&v13, v4)) )
    {
      if ( (_DWORD)v4 != 150 )
        v9 = 0;
    }
  }
  v14 = a2 - 1;
  if ( v14 )
  {
    v15 = v14 - 1;
    if ( v15 )
    {
      if ( (unsigned int)(v15 - 3) >= 2 )
        return 0;
      v17 = v12 & 0x4000;
    }
    else
    {
      v17 = v12 & 0x2000;
    }
  }
  else
  {
    v17 = v12 & 0x1000;
  }
  return v9 & (unsigned int)-(v17 != 0);
}

```

## disassembly

```asm
0x180070aec  push    rbx
0x180070aee  push    rbp
0x180070aef  push    rsi
0x180070af0  push    rdi
0x180070af1  push    r14
0x180070af3  sub     rsp, 0B90h
0x180070afa  mov     rax, cs:__security_cookie
0x180070b01  xor     rax, rsp
0x180070b04  mov     [rsp+0BB8h+var_38], rax
0x180070b0c  lea     rax, [rsp+0BB8h+var_B98]
0x180070b11  mov     esi, ecx
0x180070b13  neg     rax
0x180070b16  lea     rbp, [rsp+0BB8h+var_B98]
0x180070b1b  and     eax, 1Fh
0x180070b1e  mov     r14d, r8d
0x180070b21  add     rbp, rax
0x180070b24  mov     edi, edx
0x180070b26  xor     ecx, ecx
0x180070b28  mov     ebx, 1
0x180070b2d  lea     rax, [rcx+rcx*8]
0x180070b31  inc     rcx
0x180070b34  mov     dword ptr [rbp+rax*8+18h], 0
0x180070b3c  cmp     rcx, 28h ; '('
0x180070b40  jnz     short loc_180070B2D
0x180070b42  mov     rcx, rbp
0x180070b45  call    mpegSurroundDecoder_GetLibInfo
0x180070b4a  xor     ecx, ecx
0x180070b4c  cmp     ecx, 28h ; '('
0x180070b4f  jge     short loc_180070B7F
0x180070b51  movsxd  rax, ecx
0x180070b54  lea     rdx, [rax+rax*8]
0x180070b58  cmp     dword ptr [rbp+rdx*8+18h], 9
0x180070b5d  jz      short loc_180070B63
0x180070b5f  inc     ecx
0x180070b61  jmp     short loc_180070B4C
0x180070b63  mov     ecx, [rbp+rdx*8+20h]
0x180070b67  test    cl, 2
0x180070b6a  jz      short loc_180070B81
0x180070b6c  lea     eax, [rsi-17h]
0x180070b6f  test    eax, 0FFFFFFEFh
0x180070b74  jnz     short loc_180070B8D
0x180070b76  test    r14d, r14d
0x180070b79  jnz     short loc_180070B8D
0x180070b7b  xor     ebx, ebx
0x180070b7d  jmp     short loc_180070B8D
0x180070b7f  xor     ecx, ecx
0x180070b81  lea     eax, [rsi-17h]
0x180070b84  and     eax, 0FFFFFFEFh
0x180070b87  neg     eax
0x180070b89  sbb     eax, eax
0x180070b8b  and     ebx, eax
0x180070b8d  mov     r8d, 96h
0x180070b93  test    cl, 4
0x180070b96  jnz     short loc_180070BA9
0x180070b98  cmp     esi, 2Ah ; '*'
0x180070b9b  jz      short loc_180070BA7
0x180070b9d  cmp     esi, 32h ; '2'
0x180070ba0  jz      short loc_180070BA7
0x180070ba2  cmp     esi, r8d
0x180070ba5  jnz     short loc_180070BA9
0x180070ba7  xor     ebx, ebx
0x180070ba9  test    cl, 1
0x180070bac  jnz     short loc_180070BCB
0x180070bae  cmp     esi, 32h ; '2'
0x180070bb1  ja      short loc_180070BC3
0x180070bb3  mov     rdx, 4048000800000h
0x180070bbd  bt      rdx, rsi
0x180070bc1  jb      short loc_180070BCB
0x180070bc3  xor     eax, eax
0x180070bc5  cmp     esi, r8d
0x180070bc8  cmovnz  ebx, eax
0x180070bcb  sub     edi, 1
0x180070bce  jz      short loc_180070BF3
0x180070bd0  sub     edi, 1
0x180070bd3  jz      short loc_180070BEB
0x180070bd5  sub     edi, 3
0x180070bd8  jz      short loc_180070BE3
0x180070bda  cmp     edi, 1
0x180070bdd  jz      short loc_180070BE3
0x180070bdf  xor     eax, eax
0x180070be1  jmp     short loc_180070BFF
0x180070be3  and     ecx, 4000h
0x180070be9  jmp     short loc_180070BF9
0x180070beb  and     ecx, 2000h
0x180070bf1  jmp     short loc_180070BF9
0x180070bf3  and     ecx, 1000h
0x180070bf9  neg     ecx
0x180070bfb  sbb     eax, eax
0x180070bfd  and     eax, ebx
0x180070bff  mov     rcx, [rsp+0BB8h+var_38]
0x180070c07  xor     rcx, rsp; StackCookie
0x180070c0a  call    __security_check_cookie
0x180070c0f  add     rsp, 0B90h
0x180070c16  pop     r14
0x180070c18  pop     rdi
0x180070c19  pop     rsi
0x180070c1a  pop     rbp
0x180070c1b  pop     rbx
0x180070c1c  retn
```
