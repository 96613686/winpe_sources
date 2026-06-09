# AiCheckForElevatedUser(void *,int *)

- ea: `0x180010dd4`
- end: `0x180010e24`
- name: `?AiCheckForElevatedUser@@YAJPEAXPEAH@Z`
- size: `80`
- prototype: `NTSTATUS __fastcall(void *, int *)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180017680`
- `0x18002ed98`
- `0x18003d070`
- `0x18003f14c`
- `0x1800409a0`
- `0x180040d64`

## callees

- `0x180010dd4`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180010e0c`
- `ntdll!NtQueryInformationToken` at `0x180010e0c`

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
0x180010dd4  push    rbx
0x180010dd6  sub     rsp, 30h
0x180010dda  mov     r9d, 4; TokenInformationLength
0x180010de0  mov     dword ptr [rdx], 0
0x180010de6  mov     rbx, rdx
0x180010de9  mov     [rsp+38h+TokenInformation], 0
0x180010df1  lea     rax, [rsp+38h+arg_10]
0x180010df6  mov     [rsp+38h+arg_10], 0
0x180010dfe  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180010e03  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180010e08  lea     edx, [r9+10h]; TokenInformationClass
0x180010e0c  call    cs:__imp_NtQueryInformationToken
0x180010e12  test    eax, eax
0x180010e14  js      short loc_180010E1E
0x180010e16  mov     eax, [rsp+38h+TokenInformation]
0x180010e1a  mov     [rbx], eax
0x180010e1c  xor     eax, eax
0x180010e1e  add     rsp, 30h
0x180010e22  pop     rbx
0x180010e23  retn
```
