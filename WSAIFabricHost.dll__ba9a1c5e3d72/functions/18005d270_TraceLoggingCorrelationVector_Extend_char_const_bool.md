# TraceLoggingCorrelationVector::Extend(char const *,bool)

- ea: `0x18005d270`
- end: `0x18005d50e`
- name: `?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z`
- size: `670`
- prototype: `struct TraceLoggingCorrelationVector *__fastcall(const char *, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180065ea0`

## callees

- `0x180004ca0`
- `0x180005758`
- `0x180007aac`
- `0x180055534`
- `0x18005d270`
- `0x18006a284`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18005d417`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18005d456`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18005d46e`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18005d4a3`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18005d417`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18005d456`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18005d46e`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18005d4a3`
- `RPCRT4!UuidCreate` at `0x18005d325`
- `RPCRT4!UuidCreate` at `0x18005d3a2`
- `RPCRT4!UuidCreate` at `0x18005d325`
- `RPCRT4!UuidCreate` at `0x18005d3a2`

## pseudocode

```c
struct TraceLoggingCorrelationVector *__fastcall TraceLoggingCorrelationVector::Extend(const char *a1, __int64 a2)
{
  char v3; // al
  __int64 v4; // rbp
  unsigned __int64 v5; // rdi
  _BYTE *v6; // rax
  __int64 v7; // rbx
  _BYTE *v8; // rax
  _BYTE *v9; // rsi
  char v10; // r15
  struct TraceLoggingCorrelationVector *result; // rax
  UUID Uuid; // [rsp+20h] [rbp-48h] BYREF

  LOBYTE(a2) = 1;
  v3 = TraceLoggingCorrelationVector::ValidateImpl(a1, a2);
  if ( !v3 )
    return 0;
  v4 = 65;
  if ( v3 != 1 )
    v4 = 129;
  v5 = -1;
  do
    ++v5;
  while ( a1[v5] );
  if ( v5 >= v4 - 1 && (v5 != v4 - 1 || a1[v5 - 1] != 33) )
    return 0;
  if ( v3 == 1 )
  {
    v8 = operator new(0x90u, (const struct std::nothrow_t *)std::nothrow);
    v7 = (__int64)v8;
    if ( v8 )
    {
      v8[130] = 65;
      Uuid = 0;
      UuidCreate(&Uuid);
      *(_BYTE *)(v7 + 129) = 17;
      *(_QWORD *)(v7 + 136) = 0x1300000000LL;
      memset_0((void *)v7, 0, 0x81u);
      TLV::Base64Encode<129>((unsigned __int8 *)&Uuid, 0xCu, v7);
      *(_WORD *)(v7 + 16) = 46;
      goto LABEL_16;
    }
  }
  else
  {
    if ( v3 != 2 )
      return 0;
    v6 = operator new(0x90u, (const struct std::nothrow_t *)std::nothrow);
    v7 = (__int64)v6;
    if ( v6 )
    {
      v6[130] = -127;
      Uuid = 0;
      UuidCreate(&Uuid);
      *(_BYTE *)(v7 + 129) = 23;
      *(_QWORD *)(v7 + 136) = 0x1900000000LL;
      memset_0((void *)v7, 0, 0x81u);
      TLV::Base64Encode<129>((unsigned __int8 *)&Uuid, 0x10u, v7);
      *(_WORD *)(v7 + 22) = 46;
      goto LABEL_16;
    }
  }
  v7 = 0;
LABEL_16:
  if ( v7 )
  {
    if ( v5 && a1[v5 - 1] == 33 )
    {
      _o_strncpy_s(v7, 129, a1, v5 - 1);
      v9 = (_BYTE *)(v7 + 129);
      *(_BYTE *)(v7 + 129) = v5 - 1;
      *(_QWORD *)(v7 + 136) = (v5 + 1) << 32;
    }
    else
    {
      v9 = (_BYTE *)(v7 + 129);
      if ( v5 == v4 - 2 )
      {
        _o_strncpy_s(v7, 129, a1, v5);
        *v9 = v5;
      }
      else
      {
        v10 = v5 + 1;
        if ( v5 != v4 - 3 )
        {
          _o_strncpy_s(v7, 129, a1, v5);
          *(_BYTE *)(v5 + v7) = 46;
          *v9 = v10;
          *(_QWORD *)(v7 + 136) = (v5 + 3) << 32;
          *(_QWORD *)(v7 + 136) &= ~0x8000000000000000uLL;
          goto LABEL_27;
        }
        _o_strncpy_s(v7, 129, a1, v5);
        *(_BYTE *)(v5 + v7) = 46;
        *v9 = v10;
      }
      *(_QWORD *)(v7 + 136) = v4 << 32;
    }
    *(_QWORD *)(v7 + 136) |= 0x8000000000000000uLL;
LABEL_27:
    result = (struct TraceLoggingCorrelationVector *)v7;
    *(_BYTE *)((unsigned __int8)*v9 + v7) = 0;
    return result;
  }
  return 0;
}

```

