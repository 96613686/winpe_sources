# XMPSchemaURIsMatch(ushort const *,ushort const *)

- ea: `0x18000e21c`
- end: `0x18000e2c9`
- name: `?XMPSchemaURIsMatch@@YAHPEBG0@Z`
- size: `173`
- prototype: `__int64 __fastcall(wchar_t *String1, wchar_t *String2)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d150`
- `0x18000d550`
- `0x18000e07c`

## callees

- `0x18000e21c`
- `0x180032da9`

## pseudocode

```c
_BOOL8 __fastcall XMPSchemaURIsMatch(wchar_t *String1, wchar_t *String2)
{
  wchar_t *v4; // rax
  int v5; // r9d
  int v6; // r8d
  __int64 v7; // rbx
  __int64 v8; // rdi

  v4 = String1;
  do
  {
    v5 = *(wchar_t *)((char *)v4 + (char *)String2 - (char *)String1);
    v6 = *v4 - v5;
    if ( v6 )
      break;
    ++v4;
  }
  while ( v5 );
  if ( !v6 )
    return 1;
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( String1[v8] );
  do
    ++v7;
  while ( String2[v7] );
  if ( (_DWORD)v7 == (_DWORD)v8 + 1 && !wcsncmp_0(String1, String2, (unsigned int)v8) && String2[(unsigned int)v8] == 47 )
    return 1;
  if ( (_DWORD)v8 == (_DWORD)v7 + 1 && !wcsncmp_0(String1, String2, (unsigned int)v7) )
    return String1[(unsigned int)v7] == 47;
  return 0;
}

```

## disassembly

```asm
0x18000e21c  push    rbx
0x18000e21e  push    rbp
0x18000e21f  push    rsi
0x18000e220  push    rdi
0x18000e221  push    r14
0x18000e223  sub     rsp, 20h
0x18000e227  mov     r10, rdx
0x18000e22a  mov     rbp, rdx
0x18000e22d  sub     r10, rcx
0x18000e230  mov     rsi, rcx
0x18000e233  mov     rax, rcx
0x18000e236  movzx   r8d, word ptr [rax]
0x18000e23a  movzx   r9d, word ptr [rax+r10]
0x18000e23f  sub     r8d, r9d
0x18000e242  jnz     short loc_18000E24D
0x18000e244  add     rax, 2
0x18000e248  test    r9d, r9d
0x18000e24b  jnz     short loc_18000E236
0x18000e24d  xor     r14d, r14d
0x18000e250  test    r8d, r8d
0x18000e253  jz      short loc_18000E2B9
0x18000e255  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000e259  mov     rdi, rbx
0x18000e25c  inc     rdi
0x18000e25f  cmp     [rcx+rdi*2], r14w
0x18000e264  jnz     short loc_18000E25C
0x18000e266  inc     rbx
0x18000e269  cmp     [rdx+rbx*2], r14w
0x18000e26e  jnz     short loc_18000E266
0x18000e270  lea     eax, [rdi+1]
0x18000e273  cmp     ebx, eax
0x18000e275  jnz     short loc_18000E28D
0x18000e277  mov     r8d, edi; MaxCount
0x18000e27a  call    wcsncmp_0
0x18000e27f  test    eax, eax
0x18000e281  jnz     short loc_18000E28D
0x18000e283  mov     eax, edi
0x18000e285  cmp     word ptr [rbp+rax*2+0], 2Fh ; '/'
0x18000e28b  jz      short loc_18000E2B9
0x18000e28d  lea     eax, [rbx+1]
0x18000e290  cmp     edi, eax
0x18000e292  jnz     short loc_18000E2B5
0x18000e294  mov     r8d, ebx; MaxCount
0x18000e297  mov     rdx, rbp; String2
0x18000e29a  mov     rcx, rsi; String1
0x18000e29d  call    wcsncmp_0
0x18000e2a2  test    eax, eax
0x18000e2a4  jnz     short loc_18000E2B5
0x18000e2a6  mov     ecx, ebx
0x18000e2a8  mov     eax, r14d
0x18000e2ab  cmp     word ptr [rsi+rcx*2], 2Fh ; '/'
0x18000e2b0  setz    al
0x18000e2b3  jmp     short loc_18000E2BE
0x18000e2b5  xor     eax, eax
0x18000e2b7  jmp     short loc_18000E2BE
0x18000e2b9  mov     eax, 1
0x18000e2be  add     rsp, 20h
0x18000e2c2  pop     r14
0x18000e2c4  pop     rdi
0x18000e2c5  pop     rsi
0x18000e2c6  pop     rbp
0x18000e2c7  pop     rbx
0x18000e2c8  retn
```
