# Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo2>::InternalRelease(void)

- ea: `0x180001250`
- end: `0x180001283`
- name: `?InternalRelease@?$ComPtr@UIAppxBundleManifestPackageInfo2@@@WRL@Microsoft@@IEAAKXZ`
- size: `51`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `11`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001244`
- `0x180001c08`
- `0x180001fd0`
- `0x180002230`
- `0x180003b30`
- `0x180003c80`
- `0x180003ce4`
- `0x180003d44`
- `0x18000cef0`
- `0x180016908`
- `0x18001698c`

## callees

- `0x180001250`
- `0x180025010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo2>::InternalRelease(__int64 *a1)
{
  __int64 v2; // rcx

  v2 = *a1;
  if ( !v2 )
    return 0;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v2 + 16LL))(v2, 0);
}

```

## disassembly

```asm
0x180001250  sub     rsp, 38h
0x180001254  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000125d  mov     rax, rcx
0x180001260  xor     edx, edx
0x180001262  mov     rcx, [rcx]
0x180001265  test    rcx, rcx
0x180001268  jz      short loc_18000127F
0x18000126a  mov     [rax], rdx
0x18000126d  mov     rax, [rcx]
0x180001270  mov     rax, [rax+10h]
0x180001274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001279  nop
0x18000127a  add     rsp, 38h
0x18000127e  retn
0x18000127f  mov     eax, edx
0x180001281  jmp     short loc_18000127A
```
