# CExtensionStateManager::_LoadExtensionState(ushort const *,EXTENSION_STATE *)

- ea: `0x18004ac1c`
- end: `0x18004ad36`
- name: `?_LoadExtensionState@CExtensionStateManager@@AEAAJPEBGPEAUEXTENSION_STATE@@@Z`
- size: `282`
- prototype: `__int64 __fastcall(CExtensionStateManager *this, const unsigned __int16 *, struct EXTENSION_STATE *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180045dc0`
- `0x18004ad3c`

## callees

- `0x1800030b6`
- `0x180013810`
- `0x18004ac1c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ad20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ad20`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ac9e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ac9e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004ace2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004ad15`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004ace2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004ad15`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18004ac1c  mov     [rsp+arg_8], rbx
0x18004ac21  push    rsi
0x18004ac22  push    rdi
0x18004ac23  push    r14
0x18004ac25  sub     rsp, 40h
0x18004ac29  mov     rdi, r8
0x18004ac2c  mov     rbx, rdx
0x18004ac2f  mov     rsi, rcx
0x18004ac32  xor     edx, edx; Val
0x18004ac34  mov     rcx, rdi; void *
0x18004ac37  mov     r8d, 20Ch; Size
0x18004ac3d  call    memset_0
0x18004ac42  lea     r14, [rdi+20Ch]
0x18004ac49  mov     dword ptr [r14], 0FFFFFFFFh
0x18004ac50  cmp     qword ptr [rsi+10h], 0
0x18004ac55  jnz     short loc_18004AC61
0x18004ac57  mov     ebx, 8000FFFFh
0x18004ac5c  jmp     loc_18004AD26
0x18004ac61  mov     r8, rbx; unsigned __int16 *
0x18004ac64  mov     edx, 104h; unsigned __int64
0x18004ac69  mov     rcx, rdi; unsigned __int16 *
0x18004ac6c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004ac71  mov     ebx, eax
0x18004ac73  test    eax, eax
0x18004ac75  js      loc_18004AD26
0x18004ac7b  mov     rcx, [rsi+10h]; hKey
0x18004ac7f  lea     rax, [rsp+58h+hkey]
0x18004ac84  mov     r9d, 20019h; samDesired
0x18004ac8a  mov     [rsp+58h+phkResult], rax; phkResult
0x18004ac8f  xor     r8d, r8d; ulOptions
0x18004ac92  mov     [rsp+58h+hkey], 0
0x18004ac9b  mov     rdx, rdi; lpSubKey
0x18004ac9e  call    cs:__imp_RegOpenKeyExW
0x18004aca4  test    eax, eax
0x18004aca6  jnz     short loc_18004AD26
0x18004aca8  lea     esi, [rax+4]
0x18004acab  xor     edx, edx; lpSubKey
0x18004acad  lea     rax, [rdi+208h]
0x18004acb4  mov     [rsp+58h+arg_0], esi
0x18004acb8  lea     rcx, [rsp+58h+arg_0]
0x18004acbd  mov     [rsp+58h+pcbData], rcx; pcbData
0x18004acc2  lea     edi, [rsi+0Ch]
0x18004acc5  mov     rcx, [rsp+58h+hkey]; hkey
0x18004acca  lea     r8, ValueName; "State"
0x18004acd1  mov     [rsp+58h+pvData], rax; pvData
0x18004acd6  mov     r9d, edi; dwFlags
0x18004acd9  mov     [rsp+58h+phkResult], 0; pdwType
0x18004ace2  call    cs:__imp_RegGetValueW
0x18004ace8  mov     rcx, [rsp+58h+hkey]; hkey
0x18004aced  lea     rax, [rsp+58h+arg_0]
0x18004acf2  mov     [rsp+58h+pcbData], rax; pcbData
0x18004acf7  lea     r8, aPinnedorder; "PinnedOrder"
0x18004acfe  mov     [rsp+58h+pvData], r14; pvData
0x18004ad03  mov     r9d, edi; dwFlags
0x18004ad06  xor     edx, edx; lpSubKey
0x18004ad08  mov     [rsp+58h+phkResult], 0; pdwType
0x18004ad11  mov     [rsp+58h+arg_0], esi
0x18004ad15  call    cs:__imp_RegGetValueW
0x18004ad1b  mov     rcx, [rsp+58h+hkey]; hKey
0x18004ad20  call    cs:__imp_RegCloseKey
0x18004ad26  mov     eax, ebx
0x18004ad28  mov     rbx, [rsp+58h+arg_8]
0x18004ad2d  add     rsp, 40h
0x18004ad31  pop     r14
0x18004ad33  pop     rdi
0x18004ad34  pop     rsi
0x18004ad35  retn
```
