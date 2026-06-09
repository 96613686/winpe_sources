# _CalaisHandlerEx_::_1_::catch$9

- ea: `0x1800349d0`
- end: `0x180034a00`
- name: `_CalaisHandlerEx_::_1_::catch$9`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180019bc4`

## string_xrefs

- `0x1800349dd`: `DBT_DEVICEREMOVECOMPLETE`

## pseudocode

```c
__int64 __fastcall CalaisHandlerEx_::_1_::catch_9(
        const unsigned __int8 *a1,
        __int64 a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  CalaisError(a1, 0x206u, L"DBT_DEVICEREMOVECOMPLETE", a4);
  return 0;
}

```

## disassembly

```asm
0x1800349d0  mov     [rsp+arg_8], rdx
0x1800349d5  push    rbp
0x1800349d6  sub     rsp, 30h
0x1800349da  mov     rbp, rdx
0x1800349dd  lea     r8, aDbtDeviceremov_3; "DBT_DEVICEREMOVECOMPLETE"
0x1800349e4  mov     edx, 206h; unsigned int
0x1800349e9  call    ?CalaisError@@YAXPEBEKPEBG11@Z; CalaisError(uchar const *,ulong,ushort const *,ushort const *,ushort const *)
0x1800349ee  nop
0x1800349ef  mov     rax, 0
0x1800349f9  add     rsp, 30h
0x1800349fd  pop     rbp
0x1800349fe  retn
```
