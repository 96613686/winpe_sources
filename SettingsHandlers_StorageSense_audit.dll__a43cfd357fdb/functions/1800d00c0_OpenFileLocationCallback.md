# OpenFileLocationCallback

- ea: `0x1800d00c0`
- end: `0x1800d017b`
- name: `OpenFileLocationCallback`
- size: `187`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800d00c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d0155`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d0155`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d0163`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d0163`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d0140`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d0140`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800d00e2`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800d00fa`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800d00e2`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800d00fa`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800d014a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800d014a`
- `api-ms-win-shell-namespace-l1-1-0!SHParseDisplayName` at `0x1800d011c`
- `api-ms-win-shell-namespace-l1-1-0!SHParseDisplayName` at `0x1800d011c`
- `ext-ms-win-shell32-shellfolders-l1-2-1!SHOpenFolderAndSelectItems` at `0x1800d0135`
- `ext-ms-win-shell32-shellfolders-l1-2-1!SHOpenFolderAndSelectItems` at `0x1800d0135`

## pseudocode

```c
__int64 __fastcall OpenFileLocationCallback(WCHAR *Parameter)
{
  HRESULT v2; // ebx
  HRESULT v3; // esi
  HANDLE ProcessHeap; // rax
  LPITEMIDLIST ppidl; // [rsp+40h] [rbp+8h] BYREF

  ppidl = 0;
  v2 = CoInitializeEx(0, 6u);
  if ( v2 >= 0 || (v3 = -2147467259, v2 = CoInitializeEx(0, 4u), v2 >= 0) )
  {
    v3 = SHParseDisplayName(Parameter, 0, &ppidl, 0, 0);
    if ( v3 >= 0 )
      SHOpenFolderAndSelectItems(ppidl, 0, 0, 0);
  }
  CoTaskMemFree(ppidl);
  if ( v2 >= 0 )
    CoUninitialize();
  if ( Parameter )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, Parameter);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800d00c0  mov     [rsp+arg_8], rbx
0x1800d00c5  mov     [rsp+arg_10], rsi
0x1800d00ca  push    rdi
0x1800d00cb  sub     rsp, 30h
0x1800d00cf  mov     rdi, rcx
0x1800d00d2  mov     [rsp+38h+ppidl], 0
0x1800d00db  xor     ecx, ecx; pvReserved
0x1800d00dd  mov     edx, 6; dwCoInit
0x1800d00e2  call    cs:__imp_CoInitializeEx
0x1800d00e8  mov     ebx, eax
0x1800d00ea  test    eax, eax
0x1800d00ec  jns     short loc_1800D0106
0x1800d00ee  mov     edx, 4; dwCoInit
0x1800d00f3  xor     ecx, ecx; pvReserved
0x1800d00f5  mov     esi, 80004005h
0x1800d00fa  call    cs:__imp_CoInitializeEx
0x1800d0100  mov     ebx, eax
0x1800d0102  test    eax, eax
0x1800d0104  js      short loc_1800D013B
0x1800d0106  xor     r9d, r9d; sfgaoIn
0x1800d0109  mov     [rsp+38h+psfgaoOut], 0; psfgaoOut
0x1800d0112  lea     r8, [rsp+38h+ppidl]; ppidl
0x1800d0117  xor     edx, edx; pbc
0x1800d0119  mov     rcx, rdi; pszName
0x1800d011c  call    cs:__imp_SHParseDisplayName
0x1800d0122  mov     esi, eax
0x1800d0124  test    eax, eax
0x1800d0126  js      short loc_1800D013B
0x1800d0128  mov     rcx, [rsp+38h+ppidl]; pidlFolder
0x1800d012d  xor     r9d, r9d; dwFlags
0x1800d0130  xor     r8d, r8d; apidl
0x1800d0133  xor     edx, edx; cidl
0x1800d0135  call    cs:__imp_SHOpenFolderAndSelectItems
0x1800d013b  mov     rcx, [rsp+38h+ppidl]; pv
0x1800d0140  call    cs:__imp_CoTaskMemFree
0x1800d0146  test    ebx, ebx
0x1800d0148  js      short loc_1800D0150
0x1800d014a  call    cs:__imp_CoUninitialize
0x1800d0150  test    rdi, rdi
0x1800d0153  jz      short loc_1800D0169
0x1800d0155  call    cs:__imp_GetProcessHeap
0x1800d015b  mov     r8, rdi; lpMem
0x1800d015e  xor     edx, edx; dwFlags
0x1800d0160  mov     rcx, rax; hHeap
0x1800d0163  call    cs:__imp_HeapFree
0x1800d0169  mov     rbx, [rsp+38h+arg_8]
0x1800d016e  mov     eax, esi
0x1800d0170  mov     rsi, [rsp+38h+arg_10]
0x1800d0175  add     rsp, 30h
0x1800d0179  pop     rdi
0x1800d017a  retn
```
