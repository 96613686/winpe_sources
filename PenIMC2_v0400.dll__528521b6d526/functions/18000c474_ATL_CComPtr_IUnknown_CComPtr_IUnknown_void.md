# ATL::CComPtr<IUnknown>::~CComPtr<IUnknown>(void)

- ea: `0x18000c474`
- end: `0x18000c498`
- name: `??1?$CComPtr@UIUnknown@@@ATL@@QEAA@XZ`
- size: `36`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ee88`
- `0x18000f187`
- `0x18000f19f`
- `0x18000f1dd`

## callees

- `0x18000c474`
- `0x18000e4a0`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<IUnknown>::~CComPtr<IUnknown>(__int64 *a1)
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
0x18000c474  mov     [rsp+arg_0], rcx
0x18000c479  sub     rsp, 28h
0x18000c47d  mov     rcx, [rcx]
0x18000c480  test    rcx, rcx
0x18000c483  jz      short loc_18000C493
0x18000c485  mov     rax, [rcx]
0x18000c488  mov     rax, [rax+10h]
0x18000c48c  call    cs:__guard_dispatch_icall_fptr
0x18000c492  nop
0x18000c493  add     rsp, 28h
0x18000c497  retn
```
