# ?reset@?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@QAEXPAX@Z

- ea: `0x40c066`
- end: `0x40c097`
- name: `?reset@?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@QAEXPAX@Z`
- size: `49`
- prototype: `void *__thiscall(void **this, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x40c01c`
- `0x40c3ba`
- `0x40c51f`

## callees

- `0x40ae71`
- `0x40c066`

## import_xrefs

- `KERNEL32!SetLastError` at `0x40c085`
- `KERNEL32!SetLastError` at `0x40c085`
- `KERNEL32!GetLastError` at `0x40c076`
- `KERNEL32!GetLastError` at `0x40c076`

## pseudocode

```c
void *__thiscall _reset___unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__QAEXPAX_Z(
        void **this,
        void *a2)
{
  void *v3; // ebx
  DWORD LastError; // esi
  void *result; // eax
  void *v6; // [esp+0h] [ebp-Ch]

  v3 = *this;
  if ( *this )
  {
    LastError = GetLastError();
    wil::details::CloseHandle(v3, v6);
    SetLastError(LastError);
  }
  result = a2;
  *this = a2;
  return result;
}

```

## disassembly

```asm
0x40c066  mov     edi, edi
0x40c068  push    ebp
0x40c069  mov     ebp, esp
0x40c06b  push    ebx
0x40c06c  push    esi
0x40c06d  push    edi; void *
0x40c06e  mov     edi, ecx
0x40c070  mov     ebx, [edi]
0x40c072  test    ebx, ebx
0x40c074  jz      short loc_40C08B
0x40c076  call    ds:__imp__GetLastError@0; GetLastError()
0x40c07c  push    ebx; hObject
0x40c07d  mov     esi, eax
0x40c07f  call    ?CloseHandle@details@wil@@YGXPAX@Z; wil::details::CloseHandle(void *)
0x40c084  push    esi; dwErrCode
0x40c085  call    ds:__imp__SetLastError@4; SetLastError(x)
0x40c08b  mov     eax, [ebp+arg_0]
0x40c08e  mov     [edi], eax
0x40c090  pop     edi
0x40c091  pop     esi
0x40c092  pop     ebx
0x40c093  pop     ebp
0x40c094  retn    4
```
