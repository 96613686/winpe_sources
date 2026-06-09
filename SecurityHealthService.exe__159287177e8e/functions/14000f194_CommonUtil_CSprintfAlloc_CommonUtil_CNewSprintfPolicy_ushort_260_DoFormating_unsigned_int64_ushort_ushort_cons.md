# CommonUtil::CSprintfAlloc<CommonUtil::CNewSprintfPolicy<ushort>,260>::DoFormating(unsigned __int64 *,ushort * *,ushort const *,char *,unsigned __int64)

- ea: `0x14000f194`
- end: `0x14000f3a3`
- name: `?DoFormating@?$CSprintfAlloc@U?$CNewSprintfPolicy@G@CommonUtil@@$0BAE@@CommonUtil@@SAJPEA_KPEAPEAGPEBGPEAD_K@Z`
- size: `527`
- prototype: `__int64 __fastcall(unsigned __int64 *, void **, const unsigned __int16 *, char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14000f3dc`

## callees

- `0x1400015d0`
- `0x1400015f4`
- `0x140002450`
- `0x14000259c`
- `0x140006cc0`
- `0x14000f194`
- `0x1400121e0`

## pseudocode

```c
__int64 __fastcall CommonUtil::CSprintfAlloc<CommonUtil::CNewSprintfPolicy<unsigned short>,260>::DoFormating(
        unsigned __int64 *a1,
        void **a2,
        const unsigned __int16 *a3,
        char *a4)
{
  unsigned __int64 v5; // rdi
  unsigned __int64 v9; // rbx
  int v10; // eax
  int v11; // eax
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rbx
  __int64 v14; // rsi
  __int64 v15; // rax
  unsigned __int64 v16; // rbx
  unsigned __int64 v17; // rax
  void *v18; // rax
  __int64 result; // rax
  int v20; // eax
  unsigned __int64 v21; // rax
  void *v22; // rax
  int v23; // eax
  wchar_t Src[264]; // [rsp+20h] [rbp-258h] BYREF

  v5 = 0;
  if ( !*a2 )
  {
    v9 = 260;
    v10 = StringCchVPrintfW(Src, 0x104u, a3, a4);
    if ( v10 >= 0 )
    {
      v14 = -1;
      v15 = -1;
      do
        ++v15;
      while ( Src[v15] );
      v16 = v15 + 1;
      operator delete(*a2);
      v17 = 2 * v16;
      if ( !is_mul_ok(v16, 2u) )
        v17 = -1;
      v18 = operator new[](v17, (const struct std::nothrow_t *)&std::nothrow);
      *a2 = v18;
      if ( !v18 )
        return 2147942414LL;
      memcpy_0(v18, Src, 2 * v16);
      do
        ++v14;
      while ( Src[v14] );
      *a1 = v14 + 1;
      return 0;
    }
    if ( v10 == -2147024774 )
    {
      v11 = vscwprintf(a3, a4);
      if ( v11 >= 0 )
      {
        v12 = v11 + 1LL;
        if ( v12 > 0x104 )
          v5 = v12;
      }
    }
    goto LABEL_7;
  }
  v9 = *a1;
  result = StringCchVPrintfW((wchar_t *)*a2, *a1, a3, a4);
  if ( (int)result >= 0 )
    return 0;
  if ( (_DWORD)result == -2147024774 )
  {
    v20 = vscwprintf(a3, a4);
    if ( v20 < 0 )
      return 2147500037LL;
    v5 = v20 + 1LL;
    if ( v5 <= v9 )
      return 2147500037LL;
LABEL_7:
    if ( v9 >= v5 )
    {
      v13 = (3 * v9) >> 1;
      goto LABEL_25;
    }
    while ( 1 )
    {
      v13 = v5;
LABEL_25:
      if ( v13 > 0x7FFFFFFF )
        break;
      operator delete(*a2);
      v21 = 2 * v13;
      if ( !is_mul_ok(v13, 2u) )
        v21 = -1;
      v22 = operator new[](v21, (const struct std::nothrow_t *)&std::nothrow);
      *a2 = v22;
      if ( !v22 )
      {
        *a1 = 0;
        return 2147942414LL;
      }
      *a1 = v13;
      result = StringCchVPrintfW((wchar_t *)*a2, v13, a3, a4);
      if ( (int)result >= 0 )
        return 0;
      if ( (_DWORD)result != -2147024774 )
        return result;
      v23 = vscwprintf(a3, a4);
      if ( v23 >= 0 )
      {
        v5 = v23 + 1LL;
        if ( v13 < v5 )
          continue;
      }
      return 2147500037LL;
    }
    return 2147942522LL;
  }
  return result;
}

```

## disassembly

