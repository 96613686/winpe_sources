# WxGetCacheServerEndpointName(CWxString *,int)

- ea: `0x18001e168`
- end: `0x18001e400`
- name: `?WxGetCacheServerEndpointName@@YAJPEAVCWxString@@H@Z`
- size: `664`
- prototype: `__int64 __fastcall(struct CWxString *this, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001de88`
- `0x1800df1c8`

## callees

- `0x18001e168`
- `0x18001eaec`
- `0x1800701d0`
- `0x180074890`
- `0x18012ce48`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801e1790`
- `0x1801e1b00`
- `0x1801e4988`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001e1ee`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001e1ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001e1dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001e1dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e22e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e22e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e24e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e24e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001e289`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001e289`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001e29f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001e29f`

## string_xrefs

- `0x18001e2cb`: `webcache_{7329ea82-0845-4e4c-bd18-02b67ac065cc}_`
- `0x18001e3db`: `webcache_{031b98cf-4a69-4c31-ab42-fd9b3c199407}_`

## pseudocode

```c
__int64 __fastcall WxGetCacheServerEndpointName(struct CWxString *this, int a2)
{
  HANDLE CurrentProcess; // rax
  __int64 v5; // rcx
  int LastError; // eax
  signed int v7; // ebx
  __int64 v9; // rcx
  __int64 v10; // rcx
  unsigned __int16 *v11; // rdx
  __int64 v12; // r8
  _WORD *v13; // rcx
  int v14; // eax
  int v15; // eax
  unsigned int v16; // [rsp+30h] [rbp-69h] BYREF
  int v17; // [rsp+34h] [rbp-65h]
  unsigned __int16 *v18[2]; // [rsp+38h] [rbp-61h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-51h] BYREF
  DWORD ReturnLength; // [rsp+50h] [rbp-49h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-41h] BYREF
  PSID TokenInformation[12]; // [rsp+60h] [rbp-39h] BYREF

  v17 = 0;
  TokenHandle = 0;
  memset_0(TokenInformation, 0, 0x58u);
  ReturnLength = 0;
  hMem = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x40) != 0 )
    WPP_SF_qD(1038, 10, &WPP_5405e779efad323d0e60cfee69e77ab2_Traceguids, this, a2);
  if ( this )
    CWxString::Empty(this);
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
  {
    LastError = WxGetLastError(v5);
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    v17 = 30;
    if ( v7 >= 0 )
      v7 = -2147418113;
    goto LABEL_10;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x58u, &ReturnLength) )
  {
    v14 = WxGetLastError(v9);
    v7 = v14;
    if ( v14 > 0 )
      v7 = (unsigned __int16)v14 | 0x80070000;
    v17 = 31;
    if ( v7 >= 0 )
      v7 = -2147418113;
LABEL_10:
    if ( v7 < 0 )
      goto LABEL_11;
    goto LABEL_27;
  }
  if ( !ConvertSidToStringSidW(TokenInformation[0], (LPWSTR *)&hMem) )
  {
    v15 = WxGetLastError(v10);
    v7 = v15;
    if ( v15 > 0 )
      v7 = (unsigned __int16)v15 | 0x80070000;
    v17 = 33;
    if ( v7 >= 0 )
      v7 = -2147418113;
    goto LABEL_10;
  }
  if ( !a2 )
  {
    v7 = CWxString::Set(this, L"webcache_{031b98cf-4a69-4c31-ab42-fd9b3c199407}_", (const unsigned __int16 *)hMem);
    if ( v7 < 0 )
      v17 = 41;
    goto LABEL_10;
  }
  v11 = (unsigned __int16 *)hMem;
  if ( *((_DWORD *)this + 2) )
  {
    v13 = *(_WORD **)this;
    *((_DWORD *)this + 2) = 0;
    *v13 = 0;
  }
  if ( !v11 )
  {
    v7 = -2147024809;
LABEL_40:
    v17 = 37;
    goto LABEL_10;
  }
  v16 = 48;
  v18[0] = L"webcache_{7329ea82-0845-4e4c-bd18-02b67ac065cc}_";
  v12 = -1;
  do
    ++v12;
  while ( v11[v12] );
  v17 = v12;
  v18[1] = v11;
  v7 = CWxString::_Append(this, 2u, (int)v12 + 48, &v16, (const unsigned __int16 **const)v18);
  if ( v7 < 0 )
    goto LABEL_40;
LABEL_27:
  if ( (BYTE1(xmmword_180266B60) & 0x40) != 0 )
    WPP_SF_S(1038, 11, &WPP_5405e779efad323d0e60cfee69e77ab2_Traceguids, *(_QWORD *)this);
LABEL_11:
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( (BYTE1(xmmword_180266B60) & 0x40) != 0 )
    WPP_SF_d(1038, 12, &WPP_5405e779efad323d0e60cfee69e77ab2_Traceguids, (unsigned int)v7);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001e168  push    rbp
