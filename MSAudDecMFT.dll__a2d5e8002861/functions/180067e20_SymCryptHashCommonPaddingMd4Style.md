# SymCryptHashCommonPaddingMd4Style

- ea: `0x180067e20`
- end: `0x180067ecb`
- name: `SymCryptHashCommonPaddingMd4Style`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180067d80`

## callees

- `0x18004d320`
- `0x18004e0a0`
- `0x1800676a0`
- `0x180067e20`

## pseudocode

```c
__int64 __fastcall SymCryptHashCommonPaddingMd4Style(__int64 a1, unsigned int *a2)
{
  __int64 v2; // rax
  unsigned __int64 v4; // rax
  __int64 v6; // [rsp+20h] [rbp-38h] BYREF

  v2 = *a2;
  v6 = 0;
  *((_BYTE *)a2 + v2 + 32) = 0x80;
  v4 = v2 + 1;
  if ( v4 > 0x38 )
  {
    SymCryptWipeAsm((char *)a2 + v4 + 32, 64 - v4);
    ((void (__fastcall *)(unsigned int *, unsigned int *, __int64, __int64 *))SymCryptMd4AppendBlocks)(
      a2 + 24,
      a2 + 8,
      64,
      &v6);
    v4 = 0;
  }
  SymCryptWipeAsm((char *)a2 + v4 + 32, 64 - v4);
  *((_QWORD *)a2 + 11) = 8LL * *((_QWORD *)a2 + 2);
  return ((__int64 (__fastcall *)(unsigned int *, unsigned int *, __int64, __int64 *))SymCryptMd4AppendBlocks)(
           a2 + 24,
           a2 + 8,
           64,
           &v6);
}

```

## disassembly

```asm
0x180067e20  push    rbx
0x180067e22  push    rbp
0x180067e23  push    rsi
0x180067e24  push    rdi
0x180067e25  sub     rsp, 38h
0x180067e29  mov     rax, cs:__security_cookie
0x180067e30  xor     rax, rsp
0x180067e33  mov     [rsp+58h+var_30], rax
0x180067e38  mov     eax, [rdx]
0x180067e3a  mov     rbx, rdx
0x180067e3d  mov     [rsp+58h+var_38], 0
0x180067e46  mov     ebp, 40h ; '@'
0x180067e4b  mov     byte ptr [rax+rdx+20h], 80h
0x180067e50  inc     rax
0x180067e53  cmp     rax, 38h ; '8'
0x180067e57  jbe     short loc_180067E81
0x180067e59  mov     edx, ebp
0x180067e5b  lea     rcx, [rbx+20h]
0x180067e5f  sub     rdx, rax
0x180067e62  add     rcx, rax
0x180067e65  call    SymCryptWipeAsm
0x180067e6a  lea     r9, [rsp+58h+var_38]
0x180067e6f  mov     r8d, ebp
0x180067e72  lea     rdx, [rbx+20h]
0x180067e76  lea     rcx, [rbx+60h]
0x180067e7a  call    SymCryptMd4AppendBlocks
0x180067e7f  xor     eax, eax
0x180067e81  mov     rdx, rbp
0x180067e84  lea     rcx, [rbx+20h]
0x180067e88  sub     rdx, rax
0x180067e8b  add     rcx, rax
0x180067e8e  call    SymCryptWipeAsm
0x180067e93  mov     rax, [rbx+10h]
0x180067e97  lea     r9, [rsp+58h+var_38]
0x180067e9c  shl     rax, 3
0x180067ea0  lea     rdx, [rbx+20h]
0x180067ea4  mov     r8, rbp
0x180067ea7  mov     [rbx+58h], rax
0x180067eab  lea     rcx, [rbx+60h]
0x180067eaf  call    SymCryptMd4AppendBlocks
0x180067eb4  mov     rcx, [rsp+58h+var_30]
0x180067eb9  xor     rcx, rsp; StackCookie
0x180067ebc  call    __security_check_cookie
0x180067ec1  add     rsp, 38h
0x180067ec5  pop     rdi
0x180067ec6  pop     rsi
0x180067ec7  pop     rbp
0x180067ec8  pop     rbx
0x180067ec9  retn
```
