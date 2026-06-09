# add_pax_acl

- ea: `0x18010a844`
- end: `0x18010a92b`
- name: `add_pax_acl`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18010ad80`

## callees

- `0x180006c00`
- `0x1800ad9e0`
- `0x18010a844`
- `0x18010a934`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18010a8a4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18010a8a4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010a921`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010a921`

## string_xrefs

- `0x18010a871`: `SCHILY.acl.access`
- `0x18010a880`: `SCHILY.acl.default`
- `0x18010a862`: `SCHILY.acl.ace`

## pseudocode

```c
__int64 __fastcall add_pax_acl(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  const char *v6; // rbx
  _BYTE *v7; // rax
  __int64 v8; // r9
  void *v9; // rdi

  if ( (*(_DWORD *)(a2 + 1080) & 0x3C00) != 0 )
  {
    v6 = "SCHILY.acl.ace";
  }
  else if ( (a4 & 0x100) != 0 )
  {
    v6 = "SCHILY.acl.access";
  }
  else
  {
    if ( (a4 & 0x200) == 0 )
      return 4294967266LL;
    v6 = "SCHILY.acl.default";
  }
  v7 = (_BYTE *)archive_acl_to_text_l(a2 + 1032, 0, a4, *(_QWORD *)(a3 + 112));
  v9 = v7;
  if ( v7 )
  {
    if ( *v7 )
      add_pax_attr(a3 + 40, v6, v7, v8);
    free(v9);
    return 0;
  }
  else
  {
    if ( *(_DWORD *)_o__errno() == 12 )
    {
      archive_set_error(a1, 12, "%s %s", "Can't allocate memory for ", v6);
      return 4294967266LL;
    }
    archive_set_error(a1, 42, "%s %s %s", "Can't translate ", v6, " to UTF-8");
    return 4294967276LL;
  }
}

```

## disassembly

```asm
0x18010a844  push    rbx
0x18010a846  push    rbp
0x18010a847  push    rsi
0x18010a848  push    rdi
0x18010a849  sub     rsp, 38h
0x18010a84d  test    dword ptr [rdx+438h], 3C00h
0x18010a857  mov     eax, r9d
0x18010a85a  mov     rbp, r8
0x18010a85d  mov     rsi, rcx
0x18010a860  jz      short loc_18010A86B
0x18010a862  lea     rbx, aSchilyAclAce; "SCHILY.acl.ace"
0x18010a869  jmp     short loc_18010A887
0x18010a86b  bt      eax, 8
0x18010a86f  jnb     short loc_18010A87A
0x18010a871  lea     rbx, aSchilyAclAcces; "SCHILY.acl.access"
0x18010a878  jmp     short loc_18010A887
0x18010a87a  bt      eax, 9
0x18010a87e  jnb     short loc_18010A8CC
0x18010a880  lea     rbx, aSchilyAclDefau; "SCHILY.acl.default"
0x18010a887  mov     r9, [r8+70h]
0x18010a88b  lea     rcx, [rdx+408h]
0x18010a892  mov     r8d, eax
0x18010a895  xor     edx, edx
0x18010a897  call    archive_acl_to_text_l
0x18010a89c  mov     rdi, rax
0x18010a89f  test    rax, rax
0x18010a8a2  jnz     short loc_18010A90A
0x18010a8a4  call    cs:__imp__o__errno
0x18010a8aa  lea     edx, [rdi+0Ch]
0x18010a8ad  mov     rcx, rsi
0x18010a8b0  cmp     [rax], edx
0x18010a8b2  jnz     short loc_18010A8DA
0x18010a8b4  lea     r9, aCanTAllocateMe_3; "Can't allocate memory for "
0x18010a8bb  mov     [rsp+58h+var_38], rbx
0x18010a8c0  lea     r8, aSS_0; "%s %s"
0x18010a8c7  call    archive_set_error
0x18010a8cc  mov     eax, 0FFFFFFE2h
0x18010a8d1  add     rsp, 38h
0x18010a8d5  pop     rdi
0x18010a8d6  pop     rsi
0x18010a8d7  pop     rbp
0x18010a8d8  pop     rbx
0x18010a8d9  retn
0x18010a8da  lea     rax, aToUtf8; " to UTF-8"
0x18010a8e1  mov     edx, 2Ah ; '*'
0x18010a8e6  mov     [rsp+58h+var_30], rax
0x18010a8eb  lea     r9, aCanTTranslate; "Can't translate "
0x18010a8f2  lea     r8, aSSS; "%s %s %s"
0x18010a8f9  mov     [rsp+58h+var_38], rbx
0x18010a8fe  call    archive_set_error
0x18010a903  mov     eax, 0FFFFFFECh
0x18010a908  jmp     short loc_18010A8D1
0x18010a90a  cmp     byte ptr [rax], 0
0x18010a90d  jz      short loc_18010A91E
0x18010a90f  lea     rcx, [rbp+28h]
0x18010a913  mov     r8, rdi
0x18010a916  mov     rdx, rbx
0x18010a919  call    add_pax_attr
0x18010a91e  mov     rcx, rdi; Block
0x18010a921  call    cs:__imp_free
0x18010a927  xor     eax, eax
0x18010a929  jmp     short loc_18010A8D1
```
