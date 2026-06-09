# ATL::CComPtr<ITabletCursor>::~CComPtr<ITabletCursor>(void)

- ea: `0x1800094f4`
- end: `0x180009518`
- name: `??1?$CComPtr@UITabletCursor@@@ATL@@QEAA@XZ`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ec46`
- `0x18000ed08`

## callees

- `0x1800094f4`
- `0x18000e4a0`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<ITabletCursor>::~CComPtr<ITabletCursor>(__int64 *a1)
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
0x1800094f4  mov     [rsp+arg_0], rcx
0x1800094f9  sub     rsp, 28h
0x1800094fd  mov     rcx, [rcx]
0x180009500  test    rcx, rcx
0x180009503  jz      short loc_180009513
0x180009505  mov     rax, [rcx]
0x180009508  mov     rax, [rax+10h]
0x18000950c  call    cs:__guard_dispatch_icall_fptr
0x180009512  nop
0x180009513  add     rsp, 28h
0x180009517  retn
```
