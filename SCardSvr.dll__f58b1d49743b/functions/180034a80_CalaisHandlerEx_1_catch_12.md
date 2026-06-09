# _CalaisHandlerEx_::_1_::catch$12

- ea: `0x180034a80`
- end: `0x180034ab0`
- name: `_CalaisHandlerEx_::_1_::catch$12`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180019bc4`

## string_xrefs

- `0x180034a8d`: `DBT_DEVICEQUERYREMOVEFAILED`

## pseudocode

```c
__int64 __fastcall CalaisHandlerEx_::_1_::catch_12(
        const unsigned __int8 *a1,
        __int64 a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  CalaisError(a1, 0x201u, L"DBT_DEVICEQUERYREMOVEFAILED", a4);
  return 0;
}

```

## disassembly

```asm
0x180034a80  mov     [rsp+arg_8], rdx
0x180034a85  push    rbp
0x180034a86  sub     rsp, 30h
0x180034a8a  mov     rbp, rdx
0x180034a8d  lea     r8, aDbtDevicequery; "DBT_DEVICEQUERYREMOVEFAILED"
0x180034a94  mov     edx, 201h; unsigned int
0x180034a99  call    ?CalaisError@@YAXPEBEKPEBG11@Z; CalaisError(uchar const *,ulong,ushort const *,ushort const *,ushort const *)
0x180034a9e  nop
0x180034a9f  mov     rax, 0
0x180034aa9  add     rsp, 30h
0x180034aad  pop     rbp
0x180034aae  retn
```
