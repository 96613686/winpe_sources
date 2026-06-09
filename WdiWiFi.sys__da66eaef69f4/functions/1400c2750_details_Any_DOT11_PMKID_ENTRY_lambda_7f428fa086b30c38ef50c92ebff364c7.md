# details::Any_DOT11_PMKID_ENTRY__lambda_7f428fa086b30c38ef50c92ebff364c7___

- ea: `0x1400c2750`
- end: `0x1400c27ae`
- name: `details::Any_DOT11_PMKID_ENTRY__lambda_7f428fa086b30c38ef50c92ebff364c7___`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14005fa98`

## callees

- `0x1400c2750`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400c277f`
- `ntoskrnl!RtlCompareMemory` at `0x1400c277f`

## pseudocode

```c
char __fastcall details::Any_DOT11_PMKID_ENTRY__lambda_7f428fa086b30c38ef50c92ebff364c7___(
        int a1,
        char *a2,
        const void **a3)
{
  char *v4; // rbx
  char *v5; // rdi

  v4 = a2;
  v5 = &a2[28 * a1];
  while ( v4 != v5 )
  {
    if ( RtlCompareMemory(*a3, v4, 6u) == 6 )
      return 1;
    v4 += 28;
  }
  return 0;
}

```

## disassembly

```asm
0x1400c2750  mov     [rsp+arg_0], rbx
0x1400c2755  mov     [rsp+arg_8], rsi
0x1400c275a  push    rdi
0x1400c275b  sub     rsp, 20h
0x1400c275f  mov     eax, ecx
0x1400c2761  mov     rsi, r8
0x1400c2764  imul    rdi, rax, 1Ch
0x1400c2768  mov     rbx, rdx
0x1400c276b  add     rdi, rdx
0x1400c276e  cmp     rbx, rdi
0x1400c2771  jz      short loc_1400C279B
0x1400c2773  mov     rcx, [rsi]; Source1
0x1400c2776  mov     r8d, 6; Length
0x1400c277c  mov     rdx, rbx; Source2
0x1400c277f  call    cs:__imp_RtlCompareMemory
0x1400c2786  nop     dword ptr [rax+rax+00h]
0x1400c278b  cmp     rax, 6
0x1400c278f  jz      short loc_1400C2797
0x1400c2791  add     rbx, 1Ch
0x1400c2795  jmp     short loc_1400C276E
0x1400c2797  mov     al, 1
0x1400c2799  jmp     short loc_1400C279D
0x1400c279b  xor     al, al
0x1400c279d  mov     rbx, [rsp+28h+arg_0]
0x1400c27a2  mov     rsi, [rsp+28h+arg_8]
0x1400c27a7  add     rsp, 20h
0x1400c27ab  pop     rdi
0x1400c27ac  retn
```
