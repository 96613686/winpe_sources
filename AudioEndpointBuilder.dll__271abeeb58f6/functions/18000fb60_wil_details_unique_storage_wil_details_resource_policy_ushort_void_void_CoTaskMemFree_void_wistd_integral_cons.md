# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x18000fb60`
- end: `0x18000fbb8`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `88`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `58`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180004b00`
- `0x18000796c`
- `0x18000899c`
- `0x18000af84`
- `0x18000c0d0`
- `0x18000ecf0`
- `0x18000f820`
- `0x18001001c`
- `0x180013a8c`
- `0x180013e14`
- `0x180014844`
- `0x1800165ec`
- `0x1800170ac`
- `0x18002187c`
- `0x180021cb0`
- `0x180022948`
- `0x1800290b0`
- `0x18002b2a8`
- `0x18002c798`
- `0x18002d094`
- `0x18002e43c`
- `0x18002eb80`
- `0x18002fecc`
- `0x1800301b8`
- `0x180031920`
- `0x180031ae0`
- `0x1800328d4`
- `0x180032b38`
- `0x18003433c`
- `0x180035738`
- `0x1800359d8`
- `0x1800380c0`
- `0x1800395ec`
- `0x180039ef4`
- `0x18003a6c8`
- `0x18003af20`
- `0x18003b078`
- `0x18003b790`
- `0x18003d7a0`
- `0x18003da60`
- `0x180049c50`
- `0x18004c5c0`
- `0x18004f474`
- `0x180050048`
- `0x180050858`
- `0x180051ae0`
- `0x180052cb8`
- `0x180052ffc`
- `0x18005419c`
- `0x180055a90`

## callees

- `0x18000fb60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fb95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fb95`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fba8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fba8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fba0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fba0`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        void **a1,
        void *a2)
{
  void *v2; // rbp
  DWORD LastError; // edi

  v2 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    CoTaskMemFree(v2);
    SetLastError(LastError);
    *a1 = a2;
  }
  else
  {
    *a1 = a2;
  }
}

```

## disassembly

```asm
0x18000fb60  mov     [rsp+arg_8], rbx
0x18000fb65  mov     [rsp+arg_10], rbp
0x18000fb6a  push    rsi
0x18000fb6b  sub     rsp, 20h
0x18000fb6f  mov     rbp, [rcx]
0x18000fb72  mov     rsi, rdx
0x18000fb75  mov     rbx, rcx
0x18000fb78  test    rbp, rbp
0x18000fb7b  jnz     short loc_18000FB90
0x18000fb7d  mov     [rcx], rdx
0x18000fb80  mov     rbx, [rsp+28h+arg_8]
0x18000fb85  mov     rbp, [rsp+28h+arg_10]
0x18000fb8a  add     rsp, 20h
0x18000fb8e  pop     rsi
0x18000fb8f  retn
0x18000fb90  mov     [rsp+28h+arg_0], rdi
0x18000fb95  call    cs:__imp_GetLastError
0x18000fb9b  mov     rcx, rbp; pv
0x18000fb9e  mov     edi, eax
0x18000fba0  call    cs:__imp_CoTaskMemFree
0x18000fba6  mov     ecx, edi; dwErrCode
0x18000fba8  call    cs:__imp_SetLastError
0x18000fbae  mov     rdi, [rsp+28h+arg_0]
0x18000fbb3  mov     [rbx], rsi
0x18000fbb6  jmp     short loc_18000FB80
```
