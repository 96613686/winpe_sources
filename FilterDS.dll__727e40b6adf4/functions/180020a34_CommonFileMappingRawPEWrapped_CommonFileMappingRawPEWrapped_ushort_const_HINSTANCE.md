# CommonFileMappingRawPEWrapped::CommonFileMappingRawPEWrapped(ushort const *,HINSTANCE__ *)

- ea: `0x180020a34`
- end: `0x180020c7c`
- name: `??0CommonFileMappingRawPEWrapped@@AEAA@PEBGPEAUHINSTANCE__@@@Z`
- size: `584`
- prototype: `CommonFileMappingRawPEWrapped *__fastcall(CommonFileMappingRawPEWrapped *this, unsigned __int16 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180020f98`

## callees

- `0x18000cef4`
- `0x18000f64c`
- `0x180020a34`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180020b26`
- `msvcrt!??3@YAXPEAX@Z` at `0x180020b79`
- `msvcrt!??3@YAXPEAX@Z` at `0x180020b26`
- `msvcrt!??3@YAXPEAX@Z` at `0x180020b79`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180020c27`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180020c27`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180020c47`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180020c47`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180020c13`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180020c13`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180020c39`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180020c39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180020a7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180020a7d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180020a8e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180020a8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020aaa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020b8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020aaa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020b8e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180020ad2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180020b10`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180020ad2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180020b10`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180020b50`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180020b50`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180020b60`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180020b60`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180020b41`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180020b41`

## pseudocode

```c
CommonFileMappingRawPEWrapped *__fastcall CommonFileMappingRawPEWrapped::CommonFileMappingRawPEWrapped(
        CommonFileMappingRawPEWrapped *this,
        unsigned __int16 *a2,
        HINSTANCE a3)
{
  HANDLE CurrentProcess; // rax
  PSID *v7; // rdi
  PSID v8; // rsi
  DWORD v9; // r14d
  int v10; // esi
  BOOL v11; // eax
  __int64 v12; // r8
  HRSRC Resource; // rax
  HRSRC v14; // rsi
  DWORD v15; // eax
  __int64 v16; // rdi
  HGLOBAL v17; // rax
  LPVOID v18; // rax
  LPVOID TokenInformation[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v21; // [rsp+50h] [rbp-10h]
  DWORD TokenInformationLength; // [rsp+A8h] [rbp+48h] BYREF
  void *TokenHandle; // [rsp+B0h] [rbp+50h] BYREF

  *(_QWORD *)this = &CommonFileMappingRawBase::`vftable';
  *((_DWORD *)this + 3) = 1;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x18u, &TokenHandle) )
    goto LABEL_2;
  TokenInformationLength = 0;
  GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, &TokenInformationLength);
  if ( !TokenInformationLength )
    goto LABEL_2;
  *(_OWORD *)TokenInformation = 0;
  v21 = 0;
  std::vector<unsigned char>::resize(TokenInformation, TokenInformationLength);
  v7 = (PSID *)TokenInformation[0];
  if ( !GetTokenInformation(
          TokenHandle,
          TokenIntegrityLevel,
          TokenInformation[0],
          TokenInformationLength,
          &TokenInformationLength) )
  {
    if ( !v7 )
      goto LABEL_2;
    goto LABEL_7;
  }
  if ( !v7 )
  {
LABEL_2:
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
LABEL_16:
    v11 = 0;
    goto LABEL_18;
  }
  v8 = *v7;
  if ( !IsValidSid(*v7) )
  {
LABEL_7:
    operator delete(v7);
    goto LABEL_2;
  }
  if ( *GetSidSubAuthorityCount(v8) )
  {
    v9 = *GetSidSubAuthority(v8, 0);
    v10 = 1;
  }
  else
  {
    v9 = 0;
    v10 = 0;
  }
  operator delete(v7);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  if ( !v10 )
    goto LABEL_16;
  v11 = v9 < 0x2000;
