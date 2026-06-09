# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180009acc`
- end: `0x180009bb4`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800077a8`

## callees

- `0x1800029ca`
- `0x180009acc`
- `0x18000a168`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009b2f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009b2f`

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
0x180009acc  push    rbx
0x180009ace  push    rbp
0x180009acf  push    rsi
0x180009ad0  push    rdi
0x180009ad1  push    r14
0x180009ad3  push    r15
0x180009ad5  sub     rsp, 28h
0x180009ad9  mov     al, [rcx+2]
0x180009adc  xor     ebp, ebp
0x180009ade  mov     r9, [rdx]
0x180009ae1  mov     rdi, r8
0x180009ae4  mov     r15, rdx
0x180009ae7  mov     rsi, rcx
0x180009aea  cmp     al, 1
0x180009aec  jnz     short loc_180009B0A
0x180009aee  lea     rbx, [r9+2]
0x180009af2  cmp     rbx, r8
0x180009af5  ja      loc_180009B85
0x180009afb  test    r9, r9
0x180009afe  jz      short loc_180009B2F
0x180009b00  movzx   eax, word ptr [rcx+4]
0x180009b04  mov     [r9], ax
0x180009b08  jmp     short loc_180009B45
0x180009b0a  cmp     al, 2
0x180009b0c  jnz     short loc_180009B42
0x180009b0e  lea     rbx, [r9+4]
0x180009b12  cmp     rbx, rdi
0x180009b15  ja      short loc_180009B85
0x180009b17  test    r9, r9
0x180009b1a  jz      short loc_180009B2F
0x180009b1c  lea     rax, [rcx+4]
0x180009b20  test    rax, rax
0x180009b23  jz      short loc_180009B2C
0x180009b25  mov     eax, [rax]
0x180009b27  mov     [r9], eax
0x180009b2a  jmp     short loc_180009B45
0x180009b2c  mov     [r9], eax
0x180009b2f  call    cs:__imp__o__errno
0x180009b35  mov     dword ptr [rax], 16h
0x180009b3b  call    _invalid_parameter_noinfo
0x180009b40  jmp     short loc_180009B45
0x180009b42  mov     rbx, r9
0x180009b45  cmp     [rsi], bp
0x180009b48  jnz     short loc_180009B73
0x180009b4a  lea     r14, [rbx+2]
0x180009b4e  cmp     r14, rdi
0x180009b51  ja      short loc_180009B85
0x180009b53  lea     rbp, [rsi+8]
0x180009b57  mov     rdx, rdi
0x180009b5a  sub     rdx, rbx; DestinationSize
0x180009b5d  mov     r8, rbp; Source
0x180009b60  mov     r9d, 2; SourceSize
0x180009b66  mov     rcx, rbx; Destination
0x180009b69  call    memcpy_s
0x180009b6e  mov     rbx, r14
0x180009b71  jmp     short loc_180009B77
0x180009b73  lea     rbp, [rsi+8]
0x180009b77  movzx   r9d, word ptr [rbp+0]; SourceSize
0x180009b7c  lea     rax, [r9+rbx]
0x180009b80  cmp     rax, rdi
0x180009b83  jbe     short loc_180009B89
0x180009b85  xor     al, al
0x180009b87  jmp     short loc_180009BA7
0x180009b89  mov     r8, [rsi+18h]; Source
0x180009b8d  sub     rdi, rbx
0x180009b90  mov     rdx, rdi; DestinationSize
0x180009b93  mov     rcx, rbx; Destination
0x180009b96  call    memcpy_s
0x180009b9b  movzx   ecx, word ptr [rbp+0]
0x180009b9f  mov     al, 1
0x180009ba1  add     rcx, rbx
0x180009ba4  mov     [r15], rcx
0x180009ba7  add     rsp, 28h
0x180009bab  pop     r15
0x180009bad  pop     r14
0x180009baf  pop     rdi
0x180009bb0  pop     rsi
0x180009bb1  pop     rbp
0x180009bb2  pop     rbx
0x180009bb3  retn
```
