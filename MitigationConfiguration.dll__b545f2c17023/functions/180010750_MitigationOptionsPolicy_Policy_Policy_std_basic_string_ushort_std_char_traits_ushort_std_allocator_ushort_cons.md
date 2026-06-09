# MitigationOptionsPolicy::Policy::Policy(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x180010750`
- end: `0x180010785`
- name: `??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z`
- size: `53`
- prototype: `__int64 __fastcall(__int64, __int64, char)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180011304`
- `0x180011858`
- `0x180011b90`

## callees

- `0x180010634`

## pseudocode

```c
__int64 __fastcall MitigationOptionsPolicy::Policy::Policy(__int64 a1, __int64 a2, char a3)
{
  __int64 result; // rax

  *(_QWORD *)a1 = &MitigationOptionsPolicy::Policy::`vftable';
  std::wstring::wstring(a1 + 8, a2);
  result = a1;
  *(_BYTE *)(a1 + 40) = a3;
  return result;
}

```

## disassembly

```asm
0x180010750  mov     [rsp+arg_0], rbx
0x180010755  push    rdi
0x180010756  sub     rsp, 20h
0x18001075a  lea     rax, ??_7Policy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::Policy::`vftable'
0x180010761  mov     rbx, rcx
0x180010764  mov     [rcx], rax
0x180010767  mov     dil, r8b
0x18001076a  add     rcx, 8
0x18001076e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180010773  mov     rax, rbx
0x180010776  mov     [rbx+28h], dil
0x18001077a  mov     rbx, [rsp+28h+arg_0]
0x18001077f  add     rsp, 20h
0x180010783  pop     rdi
0x180010784  retn
```
