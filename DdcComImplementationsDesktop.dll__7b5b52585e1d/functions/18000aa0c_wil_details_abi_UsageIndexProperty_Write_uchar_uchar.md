# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000aa0c`
- end: `0x18000aaf4`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008a38`

## callees

- `0x1800020d0`
- `0x18000aa0c`
- `0x18000b080`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000aa6f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000aa6f`

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
0x18000aa0c  push    rbx
0x18000aa0e  push    rbp
0x18000aa0f  push    rsi
0x18000aa10  push    rdi
0x18000aa11  push    r14
0x18000aa13  push    r15
0x18000aa15  sub     rsp, 28h
0x18000aa19  mov     al, [rcx+2]
0x18000aa1c  xor     ebp, ebp
0x18000aa1e  mov     r9, [rdx]
0x18000aa21  mov     rdi, r8
0x18000aa24  mov     r15, rdx
0x18000aa27  mov     rsi, rcx
0x18000aa2a  cmp     al, 1
0x18000aa2c  jnz     short loc_18000AA4A
0x18000aa2e  lea     rbx, [r9+2]
0x18000aa32  cmp     rbx, r8
0x18000aa35  ja      loc_18000AAC5
0x18000aa3b  test    r9, r9
0x18000aa3e  jz      short loc_18000AA6F
0x18000aa40  movzx   eax, word ptr [rcx+4]
0x18000aa44  mov     [r9], ax
0x18000aa48  jmp     short loc_18000AA85
0x18000aa4a  cmp     al, 2
0x18000aa4c  jnz     short loc_18000AA82
0x18000aa4e  lea     rbx, [r9+4]
0x18000aa52  cmp     rbx, rdi
0x18000aa55  ja      short loc_18000AAC5
0x18000aa57  test    r9, r9
0x18000aa5a  jz      short loc_18000AA6F
0x18000aa5c  lea     rax, [rcx+4]
0x18000aa60  test    rax, rax
0x18000aa63  jz      short loc_18000AA6C
0x18000aa65  mov     eax, [rax]
0x18000aa67  mov     [r9], eax
0x18000aa6a  jmp     short loc_18000AA85
0x18000aa6c  mov     [r9], eax
0x18000aa6f  call    cs:__imp__o__errno
0x18000aa75  mov     dword ptr [rax], 16h
0x18000aa7b  call    _invalid_parameter_noinfo
0x18000aa80  jmp     short loc_18000AA85
0x18000aa82  mov     rbx, r9
0x18000aa85  cmp     [rsi], bp
0x18000aa88  jnz     short loc_18000AAB3
0x18000aa8a  lea     r14, [rbx+2]
0x18000aa8e  cmp     r14, rdi
0x18000aa91  ja      short loc_18000AAC5
0x18000aa93  lea     rbp, [rsi+8]
0x18000aa97  mov     rdx, rdi
0x18000aa9a  sub     rdx, rbx; DestinationSize
0x18000aa9d  mov     r8, rbp; Source
0x18000aaa0  mov     r9d, 2; SourceSize
0x18000aaa6  mov     rcx, rbx; Destination
0x18000aaa9  call    memcpy_s
0x18000aaae  mov     rbx, r14
0x18000aab1  jmp     short loc_18000AAB7
0x18000aab3  lea     rbp, [rsi+8]
0x18000aab7  movzx   r9d, word ptr [rbp+0]; SourceSize
0x18000aabc  lea     rax, [r9+rbx]
0x18000aac0  cmp     rax, rdi
0x18000aac3  jbe     short loc_18000AAC9
0x18000aac5  xor     al, al
0x18000aac7  jmp     short loc_18000AAE7
0x18000aac9  mov     r8, [rsi+18h]; Source
0x18000aacd  sub     rdi, rbx
0x18000aad0  mov     rdx, rdi; DestinationSize
0x18000aad3  mov     rcx, rbx; Destination
0x18000aad6  call    memcpy_s
0x18000aadb  movzx   ecx, word ptr [rbp+0]
0x18000aadf  mov     al, 1
0x18000aae1  add     rcx, rbx
0x18000aae4  mov     [r15], rcx
0x18000aae7  add     rsp, 28h
0x18000aaeb  pop     r15
0x18000aaed  pop     r14
0x18000aaef  pop     rdi
0x18000aaf0  pop     rsi
0x18000aaf1  pop     rbp
0x18000aaf2  pop     rbx
0x18000aaf3  retn
```
