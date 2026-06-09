# UnRegisterTypeLibForUser

- ea: `0x180057340`
- end: `0x1800573d2`
- name: `UnRegisterTypeLibForUser`
- size: `146`
- prototype: `HRESULT __stdcall(const GUID *const libID, WORD wMajorVerNum, WORD wMinorVerNum, LCID lcid, SYSKIND syskind)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18003fe6c`
- `0x180057340`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800573c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800573c1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180057380`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180057380`

## pseudocode

```c
HRESULT __stdcall UnRegisterTypeLibForUser(
        const GUID *const libID,
        WORD wMajorVerNum,
        WORD wMinorVerNum,
        LCID lcid,
        SYSKIND syskind)
{
  HRESULT v9; // ebx
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF

  hKey = 0;
  if ( RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\classes", 0, 0x2000000u, &hKey) )
    v9 = -2147319780;
  else
    v9 = UnRegisterTypeLib_Impl(hKey, (GUID *)libID, wMajorVerNum, wMinorVerNum, lcid, syskind);
  if ( hKey )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x180057340  push    rbx
0x180057342  push    rbp
0x180057343  push    rsi
0x180057344  push    rdi
0x180057345  sub     rsp, 48h
0x180057349  mov     ebx, r9d
0x18005734c  mov     [rsp+68h+hKey], 0
0x180057355  movzx   edi, r8w
0x180057359  lea     rax, [rsp+68h+hKey]
0x18005735e  movzx   esi, dx
0x180057361  mov     [rsp+68h+phkResult], rax; phkResult
0x180057366  mov     rbp, rcx
0x180057369  lea     rdx, aSoftwareClasse; "Software\\classes"
0x180057370  mov     r9d, 2000000h; samDesired
0x180057376  xor     r8d, r8d; ulOptions
0x180057379  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180057380  call    cs:__imp_RegOpenKeyExW
0x180057386  test    eax, eax
0x180057388  jz      short loc_180057391
0x18005738a  mov     ebx, 8002801Ch
0x18005738f  jmp     short loc_1800573B7
0x180057391  mov     eax, [rsp+68h+syskind]
0x180057398  movzx   r9d, di
0x18005739c  mov     rcx, [rsp+68h+hKey]; hKey
0x1800573a1  movzx   r8d, si
0x1800573a5  mov     [rsp+68h+var_40], eax; int
0x1800573a9  mov     rdx, rbp; rguid
0x1800573ac  mov     dword ptr [rsp+68h+phkResult], ebx; int
0x1800573b0  call    UnRegisterTypeLib_Impl
0x1800573b5  mov     ebx, eax
0x1800573b7  mov     rcx, [rsp+68h+hKey]; hKey
0x1800573bc  test    rcx, rcx
0x1800573bf  jz      short loc_1800573C7
0x1800573c1  call    cs:__imp_RegCloseKey
0x1800573c7  mov     eax, ebx
0x1800573c9  add     rsp, 48h
0x1800573cd  pop     rdi
0x1800573ce  pop     rsi
0x1800573cf  pop     rbp
0x1800573d0  pop     rbx
0x1800573d1  retn
```
