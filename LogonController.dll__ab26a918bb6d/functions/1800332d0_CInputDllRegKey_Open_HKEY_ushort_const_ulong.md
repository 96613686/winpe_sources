# CInputDllRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x1800332d0`
- end: `0x1800333ce`
- name: `?Open@CInputDllRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `254`
- prototype: `__int64 __fastcall(CInputDllRegKey *this, HKEY, const unsigned __int16 *, REGSAM)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180002f10`
- `0x180005500`
- `0x180006d90`
- `0x180032c44`
- `0x180038170`

## callees

- `0x1800332d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033319`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033319`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033331`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003334c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033331`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003334c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800333a2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800333a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800333bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800333bb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInputDllRegKey::Open(CInputDllRegKey *this, HKEY a2, const unsigned __int16 *a3, REGSAM a4)
{
  HKEY v6; // rsi
  LSTATUS v8; // eax
  unsigned int v9; // ebx
  HKEY v10; // rcx
  HKEY phkResult; // [rsp+50h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-40h] BYREF
  DWORD dwDisposition; // [rsp+A8h] [rbp+10h] BYREF

  phkResult = 0;
  hKey = 0;
  v6 = a2;
  if ( a2 == HKEY_CURRENT_USER && !RegOpenCurrentUser(a4, &hKey) )
    v6 = hKey;
  v8 = RegOpenKeyExW(v6, a3, 0, a4, &phkResult);
  v9 = v8;
  if ( !v8
    || v8 == 5 && (dwDisposition = 0, (v9 = RegCreateKeyExW(v6, a3, 0, 0, 4u, a4, 0, &phkResult, &dwDisposition)) == 0) )
  {
    v10 = (HKEY)*((_QWORD *)this + 1);
    v9 = 0;
    if ( v10 )
      v9 = RegCloseKey(v10);
    *((_QWORD *)this + 1) = phkResult;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x1800332d0  push    rbx
0x1800332d2  push    rbp
0x1800332d3  push    rsi
0x1800332d4  push    rdi
0x1800332d5  push    r14
0x1800332d7  push    r15
0x1800332d9  sub     rsp, 68h
0x1800332dd  xor     r15d, r15d
0x1800332e0  mov     ebp, r9d
0x1800332e3  mov     [rsp+98h+var_48], r15
0x1800332e8  mov     r14, r8
0x1800332eb  mov     [rsp+98h+hKey], r15
0x1800332f0  mov     rsi, rdx
0x1800332f3  mov     rdi, rcx
0x1800332f6  cmp     rdx, 0FFFFFFFF80000001h
0x1800332fd  jz      loc_1800333B4
0x180033303  lea     rax, [rsp+98h+var_48]
0x180033308  mov     r9d, ebp; samDesired
0x18003330b  xor     r8d, r8d; ulOptions
0x18003330e  mov     [rsp+98h+phkResult], rax; phkResult
0x180033313  mov     rdx, r14; lpSubKey
0x180033316  mov     rcx, rsi; hKey
0x180033319  call    cs:__imp_RegOpenKeyExW
0x18003331f  mov     ebx, eax
0x180033321  test    eax, eax
0x180033323  jnz     short loc_180033361
0x180033325  mov     rcx, [rdi+8]; hKey
0x180033329  mov     ebx, r15d
0x18003332c  test    rcx, rcx
0x18003332f  jz      short loc_180033339
0x180033331  call    cs:__imp_RegCloseKey
0x180033337  mov     ebx, eax
0x180033339  mov     rax, [rsp+98h+var_48]
0x18003333e  mov     [rdi+8], rax
0x180033342  mov     rcx, [rsp+98h+hKey]; hKey
0x180033347  test    rcx, rcx
0x18003334a  jz      short loc_180033352
0x18003334c  call    cs:__imp_RegCloseKey
0x180033352  mov     eax, ebx
0x180033354  add     rsp, 68h
0x180033358  pop     r15
0x18003335a  pop     r14
0x18003335c  pop     rdi
0x18003335d  pop     rsi
0x18003335e  pop     rbp
0x18003335f  pop     rbx
0x180033360  retn
0x180033361  cmp     eax, 5
0x180033364  jnz     short loc_180033342
0x180033366  lea     rax, [rsp+98h+dwDisposition]
0x18003336e  mov     [rsp+98h+dwDisposition], r15d
0x180033376  mov     [rsp+98h+lpdwDisposition], rax; lpdwDisposition
0x18003337b  xor     r9d, r9d; lpClass
0x18003337e  lea     rax, [rsp+98h+var_48]
0x180033383  xor     r8d, r8d; Reserved
0x180033386  mov     [rsp+98h+var_60], rax; phkResult
0x18003338b  mov     rdx, r14; lpSubKey
0x18003338e  mov     [rsp+98h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180033393  mov     rcx, rsi; hKey
0x180033396  mov     [rsp+98h+samDesired], ebp; samDesired
0x18003339a  mov     dword ptr [rsp+98h+phkResult], 4; dwOptions
0x1800333a2  call    cs:__imp_RegCreateKeyExW
0x1800333a8  mov     ebx, eax
0x1800333aa  test    eax, eax
0x1800333ac  jz      loc_180033325
0x1800333b2  jmp     short loc_180033342
0x1800333b4  lea     rdx, [rsp+98h+hKey]; phkResult
0x1800333b9  mov     ecx, ebp; samDesired
0x1800333bb  call    cs:__imp_RegOpenCurrentUser
0x1800333c1  test    eax, eax
0x1800333c3  cmovz   rsi, [rsp+98h+hKey]
0x1800333c9  jmp     loc_180033303
```
