# Smb2ForceUpdateAndQueryAttributesOnClose

- ea: `0x140085d90`
- end: `0x140085ee8`
- name: `Smb2ForceUpdateAndQueryAttributesOnClose`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400874c0`

## callees

- `0x1400152a0`
- `0x140038490`
- `0x140085d90`

## import_xrefs

- `ntoskrnl!NtQueryInformationFile` at `0x140085e5d`
- `ntoskrnl!NtQueryInformationFile` at `0x140085e5d`
- `ntoskrnl!PsAssignImpersonationToken` at `0x140085e82`
- `ntoskrnl!PsAssignImpersonationToken` at `0x140085e82`
- `ntoskrnl!NtSetInformationFile` at `0x140085e29`
- `ntoskrnl!NtSetInformationFile` at `0x140085e29`

## pseudocode

```c
__int64 __fastcall Smb2ForceUpdateAndQueryAttributesOnClose(__int64 a1)
{
  _QWORD *v1; // rbx
  SECURITY_STATUS v2; // esi
  int v3; // edx
  NTSTATUS v4; // edi
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-48h] BYREF
  __int128 FileInformation; // [rsp+40h] [rbp-38h] BYREF
  __int128 v8; // [rsp+50h] [rbp-28h]
  __int64 v9; // [rsp+60h] [rbp-18h]

  v1 = *(_QWORD **)(a1 + 560);
  FileInformation = 0;
  v8 = 0;
  v9 = 0;
  IoStatusBlock = 0;
  if ( !v1[10] )
    return 3221225768LL;
  v2 = Smb2ImpersonateWorkItem((__int64)v1);
  v3 = *(_DWORD *)(v1[9] + 184LL);
  if ( (v3 & 2) == 0
    && (v3 & 0x100) == 0
    && (v3 & 0x10) == 0
    && (v3 & 4) == 0
    && (v3 & 0x40000) == 0
    && (v3 & 0x80000) == 0
    || (FileInformation = 0,
        v8 = 0,
        v9 = 0,
        v4 = NtSetInformationFile(
               *(HANDLE *)(v1[10] + 88LL),
               &IoStatusBlock,
               &FileInformation,
               0x28u,
               FileBasicInformation),
        v4 >= 0) )
  {
    v4 = NtQueryInformationFile(*(HANDLE *)(v1[10] + 88LL), &IoStatusBlock, v1 + 25, 0x38u, FileNetworkOpenInformation);
  }
  if ( v2 >= 0 )
    PsAssignImpersonationToken(KeGetCurrentThread(), 0);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140085d90  mov     r11, rsp
0x140085d93  push    rbx
0x140085d94  sub     rsp, 70h
0x140085d98  mov     rax, cs:__security_cookie
0x140085d9f  xor     rax, rsp
0x140085da2  mov     [rsp+78h+var_10], rax
0x140085da7  mov     rbx, [rcx+230h]
0x140085dae  xorps   xmm0, xmm0
0x140085db1  xor     eax, eax
0x140085db3  movups  [rsp+78h+FileInformation], xmm0
0x140085db8  movups  [rsp+78h+var_28], xmm0
0x140085dbd  mov     [r11-18h], rax
0x140085dc1  movups  xmmword ptr [rsp+78h+IoStatusBlock], xmm0
0x140085dc6  cmp     [rbx+50h], rax
0x140085dca  jz      loc_140085EE1
0x140085dd0  mov     [r11+10h], rsi
0x140085dd4  mov     rcx, rbx
0x140085dd7  mov     [r11+18h], rdi
0x140085ddb  call    Smb2ImpersonateWorkItem
0x140085de0  mov     rcx, [rbx+48h]
0x140085de4  mov     esi, eax
0x140085de6  mov     edx, [rcx+0B8h]
0x140085dec  test    dl, 2
0x140085def  jz      loc_140085EAC
0x140085df5  xorps   xmm0, xmm0
0x140085df8  mov     [rsp+78h+FileInformationClass], 4; FileInformationClass
0x140085e00  movups  [rsp+78h+FileInformation], xmm0
0x140085e05  xor     eax, eax
0x140085e07  mov     r9d, 28h ; '('; Length
0x140085e0d  movups  [rsp+78h+var_28], xmm0
0x140085e12  mov     [rsp+78h+var_18], rax
0x140085e17  lea     r8, [rsp+78h+FileInformation]; FileInformation
0x140085e1c  mov     rcx, [rbx+50h]
0x140085e20  lea     rdx, [rsp+78h+IoStatusBlock]; IoStatusBlock
0x140085e25  mov     rcx, [rcx+58h]; FileHandle
0x140085e29  call    cs:__imp_NtSetInformationFile
0x140085e30  nop     dword ptr [rax+rax+00h]
0x140085e35  mov     edi, eax
0x140085e37  test    eax, eax
0x140085e39  js      short loc_140085E6B
0x140085e3b  mov     rcx, [rbx+50h]
0x140085e3f  lea     r8, [rbx+0C8h]; FileInformation
0x140085e46  mov     r9d, 38h ; '8'; Length
0x140085e4c  mov     [rsp+78h+FileInformationClass], 22h ; '"'; FileInformationClass
0x140085e54  lea     rdx, [rsp+78h+IoStatusBlock]; IoStatusBlock
0x140085e59  mov     rcx, [rcx+58h]; FileHandle
0x140085e5d  call    cs:__imp_NtQueryInformationFile
0x140085e64  nop     dword ptr [rax+rax+00h]
0x140085e69  mov     edi, eax
0x140085e6b  test    esi, esi
0x140085e6d  mov     rsi, [rsp+78h+arg_8]
0x140085e75  js      short loc_140085E8E
0x140085e77  mov     rcx, gs:188h; Thread
0x140085e80  xor     edx, edx; Token
0x140085e82  call    cs:__imp_PsAssignImpersonationToken
0x140085e89  nop     dword ptr [rax+rax+00h]
0x140085e8e  mov     eax, edi
0x140085e90  mov     rdi, [rsp+78h+arg_10]
0x140085e98  mov     rcx, [rsp+78h+var_10]
0x140085e9d  xor     rcx, rsp; StackCookie
0x140085ea0  call    __security_check_cookie
0x140085ea5  add     rsp, 70h
0x140085ea9  pop     rbx
0x140085eaa  retn
0x140085eac  bt      edx, 8
0x140085eb0  jb      loc_140085DF5
0x140085eb6  test    dl, 10h
0x140085eb9  jnz     loc_140085DF5
0x140085ebf  test    dl, 4
0x140085ec2  jnz     loc_140085DF5
0x140085ec8  bt      edx, 12h
0x140085ecc  jb      loc_140085DF5
0x140085ed2  bt      edx, 13h
0x140085ed6  jnb     loc_140085E3B
0x140085edc  jmp     loc_140085DF5
0x140085ee1  mov     eax, 0C0000128h
0x140085ee6  jmp     short loc_140085E98
```
