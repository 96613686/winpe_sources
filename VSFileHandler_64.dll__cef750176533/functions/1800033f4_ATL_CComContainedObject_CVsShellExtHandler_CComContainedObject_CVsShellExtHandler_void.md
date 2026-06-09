# ATL::CComContainedObject<CVsShellExtHandler>::~CComContainedObject<CVsShellExtHandler>(void)

- ea: `0x1800033f4`
- end: `0x18000340d`
- name: `??1?$CComContainedObject@VCVsShellExtHandler@@@ATL@@QEAA@XZ`
- size: `25`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024d5b`
- `0x180024da8`

## callees

- `0x1800033f4`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CVsShellExtHandler>::~CComContainedObject<CVsShellExtHandler>(__int64 a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 40);
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x1800033f4  sub     rsp, 28h
0x1800033f8  mov     rcx, [rcx+28h]
0x1800033fc  test    rcx, rcx
0x1800033ff  jz      short loc_180003408
0x180003401  mov     rax, [rcx]
0x180003404  call    qword ptr [rax+10h]
0x180003407  nop
0x180003408  add     rsp, 28h
0x18000340c  retn
```
