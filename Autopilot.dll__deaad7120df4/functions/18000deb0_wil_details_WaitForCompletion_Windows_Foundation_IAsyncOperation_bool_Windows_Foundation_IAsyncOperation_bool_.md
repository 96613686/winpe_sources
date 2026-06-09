# `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::Invoke(Windows::Foundation::IAsyncOperation<bool> *,ABI::Windows::Foundation::AsyncStatus)

- ea: `0x18000deb0`
- end: `0x18000deeb`
- name: `?Invoke@CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@_N@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@UEAAJ0W4AsyncStatus@56ABI@@@Z`
- size: `59`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000deb0`
- `0x180012220`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000debc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000debc`

## string_xrefs

- `0x18000ded9`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>'::`2'::CompletionDelegate::Invoke(
        __int64 a1,
        __int64 a2,
        int a3)
{
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_DWORD *)(a1 + 48) = a3;
  if ( !SetEvent(*(HANDLE *)(a1 + 56)) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA01,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v3);
  return 0;
}

```

## disassembly

```asm
0x18000deb0  sub     rsp, 28h
0x18000deb4  mov     [rcx+30h], r8d
0x18000deb8  mov     rcx, [rcx+38h]; hEvent
0x18000debc  call    cs:__imp_SetEvent
0x18000dec3  nop     dword ptr [rax+rax+00h]
0x18000dec8  test    eax, eax
0x18000deca  jz      short loc_18000DED4
0x18000decc  xor     eax, eax
0x18000dece  add     rsp, 28h
0x18000ded2  retn
0x18000ded4  mov     rcx, [rsp+28h]; this
0x18000ded9  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000dee0  mov     edx, 0A01h; void *
0x18000dee5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
