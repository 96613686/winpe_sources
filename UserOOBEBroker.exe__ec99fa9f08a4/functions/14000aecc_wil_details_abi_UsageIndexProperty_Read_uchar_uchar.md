# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x14000aecc`
- end: `0x14000afb5`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140009dec`
- `0x14000b688`
- `0x14000ba10`

## callees

- `0x14000aecc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000af1b`
- `msvcrt!memcpy_s` at `0x14000af50`
- `msvcrt!memcpy_s` at `0x14000af7b`
- `msvcrt!memcpy_s` at `0x14000af1b`
- `msvcrt!memcpy_s` at `0x14000af50`
- `msvcrt!memcpy_s` at `0x14000af7b`

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
0x14000aecc  mov     rax, rsp
0x14000aecf  mov     [rax+10h], rbx
0x14000aed3  mov     [rax+18h], rbp
0x14000aed7  push    rsi
0x14000aed8  push    rdi
0x14000aed9  push    r12
0x14000aedb  push    r14
0x14000aedd  push    r15
0x14000aedf  sub     rsp, 20h
0x14000aee3  xor     r15d, r15d
0x14000aee6  mov     rsi, r8
0x14000aee9  cmp     byte ptr [rcx+2], 1
0x14000aeed  mov     r12, rdx
0x14000aef0  mov     r8, [rdx]; Source
0x14000aef3  mov     rdi, rcx
0x14000aef6  jnz     short loc_14000AF2B
0x14000aef8  lea     rbx, [r8+2]
0x14000aefc  cmp     rbx, rsi
0x14000aeff  ja      loc_14000AF90
0x14000af05  lea     ebp, [r15+2]
0x14000af09  mov     [rcx+10h], r8
0x14000af0d  mov     r9d, ebp; SourceSize
0x14000af10  mov     [rax+8], r15w
0x14000af15  mov     edx, ebp; DestinationSize
0x14000af17  lea     rcx, [rax+8]; Destination
0x14000af1b  call    cs:__imp_memcpy_s
0x14000af21  movzx   eax, [rsp+48h+arg_0]
0x14000af26  mov     [rdi+4], eax
0x14000af29  jmp     short loc_14000AF56
0x14000af2b  mov     ebp, 2
0x14000af30  mov     rbx, r8
0x14000af33  cmp     [rcx+2], bpl
0x14000af37  jnz     short loc_14000AF56
0x14000af39  lea     rbx, [r8+4]
0x14000af3d  cmp     rbx, rsi
0x14000af40  ja      short loc_14000AF90
0x14000af42  lea     edx, [rbp+2]; DestinationSize
0x14000af45  mov     [rcx+10h], r8
0x14000af49  mov     r9d, edx; SourceSize
0x14000af4c  add     rcx, 4; Destination
0x14000af50  call    cs:__imp_memcpy_s
0x14000af56  movzx   eax, word ptr [rdi]
0x14000af59  lea     r14, [rdi+8]
0x14000af5d  mov     [r14], ax
0x14000af61  test    ax, ax
0x14000af64  jnz     short loc_14000AF84
0x14000af66  lea     r15, [rbx+2]
0x14000af6a  cmp     r15, rsi
0x14000af6d  ja      short loc_14000AF90
0x14000af6f  mov     r9, rbp; SourceSize
0x14000af72  mov     r8, rbx; Source
0x14000af75  mov     rdx, rbp; DestinationSize
0x14000af78  mov     rcx, r14; Destination
0x14000af7b  call    cs:__imp_memcpy_s
0x14000af81  mov     rbx, r15
0x14000af84  movzx   ecx, word ptr [r14]
0x14000af88  add     rcx, rbx
0x14000af8b  cmp     rcx, rsi
0x14000af8e  jbe     short loc_14000AF94
0x14000af90  xor     al, al
0x14000af92  jmp     short loc_14000AF9E
0x14000af94  mov     [rdi+18h], rbx
0x14000af98  mov     al, 1
0x14000af9a  mov     [r12], rcx
0x14000af9e  mov     rbx, [rsp+48h+arg_8]
0x14000afa3  mov     rbp, [rsp+48h+arg_10]
0x14000afa8  add     rsp, 20h
0x14000afac  pop     r15
0x14000afae  pop     r14
0x14000afb0  pop     r12
0x14000afb2  pop     rdi
0x14000afb3  pop     rsi
0x14000afb4  retn
```
