# OOBEUserRegistration::RegisterOwner(ushort const *)

- ea: `0x18001f5b0`
- end: `0x18001f6be`
- name: `?RegisterOwner@OOBEUserRegistration@@UEAAJPEBG@Z`
- size: `270`
- prototype: `int(OOBEUserRegistration *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180007134`
- `0x180018c98`
- `0x18001b61c`
- `0x18001f5b0`
- `0x18001f6c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f647`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f647`

## string_xrefs

- `0x18001f5e5`: `shell\oobe\user\dll\oobeuserregistration.cpp`
- `0x18001f656`: `shell\oobe\user\dll\oobeuserregistration.cpp`
- `0x18001f68f`: `shell\oobe\user\dll\oobeuserregistration.cpp`

## pseudocode

```c
__int64 __fastcall OOBEUserRegistration::RegisterOwner(OOBEUserRegistration *this, const unsigned __int16 *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  unsigned int v5; // eax
  int v6; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-38h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HKEY phkResult; // [rsp+70h] [rbp+18h] BYREF

  v3 = SHRegSetString(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows NT\\CurrentVersion", L"RegisteredOwner", a2);
  v4 = v3;
  if ( v3 >= 0 )
  {
    phkResult = 0;
    v5 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows NT\\CurrentVersion",
           0,
           0,
           0,
           0x202u,
           0,
           &phkResult,
           0);
    if ( v5 )
    {
      v4 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x1E,
             (unsigned int)"shell\\oobe\\user\\dll\\oobeuserregistration.cpp",
             (const char *)v5,
             dwOptionsa);
    }
    else
    {
      v6 = SHRegSetString(phkResult, 0, L"RegisteredOwner", a2);
      v4 = v6;
      if ( v6 >= 0 )
        v4 = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1F,
          (unsigned int)"shell\\oobe\\user\\dll\\oobeuserregistration.cpp",
          (const char *)(unsigned int)v6,
          dwOptionsa);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19,
      (unsigned int)"shell\\oobe\\user\\dll\\oobeuserregistration.cpp",
      (const char *)(unsigned int)v3,
      dwOptions);
  }
  return v4;
}

```

## disassembly

```asm
0x18001f5b0  mov     [rsp+arg_0], rbx
0x18001f5b5  push    rdi
0x18001f5b6  sub     rsp, 50h
0x18001f5ba  mov     rdi, rdx
0x18001f5bd  lea     r8, aRegisteredowne; "RegisteredOwner"
0x18001f5c4  mov     r9, rdx; unsigned __int16 *
0x18001f5c7  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18001f5ce  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001f5d5  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18001f5da  mov     ebx, eax
0x18001f5dc  test    eax, eax
0x18001f5de  jns     short loc_18001F5FE
0x18001f5e0  mov     rcx, [rsp+58h]; this
0x18001f5e5  lea     r8, aShellOobeUserD_1; "shell\\oobe\\user\\dll\\oobeuserregistr"...
0x18001f5ec  mov     r9d, eax; char *
0x18001f5ef  mov     edx, 19h; void *
0x18001f5f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f5f9  jmp     loc_18001F6B1
0x18001f5fe  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18001f607  lea     rax, [rsp+58h+arg_10]
0x18001f60c  mov     [rsp+58h+phkResult], rax; phkResult
0x18001f611  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001f618  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001f621  xor     r9d, r9d; lpClass
0x18001f624  mov     [rsp+58h+samDesired], 202h; samDesired
0x18001f62c  xor     r8d, r8d; Reserved
0x18001f62f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001f636  mov     [rsp+58h+dwOptions], 0; int
0x18001f63e  mov     [rsp+58h+arg_10], 0
0x18001f647  call    cs:__imp_RegCreateKeyExW
0x18001f64d  test    eax, eax
0x18001f64f  jz      short loc_18001F66E
0x18001f651  mov     rcx, [rsp+58h]; this
0x18001f656  lea     r8, aShellOobeUserD_1; "shell\\oobe\\user\\dll\\oobeuserregistr"...
0x18001f65d  mov     r9d, eax; char *
0x18001f660  mov     edx, 1Eh; void *
0x18001f665  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001f66a  mov     ebx, eax
0x18001f66c  jmp     short loc_18001F6A7
0x18001f66e  mov     rcx, [rsp+58h+arg_10]; HKEY
0x18001f673  lea     r8, aRegisteredowne; "RegisteredOwner"
0x18001f67a  mov     r9, rdi; unsigned __int16 *
0x18001f67d  xor     edx, edx; unsigned __int16 *
0x18001f67f  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18001f684  mov     ebx, eax
0x18001f686  test    eax, eax
0x18001f688  jns     short loc_18001F6A5
0x18001f68a  mov     rcx, [rsp+58h]; this
0x18001f68f  lea     r8, aShellOobeUserD_1; "shell\\oobe\\user\\dll\\oobeuserregistr"...
0x18001f696  mov     r9d, eax; char *
0x18001f699  mov     edx, 1Fh; void *
0x18001f69e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f6a3  jmp     short loc_18001F6A7
0x18001f6a5  xor     ebx, ebx
0x18001f6a7  lea     rcx, [rsp+58h+arg_10]
0x18001f6ac  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001f6b1  mov     eax, ebx
0x18001f6b3  mov     rbx, [rsp+58h+arg_0]
0x18001f6b8  add     rsp, 50h
0x18001f6bc  pop     rdi
0x18001f6bd  retn
```
