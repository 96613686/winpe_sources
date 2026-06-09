# ATL::CComPtr<ITypeLib>::~CComPtr<ITypeLib>(void)

- ea: `0x180002c00`
- end: `0x180002c24`
- name: `??1?$CComPtr@UITypeLib@@@ATL@@QEAA@XZ`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e67a`

## callees

- `0x180002c00`
- `0x18000e4a0`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<ITypeLib>::~CComPtr<ITypeLib>(__int64 *a1)
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
0x180002c00  mov     [rsp+arg_0], rcx
0x180002c05  sub     rsp, 28h
0x180002c09  mov     rcx, [rcx]
0x180002c0c  test    rcx, rcx
0x180002c0f  jz      short loc_180002C1F
0x180002c11  mov     rax, [rcx]
0x180002c14  mov     rax, [rax+10h]
0x180002c18  call    cs:__guard_dispatch_icall_fptr
0x180002c1e  nop
0x180002c1f  add     rsp, 28h
0x180002c23  retn
```
