# RegQueryStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t * *,RegistryHiveType)

- ea: `0x140017a68`
- end: `0x140017bc7`
- name: `?RegQueryStringValue@@YAJPEAUHKEY__@@PEB_W1PEAPEA_WW4RegistryHiveType@@@Z`
- size: `351`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, const WCHAR *, void **)`
- caller_count: `6`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14001ba3c`
- `0x14002387c`
- `0x140023974`
- `0x140023a3c`
- `0x140023db4`
- `0x140027c50`

## callees

- `0x14000cdb8`
- `0x14000ce30`
- `0x1400176fc`
- `0x140017a68`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140017ba4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140017ba4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140017ae5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140017ae5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140017b0f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140017b63`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140017b0f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140017b63`

## pseudocode

```c
__int64 __fastcall RegQueryStringValue(HKEY a1, const WCHAR *a2, const WCHAR *a3, void **a4)
{
  signed int v9; // ebx
  LSTATUS v10; // eax
  BYTE *v11; // rax
  REGSAM samDesired; // [rsp+30h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-1Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-18h] BYREF
  DWORD Type; // [rsp+40h] [rbp-10h] BYREF

  samDesired = 1;
  Type = 0;
  hKey = 0;
  cbData = 0;
  if ( !a4 )
    return 2147942487LL;
  *a4 = 0;
  v9 = SetRegistryType(a1, &samDesired);
  if ( v9 < 0 )
    goto LABEL_16;
  v10 = RegOpenKeyExW(a1, a2, 0, samDesired, &hKey);
  if ( v10 )
    goto LABEL_13;
  v10 = RegQueryValueExW(hKey, a3, 0, &Type, 0, &cbData);
  if ( v10 || !cbData )
    goto LABEL_13;
  if ( Type != 1 )
  {
    v9 = -2147024883;
LABEL_16:
    SusFree(*a4);
    *a4 = 0;
    goto LABEL_17;
  }
  cbData += 2;
  v11 = (BYTE *)SusAlloc(cbData);
  *a4 = v11;
  if ( !v11 )
  {
    v9 = -2147024882;
    goto LABEL_16;
  }
  v10 = RegQueryValueExW(hKey, a3, 0, &Type, v11, &cbData);
  if ( v10 )
  {
LABEL_13:
    v9 = (unsigned __int16)v10 | 0x80070000;
    if ( v10 <= 0 )
      v9 = v10;
    if ( v9 >= 0 )
      goto LABEL_17;
    goto LABEL_16;
  }
  *(_WORD *)((char *)*a4 + (cbData & 0xFFFFFFFE)) = 0;
LABEL_17:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140017a68  push    rbp
0x140017a6a  push    rbx
0x140017a6b  push    rsi
0x140017a6c  push    rdi
0x140017a6d  push    r12
0x140017a6f  push    r14
0x140017a71  push    r15
0x140017a73  mov     rbp, rsp
0x140017a76  sub     rsp, 50h
0x140017a7a  mov     rax, cs:__security_cookie
0x140017a81  xor     rax, rsp
0x140017a84  mov     [rbp+var_8], rax
0x140017a88  xor     r12d, r12d
0x140017a8b  mov     [rbp+samDesired], 1
0x140017a92  mov     [rbp+Type], r12d
0x140017a96  mov     rdi, r9
0x140017a99  mov     [rbp+hKey], r12
0x140017a9d  mov     rsi, r8
0x140017aa0  mov     [rbp+cbData], r12d
0x140017aa4  mov     r15, rdx
0x140017aa7  mov     r14, rcx
0x140017aaa  test    r9, r9
0x140017aad  jnz     short loc_140017AB9
0x140017aaf  mov     eax, 80070057h
0x140017ab4  jmp     loc_140017BAC
0x140017ab9  lea     rdx, [rbp+samDesired]
0x140017abd  mov     [r9], r12
0x140017ac0  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x140017ac5  mov     ebx, eax
0x140017ac7  test    eax, eax
0x140017ac9  js      loc_140017B90
0x140017acf  mov     r9d, [rbp+samDesired]; samDesired
0x140017ad3  lea     rax, [rbp+hKey]
0x140017ad7  xor     r8d, r8d; ulOptions
0x140017ada  mov     [rsp+50h+phkResult], rax; phkResult
0x140017adf  mov     rdx, r15; lpSubKey
0x140017ae2  mov     rcx, r14; hKey
0x140017ae5  call    cs:__imp_RegOpenKeyExW
0x140017aeb  test    eax, eax
0x140017aed  jnz     loc_140017B7E
0x140017af3  mov     rcx, [rbp+hKey]; hKey
0x140017af7  lea     rax, [rbp+cbData]
0x140017afb  mov     [rsp+50h+lpcbData], rax; lpcbData
0x140017b00  lea     r9, [rbp+Type]; lpType
0x140017b04  xor     r8d, r8d; lpReserved
0x140017b07  mov     [rsp+50h+phkResult], r12; lpData
0x140017b0c  mov     rdx, rsi; lpValueName
0x140017b0f  call    cs:__imp_RegQueryValueExW
0x140017b15  test    eax, eax
0x140017b17  jnz     short loc_140017B7E
0x140017b19  mov     ecx, [rbp+cbData]
0x140017b1c  test    ecx, ecx
0x140017b1e  jz      short loc_140017B7E
0x140017b20  cmp     [rbp+Type], 1
0x140017b24  jz      short loc_140017B2D
0x140017b26  mov     ebx, 8007000Dh
0x140017b2b  jmp     short loc_140017B90
0x140017b2d  add     ecx, 2; unsigned __int64
0x140017b30  mov     [rbp+cbData], ecx
0x140017b33  call    ?SusAlloc@@YAPEAX_K@Z; SusAlloc(unsigned __int64)
0x140017b38  mov     [rdi], rax
0x140017b3b  test    rax, rax
0x140017b3e  jnz     short loc_140017B47
0x140017b40  mov     ebx, 8007000Eh
0x140017b45  jmp     short loc_140017B90
0x140017b47  lea     rcx, [rbp+cbData]
0x140017b4b  xor     r8d, r8d; lpReserved
0x140017b4e  mov     [rsp+50h+lpcbData], rcx; lpcbData
0x140017b53  lea     r9, [rbp+Type]; lpType
0x140017b57  mov     rcx, [rbp+hKey]; hKey
0x140017b5b  mov     rdx, rsi; lpValueName
0x140017b5e  mov     [rsp+50h+phkResult], rax; lpData
0x140017b63  call    cs:__imp_RegQueryValueExW
0x140017b69  test    eax, eax
0x140017b6b  jnz     short loc_140017B7E
0x140017b6d  mov     ecx, [rbp+cbData]
0x140017b70  mov     rax, [rdi]
0x140017b73  and     rcx, 0FFFFFFFFFFFFFFFEh
0x140017b77  mov     [rcx+rax], r12w
0x140017b7c  jmp     short loc_140017B9B
0x140017b7e  movzx   ebx, ax
0x140017b81  or      ebx, 80070000h
0x140017b87  test    eax, eax
0x140017b89  cmovle  ebx, eax
0x140017b8c  test    ebx, ebx
0x140017b8e  jns     short loc_140017B9B
0x140017b90  mov     rcx, [rdi]; lpMem
0x140017b93  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140017b98  mov     [rdi], r12
0x140017b9b  mov     rcx, [rbp+hKey]; hKey
0x140017b9f  test    rcx, rcx
0x140017ba2  jz      short loc_140017BAA
0x140017ba4  call    cs:__imp_RegCloseKey
0x140017baa  mov     eax, ebx
0x140017bac  mov     rcx, [rbp+var_8]
0x140017bb0  xor     rcx, rsp; StackCookie
0x140017bb3  call    __security_check_cookie
0x140017bb8  add     rsp, 50h
0x140017bbc  pop     r15
0x140017bbe  pop     r14
0x140017bc0  pop     r12
0x140017bc2  pop     rdi
0x140017bc3  pop     rsi
0x140017bc4  pop     rbx
0x140017bc5  pop     rbp
0x140017bc6  retn
```
