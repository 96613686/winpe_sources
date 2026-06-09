# SetRegistryDword

- ea: `0x140075070`
- end: `0x1400750df`
- name: `SetRegistryDword`
- size: `111`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `22`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14001f870`
- `0x1400246b0`
- `0x14004452c`
- `0x140054800`
- `0x140054c5c`
- `0x140054d90`
- `0x140055090`
- `0x1400647b0`
- `0x14007fe80`
- `0x1400808c0`
- `0x140080d28`
- `0x14008119c`
- `0x140081f4c`
- `0x140082830`
- `0x140082be8`
- `0x140083774`
- `0x140083acc`
- `0x1400840c8`
- `0x140084350`
- `0x140084638`
- `0x140084984`
- `0x1400850a8`

## callees

- `0x140075070`
- `0x140076758`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x140075098`
- `ADVAPI32!RegSetValueExW` at `0x140075098`
- `KERNEL32!SetLastError` at `0x1400750be`
- `KERNEL32!SetLastError` at `0x1400750be`

## string_xrefs

- `0x1400750ad`: `RegSetValueEx() failed[%s], ec=%d`

## pseudocode

```c
__int64 __fastcall SetRegistryDword(HKEY a1, const WCHAR *a2, int a3)
{
  unsigned int v4; // eax
  DWORD v5; // ebx
  int v7; // [rsp+50h] [rbp+18h] BYREF

  v7 = a3;
  v4 = RegSetValueExW(a1, a2, 0, 4u, (const BYTE *)&v7, 4u);
  v5 = v4;
  if ( !v4 )
    return 1;
  fax_dprintf(L"RegSetValueEx() failed[%s], ec=%d", a2, v4);
  SetLastError(v5);
  return 0;
}

```

## disassembly

```asm
0x140075070  mov     r11, rsp
0x140075073  mov     [r11+8], rbx
0x140075077  mov     [r11+18h], r8d
0x14007507b  push    rdi
0x14007507c  sub     rsp, 30h
0x140075080  mov     r9d, 4; dwType
0x140075086  lea     rax, [r11+18h]
0x14007508a  mov     [r11-10h], r9d
0x14007508e  xor     r8d, r8d; Reserved
0x140075091  mov     [r11-18h], rax
0x140075095  mov     rdi, rdx
0x140075098  call    cs:__imp_RegSetValueExW
0x14007509f  nop     dword ptr [rax+rax+00h]
0x1400750a4  mov     ebx, eax
0x1400750a6  test    eax, eax
0x1400750a8  jz      short loc_1400750CE
0x1400750aa  mov     r8d, eax
0x1400750ad  lea     rcx, aRegsetvalueexF; "RegSetValueEx() failed[%s], ec=%d"
0x1400750b4  mov     rdx, rdi
0x1400750b7  call    fax_dprintf
0x1400750bc  mov     ecx, ebx; dwErrCode
0x1400750be  call    cs:__imp_SetLastError
0x1400750c5  nop     dword ptr [rax+rax+00h]
0x1400750ca  xor     eax, eax
0x1400750cc  jmp     short loc_1400750D3
0x1400750ce  mov     eax, 1
0x1400750d3  mov     rbx, [rsp+38h+arg_0]
0x1400750d8  add     rsp, 30h
0x1400750dc  pop     rdi
0x1400750dd  retn
```
