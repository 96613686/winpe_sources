# WindowsStorage::Utilities::registry_value_data_nothrow<ushort const *,void>(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x18000c0c4`
- end: `0x18000c1d2`
- name: `??$registry_value_data_nothrow@PEBGX@Utilities@WindowsStorage@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `270`
- prototype: `__int64 __fastcall(HKEY hkey, __int64, PVOID *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000e2fc`
- `0x18000fa4c`

## callees

- `0x180007fac`
- `0x18000bf7c`
- `0x18000c0c4`
- `0x18000d504`
- `0x18000d904`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c137`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c19b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c137`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c19b`

## string_xrefs

- `0x18000c1ac`: `onecore\base\windows.storage\src\Registry.h`
- `0x18000c11a`: `FilePath`
- `0x18000c17e`: `FilePath`

## pseudocode

```c
__int64 __fastcall WindowsStorage::Utilities::registry_value_data_nothrow<unsigned short const *,void>(
        HKEY hkey,
        __int64 a2,
        PVOID *a3)
{
  LSTATUS ValueW; // ebx
  int pdwType; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF
  int v10; // [rsp+5Ch] [rbp+14h]
  __int64 v11; // [rsp+60h] [rbp+18h] BYREF

  v10 = HIDWORD(a2);
  pcbData = 256;
  wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v11);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    a3,
    &v11);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v11);
  ValueW = RegGetValueW(hkey, 0, L"FilePath", 2u, 0, *a3, &pcbData);
  if ( ValueW == 234 )
  {
    wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v11);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      a3,
      &v11);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v11);
    ValueW = RegGetValueW(hkey, 0, L"FilePath", 2u, 0, *a3, &pcbData);
  }
  if ( ValueW < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE5,
      (unsigned int)"onecore\\base\\windows.storage\\src\\Registry.h",
      (const char *)(unsigned int)ValueW,
      pdwType);
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x18000c0c4  mov     rax, rsp
0x18000c0c7  mov     [rax+8], rbx
0x18000c0cb  mov     [rax+20h], rsi
0x18000c0cf  mov     [rax+10h], rdx
0x18000c0d3  push    rdi
0x18000c0d4  sub     rsp, 40h
0x18000c0d8  mov     rdi, r8
0x18000c0db  mov     rsi, rcx
0x18000c0de  mov     r8d, 100h
0x18000c0e4  lea     rcx, [rax+18h]
0x18000c0e8  xor     edx, edx
0x18000c0ea  mov     [rax+10h], r8d
0x18000c0ee  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18000c0f3  lea     rdx, [rsp+48h+arg_10]
0x18000c0f8  mov     rcx, rdi
0x18000c0fb  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18000c100  lea     rcx, [rsp+48h+arg_10]
0x18000c105  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000c10a  lea     rax, [rsp+48h+arg_8]
0x18000c10f  mov     r9d, 2; dwFlags
0x18000c115  mov     [rsp+48h+pcbData], rax; pcbData
0x18000c11a  lea     r8, Value; "FilePath"
0x18000c121  mov     rax, [rdi]
0x18000c124  xor     edx, edx; lpSubKey
0x18000c126  mov     [rsp+48h+pvData], rax; pvData
0x18000c12b  mov     rcx, rsi; hkey
0x18000c12e  mov     [rsp+48h+pdwType], 0; pdwType
0x18000c137  call    cs:__imp_RegGetValueW
0x18000c13d  mov     ebx, eax
0x18000c13f  cmp     eax, 0EAh
0x18000c144  jnz     short loc_18000C1A3
0x18000c146  mov     r8d, [rsp+48h+arg_8]
0x18000c14b  lea     rcx, [rsp+48h+arg_10]
0x18000c150  xor     edx, edx
0x18000c152  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18000c157  lea     rdx, [rsp+48h+arg_10]
0x18000c15c  mov     rcx, rdi
0x18000c15f  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18000c164  lea     rcx, [rsp+48h+arg_10]
0x18000c169  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000c16e  lea     rax, [rsp+48h+arg_8]
0x18000c173  mov     r9d, 2; dwFlags
0x18000c179  mov     [rsp+48h+pcbData], rax; pcbData
0x18000c17e  lea     r8, Value; "FilePath"
0x18000c185  mov     rax, [rdi]
0x18000c188  xor     edx, edx; lpSubKey
0x18000c18a  mov     [rsp+48h+pvData], rax; pvData
0x18000c18f  mov     rcx, rsi; hkey
0x18000c192  mov     [rsp+48h+pdwType], 0; int
0x18000c19b  call    cs:__imp_RegGetValueW
0x18000c1a1  mov     ebx, eax
0x18000c1a3  test    ebx, ebx
0x18000c1a5  jns     short loc_18000C1C0
0x18000c1a7  mov     rcx, [rsp+48h]; this
0x18000c1ac  lea     r8, aOnecoreBaseWin_7; "onecore\\base\\windows.storage\\src\\Re"...
0x18000c1b3  mov     r9d, ebx; char *
0x18000c1b6  mov     edx, 0E5h; void *
0x18000c1bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c1c0  mov     rsi, [rsp+48h+arg_18]
0x18000c1c5  mov     eax, ebx
0x18000c1c7  mov     rbx, [rsp+48h+arg_0]
0x18000c1cc  add     rsp, 40h
0x18000c1d0  pop     rdi
0x18000c1d1  retn
```
