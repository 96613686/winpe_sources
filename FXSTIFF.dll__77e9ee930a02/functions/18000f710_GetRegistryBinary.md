# GetRegistryBinary

- ea: `0x18000f710`
- end: `0x18000f854`
- name: `GetRegistryBinary`
- size: `324`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180017cb0`

## callees

- `0x18000f128`
- `0x18000f1c8`
- `0x18000f710`
- `0x1800174d8`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18000f757`
- `ADVAPI32!RegQueryValueExW` at `0x18000f7d8`
- `ADVAPI32!RegQueryValueExW` at `0x18000f757`
- `ADVAPI32!RegQueryValueExW` at `0x18000f7d8`
- `ADVAPI32!RegSetValueExW` at `0x18000f817`
- `ADVAPI32!RegSetValueExW` at `0x18000f817`

## string_xrefs

- `0x18000f831`: `RegSetValueEx() failed[%s], ec=%d`

## pseudocode

```c
void *__fastcall GetRegistryBinary(HKEY hKey, __int64 a2, DWORD *a3)
{
  unsigned int v5; // eax
  void *lpData; // rbx
  DWORD v8; // eax
  unsigned int v9; // eax
  DWORD cbData; // [rsp+58h] [rbp+28h] BYREF
  int v11; // [rsp+5Ch] [rbp+2Ch]
  DWORD Type; // [rsp+68h] [rbp+38h] BYREF

  v11 = HIDWORD(a2);
  cbData = 0;
  Type = 3;
  v5 = RegQueryValueExW(hKey, L"LastDetected", 0, &Type, 0, &cbData);
  if ( v5 )
  {
    if ( v5 != 2 )
    {
      lpData = 0;
LABEL_4:
      fax_dprintf(L"RegQueryValueEx() failed, ec=%d", v5);
LABEL_5:
      pMemFree(lpData);
      return 0;
    }
    goto LABEL_9;
  }
  if ( Type != 3 )
    return 0;
  v8 = cbData;
  if ( !cbData )
  {
LABEL_9:
    v8 = 1;
    cbData = 1;
  }
  lpData = pMemAlloc(v8 + 1);
  if ( !lpData )
    goto LABEL_5;
  v5 = RegQueryValueExW(hKey, L"LastDetected", 0, &Type, (LPBYTE)lpData, &cbData);
  *((_BYTE *)lpData + cbData) = 0;
  if ( v5 )
  {
    if ( v5 != 2 )
      goto LABEL_4;
    v9 = RegSetValueExW(hKey, L"LastDetected", 0, 3u, (const BYTE *)lpData, cbData);
    if ( v9 )
    {
      fax_dprintf(L"RegSetValueEx() failed[%s], ec=%d", L"LastDetected", v9);
      goto LABEL_5;
    }
  }
  if ( a3 )
    *a3 = cbData;
  return lpData;
}

```

## disassembly

```asm
0x18000f710  mov     r11, rsp
0x18000f713  mov     [r11+8], rbx
0x18000f717  mov     [r11+10h], rdx
0x18000f71b  push    rbp
0x18000f71c  push    rsi
0x18000f71d  push    rdi
0x18000f71e  mov     rbp, rsp
0x18000f721  sub     rsp, 30h
0x18000f725  lea     rax, [rbp+cbData]
0x18000f729  mov     [rbp+cbData], 0
0x18000f730  mov     rdi, r8
0x18000f733  mov     [r11-20h], rax
0x18000f737  lea     r9, [rbp+Type]; lpType
0x18000f73b  mov     qword ptr [r11-28h], 0
0x18000f743  xor     r8d, r8d; lpReserved
0x18000f746  mov     [rbp+Type], 3
0x18000f74d  lea     rdx, aLastdetected; "LastDetected"
0x18000f754  mov     rsi, rcx
0x18000f757  call    cs:__imp_RegQueryValueExW
0x18000f75e  nop     dword ptr [rax+rax+00h]
0x18000f763  test    eax, eax
0x18000f765  jz      short loc_18000F794
0x18000f767  cmp     eax, 2
0x18000f76a  jz      short loc_18000F7A1
0x18000f76c  xor     ebx, ebx
0x18000f76e  mov     edx, eax
0x18000f770  lea     rcx, aRegqueryvaluee_0; "RegQueryValueEx() failed, ec=%d"
0x18000f777  call    fax_dprintf
0x18000f77c  mov     rcx, rbx; lpMem
0x18000f77f  call    pMemFree
0x18000f784  xor     eax, eax
0x18000f786  mov     rbx, [rsp+30h+arg_0]
0x18000f78b  add     rsp, 30h
0x18000f78f  pop     rdi
0x18000f790  pop     rsi
0x18000f791  pop     rbp
0x18000f792  retn
0x18000f794  cmp     [rbp+Type], 3
0x18000f798  jnz     short loc_18000F784
0x18000f79a  mov     eax, [rbp+cbData]
0x18000f79d  test    eax, eax
0x18000f79f  jnz     short loc_18000F7A9
0x18000f7a1  mov     eax, 1
0x18000f7a6  mov     [rbp+cbData], eax
0x18000f7a9  lea     ecx, [rax+1]; dwBytes
0x18000f7ac  call    pMemAlloc
0x18000f7b1  mov     rbx, rax
0x18000f7b4  test    rax, rax
0x18000f7b7  jz      short loc_18000F77C
0x18000f7b9  lea     rax, [rbp+cbData]
0x18000f7bd  xor     r8d, r8d; lpReserved
0x18000f7c0  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000f7c5  lea     r9, [rbp+Type]; lpType
0x18000f7c9  lea     rdx, aLastdetected; "LastDetected"
0x18000f7d0  mov     [rsp+30h+lpData], rbx; lpData
0x18000f7d5  mov     rcx, rsi; hKey
0x18000f7d8  call    cs:__imp_RegQueryValueExW
0x18000f7df  nop     dword ptr [rax+rax+00h]
0x18000f7e4  mov     ecx, [rbp+cbData]
0x18000f7e7  mov     byte ptr [rcx+rbx], 0
0x18000f7eb  test    eax, eax
0x18000f7ed  jz      short loc_18000F842
0x18000f7ef  cmp     eax, 2
0x18000f7f2  jnz     loc_18000F76E
0x18000f7f8  mov     eax, [rbp+cbData]
0x18000f7fb  lea     rdx, aLastdetected; "LastDetected"
0x18000f802  mov     dword ptr [rsp+30h+lpcbData], eax; cbData
0x18000f806  mov     r9d, 3; dwType
0x18000f80c  xor     r8d, r8d; Reserved
0x18000f80f  mov     [rsp+30h+lpData], rbx; lpData
0x18000f814  mov     rcx, rsi; hKey
0x18000f817  call    cs:__imp_RegSetValueExW
0x18000f81e  nop     dword ptr [rax+rax+00h]
0x18000f823  test    eax, eax
0x18000f825  jz      short loc_18000F842
0x18000f827  mov     r8d, eax
0x18000f82a  lea     rdx, aLastdetected; "LastDetected"
0x18000f831  lea     rcx, aRegsetvalueexF; "RegSetValueEx() failed[%s], ec=%d"
0x18000f838  call    fax_dprintf
0x18000f83d  jmp     loc_18000F77C
0x18000f842  test    rdi, rdi
0x18000f845  jz      short loc_18000F84C
0x18000f847  mov     eax, [rbp+cbData]
0x18000f84a  mov     [rdi], eax
0x18000f84c  mov     rax, rbx
0x18000f84f  jmp     loc_18000F786
```
