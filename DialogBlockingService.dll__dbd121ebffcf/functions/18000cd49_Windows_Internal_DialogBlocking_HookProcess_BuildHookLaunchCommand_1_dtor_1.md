# _Windows::Internal::DialogBlocking::HookProcess::BuildHookLaunchCommand_::_1_::dtor$1

- ea: `0x18000cd49`
- end: `0x18000cd6f`
- name: `_Windows::Internal::DialogBlocking::HookProcess::BuildHookLaunchCommand_::_1_::dtor$1`
- size: `38`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180008810`
- `0x18000cd49`

## pseudocode

```c
void __fastcall Windows::Internal::DialogBlocking::HookProcess::BuildHookLaunchCommand_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 32) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::~NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>(*(_QWORD *)(a2 + 48));
  }
}

```

## disassembly

```asm
0x18000cd49  push    rbp
0x18000cd4b  sub     rsp, 20h
0x18000cd4f  mov     rbp, rdx
0x18000cd52  mov     eax, [rbp+20h]
0x18000cd55  and     eax, 1
0x18000cd58  test    eax, eax
0x18000cd5a  jz      short loc_18000CD69
0x18000cd5c  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x18000cd60  mov     rcx, [rbp+30h]
0x18000cd64  call    ??1?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::~NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>(void)
0x18000cd69  add     rsp, 20h
0x18000cd6d  pop     rbp
0x18000cd6e  retn
```
