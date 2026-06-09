# SetRegistryPathFullControlByTrustedAC(HKEY__ *,ushort const *,bool,ushort const *)

- ea: `0x180020844`
- end: `0x1800208f6`
- name: `?SetRegistryPathFullControlByTrustedAC@@YAJPEAUHKEY__@@PEBG_N1@Z`
- size: `178`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, bool, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000bcc0`

## callees

- `0x180020730`
- `0x180020844`
- `0x1800209fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800208cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800208cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020881`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020881`

## pseudocode

```c
__int64 __fastcall SetRegistryPathFullControlByTrustedAC(
        HKEY a1,
        const unsigned __int16 *a2,
        char a3,
        const unsigned __int16 *a4)
{
  __int64 v6; // rcx
  int v7; // ebx
  bool v8; // cc
  bool v10; // [rsp+20h] [rbp-28h]
  void *v11; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF

  hKey = 0;
  v7 = RegOpenKeyExW(HKEY_USERS, a2, 8u, 0xE0006u, &hKey);
  if ( v7 )
  {
    v8 = v7 < 0;
LABEL_7:
    if ( !v8 )
      return (unsigned __int16)v7 | 0x80070000;
    return (unsigned int)v7;
  }
  v11 = 0;
  LOBYTE(v6) = a3;
  v7 = SetTrustedACSid(v6, a4, &v11);
  if ( !v7 )
    v7 = SetHandleAccessWithInheritance(hKey, SE_REGISTRY_KEY, v11, 0xF003Fu, v10);
  RegCloseKey(hKey);
  v8 = v7 <= 0;
  if ( v7 )
    goto LABEL_7;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180020844  mov     r11, rsp
0x180020847  mov     [r11+10h], rbx
0x18002084b  mov     [r11+18h], rsi
0x18002084f  mov     [r11+8], rcx
0x180020853  push    rdi
0x180020854  sub     rsp, 40h
0x180020858  mov     rdi, r9
0x18002085b  mov     qword ptr [r11+8], 0
0x180020863  mov     sil, r8b
0x180020866  lea     rax, [r11+8]
0x18002086a  mov     r9d, 0E0006h; samDesired
0x180020870  mov     [r11-28h], rax
0x180020874  mov     r8d, 8; ulOptions
0x18002087a  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180020881  call    cs:__imp_RegOpenKeyExW
0x180020887  mov     ebx, eax
0x180020889  test    eax, eax
0x18002088b  jnz     short loc_1800208D7
0x18002088d  lea     r8, [rsp+48h+var_18]
0x180020892  mov     [rsp+48h+var_18], 0
0x18002089b  mov     rdx, rdi
0x18002089e  mov     cl, sil
0x1800208a1  call    _SetTrustedACSid
0x1800208a6  mov     ebx, eax
0x1800208a8  test    eax, eax
0x1800208aa  jnz     short loc_1800208C6
0x1800208ac  mov     r8, [rsp+48h+var_18]; void *
0x1800208b1  lea     edx, [rax+4]; ObjectType
0x1800208b4  mov     rcx, [rsp+48h+hKey]; handle
0x1800208b9  mov     r9d, 0F003Fh; unsigned int
0x1800208bf  call    SetHandleAccessWithInheritance
0x1800208c4  mov     ebx, eax
0x1800208c6  mov     rcx, [rsp+48h+hKey]; hKey
0x1800208cb  call    cs:__imp_RegCloseKey
0x1800208d1  test    ebx, ebx
0x1800208d3  jnz     short loc_1800208D9
0x1800208d5  jmp     short loc_1800208E4
0x1800208d7  test    ebx, ebx
0x1800208d9  jle     short loc_1800208E4
0x1800208db  movzx   ebx, bx
0x1800208de  or      ebx, 80070000h
0x1800208e4  mov     rsi, [rsp+48h+arg_10]
0x1800208e9  mov     eax, ebx
0x1800208eb  mov     rbx, [rsp+48h+arg_8]
0x1800208f0  add     rsp, 40h
0x1800208f4  pop     rdi
0x1800208f5  retn
```
