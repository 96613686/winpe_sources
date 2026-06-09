# TraceLoggingCorrelationVector::Extend(char const *,bool)

- ea: `0x180031f1c`
- end: `0x1800322d0`
- name: `?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z`
- size: `948`
- prototype: `struct TraceLoggingCorrelationVector *__fastcall(const char *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180032ac0`
- `0x180032cfc`

## callees

- `0x1800026b0`
- `0x18000316c`
- `0x18000d7a0`
- `0x18002cecc`
- `0x180031f1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__set_errno` at `0x18003204d`
- `api-ms-win-crt-private-l1-1-0!_o__set_errno` at `0x18003204d`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180032045`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x1800321fa`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18003223c`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180032254`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180032289`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180032045`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x1800321fa`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18003223c`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180032254`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180032289`
- `api-ms-win-crt-private-l1-1-0!_o_strtol` at `0x18003205d`
- `api-ms-win-crt-private-l1-1-0!_o_strtol` at `0x18003205d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003207a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003207a`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180031f46`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180032010`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180031f46`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180032010`
- `RPCRT4!UuidCreate` at `0x180032110`
- `RPCRT4!UuidCreate` at `0x180032188`
- `RPCRT4!UuidCreate` at `0x180032110`
- `RPCRT4!UuidCreate` at `0x180032188`

## pseudocode

```c
struct TraceLoggingCorrelationVector *__fastcall TraceLoggingCorrelationVector::Extend(const char *a1)
{
  unsigned __int64 v2; // rdx
  int v3; // r8d
  char v4; // r12
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // r14
  struct TraceLoggingCorrelationVector *result; // rax
  unsigned __int64 i; // rcx
  __int64 v9; // r9
  unsigned __int64 v10; // r15
  char *v11; // rax
  unsigned __int64 v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r15
  char *v17; // rax
  char *v18; // rbx
  char *v19; // rax
  _BYTE *v20; // r14
  char v21; // r12
  char String[16]; // [rsp+20h] [rbp-28h] BYREF

  v2 = strchr(a1, 46) - a1;
  if ( v2 == 22 )
  {
    v4 = 2;
  }
  else
  {
    if ( v2 != 16 )
      return 0;
    v4 = 1;
  }
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( a1[v6] );
  if ( v4 == 1 )
  {
    if ( v6 > 0x41 )
      return 0;
  }
  else if ( v6 > 0x81 )
  {
    return 0;
  }
  for ( i = 0; i < v2; ++i )
  {
    LOBYTE(v3) = a1[i];
    if ( (unsigned __int8)(v3 - 43) <= 0x2Fu )
    {
      v9 = 0xFFFFFFC07FF1LL;
      if ( _bittest64(&v9, (unsigned int)(v3 - 43)) )
        continue;
    }
    if ( (unsigned __int8)(v3 - 97) > 0x19u )
      return 0;
  }
  do
  {
    if ( a1[i] != 46 )
      return 0;
    v10 = i + 1;
    if ( i + 1 >= v6 )
      return 0;
    *(_QWORD *)String = 0;
    *(_WORD *)&String[8] = 0;
    String[10] = 0;
    v11 = strchr(&a1[v10], 46);
    v12 = v11 ? &v11[-v10] - a1 : v6 - v10;
    if ( v12 >= 0xB )
      return 0;
    _o_strncpy_s(String, 11, &a1[v10], v12);
    _o__set_errno(0);
    if ( !strtol(String, 0, 10) && String[0] != 48 && String[1] )
      return 0;
    if ( *(_DWORD *)_o__errno(v14, v13, v15) == 34 )
      return 0;
    i = v10 + v12;
  }
  while ( v10 + v12 < v6 );
  v16 = 65;
  if ( v4 != 1 )
    v16 = 129;
  do
    ++v5;
  while ( a1[v5] );
  if ( v5 < v16 - 1 || v5 == v16 - 1 && a1[v5 - 1] == 33 )
  {
    if ( v4 == 1 )
    {
      v19 = (char *)operator new(0x90u, (const struct std::nothrow_t *)std::nothrow);
      v18 = v19;
      if ( v19 )
      {
        v19[130] = 65;
        *(_OWORD *)String = 0;
        UuidCreate((UUID *)String);
        v18[129] = 17;
        *((_QWORD *)v18 + 17) = 0x1300000000LL;
        memset_0(v18, 0, 0x81u);
        TLV::Base64Encode<129>(String, 12, v18);
        *((_WORD *)v18 + 8) = 46;
        goto LABEL_40;
      }
    }
    else
    {
      if ( v4 != 2 )
        return 0;
      v17 = (char *)operator new(0x90u, (const struct std::nothrow_t *)std::nothrow);
      v18 = v17;
      if ( v17 )
      {
        v17[130] = -127;
        *(_OWORD *)String = 0;
        UuidCreate((UUID *)String);
        v18[129] = 23;
        *((_QWORD *)v18 + 17) = 0x1900000000LL;
        memset_0(v18, 0, 0x81u);
        TLV::Base64Encode<129>(String, 16, v18);
        *((_WORD *)v18 + 11) = 46;
        goto LABEL_40;
      }
    }
    v18 = 0;
LABEL_40:
    if ( !v18 )
      return 0;
    if ( v5 && a1[v5 - 1] == 33 )
    {
      _o_strncpy_s(v18, 129, a1, v5 - 1);
      v20 = v18 + 129;
      v18[129] = v5 - 1;
      *((_QWORD *)v18 + 17) = (v5 + 1) << 32;
    }
    else
    {
      v20 = v18 + 129;
      if ( v5 == v16 - 2 )
      {
        _o_strncpy_s(v18, 129, a1, v5);
        *v20 = v5;
      }
      else
      {
        v21 = v5 + 1;
        if ( v5 != v16 - 3 )
        {
          _o_strncpy_s(v18, 129, a1, v5);
          v18[v5] = 46;
          *v20 = v21;
          *((_QWORD *)v18 + 17) = (v5 + 3) << 32;
          *((_QWORD *)v18 + 17) &= ~0x8000000000000000uLL;
          goto LABEL_51;
        }
        _o_strncpy_s(v18, 129, a1, v5);
        v18[v5] = 46;
        *v20 = v21;
      }
      *((_QWORD *)v18 + 17) = v16 << 32;
    }
    *((_QWORD *)v18 + 17) |= 0x8000000000000000uLL;
LABEL_51:
    result = (struct TraceLoggingCorrelationVector *)v18;
    v18[(unsigned __int8)*v20] = 0;
    return result;
  }
  return 0;
}

```

