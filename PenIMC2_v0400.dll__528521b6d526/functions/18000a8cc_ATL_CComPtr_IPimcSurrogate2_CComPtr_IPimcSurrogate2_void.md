# ATL::CComPtr<IPimcSurrogate2>::~CComPtr<IPimcSurrogate2>(void)

- ea: `0x18000a8cc`
- end: `0x18000a8f0`
- name: `??1?$CComPtr@UIPimcSurrogate2@@@ATL@@QEAA@XZ`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ee7c`

## callees

- `0x18000a8cc`
- `0x18000e4a0`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<IPimcSurrogate2>::~CComPtr<IPimcSurrogate2>(__int64 *a1)
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
0x18000a8cc  mov     [rsp+arg_0], rcx
0x18000a8d1  sub     rsp, 28h
0x18000a8d5  mov     rcx, [rcx]
0x18000a8d8  test    rcx, rcx
0x18000a8db  jz      short loc_18000A8EB
0x18000a8dd  mov     rax, [rcx]
0x18000a8e0  mov     rax, [rax+10h]
0x18000a8e4  call    cs:__guard_dispatch_icall_fptr
0x18000a8ea  nop
0x18000a8eb  add     rsp, 28h
0x18000a8ef  retn
```
