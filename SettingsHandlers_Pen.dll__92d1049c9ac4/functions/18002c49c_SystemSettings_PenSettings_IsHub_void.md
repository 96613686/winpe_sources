# SystemSettings::PenSettings::IsHub(void)

- ea: `0x18002c49c`
- end: `0x18002c529`
- name: `?IsHub@PenSettings@SystemSettings@@YA_NXZ`
- size: `141`
- prototype: `bool __fastcall(SystemSettings::PenSettings *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002c44c`

## callees

- `0x180020614`
- `0x180020780`
- `0x18002c49c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c4f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c4f5`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18002c4b3`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18002c4b3`

## pseudocode

```c
bool __fastcall SystemSettings::PenSettings::IsHub(SystemSettings::PenSettings *this)
{
  bool v1; // di
  char v2; // bl
  __int64 *v4; // [rsp+30h] [rbp-28h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-20h] BYREF
  char v6; // [rsp+40h] [rbp-18h]
  __int64 v7; // [rsp+60h] [rbp+8h] BYREF

  v1 = 0;
  v2 = 0;
  v7 = 0;
  if ( (unsigned __int8)RtlIsStateSeparationEnabled(this) )
  {
    phkResult = 0;
    v4 = &v7;
    v6 = 1;
    v2 = 1;
    v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Hub", 0, 0x20019u, &phkResult) == 0;
  }
  if ( (v2 & 1) != 0 )
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v4);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v7);
  return v1;
}

```

## disassembly

```asm
0x18002c49c  mov     [rsp+arg_8], rbx
0x18002c4a1  push    rdi
0x18002c4a2  sub     rsp, 50h
0x18002c4a6  xor     edi, edi
0x18002c4a8  mov     ebx, edi
0x18002c4aa  mov     dword ptr [rsp+58h+arg_0], ebx
0x18002c4ae  mov     [rsp+58h+arg_0], rdi
0x18002c4b3  call    cs:__imp_RtlIsStateSeparationEnabled
0x18002c4b9  test    al, al
0x18002c4bb  jz      short loc_18002C502
0x18002c4bd  lea     rax, [rsp+58h+arg_0]
0x18002c4c2  mov     [rsp+58h+var_20], rdi
0x18002c4c7  mov     [rsp+58h+var_28], rax
0x18002c4cc  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Hub"
0x18002c4d3  lea     rax, [rsp+58h+var_20]
0x18002c4d8  mov     [rsp+58h+var_18], 1
0x18002c4dd  mov     r9d, 20019h; samDesired
0x18002c4e3  mov     [rsp+58h+phkResult], rax; phkResult
0x18002c4e8  xor     r8d, r8d; ulOptions
0x18002c4eb  lea     ebx, [rdi+1]
0x18002c4ee  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c4f5  call    cs:__imp_RegOpenKeyExW
0x18002c4fb  test    eax, eax
0x18002c4fd  jnz     short loc_18002C502
0x18002c4ff  mov     dil, bl
0x18002c502  test    bl, 1
0x18002c505  jz      short loc_18002C511
0x18002c507  lea     rcx, [rsp+58h+var_28]
0x18002c50c  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18002c511  lea     rcx, [rsp+58h+arg_0]
0x18002c516  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002c51b  mov     rbx, [rsp+58h+arg_8]
0x18002c520  mov     al, dil
0x18002c523  add     rsp, 50h
0x18002c527  pop     rdi
0x18002c528  retn
```