```asm
0x14000f194  push    rbx
0x14000f196  push    rsi
0x14000f197  push    rdi
0x14000f198  push    r12
0x14000f19a  push    r13
0x14000f19c  push    r14
0x14000f19e  push    r15
0x14000f1a0  sub     rsp, 240h
0x14000f1a7  mov     rax, cs:__security_cookie
0x14000f1ae  xor     rax, rsp
0x14000f1b1  mov     [rsp+278h+var_48], rax
0x14000f1b9  mov     r12, rcx
0x14000f1bc  xor     edi, edi
0x14000f1be  mov     rcx, [rdx]; Buffer
0x14000f1c1  mov     r15, r9
0x14000f1c4  mov     r14, r8
0x14000f1c7  mov     r13, rdx
0x14000f1ca  test    rcx, rcx
0x14000f1cd  jnz     loc_14000F297
0x14000f1d3  mov     ebx, 104h
0x14000f1d8  lea     rcx, [rsp+278h+Src]; Buffer
0x14000f1dd  mov     edx, ebx; unsigned __int64
0x14000f1df  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x14000f1e4  test    eax, eax
0x14000f1e6  jns     short loc_14000F21F
0x14000f1e8  cmp     eax, 8007007Ah
0x14000f1ed  jnz     short loc_14000F20A
0x14000f1ef  mov     rdx, r15; ArgList
0x14000f1f2  mov     rcx, r14; Format
0x14000f1f5  call    _vscwprintf
0x14000f1fa  test    eax, eax
0x14000f1fc  js      short loc_14000F20A
0x14000f1fe  cdqe
0x14000f200  inc     rax
0x14000f203  cmp     rax, rbx
0x14000f206  cmova   rdi, rax
0x14000f20a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000f20e  cmp     rbx, rdi
0x14000f211  jnb     loc_14000F2E1
0x14000f217  mov     rbx, rdi
0x14000f21a  jmp     loc_14000F2E8
0x14000f21f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000f223  lea     rcx, [rsp+278h+Src]
0x14000f228  mov     rax, rsi
0x14000f22b  inc     rax
0x14000f22e  cmp     [rcx+rax*2], di
0x14000f232  jnz     short loc_14000F22B
0x14000f234  mov     rcx, [r13+0]; void *
0x14000f238  lea     rbx, [rax+1]
0x14000f23c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000f241  mov     eax, 2
0x14000f246  mul     rbx
0x14000f249  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000f250  cmovb   rax, rsi
0x14000f254  mov     rcx, rax; unsigned __int64
0x14000f257  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14000f25c  mov     [r13+0], rax
0x14000f260  test    rax, rax
0x14000f263  jz      loc_14000F374
0x14000f269  lea     r8, [rbx+rbx]; Size
0x14000f26d  mov     rcx, rax; void *
0x14000f270  lea     rdx, [rsp+278h+Src]; Src
0x14000f275  call    memcpy_0
0x14000f27a  lea     rax, [rsp+278h+Src]
0x14000f27f  inc     rsi
0x14000f282  cmp     [rax+rsi*2], di
0x14000f286  jnz     short loc_14000F27F
0x14000f288  lea     rax, [rsi+1]
0x14000f28c  mov     [r12], rax
0x14000f290  xor     eax, eax
0x14000f292  jmp     loc_14000F380
0x14000f297  mov     rbx, [r12]
0x14000f29b  mov     rdx, rbx; unsigned __int64
0x14000f29e  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x14000f2a3  test    eax, eax
0x14000f2a5  js      short loc_14000F2AE
0x14000f2a7  mov     eax, edi
0x14000f2a9  jmp     loc_14000F380
0x14000f2ae  cmp     eax, 8007007Ah
0x14000f2b3  jnz     loc_14000F380
0x14000f2b9  mov     rdx, r15; ArgList
0x14000f2bc  mov     rcx, r14; Format
0x14000f2bf  call    _vscwprintf
0x14000f2c4  test    eax, eax
0x14000f2c6  js      short loc_14000F2D7
0x14000f2c8  movsxd  rdi, eax
0x14000f2cb  inc     rdi
0x14000f2ce  cmp     rdi, rbx
0x14000f2d1  ja      loc_14000F20A
0x14000f2d7  mov     eax, 80004005h
0x14000f2dc  jmp     loc_14000F380
0x14000f2e1  lea     rbx, [rbx+rbx*2]
0x14000f2e5  shr     rbx, 1
0x14000f2e8  cmp     rbx, 7FFFFFFFh
0x14000f2ef  ja      loc_14000F37B
0x14000f2f5  mov     rcx, [r13+0]; void *
0x14000f2f9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000f2fe  mov     eax, 2
0x14000f303  mul     rbx
0x14000f306  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000f30d  cmovb   rax, rsi
0x14000f311  mov     rcx, rax; unsigned __int64
0x14000f314  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14000f319  xor     edi, edi
0x14000f31b  mov     [r13+0], rax
0x14000f31f  test    rax, rax
0x14000f322  jz      short loc_14000F370
0x14000f324  mov     [r12], rbx
0x14000f328  mov     r9, r15; char *
0x14000f32b  mov     rcx, [r13+0]; Buffer
0x14000f32f  mov     r8, r14; unsigned __int16 *
0x14000f332  mov     rdx, rbx; unsigned __int64
0x14000f335  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x14000f33a  test    eax, eax
0x14000f33c  jns     loc_14000F290
0x14000f342  cmp     eax, 8007007Ah
0x14000f347  jnz     short loc_14000F380
0x14000f349  mov     rdx, r15; ArgList
0x14000f34c  mov     rcx, r14; Format
0x14000f34f  call    _vscwprintf
0x14000f354  test    eax, eax
0x14000f356  js      loc_14000F2D7
0x14000f35c  movsxd  rdi, eax
0x14000f35f  inc     rdi
0x14000f362  cmp     rbx, rdi
0x14000f365  jb      loc_14000F217
0x14000f36b  jmp     loc_14000F2D7
0x14000f370  mov     [r12], rdi
0x14000f374  mov     eax, 8007000Eh
0x14000f379  jmp     short loc_14000F380
0x14000f37b  mov     eax, 8007007Ah
0x14000f380  mov     rcx, [rsp+278h+var_48]
0x14000f388  xor     rcx, rsp; StackCookie
0x14000f38b  call    __security_check_cookie
0x14000f390  add     rsp, 240h
0x14000f397  pop     r15
0x14000f399  pop     r14
0x14000f39b  pop     r13
0x14000f39d  pop     r12
0x14000f39f  pop     rdi
0x14000f3a0  pop     rsi
0x14000f3a1  pop     rbx
0x14000f3a2  retn
```
