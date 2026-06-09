# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180012884`
- end: `0x18001296a`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000dd5c`
- `0x180010d94`
- `0x180011c24`
- `0x1800121f4`
- `0x1800134e0`

## callees

- `0x18000dbd8`
- `0x180012884`

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
0x180012884  mov     rax, rsp
0x180012887  mov     [rax+10h], rbx
0x18001288b  mov     [rax+18h], rbp
0x18001288f  push    rsi
0x180012890  push    rdi
0x180012891  push    r12
0x180012893  push    r14
0x180012895  push    r15
0x180012897  sub     rsp, 20h
0x18001289b  xor     r15d, r15d
0x18001289e  mov     rsi, r8
0x1800128a1  cmp     byte ptr [rcx+2], 1
0x1800128a5  mov     r12, rdx
0x1800128a8  mov     r8, [rdx]; Source
0x1800128ab  mov     rdi, rcx
0x1800128ae  jnz     short loc_1800128E2
0x1800128b0  lea     rbx, [r8+2]
0x1800128b4  cmp     rbx, rsi
0x1800128b7  ja      loc_180012945
0x1800128bd  lea     ebp, [r15+2]
0x1800128c1  mov     [rcx+10h], r8
0x1800128c5  mov     r9d, ebp; SourceSize
0x1800128c8  mov     [rax+8], r15w
0x1800128cd  mov     edx, ebp; DestinationSize
0x1800128cf  lea     rcx, [rax+8]; Destination
0x1800128d3  call    memcpy_s
0x1800128d8  movzx   eax, [rsp+48h+arg_0]
0x1800128dd  mov     [rdi+4], eax
0x1800128e0  jmp     short loc_18001290C
0x1800128e2  mov     ebp, 2
0x1800128e7  mov     rbx, r8
0x1800128ea  cmp     [rcx+2], bpl
0x1800128ee  jnz     short loc_18001290C
0x1800128f0  lea     rbx, [r8+4]
0x1800128f4  cmp     rbx, rsi
0x1800128f7  ja      short loc_180012945
0x1800128f9  lea     edx, [rbp+2]; DestinationSize
0x1800128fc  mov     [rcx+10h], r8
0x180012900  mov     r9d, edx; SourceSize
0x180012903  add     rcx, 4; Destination
0x180012907  call    memcpy_s
0x18001290c  movzx   eax, word ptr [rdi]
0x18001290f  lea     r14, [rdi+8]
0x180012913  mov     [r14], ax
0x180012917  test    ax, ax
0x18001291a  jnz     short loc_180012939
0x18001291c  lea     r15, [rbx+2]
0x180012920  cmp     r15, rsi
0x180012923  ja      short loc_180012945
0x180012925  mov     r9, rbp; SourceSize
0x180012928  mov     r8, rbx; Source
0x18001292b  mov     rdx, rbp; DestinationSize
0x18001292e  mov     rcx, r14; Destination
0x180012931  call    memcpy_s
0x180012936  mov     rbx, r15
0x180012939  movzx   ecx, word ptr [r14]
0x18001293d  add     rcx, rbx
0x180012940  cmp     rcx, rsi
0x180012943  jbe     short loc_180012949
0x180012945  xor     al, al
0x180012947  jmp     short loc_180012953
0x180012949  mov     [rdi+18h], rbx
0x18001294d  mov     al, 1
0x18001294f  mov     [r12], rcx
0x180012953  mov     rbx, [rsp+48h+arg_8]
0x180012958  mov     rbp, [rsp+48h+arg_10]
0x18001295d  add     rsp, 20h
0x180012961  pop     r15
0x180012963  pop     r14
0x180012965  pop     r12
0x180012967  pop     rdi
0x180012968  pop     rsi
0x180012969  retn
```
