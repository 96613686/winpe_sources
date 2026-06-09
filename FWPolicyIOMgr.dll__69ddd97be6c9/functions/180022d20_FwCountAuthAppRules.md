# FwCountAuthAppRules

- ea: `0x180022d20`
- end: `0x180022d6c`
- name: `FwCountAuthAppRules`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180022d20`

## import_xrefs

- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180022d41`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180022d41`
- `fwbase!IsRuleOldAuthApp` at `0x180022d4e`
- `fwbase!IsRuleOldAuthApp` at `0x180022d4e`

## pseudocode

```c
void __fastcall FwCountAuthAppRules(_QWORD *a1, unsigned int a2, _DWORD *a3)
{
  unsigned int v3; // edi

  v3 = 0;
  for ( *a3 = 0; v3 < a2; ++v3 )
  {
    if ( (unsigned int)IsRuleOpenPortOrAuthApp(a1) )
    {
      if ( (unsigned int)IsRuleOldAuthApp(a1) )
        ++*a3;
    }
    a1 = (_QWORD *)*a1;
  }
}

```

## disassembly

```asm
0x180022d20  push    rbx
0x180022d22  push    rbp
0x180022d23  push    rsi
0x180022d24  push    rdi
0x180022d25  sub     rsp, 28h
0x180022d29  xor     edi, edi
0x180022d2b  mov     dword ptr [r8], 0
0x180022d32  mov     rsi, r8
0x180022d35  mov     ebp, edx
0x180022d37  mov     rbx, rcx
0x180022d3a  test    edx, edx
0x180022d3c  jz      short loc_180022D63
0x180022d3e  mov     rcx, rbx
0x180022d41  call    cs:__imp_IsRuleOpenPortOrAuthApp
0x180022d47  test    eax, eax
0x180022d49  jz      short loc_180022D5A
0x180022d4b  mov     rcx, rbx
0x180022d4e  call    cs:__imp_IsRuleOldAuthApp
0x180022d54  test    eax, eax
0x180022d56  jz      short loc_180022D5A
0x180022d58  inc     dword ptr [rsi]
0x180022d5a  mov     rbx, [rbx]
0x180022d5d  inc     edi
0x180022d5f  cmp     edi, ebp
0x180022d61  jb      short loc_180022D3E
0x180022d63  add     rsp, 28h
0x180022d67  pop     rdi
0x180022d68  pop     rsi
0x180022d69  pop     rbp
0x180022d6a  pop     rbx
0x180022d6b  retn
```
