# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180007e34`
- end: `0x180007f1a`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180004aac`
- `0x180006fec`
- `0x180007470`
- `0x180008428`
- `0x180009a18`

## callees

- `0x180007e34`
- `0x18000b43c`

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
0x180007e34  mov     rax, rsp
0x180007e37  mov     [rax+10h], rbx
0x180007e3b  mov     [rax+18h], rbp
0x180007e3f  push    rsi
0x180007e40  push    rdi
0x180007e41  push    r12
0x180007e43  push    r14
0x180007e45  push    r15
0x180007e47  sub     rsp, 20h
0x180007e4b  xor     r15d, r15d
0x180007e4e  mov     rsi, r8
0x180007e51  cmp     byte ptr [rcx+2], 1
0x180007e55  mov     r12, rdx
0x180007e58  mov     r8, [rdx]; Source
0x180007e5b  mov     rdi, rcx
0x180007e5e  jnz     short loc_180007E92
0x180007e60  lea     rbx, [r8+2]
0x180007e64  cmp     rbx, rsi
0x180007e67  ja      loc_180007EF5
0x180007e6d  lea     ebp, [r15+2]
0x180007e71  mov     [rcx+10h], r8
0x180007e75  mov     r9d, ebp; SourceSize
0x180007e78  mov     [rax+8], r15w
0x180007e7d  mov     edx, ebp; DestinationSize
0x180007e7f  lea     rcx, [rax+8]; Destination
0x180007e83  call    memcpy_s
0x180007e88  movzx   eax, [rsp+48h+arg_0]
0x180007e8d  mov     [rdi+4], eax
0x180007e90  jmp     short loc_180007EBC
0x180007e92  mov     ebp, 2
0x180007e97  mov     rbx, r8
0x180007e9a  cmp     [rcx+2], bpl
0x180007e9e  jnz     short loc_180007EBC
0x180007ea0  lea     rbx, [r8+4]
0x180007ea4  cmp     rbx, rsi
0x180007ea7  ja      short loc_180007EF5
0x180007ea9  lea     edx, [rbp+2]; DestinationSize
0x180007eac  mov     [rcx+10h], r8
0x180007eb0  mov     r9d, edx; SourceSize
0x180007eb3  add     rcx, 4; Destination
0x180007eb7  call    memcpy_s
0x180007ebc  movzx   eax, word ptr [rdi]
0x180007ebf  lea     r14, [rdi+8]
0x180007ec3  mov     [r14], ax
0x180007ec7  test    ax, ax
0x180007eca  jnz     short loc_180007EE9
0x180007ecc  lea     r15, [rbx+2]
0x180007ed0  cmp     r15, rsi
0x180007ed3  ja      short loc_180007EF5
0x180007ed5  mov     r9, rbp; SourceSize
0x180007ed8  mov     r8, rbx; Source
0x180007edb  mov     rdx, rbp; DestinationSize
0x180007ede  mov     rcx, r14; Destination
0x180007ee1  call    memcpy_s
0x180007ee6  mov     rbx, r15
0x180007ee9  movzx   ecx, word ptr [r14]
0x180007eed  add     rcx, rbx
0x180007ef0  cmp     rcx, rsi
0x180007ef3  jbe     short loc_180007EF9
0x180007ef5  xor     al, al
0x180007ef7  jmp     short loc_180007F03
0x180007ef9  mov     [rdi+18h], rbx
0x180007efd  mov     al, 1
0x180007eff  mov     [r12], rcx
0x180007f03  mov     rbx, [rsp+48h+arg_8]
0x180007f08  mov     rbp, [rsp+48h+arg_10]
0x180007f0d  add     rsp, 20h
0x180007f11  pop     r15
0x180007f13  pop     r14
0x180007f15  pop     r12
0x180007f17  pop     rdi
0x180007f18  pop     rsi
0x180007f19  retn
```
