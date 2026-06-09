# TraceLoggingCorrelationVector::Extend(char const *,bool)

- ea: `0x140009e60`
- end: `0x14000a113`
- name: `?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z`
- size: `691`
- prototype: `struct TraceLoggingCorrelationVector *__fastcall(const char *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000a8f0`

## callees

- `0x140002a30`
- `0x140002e1c`
- `0x14000369c`
- `0x140009a88`
- `0x140009e60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x14000a01c`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x14000a05b`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x14000a073`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x14000a0a8`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x14000a01c`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x14000a05b`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x14000a073`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x14000a0a8`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x140009e8d`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x140009e8d`
- `RPCRT4!UuidCreate` at `0x140009f2a`
- `RPCRT4!UuidCreate` at `0x140009fa7`
- `RPCRT4!UuidCreate` at `0x140009f2a`
- `RPCRT4!UuidCreate` at `0x140009fa7`

## pseudocode

```c
struct TraceLoggingCorrelationVector *__fastcall TraceLoggingCorrelationVector::Extend(const char *a1)
{
  __int64 v2; // rax
  char v3; // al
  __int64 v4; // rbp
  unsigned __int64 v5; // rdi
  char *v6; // rax
  char *v7; // rbx
  char *v8; // rax
  _BYTE *v9; // rsi
  char v10; // r15
  struct TraceLoggingCorrelationVector *result; // rax
  UUID Uuid; // [rsp+20h] [rbp-48h] BYREF

  v2 = strchr(a1, 46) - a1;
  if ( v2 == 22 )
  {
    v3 = 2;
  }
  else
  {
    if ( v2 != 16 )
      return 0;
    v3 = 1;
  }
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
    v8 = (char *)operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
    v7 = v8;
    if ( v8 )
    {
      v8[130] = 65;
      Uuid = 0;
      UuidCreate(&Uuid);
      v7[129] = 17;
      *((_QWORD *)v7 + 17) = 0x1300000000LL;
      memset_0(v7, 0, 0x81u);
      TLV::Base64Encode<129>(&Uuid, 12, v7);
      *((_WORD *)v7 + 8) = 46;
      goto LABEL_19;
    }
  }
  else
  {
    if ( v3 != 2 )
      return 0;
    v6 = (char *)operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
    v7 = v6;
    if ( v6 )
    {
      v6[130] = -127;
      Uuid = 0;
      UuidCreate(&Uuid);
      v7[129] = 23;
      *((_QWORD *)v7 + 17) = 0x1900000000LL;
      memset_0(v7, 0, 0x81u);
      TLV::Base64Encode<129>(&Uuid, 16, v7);
      *((_WORD *)v7 + 11) = 46;
      goto LABEL_19;
    }
  }
  v7 = 0;
LABEL_19:
  if ( v7 )
  {
    if ( v5 && a1[v5 - 1] == 33 )
    {
      _o_strncpy_s(v7, 129, a1, v5 - 1);
      v9 = v7 + 129;
      v7[129] = v5 - 1;
      *((_QWORD *)v7 + 17) = (v5 + 1) << 32;
    }
    else
    {
      v9 = v7 + 129;
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
          v7[v5] = 46;
          *v9 = v10;
          *((_QWORD *)v7 + 17) = (v5 + 3) << 32;
          *((_QWORD *)v7 + 17) &= ~0x8000000000000000uLL;
          goto LABEL_30;
        }
        _o_strncpy_s(v7, 129, a1, v5);
        v7[v5] = 46;
        *v9 = v10;
      }
      *((_QWORD *)v7 + 17) = v4 << 32;
    }
    *((_QWORD *)v7 + 17) |= 0x8000000000000000uLL;
LABEL_30:
    result = (struct TraceLoggingCorrelationVector *)v7;
    v7[(unsigned __int8)*v9] = 0;
    return result;
  }
  return 0;
}

