# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180017e10`
- end: `0x180017ef8`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180015994`

## callees

- `0x1800028c8`
- `0x180017e10`
- `0x1800185ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017e73`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017e73`

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
0x180017e10  push    rbx
0x180017e12  push    rbp
0x180017e13  push    rsi
0x180017e14  push    rdi
0x180017e15  push    r14
0x180017e17  push    r15
0x180017e19  sub     rsp, 28h
0x180017e1d  mov     al, [rcx+2]
0x180017e20  xor     ebp, ebp
0x180017e22  mov     r9, [rdx]
0x180017e25  mov     rdi, r8
0x180017e28  mov     r15, rdx
0x180017e2b  mov     rsi, rcx
0x180017e2e  cmp     al, 1
0x180017e30  jnz     short loc_180017E4E
0x180017e32  lea     rbx, [r9+2]
0x180017e36  cmp     rbx, r8
0x180017e39  ja      loc_180017EC9
0x180017e3f  test    r9, r9
0x180017e42  jz      short loc_180017E73
0x180017e44  movzx   eax, word ptr [rcx+4]
0x180017e48  mov     [r9], ax
0x180017e4c  jmp     short loc_180017E89
0x180017e4e  cmp     al, 2
0x180017e50  jnz     short loc_180017E86
0x180017e52  lea     rbx, [r9+4]
0x180017e56  cmp     rbx, rdi
0x180017e59  ja      short loc_180017EC9
0x180017e5b  test    r9, r9
0x180017e5e  jz      short loc_180017E73
0x180017e60  lea     rax, [rcx+4]
0x180017e64  test    rax, rax
0x180017e67  jz      short loc_180017E70
0x180017e69  mov     eax, [rax]
0x180017e6b  mov     [r9], eax
0x180017e6e  jmp     short loc_180017E89
0x180017e70  mov     [r9], eax
0x180017e73  call    cs:__imp__o__errno
0x180017e79  mov     dword ptr [rax], 16h
0x180017e7f  call    _invalid_parameter_noinfo
0x180017e84  jmp     short loc_180017E89
0x180017e86  mov     rbx, r9
0x180017e89  cmp     [rsi], bp
0x180017e8c  jnz     short loc_180017EB7
0x180017e8e  lea     r14, [rbx+2]
0x180017e92  cmp     r14, rdi
0x180017e95  ja      short loc_180017EC9
0x180017e97  lea     rbp, [rsi+8]
0x180017e9b  mov     rdx, rdi
0x180017e9e  sub     rdx, rbx; DestinationSize
0x180017ea1  mov     r8, rbp; Source
0x180017ea4  mov     r9d, 2; SourceSize
0x180017eaa  mov     rcx, rbx; Destination
0x180017ead  call    memcpy_s
0x180017eb2  mov     rbx, r14
0x180017eb5  jmp     short loc_180017EBB
0x180017eb7  lea     rbp, [rsi+8]
0x180017ebb  movzx   r9d, word ptr [rbp+0]; SourceSize
0x180017ec0  lea     rax, [r9+rbx]
0x180017ec4  cmp     rax, rdi
0x180017ec7  jbe     short loc_180017ECD
0x180017ec9  xor     al, al
0x180017ecb  jmp     short loc_180017EEB
0x180017ecd  mov     r8, [rsi+18h]; Source
0x180017ed1  sub     rdi, rbx
0x180017ed4  mov     rdx, rdi; DestinationSize
0x180017ed7  mov     rcx, rbx; Destination
0x180017eda  call    memcpy_s
0x180017edf  movzx   ecx, word ptr [rbp+0]
0x180017ee3  mov     al, 1
0x180017ee5  add     rcx, rbx
0x180017ee8  mov     [r15], rcx
0x180017eeb  add     rsp, 28h
0x180017eef  pop     r15
0x180017ef1  pop     r14
0x180017ef3  pop     rdi
0x180017ef4  pop     rsi
0x180017ef5  pop     rbp
0x180017ef6  pop     rbx
0x180017ef7  retn
```
