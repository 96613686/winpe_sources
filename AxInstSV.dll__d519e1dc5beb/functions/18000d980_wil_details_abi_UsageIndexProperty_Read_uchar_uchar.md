# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000d980`
- end: `0x18000da66`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ad78`
- `0x18000c7fc`
- `0x18000ccd0`
- `0x18000df24`
- `0x18000fc14`

## callees

- `0x18000d980`
- `0x1800117b0`

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
0x18000d980  mov     rax, rsp
0x18000d983  mov     [rax+10h], rbx
0x18000d987  mov     [rax+18h], rbp
0x18000d98b  push    rsi
0x18000d98c  push    rdi
0x18000d98d  push    r12
0x18000d98f  push    r14
0x18000d991  push    r15
0x18000d993  sub     rsp, 20h
0x18000d997  xor     r15d, r15d
0x18000d99a  mov     rsi, r8
0x18000d99d  cmp     byte ptr [rcx+2], 1
0x18000d9a1  mov     r12, rdx
0x18000d9a4  mov     r8, [rdx]; Source
0x18000d9a7  mov     rdi, rcx
0x18000d9aa  jnz     short loc_18000D9DE
0x18000d9ac  lea     rbx, [r8+2]
0x18000d9b0  cmp     rbx, rsi
0x18000d9b3  ja      loc_18000DA41
0x18000d9b9  lea     ebp, [r15+2]
0x18000d9bd  mov     [rcx+10h], r8
0x18000d9c1  mov     r9d, ebp; SourceSize
0x18000d9c4  mov     [rax+8], r15w
0x18000d9c9  mov     edx, ebp; DestinationSize
0x18000d9cb  lea     rcx, [rax+8]; Destination
0x18000d9cf  call    memcpy_s
0x18000d9d4  movzx   eax, [rsp+48h+arg_0]
0x18000d9d9  mov     [rdi+4], eax
0x18000d9dc  jmp     short loc_18000DA08
0x18000d9de  mov     ebp, 2
0x18000d9e3  mov     rbx, r8
0x18000d9e6  cmp     [rcx+2], bpl
0x18000d9ea  jnz     short loc_18000DA08
0x18000d9ec  lea     rbx, [r8+4]
0x18000d9f0  cmp     rbx, rsi
0x18000d9f3  ja      short loc_18000DA41
0x18000d9f5  lea     edx, [rbp+2]; DestinationSize
0x18000d9f8  mov     [rcx+10h], r8
0x18000d9fc  mov     r9d, edx; SourceSize
0x18000d9ff  add     rcx, 4; Destination
0x18000da03  call    memcpy_s
0x18000da08  movzx   eax, word ptr [rdi]
0x18000da0b  lea     r14, [rdi+8]
0x18000da0f  mov     [r14], ax
0x18000da13  test    ax, ax
0x18000da16  jnz     short loc_18000DA35
0x18000da18  lea     r15, [rbx+2]
0x18000da1c  cmp     r15, rsi
0x18000da1f  ja      short loc_18000DA41
0x18000da21  mov     r9, rbp; SourceSize
0x18000da24  mov     r8, rbx; Source
0x18000da27  mov     rdx, rbp; DestinationSize
0x18000da2a  mov     rcx, r14; Destination
0x18000da2d  call    memcpy_s
0x18000da32  mov     rbx, r15
0x18000da35  movzx   ecx, word ptr [r14]
0x18000da39  add     rcx, rbx
0x18000da3c  cmp     rcx, rsi
0x18000da3f  jbe     short loc_18000DA45
0x18000da41  xor     al, al
0x18000da43  jmp     short loc_18000DA4F
0x18000da45  mov     [rdi+18h], rbx
0x18000da49  mov     al, 1
0x18000da4b  mov     [r12], rcx
0x18000da4f  mov     rbx, [rsp+48h+arg_8]
0x18000da54  mov     rbp, [rsp+48h+arg_10]
0x18000da59  add     rsp, 20h
0x18000da5d  pop     r15
0x18000da5f  pop     r14
0x18000da61  pop     r12
0x18000da63  pop     rdi
0x18000da64  pop     rsi
0x18000da65  retn
```
