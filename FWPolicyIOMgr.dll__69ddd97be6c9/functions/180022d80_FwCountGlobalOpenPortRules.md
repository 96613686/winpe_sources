# FwCountGlobalOpenPortRules

- ea: `0x180022d80`
- end: `0x180022dcc`
- name: `FwCountGlobalOpenPortRules`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180022d80`

## import_xrefs

- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180022da1`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180022da1`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x180022dae`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x180022dae`

## pseudocode

```c
void __fastcall FwCountGlobalOpenPortRules(_QWORD *a1, unsigned int a2, _DWORD *a3)
{
  unsigned int v3; // edi

  v3 = 0;
  for ( *a3 = 0; v3 < a2; ++v3 )
  {
    if ( (unsigned int)IsRuleOpenPortOrAuthApp(a1) )
    {
      if ( (unsigned int)IsRuleOldGlobalOpenPort(a1) )
        ++*a3;
    }
    a1 = (_QWORD *)*a1;
  }
}

```

## disassembly

```asm
0x180022d80  push    rbx
0x180022d82  push    rbp
0x180022d83  push    rsi
0x180022d84  push    rdi
0x180022d85  sub     rsp, 28h
0x180022d89  xor     edi, edi
0x180022d8b  mov     dword ptr [r8], 0
0x180022d92  mov     rsi, r8
0x180022d95  mov     ebp, edx
0x180022d97  mov     rbx, rcx
0x180022d9a  test    edx, edx
0x180022d9c  jz      short loc_180022DC3
0x180022d9e  mov     rcx, rbx
0x180022da1  call    cs:__imp_IsRuleOpenPortOrAuthApp
0x180022da7  test    eax, eax
0x180022da9  jz      short loc_180022DBA
0x180022dab  mov     rcx, rbx
0x180022dae  call    cs:__imp_IsRuleOldGlobalOpenPort
0x180022db4  test    eax, eax
0x180022db6  jz      short loc_180022DBA
0x180022db8  inc     dword ptr [rsi]
0x180022dba  mov     rbx, [rbx]
0x180022dbd  inc     edi
0x180022dbf  cmp     edi, ebp
0x180022dc1  jb      short loc_180022D9E
0x180022dc3  add     rsp, 28h
0x180022dc7  pop     rdi
0x180022dc8  pop     rsi
0x180022dc9  pop     rbp
0x180022dca  pop     rbx
0x180022dcb  retn
```
