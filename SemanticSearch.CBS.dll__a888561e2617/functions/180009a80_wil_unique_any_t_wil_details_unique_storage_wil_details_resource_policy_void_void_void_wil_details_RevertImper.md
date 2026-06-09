# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>>(void)

- ea: `0x180009a80`
- end: `0x180009abe`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `62`
- prototype: `void __fastcall(HANDLE *)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18006488c`
- `0x180064b67`
- `0x1800656f7`

## callees

- `0x180009a80`
- `0x1800161b0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180009aab`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180009a94`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180009a94`

## pseudocode

```c
void __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>>(
        HANDLE *a1)
{
  HANDLE v1; // rbx
  wil::details::in1diag3 *v2; // rcx

  v1 = *a1;
  if ( *a1 != (HANDLE)-1LL )
  {
    if ( !SetThreadToken(0, *a1) )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v2);
    if ( v1 )
      CloseHandle(v1);
  }
}

```

## disassembly

```asm
0x180009a80  push    rbx
0x180009a82  sub     rsp, 20h
0x180009a86  mov     rbx, [rcx]
0x180009a89  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180009a8d  jz      short loc_180009AB2
0x180009a8f  mov     rdx, rbx; Token
0x180009a92  xor     ecx, ecx; Thread
0x180009a94  call    cs:__imp_SetThreadToken
0x180009a9a  test    eax, eax
0x180009a9c  jz      short loc_180009AB8
0x180009a9e  test    rbx, rbx
0x180009aa1  jz      short loc_180009AB2
0x180009aa3  mov     rcx, rbx
0x180009aa6  add     rsp, 20h
0x180009aaa  pop     rbx
0x180009aab  jmp     cs:__imp_CloseHandle
0x180009ab2  add     rsp, 20h
0x180009ab6  pop     rbx
0x180009ab7  retn
0x180009ab8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