LABEL_18:
  *((_DWORD *)this + 4) = v11;
  *(_QWORD *)this = &CommonFileMappingRawPEWrapped::`vftable';
  *((_QWORD *)this + 6) = 7;
  *((_QWORD *)this + 5) = 0;
  *((_WORD *)this + 12) = 0;
  if ( *a2 )
  {
    v12 = -1;
    do
      ++v12;
    while ( a2[v12] );
  }
  std::wstring::assign((char *)this + 24, a2);
  *((_QWORD *)this + 7) = a3;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 2) = 0;
  Resource = FindResourceExW(a3, L"STREAM", L"DICTSTREAM", 0x409u);
  v14 = Resource;
  if ( Resource )
  {
    v15 = SizeofResource(a3, Resource);
    v16 = v15;
    if ( v15 )
    {
      v17 = LoadResource(a3, v14);
      if ( v17 )
      {
        v18 = LockResource(v17);
        if ( v18 )
        {
          *((_QWORD *)this + 8) = v18;
          *((_QWORD *)this + 9) = v16;
          *((_DWORD *)this + 2) = 1;
        }
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x180020a34  mov     [rsp-38h+arg_18], rbx
0x180020a39  mov     [rsp-38h+arg_0], rcx
0x180020a3e  push    rbp
0x180020a3f  push    rsi
0x180020a40  push    rdi
0x180020a41  push    r12
0x180020a43  push    r13
0x180020a45  push    r14
0x180020a47  push    r15
0x180020a49  mov     rbp, rsp
0x180020a4c  sub     rsp, 60h
0x180020a50  mov     r12, r8
0x180020a53  mov     r15, rdx
0x180020a56  mov     rbx, rcx
0x180020a59  lea     rax, ??_7CommonFileMappingRawBase@@6B@; const CommonFileMappingRawBase::`vftable'
0x180020a60  mov     [rcx], rax
0x180020a63  mov     dword ptr [rcx+0Ch], 1
0x180020a6a  xor     r13d, r13d
0x180020a6d  mov     [rbp+TokenHandle], r13
0x180020a71  lea     rax, [rbp+TokenHandle]
0x180020a75  mov     [rbp+var_30], rax
0x180020a79  mov     [rbp+var_28], 1
0x180020a7d  call    cs:__imp_GetCurrentProcess
0x180020a83  mov     rcx, rax; ProcessHandle
0x180020a86  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180020a8a  lea     edx, [r13+18h]; DesiredAccess
0x180020a8e  call    cs:__imp_OpenProcessToken
0x180020a94  test    eax, eax
0x180020a96  jnz     short loc_180020AB5
0x180020a98  mov     rcx, [rbp+TokenHandle]; hObject
0x180020a9c  lea     rax, [rcx-1]
0x180020aa0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180020aa4  ja      loc_180020B98
0x180020aaa  call    cs:__imp_CloseHandle
0x180020ab0  jmp     loc_180020B98
0x180020ab5  mov     [rbp+TokenInformationLength], r13d
0x180020ab9  lea     rax, [rbp+TokenInformationLength]
0x180020abd  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180020ac2  xor     r9d, r9d; TokenInformationLength
0x180020ac5  xor     r8d, r8d; TokenInformation
0x180020ac8  lea     esi, [r9+19h]
0x180020acc  mov     edx, esi; TokenInformationClass
0x180020ace  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180020ad2  call    cs:__imp_GetTokenInformation
0x180020ad8  mov     eax, [rbp+TokenInformationLength]
0x180020adb  test    eax, eax
0x180020add  jz      short loc_180020A98
0x180020adf  xorps   xmm0, xmm0
0x180020ae2  movdqu  xmmword ptr [rbp+TokenInformation], xmm0
0x180020ae7  mov     [rbp+var_10], r13
0x180020aeb  mov     edx, eax
0x180020aed  lea     rcx, [rbp+TokenInformation]
0x180020af1  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x180020af6  mov     rdi, [rbp+TokenInformation]
0x180020afa  lea     rax, [rbp+TokenInformationLength]
0x180020afe  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180020b03  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180020b07  mov     r8, rdi; TokenInformation
0x180020b0a  mov     edx, esi; TokenInformationClass
0x180020b0c  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180020b10  call    cs:__imp_GetTokenInformation
0x180020b16  test    eax, eax
0x180020b18  jnz     short loc_180020B31
0x180020b1a  test    rdi, rdi
0x180020b1d  jz      loc_180020A98
0x180020b23  mov     rcx, rdi
0x180020b26  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180020b2c  jmp     loc_180020A98
0x180020b31  test    rdi, rdi
0x180020b34  jnz     short loc_180020B3B
0x180020b36  jmp     loc_180020A98
0x180020b3b  mov     rsi, [rdi]
0x180020b3e  mov     rcx, rsi; pSid
0x180020b41  call    cs:__imp_IsValidSid
0x180020b47  test    eax, eax
0x180020b49  jnz     short loc_180020B4D
0x180020b4b  jmp     short loc_180020B23
0x180020b4d  mov     rcx, rsi; pSid
0x180020b50  call    cs:__imp_GetSidSubAuthorityCount
0x180020b56  cmp     byte ptr [rax], 1
0x180020b59  jb      short loc_180020B70
0x180020b5b  xor     edx, edx; nSubAuthority
0x180020b5d  mov     rcx, rsi; pSid
0x180020b60  call    cs:__imp_GetSidSubAuthority
0x180020b66  mov     r14d, [rax]
0x180020b69  mov     esi, 1
0x180020b6e  jmp     short loc_180020B76
0x180020b70  mov     r14d, r13d
0x180020b73  mov     esi, r13d
0x180020b76  mov     rcx, rdi
0x180020b79  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180020b7f  nop
0x180020b80  mov     rcx, [rbp+TokenHandle]; hObject
0x180020b84  lea     rax, [rcx-1]
0x180020b88  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180020b8c  ja      short loc_180020B94
0x180020b8e  call    cs:__imp_CloseHandle
0x180020b94  test    esi, esi
0x180020b96  jnz     short loc_180020B9D
0x180020b98  mov     eax, r13d
0x180020b9b  jmp     short loc_180020BAA
0x180020b9d  mov     eax, r13d
0x180020ba0  cmp     r14d, 2000h
0x180020ba7  setb    al
0x180020baa  mov     [rbx+10h], eax
0x180020bad  lea     rax, ??_7CommonFileMappingRawPEWrapped@@6B@; const CommonFileMappingRawPEWrapped::`vftable'
0x180020bb4  mov     [rbx], rax
0x180020bb7  lea     rcx, [rbx+18h]; void *
0x180020bbb  mov     qword ptr [rcx+18h], 7
0x180020bc3  mov     [rcx+10h], r13
0x180020bc7  mov     [rcx], r13w
0x180020bcb  cmp     [r15], r13w
0x180020bcf  jnz     short loc_180020BD6
0x180020bd1  mov     r8, r13
0x180020bd4  jmp     short loc_180020BE4
0x180020bd6  or      r8, 0FFFFFFFFFFFFFFFFh
0x180020bda  inc     r8
0x180020bdd  cmp     [r15+r8*2], r13w
0x180020be2  jnz     short loc_180020BDA
0x180020be4  mov     rdx, r15; Src
0x180020be7  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180020bec  mov     [rbx+38h], r12
0x180020bf0  mov     [rbx+40h], r13
0x180020bf4  mov     [rbx+48h], r13
0x180020bf8  mov     [rbx+8], r13d
0x180020bfc  mov     r9d, 409h; wLanguage
0x180020c02  lea     r8, Name; "DICTSTREAM"
0x180020c09  lea     rdx, Type; "STREAM"
0x180020c10  mov     rcx, r12; hModule
0x180020c13  call    cs:__imp_FindResourceExW
0x180020c19  mov     rsi, rax
0x180020c1c  test    rax, rax
0x180020c1f  jz      short loc_180020C61
0x180020c21  mov     rdx, rax; hResInfo
0x180020c24  mov     rcx, r12; hModule
0x180020c27  call    cs:__imp_SizeofResource
0x180020c2d  mov     edi, eax
0x180020c2f  test    eax, eax
0x180020c31  jz      short loc_180020C61
0x180020c33  mov     rdx, rsi; hResInfo
0x180020c36  mov     rcx, r12; hModule
0x180020c39  call    cs:__imp_LoadResource
0x180020c3f  test    rax, rax
0x180020c42  jz      short loc_180020C61
0x180020c44  mov     rcx, rax; hResData
0x180020c47  call    cs:__imp_LockResource
0x180020c4d  test    rax, rax
0x180020c50  jz      short loc_180020C61
0x180020c52  mov     [rbx+40h], rax
0x180020c56  mov     [rbx+48h], rdi
0x180020c5a  mov     dword ptr [rbx+8], 1
0x180020c61  mov     rax, rbx
0x180020c64  mov     rbx, [rsp+60h+arg_18]
0x180020c6c  add     rsp, 60h
0x180020c70  pop     r15
0x180020c72  pop     r14
0x180020c74  pop     r13
0x180020c76  pop     r12
0x180020c78  pop     rdi
0x180020c79  pop     rsi
0x180020c7a  pop     rbp
0x180020c7b  retn
```
