# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x18004ea24`
- end: `0x18004ea60`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `60`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004e980`

## callees

- `0x18004ea24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ea3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ea3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ea4e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ea4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ea46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ea46`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
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
0x18004ea24  push    rbx
0x18004ea26  push    rbp
0x18004ea27  push    rsi
0x18004ea28  push    rdi
0x18004ea29  sub     rsp, 28h
0x18004ea2d  mov     rsi, [rcx]
0x18004ea30  mov     rbp, rdx
0x18004ea33  mov     rdi, rcx
0x18004ea36  test    rsi, rsi
0x18004ea39  jz      short loc_18004EA54
0x18004ea3b  call    cs:__imp_GetLastError
0x18004ea41  mov     rcx, rsi; pv
0x18004ea44  mov     ebx, eax
0x18004ea46  call    cs:__imp_CoTaskMemFree
0x18004ea4c  mov     ecx, ebx; dwErrCode
0x18004ea4e  call    cs:__imp_SetLastError
0x18004ea54  mov     [rdi], rbp
0x18004ea57  add     rsp, 28h
0x18004ea5b  pop     rdi
0x18004ea5c  pop     rsi
0x18004ea5d  pop     rbp
0x18004ea5e  pop     rbx
0x18004ea5f  retn
```
