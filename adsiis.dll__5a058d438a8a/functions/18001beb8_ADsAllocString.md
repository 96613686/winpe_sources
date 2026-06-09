# ADsAllocString

- ea: `0x18001beb8`
- end: `0x18001bee8`
- name: `ADsAllocString`
- size: `48`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `40`
- callee_count: `1`
- tags: ``

## callers

- `0x180003260`
- `0x180003bb8`
- `0x180006240`
- `0x1800079c4`
- `0x180007e04`
- `0x180008a50`
- `0x180009154`
- `0x180009a44`
- `0x180009d90`
- `0x18000a340`
- `0x18000a660`
- `0x18000b3b4`
- `0x18000bee0`
- `0x18000c610`
- `0x18000c690`
- `0x18000ce28`
- `0x18000d638`
- `0x18000dfe0`
- `0x18000e000`
- `0x18000eab0`
- `0x18000ec00`
- `0x18000ed80`
- `0x18000eee0`
- `0x18000fc80`
- `0x180012d2c`
- `0x180012e6c`
- `0x180013190`
- `0x180013b94`
- `0x180013e08`
- `0x1800148a0`
- `0x180014994`
- `0x1800149b0`
- `0x1800149cc`
- `0x1800149e8`
- `0x180014a04`
- `0x180017480`
- `0x180018518`
- `0x18001883c`
- `0x18001a34c`
- `0x18001b970`

## callees

- `0x18001beb8`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001becd`
- `OLEAUT32!__imp_SysAllocString` at `0x18001becd`

## pseudocode

```c
__int64 __fastcall ADsAllocString(const OLECHAR *a1, BSTR *a2)
{
  BSTR v4; // rax

  if ( a1 )
  {
    v4 = SysAllocString(a1);
    *a2 = v4;
    return v4 == 0 ? 0x8007000E : 0;
  }
  else
  {
    *a2 = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x18001beb8  push    rbx
0x18001beba  sub     rsp, 20h
0x18001bebe  mov     rbx, rdx
0x18001bec1  test    rcx, rcx
0x18001bec4  jnz     short loc_18001BECD
0x18001bec6  mov     [rdx], rcx
0x18001bec9  xor     eax, eax
0x18001becb  jmp     short loc_18001BEE2
0x18001becd  call    cs:__imp_SysAllocString
0x18001bed3  mov     [rbx], rax
0x18001bed6  neg     rax
0x18001bed9  sbb     eax, eax
0x18001bedb  not     eax
0x18001bedd  and     eax, 8007000Eh
0x18001bee2  add     rsp, 20h
0x18001bee6  pop     rbx
0x18001bee7  retn
```
