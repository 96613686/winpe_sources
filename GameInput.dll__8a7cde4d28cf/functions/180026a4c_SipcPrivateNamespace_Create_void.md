# SipcPrivateNamespace::Create(void)

- ea: `0x180026a4c`
- end: `0x180026cd7`
- name: `?Create@SipcPrivateNamespace@@QEAAJXZ`
- size: `651`
- prototype: `__int64 __fastcall(SipcPrivateNamespace *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180026d6c`
- `0x18002a900`

## callees

- `0x180026a4c`
- `0x180028cec`
- `0x18002958c`
- `0x1800297f8`
- `0x18004c8a5`
- `0x18004c8e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026be6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026c5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026c90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026be6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026c5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026c90`
- `api-ms-win-core-namespace-l1-1-0!CreatePrivateNamespaceW` at `0x180026c21`
- `api-ms-win-core-namespace-l1-1-0!CreatePrivateNamespaceW` at `0x180026c21`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x180026bad`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x180026c77`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x180026ca4`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x180026bad`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x180026c77`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x180026ca4`
- `bcrypt!BCryptGenRandom` at `0x180026af3`
- `bcrypt!BCryptGenRandom` at `0x180026af3`

## pseudocode

```c
__int64 __fastcall SipcPrivateNamespace::Create(SipcPrivateNamespace *this)
{
  int SidFromCurrentProcessToken; // esi
  NTSTATUS v3; // eax
  int v4; // eax
  int v6; // eax
  __int128 v7; // xmm1
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  int v11; // eax
  __int128 v12; // xmm1
  int BoundaryDescriptorAndInitializeName; // ebx
  HANDLE v14; // rbx
  HLOCAL v15; // rdi
  HANDLE v16; // rax
  signed int LastError; // eax
  HANDLE BoundaryDescriptor; // [rsp+30h] [rbp-D0h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-C8h] BYREF
  _SECURITY_ATTRIBUTES PrivateNamespaceAttributes; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v22[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v23; // [rsp+78h] [rbp-88h]
  __int128 v24; // [rsp+88h] [rbp-78h]
  __int128 v25; // [rsp+98h] [rbp-68h]
  int v26; // [rsp+A8h] [rbp-58h]
  _BYTE v27[16]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v28[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v29; // [rsp+D0h] [rbp-30h]
  __int128 v30; // [rsp+E0h] [rbp-20h]
  __int128 v31; // [rsp+F0h] [rbp-10h]
  int v32; // [rsp+100h] [rbp+0h]

  memset_0(v21, 0, 0x50u);
  SidFromCurrentProcessToken = anonymous_namespace_::GetSidFromCurrentProcessToken(TokenAppContainerSid, (__int64)v22);
  if ( SidFromCurrentProcessToken < 0 )
    return (unsigned int)SidFromCurrentProcessToken;
  memset_0(v27, 0, 0x58u);
  SidFromCurrentProcessToken = anonymous_namespace_::GetSidFromCurrentProcessToken(TokenUser, (__int64)v28);
  if ( SidFromCurrentProcessToken < 0 )
    return (unsigned int)SidFromCurrentProcessToken;
  v3 = BCryptGenRandom(0, (PUCHAR)this + 84, 0x10u, 2u);
  if ( v3 < 0 )
  {
    v4 = v3 | 0x10000000;
    SidFromCurrentProcessToken = -2147418113;
    if ( v4 < 0 )
      return (unsigned int)v4;
    return (unsigned int)SidFromCurrentProcessToken;
  }
  v6 = v26;
  v7 = v23;
  BoundaryDescriptor = 0;
  *(_OWORD *)((char *)this + 100) = *(_OWORD *)v22;
  v8 = v24;
  *(_OWORD *)((char *)this + 116) = v7;
  v9 = v25;
  *(_OWORD *)((char *)this + 132) = v8;
  *(_OWORD *)((char *)this + 168) = *(_OWORD *)v28;
  v10 = v30;
  *(_OWORD *)((char *)this + 148) = v9;
  *((_DWORD *)this + 41) = v6;
  v11 = v32;
  *(_OWORD *)((char *)this + 184) = v29;
  v12 = v31;
  *(_OWORD *)((char *)this + 200) = v10;
  *(_OWORD *)((char *)this + 216) = v12;
  *((_DWORD *)this + 58) = v11;
  BoundaryDescriptorAndInitializeName = SipcPrivateNamespace::GetBoundaryDescriptorAndInitializeName(
                                          this,
                                          &BoundaryDescriptor);
  if ( BoundaryDescriptorAndInitializeName < 0 )
    goto LABEL_8;
  hMem = 0;
  BoundaryDescriptorAndInitializeName = SipcPrivateNamespace::GetSecurityDescriptor(this, &hMem);
  if ( BoundaryDescriptorAndInitializeName < 0 )
  {
    if ( hMem )
      LocalFree(hMem);
LABEL_8:
    if ( BoundaryDescriptor )
      DeleteBoundaryDescriptor(BoundaryDescriptor);
    return (unsigned int)BoundaryDescriptorAndInitializeName;
  }
  v14 = BoundaryDescriptor;
  v15 = hMem;
  *(_QWORD *)&PrivateNamespaceAttributes.nLength = 24;
  PrivateNamespaceAttributes.lpSecurityDescriptor = hMem;
  *(_QWORD *)&PrivateNamespaceAttributes.bInheritHandle = 0;
  v16 = CreatePrivateNamespaceW(&PrivateNamespaceAttributes, BoundaryDescriptor, (LPCWSTR)this + 4);
  *(_QWORD *)this = v16;
  if ( !v16 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    SidFromCurrentProcessToken = -2147418113;
    if ( LastError < 0 )
      SidFromCurrentProcessToken = LastError;
    if ( v15 )
      LocalFree(v15);
    if ( v14 )
      DeleteBoundaryDescriptor(v14);
    return (unsigned int)SidFromCurrentProcessToken;
  }
  if ( v15 )
    LocalFree(v15);
  if ( v14 )
    DeleteBoundaryDescriptor(v14);
  return 0;
}

```

