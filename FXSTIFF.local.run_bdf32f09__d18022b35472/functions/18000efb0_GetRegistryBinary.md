# GetRegistryBinary

- ea: `0x18000efb0`
- end: `0x18000f0dd`
- name: `GetRegistryBinary`
- size: `301`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180016f40`

## callees

- `0x18000ea18`
- `0x18000eac0`
- `0x18000efb0`
- `0x180016794`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18000eff7`
- `ADVAPI32!RegQueryValueExW` at `0x18000f071`
- `ADVAPI32!RegQueryValueExW` at `0x18000eff7`
- `ADVAPI32!RegQueryValueExW` at `0x18000f071`
- `ADVAPI32!RegSetValueExW` at `0x18000f0a6`
- `ADVAPI32!RegSetValueExW` at `0x18000f0a6`

## string_xrefs

- `0x18000f0ba`: `RegSetValueEx() failed[%s], ec=%d`

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
0x18000efb0  mov     r11, rsp
0x18000efb3  mov     [r11+8], rbx
0x18000efb7  mov     [r11+10h], rdx
0x18000efbb  push    rbp
0x18000efbc  push    rsi
0x18000efbd  push    rdi
0x18000efbe  mov     rbp, rsp
0x18000efc1  sub     rsp, 30h
0x18000efc5  lea     rax, [rbp+cbData]
0x18000efc9  mov     [rbp+cbData], 0
0x18000efd0  mov     rdi, r8
0x18000efd3  mov     [r11-20h], rax
0x18000efd7  lea     r9, [rbp+Type]; lpType
0x18000efdb  mov     qword ptr [r11-28h], 0
0x18000efe3  xor     r8d, r8d; lpReserved
0x18000efe6  mov     [rbp+Type], 3
0x18000efed  lea     rdx, aLastdetected; "LastDetected"
0x18000eff4  mov     rsi, rcx
0x18000eff7  call    cs:__imp_RegQueryValueExW
0x18000effd  test    eax, eax
0x18000efff  jz      short loc_18000F02D
0x18000f001  cmp     eax, 2
0x18000f004  jz      short loc_18000F03A
0x18000f006  xor     ebx, ebx
0x18000f008  mov     edx, eax
0x18000f00a  lea     rcx, aRegqueryvaluee_0; "RegQueryValueEx() failed, ec=%d"
0x18000f011  call    fax_dprintf
0x18000f016  mov     rcx, rbx; lpMem
0x18000f019  call    pMemFree
0x18000f01e  xor     eax, eax
0x18000f020  mov     rbx, [rsp+30h+arg_0]
0x18000f025  add     rsp, 30h
0x18000f029  pop     rdi
0x18000f02a  pop     rsi
0x18000f02b  pop     rbp
0x18000f02c  retn
0x18000f02d  cmp     [rbp+Type], 3
0x18000f031  jnz     short loc_18000F01E
0x18000f033  mov     eax, [rbp+cbData]
0x18000f036  test    eax, eax
0x18000f038  jnz     short loc_18000F042
0x18000f03a  mov     eax, 1
0x18000f03f  mov     [rbp+cbData], eax
0x18000f042  lea     ecx, [rax+1]; dwBytes
0x18000f045  call    pMemAlloc
0x18000f04a  mov     rbx, rax
0x18000f04d  test    rax, rax
0x18000f050  jz      short loc_18000F016
0x18000f052  lea     rax, [rbp+cbData]
0x18000f056  xor     r8d, r8d; lpReserved
0x18000f059  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000f05e  lea     r9, [rbp+Type]; lpType
0x18000f062  lea     rdx, aLastdetected; "LastDetected"
0x18000f069  mov     [rsp+30h+lpData], rbx; lpData
0x18000f06e  mov     rcx, rsi; hKey
0x18000f071  call    cs:__imp_RegQueryValueExW
0x18000f077  mov     ecx, [rbp+cbData]
0x18000f07a  mov     byte ptr [rcx+rbx], 0
0x18000f07e  test    eax, eax
0x18000f080  jz      short loc_18000F0CB
0x18000f082  cmp     eax, 2
0x18000f085  jnz     short loc_18000F008
0x18000f087  mov     eax, [rbp+cbData]
0x18000f08a  lea     rdx, aLastdetected; "LastDetected"
0x18000f091  mov     dword ptr [rsp+30h+lpcbData], eax; cbData
0x18000f095  mov     r9d, 3; dwType
0x18000f09b  xor     r8d, r8d; Reserved
0x18000f09e  mov     [rsp+30h+lpData], rbx; lpData
0x18000f0a3  mov     rcx, rsi; hKey
0x18000f0a6  call    cs:__imp_RegSetValueExW
0x18000f0ac  test    eax, eax
0x18000f0ae  jz      short loc_18000F0CB
0x18000f0b0  mov     r8d, eax
0x18000f0b3  lea     rdx, aLastdetected; "LastDetected"
0x18000f0ba  lea     rcx, aRegsetvalueexF; "RegSetValueEx() failed[%s], ec=%d"
0x18000f0c1  call    fax_dprintf
0x18000f0c6  jmp     loc_18000F016
0x18000f0cb  test    rdi, rdi
0x18000f0ce  jz      short loc_18000F0D5
0x18000f0d0  mov     eax, [rbp+cbData]
0x18000f0d3  mov     [rdi], eax
0x18000f0d5  mov     rax, rbx
0x18000f0d8  jmp     loc_18000F020
```
