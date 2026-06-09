# wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(void)

- ea: `0x180010330`
- end: `0x18001034e`
- name: `??1?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `13`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001442c`
- `0x180014550`
- `0x180014994`
- `0x180014adc`
- `0x180014cd0`
- `0x18002b39a`
- `0x18002b3d0`
- `0x18002b3e2`
- `0x18002b406`
- `0x18002b418`
- `0x18002b44e`
- `0x18002b460`
- `0x18002b484`

## callees

- `0x180010330`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(
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
0x180010330  sub     rsp, 28h
0x180010334  mov     rcx, [rcx]
0x180010337  test    rcx, rcx
0x18001033a  jz      short loc_180010349
0x18001033c  mov     rax, [rcx]
0x18001033f  mov     rax, [rax+10h]
0x180010343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010348  nop
0x180010349  add     rsp, 28h
0x18001034d  retn
```
