# ATL::CDacl::CAccessObjectAce::CAccessObjectAce(ATL::CSid const &,ulong,uchar,bool,_GUID const *,_GUID const *)

- ea: `0x18002bca0`
- end: `0x18002bd9b`
- name: `??0CAccessObjectAce@CDacl@ATL@@QEAA@AEBVCSid@2@KE_NPEBU_GUID@@2@Z`
- size: `251`
- prototype: `ATL::CDacl::CAccessObjectAce *__fastcall(ATL::CDacl::CAccessObjectAce *this, const struct ATL::CSid *, int, char, bool, const struct _GUID *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18000dff0`

## callees

- `0x18000e790`
- `0x180019e00`
- `0x18001bc04`
- `0x18001c058`
- `0x18002bca0`

## pseudocode

```c
ATL::CDacl::CAccessObjectAce *__fastcall ATL::CDacl::CAccessObjectAce::CAccessObjectAce(
        ATL::CDacl::CAccessObjectAce *this,
        const struct ATL::CSid *a2,
        int a3,
        char a4,
        bool a5,
        const struct _GUID *a6,
        const struct _GUID *a7)
{
  ATL::CDacl::CAccessObjectAce *v7; // rdi
  void **v8; // rbx
  struct _GUID **v9; // rsi
  struct _GUID *v10; // rax
  struct _GUID *v11; // rax
  void **v13; // [rsp+30h] [rbp-38h]
  struct _GUID **v16; // [rsp+38h] [rbp-30h]

  v7 = this;
  ATL::CDacl::CAccessAce::CAccessAce(this, a2, a3, a4, a5);
  *(_QWORD *)v7 = &ATL::CDacl::CAccessObjectAce::`vftable';
  v8 = (void **)((char *)v7 + 152);
  v13 = (void **)((char *)v7 + 152);
  *((_QWORD *)v7 + 19) = 0;
  v9 = (struct _GUID **)((char *)v7 + 160);
  v16 = (struct _GUID **)((char *)v7 + 160);
  *((_QWORD *)v7 + 20) = 0;
  if ( a6 )
  {
    try
    {
      v10 = (struct _GUID *)operator new(0x10u);
      *v10 = *a6;
      *v8 = v10;
    }
    catch ( ... )
    {
      v7 = this;
      v8 = v13;
      v9 = v16;
    }
    if ( !*v8 )
      ATL::AtlThrowImpl(-2147024882);
  }
  if ( a7 )
  {
    try
    {
      v11 = (struct _GUID *)operator new(0x10u);
      *v11 = *a7;
      *v9 = v11;
    }
    catch ( ... )
    {
      v7 = this;
      v8 = v13;
      v9 = v16;
    }
    if ( !*v9 )
    {
      operator delete(*v8, (const struct std::nothrow_t *)0x10);
      *v8 = 0;
      ATL::AtlThrowImpl(-2147024882);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18002bca0  mov     [rsp+arg_0], rcx
0x18002bca5  push    rbx
0x18002bca6  push    rsi
0x18002bca7  push    rdi
0x18002bca8  push    r14
0x18002bcaa  sub     rsp, 48h
0x18002bcae  mov     rdi, rcx
0x18002bcb1  mov     al, [rsp+68h+arg_20]
0x18002bcb8  mov     [rsp+68h+var_48], al; bool
0x18002bcbc  call    ??0CAccessAce@CDacl@ATL@@QEAA@AEBVCSid@2@KE_N@Z; ATL::CDacl::CAccessAce::CAccessAce(ATL::CSid const &,ulong,uchar,bool)
0x18002bcc1  nop
0x18002bcc2  lea     rax, ??_7CAccessObjectAce@CDacl@ATL@@6B@; const ATL::CDacl::CAccessObjectAce::`vftable'
0x18002bcc9  mov     [rdi], rax
0x18002bccc  lea     rbx, [rdi+98h]
0x18002bcd3  mov     [rsp+68h+var_38], rbx
0x18002bcd8  mov     qword ptr [rbx], 0
0x18002bcdf  lea     rsi, [rdi+0A0h]
0x18002bce6  mov     [rsp+68h+var_30], rsi
0x18002bceb  mov     qword ptr [rsi], 0
0x18002bcf2  mov     r14, [rsp+68h+arg_28]
0x18002bcfa  test    r14, r14
0x18002bcfd  jz      short loc_18002BD36
0x18002bcff  mov     ecx, 10h; Size
0x18002bd04  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002bd09  movups  xmm0, xmmword ptr [r14]
0x18002bd0d  movdqu  xmmword ptr [rax], xmm0
0x18002bd11  mov     [rbx], rax
0x18002bd14  jmp     short loc_18002BD25
0x18002bd16  mov     rdi, [rsp+68h+arg_0]
0x18002bd1b  mov     rbx, [rsp+68h+var_38]
0x18002bd20  mov     rsi, [rsp+68h+var_30]
0x18002bd25  cmp     qword ptr [rbx], 0
0x18002bd29  jnz     short loc_18002BD36
0x18002bd2b  mov     ecx, 8007000Eh; int
0x18002bd30  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002bd36  mov     r14, [rsp+68h+arg_30]
0x18002bd3e  test    r14, r14
0x18002bd41  jz      short loc_18002BD8E
0x18002bd43  mov     ecx, 10h; Size
0x18002bd48  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002bd4d  movups  xmm0, xmmword ptr [r14]
0x18002bd51  movdqu  xmmword ptr [rax], xmm0
0x18002bd55  mov     [rsi], rax
0x18002bd58  jmp     short loc_18002BD69
0x18002bd5a  mov     rdi, [rsp+68h+arg_0]
0x18002bd5f  mov     rbx, [rsp+68h+var_38]
0x18002bd64  mov     rsi, [rsp+68h+var_30]
0x18002bd69  cmp     qword ptr [rsi], 0
0x18002bd6d  jnz     short loc_18002BD8E
0x18002bd6f  mov     edx, 10h; struct std::nothrow_t *
0x18002bd74  mov     rcx, [rbx]; void *
0x18002bd77  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002bd7c  mov     qword ptr [rbx], 0
0x18002bd83  mov     ecx, 8007000Eh; int
0x18002bd88  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002bd8e  mov     rax, rdi
0x18002bd91  add     rsp, 48h
0x18002bd95  pop     r14
0x18002bd97  pop     rdi
0x18002bd98  pop     rsi
0x18002bd99  pop     rbx
0x18002bd9a  retn
```
