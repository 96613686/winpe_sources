# TraceLoggingCorrelationVector::Extend(char const *,bool)

- ea: `0x180017ab0`
- end: `0x180017cbc`
- name: `?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z`
- size: `524`
- prototype: `struct TraceLoggingCorrelationVector *__fastcall(const char *, bool)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180017cc4`
- `0x1800203f4`

## callees

- `0x18000c6e0`
- `0x18000cc64`
- `0x180013b9c`
- `0x180015a94`
- `0x180017ab0`
- `0x18001c3ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180017bc5`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180017c04`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180017c1c`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180017c51`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180017bc5`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180017c04`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180017c1c`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180017c51`
- `RPCRT4!UuidCreate` at `0x180017b80`
- `RPCRT4!UuidCreate` at `0x180017b80`

## pseudocode

```c
struct TraceLoggingCorrelationVector *__fastcall TraceLoggingCorrelationVector::Extend(const char *a1)
{
  char v2; // al
  __int64 v3; // rbp
  unsigned __int64 v4; // rdi
  void *v5; // rax
  __int64 v6; // rbx
  _BYTE *v7; // rax
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
    v7 = operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
    v6 = (__int64)v7;
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
    v5 = operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v5 )
    {
      v6 = TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v5);
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
      v8 = (_BYTE *)(v6 + 129);
      *(_BYTE *)(v6 + 129) = v4 - 1;
      *(_QWORD *)(v6 + 136) = (v4 + 1) << 32;
    }
    else
    {
      v8 = (_BYTE *)(v6 + 129);
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
          *(_BYTE *)(v4 + v6) = 46;
          *v8 = v9;
          *(_QWORD *)(v6 + 136) = (v4 + 3) << 32;
          *(_QWORD *)(v6 + 136) &= ~0x8000000000000000uLL;
          goto LABEL_27;
        }
        _o_strncpy_s(v6, 129, a1, v4);
        *(_BYTE *)(v4 + v6) = 46;
        *v8 = v9;
      }
      *(_QWORD *)(v6 + 136) = v3 << 32;
    }
    *(_QWORD *)(v6 + 136) |= 0x8000000000000000uLL;
LABEL_27:
    result = (struct TraceLoggingCorrelationVector *)v6;
    *(_BYTE *)((unsigned __int8)*v8 + v6) = 0;
    return result;
  }
  return 0;
}

