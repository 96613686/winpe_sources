# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)

- ea: `0x18001d320`
- end: `0x18001d35e`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z`
- size: `62`
- prototype: ``
- caller_count: `24`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d188`
- `0x180011a4c`
- `0x18001e010`
- `0x180028c5c`
- `0x18002a898`
- `0x180034908`
- `0x1800353dc`
- `0x180035c58`
- `0x180041334`
- `0x180057248`
- `0x1800589d8`
- `0x180059834`
- `0x18005cd30`
- `0x18006052c`
- `0x180065380`
- `0x180067254`
- `0x180068abc`
- `0x18006aa8c`
- `0x18006df6c`
- `0x18006e3f8`
- `0x18006f5c0`
- `0x1800723b0`
- `0x180074b10`
- `0x18007768c`

## callees

- `0x18001d320`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d356`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d356`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d343`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d343`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d34e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d34e`

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
0x18001d320  push    rbx
0x18001d322  push    rbp
0x18001d323  push    rsi
0x18001d324  push    rdi
0x18001d325  sub     rsp, 28h
0x18001d329  mov     rsi, [rcx]
0x18001d32c  mov     rbp, rdx
0x18001d32f  mov     rdi, rcx
0x18001d332  test    rsi, rsi
0x18001d335  jnz     short loc_18001D343
0x18001d337  mov     [rdi], rbp
0x18001d33a  add     rsp, 28h
0x18001d33e  pop     rdi
0x18001d33f  pop     rsi
0x18001d340  pop     rbp
0x18001d341  pop     rbx
0x18001d342  retn
0x18001d343  call    cs:__imp_GetLastError
0x18001d349  mov     rcx, rsi; pv
0x18001d34c  mov     ebx, eax
0x18001d34e  call    cs:__imp_CoTaskMemFree
0x18001d354  mov     ecx, ebx; dwErrCode
0x18001d356  call    cs:__imp_SetLastError
0x18001d35c  jmp     short loc_18001D337
```
