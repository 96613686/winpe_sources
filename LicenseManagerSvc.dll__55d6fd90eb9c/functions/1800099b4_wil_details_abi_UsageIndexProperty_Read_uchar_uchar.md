# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800099b4`
- end: `0x180009a9a`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180008774`
- `0x1800091dc`
- `0x18000931c`
- `0x180009f68`
- `0x18000aa44`

## callees

- `0x180007b30`
- `0x1800099b4`

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
0x1800099b4  mov     rax, rsp
0x1800099b7  mov     [rax+10h], rbx
0x1800099bb  mov     [rax+18h], rbp
0x1800099bf  push    rsi
0x1800099c0  push    rdi
0x1800099c1  push    r12
0x1800099c3  push    r14
0x1800099c5  push    r15
0x1800099c7  sub     rsp, 20h
0x1800099cb  xor     r15d, r15d
0x1800099ce  mov     rsi, r8
0x1800099d1  cmp     byte ptr [rcx+2], 1
0x1800099d5  mov     r12, rdx
0x1800099d8  mov     r8, [rdx]; Source
0x1800099db  mov     rdi, rcx
0x1800099de  jnz     short loc_180009A12
0x1800099e0  lea     rbx, [r8+2]
0x1800099e4  cmp     rbx, rsi
0x1800099e7  ja      loc_180009A75
0x1800099ed  lea     ebp, [r15+2]
0x1800099f1  mov     [rcx+10h], r8
0x1800099f5  mov     r9d, ebp; SourceSize
0x1800099f8  mov     [rax+8], r15w
0x1800099fd  mov     edx, ebp; DestinationSize
0x1800099ff  lea     rcx, [rax+8]; Destination
0x180009a03  call    memcpy_s
0x180009a08  movzx   eax, [rsp+48h+arg_0]
0x180009a0d  mov     [rdi+4], eax
0x180009a10  jmp     short loc_180009A3C
0x180009a12  mov     ebp, 2
0x180009a17  mov     rbx, r8
0x180009a1a  cmp     [rcx+2], bpl
0x180009a1e  jnz     short loc_180009A3C
0x180009a20  lea     rbx, [r8+4]
0x180009a24  cmp     rbx, rsi
0x180009a27  ja      short loc_180009A75
0x180009a29  lea     edx, [rbp+2]; DestinationSize
0x180009a2c  mov     [rcx+10h], r8
0x180009a30  mov     r9d, edx; SourceSize
0x180009a33  add     rcx, 4; Destination
0x180009a37  call    memcpy_s
0x180009a3c  movzx   eax, word ptr [rdi]
0x180009a3f  lea     r14, [rdi+8]
0x180009a43  mov     [r14], ax
0x180009a47  test    ax, ax
0x180009a4a  jnz     short loc_180009A69
0x180009a4c  lea     r15, [rbx+2]
0x180009a50  cmp     r15, rsi
0x180009a53  ja      short loc_180009A75
0x180009a55  mov     r9, rbp; SourceSize
0x180009a58  mov     r8, rbx; Source
0x180009a5b  mov     rdx, rbp; DestinationSize
0x180009a5e  mov     rcx, r14; Destination
0x180009a61  call    memcpy_s
0x180009a66  mov     rbx, r15
0x180009a69  movzx   ecx, word ptr [r14]
0x180009a6d  add     rcx, rbx
0x180009a70  cmp     rcx, rsi
0x180009a73  jbe     short loc_180009A79
0x180009a75  xor     al, al
0x180009a77  jmp     short loc_180009A83
0x180009a79  mov     [rdi+18h], rbx
0x180009a7d  mov     al, 1
0x180009a7f  mov     [r12], rcx
0x180009a83  mov     rbx, [rsp+48h+arg_8]
0x180009a88  mov     rbp, [rsp+48h+arg_10]
0x180009a8d  add     rsp, 20h
0x180009a91  pop     r15
0x180009a93  pop     r14
0x180009a95  pop     r12
0x180009a97  pop     rdi
0x180009a98  pop     rsi
0x180009a99  retn
```
