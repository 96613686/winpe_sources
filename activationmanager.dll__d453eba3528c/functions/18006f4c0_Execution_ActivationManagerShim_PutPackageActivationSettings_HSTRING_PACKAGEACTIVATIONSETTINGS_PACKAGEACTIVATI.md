# Execution::ActivationManagerShim::PutPackageActivationSettings(HSTRING__ *,PACKAGEACTIVATIONSETTINGS,PACKAGEACTIVATIONSETTINGS)

- ea: `0x18006f4c0`
- end: `0x18006f677`
- name: `?PutPackageActivationSettings@ActivationManagerShim@Execution@@UEAAJPEAUHSTRING__@@W4PACKAGEACTIVATIONSETTINGS@@1@Z`
- size: `439`
- prototype: `int __high(HSTRING, enum PACKAGEACTIVATIONSETTINGS, enum PACKAGEACTIVATIONSETTINGS)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000b5c0`
- `0x180036ad4`
- `0x18003ab00`
- `0x18003cfc4`
- `0x1800445ac`
- `0x18006f4c0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006f5cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006f5cc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006f642`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006f642`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006f611`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006f611`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006f595`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006f595`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18006f51d`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18006f51d`

## pseudocode

```c
__int64 __fastcall Execution::ActivationManagerShim::PutPackageActivationSettings(
        Execution::ActivationManagerShim *a1,
        HSTRING a2,
        int a3,
        int a4)
{
  int v7; // eax
  unsigned int v8; // edi
  unsigned int v10; // eax
  unsigned int v11; // ebx
  unsigned int v12; // eax
  __int64 v13; // rdx
  const WCHAR *StringRawBuffer; // rdi
  unsigned int dwOptions; // [rsp+20h] [rbp-50h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-50h]
  BYTE Data[4]; // [rsp+50h] [rbp-20h] BYREF
  int pvData; // [rsp+54h] [rbp-1Ch] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-18h] BYREF
  HKEY hkey; // [rsp+60h] [rbp-10h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v7 = Execution::ActivationManagerShim::_CheckDebugPermission(a1);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x67E,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
      (const char *)(unsigned int)v7,
      dwOptions);
    return v8;
  }
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v10 = RegOpenCurrentUser(0x2001Du, &phkResult);
  if ( v10 )
  {
    v11 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x684,
            (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
            (const char *)v10,
            dwOptions);
  }
  else
  {
    hkey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hkey,
      0);
    v12 = RegCreateKeyExW(
            phkResult,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced\\PackageActivate",
            0,
            0,
            1u,
            0xF003Fu,
            0,
            &hkey,
            0);
    if ( v12 )
    {
      v13 = 1672;
    }
    else
    {
      StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
      pcbData = 4;
      pvData = 0;
      *(_DWORD *)Data = a4;
      if ( !RegGetValueW(hkey, 0, StringRawBuffer, 0x10u, 0, &pvData, &pcbData) )
        *(_DWORD *)Data |= pvData & ~a3;
      pcbData = 4;
      v12 = RegSetValueExW(hkey, StringRawBuffer, 0, 4u, Data, 4u);
      if ( !v12 )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        v11 = 0;
        goto LABEL_13;
      }
      v13 = 1685;
    }
    v11 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v13,
            (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
            (const char *)v12,
            dwOptionsa);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  }
LABEL_13:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  return v11;
}

