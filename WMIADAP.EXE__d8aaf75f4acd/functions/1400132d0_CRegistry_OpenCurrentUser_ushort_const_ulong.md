# CRegistry::OpenCurrentUser(ushort const *,ulong)

- ea: `0x1400132d0`
- end: `0x1400133cf`
- name: `?OpenCurrentUser@CRegistry@@QEAAKPEBGK@Z`
- size: `255`
- prototype: `__int64 __fastcall(PHKEY phkResult, WCHAR *, REGSAM samDesired)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x140010190`
- `0x1400132d0`
- `0x1400134b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1400132f4`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1400132f4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001331f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001331f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400133a9`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400133a9`

## pseudocode

```c
__int64 __fastcall CRegistry::OpenCurrentUser(PHKEY phkResult, WCHAR *a2, REGSAM samDesired)
{
  unsigned int v6; // r15d
  HKEY v7; // rcx
  HKEY v8; // rcx

  CRegistry::PrepareToReOpen((CRegistry *)phkResult);
  v6 = RegOpenCurrentUser(samDesired, phkResult);
  if ( !v6 )
  {
    v7 = *phkResult;
    *((_BYTE *)phkResult + 36) = 1;
    v6 = RegOpenKeyExW(v7, a2, 0, samDesired, phkResult + 1);
    if ( !v6 )
    {
      v8 = phkResult[1];
      *((_DWORD *)phkResult + 140) = 260;
      RegQueryInfoKeyW(
        v8,
        (LPWSTR)phkResult + 19,
        (LPDWORD)phkResult + 140,
        0,
        (LPDWORD)phkResult + 141,
        (LPDWORD)phkResult + 142,
        (LPDWORD)phkResult + 143,
        (LPDWORD)phkResult + 144,
        (LPDWORD)phkResult + 145,
        (LPDWORD)phkResult + 146,
        (LPDWORD)phkResult + 147,
        (PFILETIME)phkResult + 74);
      CHString::operator=((CHString *)(phkResult + 3), a2);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1400132d0  push    rbx
0x1400132d2  push    rbp
0x1400132d3  push    rsi
0x1400132d4  push    rdi
0x1400132d5  push    r12
0x1400132d7  push    r13
0x1400132d9  push    r14
0x1400132db  push    r15
0x1400132dd  sub     rsp, 68h
0x1400132e1  mov     ebx, r8d
0x1400132e4  mov     r13, rdx
0x1400132e7  mov     r14, rcx
0x1400132ea  call    ?PrepareToReOpen@CRegistry@@AEAAXXZ; CRegistry::PrepareToReOpen(void)
0x1400132ef  mov     rdx, r14; phkResult
0x1400132f2  mov     ecx, ebx; samDesired
0x1400132f4  call    cs:__imp_RegOpenCurrentUser
0x1400132fa  mov     r15d, eax
0x1400132fd  test    eax, eax
0x1400132ff  jnz     loc_1400133BB
0x140013305  mov     rcx, [r14]; hKey
0x140013308  lea     r12, [r14+8]
0x14001330c  mov     r9d, ebx; samDesired
0x14001330f  mov     [rsp+0A8h+phkResult], r12; phkResult
0x140013314  xor     r8d, r8d; ulOptions
0x140013317  mov     byte ptr [r14+24h], 1
0x14001331c  mov     rdx, r13; lpSubKey
0x14001331f  call    cs:__imp_RegOpenKeyExW
0x140013325  mov     r15d, eax
0x140013328  test    eax, eax
0x14001332a  jnz     loc_1400133BB
0x140013330  mov     rcx, [r12]; hKey
0x140013334  lea     rax, [r14+250h]
0x14001333b  mov     [rsp+0A8h+lpftLastWriteTime], rax; lpftLastWriteTime
0x140013340  lea     r9, [r14+24Ch]
0x140013347  mov     [rsp+0A8h+lpcbSecurityDescriptor], r9; lpcbSecurityDescriptor
0x14001334c  lea     r10, [r14+248h]
0x140013353  mov     [rsp+0A8h+lpcbMaxValueLen], r10; lpcbMaxValueLen
0x140013358  lea     r11, [r14+244h]
0x14001335f  mov     [rsp+0A8h+lpcbMaxValueNameLen], r11; lpcbMaxValueNameLen
0x140013364  lea     r8, [r14+230h]; lpcchClass
0x14001336b  lea     rbx, [r14+240h]
0x140013372  mov     dword ptr [r8], 104h
0x140013379  mov     [rsp+0A8h+lpcValues], rbx; lpcValues
0x14001337e  lea     rdi, [r14+23Ch]
0x140013385  mov     [rsp+0A8h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x14001338a  lea     rsi, [r14+238h]
0x140013391  lea     rbp, [r14+234h]
0x140013398  mov     [rsp+0A8h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x14001339d  lea     rdx, [r14+26h]; lpClass
0x1400133a1  mov     [rsp+0A8h+phkResult], rbp; lpcSubKeys
0x1400133a6  xor     r9d, r9d; lpReserved
0x1400133a9  call    cs:__imp_RegQueryInfoKeyW
0x1400133af  lea     rcx, [r14+18h]; this
0x1400133b3  mov     rdx, r13; unsigned __int16 *
0x1400133b6  call    ??4CHString@@QEAAAEBV0@PEBG@Z; CHString::operator=(ushort const *)
0x1400133bb  mov     eax, r15d
0x1400133be  add     rsp, 68h
0x1400133c2  pop     r15
0x1400133c4  pop     r14
0x1400133c6  pop     r13
0x1400133c8  pop     r12
0x1400133ca  pop     rdi
0x1400133cb  pop     rsi
0x1400133cc  pop     rbp
0x1400133cd  pop     rbx
0x1400133ce  retn
```
