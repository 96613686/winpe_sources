# wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)

- ea: `0x180023ee4`
- end: `0x180023f20`
- name: `?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180023e44`

## callees

- `0x180023ee4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023f0e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023f0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023efb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023efb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023f06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023f06`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
        void **a1,
        void *a2)
{
  void *v2; // rsi
  DWORD LastError; // ebx

  v2 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    CoTaskMemFree(v2);
    SetLastError(LastError);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x180023ee4  push    rbx
0x180023ee6  push    rbp
0x180023ee7  push    rsi
0x180023ee8  push    rdi
0x180023ee9  sub     rsp, 28h
0x180023eed  mov     rsi, [rcx]
0x180023ef0  mov     rbp, rdx
0x180023ef3  mov     rdi, rcx
0x180023ef6  test    rsi, rsi
0x180023ef9  jz      short loc_180023F14
0x180023efb  call    cs:__imp_GetLastError
0x180023f01  mov     rcx, rsi; pv
0x180023f04  mov     ebx, eax
0x180023f06  call    cs:__imp_CoTaskMemFree
0x180023f0c  mov     ecx, ebx; dwErrCode
0x180023f0e  call    cs:__imp_SetLastError
0x180023f14  mov     [rdi], rbp
0x180023f17  add     rsp, 28h
0x180023f1b  pop     rdi
0x180023f1c  pop     rsi
0x180023f1d  pop     rbp
0x180023f1e  pop     rbx
0x180023f1f  retn
```
