# ATL::CComPtr<ITabletContextP>::~CComPtr<ITabletContextP>(void)

- ea: `0x18000627c`
- end: `0x1800062a0`
- name: `??1?$CComPtr@UITabletContextP@@@ATL@@QEAA@XZ`
- size: `36`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e8f0`
- `0x18000e8fc`
- `0x18000e908`
- `0x18000e998`
- `0x18000e9c8`
- `0x18000e9d4`
- `0x18000e9ec`
- `0x18000ea10`
- `0x18000ea64`
- `0x18000eaba`
- `0x18000ed88`
- `0x18000ee3c`

## callees

- `0x18000627c`
- `0x18000e4a0`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<ITabletContextP>::~CComPtr<ITabletContextP>(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x18000627c  mov     [rsp+arg_0], rcx
0x180006281  sub     rsp, 28h
0x180006285  mov     rcx, [rcx]
0x180006288  test    rcx, rcx
0x18000628b  jz      short loc_18000629B
0x18000628d  mov     rax, [rcx]
0x180006290  mov     rax, [rax+10h]
0x180006294  call    cs:__guard_dispatch_icall_fptr
0x18000629a  nop
0x18000629b  add     rsp, 28h
0x18000629f  retn
```
