# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180013678`
- end: `0x18001375e`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180012604`
- `0x180012e58`
- `0x180013178`
- `0x180013bb0`
- `0x180014224`

## callees

- `0x180005920`
- `0x180013678`

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
0x180013678  mov     rax, rsp
0x18001367b  mov     [rax+10h], rbx
0x18001367f  mov     [rax+18h], rbp
0x180013683  push    rsi
0x180013684  push    rdi
0x180013685  push    r12
0x180013687  push    r14
0x180013689  push    r15
0x18001368b  sub     rsp, 20h
0x18001368f  xor     r15d, r15d
0x180013692  mov     rsi, r8
0x180013695  cmp     byte ptr [rcx+2], 1
0x180013699  mov     r12, rdx
0x18001369c  mov     r8, [rdx]; Source
0x18001369f  mov     rdi, rcx
0x1800136a2  jnz     short loc_1800136D6
0x1800136a4  lea     rbx, [r8+2]
0x1800136a8  cmp     rbx, rsi
0x1800136ab  ja      loc_180013739
0x1800136b1  lea     ebp, [r15+2]
0x1800136b5  mov     [rcx+10h], r8
0x1800136b9  mov     r9d, ebp; SourceSize
0x1800136bc  mov     [rax+8], r15w
0x1800136c1  mov     edx, ebp; DestinationSize
0x1800136c3  lea     rcx, [rax+8]; Destination
0x1800136c7  call    memcpy_s
0x1800136cc  movzx   eax, [rsp+48h+arg_0]
0x1800136d1  mov     [rdi+4], eax
0x1800136d4  jmp     short loc_180013700
0x1800136d6  mov     ebp, 2
0x1800136db  mov     rbx, r8
0x1800136de  cmp     [rcx+2], bpl
0x1800136e2  jnz     short loc_180013700
0x1800136e4  lea     rbx, [r8+4]
0x1800136e8  cmp     rbx, rsi
0x1800136eb  ja      short loc_180013739
0x1800136ed  lea     edx, [rbp+2]; DestinationSize
0x1800136f0  mov     [rcx+10h], r8
0x1800136f4  mov     r9d, edx; SourceSize
0x1800136f7  add     rcx, 4; Destination
0x1800136fb  call    memcpy_s
0x180013700  movzx   eax, word ptr [rdi]
0x180013703  lea     r14, [rdi+8]
0x180013707  mov     [r14], ax
0x18001370b  test    ax, ax
0x18001370e  jnz     short loc_18001372D
0x180013710  lea     r15, [rbx+2]
0x180013714  cmp     r15, rsi
0x180013717  ja      short loc_180013739
0x180013719  mov     r9, rbp; SourceSize
0x18001371c  mov     r8, rbx; Source
0x18001371f  mov     rdx, rbp; DestinationSize
0x180013722  mov     rcx, r14; Destination
0x180013725  call    memcpy_s
0x18001372a  mov     rbx, r15
0x18001372d  movzx   ecx, word ptr [r14]
0x180013731  add     rcx, rbx
0x180013734  cmp     rcx, rsi
0x180013737  jbe     short loc_18001373D
0x180013739  xor     al, al
0x18001373b  jmp     short loc_180013747
0x18001373d  mov     [rdi+18h], rbx
0x180013741  mov     al, 1
0x180013743  mov     [r12], rcx
0x180013747  mov     rbx, [rsp+48h+arg_8]
0x18001374c  mov     rbp, [rsp+48h+arg_10]
0x180013751  add     rsp, 20h
0x180013755  pop     r15
0x180013757  pop     r14
0x180013759  pop     r12
0x18001375b  pop     rdi
0x18001375c  pop     rsi
0x18001375d  retn
```
