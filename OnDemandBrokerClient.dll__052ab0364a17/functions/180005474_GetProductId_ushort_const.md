# GetProductId(ushort const *)

- ea: `0x180005474`
- end: `0x1800055a0`
- name: `?GetProductId@@YA?AU_GUID@@PEBG@Z`
- size: `300`
- prototype: `struct _GUID *__fastcall(struct _GUID *__return_ptr retstr, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800058f0`

## callees

- `0x180004d44`
- `0x180004d78`
- `0x180005474`
- `0x180006150`
- `0x180006570`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18000558f`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18000558f`

## pseudocode

```c
struct _GUID *__fastcall GetProductId(struct _GUID *__return_ptr retstr, const unsigned __int16 *a2)
{
  const unsigned __int16 *v4; // rax
  __int64 v5; // r8
  unsigned __int64 v6; // rsi
  size_t v7; // rax
  void *v8; // r14
  GUID v9; // xmm0
  struct _GUID *result; // rax
  GUID iid; // [rsp+20h] [rbp-A8h] BYREF
  OLECHAR sz; // [rsp+30h] [rbp-98h] BYREF
  unsigned __int16 v13[36]; // [rsp+32h] [rbp-96h] BYREF
  int v14; // [rsp+7Ah] [rbp-4Eh]

  iid = 0;
  if ( a2 )
  {
    v4 = a2;
    v5 = 4096;
    do
    {
      if ( !*v4 )
        break;
      ++v4;
      --v5;
    }
    while ( v5 );
    v6 = (4096 - v5) & -(__int64)(v5 != 0);
    if ( v5 )
    {
      if ( !v6 )
        goto LABEL_14;
      v7 = 2 * (v6 + 1);
      if ( !is_mul_ok(v6 + 1, 2u) )
        v7 = -1;
      v8 = operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
      if ( (int)StringCchCopyNW((unsigned __int16 *)v8, v6 + 1, a2, v6) < 0 )
      {
        if ( v8 )
          operator delete[](v8);
      }
      else
      {
LABEL_14:
        sz = 123;
        if ( (int)StringCchCopyNW(v13, 0x26u, a2 + 6, 0x24u) >= 0 )
        {
          v14 = 125;
          if ( IIDFromString(&sz, &iid) >= 0 )
          {
            v9 = iid;
            goto LABEL_13;
          }
        }
      }
    }
  }
  v9 = 0;
LABEL_13:
  result = retstr;
  *retstr = v9;
  return result;
}

```

## disassembly

```asm
0x180005474  push    rbx
0x180005476  push    rbp
0x180005477  push    rsi
0x180005478  push    rdi
0x180005479  push    r14
0x18000547b  push    r15
0x18000547d  sub     rsp, 98h
0x180005484  mov     rax, cs:__security_cookie
0x18000548b  xor     rax, rsp
0x18000548e  mov     [rsp+0C8h+var_48], rax
0x180005496  xor     r15d, r15d
0x180005499  xorps   xmm0, xmm0
0x18000549c  mov     rbp, rdx
0x18000549f  mov     rdi, rcx
0x1800054a2  movups  xmmword ptr [rsp+0C8h+iid.Data1], xmm0
0x1800054a7  test    rdx, rdx
0x1800054aa  jz      loc_180005530
0x1800054b0  mov     r9d, 1000h
0x1800054b6  mov     rax, rdx
0x1800054b9  mov     r8d, r9d
0x1800054bc  cmp     [rax], r15w
0x1800054c0  jz      short loc_1800054CC
0x1800054c2  add     rax, 2
0x1800054c6  sub     r8, 1
0x1800054ca  jnz     short loc_1800054BC
0x1800054cc  sub     r9, r8
0x1800054cf  mov     rcx, r8
0x1800054d2  neg     rcx
0x1800054d5  sbb     rsi, rsi
0x1800054d8  and     rsi, r9
0x1800054db  test    r8, r8
0x1800054de  jz      short loc_180005530
0x1800054e0  test    rsi, rsi
0x1800054e3  jz      short loc_18000555A
0x1800054e5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800054ec  lea     rbx, [rsi+1]
0x1800054f0  mov     eax, 2
0x1800054f5  mul     rbx
0x1800054f8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800054ff  cmovb   rax, rcx
0x180005503  mov     rcx, rax; unsigned __int64
0x180005506  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000550b  mov     r9, rsi; unsigned __int64
0x18000550e  mov     r8, rbp; unsigned __int16 *
0x180005511  mov     rdx, rbx; unsigned __int64
0x180005514  mov     rcx, rax; unsigned __int16 *
0x180005517  mov     r14, rax
0x18000551a  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000551f  test    eax, eax
0x180005521  jns     short loc_18000555A
0x180005523  test    r14, r14
0x180005526  jz      short loc_180005530
0x180005528  mov     rcx, r14; Block
0x18000552b  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180005530  xorps   xmm0, xmm0
0x180005533  mov     rax, rdi
0x180005536  movdqu  xmmword ptr [rdi], xmm0
0x18000553a  mov     rcx, [rsp+0C8h+var_48]
0x180005542  xor     rcx, rsp; StackCookie
0x180005545  call    __security_check_cookie
0x18000554a  add     rsp, 98h
0x180005551  pop     r15
0x180005553  pop     r14
0x180005555  pop     rdi
0x180005556  pop     rsi
0x180005557  pop     rbp
0x180005558  pop     rbx
0x180005559  retn
0x18000555a  mov     eax, 7Bh ; '{'
0x18000555f  lea     r8, [rbp+0Ch]; unsigned __int16 *
0x180005563  lea     rcx, [rsp+0C8h+var_96]; unsigned __int16 *
0x180005568  mov     [rsp+0C8h+sz], ax
0x18000556d  lea     edx, [rax-55h]; unsigned __int64
0x180005570  lea     r9d, [rax-57h]; unsigned __int64
0x180005574  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180005579  test    eax, eax
0x18000557b  js      short loc_180005530
0x18000557d  lea     rdx, [rsp+0C8h+iid]; lpiid
0x180005582  mov     [rsp+0C8h+var_4E], 7Dh ; '}'
0x18000558a  lea     rcx, [rsp+0C8h+sz]; lpsz
0x18000558f  call    cs:__imp_IIDFromString
0x180005595  test    eax, eax
0x180005597  js      short loc_180005530
0x180005599  movups  xmm0, xmmword ptr [rsp+0C8h+iid.Data1]
0x18000559e  jmp     short loc_180005533
```
