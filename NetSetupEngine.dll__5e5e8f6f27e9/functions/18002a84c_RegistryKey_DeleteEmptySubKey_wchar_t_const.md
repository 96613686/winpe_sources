# RegistryKey::DeleteEmptySubKey(wchar_t const *)

- ea: `0x18002a84c`
- end: `0x18002a90a`
- name: `?DeleteEmptySubKey@RegistryKey@@QEBAXPEB_W@Z`
- size: `190`
- prototype: `void __fastcall(RegistryKey *__hidden this, const wchar_t *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180027ac0`
- `0x18002a348`
- `0x180038b30`

## callees

- `0x18002a84c`
- `0x18002b624`
- `0x180065035`
- `0x18006e0b4`
- `0x18007fe54`

## import_xrefs

- `ntdll!NtDeleteKey` at `0x18002a889`
- `ntdll!NtDeleteKey` at `0x18002a889`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a8f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a8f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RegistryKey::DeleteEmptySubKey(HKEY *this, const wchar_t *a2)
{
  int v2; // esi
  NTSTATUS v3; // edi
  int v4; // r8d
  HANDLE KeyHandle[2]; // [rsp+30h] [rbp-E8h] BYREF
  _BYTE pExceptionObject[216]; // [rsp+40h] [rbp-D8h] BYREF

  KeyHandle[1] = (HANDLE)-2LL;
  v2 = (int)a2;
  RegistryKey::OpenSubKey(this, (HKEY)KeyHandle, a2, 0x10000u, 0);
  v3 = NtDeleteKey(KeyHandle[0]);
  if ( v3 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_Sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), v3 | 0x10000000, v4, v2, v3, v3);
    NtStatusException::NtStatusException((NtStatusException *)pExceptionObject, v3);
    throw (NtStatusException *)pExceptionObject;
  }
  if ( KeyHandle[0] )
    RegCloseKey((HKEY)KeyHandle[0]);
}

```

## disassembly

```asm
0x18002a84c  mov     rax, rsp
0x18002a84f  push    rdi
0x18002a850  sub     rsp, 110h
0x18002a857  mov     [rsp+118h+var_E0], 0FFFFFFFFFFFFFFFEh
0x18002a860  mov     [rax+18h], rsi
0x18002a864  mov     rsi, rdx
0x18002a867  mov     [rsp+118h+var_F8], 0
0x18002a870  mov     r9d, 10000h
0x18002a876  mov     r8, rdx
0x18002a879  lea     rdx, [rsp+118h+KeyHandle]
0x18002a87e  call    ?OpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::OpenSubKey(wchar_t const *,ulong,void *)
0x18002a883  nop
0x18002a884  mov     rcx, [rsp+118h+KeyHandle]; KeyHandle
0x18002a889  call    cs:__imp_NtDeleteKey
0x18002a88f  mov     edi, eax
0x18002a891  test    eax, eax
0x18002a893  jns     short loc_18002A8E6
0x18002a895  lea     rax, WPP_GLOBAL_Control
0x18002a89c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a8a3  cmp     rcx, rax
0x18002a8a6  jz      short loc_18002A8C8
0x18002a8a8  cmp     byte ptr [rcx+19h], 2
0x18002a8ac  jb      short loc_18002A8C8
0x18002a8ae  mov     edx, edi
0x18002a8b0  bts     edx, 1Ch
0x18002a8b4  mov     [rsp+118h+var_F0], edx
0x18002a8b8  mov     dword ptr [rsp+118h+var_F8], edi
0x18002a8bc  mov     r9, rsi
0x18002a8bf  mov     rcx, [rcx+10h]
0x18002a8c3  call    WPP_SF_Sdd
0x18002a8c8  mov     edx, edi; int
0x18002a8ca  lea     rcx, [rsp+118h+pExceptionObject]; this
0x18002a8cf  call    ??0NtStatusException@@QEAA@J@Z; NtStatusException::NtStatusException(long)
0x18002a8d4  lea     rdx, _TI4?AVNtStatusException@@; pThrowInfo
0x18002a8db  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x18002a8e0  call    _CxxThrowException_0
0x18002a8e6  cmp     [rsp+118h+KeyHandle], 0
0x18002a8ec  jz      short loc_18002A8F9
0x18002a8ee  mov     rcx, [rsp+118h+KeyHandle]; hKey
0x18002a8f3  call    cs:__imp_RegCloseKey
0x18002a8f9  mov     rsi, [rsp+118h+arg_10]
0x18002a901  add     rsp, 110h
0x18002a908  pop     rdi
0x18002a909  retn
```
