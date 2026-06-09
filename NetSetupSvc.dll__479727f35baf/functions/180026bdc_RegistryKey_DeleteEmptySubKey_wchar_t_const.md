# RegistryKey::DeleteEmptySubKey(wchar_t const *)

- ea: `0x180026bdc`
- end: `0x180026caf`
- name: `?DeleteEmptySubKey@RegistryKey@@QEBAXPEB_W@Z`
- size: `211`
- prototype: `void __fastcall(RegistryKey *__hidden this, const wchar_t *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180026cb8`
- `0x180028104`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x180008e3c`
- `0x180010334`
- `0x180026bdc`
- `0x180027ef4`
- `0x180028a8c`

## import_xrefs

- `ntdll!NtDeleteKey` at `0x180026c24`
- `ntdll!NtDeleteKey` at `0x180026c24`

## pseudocode

```c
void __fastcall RegistryKey::DeleteEmptySubKey(RegistryKey *this, const wchar_t *a2)
{
  int v2; // edi
  NTSTATUS v3; // ebx
  int v4; // r8d
  _BYTE pExceptionObject[208]; // [rsp+30h] [rbp-E8h] BYREF
  HANDLE KeyHandle; // [rsp+100h] [rbp-18h] BYREF

  v2 = (int)a2;
  RegistryKey::OpenSubKey(this, &KeyHandle, a2, 0x10000, 0);
  v3 = NtDeleteKey(KeyHandle);
  if ( v3 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_Sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), v3 | 0x10000000, v4, v2, v3, v3);
    NtStatusException::NtStatusException((NtStatusException *)pExceptionObject, v3);
    throw (NtStatusException *)pExceptionObject;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>((HKEY *)&KeyHandle);
}

```

## disassembly

```asm
0x180026bdc  mov     r11, rsp
0x180026bdf  mov     [r11+18h], rbx
0x180026be3  push    rdi
0x180026be4  sub     rsp, 110h
0x180026beb  mov     rax, cs:__security_cookie
0x180026bf2  xor     rax, rsp
0x180026bf5  mov     [rsp+118h+var_10], rax
0x180026bfd  mov     rdi, rdx
0x180026c00  mov     [rsp+118h+var_F8], 0
0x180026c09  mov     r9d, 10000h
0x180026c0f  mov     r8, rdx
0x180026c12  lea     rdx, [r11-18h]
0x180026c16  call    ?OpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::OpenSubKey(wchar_t const *,ulong,void *)
0x180026c1b  nop
0x180026c1c  mov     rcx, [rsp+118h+KeyHandle]; KeyHandle
0x180026c24  call    cs:__imp_NtDeleteKey
0x180026c2a  mov     ebx, eax
0x180026c2c  test    eax, eax
0x180026c2e  jns     short loc_180026C81
0x180026c30  lea     rax, WPP_GLOBAL_Control
0x180026c37  mov     rcx, cs:WPP_GLOBAL_Control
0x180026c3e  cmp     rcx, rax
0x180026c41  jz      short loc_180026C63
0x180026c43  cmp     byte ptr [rcx+19h], 2
0x180026c47  jb      short loc_180026C63
0x180026c49  mov     edx, ebx
0x180026c4b  bts     edx, 1Ch
0x180026c4f  mov     [rsp+118h+var_F0], edx
0x180026c53  mov     dword ptr [rsp+118h+var_F8], ebx
0x180026c57  mov     r9, rdi
0x180026c5a  mov     rcx, [rcx+10h]
0x180026c5e  call    WPP_SF_Sdd
0x180026c63  mov     edx, ebx; int
0x180026c65  lea     rcx, [rsp+118h+pExceptionObject]; this
0x180026c6a  call    ??0NtStatusException@@QEAA@J@Z; NtStatusException::NtStatusException(long)
0x180026c6f  lea     rdx, _TI4?AVNtStatusException@@; pThrowInfo
0x180026c76  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x180026c7b  call    _CxxThrowException_0
0x180026c81  lea     rcx, [rsp+118h+KeyHandle]
0x180026c89  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180026c8e  mov     rcx, [rsp+118h+var_10]
0x180026c96  xor     rcx, rsp; StackCookie
0x180026c99  call    __security_check_cookie
0x180026c9e  mov     rbx, [rsp+118h+arg_10]
0x180026ca6  add     rsp, 110h
0x180026cad  pop     rdi
0x180026cae  retn
```
