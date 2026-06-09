# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180007a3c`
- end: `0x180007b24`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006060`

## callees

- `0x180002472`
- `0x180007a3c`
- `0x180007ed4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007a9f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007a9f`

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
0x180007a3c  push    rbx
0x180007a3e  push    rbp
0x180007a3f  push    rsi
0x180007a40  push    rdi
0x180007a41  push    r14
0x180007a43  push    r15
0x180007a45  sub     rsp, 28h
0x180007a49  mov     al, [rcx+2]
0x180007a4c  xor     ebp, ebp
0x180007a4e  mov     r9, [rdx]
0x180007a51  mov     rdi, r8
0x180007a54  mov     r15, rdx
0x180007a57  mov     rsi, rcx
0x180007a5a  cmp     al, 1
0x180007a5c  jnz     short loc_180007A7A
0x180007a5e  lea     rbx, [r9+2]
0x180007a62  cmp     rbx, r8
0x180007a65  ja      loc_180007AF5
0x180007a6b  test    r9, r9
0x180007a6e  jz      short loc_180007A9F
0x180007a70  movzx   eax, word ptr [rcx+4]
0x180007a74  mov     [r9], ax
0x180007a78  jmp     short loc_180007AB5
0x180007a7a  cmp     al, 2
0x180007a7c  jnz     short loc_180007AB2
0x180007a7e  lea     rbx, [r9+4]
0x180007a82  cmp     rbx, rdi
0x180007a85  ja      short loc_180007AF5
0x180007a87  test    r9, r9
0x180007a8a  jz      short loc_180007A9F
0x180007a8c  lea     rax, [rcx+4]
0x180007a90  test    rax, rax
0x180007a93  jz      short loc_180007A9C
0x180007a95  mov     eax, [rax]
0x180007a97  mov     [r9], eax
0x180007a9a  jmp     short loc_180007AB5
0x180007a9c  mov     [r9], eax
0x180007a9f  call    cs:__imp__o__errno
0x180007aa5  mov     dword ptr [rax], 16h
0x180007aab  call    _invalid_parameter_noinfo
0x180007ab0  jmp     short loc_180007AB5
0x180007ab2  mov     rbx, r9
0x180007ab5  cmp     [rsi], bp
0x180007ab8  jnz     short loc_180007AE3
0x180007aba  lea     r14, [rbx+2]
0x180007abe  cmp     r14, rdi
0x180007ac1  ja      short loc_180007AF5
0x180007ac3  lea     rbp, [rsi+8]
0x180007ac7  mov     rdx, rdi
0x180007aca  sub     rdx, rbx; DestinationSize
0x180007acd  mov     r8, rbp; Source
0x180007ad0  mov     r9d, 2; SourceSize
0x180007ad6  mov     rcx, rbx; Destination
0x180007ad9  call    memcpy_s
0x180007ade  mov     rbx, r14
0x180007ae1  jmp     short loc_180007AE7
0x180007ae3  lea     rbp, [rsi+8]
0x180007ae7  movzx   r9d, word ptr [rbp+0]; SourceSize
0x180007aec  lea     rax, [r9+rbx]
0x180007af0  cmp     rax, rdi
0x180007af3  jbe     short loc_180007AF9
0x180007af5  xor     al, al
0x180007af7  jmp     short loc_180007B17
0x180007af9  mov     r8, [rsi+18h]; Source
0x180007afd  sub     rdi, rbx
0x180007b00  mov     rdx, rdi; DestinationSize
0x180007b03  mov     rcx, rbx; Destination
0x180007b06  call    memcpy_s
0x180007b0b  movzx   ecx, word ptr [rbp+0]
0x180007b0f  mov     al, 1
0x180007b11  add     rcx, rbx
0x180007b14  mov     [r15], rcx
0x180007b17  add     rsp, 28h
0x180007b1b  pop     r15
0x180007b1d  pop     r14
0x180007b1f  pop     rdi
0x180007b20  pop     rsi
0x180007b21  pop     rbp
0x180007b22  pop     rbx
0x180007b23  retn
```
