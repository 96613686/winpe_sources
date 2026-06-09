# ServiceBase::_SetShutdownRegistryKey(void)

- ea: `0x180020c7c`
- end: `0x180020d40`
- name: `?_SetShutdownRegistryKey@ServiceBase@@AEAAJXZ`
- size: `196`
- prototype: `__int64 __fastcall(ServiceBase *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180020720`

## callees

- `0x180003edc`
- `0x180020c7c`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020d1e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020d2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020d1e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020d2d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180020cfb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180020cfb`

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
0x180020c7c  mov     [rsp+arg_8], rbx
0x180020c81  push    rdi
0x180020c82  sub     rsp, 50h
0x180020c86  mov     rax, [rcx]
0x180020c89  mov     rbx, rcx
0x180020c8c  mov     rax, [rax+58h]
0x180020c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c95  mov     rdi, rax
0x180020c98  test    rax, rax
0x180020c9b  jnz     short loc_180020CB1
0x180020c9d  mov     rax, [rbx]
0x180020ca0  mov     rcx, rbx
0x180020ca3  mov     rax, [rax+40h]
0x180020ca7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020cac  jmp     loc_180020D33
0x180020cb1  lea     rcx, [rsp+58h+hKey]
0x180020cb6  mov     [rsp+58h+hKey], 0
0x180020cbf  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x180020cc4  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180020ccd  xor     r9d, r9d; lpClass
0x180020cd0  mov     [rsp+58h+phkResult], rax; phkResult
0x180020cd5  xor     r8d, r8d; Reserved
0x180020cd8  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180020ce1  mov     rdx, rdi; lpSubKey
0x180020ce4  mov     [rsp+58h+samDesired], 20019h; samDesired
0x180020cec  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180020cf3  mov     [rsp+58h+dwOptions], 1; dwOptions
0x180020cfb  call    cs:__imp_RegCreateKeyExW
0x180020d01  mov     ebx, eax
0x180020d03  test    eax, eax
0x180020d05  jle     short loc_180020D10
0x180020d07  movzx   ebx, ax
0x180020d0a  or      ebx, 80070000h
0x180020d10  mov     rcx, [rsp+58h+hKey]; hKey
0x180020d15  test    ebx, ebx
0x180020d17  jns     short loc_180020D28
0x180020d19  test    rcx, rcx
0x180020d1c  jz      short loc_180020D24
0x180020d1e  call    cs:__imp_RegCloseKey
0x180020d24  mov     eax, ebx
0x180020d26  jmp     short loc_180020D35
0x180020d28  test    rcx, rcx
0x180020d2b  jz      short loc_180020D33
0x180020d2d  call    cs:__imp_RegCloseKey
0x180020d33  xor     eax, eax
0x180020d35  mov     rbx, [rsp+58h+arg_8]
0x180020d3a  add     rsp, 50h
0x180020d3e  pop     rdi
0x180020d3f  retn
```
