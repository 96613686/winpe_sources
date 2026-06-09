# wil::details::lambda_call__Windows::AI::IsolationEnvironment::IsolationEnvironment::GetRegisteredPathResources_::_2_::_lambda_1___::_lambda_call__Windows::AI::IsolationEnvironment::IsolationEnvironment::GetRegisteredPathResources_::_2_::_lambda_1___

- ea: `0x180048c30`
- end: `0x180048c97`
- name: `wil::details::lambda_call__Windows::AI::IsolationEnvironment::IsolationEnvironment::GetRegisteredPathResources_::_2_::_lambda_1___::_lambda_call__Windows::AI::IsolationEnvironment::IsolationEnvironment::GetRegisteredPathResources_::_2_::_lambda_1___`
- size: `103`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180049750`

## callees

- `0x180048c30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048c86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048c86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048c64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048c64`

## pseudocode

```c
void __fastcall wil::details::lambda_call__Windows::AI::IsolationEnvironment::IsolationEnvironment::GetRegisteredPathResources_::_2_::_lambda_1___::_lambda_call__Windows::AI::IsolationEnvironment::IsolationEnvironment::GetRegisteredPathResources_::_2_::_lambda_1___(
        __int64 a1)
{
  __int64 i; // rdi
  void *v3; // rcx

  if ( *(_BYTE *)(a1 + 16) )
  {
    *(_BYTE *)(a1 + 16) = 0;
    if ( **(_QWORD **)a1 )
    {
      for ( i = 0; (unsigned int)i < **(_DWORD **)(a1 + 8); i = (unsigned int)(i + 1) )
        WindowsDeleteString(*(HSTRING *)(**(_QWORD **)a1 + 8 * i));
      v3 = **(void ***)a1;
      **(_QWORD **)a1 = 0;
      if ( v3 )
        CoTaskMemFree(v3);
    }
  }
}

```

## disassembly

```asm
0x180048c30  mov     [rsp+arg_0], rbx
0x180048c35  push    rdi
0x180048c36  sub     rsp, 20h
0x180048c3a  cmp     byte ptr [rcx+10h], 0
0x180048c3e  mov     rbx, rcx
0x180048c41  jz      short loc_180048C8C
0x180048c43  mov     byte ptr [rcx+10h], 0
0x180048c47  mov     rax, [rcx]
0x180048c4a  cmp     qword ptr [rax], 0
0x180048c4e  jz      short loc_180048C8C
0x180048c50  mov     rax, [rcx+8]
0x180048c54  xor     edi, edi
0x180048c56  cmp     [rax], edi
0x180048c58  jbe     short loc_180048C74
0x180048c5a  mov     rax, [rbx]
0x180048c5d  mov     rcx, [rax]
0x180048c60  mov     rcx, [rcx+rdi*8]; string
0x180048c64  call    cs:__imp_WindowsDeleteString
0x180048c6a  mov     rax, [rbx+8]
0x180048c6e  inc     edi
0x180048c70  cmp     edi, [rax]
0x180048c72  jb      short loc_180048C5A
0x180048c74  mov     rax, [rbx]
0x180048c77  mov     rcx, [rax]; pv
0x180048c7a  mov     qword ptr [rax], 0
0x180048c81  test    rcx, rcx
0x180048c84  jz      short loc_180048C8C
0x180048c86  call    cs:__imp_CoTaskMemFree
0x180048c8c  mov     rbx, [rsp+28h+arg_0]
0x180048c91  add     rsp, 20h
0x180048c95  pop     rdi
0x180048c96  retn
```
