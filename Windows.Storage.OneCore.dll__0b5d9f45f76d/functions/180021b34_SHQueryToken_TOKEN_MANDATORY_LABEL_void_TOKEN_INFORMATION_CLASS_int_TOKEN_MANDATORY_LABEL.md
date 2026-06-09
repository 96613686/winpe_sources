# SHQueryToken<_TOKEN_MANDATORY_LABEL>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_MANDATORY_LABEL * *)

- ea: `0x180021b34`
- end: `0x180021c5f`
- name: `??$SHQueryToken@U_TOKEN_MANDATORY_LABEL@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_MANDATORY_LABEL@@@Z`
- size: `299`
- prototype: `int __fastcall(HANDLE TokenHandle, int, DWORD, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180021d04`

## callees

- `0x180021b34`
- `0x180021c94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021bbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021c0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021bbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021c0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021c49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021c49`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021bcb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021c26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021bcb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021c26`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021b85`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021bd8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021b85`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021bd8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021bb1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021c00`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021bb1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021c00`

## pseudocode

```c
int __fastcall SHQueryToken<_TOKEN_MANDATORY_LABEL>(HANDLE TokenHandle, int a2, DWORD a3, _QWORD *a4)
{
  HANDLE v5; // rsi
  int result; // eax
  HLOCAL v7; // rdi
  signed int v8; // ebx
  signed int LastError; // eax
  HANDLE hObject; // [rsp+50h] [rbp+8h] BYREF
  DWORD TokenInformationLength; // [rsp+60h] [rbp+18h] BYREF

  TokenInformationLength = a3;
  *a4 = 0;
  hObject = 0;
  v5 = TokenHandle;
  if ( !TokenHandle )
  {
    result = SHOpenEffectiveToken(0, a2, &hObject);
    if ( result < 0 )
      return result;
    v5 = hObject;
  }
  TokenInformationLength = 2048;
  v7 = LocalAlloc(0x40u, 0x800u);
  if ( !v7 )
  {
    v8 = -2147024882;
    goto LABEL_17;
  }
  v8 = 0;
  if ( GetTokenInformation(v5, TokenIntegrityLevel, v7, TokenInformationLength, &TokenInformationLength) )
    goto LABEL_15;
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError != 122 )
    goto LABEL_10;
  LocalFree(v7);
  v7 = LocalAlloc(0x40u, TokenInformationLength);
  if ( v7 )
  {
    v8 = 0;
    if ( GetTokenInformation(v5, TokenIntegrityLevel, v7, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_15;
    LastError = GetLastError();
    v8 = LastError;
LABEL_10:
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 < 0 )
      goto LABEL_13;
LABEL_15:
    *a4 = v7;
    goto LABEL_17;
  }
  v8 = -2147024882;
LABEL_13:
  LocalFree(v7);
LABEL_17:
  if ( hObject )
    CloseHandle(hObject);
  return v8;
}

```

## disassembly

```asm
0x180021b34  mov     rax, rsp
0x180021b37  mov     [rax+10h], rbx
0x180021b3b  mov     [rax+18h], r8d
0x180021b3f  push    rsi
0x180021b40  push    rdi
0x180021b41  push    r14
0x180021b43  sub     rsp, 30h
0x180021b47  mov     qword ptr [r9], 0
0x180021b4e  mov     r14, r9
0x180021b51  mov     qword ptr [rax+8], 0
0x180021b59  mov     rsi, rcx
0x180021b5c  test    rcx, rcx
0x180021b5f  jnz     short loc_180021B77
0x180021b61  lea     r8, [rax+8]; void **
0x180021b65  call    ?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z; SHOpenEffectiveToken(ulong,int,void * *)
0x180021b6a  test    eax, eax
0x180021b6c  js      loc_180021C51
0x180021b72  mov     rsi, [rsp+48h+hObject]
0x180021b77  mov     edx, 800h; uBytes
0x180021b7c  mov     ecx, 40h ; '@'; uFlags
0x180021b81  mov     [rsp+48h+TokenInformationLength], edx
0x180021b85  call    cs:__imp_LocalAlloc
0x180021b8b  mov     rdi, rax
0x180021b8e  test    rax, rax
0x180021b91  jz      loc_180021C3A
0x180021b97  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180021b9c  lea     rax, [rsp+48h+TokenInformationLength]
0x180021ba1  xor     ebx, ebx
0x180021ba3  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180021ba8  mov     r8, rdi; TokenInformation
0x180021bab  mov     rcx, rsi; TokenHandle
0x180021bae  lea     edx, [rbx+19h]; TokenInformationClass
0x180021bb1  call    cs:__imp_GetTokenInformation
0x180021bb7  test    eax, eax
0x180021bb9  jnz     short loc_180021C35
0x180021bbb  call    cs:__imp_GetLastError
0x180021bc1  mov     ebx, eax
0x180021bc3  cmp     eax, 7Ah ; 'z'
0x180021bc6  jnz     short loc_180021C12
0x180021bc8  mov     rcx, rdi; hMem
0x180021bcb  call    cs:__imp_LocalFree
0x180021bd1  mov     edx, [rsp+48h+TokenInformationLength]; uBytes
0x180021bd5  lea     ecx, [rbx-3Ah]; uFlags
0x180021bd8  call    cs:__imp_LocalAlloc
0x180021bde  mov     rdi, rax
0x180021be1  test    rax, rax
0x180021be4  jz      short loc_180021C2E
0x180021be6  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180021beb  lea     rax, [rsp+48h+TokenInformationLength]
0x180021bf0  xor     ebx, ebx
0x180021bf2  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180021bf7  mov     r8, rdi; TokenInformation
0x180021bfa  mov     rcx, rsi; TokenHandle
0x180021bfd  lea     edx, [rbx+19h]; TokenInformationClass
0x180021c00  call    cs:__imp_GetTokenInformation
0x180021c06  test    eax, eax
0x180021c08  jnz     short loc_180021C35
0x180021c0a  call    cs:__imp_GetLastError
0x180021c10  mov     ebx, eax
0x180021c12  test    eax, eax
0x180021c14  jle     short loc_180021C1F
0x180021c16  movzx   ebx, ax
0x180021c19  or      ebx, 80070000h
0x180021c1f  test    ebx, ebx
0x180021c21  jns     short loc_180021C35
0x180021c23  mov     rcx, rdi; hMem
0x180021c26  call    cs:__imp_LocalFree
0x180021c2c  jmp     short loc_180021C3F
0x180021c2e  mov     ebx, 8007000Eh
0x180021c33  jmp     short loc_180021C23
0x180021c35  mov     [r14], rdi
0x180021c38  jmp     short loc_180021C3F
0x180021c3a  mov     ebx, 8007000Eh
0x180021c3f  mov     rcx, [rsp+48h+hObject]; hObject
0x180021c44  test    rcx, rcx
0x180021c47  jz      short loc_180021C4F
0x180021c49  call    cs:__imp_CloseHandle
0x180021c4f  mov     eax, ebx
0x180021c51  mov     rbx, [rsp+48h+arg_8]
0x180021c56  add     rsp, 30h
0x180021c5a  pop     r14
0x180021c5c  pop     rdi
0x180021c5d  pop     rsi
0x180021c5e  retn
```
