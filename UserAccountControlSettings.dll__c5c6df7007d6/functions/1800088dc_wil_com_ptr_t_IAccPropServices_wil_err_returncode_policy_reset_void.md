# wil::com_ptr_t<IAccPropServices,wil::err_returncode_policy>::reset(void)

- ea: `0x1800088dc`
- end: `0x180008903`
- name: `?reset@?$com_ptr_t@UIAccPropServices@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ`
- size: `39`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800078f4`
- `0x180008100`

## callees

- `0x1800088dc`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<IAccPropServices,wil::err_returncode_policy>::reset(__int64 *a1)
{
  __int64 v1; // rdx
  __int64 result; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x1800088dc  sub     rsp, 28h
0x1800088e0  mov     rdx, [rcx]
0x1800088e3  mov     qword ptr [rcx], 0
0x1800088ea  test    rdx, rdx
0x1800088ed  jz      short loc_1800088FE
0x1800088ef  mov     rax, [rdx]
0x1800088f2  mov     rcx, rdx
0x1800088f5  mov     rax, [rax+10h]
0x1800088f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088fe  add     rsp, 28h
0x180008902  retn
```
