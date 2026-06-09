# wil::details::ScopeExitFn__lambda_aad7baa8f617cb55e890afd752e38a97___::_ScopeExitFn__lambda_aad7baa8f617cb55e890afd752e38a97___

- ea: `0x18000d364`
- end: `0x18000d38b`
- name: `wil::details::ScopeExitFn__lambda_aad7baa8f617cb55e890afd752e38a97___::_ScopeExitFn__lambda_aad7baa8f617cb55e890afd752e38a97___`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180029023`

## callees

- `0x18000d364`

## import_xrefs

- `ntdll!RtlReleasePrivilege` at `0x18000d380`
- `ntdll!RtlReleasePrivilege` at `0x18000d380`

## pseudocode

```c
void __fastcall wil::details::ScopeExitFn__lambda_aad7baa8f617cb55e890afd752e38a97___::_ScopeExitFn__lambda_aad7baa8f617cb55e890afd752e38a97___(
        __int64 a1)
{
  if ( *(_BYTE *)(a1 + 16) )
  {
    *(_BYTE *)(a1 + 16) = 0;
    if ( **(int **)a1 >= 0 )
      RtlReleasePrivilege(**(PVOID **)(a1 + 8));
  }
}

```

## disassembly

```asm
0x18000d364  sub     rsp, 28h
0x18000d368  xor     edx, edx
0x18000d36a  cmp     [rcx+10h], dl
0x18000d36d  jz      short loc_18000D386
0x18000d36f  mov     [rcx+10h], dl
0x18000d372  mov     rax, [rcx]
0x18000d375  cmp     [rax], edx
0x18000d377  jl      short loc_18000D386
0x18000d379  mov     rcx, [rcx+8]
0x18000d37d  mov     rcx, [rcx]; ReturnedState
0x18000d380  call    cs:__imp_RtlReleasePrivilege
0x18000d386  add     rsp, 28h
0x18000d38a  retn
```
