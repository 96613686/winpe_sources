# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)

- ea: `0x14000934c`
- end: `0x140009363`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(HANDLE *, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140009264`
- `0x1400105bc`

## callees

- `0x14000934c`
- `0x1400103e8`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(
        HANDLE *a1,
        void *a2)
{
  if ( *a1 != (HANDLE)-1LL )
    wil::details::RevertImpersonateToken(*a1, a2);
}

```

## disassembly

```asm
0x14000934c  sub     rsp, 28h
0x140009350  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x140009354  jz      short loc_14000935E
0x140009356  mov     rcx, [rcx]; hObject
0x140009359  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x14000935e  add     rsp, 28h
0x140009362  retn
```
