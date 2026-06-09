# wil::run_as_self_failfast(void)

- ea: `0x140012c58`
- end: `0x140012c8b`
- name: `?run_as_self_failfast@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ`
- size: `51`
- prototype: `void **__fastcall(void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400105bc`

## callees

- `0x140011a18`
- `0x140012944`
- `0x140012c58`

## pseudocode

```c
void **__fastcall wil::run_as_self_failfast(void **a1)
{
  int v2; // eax
  void *v3; // rdx
  __int64 v4; // r8
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *a1 = (void *)-1LL;
  v2 = wil::impersonate_token_nothrow((__int64)a1, a1);
  if ( v2 < 0 )
    wil::details::in1diag3::_FailFast_Hr(retaddr, v3, v4, (const char *)(unsigned int)v2, v6);
  return a1;
}

```

## disassembly

```asm
0x140012c58  push    rbx; int
0x140012c5a  sub     rsp, 20h
0x140012c5e  mov     rdx, rcx
0x140012c61  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x140012c68  mov     rbx, rcx
0x140012c6b  call    ?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z; wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x140012c70  test    eax, eax
0x140012c72  jns     short loc_140012C82
0x140012c74  mov     rcx, [rsp+28h]; this
0x140012c79  mov     r9d, eax; char *
0x140012c7c  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x140012c82  mov     rax, rbx
0x140012c85  add     rsp, 20h
0x140012c89  pop     rbx
0x140012c8a  retn
```
