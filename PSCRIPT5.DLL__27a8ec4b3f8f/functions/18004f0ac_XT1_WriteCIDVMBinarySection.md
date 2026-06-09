# XT1_WriteCIDVMBinarySection

- ea: `0x18004f0ac`
- end: `0x18004f3f4`
- name: `XT1_WriteCIDVMBinarySection`
- size: `840`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800477ac`

## callees

- `0x180001f20`
- `0x180002938`
- `0x18004ac9c`
- `0x18004b690`
- `0x18004e03c`
- `0x18004e0fc`
- `0x18004f0ac`
- `0x18005f010`

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
  int v10; // r12d
  __int16 v11; // cx
  unsigned __int16 j; // dx
  __int64 v13; // rax
  unsigned int v14; // edi
  int v15; // eax
  __int16 v16; // r8
  unsigned __int16 v17; // di
  unsigned __int16 v18; // cx
  unsigned __int16 v19; // di
  char v21; // [rsp+30h] [rbp-D0h]
  __int16 v22; // [rsp+34h] [rbp-CCh] BYREF
  int v23; // [rsp+38h] [rbp-C8h]
  _BOOL8 v24; // [rsp+3Ch] [rbp-C4h] BYREF
  int v25; // [rsp+44h] [rbp-BCh]
  _BYTE v26[1024]; // [rsp+50h] [rbp-B0h] BYREF

  v1 = *(_BYTE *)(a1 + 7988);
  v2 = 0;
  v21 = v1;
  v25 = 0;
  v22 = 0;
  v4 = 0;
  v24 = v1 == 2;
  v5 = *(_WORD *)(a1 + 7976);
  if ( v5 == 0xFFFF )
  {
    v6 = 0;
    v23 = 0;
  }
  else
  {
    v6 = *(_WORD *)(a1 + 7976);
    v23 = v5;
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
      v10 = v24;
      do
      {
        GetSubr(a1, v2, v10, (_BOOL8 *)((char *)&v24 + 4), &v22);
        v4 += v22;
        ++v2;
      }
      while ( v2 < v9 );
      v1 = v21;
      v6 = v23;
    }
    v7 = *(_WORD *)(a1 + 14952);
    ++i;
  }
  memset_0(v26, 0, sizeof(v26));
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
  PutString(a1, (__int64)"%%BeginData: ");
  if ( *(_DWORD *)(a1 + 7980) )
  {
    v15 = 27;
    if ( !v4 )
      v15 = 25;
    (*(void (__fastcall **)(_BYTE *, __int64, const char *, _QWORD, const char *))(a1 + 360))(
      v26,
      1024,
      "%8ld Binary Bytes%s",
      v15 + 2 * v14,
      "\r\n");
    PutString(a1, (__int64)v26);
    (*(void (**)(_BYTE *, __int64, const char *, ...))(a1 + 360))(v26, 1024, "(Hex) %8ld StartData%s", v14, "\r\n");
  }
  else
  {
    (*(void (**)(_BYTE *, __int64, const char *, ...))(a1 + 360))(v26, 1024, "%8ld Binary Bytes", v14 + 28);
    PutString(a1, (__int64)v26);
    PutString(a1, (__int64)"\r\n");
    (*(void (**)(_BYTE *, __int64, const char *, ...))(a1 + 360))(v26, 1024, "(Binary) %8ld StartData ", v14);
  }
  PutString(a1, (__int64)v26);
  if ( v4 )
  {
    *(_WORD *)(a1 + 15000) |= 2u;
    v17 = 0;
    if ( *(_WORD *)(a1 + 14952) )
    {
      do
      {
        XT1_CIDWriteSubrMap(a1, v17, v16);
        v18 = *(_WORD *)(a1 + 14952);
        ++v17;
      }
      while ( v17 < v18 );
      v19 = 0;
      if ( v18 )
      {
        do
          XT1_CIDWriteSubrs(a1, v19++);
        while ( v19 < *(_WORD *)(a1 + 14952) );
      }
    }
    *(_WORD *)(a1 + 15000) &= ~2u;
  }
  if ( *(_DWORD *)(a1 + 7980) && v4 )
    PutString(a1, (__int64)">\r\n");
  return PutString(a1, (__int64)"%%EndData\r\n%%EndResource\r\n");
}

```

## disassembly

