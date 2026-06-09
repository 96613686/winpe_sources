# AccProvpInitProviders

- ea: `0x18002d8a0`
- end: `0x18002db00`
- name: `AccProvpInitProviders`
- size: `608`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `20`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18002d4d0`
- `0x18004f58c`
- `0x18004f77c`
- `0x18004f89c`
- `0x18004fa5c`
- `0x18004fb00`
- `0x18004fb70`
- `0x18004fce0`
- `0x180050120`
- `0x180050260`
- `0x180050500`
- `0x180050820`
- `0x180050950`
- `0x180050bd0`
- `0x180051010`
- `0x1800514d0`
- `0x180051820`
- `0x180051c70`
- `0x180051fd0`
- `0x180052240`

## callees

- `0x18002d2fc`
- `0x18002d8a0`
- `0x18002db08`
- `0x18002dc7c`
- `0x18002dcc8`

## import_xrefs

- `msvcrt!wcschr` at `0x18002d9e4`
- `msvcrt!wcschr` at `0x18002dab3`
- `msvcrt!wcschr` at `0x18002d9e4`
- `msvcrt!wcschr` at `0x18002dab3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002da6f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002da6f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d921`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d921`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d98a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d98a`
- `KERNEL32!LocalFree` at `0x18002d975`
- `KERNEL32!LocalFree` at `0x18002d975`
- `KERNEL32!EnterCriticalSection` at `0x18002d8c4`
- `KERNEL32!EnterCriticalSection` at `0x18002d8c4`
- `KERNEL32!LeaveCriticalSection` at `0x18002d8e3`
- `KERNEL32!LeaveCriticalSection` at `0x18002d8e3`

## string_xrefs

- `0x18002d913`: `System\CurrentControlSet\Control\LSA\AccessProviders`
- `0x18002da5d`: `RequireUniqueAccessibility`

## pseudocode

```c
__int64 __fastcall AccProvpInitProviders(__int64 a1)
{
  unsigned int StringFromRegistry; // ebx
  __int64 v3; // rax
  __int64 Data; // [rsp+80h] [rbp+40h]
  HKEY hKey; // [rsp+98h] [rbp+58h] BYREF

  Data = a1;
  hKey = 0;
  EnterCriticalSection(&gAccProviders);
  if ( (qword_1800B26E8 & 2) != 0 )
  {
    StringFromRegistry = 0;
  }
  else
  {
    StringFromRegistry = RegOpenKeyExW(
                           HKEY_LOCAL_MACHINE,
                           L"System\\CurrentControlSet\\Control\\LSA\\AccessProviders",
                           0,
                           0x20019u,
                           &hKey);
    if ( !StringFromRegistry )
    {
      StringFromRegistry = AccProvpGetStringFromRegistry(hKey, L"ProviderOrder");
      if ( !StringFromRegistry )
      {
        v3 = -1;
        do
          ++v3;
        while ( *(_WORD *)(2 * v3) );
        StringFromRegistry = 13;
        LocalFree(0);
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  LeaveCriticalSection(&gAccProviders);
  return StringFromRegistry;
}

```

## disassembly

```asm
0x18002d8a0  mov     [rsp-38h+Data], rcx
0x18002d8a5  push    rbp
0x18002d8a6  push    rbx
0x18002d8a7  push    rsi
0x18002d8a8  push    rdi
0x18002d8a9  push    r12
0x18002d8ab  push    r13
0x18002d8ad  push    r14
0x18002d8af  mov     rbp, rsp
0x18002d8b2  sub     rsp, 40h
0x18002d8b6  xor     r12d, r12d
0x18002d8b9  lea     rcx, gAccProviders; lpCriticalSection
0x18002d8c0  mov     [rbp+hKey], r12
0x18002d8c4  call    cs:__imp_EnterCriticalSection
0x18002d8cb  nop     dword ptr [rax+rax+00h]
0x18002d8d0  test    byte ptr cs:qword_1800B26E8, 2
0x18002d8d7  jz      short loc_18002D901
0x18002d8d9  mov     ebx, r12d
0x18002d8dc  lea     rcx, gAccProviders; lpCriticalSection
0x18002d8e3  call    cs:__imp_LeaveCriticalSection
0x18002d8ea  nop     dword ptr [rax+rax+00h]
0x18002d8ef  mov     eax, ebx
0x18002d8f1  add     rsp, 40h
0x18002d8f5  pop     r14
0x18002d8f7  pop     r13
0x18002d8f9  pop     r12
0x18002d8fb  pop     rdi
0x18002d8fc  pop     rsi
0x18002d8fd  pop     rbx
0x18002d8fe  pop     rbp
0x18002d8ff  retn
0x18002d901  lea     rax, [rbp+hKey]
0x18002d905  mov     r9d, 20019h; samDesired
0x18002d90b  xor     r8d, r8d; ulOptions
0x18002d90e  mov     [rsp+40h+phkResult], rax; phkResult
0x18002d913  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\LSA"...
0x18002d91a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d921  call    cs:__imp_RegOpenKeyExW
0x18002d928  nop     dword ptr [rax+rax+00h]
0x18002d92d  mov     ebx, eax
0x18002d92f  test    eax, eax
0x18002d931  jnz     short loc_18002D981
0x18002d933  mov     rcx, [rbp+hKey]; hKey
0x18002d937  lea     r8, [rbp+hMem]
0x18002d93b  lea     rdx, aProviderorder; "ProviderOrder"
0x18002d942  mov     [rbp+hMem], r12
0x18002d946  call    AccProvpGetStringFromRegistry
0x18002d94b  mov     ebx, eax
0x18002d94d  test    eax, eax
0x18002d94f  jnz     short loc_18002D981
0x18002d951  mov     rcx, [rbp+hMem]; Str
0x18002d955  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002d959  inc     rax
0x18002d95c  cmp     [rcx+rax*2], r12w
0x18002d961  jnz     short loc_18002D959
0x18002d963  test    rax, rax
0x18002d966  jnz     loc_18002DA9C
0x18002d96c  mov     ebx, 0Dh
0x18002d971  mov     rcx, [rbp+hMem]; hMem
0x18002d975  call    cs:__imp_LocalFree
0x18002d97c  nop     dword ptr [rax+rax+00h]
0x18002d981  mov     rcx, [rbp+hKey]; hKey
0x18002d985  test    rcx, rcx
0x18002d988  jz      short loc_18002D996
0x18002d98a  call    cs:__imp_RegCloseKey
0x18002d991  nop     dword ptr [rax+rax+00h]
0x18002d996  test    ebx, ebx
0x18002d998  jnz     loc_18002D8DC
0x18002d99e  call    AccProvpLoadMartaFunctions
0x18002d9a3  mov     ebx, eax
0x18002d9a5  test    eax, eax
0x18002d9a7  jnz     loc_18002D8DC
0x18002d9ad  or      dword ptr cs:qword_1800B26E8, 2
0x18002d9b4  jmp     loc_18002D8DC
0x18002d9b9  test    ebx, ebx
0x18002d9bb  jz      short loc_18002D96C
0x18002d9bd  mov     dword ptr cs:qword_1800B26E8+4, ebx
0x18002d9c3  call    AccProvpAllocateProviderList
0x18002d9c8  mov     ebx, eax
0x18002d9ca  test    eax, eax
0x18002d9cc  jnz     short loc_18002D971
0x18002d9ce  mov     rsi, [rbp+hMem]
0x18002d9d2  mov     r14d, r12d
0x18002d9d5  test    rsi, rsi
0x18002d9d8  jz      loc_18002DA92
0x18002d9de  mov     edx, r13d; Ch
0x18002d9e1  mov     rcx, rsi; Str
0x18002d9e4  call    cs:__imp_wcschr
0x18002d9eb  nop     dword ptr [rax+rax+00h]
0x18002d9f0  mov     rdi, rax
0x18002d9f3  test    rax, rax
0x18002d9f6  jnz     loc_18002DAD4
0x18002d9fc  mov     ecx, r14d
0x18002d9ff  mov     rdx, rsi
0x18002da02  lea     r8, [rcx+rcx*2]
0x18002da06  mov     rcx, [rbp+hKey]
0x18002da0a  shl     r8, 6
0x18002da0e  add     r8, cs:qword_1800B26F0
0x18002da15  call    AccProvpLoadProviderDef
0x18002da1a  test    rdi, rdi
0x18002da1d  jnz     loc_18002DADD
0x18002da23  test    eax, eax
0x18002da25  lea     ecx, [r14+1]
0x18002da29  mov     rsi, rdi
0x18002da2c  cmovnz  ecx, r14d
0x18002da30  mov     r14d, ecx
0x18002da33  test    rdi, rdi
0x18002da36  jnz     short loc_18002D9DE
0x18002da38  test    ecx, ecx
0x18002da3a  jz      short loc_18002DA92
0x18002da3c  mov     rcx, [rbp+hKey]; hKey
0x18002da40  lea     rax, [rbp+cbData]
0x18002da44  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18002da49  lea     r9, [rbp+Type]; lpType
0x18002da4d  lea     rax, [rbp+Data]
0x18002da51  mov     [rbp+Type], r12d
0x18002da55  xor     r8d, r8d; lpReserved
0x18002da58  mov     [rsp+40h+phkResult], rax; lpData
0x18002da5d  lea     rdx, aRequireuniquea; "RequireUniqueAccessibility"
0x18002da64  mov     dword ptr [rbp+Data], r12d
0x18002da68  mov     [rbp+cbData], 4
0x18002da6f  call    cs:__imp_RegQueryValueExW
0x18002da76  nop     dword ptr [rax+rax+00h]
0x18002da7b  mov     ebx, eax
0x18002da7d  test    eax, eax
0x18002da7f  jz      short loc_18002DAEA
0x18002da81  cmp     eax, 2
0x18002da84  jnz     loc_18002D971
0x18002da8a  mov     ebx, r12d
0x18002da8d  jmp     loc_18002D971
0x18002da92  mov     ebx, 4B4h
0x18002da97  jmp     loc_18002D971
0x18002da9c  mov     ebx, r12d
0x18002da9f  test    rcx, rcx
0x18002daa2  jz      loc_18002D96C
0x18002daa8  mov     r13d, 2Ch ; ','
0x18002daae  mov     edx, r13d; Ch
0x18002dab1  inc     ebx
0x18002dab3  call    cs:__imp_wcschr
0x18002daba  nop     dword ptr [rax+rax+00h]
0x18002dabf  test    rax, rax
0x18002dac2  lea     rcx, [rax+2]
0x18002dac6  cmovz   rcx, rax
0x18002daca  test    rcx, rcx
0x18002dacd  jnz     short loc_18002DAAE
0x18002dacf  jmp     loc_18002D9B9
0x18002dad4  mov     [rax], r12w
0x18002dad8  jmp     loc_18002D9FC
0x18002dadd  mov     [rdi], r13w
0x18002dae1  add     rdi, 2
0x18002dae5  jmp     loc_18002DA23
0x18002daea  cmp     dword ptr [rbp+Data], 1
0x18002daee  jnz     loc_18002D971
0x18002daf4  or      dword ptr cs:qword_1800B26E8, 1
0x18002dafb  jmp     loc_18002D971
```
