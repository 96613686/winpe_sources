# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000c2bc`
- end: `0x18000c3a2`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180003ab8`
- `0x18000bc48`
- `0x18000be24`
- `0x18000bf58`
- `0x18000ca9c`

## callees

- `0x1800034d8`
- `0x18000c2bc`

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
0x18000c2bc  mov     rax, rsp
0x18000c2bf  mov     [rax+10h], rbx
0x18000c2c3  mov     [rax+18h], rbp
0x18000c2c7  push    rsi
0x18000c2c8  push    rdi
0x18000c2c9  push    r12
0x18000c2cb  push    r14
0x18000c2cd  push    r15
0x18000c2cf  sub     rsp, 20h
0x18000c2d3  xor     r15d, r15d
0x18000c2d6  mov     rsi, r8
0x18000c2d9  cmp     byte ptr [rcx+2], 1
0x18000c2dd  mov     r12, rdx
0x18000c2e0  mov     r8, [rdx]; Source
0x18000c2e3  mov     rdi, rcx
0x18000c2e6  jnz     short loc_18000C31A
0x18000c2e8  lea     rbx, [r8+2]
0x18000c2ec  cmp     rbx, rsi
0x18000c2ef  ja      loc_18000C37D
0x18000c2f5  lea     ebp, [r15+2]
0x18000c2f9  mov     [rcx+10h], r8
0x18000c2fd  mov     r9d, ebp; SourceSize
0x18000c300  mov     [rax+8], r15w
0x18000c305  mov     edx, ebp; DestinationSize
0x18000c307  lea     rcx, [rax+8]; Destination
0x18000c30b  call    memcpy_s
0x18000c310  movzx   eax, [rsp+48h+arg_0]
0x18000c315  mov     [rdi+4], eax
0x18000c318  jmp     short loc_18000C344
0x18000c31a  mov     ebp, 2
0x18000c31f  mov     rbx, r8
0x18000c322  cmp     [rcx+2], bpl
0x18000c326  jnz     short loc_18000C344
0x18000c328  lea     rbx, [r8+4]
0x18000c32c  cmp     rbx, rsi
0x18000c32f  ja      short loc_18000C37D
0x18000c331  lea     edx, [rbp+2]; DestinationSize
0x18000c334  mov     [rcx+10h], r8
0x18000c338  mov     r9d, edx; SourceSize
0x18000c33b  add     rcx, 4; Destination
0x18000c33f  call    memcpy_s
0x18000c344  movzx   eax, word ptr [rdi]
0x18000c347  lea     r14, [rdi+8]
0x18000c34b  mov     [r14], ax
0x18000c34f  test    ax, ax
0x18000c352  jnz     short loc_18000C371
0x18000c354  lea     r15, [rbx+2]
0x18000c358  cmp     r15, rsi
0x18000c35b  ja      short loc_18000C37D
0x18000c35d  mov     r9, rbp; SourceSize
0x18000c360  mov     r8, rbx; Source
0x18000c363  mov     rdx, rbp; DestinationSize
0x18000c366  mov     rcx, r14; Destination
0x18000c369  call    memcpy_s
0x18000c36e  mov     rbx, r15
0x18000c371  movzx   ecx, word ptr [r14]
0x18000c375  add     rcx, rbx
0x18000c378  cmp     rcx, rsi
0x18000c37b  jbe     short loc_18000C381
0x18000c37d  xor     al, al
0x18000c37f  jmp     short loc_18000C38B
0x18000c381  mov     [rdi+18h], rbx
0x18000c385  mov     al, 1
0x18000c387  mov     [r12], rcx
0x18000c38b  mov     rbx, [rsp+48h+arg_8]
0x18000c390  mov     rbp, [rsp+48h+arg_10]
0x18000c395  add     rsp, 20h
0x18000c399  pop     r15
0x18000c39b  pop     r14
0x18000c39d  pop     r12
0x18000c39f  pop     rdi
0x18000c3a0  pop     rsi
0x18000c3a1  retn
```
