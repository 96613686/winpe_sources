# Registry::RegKeyNotFoundHandler<Registry::NotFoundPolicy::CreateNew>(long,HKEY__ *,ushort const *)

- ea: `0x180014800`
- end: `0x180014873`
- name: `??$RegKeyNotFoundHandler@UCreateNew@NotFoundPolicy@Registry@@@Registry@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@JPEAUHKEY__@@PEBG@Z`
- size: `115`
- prototype: `PHKEY __fastcall(PHKEY phkResult, __int64, HKEY, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180014750`

## callees

- `0x180014800`
- `0x180019640`
- `0x18001993c`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180014842`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180014842`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
PHKEY __fastcall Registry::RegKeyNotFoundHandler<Registry::NotFoundPolicy::CreateNew>(
        PHKEY phkResult,
        __int64 a2,
        HKEY a3,
        const WCHAR *a4)
{
  unsigned int KeyW; // eax
  unsigned int v8; // r8d
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    phkResult,
    0);
  KeyW = RegCreateKeyW(a3, a4, phkResult);
  if ( KeyW )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0xA6, v8, (const char *)KeyW, 1u);
  return phkResult;
}

```

## disassembly

```asm
0x180014800  mov     rax, rsp
0x180014803  mov     [rax+10h], rbx
0x180014807  mov     [rax+18h], rsi
0x18001480b  mov     [rax+8], rcx
0x18001480f  push    rdi
0x180014810  sub     rsp, 30h
0x180014814  mov     rbx, r9
0x180014817  mov     rdi, r8
0x18001481a  mov     rsi, rcx
0x18001481d  mov     dword ptr [rax-18h], 0
0x180014824  mov     qword ptr [rcx], 0
0x18001482b  mov     dword ptr [rax-18h], 1
0x180014832  xor     edx, edx
0x180014834  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180014839  mov     r8, rsi; phkResult
0x18001483c  mov     rdx, rbx; lpSubKey
0x18001483f  mov     rcx, rdi; hKey
0x180014842  call    cs:__imp_RegCreateKeyW
0x180014848  test    eax, eax
0x18001484a  jz      short loc_18001485F
0x18001484c  mov     rcx, [rsp+38h]; this
0x180014851  mov     r9d, eax; char *
0x180014854  mov     edx, 0A6h; void *
0x180014859  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18001485f  mov     rax, rsi
0x180014862  mov     rbx, [rsp+38h+arg_8]
0x180014867  mov     rsi, [rsp+38h+arg_10]
0x18001486c  add     rsp, 30h
0x180014870  pop     rdi
0x180014871  retn
```
