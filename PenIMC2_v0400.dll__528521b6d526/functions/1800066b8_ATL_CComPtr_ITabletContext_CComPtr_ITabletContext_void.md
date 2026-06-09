# ATL::CComPtr<ITabletContext>::~CComPtr<ITabletContext>(void)

- ea: `0x1800066b8`
- end: `0x1800066dc`
- name: `??1?$CComPtr@UITabletContext@@@ATL@@QEAA@XZ`
- size: `36`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e8d8`
- `0x18000eb6e`
- `0x18000eb7a`
- `0x18000eb92`

## callees

- `0x1800066b8`
- `0x18000e4a0`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<ITabletContext>::~CComPtr<ITabletContext>(__int64 *a1)
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
0x1800066b8  mov     [rsp+arg_0], rcx
0x1800066bd  sub     rsp, 28h
0x1800066c1  mov     rcx, [rcx]
0x1800066c4  test    rcx, rcx
0x1800066c7  jz      short loc_1800066D7
0x1800066c9  mov     rax, [rcx]
0x1800066cc  mov     rax, [rax+10h]
0x1800066d0  call    cs:__guard_dispatch_icall_fptr
0x1800066d6  nop
0x1800066d7  add     rsp, 28h
0x1800066db  retn
```
