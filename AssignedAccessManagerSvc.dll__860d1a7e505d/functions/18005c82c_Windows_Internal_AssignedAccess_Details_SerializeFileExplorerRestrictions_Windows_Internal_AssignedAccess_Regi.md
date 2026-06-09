# Windows::Internal::AssignedAccess::Details::SerializeFileExplorerRestrictions<Windows::Internal::AssignedAccess::RegistryKey>(Windows::Internal::AssignedAccess::RegistryKey &,Windows::Internal::AssignedAccess::IAssignedAccessFileExplorerRestrictions *)

- ea: `0x18005c82c`
- end: `0x18005c922`
- name: `??$SerializeFileExplorerRestrictions@VRegistryKey@AssignedAccess@Internal@Windows@@@Details@AssignedAccess@Internal@Windows@@YAXAEAVRegistryKey@123@PEAUIAssignedAccessFileExplorerRestrictions@123@@Z`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18005cac0`

## callees

- `0x180020050`
- `0x18002b190`
- `0x18005c82c`
- `0x18005e090`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005c8a2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005c8a2`

## string_xrefs

- `0x18005c8b1`: `onecoreuap\internal\base\inc\embedded\registrykey.h`
- `0x18005c85e`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005c8e8`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AssignedAccess::Details::SerializeFileExplorerRestrictions<Windows::Internal::AssignedAccess::RegistryKey>(
        HKEY *a1,
        __int64 *a2)
{
  __int64 v2; // rax
  int v5; // eax
  HKEY v6; // rcx
  unsigned int v7; // eax
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rdx
  int lpData; // [rsp+20h] [rbp-18h]
  unsigned int lpDataa; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  char v15; // [rsp+48h] [rbp+10h] BYREF
  char v16; // [rsp+50h] [rbp+18h] BYREF
  BOOL Data; // [rsp+58h] [rbp+20h] BYREF

  v2 = *a2;
  v15 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, char *))(v2 + 48))(a2, &v15);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x26A,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
      (const char *)(unsigned int)v5,
      lpData);
  v6 = *a1;
  Data = v15 != 0;
  v7 = RegSetValueExW(v6, L"AllowRemovableDrives", 0, 4u, (const BYTE *)&Data, 4u);
  if ( v7 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xCD,
      (unsigned int)"onecoreuap\\internal\\base\\inc\\embedded\\registrykey.h",
      (const char *)v7,
      lpDataa);
  v8 = *a2;
  v16 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, char *))(v8 + 64))(a2, &v16);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x26E,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
      (const char *)(unsigned int)v9,
      lpDataa);
  Data = v16 != 0;
  return Windows::Internal::AssignedAccess::RegistryKey::SetDWORD<unsigned short const [14]>(a1, v10, &Data);
}

```

## disassembly

```asm
0x18005c82c  mov     [rsp+arg_0], rbx
0x18005c831  push    rdi
0x18005c832  sub     rsp, 30h
0x18005c836  mov     rax, [rdx]
0x18005c839  mov     rbx, rdx
0x18005c83c  mov     rdi, rcx
0x18005c83f  mov     [rsp+38h+arg_8], 0
0x18005c844  lea     rdx, [rsp+38h+arg_8]
0x18005c849  mov     rcx, rbx
0x18005c84c  mov     rax, [rax+30h]
0x18005c850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c855  test    eax, eax
0x18005c857  jns     short loc_18005C873
0x18005c859  mov     rcx, [rsp+38h]; this
0x18005c85e  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005c865  mov     r9d, eax; char *
0x18005c868  mov     edx, 26Ah; void *
0x18005c86d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005c873  mov     rcx, [rdi]; hKey
0x18005c876  lea     rdx, aAllowremovable; "AllowRemovableDrives"
0x18005c87d  xor     eax, eax
0x18005c87f  mov     r9d, 4; dwType
0x18005c885  cmp     [rsp+38h+arg_8], al
0x18005c889  mov     [rsp+38h+cbData], r9d; cbData
0x18005c88e  setnz   al
0x18005c891  xor     r8d, r8d; Reserved
0x18005c894  mov     [rsp+38h+Data], eax
0x18005c898  lea     rax, [rsp+38h+Data]
0x18005c89d  mov     [rsp+38h+lpData], rax; int
0x18005c8a2  call    cs:__imp_RegSetValueExW
0x18005c8a8  test    eax, eax
0x18005c8aa  jz      short loc_18005C8C6
0x18005c8ac  mov     rcx, [rsp+38h]; this
0x18005c8b1  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\base\\inc\\embedd"...
0x18005c8b8  mov     r9d, eax; char *
0x18005c8bb  mov     edx, 0CDh; void *
0x18005c8c0  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18005c8c6  mov     rax, [rbx]
0x18005c8c9  lea     rdx, [rsp+38h+arg_10]
0x18005c8ce  mov     rcx, rbx
0x18005c8d1  mov     [rsp+38h+arg_10], 0
0x18005c8d6  mov     rax, [rax+40h]
0x18005c8da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c8df  test    eax, eax
0x18005c8e1  jns     short loc_18005C8FD
0x18005c8e3  mov     rcx, [rsp+38h]; this
0x18005c8e8  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005c8ef  mov     r9d, eax; char *
0x18005c8f2  mov     edx, 26Eh; void *
0x18005c8f7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005c8fd  xor     eax, eax
0x18005c8ff  lea     r8, [rsp+38h+Data]
0x18005c904  cmp     [rsp+38h+arg_10], al
0x18005c908  mov     rcx, rdi
0x18005c90b  setnz   al
0x18005c90e  mov     [rsp+38h+Data], eax
0x18005c912  call    ??$SetDWORD@$$BY0O@$$CBG@RegistryKey@AssignedAccess@Internal@Windows@@QEBAXAEAY0O@$$CBGAEBK@Z; Windows::Internal::AssignedAccess::RegistryKey::SetDWORD<ushort const [14]>(ushort const (&)[14],ulong const &)
0x18005c917  mov     rbx, [rsp+38h+arg_0]
0x18005c91c  add     rsp, 30h
0x18005c920  pop     rdi
0x18005c921  retn
```
