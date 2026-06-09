# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator&(void)

- ea: `0x18000bcd8`
- end: `0x18000bd25`
- name: `??I?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d750`

## callees

- `0x18000bcd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bcf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bcf2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bd05`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bd05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bcfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bcfd`

## pseudocode

```c
void **__fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator&(
        void **a1)
{
  void *v1; // rsi
  DWORD LastError; // ebx
  void **result; // rax

  v1 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    CoTaskMemFree(v1);
    SetLastError(LastError);
  }
  result = a1;
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x18000bcd8  mov     [rsp+arg_0], rbx
0x18000bcdd  mov     [rsp+arg_8], rsi
0x18000bce2  push    rdi
0x18000bce3  sub     rsp, 20h
0x18000bce7  mov     rsi, [rcx]
0x18000bcea  mov     rdi, rcx
0x18000bced  test    rsi, rsi
0x18000bcf0  jz      short loc_18000BD0B
0x18000bcf2  call    cs:__imp_GetLastError
0x18000bcf8  mov     rcx, rsi; pv
0x18000bcfb  mov     ebx, eax
0x18000bcfd  call    cs:__imp_CoTaskMemFree
0x18000bd03  mov     ecx, ebx; dwErrCode
0x18000bd05  call    cs:__imp_SetLastError
0x18000bd0b  mov     rbx, [rsp+28h+arg_0]
0x18000bd10  mov     rax, rdi
0x18000bd13  mov     rsi, [rsp+28h+arg_8]
0x18000bd18  mov     qword ptr [rdi], 0
0x18000bd1f  add     rsp, 20h
0x18000bd23  pop     rdi
0x18000bd24  retn
```
