# StartupDB::StartupApproval::Initialize(HKEY__ *,ushort const *,ushort const *,ulong)

- ea: `0x180003c04`
- end: `0x180003cf6`
- name: `?Initialize@StartupApproval@StartupDB@@QEAAJPEAUHKEY__@@PEBG1K@Z`
- size: `242`
- prototype: `__int64 __fastcall(PHKEY phkResult, HKEY hKey, LPCWSTR lpSubKey, LPCWSTR)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180003cfc`
- `0x180003dec`

## callees

- `0x180003c04`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003c95`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003cd5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003c95`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003cd5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003c22`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003ce5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003c22`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003ce5`

## pseudocode

```c
__int64 __fastcall StartupDB::StartupApproval::Initialize(PHKEY phkResult, HKEY hKey, LPCWSTR lpSubKey, LPCWSTR a4)
{
  bool v8; // zf
  unsigned int Key; // edi
  HKEY hKeya; // [rsp+80h] [rbp+8h] BYREF

  if ( (unsigned __int64)*phkResult > 2 )
    RegCloseKey(*phkResult);
  v8 = *((_DWORD *)phkResult + 2) == 0;
  *phkResult = 0;
  if ( v8 )
  {
    hKeya = 0;
    Key = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0x103u, 0, &hKeya, 0);
    if ( !Key )
    {
      Key = RegCreateKeyExW(hKeya, a4, 0, 0, 0, 0x103u, 0, phkResult, 0);
      RegCloseKey(hKeya);
    }
  }
  else
  {
    Key = 5;
    *phkResult = (HKEY)((*((_DWORD *)phkResult + 2) != 1) + 1LL);
  }
  return Key;
}

```

## disassembly

```asm
0x180003c04  push    rbx
0x180003c06  push    rbp
0x180003c07  push    rsi
0x180003c08  push    rdi
0x180003c09  sub     rsp, 58h
0x180003c0d  cmp     qword ptr [rcx], 2
0x180003c11  mov     rbp, r9
0x180003c14  mov     rdi, r8
0x180003c17  mov     rsi, rdx
0x180003c1a  mov     rbx, rcx
0x180003c1d  jbe     short loc_180003C28
0x180003c1f  mov     rcx, [rcx]; hKey
0x180003c22  call    cs:__imp_RegCloseKey
0x180003c28  cmp     dword ptr [rbx+8], 0
0x180003c2c  mov     qword ptr [rbx], 0
0x180003c33  jz      short loc_180003C4E
0x180003c35  xor     eax, eax
0x180003c37  mov     edi, 5
0x180003c3c  cmp     dword ptr [rbx+8], 1
0x180003c40  setnz   al
0x180003c43  inc     rax
0x180003c46  mov     [rbx], rax
0x180003c49  jmp     loc_180003CEB
0x180003c4e  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x180003c57  lea     rax, [rsp+78h+hKey]
0x180003c5f  mov     [rsp+78h+phkResult], rax; phkResult
0x180003c64  xor     r9d, r9d; lpClass
0x180003c67  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180003c70  xor     r8d, r8d; Reserved
0x180003c73  mov     [rsp+78h+samDesired], 103h; samDesired
0x180003c7b  mov     rdx, rdi; lpSubKey
0x180003c7e  mov     rcx, rsi; hKey
0x180003c81  mov     [rsp+78h+dwOptions], 0; dwOptions
0x180003c89  mov     [rsp+78h+hKey], 0
0x180003c95  call    cs:__imp_RegCreateKeyExW
0x180003c9b  mov     edi, eax
0x180003c9d  test    eax, eax
0x180003c9f  jnz     short loc_180003CEB
0x180003ca1  mov     rcx, [rsp+78h+hKey]; hKey
0x180003ca9  xor     r9d, r9d; lpClass
0x180003cac  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x180003cb5  xor     r8d, r8d; Reserved
0x180003cb8  mov     [rsp+78h+phkResult], rbx; phkResult
0x180003cbd  mov     rdx, rbp; lpSubKey
0x180003cc0  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180003cc9  mov     [rsp+78h+samDesired], 103h; samDesired
0x180003cd1  mov     [rsp+78h+dwOptions], eax; dwOptions
0x180003cd5  call    cs:__imp_RegCreateKeyExW
0x180003cdb  mov     rcx, [rsp+78h+hKey]; hKey
0x180003ce3  mov     edi, eax
0x180003ce5  call    cs:__imp_RegCloseKey
0x180003ceb  mov     eax, edi
0x180003ced  add     rsp, 58h
0x180003cf1  pop     rdi
0x180003cf2  pop     rsi
0x180003cf3  pop     rbp
0x180003cf4  pop     rbx
0x180003cf5  retn
```
