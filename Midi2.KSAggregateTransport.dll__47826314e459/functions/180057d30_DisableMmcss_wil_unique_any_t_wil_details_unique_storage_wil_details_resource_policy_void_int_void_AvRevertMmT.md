# DisableMmcss(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&AvRevertMmThreadCharacteristics(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)

- ea: `0x180057d30`
- end: `0x180057d85`
- name: `?DisableMmcss@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?AvRevertMmThreadCharacteristics@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `85`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180049670`
- `0x18004a750`
- `0x1800583d0`
- `0x1800592dc`

## callees

- `0x180057d30`
- `0x18005836c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180057d66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180057d66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057d53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057d53`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x180057d5e`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x180057d5e`

## pseudocode

```c
__int64 __fastcall DisableMmcss(void **a1)
{
  void *v2; // rdi
  DWORD LastError; // ebx

  if ( CMidiXProc::MMCSSUseEnabled() )
  {
    v2 = *a1;
    if ( *a1 )
    {
      LastError = GetLastError();
      AvRevertMmThreadCharacteristics(v2);
      SetLastError(LastError);
      *a1 = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180057d30  mov     [rsp+arg_0], rbx
0x180057d35  mov     [rsp+arg_8], rsi
0x180057d3a  push    rdi
0x180057d3b  sub     rsp, 20h
0x180057d3f  mov     rsi, rcx
0x180057d42  call    ?MMCSSUseEnabled@CMidiXProc@@SA_NXZ; CMidiXProc::MMCSSUseEnabled(void)
0x180057d47  test    al, al
0x180057d49  jz      short loc_180057D73
0x180057d4b  mov     rdi, [rsi]
0x180057d4e  test    rdi, rdi
0x180057d51  jz      short loc_180057D73
0x180057d53  call    cs:__imp_GetLastError
0x180057d59  mov     rcx, rdi; AvrtHandle
0x180057d5c  mov     ebx, eax
0x180057d5e  call    cs:__imp_AvRevertMmThreadCharacteristics
0x180057d64  mov     ecx, ebx; dwErrCode
0x180057d66  call    cs:__imp_SetLastError
0x180057d6c  mov     qword ptr [rsi], 0
0x180057d73  mov     rbx, [rsp+28h+arg_0]
0x180057d78  xor     eax, eax
0x180057d7a  mov     rsi, [rsp+28h+arg_8]
0x180057d7f  add     rsp, 20h
0x180057d83  pop     rdi
0x180057d84  retn
```
