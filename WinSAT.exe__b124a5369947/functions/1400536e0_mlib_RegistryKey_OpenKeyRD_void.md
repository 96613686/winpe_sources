# mlib::RegistryKey::OpenKeyRD(void)

- ea: `0x1400536e0`
- end: `0x140053737`
- name: `?OpenKeyRD@RegistryKey@mlib@@QEAAHXZ`
- size: `87`
- prototype: `__int64 __fastcall(mlib::RegistryKey *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140053900`
- `0x14005396c`

## callees

- `0x1400536e0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140053708`
- `ADVAPI32!RegOpenKeyExW` at `0x140053708`
- `KERNEL32!SetLastError` at `0x140053712`
- `KERNEL32!SetLastError` at `0x140053712`

## pseudocode

```c
__int64 __fastcall mlib::RegistryKey::OpenKeyRD(HKEY *this)
{
  _QWORD *v1; // rdi
  LSTATUS v2; // ebx

  v1 = this + 1;
  v2 = RegOpenKeyExW(this[4], *((LPCWSTR *)this[3] + 3), 0, 0x20019u, this + 1);
  SetLastError(v2);
  if ( !v2 )
    return 0;
  *v1 = 0;
  return 1;
}

```

## disassembly

```asm
0x1400536e0  mov     [rsp+arg_0], rbx
0x1400536e5  push    rdi
0x1400536e6  sub     rsp, 30h
0x1400536ea  mov     rdx, [rcx+18h]
0x1400536ee  lea     rdi, [rcx+8]
0x1400536f2  mov     rcx, [rcx+20h]; hKey
0x1400536f6  mov     r9d, 20019h; samDesired
0x1400536fc  xor     r8d, r8d; ulOptions
0x1400536ff  mov     [rsp+38h+phkResult], rdi; phkResult
0x140053704  mov     rdx, [rdx+18h]; lpSubKey
0x140053708  call    cs:__imp_RegOpenKeyExW
0x14005370e  mov     ecx, eax; dwErrCode
0x140053710  mov     ebx, eax
0x140053712  call    cs:__imp_SetLastError
0x140053718  test    ebx, ebx
0x14005371a  jnz     short loc_140053720
0x14005371c  xor     eax, eax
0x14005371e  jmp     short loc_14005372C
0x140053720  mov     qword ptr [rdi], 0
0x140053727  mov     eax, 1
0x14005372c  mov     rbx, [rsp+38h+arg_0]
0x140053731  add     rsp, 30h
0x140053735  pop     rdi
0x140053736  retn
```
