# ServiceBase::_SetShutdownRegistryKey(void)

- ea: `0x18002ccd0`
- end: `0x18002cd97`
- name: `?_SetShutdownRegistryKey@ServiceBase@@AEAAJXZ`
- size: `199`
- prototype: `__int64 __fastcall(ServiceBase *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18001f588`

## callees

- `0x1800202bc`
- `0x180023df0`
- `0x18002c164`
- `0x18002ccd0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002cd68`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002cd68`

## string_xrefs

- `0x18002cd04`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\servicebase\servicebase.cpp`

## pseudocode

```c
__int64 __fastcall ServiceBase::_SetShutdownRegistryKey(ServiceBase *this)
{
  const WCHAR *v2; // rax
  unsigned int v3; // ebx
  unsigned int v5; // eax
  void *v6; // rdx
  unsigned int v7; // r8d
  DWORD dwOptions; // [rsp+20h] [rbp-38h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HKEY phkResult; // [rsp+60h] [rbp+8h] BYREF

  v2 = (const WCHAR *)(*(__int64 (__fastcall **)(ServiceBase *))(*(_QWORD *)this + 80LL))(this);
  if ( v2 )
  {
    phkResult = 0;
    v5 = RegCreateKeyExW(HKEY_CURRENT_USER, v2, 0, 0, 1u, 0x20019u, 0, &phkResult, 0);
    if ( v5 )
      v3 = wil::details::in1diag3::Return_Win32(retaddr, v6, v7, (const char *)v5, dwOptionsa);
    else
      v3 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  }
  else
  {
    if ( ((*(__int64 (__fastcall **)(ServiceBase *))(*(_QWORD *)this + 56LL))(this) & 0x100) == 0 )
      return 0;
    v3 = -2147483635;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27A,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\servicebase\\servicebase.cpp",
      (const char *)0x8000000DLL,
      dwOptions);
  }
  return v3;
}

```

## disassembly

```asm
0x18002ccd0  push    rbx
0x18002ccd2  sub     rsp, 50h
0x18002ccd6  mov     rax, [rcx]
0x18002ccd9  mov     rbx, rcx
0x18002ccdc  mov     rax, [rax+50h]
0x18002cce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cce5  test    rax, rax
0x18002cce8  jnz     short loc_18002CD23
0x18002ccea  mov     rax, [rbx]
0x18002cced  mov     rcx, rbx
0x18002ccf0  mov     rax, [rax+38h]
0x18002ccf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ccf9  bt      eax, 8
0x18002ccfd  jnb     short loc_18002CD1F
0x18002ccff  mov     rcx, [rsp+58h]; this
0x18002cd04  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002cd0b  mov     ebx, 8000000Dh
0x18002cd10  mov     edx, 27Ah; void *
0x18002cd15  mov     r9d, ebx; char *
0x18002cd18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cd1d  jmp     short loc_18002CD8F
0x18002cd1f  xor     eax, eax
0x18002cd21  jmp     short loc_18002CD91
0x18002cd23  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18002cd2c  lea     rcx, [rsp+58h+arg_0]
0x18002cd31  mov     [rsp+58h+phkResult], rcx; phkResult
0x18002cd36  xor     r9d, r9d; lpClass
0x18002cd39  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002cd42  xor     r8d, r8d; Reserved
0x18002cd45  mov     [rsp+58h+samDesired], 20019h; samDesired
0x18002cd4d  mov     rdx, rax; lpSubKey
0x18002cd50  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002cd57  mov     [rsp+58h+dwOptions], 1; unsigned int
0x18002cd5f  mov     [rsp+58h+arg_0], 0
0x18002cd68  call    cs:__imp_RegCreateKeyExW
0x18002cd6e  test    eax, eax
0x18002cd70  jz      short loc_18002CD83
0x18002cd72  mov     rcx, [rsp+58h]; this
0x18002cd77  mov     r9d, eax; char *
0x18002cd7a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002cd7f  mov     ebx, eax
0x18002cd81  jmp     short loc_18002CD85
0x18002cd83  xor     ebx, ebx
0x18002cd85  lea     rcx, [rsp+58h+arg_0]
0x18002cd8a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002cd8f  mov     eax, ebx
0x18002cd91  add     rsp, 50h
0x18002cd95  pop     rbx
0x18002cd96  retn
```
