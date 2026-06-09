# LAZY_WRITER::GetInterval(void)

- ea: `0x180001584`
- end: `0x1800015fd`
- name: `?GetInterval@LAZY_WRITER@@QEAAJXZ`
- size: `121`
- prototype: `__int64 __fastcall(LAZY_WRITER *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18000147c`

## callees

- `0x180001584`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800015f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800015f5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800039e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800039e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800015d1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800015d1`

## string_xrefs

- `0x1800015ca`: `System\CurrentControlSet\Services\IISADMIN\Parameters`
- `0x1800039da`: `LazyWriteTime`

## pseudocode

```c
__int64 __fastcall LAZY_WRITER::GetInterval(LAZY_WRITER *this)
{
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+18h] BYREF
  int Data; // [rsp+60h] [rbp+20h] BYREF
  DWORD Type; // [rsp+68h] [rbp+28h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  Data = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\IISADMIN\\Parameters",
          0,
          0x20019u,
          &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"LazyWriteTime", 0, &Type, (LPBYTE)&Data, &cbData) )
      *(_DWORD *)this = Data;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180001584  mov     [rsp-8+arg_0], rbx
0x180001589  push    rbp
0x18000158a  mov     rbp, rsp
0x18000158d  sub     rsp, 40h
0x180001591  mov     rbx, rcx
0x180001594  mov     [rbp+hKey], 0
0x18000159c  lea     rax, [rbp+hKey]
0x1800015a0  mov     [rbp+Type], 0
0x1800015a7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800015ae  mov     [rsp+40h+phkResult], rax; phkResult
0x1800015b3  mov     r9d, 20019h; samDesired
0x1800015b9  mov     [rbp+cbData], 0
0x1800015c0  xor     r8d, r8d; ulOptions
0x1800015c3  mov     [rbp+Data], 0
0x1800015ca  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\II"...
0x1800015d1  call    cs:__imp_RegOpenKeyExW
0x1800015d7  test    eax, eax
0x1800015d9  jz      loc_1800039B6
0x1800015df  mov     rcx, [rbp+hKey]; hKey
0x1800015e3  test    rcx, rcx
0x1800015e6  jnz     short loc_1800015F5
0x1800015e8  mov     rbx, [rsp+40h+arg_0]
0x1800015ed  xor     eax, eax
0x1800015ef  add     rsp, 40h
0x1800015f3  pop     rbp
0x1800015f4  retn
0x1800015f5  call    cs:__imp_RegCloseKey
0x1800015fb  jmp     short loc_1800015E8
0x1800039b6  mov     rcx, [rbp+hKey]; hKey
0x1800039ba  lea     rax, [rbp+cbData]
0x1800039be  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800039c3  lea     r9, [rbp+Type]; lpType
0x1800039c7  lea     rax, [rbp+Data]
0x1800039cb  mov     [rbp+cbData], 4
0x1800039d2  xor     r8d, r8d; lpReserved
0x1800039d5  mov     [rsp+40h+phkResult], rax; lpData
0x1800039da  lea     rdx, aLazywritetime; "LazyWriteTime"
0x1800039e1  call    cs:__imp_RegQueryValueExW
0x1800039e7  test    eax, eax
0x1800039e9  jnz     loc_1800015DF
0x1800039ef  mov     eax, [rbp+Data]
0x1800039f2  mov     [rbx], eax
0x1800039f4  jmp     loc_1800015DF
```
