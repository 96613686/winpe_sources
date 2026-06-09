# RegistryPath::OpenSubKey(ulong,HKEY__ * *,int)

- ea: `0x180081b94`
- end: `0x180081c3f`
- name: `?OpenSubKey@RegistryPath@@QEBAKKPEAPEAUHKEY__@@H@Z`
- size: `171`
- prototype: `unsigned int __fastcall(RegistryPath *__hidden this, unsigned int, HKEY *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180081b6c`

## callees

- `0x18007d1b8`
- `0x18007d37c`
- `0x180081b94`
- `0x180081f84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180081bd3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180081bd3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180081c11`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180081c11`

## string_xrefs

- `0x180081be2`: `RegOpenKeyExW`
- `0x180081bfd`: `%s: Failed to open registry key "%s". Error code: 0x%08x.`
- `0x180081bf3`: `RegistryPath::OpenSubKey`
- `0x180081c1e`: `RegistryPath::OpenSubKey`
- `0x180081c25`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`

## pseudocode

```c
__int64 __fastcall RegistryPath::OpenSubKey(RegistryPath *this, __int64 a2, HKEY *a3)
{
  const WCHAR *v5; // rax
  __int64 v6; // rcx
  PHKEY phkResult; // r8
  LSTATUS v8; // eax
  unsigned int v9; // esi

  *a3 = 0;
  if ( *((_QWORD *)this + 4) && *(_QWORD *)this && **(_WORD **)this )
  {
    v5 = RegistryPath::SubPath(this);
    v8 = RegOpenKeyExW(*(HKEY *)(v6 + 32), v5, 0, 1u, phkResult);
    v9 = v8;
    if ( v8 )
    {
      Logger::WriteRegistryFailureEvent(v8, L"RegOpenKeyExW", *(const unsigned __int16 **)this);
      Logger::TraceError(
        L"%s: Failed to open registry key \"%s\". Error code: 0x%08x.",
        L"RegistryPath::OpenSubKey",
        *(_QWORD *)this,
        v9);
      if ( *a3 )
      {
        RegCloseKey(*a3);
        *a3 = 0;
      }
    }
    return v9;
  }
  else
  {
    Logger::TraceError(
      L"%s: This path object has not been properly initiliazed. Either root key or full path is NULL.",
      L"RegistryPath::OpenSubKey");
    return 87;
  }
}

```

## disassembly

```asm
0x180081b94  push    rbx
0x180081b96  push    rbp
0x180081b97  push    rsi
0x180081b98  push    rdi
0x180081b99  sub     rsp, 38h
0x180081b9d  xor     ebp, ebp
0x180081b9f  mov     rdi, r8
0x180081ba2  mov     [r8], rbp
0x180081ba5  mov     rbx, rcx
0x180081ba8  cmp     [rcx+20h], rbp
0x180081bac  jz      short loc_180081C1E
0x180081bae  mov     rax, [rcx]
0x180081bb1  test    rax, rax
0x180081bb4  jz      short loc_180081C1E
0x180081bb6  cmp     [rax], bp
0x180081bb9  jz      short loc_180081C1E
0x180081bbb  call    ?SubPath@RegistryPath@@QEBAPEBGXZ; RegistryPath::SubPath(void)
0x180081bc0  mov     rcx, [rcx+20h]; hKey
0x180081bc4  lea     r9d, [rbp+1]; samDesired
0x180081bc8  mov     [rsp+58h+phkResult], r8; phkResult
0x180081bcd  mov     rdx, rax; lpSubKey
0x180081bd0  xor     r8d, r8d; ulOptions
0x180081bd3  call    cs:__imp_RegOpenKeyExW
0x180081bd9  mov     esi, eax
0x180081bdb  test    eax, eax
0x180081bdd  jz      short loc_180081C1A
0x180081bdf  mov     r8, [rbx]; unsigned __int16 *
0x180081be2  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x180081be9  mov     ecx, eax; unsigned int
0x180081beb  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *)
0x180081bf0  mov     r8, [rbx]
0x180081bf3  lea     rdx, aRegistrypathOp; "RegistryPath::OpenSubKey"
0x180081bfa  mov     r9d, esi
0x180081bfd  lea     rcx, aSFailedToOpenR; "%s: Failed to open registry key \"%s\"."...
0x180081c04  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180081c09  mov     rcx, [rdi]; hKey
0x180081c0c  test    rcx, rcx
0x180081c0f  jz      short loc_180081C1A
0x180081c11  call    cs:__imp_RegCloseKey
0x180081c17  mov     [rdi], rbp
0x180081c1a  mov     eax, esi
0x180081c1c  jmp     short loc_180081C36
0x180081c1e  lea     rdx, aRegistrypathOp; "RegistryPath::OpenSubKey"
0x180081c25  lea     rcx, aSThisPathObjec; "%s: This path object has not been prope"...
0x180081c2c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180081c31  mov     eax, 57h ; 'W'
0x180081c36  add     rsp, 38h
0x180081c3a  pop     rdi
0x180081c3b  pop     rsi
0x180081c3c  pop     rbp
0x180081c3d  pop     rbx
0x180081c3e  retn
```
