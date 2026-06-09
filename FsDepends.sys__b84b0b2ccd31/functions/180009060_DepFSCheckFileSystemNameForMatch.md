# DepFSCheckFileSystemNameForMatch

- ea: `0x180009060`
- end: `0x1800090ef`
- name: `DepFSCheckFileSystemNameForMatch`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800090f8`

## callees

- `0x180009060`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x180009098`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800090cf`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180009098`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800090cf`

## pseudocode

```c
bool __fastcall DepFSCheckFileSystemNameForMatch(__int64 a1, const UNICODE_STRING *a2)
{
  __int64 v4; // r8
  __int64 v5; // rdx
  char v6; // bl
  __int64 v7; // rax
  __int64 v8; // rdx

  v4 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 56LL);
  if ( v4 )
  {
    v5 = *(_QWORD *)(v4 + 8);
    if ( v5 )
    {
      if ( RtlEqualUnicodeString(a2, (PCUNICODE_STRING)(*(_QWORD *)(v5 + 8) + 56LL), 1u) )
        return 1;
    }
  }
  v7 = *(_QWORD *)(a1 + 16);
  v6 = 0;
  if ( v7 )
  {
    v8 = *(_QWORD *)(v7 + 8);
    if ( v8 )
      return RtlEqualUnicodeString(a2, (PCUNICODE_STRING)(*(_QWORD *)(v8 + 8) + 56LL), 1u) != 0;
  }
  return v6;
}

```

## disassembly

```asm
0x180009060  push    rbx
0x180009062  push    rbp
0x180009063  push    rsi
0x180009064  push    rdi
0x180009065  sub     rsp, 28h
0x180009069  mov     rax, [rcx+8]
0x18000906d  mov     rsi, rdx
0x180009070  mov     rdi, rcx
0x180009073  mov     ebp, 1
0x180009078  mov     r8, [rax+38h]
0x18000907c  test    r8, r8
0x18000907f  jz      short loc_1800090AD
0x180009081  mov     rdx, [r8+8]
0x180009085  test    rdx, rdx
0x180009088  jz      short loc_1800090AD
0x18000908a  mov     rdx, [rdx+8]
0x18000908e  mov     r8b, bpl; CaseInSensitive
0x180009091  add     rdx, 38h ; '8'; String2
0x180009095  mov     rcx, rsi; String1
0x180009098  call    cs:__imp_RtlEqualUnicodeString
0x18000909f  nop     dword ptr [rax+rax+00h]
0x1800090a4  test    al, al
0x1800090a6  jz      short loc_1800090AD
0x1800090a8  mov     bl, bpl
0x1800090ab  jmp     short loc_1800090E3
0x1800090ad  mov     rax, [rdi+10h]
0x1800090b1  xor     bl, bl
0x1800090b3  test    rax, rax
0x1800090b6  jz      short loc_1800090E3
0x1800090b8  mov     rdx, [rax+8]
0x1800090bc  test    rdx, rdx
0x1800090bf  jz      short loc_1800090E3
0x1800090c1  mov     rdx, [rdx+8]
0x1800090c5  mov     r8b, bpl; CaseInSensitive
0x1800090c8  add     rdx, 38h ; '8'; String2
0x1800090cc  mov     rcx, rsi; String1
0x1800090cf  call    cs:__imp_RtlEqualUnicodeString
0x1800090d6  nop     dword ptr [rax+rax+00h]
0x1800090db  test    al, al
0x1800090dd  movzx   ebx, bl
0x1800090e0  cmovnz  ebx, ebp
0x1800090e3  mov     al, bl
0x1800090e5  add     rsp, 28h
0x1800090e9  pop     rdi
0x1800090ea  pop     rsi
0x1800090eb  pop     rbp
0x1800090ec  pop     rbx
0x1800090ed  retn
```
