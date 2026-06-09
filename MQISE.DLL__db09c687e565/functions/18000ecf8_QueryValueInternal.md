# QueryValueInternal

- ea: `0x18000ecf8`
- end: `0x18000edca`
- name: `QueryValueInternal`
- size: `210`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180005528`
- `0x18000d1e0`
- `0x18000eb70`

## callees

- `0x180001c0c`
- `0x18000e76c`
- `0x18000e800`
- `0x18000e884`
- `0x18000ecf8`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18000ed4d`
- `ADVAPI32!RegQueryValueExW` at `0x18000ed4d`
- `ADVAPI32!RegCloseKey` at `0x18000ed69`
- `ADVAPI32!RegCloseKey` at `0x18000ed8e`
- `ADVAPI32!RegCloseKey` at `0x18000ed9a`
- `ADVAPI32!RegCloseKey` at `0x18000ed69`
- `ADVAPI32!RegCloseKey` at `0x18000ed8e`
- `ADVAPI32!RegCloseKey` at `0x18000ed9a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall QueryValueInternal(__int64 a1, DWORD a2, BYTE *a3, DWORD a4)
{
  HKEY v8; // rax
  HKEY v9; // rbx
  int v10; // eax
  DWORD Type; // [rsp+30h] [rbp-58h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-54h] BYREF
  HKEY v14; // [rsp+38h] [rbp-50h]
  _BYTE pExceptionObject[72]; // [rsp+40h] [rbp-48h] BYREF

  v8 = CmOpenKey((const struct RegEntry *)a1, 1u);
  v9 = v8;
  v14 = v8;
  if ( v8 )
  {
    Type = a2;
    cbData = a4;
    v10 = RegQueryValueExW(v8, *(LPCWSTR *)(a1 + 16), 0, &Type, a3, &cbData);
    if ( v10 )
    {
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
      if ( *(_DWORD *)a1 == 1 )
      {
        registry_access_error::registry_access_error((registry_access_error *)pExceptionObject, v10);
        throw (registry_access_error *)pExceptionObject;
      }
      LODWORD(v8) = RegCloseKey(v9);
    }
    else if ( Type == 2 && a2 == 1 )
    {
      ExpandRegistryValue((LPWSTR)a3, a4 >> 1);
      LODWORD(v8) = RegCloseKey(v9);
    }
    else
    {
      LODWORD(v8) = RegCloseKey(v9);
    }
  }
  return (int)v8;
}

```

## disassembly

```asm
0x18000ecf8  push    rbx
0x18000ecfa  push    rbp
0x18000ecfb  push    rsi
0x18000ecfc  push    rdi
0x18000ecfd  push    r14
0x18000ecff  sub     rsp, 60h
0x18000ed03  mov     edi, r9d
0x18000ed06  mov     r14, r8
0x18000ed09  mov     ebp, edx
0x18000ed0b  mov     rsi, rcx
0x18000ed0e  mov     edx, 1; unsigned int
0x18000ed13  call    ?CmOpenKey@@YAPEAUHKEY__@@AEBVRegEntry@@K@Z; CmOpenKey(RegEntry const &,ulong)
0x18000ed18  mov     rbx, rax
0x18000ed1b  mov     [rsp+88h+var_50], rax
0x18000ed20  test    rax, rax
0x18000ed23  jnz     short loc_18000ED27
0x18000ed25  jmp     short loc_18000EDA1
0x18000ed27  mov     [rsp+88h+Type], ebp
0x18000ed2b  mov     [rsp+88h+cbData], edi
0x18000ed2f  lea     rax, [rsp+88h+cbData]
0x18000ed34  mov     [rsp+88h+lpcbData], rax; lpcbData
0x18000ed39  mov     [rsp+88h+lpData], r14; lpData
0x18000ed3e  lea     r9, [rsp+88h+Type]; lpType
0x18000ed43  xor     r8d, r8d; lpReserved
0x18000ed46  mov     rdx, [rsi+10h]; lpValueName
0x18000ed4a  mov     rcx, rbx; hKey
0x18000ed4d  call    cs:__imp_RegQueryValueExW
0x18000ed53  test    eax, eax
0x18000ed55  jz      short loc_18000ED72
0x18000ed57  jle     short loc_18000ED61
0x18000ed59  movzx   eax, ax
0x18000ed5c  or      eax, 80070000h
0x18000ed61  cmp     dword ptr [rsi], 1
0x18000ed64  jz      short loc_18000EDAC
0x18000ed66  mov     rcx, rbx; hKey
0x18000ed69  call    cs:__imp_RegCloseKey
0x18000ed6f  nop
0x18000ed70  jmp     short loc_18000EDA1
0x18000ed72  cmp     [rsp+88h+Type], 2
0x18000ed77  jnz     short loc_18000ED97
0x18000ed79  cmp     ebp, 1
0x18000ed7c  jnz     short loc_18000ED97
0x18000ed7e  shr     edi, 1
0x18000ed80  mov     edx, edi; nSize
0x18000ed82  mov     rcx, r14; lpDst
0x18000ed85  call    ?ExpandRegistryValue@@YAXPEA_WK@Z; ExpandRegistryValue(wchar_t *,ulong)
0x18000ed8a  nop
0x18000ed8b  mov     rcx, rbx; hKey
0x18000ed8e  call    cs:__imp_RegCloseKey
0x18000ed94  nop
0x18000ed95  jmp     short loc_18000EDA1
0x18000ed97  mov     rcx, rbx; hKey
0x18000ed9a  call    cs:__imp_RegCloseKey
0x18000eda0  nop
0x18000eda1  add     rsp, 60h
0x18000eda5  pop     r14
0x18000eda7  pop     rdi
0x18000eda8  pop     rsi
0x18000eda9  pop     rbp
0x18000edaa  pop     rbx
0x18000edab  retn
0x18000edac  mov     edx, eax; int
0x18000edae  lea     rcx, [rsp+88h+pExceptionObject]; this
0x18000edb3  call    ??0registry_access_error@@QEAA@J@Z; registry_access_error::registry_access_error(long)
0x18000edb8  lea     rdx, _TI3?AVregistry_access_error@@; pThrowInfo
0x18000edbf  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18000edc4  call    _CxxThrowException_0
```
