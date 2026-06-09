# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800135cc`
- end: `0x1800136b5`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180011c5c`
- `0x180013c08`
- `0x180013f90`

## callees

- `0x1800135cc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001361b`
- `msvcrt!memcpy_s` at `0x180013650`
- `msvcrt!memcpy_s` at `0x18001367b`
- `msvcrt!memcpy_s` at `0x18001361b`
- `msvcrt!memcpy_s` at `0x180013650`
- `msvcrt!memcpy_s` at `0x18001367b`

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
0x1800135cc  mov     rax, rsp
0x1800135cf  mov     [rax+10h], rbx
0x1800135d3  mov     [rax+18h], rbp
0x1800135d7  push    rsi
0x1800135d8  push    rdi
0x1800135d9  push    r12
0x1800135db  push    r14
0x1800135dd  push    r15
0x1800135df  sub     rsp, 20h
0x1800135e3  xor     r15d, r15d
0x1800135e6  mov     rsi, r8
0x1800135e9  cmp     byte ptr [rcx+2], 1
0x1800135ed  mov     r12, rdx
0x1800135f0  mov     r8, [rdx]; Source
0x1800135f3  mov     rdi, rcx
0x1800135f6  jnz     short loc_18001362B
0x1800135f8  lea     rbx, [r8+2]
0x1800135fc  cmp     rbx, rsi
0x1800135ff  ja      loc_180013690
0x180013605  lea     ebp, [r15+2]
0x180013609  mov     [rcx+10h], r8
0x18001360d  mov     r9d, ebp; SourceSize
0x180013610  mov     [rax+8], r15w
0x180013615  mov     edx, ebp; DestinationSize
0x180013617  lea     rcx, [rax+8]; Destination
0x18001361b  call    cs:__imp_memcpy_s
0x180013621  movzx   eax, [rsp+48h+arg_0]
0x180013626  mov     [rdi+4], eax
0x180013629  jmp     short loc_180013656
0x18001362b  mov     ebp, 2
0x180013630  mov     rbx, r8
0x180013633  cmp     [rcx+2], bpl
0x180013637  jnz     short loc_180013656
0x180013639  lea     rbx, [r8+4]
0x18001363d  cmp     rbx, rsi
0x180013640  ja      short loc_180013690
0x180013642  lea     edx, [rbp+2]; DestinationSize
0x180013645  mov     [rcx+10h], r8
0x180013649  mov     r9d, edx; SourceSize
0x18001364c  add     rcx, 4; Destination
0x180013650  call    cs:__imp_memcpy_s
0x180013656  movzx   eax, word ptr [rdi]
0x180013659  lea     r14, [rdi+8]
0x18001365d  mov     [r14], ax
0x180013661  test    ax, ax
0x180013664  jnz     short loc_180013684
0x180013666  lea     r15, [rbx+2]
0x18001366a  cmp     r15, rsi
0x18001366d  ja      short loc_180013690
0x18001366f  mov     r9, rbp; SourceSize
0x180013672  mov     r8, rbx; Source
0x180013675  mov     rdx, rbp; DestinationSize
0x180013678  mov     rcx, r14; Destination
0x18001367b  call    cs:__imp_memcpy_s
0x180013681  mov     rbx, r15
0x180013684  movzx   ecx, word ptr [r14]
0x180013688  add     rcx, rbx
0x18001368b  cmp     rcx, rsi
0x18001368e  jbe     short loc_180013694
0x180013690  xor     al, al
0x180013692  jmp     short loc_18001369E
0x180013694  mov     [rdi+18h], rbx
0x180013698  mov     al, 1
0x18001369a  mov     [r12], rcx
0x18001369e  mov     rbx, [rsp+48h+arg_8]
0x1800136a3  mov     rbp, [rsp+48h+arg_10]
0x1800136a8  add     rsp, 20h
0x1800136ac  pop     r15
0x1800136ae  pop     r14
0x1800136b0  pop     r12
0x1800136b2  pop     rdi
0x1800136b3  pop     rsi
0x1800136b4  retn
```