0x18001e16a  push    rbx
0x18001e16b  push    rsi
0x18001e16c  push    rdi
0x18001e16d  lea     rbp, [rsp-3Fh]
0x18001e172  sub     rsp, 0D8h
0x18001e179  mov     rax, cs:__security_cookie
0x18001e180  xor     rax, rsp
0x18001e183  mov     [rbp+57h+var_30], rax
0x18001e187  xor     esi, esi
0x18001e189  mov     ebx, edx
0x18001e18b  mov     rdi, rcx
0x18001e18e  mov     [rbp+57h+var_BC], esi
0x18001e191  xor     edx, edx; Val
0x18001e193  mov     [rbp+57h+TokenHandle], rsi
0x18001e197  lea     rcx, [rbp+57h+TokenInformation]; void *
0x18001e19b  lea     r8d, [rsi+58h]; Size
0x18001e19f  call    memset_0
0x18001e1a4  mov     [rbp+57h+var_A0], esi
0x18001e1a7  mov     [rbp+57h+hMem], rsi
0x18001e1ab  test    byte ptr cs:xmmword_180266B60+1, 40h
0x18001e1b2  jz      short loc_18001E1CF
0x18001e1b4  lea     edx, [rsi+0Ah]
0x18001e1b7  mov     dword ptr [rsp+0F0h+ReturnLength], ebx
0x18001e1bb  mov     ecx, 40Eh
0x18001e1c0  lea     r8, WPP_5405e779efad323d0e60cfee69e77ab2_Traceguids
0x18001e1c7  mov     r9, rdi
0x18001e1ca  call    WPP_SF_qD
0x18001e1cf  test    rdi, rdi
0x18001e1d2  jz      short loc_18001E1DC
0x18001e1d4  mov     rcx, rdi; this
0x18001e1d7  call    ?Empty@CWxString@@QEAAXXZ; CWxString::Empty(void)
0x18001e1dc  call    cs:__imp_GetCurrentProcess
0x18001e1e2  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18001e1e6  mov     edx, 20008h; DesiredAccess
0x18001e1eb  mov     rcx, rax; ProcessHandle
0x18001e1ee  call    cs:__imp_OpenProcessToken
0x18001e1f4  test    eax, eax
0x18001e1f6  jnz     short loc_18001E26E
0x18001e1f8  call    WxGetLastError
0x18001e1fd  mov     ebx, eax
0x18001e1ff  test    eax, eax
0x18001e201  jle     short loc_18001E20C
0x18001e203  movzx   ebx, ax
0x18001e206  or      ebx, 80070000h
0x18001e20c  test    ebx, ebx
0x18001e20e  mov     [rbp+57h+var_BC], 1Eh
0x18001e215  mov     eax, 8000FFFFh
0x18001e21a  cmovns  ebx, eax
0x18001e21d  test    ebx, ebx
0x18001e21f  jns     loc_18001E31B
0x18001e225  mov     rcx, [rbp+57h+hMem]; hMem
0x18001e229  test    rcx, rcx
0x18001e22c  jz      short loc_18001E238
0x18001e22e  call    cs:__imp_LocalFree
0x18001e234  mov     [rbp+57h+hMem], rsi
0x18001e238  test    byte ptr cs:xmmword_180266B60+1, 40h
0x18001e23f  jnz     loc_18001E346
0x18001e245  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18001e249  test    rcx, rcx
0x18001e24c  jz      short loc_18001E254
0x18001e24e  call    cs:__imp_CloseHandle
0x18001e254  mov     eax, ebx
0x18001e256  mov     rcx, [rbp+57h+var_30]
0x18001e25a  xor     rcx, rsp; StackCookie
0x18001e25d  call    __security_check_cookie
0x18001e262  add     rsp, 0D8h
0x18001e269  pop     rdi
0x18001e26a  pop     rsi
0x18001e26b  pop     rbx
0x18001e26c  pop     rbp
0x18001e26d  retn
0x18001e26e  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18001e272  lea     rax, [rbp+57h+var_A0]
0x18001e276  mov     r9d, 58h ; 'X'; TokenInformationLength
0x18001e27c  mov     [rsp+0F0h+ReturnLength], rax; ReturnLength
0x18001e281  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18001e285  lea     edx, [r9-57h]; TokenInformationClass
0x18001e289  call    cs:__imp_GetTokenInformation
0x18001e28f  test    eax, eax
0x18001e291  jz      loc_18001E372
0x18001e297  mov     rcx, [rbp+57h+TokenInformation]; Sid
0x18001e29b  lea     rdx, [rbp+57h+hMem]; StringSid
0x18001e29f  call    cs:__imp_ConvertSidToStringSidW
0x18001e2a5  test    eax, eax
0x18001e2a7  jz      loc_18001E39C
0x18001e2ad  test    ebx, ebx
0x18001e2af  jz      loc_18001E3D7
0x18001e2b5  mov     rdx, [rbp+57h+hMem]
0x18001e2b9  cmp     [rdi+8], esi
0x18001e2bc  jnz     loc_18001E364
0x18001e2c2  test    rdx, rdx
0x18001e2c5  jz      loc_18001E3C6
0x18001e2cb  lea     rax, aWebcache7329ea; "webcache_{7329ea82-0845-4e4c-bd18-02b67"...
0x18001e2d2  mov     [rbp+57h+var_C0], 30h ; '0'
0x18001e2d9  mov     [rbp+57h+var_B8], rax
0x18001e2dd  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001e2e1  inc     r8
0x18001e2e4  cmp     [rdx+r8*2], si
0x18001e2e9  jnz     short loc_18001E2E1
0x18001e2eb  mov     [rbp+57h+var_BC], r8d
0x18001e2ef  lea     rax, [rbp+57h+var_B8]
0x18001e2f3  mov     [rbp+57h+var_B0], rdx
0x18001e2f7  lea     r9, [rbp+57h+var_C0]; unsigned int *
0x18001e2fb  add     r8d, 30h ; '0'; unsigned int
0x18001e2ff  mov     [rsp+0F0h+ReturnLength], rax; unsigned __int16 **
0x18001e304  mov     edx, 2; unsigned int
0x18001e309  mov     rcx, rdi; this
0x18001e30c  call    ?_Append@CWxString@@AEAAJKKQEAKQEAPEBG@Z; CWxString::_Append(ulong,ulong,ulong * const,ushort const * * const)
0x18001e311  mov     ebx, eax
0x18001e313  test    eax, eax
0x18001e315  js      loc_18001E3CB
0x18001e31b  test    byte ptr cs:xmmword_180266B60+1, 40h
0x18001e322  jz      loc_18001E225
0x18001e328  mov     r9, [rdi]
0x18001e32b  lea     r8, WPP_5405e779efad323d0e60cfee69e77ab2_Traceguids
0x18001e332  mov     edx, 0Bh
0x18001e337  mov     ecx, 40Eh
0x18001e33c  call    WPP_SF_S
0x18001e341  jmp     loc_18001E225
0x18001e346  mov     edx, 0Ch
0x18001e34b  lea     r8, WPP_5405e779efad323d0e60cfee69e77ab2_Traceguids
0x18001e352  mov     ecx, 40Eh
0x18001e357  mov     r9d, ebx
0x18001e35a  call    WPP_SF_d
0x18001e35f  jmp     loc_18001E245
0x18001e364  mov     rcx, [rdi]
0x18001e367  mov     [rdi+8], esi
0x18001e36a  mov     [rcx], si
0x18001e36d  jmp     loc_18001E2C2
0x18001e372  call    WxGetLastError
0x18001e377  mov     ebx, eax
0x18001e379  test    eax, eax
0x18001e37b  jle     short loc_18001E386
0x18001e37d  movzx   ebx, ax
0x18001e380  or      ebx, 80070000h
0x18001e386  test    ebx, ebx
0x18001e388  mov     [rbp+57h+var_BC], 1Fh
0x18001e38f  mov     eax, 8000FFFFh
0x18001e394  cmovns  ebx, eax
0x18001e397  jmp     loc_18001E21D
0x18001e39c  call    WxGetLastError
0x18001e3a1  mov     ebx, eax
0x18001e3a3  test    eax, eax
0x18001e3a5  jle     short loc_18001E3B0
0x18001e3a7  movzx   ebx, ax
0x18001e3aa  or      ebx, 80070000h
0x18001e3b0  test    ebx, ebx
0x18001e3b2  mov     [rbp+57h+var_BC], 21h ; '!'
0x18001e3b9  mov     eax, 8000FFFFh
0x18001e3be  cmovns  ebx, eax
0x18001e3c1  jmp     loc_18001E21D
0x18001e3c6  mov     ebx, 80070057h
0x18001e3cb  mov     [rbp+57h+var_BC], 25h ; '%'
0x18001e3d2  jmp     loc_18001E21D
0x18001e3d7  mov     r8, [rbp+57h+hMem]; unsigned __int16 *
0x18001e3db  lea     rdx, aWebcache031b98; "webcache_{031b98cf-4a69-4c31-ab42-fd9b3"...
0x18001e3e2  mov     rcx, rdi; this
0x18001e3e5  call    ?Set@CWxString@@QEAAJPEBG0@Z; CWxString::Set(ushort const *,ushort const *)
0x18001e3ea  mov     ebx, eax
0x18001e3ec  test    eax, eax
0x18001e3ee  jns     loc_18001E21D
0x18001e3f4  mov     [rbp+57h+var_BC], 29h ; ')'
0x18001e3fb  jmp     loc_18001E21D
```
