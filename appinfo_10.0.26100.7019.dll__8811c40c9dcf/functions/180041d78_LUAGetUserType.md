# LUAGetUserType

- ea: `0x180041d78`
- end: `0x180041e5d`
- name: `LUAGetUserType`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002b828`

## callees

- `0x1800191cc`
- `0x180041d78`
- `0x180041eb0`

## import_xrefs

- `ntdll!NtClose` at `0x180041e41`
- `ntdll!NtClose` at `0x180041e41`
- `ntdll!NtOpenThreadToken` at `0x180041daf`
- `ntdll!NtOpenThreadToken` at `0x180041daf`
- `ntdll!NtOpenProcessToken` at `0x180041dce`
- `ntdll!NtOpenProcessToken` at `0x180041dce`

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
0x180041d78  mov     [rsp-18h+arg_8], rbx
0x180041d7d  mov     [rsp-18h+TokenHandle], rcx
0x180041d82  push    rbp
0x180041d83  push    rsi
0x180041d84  push    rdi
0x180041d85  mov     rbp, rsp
0x180041d88  sub     rsp, 30h
0x180041d8c  xor     esi, esi
0x180041d8e  mov     rdi, rdx
0x180041d91  and     [rbp+arg_10], esi
0x180041d94  and     [rbp+arg_18], esi
0x180041d97  and     [rbp+var_10], esi
0x180041d9a  test    rcx, rcx
0x180041d9d  jnz     short loc_180041DE7
0x180041d9f  lea     esi, [rcx+8]
0x180041da2  xor     r8d, r8d; OpenAsSelf
0x180041da5  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180041da9  mov     edx, esi; DesiredAccess
0x180041dab  lea     rcx, [r8-2]; ThreadHandle
0x180041daf  call    cs:__imp_NtOpenThreadToken
0x180041db6  nop     dword ptr [rax+rax+00h]
0x180041dbb  mov     ebx, eax
0x180041dbd  cmp     eax, 0C000007Ch
0x180041dc2  jnz     short loc_180041DDC
0x180041dc4  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180041dc8  mov     edx, esi; DesiredAccess
0x180041dca  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180041dce  call    cs:__imp_NtOpenProcessToken
0x180041dd5  nop     dword ptr [rax+rax+00h]
0x180041dda  mov     ebx, eax
0x180041ddc  test    ebx, ebx
0x180041dde  js      short loc_180041E4D
0x180041de0  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180041de4  mov     rsi, rcx
0x180041de7  lea     r8, [rbp+arg_18]
0x180041deb  lea     rdx, [rbp+arg_10]
0x180041def  call    LUAIsElevatedToken
0x180041df4  mov     ebx, eax
0x180041df6  test    eax, eax
0x180041df8  js      short loc_180041E39
0x180041dfa  cmp     [rbp+arg_10], 0
0x180041dfe  jz      short loc_180041E05
0x180041e00  and     dword ptr [rdi], 0
0x180041e03  jmp     short loc_180041E11
0x180041e05  mov     eax, [rbp+arg_18]
0x180041e08  neg     eax
0x180041e0a  sbb     ecx, ecx
0x180041e0c  add     ecx, 2
0x180041e0f  mov     [rdi], ecx
0x180041e11  mov     rcx, [rbp+TokenHandle]
0x180041e15  lea     rdx, [rbp+var_10]
0x180041e19  call    LUAIsUIAToken
0x180041e1e  mov     ebx, eax
0x180041e20  test    eax, eax
0x180041e22  js      short loc_180041E39
0x180041e24  cmp     [rbp+var_10], 0
0x180041e28  jz      short loc_180041E39
0x180041e2a  mov     ecx, [rdi]
0x180041e2c  lea     eax, [rcx-10h]
0x180041e2f  cmp     eax, 2
0x180041e32  jbe     short loc_180041E37
0x180041e34  add     ecx, 10h
0x180041e37  mov     [rdi], ecx
0x180041e39  test    rsi, rsi
0x180041e3c  jz      short loc_180041E4D
0x180041e3e  mov     rcx, rsi; Handle
0x180041e41  call    cs:__imp_NtClose
0x180041e48  nop     dword ptr [rax+rax+00h]
0x180041e4d  mov     eax, ebx
0x180041e4f  mov     rbx, [rsp+30h+arg_8]
0x180041e54  add     rsp, 30h
0x180041e58  pop     rdi
0x180041e59  pop     rsi
0x180041e5a  pop     rbp
0x180041e5b  retn
```