## disassembly

```asm
0x180026a4c  mov     [rsp-8+arg_8], rbx
0x180026a51  mov     [rsp-8+arg_10], rsi
0x180026a56  push    rbp
0x180026a57  push    rdi
0x180026a58  push    r14
0x180026a5a  lea     rbp, [rsp-20h]
0x180026a5f  sub     rsp, 120h
0x180026a66  mov     rax, cs:__security_cookie
0x180026a6d  xor     rax, rsp
0x180026a70  mov     [rbp+30h+var_20], rax
0x180026a74  mov     r14, rcx
0x180026a77  mov     ebx, 50h ; 'P'
0x180026a7c  mov     r8d, ebx; Size
0x180026a7f  lea     rcx, [rsp+130h+var_D0]; void *
0x180026a84  xor     edx, edx; Val
0x180026a86  call    memset_0
0x180026a8b  lea     rax, [rsp+130h+var_C8]
0x180026a90  mov     r8d, ebx
0x180026a93  lea     r9, [rsp+130h+var_D0]
0x180026a98  mov     [rsp+130h+var_110], rax; __int64
0x180026a9d  lea     rdx, [rsp+130h+var_D0]
0x180026aa2  lea     ecx, [rbx-31h]; TokenInformationClass
0x180026aa5  call    _anonymous_namespace___GetSidFromCurrentProcessToken
0x180026aaa  mov     esi, eax
0x180026aac  test    eax, eax
0x180026aae  js      short loc_180026B10
0x180026ab0  mov     ebx, 58h ; 'X'
0x180026ab5  lea     rcx, [rbp+30h+var_80]; void *
0x180026ab9  mov     r8d, ebx; Size
0x180026abc  xor     edx, edx; Val
0x180026abe  call    memset_0
0x180026ac3  lea     rax, [rbp+30h+var_70]
0x180026ac7  mov     r8d, ebx
0x180026aca  lea     r9, [rbp+30h+var_80]
0x180026ace  mov     [rsp+130h+var_110], rax; __int64
0x180026ad3  lea     rdx, [rbp+30h+var_80]
0x180026ad7  lea     ecx, [rbx-57h]; TokenInformationClass
0x180026ada  call    _anonymous_namespace___GetSidFromCurrentProcessToken
0x180026adf  mov     esi, eax
0x180026ae1  test    eax, eax
0x180026ae3  js      short loc_180026B10
0x180026ae5  lea     r9d, [rbx-56h]; dwFlags
0x180026ae9  xor     ecx, ecx; hAlgorithm
0x180026aeb  lea     r8d, [rbx-48h]; cbBuffer
0x180026aef  lea     rdx, [r14+54h]; pbBuffer
0x180026af3  call    cs:__imp_BCryptGenRandom
0x180026afa  nop     dword ptr [rax+rax+00h]
0x180026aff  test    eax, eax
0x180026b01  jns     short loc_180026B17
0x180026b03  or      eax, 10000000h
0x180026b08  mov     esi, 8000FFFFh
0x180026b0d  cmovl   esi, eax
0x180026b10  mov     eax, esi
0x180026b12  jmp     loc_180026CB2
0x180026b17  movups  xmm0, xmmword ptr [rsp+130h+var_C8]
0x180026b1c  mov     eax, [rbp+30h+var_88]
0x180026b1f  lea     rdx, [rsp+130h+BoundaryDescriptor]; void **
0x180026b24  movups  xmm1, [rsp+130h+var_B8]
0x180026b29  mov     rcx, r14; this
0x180026b2c  mov     [rsp+130h+BoundaryDescriptor], 0
0x180026b35  movups  xmmword ptr [r14+64h], xmm0
0x180026b3a  movups  xmm0, [rbp+30h+var_A8]
0x180026b3e  movups  xmmword ptr [r14+74h], xmm1
0x180026b43  movups  xmm1, [rbp+30h+var_98]
0x180026b47  movups  xmmword ptr [r14+84h], xmm0
0x180026b4f  movaps  xmm0, xmmword ptr [rbp+30h+var_70]
0x180026b53  movups  xmmword ptr [r14+0A8h], xmm0
0x180026b5b  movaps  xmm0, [rbp+30h+var_50]
0x180026b5f  movups  xmmword ptr [r14+94h], xmm1
0x180026b67  mov     [r14+0A4h], eax
0x180026b6e  movaps  xmm1, [rbp+30h+var_60]
0x180026b72  mov     eax, [rbp+30h+var_30]
0x180026b75  movups  xmmword ptr [r14+0B8h], xmm1
0x180026b7d  movaps  xmm1, [rbp+30h+var_40]
0x180026b81  movups  xmmword ptr [r14+0C8h], xmm0
0x180026b89  movups  xmmword ptr [r14+0D8h], xmm1
0x180026b91  mov     [r14+0E8h], eax
0x180026b98  call    ?GetBoundaryDescriptorAndInitializeName@SipcPrivateNamespace@@AEAAJPEAPEAX@Z; SipcPrivateNamespace::GetBoundaryDescriptorAndInitializeName(void * *)
0x180026b9d  mov     ebx, eax
0x180026b9f  test    eax, eax
0x180026ba1  jns     short loc_180026BC0
0x180026ba3  mov     rcx, [rsp+130h+BoundaryDescriptor]; BoundaryDescriptor
0x180026ba8  test    rcx, rcx
0x180026bab  jz      short loc_180026BB9
0x180026bad  call    cs:__imp_DeleteBoundaryDescriptor
0x180026bb4  nop     dword ptr [rax+rax+00h]
0x180026bb9  mov     eax, ebx
0x180026bbb  jmp     loc_180026CB2
0x180026bc0  lea     rdx, [rsp+130h+hMem]; void **
0x180026bc5  mov     [rsp+130h+hMem], 0
0x180026bce  mov     rcx, r14; this
0x180026bd1  call    ?GetSecurityDescriptor@SipcPrivateNamespace@@AEAAJPEAPEAX@Z; SipcPrivateNamespace::GetSecurityDescriptor(void * *)
0x180026bd6  mov     ebx, eax
0x180026bd8  test    eax, eax
0x180026bda  jns     short loc_180026BF4
0x180026bdc  mov     rcx, [rsp+130h+hMem]; hMem
0x180026be1  test    rcx, rcx
0x180026be4  jz      short loc_180026BA3
0x180026be6  call    cs:__imp_LocalFree
0x180026bed  nop     dword ptr [rax+rax+00h]
0x180026bf2  jmp     short loc_180026BA3
0x180026bf4  mov     rbx, [rsp+130h+BoundaryDescriptor]
0x180026bf9  lea     r8, [r14+8]; lpAliasPrefix
0x180026bfd  mov     rdi, [rsp+130h+hMem]
0x180026c02  lea     rcx, [rsp+130h+PrivateNamespaceAttributes]; lpPrivateNamespaceAttributes
0x180026c07  mov     rdx, rbx; lpBoundaryDescriptor
0x180026c0a  mov     qword ptr [rsp+130h+PrivateNamespaceAttributes.nLength], 18h
0x180026c13  mov     [rsp+130h+PrivateNamespaceAttributes.lpSecurityDescriptor], rdi
0x180026c18  mov     qword ptr [rsp+130h+PrivateNamespaceAttributes.bInheritHandle], 0
0x180026c21  call    cs:__imp_CreatePrivateNamespaceW
0x180026c28  nop     dword ptr [rax+rax+00h]
0x180026c2d  mov     [r14], rax
0x180026c30  test    rax, rax
0x180026c33  jnz     short loc_180026C88
0x180026c35  call    cs:__imp_GetLastError
0x180026c3c  nop     dword ptr [rax+rax+00h]
0x180026c41  test    eax, eax
0x180026c43  jle     short loc_180026C4D
0x180026c45  movzx   eax, ax
0x180026c48  or      eax, 80070000h
0x180026c4d  test    eax, eax
0x180026c4f  mov     esi, 8000FFFFh
0x180026c54  cmovs   esi, eax
0x180026c57  test    rdi, rdi
0x180026c5a  jz      short loc_180026C6B
0x180026c5c  mov     rcx, rdi; hMem
0x180026c5f  call    cs:__imp_LocalFree
0x180026c66  nop     dword ptr [rax+rax+00h]
0x180026c6b  test    rbx, rbx
0x180026c6e  jz      loc_180026B10
0x180026c74  mov     rcx, rbx; BoundaryDescriptor
0x180026c77  call    cs:__imp_DeleteBoundaryDescriptor
0x180026c7e  nop     dword ptr [rax+rax+00h]
0x180026c83  jmp     loc_180026B10
0x180026c88  test    rdi, rdi
0x180026c8b  jz      short loc_180026C9C
0x180026c8d  mov     rcx, rdi; hMem
0x180026c90  call    cs:__imp_LocalFree
0x180026c97  nop     dword ptr [rax+rax+00h]
0x180026c9c  test    rbx, rbx
0x180026c9f  jz      short loc_180026CB0
0x180026ca1  mov     rcx, rbx; BoundaryDescriptor
0x180026ca4  call    cs:__imp_DeleteBoundaryDescriptor
0x180026cab  nop     dword ptr [rax+rax+00h]
0x180026cb0  xor     eax, eax
0x180026cb2  mov     rcx, [rbp+30h+var_20]
0x180026cb6  xor     rcx, rsp; StackCookie
0x180026cb9  call    __security_check_cookie
0x180026cbe  lea     r11, [rsp+130h+var_10]
0x180026cc6  mov     rbx, [r11+28h]
0x180026cca  mov     rsi, [r11+30h]
0x180026cce  mov     rsp, r11
0x180026cd1  pop     r14
0x180026cd3  pop     rdi
0x180026cd4  pop     rbp
0x180026cd5  retn
```
