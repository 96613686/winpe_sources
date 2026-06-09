# ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)

- ea: `0x180008d28`
- end: `0x180008d4c`
- name: `??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ`
- size: `36`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ebf2`
- `0x18000ec0a`
- `0x18000ec2e`

## callees

- `0x180008d28`
- `0x18000e4a0`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(__int64 *a1)
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
0x180008d28  mov     [rsp+arg_0], rcx
0x180008d2d  sub     rsp, 28h
0x180008d31  mov     rcx, [rcx]
0x180008d34  test    rcx, rcx
0x180008d37  jz      short loc_180008D47
0x180008d39  mov     rax, [rcx]
0x180008d3c  mov     rax, [rax+10h]
0x180008d40  call    cs:__guard_dispatch_icall_fptr
0x180008d46  nop
0x180008d47  add     rsp, 28h
0x180008d4b  retn
```