```

## disassembly

```asm
0x18006f4c0  push    rbp
0x18006f4c2  push    rbx
0x18006f4c3  push    rsi
0x18006f4c4  push    rdi
0x18006f4c5  push    r14
0x18006f4c7  mov     rbp, rsp
0x18006f4ca  sub     rsp, 70h
0x18006f4ce  mov     esi, r9d
0x18006f4d1  mov     ebx, r8d
0x18006f4d4  mov     r14, rdx
0x18006f4d7  call    ?_CheckDebugPermission@ActivationManagerShim@Execution@@IEAAJXZ; Execution::ActivationManagerShim::_CheckDebugPermission(void)
0x18006f4dc  mov     edi, eax
0x18006f4de  test    eax, eax
0x18006f4e0  jns     short loc_18006F501
0x18006f4e2  mov     rcx, [rbp+28h]; this
0x18006f4e6  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18006f4ed  mov     r9d, eax; char *
0x18006f4f0  mov     edx, 67Eh; void *
0x18006f4f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f4fa  mov     eax, edi
0x18006f4fc  jmp     loc_18006F66C
0x18006f501  xor     edx, edx
0x18006f503  mov     [rbp+phkResult], 0
0x18006f50b  lea     rcx, [rbp+phkResult]
0x18006f50f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18006f514  lea     rdx, [rbp+phkResult]; phkResult
0x18006f518  mov     ecx, 2001Dh; samDesired
0x18006f51d  call    cs:__imp_RegOpenCurrentUser
0x18006f523  test    eax, eax
0x18006f525  jz      short loc_18006F546
0x18006f527  mov     rcx, [rbp+28h]; this
0x18006f52b  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18006f532  mov     r9d, eax; char *
0x18006f535  mov     edx, 684h; void *
0x18006f53a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006f53f  mov     ebx, eax
0x18006f541  jmp     loc_18006F661
0x18006f546  xor     edx, edx
0x18006f548  mov     [rbp+hkey], 0
0x18006f550  lea     rcx, [rbp+hkey]
0x18006f554  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18006f559  mov     rcx, [rbp+phkResult]; hKey
0x18006f55d  lea     rax, [rbp+hkey]
0x18006f561  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x18006f56a  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18006f571  mov     [rsp+70h+var_38], rax; phkResult
0x18006f576  xor     r9d, r9d; lpClass
0x18006f579  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18006f582  xor     r8d, r8d; Reserved
0x18006f585  mov     [rsp+70h+samDesired], 0F003Fh; samDesired
0x18006f58d  mov     [rsp+70h+dwOptions], 1; unsigned int
0x18006f595  call    cs:__imp_RegCreateKeyExW
0x18006f59b  test    eax, eax
0x18006f59d  jz      short loc_18006F5C7
0x18006f59f  mov     edx, 688h; void *
0x18006f5a4  mov     rcx, [rbp+28h]; this
0x18006f5a8  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18006f5af  mov     r9d, eax; char *
0x18006f5b2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006f5b7  lea     rcx, [rbp+hkey]
0x18006f5bb  mov     ebx, eax
0x18006f5bd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18006f5c2  jmp     loc_18006F661
0x18006f5c7  xor     edx, edx; length
0x18006f5c9  mov     rcx, r14; string
0x18006f5cc  call    cs:__imp_WindowsGetStringRawBuffer
0x18006f5d2  mov     rcx, [rbp+hkey]; hkey
0x18006f5d6  mov     r14d, 4
0x18006f5dc  mov     rdi, rax
0x18006f5df  mov     [rbp+pcbData], r14d
0x18006f5e3  lea     rax, [rbp+pcbData]
0x18006f5e7  mov     [rbp+pvData], 0
0x18006f5ee  mov     [rsp+70h+lpSecurityAttributes], rax; pcbData
0x18006f5f3  mov     r8, rdi; lpValue
0x18006f5f6  lea     rax, [rbp+pvData]
0x18006f5fa  mov     dword ptr [rbp+Data], esi
0x18006f5fd  mov     qword ptr [rsp+70h+samDesired], rax; pvData
0x18006f602  lea     r9d, [r14+0Ch]; dwFlags
0x18006f606  xor     edx, edx; lpSubKey
0x18006f608  mov     qword ptr [rsp+70h+dwOptions], 0; pdwType
0x18006f611  call    cs:__imp_RegGetValueW
0x18006f617  test    eax, eax
0x18006f619  jnz     short loc_18006F623
0x18006f61b  not     ebx
0x18006f61d  and     ebx, [rbp+pvData]
0x18006f620  or      dword ptr [rbp+Data], ebx
0x18006f623  mov     rcx, [rbp+hkey]; hKey
0x18006f627  lea     rax, [rbp+Data]
0x18006f62b  mov     [rsp+70h+samDesired], r14d; cbData
0x18006f630  mov     r9d, r14d; dwType
0x18006f633  xor     r8d, r8d; Reserved
0x18006f636  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x18006f63b  mov     rdx, rdi; lpValueName
0x18006f63e  mov     [rbp+pcbData], r14d
0x18006f642  call    cs:__imp_RegSetValueExW
0x18006f648  test    eax, eax
0x18006f64a  jz      short loc_18006F656
0x18006f64c  mov     edx, 695h
0x18006f651  jmp     loc_18006F5A4
0x18006f656  lea     rcx, [rbp+hkey]
0x18006f65a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18006f65f  xor     ebx, ebx
0x18006f661  lea     rcx, [rbp+phkResult]
0x18006f665  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18006f66a  mov     eax, ebx
0x18006f66c  add     rsp, 70h
0x18006f670  pop     r14
0x18006f672  pop     rdi
0x18006f673  pop     rsi
0x18006f674  pop     rbx
0x18006f675  pop     rbp
0x18006f676  retn
```