```

## disassembly

```asm
0x180017ab0  mov     [rsp+arg_8], rbx
0x180017ab5  mov     [rsp+arg_10], rbp
0x180017aba  push    rsi
0x180017abb  push    rdi
0x180017abc  push    r12
0x180017abe  push    r14
0x180017ac0  push    r15
0x180017ac2  sub     rsp, 50h
0x180017ac6  mov     rax, cs:__security_cookie
0x180017acd  xor     rax, rsp
0x180017ad0  mov     [rsp+78h+var_38], rax
0x180017ad5  xor     edx, edx
0x180017ad7  mov     r14, rcx
0x180017ada  call    ?ValidateImpl@TraceLoggingCorrelationVector@@CA?AW4CvVersion@1@PEBD_N@Z; TraceLoggingCorrelationVector::ValidateImpl(char const *,bool)
0x180017adf  test    al, al
0x180017ae1  jz      loc_180017C94
0x180017ae7  mov     ebp, 41h ; 'A'
0x180017aec  cmp     al, 1
0x180017aee  lea     r12d, [rbp+40h]
0x180017af2  cmovnz  ebp, r12d
0x180017af6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180017afa  inc     rdi
0x180017afd  cmp     byte ptr [r14+rdi], 0
0x180017b02  jnz     short loc_180017AFA
0x180017b04  lea     rcx, [rbp-1]
0x180017b08  cmp     rdi, rcx
0x180017b0b  jb      short loc_180017B1F
0x180017b0d  jnz     loc_180017C94
0x180017b13  cmp     byte ptr [rdi+r14-1], 21h ; '!'
0x180017b19  jnz     loc_180017C94
0x180017b1f  movzx   ecx, al
0x180017b22  sub     ecx, 1
0x180017b25  jz      short loc_180017B53
0x180017b27  cmp     ecx, 1
0x180017b2a  jnz     loc_180017C94
0x180017b30  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017b37  mov     ecx, 90h; unsigned __int64
0x180017b3c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180017b41  test    rax, rax
0x180017b44  jz      short loc_180017BA0
0x180017b46  mov     rcx, rax
0x180017b49  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x180017b4e  mov     rbx, rax
0x180017b51  jmp     short loc_180017BA2
0x180017b53  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017b5a  mov     ecx, 90h; unsigned __int64
0x180017b5f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180017b64  mov     rbx, rax
0x180017b67  test    rax, rax
0x180017b6a  jz      short loc_180017BA0
0x180017b6c  xorps   xmm0, xmm0
0x180017b6f  mov     byte ptr [rax+82h], 41h ; 'A'
0x180017b76  lea     rcx, [rsp+78h+Uuid]; Uuid
0x180017b7b  movups  xmmword ptr [rsp+78h+Uuid.Data1], xmm0
0x180017b80  call    cs:__imp_UuidCreate
0x180017b86  movaps  xmm0, xmmword ptr [rsp+78h+Uuid.Data1]
0x180017b8b  lea     rdx, [rsp+78h+var_58]
0x180017b90  mov     rcx, rbx
0x180017b93  movdqa  [rsp+78h+var_58], xmm0
0x180017b99  call    ??$CreateCvFromGuid@$0M@@TraceLoggingCorrelationVector@@AEAAXU_GUID@@@Z; TraceLoggingCorrelationVector::CreateCvFromGuid<12>(_GUID)
0x180017b9e  jmp     short loc_180017BA2
0x180017ba0  xor     ebx, ebx
0x180017ba2  test    rbx, rbx
0x180017ba5  jz      loc_180017C94
0x180017bab  test    rdi, rdi
0x180017bae  jz      short loc_180017BE8
0x180017bb0  cmp     byte ptr [rdi+r14-1], 21h ; '!'
0x180017bb6  jnz     short loc_180017BE8
0x180017bb8  lea     r9, [rdi-1]
0x180017bbc  mov     r8, r14
0x180017bbf  mov     rdx, r12
0x180017bc2  mov     rcx, rbx
0x180017bc5  call    cs:__imp__o_strncpy_s
0x180017bcb  lea     eax, [rdi-1]
0x180017bce  lea     rsi, [rbx+81h]
0x180017bd5  mov     [rsi], al
0x180017bd7  lea     rax, [rdi+1]
0x180017bdb  shl     rax, 20h
0x180017bdf  mov     [rbx+88h], rax
0x180017be6  jmp     short loc_180017C34
0x180017be8  lea     rax, [rbp-2]
0x180017bec  mov     r9, rdi
0x180017bef  lea     rsi, [rbx+81h]
0x180017bf6  mov     r8, r14
0x180017bf9  mov     rdx, r12
0x180017bfc  mov     rcx, rbx
0x180017bff  cmp     rdi, rax
0x180017c02  jnz     short loc_180017C0F
0x180017c04  call    cs:__imp__o_strncpy_s
0x180017c0a  mov     [rsi], dil
0x180017c0d  jmp     short loc_180017C29
0x180017c0f  lea     rax, [rbp-3]
0x180017c13  lea     r15d, [rdi+1]
0x180017c17  cmp     rdi, rax
0x180017c1a  jnz     short loc_180017C51
0x180017c1c  call    cs:__imp__o_strncpy_s
0x180017c22  mov     byte ptr [rdi+rbx], 2Eh ; '.'
0x180017c26  mov     [rsi], r15b
0x180017c29  shl     rbp, 20h
0x180017c2d  mov     [rbx+88h], rbp
0x180017c34  mov     rax, [rbx+88h]
0x180017c3b  mov     rcx, 8000000000000000h
0x180017c45  or      rax, rcx
0x180017c48  mov     [rbx+88h], rax
0x180017c4f  jmp     short loc_180017C88
0x180017c51  call    cs:__imp__o_strncpy_s
0x180017c57  mov     byte ptr [rdi+rbx], 2Eh ; '.'
0x180017c5b  lea     rcx, [rdi+3]
0x180017c5f  shl     rcx, 20h
0x180017c63  mov     rax, 7FFFFFFFFFFFFFFFh
0x180017c6d  mov     [rsi], r15b
0x180017c70  mov     [rbx+88h], rcx
0x180017c77  mov     rcx, [rbx+88h]
0x180017c7e  and     rcx, rax
0x180017c81  mov     [rbx+88h], rcx
0x180017c88  movzx   ecx, byte ptr [rsi]
0x180017c8b  mov     rax, rbx
0x180017c8e  mov     byte ptr [rcx+rbx], 0
0x180017c92  jmp     short loc_180017C96
0x180017c94  xor     eax, eax
0x180017c96  mov     rcx, [rsp+78h+var_38]
0x180017c9b  xor     rcx, rsp; StackCookie
0x180017c9e  call    __security_check_cookie
0x180017ca3  lea     r11, [rsp+78h+var_28]
0x180017ca8  mov     rbx, [r11+38h]
0x180017cac  mov     rbp, [r11+40h]
0x180017cb0  mov     rsp, r11
0x180017cb3  pop     r15
0x180017cb5  pop     r14
0x180017cb7  pop     r12
0x180017cb9  pop     rdi
0x180017cba  pop     rsi
0x180017cbb  retn
```
