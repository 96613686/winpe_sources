# XT1_WriteCIDVMBinarySection

- ea: `0x18004d81c`
- end: `0x18004db63`
- name: `XT1_WriteCIDVMBinarySection`
- size: `839`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180045e88`

## callees

- `0x180001ee0`
- `0x1800028d8`
- `0x180049428`
- `0x180049e14`
- `0x18004c7b4`
- `0x18004c870`
- `0x18004d81c`
- `0x18005d010`

## pseudocode

```c
__int64 __fastcall XT1_WriteCIDVMBinarySection(__int64 a1)
{
  char v1; // r12
  unsigned int v2; // r15d
  unsigned __int16 v4; // si
  unsigned __int16 v5; // ax
  __int16 v6; // r13
  unsigned __int16 v7; // di
  unsigned __int16 i; // r14
  unsigned int v9; // edi
  BOOL v10; // r12d
  __int16 v11; // cx
  unsigned __int16 j; // dx
  __int64 v13; // rax
  unsigned int v14; // edi
  int v15; // eax
  unsigned __int16 v16; // di
  unsigned __int16 v17; // cx
  unsigned __int16 v18; // di
  char v20; // [rsp+30h] [rbp-D0h]
  __int16 v21; // [rsp+34h] [rbp-CCh] BYREF
  int v22; // [rsp+38h] [rbp-C8h]
  _BOOL8 v23; // [rsp+3Ch] [rbp-C4h] BYREF
  int v24; // [rsp+44h] [rbp-BCh]
  char v25[1024]; // [rsp+50h] [rbp-B0h] BYREF

  v1 = *(_BYTE *)(a1 + 7988);
  v2 = 0;
  v20 = v1;
  v24 = 0;
  v21 = 0;
  v4 = 0;
  v23 = v1 == 2;
  v5 = *(_WORD *)(a1 + 7976);
  if ( v5 == 0xFFFF )
  {
    v6 = 0;
    v22 = 0;
  }
  else
  {
    v6 = *(_WORD *)(a1 + 7976);
    v22 = v5;
  }
  v7 = *(_WORD *)(a1 + 14952);
  for ( i = 0; i < v7; v2 = 0 )
  {
    *(_OWORD *)(a1 + 6820) = *(_OWORD *)(a1 + 16 * (i + 1082LL));
    *(_WORD *)(a1 + 6836) = *(_WORD *)(a1 + 2LL * i + 21408);
    if ( v1 == 2 )
      v9 = *(_DWORD *)(a1 + 6820);
    else
      v9 = *(_DWORD *)(a1 + 14328) - 1;
    v4 += v6 * v9;
    if ( v9 )
    {
      v10 = v23;
      do
      {
        GetSubr(a1, v2, v10, (unsigned int)&v23 + 4, (__int64)&v21);
        v4 += v21;
        ++v2;
      }
      while ( v2 < v9 );
      v1 = v20;
      v6 = v22;
    }
    v7 = *(_WORD *)(a1 + 14952);
    ++i;
  }
  memset_0(v25, 0, sizeof(v25));
  if ( v1 == 2 )
  {
    if ( (*(_BYTE *)(a1 + 15000) & 1) != 0 )
    {
      v11 = 0;
      if ( v7 )
      {
        for ( j = 0; j < v7; ++j )
        {
          v13 = j;
          v11 += *(_WORD *)(16 * (v13 + 1082) + a1);
        }
      }
    }
    else
    {
      v11 = *(_WORD *)(a1 + 6820);
    }
  }
  else
  {
    v11 = v7 * *(_WORD *)(a1 + 14328);
  }
  v14 = v4 + (unsigned __int16)(4 * v11);
  PutString(a1, "%%BeginData: ");
  if ( *(_DWORD *)(a1 + 7980) )
  {
    v15 = 27;
    if ( !v4 )
      v15 = 25;
    (*(void (__fastcall **)(char *, __int64, const char *, _QWORD, const char *))(a1 + 360))(
      v25,
      1024,
      "%8ld Binary Bytes%s",
      v15 + 2 * v14,
      "\r\n");
    PutString(a1, v25);
    (*(void (**)(char *, __int64, const char *, ...))(a1 + 360))(v25, 1024, "(Hex) %8ld StartData%s", v14, "\r\n");
  }
  else
  {
    (*(void (**)(char *, __int64, const char *, ...))(a1 + 360))(v25, 1024, "%8ld Binary Bytes", v14 + 28);
    PutString(a1, v25);
    PutString(a1, "\r\n");
    (*(void (**)(char *, __int64, const char *, ...))(a1 + 360))(v25, 1024, "(Binary) %8ld StartData ", v14);
  }
  PutString(a1, v25);
  if ( v4 )
  {
    *(_WORD *)(a1 + 15000) |= 2u;
    v16 = 0;
    if ( *(_WORD *)(a1 + 14952) )
    {
      do
      {
        XT1_CIDWriteSubrMap(a1, v16);
        v17 = *(_WORD *)(a1 + 14952);
        ++v16;
      }
      while ( v16 < v17 );
      v18 = 0;
      if ( v17 )
      {
        do
          XT1_CIDWriteSubrs(a1, v18++);
        while ( v18 < *(_WORD *)(a1 + 14952) );
      }
    }
    *(_WORD *)(a1 + 15000) &= ~2u;
  }
  if ( *(_DWORD *)(a1 + 7980) && v4 )
    PutString(a1, ">\r\n");
  return PutString(a1, "%%EndData\r\n%%EndResource\r\n");
}

