# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x1400089fc`
- end: `0x140008ae4`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140006848`

## callees

- `0x14000216a`
- `0x1400089fc`
- `0x140009088`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140008a5f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140008a5f`

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
0x1400089fc  push    rbx
0x1400089fe  push    rbp
0x1400089ff  push    rsi
0x140008a00  push    rdi
0x140008a01  push    r14
0x140008a03  push    r15
0x140008a05  sub     rsp, 28h
0x140008a09  mov     al, [rcx+2]
0x140008a0c  xor     ebp, ebp
0x140008a0e  mov     r9, [rdx]
0x140008a11  mov     rdi, r8
0x140008a14  mov     r15, rdx
0x140008a17  mov     rsi, rcx
0x140008a1a  cmp     al, 1
0x140008a1c  jnz     short loc_140008A3A
0x140008a1e  lea     rbx, [r9+2]
0x140008a22  cmp     rbx, r8
0x140008a25  ja      loc_140008AB5
0x140008a2b  test    r9, r9
0x140008a2e  jz      short loc_140008A5F
0x140008a30  movzx   eax, word ptr [rcx+4]
0x140008a34  mov     [r9], ax
0x140008a38  jmp     short loc_140008A75
0x140008a3a  cmp     al, 2
0x140008a3c  jnz     short loc_140008A72
0x140008a3e  lea     rbx, [r9+4]
0x140008a42  cmp     rbx, rdi
0x140008a45  ja      short loc_140008AB5
0x140008a47  test    r9, r9
0x140008a4a  jz      short loc_140008A5F
0x140008a4c  lea     rax, [rcx+4]
0x140008a50  test    rax, rax
0x140008a53  jz      short loc_140008A5C
0x140008a55  mov     eax, [rax]
0x140008a57  mov     [r9], eax
0x140008a5a  jmp     short loc_140008A75
0x140008a5c  mov     [r9], eax
0x140008a5f  call    cs:__imp__o__errno
0x140008a65  mov     dword ptr [rax], 16h
0x140008a6b  call    _invalid_parameter_noinfo
0x140008a70  jmp     short loc_140008A75
0x140008a72  mov     rbx, r9
0x140008a75  cmp     [rsi], bp
0x140008a78  jnz     short loc_140008AA3
0x140008a7a  lea     r14, [rbx+2]
0x140008a7e  cmp     r14, rdi
0x140008a81  ja      short loc_140008AB5
0x140008a83  lea     rbp, [rsi+8]
0x140008a87  mov     rdx, rdi
0x140008a8a  sub     rdx, rbx; DestinationSize
0x140008a8d  mov     r8, rbp; Source
0x140008a90  mov     r9d, 2; SourceSize
0x140008a96  mov     rcx, rbx; Destination
0x140008a99  call    memcpy_s
0x140008a9e  mov     rbx, r14
0x140008aa1  jmp     short loc_140008AA7
0x140008aa3  lea     rbp, [rsi+8]
0x140008aa7  movzx   r9d, word ptr [rbp+0]; SourceSize
0x140008aac  lea     rax, [r9+rbx]
0x140008ab0  cmp     rax, rdi
0x140008ab3  jbe     short loc_140008AB9
0x140008ab5  xor     al, al
0x140008ab7  jmp     short loc_140008AD7
0x140008ab9  mov     r8, [rsi+18h]; Source
0x140008abd  sub     rdi, rbx
0x140008ac0  mov     rdx, rdi; DestinationSize
0x140008ac3  mov     rcx, rbx; Destination
0x140008ac6  call    memcpy_s
0x140008acb  movzx   ecx, word ptr [rbp+0]
0x140008acf  mov     al, 1
0x140008ad1  add     rcx, rbx
0x140008ad4  mov     [r15], rcx
0x140008ad7  add     rsp, 28h
0x140008adb  pop     r15
0x140008add  pop     r14
0x140008adf  pop     rdi
0x140008ae0  pop     rsi
0x140008ae1  pop     rbp
0x140008ae2  pop     rbx
0x140008ae3  retn
```
