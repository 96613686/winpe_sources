# SystemSettings::DataModel::UserImpersonator::StartImpersonating(void *)

- ea: `0x18003a818`
- end: `0x18003a853`
- name: `?StartImpersonating@UserImpersonator@DataModel@SystemSettings@@QEAAKPEAX@Z`
- size: `59`
- prototype: `unsigned int(SystemSettings::DataModel::UserImpersonator *__hidden this, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003ab50`
- `0x1800530a0`

## callees

- `0x18003a818`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a83e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a83e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003a82f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003a82f`

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
0x18003a818  mov     [rsp+arg_0], rbx
0x18003a81d  push    rdi
0x18003a81e  sub     rsp, 20h
0x18003a822  xor     ebx, ebx
0x18003a824  mov     rdi, rcx
0x18003a827  test    rdx, rdx
0x18003a82a  jz      short loc_18003A846
0x18003a82c  mov     rcx, rdx; hToken
0x18003a82f  call    cs:__imp_ImpersonateLoggedOnUser
0x18003a835  test    eax, eax
0x18003a837  jz      short loc_18003A83E
0x18003a839  mov     byte ptr [rdi], 1
0x18003a83c  jmp     short loc_18003A846
0x18003a83e  call    cs:__imp_GetLastError
0x18003a844  mov     ebx, eax
0x18003a846  mov     eax, ebx
0x18003a848  mov     rbx, [rsp+28h+arg_0]
0x18003a84d  add     rsp, 20h
0x18003a851  pop     rdi
0x18003a852  retn
```