```

## disassembly

```asm
0x140009e60  mov     [rsp+arg_8], rbx
0x140009e65  mov     [rsp+arg_10], rbp
0x140009e6a  push    rsi
0x140009e6b  push    rdi
0x140009e6c  push    r13
0x140009e6e  push    r14
0x140009e70  push    r15
0x140009e72  sub     rsp, 40h
0x140009e76  mov     rax, cs:__security_cookie
0x140009e7d  xor     rax, rsp
0x140009e80  mov     [rsp+68h+var_38], rax
0x140009e85  mov     edx, 2Eh ; '.'; Val
0x140009e8a  mov     r14, rcx
0x140009e8d  call    cs:__imp_strchr
0x140009e93  sub     rax, r14
0x140009e96  cmp     rax, 16h
0x140009e9a  jnz     short loc_140009EA0
0x140009e9c  mov     al, 2
0x140009e9e  jmp     short loc_140009EAC
0x140009ea0  cmp     rax, 10h
0x140009ea4  jnz     loc_14000A0EB
0x140009eaa  mov     al, 1
0x140009eac  mov     ebp, 41h ; 'A'
0x140009eb1  cmp     al, 1
0x140009eb3  lea     r13d, [rbp+40h]
0x140009eb7  cmovnz  ebp, r13d
0x140009ebb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140009ebf  inc     rdi
0x140009ec2  cmp     byte ptr [r14+rdi], 0
0x140009ec7  jnz     short loc_140009EBF
0x140009ec9  lea     rcx, [rbp-1]
0x140009ecd  cmp     rdi, rcx
0x140009ed0  jb      short loc_140009EE4
0x140009ed2  jnz     loc_14000A0EB
0x140009ed8  cmp     byte ptr [rdi+r14-1], 21h ; '!'
0x140009ede  jnz     loc_14000A0EB
0x140009ee4  movzx   ecx, al
0x140009ee7  sub     ecx, 1
0x140009eea  jz      loc_140009F7A
0x140009ef0  cmp     ecx, 1
0x140009ef3  jnz     loc_14000A0EB
0x140009ef9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140009f00  mov     ecx, 90h; unsigned __int64
0x140009f05  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140009f0a  mov     rbx, rax
0x140009f0d  test    rax, rax
0x140009f10  jz      loc_140009FF7
0x140009f16  xorps   xmm0, xmm0
0x140009f19  mov     [rax+82h], r13b
0x140009f20  lea     rcx, [rsp+68h+Uuid]; Uuid
0x140009f25  movups  xmmword ptr [rsp+68h+Uuid.Data1], xmm0
0x140009f2a  call    cs:__imp_UuidCreate
0x140009f30  movaps  xmm0, xmmword ptr [rsp+68h+Uuid.Data1]
0x140009f35  mov     rax, 1900000000h
0x140009f3f  movdqa  xmmword ptr [rsp+68h+Uuid.Data1], xmm0
0x140009f45  mov     r8, r13; Size
0x140009f48  mov     byte ptr [rbx+81h], 17h
0x140009f4f  xor     edx, edx; Val
0x140009f51  mov     rcx, rbx; void *
0x140009f54  mov     [rbx+88h], rax
0x140009f5b  call    memset_0
0x140009f60  mov     r8, rbx
0x140009f63  lea     rcx, [rsp+68h+Uuid]
0x140009f68  mov     edx, 10h
0x140009f6d  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x140009f72  mov     word ptr [rbx+16h], 2Eh ; '.'
0x140009f78  jmp     short loc_140009FF9
0x140009f7a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140009f81  mov     ecx, 90h; unsigned __int64
0x140009f86  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140009f8b  mov     rbx, rax
0x140009f8e  test    rax, rax
0x140009f91  jz      short loc_140009FF7
0x140009f93  xorps   xmm0, xmm0
0x140009f96  mov     byte ptr [rax+82h], 41h ; 'A'
0x140009f9d  lea     rcx, [rsp+68h+Uuid]; Uuid
0x140009fa2  movups  xmmword ptr [rsp+68h+Uuid.Data1], xmm0
0x140009fa7  call    cs:__imp_UuidCreate
0x140009fad  movaps  xmm0, xmmword ptr [rsp+68h+Uuid.Data1]
0x140009fb2  mov     rax, 1300000000h
0x140009fbc  movdqa  xmmword ptr [rsp+68h+Uuid.Data1], xmm0
0x140009fc2  mov     r8, r13; Size
0x140009fc5  mov     byte ptr [rbx+81h], 11h
0x140009fcc  xor     edx, edx; Val
0x140009fce  mov     rcx, rbx; void *
0x140009fd1  mov     [rbx+88h], rax
0x140009fd8  call    memset_0
0x140009fdd  mov     r8, rbx
0x140009fe0  lea     rcx, [rsp+68h+Uuid]
0x140009fe5  mov     edx, 0Ch
0x140009fea  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x140009fef  mov     word ptr [rbx+10h], 2Eh ; '.'
0x140009ff5  jmp     short loc_140009FF9
0x140009ff7  xor     ebx, ebx
0x140009ff9  test    rbx, rbx
0x140009ffc  jz      loc_14000A0EB
0x14000a002  test    rdi, rdi
0x14000a005  jz      short loc_14000A03F
0x14000a007  cmp     byte ptr [rdi+r14-1], 21h ; '!'
0x14000a00d  jnz     short loc_14000A03F
0x14000a00f  lea     r9, [rdi-1]
0x14000a013  mov     r8, r14
0x14000a016  mov     rdx, r13
0x14000a019  mov     rcx, rbx
0x14000a01c  call    cs:__imp__o_strncpy_s
0x14000a022  lea     eax, [rdi-1]
0x14000a025  lea     rsi, [rbx+81h]
0x14000a02c  mov     [rsi], al
0x14000a02e  lea     rax, [rdi+1]
0x14000a032  shl     rax, 20h
0x14000a036  mov     [rbx+88h], rax
0x14000a03d  jmp     short loc_14000A08B
0x14000a03f  lea     rax, [rbp-2]
0x14000a043  mov     r9, rdi
0x14000a046  lea     rsi, [rbx+81h]
0x14000a04d  mov     r8, r14
0x14000a050  mov     rdx, r13
0x14000a053  mov     rcx, rbx
0x14000a056  cmp     rdi, rax
0x14000a059  jnz     short loc_14000A066
0x14000a05b  call    cs:__imp__o_strncpy_s
0x14000a061  mov     [rsi], dil
0x14000a064  jmp     short loc_14000A080
0x14000a066  lea     rax, [rbp-3]
0x14000a06a  lea     r15d, [rdi+1]
0x14000a06e  cmp     rdi, rax
0x14000a071  jnz     short loc_14000A0A8
0x14000a073  call    cs:__imp__o_strncpy_s
0x14000a079  mov     byte ptr [rdi+rbx], 2Eh ; '.'
0x14000a07d  mov     [rsi], r15b
0x14000a080  shl     rbp, 20h
0x14000a084  mov     [rbx+88h], rbp
0x14000a08b  mov     rax, [rbx+88h]
0x14000a092  mov     rcx, 8000000000000000h
0x14000a09c  or      rax, rcx
0x14000a09f  mov     [rbx+88h], rax
0x14000a0a6  jmp     short loc_14000A0DF
0x14000a0a8  call    cs:__imp__o_strncpy_s
0x14000a0ae  mov     byte ptr [rdi+rbx], 2Eh ; '.'
0x14000a0b2  lea     rcx, [rdi+3]
0x14000a0b6  shl     rcx, 20h
0x14000a0ba  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000a0c4  mov     [rsi], r15b
0x14000a0c7  mov     [rbx+88h], rcx
0x14000a0ce  mov     rcx, [rbx+88h]
0x14000a0d5  and     rcx, rax
0x14000a0d8  mov     [rbx+88h], rcx
0x14000a0df  movzx   ecx, byte ptr [rsi]
0x14000a0e2  mov     rax, rbx
0x14000a0e5  mov     byte ptr [rcx+rbx], 0
0x14000a0e9  jmp     short loc_14000A0ED
0x14000a0eb  xor     eax, eax
0x14000a0ed  mov     rcx, [rsp+68h+var_38]
0x14000a0f2  xor     rcx, rsp; StackCookie
0x14000a0f5  call    __security_check_cookie
0x14000a0fa  lea     r11, [rsp+68h+var_28]
0x14000a0ff  mov     rbx, [r11+38h]
0x14000a103  mov     rbp, [r11+40h]
0x14000a107  mov     rsp, r11
0x14000a10a  pop     r15
0x14000a10c  pop     r14
0x14000a10e  pop     r13
0x14000a110  pop     rdi
0x14000a111  pop     rsi
0x14000a112  retn
```
