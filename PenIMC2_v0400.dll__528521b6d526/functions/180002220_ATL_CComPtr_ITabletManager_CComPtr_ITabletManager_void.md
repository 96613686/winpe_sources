# ATL::CComPtr<ITabletManager>::~CComPtr<ITabletManager>(void)

- ea: `0x180002220`
- end: `0x180002244`
- name: `??1?$CComPtr@UITabletManager@@@ATL@@QEAA@XZ`
- size: `36`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e58f`
- `0x18000e5e6`
- `0x18000ee70`
- `0x18000f0fb`

## callees

- `0x180002220`
- `0x18000e4a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComPtr<ITabletManager>::~CComPtr<ITabletManager>(__int64 *a1)
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
0x180002220  mov     [rsp+arg_0], rcx
0x180002225  sub     rsp, 28h
0x180002229  mov     rcx, [rcx]
0x18000222c  test    rcx, rcx
0x18000222f  jz      short loc_18000223F
0x180002231  mov     rax, [rcx]
0x180002234  mov     rax, [rax+10h]
0x180002238  call    cs:__guard_dispatch_icall_fptr
0x18000223e  nop
0x18000223f  add     rsp, 28h
0x180002243  retn
```
