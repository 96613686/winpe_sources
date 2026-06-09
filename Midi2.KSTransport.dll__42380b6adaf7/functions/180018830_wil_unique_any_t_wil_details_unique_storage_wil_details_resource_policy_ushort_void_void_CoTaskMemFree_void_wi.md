# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator&(void)

- ea: `0x180018830`
- end: `0x18001887d`
- name: `??I?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001b7a0`

## callees

- `0x180018830`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001885d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001885d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001884a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001884a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018855`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018855`

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
0x180018830  mov     [rsp+arg_0], rbx
0x180018835  mov     [rsp+arg_8], rsi
0x18001883a  push    rdi
0x18001883b  sub     rsp, 20h
0x18001883f  mov     rsi, [rcx]
0x180018842  mov     rdi, rcx
0x180018845  test    rsi, rsi
0x180018848  jz      short loc_180018863
0x18001884a  call    cs:__imp_GetLastError
0x180018850  mov     rcx, rsi; pv
0x180018853  mov     ebx, eax
0x180018855  call    cs:__imp_CoTaskMemFree
0x18001885b  mov     ecx, ebx; dwErrCode
0x18001885d  call    cs:__imp_SetLastError
0x180018863  mov     rbx, [rsp+28h+arg_0]
0x180018868  mov     rax, rdi
0x18001886b  mov     rsi, [rsp+28h+arg_8]
0x180018870  mov     qword ptr [rdi], 0
0x180018877  add     rsp, 20h
0x18001887b  pop     rdi
0x18001887c  retn
```
