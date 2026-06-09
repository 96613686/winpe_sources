# PrintCore::RegHelpers::SetStringValue(HKEY__ * const &,ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong)

- ea: `0x18002b07c`
- end: `0x18002b0dd`
- name: `?SetStringValue@RegHelpers@PrintCore@@SAJAEBQEAUHKEY__@@PEBG1V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `97`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800296a0`

## callees

- `0x18000f8a8`
- `0x18002b07c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002b0b3`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002b0b3`

## pseudocode

```c
__int64 __fastcall PrintCore::RegHelpers::SetStringValue(HKEY *a1, __int64 a2, const WCHAR *a3, const void **a4)
{
  const void *lpData; // rax
  LSTATUS v6; // eax
  unsigned int v7; // ebx

  if ( (unsigned __int64)a4[3] <= 7 )
    lpData = a4;
  else
    lpData = *a4;
  v6 = RegSetKeyValueW(*a1, 0, a3, 1u, lpData, 2 * *((_DWORD *)a4 + 4));
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  std::wstring::_Tidy_deallocate(a4);
  return v7;
}

```

## disassembly

```asm
0x18002b07c  mov     [rsp+arg_8], rbx
0x18002b081  push    rdi
0x18002b082  sub     rsp, 30h
0x18002b086  mov     r10, rcx
0x18002b089  mov     rdi, r9
0x18002b08c  mov     ecx, [r9+10h]
0x18002b090  add     ecx, ecx
0x18002b092  cmp     qword ptr [r9+18h], 7
0x18002b097  jbe     short loc_18002B09E
0x18002b099  mov     rax, [r9]
0x18002b09c  jmp     short loc_18002B0A1
0x18002b09e  mov     rax, rdi
0x18002b0a1  mov     [rsp+38h+cbData], ecx; cbData
0x18002b0a5  xor     edx, edx; lpSubKey
0x18002b0a7  mov     rcx, [r10]; hKey
0x18002b0aa  mov     [rsp+38h+lpData], rax; lpData
0x18002b0af  lea     r9d, [rdx+1]; dwType
0x18002b0b3  call    cs:__imp_RegSetKeyValueW
0x18002b0b9  mov     ebx, eax
0x18002b0bb  test    eax, eax
0x18002b0bd  jle     short loc_18002B0C8
0x18002b0bf  movzx   ebx, ax
0x18002b0c2  or      ebx, 80070000h
0x18002b0c8  mov     rcx, rdi
0x18002b0cb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b0d0  mov     eax, ebx
0x18002b0d2  mov     rbx, [rsp+38h+arg_8]
0x18002b0d7  add     rsp, 30h
0x18002b0db  pop     rdi
0x18002b0dc  retn
```
