# RegistryPath::OpenSubKey(ulong,HKEY__ * *,int)

- ea: `0x180092168`
- end: `0x180092248`
- name: `?OpenSubKey@RegistryPath@@QEBAKKPEAPEAUHKEY__@@H@Z`
- size: `224`
- prototype: `unsigned int __fastcall(RegistryPath *__hidden this, unsigned int, HKEY *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180092138`

## callees

- `0x18008aa28`
- `0x18008aa9c`
- `0x18008afb0`
- `0x180092168`
- `0x180092760`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800921b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800921b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180092218`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180092218`

## string_xrefs

- `0x1800921e9`: `RegOpenKeyExW`
- `0x180092204`: `%s: Failed to open registry key "%s". Error code: 0x%08x.`
- `0x1800921cd`: `RegistryPath::OpenSubKey`
- `0x1800921fa`: `RegistryPath::OpenSubKey`
- `0x180092225`: `RegistryPath::OpenSubKey`
- `0x18009222c`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x1800921d4`: `%s: Registry key "%s" does not exist.`

## pseudocode

```c
__int64 __fastcall RegistryPath::OpenSubKey(RegistryPath *this, unsigned int a2, HKEY *a3, int a4)
{
  const WCHAR *v7; // rax
  __int64 v8; // rcx
  PHKEY phkResult; // r8
  REGSAM v10; // r9d
  LSTATUS v11; // eax
  unsigned int v12; // ebx

  *a3 = 0;
  if ( *((_QWORD *)this + 4) && *(_QWORD *)this && **(_WORD **)this )
  {
    v7 = RegistryPath::SubPath(this);
    v11 = RegOpenKeyExW(*(HKEY *)(v8 + 32), v7, 0, v10, phkResult);
    v12 = v11;
    if ( a4 || v11 != 2 )
    {
      if ( !v11 )
        return v12;
      Logger::WriteRegistryFailureEvent(v11, L"RegOpenKeyExW", *(const unsigned __int16 **)this);
      Logger::TraceError(
        L"%s: Failed to open registry key \"%s\". Error code: 0x%08x.",
        L"RegistryPath::OpenSubKey",
        *(_QWORD *)this,
        v12);
    }
    else
    {
      Logger::TraceVerbose(L"%s: Registry key \"%s\" does not exist.", L"RegistryPath::OpenSubKey", *(_QWORD *)this);
    }
    if ( *a3 )
    {
      RegCloseKey(*a3);
      *a3 = 0;
    }
    return v12;
  }
  Logger::TraceError(
    L"%s: This path object has not been properly initiliazed. Either root key or full path is NULL.",
    L"RegistryPath::OpenSubKey",
    a3,
    a2);
  return 87;
}

```

## disassembly

```asm
0x180092168  push    rbx
0x18009216a  push    rbp
0x18009216b  push    rsi
0x18009216c  push    rdi
0x18009216d  push    r14
0x18009216f  sub     rsp, 30h
0x180092173  xor     r14d, r14d
0x180092176  mov     ebp, r9d
0x180092179  mov     [r8], r14
0x18009217c  mov     rsi, r8
0x18009217f  mov     r9d, edx
0x180092182  mov     rdi, rcx
0x180092185  cmp     [rcx+20h], r14
0x180092189  jz      loc_180092225
0x18009218f  mov     rax, [rcx]
0x180092192  test    rax, rax
0x180092195  jz      loc_180092225
0x18009219b  cmp     [rax], r14w
0x18009219f  jz      loc_180092225
0x1800921a5  call    ?SubPath@RegistryPath@@QEBAPEBGXZ; RegistryPath::SubPath(void)
0x1800921aa  mov     rcx, [rcx+20h]; hKey
0x1800921ae  mov     rdx, rax; lpSubKey
0x1800921b1  mov     [rsp+58h+phkResult], r8; phkResult
0x1800921b6  xor     r8d, r8d; ulOptions
0x1800921b9  call    cs:__imp_RegOpenKeyExW
0x1800921bf  mov     ebx, eax
0x1800921c1  test    ebp, ebp
0x1800921c3  jnz     short loc_1800921E2
0x1800921c5  cmp     eax, 2
0x1800921c8  jnz     short loc_1800921E2
0x1800921ca  mov     r8, [rdi]
0x1800921cd  lea     rdx, aRegistrypathOp; "RegistryPath::OpenSubKey"
0x1800921d4  lea     rcx, aSRegistryKeySD; "%s: Registry key \"%s\" does not exist."
0x1800921db  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800921e0  jmp     short loc_180092210
0x1800921e2  test    ebx, ebx
0x1800921e4  jz      short loc_180092221
0x1800921e6  mov     r8, [rdi]; unsigned __int16 *
0x1800921e9  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x1800921f0  mov     ecx, ebx; unsigned int
0x1800921f2  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *)
0x1800921f7  mov     r8, [rdi]
0x1800921fa  lea     rdx, aRegistrypathOp; "RegistryPath::OpenSubKey"
0x180092201  mov     r9d, ebx
0x180092204  lea     rcx, aSFailedToOpenR; "%s: Failed to open registry key \"%s\"."...
0x18009220b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180092210  mov     rcx, [rsi]; hKey
0x180092213  test    rcx, rcx
0x180092216  jz      short loc_180092221
0x180092218  call    cs:__imp_RegCloseKey
0x18009221e  mov     [rsi], r14
0x180092221  mov     eax, ebx
0x180092223  jmp     short loc_18009223D
0x180092225  lea     rdx, aRegistrypathOp; "RegistryPath::OpenSubKey"
0x18009222c  lea     rcx, aSThisPathObjec; "%s: This path object has not been prope"...
0x180092233  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180092238  mov     eax, 57h ; 'W'
0x18009223d  add     rsp, 30h
0x180092241  pop     r14
0x180092243  pop     rdi
0x180092244  pop     rsi
0x180092245  pop     rbp
0x180092246  pop     rbx
0x180092247  retn
```