## disassembly

```asm
0x180031f1c  push    rbp
0x180031f1e  push    rbx
0x180031f1f  push    rsi
0x180031f20  push    rdi
0x180031f21  push    r12
0x180031f23  push    r13
0x180031f25  push    r14
0x180031f27  push    r15
0x180031f29  mov     rbp, rsp
0x180031f2c  sub     rsp, 48h
0x180031f30  mov     rax, cs:__security_cookie
0x180031f37  xor     rax, rsp
0x180031f3a  mov     [rbp+var_18], rax
0x180031f3e  mov     edx, 2Eh ; '.'; Val
0x180031f43  mov     rsi, rcx
0x180031f46  call    cs:__imp_strchr
0x180031f4c  mov     rdx, rax
0x180031f4f  sub     rdx, rsi
0x180031f52  cmp     rdx, 16h
0x180031f56  jnz     short loc_180031F5D
0x180031f58  mov     r12b, 2
0x180031f5b  jmp     short loc_180031F66
0x180031f5d  cmp     rdx, 10h
0x180031f61  jnz     short loc_180031F8A
0x180031f63  mov     r12b, 1
0x180031f66  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180031f6a  mov     r14, rdi
0x180031f6d  xor     r13d, r13d
0x180031f70  inc     r14
0x180031f73  cmp     [rsi+r14], r13b
0x180031f77  jnz     short loc_180031F70
0x180031f79  mov     eax, 81h
0x180031f7e  cmp     r12b, 1
0x180031f82  jnz     short loc_180031FA9
0x180031f84  cmp     r14, 41h ; 'A'
0x180031f88  jbe     short loc_180031FB4
0x180031f8a  xor     eax, eax
0x180031f8c  mov     rcx, [rbp+var_18]
0x180031f90  xor     rcx, rsp; StackCookie
0x180031f93  call    __security_check_cookie
0x180031f98  add     rsp, 48h
0x180031f9c  pop     r15
0x180031f9e  pop     r14
0x180031fa0  pop     r13
0x180031fa2  pop     r12
0x180031fa4  pop     rdi
0x180031fa5  pop     rsi
0x180031fa6  pop     rbx
0x180031fa7  pop     rbp
0x180031fa8  retn
0x180031fa9  cmp     r12b, 2
0x180031fad  jnz     short loc_180031FB4
0x180031faf  cmp     r14, rax
0x180031fb2  ja      short loc_180031F8A
0x180031fb4  mov     rcx, r13
0x180031fb7  test    rdx, rdx
0x180031fba  jz      short loc_180031FEA
0x180031fbc  mov     r8b, [rsi+rcx]
0x180031fc0  lea     eax, [r8-2Bh]
0x180031fc4  cmp     al, 2Fh ; '/'
0x180031fc6  ja      short loc_180031FD8
0x180031fc8  mov     r9, 0FFFFFFC07FF1h
0x180031fd2  bt      r9, rax
0x180031fd6  jb      short loc_180031FE2
0x180031fd8  sub     r8b, 61h ; 'a'
0x180031fdc  cmp     r8b, 19h
0x180031fe0  ja      short loc_180031F8A
0x180031fe2  inc     rcx
0x180031fe5  cmp     rcx, rdx
0x180031fe8  jb      short loc_180031FBC
0x180031fea  cmp     byte ptr [rsi+rcx], 2Eh ; '.'
0x180031fee  jnz     short loc_180031F8A
0x180031ff0  lea     r15, [rcx+1]
0x180031ff4  cmp     r15, r14
0x180031ff7  jnb     short loc_180031F8A
0x180031ff9  xor     eax, eax
0x180031ffb  lea     r13, [r15+rsi]
0x180031fff  mov     rcx, r13; Str
0x180032002  mov     qword ptr [rbp+String], rax
0x180032006  mov     word ptr [rbp+String+8], ax
0x18003200a  mov     [rbp+String+0Ah], al
0x18003200d  lea     edx, [rax+2Eh]; Val
0x180032010  call    cs:__imp_strchr
0x180032016  mov     rbx, rax
0x180032019  test    rax, rax
0x18003201c  jnz     short loc_180032026
0x18003201e  mov     rbx, r14
0x180032021  sub     rbx, r15
0x180032024  jmp     short loc_18003202C
0x180032026  sub     rbx, r15
0x180032029  sub     rbx, rsi
0x18003202c  cmp     rbx, 0Bh
0x180032030  jnb     loc_180031F8A
0x180032036  mov     r9, rbx
0x180032039  lea     rcx, [rbp+String]
0x18003203d  mov     r8, r13
0x180032040  mov     edx, 0Bh
0x180032045  call    cs:__imp__o_strncpy_s
0x18003204b  xor     ecx, ecx
0x18003204d  call    cs:__imp__o__set_errno
0x180032053  xor     edx, edx; EndPtr
0x180032055  lea     rcx, [rbp+String]; String
0x180032059  lea     r8d, [rdx+0Ah]; Radix
0x18003205d  call    cs:__imp_strtol
0x180032063  xor     r13d, r13d
0x180032066  test    eax, eax
0x180032068  jnz     short loc_18003207A
0x18003206a  cmp     [rbp+String], 30h ; '0'
0x18003206e  jz      short loc_18003207A
0x180032070  cmp     [rbp+String+1], r13b
0x180032074  jnz     loc_180031F8A
0x18003207a  call    cs:__imp__o__errno
0x180032080  cmp     dword ptr [rax], 22h ; '"'
0x180032083  jz      loc_180031F8A
0x180032089  lea     rcx, [r15+rbx]
0x18003208d  cmp     rcx, r14
0x180032090  jb      loc_180031FEA
0x180032096  mov     r15d, 41h ; 'A'
0x18003209c  cmp     r12b, 1
0x1800320a0  lea     r14d, [r15+40h]
0x1800320a4  cmovnz  r15d, r14d
0x1800320a8  inc     rdi
0x1800320ab  cmp     [rsi+rdi], r13b
0x1800320af  jnz     short loc_1800320A8
0x1800320b1  lea     rax, [r15-1]
0x1800320b5  cmp     rdi, rax
0x1800320b8  jb      short loc_1800320CB
0x1800320ba  jnz     loc_180031F8A
0x1800320c0  cmp     byte ptr [rdi+rsi-1], 21h ; '!'
0x1800320c5  jnz     loc_180031F8A
0x1800320cb  movzx   ecx, r12b
0x1800320cf  sub     ecx, 1
0x1800320d2  jz      loc_18003215D
0x1800320d8  cmp     ecx, 1
0x1800320db  jnz     loc_180031F8A
0x1800320e1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800320e8  mov     ecx, 90h; unsigned __int64
0x1800320ed  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800320f2  mov     rbx, rax
0x1800320f5  test    rax, rax
0x1800320f8  jz      loc_1800321D5
0x1800320fe  xorps   xmm0, xmm0
0x180032101  mov     [rax+82h], r14b
0x180032108  lea     rcx, [rbp+String]; Uuid
0x18003210c  movups  xmmword ptr [rbp+String], xmm0
0x180032110  call    cs:__imp_UuidCreate
0x180032116  movaps  xmm0, xmmword ptr [rbp+String]
0x18003211a  mov     rax, 1900000000h
0x180032124  movdqa  xmmword ptr [rbp+String], xmm0
0x180032129  mov     r8, r14; Size
0x18003212c  mov     byte ptr [rbx+81h], 17h
0x180032133  xor     edx, edx; Val
0x180032135  mov     rcx, rbx; void *
0x180032138  mov     [rbx+88h], rax
0x18003213f  call    memset_0
0x180032144  mov     r8, rbx
0x180032147  lea     rcx, [rbp+String]
0x18003214b  mov     edx, 10h
0x180032150  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x180032155  mov     word ptr [rbx+16h], 2Eh ; '.'
0x18003215b  jmp     short loc_1800321D8
0x18003215d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180032164  mov     ecx, 90h; unsigned __int64
0x180032169  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003216e  mov     rbx, rax
0x180032171  test    rax, rax
0x180032174  jz      short loc_1800321D5
0x180032176  xorps   xmm0, xmm0
0x180032179  mov     byte ptr [rax+82h], 41h ; 'A'
0x180032180  lea     rcx, [rbp+String]; Uuid
0x180032184  movups  xmmword ptr [rbp+String], xmm0
0x180032188  call    cs:__imp_UuidCreate
0x18003218e  movaps  xmm0, xmmword ptr [rbp+String]
0x180032192  mov     rax, 1300000000h
0x18003219c  movdqa  xmmword ptr [rbp+String], xmm0
0x1800321a1  mov     r8, r14; Size
0x1800321a4  mov     byte ptr [rbx+81h], 11h
0x1800321ab  xor     edx, edx; Val
0x1800321ad  mov     rcx, rbx; void *
0x1800321b0  mov     [rbx+88h], rax
0x1800321b7  call    memset_0
0x1800321bc  mov     r8, rbx
0x1800321bf  lea     rcx, [rbp+String]
0x1800321c3  mov     edx, 0Ch
0x1800321c8  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x1800321cd  mov     word ptr [rbx+10h], 2Eh ; '.'
0x1800321d3  jmp     short loc_1800321D8
0x1800321d5  mov     rbx, r13
0x1800321d8  test    rbx, rbx
0x1800321db  jz      loc_180031F8A
0x1800321e1  test    rdi, rdi
0x1800321e4  jz      short loc_18003221E
0x1800321e6  cmp     byte ptr [rdi+rsi-1], 21h ; '!'
0x1800321eb  jnz     short loc_18003221E
0x1800321ed  lea     r9, [rdi-1]
0x1800321f1  mov     r8, rsi
0x1800321f4  mov     rdx, r14
0x1800321f7  mov     rcx, rbx
0x1800321fa  call    cs:__imp__o_strncpy_s
0x180032200  lea     eax, [rdi-1]
0x180032203  lea     r14, [rbx+81h]
0x18003220a  mov     [r14], al
0x18003220d  lea     rax, [rdi+1]
0x180032211  shl     rax, 20h
0x180032215  mov     [rbx+88h], rax
0x18003221c  jmp     short loc_18003226C
0x18003221e  lea     rax, [r15-2]
0x180032222  mov     r9, rdi
0x180032225  lea     r14, [rbx+81h]
0x18003222c  mov     r8, rsi
0x18003222f  mov     edx, 81h
0x180032234  mov     rcx, rbx
0x180032237  cmp     rdi, rax
0x18003223a  jnz     short loc_180032247
0x18003223c  call    cs:__imp__o_strncpy_s
0x180032242  mov     [r14], dil
0x180032245  jmp     short loc_180032261
0x180032247  lea     rax, [r15-3]
0x18003224b  lea     r12d, [rdi+1]
0x18003224f  cmp     rdi, rax
0x180032252  jnz     short loc_180032289
0x180032254  call    cs:__imp__o_strncpy_s
0x18003225a  mov     byte ptr [rdi+rbx], 2Eh ; '.'
0x18003225e  mov     [r14], r12b
0x180032261  shl     r15, 20h
0x180032265  mov     [rbx+88h], r15
0x18003226c  mov     rax, [rbx+88h]
0x180032273  mov     rcx, 8000000000000000h
0x18003227d  or      rax, rcx
0x180032280  mov     [rbx+88h], rax
0x180032287  jmp     short loc_1800322C0
0x180032289  call    cs:__imp__o_strncpy_s
0x18003228f  mov     byte ptr [rdi+rbx], 2Eh ; '.'
0x180032293  lea     rcx, [rdi+3]
0x180032297  shl     rcx, 20h
0x18003229b  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800322a5  mov     [r14], r12b
0x1800322a8  mov     [rbx+88h], rcx
0x1800322af  mov     rcx, [rbx+88h]
0x1800322b6  and     rcx, rax
0x1800322b9  mov     [rbx+88h], rcx
0x1800322c0  movzx   ecx, byte ptr [r14]
0x1800322c4  mov     rax, rbx
0x1800322c7  mov     [rcx+rbx], r13b
0x1800322cb  jmp     loc_180031F8C
```
