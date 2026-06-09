# std::thread::_Invoke_std::tuple__lambda_1ad8bec329c890e3e1881878130943db____0_

- ea: `0x1800753e0`
- end: `0x180075446`
- name: `std::thread::_Invoke_std::tuple__lambda_1ad8bec329c890e3e1881878130943db____0_`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800112c0`
- `0x180031540`
- `0x1800753e0`
- `0x1800759c0`

## import_xrefs

- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x18007542e`
- `msvcp_win!_Cnd_do_broadcast_at_thread_exit` at `0x18007542e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800753f2`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800753f2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180075427`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180075427`

## string_xrefs

- `0x180075404`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::thread::_Invoke_std::tuple__lambda_1ad8bec329c890e3e1881878130943db____0_(
        NamedPipeChannel **a1)
{
  NamedPipeChannel *v1; // rbx
  HRESULT v2; // eax
  bool v3; // dl
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  NamedPipeChannel **v7; // [rsp+30h] [rbp+8h] BYREF

  v7 = a1;
  v1 = *a1;
  v2 = CoInitializeEx(0, 0);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14D3,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v2,
      v5);
  while ( !*((_BYTE *)v1 + 152) )
    NamedPipeChannel::RunOnce(v1, v3);
  CoUninitialize();
  _Cnd_do_broadcast_at_thread_exit();
  std::unique_ptr_std::tuple__lambda_1ad8bec329c890e3e1881878130943db____std::default_delete_std::tuple__lambda_1ad8bec329c890e3e1881878130943db_______::_unique_ptr_std::tuple__lambda_1ad8bec329c890e3e1881878130943db____std::default_delete_std::tuple__lambda_1ad8bec329c890e3e1881878130943db_______(&v7);
  return 0;
}

```

## disassembly

```asm
0x1800753e0  push    rbx; int
0x1800753e2  sub     rsp, 20h
0x1800753e6  mov     [rsp+28h+arg_0], rcx
0x1800753eb  mov     rbx, [rcx]
0x1800753ee  xor     edx, edx; dwCoInit
0x1800753f0  xor     ecx, ecx; pvReserved
0x1800753f2  call    cs:__imp_CoInitializeEx
0x1800753f8  mov     rcx, [rsp+28h]; this
0x1800753fd  test    eax, eax
0x1800753ff  jns     short loc_18007541E
0x180075401  mov     r9d, eax; char *
0x180075404  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18007540b  mov     edx, 14D3h; void *
0x180075410  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180075416  mov     rcx, rbx; this
0x180075419  call    ?RunOnce@NamedPipeChannel@@AEAAJXZ; NamedPipeChannel::RunOnce(void)
0x18007541e  cmp     byte ptr [rbx+98h], 0
0x180075425  jz      short loc_180075416
0x180075427  call    cs:__imp_CoUninitialize
0x18007542d  nop
0x18007542e  call    cs:__imp__Cnd_do_broadcast_at_thread_exit
0x180075434  lea     rcx, [rsp+28h+arg_0]
0x180075439  call    std__unique_ptr_std__tuple__lambda_1ad8bec329c890e3e1881878130943db____std__default_delete_std__tuple__lambda_1ad8bec329c890e3e1881878130943db__________unique_ptr_std__tuple__lambda_1ad8bec329c890e3e1881878130943db____std__default_delete_std__tuple__lambda_1ad8bec329c890e3e1881878130943db_______
0x18007543e  xor     eax, eax
0x180075440  add     rsp, 20h
0x180075444  pop     rbx
0x180075445  retn
```
