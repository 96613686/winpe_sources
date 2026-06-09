# `wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::RuntimeClassInitialize(void)

- ea: `0x180030a84`
- end: `0x180030af3`
- name: `?RuntimeClassInitialize@CompletionDelegate@?1???$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@QEAAJXZ`
- size: `111`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e8a0`

## callees

- `0x1800227e8`
- `0x180030914`
- `0x180030a84`
- `0x180030ca0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180030a9e`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180030a9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030aac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030aac`

## string_xrefs

- `0x180030ad2`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 __fastcall `wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>'::`2'::CompletionDelegate::RuntimeClassInitialize(
        __int64 a1)
{
  wil::details *v2; // rcx
  HANDLE Event; // rbx
  unsigned int v4; // ebx
  int LastErrorFailHr; // eax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      a1 + 56,
      Event);
    return 0;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v2);
    v4 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x62B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
        (const char *)(unsigned int)LastErrorFailHr,
        v7);
  }
  return v4;
}

```

## disassembly

```asm
0x180030a84  mov     [rsp+arg_0], rbx
0x180030a89  push    rdi; int
0x180030a8a  sub     rsp, 20h
0x180030a8e  mov     rdi, rcx
0x180030a91  mov     r9d, 1F0003h; dwDesiredAccess
0x180030a97  xor     ecx, ecx; lpEventAttributes
0x180030a99  xor     r8d, r8d; dwFlags
0x180030a9c  xor     edx, edx; lpName
0x180030a9e  call    cs:__imp_CreateEventExW
0x180030aa4  mov     rbx, rax
0x180030aa7  test    rax, rax
0x180030aaa  jz      short loc_180030AC2
0x180030aac  call    cs:__imp_GetLastError
0x180030ab2  lea     rcx, [rdi+38h]
0x180030ab6  mov     rdx, rbx
0x180030ab9  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180030abe  xor     ebx, ebx
0x180030ac0  jmp     short loc_180030AE6
0x180030ac2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180030ac7  mov     ebx, eax
0x180030ac9  test    eax, eax
0x180030acb  jns     short loc_180030AE6
0x180030acd  mov     rcx, [rsp+28h]; this
0x180030ad2  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180030ad9  mov     r9d, eax; char *
0x180030adc  mov     edx, 62Bh; void *
0x180030ae1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030ae6  mov     eax, ebx
0x180030ae8  mov     rbx, [rsp+28h+arg_0]
0x180030aed  add     rsp, 20h
0x180030af1  pop     rdi
0x180030af2  retn
```
