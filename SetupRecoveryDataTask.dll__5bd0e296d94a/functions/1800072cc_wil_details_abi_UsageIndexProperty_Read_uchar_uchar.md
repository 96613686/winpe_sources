# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800072cc`
- end: `0x1800073d1`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `261`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180004cc0`
- `0x180007b94`
- `0x180007f30`

## callees

- `0x1800072cc`
- `0x18000c610`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000732a`
- `msvcrt!memcpy_s` at `0x18000735f`
- `msvcrt!memcpy_s` at `0x18000738a`
- `msvcrt!memcpy_s` at `0x18000732a`
- `msvcrt!memcpy_s` at `0x18000735f`
- `msvcrt!memcpy_s` at `0x18000738a`

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
0x1800072cc  mov     r11, rsp
0x1800072cf  mov     [r11+18h], rbx
0x1800072d3  mov     [r11+20h], rbp
0x1800072d7  push    rsi
0x1800072d8  push    rdi
0x1800072d9  push    r12
0x1800072db  push    r14
0x1800072dd  push    r15
0x1800072df  sub     rsp, 30h
0x1800072e3  mov     rax, cs:__security_cookie
0x1800072ea  xor     rax, rsp
0x1800072ed  mov     [rsp+58h+var_30], rax
0x1800072f2  xor     r15d, r15d
0x1800072f5  mov     rsi, r8
0x1800072f8  cmp     byte ptr [rcx+2], 1
0x1800072fc  mov     r12, rdx
0x1800072ff  mov     r8, [rdx]; Source
0x180007302  mov     rdi, rcx
0x180007305  jnz     short loc_18000733A
0x180007307  lea     rbx, [r8+2]
0x18000730b  cmp     rbx, rsi
0x18000730e  ja      loc_18000739F
0x180007314  lea     ebp, [r15+2]
0x180007318  mov     [rcx+10h], r8
0x18000731c  mov     r9d, ebp; SourceSize
0x18000731f  mov     [r11-38h], r15w
0x180007324  mov     edx, ebp; DestinationSize
0x180007326  lea     rcx, [r11-38h]; Destination
0x18000732a  call    cs:__imp_memcpy_s
0x180007330  movzx   eax, [rsp+58h+var_38]
0x180007335  mov     [rdi+4], eax
0x180007338  jmp     short loc_180007365
0x18000733a  mov     ebp, 2
0x18000733f  mov     rbx, r8
0x180007342  cmp     [rcx+2], bpl
0x180007346  jnz     short loc_180007365
0x180007348  lea     rbx, [r8+4]
0x18000734c  cmp     rbx, rsi
0x18000734f  ja      short loc_18000739F
0x180007351  lea     edx, [rbp+2]; DestinationSize
0x180007354  mov     [rcx+10h], r8
0x180007358  mov     r9d, edx; SourceSize
0x18000735b  add     rcx, 4; Destination
0x18000735f  call    cs:__imp_memcpy_s
0x180007365  movzx   eax, word ptr [rdi]
0x180007368  lea     r14, [rdi+8]
0x18000736c  mov     [r14], ax
0x180007370  test    ax, ax
0x180007373  jnz     short loc_180007393
0x180007375  lea     r15, [rbx+2]
0x180007379  cmp     r15, rsi
0x18000737c  ja      short loc_18000739F
0x18000737e  mov     r9, rbp; SourceSize
0x180007381  mov     r8, rbx; Source
0x180007384  mov     rdx, rbp; DestinationSize
0x180007387  mov     rcx, r14; Destination
0x18000738a  call    cs:__imp_memcpy_s
0x180007390  mov     rbx, r15
0x180007393  movzx   ecx, word ptr [r14]
0x180007397  add     rcx, rbx
0x18000739a  cmp     rcx, rsi
0x18000739d  jbe     short loc_1800073A3
0x18000739f  xor     al, al
0x1800073a1  jmp     short loc_1800073AD
0x1800073a3  mov     [rdi+18h], rbx
0x1800073a7  mov     al, 1
0x1800073a9  mov     [r12], rcx
0x1800073ad  mov     rcx, [rsp+58h+var_30]
0x1800073b2  xor     rcx, rsp; StackCookie
0x1800073b5  call    __security_check_cookie
0x1800073ba  mov     rbx, [rsp+58h+arg_10]
0x1800073bf  mov     rbp, [rsp+58h+arg_18]
0x1800073c4  add     rsp, 30h
0x1800073c8  pop     r15
0x1800073ca  pop     r14
0x1800073cc  pop     r12
0x1800073ce  pop     rdi
0x1800073cf  pop     rsi
0x1800073d0  retn
```
