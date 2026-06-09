# SipcPrivateNamespace::GetBoundaryDescriptorAndInitializeName(void * *)

- ea: `0x180028cec`
- end: `0x180028e46`
- name: `?GetBoundaryDescriptorAndInitializeName@SipcPrivateNamespace@@AEAAJPEAPEAX@Z`
- size: `346`
- prototype: `__int64 __fastcall(SipcPrivateNamespace *__hidden this, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180026a4c`
- `0x18002a07c`

## callees

- `0x180028cec`
- `0x18004c8e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028d8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028d8c`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180028df4`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180028df4`
- `api-ms-win-core-namespace-l1-1-0!AddSIDToBoundaryDescriptor` at `0x180028dde`
- `api-ms-win-core-namespace-l1-1-0!AddSIDToBoundaryDescriptor` at `0x180028e0c`
- `api-ms-win-core-namespace-l1-1-0!AddSIDToBoundaryDescriptor` at `0x180028dde`
- `api-ms-win-core-namespace-l1-1-0!AddSIDToBoundaryDescriptor` at `0x180028e0c`
- `api-ms-win-core-namespace-l1-1-0!CreateBoundaryDescriptorW` at `0x180028d77`
- `api-ms-win-core-namespace-l1-1-0!CreateBoundaryDescriptorW` at `0x180028d77`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x180028db7`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x180028db7`

## pseudocode

```c
__int64 __fastcall SipcPrivateNamespace::GetBoundaryDescriptorAndInitializeName(SipcPrivateNamespace *this, void **a2)
{
  char *v3; // rcx
  unsigned __int64 v5; // r9
  _WORD *v6; // r8
  unsigned int v7; // edx
  signed int LastError; // eax
  unsigned int v9; // ebx
  HANDLE BoundaryDescriptor; // [rsp+20h] [rbp-20h] BYREF
  int RequiredSid; // [rsp+28h] [rbp-18h] BYREF
  __int64 v13; // [rsp+2Ch] [rbp-14h]

  *a2 = 0;
  v3 = (char *)this + 8;
  v5 = 0;
  v6 = (_WORD *)((char *)this + 18);
  *(_QWORD *)v3 = SipcPrivateNamespace::NamespacePrefix;
  *((_DWORD *)v3 + 2) = 95;
  do
  {
    v7 = *((unsigned __int8 *)this + v5++ + 84);
    *v6 = a0123456789abcd_0[(unsigned __int64)v7 >> 4];
    v6 += 2;
    *(v6 - 1) = a0123456789abcd_0[v7 & 0xF];
  }
  while ( v5 < 0x10 );
  *v6 = 0;
  BoundaryDescriptor = CreateBoundaryDescriptorW((LPCWSTR)v3, 0);
  if ( BoundaryDescriptor
    && (RequiredSid = 257, v13 = 0x1000000, AddSIDToBoundaryDescriptor(&BoundaryDescriptor, &RequiredSid))
    && (IsWellKnownSid((char *)this + 100, WinNullSid)
     || AddSIDToBoundaryDescriptor(&BoundaryDescriptor, (char *)this + 100)) )
  {
    *a2 = BoundaryDescriptor;
    return 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = -2147418113;
    if ( LastError < 0 )
      v9 = LastError;
    if ( BoundaryDescriptor )
      DeleteBoundaryDescriptor(BoundaryDescriptor);
    return v9;
  }
}

```

## disassembly

