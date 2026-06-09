# _CalaisHandlerEx_::_1_::catch$8

- ea: `0x180034990`
- end: `0x1800349c0`
- name: `_CalaisHandlerEx_::_1_::catch$8`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180019bc4`

## string_xrefs

- `0x18003499d`: `DBT_DEVICEREMOVECOMPLETE/DBT_DEVTYP_DEVICEINTERFACE`

## pseudocode

```c
__int64 __fastcall CalaisHandlerEx_::_1_::catch_8(
        const unsigned __int8 *a1,
        __int64 a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  CalaisError(a1, 0x1FCu, L"DBT_DEVICEREMOVECOMPLETE/DBT_DEVTYP_DEVICEINTERFACE", a4);
  return 0;
}

```

## disassembly

```asm
0x180034990  mov     [rsp+arg_8], rdx
0x180034995  push    rbp
0x180034996  sub     rsp, 30h
0x18003499a  mov     rbp, rdx
0x18003499d  lea     r8, aDbtDeviceremov; "DBT_DEVICEREMOVECOMPLETE/DBT_DEVTYP_DEV"...
0x1800349a4  mov     edx, 1FCh; unsigned int
0x1800349a9  call    ?CalaisError@@YAXPEBEKPEBG11@Z; CalaisError(uchar const *,ulong,ushort const *,ushort const *,ushort const *)
0x1800349ae  nop
0x1800349af  mov     rax, 0
0x1800349b9  add     rsp, 30h
0x1800349bd  pop     rbp
0x1800349be  retn
```
