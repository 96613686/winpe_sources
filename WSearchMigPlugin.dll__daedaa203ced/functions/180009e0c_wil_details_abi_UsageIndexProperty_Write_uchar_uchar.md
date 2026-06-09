# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180009e0c`
- end: `0x180009ef4`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007c98`

## callees

- `0x18000321a`
- `0x180009e0c`
- `0x18000a4a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009e6f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009e6f`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char v3; // al
  _WORD *v4; // r9
  _WORD *v8; // rbx
  _DWORD *v9; // rax
  unsigned __int16 *v10; // rbp
  rsize_t v11; // r9
  bool result; // al

  v3 = *((_BYTE *)this + 2);
  v4 = *a2;
  if ( v3 == 1 )
  {
    v8 = v4 + 1;
    if ( v4 + 1 > (_WORD *)a3 )
      return 0;
    if ( v4 )
    {
      *v4 = *((_WORD *)this + 2);
      goto LABEL_13;
    }
LABEL_11:
    *(_DWORD *)_o__errno(this) = 22;
    invalid_parameter_noinfo();
    goto LABEL_13;
  }
  if ( v3 == 2 )
  {
    v8 = v4 + 2;
    if ( v4 + 2 > (_WORD *)a3 )
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
    if ( v8 + 1 <= (_WORD *)a3 )
    {
      v10 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v8, a3 - (unsigned __int8 *)v8, (char *)this + 8, 2u);
      ++v8;
      goto LABEL_17;
    }
    return 0;
  }
  v10 = (unsigned __int16 *)((char *)this + 8);
LABEL_17:
  v11 = *v10;
  if ( (unsigned __int8 *)((char *)v8 + v11) > a3 )
    return 0;
  memcpy_s(v8, a3 - (unsigned __int8 *)v8, *((const void *const *)this + 3), v11);
  result = 1;
  *a2 = (unsigned __int8 *)v8 + *v10;
  return result;
}

```

## disassembly

```asm
0x180009e0c  push    rbx
0x180009e0e  push    rbp
0x180009e0f  push    rsi
0x180009e10  push    rdi
0x180009e11  push    r14
0x180009e13  push    r15
0x180009e15  sub     rsp, 28h
0x180009e19  mov     al, [rcx+2]
0x180009e1c  xor     ebp, ebp
0x180009e1e  mov     r9, [rdx]
0x180009e21  mov     rdi, r8
0x180009e24  mov     r15, rdx
0x180009e27  mov     rsi, rcx
0x180009e2a  cmp     al, 1
0x180009e2c  jnz     short loc_180009E4A
0x180009e2e  lea     rbx, [r9+2]
0x180009e32  cmp     rbx, r8
0x180009e35  ja      loc_180009EC5
0x180009e3b  test    r9, r9
0x180009e3e  jz      short loc_180009E6F
0x180009e40  movzx   eax, word ptr [rcx+4]
0x180009e44  mov     [r9], ax
0x180009e48  jmp     short loc_180009E85
0x180009e4a  cmp     al, 2
0x180009e4c  jnz     short loc_180009E82
0x180009e4e  lea     rbx, [r9+4]
0x180009e52  cmp     rbx, rdi
0x180009e55  ja      short loc_180009EC5
0x180009e57  test    r9, r9
0x180009e5a  jz      short loc_180009E6F
0x180009e5c  lea     rax, [rcx+4]
0x180009e60  test    rax, rax
0x180009e63  jz      short loc_180009E6C
0x180009e65  mov     eax, [rax]
0x180009e67  mov     [r9], eax
0x180009e6a  jmp     short loc_180009E85
0x180009e6c  mov     [r9], eax
0x180009e6f  call    cs:__imp__o__errno
0x180009e75  mov     dword ptr [rax], 16h
0x180009e7b  call    _invalid_parameter_noinfo
0x180009e80  jmp     short loc_180009E85
0x180009e82  mov     rbx, r9
0x180009e85  cmp     [rsi], bp
0x180009e88  jnz     short loc_180009EB3
0x180009e8a  lea     r14, [rbx+2]
0x180009e8e  cmp     r14, rdi
0x180009e91  ja      short loc_180009EC5
0x180009e93  lea     rbp, [rsi+8]
0x180009e97  mov     rdx, rdi
0x180009e9a  sub     rdx, rbx; DestinationSize
0x180009e9d  mov     r8, rbp; Source
0x180009ea0  mov     r9d, 2; SourceSize
0x180009ea6  mov     rcx, rbx; Destination
0x180009ea9  call    memcpy_s
0x180009eae  mov     rbx, r14
0x180009eb1  jmp     short loc_180009EB7
0x180009eb3  lea     rbp, [rsi+8]
0x180009eb7  movzx   r9d, word ptr [rbp+0]; SourceSize
0x180009ebc  lea     rax, [r9+rbx]
0x180009ec0  cmp     rax, rdi
0x180009ec3  jbe     short loc_180009EC9
0x180009ec5  xor     al, al
0x180009ec7  jmp     short loc_180009EE7
0x180009ec9  mov     r8, [rsi+18h]; Source
0x180009ecd  sub     rdi, rbx
0x180009ed0  mov     rdx, rdi; DestinationSize
0x180009ed3  mov     rcx, rbx; Destination
0x180009ed6  call    memcpy_s
0x180009edb  movzx   ecx, word ptr [rbp+0]
0x180009edf  mov     al, 1
0x180009ee1  add     rcx, rbx
0x180009ee4  mov     [r15], rcx
0x180009ee7  add     rsp, 28h
0x180009eeb  pop     r15
0x180009eed  pop     r14
0x180009eef  pop     rdi
0x180009ef0  pop     rsi
0x180009ef1  pop     rbp
0x180009ef2  pop     rbx
0x180009ef3  retn
```
