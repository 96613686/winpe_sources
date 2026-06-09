# CEnumInstalledApps::_GetNextLegacyApp(IInstalledApp * *)

- ea: `0x18002d9cc`
- end: `0x18002da90`
- name: `?_GetNextLegacyApp@CEnumInstalledApps@@IEAAJPEAPEAUIInstalledApp@@@Z`
- size: `196`
- prototype: `__int64 __fastcall(CEnumInstalledApps *__hidden this, struct IInstalledApp **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x18002d580`

## callees

- `0x18002d9cc`
- `0x18002da98`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002da38`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002da38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002da6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002da6c`

## pseudocode

```c
__int64 __fastcall CEnumInstalledApps::_GetNextLegacyApp(CEnumInstalledApps *this, struct IInstalledApp **a2)
{
  HKEY *phkResult; // rbx
  int NextLegacyAppFromRegistry; // esi
  __int64 v6; // rax
  HKEY *v7; // rbp

  phkResult = (HKEY *)((char *)this + 32);
  NextLegacyAppFromRegistry = -2147467259;
  while ( 1 )
  {
    v6 = *((unsigned int *)this + 7);
    if ( (unsigned int)v6 < 4 )
    {
      v7 = phkResult;
      if ( *phkResult )
        goto LABEL_8;
      *((_DWORD *)this + 5) = 0;
      RegOpenKeyExW((HKEY)*(&rgKeys + 67 * v6 + 1), (LPCWSTR)&qword_1800776E8[67 * v6 + 1], 0, 0x20019u, phkResult);
      LODWORD(v6) = ++*((_DWORD *)this + 7);
    }
    else
    {
      if ( !*phkResult )
        return (unsigned int)NextLegacyAppFromRegistry;
      v7 = phkResult;
    }
    if ( !*phkResult )
      goto LABEL_10;
LABEL_8:
    NextLegacyAppFromRegistry = CEnumInstalledApps::_GetNextLegacyAppFromRegistry(
                                  this,
                                  *((_DWORD *)&rgKeys + 134 * (unsigned int)(v6 - 1)),
                                  a2);
    if ( NextLegacyAppFromRegistry >= 0 )
      return (unsigned int)NextLegacyAppFromRegistry;
    RegCloseKey(*phkResult);
    *phkResult = 0;
LABEL_10:
    phkResult = v7;
  }
}

```

## disassembly

```asm
0x18002d9cc  push    rbx
0x18002d9ce  push    rbp
0x18002d9cf  push    rsi
0x18002d9d0  push    rdi
0x18002d9d1  push    r12
0x18002d9d3  push    r14
0x18002d9d5  sub     rsp, 38h
0x18002d9d9  mov     r14, rdx
0x18002d9dc  lea     rbx, [rcx+20h]
0x18002d9e0  mov     rdi, rcx
0x18002d9e3  lea     r12, ?rgKeys@@3PAUAPPREGKEY@@A; APPREGKEY near * rgKeys
0x18002d9ea  mov     esi, 80004005h
0x18002d9ef  mov     eax, [rdi+1Ch]
0x18002d9f2  cmp     eax, 4
0x18002d9f5  jb      short loc_18002DA06
0x18002d9f7  cmp     qword ptr [rbx], 0
0x18002d9fb  jz      loc_18002DA81
0x18002da01  mov     rbp, rbx
0x18002da04  jmp     short loc_18002DA44
0x18002da06  cmp     qword ptr [rbx], 0
0x18002da0a  mov     rbp, rbx
0x18002da0d  jnz     short loc_18002DA4A
0x18002da0f  imul    rcx, rax, 218h
0x18002da16  mov     dword ptr [rdi+14h], 0
0x18002da1d  lea     rdx, [r12+10h]
0x18002da22  add     rdx, rcx; lpSubKey
0x18002da25  mov     [rsp+68h+phkResult], rbx; phkResult
0x18002da2a  mov     r9d, 20019h; samDesired
0x18002da30  xor     r8d, r8d; ulOptions
0x18002da33  mov     rcx, [rcx+r12+8]; hKey
0x18002da38  call    cs:__imp_RegOpenKeyExW
0x18002da3e  inc     dword ptr [rdi+1Ch]
0x18002da41  mov     eax, [rdi+1Ch]
0x18002da44  cmp     qword ptr [rbx], 0
0x18002da48  jz      short loc_18002DA79
0x18002da4a  lea     ecx, [rax-1]
0x18002da4d  mov     r8, r14; struct IInstalledApp **
0x18002da50  imul    rdx, rcx, 218h
0x18002da57  mov     rcx, rdi; this
0x18002da5a  mov     edx, [rdx+r12]; unsigned int
0x18002da5e  call    ?_GetNextLegacyAppFromRegistry@CEnumInstalledApps@@IEAAJKPEAPEAUIInstalledApp@@@Z; CEnumInstalledApps::_GetNextLegacyAppFromRegistry(ulong,IInstalledApp * *)
0x18002da63  mov     esi, eax
0x18002da65  test    eax, eax
0x18002da67  jns     short loc_18002DA81
0x18002da69  mov     rcx, [rbx]; hKey
0x18002da6c  call    cs:__imp_RegCloseKey
0x18002da72  mov     qword ptr [rbx], 0
0x18002da79  mov     rbx, rbp
0x18002da7c  jmp     loc_18002D9EF
0x18002da81  mov     eax, esi
0x18002da83  add     rsp, 38h
0x18002da87  pop     r14
0x18002da89  pop     r12
0x18002da8b  pop     rdi
0x18002da8c  pop     rsi
0x18002da8d  pop     rbp
0x18002da8e  pop     rbx
0x18002da8f  retn
```
