# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>>(void)

- ea: `0x18001b380`
- end: `0x18001b3be`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `62`
- prototype: ``
- caller_count: `21`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18024ceb0`
- `0x18024cec8`
- `0x18024ceec`
- `0x18024cf04`
- `0x18024dad0`
- `0x18024dae8`
- `0x18024db0c`
- `0x18024db24`
- `0x18025901a`
- `0x180259259`
- `0x18025993f`
- `0x180259a25`
- `0x180259ff8`
- `0x18025a10c`
- `0x18025b0da`
- `0x18025b669`
- `0x18025bad8`
- `0x18025bcc6`
- `0x18025c426`
- `0x18025cc26`
- `0x18025d386`

## callees

- `0x18000d4b0`
- `0x18001b380`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18001b3ab`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001b394`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001b394`

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
0x18001b380  push    rbx
0x18001b382  sub     rsp, 20h
0x18001b386  mov     rbx, [rcx]
0x18001b389  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001b38d  jz      short loc_18001B3B2
0x18001b38f  mov     rdx, rbx; Token
0x18001b392  xor     ecx, ecx; Thread
0x18001b394  call    cs:__imp_SetThreadToken
0x18001b39a  test    eax, eax
0x18001b39c  jz      short loc_18001B3B8
0x18001b39e  test    rbx, rbx
0x18001b3a1  jz      short loc_18001B3B2
0x18001b3a3  mov     rcx, rbx
0x18001b3a6  add     rsp, 20h
0x18001b3aa  pop     rbx
0x18001b3ab  jmp     cs:__imp_CloseHandle
0x18001b3b2  add     rsp, 20h
0x18001b3b6  pop     rbx
0x18001b3b7  retn
0x18001b3b8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
