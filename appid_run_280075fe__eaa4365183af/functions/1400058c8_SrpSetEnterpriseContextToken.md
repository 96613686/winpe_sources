# SrpSetEnterpriseContextToken

- ea: `0x1400058c8`
- end: `0x14000598d`
- name: `SrpSetEnterpriseContextToken`
- size: `197`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140003c8c`
- `0x14002c338`
- `0x14002c524`

## callees

- `0x140004410`
- `0x140004838`
- `0x1400058c8`

## import_xrefs

- `ntoskrnl!SeSetSecurityAttributesTokenEx` at `0x140005960`
- `ntoskrnl!SeSetSecurityAttributesTokenEx` at `0x140005960`

## pseudocode

```c
__int64 __fastcall SrpSetEnterpriseContextToken(__int64 a1, __int64 a2, char a3, __int64 a4, __int64 a5, __int64 a6)
{
  int AttributesFromContext; // eax
  __int64 v9; // r9
  PVOID v10; // rdi
  unsigned int v11; // ebx
  PVOID P; // [rsp+68h] [rbp+10h] BYREF
  char v14; // [rsp+78h] [rbp+20h] BYREF

  P = 0;
  v14 = 0;
  if ( !a1 || !a5 || (*(_QWORD *)(a5 + 8) & 0xFFFFFFFFFFFFFF00uLL) != 0 )
    return 3221225485LL;
  AttributesFromContext = CreateAttributesFromContext(a5, 0, a3 == 0, a6, (__int64)&P);
  v10 = P;
  v11 = AttributesFromContext;
  if ( AttributesFromContext >= 0 )
  {
    LOBYTE(v9) = a3;
    v11 = SeSetSecurityAttributesTokenEx(a1, 0, 0, v9, SrpReplaceOperations, P, &v14);
  }
  DeleteAttributes(v10);
  return v11;
}

```

## disassembly

```asm
0x1400058c8  mov     rax, rsp
0x1400058cb  mov     [rax+8], rbx
0x1400058cf  mov     [rax+20h], r9b
0x1400058d3  mov     [rax+10h], rdx
0x1400058d7  push    rbp
0x1400058d8  push    rsi
0x1400058d9  push    rdi
0x1400058da  sub     rsp, 40h
0x1400058de  mov     qword ptr [rax+10h], 0
0x1400058e6  mov     bpl, r8b
0x1400058e9  mov     byte ptr [rax+20h], 0
0x1400058ed  mov     rsi, rcx
0x1400058f0  test    rcx, rcx
0x1400058f3  jz      loc_14000597A
0x1400058f9  mov     rcx, [rsp+58h+arg_20]
0x140005901  test    rcx, rcx
0x140005904  jz      short loc_14000597A
0x140005906  test    qword ptr [rcx+8], 0FFFFFFFFFFFFFF00h
0x14000590e  jnz     short loc_14000597A
0x140005910  mov     r9, [rsp+58h+arg_28]
0x140005918  lea     rax, [rax+10h]
0x14000591c  test    r8b, r8b
0x14000591f  mov     [rsp+58h+var_38], rax
0x140005924  setz    r8b
0x140005928  xor     edx, edx
0x14000592a  call    CreateAttributesFromContext
0x14000592f  mov     rdi, [rsp+58h+P]
0x140005934  mov     ebx, eax
0x140005936  test    eax, eax
0x140005938  js      short loc_14000596E
0x14000593a  lea     rax, [rsp+58h+arg_18]
0x14000593f  mov     r9b, bpl
0x140005942  mov     [rsp+58h+var_28], rax
0x140005947  xor     r8d, r8d
0x14000594a  lea     rax, SrpReplaceOperations
0x140005951  mov     [rsp+58h+var_30], rdi
0x140005956  xor     edx, edx
0x140005958  mov     [rsp+58h+var_38], rax
0x14000595d  mov     rcx, rsi
0x140005960  call    cs:__imp_SeSetSecurityAttributesTokenEx
0x140005967  nop     dword ptr [rax+rax+00h]
0x14000596c  mov     ebx, eax
0x14000596e  mov     rcx, rdi; P
0x140005971  call    DeleteAttributes
0x140005976  mov     eax, ebx
0x140005978  jmp     short loc_14000597F
0x14000597a  mov     eax, 0C000000Dh
0x14000597f  mov     rbx, [rsp+58h+arg_0]
0x140005984  add     rsp, 40h
0x140005988  pop     rdi
0x140005989  pop     rsi
0x14000598a  pop     rbp
0x14000598b  retn
```
