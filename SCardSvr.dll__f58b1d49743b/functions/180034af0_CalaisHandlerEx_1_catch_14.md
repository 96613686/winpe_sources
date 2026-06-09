# _CalaisHandlerEx_::_1_::catch$14

- ea: `0x180034af0`
- end: `0x180034b26`
- name: `_CalaisHandlerEx_::_1_::catch$14`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180019bc4`

## string_xrefs

- `0x180034afd`: `DBT_DEVICEQUERYREMOVE`

## pseudocode

```c
__int64 __fastcall CalaisHandlerEx_::_1_::catch_14(
        const unsigned __int8 *a1,
        __int64 a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  CalaisError(a1, 0x20Au, L"DBT_DEVICEQUERYREMOVE", a4);
  *(_DWORD *)(a2 + 48) = 2404;
  return 0;
}

```

## disassembly

```asm
0x180034af0  mov     [rsp+arg_8], rdx
0x180034af5  push    rbp
0x180034af6  sub     rsp, 30h
0x180034afa  mov     rbp, rdx
0x180034afd  lea     r8, aDbtDevicequery_1; "DBT_DEVICEQUERYREMOVE"
0x180034b04  mov     edx, 20Ah; unsigned int
0x180034b09  call    ?CalaisError@@YAXPEBEKPEBG11@Z; CalaisError(uchar const *,ulong,ushort const *,ushort const *,ushort const *)
0x180034b0e  mov     dword ptr [rbp+30h], 964h
0x180034b15  mov     rax, 0
0x180034b1f  add     rsp, 30h
0x180034b23  pop     rbp
0x180034b24  retn
```
