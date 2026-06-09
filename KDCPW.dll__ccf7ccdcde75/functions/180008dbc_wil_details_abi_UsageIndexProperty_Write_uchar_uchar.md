# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180008dbc`
- end: `0x180008ea4`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006e74`

## callees

- `0x180001f32`
- `0x180008dbc`
- `0x1800094bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008e1f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008e1f`

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
0x180008dbc  push    rbx
0x180008dbe  push    rbp
0x180008dbf  push    rsi
0x180008dc0  push    rdi
0x180008dc1  push    r14
0x180008dc3  push    r15
0x180008dc5  sub     rsp, 28h
0x180008dc9  mov     al, [rcx+2]
0x180008dcc  xor     ebp, ebp
0x180008dce  mov     r9, [rdx]
0x180008dd1  mov     rdi, r8
0x180008dd4  mov     r15, rdx
0x180008dd7  mov     rsi, rcx
0x180008dda  cmp     al, 1
0x180008ddc  jnz     short loc_180008DFA
0x180008dde  lea     rbx, [r9+2]
0x180008de2  cmp     rbx, r8
0x180008de5  ja      loc_180008E75
0x180008deb  test    r9, r9
0x180008dee  jz      short loc_180008E1F
0x180008df0  movzx   eax, word ptr [rcx+4]
0x180008df4  mov     [r9], ax
0x180008df8  jmp     short loc_180008E35
0x180008dfa  cmp     al, 2
0x180008dfc  jnz     short loc_180008E32
0x180008dfe  lea     rbx, [r9+4]
0x180008e02  cmp     rbx, rdi
0x180008e05  ja      short loc_180008E75
0x180008e07  test    r9, r9
0x180008e0a  jz      short loc_180008E1F
0x180008e0c  lea     rax, [rcx+4]
0x180008e10  test    rax, rax
0x180008e13  jz      short loc_180008E1C
0x180008e15  mov     eax, [rax]
0x180008e17  mov     [r9], eax
0x180008e1a  jmp     short loc_180008E35
0x180008e1c  mov     [r9], eax
0x180008e1f  call    cs:__imp__o__errno
0x180008e25  mov     dword ptr [rax], 16h
0x180008e2b  call    _invalid_parameter_noinfo
0x180008e30  jmp     short loc_180008E35
0x180008e32  mov     rbx, r9
0x180008e35  cmp     [rsi], bp
0x180008e38  jnz     short loc_180008E63
0x180008e3a  lea     r14, [rbx+2]
0x180008e3e  cmp     r14, rdi
0x180008e41  ja      short loc_180008E75
0x180008e43  lea     rbp, [rsi+8]
0x180008e47  mov     rdx, rdi
0x180008e4a  sub     rdx, rbx; DestinationSize
0x180008e4d  mov     r8, rbp; Source
0x180008e50  mov     r9d, 2; SourceSize
0x180008e56  mov     rcx, rbx; Destination
0x180008e59  call    memcpy_s
0x180008e5e  mov     rbx, r14
0x180008e61  jmp     short loc_180008E67
0x180008e63  lea     rbp, [rsi+8]
0x180008e67  movzx   r9d, word ptr [rbp+0]; SourceSize
0x180008e6c  lea     rax, [r9+rbx]
0x180008e70  cmp     rax, rdi
0x180008e73  jbe     short loc_180008E79
0x180008e75  xor     al, al
0x180008e77  jmp     short loc_180008E97
0x180008e79  mov     r8, [rsi+18h]; Source
0x180008e7d  sub     rdi, rbx
0x180008e80  mov     rdx, rdi; DestinationSize
0x180008e83  mov     rcx, rbx; Destination
0x180008e86  call    memcpy_s
0x180008e8b  movzx   ecx, word ptr [rbp+0]
0x180008e8f  mov     al, 1
0x180008e91  add     rcx, rbx
0x180008e94  mov     [r15], rcx
0x180008e97  add     rsp, 28h
0x180008e9b  pop     r15
0x180008e9d  pop     r14
0x180008e9f  pop     rdi
0x180008ea0  pop     rsi
0x180008ea1  pop     rbp
0x180008ea2  pop     rbx
0x180008ea3  retn
```
