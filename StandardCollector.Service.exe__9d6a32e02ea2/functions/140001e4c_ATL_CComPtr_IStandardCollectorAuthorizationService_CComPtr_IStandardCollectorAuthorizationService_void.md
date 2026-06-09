# ATL::CComPtr<IStandardCollectorAuthorizationService>::~CComPtr<IStandardCollectorAuthorizationService>(void)

- ea: `0x140001e4c`
- end: `0x140001e6b`
- name: `??1?$CComPtr@UIStandardCollectorAuthorizationService@@@ATL@@QEAA@XZ`
- size: `31`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `25`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140014cba`
- `0x140014cc6`
- `0x140014cd2`
- `0x140014cf6`
- `0x140014d87`
- `0x140014fe2`
- `0x140014fee`
- `0x140014ffa`
- `0x140015030`
- `0x14001503c`
- `0x140015048`
- `0x1400150a8`
- `0x14001511c`
- `0x140015128`
- `0x14001573e`
- `0x14001576e`
- `0x14001577a`
- `0x140015786`
- `0x1400158f8`
- `0x140015904`
- `0x140015910`
- `0x140015964`
- `0x140015970`
- `0x14001597c`
- `0x140015988`

## callees

- `0x140001e4c`
- `0x140014c70`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<IStandardCollectorAuthorizationService>::~CComPtr<IStandardCollectorAuthorizationService>(
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
0x140001e4c  sub     rsp, 28h
0x140001e50  mov     rcx, [rcx]
0x140001e53  test    rcx, rcx
0x140001e56  jz      short loc_140001E66
0x140001e58  mov     rax, [rcx]
0x140001e5b  mov     rax, [rax+10h]
0x140001e5f  call    cs:__guard_dispatch_icall_fptr
0x140001e65  nop
0x140001e66  add     rsp, 28h
0x140001e6a  retn
```
