# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x14000952c`
- end: `0x140009612`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140006e48`
- `0x140008444`
- `0x140008950`
- `0x140009ae0`
- `0x14000ab4c`

## callees

- `0x14000952c`
- `0x14000eff0`

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
0x14000952c  mov     rax, rsp
0x14000952f  mov     [rax+10h], rbx
0x140009533  mov     [rax+18h], rbp
0x140009537  push    rsi
0x140009538  push    rdi
0x140009539  push    r12
0x14000953b  push    r14
0x14000953d  push    r15
0x14000953f  sub     rsp, 20h
0x140009543  xor     r15d, r15d
0x140009546  mov     rsi, r8
0x140009549  cmp     byte ptr [rcx+2], 1
0x14000954d  mov     r12, rdx
0x140009550  mov     r8, [rdx]; Source
0x140009553  mov     rdi, rcx
0x140009556  jnz     short loc_14000958A
0x140009558  lea     rbx, [r8+2]
0x14000955c  cmp     rbx, rsi
0x14000955f  ja      loc_1400095ED
0x140009565  lea     ebp, [r15+2]
0x140009569  mov     [rcx+10h], r8
0x14000956d  mov     r9d, ebp; SourceSize
0x140009570  mov     [rax+8], r15w
0x140009575  mov     edx, ebp; DestinationSize
0x140009577  lea     rcx, [rax+8]; Destination
0x14000957b  call    memcpy_s
0x140009580  movzx   eax, [rsp+48h+arg_0]
0x140009585  mov     [rdi+4], eax
0x140009588  jmp     short loc_1400095B4
0x14000958a  mov     ebp, 2
0x14000958f  mov     rbx, r8
0x140009592  cmp     [rcx+2], bpl
0x140009596  jnz     short loc_1400095B4
0x140009598  lea     rbx, [r8+4]
0x14000959c  cmp     rbx, rsi
0x14000959f  ja      short loc_1400095ED
0x1400095a1  lea     edx, [rbp+2]; DestinationSize
0x1400095a4  mov     [rcx+10h], r8
0x1400095a8  mov     r9d, edx; SourceSize
0x1400095ab  add     rcx, 4; Destination
0x1400095af  call    memcpy_s
0x1400095b4  movzx   eax, word ptr [rdi]
0x1400095b7  lea     r14, [rdi+8]
0x1400095bb  mov     [r14], ax
0x1400095bf  test    ax, ax
0x1400095c2  jnz     short loc_1400095E1
0x1400095c4  lea     r15, [rbx+2]
0x1400095c8  cmp     r15, rsi
0x1400095cb  ja      short loc_1400095ED
0x1400095cd  mov     r9, rbp; SourceSize
0x1400095d0  mov     r8, rbx; Source
0x1400095d3  mov     rdx, rbp; DestinationSize
0x1400095d6  mov     rcx, r14; Destination
0x1400095d9  call    memcpy_s
0x1400095de  mov     rbx, r15
0x1400095e1  movzx   ecx, word ptr [r14]
0x1400095e5  add     rcx, rbx
0x1400095e8  cmp     rcx, rsi
0x1400095eb  jbe     short loc_1400095F1
0x1400095ed  xor     al, al
0x1400095ef  jmp     short loc_1400095FB
0x1400095f1  mov     [rdi+18h], rbx
0x1400095f5  mov     al, 1
0x1400095f7  mov     [r12], rcx
0x1400095fb  mov     rbx, [rsp+48h+arg_8]
0x140009600  mov     rbp, [rsp+48h+arg_10]
0x140009605  add     rsp, 20h
0x140009609  pop     r15
0x14000960b  pop     r14
0x14000960d  pop     r12
0x14000960f  pop     rdi
0x140009610  pop     rsi
0x140009611  retn
```
