# wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)

- ea: `0x180008ebc`
- end: `0x180008eda`
- name: `??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `61`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800097ec`
- `0x18001133c`
- `0x1800114fc`
- `0x1800116e4`
- `0x180012110`
- `0x180012b98`
- `0x18001341c`
- `0x1800136b4`
- `0x18001375c`
- `0x180013848`
- `0x180013d20`
- `0x180014e20`
- `0x180014ec8`
- `0x180014f70`
- `0x180015018`
- `0x180015cf0`
- `0x1800167ec`
- `0x180016b90`
- `0x180016c50`
- `0x180016d10`
- `0x180016dd0`
- `0x180016e90`
- `0x180018838`
- `0x180018a20`
- `0x180019124`
- `0x1800195f4`
- `0x1800196fc`
- `0x180019b30`
- `0x180019c80`
- `0x180019d30`
- `0x180019de0`
- `0x180019e90`
- `0x180019f40`
- `0x180019ff0`
- `0x18001a0c0`
- `0x18001a190`
- `0x18001a260`
- `0x18001a330`
- `0x18001a400`
- `0x18001a4d0`
- `0x18001dfb0`
- `0x18001e198`
- `0x18001f4c8`
- `0x180020460`
- `0x18002a010`
- `0x18002e730`
- `0x180032738`
- `0x180032764`
- `0x180032776`
- `0x180032a58`

## callees

- `0x180008ebc`
- `0x180035010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(
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
0x180008ebc  sub     rsp, 28h
0x180008ec0  mov     rcx, [rcx]
0x180008ec3  test    rcx, rcx
0x180008ec6  jz      short loc_180008ED5
0x180008ec8  mov     rax, [rcx]
0x180008ecb  mov     rax, [rax+10h]
0x180008ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ed4  nop
0x180008ed5  add     rsp, 28h
0x180008ed9  retn
```
