# _CalaisHandlerEx_::_1_::catch$5

- ea: `0x1800348f0`
- end: `0x180034920`
- name: `_CalaisHandlerEx_::_1_::catch$5`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180019bc4`

## string_xrefs

- `0x1800348fd`: `DBT_DEVICEREMOVECOMPLETE/DBT_DEVTYP_HANDLE`

## pseudocode

```c
__int64 __fastcall CalaisHandlerEx_::_1_::catch_5(
        const unsigned __int8 *a1,
        __int64 a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  CalaisError(a1, 0x1FDu, L"DBT_DEVICEREMOVECOMPLETE/DBT_DEVTYP_HANDLE", a4);
  return 0;
}

```

## disassembly

```asm
0x1800348f0  mov     [rsp+arg_8], rdx
0x1800348f5  push    rbp
0x1800348f6  sub     rsp, 30h
0x1800348fa  mov     rbp, rdx
0x1800348fd  lea     r8, aDbtDeviceremov_2; "DBT_DEVICEREMOVECOMPLETE/DBT_DEVTYP_HAN"...
0x180034904  mov     edx, 1FDh; unsigned int
0x180034909  call    ?CalaisError@@YAXPEBEKPEBG11@Z; CalaisError(uchar const *,ulong,ushort const *,ushort const *,ushort const *)
0x18003490e  nop
0x18003490f  mov     rax, 0
0x180034919  add     rsp, 30h
0x18003491d  pop     rbp
0x18003491e  retn
```
