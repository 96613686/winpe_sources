# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800265d8`
- end: `0x1800266d1`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `249`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180024620`
- `0x180025978`
- `0x180025e1c`
- `0x180026bc4`
- `0x180027900`

## callees

- `0x1800265d8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180026628`
- `msvcrt!memcpy_s` at `0x180026660`
- `msvcrt!memcpy_s` at `0x180026691`
- `msvcrt!memcpy_s` at `0x180026628`
- `msvcrt!memcpy_s` at `0x180026660`
- `msvcrt!memcpy_s` at `0x180026691`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char *v5; // r8
  char *v7; // rbp
  __int16 v8; // ax
  char *v9; // rbp
  unsigned __int8 *v10; // rcx
  bool result; // al
  unsigned __int16 v12; // [rsp+50h] [rbp+8h] BYREF

  v5 = (char *)*a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v5 + 2;
    if ( v5 + 2 > (char *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v5;
    v12 = 0;
    memcpy_s(&v12, 2u, v5, 2u);
    *((_DWORD *)this + 1) = v12;
  }
  else
  {
    if ( *((_BYTE *)this + 2) != 2 )
      goto LABEL_8;
    v7 = v5 + 4;
    if ( v5 + 4 > (char *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v5;
    memcpy_s((char *)this + 4, 4u, v5, 4u);
  }
  v5 = v7;
LABEL_8:
  v8 = *(_WORD *)this;
  *((_WORD *)this + 4) = *(_WORD *)this;
  if ( v8 )
    goto LABEL_11;
  v9 = v5 + 2;
  if ( v5 + 2 > (char *)a3 )
    return 0;
  memcpy_s((char *)this + 8, 2u, v5, 2u);
  v5 = v9;
LABEL_11:
  v10 = (unsigned __int8 *)&v5[*((unsigned __int16 *)this + 4)];
  if ( v10 > a3 )
    return 0;
  *((_QWORD *)this + 3) = v5;
  result = 1;
  *a2 = v10;
  return result;
}

```

## disassembly

```asm
0x1800265d8  mov     rax, rsp
0x1800265db  mov     [rax+10h], rbx
0x1800265df  mov     [rax+18h], rbp
0x1800265e3  push    rsi
0x1800265e4  push    rdi
0x1800265e5  push    r12
0x1800265e7  push    r14
0x1800265e9  push    r15
0x1800265eb  sub     rsp, 20h
0x1800265ef  xor     r12d, r12d
0x1800265f2  mov     rdi, r8
0x1800265f5  cmp     byte ptr [rcx+2], 1
0x1800265f9  mov     r15, rdx
0x1800265fc  mov     r8, [rdx]; Source
0x1800265ff  mov     rbx, rcx
0x180026602  jnz     short loc_18002663E
0x180026604  lea     rbp, [r8+2]
0x180026608  cmp     rbp, rdi
0x18002660b  ja      loc_1800266AC
0x180026611  lea     esi, [r12+2]
0x180026616  mov     [rcx+10h], r8
0x18002661a  mov     r9d, esi; SourceSize
0x18002661d  mov     [rax+8], r12w
0x180026622  mov     edx, esi; DestinationSize
0x180026624  lea     rcx, [rax+8]; Destination
0x180026628  call    cs:__imp_memcpy_s
0x18002662f  nop     dword ptr [rax+rax+00h]
0x180026634  movzx   eax, [rsp+48h+arg_0]
0x180026639  mov     [rbx+4], eax
0x18002663c  jmp     short loc_18002666C
0x18002663e  mov     esi, 2
0x180026643  cmp     [rcx+2], sil
0x180026647  jnz     short loc_18002666F
0x180026649  lea     rbp, [r8+4]
0x18002664d  cmp     rbp, rdi
0x180026650  ja      short loc_1800266AC
0x180026652  lea     edx, [rsi+2]; DestinationSize
0x180026655  mov     [rcx+10h], r8
0x180026659  mov     r9d, edx; SourceSize
0x18002665c  add     rcx, 4; Destination
0x180026660  call    cs:__imp_memcpy_s
0x180026667  nop     dword ptr [rax+rax+00h]
0x18002666c  mov     r8, rbp; Source
0x18002666f  movzx   eax, word ptr [rbx]
0x180026672  lea     r14, [rbx+8]
0x180026676  mov     [r14], ax
0x18002667a  test    ax, ax
0x18002667d  jnz     short loc_1800266A0
0x18002667f  lea     rbp, [r8+2]
0x180026683  cmp     rbp, rdi
0x180026686  ja      short loc_1800266AC
0x180026688  mov     r9, rsi; SourceSize
0x18002668b  mov     rdx, rsi; DestinationSize
0x18002668e  mov     rcx, r14; Destination
0x180026691  call    cs:__imp_memcpy_s
0x180026698  nop     dword ptr [rax+rax+00h]
0x18002669d  mov     r8, rbp
0x1800266a0  movzx   ecx, word ptr [r14]
0x1800266a4  add     rcx, r8
0x1800266a7  cmp     rcx, rdi
0x1800266aa  jbe     short loc_1800266B0
0x1800266ac  xor     al, al
0x1800266ae  jmp     short loc_1800266B9
0x1800266b0  mov     [rbx+18h], r8
0x1800266b4  mov     al, 1
0x1800266b6  mov     [r15], rcx
0x1800266b9  mov     rbx, [rsp+48h+arg_8]
0x1800266be  mov     rbp, [rsp+48h+arg_10]
0x1800266c3  add     rsp, 20h
0x1800266c7  pop     r15
0x1800266c9  pop     r14
0x1800266cb  pop     r12
0x1800266cd  pop     rdi
0x1800266ce  pop     rsi
0x1800266cf  retn
```
