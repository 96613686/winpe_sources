# wil::details::out_param_t<wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>>(void)

- ea: `0x18001b1b8`
- end: `0x18001b1e6`
- name: `??1?$out_param_t@V?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ`
- size: `46`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800181fc`
- `0x1800184c0`
- `0x180018778`
- `0x180018a50`
- `0x180018d24`
- `0x180018f98`
- `0x180019250`
- `0x18002f0bc`

## callees

- `0x18001b1b8`
- `0x180031010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall wil::details::out_param_t<wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>>(
        __int64 **a1)
{
  __int64 *v1; // rdx
  __int64 *result; // rax
  __int64 v3; // rcx

  if ( *((_BYTE *)a1 + 16) )
  {
    v1 = a1[1];
    result = *a1;
    v3 = **a1;
    *result = (__int64)v1;
    if ( v3 )
      return (__int64 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  return result;
}

```

## disassembly

```asm
0x18001b1b8  sub     rsp, 28h
0x18001b1bc  cmp     byte ptr [rcx+10h], 0
0x18001b1c0  jz      short loc_18001B1E1
0x18001b1c2  mov     rdx, [rcx+8]
0x18001b1c6  mov     rax, [rcx]
0x18001b1c9  mov     rcx, [rax]
0x18001b1cc  mov     [rax], rdx
0x18001b1cf  test    rcx, rcx
0x18001b1d2  jz      short loc_18001B1E1
0x18001b1d4  mov     rax, [rcx]
0x18001b1d7  mov     rax, [rax+10h]
0x18001b1db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1e0  nop
0x18001b1e1  add     rsp, 28h
0x18001b1e5  retn
```
