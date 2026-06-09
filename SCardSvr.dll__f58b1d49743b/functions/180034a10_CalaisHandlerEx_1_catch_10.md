# _CalaisHandlerEx_::_1_::catch$10

- ea: `0x180034a10`
- end: `0x180034a40`
- name: `_CalaisHandlerEx_::_1_::catch$10`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180019bc4`

## string_xrefs

- `0x180034a1d`: `DBT_DEVICEREMOVEPENDING`

## pseudocode

```c
__int64 __fastcall CalaisHandlerEx_::_1_::catch_10(
        const unsigned __int8 *a1,
        __int64 a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  CalaisError(a1, 0x1FFu, L"DBT_DEVICEREMOVEPENDING", a4);
  return 0;
}

```

## disassembly

```asm
0x180034a10  mov     [rsp+arg_8], rdx
0x180034a15  push    rbp
0x180034a16  sub     rsp, 30h
0x180034a1a  mov     rbp, rdx
0x180034a1d  lea     r8, aDbtDeviceremov_0; "DBT_DEVICEREMOVEPENDING"
0x180034a24  mov     edx, 1FFh; unsigned int
0x180034a29  call    ?CalaisError@@YAXPEBEKPEBG11@Z; CalaisError(uchar const *,ulong,ushort const *,ushort const *,ushort const *)
0x180034a2e  nop
0x180034a2f  mov     rax, 0
0x180034a39  add     rsp, 30h
0x180034a3d  pop     rbp
0x180034a3e  retn
```
