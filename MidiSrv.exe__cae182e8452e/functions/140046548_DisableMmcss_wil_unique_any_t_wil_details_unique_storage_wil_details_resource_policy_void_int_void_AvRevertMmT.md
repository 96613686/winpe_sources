# DisableMmcss(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&AvRevertMmThreadCharacteristics(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)

- ea: `0x140046548`
- end: `0x14004659d`
- name: `?DisableMmcss@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?AvRevertMmThreadCharacteristics@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `85`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140046bf0`
- `0x140047b08`

## callees

- `0x140046548`
- `0x140046b90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14004657e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14004657e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004656b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004656b`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x140046576`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x140046576`

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
0x140046548  mov     [rsp+arg_0], rbx
0x14004654d  mov     [rsp+arg_8], rsi
0x140046552  push    rdi
0x140046553  sub     rsp, 20h
0x140046557  mov     rsi, rcx
0x14004655a  call    ?MMCSSUseEnabled@CMidiXProc@@SA_NXZ; CMidiXProc::MMCSSUseEnabled(void)
0x14004655f  test    al, al
0x140046561  jz      short loc_14004658B
0x140046563  mov     rdi, [rsi]
0x140046566  test    rdi, rdi
0x140046569  jz      short loc_14004658B
0x14004656b  call    cs:__imp_GetLastError
0x140046571  mov     rcx, rdi; AvrtHandle
0x140046574  mov     ebx, eax
0x140046576  call    cs:__imp_AvRevertMmThreadCharacteristics
0x14004657c  mov     ecx, ebx; dwErrCode
0x14004657e  call    cs:__imp_SetLastError
0x140046584  mov     qword ptr [rsi], 0
0x14004658b  mov     rbx, [rsp+28h+arg_0]
0x140046590  xor     eax, eax
0x140046592  mov     rsi, [rsp+28h+arg_8]
0x140046597  add     rsp, 20h
0x14004659b  pop     rdi
0x14004659c  retn
```
