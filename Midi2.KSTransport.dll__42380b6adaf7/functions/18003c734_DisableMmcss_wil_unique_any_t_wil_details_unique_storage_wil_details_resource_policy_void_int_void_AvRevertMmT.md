# DisableMmcss(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&AvRevertMmThreadCharacteristics(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)

- ea: `0x18003c734`
- end: `0x18003c789`
- name: `?DisableMmcss@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?AvRevertMmThreadCharacteristics@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `85`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180028b30`
- `0x180029db0`
- `0x18003cdd0`
- `0x18003dd1c`

## callees

- `0x18003c734`
- `0x18003cd70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c76a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c76a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c757`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c757`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18003c762`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18003c762`

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
0x18003c734  mov     [rsp+arg_0], rbx
0x18003c739  mov     [rsp+arg_8], rsi
0x18003c73e  push    rdi
0x18003c73f  sub     rsp, 20h
0x18003c743  mov     rsi, rcx
0x18003c746  call    ?MMCSSUseEnabled@CMidiXProc@@SA_NXZ; CMidiXProc::MMCSSUseEnabled(void)
0x18003c74b  test    al, al
0x18003c74d  jz      short loc_18003C777
0x18003c74f  mov     rdi, [rsi]
0x18003c752  test    rdi, rdi
0x18003c755  jz      short loc_18003C777
0x18003c757  call    cs:__imp_GetLastError
0x18003c75d  mov     rcx, rdi; AvrtHandle
0x18003c760  mov     ebx, eax
0x18003c762  call    cs:__imp_AvRevertMmThreadCharacteristics
0x18003c768  mov     ecx, ebx; dwErrCode
0x18003c76a  call    cs:__imp_SetLastError
0x18003c770  mov     qword ptr [rsi], 0
0x18003c777  mov     rbx, [rsp+28h+arg_0]
0x18003c77c  xor     eax, eax
0x18003c77e  mov     rsi, [rsp+28h+arg_8]
0x18003c783  add     rsp, 20h
0x18003c787  pop     rdi
0x18003c788  retn
```
