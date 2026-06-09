# ATL::CAtlTransactionManager::RegCreateKeyExW(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *)

- ea: `0x180003d7c`
- end: `0x180003e74`
- name: `?RegCreateKeyExW@CAtlTransactionManager@ATL@@QEAAJPEAUHKEY__@@PEBGKPEAGKKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU3@PEAK@Z`
- size: `248`
- prototype: `int(ATL::CAtlTransactionManager *__hidden this, HKEY, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *const, HKEY *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800049b8`

## callees

- `0x180003d7c`
- `0x18000e4a0`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x180003e57`
- `ADVAPI32!RegCreateKeyExW` at `0x180003e57`
- `KERNEL32!GetProcAddress` at `0x180003dba`
- `KERNEL32!GetProcAddress` at `0x180003dba`
- `KERNEL32!GetModuleHandleW` at `0x180003da1`
- `KERNEL32!GetModuleHandleW` at `0x180003da1`

## string_xrefs

- `0x180003db0`: `RegCreateKeyTransactedW`
- `0x180003d9a`: `Advapi32.dll`

## pseudocode

```c
LSTATUS __fastcall ATL::CAtlTransactionManager::RegCreateKeyExW(
        ATL::CAtlTransactionManager *this,
        HKEY a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned __int16 *a5,
        unsigned int a6,
        unsigned int a7,
        struct _SECURITY_ATTRIBUTES *const a8,
        HKEY *phkResult,
        unsigned int *lpdwDisposition)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  if ( *(_QWORD *)this )
  {
    ModuleHandleW = GetModuleHandleW(L"Advapi32.dll");
    if ( ModuleHandleW )
    {
      ProcAddress = GetProcAddress(ModuleHandleW, "RegCreateKeyTransactedW");
      if ( ProcAddress )
        return ((__int64 (__fastcall *)(HKEY, const unsigned __int16 *, _QWORD, _QWORD, _DWORD, int, _QWORD, HKEY *, unsigned int *, _QWORD, _QWORD))ProcAddress)(
                 a2,
                 a3,
                 0,
                 0,
                 0,
                 131103,
                 0,
                 phkResult,
                 lpdwDisposition,
                 *(_QWORD *)this,
                 0);
    }
  }
  else if ( *((_DWORD *)this + 2) )
  {
    return RegCreateKeyExW(a2, a3, 0, 0, 0, 0x2001Fu, 0, phkResult, lpdwDisposition);
  }
  return 1;
}

```

## disassembly

```asm
0x180003d7c  mov     [rsp+arg_0], rbx
0x180003d81  mov     [rsp+arg_8], rsi
0x180003d86  push    rdi
0x180003d87  sub     rsp, 60h
0x180003d8b  cmp     qword ptr [rcx], 0
0x180003d8f  mov     rdi, r8
0x180003d92  mov     rsi, rdx
0x180003d95  mov     rbx, rcx
0x180003d98  jz      short loc_180003E18
0x180003d9a  lea     rcx, aAdvapi32Dll_0; "Advapi32.dll"
0x180003da1  call    cs:__imp_GetModuleHandleW
0x180003da7  test    rax, rax
0x180003daa  jz      loc_180003E5F
0x180003db0  lea     rdx, aRegcreatekeytr; "RegCreateKeyTransactedW"
0x180003db7  mov     rcx, rax; hModule
0x180003dba  call    cs:__imp_GetProcAddress
0x180003dc0  test    rax, rax
0x180003dc3  jz      loc_180003E5F
0x180003dc9  and     [rsp+68h+var_18], 0
0x180003dcf  xor     r9d, r9d
0x180003dd2  mov     rcx, [rbx]
0x180003dd5  xor     r8d, r8d
0x180003dd8  mov     [rsp+68h+var_20], rcx
0x180003ddd  mov     rdx, rdi
0x180003de0  mov     rcx, [rsp+68h+arg_48]
0x180003de8  mov     [rsp+68h+lpdwDisposition], rcx
0x180003ded  mov     rcx, [rsp+68h+arg_40]
0x180003df5  mov     [rsp+68h+phkResult], rcx
0x180003dfa  mov     rcx, rsi
0x180003dfd  and     [rsp+68h+var_38], 0
0x180003e03  mov     [rsp+68h+samDesired], 2001Fh
0x180003e0b  and     [rsp+68h+var_48], 0
0x180003e10  call    cs:__guard_dispatch_icall_fptr
0x180003e16  jmp     short loc_180003E64
0x180003e18  cmp     dword ptr [rcx+8], 0
0x180003e1c  jz      short loc_180003E5F
0x180003e1e  mov     rax, [rsp+68h+arg_48]
0x180003e26  xor     r9d, r9d; lpClass
0x180003e29  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x180003e2e  xor     r8d, r8d; Reserved
0x180003e31  mov     rax, [rsp+68h+arg_40]
0x180003e39  mov     rdx, rdi; lpSubKey
0x180003e3c  mov     [rsp+68h+phkResult], rax; phkResult
0x180003e41  mov     rcx, rsi; hKey
0x180003e44  and     [rsp+68h+var_38], 0
0x180003e4a  mov     [rsp+68h+samDesired], 2001Fh; samDesired
0x180003e52  and     [rsp+68h+var_48], 0
0x180003e57  call    cs:__imp_RegCreateKeyExW
0x180003e5d  jmp     short loc_180003E64
0x180003e5f  mov     eax, 1
0x180003e64  mov     rbx, [rsp+68h+arg_0]
0x180003e69  mov     rsi, [rsp+68h+arg_8]
0x180003e6e  add     rsp, 60h
0x180003e72  pop     rdi
0x180003e73  retn
```
