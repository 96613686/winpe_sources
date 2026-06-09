# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180013ddc`
- end: `0x180013ed8`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `252`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800122a8`
- `0x180014480`
- `0x180014820`

## callees

- `0x180013ddc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180013e2b`
- `msvcrt!memcpy_s` at `0x180013e66`
- `msvcrt!memcpy_s` at `0x180013e97`
- `msvcrt!memcpy_s` at `0x180013e2b`
- `msvcrt!memcpy_s` at `0x180013e66`
- `msvcrt!memcpy_s` at `0x180013e97`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char *v5; // r8
  char *v7; // rbx
  __int16 v8; // ax
  unsigned __int8 *v9; // rcx
  bool result; // al
  unsigned __int16 v11; // [rsp+50h] [rbp+8h] BYREF

  v5 = (char *)*a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v5 + 2;
    if ( v5 + 2 > (char *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v5;
    v11 = 0;
    memcpy_s(&v11, 2u, v5, 2u);
    *((_DWORD *)this + 1) = v11;
  }
  else
  {
    v7 = (char *)*a2;
    if ( *((_BYTE *)this + 2) == 2 )
    {
      v7 = v5 + 4;
      if ( v5 + 4 > (char *)a3 )
        return 0;
      *((_QWORD *)this + 2) = v5;
      memcpy_s((char *)this + 4, 4u, v5, 4u);
    }
  }
  v8 = *(_WORD *)this;
  *((_WORD *)this + 4) = *(_WORD *)this;
  if ( v8 )
    goto LABEL_10;
  if ( v7 + 2 > (char *)a3 )
    return 0;
  memcpy_s((char *)this + 8, 2u, v7, 2u);
  v7 += 2;
LABEL_10:
  v9 = (unsigned __int8 *)&v7[*((unsigned __int16 *)this + 4)];
  if ( v9 > a3 )
    return 0;
  *((_QWORD *)this + 3) = v7;
  result = 1;
  *a2 = v9;
  return result;
}

```

## disassembly

```asm
0x180013ddc  mov     rax, rsp
0x180013ddf  mov     [rax+10h], rbx
0x180013de3  mov     [rax+18h], rbp
0x180013de7  push    rsi
0x180013de8  push    rdi
0x180013de9  push    r12
0x180013deb  push    r14
0x180013ded  push    r15
0x180013def  sub     rsp, 20h
0x180013df3  xor     r15d, r15d
0x180013df6  mov     rsi, r8
0x180013df9  cmp     byte ptr [rcx+2], 1
0x180013dfd  mov     r12, rdx
0x180013e00  mov     r8, [rdx]; Source
0x180013e03  mov     rdi, rcx
0x180013e06  jnz     short loc_180013E41
0x180013e08  lea     rbx, [r8+2]
0x180013e0c  cmp     rbx, rsi
0x180013e0f  ja      loc_180013EB2
0x180013e15  lea     ebp, [r15+2]
0x180013e19  mov     [rcx+10h], r8
0x180013e1d  mov     r9d, ebp; SourceSize
0x180013e20  mov     [rax+8], r15w
0x180013e25  mov     edx, ebp; DestinationSize
0x180013e27  lea     rcx, [rax+8]; Destination
0x180013e2b  call    cs:__imp_memcpy_s
0x180013e32  nop     dword ptr [rax+rax+00h]
0x180013e37  movzx   eax, [rsp+48h+arg_0]
0x180013e3c  mov     [rdi+4], eax
0x180013e3f  jmp     short loc_180013E72
0x180013e41  mov     ebp, 2
0x180013e46  mov     rbx, r8
0x180013e49  cmp     [rcx+2], bpl
0x180013e4d  jnz     short loc_180013E72
0x180013e4f  lea     rbx, [r8+4]
0x180013e53  cmp     rbx, rsi
0x180013e56  ja      short loc_180013EB2
0x180013e58  lea     edx, [rbp+2]; DestinationSize
0x180013e5b  mov     [rcx+10h], r8
0x180013e5f  mov     r9d, edx; SourceSize
0x180013e62  add     rcx, 4; Destination
0x180013e66  call    cs:__imp_memcpy_s
0x180013e6d  nop     dword ptr [rax+rax+00h]
0x180013e72  movzx   eax, word ptr [rdi]
0x180013e75  lea     r14, [rdi+8]
0x180013e79  mov     [r14], ax
0x180013e7d  test    ax, ax
0x180013e80  jnz     short loc_180013EA6
0x180013e82  lea     r15, [rbx+2]
0x180013e86  cmp     r15, rsi
0x180013e89  ja      short loc_180013EB2
0x180013e8b  mov     r9, rbp; SourceSize
0x180013e8e  mov     r8, rbx; Source
0x180013e91  mov     rdx, rbp; DestinationSize
0x180013e94  mov     rcx, r14; Destination
0x180013e97  call    cs:__imp_memcpy_s
0x180013e9e  nop     dword ptr [rax+rax+00h]
0x180013ea3  mov     rbx, r15
0x180013ea6  movzx   ecx, word ptr [r14]
0x180013eaa  add     rcx, rbx
0x180013ead  cmp     rcx, rsi
0x180013eb0  jbe     short loc_180013EB6
0x180013eb2  xor     al, al
0x180013eb4  jmp     short loc_180013EC0
0x180013eb6  mov     [rdi+18h], rbx
0x180013eba  mov     al, 1
0x180013ebc  mov     [r12], rcx
0x180013ec0  mov     rbx, [rsp+48h+arg_8]
0x180013ec5  mov     rbp, [rsp+48h+arg_10]
0x180013eca  add     rsp, 20h
0x180013ece  pop     r15
0x180013ed0  pop     r14
0x180013ed2  pop     r12
0x180013ed4  pop     rdi
0x180013ed5  pop     rsi
0x180013ed6  retn
```
