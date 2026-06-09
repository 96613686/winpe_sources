# DisableMmcss(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&AvRevertMmThreadCharacteristics(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)

- ea: `0x18000d854`
- end: `0x18000d8a9`
- name: `?DisableMmcss@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?AvRevertMmThreadCharacteristics@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `85`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000f4e0`
- `0x180010b10`

## callees

- `0x18000d854`
- `0x18000f438`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d88a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d88a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d877`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d877`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18000d882`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18000d882`

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
0x18000d854  mov     [rsp+arg_0], rbx
0x18000d859  mov     [rsp+arg_8], rsi
0x18000d85e  push    rdi
0x18000d85f  sub     rsp, 20h
0x18000d863  mov     rsi, rcx
0x18000d866  call    ?MMCSSUseEnabled@CMidiXProc@@SA_NXZ; CMidiXProc::MMCSSUseEnabled(void)
0x18000d86b  test    al, al
0x18000d86d  jz      short loc_18000D897
0x18000d86f  mov     rdi, [rsi]
0x18000d872  test    rdi, rdi
0x18000d875  jz      short loc_18000D897
0x18000d877  call    cs:__imp_GetLastError
0x18000d87d  mov     rcx, rdi; AvrtHandle
0x18000d880  mov     ebx, eax
0x18000d882  call    cs:__imp_AvRevertMmThreadCharacteristics
0x18000d888  mov     ecx, ebx; dwErrCode
0x18000d88a  call    cs:__imp_SetLastError
0x18000d890  mov     qword ptr [rsi], 0
0x18000d897  mov     rbx, [rsp+28h+arg_0]
0x18000d89c  xor     eax, eax
0x18000d89e  mov     rsi, [rsp+28h+arg_8]
0x18000d8a3  add     rsp, 20h
0x18000d8a7  pop     rdi
0x18000d8a8  retn
```
