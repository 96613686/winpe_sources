# Windows::Internal::ServiceModule::DecrementObjectCount(void)

- ea: `0x180004f20`
- end: `0x180004f5b`
- name: `?DecrementObjectCount@ServiceModule@Internal@Windows@@UEAAKXZ`
- size: `59`
- prototype: `__int64 __fastcall(Windows::Internal::ServiceModule *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004f70`

## callees

- `0x180004f20`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoReleaseServerProcess` at `0x180004f2d`
- `api-ms-win-core-com-l1-1-0!CoReleaseServerProcess` at `0x180004f2d`

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
0x180004f20  mov     [rsp+arg_0], rbx
0x180004f25  push    rdi
0x180004f26  sub     rsp, 20h
0x180004f2a  mov     rdi, rcx
0x180004f2d  call    cs:__imp_CoReleaseServerProcess
0x180004f33  mov     ebx, eax
0x180004f35  test    eax, eax
0x180004f37  jnz     short loc_180004F4E
0x180004f39  mov     rcx, [rdi+30h]
0x180004f3d  test    rcx, rcx
0x180004f40  jz      short loc_180004F4E
0x180004f42  mov     rdx, [rcx]
0x180004f45  mov     rax, [rdx+8]
0x180004f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f4e  mov     eax, ebx
0x180004f50  mov     rbx, [rsp+28h+arg_0]
0x180004f55  add     rsp, 20h
0x180004f59  pop     rdi
0x180004f5a  retn
```
