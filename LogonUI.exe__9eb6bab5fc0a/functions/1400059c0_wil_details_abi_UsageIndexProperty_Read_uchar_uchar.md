# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1400059c0`
- end: `0x140005aa6`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140001e60`
- `0x140004490`
- `0x140004f94`
- `0x1400053c0`
- `0x140006590`

## callees

- `0x140001cdc`
- `0x1400059c0`

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
0x1400059c0  mov     rax, rsp
0x1400059c3  mov     [rax+10h], rbx
0x1400059c7  mov     [rax+18h], rbp
0x1400059cb  push    rsi
0x1400059cc  push    rdi
0x1400059cd  push    r12
0x1400059cf  push    r14
0x1400059d1  push    r15
0x1400059d3  sub     rsp, 20h
0x1400059d7  xor     r15d, r15d
0x1400059da  mov     rsi, r8
0x1400059dd  cmp     byte ptr [rcx+2], 1
0x1400059e1  mov     r12, rdx
0x1400059e4  mov     r8, [rdx]; Source
0x1400059e7  mov     rdi, rcx
0x1400059ea  jnz     short loc_140005A1E
0x1400059ec  lea     rbx, [r8+2]
0x1400059f0  cmp     rbx, rsi
0x1400059f3  ja      loc_140005A81
0x1400059f9  lea     ebp, [r15+2]
0x1400059fd  mov     [rcx+10h], r8
0x140005a01  mov     r9d, ebp; SourceSize
0x140005a04  mov     [rax+8], r15w
0x140005a09  mov     edx, ebp; DestinationSize
0x140005a0b  lea     rcx, [rax+8]; Destination
0x140005a0f  call    memcpy_s
0x140005a14  movzx   eax, [rsp+48h+arg_0]
0x140005a19  mov     [rdi+4], eax
0x140005a1c  jmp     short loc_140005A48
0x140005a1e  mov     ebp, 2
0x140005a23  mov     rbx, r8
0x140005a26  cmp     [rcx+2], bpl
0x140005a2a  jnz     short loc_140005A48
0x140005a2c  lea     rbx, [r8+4]
0x140005a30  cmp     rbx, rsi
0x140005a33  ja      short loc_140005A81
0x140005a35  lea     edx, [rbp+2]; DestinationSize
0x140005a38  mov     [rcx+10h], r8
0x140005a3c  mov     r9d, edx; SourceSize
0x140005a3f  add     rcx, 4; Destination
0x140005a43  call    memcpy_s
0x140005a48  movzx   eax, word ptr [rdi]
0x140005a4b  lea     r14, [rdi+8]
0x140005a4f  mov     [r14], ax
0x140005a53  test    ax, ax
0x140005a56  jnz     short loc_140005A75
0x140005a58  lea     r15, [rbx+2]
0x140005a5c  cmp     r15, rsi
0x140005a5f  ja      short loc_140005A81
0x140005a61  mov     r9, rbp; SourceSize
0x140005a64  mov     r8, rbx; Source
0x140005a67  mov     rdx, rbp; DestinationSize
0x140005a6a  mov     rcx, r14; Destination
0x140005a6d  call    memcpy_s
0x140005a72  mov     rbx, r15
0x140005a75  movzx   ecx, word ptr [r14]
0x140005a79  add     rcx, rbx
0x140005a7c  cmp     rcx, rsi
0x140005a7f  jbe     short loc_140005A85
0x140005a81  xor     al, al
0x140005a83  jmp     short loc_140005A8F
0x140005a85  mov     [rdi+18h], rbx
0x140005a89  mov     al, 1
0x140005a8b  mov     [r12], rcx
0x140005a8f  mov     rbx, [rsp+48h+arg_8]
0x140005a94  mov     rbp, [rsp+48h+arg_10]
0x140005a99  add     rsp, 20h
0x140005a9d  pop     r15
0x140005a9f  pop     r14
0x140005aa1  pop     r12
0x140005aa3  pop     rdi
0x140005aa4  pop     rsi
0x140005aa5  retn
```
