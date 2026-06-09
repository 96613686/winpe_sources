# Registry::OpenKeyForWrite<Registry::NotFoundPolicy::CreateNew>(HKEY__ *,ushort const *)

- ea: `0x180014750`
- end: `0x1800147f7`
- name: `??$OpenKeyForWrite@UCreateNew@NotFoundPolicy@Registry@@@Registry@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHKEY__@@PEBG@Z`
- size: `167`
- prototype: `PHKEY __fastcall(PHKEY phkResult, HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180017b80`
- `0x180027178`

## callees

- `0x180014750`
- `0x180014800`
- `0x1800156e8`
- `0x1800158e4`
- `0x180019640`
- `0x18001993c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001479d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001479d`

## pseudocode

```c
PHKEY __fastcall Registry::OpenKeyForWrite<Registry::NotFoundPolicy::CreateNew>(
        PHKEY phkResult,
        HKEY hKey,
        LPCWSTR lpSubKey)
{
  unsigned int v6; // eax
  unsigned int v7; // r8d
  __int64 v8; // rax
  unsigned int phkResulta; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HKEY v12; // [rsp+68h] [rbp+20h] BYREF

  *phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    phkResult,
    0);
  v6 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20006u, phkResult);
  if ( v6 == 2 )
  {
    v8 = Registry::RegKeyNotFoundHandler<Registry::NotFoundPolicy::CreateNew>(&v12);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(
      phkResult,
      v8);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v12);
  }
  else if ( v6 )
  {
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0xC6, v7, (const char *)v6, phkResulta);
  }
  return phkResult;
}

```

## disassembly

```asm
0x180014750  mov     rax, rsp
0x180014753  mov     [rax+10h], rbx
0x180014757  mov     [rax+18h], rsi
0x18001475b  mov     [rax+8], rcx
0x18001475f  push    rdi
0x180014760  sub     rsp, 40h
0x180014764  mov     rdi, r8
0x180014767  mov     rsi, rdx
0x18001476a  mov     rbx, rcx
0x18001476d  mov     dword ptr [rax-18h], 0
0x180014774  mov     qword ptr [rcx], 0
0x18001477b  mov     dword ptr [rax-18h], 1
0x180014782  xor     edx, edx
0x180014784  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180014789  mov     qword ptr [rsp+48h+phkResult], rbx; unsigned int
0x18001478e  mov     r9d, 20006h; samDesired
0x180014794  xor     r8d, r8d; ulOptions
0x180014797  mov     rdx, rdi; lpSubKey
0x18001479a  mov     rcx, rsi; hKey
0x18001479d  call    cs:__imp_RegOpenKeyExW
0x1800147a3  cmp     eax, 2
0x1800147a6  jnz     short loc_1800147E0
0x1800147a8  mov     r9, rdi
0x1800147ab  mov     r8, rsi
0x1800147ae  lea     rcx, [rsp+48h+arg_18]; phkResult
0x1800147b3  call    ??$RegKeyNotFoundHandler@UCreateNew@NotFoundPolicy@Registry@@@Registry@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@JPEAUHKEY__@@PEBG@Z; Registry::RegKeyNotFoundHandler<Registry::NotFoundPolicy::CreateNew>(long,HKEY__ *,ushort const *)
0x1800147b8  mov     rdx, rax
0x1800147bb  mov     rcx, rbx
0x1800147be  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&)
0x1800147c3  lea     rcx, [rsp+48h+arg_18]
0x1800147c8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800147cd  mov     rax, rbx
0x1800147d0  mov     rbx, [rsp+48h+arg_8]
0x1800147d5  mov     rsi, [rsp+48h+arg_10]
0x1800147da  add     rsp, 40h
0x1800147de  pop     rdi
0x1800147df  retn
0x1800147e0  test    eax, eax
0x1800147e2  jz      short loc_1800147CD
0x1800147e4  mov     rcx, [rsp+48h]; this
0x1800147e9  mov     r9d, eax; char *
0x1800147ec  mov     edx, 0C6h; void *
0x1800147f1  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
