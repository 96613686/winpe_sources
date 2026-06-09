# CFFUpdateMetrics2

- ea: `0x18003a008`
- end: `0x18003a2f4`
- name: `CFFUpdateMetrics2`
- size: `748`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x18003997c`

## callees

- `0x180001ee0`
- `0x1800055e0`
- `0x18003858c`
- `0x180038968`
- `0x180038b18`
- `0x1800395ec`
- `0x18003a008`
- `0x18004306c`
- `0x18005d010`

## pseudocode

```c
__int64 __fastcall CFFUpdateMetrics2(__int64 a1, int *a2, const char *a3)
{
  __int64 v3; // rax
  unsigned __int16 v4; // di
  int v7; // edx
  __int64 v8; // rdi
  __int64 v9; // rax
  __int64 v10; // r13
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // r14
  int v14; // r12d
  unsigned int v15; // r10d
  __int64 v16; // rax
  unsigned __int64 v17; // r13
  __int64 v18; // r9
  __int64 v19; // r8
  unsigned __int16 v20; // r15
  const char *v21; // r9
  const char *v22; // rax
  const char *v23; // r9
  char v25[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v26; // [rsp+54h] [rbp-ACh] BYREF
  int v27; // [rsp+58h] [rbp-A8h] BYREF
  int v28; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+68h] [rbp-98h] BYREF
  int v31; // [rsp+6Ch] [rbp-94h] BYREF
  int v32; // [rsp+70h] [rbp-90h] BYREF
  int v33; // [rsp+74h] [rbp-8Ch]
  __int64 v34; // [rsp+78h] [rbp-88h]
  const char *v35; // [rsp+80h] [rbp-80h]
  __int64 v36; // [rsp+88h] [rbp-78h]
  char pszDest[256]; // [rsp+90h] [rbp-70h] BYREF

  v3 = *(_QWORD *)(a1 + 48);
  v4 = 0;
  v35 = a3;
  if ( !*(_QWORD *)(a1 + 160) || (*(_BYTE *)(a1 + 28) & 8) == 0 || *(char *)(v3 + 68) < 0 )
  {
    v7 = *a2;
    if ( v7 > 0 )
    {
      v8 = *(_QWORD *)(v3 + 8);
      v9 = *(_QWORD *)(a1 + 40);
      v10 = *((_QWORD *)a2 + 1);
      v11 = *(_QWORD *)(a1 + 32);
      v36 = v8;
      v34 = *(_QWORD *)(v9 + 168);
      v29 = v10;
      v12 = UFLNewPtr(v11, (unsigned int)(2 * v7));
      v13 = v12;
      if ( v12 )
      {
        v4 = CFFGIDsToCIDs(v8, (unsigned int)*a2, v10, v12);
        if ( !v4 )
        {
          v14 = 0;
          if ( *a2 > 0 )
          {
            while ( 1 )
            {
              v15 = *(unsigned __int16 *)(v10 + 4LL * v14);
              if ( v15 < *(_DWORD *)(*(_QWORD *)(a1 + 120) + 4LL) )
                break;
LABEL_28:
              if ( ++v14 >= *a2 )
                goto LABEL_29;
            }
            v16 = *(_QWORD *)(a1 + 48);
            v17 = (unsigned __int64)*(unsigned __int16 *)(v10 + 4LL * v14) >> 3;
            v33 = v15 & 7;
            if ( (*(_BYTE *)(*(_QWORD *)(v16 + 32) + v17) & (unsigned __int8)(1 << (v15 & 7))) != 0 )
            {
LABEL_27:
              v10 = v29;
              goto LABEL_28;
            }
            v32 = 0;
            v26 = 0;
            v28 = 0;
            v31 = 0;
            v27 = 0;
            v30 = 0;
            v25[0] = 0;
            GetMetrics2FromTTF(
              a1,
              (unsigned __int16)v15,
              (unsigned int)&v32,
              (unsigned int)&v26,
              (__int64)&v28,
              (__int64)&v31,
              (__int64)&v27,
              (__int64)v25,
              0,
              (__int64)&v30);
            StringCchPrintfA(
              pszDest,
              0x100u,
              "%ld [0 %ld %ld %ld] ",
              *(unsigned __int16 *)(v13 + 2LL * v14),
              -v26,
              v28,
              v27);
            if ( pszDest[0] )
            {
              v19 = -1;
              do
                ++v19;
              while ( pszDest[v19] );
              LOBYTE(v18) = 1;
              v20 = StrmPutBytes(v34, pszDest, v19, v18);
            }
            else
            {
              v20 = 0;
            }
            v4 = v20;
            if ( *(_QWORD *)(a1 + 160) && (*(_BYTE *)(a1 + 28) & 8) != 0 )
            {
              v21 = v35;
              v22 = "-hf";
            }
            else
            {
              v22 = (const char *)(v36 + 92);
              if ( !*(_DWORD *)(a1 + 136) )
              {
                v23 = "ADBCFA+";
                if ( *(_DWORD *)(a1 + 4) != 5 )
                  v23 = "ADBCFB+";
                StringCchPrintfA(pszDest, 0x100u, "/%s%s T0AddCFFMtx2", v23, v22);
                goto LABEL_24;
              }
              v21 = "ADBCFF+";
            }
            StringCchPrintfA(pszDest, 0x100u, " /%s%s T0AddCFFMtx2", v21, v22);
LABEL_24:
            if ( !v20 )
            {
              v4 = StrmPutStringEOL(v34, pszDest);
              if ( !v4 )
                *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 48) + 32LL) + v17) |= 1 << v33;
            }
            goto LABEL_27;
          }
        }
LABEL_29:
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(a1 + 32) + 8LL))(
          v13 - 8,
          *(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL));
      }
      else
      {
        return 6;
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18003a008  mov     [rsp-8+arg_18], rbx
0x18003a00d  push    rbp
0x18003a00e  push    rsi
0x18003a00f  push    rdi
0x18003a010  push    r12
0x18003a012  push    r13
0x18003a014  push    r14
0x18003a016  push    r15
0x18003a018  lea     rbp, [rsp-0A0h]
0x18003a020  sub     rsp, 1A0h
0x18003a027  mov     rax, cs:__security_cookie
0x18003a02e  xor     rax, rsp
0x18003a031  mov     [rbp+0D0h+var_40], rax
0x18003a038  mov     rax, [rcx+30h]
0x18003a03c  xor     edi, edi
0x18003a03e  mov     rsi, rdx
0x18003a041  mov     [rbp+0D0h+var_150], r8
0x18003a045  mov     rbx, rcx
0x18003a048  cmp     [rcx+0A0h], rdi
0x18003a04f  jz      short loc_18003A061
0x18003a051  test    byte ptr [rcx+1Ch], 8
0x18003a055  jz      short loc_18003A061
0x18003a057  test    byte ptr [rax+44h], 80h
0x18003a05b  jz      loc_18003A2C7
0x18003a061  mov     edx, [rdx]
0x18003a063  test    edx, edx
0x18003a065  jle     loc_18003A2C7
0x18003a06b  mov     rdi, [rax+8]
0x18003a06f  add     edx, edx
0x18003a071  mov     rax, [rcx+28h]
0x18003a075  mov     r13, [rsi+8]
0x18003a079  mov     rcx, [rcx+20h]
0x18003a07d  mov     [rbp+0D0h+var_148], rdi
0x18003a081  mov     rax, [rax+0A8h]
0x18003a088  mov     [rsp+1D0h+var_158], rax
0x18003a08d  mov     [rsp+1D0h+var_170], r13
0x18003a092  call    UFLNewPtr
0x18003a097  mov     r14, rax
0x18003a09a  test    rax, rax
0x18003a09d  jz      loc_18003A2C2
0x18003a0a3  mov     edx, [rsi]
0x18003a0a5  mov     r9, rax
0x18003a0a8  mov     r8, r13
0x18003a0ab  mov     rcx, rdi
0x18003a0ae  call    CFFGIDsToCIDs
0x18003a0b3  xor     r9d, r9d
0x18003a0b6  movzx   edi, ax
0x18003a0b9  cmp     r9w, ax
0x18003a0bd  jnz     loc_18003A2AB
0x18003a0c3  mov     r12d, r9d
0x18003a0c6  cmp     [rsi], r9d
0x18003a0c9  jle     loc_18003A2AB
0x18003a0cf  mov     rax, [rbx+78h]
0x18003a0d3  movsxd  r15, r12d
0x18003a0d6  movzx   r10d, word ptr [r13+r15*4+0]
0x18003a0dc  cmp     r10d, [rax+4]
0x18003a0e0  jnb     loc_18003A29F
0x18003a0e6  mov     rax, [rbx+30h]
0x18003a0ea  mov     r13d, r10d
0x18003a0ed  shr     r13, 3
0x18003a0f1  mov     r8d, r10d
0x18003a0f4  and     r8d, 7
0x18003a0f8  mov     [rsp+1D0h+var_15C], r8d
0x18003a0fd  mov     rcx, [rax+20h]
0x18003a101  mov     eax, 1
0x18003a106  mov     dl, [rcx+r13]
0x18003a10a  mov     ecx, r8d
0x18003a10d  shl     eax, cl
0x18003a10f  test    al, dl
0x18003a111  jnz     loc_18003A29A
0x18003a117  lea     rax, [rsp+1D0h+var_168]
0x18003a11c  mov     [rsp+1D0h+var_160], r9d
0x18003a121  mov     [rsp+1D0h+var_188], rax
0x18003a126  lea     r8, [rsp+1D0h+var_160]
0x18003a12b  mov     [rsp+1D0h+var_190], r9b
0x18003a130  lea     rax, [rsp+1D0h+var_180]
0x18003a135  mov     [rsp+1D0h+var_198], rax
0x18003a13a  movzx   edx, r10w
0x18003a13e  lea     rax, [rsp+1D0h+var_178]
0x18003a143  mov     [rsp+1D0h+var_17C], r9d
0x18003a148  mov     [rsp+1D0h+var_1A0], rax
0x18003a14d  mov     rcx, rbx
0x18003a150  lea     rax, [rsp+1D0h+var_164]
0x18003a155  mov     [rsp+1D0h+var_174], r9d
0x18003a15a  mov     [rsp+1D0h+var_1A8], rax
0x18003a15f  lea     rax, [rsp+1D0h+var_174]
0x18003a164  mov     [rsp+1D0h+var_164], r9d
0x18003a169  mov     [rsp+1D0h+var_178], r9d
0x18003a16e  mov     [rsp+1D0h+var_168], r9d
0x18003a173  mov     [rsp+1D0h+var_180], r9b
0x18003a178  lea     r9, [rsp+1D0h+var_17C]
0x18003a17d  mov     [rsp+1D0h+var_1B0], rax
0x18003a182  call    GetMetrics2FromTTF
0x18003a187  mov     eax, [rsp+1D0h+var_178]
0x18003a18b  lea     r8, aLd0LdLdLd; "%ld [0 %ld %ld %ld] "
0x18003a192  mov     ecx, [rsp+1D0h+var_17C]
0x18003a196  mov     edx, 100h; cchDest
0x18003a19b  movzx   r9d, word ptr [r14+r15*2]
0x18003a1a0  neg     ecx
0x18003a1a2  mov     dword ptr [rsp+1D0h+var_1A0], eax
0x18003a1a6  mov     eax, [rsp+1D0h+var_174]
0x18003a1aa  mov     dword ptr [rsp+1D0h+var_1A8], eax
0x18003a1ae  mov     dword ptr [rsp+1D0h+var_1B0], ecx
0x18003a1b2  lea     rcx, [rbp+0D0h+pszDest]; pszDest
0x18003a1b6  call    StringCchPrintfA
0x18003a1bb  cmp     [rbp+0D0h+pszDest], 0
0x18003a1bf  jz      short loc_18003A1EA
0x18003a1c1  lea     rax, [rbp+0D0h+pszDest]
0x18003a1c5  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003a1c9  inc     r8
0x18003a1cc  cmp     byte ptr [rax+r8], 0
0x18003a1d1  jnz     short loc_18003A1C9
0x18003a1d3  mov     rcx, [rsp+1D0h+var_158]
0x18003a1d8  lea     rdx, [rbp+0D0h+pszDest]
0x18003a1dc  mov     r9b, 1
0x18003a1df  call    StrmPutBytes
0x18003a1e4  movzx   r15d, ax
0x18003a1e8  jmp     short loc_18003A1ED
0x18003a1ea  xor     r15d, r15d
0x18003a1ed  cmp     qword ptr [rbx+0A0h], 0
0x18003a1f5  movzx   edi, r15w
0x18003a1f9  jz      short loc_18003A20E
0x18003a1fb  test    byte ptr [rbx+1Ch], 8
0x18003a1ff  jz      short loc_18003A20E
0x18003a201  mov     r9, [rbp+0D0h+var_150]
0x18003a205  lea     rax, aHf; "-hf"
0x18003a20c  jmp     short loc_18003A245
0x18003a20e  mov     rax, [rbp+0D0h+var_148]
0x18003a212  add     rax, 5Ch ; '\'
0x18003a216  cmp     dword ptr [rbx+88h], 0
0x18003a21d  jnz     short loc_18003A23E
0x18003a21f  cmp     dword ptr [rbx+4], 5
0x18003a223  lea     rcx, aAdbcfb; "ADBCFB+"
0x18003a22a  lea     r9, aAdbcfa; "ADBCFA+"
0x18003a231  cmovnz  r9, rcx
0x18003a235  lea     r8, aSST0addcffmtx2_0; "/%s%s T0AddCFFMtx2"
0x18003a23c  jmp     short loc_18003A24C
0x18003a23e  lea     r9, aAdbcff; "ADBCFF+"
0x18003a245  lea     r8, aSST0addcffmtx2; " /%s%s T0AddCFFMtx2"
0x18003a24c  mov     edx, 100h; cchDest
0x18003a251  mov     [rsp+1D0h+var_1B0], rax
0x18003a256  lea     rcx, [rbp+0D0h+pszDest]; pszDest
0x18003a25a  call    StringCchPrintfA
0x18003a25f  xor     r9d, r9d
0x18003a262  cmp     r9w, r15w
0x18003a266  jnz     short loc_18003A29A
0x18003a268  mov     rcx, [rsp+1D0h+var_158]
0x18003a26d  lea     rdx, [rbp+0D0h+pszDest]
0x18003a271  call    StrmPutStringEOL
0x18003a276  xor     r9d, r9d
0x18003a279  movzx   edi, ax
0x18003a27c  cmp     r9w, ax
0x18003a280  jnz     short loc_18003A29A
0x18003a282  mov     rcx, [rbx+30h]
0x18003a286  mov     eax, [rsp+1D0h+var_15C]
0x18003a28a  mov     rdx, [rcx+20h]
0x18003a28e  movzx   ecx, byte ptr [rdx+r13]
0x18003a293  bts     ecx, eax
0x18003a296  mov     [rdx+r13], cl
0x18003a29a  mov     r13, [rsp+1D0h+var_170]
0x18003a29f  inc     r12d
0x18003a2a2  cmp     r12d, [rsi]
0x18003a2a5  jl      loc_18003A0CF
0x18003a2ab  mov     rax, [rbx+20h]
0x18003a2af  lea     rcx, [r14-8]
0x18003a2b3  mov     rdx, [rax+20h]
0x18003a2b7  mov     rax, [rax+8]
0x18003a2bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a2c0  jmp     short loc_18003A2C7
0x18003a2c2  mov     edi, 6
0x18003a2c7  movzx   eax, di
0x18003a2ca  mov     rcx, [rbp+0D0h+var_40]
0x18003a2d1  xor     rcx, rsp; StackCookie
0x18003a2d4  call    __security_check_cookie
0x18003a2d9  mov     rbx, [rsp+1D0h+arg_18]
0x18003a2e1  add     rsp, 1A0h
0x18003a2e8  pop     r15
0x18003a2ea  pop     r14
0x18003a2ec  pop     r13
0x18003a2ee  pop     r12
0x18003a2f0  pop     rdi
0x18003a2f1  pop     rsi
0x18003a2f2  pop     rbp
0x18003a2f3  retn
```
