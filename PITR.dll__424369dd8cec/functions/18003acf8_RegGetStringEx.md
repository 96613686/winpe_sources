# RegGetStringEx

- ea: `0x18003acf8`
- end: `0x18003ae5f`
- name: `RegGetStringEx`
- size: `359`
- prototype: `BYTE *__fastcall(HKEY, const WCHAR *, const WCHAR *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800044f4`
- `0x180020e50`
- `0x1800212c0`

## callees

- `0x18003acf8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ad5c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ad5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ae3b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ae3b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ad96`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003adf7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ad96`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003adf7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003adb8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ae12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003adb8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ae12`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003adc9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003adc9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ae20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ae20`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ad38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ae43`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ad38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ae43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ae2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ae2a`

## pseudocode

```c
BYTE *__fastcall RegGetStringEx(HKEY a1, const WCHAR *a2, const WCHAR *a3)
{
  DWORD LastError; // ebx
  BYTE *v7; // rdi
  DWORD v8; // ebx
  HANDLE ProcessHeap; // rax
  BYTE *v10; // rax
  HANDLE v11; // rax
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD Type; // [rsp+60h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+38h] BYREF

  hKey = 0;
  cbData = 0;
  Type = 0;
  if ( !a1 )
  {
    SetLastError(0x57u);
    return 0;
  }
  if ( !a2 )
  {
    hKey = a1;
    goto LABEL_8;
  }
  LastError = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
  if ( !LastError )
  {
    a1 = hKey;
    if ( hKey )
    {
LABEL_8:
      v7 = 0;
      LastError = RegQueryValueExW(a1, a3, 0, &Type, 0, &cbData);
      if ( LastError )
        goto LABEL_17;
      if ( Type - 1 > 1 )
      {
        LastError = 13;
        goto LABEL_17;
      }
      v8 = cbData;
      ProcessHeap = GetProcessHeap();
      v10 = (BYTE *)HeapAlloc(ProcessHeap, 8u, v8);
      v7 = v10;
      if ( v10 )
      {
        *(_WORD *)v10 = 0;
        LastError = RegQueryValueExW(hKey, a3, 0, 0, v10, &cbData);
        if ( !LastError )
        {
          if ( Type - 1 <= 1 )
            goto LABEL_17;
          LastError = 13;
        }
        v11 = GetProcessHeap();
        HeapFree(v11, 0, v7);
        v7 = 0;
      }
      else
      {
        LastError = GetLastError();
      }
LABEL_17:
      if ( a2 )
        RegCloseKey(hKey);
      goto LABEL_19;
    }
  }
  v7 = 0;
LABEL_19:
  SetLastError(LastError);
  return v7;
}

