# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x14000cd78`
- end: `0x14000ce5f`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `231`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b918`
- `0x14000bfac`
- `0x14000c0dc`
- `0x14000d290`
- `0x1400109fc`

## callees

- `0x140008200`
- `0x14000cd78`

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
0x14000cd78  mov     rax, rsp
0x14000cd7b  mov     [rax+10h], rbx
0x14000cd7f  mov     [rax+18h], rbp
0x14000cd83  push    rsi
0x14000cd84  push    rdi
0x14000cd85  push    r12
0x14000cd87  push    r14
0x14000cd89  push    r15
0x14000cd8b  sub     rsp, 20h
0x14000cd8f  xor     r15d, r15d
0x14000cd92  mov     rsi, r8
0x14000cd95  cmp     byte ptr [rcx+2], 1
0x14000cd99  mov     r12, rdx
0x14000cd9c  mov     r8, [rdx]; Source
0x14000cd9f  mov     rdi, rcx
0x14000cda2  jnz     short loc_14000CDD6
0x14000cda4  lea     rbx, [r8+2]
0x14000cda8  cmp     rbx, rsi
0x14000cdab  ja      loc_14000CE39
0x14000cdb1  lea     ebp, [r15+2]
0x14000cdb5  mov     [rcx+10h], r8
0x14000cdb9  mov     r9d, ebp; SourceSize
0x14000cdbc  mov     [rax+8], r15w
0x14000cdc1  mov     edx, ebp; DestinationSize
0x14000cdc3  lea     rcx, [rax+8]; Destination
0x14000cdc7  call    memcpy_s
0x14000cdcc  movzx   eax, [rsp+48h+arg_0]
0x14000cdd1  mov     [rdi+4], eax
0x14000cdd4  jmp     short loc_14000CE00
0x14000cdd6  mov     ebp, 2
0x14000cddb  mov     rbx, r8
0x14000cdde  cmp     [rcx+2], bpl
0x14000cde2  jnz     short loc_14000CE00
0x14000cde4  lea     rbx, [r8+4]
0x14000cde8  cmp     rbx, rsi
0x14000cdeb  ja      short loc_14000CE39
0x14000cded  lea     edx, [rbp+2]; DestinationSize
0x14000cdf0  mov     [rcx+10h], r8
0x14000cdf4  mov     r9d, edx; SourceSize
0x14000cdf7  add     rcx, 4; Destination
0x14000cdfb  call    memcpy_s
0x14000ce00  movzx   eax, word ptr [rdi]
0x14000ce03  lea     r14, [rdi+8]
0x14000ce07  mov     [r14], ax
0x14000ce0b  test    ax, ax
0x14000ce0e  jnz     short loc_14000CE2D
0x14000ce10  lea     r15, [rbx+2]
0x14000ce14  cmp     r15, rsi
0x14000ce17  ja      short loc_14000CE39
0x14000ce19  mov     r9, rbp; SourceSize
0x14000ce1c  mov     r8, rbx; Source
0x14000ce1f  mov     rdx, rbp; DestinationSize
0x14000ce22  mov     rcx, r14; Destination
0x14000ce25  call    memcpy_s
0x14000ce2a  mov     rbx, r15
0x14000ce2d  movzx   ecx, word ptr [r14]
0x14000ce31  add     rcx, rbx
0x14000ce34  cmp     rcx, rsi
0x14000ce37  jbe     short loc_14000CE3D
0x14000ce39  xor     al, al
0x14000ce3b  jmp     short loc_14000CE47
0x14000ce3d  mov     [rdi+18h], rbx
0x14000ce41  mov     al, 1
0x14000ce43  mov     [r12], rcx
0x14000ce47  mov     rbx, [rsp+48h+arg_8]
0x14000ce4c  mov     rbp, [rsp+48h+arg_10]
0x14000ce51  add     rsp, 20h
0x14000ce55  pop     r15
0x14000ce57  pop     r14
0x14000ce59  pop     r12
0x14000ce5b  pop     rdi
0x14000ce5c  pop     rsi
0x14000ce5d  retn
```
