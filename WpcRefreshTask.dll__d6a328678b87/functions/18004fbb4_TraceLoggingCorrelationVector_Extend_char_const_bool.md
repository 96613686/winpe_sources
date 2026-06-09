# TraceLoggingCorrelationVector::Extend(char const *,bool)

- ea: `0x18004fbb4`
- end: `0x18004fe52`
- name: `?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z`
- size: `670`
- prototype: `struct TraceLoggingCorrelationVector *__fastcall(const char *, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180076364`

## callees

- `0x1800060a0`
- `0x1800065c8`
- `0x180006ed4`
- `0x18004f950`
- `0x18004fbb4`
- `0x180050164`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18004fd5b`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18004fd9a`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18004fdb2`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18004fde7`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18004fd5b`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18004fd9a`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18004fdb2`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18004fde7`
- `RPCRT4!UuidCreate` at `0x18004fc69`
- `RPCRT4!UuidCreate` at `0x18004fce6`
- `RPCRT4!UuidCreate` at `0x18004fc69`
- `RPCRT4!UuidCreate` at `0x18004fce6`

## pseudocode

```c
struct TraceLoggingCorrelationVector *__fastcall TraceLoggingCorrelationVector::Extend(const char *a1)
{
  char v2; // al
  __int64 v3; // rbp
  unsigned __int64 v4; // rdi
  char *v5; // rax
  char *v6; // rbx
  char *v7; // rax
  _BYTE *v8; // rsi
  char v9; // r15
  struct TraceLoggingCorrelationVector *result; // rax
  UUID Uuid; // [rsp+20h] [rbp-48h] BYREF

  v2 = TraceLoggingCorrelationVector::ValidateImpl(a1, 0);
  if ( !v2 )
    return 0;
  v3 = 65;
  if ( v2 != 1 )
    v3 = 129;
  v4 = -1;
  do
    ++v4;
  while ( a1[v4] );
  if ( v4 >= v3 - 1 && (v4 != v3 - 1 || a1[v4 - 1] != 33) )
    return 0;
  if ( v2 == 1 )
  {
    v7 = (char *)operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
    v6 = v7;
    if ( v7 )
    {
      v7[130] = 65;
      Uuid = 0;
      UuidCreate(&Uuid);
      v6[129] = 17;
      *((_QWORD *)v6 + 17) = 0x1300000000LL;
      memset_0(v6, 0, 0x81u);
      TLV::Base64Encode<129>(&Uuid, 12, v6);
      *((_WORD *)v6 + 8) = 46;
      goto LABEL_16;
    }
  }
  else
  {
    if ( v2 != 2 )
      return 0;
    v5 = (char *)operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
    v6 = v5;
    if ( v5 )
    {
      v5[130] = -127;
      Uuid = 0;
      UuidCreate(&Uuid);
      v6[129] = 23;
      *((_QWORD *)v6 + 17) = 0x1900000000LL;
      memset_0(v6, 0, 0x81u);
      TLV::Base64Encode<129>(&Uuid, 16, v6);
      *((_WORD *)v6 + 11) = 46;
      goto LABEL_16;
    }
  }
  v6 = 0;
LABEL_16:
  if ( v6 )
  {
    if ( v4 && a1[v4 - 1] == 33 )
    {
      _o_strncpy_s(v6, 129, a1, v4 - 1);
      v8 = v6 + 129;
      v6[129] = v4 - 1;
      *((_QWORD *)v6 + 17) = (v4 + 1) << 32;
    }
    else
    {
      v8 = v6 + 129;
      if ( v4 == v3 - 2 )
      {
        _o_strncpy_s(v6, 129, a1, v4);
        *v8 = v4;
      }
      else
      {
        v9 = v4 + 1;
        if ( v4 != v3 - 3 )
        {
          _o_strncpy_s(v6, 129, a1, v4);
          v6[v4] = 46;
          *v8 = v9;
          *((_QWORD *)v6 + 17) = (v4 + 3) << 32;
          *((_QWORD *)v6 + 17) &= ~0x8000000000000000uLL;
          goto LABEL_27;
        }
        _o_strncpy_s(v6, 129, a1, v4);
        v6[v4] = 46;
        *v8 = v9;
      }
      *((_QWORD *)v6 + 17) = v3 << 32;
    }
    *((_QWORD *)v6 + 17) |= 0x8000000000000000uLL;
LABEL_27:
    result = (struct TraceLoggingCorrelationVector *)v6;
    v6[(unsigned __int8)*v8] = 0;
    return result;
  }
  return 0;
}

```

