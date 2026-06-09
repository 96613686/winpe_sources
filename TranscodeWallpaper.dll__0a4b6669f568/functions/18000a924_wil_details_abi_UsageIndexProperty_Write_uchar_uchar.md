# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000a924`
- end: `0x18000aa0c`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800093bc`

## callees

- `0x180002c4a`
- `0x180006fa4`
- `0x18000a924`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a987`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a987`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char v3; // al
  unsigned __int8 *v4; // r9
  unsigned __int8 *v8; // rbx
  _DWORD *v9; // rax
  unsigned __int16 *v10; // rbp
  rsize_t v11; // r9
  bool result; // al

  v3 = *((_BYTE *)this + 2);
  v4 = *a2;
  if ( v3 == 1 )
  {
    v8 = v4 + 2;
    if ( v4 + 2 > a3 )
      return 0;
    if ( v4 )
    {
      *(_WORD *)v4 = *((_WORD *)this + 2);
      goto LABEL_13;
    }
LABEL_11:
    *(_DWORD *)_o__errno(this, a2, a3) = 22;
    invalid_parameter_noinfo();
    goto LABEL_13;
  }
  if ( v3 == 2 )
  {
    v8 = v4 + 4;
    if ( v4 + 4 > a3 )
      return 0;
    if ( v4 )
    {
      v9 = (_DWORD *)((char *)this + 4);
      if ( this != (wil::details_abi::UsageIndexProperty *)-4LL )
      {
        *(_DWORD *)v4 = *v9;
        goto LABEL_13;
      }
      *(_DWORD *)v4 = (_DWORD)v9;
    }
    goto LABEL_11;
  }
  v8 = *a2;
LABEL_13:
  if ( !*(_WORD *)this )
  {
    if ( v8 + 2 <= a3 )
    {
      v10 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v8, a3 - v8, (char *)this + 8, 2u);
      v8 += 2;
      goto LABEL_17;
    }
    return 0;
  }
  v10 = (unsigned __int16 *)((char *)this + 8);
LABEL_17:
  v11 = *v10;
  if ( &v8[v11] > a3 )
    return 0;
  memcpy_s(v8, a3 - v8, *((const void *const *)this + 3), v11);
  result = 1;
  *a2 = &v8[*v10];
  return result;
}

```

## disassembly

```asm
0x18000a924  push    rbx
0x18000a926  push    rbp
0x18000a927  push    rsi
0x18000a928  push    rdi
0x18000a929  push    r14
0x18000a92b  push    r15
0x18000a92d  sub     rsp, 28h
0x18000a931  mov     al, [rcx+2]
0x18000a934  xor     ebp, ebp
0x18000a936  mov     r9, [rdx]
0x18000a939  mov     rdi, r8
0x18000a93c  mov     r15, rdx
0x18000a93f  mov     rsi, rcx
0x18000a942  cmp     al, 1
0x18000a944  jnz     short loc_18000A962
0x18000a946  lea     rbx, [r9+2]
0x18000a94a  cmp     rbx, r8
0x18000a94d  ja      loc_18000A9DD
0x18000a953  test    r9, r9
0x18000a956  jz      short loc_18000A987
0x18000a958  movzx   eax, word ptr [rcx+4]
0x18000a95c  mov     [r9], ax
0x18000a960  jmp     short loc_18000A99D
0x18000a962  cmp     al, 2
0x18000a964  jnz     short loc_18000A99A
0x18000a966  lea     rbx, [r9+4]
0x18000a96a  cmp     rbx, rdi
0x18000a96d  ja      short loc_18000A9DD
0x18000a96f  test    r9, r9
0x18000a972  jz      short loc_18000A987
0x18000a974  lea     rax, [rcx+4]
0x18000a978  test    rax, rax
0x18000a97b  jz      short loc_18000A984
0x18000a97d  mov     eax, [rax]
0x18000a97f  mov     [r9], eax
0x18000a982  jmp     short loc_18000A99D
0x18000a984  mov     [r9], eax
0x18000a987  call    cs:__imp__o__errno
0x18000a98d  mov     dword ptr [rax], 16h
0x18000a993  call    _invalid_parameter_noinfo
0x18000a998  jmp     short loc_18000A99D
0x18000a99a  mov     rbx, r9
0x18000a99d  cmp     [rsi], bp
0x18000a9a0  jnz     short loc_18000A9CB
0x18000a9a2  lea     r14, [rbx+2]
0x18000a9a6  cmp     r14, rdi
0x18000a9a9  ja      short loc_18000A9DD
0x18000a9ab  lea     rbp, [rsi+8]
0x18000a9af  mov     rdx, rdi
0x18000a9b2  sub     rdx, rbx; DestinationSize
0x18000a9b5  mov     r8, rbp; Source
0x18000a9b8  mov     r9d, 2; SourceSize
0x18000a9be  mov     rcx, rbx; Destination
0x18000a9c1  call    memcpy_s
0x18000a9c6  mov     rbx, r14
0x18000a9c9  jmp     short loc_18000A9CF
0x18000a9cb  lea     rbp, [rsi+8]
0x18000a9cf  movzx   r9d, word ptr [rbp+0]; SourceSize
0x18000a9d4  lea     rax, [r9+rbx]
0x18000a9d8  cmp     rax, rdi
0x18000a9db  jbe     short loc_18000A9E1
0x18000a9dd  xor     al, al
0x18000a9df  jmp     short loc_18000A9FF
0x18000a9e1  mov     r8, [rsi+18h]; Source
0x18000a9e5  sub     rdi, rbx
0x18000a9e8  mov     rdx, rdi; DestinationSize
0x18000a9eb  mov     rcx, rbx; Destination
0x18000a9ee  call    memcpy_s
0x18000a9f3  movzx   ecx, word ptr [rbp+0]
0x18000a9f7  mov     al, 1
0x18000a9f9  add     rcx, rbx
0x18000a9fc  mov     [r15], rcx
0x18000a9ff  add     rsp, 28h
0x18000aa03  pop     r15
0x18000aa05  pop     r14
0x18000aa07  pop     rdi
0x18000aa08  pop     rsi
0x18000aa09  pop     rbp
0x18000aa0a  pop     rbx
0x18000aa0b  retn
```
