# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000c9e4`
- end: `0x18000cacc`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ae90`

## callees

- `0x1800034fe`
- `0x1800073b8`
- `0x18000c9e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ca47`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ca47`

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
0x18000c9e4  push    rbx
0x18000c9e6  push    rbp
0x18000c9e7  push    rsi
0x18000c9e8  push    rdi
0x18000c9e9  push    r14
0x18000c9eb  push    r15
0x18000c9ed  sub     rsp, 28h
0x18000c9f1  mov     al, [rcx+2]
0x18000c9f4  xor     ebp, ebp
0x18000c9f6  mov     r9, [rdx]
0x18000c9f9  mov     rdi, r8
0x18000c9fc  mov     r15, rdx
0x18000c9ff  mov     rsi, rcx
0x18000ca02  cmp     al, 1
0x18000ca04  jnz     short loc_18000CA22
0x18000ca06  lea     rbx, [r9+2]
0x18000ca0a  cmp     rbx, r8
0x18000ca0d  ja      loc_18000CA9D
0x18000ca13  test    r9, r9
0x18000ca16  jz      short loc_18000CA47
0x18000ca18  movzx   eax, word ptr [rcx+4]
0x18000ca1c  mov     [r9], ax
0x18000ca20  jmp     short loc_18000CA5D
0x18000ca22  cmp     al, 2
0x18000ca24  jnz     short loc_18000CA5A
0x18000ca26  lea     rbx, [r9+4]
0x18000ca2a  cmp     rbx, rdi
0x18000ca2d  ja      short loc_18000CA9D
0x18000ca2f  test    r9, r9
0x18000ca32  jz      short loc_18000CA47
0x18000ca34  lea     rax, [rcx+4]
0x18000ca38  test    rax, rax
0x18000ca3b  jz      short loc_18000CA44
0x18000ca3d  mov     eax, [rax]
0x18000ca3f  mov     [r9], eax
0x18000ca42  jmp     short loc_18000CA5D
0x18000ca44  mov     [r9], eax
0x18000ca47  call    cs:__imp__o__errno
0x18000ca4d  mov     dword ptr [rax], 16h
0x18000ca53  call    _invalid_parameter_noinfo
0x18000ca58  jmp     short loc_18000CA5D
0x18000ca5a  mov     rbx, r9
0x18000ca5d  cmp     [rsi], bp
0x18000ca60  jnz     short loc_18000CA8B
0x18000ca62  lea     r14, [rbx+2]
0x18000ca66  cmp     r14, rdi
0x18000ca69  ja      short loc_18000CA9D
0x18000ca6b  lea     rbp, [rsi+8]
0x18000ca6f  mov     rdx, rdi
0x18000ca72  sub     rdx, rbx; DestinationSize
0x18000ca75  mov     r8, rbp; Source
0x18000ca78  mov     r9d, 2; SourceSize
0x18000ca7e  mov     rcx, rbx; Destination
0x18000ca81  call    memcpy_s
0x18000ca86  mov     rbx, r14
0x18000ca89  jmp     short loc_18000CA8F
0x18000ca8b  lea     rbp, [rsi+8]
0x18000ca8f  movzx   r9d, word ptr [rbp+0]; SourceSize
0x18000ca94  lea     rax, [r9+rbx]
0x18000ca98  cmp     rax, rdi
0x18000ca9b  jbe     short loc_18000CAA1
0x18000ca9d  xor     al, al
0x18000ca9f  jmp     short loc_18000CABF
0x18000caa1  mov     r8, [rsi+18h]; Source
0x18000caa5  sub     rdi, rbx
0x18000caa8  mov     rdx, rdi; DestinationSize
0x18000caab  mov     rcx, rbx; Destination
0x18000caae  call    memcpy_s
0x18000cab3  movzx   ecx, word ptr [rbp+0]
0x18000cab7  mov     al, 1
0x18000cab9  add     rcx, rbx
0x18000cabc  mov     [r15], rcx
0x18000cabf  add     rsp, 28h
0x18000cac3  pop     r15
0x18000cac5  pop     r14
0x18000cac7  pop     rdi
0x18000cac8  pop     rsi
0x18000cac9  pop     rbp
0x18000caca  pop     rbx
0x18000cacb  retn
```
