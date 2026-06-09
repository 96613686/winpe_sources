# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x14000c7b0`
- end: `0x14000c896`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b3f8`
- `0x14000ba60`
- `0x14000bb90`
- `0x14000cca8`
- `0x1400101d8`

## callees

- `0x140007ea4`
- `0x14000c7b0`

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
0x14000c7b0  mov     rax, rsp
0x14000c7b3  mov     [rax+10h], rbx
0x14000c7b7  mov     [rax+18h], rbp
0x14000c7bb  push    rsi
0x14000c7bc  push    rdi
0x14000c7bd  push    r12
0x14000c7bf  push    r14
0x14000c7c1  push    r15
0x14000c7c3  sub     rsp, 20h
0x14000c7c7  xor     r15d, r15d
0x14000c7ca  mov     rsi, r8
0x14000c7cd  cmp     byte ptr [rcx+2], 1
0x14000c7d1  mov     r12, rdx
0x14000c7d4  mov     r8, [rdx]; Source
0x14000c7d7  mov     rdi, rcx
0x14000c7da  jnz     short loc_14000C80E
0x14000c7dc  lea     rbx, [r8+2]
0x14000c7e0  cmp     rbx, rsi
0x14000c7e3  ja      loc_14000C871
0x14000c7e9  lea     ebp, [r15+2]
0x14000c7ed  mov     [rcx+10h], r8
0x14000c7f1  mov     r9d, ebp; SourceSize
0x14000c7f4  mov     [rax+8], r15w
0x14000c7f9  mov     edx, ebp; DestinationSize
0x14000c7fb  lea     rcx, [rax+8]; Destination
0x14000c7ff  call    memcpy_s
0x14000c804  movzx   eax, [rsp+48h+arg_0]
0x14000c809  mov     [rdi+4], eax
0x14000c80c  jmp     short loc_14000C838
0x14000c80e  mov     ebp, 2
0x14000c813  mov     rbx, r8
0x14000c816  cmp     [rcx+2], bpl
0x14000c81a  jnz     short loc_14000C838
0x14000c81c  lea     rbx, [r8+4]
0x14000c820  cmp     rbx, rsi
0x14000c823  ja      short loc_14000C871
0x14000c825  lea     edx, [rbp+2]; DestinationSize
0x14000c828  mov     [rcx+10h], r8
0x14000c82c  mov     r9d, edx; SourceSize
0x14000c82f  add     rcx, 4; Destination
0x14000c833  call    memcpy_s
0x14000c838  movzx   eax, word ptr [rdi]
0x14000c83b  lea     r14, [rdi+8]
0x14000c83f  mov     [r14], ax
0x14000c843  test    ax, ax
0x14000c846  jnz     short loc_14000C865
0x14000c848  lea     r15, [rbx+2]
0x14000c84c  cmp     r15, rsi
0x14000c84f  ja      short loc_14000C871
0x14000c851  mov     r9, rbp; SourceSize
0x14000c854  mov     r8, rbx; Source
0x14000c857  mov     rdx, rbp; DestinationSize
0x14000c85a  mov     rcx, r14; Destination
0x14000c85d  call    memcpy_s
0x14000c862  mov     rbx, r15
0x14000c865  movzx   ecx, word ptr [r14]
0x14000c869  add     rcx, rbx
0x14000c86c  cmp     rcx, rsi
0x14000c86f  jbe     short loc_14000C875
0x14000c871  xor     al, al
0x14000c873  jmp     short loc_14000C87F
0x14000c875  mov     [rdi+18h], rbx
0x14000c879  mov     al, 1
0x14000c87b  mov     [r12], rcx
0x14000c87f  mov     rbx, [rsp+48h+arg_8]
0x14000c884  mov     rbp, [rsp+48h+arg_10]
0x14000c889  add     rsp, 20h
0x14000c88d  pop     r15
0x14000c88f  pop     r14
0x14000c891  pop     r12
0x14000c893  pop     rdi
0x14000c894  pop     rsi
0x14000c895  retn
```
