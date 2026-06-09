# RegistryKey::RegistryKey(HKEY__ *)

- ea: `0x180005328`
- end: `0x180005366`
- name: `??0RegistryKey@@QEAA@PEAUHKEY__@@@Z`
- size: `62`
- prototype: `RegistryKey *__fastcall(RegistryKey *__hidden this, HKEY)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180006208`
- `0x18000e0d8`
- `0x18000e90c`
- `0x1800102e8`
- `0x180010c9c`

## callees

- `0x180005328`
- `0x1800065d4`
- `0x18000895c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005342`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005342`

## pseudocode

```c
RegistryKey *__fastcall RegistryKey::RegistryKey(RegistryKey *this, HKEY a2)
{
  DWORD LastError; // eax
  _BYTE pExceptionObject[216]; // [rsp+20h] [rbp-D8h] BYREF

  if ( !a2 )
  {
    LastError = GetLastError();
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, LastError);
    throw (Win32Exception *)pExceptionObject;
  }
  *(_QWORD *)this = a2;
  return this;
}

```

## disassembly

```asm
0x180005328  sub     rsp, 0F8h
0x18000532f  test    rdx, rdx
0x180005332  jz      short loc_180005342
0x180005334  mov     [rcx], rdx
0x180005337  mov     rax, rcx
0x18000533a  add     rsp, 0F8h
0x180005341  retn
0x180005342  call    cs:__imp_GetLastError
0x180005348  mov     edx, eax; int
0x18000534a  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x18000534f  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x180005354  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x18000535b  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180005360  call    _CxxThrowException_0
```
