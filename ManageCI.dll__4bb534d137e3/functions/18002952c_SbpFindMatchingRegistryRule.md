# SbpFindMatchingRegistryRule

- ea: `0x18002952c`
- end: `0x1800295f9`
- name: `SbpFindMatchingRegistryRule`
- size: `205`
- prototype: `_DWORD *__fastcall(__int64, int, const UNICODE_STRING *, const UNICODE_STRING *)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180016c38`
- `0x180016de0`
- `0x180016e88`
- `0x18002944c`

## callees

- `0x18002952c`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x180029598`
- `ntdll!RtlEqualUnicodeString` at `0x1800295d2`
- `ntdll!RtlEqualUnicodeString` at `0x180029598`
- `ntdll!RtlEqualUnicodeString` at `0x1800295d2`

## pseudocode

```c
_DWORD *__fastcall SbpFindMatchingRegistryRule(__int64 a1, int a2, const UNICODE_STRING *a3, const UNICODE_STRING *a4)
{
  _DWORD *v4; // rbx
  _DWORD *v7; // rdi
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  UNICODE_STRING String2; // [rsp+20h] [rbp-48h] BYREF

  v4 = *(_DWORD **)(a1 + 80);
  v7 = &v4[4 * *(unsigned __int16 *)(a1 + 38)];
  String2 = 0;
  while ( v4 < v7 )
  {
    if ( *v4 == a2 )
    {
      v10 = (unsigned int)v4[1];
      v11 = *(_QWORD *)(a1 + 88);
      String2.Buffer = (PWSTR)(v10 + v11 + 2);
      String2.Length = *(_WORD *)(v10 + v11);
      String2.MaximumLength = String2.Length + 2;
      if ( RtlEqualUnicodeString(a3, &String2, 1u) )
      {
        v12 = (unsigned int)v4[2];
        v13 = *(_QWORD *)(a1 + 88);
        String2.Buffer = (PWSTR)(v12 + v13 + 2);
        String2.Length = *(_WORD *)(v12 + v13);
        String2.MaximumLength = String2.Length + 2;
        if ( RtlEqualUnicodeString(a4, &String2, 1u) )
          return v4;
      }
    }
    v4 += 4;
  }
  return 0;
}

```

## disassembly

```asm
0x18002952c  push    rbx
0x18002952e  push    rbp
0x18002952f  push    rsi
0x180029530  push    rdi
0x180029531  push    r14
0x180029533  push    r15
0x180029535  sub     rsp, 38h
0x180029539  movzx   edi, word ptr [rcx+26h]
0x18002953d  xorps   xmm0, xmm0
0x180029540  mov     rbx, [rcx+50h]
0x180029544  mov     r14, r9
0x180029547  shl     rdi, 4
0x18002954b  mov     r15, r8
0x18002954e  add     rdi, rbx
0x180029551  mov     ebp, edx
0x180029553  mov     rsi, rcx
0x180029556  movups  xmmword ptr [rsp+68h+String2.Length], xmm0
0x18002955b  cmp     rbx, rdi
0x18002955e  jnb     loc_1800295EA
0x180029564  cmp     [rbx], ebp
0x180029566  jnz     short loc_1800295DC
0x180029568  mov     edx, [rbx+4]
0x18002956b  mov     r8b, 1; CaseInsensitive
0x18002956e  mov     rcx, [rsi+58h]
0x180029572  lea     rax, [rcx+2]
0x180029576  add     rax, rdx
0x180029579  mov     [rsp+68h+String2.Buffer], rax
0x18002957e  movzx   eax, word ptr [rdx+rcx]
0x180029582  lea     rdx, [rsp+68h+String2]; String2
0x180029587  mov     [rsp+68h+String2.Length], ax
0x18002958c  mov     rcx, r15; String1
0x18002958f  add     ax, 2
0x180029593  mov     [rsp+68h+String2.MaximumLength], ax
0x180029598  call    cs:__imp_RtlEqualUnicodeString
0x18002959e  test    al, al
0x1800295a0  jz      short loc_1800295DC
0x1800295a2  mov     edx, [rbx+8]
0x1800295a5  mov     r8b, 1; CaseInsensitive
0x1800295a8  mov     rcx, [rsi+58h]
0x1800295ac  lea     rax, [rcx+2]
0x1800295b0  add     rax, rdx
0x1800295b3  mov     [rsp+68h+String2.Buffer], rax
0x1800295b8  movzx   eax, word ptr [rdx+rcx]
0x1800295bc  lea     rdx, [rsp+68h+String2]; String2
0x1800295c1  mov     [rsp+68h+String2.Length], ax
0x1800295c6  mov     rcx, r14; String1
0x1800295c9  add     ax, 2
0x1800295cd  mov     [rsp+68h+String2.MaximumLength], ax
0x1800295d2  call    cs:__imp_RtlEqualUnicodeString
0x1800295d8  test    al, al
0x1800295da  jnz     short loc_1800295E5
0x1800295dc  add     rbx, 10h
0x1800295e0  jmp     loc_18002955B
0x1800295e5  mov     rax, rbx
0x1800295e8  jmp     short loc_1800295EC
0x1800295ea  xor     eax, eax
0x1800295ec  add     rsp, 38h
0x1800295f0  pop     r15
0x1800295f2  pop     r14
0x1800295f4  pop     rdi
0x1800295f5  pop     rsi
0x1800295f6  pop     rbp
0x1800295f7  pop     rbx
0x1800295f8  retn
```
