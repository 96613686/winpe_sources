# ATL::CComPtr<ITablet>::~CComPtr<ITablet>(void)

- ea: `0x18000814c`
- end: `0x180008170`
- name: `??1?$CComPtr@UITablet@@@ATL@@QEAA@XZ`
- size: `36`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000eb0e`
- `0x18000eb1a`
- `0x18000eb3e`
- `0x18000edcf`
- `0x18000efe3`
- `0x18000efef`
- `0x18000f015`
- `0x18000f047`
- `0x18000f09b`
- `0x18000f0c3`
- `0x18000f13b`

## callees

- `0x18000814c`
- `0x18000e4a0`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<ITablet>::~CComPtr<ITablet>(__int64 *a1)
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
0x18000814c  mov     [rsp+arg_0], rcx
0x180008151  sub     rsp, 28h
0x180008155  mov     rcx, [rcx]
0x180008158  test    rcx, rcx
0x18000815b  jz      short loc_18000816B
0x18000815d  mov     rax, [rcx]
0x180008160  mov     rax, [rax+10h]
0x180008164  call    cs:__guard_dispatch_icall_fptr
0x18000816a  nop
0x18000816b  add     rsp, 28h
0x18000816f  retn
```
