# CommonUtil::CSprintfAlloc<CommonUtil::CNewSprintfPolicy<ushort>,260>::DoFormating(unsigned __int64 *,ushort * *,ushort const *,char *,unsigned __int64)

- ea: `0x14000dc20`
- end: `0x14000de2f`
- name: `?DoFormating@?$CSprintfAlloc@U?$CNewSprintfPolicy@G@CommonUtil@@$0BAE@@CommonUtil@@SAJPEA_KPEAPEAGPEBGPEAD_K@Z`
- size: `527`
- prototype: `__int64 __fastcall(unsigned __int64 *, void **, const unsigned __int16 *, char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14000de68`

## callees

- `0x1400015f0`
- `0x140001614`
- `0x140002310`
- `0x140002340`
- `0x140006770`
- `0x14000dc20`
- `0x14000fa80`

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
      v18 = operator new[](v17, (const struct std::nothrow_t *)std::nothrow);
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
      v22 = operator new[](v21, (const struct std::nothrow_t *)std::nothrow);
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
0x14000dc20  push    rbx
0x14000dc22  push    rsi
0x14000dc23  push    rdi
0x14000dc24  push    r12
0x14000dc26  push    r13
0x14000dc28  push    r14
0x14000dc2a  push    r15
0x14000dc2c  sub     rsp, 240h
0x14000dc33  mov     rax, cs:__security_cookie
0x14000dc3a  xor     rax, rsp
0x14000dc3d  mov     [rsp+278h+var_48], rax
0x14000dc45  mov     r12, rcx
0x14000dc48  xor     edi, edi
0x14000dc4a  mov     rcx, [rdx]; Buffer
0x14000dc4d  mov     r15, r9
0x14000dc50  mov     r14, r8
0x14000dc53  mov     r13, rdx
0x14000dc56  test    rcx, rcx
0x14000dc59  jnz     loc_14000DD23
0x14000dc5f  mov     ebx, 104h
0x14000dc64  lea     rcx, [rsp+278h+Src]; Buffer
0x14000dc69  mov     edx, ebx; unsigned __int64
0x14000dc6b  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x14000dc70  test    eax, eax
0x14000dc72  jns     short loc_14000DCAB
0x14000dc74  cmp     eax, 8007007Ah
0x14000dc79  jnz     short loc_14000DC96
0x14000dc7b  mov     rdx, r15; ArgList
0x14000dc7e  mov     rcx, r14; Format
0x14000dc81  call    _vscwprintf
0x14000dc86  test    eax, eax
0x14000dc88  js      short loc_14000DC96
0x14000dc8a  cdqe
0x14000dc8c  inc     rax
0x14000dc8f  cmp     rax, rbx
0x14000dc92  cmova   rdi, rax
0x14000dc96  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000dc9a  cmp     rbx, rdi
0x14000dc9d  jnb     loc_14000DD6D
0x14000dca3  mov     rbx, rdi
0x14000dca6  jmp     loc_14000DD74
0x14000dcab  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000dcaf  lea     rcx, [rsp+278h+Src]
0x14000dcb4  mov     rax, rsi
0x14000dcb7  inc     rax
0x14000dcba  cmp     [rcx+rax*2], di
0x14000dcbe  jnz     short loc_14000DCB7
0x14000dcc0  mov     rcx, [r13+0]; void *
0x14000dcc4  lea     rbx, [rax+1]
0x14000dcc8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000dccd  mov     eax, 2
0x14000dcd2  mul     rbx
0x14000dcd5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000dcdc  cmovb   rax, rsi
0x14000dce0  mov     rcx, rax; unsigned __int64
0x14000dce3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14000dce8  mov     [r13+0], rax
0x14000dcec  test    rax, rax
0x14000dcef  jz      loc_14000DE00
0x14000dcf5  lea     r8, [rbx+rbx]; Size
0x14000dcf9  mov     rcx, rax; void *
0x14000dcfc  lea     rdx, [rsp+278h+Src]; Src
0x14000dd01  call    memcpy_0
0x14000dd06  lea     rax, [rsp+278h+Src]
0x14000dd0b  inc     rsi
0x14000dd0e  cmp     [rax+rsi*2], di
0x14000dd12  jnz     short loc_14000DD0B
0x14000dd14  lea     rax, [rsi+1]
0x14000dd18  mov     [r12], rax
0x14000dd1c  xor     eax, eax
0x14000dd1e  jmp     loc_14000DE0C
0x14000dd23  mov     rbx, [r12]
0x14000dd27  mov     rdx, rbx; unsigned __int64
0x14000dd2a  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x14000dd2f  test    eax, eax
0x14000dd31  js      short loc_14000DD3A
0x14000dd33  mov     eax, edi
0x14000dd35  jmp     loc_14000DE0C
0x14000dd3a  cmp     eax, 8007007Ah
0x14000dd3f  jnz     loc_14000DE0C
0x14000dd45  mov     rdx, r15; ArgList
0x14000dd48  mov     rcx, r14; Format
0x14000dd4b  call    _vscwprintf
0x14000dd50  test    eax, eax
0x14000dd52  js      short loc_14000DD63
0x14000dd54  movsxd  rdi, eax
0x14000dd57  inc     rdi
0x14000dd5a  cmp     rdi, rbx
0x14000dd5d  ja      loc_14000DC96
0x14000dd63  mov     eax, 80004005h
0x14000dd68  jmp     loc_14000DE0C
0x14000dd6d  lea     rbx, [rbx+rbx*2]
0x14000dd71  shr     rbx, 1
0x14000dd74  cmp     rbx, 7FFFFFFFh
0x14000dd7b  ja      loc_14000DE07
0x14000dd81  mov     rcx, [r13+0]; void *
0x14000dd85  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000dd8a  mov     eax, 2
0x14000dd8f  mul     rbx
0x14000dd92  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000dd99  cmovb   rax, rsi
0x14000dd9d  mov     rcx, rax; unsigned __int64
0x14000dda0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14000dda5  xor     edi, edi
0x14000dda7  mov     [r13+0], rax
0x14000ddab  test    rax, rax
0x14000ddae  jz      short loc_14000DDFC
0x14000ddb0  mov     [r12], rbx
0x14000ddb4  mov     r9, r15; char *
0x14000ddb7  mov     rcx, [r13+0]; Buffer
0x14000ddbb  mov     r8, r14; unsigned __int16 *
0x14000ddbe  mov     rdx, rbx; unsigned __int64
0x14000ddc1  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x14000ddc6  test    eax, eax
0x14000ddc8  jns     loc_14000DD1C
0x14000ddce  cmp     eax, 8007007Ah
0x14000ddd3  jnz     short loc_14000DE0C
0x14000ddd5  mov     rdx, r15; ArgList
0x14000ddd8  mov     rcx, r14; Format
0x14000dddb  call    _vscwprintf
0x14000dde0  test    eax, eax
0x14000dde2  js      loc_14000DD63
0x14000dde8  movsxd  rdi, eax
0x14000ddeb  inc     rdi
0x14000ddee  cmp     rbx, rdi
0x14000ddf1  jb      loc_14000DCA3
0x14000ddf7  jmp     loc_14000DD63
0x14000ddfc  mov     [r12], rdi
0x14000de00  mov     eax, 8007000Eh
0x14000de05  jmp     short loc_14000DE0C
0x14000de07  mov     eax, 8007007Ah
0x14000de0c  mov     rcx, [rsp+278h+var_48]
0x14000de14  xor     rcx, rsp; StackCookie
0x14000de17  call    __security_check_cookie
0x14000de1c  add     rsp, 240h
0x14000de23  pop     r15
0x14000de25  pop     r14
0x14000de27  pop     r13
0x14000de29  pop     r12
0x14000de2b  pop     rdi
0x14000de2c  pop     rsi
0x14000de2d  pop     rbx
0x14000de2e  retn
```
