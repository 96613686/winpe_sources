# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18000193c`
- end: `0x180001a37`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `251`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x1800048ec`

## callees

- `0x18000193c`

## import_xrefs

- `ADVAPI32!RegDeleteKeyW` at `0x1800019b1`
- `ADVAPI32!RegDeleteKeyW` at `0x1800019b1`
- `KERNEL32!GetModuleHandleW` at `0x18000196a`
- `KERNEL32!GetModuleHandleW` at `0x1800019de`
- `KERNEL32!GetModuleHandleW` at `0x18000196a`
- `KERNEL32!GetModuleHandleW` at `0x1800019de`
- `KERNEL32!GetProcAddress` at `0x18000197f`
- `KERNEL32!GetProcAddress` at `0x1800019f3`
- `KERNEL32!GetProcAddress` at `0x18000197f`
- `KERNEL32!GetProcAddress` at `0x1800019f3`

## string_xrefs

- `0x180001975`: `RegDeleteKeyTransactedW`
- `0x180001963`: `Advapi32.dll`
- `0x1800019d7`: `Advapi32.dll`
- `0x1800019e9`: `RegDeleteKeyExW`

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
0x18000193c  mov     [rsp+arg_0], rbx
0x180001941  mov     [rsp+arg_8], rsi
0x180001946  push    rdi
0x180001947  sub     rsp, 30h
0x18000194b  mov     rdi, [rcx+10h]
0x18000194f  mov     rsi, rdx
0x180001952  mov     rbx, rcx
0x180001955  test    rdi, rdi
0x180001958  jz      short loc_1800019CE
0x18000195a  cmp     qword ptr [rdi], 0
0x18000195e  mov     rbx, [rcx]
0x180001961  jz      short loc_1800019A8
0x180001963  lea     rcx, aAdvapi32Dll_0; "Advapi32.dll"
0x18000196a  call    cs:__imp_GetModuleHandleW
0x180001970  test    rax, rax
0x180001973  jz      short loc_1800019C7
0x180001975  lea     rdx, aRegdeletekeytr; "RegDeleteKeyTransactedW"
0x18000197c  mov     rcx, rax; hModule
0x18000197f  call    cs:__imp_GetProcAddress
0x180001985  test    rax, rax
0x180001988  jz      short loc_1800019C7
0x18000198a  mov     rdx, [rdi]
0x18000198d  xor     r9d, r9d
0x180001990  and     [rsp+38h+var_10], 0
0x180001996  xor     r8d, r8d
0x180001999  mov     [rsp+38h+var_18], rdx
0x18000199e  mov     rcx, rbx
0x1800019a1  mov     rdx, rsi
0x1800019a4  call    rax
0x1800019a6  jmp     short loc_1800019B7
0x1800019a8  cmp     dword ptr [rdi+8], 0
0x1800019ac  jz      short loc_1800019C7
0x1800019ae  mov     rcx, rbx; hKey
0x1800019b1  call    cs:__imp_RegDeleteKeyW
0x1800019b7  mov     rbx, [rsp+38h+arg_0]
0x1800019bc  mov     rsi, [rsp+38h+arg_8]
0x1800019c1  add     rsp, 30h
0x1800019c5  pop     rdi
0x1800019c6  retn
0x1800019c7  mov     eax, 1
0x1800019cc  jmp     short loc_1800019B7
0x1800019ce  cmp     cs:?bInitialized@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4_NA, 0; bool `ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::bInitialized
0x1800019d5  jnz     short loc_180001A19
0x1800019d7  lea     rcx, aAdvapi32Dll_0; "Advapi32.dll"
0x1800019de  call    cs:__imp_GetModuleHandleW
0x1800019e4  test    rax, rax
0x1800019e7  jz      short loc_180001A05
0x1800019e9  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x1800019f0  mov     rcx, rax; hModule
0x1800019f3  call    cs:__imp_GetProcAddress
0x1800019f9  mov     r10, rax
0x1800019fc  mov     cs:?pfnRegDeleteKeyEx@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4P6AJPEAUHKEY__@@0KK@ZEA, rax; long (*`ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::pfnRegDeleteKeyEx)(HKEY__ *,ushort const *,ulong,ulong)
0x180001a03  jmp     short loc_180001A0C
0x180001a05  mov     r10, cs:?pfnRegDeleteKeyEx@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4P6AJPEAUHKEY__@@0KK@ZEA; long (*`ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::pfnRegDeleteKeyEx)(HKEY__ *,ushort const *,ulong,ulong)
0x180001a0c  mov     eax, 1
0x180001a11  mov     cs:?bInitialized@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4_NA, al; bool `ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::bInitialized
0x180001a17  jmp     short loc_180001A20
0x180001a19  mov     r10, cs:?pfnRegDeleteKeyEx@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4P6AJPEAUHKEY__@@0KK@ZEA; long (*`ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::pfnRegDeleteKeyEx)(HKEY__ *,ushort const *,ulong,ulong)
0x180001a20  mov     rcx, [rbx]
0x180001a23  mov     rdx, rsi
0x180001a26  test    r10, r10
0x180001a29  jz      short loc_1800019B1
0x180001a2b  mov     r8d, [rbx+8]
0x180001a2f  xor     r9d, r9d
0x180001a32  call    r10
0x180001a35  jmp     short loc_1800019B7
```
