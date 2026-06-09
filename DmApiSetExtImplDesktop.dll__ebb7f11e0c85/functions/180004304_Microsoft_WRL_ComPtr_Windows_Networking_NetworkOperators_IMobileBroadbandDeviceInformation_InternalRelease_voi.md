# Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandDeviceInformation>::InternalRelease(void)

- ea: `0x180004304`
- end: `0x18000432b`
- name: `?InternalRelease@?$ComPtr@UIMobileBroadbandDeviceInformation@NetworkOperators@Networking@Windows@@@WRL@Microsoft@@IEAAKXZ`
- size: `39`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002e8c`
- `0x180006840`
- `0x1800083c0`
- `0x180008980`

## callees

- `0x180004304`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandDeviceInformation>::InternalRelease(
        __int64 *a1)
{
  __int64 result; // rax
  __int64 v3; // rcx

  result = 0;
  v3 = *a1;
  if ( v3 )
  {
    *a1 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  return result;
}

```

## disassembly

```asm
0x180004304  sub     rsp, 28h
0x180004308  mov     rdx, rcx
0x18000430b  xor     eax, eax
0x18000430d  mov     rcx, [rcx]
0x180004310  test    rcx, rcx
0x180004313  jz      short loc_180004325
0x180004315  mov     [rdx], rax
0x180004318  mov     rax, [rcx]
0x18000431b  mov     rax, [rax+10h]
0x18000431f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004324  nop
0x180004325  add     rsp, 28h
0x180004329  retn
```
