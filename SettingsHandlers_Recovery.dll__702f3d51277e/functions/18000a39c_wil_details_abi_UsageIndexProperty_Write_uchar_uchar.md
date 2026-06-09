# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000a39c`
- end: `0x18000a484`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007f48`

## callees

- `0x180002e3a`
- `0x18000a39c`
- `0x18000aa28`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a3ff`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a3ff`

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
0x18000a39c  push    rbx
0x18000a39e  push    rbp
0x18000a39f  push    rsi
0x18000a3a0  push    rdi
0x18000a3a1  push    r14
0x18000a3a3  push    r15
0x18000a3a5  sub     rsp, 28h
0x18000a3a9  mov     al, [rcx+2]
0x18000a3ac  xor     ebp, ebp
0x18000a3ae  mov     r9, [rdx]
0x18000a3b1  mov     rdi, r8
0x18000a3b4  mov     r15, rdx
0x18000a3b7  mov     rsi, rcx
0x18000a3ba  cmp     al, 1
0x18000a3bc  jnz     short loc_18000A3DA
0x18000a3be  lea     rbx, [r9+2]
0x18000a3c2  cmp     rbx, r8
0x18000a3c5  ja      loc_18000A455
0x18000a3cb  test    r9, r9
0x18000a3ce  jz      short loc_18000A3FF
0x18000a3d0  movzx   eax, word ptr [rcx+4]
0x18000a3d4  mov     [r9], ax
0x18000a3d8  jmp     short loc_18000A415
0x18000a3da  cmp     al, 2
0x18000a3dc  jnz     short loc_18000A412
0x18000a3de  lea     rbx, [r9+4]
0x18000a3e2  cmp     rbx, rdi
0x18000a3e5  ja      short loc_18000A455
0x18000a3e7  test    r9, r9
0x18000a3ea  jz      short loc_18000A3FF
0x18000a3ec  lea     rax, [rcx+4]
0x18000a3f0  test    rax, rax
0x18000a3f3  jz      short loc_18000A3FC
0x18000a3f5  mov     eax, [rax]
0x18000a3f7  mov     [r9], eax
0x18000a3fa  jmp     short loc_18000A415
0x18000a3fc  mov     [r9], eax
0x18000a3ff  call    cs:__imp__o__errno
0x18000a405  mov     dword ptr [rax], 16h
0x18000a40b  call    _invalid_parameter_noinfo
0x18000a410  jmp     short loc_18000A415
0x18000a412  mov     rbx, r9
0x18000a415  cmp     [rsi], bp
0x18000a418  jnz     short loc_18000A443
0x18000a41a  lea     r14, [rbx+2]
0x18000a41e  cmp     r14, rdi
0x18000a421  ja      short loc_18000A455
0x18000a423  lea     rbp, [rsi+8]
0x18000a427  mov     rdx, rdi
0x18000a42a  sub     rdx, rbx; DestinationSize
0x18000a42d  mov     r8, rbp; Source
0x18000a430  mov     r9d, 2; SourceSize
0x18000a436  mov     rcx, rbx; Destination
0x18000a439  call    memcpy_s
0x18000a43e  mov     rbx, r14
0x18000a441  jmp     short loc_18000A447
0x18000a443  lea     rbp, [rsi+8]
0x18000a447  movzx   r9d, word ptr [rbp+0]; SourceSize
0x18000a44c  lea     rax, [r9+rbx]
0x18000a450  cmp     rax, rdi
0x18000a453  jbe     short loc_18000A459
0x18000a455  xor     al, al
0x18000a457  jmp     short loc_18000A477
0x18000a459  mov     r8, [rsi+18h]; Source
0x18000a45d  sub     rdi, rbx
0x18000a460  mov     rdx, rdi; DestinationSize
0x18000a463  mov     rcx, rbx; Destination
0x18000a466  call    memcpy_s
0x18000a46b  movzx   ecx, word ptr [rbp+0]
0x18000a46f  mov     al, 1
0x18000a471  add     rcx, rbx
0x18000a474  mov     [r15], rcx
0x18000a477  add     rsp, 28h
0x18000a47b  pop     r15
0x18000a47d  pop     r14
0x18000a47f  pop     rdi
0x18000a480  pop     rsi
0x18000a481  pop     rbp
0x18000a482  pop     rbx
0x18000a483  retn
```
