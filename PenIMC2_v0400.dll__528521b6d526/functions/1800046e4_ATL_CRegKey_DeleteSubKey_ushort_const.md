# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800046e4`
- end: `0x1800047ec`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `264`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180004550`

## callees

- `0x1800046e4`
- `0x18000e4a0`

## import_xrefs

- `ADVAPI32!RegDeleteKeyW` at `0x18000475d`
- `ADVAPI32!RegDeleteKeyW` at `0x18000475d`
- `KERNEL32!GetProcAddress` at `0x180004727`
- `KERNEL32!GetProcAddress` at `0x18000479f`
- `KERNEL32!GetProcAddress` at `0x180004727`
- `KERNEL32!GetProcAddress` at `0x18000479f`
- `KERNEL32!GetModuleHandleW` at `0x180004712`
- `KERNEL32!GetModuleHandleW` at `0x18000478a`
- `KERNEL32!GetModuleHandleW` at `0x180004712`
- `KERNEL32!GetModuleHandleW` at `0x18000478a`

## string_xrefs

- `0x18000471d`: `RegDeleteKeyTransactedW`
- `0x18000470b`: `Advapi32.dll`
- `0x180004783`: `Advapi32.dll`
- `0x180004795`: `RegDeleteKeyExW`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::DeleteSubKey(ATL::CRegKey *this, const unsigned __int16 *a2)
{
  __int64 v2; // rdi
  const unsigned __int16 *v3; // rsi
  __int64 v5; // rbx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  HKEY v9; // rcx
  HMODULE v10; // rax
  FARPROC v11; // r10

  v2 = *((_QWORD *)this + 2);
  v3 = a2;
  if ( v2 )
  {
    v5 = *(_QWORD *)this;
    if ( *(_QWORD *)v2 )
    {
      ModuleHandleW = GetModuleHandleW(L"Advapi32.dll");
      if ( ModuleHandleW )
      {
        ProcAddress = GetProcAddress(ModuleHandleW, "RegDeleteKeyTransactedW");
        if ( ProcAddress )
          return ((__int64 (__fastcall *)(__int64, const unsigned __int16 *, _QWORD, _QWORD, _QWORD, _QWORD))ProcAddress)(
                   v5,
                   v3,
                   0,
                   0,
                   *(_QWORD *)v2,
                   0);
      }
      return 1;
    }
    if ( !*(_DWORD *)(v2 + 8) )
      return 1;
    v9 = *(HKEY *)this;
    return RegDeleteKeyW(v9, a2);
  }
  if ( `ATL::CRegKey::DeleteSubKey'::`2'::bInitialized )
  {
    v11 = (FARPROC)`ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx;
  }
  else
  {
    v10 = GetModuleHandleW(L"Advapi32.dll");
    if ( v10 )
    {
      v11 = GetProcAddress(v10, "RegDeleteKeyExW");
      `ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx = (__int64)v11;
    }
    else
    {
      v11 = (FARPROC)`ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx;
    }
    `ATL::CRegKey::DeleteSubKey'::`2'::bInitialized = 1;
  }
  v9 = *(HKEY *)this;
  a2 = v3;
  if ( !v11 )
    return RegDeleteKeyW(v9, a2);
  return ((__int64 (__fastcall *)(HKEY, const unsigned __int16 *, _QWORD, _QWORD))v11)(
           v9,
           v3,
           *((unsigned int *)this + 2),
           0);
}

```

## disassembly

```asm
0x1800046e4  mov     [rsp+arg_0], rbx
0x1800046e9  mov     [rsp+arg_8], rsi
0x1800046ee  push    rdi
0x1800046ef  sub     rsp, 40h
0x1800046f3  mov     rdi, [rcx+10h]
0x1800046f7  mov     rsi, rdx
0x1800046fa  mov     rbx, rcx
0x1800046fd  test    rdi, rdi
0x180004700  jz      short loc_18000477A
0x180004702  cmp     qword ptr [rdi], 0
0x180004706  mov     rbx, [rcx]
0x180004709  jz      short loc_180004754
0x18000470b  lea     rcx, aAdvapi32Dll_0; "Advapi32.dll"
0x180004712  call    cs:__imp_GetModuleHandleW
0x180004718  test    rax, rax
0x18000471b  jz      short loc_180004773
0x18000471d  lea     rdx, aRegdeletekeytr; "RegDeleteKeyTransactedW"
0x180004724  mov     rcx, rax; hModule
0x180004727  call    cs:__imp_GetProcAddress
0x18000472d  test    rax, rax
0x180004730  jz      short loc_180004773
0x180004732  mov     rdx, [rdi]
0x180004735  xor     r9d, r9d
0x180004738  and     [rsp+48h+var_20], 0
0x18000473e  xor     r8d, r8d
0x180004741  mov     [rsp+48h+var_28], rdx
0x180004746  mov     rcx, rbx
0x180004749  mov     rdx, rsi
0x18000474c  call    cs:__guard_dispatch_icall_fptr
0x180004752  jmp     short loc_180004763
0x180004754  cmp     dword ptr [rdi+8], 0
0x180004758  jz      short loc_180004773
0x18000475a  mov     rcx, rbx; hKey
0x18000475d  call    cs:__imp_RegDeleteKeyW
0x180004763  mov     rbx, [rsp+48h+arg_0]
0x180004768  mov     rsi, [rsp+48h+arg_8]
0x18000476d  add     rsp, 40h
0x180004771  pop     rdi
0x180004772  retn
0x180004773  mov     eax, 1
0x180004778  jmp     short loc_180004763
0x18000477a  cmp     cs:?bInitialized@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4_NA, 0; bool `ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::bInitialized
0x180004781  jnz     short loc_1800047C5
0x180004783  lea     rcx, aAdvapi32Dll_0; "Advapi32.dll"
0x18000478a  call    cs:__imp_GetModuleHandleW
0x180004790  test    rax, rax
0x180004793  jz      short loc_1800047B1
0x180004795  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18000479c  mov     rcx, rax; hModule
0x18000479f  call    cs:__imp_GetProcAddress
0x1800047a5  mov     r10, rax
0x1800047a8  mov     cs:?pfnRegDeleteKeyEx@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4P6AJPEAUHKEY__@@0KK@ZEA, rax; long (*`ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::pfnRegDeleteKeyEx)(HKEY__ *,ushort const *,ulong,ulong)
0x1800047af  jmp     short loc_1800047B8
0x1800047b1  mov     r10, cs:?pfnRegDeleteKeyEx@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4P6AJPEAUHKEY__@@0KK@ZEA; long (*`ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::pfnRegDeleteKeyEx)(HKEY__ *,ushort const *,ulong,ulong)
0x1800047b8  mov     eax, 1
0x1800047bd  mov     cs:?bInitialized@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4_NA, al; bool `ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::bInitialized
0x1800047c3  jmp     short loc_1800047CC
0x1800047c5  mov     r10, cs:?pfnRegDeleteKeyEx@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4P6AJPEAUHKEY__@@0KK@ZEA; long (*`ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::pfnRegDeleteKeyEx)(HKEY__ *,ushort const *,ulong,ulong)
0x1800047cc  mov     rcx, [rbx]
0x1800047cf  mov     rdx, rsi
0x1800047d2  test    r10, r10
0x1800047d5  jz      short loc_18000475D
0x1800047d7  mov     r8d, [rbx+8]
0x1800047db  xor     r9d, r9d
0x1800047de  mov     rax, r10
0x1800047e1  call    cs:__guard_dispatch_icall_fptr
0x1800047e7  jmp     loc_180004763
```
