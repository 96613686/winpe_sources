# RegGetDword

- ea: `0x140025848`
- end: `0x14002591e`
- name: `RegGetDword`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140024fac`

## callees

- `0x140025848`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140025881`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002590d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140025881`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002590d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400258a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400258a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140025905`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140025905`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400258e0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400258e0`

## pseudocode

```c
__int64 __fastcall RegGetDword(HKEY a1, const WCHAR *a2, __int64 a3)
{
  DWORD v4; // ecx
  LSTATUS v6; // eax
  LSTATUS v7; // edi
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+20h] BYREF
  unsigned int Data; // [rsp+70h] [rbp+30h] BYREF
  int v11; // [rsp+74h] [rbp+34h]
  DWORD Type; // [rsp+78h] [rbp+38h] BYREF

  v11 = HIDWORD(a3);
  hKey = 0;
  Data = 0;
  cbData = 4;
  Type = 0;
  if ( !a1 )
  {
    v4 = 87;
LABEL_3:
    SetLastError(v4);
    return 0;
  }
  if ( a2 )
  {
    v6 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
    if ( v6 || (a1 = hKey) == 0 )
    {
      v4 = v6;
      goto LABEL_3;
    }
  }
  else
  {
    hKey = a1;
  }
  v7 = RegQueryValueExW(a1, L"AuditBoot", 0, &Type, (LPBYTE)&Data, &cbData);
  if ( v7 )
    goto LABEL_12;
  if ( cbData != 4 )
  {
    v7 = 13;
LABEL_12:
    Data = 0;
  }
  if ( a2 )
    RegCloseKey(hKey);
  SetLastError(v7);
  return Data;
}

```

## disassembly

```asm
0x140025848  mov     qword ptr [rsp-18h+Data], r8
0x14002584d  push    rbp
0x14002584e  push    rbx
0x14002584f  push    rdi
0x140025850  mov     rbp, rsp
0x140025853  sub     rsp, 40h
0x140025857  mov     [rbp+hKey], 0
0x14002585f  mov     rbx, rdx
0x140025862  mov     [rbp+Data], 0
0x140025869  mov     [rbp+cbData], 4
0x140025870  mov     [rbp+Type], 0
0x140025877  test    rcx, rcx
0x14002587a  jnz     short loc_14002588E
0x14002587c  mov     ecx, 57h ; 'W'; dwErrCode
0x140025881  call    cs:__imp_SetLastError
0x140025887  xor     eax, eax
0x140025889  jmp     loc_140025916
0x14002588e  test    rbx, rbx
0x140025891  jz      short loc_1400258BC
0x140025893  lea     rax, [rbp+hKey]
0x140025897  mov     r9d, 20019h; samDesired
0x14002589d  xor     r8d, r8d; ulOptions
0x1400258a0  mov     [rsp+40h+phkResult], rax; phkResult
0x1400258a5  call    cs:__imp_RegOpenKeyExW
0x1400258ab  test    eax, eax
0x1400258ad  jnz     short loc_1400258B8
0x1400258af  mov     rcx, [rbp+hKey]
0x1400258b3  test    rcx, rcx
0x1400258b6  jnz     short loc_1400258C0
0x1400258b8  mov     ecx, eax; hKey
0x1400258ba  jmp     short loc_140025881
0x1400258bc  mov     [rbp+hKey], rcx
0x1400258c0  lea     rax, [rbp+cbData]
0x1400258c4  xor     r8d, r8d; lpReserved
0x1400258c7  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1400258cc  lea     r9, [rbp+Type]; lpType
0x1400258d0  lea     rax, [rbp+Data]
0x1400258d4  lea     rdx, ValueName; "AuditBoot"
0x1400258db  mov     [rsp+40h+phkResult], rax; lpData
0x1400258e0  call    cs:__imp_RegQueryValueExW
0x1400258e6  mov     edi, eax
0x1400258e8  test    eax, eax
0x1400258ea  jnz     short loc_1400258F5
0x1400258ec  cmp     [rbp+cbData], 4
0x1400258f0  jz      short loc_1400258FC
0x1400258f2  lea     edi, [rax+0Dh]
0x1400258f5  mov     [rbp+Data], 0
0x1400258fc  test    rbx, rbx
0x1400258ff  jz      short loc_14002590B
0x140025901  mov     rcx, [rbp+hKey]; hKey
0x140025905  call    cs:__imp_RegCloseKey
0x14002590b  mov     ecx, edi; dwErrCode
0x14002590d  call    cs:__imp_SetLastError
0x140025913  mov     eax, [rbp+Data]
0x140025916  add     rsp, 40h
0x14002591a  pop     rdi
0x14002591b  pop     rbx
0x14002591c  pop     rbp
0x14002591d  retn
```
