# mlib::RegistryKey::OpenKeyWR(void)

- ea: `0x140053740`
- end: `0x1400537bd`
- name: `?OpenKeyWR@RegistryKey@mlib@@QEAAHXZ`
- size: `125`
- prototype: `__int64 __fastcall(mlib::RegistryKey *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000e074`
- `0x140053bf0`

## callees

- `0x140053740`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x14005378e`
- `ADVAPI32!RegCreateKeyExW` at `0x14005378e`
- `KERNEL32!SetLastError` at `0x140053798`
- `KERNEL32!SetLastError` at `0x140053798`

## pseudocode

```c
__int64 __fastcall mlib::RegistryKey::OpenKeyWR(mlib::RegistryKey *this)
{
  __int64 v1; // rdx
  HKEY *v2; // rdi
  HKEY v3; // rcx
  LSTATUS v4; // ebx
  DWORD v6; // [rsp+60h] [rbp+8h] BYREF

  v1 = *((_QWORD *)this + 3);
  v2 = (HKEY *)((char *)this + 8);
  v3 = (HKEY)*((_QWORD *)this + 4);
  v6 = 0;
  v4 = RegCreateKeyExW(v3, *(LPCWSTR *)(v1 + 24), 0, 0, 0, 0x20006u, 0, v2, &v6);
  SetLastError(v4);
  if ( !v4 )
    return 0;
  *v2 = 0;
  return 1;
}

```

## disassembly

```asm
0x140053740  mov     r11, rsp
0x140053743  mov     [r11+10h], rbx
0x140053747  push    rdi
0x140053748  sub     rsp, 50h
0x14005374c  mov     rdx, [rcx+18h]
0x140053750  lea     rdi, [rcx+8]
0x140053754  mov     rcx, [rcx+20h]; hKey
0x140053758  lea     rax, [r11+8]
0x14005375c  mov     [r11-18h], rax
0x140053760  xor     r9d, r9d; lpClass
0x140053763  mov     [r11-20h], rdi
0x140053767  xor     r8d, r8d; Reserved
0x14005376a  mov     qword ptr [r11-28h], 0
0x140053772  mov     [rsp+58h+arg_0], 0
0x14005377a  mov     rdx, [rdx+18h]; lpSubKey
0x14005377e  mov     [rsp+58h+samDesired], 20006h; samDesired
0x140053786  mov     [rsp+58h+dwOptions], 0; dwOptions
0x14005378e  call    cs:__imp_RegCreateKeyExW
0x140053794  mov     ecx, eax; dwErrCode
0x140053796  mov     ebx, eax
0x140053798  call    cs:__imp_SetLastError
0x14005379e  test    ebx, ebx
0x1400537a0  jnz     short loc_1400537A6
0x1400537a2  xor     eax, eax
0x1400537a4  jmp     short loc_1400537B2
0x1400537a6  mov     qword ptr [rdi], 0
0x1400537ad  mov     eax, 1
0x1400537b2  mov     rbx, [rsp+58h+arg_8]
0x1400537b7  add     rsp, 50h
0x1400537bb  pop     rdi
0x1400537bc  retn
```
