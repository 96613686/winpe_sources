# wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(void)

- ea: `0x18001cea8`
- end: `0x18001cec6`
- name: `??1?$com_ptr_t@UIWebAccountProvider3@Credentials@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `17`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001dbe0`
- `0x18001e4f0`
- `0x18001f668`
- `0x180020030`
- `0x180033178`
- `0x18004518c`
- `0x18004c1eb`
- `0x18004c1fd`
- `0x18004c221`
- `0x18004c2a7`
- `0x18004c2b9`
- `0x18004c2ef`
- `0x18004c301`
- `0x18004c325`
- `0x18004c337`
- `0x18004ca63`
- `0x18004cae2`

## callees

- `0x18001cea8`
- `0x18004d010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(
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
0x18001cea8  sub     rsp, 28h
0x18001ceac  mov     rcx, [rcx]
0x18001ceaf  test    rcx, rcx
0x18001ceb2  jz      short loc_18001CEC1
0x18001ceb4  mov     rax, [rcx]
0x18001ceb7  mov     rax, [rax+10h]
0x18001cebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cec0  nop
0x18001cec1  add     rsp, 28h
0x18001cec5  retn
```
