# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180006028`
- end: `0x180006111`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800046ac`
- `0x180006844`
- `0x180006bcc`

## callees

- `0x180006028`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180006077`
- `msvcrt!memcpy_s` at `0x1800060ac`
- `msvcrt!memcpy_s` at `0x1800060d7`
- `msvcrt!memcpy_s` at `0x180006077`
- `msvcrt!memcpy_s` at `0x1800060ac`
- `msvcrt!memcpy_s` at `0x1800060d7`

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
0x180006028  mov     rax, rsp
0x18000602b  mov     [rax+10h], rbx
0x18000602f  mov     [rax+18h], rbp
0x180006033  push    rsi
0x180006034  push    rdi
0x180006035  push    r12
0x180006037  push    r14
0x180006039  push    r15
0x18000603b  sub     rsp, 20h
0x18000603f  xor     r15d, r15d
0x180006042  mov     rsi, r8
0x180006045  cmp     byte ptr [rcx+2], 1
0x180006049  mov     r12, rdx
0x18000604c  mov     r8, [rdx]; Source
0x18000604f  mov     rdi, rcx
0x180006052  jnz     short loc_180006087
0x180006054  lea     rbx, [r8+2]
0x180006058  cmp     rbx, rsi
0x18000605b  ja      loc_1800060EC
0x180006061  lea     ebp, [r15+2]
0x180006065  mov     [rcx+10h], r8
0x180006069  mov     r9d, ebp; SourceSize
0x18000606c  mov     [rax+8], r15w
0x180006071  mov     edx, ebp; DestinationSize
0x180006073  lea     rcx, [rax+8]; Destination
0x180006077  call    cs:__imp_memcpy_s
0x18000607d  movzx   eax, [rsp+48h+arg_0]
0x180006082  mov     [rdi+4], eax
0x180006085  jmp     short loc_1800060B2
0x180006087  mov     ebp, 2
0x18000608c  mov     rbx, r8
0x18000608f  cmp     [rcx+2], bpl
0x180006093  jnz     short loc_1800060B2
0x180006095  lea     rbx, [r8+4]
0x180006099  cmp     rbx, rsi
0x18000609c  ja      short loc_1800060EC
0x18000609e  lea     edx, [rbp+2]; DestinationSize
0x1800060a1  mov     [rcx+10h], r8
0x1800060a5  mov     r9d, edx; SourceSize
0x1800060a8  add     rcx, 4; Destination
0x1800060ac  call    cs:__imp_memcpy_s
0x1800060b2  movzx   eax, word ptr [rdi]
0x1800060b5  lea     r14, [rdi+8]
0x1800060b9  mov     [r14], ax
0x1800060bd  test    ax, ax
0x1800060c0  jnz     short loc_1800060E0
0x1800060c2  lea     r15, [rbx+2]
0x1800060c6  cmp     r15, rsi
0x1800060c9  ja      short loc_1800060EC
0x1800060cb  mov     r9, rbp; SourceSize
0x1800060ce  mov     r8, rbx; Source
0x1800060d1  mov     rdx, rbp; DestinationSize
0x1800060d4  mov     rcx, r14; Destination
0x1800060d7  call    cs:__imp_memcpy_s
0x1800060dd  mov     rbx, r15
0x1800060e0  movzx   ecx, word ptr [r14]
0x1800060e4  add     rcx, rbx
0x1800060e7  cmp     rcx, rsi
0x1800060ea  jbe     short loc_1800060F0
0x1800060ec  xor     al, al
0x1800060ee  jmp     short loc_1800060FA
0x1800060f0  mov     [rdi+18h], rbx
0x1800060f4  mov     al, 1
0x1800060f6  mov     [r12], rcx
0x1800060fa  mov     rbx, [rsp+48h+arg_8]
0x1800060ff  mov     rbp, [rsp+48h+arg_10]
0x180006104  add     rsp, 20h
0x180006108  pop     r15
0x18000610a  pop     r14
0x18000610c  pop     r12
0x18000610e  pop     rdi
0x18000610f  pop     rsi
0x180006110  retn
```
