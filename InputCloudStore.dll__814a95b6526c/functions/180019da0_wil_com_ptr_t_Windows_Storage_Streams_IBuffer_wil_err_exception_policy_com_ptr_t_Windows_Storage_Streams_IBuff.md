# wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>(Windows::Storage::Streams::IBuffer *)

- ea: `0x180019da0`
- end: `0x180019dc9`
- name: `??0?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUIBuffer@Streams@Storage@Windows@@@Z`
- size: `41`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `9`
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
- `0x180022280`
- `0x1800282c0`

## callees

- `0x180019da0`
- `0x180031010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>(
        _QWORD *a1,
        __int64 a2)
{
  *a1 = a2;
  if ( a2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  return a1;
}

```

## disassembly

```asm
0x180019da0  push    rbx
0x180019da2  sub     rsp, 20h
0x180019da6  mov     rbx, rcx
0x180019da9  mov     [rcx], rdx
0x180019dac  test    rdx, rdx
0x180019daf  jz      short loc_180019DC0
0x180019db1  mov     rax, [rdx]
0x180019db4  mov     rcx, rdx
0x180019db7  mov     rax, [rax+8]
0x180019dbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019dc0  mov     rax, rbx
0x180019dc3  add     rsp, 20h
0x180019dc7  pop     rbx
0x180019dc8  retn
```
