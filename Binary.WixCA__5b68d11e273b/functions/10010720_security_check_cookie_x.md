# __security_check_cookie(x)

- ea: `0x10010720`
- end: `0x10010731`
- name: `@__security_check_cookie@4`
- size: `17`
- prototype: `void __fastcall(uintptr_t StackCookie)`
- caller_count: `47`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x100014a3`
- `0x100026eb`
- `0x100028f4`
- `0x10002cd0`
- `0x1000380d`
- `0x1000530d`
- `0x1000582e`
- `0x1000ad2c`
- `0x1000b2d8`
- `0x1000b4e3`
- `0x1000bdbd`
- `0x1000c7b9`
- `0x1000d51f`
- `0x1000d6ea`
- `0x1000da66`
- `0x1000dba2`
- `0x1000e5c3`
- `0x1000f00c`
- `0x1000f1d7`
- `0x1000f331`
- `0x1000f4bb`
- `0x1000fbcf`
- `0x10012330`
- `0x100125e0`
- `0x10012bc1`
- `0x1001380a`
- `0x1001398a`
- `0x10014bb6`
- `0x100158ae`
- `0x10015b0e`
- `0x10016e02`
- `0x100184ce`
- `0x10019155`
- `0x10019637`
- `0x100198b6`
- `0x10019c45`
- `0x1001acc5`
- `0x1001b3ff`
- `0x1001bdd8`
- `0x1001d540`
- `0x1001dd18`
- `0x1001e1a1`
- `0x1001e27e`
- `0x1001e369`
- `0x1001e785`
- `0x1002056c`
- `0x100206c0`

## callees

- `0x10010720`
- `0x10010b35`

## pseudocode

```c
void __fastcall __security_check_cookie(uintptr_t StackCookie)
{
  if ( StackCookie != __security_cookie )
    __report_gsfailure();
}

```

## disassembly

```asm
0x10010720  cmp     ecx, ___security_cookie
0x10010726  bnd jnz short loc_1001072B
0x10010729  bnd retn
0x1001072b  bnd jmp ___report_gsfailure
```
