# RegistryDataHelper::WriteData<ulong,4>(ushort const *,ulong,ulong)

- ea: `0x1800247a8`
- end: `0x180024899`
- name: `??$WriteData@K$03@RegistryDataHelper@@AEAAJPEBGKK@Z`
- size: `241`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025a9c`
- `0x180025af4`

## callees

- `0x18001cf84`
- `0x180021a0c`
- `0x1800247a8`
- `0x18002498c`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18002486f`
- `ADVAPI32!RegSetValueExW` at `0x18002486f`
- `ADVAPI32!RegDeleteValueW` at `0x180024827`
- `ADVAPI32!RegDeleteValueW` at `0x180024827`
- `ADVAPI32!RegCreateKeyExW` at `0x18002480a`
- `ADVAPI32!RegCreateKeyExW` at `0x18002480a`

## string_xrefs

- `0x180024840`: `shellcommon\internal\shell\inc\RegistryDataHelper.h`

## pseudocode

```c
__int64 __fastcall RegistryDataHelper::WriteData<unsigned long,4>(__int64 a1, const WCHAR *a2, int a3, int a4)
{
  const WCHAR *v6; // rax
  HKEY *v7; // r10
  unsigned int v8; // eax
  __int64 v9; // rdx
  unsigned int v10; // ebx
  unsigned int dwOptions; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF
  int Data; // [rsp+70h] [rbp+18h] BYREF

  Data = a3;
  hKey = 0;
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 8);
  v8 = RegCreateKeyExW(*v7, v6, 0, 0, 0, 0x20006u, 0, &hKey, 0);
  if ( !v8 )
  {
    if ( a4 )
    {
      Data = a4;
      v8 = RegSetValueExW(hKey, a2, 0, 4u, (const BYTE *)&Data, 4u);
      if ( v8 )
      {
        v9 = 544;
        goto LABEL_7;
      }
    }
    else
    {
      v8 = RegDeleteValueW(hKey, a2);
      if ( v8 != 2 && v8 )
      {
        v9 = 530;
        goto LABEL_7;
      }
    }
    v10 = 0;
    goto LABEL_11;
  }
  v9 = 518;
LABEL_7:
  v10 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)v9,
          (unsigned int)"shellcommon\\internal\\shell\\inc\\RegistryDataHelper.h",
          (const char *)v8,
          dwOptions);
LABEL_11:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v10;
}

```

## disassembly

```asm
0x1800247a8  mov     [rsp+arg_8], rbx
0x1800247ad  mov     [rsp+Data], r8d
0x1800247b2  push    rdi
0x1800247b3  sub     rsp, 50h
0x1800247b7  mov     r10, rcx
0x1800247ba  mov     [rsp+58h+hKey], 0
0x1800247c3  add     rcx, 8
0x1800247c7  mov     ebx, r9d
0x1800247ca  mov     rdi, rdx
0x1800247cd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800247d2  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1800247db  lea     rcx, [rsp+58h+hKey]
0x1800247e0  mov     [rsp+58h+phkResult], rcx; phkResult
0x1800247e5  xor     r9d, r9d; lpClass
0x1800247e8  mov     rcx, [r10]; hKey
0x1800247eb  xor     r8d, r8d; Reserved
0x1800247ee  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800247f7  mov     rdx, rax; lpSubKey
0x1800247fa  mov     [rsp+58h+samDesired], 20006h; samDesired
0x180024802  mov     [rsp+58h+dwOptions], 0; unsigned int
0x18002480a  call    cs:__imp_RegCreateKeyExW
0x180024810  test    eax, eax
0x180024812  jz      short loc_18002481B
0x180024814  mov     edx, 206h
0x180024819  jmp     short loc_18002483B
0x18002481b  mov     rcx, [rsp+58h+hKey]; hKey
0x180024820  mov     rdx, rdi; lpValueName
0x180024823  test    ebx, ebx
0x180024825  jnz     short loc_180024853
0x180024827  call    cs:__imp_RegDeleteValueW
0x18002482d  cmp     eax, 2
0x180024830  jz      short loc_180024880
0x180024832  test    eax, eax
0x180024834  jz      short loc_180024880
0x180024836  mov     edx, 212h; void *
0x18002483b  mov     rcx, [rsp+58h]; this
0x180024840  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\Regi"...
0x180024847  mov     r9d, eax; char *
0x18002484a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002484f  mov     ebx, eax
0x180024851  jmp     short loc_180024882
0x180024853  mov     r9d, 4; dwType
0x180024859  mov     [rsp+58h+Data], ebx
0x18002485d  lea     rax, [rsp+58h+Data]
0x180024862  mov     [rsp+58h+samDesired], r9d; cbData
0x180024867  xor     r8d, r8d; Reserved
0x18002486a  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18002486f  call    cs:__imp_RegSetValueExW
0x180024875  test    eax, eax
0x180024877  jz      short loc_180024880
0x180024879  mov     edx, 220h
0x18002487e  jmp     short loc_18002483B
0x180024880  xor     ebx, ebx
0x180024882  lea     rcx, [rsp+58h+hKey]
0x180024887  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002488c  mov     eax, ebx
0x18002488e  mov     rbx, [rsp+58h+arg_8]
0x180024893  add     rsp, 50h
0x180024897  pop     rdi
0x180024898  retn
```
