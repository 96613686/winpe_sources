# BfFreeMappingLookupList

- ea: `0x140014a70`
- end: `0x140014b1a`
- name: `BfFreeMappingLookupList`
- size: `170`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140013864`
- `0x140014324`
- `0x140017920`

## callees

- `0x140014a70`
- `0x14001e998`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140014ab7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014af4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014ab7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014af4`

## pseudocode

```c
void __fastcall BfFreeMappingLookupList(_QWORD *a1)
{
  void *v2; // rbx
  void **v3; // rax
  void *v4; // rcx
  volatile signed __int64 *v5; // rcx
  signed __int64 v6; // rax
  bool v7; // cc
  signed __int64 v8; // rax

  while ( (_QWORD *)*a1 != a1 )
  {
    v2 = (void *)a1[1];
    if ( *(_QWORD **)v2 != a1 || (v3 = (void **)*((_QWORD *)v2 + 1), *v3 != v2) )
      __fastfail(3u);
    a1[1] = v3;
    *v3 = a1;
    v4 = (void *)*((_QWORD *)v2 + 3);
    if ( v4 )
    {
      ExFreePoolWithTag(v4, 0x74734642u);
      *((_QWORD *)v2 + 3) = 0;
    }
    *((_DWORD *)v2 + 4) = 0;
    v5 = (volatile signed __int64 *)*((_QWORD *)v2 + 4);
    v6 = _InterlockedExchangeAdd64(v5, 0xFFFFFFFFFFFFFFFFuLL);
    v7 = v6 <= 1;
    v8 = v6 - 1;
    if ( v7 )
    {
      if ( v8 )
        __fastfail(0xEu);
      BfpDeleteMappingInformation((char *)v5);
    }
    ExFreePoolWithTag(v2, 0x706D4642u);
  }
}

```

## disassembly

```asm
0x140014a70  mov     [rsp+arg_8], rsi
0x140014a75  push    rdi
0x140014a76  sub     rsp, 20h
0x140014a7a  mov     rdi, rcx
0x140014a7d  mov     [rsp+28h+arg_0], rbx
0x140014a82  xor     esi, esi
0x140014a84  cmp     [rdi], rdi
0x140014a87  jz      short loc_140014B02
0x140014a89  mov     rbx, [rdi+8]
0x140014a8d  cmp     [rbx], rdi
0x140014a90  jnz     short loc_140014A9B
0x140014a92  mov     rax, [rbx+8]
0x140014a96  cmp     [rax], rbx
0x140014a99  jz      short loc_140014AA2
0x140014a9b  mov     ecx, 3
0x140014aa0  int     29h; Win8: RtlFailFast(ecx)
0x140014aa2  mov     [rdi+8], rax
0x140014aa6  mov     [rax], rdi
0x140014aa9  mov     rcx, [rbx+18h]; P
0x140014aad  test    rcx, rcx
0x140014ab0  jz      short loc_140014AC7
0x140014ab2  mov     edx, 74734642h; Tag
0x140014ab7  call    cs:__imp_ExFreePoolWithTag
0x140014abe  nop     dword ptr [rax+rax+00h]
0x140014ac3  mov     [rbx+18h], rsi
0x140014ac7  mov     [rbx+10h], esi
0x140014aca  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140014ad1  mov     rcx, [rbx+20h]; P
0x140014ad5  lock xadd [rcx], rax
0x140014ada  sub     rax, 1
0x140014ade  jg      short loc_140014AEC
0x140014ae0  test    rax, rax
0x140014ae3  jz      short loc_140014B13
0x140014ae5  mov     ecx, 0Eh
0x140014aea  int     29h; Win8: RtlFailFast(ecx)
0x140014aec  mov     edx, 706D4642h; Tag
0x140014af1  mov     rcx, rbx; P
0x140014af4  call    cs:__imp_ExFreePoolWithTag
0x140014afb  nop     dword ptr [rax+rax+00h]
0x140014b00  jmp     short loc_140014A84
0x140014b02  mov     rbx, [rsp+28h+arg_0]
0x140014b07  mov     rsi, [rsp+28h+arg_8]
0x140014b0c  add     rsp, 20h
0x140014b10  pop     rdi
0x140014b11  retn
0x140014b13  call    BfpDeleteMappingInformation
0x140014b18  jmp     short loc_140014AEC
```
