# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator&(void)

- ea: `0x180039bb4`
- end: `0x180039c01`
- name: `??I?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ`
- size: `77`
- prototype: `void **__fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800418e4`

## callees

- `0x180039bb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039bce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039bce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039be1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039be1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039bd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039bd9`

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
0x180039bb4  mov     [rsp+arg_0], rbx
0x180039bb9  mov     [rsp+arg_8], rsi
0x180039bbe  push    rdi
0x180039bbf  sub     rsp, 20h
0x180039bc3  mov     rsi, [rcx]
0x180039bc6  mov     rdi, rcx
0x180039bc9  test    rsi, rsi
0x180039bcc  jz      short loc_180039BE7
0x180039bce  call    cs:__imp_GetLastError
0x180039bd4  mov     rcx, rsi; pv
0x180039bd7  mov     ebx, eax
0x180039bd9  call    cs:__imp_CoTaskMemFree
0x180039bdf  mov     ecx, ebx; dwErrCode
0x180039be1  call    cs:__imp_SetLastError
0x180039be7  mov     rbx, [rsp+28h+arg_0]
0x180039bec  mov     rax, rdi
0x180039bef  mov     rsi, [rsp+28h+arg_8]
0x180039bf4  mov     qword ptr [rdi], 0
0x180039bfb  add     rsp, 20h
0x180039bff  pop     rdi
0x180039c00  retn
```
