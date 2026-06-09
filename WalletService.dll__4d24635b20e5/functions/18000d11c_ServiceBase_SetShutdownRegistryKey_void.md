# ServiceBase::_SetShutdownRegistryKey(void)

- ea: `0x18000d11c`
- end: `0x18000d1e0`
- name: `?_SetShutdownRegistryKey@ServiceBase@@AEAAJXZ`
- size: `196`
- prototype: `__int64 __fastcall(ServiceBase *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000cba4`

## callees

- `0x18000c928`
- `0x18000d11c`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d1be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d1cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d1be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d1cd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000d19b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000d19b`

## pseudocode

```c
__int64 __fastcall ServiceBase::_SetShutdownRegistryKey(ServiceBase *this)
{
  const WCHAR *v2; // rdi
  HKEY *phkResult; // rax
  LSTATUS Key; // eax
  signed int v5; // ebx
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  v2 = (const WCHAR *)(*(__int64 (__fastcall **)(ServiceBase *))(*(_QWORD *)this + 88LL))(this);
  if ( !v2 )
  {
    (*(void (__fastcall **)(ServiceBase *))(*(_QWORD *)this + 64LL))(this);
    return 0;
  }
  hKey = 0;
  phkResult = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&hKey);
  Key = RegCreateKeyExW(HKEY_CURRENT_USER, v2, 0, 0, 1u, 0x20019u, 0, phkResult, 0);
  v5 = Key;
  if ( Key > 0 )
    v5 = (unsigned __int16)Key | 0x80070000;
  if ( v5 >= 0 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000d11c  mov     [rsp+arg_8], rbx
0x18000d121  push    rdi
0x18000d122  sub     rsp, 50h
0x18000d126  mov     rax, [rcx]
0x18000d129  mov     rbx, rcx
0x18000d12c  mov     rax, [rax+58h]
0x18000d130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d135  mov     rdi, rax
0x18000d138  test    rax, rax
0x18000d13b  jnz     short loc_18000D151
0x18000d13d  mov     rax, [rbx]
0x18000d140  mov     rcx, rbx
0x18000d143  mov     rax, [rax+40h]
0x18000d147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d14c  jmp     loc_18000D1D3
0x18000d151  lea     rcx, [rsp+58h+hKey]
0x18000d156  mov     [rsp+58h+hKey], 0
0x18000d15f  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18000d164  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18000d16d  xor     r9d, r9d; lpClass
0x18000d170  mov     [rsp+58h+phkResult], rax; phkResult
0x18000d175  xor     r8d, r8d; Reserved
0x18000d178  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000d181  mov     rdx, rdi; lpSubKey
0x18000d184  mov     [rsp+58h+samDesired], 20019h; samDesired
0x18000d18c  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000d193  mov     [rsp+58h+dwOptions], 1; dwOptions
0x18000d19b  call    cs:__imp_RegCreateKeyExW
0x18000d1a1  mov     ebx, eax
0x18000d1a3  test    eax, eax
0x18000d1a5  jle     short loc_18000D1B0
0x18000d1a7  movzx   ebx, ax
0x18000d1aa  or      ebx, 80070000h
0x18000d1b0  mov     rcx, [rsp+58h+hKey]; hKey
0x18000d1b5  test    ebx, ebx
0x18000d1b7  jns     short loc_18000D1C8
0x18000d1b9  test    rcx, rcx
0x18000d1bc  jz      short loc_18000D1C4
0x18000d1be  call    cs:__imp_RegCloseKey
0x18000d1c4  mov     eax, ebx
0x18000d1c6  jmp     short loc_18000D1D5
0x18000d1c8  test    rcx, rcx
0x18000d1cb  jz      short loc_18000D1D3
0x18000d1cd  call    cs:__imp_RegCloseKey
0x18000d1d3  xor     eax, eax
0x18000d1d5  mov     rbx, [rsp+58h+arg_8]
0x18000d1da  add     rsp, 50h
0x18000d1de  pop     rdi
0x18000d1df  retn
```
