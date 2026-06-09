# __anonymous_namespace_::AssociationSupportsDirectInvoke_::_2_::CDirectInvokeChecker::_GetTargetProtocol

- ea: `0x180026d50`
- end: `0x180026e55`
- name: `__anonymous_namespace_::AssociationSupportsDirectInvoke_::_2_::CDirectInvokeChecker::_GetTargetProtocol`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180026c30`

## callees

- `0x180026b10`
- `0x180026d50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026da3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026e00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026da3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026e00`

## pseudocode

```c
__int64 __fastcall _anonymous_namespace_::AssociationSupportsDirectInvoke_::_2_::CDirectInvokeChecker::_GetTargetProtocol(
        __int64 a1,
        unsigned __int16 **a2)
{
  const unsigned __int16 *v4; // rbp
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // r14
  unsigned __int16 *v7; // rcx
  unsigned int v8; // ebx
  unsigned __int16 *v9; // rax
  unsigned __int16 **v11; // [rsp+20h] [rbp-48h]
  unsigned __int64 *v12; // [rsp+28h] [rbp-40h]
  unsigned int v13; // [rsp+30h] [rbp-38h]

  *a2 = 0;
  v4 = *(const unsigned __int16 **)(a1 + 8);
  if ( !v4 )
  {
    v8 = -2147023728;
LABEL_12:
    if ( (*(_DWORD *)a1 & 0x400000) != 0 )
    {
      *a2 = 0;
      if ( is_mul_ok(0xFu, 2u) )
      {
        v9 = (unsigned __int16 *)CoTaskMemAlloc(0x1Eu);
        *a2 = v9;
        v8 = v9 == 0 ? 0x8007000E : 0;
        if ( v9 )
          StringCchCopyNExW(v9, 0xFu, L"ms-shellstream", 0xEu, v11, v12, v13);
      }
      else
      {
        return (unsigned int)-2147024362;
      }
    }
    return v8;
  }
  v5 = -1;
  do
    ++v5;
  while ( v4[v5] );
  v6 = v5 + 1;
  if ( v5 + 1 >= v5 && is_mul_ok(v6, 2u) )
  {
    v7 = (unsigned __int16 *)CoTaskMemAlloc(2 * v6);
    *a2 = v7;
    v8 = v7 == 0 ? 0x8007000E : 0;
    if ( v7 )
      StringCchCopyNExW(v7, v5 + 1, v4, v5, v11, v12, v13);
  }
  else
  {
    v8 = -2147024362;
  }
  if ( (v8 & 0x80000000) != 0 )
    goto LABEL_12;
  return v8;
}

```

## disassembly

```asm
0x180026d50  mov     [rsp+arg_8], rbx
0x180026d55  mov     [rsp+arg_10], rbp
0x180026d5a  push    rsi
0x180026d5b  push    rdi
0x180026d5c  push    r12
0x180026d5e  push    r14
0x180026d60  push    r15
0x180026d62  sub     rsp, 40h
0x180026d66  xor     r12d, r12d
0x180026d69  mov     rsi, rdx
0x180026d6c  mov     [rdx], r12
0x180026d6f  mov     r15, rcx
0x180026d72  mov     rbp, [rcx+8]
0x180026d76  test    rbp, rbp
0x180026d79  jz      short loc_180026DDC
0x180026d7b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180026d7f  inc     rdi
0x180026d82  cmp     [rbp+rdi*2+0], r12w
0x180026d88  jnz     short loc_180026D7F
0x180026d8a  lea     r14, [rdi+1]
0x180026d8e  cmp     r14, rdi
0x180026d91  jb      short loc_180026DD1
0x180026d93  mov     eax, 2
0x180026d98  mul     r14
0x180026d9b  test    rdx, rdx
0x180026d9e  jnz     short loc_180026DD1
0x180026da0  mov     rcx, rax; cb
0x180026da3  call    cs:__imp_CoTaskMemAlloc
0x180026da9  mov     rcx, rax; unsigned __int16 *
0x180026dac  mov     [rsi], rax
0x180026daf  neg     rax
0x180026db2  sbb     ebx, ebx
0x180026db4  not     ebx
0x180026db6  and     ebx, 8007000Eh
0x180026dbc  test    rcx, rcx
0x180026dbf  jz      short loc_180026DD6
0x180026dc1  mov     r9, rdi; unsigned __int64
0x180026dc4  mov     r8, rbp; unsigned __int16 *
0x180026dc7  mov     rdx, r14; unsigned __int64
0x180026dca  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180026dcf  jmp     short loc_180026DD6
0x180026dd1  mov     ebx, 80070216h
0x180026dd6  test    ebx, ebx
0x180026dd8  jns     short loc_180026E3A
0x180026dda  jmp     short loc_180026DE1
0x180026ddc  mov     ebx, 80070490h
0x180026de1  test    dword ptr [r15], 400000h
0x180026de8  jz      short loc_180026E3A
0x180026dea  mov     edi, 0Fh
0x180026def  mov     [rsi], r12
0x180026df2  lea     eax, [rdi-0Dh]
0x180026df5  mul     rdi
0x180026df8  test    rdx, rdx
0x180026dfb  jnz     short loc_180026E35
0x180026dfd  mov     rcx, rax; cb
0x180026e00  call    cs:__imp_CoTaskMemAlloc
0x180026e06  mov     rcx, rax
0x180026e09  mov     [rsi], rax
0x180026e0c  neg     rcx
0x180026e0f  sbb     ebx, ebx
0x180026e11  not     ebx
0x180026e13  and     ebx, 8007000Eh
0x180026e19  test    rax, rax
0x180026e1c  jz      short loc_180026E3A
0x180026e1e  lea     r9d, [rdi-1]; unsigned __int64
0x180026e22  mov     edx, edi; unsigned __int64
0x180026e24  lea     r8, aMsShellstream; "ms-shellstream"
0x180026e2b  mov     rcx, rax; unsigned __int16 *
0x180026e2e  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180026e33  jmp     short loc_180026E3A
0x180026e35  mov     ebx, 80070216h
0x180026e3a  lea     r11, [rsp+68h+var_28]
0x180026e3f  mov     eax, ebx
0x180026e41  mov     rbx, [r11+38h]
0x180026e45  mov     rbp, [r11+40h]
0x180026e49  mov     rsp, r11
0x180026e4c  pop     r15
0x180026e4e  pop     r14
0x180026e50  pop     r12
0x180026e52  pop     rdi
0x180026e53  pop     rsi
0x180026e54  retn
```