```asm
0x180028cec  mov     [rsp-8+arg_10], rbx
0x180028cf1  mov     [rsp-8+arg_18], rdi
0x180028cf6  push    rbp
0x180028cf7  mov     rbp, rsp
0x180028cfa  sub     rsp, 40h
0x180028cfe  mov     rax, cs:__security_cookie
0x180028d05  xor     rax, rsp
0x180028d08  mov     [rbp+var_8], rax
0x180028d0c  mov     qword ptr [rdx], 0
0x180028d13  lea     r10, a0123456789abcd_0; "0123456789ABCDEF"
0x180028d1a  movsd   xmm0, cs:?NamespacePrefix@SipcPrivateNamespace@@0QBGB; ushort const near * const SipcPrivateNamespace::NamespacePrefix
0x180028d22  mov     rbx, rcx
0x180028d25  add     rcx, 8; Name
0x180028d29  mov     rdi, rdx
0x180028d2c  xor     r9d, r9d
0x180028d2f  lea     r8, [rbx+12h]
0x180028d33  movsd   qword ptr [rcx], xmm0
0x180028d37  mov     eax, cs:dword_1800551F8
0x180028d3d  mov     [rcx+8], eax
0x180028d40  movzx   edx, byte ptr [rbx+r9+54h]
0x180028d46  inc     r9
0x180028d49  mov     eax, edx
0x180028d4b  and     edx, 0Fh
0x180028d4e  shr     rax, 4
0x180028d52  movzx   eax, word ptr [r10+rax*2]
0x180028d57  mov     [r8], ax
0x180028d5b  lea     r8, [r8+4]
0x180028d5f  movzx   eax, word ptr [r10+rdx*2]
0x180028d64  mov     [r8-2], ax
0x180028d69  cmp     r9, 10h
0x180028d6d  jb      short loc_180028D40
0x180028d6f  xor     eax, eax
0x180028d71  xor     edx, edx; Flags
0x180028d73  mov     [r8], ax
0x180028d77  call    cs:__imp_CreateBoundaryDescriptorW
0x180028d7e  nop     dword ptr [rax+rax+00h]
0x180028d83  mov     [rbp+BoundaryDescriptor], rax
0x180028d87  test    rax, rax
0x180028d8a  jnz     short loc_180028DC7
0x180028d8c  call    cs:__imp_GetLastError
0x180028d93  nop     dword ptr [rax+rax+00h]
0x180028d98  test    eax, eax
0x180028d9a  jle     short loc_180028DA4
0x180028d9c  movzx   eax, ax
0x180028d9f  or      eax, 80070000h
0x180028da4  mov     rcx, [rbp+BoundaryDescriptor]; BoundaryDescriptor
0x180028da8  test    eax, eax
0x180028daa  mov     ebx, 8000FFFFh
0x180028daf  cmovs   ebx, eax
0x180028db2  test    rcx, rcx
0x180028db5  jz      short loc_180028DC3
0x180028db7  call    cs:__imp_DeleteBoundaryDescriptor
0x180028dbe  nop     dword ptr [rax+rax+00h]
0x180028dc3  mov     eax, ebx
0x180028dc5  jmp     short loc_180028E29
0x180028dc7  lea     rdx, [rbp+RequiredSid]; RequiredSid
0x180028dcb  mov     [rbp+RequiredSid], 101h
0x180028dd2  lea     rcx, [rbp+BoundaryDescriptor]; BoundaryDescriptor
0x180028dd6  mov     [rbp+var_14], 1000000h
0x180028dde  call    cs:__imp_AddSIDToBoundaryDescriptor
0x180028de5  nop     dword ptr [rax+rax+00h]
0x180028dea  test    eax, eax
0x180028dec  jz      short loc_180028D8C
0x180028dee  xor     edx, edx; WellKnownSidType
0x180028df0  lea     rcx, [rbx+64h]; pSid
0x180028df4  call    cs:__imp_IsWellKnownSid
0x180028dfb  nop     dword ptr [rax+rax+00h]
0x180028e00  test    eax, eax
0x180028e02  jnz     short loc_180028E20
0x180028e04  lea     rdx, [rbx+64h]; RequiredSid
0x180028e08  lea     rcx, [rbp+BoundaryDescriptor]; BoundaryDescriptor
0x180028e0c  call    cs:__imp_AddSIDToBoundaryDescriptor
0x180028e13  nop     dword ptr [rax+rax+00h]
0x180028e18  test    eax, eax
0x180028e1a  jz      loc_180028D8C
0x180028e20  mov     rax, [rbp+BoundaryDescriptor]
0x180028e24  mov     [rdi], rax
0x180028e27  xor     eax, eax
0x180028e29  mov     rcx, [rbp+var_8]
0x180028e2d  xor     rcx, rsp; StackCookie
0x180028e30  call    __security_check_cookie
0x180028e35  mov     rbx, [rsp+40h+arg_10]
0x180028e3a  mov     rdi, [rsp+40h+arg_18]
0x180028e3f  add     rsp, 40h
0x180028e43  pop     rbp
0x180028e44  retn
```
