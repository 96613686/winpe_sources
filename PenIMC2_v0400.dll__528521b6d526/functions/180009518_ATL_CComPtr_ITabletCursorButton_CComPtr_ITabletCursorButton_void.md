# ATL::CComPtr<ITabletCursorButton>::~CComPtr<ITabletCursorButton>(void)

- ea: `0x180009518`
- end: `0x18000953c`
- name: `??1?$CComPtr@UITabletCursorButton@@@ATL@@QEAA@XZ`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ec52`
- `0x18000ecf0`

## callees

- `0x180009518`
- `0x18000e4a0`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<ITabletCursorButton>::~CComPtr<ITabletCursorButton>(__int64 *a1)
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
0x180009518  mov     [rsp+arg_0], rcx
0x18000951d  sub     rsp, 28h
0x180009521  mov     rcx, [rcx]
0x180009524  test    rcx, rcx
0x180009527  jz      short loc_180009537
0x180009529  mov     rax, [rcx]
0x18000952c  mov     rax, [rax+10h]
0x180009530  call    cs:__guard_dispatch_icall_fptr
0x180009536  nop
0x180009537  add     rsp, 28h
0x18000953b  retn
```
