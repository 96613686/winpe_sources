# SystemSettings::DataModel::UserImpersonator::StartImpersonating(void *)

- ea: `0x18001e350`
- end: `0x18001e398`
- name: `?StartImpersonating@UserImpersonator@DataModel@SystemSettings@@QEAAKPEAX@Z`
- size: `72`
- prototype: `unsigned int(SystemSettings::DataModel::UserImpersonator *__hidden this, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180021f20`
- `0x180021fb0`

## callees

- `0x18001e350`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e37c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e37c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001e367`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001e367`

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
0x18001e350  mov     [rsp+arg_0], rbx
0x18001e355  push    rdi
0x18001e356  sub     rsp, 20h
0x18001e35a  xor     ebx, ebx
0x18001e35c  mov     rdi, rcx
0x18001e35f  test    rdx, rdx
0x18001e362  jz      short loc_18001E38A
0x18001e364  mov     rcx, rdx; hToken
0x18001e367  call    cs:__imp_ImpersonateLoggedOnUser
0x18001e36e  nop     dword ptr [rax+rax+00h]
0x18001e373  test    eax, eax
0x18001e375  jz      short loc_18001E37C
0x18001e377  mov     byte ptr [rdi], 1
0x18001e37a  jmp     short loc_18001E38A
0x18001e37c  call    cs:__imp_GetLastError
0x18001e383  nop     dword ptr [rax+rax+00h]
0x18001e388  mov     ebx, eax
0x18001e38a  mov     eax, ebx
0x18001e38c  mov     rbx, [rsp+28h+arg_0]
0x18001e391  add     rsp, 20h
0x18001e395  pop     rdi
0x18001e396  retn
```
