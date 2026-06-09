# OmaDmRegistryGetBinary(HKEY__ *,ushort const *,ushort const *,void *,ulong *)

- ea: `0x180061330`
- end: `0x180061411`
- name: `?OmaDmRegistryGetBinary@@YAJPEAUHKEY__@@PEBG1PEAXPEAK@Z`
- size: `225`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, BYTE *, unsigned int *cbData)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180061330`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006138a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006138a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800613c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800613c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800613ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800613ef`

## pseudocode

```c
__int64 __fastcall OmaDmRegistryGetBinary(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        BYTE *a4,
        unsigned int *cbData)
{
  unsigned int *v5; // rsi
  unsigned int v9; // ebx
  LSTATUS v10; // eax
  bool v11; // cc
  DWORD Type; // [rsp+50h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+10h] BYREF

  v5 = cbData;
  Type = 3;
  hKey = 0;
  LODWORD(cbData) = *cbData;
  if ( a1 && a4 )
  {
    v10 = RegOpenKeyExW(a1, a2, 0, 0x20119u, &hKey);
    v9 = v10;
    v11 = v10 <= 0;
    if ( v10 || (v10 = RegQueryValueExW(hKey, a3, 0, &Type, a4, (LPDWORD)&cbData), v9 = v10, v11 = v10 <= 0, v10) )
    {
      if ( !v11 )
        v9 = (unsigned __int16)v10 | 0x80070000;
    }
    else
    {
      *v5 = (unsigned int)cbData;
    }
  }
  else
  {
    v9 = -2147024809;
  }
  if ( a2 && hKey )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x180061330  mov     rax, rsp
0x180061333  mov     [rax+18h], rbx
0x180061337  mov     [rax+20h], rbp
0x18006133b  push    rsi
0x18006133c  push    rdi
0x18006133d  push    r14
0x18006133f  sub     rsp, 30h
0x180061343  mov     rsi, qword ptr [rsp+48h+cbData]
0x180061348  mov     rdi, r9
0x18006134b  mov     dword ptr [rax+8], 3
0x180061352  mov     r14, r8
0x180061355  mov     qword ptr [rax+10h], 0
0x18006135d  mov     rbp, rdx
0x180061360  mov     eax, [rsi]
0x180061362  mov     [rsp+48h+cbData], eax
0x180061366  test    rcx, rcx
0x180061369  jnz     short loc_180061372
0x18006136b  mov     ebx, 80070057h
0x180061370  jmp     short loc_1800613E0
0x180061372  test    rdi, rdi
0x180061375  jz      short loc_18006136B
0x180061377  lea     rax, [rsp+48h+hKey]
0x18006137c  mov     r9d, 20119h; samDesired
0x180061382  xor     r8d, r8d; ulOptions
0x180061385  mov     [rsp+48h+phkResult], rax; phkResult
0x18006138a  call    cs:__imp_RegOpenKeyExW
0x180061391  nop     dword ptr [rax+rax+00h]
0x180061396  mov     ebx, eax
0x180061398  test    eax, eax
0x18006139a  jz      short loc_1800613A9
0x18006139c  jle     short loc_1800613E0
0x18006139e  movzx   ebx, ax
0x1800613a1  or      ebx, 80070000h
0x1800613a7  jmp     short loc_1800613E0
0x1800613a9  mov     rcx, [rsp+48h+hKey]; hKey
0x1800613ae  lea     rax, [rsp+48h+cbData]
0x1800613b3  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800613b8  lea     r9, [rsp+48h+Type]; lpType
0x1800613bd  xor     r8d, r8d; lpReserved
0x1800613c0  mov     [rsp+48h+phkResult], rdi; lpData
0x1800613c5  mov     rdx, r14; lpValueName
0x1800613c8  call    cs:__imp_RegQueryValueExW
0x1800613cf  nop     dword ptr [rax+rax+00h]
0x1800613d4  mov     ebx, eax
0x1800613d6  test    eax, eax
0x1800613d8  jnz     short loc_18006139C
0x1800613da  mov     ecx, [rsp+48h+cbData]
0x1800613de  mov     [rsi], ecx
0x1800613e0  test    rbp, rbp
0x1800613e3  jz      short loc_1800613FB
0x1800613e5  mov     rcx, [rsp+48h+hKey]; hKey
0x1800613ea  test    rcx, rcx
0x1800613ed  jz      short loc_1800613FB
0x1800613ef  call    cs:__imp_RegCloseKey
0x1800613f6  nop     dword ptr [rax+rax+00h]
0x1800613fb  mov     rbp, [rsp+48h+arg_18]
0x180061400  mov     eax, ebx
0x180061402  mov     rbx, [rsp+48h+arg_10]
0x180061407  add     rsp, 30h
0x18006140b  pop     r14
0x18006140d  pop     rdi
0x18006140e  pop     rsi
0x18006140f  retn
```
