# Windows::Internal::ServiceModule::DecrementObjectCount(void)

- ea: `0x180004d50`
- end: `0x180004d8b`
- name: `?DecrementObjectCount@ServiceModule@Internal@Windows@@UEAAKXZ`
- size: `59`
- prototype: `__int64 __fastcall(Windows::Internal::ServiceModule *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004da0`

## callees

- `0x180004d50`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoReleaseServerProcess` at `0x180004d5d`
- `api-ms-win-core-com-l1-1-0!CoReleaseServerProcess` at `0x180004d5d`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ServiceModule::DecrementObjectCount(Windows::Internal::ServiceModule *this)
{
  ULONG v2; // ebx
  __int64 v3; // rcx

  v2 = CoReleaseServerProcess();
  if ( !v2 )
  {
    v3 = *((_QWORD *)this + 6);
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
  }
  return v2;
}

```

## disassembly

```asm
0x180004d50  mov     [rsp+arg_0], rbx
0x180004d55  push    rdi
0x180004d56  sub     rsp, 20h
0x180004d5a  mov     rdi, rcx
0x180004d5d  call    cs:__imp_CoReleaseServerProcess
0x180004d63  mov     ebx, eax
0x180004d65  test    eax, eax
0x180004d67  jnz     short loc_180004D7E
0x180004d69  mov     rcx, [rdi+30h]
0x180004d6d  test    rcx, rcx
0x180004d70  jz      short loc_180004D7E
0x180004d72  mov     rdx, [rcx]
0x180004d75  mov     rax, [rdx+8]
0x180004d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d7e  mov     eax, ebx
0x180004d80  mov     rbx, [rsp+28h+arg_0]
0x180004d85  add     rsp, 20h
0x180004d89  pop     rdi
0x180004d8a  retn
```
