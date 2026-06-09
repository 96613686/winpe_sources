# CCoreADsObject::get_CoreSchema(ushort * *)

- ea: `0x180014a04`
- end: `0x180014a4c`
- name: `?get_CoreSchema@CCoreADsObject@@QEAAJPEAPEAG@Z`
- size: `72`
- prototype: `__int64 __fastcall(CCoreADsObject *__hidden this, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002550`
- `0x1800039d0`

## callees

- `0x180014a04`
- `0x18001beb8`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180014a24`
- `OLEAUT32!__imp_SysStringLen` at `0x180014a24`

## pseudocode

```c
__int64 __fastcall CCoreADsObject::get_CoreSchema(CCoreADsObject *this, unsigned __int16 **a2)
{
  if ( !a2 )
    return 2147504136LL;
  if ( SysStringLen(*((BSTR *)this + 7)) )
    return ADsAllocString(*((_QWORD *)this + 7), a2);
  return 2147504134LL;
}

```

## disassembly

```asm
0x180014a04  mov     [rsp+arg_0], rbx
0x180014a09  push    rdi
0x180014a0a  sub     rsp, 20h
0x180014a0e  mov     rbx, rdx
0x180014a11  mov     rdi, rcx
0x180014a14  test    rdx, rdx
0x180014a17  jnz     short loc_180014A20
0x180014a19  mov     eax, 80005008h
0x180014a1e  jmp     short loc_180014A41
0x180014a20  mov     rcx, [rcx+38h]; pbstr
0x180014a24  call    cs:__imp_SysStringLen
0x180014a2a  test    eax, eax
0x180014a2c  jnz     short loc_180014A35
0x180014a2e  mov     eax, 80005006h
0x180014a33  jmp     short loc_180014A41
0x180014a35  mov     rcx, [rdi+38h]
0x180014a39  mov     rdx, rbx
0x180014a3c  call    ADsAllocString
0x180014a41  mov     rbx, [rsp+28h+arg_0]
0x180014a46  add     rsp, 20h
0x180014a4a  pop     rdi
0x180014a4b  retn
```
