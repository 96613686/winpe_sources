# _lambda_8863e87adec99bfd8cc729a691af39d4_::operator()

- ea: `0x180060a68`
- end: `0x180060bc0`
- name: `_lambda_8863e87adec99bfd8cc729a691af39d4_::operator()`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180047850`

## callees

- `0x18000ba40`
- `0x18000baa4`
- `0x180060a68`
- `0x180060bc8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060acb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060b4b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060acb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060b4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060a93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060aeb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060b16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060b6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060b7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060b9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060baf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060a93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060aeb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060b16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060b6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060b7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060b9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060baf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_8863e87adec99bfd8cc729a691af39d4_::operator()(__int64 a1)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  LSTATUS v5; // eax
  Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0 *v6; // rcx
  _BYTE *v7; // rbx
  HKEY hKey; // [rsp+50h] [rbp+20h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp+28h] BYREF

  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, *(LPCWSTR *)(*(_QWORD *)a1 + 8LL), 0, 0x20019u, &hKey);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    if ( hKey )
      RegCloseKey(hKey);
    return v3;
  }
  phkResult = 0;
  v5 = RegOpenKeyExW(hKey, **(LPCWSTR **)(a1 + 8), 0, 0x20019u, &phkResult);
  v3 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v3 = (unsigned __int16)v5 | 0x80070000;
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( hKey )
      RegCloseKey(hKey);
    return v3;
  }
  v7 = *(_BYTE **)(a1 + 16);
  *v7 = Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0::IsValidProfile(v6, phkResult);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180060a68  push    rbp
0x180060a6a  push    rbx
0x180060a6b  push    rdi
0x180060a6c  mov     rbp, rsp
0x180060a6f  sub     rsp, 30h
0x180060a73  mov     rdi, rcx
0x180060a76  mov     [rbp+hKey], 0
0x180060a7e  mov     rbx, [rbp+hKey]
0x180060a82  test    rbx, rbx
0x180060a85  jz      short loc_180060AA3
0x180060a87  lea     rcx, [rbp+arg_10]; this
0x180060a8b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180060a90  mov     rcx, rbx; hKey
0x180060a93  call    cs:__imp_RegCloseKey
0x180060a99  lea     rcx, [rbp+arg_10]; this
0x180060a9d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180060aa2  nop
0x180060aa3  mov     [rbp+hKey], 0
0x180060aab  mov     rdx, [rdi]
0x180060aae  lea     rax, [rbp+hKey]
0x180060ab2  mov     [rsp+30h+phkResult], rax; phkResult
0x180060ab7  mov     r9d, 20019h; samDesired
0x180060abd  xor     r8d, r8d; ulOptions
0x180060ac0  mov     rdx, [rdx+8]; lpSubKey
0x180060ac4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180060acb  call    cs:__imp_RegOpenKeyExW
0x180060ad1  mov     ebx, eax
0x180060ad3  test    eax, eax
0x180060ad5  jz      short loc_180060AF9
0x180060ad7  jle     short loc_180060AE2
0x180060ad9  movzx   ebx, ax
0x180060adc  or      ebx, 80070000h
0x180060ae2  mov     rcx, [rbp+hKey]; hKey
0x180060ae6  test    rcx, rcx
0x180060ae9  jz      short loc_180060AF2
0x180060aeb  call    cs:__imp_RegCloseKey
0x180060af1  nop
0x180060af2  mov     eax, ebx
0x180060af4  jmp     loc_180060BB8
0x180060af9  mov     [rbp+arg_8], 0
0x180060b01  mov     rbx, [rbp+arg_8]
0x180060b05  test    rbx, rbx
0x180060b08  jz      short loc_180060B26
0x180060b0a  lea     rcx, [rbp+arg_10]; this
0x180060b0e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180060b13  mov     rcx, rbx; hKey
0x180060b16  call    cs:__imp_RegCloseKey
0x180060b1c  lea     rcx, [rbp+arg_10]; this
0x180060b20  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180060b25  nop
0x180060b26  mov     [rbp+arg_8], 0
0x180060b2e  mov     rdx, [rdi+8]
0x180060b32  lea     rax, [rbp+arg_8]
0x180060b36  mov     [rsp+30h+phkResult], rax; phkResult
0x180060b3b  mov     r9d, 20019h; samDesired
0x180060b41  xor     r8d, r8d; ulOptions
0x180060b44  mov     rdx, [rdx]; lpSubKey
0x180060b47  mov     rcx, [rbp+hKey]; hKey
0x180060b4b  call    cs:__imp_RegOpenKeyExW
0x180060b51  mov     ebx, eax
0x180060b53  test    eax, eax
0x180060b55  jz      short loc_180060B87
0x180060b57  jle     short loc_180060B62
0x180060b59  movzx   ebx, ax
0x180060b5c  or      ebx, 80070000h
0x180060b62  mov     rcx, [rbp+arg_8]; hKey
0x180060b66  test    rcx, rcx
0x180060b69  jz      short loc_180060B72
0x180060b6b  call    cs:__imp_RegCloseKey
0x180060b71  nop
0x180060b72  mov     rcx, [rbp+hKey]; hKey
0x180060b76  test    rcx, rcx
0x180060b79  jz      short loc_180060B82
0x180060b7b  call    cs:__imp_RegCloseKey
0x180060b81  nop
0x180060b82  jmp     loc_180060AF2
0x180060b87  mov     rbx, [rdi+10h]
0x180060b8b  mov     rdx, [rbp+arg_8]; HKEY
0x180060b8f  call    ?IsValidProfile@AssignedAccessConfigStoreV0@AssignedAccess@Internal@Windows@@AEAA_NPEAUHKEY__@@@Z; Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV0::IsValidProfile(HKEY__ *)
0x180060b94  mov     [rbx], al
0x180060b96  mov     rcx, [rbp+arg_8]; hKey
0x180060b9a  test    rcx, rcx
0x180060b9d  jz      short loc_180060BA6
0x180060b9f  call    cs:__imp_RegCloseKey
0x180060ba5  nop
0x180060ba6  mov     rcx, [rbp+hKey]; hKey
0x180060baa  test    rcx, rcx
0x180060bad  jz      short loc_180060BB6
0x180060baf  call    cs:__imp_RegCloseKey
0x180060bb5  nop
0x180060bb6  xor     eax, eax
0x180060bb8  add     rsp, 30h
0x180060bbc  pop     rdi
0x180060bbd  pop     rbx
0x180060bbe  pop     rbp
0x180060bbf  retn
```