## disassembly

```asm
0x18004fbb4  mov     [rsp+arg_8], rbx
0x18004fbb9  mov     [rsp+arg_10], rbp
0x18004fbbe  push    rsi
0x18004fbbf  push    rdi
0x18004fbc0  push    r13
0x18004fbc2  push    r14
0x18004fbc4  push    r15
0x18004fbc6  sub     rsp, 40h
0x18004fbca  mov     rax, cs:__security_cookie
0x18004fbd1  xor     rax, rsp
0x18004fbd4  mov     [rsp+68h+var_38], rax
0x18004fbd9  xor     edx, edx
0x18004fbdb  mov     r14, rcx
0x18004fbde  call    ?ValidateImpl@TraceLoggingCorrelationVector@@CA?AW4CvVersion@1@PEBD_N@Z; TraceLoggingCorrelationVector::ValidateImpl(char const *,bool)
0x18004fbe3  test    al, al
0x18004fbe5  jz      loc_18004FE2A
0x18004fbeb  mov     ebp, 41h ; 'A'
0x18004fbf0  cmp     al, 1
0x18004fbf2  lea     r13d, [rbp+40h]
0x18004fbf6  cmovnz  ebp, r13d
0x18004fbfa  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004fbfe  inc     rdi
0x18004fc01  cmp     byte ptr [r14+rdi], 0
0x18004fc06  jnz     short loc_18004FBFE
0x18004fc08  lea     rcx, [rbp-1]
0x18004fc0c  cmp     rdi, rcx
0x18004fc0f  jb      short loc_18004FC23
0x18004fc11  jnz     loc_18004FE2A
0x18004fc17  cmp     byte ptr [rdi+r14-1], 21h ; '!'
0x18004fc1d  jnz     loc_18004FE2A
0x18004fc23  movzx   ecx, al
0x18004fc26  sub     ecx, 1
0x18004fc29  jz      loc_18004FCB9
0x18004fc2f  cmp     ecx, 1
0x18004fc32  jnz     loc_18004FE2A
0x18004fc38  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004fc3f  mov     ecx, 90h; unsigned __int64
0x18004fc44  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004fc49  mov     rbx, rax
0x18004fc4c  test    rax, rax
0x18004fc4f  jz      loc_18004FD36
0x18004fc55  xorps   xmm0, xmm0
0x18004fc58  mov     [rax+82h], r13b
0x18004fc5f  lea     rcx, [rsp+68h+Uuid]; Uuid
0x18004fc64  movups  xmmword ptr [rsp+68h+Uuid.Data1], xmm0
0x18004fc69  call    cs:__imp_UuidCreate
0x18004fc6f  movaps  xmm0, xmmword ptr [rsp+68h+Uuid.Data1]
0x18004fc74  mov     rax, 1900000000h
0x18004fc7e  movdqa  xmmword ptr [rsp+68h+Uuid.Data1], xmm0
0x18004fc84  mov     r8, r13; Size
0x18004fc87  mov     byte ptr [rbx+81h], 17h
0x18004fc8e  xor     edx, edx; Val
0x18004fc90  mov     rcx, rbx; void *
0x18004fc93  mov     [rbx+88h], rax
0x18004fc9a  call    memset_0
0x18004fc9f  mov     r8, rbx
0x18004fca2  lea     rcx, [rsp+68h+Uuid]
0x18004fca7  mov     edx, 10h
0x18004fcac  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x18004fcb1  mov     word ptr [rbx+16h], 2Eh ; '.'
0x18004fcb7  jmp     short loc_18004FD38
0x18004fcb9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004fcc0  mov     ecx, 90h; unsigned __int64
0x18004fcc5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004fcca  mov     rbx, rax
0x18004fccd  test    rax, rax
0x18004fcd0  jz      short loc_18004FD36
0x18004fcd2  xorps   xmm0, xmm0
0x18004fcd5  mov     byte ptr [rax+82h], 41h ; 'A'
0x18004fcdc  lea     rcx, [rsp+68h+Uuid]; Uuid
0x18004fce1  movups  xmmword ptr [rsp+68h+Uuid.Data1], xmm0
0x18004fce6  call    cs:__imp_UuidCreate
0x18004fcec  movaps  xmm0, xmmword ptr [rsp+68h+Uuid.Data1]
0x18004fcf1  mov     rax, 1300000000h
0x18004fcfb  movdqa  xmmword ptr [rsp+68h+Uuid.Data1], xmm0
0x18004fd01  mov     r8, r13; Size
0x18004fd04  mov     byte ptr [rbx+81h], 11h
0x18004fd0b  xor     edx, edx; Val
0x18004fd0d  mov     rcx, rbx; void *
0x18004fd10  mov     [rbx+88h], rax
0x18004fd17  call    memset_0
0x18004fd1c  mov     r8, rbx
0x18004fd1f  lea     rcx, [rsp+68h+Uuid]
0x18004fd24  mov     edx, 0Ch
0x18004fd29  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x18004fd2e  mov     word ptr [rbx+10h], 2Eh ; '.'
0x18004fd34  jmp     short loc_18004FD38
0x18004fd36  xor     ebx, ebx
0x18004fd38  test    rbx, rbx
0x18004fd3b  jz      loc_18004FE2A
0x18004fd41  test    rdi, rdi
0x18004fd44  jz      short loc_18004FD7E
0x18004fd46  cmp     byte ptr [rdi+r14-1], 21h ; '!'
0x18004fd4c  jnz     short loc_18004FD7E
0x18004fd4e  lea     r9, [rdi-1]
0x18004fd52  mov     r8, r14
0x18004fd55  mov     rdx, r13
0x18004fd58  mov     rcx, rbx
0x18004fd5b  call    cs:__imp__o_strncpy_s
0x18004fd61  lea     eax, [rdi-1]
0x18004fd64  lea     rsi, [rbx+81h]
0x18004fd6b  mov     [rsi], al
0x18004fd6d  lea     rax, [rdi+1]
0x18004fd71  shl     rax, 20h
0x18004fd75  mov     [rbx+88h], rax
0x18004fd7c  jmp     short loc_18004FDCA
0x18004fd7e  lea     rax, [rbp-2]
0x18004fd82  mov     r9, rdi
0x18004fd85  lea     rsi, [rbx+81h]
0x18004fd8c  mov     r8, r14
0x18004fd8f  mov     rdx, r13
0x18004fd92  mov     rcx, rbx
0x18004fd95  cmp     rdi, rax
0x18004fd98  jnz     short loc_18004FDA5
0x18004fd9a  call    cs:__imp__o_strncpy_s
0x18004fda0  mov     [rsi], dil
0x18004fda3  jmp     short loc_18004FDBF
0x18004fda5  lea     rax, [rbp-3]
0x18004fda9  lea     r15d, [rdi+1]
0x18004fdad  cmp     rdi, rax
0x18004fdb0  jnz     short loc_18004FDE7
0x18004fdb2  call    cs:__imp__o_strncpy_s
0x18004fdb8  mov     byte ptr [rdi+rbx], 2Eh ; '.'
0x18004fdbc  mov     [rsi], r15b
0x18004fdbf  shl     rbp, 20h
0x18004fdc3  mov     [rbx+88h], rbp
0x18004fdca  mov     rax, [rbx+88h]
0x18004fdd1  mov     rcx, 8000000000000000h
0x18004fddb  or      rax, rcx
0x18004fdde  mov     [rbx+88h], rax
0x18004fde5  jmp     short loc_18004FE1E
0x18004fde7  call    cs:__imp__o_strncpy_s
0x18004fded  mov     byte ptr [rdi+rbx], 2Eh ; '.'
0x18004fdf1  lea     rcx, [rdi+3]
0x18004fdf5  shl     rcx, 20h
0x18004fdf9  mov     rax, 7FFFFFFFFFFFFFFFh
0x18004fe03  mov     [rsi], r15b
0x18004fe06  mov     [rbx+88h], rcx
0x18004fe0d  mov     rcx, [rbx+88h]
0x18004fe14  and     rcx, rax
0x18004fe17  mov     [rbx+88h], rcx
0x18004fe1e  movzx   ecx, byte ptr [rsi]
0x18004fe21  mov     rax, rbx
0x18004fe24  mov     byte ptr [rcx+rbx], 0
0x18004fe28  jmp     short loc_18004FE2C
0x18004fe2a  xor     eax, eax
0x18004fe2c  mov     rcx, [rsp+68h+var_38]
0x18004fe31  xor     rcx, rsp; StackCookie
0x18004fe34  call    __security_check_cookie
0x18004fe39  lea     r11, [rsp+68h+var_28]
0x18004fe3e  mov     rbx, [r11+38h]
0x18004fe42  mov     rbp, [r11+40h]
0x18004fe46  mov     rsp, r11
0x18004fe49  pop     r15
0x18004fe4b  pop     r14
0x18004fe4d  pop     r13
0x18004fe4f  pop     rdi
0x18004fe50  pop     rsi
0x18004fe51  retn
```
