# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x14000bb7c`
- end: `0x14000bc7e`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `258`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x14000ac1c`
- `0x14000b4a0`
- `0x14000b5fc`
- `0x14000c0f8`
- `0x14000c7c4`

## callees

- `0x140002310`
- `0x140005ef8`
- `0x14000bb7c`

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
  unsigned __int16 v11; // [rsp+20h] [rbp-38h] BYREF

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
0x14000bb7c  mov     r11, rsp
0x14000bb7f  mov     [r11+18h], rbx
0x14000bb83  mov     [r11+20h], rbp
0x14000bb87  push    rsi
0x14000bb88  push    rdi
0x14000bb89  push    r12
0x14000bb8b  push    r14
0x14000bb8d  push    r15
0x14000bb8f  sub     rsp, 30h
0x14000bb93  mov     rax, cs:__security_cookie
0x14000bb9a  xor     rax, rsp
0x14000bb9d  mov     [rsp+58h+var_30], rax
0x14000bba2  xor     r15d, r15d
0x14000bba5  mov     rsi, r8
0x14000bba8  cmp     byte ptr [rcx+2], 1
0x14000bbac  mov     r12, rdx
0x14000bbaf  mov     r8, [rdx]; Source
0x14000bbb2  mov     rdi, rcx
0x14000bbb5  jnz     short loc_14000BBE9
0x14000bbb7  lea     rbx, [r8+2]
0x14000bbbb  cmp     rbx, rsi
0x14000bbbe  ja      loc_14000BC4C
0x14000bbc4  lea     ebp, [r15+2]
0x14000bbc8  mov     [rcx+10h], r8
0x14000bbcc  mov     r9d, ebp; SourceSize
0x14000bbcf  mov     [r11-38h], r15w
0x14000bbd4  mov     edx, ebp; DestinationSize
0x14000bbd6  lea     rcx, [r11-38h]; Destination
0x14000bbda  call    memcpy_s
0x14000bbdf  movzx   eax, [rsp+58h+var_38]
0x14000bbe4  mov     [rdi+4], eax
0x14000bbe7  jmp     short loc_14000BC13
0x14000bbe9  mov     ebp, 2
0x14000bbee  mov     rbx, r8
0x14000bbf1  cmp     [rcx+2], bpl
0x14000bbf5  jnz     short loc_14000BC13
0x14000bbf7  lea     rbx, [r8+4]
0x14000bbfb  cmp     rbx, rsi
0x14000bbfe  ja      short loc_14000BC4C
0x14000bc00  lea     edx, [rbp+2]; DestinationSize
0x14000bc03  mov     [rcx+10h], r8
0x14000bc07  mov     r9d, edx; SourceSize
0x14000bc0a  add     rcx, 4; Destination
0x14000bc0e  call    memcpy_s
0x14000bc13  movzx   eax, word ptr [rdi]
0x14000bc16  lea     r14, [rdi+8]
0x14000bc1a  mov     [r14], ax
0x14000bc1e  test    ax, ax
0x14000bc21  jnz     short loc_14000BC40
0x14000bc23  lea     r15, [rbx+2]
0x14000bc27  cmp     r15, rsi
0x14000bc2a  ja      short loc_14000BC4C
0x14000bc2c  mov     r9, rbp; SourceSize
0x14000bc2f  mov     r8, rbx; Source
0x14000bc32  mov     rdx, rbp; DestinationSize
0x14000bc35  mov     rcx, r14; Destination
0x14000bc38  call    memcpy_s
0x14000bc3d  mov     rbx, r15
0x14000bc40  movzx   ecx, word ptr [r14]
0x14000bc44  add     rcx, rbx
0x14000bc47  cmp     rcx, rsi
0x14000bc4a  jbe     short loc_14000BC50
0x14000bc4c  xor     al, al
0x14000bc4e  jmp     short loc_14000BC5A
0x14000bc50  mov     [rdi+18h], rbx
0x14000bc54  mov     al, 1
0x14000bc56  mov     [r12], rcx
0x14000bc5a  mov     rcx, [rsp+58h+var_30]
0x14000bc5f  xor     rcx, rsp; StackCookie
0x14000bc62  call    __security_check_cookie
0x14000bc67  mov     rbx, [rsp+58h+arg_10]
0x14000bc6c  mov     rbp, [rsp+58h+arg_18]
0x14000bc71  add     rsp, 30h
0x14000bc75  pop     r15
0x14000bc77  pop     r14
0x14000bc79  pop     r12
0x14000bc7b  pop     rdi
0x14000bc7c  pop     rsi
0x14000bc7d  retn
```
