# XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<double>(String &)

- ea: `0x18000615c`
- end: `0x1800061a5`
- name: `??$LookupRelationalOrEqualityOperatorFunc@N@XPathQueryStringCompiler@@CAP6A_NNN@ZAEAVString@@@Z`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005a3c`

## callees

- `0x18000615c`
- `0x1800083b4`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<double>(const WCHAR **a1)
{
  unsigned __int16 i; // bx

  for ( i = 0; i < 6u; ++i )
  {
    if ( WideCharStringTemplate<String>::Equals(
           a1,
           (&`XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<double>'::`2'::rgOperatorMap)[2 * i]) )
    {
      return (__int64)*(&`XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<double>'::`2'::rgOperatorMap
                      + 2 * i
                      + 1);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000615c  push    rbx
0x18000615e  push    rbp
0x18000615f  push    rsi
0x180006160  push    rdi
0x180006161  sub     rsp, 28h
0x180006165  mov     rsi, rcx
0x180006168  lea     rbp, ?rgOperatorMap@?1???$LookupRelationalOrEqualityOperatorFunc@N@XPathQueryStringCompiler@@CAP6A_NNN@ZAEAVString@@@Z@4PAU_unnamed_type_rgOperatorMap_@?1???$LookupRelationalOrEqualityOperatorFunc@N@1@CAP6A_NNN@Z0@Z@A; `XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<double>(String &)'::`2'::_unnamed_type_rgOperatorMap_ near * `XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<double>(String &)'::`2'::rgOperatorMap
0x18000616f  xor     ebx, ebx
0x180006171  cmp     bx, 6
0x180006175  jnb     short loc_18000619A
0x180006177  movzx   edi, bx
0x18000617a  mov     rcx, rsi
0x18000617d  add     rdi, rdi
0x180006180  mov     rdx, [rbp+rdi*8+0]
0x180006185  call    ?Equals@?$WideCharStringTemplate@VString@@@@QEBA_NPEBG@Z; WideCharStringTemplate<String>::Equals(ushort const *)
0x18000618a  test    al, al
0x18000618c  jnz     short loc_180006193
0x18000618e  inc     bx
0x180006191  jmp     short loc_180006171
0x180006193  mov     rax, [rbp+rdi*8+8]
0x180006198  jmp     short loc_18000619C
0x18000619a  xor     eax, eax
0x18000619c  add     rsp, 28h
0x1800061a0  pop     rdi
0x1800061a1  pop     rsi
0x1800061a2  pop     rbp
0x1800061a3  pop     rbx
0x1800061a4  retn
```
