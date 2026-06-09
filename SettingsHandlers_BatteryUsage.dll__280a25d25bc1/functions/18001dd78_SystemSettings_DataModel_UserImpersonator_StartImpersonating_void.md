# SystemSettings::DataModel::UserImpersonator::StartImpersonating(void *)

- ea: `0x18001dd78`
- end: `0x18001ddb3`
- name: `?StartImpersonating@UserImpersonator@DataModel@SystemSettings@@QEAAKPEAX@Z`
- size: `59`
- prototype: `unsigned int(SystemSettings::DataModel::UserImpersonator *__hidden this, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001ebc0`
- `0x180031530`

## callees

- `0x18001dd78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dd9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dd9e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001dd8f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001dd8f`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::UserImpersonator::StartImpersonating(
        SystemSettings::DataModel::UserImpersonator *this,
        void *a2)
{
  unsigned int v2; // ebx

  v2 = 0;
  if ( a2 )
  {
    if ( ImpersonateLoggedOnUser(a2) )
      *(_BYTE *)this = 1;
    else
      return GetLastError();
  }
  return v2;
}

```

## disassembly

```asm
0x18001dd78  mov     [rsp+arg_0], rbx
0x18001dd7d  push    rdi
0x18001dd7e  sub     rsp, 20h
0x18001dd82  xor     ebx, ebx
0x18001dd84  mov     rdi, rcx
0x18001dd87  test    rdx, rdx
0x18001dd8a  jz      short loc_18001DDA6
0x18001dd8c  mov     rcx, rdx; hToken
0x18001dd8f  call    cs:__imp_ImpersonateLoggedOnUser
0x18001dd95  test    eax, eax
0x18001dd97  jz      short loc_18001DD9E
0x18001dd99  mov     byte ptr [rdi], 1
0x18001dd9c  jmp     short loc_18001DDA6
0x18001dd9e  call    cs:__imp_GetLastError
0x18001dda4  mov     ebx, eax
0x18001dda6  mov     eax, ebx
0x18001dda8  mov     rbx, [rsp+28h+arg_0]
0x18001ddad  add     rsp, 20h
0x18001ddb1  pop     rdi
0x18001ddb2  retn
```
