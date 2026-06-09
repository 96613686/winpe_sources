# XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<bool>(String &)

- ea: `0x1800061fc`
- end: `0x180006245`
- name: `??$LookupRelationalOrEqualityOperatorFunc@_N@XPathQueryStringCompiler@@CAP6A_N_N0@ZAEAVString@@@Z`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005c7c`

## callees

- `0x1800061fc`
- `0x1800083b4`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<bool>(const WCHAR **a1)
{
  unsigned __int16 i; // bx

  for ( i = 0; i < 6u; ++i )
  {
    if ( WideCharStringTemplate<String>::Equals(
           a1,
           (&`XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<bool>'::`2'::rgOperatorMap)[2 * i]) )
    {
      return (__int64)*(&`XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<bool>'::`2'::rgOperatorMap
                      + 2 * i
                      + 1);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800061fc  push    rbx
0x1800061fe  push    rbp
0x1800061ff  push    rsi
0x180006200  push    rdi
0x180006201  sub     rsp, 28h
0x180006205  mov     rsi, rcx
0x180006208  lea     rbp, ?rgOperatorMap@?1???$LookupRelationalOrEqualityOperatorFunc@_N@XPathQueryStringCompiler@@CAP6A_N_N0@ZAEAVString@@@Z@4PAU_unnamed_type_rgOperatorMap_@?1???$LookupRelationalOrEqualityOperatorFunc@_N@1@CAP6A_N00@Z1@Z@A; `XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<bool>(String &)'::`2'::_unnamed_type_rgOperatorMap_ near * `XPathQueryStringCompiler::LookupRelationalOrEqualityOperatorFunc<bool>(String &)'::`2'::rgOperatorMap
0x18000620f  xor     ebx, ebx
0x180006211  cmp     bx, 6
0x180006215  jnb     short loc_18000623A
0x180006217  movzx   edi, bx
0x18000621a  mov     rcx, rsi
0x18000621d  add     rdi, rdi
0x180006220  mov     rdx, [rbp+rdi*8+0]
0x180006225  call    ?Equals@?$WideCharStringTemplate@VString@@@@QEBA_NPEBG@Z; WideCharStringTemplate<String>::Equals(ushort const *)
0x18000622a  test    al, al
0x18000622c  jnz     short loc_180006233
0x18000622e  inc     bx
0x180006231  jmp     short loc_180006211
0x180006233  mov     rax, [rbp+rdi*8+8]
0x180006238  jmp     short loc_18000623C
0x18000623a  xor     eax, eax
0x18000623c  add     rsp, 28h
0x180006240  pop     rdi
0x180006241  pop     rsi
0x180006242  pop     rbp
0x180006243  pop     rbx
0x180006244  retn
```
