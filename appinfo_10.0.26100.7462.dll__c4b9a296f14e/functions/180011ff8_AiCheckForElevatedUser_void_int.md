# AiCheckForElevatedUser(void *,int *)

- ea: `0x180011ff8`
- end: `0x180012046`
- name: `?AiCheckForElevatedUser@@YAJPEAXPEAH@Z`
- size: `78`
- prototype: `__int64 __fastcall(void *, int *)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180016da4`
- `0x180016fa0`
- `0x18002a2a8`
- `0x18003ac30`
- `0x18003e0d0`
- `0x18003e5d4`

## callees

- `0x180011ff8`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180012027`
- `ntdll!NtQueryInformationToken` at `0x180012027`

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
0x180011ff8  push    rbx
0x180011ffa  sub     rsp, 30h
0x180011ffe  and     dword ptr [rdx], 0
0x180012001  lea     rax, [rsp+38h+arg_10]
0x180012006  and     [rsp+38h+TokenInformation], 0
0x18001200b  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180012010  and     [rsp+38h+arg_10], 0
0x180012015  mov     r9d, 4; TokenInformationLength
0x18001201b  mov     rbx, rdx
0x18001201e  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180012023  lea     edx, [r9+10h]; TokenInformationClass
0x180012027  call    cs:__imp_NtQueryInformationToken
0x18001202e  nop     dword ptr [rax+rax+00h]
0x180012033  test    eax, eax
0x180012035  js      short loc_18001203F
0x180012037  mov     eax, [rsp+38h+TokenInformation]
0x18001203b  mov     [rbx], eax
0x18001203d  xor     eax, eax
0x18001203f  add     rsp, 30h
0x180012043  pop     rbx
0x180012044  retn
```