```

## disassembly

```asm
0x18003acf8  mov     [rsp-18h+arg_8], rbx
0x18003acfd  mov     [rsp-18h+arg_10], rsi
0x18003ad02  mov     [rsp-18h+cbData], r9d
0x18003ad07  push    rbp
0x18003ad08  push    rdi
0x18003ad09  push    r14
0x18003ad0b  mov     rbp, rsp
0x18003ad0e  sub     rsp, 40h
0x18003ad12  mov     [rbp+hKey], 0
0x18003ad1a  mov     r14, r8
0x18003ad1d  mov     [rbp+cbData], 0
0x18003ad24  mov     rsi, rdx
0x18003ad27  mov     [rbp+Type], 0
0x18003ad2e  test    rcx, rcx
0x18003ad31  jnz     short loc_18003AD45
0x18003ad33  mov     ecx, 57h ; 'W'; dwErrCode
0x18003ad38  call    cs:__imp_SetLastError
0x18003ad3e  xor     eax, eax
0x18003ad40  jmp     loc_18003AE4C
0x18003ad45  test    rsi, rsi
0x18003ad48  jz      short loc_18003AD78
0x18003ad4a  lea     rax, [rbp+hKey]
0x18003ad4e  mov     r9d, 20019h; samDesired
0x18003ad54  xor     r8d, r8d; ulOptions
0x18003ad57  mov     [rsp+40h+phkResult], rax; phkResult
0x18003ad5c  call    cs:__imp_RegOpenKeyExW
0x18003ad62  mov     ebx, eax
0x18003ad64  test    eax, eax
0x18003ad66  jnz     short loc_18003AD71
0x18003ad68  mov     rcx, [rbp+hKey]; hKey
0x18003ad6c  test    rcx, rcx
0x18003ad6f  jnz     short loc_18003AD7C
0x18003ad71  xor     edi, edi
0x18003ad73  jmp     loc_18003AE41
0x18003ad78  mov     [rbp+hKey], rcx
0x18003ad7c  lea     rax, [rbp+cbData]
0x18003ad80  xor     edi, edi
0x18003ad82  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18003ad87  lea     r9, [rbp+Type]; lpType
0x18003ad8b  xor     r8d, r8d; lpReserved
0x18003ad8e  mov     [rsp+40h+phkResult], rdi; lpData
0x18003ad93  mov     rdx, r14; lpValueName
0x18003ad96  call    cs:__imp_RegQueryValueExW
0x18003ad9c  mov     ebx, eax
0x18003ad9e  test    eax, eax
0x18003ada0  jnz     loc_18003AE32
0x18003ada6  mov     eax, [rbp+Type]
0x18003ada9  dec     eax
0x18003adab  cmp     eax, 1
0x18003adae  jbe     short loc_18003ADB5
0x18003adb0  lea     ebx, [rdi+0Dh]
0x18003adb3  jmp     short loc_18003AE32
0x18003adb5  mov     ebx, [rbp+cbData]
0x18003adb8  call    cs:__imp_GetProcessHeap
0x18003adbe  mov     r8d, ebx; dwBytes
0x18003adc1  mov     edx, 8; dwFlags
0x18003adc6  mov     rcx, rax; hHeap
0x18003adc9  call    cs:__imp_HeapAlloc
0x18003adcf  mov     rdi, rax
0x18003add2  test    rax, rax
0x18003add5  jz      short loc_18003AE2A
0x18003add7  xor     ecx, ecx
0x18003add9  xor     r9d, r9d; lpType
0x18003addc  mov     [rax], cx
0x18003addf  xor     r8d, r8d; lpReserved
0x18003ade2  mov     rcx, [rbp+hKey]; hKey
0x18003ade6  lea     rax, [rbp+cbData]
0x18003adea  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18003adef  mov     rdx, r14; lpValueName
0x18003adf2  mov     [rsp+40h+phkResult], rdi; lpData
0x18003adf7  call    cs:__imp_RegQueryValueExW
0x18003adfd  mov     ebx, eax
0x18003adff  test    eax, eax
0x18003ae01  jnz     short loc_18003AE12
0x18003ae03  mov     eax, [rbp+Type]
0x18003ae06  dec     eax
0x18003ae08  cmp     eax, 1
0x18003ae0b  jbe     short loc_18003AE32
0x18003ae0d  mov     ebx, 0Dh
0x18003ae12  call    cs:__imp_GetProcessHeap
0x18003ae18  mov     r8, rdi; lpMem
0x18003ae1b  xor     edx, edx; dwFlags
0x18003ae1d  mov     rcx, rax; hHeap
0x18003ae20  call    cs:__imp_HeapFree
0x18003ae26  xor     edi, edi
0x18003ae28  jmp     short loc_18003AE32
0x18003ae2a  call    cs:__imp_GetLastError
0x18003ae30  mov     ebx, eax
0x18003ae32  test    rsi, rsi
0x18003ae35  jz      short loc_18003AE41
0x18003ae37  mov     rcx, [rbp+hKey]; hKey
0x18003ae3b  call    cs:__imp_RegCloseKey
0x18003ae41  mov     ecx, ebx; dwErrCode
0x18003ae43  call    cs:__imp_SetLastError
0x18003ae49  mov     rax, rdi
0x18003ae4c  mov     rbx, [rsp+40h+arg_8]
0x18003ae51  mov     rsi, [rsp+40h+arg_10]
0x18003ae56  add     rsp, 40h
0x18003ae5a  pop     r14
0x18003ae5c  pop     rdi
0x18003ae5d  pop     rbp
0x18003ae5e  retn
```
