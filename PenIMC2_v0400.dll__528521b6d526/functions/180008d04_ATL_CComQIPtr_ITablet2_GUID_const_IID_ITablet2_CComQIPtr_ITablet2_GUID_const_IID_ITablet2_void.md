# ATL::CComQIPtr<ITablet2,&_GUID const IID_ITablet2>::~CComQIPtr<ITablet2,&_GUID const IID_ITablet2>(void)

- ea: `0x180008d04`
- end: `0x180008d28`
- name: `??1?$CComQIPtr@UITablet2@@$1?IID_ITablet2@@3U_GUID@@B@ATL@@QEAA@XZ`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ebe6`
- `0x18000ec22`

## callees

- `0x180008d04`
- `0x18000e4a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComQIPtr<ITablet2,&_GUID const IID_ITablet2>::~CComQIPtr<ITablet2,&_GUID const IID_ITablet2>(
        __int64 *a1)
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
0x180008d04  mov     [rsp+arg_0], rcx
0x180008d09  sub     rsp, 28h
0x180008d0d  mov     rcx, [rcx]
0x180008d10  test    rcx, rcx
0x180008d13  jz      short loc_180008D23
0x180008d15  mov     rax, [rcx]
0x180008d18  mov     rax, [rax+10h]
0x180008d1c  call    cs:__guard_dispatch_icall_fptr
0x180008d22  nop
0x180008d23  add     rsp, 28h
0x180008d27  retn
```
