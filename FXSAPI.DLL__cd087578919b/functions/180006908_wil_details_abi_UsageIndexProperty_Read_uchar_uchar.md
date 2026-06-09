# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180006908`
- end: `0x180006a04`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `252`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004d5c`
- `0x180006fb0`
- `0x180007350`

## callees

- `0x180006908`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180006957`
- `msvcrt!memcpy_s` at `0x180006992`
- `msvcrt!memcpy_s` at `0x1800069c3`
- `msvcrt!memcpy_s` at `0x180006957`
- `msvcrt!memcpy_s` at `0x180006992`
- `msvcrt!memcpy_s` at `0x1800069c3`

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
0x180006908  mov     rax, rsp
0x18000690b  mov     [rax+10h], rbx
0x18000690f  mov     [rax+18h], rbp
0x180006913  push    rsi
0x180006914  push    rdi
0x180006915  push    r12
0x180006917  push    r14
0x180006919  push    r15
0x18000691b  sub     rsp, 20h
0x18000691f  xor     r15d, r15d
0x180006922  mov     rsi, r8
0x180006925  cmp     byte ptr [rcx+2], 1
0x180006929  mov     r12, rdx
0x18000692c  mov     r8, [rdx]; Source
0x18000692f  mov     rdi, rcx
0x180006932  jnz     short loc_18000696D
0x180006934  lea     rbx, [r8+2]
0x180006938  cmp     rbx, rsi
0x18000693b  ja      loc_1800069DE
0x180006941  lea     ebp, [r15+2]
0x180006945  mov     [rcx+10h], r8
0x180006949  mov     r9d, ebp; SourceSize
0x18000694c  mov     [rax+8], r15w
0x180006951  mov     edx, ebp; DestinationSize
0x180006953  lea     rcx, [rax+8]; Destination
0x180006957  call    cs:__imp_memcpy_s
0x18000695e  nop     dword ptr [rax+rax+00h]
0x180006963  movzx   eax, [rsp+48h+arg_0]
0x180006968  mov     [rdi+4], eax
0x18000696b  jmp     short loc_18000699E
0x18000696d  mov     ebp, 2
0x180006972  mov     rbx, r8
0x180006975  cmp     [rcx+2], bpl
0x180006979  jnz     short loc_18000699E
0x18000697b  lea     rbx, [r8+4]
0x18000697f  cmp     rbx, rsi
0x180006982  ja      short loc_1800069DE
0x180006984  lea     edx, [rbp+2]; DestinationSize
0x180006987  mov     [rcx+10h], r8
0x18000698b  mov     r9d, edx; SourceSize
0x18000698e  add     rcx, 4; Destination
0x180006992  call    cs:__imp_memcpy_s
0x180006999  nop     dword ptr [rax+rax+00h]
0x18000699e  movzx   eax, word ptr [rdi]
0x1800069a1  lea     r14, [rdi+8]
0x1800069a5  mov     [r14], ax
0x1800069a9  test    ax, ax
0x1800069ac  jnz     short loc_1800069D2
0x1800069ae  lea     r15, [rbx+2]
0x1800069b2  cmp     r15, rsi
0x1800069b5  ja      short loc_1800069DE
0x1800069b7  mov     r9, rbp; SourceSize
0x1800069ba  mov     r8, rbx; Source
0x1800069bd  mov     rdx, rbp; DestinationSize
0x1800069c0  mov     rcx, r14; Destination
0x1800069c3  call    cs:__imp_memcpy_s
0x1800069ca  nop     dword ptr [rax+rax+00h]
0x1800069cf  mov     rbx, r15
0x1800069d2  movzx   ecx, word ptr [r14]
0x1800069d6  add     rcx, rbx
0x1800069d9  cmp     rcx, rsi
0x1800069dc  jbe     short loc_1800069E2
0x1800069de  xor     al, al
0x1800069e0  jmp     short loc_1800069EC
0x1800069e2  mov     [rdi+18h], rbx
0x1800069e6  mov     al, 1
0x1800069e8  mov     [r12], rcx
0x1800069ec  mov     rbx, [rsp+48h+arg_8]
0x1800069f1  mov     rbp, [rsp+48h+arg_10]
0x1800069f6  add     rsp, 20h
0x1800069fa  pop     r15
0x1800069fc  pop     r14
0x1800069fe  pop     r12
0x180006a00  pop     rdi
0x180006a01  pop     rsi
0x180006a02  retn
```
