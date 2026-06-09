# pDrvRecoveryOpenAttributeRoot(HDRIVERSTORE__ *,ushort const *,HKEY__ * *)

- ea: `0x18003b868`
- end: `0x18003b93a`
- name: `?pDrvRecoveryOpenAttributeRoot@@YAHPEAUHDRIVERSTORE__@@PEBGPEAPEAUHKEY__@@@Z`
- size: `210`
- prototype: `_BOOL8 __fastcall(struct HDRIVERSTORE__ *, const unsigned __int16 *, HKEY *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18003b5d4`

## callees

- `0x18003b6ec`
- `0x18003b868`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b91d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b91d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b893`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b893`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b8b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b8b4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003b8f5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003b8f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b907`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b915`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b907`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b915`

## pseudocode

```c
_BOOL8 __fastcall pDrvRecoveryOpenAttributeRoot(struct HDRIVERSTORE__ *a1, const unsigned __int16 *a2, HKEY *a3)
{
  HKEY RecordRoot; // rdi
  DWORD Key; // eax
  LSTATUS v7; // ebx
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  hKey = 0;
  RecordRoot = pDrvRecoveryGetRecordRoot(a1);
  if ( RecordRoot )
  {
    v7 = RegOpenKeyExW(RecordRoot, a2, 0, 0x2001Fu, &hKey);
    if ( v7 )
      goto LABEL_6;
    Key = RegCreateKeyExW(hKey, L"Attributes", 0, 0, 0, 0x2001Fu, 0, a3, 0);
  }
  else
  {
    Key = GetLastError();
  }
  v7 = Key;
LABEL_6:
  if ( hKey )
    RegCloseKey(hKey);
  if ( RecordRoot )
    RegCloseKey(RecordRoot);
  SetLastError(v7);
  return v7 == 0;
}

```

## disassembly

```asm
0x18003b868  mov     [rsp+arg_0], rbx
0x18003b86d  mov     [rsp+arg_8], rsi
0x18003b872  push    rdi
0x18003b873  sub     rsp, 50h
0x18003b877  mov     rsi, r8
0x18003b87a  mov     [rsp+58h+hKey], 0
0x18003b883  mov     rbx, rdx
0x18003b886  call    ?pDrvRecoveryGetRecordRoot@@YAPEAUHKEY__@@PEAUHDRIVERSTORE__@@@Z; pDrvRecoveryGetRecordRoot(HDRIVERSTORE__ *)
0x18003b88b  mov     rdi, rax
0x18003b88e  test    rax, rax
0x18003b891  jnz     short loc_18003B89B
0x18003b893  call    cs:__imp_GetLastError
0x18003b899  jmp     short loc_18003B8FB
0x18003b89b  lea     rax, [rsp+58h+hKey]
0x18003b8a0  mov     r9d, 2001Fh; samDesired
0x18003b8a6  xor     r8d, r8d; ulOptions
0x18003b8a9  mov     [rsp+58h+phkResult], rax; phkResult
0x18003b8ae  mov     rdx, rbx; lpSubKey
0x18003b8b1  mov     rcx, rdi; hKey
0x18003b8b4  call    cs:__imp_RegOpenKeyExW
0x18003b8ba  mov     ebx, eax
0x18003b8bc  test    eax, eax
0x18003b8be  jnz     short loc_18003B8FD
0x18003b8c0  mov     rcx, [rsp+58h+hKey]; hKey
0x18003b8c5  lea     rdx, aAttributes; "Attributes"
0x18003b8cc  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18003b8d5  xor     r9d, r9d; lpClass
0x18003b8d8  mov     [rsp+58h+var_20], rsi; phkResult
0x18003b8dd  xor     r8d, r8d; Reserved
0x18003b8e0  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003b8e9  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x18003b8f1  mov     dword ptr [rsp+58h+phkResult], eax; dwOptions
0x18003b8f5  call    cs:__imp_RegCreateKeyExW
0x18003b8fb  mov     ebx, eax
0x18003b8fd  mov     rcx, [rsp+58h+hKey]; hKey
0x18003b902  test    rcx, rcx
0x18003b905  jz      short loc_18003B90D
0x18003b907  call    cs:__imp_RegCloseKey
0x18003b90d  test    rdi, rdi
0x18003b910  jz      short loc_18003B91B
0x18003b912  mov     rcx, rdi; hKey
0x18003b915  call    cs:__imp_RegCloseKey
0x18003b91b  mov     ecx, ebx; dwErrCode
0x18003b91d  call    cs:__imp_SetLastError
0x18003b923  mov     rsi, [rsp+58h+arg_8]
0x18003b928  xor     eax, eax
0x18003b92a  test    ebx, ebx
0x18003b92c  mov     rbx, [rsp+58h+arg_0]
0x18003b931  setz    al
0x18003b934  add     rsp, 50h
0x18003b938  pop     rdi
0x18003b939  retn
```
