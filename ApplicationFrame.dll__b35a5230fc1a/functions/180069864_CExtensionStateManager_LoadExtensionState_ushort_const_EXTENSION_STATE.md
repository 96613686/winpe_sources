# CExtensionStateManager::_LoadExtensionState(ushort const *,EXTENSION_STATE *)

- ea: `0x180069864`
- end: `0x18006997e`
- name: `?_LoadExtensionState@CExtensionStateManager@@AEAAJPEBGPEAUEXTENSION_STATE@@@Z`
- size: `282`
- prototype: `int(CExtensionStateManager *__hidden this, const unsigned __int16 *, struct EXTENSION_STATE *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180064c70`
- `0x180069984`

## callees

- `0x18002cf10`
- `0x1800446fc`
- `0x180069864`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800698e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800698e6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006992a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006995d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006992a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006995d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180069968`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180069968`

## pseudocode

```c
__int64 __fastcall CExtensionStateManager::_LoadExtensionState(
        CExtensionStateManager *this,
        const unsigned __int16 *a2,
        struct EXTENSION_STATE *a3)
{
  int v6; // ebx
  HKEY v7; // rcx
  DWORD pcbData; // [rsp+60h] [rbp+8h] BYREF
  HKEY hkey; // [rsp+70h] [rbp+18h] BYREF

  memset_0(a3, 0, 0x20Cu);
  *((_DWORD *)a3 + 131) = -1;
  if ( *((_QWORD *)this + 2) )
  {
    v6 = StringCchCopyW((unsigned __int16 *)a3, 0x104u, a2);
    if ( v6 >= 0 )
    {
      v7 = (HKEY)*((_QWORD *)this + 2);
      hkey = 0;
      if ( !RegOpenKeyExW(v7, (LPCWSTR)a3, 0, 0x20019u, &hkey) )
      {
        pcbData = 4;
        RegGetValueW(hkey, 0, L"State", 0x10u, 0, (char *)a3 + 520, &pcbData);
        pcbData = 4;
        RegGetValueW(hkey, 0, L"PinnedOrder", 0x10u, 0, (char *)a3 + 524, &pcbData);
        RegCloseKey(hkey);
      }
    }
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180069864  mov     [rsp+arg_8], rbx
0x180069869  push    rsi
0x18006986a  push    rdi
0x18006986b  push    r14
0x18006986d  sub     rsp, 40h
0x180069871  mov     rdi, r8
0x180069874  mov     rbx, rdx
0x180069877  mov     rsi, rcx
0x18006987a  xor     edx, edx; Val
0x18006987c  mov     rcx, rdi; void *
0x18006987f  mov     r8d, 20Ch; Size
0x180069885  call    memset_0
0x18006988a  lea     r14, [rdi+20Ch]
0x180069891  mov     dword ptr [r14], 0FFFFFFFFh
0x180069898  cmp     qword ptr [rsi+10h], 0
0x18006989d  jnz     short loc_1800698A9
0x18006989f  mov     ebx, 8000FFFFh
0x1800698a4  jmp     loc_18006996E
0x1800698a9  mov     r8, rbx; unsigned __int16 *
0x1800698ac  mov     edx, 104h; unsigned __int64
0x1800698b1  mov     rcx, rdi; unsigned __int16 *
0x1800698b4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800698b9  mov     ebx, eax
0x1800698bb  test    eax, eax
0x1800698bd  js      loc_18006996E
0x1800698c3  mov     rcx, [rsi+10h]; hKey
0x1800698c7  lea     rax, [rsp+58h+hkey]
0x1800698cc  mov     r9d, 20019h; samDesired
0x1800698d2  mov     [rsp+58h+phkResult], rax; phkResult
0x1800698d7  xor     r8d, r8d; ulOptions
0x1800698da  mov     [rsp+58h+hkey], 0
0x1800698e3  mov     rdx, rdi; lpSubKey
0x1800698e6  call    cs:__imp_RegOpenKeyExW
0x1800698ec  test    eax, eax
0x1800698ee  jnz     short loc_18006996E
0x1800698f0  lea     esi, [rax+4]
0x1800698f3  xor     edx, edx; lpSubKey
0x1800698f5  lea     rax, [rdi+208h]
0x1800698fc  mov     [rsp+58h+arg_0], esi
0x180069900  lea     rcx, [rsp+58h+arg_0]
0x180069905  mov     [rsp+58h+pcbData], rcx; pcbData
0x18006990a  lea     edi, [rsi+0Ch]
0x18006990d  mov     rcx, [rsp+58h+hkey]; hkey
0x180069912  lea     r8, aState; "State"
0x180069919  mov     [rsp+58h+pvData], rax; pvData
0x18006991e  mov     r9d, edi; dwFlags
0x180069921  mov     [rsp+58h+phkResult], 0; pdwType
0x18006992a  call    cs:__imp_RegGetValueW
0x180069930  mov     rcx, [rsp+58h+hkey]; hkey
0x180069935  lea     rax, [rsp+58h+arg_0]
0x18006993a  mov     [rsp+58h+pcbData], rax; pcbData
0x18006993f  lea     r8, aPinnedorder; "PinnedOrder"
0x180069946  mov     [rsp+58h+pvData], r14; pvData
0x18006994b  mov     r9d, edi; dwFlags
0x18006994e  xor     edx, edx; lpSubKey
0x180069950  mov     [rsp+58h+phkResult], 0; pdwType
0x180069959  mov     [rsp+58h+arg_0], esi
0x18006995d  call    cs:__imp_RegGetValueW
0x180069963  mov     rcx, [rsp+58h+hkey]; hKey
0x180069968  call    cs:__imp_RegCloseKey
0x18006996e  mov     eax, ebx
0x180069970  mov     rbx, [rsp+58h+arg_8]
0x180069975  add     rsp, 40h
0x180069979  pop     r14
0x18006997b  pop     rdi
0x18006997c  pop     rsi
0x18006997d  retn
```
