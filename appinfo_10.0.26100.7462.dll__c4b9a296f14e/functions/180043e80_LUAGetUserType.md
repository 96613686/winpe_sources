# LUAGetUserType

- ea: `0x180043e80`
- end: `0x180043f65`
- name: `LUAGetUserType`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002a2a8`

## callees

- `0x18001959c`
- `0x180043e80`
- `0x180043fb8`

## import_xrefs

- `ntdll!NtClose` at `0x180043f49`
- `ntdll!NtClose` at `0x180043f49`
- `ntdll!NtOpenThreadToken` at `0x180043eb7`
- `ntdll!NtOpenThreadToken` at `0x180043eb7`
- `ntdll!NtOpenProcessToken` at `0x180043ed6`
- `ntdll!NtOpenProcessToken` at `0x180043ed6`

## pseudocode

```c
__int64 __fastcall LUAGetUserType(void *a1, int *a2)
{
  void *v2; // rsi
  NTSTATUS v4; // ebx
  int v5; // ecx
  _DWORD v7[4]; // [rsp+20h] [rbp-10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+20h] BYREF
  int v9; // [rsp+60h] [rbp+30h] BYREF
  int v10; // [rsp+68h] [rbp+38h] BYREF

  TokenHandle = a1;
  v2 = 0;
  v9 = 0;
  v10 = 0;
  v7[0] = 0;
  if ( a1 )
  {
LABEL_6:
    v4 = LUAIsElevatedToken(a1, &v9, &v10);
    if ( v4 >= 0 )
    {
      *a2 = v9 ? 0 : 2 - (v10 != 0);
      v4 = LUAIsUIAToken(TokenHandle, v7);
      if ( v4 >= 0 )
      {
        if ( v7[0] )
        {
          v5 = *a2;
          if ( (unsigned int)(*a2 - 16) > 2 )
            v5 += 16;
          *a2 = v5;
        }
      }
    }
    if ( v2 )
      NtClose(v2);
    return (unsigned int)v4;
  }
  v4 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 0, &TokenHandle);
  if ( v4 == -1073741700 )
    v4 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
  if ( v4 >= 0 )
  {
    a1 = TokenHandle;
    v2 = TokenHandle;
    goto LABEL_6;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180043e80  mov     [rsp-18h+arg_8], rbx
0x180043e85  mov     [rsp-18h+TokenHandle], rcx
0x180043e8a  push    rbp
0x180043e8b  push    rsi
0x180043e8c  push    rdi
0x180043e8d  mov     rbp, rsp
0x180043e90  sub     rsp, 30h
0x180043e94  xor     esi, esi
0x180043e96  mov     rdi, rdx
0x180043e99  and     [rbp+arg_10], esi
0x180043e9c  and     [rbp+arg_18], esi
0x180043e9f  and     [rbp+var_10], esi
0x180043ea2  test    rcx, rcx
0x180043ea5  jnz     short loc_180043EEF
0x180043ea7  lea     esi, [rcx+8]
0x180043eaa  xor     r8d, r8d; OpenAsSelf
0x180043ead  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180043eb1  mov     edx, esi; DesiredAccess
0x180043eb3  lea     rcx, [r8-2]; ThreadHandle
0x180043eb7  call    cs:__imp_NtOpenThreadToken
0x180043ebe  nop     dword ptr [rax+rax+00h]
0x180043ec3  mov     ebx, eax
0x180043ec5  cmp     eax, 0C000007Ch
0x180043eca  jnz     short loc_180043EE4
0x180043ecc  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180043ed0  mov     edx, esi; DesiredAccess
0x180043ed2  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180043ed6  call    cs:__imp_NtOpenProcessToken
0x180043edd  nop     dword ptr [rax+rax+00h]
0x180043ee2  mov     ebx, eax
0x180043ee4  test    ebx, ebx
0x180043ee6  js      short loc_180043F55
0x180043ee8  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180043eec  mov     rsi, rcx
0x180043eef  lea     r8, [rbp+arg_18]
0x180043ef3  lea     rdx, [rbp+arg_10]
0x180043ef7  call    LUAIsElevatedToken
0x180043efc  mov     ebx, eax
0x180043efe  test    eax, eax
0x180043f00  js      short loc_180043F41
0x180043f02  cmp     [rbp+arg_10], 0
0x180043f06  jz      short loc_180043F0D
0x180043f08  and     dword ptr [rdi], 0
0x180043f0b  jmp     short loc_180043F19
0x180043f0d  mov     eax, [rbp+arg_18]
0x180043f10  neg     eax
0x180043f12  sbb     ecx, ecx
0x180043f14  add     ecx, 2
0x180043f17  mov     [rdi], ecx
0x180043f19  mov     rcx, [rbp+TokenHandle]
0x180043f1d  lea     rdx, [rbp+var_10]
0x180043f21  call    LUAIsUIAToken
0x180043f26  mov     ebx, eax
0x180043f28  test    eax, eax
0x180043f2a  js      short loc_180043F41
0x180043f2c  cmp     [rbp+var_10], 0
0x180043f30  jz      short loc_180043F41
0x180043f32  mov     ecx, [rdi]
0x180043f34  lea     eax, [rcx-10h]
0x180043f37  cmp     eax, 2
0x180043f3a  jbe     short loc_180043F3F
0x180043f3c  add     ecx, 10h
0x180043f3f  mov     [rdi], ecx
0x180043f41  test    rsi, rsi
0x180043f44  jz      short loc_180043F55
0x180043f46  mov     rcx, rsi; Handle
0x180043f49  call    cs:__imp_NtClose
0x180043f50  nop     dword ptr [rax+rax+00h]
0x180043f55  mov     eax, ebx
0x180043f57  mov     rbx, [rsp+30h+arg_8]
0x180043f5c  add     rsp, 30h
0x180043f60  pop     rdi
0x180043f61  pop     rsi
0x180043f62  pop     rbp
0x180043f63  retn
```
