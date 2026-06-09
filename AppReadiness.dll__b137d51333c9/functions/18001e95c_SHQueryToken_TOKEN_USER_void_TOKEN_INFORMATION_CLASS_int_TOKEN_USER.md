# SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)

- ea: `0x18001e95c`
- end: `0x18001ea86`
- name: `??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z`
- size: `298`
- prototype: `int __fastcall(HANDLE TokenHandle, int, DWORD, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010454`
- `0x180063d50`

## callees

- `0x18001e95c`
- `0x180021750`
- `0x18003868c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ea1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ea71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ea1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ea71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ea7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ea7b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001e9bf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ea63`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001e9bf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ea63`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e995`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e995`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ea07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ea2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ea07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ea2e`

## pseudocode

```c
int __fastcall SHQueryToken<_TOKEN_USER>(HANDLE TokenHandle, int a2, DWORD a3, _QWORD *a4)
{
  HANDLE v5; // rsi
  void *v6; // rdi
  signed int v7; // ebx
  int result; // eax
  signed int LastError; // eax
  unsigned int v10; // edx
  void *v11; // rcx
  int v12; // eax
  LPVOID TokenInformation; // [rsp+60h] [rbp+30h] BYREF
  DWORD TokenInformationLength; // [rsp+70h] [rbp+40h] BYREF
  HANDLE hObject; // [rsp+78h] [rbp+48h] BYREF

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
  TokenInformation = LocalAlloc(0x40u, 0x800u);
  v6 = TokenInformation;
  if ( !TokenInformation )
  {
    v7 = -2147024882;
    goto LABEL_5;
  }
  v7 = 0;
  if ( !GetTokenInformation(v5, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError == 122 )
    {
      LocalFree(v6);
      v12 = CTLocalAllocPolicy::Alloc(v11, v10, TokenInformationLength, &TokenInformation);
      v6 = TokenInformation;
      v7 = v12;
      if ( v12 < 0 )
        goto LABEL_13;
      if ( GetTokenInformation(v5, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
        goto LABEL_4;
      LastError = GetLastError();
      v7 = LastError;
    }
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 >= 0 )
      goto LABEL_4;
LABEL_13:
    LocalFree(v6);
    goto LABEL_5;
  }
LABEL_4:
  *a4 = v6;
LABEL_5:
  if ( hObject )
    CloseHandle(hObject);
  return v7;
}

```

## disassembly

```asm
0x18001e95c  mov     [rsp-28h+TokenInformationLength], r8d
0x18001e961  push    rbp
0x18001e962  push    rbx
0x18001e963  push    rsi
0x18001e964  push    rdi
0x18001e965  push    r14
0x18001e967  mov     rbp, rsp
0x18001e96a  sub     rsp, 30h
0x18001e96e  mov     qword ptr [r9], 0
0x18001e975  mov     r14, r9
0x18001e978  mov     [rbp+hObject], 0
0x18001e980  mov     rsi, rcx
0x18001e983  test    rcx, rcx
0x18001e986  jz      short loc_18001E9E6
0x18001e988  mov     edx, 800h; uBytes
0x18001e98d  mov     ecx, 40h ; '@'; uFlags
0x18001e992  mov     [rbp+TokenInformationLength], edx
0x18001e995  call    cs:__imp_LocalAlloc
0x18001e99b  mov     [rbp+TokenInformation], rax
0x18001e99f  mov     rdi, rax
0x18001e9a2  test    rax, rax
0x18001e9a5  jz      short loc_18001E9F9
0x18001e9a7  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18001e9ab  lea     rax, [rbp+TokenInformationLength]
0x18001e9af  xor     ebx, ebx
0x18001e9b1  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18001e9b6  mov     r8, rdi; TokenInformation
0x18001e9b9  mov     rcx, rsi; TokenHandle
0x18001e9bc  lea     edx, [rbx+1]; TokenInformationClass
0x18001e9bf  call    cs:__imp_GetTokenInformation
0x18001e9c5  test    eax, eax
0x18001e9c7  jz      short loc_18001EA1E
0x18001e9c9  mov     [r14], rdi
0x18001e9cc  mov     rcx, [rbp+hObject]; unsigned int
0x18001e9d0  test    rcx, rcx
0x18001e9d3  jnz     loc_18001EA7B
0x18001e9d9  mov     eax, ebx
0x18001e9db  add     rsp, 30h
0x18001e9df  pop     r14
0x18001e9e1  pop     rdi
0x18001e9e2  pop     rsi
0x18001e9e3  pop     rbx
0x18001e9e4  pop     rbp
0x18001e9e5  retn
0x18001e9e6  lea     r8, [rbp+hObject]; void **
0x18001e9ea  call    ?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z; SHOpenEffectiveToken(ulong,int,void * *)
0x18001e9ef  test    eax, eax
0x18001e9f1  js      short loc_18001E9DB
0x18001e9f3  mov     rsi, [rbp+hObject]
0x18001e9f7  jmp     short loc_18001E988
0x18001e9f9  mov     ebx, 8007000Eh
0x18001e9fe  jmp     short loc_18001E9CC
0x18001ea00  test    ebx, ebx
0x18001ea02  jns     short loc_18001E9C9
0x18001ea04  mov     rcx, rdi; hMem
0x18001ea07  call    cs:__imp_LocalFree
0x18001ea0d  jmp     short loc_18001E9CC
0x18001ea0f  test    eax, eax
0x18001ea11  jle     short loc_18001EA00
0x18001ea13  movzx   ebx, ax
0x18001ea16  or      ebx, 80070000h
0x18001ea1c  jmp     short loc_18001EA00
0x18001ea1e  call    cs:__imp_GetLastError
0x18001ea24  mov     ebx, eax
0x18001ea26  cmp     eax, 7Ah ; 'z'
0x18001ea29  jnz     short loc_18001EA0F
0x18001ea2b  mov     rcx, rdi; hMem
0x18001ea2e  call    cs:__imp_LocalFree
0x18001ea34  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x18001ea38  lea     r9, [rbp+TokenInformation]; void **
0x18001ea3c  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18001ea41  mov     rdi, [rbp+TokenInformation]
0x18001ea45  mov     ebx, eax
0x18001ea47  test    eax, eax
0x18001ea49  js      short loc_18001EA04
0x18001ea4b  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18001ea4f  lea     rax, [rbp+TokenInformationLength]
0x18001ea53  mov     r8, rdi; TokenInformation
0x18001ea56  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18001ea5b  mov     edx, 1; TokenInformationClass
0x18001ea60  mov     rcx, rsi; TokenHandle
0x18001ea63  call    cs:__imp_GetTokenInformation
0x18001ea69  test    eax, eax
0x18001ea6b  jnz     loc_18001E9C9
0x18001ea71  call    cs:__imp_GetLastError
0x18001ea77  mov     ebx, eax
0x18001ea79  jmp     short loc_18001EA0F
0x18001ea7b  call    cs:__imp_CloseHandle
0x18001ea81  jmp     loc_18001E9D9
```
