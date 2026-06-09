# TraceLoggingCorrelationVector::Extend(char const *,bool)

- ea: `0x18001f0a4`
- end: `0x18001f312`
- name: `?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z`
- size: `622`
- prototype: `struct TraceLoggingCorrelationVector *__fastcall(const char *, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001f318`

## callees

- `0x180005890`
- `0x180005d6c`
- `0x180006938`
- `0x18001d24c`
- `0x18001d3d0`
- `0x18001f0a4`
- `0x180022018`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18001f21b`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18001f25a`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18001f272`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18001f2a7`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18001f21b`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18001f25a`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18001f272`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18001f2a7`
- `RPCRT4!UuidCreate` at `0x18001f159`
- `RPCRT4!UuidCreate` at `0x18001f1d6`
- `RPCRT4!UuidCreate` at `0x18001f159`
- `RPCRT4!UuidCreate` at `0x18001f1d6`

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
  UUID v11; // [rsp+20h] [rbp-58h] BYREF
  UUID Uuid; // [rsp+30h] [rbp-48h] BYREF

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
    v7 = (char *)operator new(0x90u, (const struct std::nothrow_t *)std::nothrow);
    v6 = v7;
    if ( v7 )
    {
      v7[130] = 65;
      Uuid = 0;
      UuidCreate(&Uuid);
      v11 = Uuid;
      TraceLoggingCorrelationVector::CreateCvFromGuid<12>(v6, &v11);
      goto LABEL_16;
    }
  }
  else
  {
    if ( v2 != 2 )
      return 0;
    v5 = (char *)operator new(0x90u, (const struct std::nothrow_t *)std::nothrow);
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
0x18001f0a4  mov     [rsp+arg_8], rbx
0x18001f0a9  mov     [rsp+arg_10], rbp
0x18001f0ae  push    rsi
0x18001f0af  push    rdi
0x18001f0b0  push    r13
0x18001f0b2  push    r14
0x18001f0b4  push    r15
0x18001f0b6  sub     rsp, 50h
0x18001f0ba  mov     rax, cs:__security_cookie
0x18001f0c1  xor     rax, rsp
0x18001f0c4  mov     [rsp+78h+var_38], rax
0x18001f0c9  xor     edx, edx
0x18001f0cb  mov     r14, rcx
0x18001f0ce  call    ?ValidateImpl@TraceLoggingCorrelationVector@@CA?AW4CvVersion@1@PEBD_N@Z; TraceLoggingCorrelationVector::ValidateImpl(char const *,bool)
0x18001f0d3  test    al, al
0x18001f0d5  jz      loc_18001F2EA
0x18001f0db  mov     ebp, 41h ; 'A'
0x18001f0e0  cmp     al, 1
0x18001f0e2  lea     r13d, [rbp+40h]
0x18001f0e6  cmovnz  ebp, r13d
0x18001f0ea  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001f0ee  inc     rdi
0x18001f0f1  cmp     byte ptr [r14+rdi], 0
0x18001f0f6  jnz     short loc_18001F0EE
0x18001f0f8  lea     rcx, [rbp-1]
0x18001f0fc  cmp     rdi, rcx
0x18001f0ff  jb      short loc_18001F113
0x18001f101  jnz     loc_18001F2EA
0x18001f107  cmp     byte ptr [rdi+r14-1], 21h ; '!'
0x18001f10d  jnz     loc_18001F2EA
0x18001f113  movzx   ecx, al
0x18001f116  sub     ecx, 1
0x18001f119  jz      loc_18001F1A9
0x18001f11f  cmp     ecx, 1
0x18001f122  jnz     loc_18001F2EA
0x18001f128  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001f12f  mov     ecx, 90h; unsigned __int64
0x18001f134  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001f139  mov     rbx, rax
0x18001f13c  test    rax, rax
0x18001f13f  jz      loc_18001F1F6
0x18001f145  xorps   xmm0, xmm0
0x18001f148  mov     [rax+82h], r13b
0x18001f14f  lea     rcx, [rsp+78h+Uuid]; Uuid
0x18001f154  movups  xmmword ptr [rsp+78h+Uuid.Data1], xmm0
0x18001f159  call    cs:__imp_UuidCreate
0x18001f15f  movaps  xmm0, xmmword ptr [rsp+78h+Uuid.Data1]
0x18001f164  mov     rax, 1900000000h
0x18001f16e  movdqa  xmmword ptr [rsp+78h+Uuid.Data1], xmm0
0x18001f174  mov     r8, r13; Size
0x18001f177  mov     byte ptr [rbx+81h], 17h
0x18001f17e  xor     edx, edx; Val
0x18001f180  mov     rcx, rbx; void *
0x18001f183  mov     [rbx+88h], rax
0x18001f18a  call    memset_0
0x18001f18f  mov     r8, rbx
0x18001f192  lea     rcx, [rsp+78h+Uuid]
0x18001f197  mov     edx, 10h
0x18001f19c  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x18001f1a1  mov     word ptr [rbx+16h], 2Eh ; '.'
0x18001f1a7  jmp     short loc_18001F1F8
0x18001f1a9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001f1b0  mov     ecx, 90h; unsigned __int64
0x18001f1b5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001f1ba  mov     rbx, rax
0x18001f1bd  test    rax, rax
0x18001f1c0  jz      short loc_18001F1F6
0x18001f1c2  xorps   xmm0, xmm0
0x18001f1c5  mov     byte ptr [rax+82h], 41h ; 'A'
0x18001f1cc  lea     rcx, [rsp+78h+Uuid]; Uuid
0x18001f1d1  movups  xmmword ptr [rsp+78h+Uuid.Data1], xmm0
0x18001f1d6  call    cs:__imp_UuidCreate
0x18001f1dc  movaps  xmm0, xmmword ptr [rsp+78h+Uuid.Data1]
0x18001f1e1  lea     rdx, [rsp+78h+var_58]
0x18001f1e6  mov     rcx, rbx
0x18001f1e9  movdqa  [rsp+78h+var_58], xmm0
0x18001f1ef  call    ??$CreateCvFromGuid@$0M@@TraceLoggingCorrelationVector@@AEAAXU_GUID@@@Z; TraceLoggingCorrelationVector::CreateCvFromGuid<12>(_GUID)
0x18001f1f4  jmp     short loc_18001F1F8
0x18001f1f6  xor     ebx, ebx
0x18001f1f8  test    rbx, rbx
0x18001f1fb  jz      loc_18001F2EA
0x18001f201  test    rdi, rdi
0x18001f204  jz      short loc_18001F23E
0x18001f206  cmp     byte ptr [rdi+r14-1], 21h ; '!'
0x18001f20c  jnz     short loc_18001F23E
0x18001f20e  lea     r9, [rdi-1]
0x18001f212  mov     r8, r14
0x18001f215  mov     rdx, r13
0x18001f218  mov     rcx, rbx
0x18001f21b  call    cs:__imp__o_strncpy_s
0x18001f221  lea     eax, [rdi-1]
0x18001f224  lea     rsi, [rbx+81h]
0x18001f22b  mov     [rsi], al
0x18001f22d  lea     rax, [rdi+1]
0x18001f231  shl     rax, 20h
0x18001f235  mov     [rbx+88h], rax
0x18001f23c  jmp     short loc_18001F28A
0x18001f23e  lea     rax, [rbp-2]
0x18001f242  mov     r9, rdi
0x18001f245  lea     rsi, [rbx+81h]
0x18001f24c  mov     r8, r14
0x18001f24f  mov     rdx, r13
0x18001f252  mov     rcx, rbx
0x18001f255  cmp     rdi, rax
0x18001f258  jnz     short loc_18001F265
0x18001f25a  call    cs:__imp__o_strncpy_s
0x18001f260  mov     [rsi], dil
0x18001f263  jmp     short loc_18001F27F
0x18001f265  lea     rax, [rbp-3]
0x18001f269  lea     r15d, [rdi+1]
0x18001f26d  cmp     rdi, rax
0x18001f270  jnz     short loc_18001F2A7
0x18001f272  call    cs:__imp__o_strncpy_s
0x18001f278  mov     byte ptr [rdi+rbx], 2Eh ; '.'
0x18001f27c  mov     [rsi], r15b
0x18001f27f  shl     rbp, 20h
0x18001f283  mov     [rbx+88h], rbp
0x18001f28a  mov     rax, [rbx+88h]
0x18001f291  mov     rcx, 8000000000000000h
0x18001f29b  or      rax, rcx
0x18001f29e  mov     [rbx+88h], rax
0x18001f2a5  jmp     short loc_18001F2DE
0x18001f2a7  call    cs:__imp__o_strncpy_s
0x18001f2ad  mov     byte ptr [rdi+rbx], 2Eh ; '.'
0x18001f2b1  lea     rcx, [rdi+3]
0x18001f2b5  shl     rcx, 20h
0x18001f2b9  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001f2c3  mov     [rsi], r15b
0x18001f2c6  mov     [rbx+88h], rcx
0x18001f2cd  mov     rcx, [rbx+88h]
0x18001f2d4  and     rcx, rax
0x18001f2d7  mov     [rbx+88h], rcx
0x18001f2de  movzx   ecx, byte ptr [rsi]
0x18001f2e1  mov     rax, rbx
0x18001f2e4  mov     byte ptr [rcx+rbx], 0
0x18001f2e8  jmp     short loc_18001F2EC
0x18001f2ea  xor     eax, eax
0x18001f2ec  mov     rcx, [rsp+78h+var_38]
0x18001f2f1  xor     rcx, rsp; StackCookie
0x18001f2f4  call    __security_check_cookie
0x18001f2f9  lea     r11, [rsp+78h+var_28]
0x18001f2fe  mov     rbx, [r11+38h]
0x18001f302  mov     rbp, [r11+40h]
0x18001f306  mov     rsp, r11
0x18001f309  pop     r15
0x18001f30b  pop     r14
0x18001f30d  pop     r13
0x18001f30f  pop     rdi
0x18001f310  pop     rsi
0x18001f311  retn
```
