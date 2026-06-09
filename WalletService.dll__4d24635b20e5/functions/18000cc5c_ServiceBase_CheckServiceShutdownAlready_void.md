# ServiceBase::_CheckServiceShutdownAlready(void)

- ea: `0x18000cc5c`
- end: `0x18000cd23`
- name: `?_CheckServiceShutdownAlready@ServiceBase@@AEAAJXZ`
- size: `199`
- prototype: `__int64 __fastcall(ServiceBase *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000cf58`

## callees

- `0x18000c928`
- `0x18000cc5c`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ccf2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cd03`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cd12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ccf2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cd03`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cd12`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cccb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cccb`

## pseudocode

```c
__int64 __fastcall ServiceBase::_CheckServiceShutdownAlready(ServiceBase *this)
{
  const WCHAR *v1; // rbx
  HKEY *phkResult; // rax
  LSTATUS v4; // eax
  signed int v5; // ebx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = (HKEY)this;
  v1 = (const WCHAR *)(*(__int64 (__fastcall **)(void *))(g_rwService + 88LL))(&g_rwService);
  if ( !v1 )
  {
    (*(void (__fastcall **)(void *))(g_rwService + 64LL))(&g_rwService);
    return 0;
  }
  hKey = 0;
  phkResult = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&hKey);
  v4 = RegOpenKeyExW(HKEY_CURRENT_USER, v1, 0, 0x20019u, phkResult);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 == -2147024894 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  if ( v5 >= 0 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return 2147943515LL;
  }
  else
  {
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v5;
  }
}

```

## disassembly

```asm
0x18000cc5c  mov     [rsp+hKey], rcx
0x18000cc61  push    rbx
0x18000cc62  sub     rsp, 30h
0x18000cc66  mov     rax, cs:?g_rwService@@3VRWService@@A; RWService g_rwService
0x18000cc6d  lea     rcx, ?g_rwService@@3VRWService@@A; RWService g_rwService
0x18000cc74  mov     rax, [rax+58h]
0x18000cc78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc7d  mov     rbx, rax
0x18000cc80  test    rax, rax
0x18000cc83  jnz     short loc_18000CCA0
0x18000cc85  mov     rax, cs:?g_rwService@@3VRWService@@A; RWService g_rwService
0x18000cc8c  lea     rcx, ?g_rwService@@3VRWService@@A; RWService g_rwService
0x18000cc93  mov     rax, [rax+40h]
0x18000cc97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc9c  xor     eax, eax
0x18000cc9e  jmp     short loc_18000CD1D
0x18000cca0  lea     rcx, [rsp+38h+hKey]
0x18000cca5  mov     [rsp+38h+hKey], 0
0x18000ccae  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18000ccb3  mov     r9d, 20019h; samDesired
0x18000ccb9  mov     [rsp+38h+phkResult], rax; phkResult
0x18000ccbe  xor     r8d, r8d; ulOptions
0x18000ccc1  mov     rdx, rbx; lpSubKey
0x18000ccc4  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000cccb  call    cs:__imp_RegOpenKeyExW
0x18000ccd1  mov     ebx, eax
0x18000ccd3  test    eax, eax
0x18000ccd5  jle     short loc_18000CCE0
0x18000ccd7  movzx   ebx, ax
0x18000ccda  or      ebx, 80070000h
0x18000cce0  mov     rcx, [rsp+38h+hKey]; hKey
0x18000cce5  cmp     ebx, 80070002h
0x18000cceb  jnz     short loc_18000CCFA
0x18000cced  test    rcx, rcx
0x18000ccf0  jz      short loc_18000CC9C
0x18000ccf2  call    cs:__imp_RegCloseKey
0x18000ccf8  jmp     short loc_18000CC9C
0x18000ccfa  test    ebx, ebx
0x18000ccfc  jns     short loc_18000CD0D
0x18000ccfe  test    rcx, rcx
0x18000cd01  jz      short loc_18000CD09
0x18000cd03  call    cs:__imp_RegCloseKey
0x18000cd09  mov     eax, ebx
0x18000cd0b  jmp     short loc_18000CD1D
0x18000cd0d  test    rcx, rcx
0x18000cd10  jz      short loc_18000CD18
0x18000cd12  call    cs:__imp_RegCloseKey
0x18000cd18  mov     eax, 8007045Bh
0x18000cd1d  add     rsp, 30h
0x18000cd21  pop     rbx
0x18000cd22  retn
```
