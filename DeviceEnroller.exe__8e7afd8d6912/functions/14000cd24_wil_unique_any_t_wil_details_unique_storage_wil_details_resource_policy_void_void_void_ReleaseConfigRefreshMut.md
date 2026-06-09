# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&ReleaseConfigRefreshMutex(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator&(void)

- ea: `0x14000cd24`
- end: `0x14000cd72`
- name: `??I?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?ReleaseConfigRefreshMutex@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ`
- size: `78`
- prototype: `void **__fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140019a6c`

## callees

- `0x14000cd24`

## import_xrefs

- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14000cd49`
- `omadmapi!__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z` at `0x14000cd49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cd3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cd3e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000cd51`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000cd51`

## pseudocode

```c
void **__fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void ReleaseConfigRefreshMutex(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator&(
        void **a1)
{
  void *v2; // rsi
  DWORD LastError; // ebx

  v2 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    ReleaseConfigRefreshMutex(v2);
    SetLastError(LastError);
  }
  *a1 = 0;
  return a1;
}

```

## disassembly

```asm
0x14000cd24  mov     [rsp+arg_0], rbx
0x14000cd29  mov     [rsp+arg_8], rsi
0x14000cd2e  push    rdi
0x14000cd2f  sub     rsp, 20h
0x14000cd33  mov     rdi, rcx
0x14000cd36  mov     rsi, [rcx]
0x14000cd39  test    rsi, rsi
0x14000cd3c  jz      short loc_14000CD58
0x14000cd3e  call    cs:__imp_GetLastError
0x14000cd44  mov     ebx, eax
0x14000cd46  mov     rcx, rsi
0x14000cd49  call    cs:__imp_?ReleaseConfigRefreshMutex@@YAXPEAX@Z; ReleaseConfigRefreshMutex(void *)
0x14000cd4f  mov     ecx, ebx; dwErrCode
0x14000cd51  call    cs:__imp_SetLastError
0x14000cd57  nop
0x14000cd58  mov     qword ptr [rdi], 0
0x14000cd5f  mov     rax, rdi
0x14000cd62  mov     rbx, [rsp+28h+arg_0]
0x14000cd67  mov     rsi, [rsp+28h+arg_8]
0x14000cd6c  add     rsp, 20h
0x14000cd70  pop     rdi
0x14000cd71  retn
```
