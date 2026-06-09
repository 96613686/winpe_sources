# XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<String>(String &)

- ea: `0x1800061ac`
- end: `0x1800061f5`
- name: `??$LookupRelationalOrEqualityOperatorFunc@VString@@@XPathQueryStringCompiler@@CAP6A_NVString@@0@ZAEAV1@@Z`
- size: `73`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005b60`
- `0x180008f04`

## callees

- `0x1800061ac`
- `0x1800083b4`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<String>(const WCHAR **a1)
{
  unsigned __int16 i; // bx

  for ( i = 0; i < 6u; ++i )
  {
    if ( WideCharStringTemplate<String>::Equals(
           a1,
           (&`XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<String>'::`2'::rgOperatorMap)[2 * i]) )
    {
      return (__int64)*(&`XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<String>'::`2'::rgOperatorMap
                      + 2 * i
                      + 1);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800061ac  push    rbx
0x1800061ae  push    rbp
0x1800061af  push    rsi
0x1800061b0  push    rdi
0x1800061b1  sub     rsp, 28h
0x1800061b5  mov     rsi, rcx
0x1800061b8  lea     rbp, ?rgOperatorMap@?1???$LookupRelationalOrEqualityOperatorFunc@VString@@@XPathQueryStringCompiler@@CAP6A_NVString@@0@ZAEAV2@@Z@4PAU_unnamed_type_rgOperatorMap_@?1???$LookupRelationalOrEqualityOperatorFunc@VString@@@1@CAP6A_N00@Z1@Z@A; `XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<String>(String &)'::`2'::_unnamed_type_rgOperatorMap_ near * `XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<String>(String &)'::`2'::rgOperatorMap
0x1800061bf  xor     ebx, ebx
0x1800061c1  cmp     bx, 6
0x1800061c5  jnb     short loc_1800061EA
0x1800061c7  movzx   edi, bx
0x1800061ca  mov     rcx, rsi
0x1800061cd  add     rdi, rdi
0x1800061d0  mov     rdx, [rbp+rdi*8+0]
0x1800061d5  call    ?Equals@?$WideCharStringTemplate@VString@@@@QEBA_NPEBG@Z; WideCharStringTemplate<String>::Equals(ushort const *)
0x1800061da  test    al, al
0x1800061dc  jnz     short loc_1800061E3
0x1800061de  inc     bx
0x1800061e1  jmp     short loc_1800061C1
0x1800061e3  mov     rax, [rbp+rdi*8+8]
0x1800061e8  jmp     short loc_1800061EC
0x1800061ea  xor     eax, eax
0x1800061ec  add     rsp, 28h
0x1800061f0  pop     rdi
0x1800061f1  pop     rsi
0x1800061f2  pop     rbp
0x1800061f3  pop     rbx
0x1800061f4  retn
```
