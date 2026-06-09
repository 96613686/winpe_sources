# EdppIsAppxLineOfBusiness

- ea: `0x14002bd3c`
- end: `0x14002bde7`
- name: `EdppIsAppxLineOfBusiness`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140003ec0`

## callees

- `0x14002bd3c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14002bdb3`
- `ntoskrnl!ObfDereferenceObject` at `0x14002bdb3`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14002bd5e`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14002bd5e`
- `ntoskrnl!RtlQueryPackageClaims` at `0x14002bda2`
- `ntoskrnl!RtlQueryPackageClaims` at `0x14002bda2`

## pseudocode

```c
__int64 __fastcall EdppIsAppxLineOfBusiness(__int64 a1, bool *a2)
{
  struct _KPROCESS *v2; // rcx
  PACCESS_TOKEN v4; // rsi
  int v5; // ebx
  __int64 v7; // [rsp+50h] [rbp+8h] BYREF

  v2 = *(struct _KPROCESS **)(a1 + 8);
  v7 = 0;
  *a2 = 0;
  v4 = PsReferencePrimaryToken(v2);
  if ( !v4 )
    return 3221225485LL;
  v5 = RtlQueryPackageClaims(v4, 0, 0, 0, 0, 0, &v7, 0);
  ObfDereferenceObject(v4);
  if ( v5 >= 0 )
    *a2 = BYTE4(v7) == 6;
  return 0;
}

```

## disassembly

```asm
0x14002bd3c  mov     [rsp+arg_8], rbx
0x14002bd41  mov     [rsp+arg_10], rsi
0x14002bd46  push    rdi
0x14002bd47  sub     rsp, 40h
0x14002bd4b  mov     rcx, [rcx+8]; Process
0x14002bd4f  mov     rdi, rdx
0x14002bd52  mov     [rsp+48h+arg_0], 0
0x14002bd5b  mov     byte ptr [rdx], 0
0x14002bd5e  call    cs:__imp_PsReferencePrimaryToken
0x14002bd65  nop     dword ptr [rax+rax+00h]
0x14002bd6a  mov     rsi, rax
0x14002bd6d  test    rax, rax
0x14002bd70  jz      short loc_14002BDD1
0x14002bd72  mov     [rsp+48h+var_10], 0
0x14002bd7b  lea     rax, [rsp+48h+arg_0]
0x14002bd80  mov     [rsp+48h+var_18], rax
0x14002bd85  xor     r9d, r9d
0x14002bd88  mov     [rsp+48h+var_20], 0
0x14002bd91  xor     r8d, r8d
0x14002bd94  xor     edx, edx
0x14002bd96  mov     [rsp+48h+var_28], 0
0x14002bd9f  mov     rcx, rsi
0x14002bda2  call    cs:__imp_RtlQueryPackageClaims
0x14002bda9  nop     dword ptr [rax+rax+00h]
0x14002bdae  mov     rcx, rsi; Object
0x14002bdb1  mov     ebx, eax
0x14002bdb3  call    cs:__imp_ObfDereferenceObject
0x14002bdba  nop     dword ptr [rax+rax+00h]
0x14002bdbf  test    ebx, ebx
0x14002bdc1  js      short loc_14002BDCD
0x14002bdc3  cmp     byte ptr [rsp+48h+arg_0+4], 6
0x14002bdc8  setz    al
0x14002bdcb  mov     [rdi], al
0x14002bdcd  xor     eax, eax
0x14002bdcf  jmp     short loc_14002BDD6
0x14002bdd1  mov     eax, 0C000000Dh
0x14002bdd6  mov     rbx, [rsp+48h+arg_8]
0x14002bddb  mov     rsi, [rsp+48h+arg_10]
0x14002bde0  add     rsp, 40h
0x14002bde4  pop     rdi
0x14002bde5  retn
```
