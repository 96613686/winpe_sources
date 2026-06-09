# ServiceBase::_SetShutdownRegistryKey(void)

- ea: `0x180010884`
- end: `0x180010964`
- name: `?_SetShutdownRegistryKey@ServiceBase@@AEAAJXZ`
- size: `224`
- prototype: `__int64 __fastcall(ServiceBase *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000edbc`

## callees

- `0x180006244`
- `0x18000e9c4`
- `0x180010884`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010944`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010956`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010944`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010956`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010921`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010921`

## string_xrefs

- `0x1800108bc`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\servicebase\servicebase.cpp`

## pseudocode

```c
__int64 __fastcall ServiceBase::_SetShutdownRegistryKey(ServiceBase *this)
{
  const WCHAR *v2; // rax
  unsigned int v3; // ebx
  unsigned int v5; // eax
  void *v6; // rdx
  unsigned int v7; // r8d
  DWORD dwOptions; // [rsp+20h] [rbp-38h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  v2 = (const WCHAR *)(*(__int64 (__fastcall **)(ServiceBase *))(*(_QWORD *)this + 80LL))(this);
  if ( v2 )
  {
    hKey = 0;
    v5 = RegCreateKeyExW(HKEY_CURRENT_USER, v2, 0, 0, 1u, 0x20019u, 0, &hKey, 0);
    if ( v5 )
    {
      v3 = wil::details::in1diag3::Return_Win32(retaddr, v6, v7, (const char *)v5, dwOptionsa);
      if ( hKey )
        RegCloseKey(hKey);
      return v3;
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  else if ( ((*(__int64 (__fastcall **)(ServiceBase *))(*(_QWORD *)this + 56LL))(this) & 0x100) != 0 )
  {
    v3 = -2147483635;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27A,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\servicebase\\servicebase.cpp",
      (const char *)0x8000000DLL,
      dwOptions);
    return v3;
  }
  return 0;
}

```

## disassembly

```asm
0x180010884  push    rbx
0x180010886  sub     rsp, 50h
0x18001088a  mov     rax, [rcx]
0x18001088d  mov     rbx, rcx
0x180010890  mov     rax, [rax+50h]
0x180010894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010899  test    rax, rax
0x18001089c  jnz     short loc_1800108DC
0x18001089e  mov     rax, [rbx]
0x1800108a1  mov     rcx, rbx
0x1800108a4  mov     rax, [rax+38h]
0x1800108a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108ad  bt      eax, 8
0x1800108b1  jnb     loc_18001095C
0x1800108b7  mov     rcx, [rsp+58h]; this
0x1800108bc  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800108c3  mov     ebx, 8000000Dh
0x1800108c8  mov     edx, 27Ah; void *
0x1800108cd  mov     r9d, ebx; char *
0x1800108d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800108d5  mov     eax, ebx
0x1800108d7  jmp     loc_18001095E
0x1800108dc  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1800108e5  lea     rcx, [rsp+58h+hKey]
0x1800108ea  mov     [rsp+58h+phkResult], rcx; phkResult
0x1800108ef  xor     r9d, r9d; lpClass
0x1800108f2  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800108fb  xor     r8d, r8d; Reserved
0x1800108fe  mov     [rsp+58h+samDesired], 20019h; samDesired
0x180010906  mov     rdx, rax; lpSubKey
0x180010909  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180010910  mov     [rsp+58h+dwOptions], 1; unsigned int
0x180010918  mov     [rsp+58h+hKey], 0
0x180010921  call    cs:__imp_RegCreateKeyExW
0x180010927  test    eax, eax
0x180010929  jz      short loc_18001094C
0x18001092b  mov     rcx, [rsp+58h]; this
0x180010930  mov     r9d, eax; char *
0x180010933  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180010938  mov     rcx, [rsp+58h+hKey]; hKey
0x18001093d  mov     ebx, eax
0x18001093f  test    rcx, rcx
0x180010942  jz      short loc_1800108D5
0x180010944  call    cs:__imp_RegCloseKey
0x18001094a  jmp     short loc_1800108D5
0x18001094c  mov     rcx, [rsp+58h+hKey]; hKey
0x180010951  test    rcx, rcx
0x180010954  jz      short loc_18001095C
0x180010956  call    cs:__imp_RegCloseKey
0x18001095c  xor     eax, eax
0x18001095e  add     rsp, 50h
0x180010962  pop     rbx
0x180010963  retn
```