```

## disassembly

```asm
0x18004d81c  push    rbp
0x18004d81e  push    rbx
0x18004d81f  push    rsi
0x18004d820  push    rdi
0x18004d821  push    r12
0x18004d823  push    r13
0x18004d825  push    r14
0x18004d827  push    r15
0x18004d829  lea     rbp, [rsp-368h]
0x18004d831  sub     rsp, 468h
0x18004d838  mov     rax, cs:__security_cookie
0x18004d83f  xor     rax, rsp
0x18004d842  mov     [rbp+3A0h+var_50], rax
0x18004d849  mov     r12b, [rcx+1F34h]
0x18004d850  xor     r15d, r15d
0x18004d853  mov     eax, r15d
0x18004d856  mov     [rsp+4A0h+var_470], r12b
0x18004d85b  cmp     r12b, 2
0x18004d85f  mov     qword ptr [rsp+4A0h+var_460], r15
0x18004d864  mov     rbx, rcx
0x18004d867  mov     [rsp+4A0h+var_46C], r15w
0x18004d86d  setz    al
0x18004d870  mov     esi, r15d
0x18004d873  mov     [rsp+4A0h+var_464], eax
0x18004d877  movzx   eax, word ptr [rcx+1F28h]
0x18004d87e  cmp     ax, 0FFFFh
0x18004d882  jnz     short loc_18004D88E
0x18004d884  mov     r13d, r15d
0x18004d887  mov     [rsp+4A0h+var_468], r15d
0x18004d88c  jmp     short loc_18004D897
0x18004d88e  movzx   r13d, ax
0x18004d892  mov     [rsp+4A0h+var_468], r13d
0x18004d897  movzx   edi, word ptr [rcx+3A68h]
0x18004d89e  mov     r14d, r15d
0x18004d8a1  mov     edx, 1
0x18004d8a6  cmp     r15w, di
0x18004d8aa  jnb     loc_18004D959
0x18004d8b0  movzx   ecx, r14w
0x18004d8b4  lea     rax, [rcx+43Ah]
0x18004d8bb  add     rax, rax
0x18004d8be  movups  xmm0, xmmword ptr [rbx+rax*8]
0x18004d8c2  movdqu  xmmword ptr [rbx+1AA4h], xmm0
0x18004d8ca  movzx   eax, word ptr [rbx+rcx*2+53A0h]
0x18004d8d2  mov     [rbx+1AB4h], ax
0x18004d8d9  cmp     r12b, 2
0x18004d8dd  jnz     short loc_18004D8E7
0x18004d8df  mov     edi, [rbx+1AA4h]
0x18004d8e5  jmp     short loc_18004D8EF
0x18004d8e7  mov     edi, [rbx+37F8h]
0x18004d8ed  sub     edi, edx
0x18004d8ef  movzx   eax, r13w
0x18004d8f3  movzx   ecx, di
0x18004d8f6  imul    ecx, eax
0x18004d8f9  add     si, cx
0x18004d8fc  test    edi, edi
0x18004d8fe  jz      short loc_18004D93E
0x18004d900  mov     r12d, [rsp+4A0h+var_464]
0x18004d905  lea     rax, [rsp+4A0h+var_46C]
0x18004d90a  mov     r8d, r12d
0x18004d90d  lea     r9, [rsp+4A0h+var_460]
0x18004d912  mov     [rsp+4A0h+var_480], rax
0x18004d917  mov     edx, r15d
0x18004d91a  mov     rcx, rbx
0x18004d91d  call    GetSubr
0x18004d922  add     si, [rsp+4A0h+var_46C]
0x18004d927  inc     r15d
0x18004d92a  cmp     r15d, edi
0x18004d92d  jb      short loc_18004D905
0x18004d92f  mov     r12b, [rsp+4A0h+var_470]
0x18004d934  mov     edx, 1
0x18004d939  mov     r13d, [rsp+4A0h+var_468]
0x18004d93e  movzx   edi, word ptr [rbx+3A68h]
0x18004d945  add     r14w, dx
0x18004d949  mov     r15d, 0
0x18004d94f  cmp     r14w, di
0x18004d953  jb      loc_18004D8B0
0x18004d959  mov     r13d, 400h
0x18004d95f  lea     rcx, [rsp+4A0h+var_450]; void *
0x18004d964  mov     r8d, r13d; Size
0x18004d967  xor     edx, edx; Val
0x18004d969  call    memset_0
0x18004d96e  cmp     r12b, 2
0x18004d972  mov     r12d, 1
0x18004d978  jnz     short loc_18004D9B4
0x18004d97a  test    [rbx+3A98h], r12b
0x18004d981  jz      short loc_18004D9AB
0x18004d983  mov     ecx, r15d
0x18004d986  cmp     r15w, di
0x18004d98a  jnb     short loc_18004D9C1
0x18004d98c  mov     edx, r15d
0x18004d98f  movzx   eax, dx
0x18004d992  add     dx, r12w
0x18004d996  add     rax, 43Ah
0x18004d99c  shl     rax, 4
0x18004d9a0  add     cx, [rax+rbx]
0x18004d9a4  cmp     dx, di
0x18004d9a7  jb      short loc_18004D98F
0x18004d9a9  jmp     short loc_18004D9C1
0x18004d9ab  movzx   ecx, word ptr [rbx+1AA4h]
0x18004d9b2  jmp     short loc_18004D9C1
0x18004d9b4  movzx   ecx, word ptr [rbx+37F8h]
0x18004d9bb  movzx   eax, di
0x18004d9be  imul    ecx, eax
0x18004d9c1  shl     cx, 2
0x18004d9c5  lea     rdx, aBegindata; "%%BeginData: "
0x18004d9cc  movzx   edi, cx
0x18004d9cf  mov     rcx, rbx
0x18004d9d2  movzx   eax, si
0x18004d9d5  add     edi, eax
0x18004d9d7  call    PutString
0x18004d9dc  mov     rdx, r13
0x18004d9df  mov     r10, [rbx+168h]
0x18004d9e6  cmp     [rbx+1F2Ch], r15d
0x18004d9ed  jz      short loc_18004DA53
0x18004d9ef  mov     eax, 1Bh
0x18004d9f4  lea     r14, asc_180062FDC; "\r\n"
0x18004d9fb  test    si, si
0x18004d9fe  mov     [rsp+4A0h+var_480], r14
0x18004da03  lea     r8, a8ldBinaryBytes; "%8ld Binary Bytes%s"
0x18004da0a  lea     ecx, [rax-2]
0x18004da0d  cmovz   eax, ecx
0x18004da10  lea     rcx, [rsp+4A0h+var_450]
0x18004da15  lea     r9d, [rax+rdi*2]
0x18004da19  mov     rax, r10
0x18004da1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004da21  lea     rdx, [rsp+4A0h+var_450]
0x18004da26  mov     rcx, rbx
0x18004da29  call    PutString
0x18004da2e  mov     rax, [rbx+168h]
0x18004da35  lea     r8, aHex8ldStartdat; "(Hex) %8ld StartData%s"
0x18004da3c  mov     r9d, edi
0x18004da3f  mov     [rsp+4A0h+var_480], r14
0x18004da44  mov     rdx, r13
0x18004da47  lea     rcx, [rsp+4A0h+var_450]
0x18004da4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004da51  jmp     short loc_18004DAA5
0x18004da53  lea     r9d, [rdi+1Ch]
0x18004da57  mov     rax, r10
0x18004da5a  lea     r8, a8ldBinaryBytes_0; "%8ld Binary Bytes"
0x18004da61  lea     rcx, [rsp+4A0h+var_450]
0x18004da66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004da6b  lea     rdx, [rsp+4A0h+var_450]
0x18004da70  mov     rcx, rbx
0x18004da73  call    PutString
0x18004da78  lea     rdx, asc_180062FDC; "\r\n"
0x18004da7f  mov     rcx, rbx
0x18004da82  call    PutString
0x18004da87  mov     rax, [rbx+168h]
0x18004da8e  lea     r8, aBinary8ldStart; "(Binary) %8ld StartData "
0x18004da95  mov     r9d, edi
0x18004da98  lea     rcx, [rsp+4A0h+var_450]
0x18004da9d  mov     rdx, r13
0x18004daa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004daa5  lea     rdx, [rsp+4A0h+var_450]
0x18004daaa  mov     rcx, rbx
0x18004daad  call    PutString
0x18004dab2  test    si, si
0x18004dab5  jz      short loc_18004DB14
0x18004dab7  or      word ptr [rbx+3A98h], 2
0x18004dabf  mov     edi, r15d
0x18004dac2  cmp     r15w, [rbx+3A68h]
0x18004daca  jnb     short loc_18004DB08
0x18004dacc  movzx   edx, di
0x18004dacf  mov     rcx, rbx
0x18004dad2  call    XT1_CIDWriteSubrMap
0x18004dad7  movzx   ecx, word ptr [rbx+3A68h]
0x18004dade  add     di, r12w
0x18004dae2  cmp     di, cx
0x18004dae5  jb      short loc_18004DACC
0x18004dae7  mov     edi, r15d
0x18004daea  cmp     r15w, cx
0x18004daee  jnb     short loc_18004DB08
0x18004daf0  movzx   edx, di
0x18004daf3  mov     rcx, rbx
0x18004daf6  call    XT1_CIDWriteSubrs
0x18004dafb  add     di, r12w
0x18004daff  cmp     di, [rbx+3A68h]
0x18004db06  jb      short loc_18004DAF0
0x18004db08  mov     eax, 0FFFDh
0x18004db0d  and     [rbx+3A98h], ax
0x18004db14  cmp     [rbx+1F2Ch], r15d
0x18004db1b  jz      short loc_18004DB31
0x18004db1d  test    si, si
0x18004db20  jz      short loc_18004DB31
0x18004db22  lea     rdx, asc_18006B160; ">\r\n"
0x18004db29  mov     rcx, rbx
0x18004db2c  call    PutString
0x18004db31  lea     rdx, aEnddataEndreso; "%%EndData\r\n%%EndResource\r\n"
0x18004db38  mov     rcx, rbx
0x18004db3b  call    PutString
0x18004db40  mov     rcx, [rbp+3A0h+var_50]
0x18004db47  xor     rcx, rsp; StackCookie
0x18004db4a  call    __security_check_cookie
0x18004db4f  add     rsp, 468h
0x18004db56  pop     r15
0x18004db58  pop     r14
0x18004db5a  pop     r13
0x18004db5c  pop     r12
0x18004db5e  pop     rdi
0x18004db5f  pop     rsi
0x18004db60  pop     rbx
0x18004db61  pop     rbp
0x18004db62  retn
```
