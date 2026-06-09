# ATL::CAtlTransactionManager::RegCreateKeyExW(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *)

- ea: `0x180004128`
- end: `0x18000421c`
- name: `?RegCreateKeyExW@CAtlTransactionManager@ATL@@QEAAJPEAUHKEY__@@PEBGKPEAGKKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU3@PEAK@Z`
- size: `244`
- prototype: `int(ATL::CAtlTransactionManager *__hidden this, HKEY, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *const, HKEY *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004bb4`

## callees

- `0x180004128`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x1800041ff`
- `ADVAPI32!RegCreateKeyExW` at `0x1800041ff`
- `KERNEL32!GetModuleHandleW` at `0x18000414d`
- `KERNEL32!GetModuleHandleW` at `0x18000414d`
- `KERNEL32!GetProcAddress` at `0x180004166`
- `KERNEL32!GetProcAddress` at `0x180004166`

## string_xrefs

- `0x180004146`: `Advapi32.dll`
- `0x18000415c`: `RegCreateKeyTransactedW`

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
0x180004128  mov     [rsp+arg_0], rbx
0x18000412d  mov     [rsp+arg_8], rsi
0x180004132  push    rdi
0x180004133  sub     rsp, 60h
0x180004137  cmp     qword ptr [rcx], 0
0x18000413b  mov     rdi, r8
0x18000413e  mov     rsi, rdx
0x180004141  mov     rbx, rcx
0x180004144  jz      short loc_1800041C0
0x180004146  lea     rcx, aAdvapi32Dll_0; "Advapi32.dll"
0x18000414d  call    cs:__imp_GetModuleHandleW
0x180004153  test    rax, rax
0x180004156  jz      loc_180004207
0x18000415c  lea     rdx, aRegcreatekeytr; "RegCreateKeyTransactedW"
0x180004163  mov     rcx, rax; hModule
0x180004166  call    cs:__imp_GetProcAddress
0x18000416c  test    rax, rax
0x18000416f  jz      loc_180004207
0x180004175  and     [rsp+68h+var_18], 0
0x18000417b  xor     r9d, r9d
0x18000417e  mov     rcx, [rbx]
0x180004181  xor     r8d, r8d
0x180004184  mov     [rsp+68h+var_20], rcx
0x180004189  mov     rdx, rdi
0x18000418c  mov     rcx, [rsp+68h+arg_48]
0x180004194  mov     [rsp+68h+lpdwDisposition], rcx
0x180004199  mov     rcx, [rsp+68h+arg_40]
0x1800041a1  mov     [rsp+68h+phkResult], rcx
0x1800041a6  mov     rcx, rsi
0x1800041a9  and     [rsp+68h+var_38], 0
0x1800041af  mov     [rsp+68h+samDesired], 2001Fh
0x1800041b7  and     [rsp+68h+var_48], 0
0x1800041bc  call    rax
0x1800041be  jmp     short loc_18000420C
0x1800041c0  cmp     dword ptr [rcx+8], 0
0x1800041c4  jz      short loc_180004207
0x1800041c6  mov     rax, [rsp+68h+arg_48]
0x1800041ce  xor     r9d, r9d; lpClass
0x1800041d1  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x1800041d6  xor     r8d, r8d; Reserved
0x1800041d9  mov     rax, [rsp+68h+arg_40]
0x1800041e1  mov     rdx, rdi; lpSubKey
0x1800041e4  mov     [rsp+68h+phkResult], rax; phkResult
0x1800041e9  mov     rcx, rsi; hKey
0x1800041ec  and     [rsp+68h+var_38], 0
0x1800041f2  mov     [rsp+68h+samDesired], 2001Fh; samDesired
0x1800041fa  and     [rsp+68h+var_48], 0
0x1800041ff  call    cs:__imp_RegCreateKeyExW
0x180004205  jmp     short loc_18000420C
0x180004207  mov     eax, 1
0x18000420c  mov     rbx, [rsp+68h+arg_0]
0x180004211  mov     rsi, [rsp+68h+arg_8]
0x180004216  add     rsp, 60h
0x18000421a  pop     rdi
0x18000421b  retn
```
