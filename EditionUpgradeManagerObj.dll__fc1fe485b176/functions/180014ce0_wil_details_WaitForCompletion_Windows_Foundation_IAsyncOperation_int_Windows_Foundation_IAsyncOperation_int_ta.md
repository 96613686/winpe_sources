# `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<int> *>(Windows::Foundation::IAsyncOperation<int> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::Invoke(Windows::Foundation::IAsyncOperation<int> *,ABI::Windows::Foundation::AsyncStatus)

- ea: `0x180014ce0`
- end: `0x180014d0d`
- name: `?Invoke@CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@H@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@H@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@UEAAJ0W4AsyncStatus@56ABI@@@Z`
- size: `45`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800086fc`
- `0x180014ce0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014cec`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014cec`

## pseudocode

```c
__int64 __fastcall `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<int> *>'::`2'::CompletionDelegate::Invoke(
        __int64 a1,
        __int64 a2,
        int a3)
{
  __int64 v3; // r8
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_DWORD *)(a1 + 48) = a3;
  if ( !SetEvent(*(HANDLE *)(a1 + 56)) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v3, v4);
  return 0;
}

```

## disassembly

```asm
0x180014ce0  sub     rsp, 28h
0x180014ce4  mov     [rcx+30h], r8d
0x180014ce8  mov     rcx, [rcx+38h]; hEvent
0x180014cec  call    cs:__imp_SetEvent
0x180014cf2  test    eax, eax
0x180014cf4  jz      short loc_180014CFD
0x180014cf6  xor     eax, eax
0x180014cf8  add     rsp, 28h
0x180014cfc  retn
0x180014cfd  mov     rcx, [rsp+28h]; this
0x180014d02  mov     edx, 0A01h; void *
0x180014d07  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
