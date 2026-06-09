# ATL::CAtlTransactionManager::RegCreateKeyExW(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *)

- ea: `0x180001bec`
- end: `0x180001cf8`
- name: `?RegCreateKeyExW@CAtlTransactionManager@ATL@@QEAAJPEAUHKEY__@@PEBGKPEAGKKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU3@PEAK@Z`
- size: `268`
- prototype: `int(ATL::CAtlTransactionManager *__hidden this, HKEY, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *const, HKEY *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001cf8`

## callees

- `0x180001bec`
- `0x18004b640`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180001c0d`
- `KERNEL32!GetModuleHandleW` at `0x180001c0d`
- `KERNEL32!GetProcAddress` at `0x180001c26`
- `KERNEL32!GetProcAddress` at `0x180001c26`
- `ADVAPI32!RegCreateKeyExW` at `0x180001ce0`
- `ADVAPI32!RegCreateKeyExW` at `0x180001ce0`

## string_xrefs

- `0x180001c06`: `Advapi32.dll`
- `0x180001c1c`: `RegCreateKeyTransactedW`

## pseudocode

```c
LSTATUS __fastcall ATL::CAtlTransactionManager::RegCreateKeyExW(
        ATL::CAtlTransactionManager *this,
        HKEY a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned __int16 *a5,
        unsigned int a6,
        REGSAM samDesired,
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
        return ((__int64 (__fastcall *)(__int64, const unsigned __int16 *, _QWORD, _QWORD, int, REGSAM, _QWORD, HKEY *, unsigned int *, _QWORD, _QWORD))ProcAddress)(
                 -2147483646,
                 a3,
                 0,
                 0,
                 1,
                 samDesired,
                 0,
                 phkResult,
                 lpdwDisposition,
                 *(_QWORD *)this,
                 0);
    }
  }
  else if ( *((_DWORD *)this + 2) )
  {
    return RegCreateKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0, 1u, samDesired, 0, phkResult, lpdwDisposition);
  }
  return 1;
}

```

## disassembly

```asm
0x180001bec  mov     [rsp+arg_0], rbx
0x180001bf1  push    rdi
0x180001bf2  sub     rsp, 60h
0x180001bf6  cmp     qword ptr [rcx], 0
0x180001bfa  mov     rdi, r8
0x180001bfd  mov     rbx, rcx
0x180001c00  jz      loc_180001C94
0x180001c06  lea     rcx, ModuleName; "Advapi32.dll"
0x180001c0d  call    cs:__imp_GetModuleHandleW
0x180001c13  test    rax, rax
0x180001c16  jz      loc_180001CE8
0x180001c1c  lea     rdx, ProcName; "RegCreateKeyTransactedW"
0x180001c23  mov     rcx, rax; hModule
0x180001c26  call    cs:__imp_GetProcAddress
0x180001c2c  test    rax, rax
0x180001c2f  jz      loc_180001CE8
0x180001c35  mov     rcx, [rbx]
0x180001c38  xor     r9d, r9d
0x180001c3b  mov     [rsp+68h+var_18], 0
0x180001c44  xor     r8d, r8d
0x180001c47  mov     [rsp+68h+var_20], rcx
0x180001c4c  mov     rdx, rdi
0x180001c4f  mov     rcx, [rsp+68h+arg_48]
0x180001c57  mov     [rsp+68h+lpdwDisposition], rcx
0x180001c5c  mov     rcx, [rsp+68h+arg_40]
0x180001c64  mov     [rsp+68h+phkResult], rcx
0x180001c69  mov     ecx, [rsp+68h+arg_30]
0x180001c70  mov     [rsp+68h+lpSecurityAttributes], 0
0x180001c79  mov     [rsp+68h+samDesired], ecx
0x180001c7d  mov     rcx, 0FFFFFFFF80000002h
0x180001c84  mov     [rsp+68h+dwOptions], 1
0x180001c8c  call    cs:__guard_dispatch_icall_fptr
0x180001c92  jmp     short loc_180001CED
0x180001c94  cmp     dword ptr [rcx+8], 0
0x180001c98  jz      short loc_180001CE8
0x180001c9a  mov     rax, [rsp+68h+arg_48]
0x180001ca2  xor     r9d, r9d; lpClass
0x180001ca5  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x180001caa  xor     r8d, r8d; Reserved
0x180001cad  mov     rax, [rsp+68h+arg_40]
0x180001cb5  mov     rdx, rdi; lpSubKey
0x180001cb8  mov     [rsp+68h+phkResult], rax; phkResult
0x180001cbd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180001cc4  mov     eax, [rsp+68h+arg_30]
0x180001ccb  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180001cd4  mov     [rsp+68h+samDesired], eax; samDesired
0x180001cd8  mov     [rsp+68h+dwOptions], 1; dwOptions
0x180001ce0  call    cs:__imp_RegCreateKeyExW
0x180001ce6  jmp     short loc_180001CED
0x180001ce8  mov     eax, 1
0x180001ced  mov     rbx, [rsp+68h+arg_0]
0x180001cf2  add     rsp, 60h
0x180001cf6  pop     rdi
0x180001cf7  retn
```
