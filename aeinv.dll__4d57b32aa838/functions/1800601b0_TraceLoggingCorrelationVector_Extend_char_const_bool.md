# TraceLoggingCorrelationVector::Extend(char const *,bool)

- ea: `0x1800601b0`
- end: `0x18006041e`
- name: `?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z`
- size: `622`
- prototype: `struct TraceLoggingCorrelationVector *__fastcall(const char *, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18005308c`

## callees

- `0x1800499d8`
- `0x180049a50`
- `0x180059920`
- `0x180059db4`
- `0x18005a8bc`
- `0x1800601b0`
- `0x180067240`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180060327`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180060366`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18006037e`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x1800603b3`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180060327`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180060366`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x18006037e`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x1800603b3`
- `RPCRT4!UuidCreate` at `0x180060265`
- `RPCRT4!UuidCreate` at `0x1800602e2`
- `RPCRT4!UuidCreate` at `0x180060265`
- `RPCRT4!UuidCreate` at `0x1800602e2`

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
    v7 = (char *)operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
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
0x1800601b0  mov     [rsp+arg_8], rbx
0x1800601b5  mov     [rsp+arg_10], rbp
0x1800601ba  push    rsi
0x1800601bb  push    rdi
0x1800601bc  push    r13
0x1800601be  push    r14
0x1800601c0  push    r15
0x1800601c2  sub     rsp, 50h
0x1800601c6  mov     rax, cs:__security_cookie
0x1800601cd  xor     rax, rsp
0x1800601d0  mov     [rsp+78h+var_38], rax
0x1800601d5  xor     edx, edx
0x1800601d7  mov     r14, rcx
0x1800601da  call    ?ValidateImpl@TraceLoggingCorrelationVector@@CA?AW4CvVersion@1@PEBD_N@Z; TraceLoggingCorrelationVector::ValidateImpl(char const *,bool)
0x1800601df  test    al, al
0x1800601e1  jz      loc_1800603F6
0x1800601e7  mov     ebp, 41h ; 'A'
0x1800601ec  cmp     al, 1
0x1800601ee  lea     r13d, [rbp+40h]
0x1800601f2  cmovnz  ebp, r13d
0x1800601f6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800601fa  inc     rdi
0x1800601fd  cmp     byte ptr [r14+rdi], 0
0x180060202  jnz     short loc_1800601FA
0x180060204  lea     rcx, [rbp-1]
0x180060208  cmp     rdi, rcx
0x18006020b  jb      short loc_18006021F
0x18006020d  jnz     loc_1800603F6
0x180060213  cmp     byte ptr [rdi+r14-1], 21h ; '!'
0x180060219  jnz     loc_1800603F6
0x18006021f  movzx   ecx, al
0x180060222  sub     ecx, 1
0x180060225  jz      loc_1800602B5
0x18006022b  cmp     ecx, 1
0x18006022e  jnz     loc_1800603F6
0x180060234  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006023b  mov     ecx, 90h; unsigned __int64
0x180060240  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180060245  mov     rbx, rax
0x180060248  test    rax, rax
0x18006024b  jz      loc_180060302
0x180060251  xorps   xmm0, xmm0
0x180060254  mov     [rax+82h], r13b
0x18006025b  lea     rcx, [rsp+78h+Uuid]; Uuid
0x180060260  movups  xmmword ptr [rsp+78h+Uuid.Data1], xmm0
0x180060265  call    cs:__imp_UuidCreate
0x18006026b  movaps  xmm0, xmmword ptr [rsp+78h+Uuid.Data1]
0x180060270  mov     rax, 1900000000h
0x18006027a  movdqa  xmmword ptr [rsp+78h+Uuid.Data1], xmm0
0x180060280  mov     r8, r13; Size
0x180060283  mov     byte ptr [rbx+81h], 17h
0x18006028a  xor     edx, edx; Val
0x18006028c  mov     rcx, rbx; void *
0x18006028f  mov     [rbx+88h], rax
0x180060296  call    memset_0
0x18006029b  mov     r8, rbx
0x18006029e  lea     rcx, [rsp+78h+Uuid]
0x1800602a3  mov     edx, 10h
0x1800602a8  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x1800602ad  mov     word ptr [rbx+16h], 2Eh ; '.'
0x1800602b3  jmp     short loc_180060304
0x1800602b5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800602bc  mov     ecx, 90h; unsigned __int64
0x1800602c1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800602c6  mov     rbx, rax
0x1800602c9  test    rax, rax
0x1800602cc  jz      short loc_180060302
0x1800602ce  xorps   xmm0, xmm0
0x1800602d1  mov     byte ptr [rax+82h], 41h ; 'A'
0x1800602d8  lea     rcx, [rsp+78h+Uuid]; Uuid
0x1800602dd  movups  xmmword ptr [rsp+78h+Uuid.Data1], xmm0
0x1800602e2  call    cs:__imp_UuidCreate
0x1800602e8  movaps  xmm0, xmmword ptr [rsp+78h+Uuid.Data1]
0x1800602ed  lea     rdx, [rsp+78h+var_58]
0x1800602f2  mov     rcx, rbx
0x1800602f5  movdqa  [rsp+78h+var_58], xmm0
0x1800602fb  call    ??$CreateCvFromGuid@$0M@@TraceLoggingCorrelationVector@@AEAAXU_GUID@@@Z; TraceLoggingCorrelationVector::CreateCvFromGuid<12>(_GUID)
0x180060300  jmp     short loc_180060304
0x180060302  xor     ebx, ebx
0x180060304  test    rbx, rbx
0x180060307  jz      loc_1800603F6
0x18006030d  test    rdi, rdi
0x180060310  jz      short loc_18006034A
0x180060312  cmp     byte ptr [rdi+r14-1], 21h ; '!'
0x180060318  jnz     short loc_18006034A
0x18006031a  lea     r9, [rdi-1]
0x18006031e  mov     r8, r14
0x180060321  mov     rdx, r13
0x180060324  mov     rcx, rbx
0x180060327  call    cs:__imp__o_strncpy_s
0x18006032d  lea     eax, [rdi-1]
0x180060330  lea     rsi, [rbx+81h]
0x180060337  mov     [rsi], al
0x180060339  lea     rax, [rdi+1]
0x18006033d  shl     rax, 20h
0x180060341  mov     [rbx+88h], rax
0x180060348  jmp     short loc_180060396
0x18006034a  lea     rax, [rbp-2]
0x18006034e  mov     r9, rdi
0x180060351  lea     rsi, [rbx+81h]
0x180060358  mov     r8, r14
0x18006035b  mov     rdx, r13
0x18006035e  mov     rcx, rbx
0x180060361  cmp     rdi, rax
0x180060364  jnz     short loc_180060371
0x180060366  call    cs:__imp__o_strncpy_s
0x18006036c  mov     [rsi], dil
0x18006036f  jmp     short loc_18006038B
0x180060371  lea     rax, [rbp-3]
0x180060375  lea     r15d, [rdi+1]
0x180060379  cmp     rdi, rax
0x18006037c  jnz     short loc_1800603B3
0x18006037e  call    cs:__imp__o_strncpy_s
0x180060384  mov     byte ptr [rdi+rbx], 2Eh ; '.'
0x180060388  mov     [rsi], r15b
0x18006038b  shl     rbp, 20h
0x18006038f  mov     [rbx+88h], rbp
0x180060396  mov     rax, [rbx+88h]
0x18006039d  mov     rcx, 8000000000000000h
0x1800603a7  or      rax, rcx
0x1800603aa  mov     [rbx+88h], rax
0x1800603b1  jmp     short loc_1800603EA
0x1800603b3  call    cs:__imp__o_strncpy_s
0x1800603b9  mov     byte ptr [rdi+rbx], 2Eh ; '.'
0x1800603bd  lea     rcx, [rdi+3]
0x1800603c1  shl     rcx, 20h
0x1800603c5  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800603cf  mov     [rsi], r15b
0x1800603d2  mov     [rbx+88h], rcx
0x1800603d9  mov     rcx, [rbx+88h]
0x1800603e0  and     rcx, rax
0x1800603e3  mov     [rbx+88h], rcx
0x1800603ea  movzx   ecx, byte ptr [rsi]
0x1800603ed  mov     rax, rbx
0x1800603f0  mov     byte ptr [rcx+rbx], 0
0x1800603f4  jmp     short loc_1800603F8
0x1800603f6  xor     eax, eax
0x1800603f8  mov     rcx, [rsp+78h+var_38]
0x1800603fd  xor     rcx, rsp; StackCookie
0x180060400  call    __security_check_cookie
0x180060405  lea     r11, [rsp+78h+var_28]
0x18006040a  mov     rbx, [r11+38h]
0x18006040e  mov     rbp, [r11+40h]
0x180060412  mov     rsp, r11
0x180060415  pop     r15
0x180060417  pop     r14
0x180060419  pop     r13
0x18006041b  pop     rdi
0x18006041c  pop     rsi
0x18006041d  retn
```