## disassembly

```asm
0x18005d270  mov     [rsp+arg_8], rbx
0x18005d275  mov     [rsp+arg_10], rbp
0x18005d27a  push    rsi
0x18005d27b  push    rdi
0x18005d27c  push    r13
0x18005d27e  push    r14
0x18005d280  push    r15
0x18005d282  sub     rsp, 40h
0x18005d286  mov     rax, cs:__security_cookie
0x18005d28d  xor     rax, rsp
0x18005d290  mov     [rsp+68h+var_38], rax
0x18005d295  mov     dl, 1
0x18005d297  mov     r14, rcx
0x18005d29a  call    ?ValidateImpl@TraceLoggingCorrelationVector@@CA?AW4CvVersion@1@PEBD_N@Z; TraceLoggingCorrelationVector::ValidateImpl(char const *,bool)
0x18005d29f  test    al, al
0x18005d2a1  jz      loc_18005D4E6
0x18005d2a7  mov     ebp, 41h ; 'A'
0x18005d2ac  cmp     al, 1
0x18005d2ae  lea     r13d, [rbp+40h]
0x18005d2b2  cmovnz  ebp, r13d
0x18005d2b6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18005d2ba  inc     rdi
0x18005d2bd  cmp     byte ptr [r14+rdi], 0
0x18005d2c2  jnz     short loc_18005D2BA
0x18005d2c4  lea     rcx, [rbp-1]
0x18005d2c8  cmp     rdi, rcx
0x18005d2cb  jb      short loc_18005D2DF
0x18005d2cd  jnz     loc_18005D4E6
0x18005d2d3  cmp     byte ptr [rdi+r14-1], 21h ; '!'
0x18005d2d9  jnz     loc_18005D4E6
0x18005d2df  movzx   ecx, al
0x18005d2e2  sub     ecx, 1
0x18005d2e5  jz      loc_18005D375
0x18005d2eb  cmp     ecx, 1
0x18005d2ee  jnz     loc_18005D4E6
0x18005d2f4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005d2fb  mov     ecx, 90h; unsigned __int64
0x18005d300  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005d305  mov     rbx, rax
0x18005d308  test    rax, rax
0x18005d30b  jz      loc_18005D3F2
0x18005d311  xorps   xmm0, xmm0
0x18005d314  mov     [rax+82h], r13b
0x18005d31b  lea     rcx, [rsp+68h+Uuid]; Uuid
0x18005d320  movups  xmmword ptr [rsp+68h+Uuid.Data1], xmm0
0x18005d325  call    cs:__imp_UuidCreate
0x18005d32b  movaps  xmm0, xmmword ptr [rsp+68h+Uuid.Data1]
0x18005d330  mov     rax, 1900000000h
0x18005d33a  movdqa  xmmword ptr [rsp+68h+Uuid.Data1], xmm0
0x18005d340  mov     r8, r13; Size
0x18005d343  mov     byte ptr [rbx+81h], 17h
0x18005d34a  xor     edx, edx; Val
0x18005d34c  mov     rcx, rbx; void *
0x18005d34f  mov     [rbx+88h], rax
0x18005d356  call    memset_0
0x18005d35b  mov     r8, rbx
0x18005d35e  lea     rcx, [rsp+68h+Uuid]
0x18005d363  mov     edx, 10h
0x18005d368  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x18005d36d  mov     word ptr [rbx+16h], 2Eh ; '.'
0x18005d373  jmp     short loc_18005D3F4
0x18005d375  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005d37c  mov     ecx, 90h; unsigned __int64
0x18005d381  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005d386  mov     rbx, rax
0x18005d389  test    rax, rax
0x18005d38c  jz      short loc_18005D3F2
0x18005d38e  xorps   xmm0, xmm0
0x18005d391  mov     byte ptr [rax+82h], 41h ; 'A'
0x18005d398  lea     rcx, [rsp+68h+Uuid]; Uuid
0x18005d39d  movups  xmmword ptr [rsp+68h+Uuid.Data1], xmm0
0x18005d3a2  call    cs:__imp_UuidCreate
0x18005d3a8  movaps  xmm0, xmmword ptr [rsp+68h+Uuid.Data1]
0x18005d3ad  mov     rax, 1300000000h
0x18005d3b7  movdqa  xmmword ptr [rsp+68h+Uuid.Data1], xmm0
0x18005d3bd  mov     r8, r13; Size
0x18005d3c0  mov     byte ptr [rbx+81h], 11h
0x18005d3c7  xor     edx, edx; Val
0x18005d3c9  mov     rcx, rbx; void *
0x18005d3cc  mov     [rbx+88h], rax
0x18005d3d3  call    memset_0
0x18005d3d8  mov     r8, rbx
0x18005d3db  lea     rcx, [rsp+68h+Uuid]
0x18005d3e0  mov     edx, 0Ch
0x18005d3e5  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x18005d3ea  mov     word ptr [rbx+10h], 2Eh ; '.'
0x18005d3f0  jmp     short loc_18005D3F4
0x18005d3f2  xor     ebx, ebx
0x18005d3f4  test    rbx, rbx
0x18005d3f7  jz      loc_18005D4E6
0x18005d3fd  test    rdi, rdi
0x18005d400  jz      short loc_18005D43A
0x18005d402  cmp     byte ptr [rdi+r14-1], 21h ; '!'
0x18005d408  jnz     short loc_18005D43A
0x18005d40a  lea     r9, [rdi-1]
0x18005d40e  mov     r8, r14
0x18005d411  mov     rdx, r13
0x18005d414  mov     rcx, rbx
0x18005d417  call    cs:__imp__o_strncpy_s
0x18005d41d  lea     eax, [rdi-1]
0x18005d420  lea     rsi, [rbx+81h]
0x18005d427  mov     [rsi], al
0x18005d429  lea     rax, [rdi+1]
0x18005d42d  shl     rax, 20h
0x18005d431  mov     [rbx+88h], rax
0x18005d438  jmp     short loc_18005D486
0x18005d43a  lea     rax, [rbp-2]
0x18005d43e  mov     r9, rdi
0x18005d441  lea     rsi, [rbx+81h]
0x18005d448  mov     r8, r14
0x18005d44b  mov     rdx, r13
0x18005d44e  mov     rcx, rbx
0x18005d451  cmp     rdi, rax
0x18005d454  jnz     short loc_18005D461
0x18005d456  call    cs:__imp__o_strncpy_s
0x18005d45c  mov     [rsi], dil
0x18005d45f  jmp     short loc_18005D47B
0x18005d461  lea     rax, [rbp-3]
0x18005d465  lea     r15d, [rdi+1]
0x18005d469  cmp     rdi, rax
0x18005d46c  jnz     short loc_18005D4A3
0x18005d46e  call    cs:__imp__o_strncpy_s
0x18005d474  mov     byte ptr [rdi+rbx], 2Eh ; '.'
0x18005d478  mov     [rsi], r15b
0x18005d47b  shl     rbp, 20h
0x18005d47f  mov     [rbx+88h], rbp
0x18005d486  mov     rax, [rbx+88h]
0x18005d48d  mov     rcx, 8000000000000000h
0x18005d497  or      rax, rcx
0x18005d49a  mov     [rbx+88h], rax
0x18005d4a1  jmp     short loc_18005D4DA
0x18005d4a3  call    cs:__imp__o_strncpy_s
0x18005d4a9  mov     byte ptr [rdi+rbx], 2Eh ; '.'
0x18005d4ad  lea     rcx, [rdi+3]
0x18005d4b1  shl     rcx, 20h
0x18005d4b5  mov     rax, 7FFFFFFFFFFFFFFFh
0x18005d4bf  mov     [rsi], r15b
0x18005d4c2  mov     [rbx+88h], rcx
0x18005d4c9  mov     rcx, [rbx+88h]
0x18005d4d0  and     rcx, rax
0x18005d4d3  mov     [rbx+88h], rcx
0x18005d4da  movzx   ecx, byte ptr [rsi]
0x18005d4dd  mov     rax, rbx
0x18005d4e0  mov     byte ptr [rcx+rbx], 0
0x18005d4e4  jmp     short loc_18005D4E8
0x18005d4e6  xor     eax, eax
0x18005d4e8  mov     rcx, [rsp+68h+var_38]
0x18005d4ed  xor     rcx, rsp; StackCookie
0x18005d4f0  call    __security_check_cookie
0x18005d4f5  lea     r11, [rsp+68h+var_28]
0x18005d4fa  mov     rbx, [r11+38h]
0x18005d4fe  mov     rbp, [r11+40h]
0x18005d502  mov     rsp, r11
0x18005d505  pop     r15
0x18005d507  pop     r14
0x18005d509  pop     r13
0x18005d50b  pop     rdi
0x18005d50c  pop     rsi
0x18005d50d  retn
```
