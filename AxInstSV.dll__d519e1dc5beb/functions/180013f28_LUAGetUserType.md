# LUAGetUserType

- ea: `0x180013f28`
- end: `0x18001401d`
- name: `LUAGetUserType`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180005ee0`

## callees

- `0x180013f28`
- `0x180014024`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x180013f75`
- `ntdll!NtOpenProcessToken` at `0x180013f75`
- `ntdll!NtClose` at `0x180014008`
- `ntdll!NtClose` at `0x180014008`
- `ntdll!NtQueryInformationToken` at `0x180013fdf`
- `ntdll!NtQueryInformationToken` at `0x180013fdf`
- `ntdll!NtOpenThreadToken` at `0x180013f5c`
- `ntdll!NtOpenThreadToken` at `0x180013f5c`

## pseudocode

```c
__int64 __fastcall LUAGetUserType(void *a1, int *a2)
{
  void *v2; // rsi
  NTSTATUS v4; // ebx
  int v5; // ecx
  void *TokenHandle; // [rsp+50h] [rbp+20h] BYREF
  int TokenInformation; // [rsp+60h] [rbp+30h] BYREF
  ULONG ReturnLength; // [rsp+68h] [rbp+38h] BYREF

  TokenHandle = a1;
  v2 = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  if ( a1 )
  {
LABEL_6:
    v4 = LUAIsElevatedToken(a1);
    if ( v4 >= 0 )
    {
      *a2 = TokenInformation ? 0 : 2 - (ReturnLength != 0);
      TokenInformation = 0;
      ReturnLength = 4;
      v4 = NtQueryInformationToken(TokenHandle, TokenUIAccess, &TokenInformation, 4u, &ReturnLength);
      if ( v4 >= 0 )
      {
        if ( TokenInformation )
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
0x180013f28  mov     [rsp-18h+arg_8], rbx
0x180013f2d  mov     [rsp-18h+TokenHandle], rcx
0x180013f32  push    rbp
0x180013f33  push    rsi
0x180013f34  push    rdi
0x180013f35  mov     rbp, rsp
0x180013f38  sub     rsp, 30h
0x180013f3c  xor     esi, esi
0x180013f3e  mov     rdi, rdx
0x180013f41  mov     [rbp+TokenInformation], esi
0x180013f44  mov     [rbp+arg_18], esi
0x180013f47  test    rcx, rcx
0x180013f4a  jnz     short loc_180013F8C
0x180013f4c  lea     esi, [rcx+8]
0x180013f4f  xor     r8d, r8d; OpenAsSelf
0x180013f52  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180013f56  mov     edx, esi; DesiredAccess
0x180013f58  lea     rcx, [r8-2]; ThreadHandle
0x180013f5c  call    cs:__imp_NtOpenThreadToken
0x180013f62  mov     ebx, eax
0x180013f64  cmp     eax, 0C000007Ch
0x180013f69  jnz     short loc_180013F7D
0x180013f6b  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180013f6f  mov     edx, esi; DesiredAccess
0x180013f71  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180013f75  call    cs:__imp_NtOpenProcessToken
0x180013f7b  mov     ebx, eax
0x180013f7d  test    ebx, ebx
0x180013f7f  js      loc_18001400E
0x180013f85  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180013f89  mov     rsi, rcx
0x180013f8c  lea     r8, [rbp+arg_18]
0x180013f90  lea     rdx, [rbp+TokenInformation]
0x180013f94  call    LUAIsElevatedToken
0x180013f99  mov     ebx, eax
0x180013f9b  test    eax, eax
0x180013f9d  js      short loc_180014000
0x180013f9f  cmp     [rbp+TokenInformation], 0
0x180013fa3  jz      short loc_180013FAD
0x180013fa5  mov     dword ptr [rdi], 0
0x180013fab  jmp     short loc_180013FB9
0x180013fad  mov     eax, [rbp+arg_18]
0x180013fb0  neg     eax
0x180013fb2  sbb     ecx, ecx
0x180013fb4  add     ecx, 2
0x180013fb7  mov     [rdi], ecx
0x180013fb9  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180013fbd  lea     rax, [rbp+arg_18]
0x180013fc1  mov     r9d, 4; TokenInformationLength
0x180013fc7  mov     [rbp+TokenInformation], 0
0x180013fce  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180013fd2  mov     [rbp+arg_18], r9d
0x180013fd6  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180013fdb  lea     edx, [r9+16h]; TokenInformationClass
0x180013fdf  call    cs:__imp_NtQueryInformationToken
0x180013fe5  mov     ebx, eax
0x180013fe7  test    eax, eax
0x180013fe9  js      short loc_180014000
0x180013feb  cmp     [rbp+TokenInformation], 0
0x180013fef  jz      short loc_180014000
0x180013ff1  mov     ecx, [rdi]
0x180013ff3  lea     eax, [rcx-10h]
0x180013ff6  cmp     eax, 2
0x180013ff9  jbe     short loc_180013FFE
0x180013ffb  add     ecx, 10h
0x180013ffe  mov     [rdi], ecx
0x180014000  test    rsi, rsi
0x180014003  jz      short loc_18001400E
0x180014005  mov     rcx, rsi; Handle
0x180014008  call    cs:__imp_NtClose
0x18001400e  mov     eax, ebx
0x180014010  mov     rbx, [rsp+30h+arg_8]
0x180014015  add     rsp, 30h
0x180014019  pop     rdi
0x18001401a  pop     rsi
0x18001401b  pop     rbp
0x18001401c  retn
```
