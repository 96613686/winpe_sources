# IsTokenLowIL(void *)

- ea: `0x18001218c`
- end: `0x1800122c4`
- name: `?IsTokenLowIL@@YAJPEAX@Z`
- size: `312`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180012028`

## callees

- `0x18001218c`
- `0x180021750`
- `0x18003868c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012205`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012254`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012205`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012254`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001228b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001228b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800121fb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001224a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800121fb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001224a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18001229a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18001229a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800121cd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800121cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012215`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012270`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800122a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012215`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012270`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800122a5`

## pseudocode

```c
__int64 __fastcall IsTokenLowIL(HANDLE TokenHandle, int a2)
{
  PSID *v2; // r14
  HANDLE v3; // rsi
  signed int v4; // edi
  void *v5; // rbx
  signed int LastError; // eax
  unsigned int v7; // edx
  void *v8; // rcx
  int v9; // eax
  DWORD v10; // ebx
  DWORD TokenInformationLength; // [rsp+60h] [rbp+30h] BYREF
  LPVOID TokenInformation; // [rsp+68h] [rbp+38h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp+40h] BYREF

  v2 = 0;
  v3 = TokenHandle;
  hObject = 0;
  if ( !TokenHandle )
  {
    v4 = SHOpenEffectiveToken(0, a2, &hObject);
    if ( v4 < 0 )
      goto LABEL_18;
    v3 = hObject;
  }
  TokenInformationLength = 2048;
  TokenInformation = LocalAlloc(0x40u, 0x800u);
  v5 = TokenInformation;
  if ( TokenInformation )
  {
    v4 = 0;
    if ( !GetTokenInformation(
            v3,
            TokenIntegrityLevel,
            TokenInformation,
            TokenInformationLength,
            &TokenInformationLength) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError == 122 )
      {
        LocalFree(v5);
        v9 = CTLocalAllocPolicy::Alloc(v8, v7, TokenInformationLength, &TokenInformation);
        v5 = TokenInformation;
        v4 = v9;
        if ( v9 < 0 )
        {
LABEL_13:
          LocalFree(v5);
          goto LABEL_16;
        }
        if ( GetTokenInformation(
               v3,
               TokenIntegrityLevel,
               TokenInformation,
               TokenInformationLength,
               &TokenInformationLength) )
        {
          goto LABEL_14;
        }
        LastError = GetLastError();
        v4 = LastError;
      }
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( v4 < 0 )
        goto LABEL_13;
    }
LABEL_14:
    v2 = (PSID *)v5;
    goto LABEL_16;
  }
  v4 = -2147024882;
LABEL_16:
  if ( hObject )
    CloseHandle(hObject);
LABEL_18:
  if ( v4 >= 0 )
  {
    v10 = *GetSidSubAuthority(*v2, 0);
    LocalFree(v2);
    return v10 >= 0x2000;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001218c  push    rbp
0x18001218e  push    rbx
0x18001218f  push    rsi
0x180012190  push    rdi
0x180012191  push    r14
0x180012193  mov     rbp, rsp
0x180012196  sub     rsp, 30h
0x18001219a  xor     r14d, r14d
0x18001219d  mov     rsi, rcx
0x1800121a0  mov     [rbp+hObject], r14
0x1800121a4  test    rcx, rcx
0x1800121a7  jnz     short loc_1800121C0
0x1800121a9  lea     r8, [rbp+hObject]; void **
0x1800121ad  call    ?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z; SHOpenEffectiveToken(ulong,int,void * *)
0x1800121b2  mov     edi, eax
0x1800121b4  test    eax, eax
0x1800121b6  js      loc_180012291
0x1800121bc  mov     rsi, [rbp+hObject]
0x1800121c0  mov     edx, 800h; uBytes
0x1800121c5  mov     ecx, 40h ; '@'; uFlags
0x1800121ca  mov     [rbp+TokenInformationLength], edx
0x1800121cd  call    cs:__imp_LocalAlloc
0x1800121d3  mov     [rbp+TokenInformation], rax
0x1800121d7  mov     rbx, rax
0x1800121da  test    rax, rax
0x1800121dd  jz      loc_18001227D
0x1800121e3  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800121e7  lea     rax, [rbp+TokenInformationLength]
0x1800121eb  xor     edi, edi
0x1800121ed  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800121f2  mov     r8, rbx; TokenInformation
0x1800121f5  mov     rcx, rsi; TokenHandle
0x1800121f8  lea     edx, [rdi+19h]; TokenInformationClass
0x1800121fb  call    cs:__imp_GetTokenInformation
0x180012201  test    eax, eax
0x180012203  jnz     short loc_180012278
0x180012205  call    cs:__imp_GetLastError
0x18001220b  mov     edi, eax
0x18001220d  cmp     eax, 7Ah ; 'z'
0x180012210  jnz     short loc_18001225C
0x180012212  mov     rcx, rbx; hMem
0x180012215  call    cs:__imp_LocalFree
0x18001221b  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x18001221f  lea     r9, [rbp+TokenInformation]; void **
0x180012223  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180012228  mov     rbx, [rbp+TokenInformation]
0x18001222c  mov     edi, eax
0x18001222e  test    eax, eax
0x180012230  js      short loc_18001226D
0x180012232  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180012236  lea     rax, [rbp+TokenInformationLength]
0x18001223a  mov     r8, rbx; TokenInformation
0x18001223d  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180012242  mov     edx, 19h; TokenInformationClass
0x180012247  mov     rcx, rsi; TokenHandle
0x18001224a  call    cs:__imp_GetTokenInformation
0x180012250  test    eax, eax
0x180012252  jnz     short loc_180012278
0x180012254  call    cs:__imp_GetLastError
0x18001225a  mov     edi, eax
0x18001225c  test    eax, eax
0x18001225e  jle     short loc_180012269
0x180012260  movzx   edi, ax
0x180012263  or      edi, 80070000h
0x180012269  test    edi, edi
0x18001226b  jns     short loc_180012278
0x18001226d  mov     rcx, rbx; hMem
0x180012270  call    cs:__imp_LocalFree
0x180012276  jmp     short loc_180012282
0x180012278  mov     r14, rbx
0x18001227b  jmp     short loc_180012282
0x18001227d  mov     edi, 8007000Eh
0x180012282  mov     rcx, [rbp+hObject]; hObject
0x180012286  test    rcx, rcx
0x180012289  jz      short loc_180012291
0x18001228b  call    cs:__imp_CloseHandle
0x180012291  test    edi, edi
0x180012293  js      short loc_1800122B7
0x180012295  mov     rcx, [r14]; pSid
0x180012298  xor     edx, edx; nSubAuthority
0x18001229a  call    cs:__imp_GetSidSubAuthority
0x1800122a0  mov     rcx, r14; hMem
0x1800122a3  mov     ebx, [rax]
0x1800122a5  call    cs:__imp_LocalFree
0x1800122ab  xor     edi, edi
0x1800122ad  cmp     ebx, 2000h
0x1800122b3  setnb   dil
0x1800122b7  mov     eax, edi
0x1800122b9  add     rsp, 30h
0x1800122bd  pop     r14
0x1800122bf  pop     rdi
0x1800122c0  pop     rsi
0x1800122c1  pop     rbx
0x1800122c2  pop     rbp
0x1800122c3  retn
```
