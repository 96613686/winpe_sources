# SHGetUserSid

- ea: `0x180012630`
- end: `0x18001277b`
- name: `SHGetUserSid`
- size: `331`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, LPWSTR *StringSid)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180011cac`
- `0x1800132a4`
- `0x180027390`

## callees

- `0x180012630`
- `0x180021750`
- `0x18003868c`
- `0x1800473d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800126b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012707`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800126b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012707`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001273e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001273e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800126ae`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800126fd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800126ae`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800126fd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012680`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012680`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800126c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012723`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012762`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800126c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012723`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012762`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001274e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001274e`

## pseudocode

```c
__int64 __fastcall SHGetUserSid(HANDLE TokenHandle, LPWSTR *StringSid)
{
  PSID *v2; // r14
  HANDLE v4; // rsi
  signed int Error; // ebx
  void *v6; // rdi
  signed int LastError; // eax
  unsigned int v8; // edx
  void *v9; // rcx
  int v10; // eax
  DWORD TokenInformationLength; // [rsp+60h] [rbp+30h] BYREF
  LPVOID TokenInformation; // [rsp+68h] [rbp+38h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp+40h] BYREF

  v2 = 0;
  *StringSid = 0;
  hObject = 0;
  v4 = TokenHandle;
  if ( !TokenHandle )
  {
    Error = SHOpenEffectiveToken(0, (int)StringSid, &hObject);
    if ( Error < 0 )
      goto LABEL_18;
    v4 = hObject;
  }
  TokenInformationLength = 2048;
  TokenInformation = LocalAlloc(0x40u, 0x800u);
  v6 = TokenInformation;
  if ( TokenInformation )
  {
    Error = 0;
    if ( !GetTokenInformation(v4, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
    {
      LastError = GetLastError();
      Error = LastError;
      if ( LastError == 122 )
      {
        LocalFree(v6);
        v10 = CTLocalAllocPolicy::Alloc(v9, v8, TokenInformationLength, &TokenInformation);
        v6 = TokenInformation;
        Error = v10;
        if ( v10 < 0 )
        {
LABEL_13:
          LocalFree(v6);
          goto LABEL_16;
        }
        if ( GetTokenInformation(v4, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
          goto LABEL_14;
        LastError = GetLastError();
        Error = LastError;
      }
      if ( LastError > 0 )
        Error = (unsigned __int16)LastError | 0x80070000;
      if ( Error < 0 )
        goto LABEL_13;
    }
LABEL_14:
    v2 = (PSID *)v6;
    goto LABEL_16;
  }
  Error = -2147024882;
LABEL_16:
  if ( hObject )
    CloseHandle(hObject);
LABEL_18:
  if ( Error >= 0 )
  {
    if ( !ConvertSidToStringSidW(*v2, StringSid) )
      Error = ResultFromKnownLastError();
    LocalFree(v2);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180012630  mov     [rsp-28h+arg_18], rbx
0x180012635  push    rbp
0x180012636  push    rsi
0x180012637  push    rdi
0x180012638  push    r14
0x18001263a  push    r15
0x18001263c  mov     rbp, rsp
0x18001263f  sub     rsp, 30h
0x180012643  xor     r14d, r14d
0x180012646  mov     qword ptr [rdx], 0
0x18001264d  mov     [rbp+hObject], r14
0x180012651  mov     r15, rdx
0x180012654  mov     rsi, rcx
0x180012657  test    rcx, rcx
0x18001265a  jnz     short loc_180012673
0x18001265c  lea     r8, [rbp+hObject]; void **
0x180012660  call    ?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z; SHOpenEffectiveToken(ulong,int,void * *)
0x180012665  mov     ebx, eax
0x180012667  test    eax, eax
0x180012669  js      loc_180012744
0x18001266f  mov     rsi, [rbp+hObject]
0x180012673  mov     edx, 800h; uBytes
0x180012678  mov     ecx, 40h ; '@'; uFlags
0x18001267d  mov     [rbp+TokenInformationLength], edx
0x180012680  call    cs:__imp_LocalAlloc
0x180012686  mov     [rbp+TokenInformation], rax
0x18001268a  mov     rdi, rax
0x18001268d  test    rax, rax
0x180012690  jz      loc_180012730
0x180012696  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18001269a  lea     rax, [rbp+TokenInformationLength]
0x18001269e  xor     ebx, ebx
0x1800126a0  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800126a5  mov     r8, rdi; TokenInformation
0x1800126a8  mov     rcx, rsi; TokenHandle
0x1800126ab  lea     edx, [rbx+1]; TokenInformationClass
0x1800126ae  call    cs:__imp_GetTokenInformation
0x1800126b4  test    eax, eax
0x1800126b6  jnz     short loc_18001272B
0x1800126b8  call    cs:__imp_GetLastError
0x1800126be  mov     ebx, eax
0x1800126c0  cmp     eax, 7Ah ; 'z'
0x1800126c3  jnz     short loc_18001270F
0x1800126c5  mov     rcx, rdi; hMem
0x1800126c8  call    cs:__imp_LocalFree
0x1800126ce  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x1800126d2  lea     r9, [rbp+TokenInformation]; void **
0x1800126d6  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800126db  mov     rdi, [rbp+TokenInformation]
0x1800126df  mov     ebx, eax
0x1800126e1  test    eax, eax
0x1800126e3  js      short loc_180012720
0x1800126e5  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800126e9  lea     rax, [rbp+TokenInformationLength]
0x1800126ed  mov     r8, rdi; TokenInformation
0x1800126f0  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800126f5  mov     edx, 1; TokenInformationClass
0x1800126fa  mov     rcx, rsi; TokenHandle
0x1800126fd  call    cs:__imp_GetTokenInformation
0x180012703  test    eax, eax
0x180012705  jnz     short loc_18001272B
0x180012707  call    cs:__imp_GetLastError
0x18001270d  mov     ebx, eax
0x18001270f  test    eax, eax
0x180012711  jle     short loc_18001271C
0x180012713  movzx   ebx, ax
0x180012716  or      ebx, 80070000h
0x18001271c  test    ebx, ebx
0x18001271e  jns     short loc_18001272B
0x180012720  mov     rcx, rdi; hMem
0x180012723  call    cs:__imp_LocalFree
0x180012729  jmp     short loc_180012735
0x18001272b  mov     r14, rdi
0x18001272e  jmp     short loc_180012735
0x180012730  mov     ebx, 8007000Eh
0x180012735  mov     rcx, [rbp+hObject]; hObject
0x180012739  test    rcx, rcx
0x18001273c  jz      short loc_180012744
0x18001273e  call    cs:__imp_CloseHandle
0x180012744  test    ebx, ebx
0x180012746  js      short loc_180012768
0x180012748  mov     rcx, [r14]; Sid
0x18001274b  mov     rdx, r15; StringSid
0x18001274e  call    cs:__imp_ConvertSidToStringSidW
0x180012754  test    eax, eax
0x180012756  jnz     short loc_18001275F
0x180012758  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001275d  mov     ebx, eax
0x18001275f  mov     rcx, r14; hMem
0x180012762  call    cs:__imp_LocalFree
0x180012768  mov     eax, ebx
0x18001276a  mov     rbx, [rsp+30h+arg_18]
0x18001276f  add     rsp, 30h
0x180012773  pop     r15
0x180012775  pop     r14
0x180012777  pop     rdi
0x180012778  pop     rsi
0x180012779  pop     rbp
0x18001277a  retn
```
