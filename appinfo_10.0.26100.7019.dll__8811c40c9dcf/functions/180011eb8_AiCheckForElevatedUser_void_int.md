# AiCheckForElevatedUser(void *,int *)

- ea: `0x180011eb8`
- end: `0x180011f06`
- name: `?AiCheckForElevatedUser@@YAJPEAXPEAH@Z`
- size: `78`
- prototype: `__int64 __fastcall(void *, int *)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001362c`
- `0x180016c54`
- `0x18002b828`
- `0x180039cb0`
- `0x18003bfe0`
- `0x18003c4c4`

## callees

- `0x180011eb8`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180011ee7`
- `ntdll!NtQueryInformationToken` at `0x180011ee7`

## pseudocode

```c
NTSTATUS __fastcall AiCheckForElevatedUser(void *a1, int *a2)
{
  NTSTATUS result; // eax
  int TokenInformation; // [rsp+48h] [rbp+10h] BYREF
  ULONG ReturnLength; // [rsp+50h] [rbp+18h] BYREF

  *a2 = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  result = NtQueryInformationToken(a1, TokenElevation, &TokenInformation, 4u, &ReturnLength);
  if ( result >= 0 )
  {
    *a2 = TokenInformation;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180011eb8  push    rbx
0x180011eba  sub     rsp, 30h
0x180011ebe  and     dword ptr [rdx], 0
0x180011ec1  lea     rax, [rsp+38h+arg_10]
0x180011ec6  and     [rsp+38h+TokenInformation], 0
0x180011ecb  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180011ed0  and     [rsp+38h+arg_10], 0
0x180011ed5  mov     r9d, 4; TokenInformationLength
0x180011edb  mov     rbx, rdx
0x180011ede  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180011ee3  lea     edx, [r9+10h]; TokenInformationClass
0x180011ee7  call    cs:__imp_NtQueryInformationToken
0x180011eee  nop     dword ptr [rax+rax+00h]
0x180011ef3  test    eax, eax
0x180011ef5  js      short loc_180011EFF
0x180011ef7  mov     eax, [rsp+38h+TokenInformation]
0x180011efb  mov     [rbx], eax
0x180011efd  xor     eax, eax
0x180011eff  add     rsp, 30h
0x180011f03  pop     rbx
0x180011f04  retn
```
