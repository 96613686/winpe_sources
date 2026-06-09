# mlib::RegistryKey::OpenKeyWR(void)

- ea: `0x18002e1f8`
- end: `0x18002e276`
- name: `?OpenKeyWR@RegistryKey@mlib@@QEAAHXZ`
- size: `126`
- prototype: `__int64 __fastcall(mlib::RegistryKey *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002e380`

## callees

- `0x18002e1f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002e23d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002e23d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e24d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e24d`

## pseudocode

```c
__int64 __fastcall mlib::RegistryKey::OpenKeyWR(mlib::RegistryKey *this)
{
  __int64 v1; // rax
  _QWORD *v2; // rdi
  LSTATUS v3; // ebx
  DWORD v5; // [rsp+60h] [rbp+8h] BYREF

  v1 = *((_QWORD *)this + 3);
  v5 = 0;
  v2 = (_QWORD *)((char *)this + 8);
  v3 = RegCreateKeyExW(*((HKEY *)this + 4), *(LPCWSTR *)(v1 + 24), 0, 0, 0, 0x20006u, 0, (PHKEY)this + 1, &v5);
  SetLastError(v3);
  if ( !v3 )
    return 0;
  *v2 = 0;
  return 1;
}

```

## disassembly

```asm
0x18002e1f8  mov     r11, rsp
0x18002e1fb  mov     [r11+10h], rbx
0x18002e1ff  push    rdi
0x18002e200  sub     rsp, 50h
0x18002e204  mov     rax, [rcx+18h]
0x18002e208  lea     rdx, [r11+8]
0x18002e20c  and     [rsp+58h+arg_0], 0
0x18002e211  lea     rdi, [rcx+8]
0x18002e215  mov     rcx, [rcx+20h]; hKey
0x18002e219  xor     r9d, r9d; lpClass
0x18002e21c  mov     [r11-18h], rdx
0x18002e220  xor     r8d, r8d; Reserved
0x18002e223  mov     rdx, [rax+18h]; lpSubKey
0x18002e227  mov     [r11-20h], rdi
0x18002e22b  and     qword ptr [r11-28h], 0
0x18002e230  mov     [rsp+58h+samDesired], 20006h; samDesired
0x18002e238  and     [rsp+58h+var_38], 0
0x18002e23d  call    cs:__imp_RegCreateKeyExW
0x18002e244  nop     dword ptr [rax+rax+00h]
0x18002e249  mov     ecx, eax; dwErrCode
0x18002e24b  mov     ebx, eax
0x18002e24d  call    cs:__imp_SetLastError
0x18002e254  nop     dword ptr [rax+rax+00h]
0x18002e259  test    ebx, ebx
0x18002e25b  jnz     short loc_18002E261
0x18002e25d  xor     eax, eax
0x18002e25f  jmp     short loc_18002E26A
0x18002e261  and     qword ptr [rdi], 0
0x18002e265  mov     eax, 1
0x18002e26a  mov     rbx, [rsp+58h+arg_8]
0x18002e26f  add     rsp, 50h
0x18002e273  pop     rdi
0x18002e274  retn
```
