# Microsoft::WRL::ComPtr<IMarshal>::ReleaseAndGetAddressOf(void)

- ea: `0x1800108b0`
- end: `0x1800108cd`
- name: `?ReleaseAndGetAddressOf@?$ComPtr@UIMarshal@@@WRL@Microsoft@@QEAAPEAPEAUIMarshal@@XZ`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000cd44`

## callees

- `0x18000edd8`

## pseudocode

```c
__int64 *__fastcall Microsoft::WRL::ComPtr<IMarshal>::ReleaseAndGetAddressOf(__int64 *a1)
{
  Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IShellExperienceManagerFactory>::InternalRelease(a1);
  return a1;
}

```

## disassembly

```asm
0x1800108b0  mov     [rsp+arg_0], rcx
0x1800108b5  sub     rsp, 28h
0x1800108b9  mov     rcx, [rsp+28h+arg_0]
0x1800108be  call    ?InternalRelease@?$ComPtr@UIShellExperienceManagerFactory@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IShellExperienceManagerFactory>::InternalRelease(void)
0x1800108c3  mov     rax, [rsp+28h+arg_0]
0x1800108c8  add     rsp, 28h
0x1800108cc  retn
```
