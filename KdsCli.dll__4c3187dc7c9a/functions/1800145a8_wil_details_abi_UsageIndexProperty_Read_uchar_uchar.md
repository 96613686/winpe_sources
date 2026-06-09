# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800145a8`
- end: `0x18001468e`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180012e3c`
- `0x180014c04`
- `0x180014f88`

## callees

- `0x180001f4c`
- `0x1800145a8`

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
0x1800145a8  mov     rax, rsp
0x1800145ab  mov     [rax+10h], rbx
0x1800145af  mov     [rax+18h], rbp
0x1800145b3  push    rsi
0x1800145b4  push    rdi
0x1800145b5  push    r12
0x1800145b7  push    r14
0x1800145b9  push    r15
0x1800145bb  sub     rsp, 20h
0x1800145bf  xor     r15d, r15d
0x1800145c2  mov     rsi, r8
0x1800145c5  cmp     byte ptr [rcx+2], 1
0x1800145c9  mov     r12, rdx
0x1800145cc  mov     r8, [rdx]; Source
0x1800145cf  mov     rdi, rcx
0x1800145d2  jnz     short loc_180014606
0x1800145d4  lea     rbx, [r8+2]
0x1800145d8  cmp     rbx, rsi
0x1800145db  ja      loc_180014669
0x1800145e1  lea     ebp, [r15+2]
0x1800145e5  mov     [rcx+10h], r8
0x1800145e9  mov     r9d, ebp; SourceSize
0x1800145ec  mov     [rax+8], r15w
0x1800145f1  mov     edx, ebp; DestinationSize
0x1800145f3  lea     rcx, [rax+8]; Destination
0x1800145f7  call    memcpy_s
0x1800145fc  movzx   eax, [rsp+48h+arg_0]
0x180014601  mov     [rdi+4], eax
0x180014604  jmp     short loc_180014630
0x180014606  mov     ebp, 2
0x18001460b  mov     rbx, r8
0x18001460e  cmp     [rcx+2], bpl
0x180014612  jnz     short loc_180014630
0x180014614  lea     rbx, [r8+4]
0x180014618  cmp     rbx, rsi
0x18001461b  ja      short loc_180014669
0x18001461d  lea     edx, [rbp+2]; DestinationSize
0x180014620  mov     [rcx+10h], r8
0x180014624  mov     r9d, edx; SourceSize
0x180014627  add     rcx, 4; Destination
0x18001462b  call    memcpy_s
0x180014630  movzx   eax, word ptr [rdi]
0x180014633  lea     r14, [rdi+8]
0x180014637  mov     [r14], ax
0x18001463b  test    ax, ax
0x18001463e  jnz     short loc_18001465D
0x180014640  lea     r15, [rbx+2]
0x180014644  cmp     r15, rsi
0x180014647  ja      short loc_180014669
0x180014649  mov     r9, rbp; SourceSize
0x18001464c  mov     r8, rbx; Source
0x18001464f  mov     rdx, rbp; DestinationSize
0x180014652  mov     rcx, r14; Destination
0x180014655  call    memcpy_s
0x18001465a  mov     rbx, r15
0x18001465d  movzx   ecx, word ptr [r14]
0x180014661  add     rcx, rbx
0x180014664  cmp     rcx, rsi
0x180014667  jbe     short loc_18001466D
0x180014669  xor     al, al
0x18001466b  jmp     short loc_180014677
0x18001466d  mov     [rdi+18h], rbx
0x180014671  mov     al, 1
0x180014673  mov     [r12], rcx
0x180014677  mov     rbx, [rsp+48h+arg_8]
0x18001467c  mov     rbp, [rsp+48h+arg_10]
0x180014681  add     rsp, 20h
0x180014685  pop     r15
0x180014687  pop     r14
0x180014689  pop     r12
0x18001468b  pop     rdi
0x18001468c  pop     rsi
0x18001468d  retn
```
