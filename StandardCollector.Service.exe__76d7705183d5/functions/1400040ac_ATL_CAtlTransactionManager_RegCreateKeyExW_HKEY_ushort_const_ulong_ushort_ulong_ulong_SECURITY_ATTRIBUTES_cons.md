# ATL::CAtlTransactionManager::RegCreateKeyExW(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *)

- ea: `0x1400040ac`
- end: `0x1400041b2`
- name: `?RegCreateKeyExW@CAtlTransactionManager@ATL@@QEAAJPEAUHKEY__@@PEBGKPEAGKKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU3@PEAK@Z`
- size: `262`
- prototype: `int(ATL::CAtlTransactionManager *__hidden this, HKEY, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *const, HKEY *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400041b4`

## callees

- `0x1400040ac`
- `0x140014c70`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1400040e6`
- `KERNEL32!GetProcAddress` at `0x1400040e6`
- `KERNEL32!GetModuleHandleW` at `0x1400040cd`
- `KERNEL32!GetModuleHandleW` at `0x1400040cd`
- `ADVAPI32!RegCreateKeyExW` at `0x14000419a`
- `ADVAPI32!RegCreateKeyExW` at `0x14000419a`

## string_xrefs

- `0x1400040c6`: `Advapi32.dll`
- `0x1400040dc`: `RegCreateKeyTransactedW`

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
        return ((__int64 (__fastcall *)(unsigned __int64, const unsigned __int16 *, _QWORD, _QWORD, _DWORD, int, _QWORD, HKEY *, unsigned int *, _QWORD, _QWORD))ProcAddress)(
                 0xFFFFFFFF80000000uLL,
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
    return RegCreateKeyExW(HKEY_CLASSES_ROOT, a3, 0, 0, 0, 0x2001Fu, 0, phkResult, lpdwDisposition);
  }
  return 1;
}

```

## disassembly

```asm
0x1400040ac  mov     [rsp+arg_0], rbx
0x1400040b1  push    rdi
0x1400040b2  sub     rsp, 60h
0x1400040b6  cmp     qword ptr [rcx], 0
0x1400040ba  mov     rdi, r8
0x1400040bd  mov     rbx, rcx
0x1400040c0  jz      loc_140004151
0x1400040c6  lea     rcx, ModuleName; "Advapi32.dll"
0x1400040cd  call    cs:__imp_GetModuleHandleW
0x1400040d3  test    rax, rax
0x1400040d6  jz      loc_1400041A2
0x1400040dc  lea     rdx, aRegcreatekeytr; "RegCreateKeyTransactedW"
0x1400040e3  mov     rcx, rax; hModule
0x1400040e6  call    cs:__imp_GetProcAddress
0x1400040ec  test    rax, rax
0x1400040ef  jz      loc_1400041A2
0x1400040f5  mov     rcx, [rbx]
0x1400040f8  xor     r9d, r9d
0x1400040fb  mov     [rsp+68h+var_18], 0
0x140004104  xor     r8d, r8d
0x140004107  mov     [rsp+68h+var_20], rcx
0x14000410c  mov     rdx, rdi
0x14000410f  mov     rcx, [rsp+68h+arg_48]
0x140004117  mov     [rsp+68h+lpdwDisposition], rcx
0x14000411c  mov     rcx, [rsp+68h+arg_40]
0x140004124  mov     [rsp+68h+phkResult], rcx
0x140004129  mov     rcx, 0FFFFFFFF80000000h
0x140004130  mov     [rsp+68h+lpSecurityAttributes], 0
0x140004139  mov     [rsp+68h+samDesired], 2001Fh
0x140004141  mov     [rsp+68h+dwOptions], 0
0x140004149  call    cs:__guard_dispatch_icall_fptr
0x14000414f  jmp     short loc_1400041A7
0x140004151  cmp     dword ptr [rcx+8], 0
0x140004155  jz      short loc_1400041A2
0x140004157  mov     rax, [rsp+68h+arg_48]
0x14000415f  xor     r9d, r9d; lpClass
0x140004162  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x140004167  xor     r8d, r8d; Reserved
0x14000416a  mov     rax, [rsp+68h+arg_40]
0x140004172  mov     rdx, rdi; lpSubKey
0x140004175  mov     [rsp+68h+phkResult], rax; phkResult
0x14000417a  mov     rcx, 0FFFFFFFF80000000h; hKey
0x140004181  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14000418a  mov     [rsp+68h+samDesired], 2001Fh; samDesired
0x140004192  mov     [rsp+68h+dwOptions], 0; dwOptions
0x14000419a  call    cs:__imp_RegCreateKeyExW
0x1400041a0  jmp     short loc_1400041A7
0x1400041a2  mov     eax, 1
0x1400041a7  mov     rbx, [rsp+68h+arg_0]
0x1400041ac  add     rsp, 60h
0x1400041b0  pop     rdi
0x1400041b1  retn
```