```asm
0x18004f0ac  push    rbp
0x18004f0ae  push    rbx
0x18004f0af  push    rsi
0x18004f0b0  push    rdi
0x18004f0b1  push    r12
0x18004f0b3  push    r13
0x18004f0b5  push    r14
0x18004f0b7  push    r15
0x18004f0b9  lea     rbp, [rsp-368h]
0x18004f0c1  sub     rsp, 468h
0x18004f0c8  mov     rax, cs:__security_cookie
0x18004f0cf  xor     rax, rsp
0x18004f0d2  mov     [rbp+3A0h+var_50], rax
0x18004f0d9  mov     r12b, [rcx+1F34h]
0x18004f0e0  xor     r15d, r15d
0x18004f0e3  mov     eax, r15d
0x18004f0e6  mov     [rsp+4A0h+var_470], r12b
0x18004f0eb  cmp     r12b, 2
0x18004f0ef  mov     qword ptr [rsp+4A0h+var_460], r15
0x18004f0f4  mov     rbx, rcx
0x18004f0f7  mov     [rsp+4A0h+var_46C], r15w
0x18004f0fd  setz    al
0x18004f100  mov     esi, r15d
0x18004f103  mov     [rsp+4A0h+var_464], eax
0x18004f107  movzx   eax, word ptr [rcx+1F28h]
0x18004f10e  cmp     ax, 0FFFFh
0x18004f112  jnz     short loc_18004F11E
0x18004f114  mov     r13d, r15d
0x18004f117  mov     [rsp+4A0h+var_468], r15d
0x18004f11c  jmp     short loc_18004F127
0x18004f11e  movzx   r13d, ax
0x18004f122  mov     [rsp+4A0h+var_468], r13d
0x18004f127  movzx   edi, word ptr [rcx+3A68h]
0x18004f12e  mov     r14d, r15d
0x18004f131  mov     edx, 1
0x18004f136  cmp     r15w, di
0x18004f13a  jnb     loc_18004F1E9
0x18004f140  movzx   ecx, r14w
0x18004f144  lea     rax, [rcx+43Ah]
0x18004f14b  add     rax, rax
0x18004f14e  movups  xmm0, xmmword ptr [rbx+rax*8]
0x18004f152  movdqu  xmmword ptr [rbx+1AA4h], xmm0
0x18004f15a  movzx   eax, word ptr [rbx+rcx*2+53A0h]
0x18004f162  mov     [rbx+1AB4h], ax
0x18004f169  cmp     r12b, 2
0x18004f16d  jnz     short loc_18004F177
0x18004f16f  mov     edi, [rbx+1AA4h]
0x18004f175  jmp     short loc_18004F17F
0x18004f177  mov     edi, [rbx+37F8h]
0x18004f17d  sub     edi, edx
0x18004f17f  movzx   eax, r13w
0x18004f183  movzx   ecx, di
0x18004f186  imul    ecx, eax
0x18004f189  add     si, cx
0x18004f18c  test    edi, edi
0x18004f18e  jz      short loc_18004F1CE
0x18004f190  mov     r12d, [rsp+4A0h+var_464]
0x18004f195  lea     rax, [rsp+4A0h+var_46C]
0x18004f19a  mov     r8d, r12d
0x18004f19d  lea     r9, [rsp+4A0h+var_460]
0x18004f1a2  mov     [rsp+4A0h+var_480], rax
0x18004f1a7  mov     edx, r15d
0x18004f1aa  mov     rcx, rbx
0x18004f1ad  call    GetSubr
0x18004f1b2  add     si, [rsp+4A0h+var_46C]
0x18004f1b7  inc     r15d
0x18004f1ba  cmp     r15d, edi
0x18004f1bd  jb      short loc_18004F195
0x18004f1bf  mov     r12b, [rsp+4A0h+var_470]
0x18004f1c4  mov     edx, 1
0x18004f1c9  mov     r13d, [rsp+4A0h+var_468]
0x18004f1ce  movzx   edi, word ptr [rbx+3A68h]
0x18004f1d5  add     r14w, dx
0x18004f1d9  mov     r15d, 0
0x18004f1df  cmp     r14w, di
0x18004f1e3  jb      loc_18004F140
0x18004f1e9  mov     r13d, 400h
0x18004f1ef  lea     rcx, [rsp+4A0h+var_450]; void *
0x18004f1f4  mov     r8d, r13d; Size
0x18004f1f7  xor     edx, edx; Val
0x18004f1f9  call    memset_0
0x18004f1fe  cmp     r12b, 2
0x18004f202  mov     r12d, 1
0x18004f208  jnz     short loc_18004F244
0x18004f20a  test    [rbx+3A98h], r12b
0x18004f211  jz      short loc_18004F23B
0x18004f213  mov     ecx, r15d
0x18004f216  cmp     r15w, di
0x18004f21a  jnb     short loc_18004F251
0x18004f21c  mov     edx, r15d
0x18004f21f  movzx   eax, dx
0x18004f222  add     dx, r12w
0x18004f226  add     rax, 43Ah
0x18004f22c  shl     rax, 4
0x18004f230  add     cx, [rax+rbx]
0x18004f234  cmp     dx, di
0x18004f237  jb      short loc_18004F21F
0x18004f239  jmp     short loc_18004F251
0x18004f23b  movzx   ecx, word ptr [rbx+1AA4h]
0x18004f242  jmp     short loc_18004F251
0x18004f244  movzx   ecx, word ptr [rbx+37F8h]
0x18004f24b  movzx   eax, di
0x18004f24e  imul    ecx, eax
0x18004f251  shl     cx, 2
0x18004f255  lea     rdx, aBegindata; "%%BeginData: "
0x18004f25c  movzx   edi, cx
0x18004f25f  mov     rcx, rbx
0x18004f262  movzx   eax, si
0x18004f265  add     edi, eax
0x18004f267  call    PutString
0x18004f26c  mov     rdx, r13
0x18004f26f  mov     r10, [rbx+168h]
0x18004f276  cmp     [rbx+1F2Ch], r15d
0x18004f27d  jz      short loc_18004F2E3
0x18004f27f  mov     eax, 1Bh
0x18004f284  lea     r14, asc_180064FCC; "\r\n"
0x18004f28b  test    si, si
0x18004f28e  mov     [rsp+4A0h+var_480], r14
0x18004f293  lea     r8, a8ldBinaryBytes; "%8ld Binary Bytes%s"
0x18004f29a  lea     ecx, [rax-2]
0x18004f29d  cmovz   eax, ecx
0x18004f2a0  lea     rcx, [rsp+4A0h+var_450]
0x18004f2a5  lea     r9d, [rax+rdi*2]
0x18004f2a9  mov     rax, r10
0x18004f2ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f2b1  lea     rdx, [rsp+4A0h+var_450]
0x18004f2b6  mov     rcx, rbx
0x18004f2b9  call    PutString
0x18004f2be  mov     rax, [rbx+168h]
0x18004f2c5  lea     r8, aHex8ldStartdat; "(Hex) %8ld StartData%s"
0x18004f2cc  mov     r9d, edi
0x18004f2cf  mov     [rsp+4A0h+var_480], r14
0x18004f2d4  mov     rdx, r13
0x18004f2d7  lea     rcx, [rsp+4A0h+var_450]
0x18004f2dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f2e1  jmp     short loc_18004F335
0x18004f2e3  lea     r9d, [rdi+1Ch]
0x18004f2e7  mov     rax, r10
0x18004f2ea  lea     r8, a8ldBinaryBytes_0; "%8ld Binary Bytes"
0x18004f2f1  lea     rcx, [rsp+4A0h+var_450]
0x18004f2f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f2fb  lea     rdx, [rsp+4A0h+var_450]
0x18004f300  mov     rcx, rbx
0x18004f303  call    PutString
0x18004f308  lea     rdx, asc_180064FCC; "\r\n"
0x18004f30f  mov     rcx, rbx
0x18004f312  call    PutString
0x18004f317  mov     rax, [rbx+168h]
0x18004f31e  lea     r8, aBinary8ldStart; "(Binary) %8ld StartData "
0x18004f325  mov     r9d, edi
0x18004f328  lea     rcx, [rsp+4A0h+var_450]
0x18004f32d  mov     rdx, r13
0x18004f330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f335  lea     rdx, [rsp+4A0h+var_450]
0x18004f33a  mov     rcx, rbx
0x18004f33d  call    PutString
0x18004f342  test    si, si
0x18004f345  jz      short loc_18004F3A4
0x18004f347  or      word ptr [rbx+3A98h], 2
0x18004f34f  mov     edi, r15d
0x18004f352  cmp     r15w, [rbx+3A68h]
0x18004f35a  jnb     short loc_18004F398
0x18004f35c  movzx   edx, di
0x18004f35f  mov     rcx, rbx
0x18004f362  call    XT1_CIDWriteSubrMap
0x18004f367  movzx   ecx, word ptr [rbx+3A68h]
0x18004f36e  add     di, r12w
0x18004f372  cmp     di, cx
0x18004f375  jb      short loc_18004F35C
0x18004f377  mov     edi, r15d
0x18004f37a  cmp     r15w, cx
0x18004f37e  jnb     short loc_18004F398
0x18004f380  movzx   edx, di
0x18004f383  mov     rcx, rbx
0x18004f386  call    XT1_CIDWriteSubrs
0x18004f38b  add     di, r12w
0x18004f38f  cmp     di, [rbx+3A68h]
0x18004f396  jb      short loc_18004F380
0x18004f398  mov     eax, 0FFFDh
0x18004f39d  and     [rbx+3A98h], ax
0x18004f3a4  cmp     [rbx+1F2Ch], r15d
0x18004f3ab  jz      short loc_18004F3C1
0x18004f3ad  test    si, si
0x18004f3b0  jz      short loc_18004F3C1
0x18004f3b2  lea     rdx, asc_18006D120; ">\r\n"
0x18004f3b9  mov     rcx, rbx
0x18004f3bc  call    PutString
0x18004f3c1  lea     rdx, aEnddataEndreso; "%%EndData\r\n%%EndResource\r\n"
0x18004f3c8  mov     rcx, rbx
0x18004f3cb  call    PutString
0x18004f3d0  mov     rcx, [rbp+3A0h+var_50]
0x18004f3d7  xor     rcx, rsp; StackCookie
0x18004f3da  call    __security_check_cookie
0x18004f3df  add     rsp, 468h
0x18004f3e6  pop     r15
0x18004f3e8  pop     r14
0x18004f3ea  pop     r13
0x18004f3ec  pop     r12
0x18004f3ee  pop     rdi
0x18004f3ef  pop     rsi
0x18004f3f0  pop     rbx
0x18004f3f1  pop     rbp
0x18004f3f2  retn
```
