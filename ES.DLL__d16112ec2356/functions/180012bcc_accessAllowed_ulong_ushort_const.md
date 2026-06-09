# accessAllowed(ulong,ushort const *)

- ea: `0x180012bcc`
- end: `0x180012dd1`
- name: `?accessAllowed@@YA_NKPEBG@Z`
- size: `517`
- prototype: `bool __fastcall(unsigned int, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011a30`
- `0x180012380`
- `0x180012700`
- `0x180013000`

## callees

- `0x180003d54`
- `0x180008938`
- `0x180009034`
- `0x180012bcc`
- `0x1800161ec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012bfc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012bfc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180012c13`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180012c13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012db2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004425e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012db2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004425e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012cd5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012cd5`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180012c6b`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180012c6b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180012c1b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180012c1b`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180012bf2`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180012bf2`

## string_xrefs

- `0x180012cfe`: `com\complus\src\events\tier2\security.cpp`
- `0x180012d20`: `com\complus\src\events\tier2\security.cpp`
- `0x180012d3e`: `com\complus\src\events\tier2\security.cpp`
- `0x180012d5c`: `com\complus\src\events\tier2\security.cpp`
- `0x180012d97`: `com\complus\src\events\tier2\security.cpp`
- `0x180012d15`: `OpenThreadToken`

## pseudocode

```c
bool __fastcall accessAllowed(char a1, char *a2)
{
  HRESULT v4; // eax
  HANDLE CurrentThread; // rax
  BOOL v6; // ebx
  signed int LastError; // eax
  bool v8; // sf
  LPWSTR TokenSID; // rbx
  LPWSTR v10; // rcx
  char *v11; // rsi
  int v12; // edx
  int v13; // eax
  int v14; // r9d
  WINBOOL IsMember; // [rsp+40h] [rbp+18h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+20h] BYREF

  TokenHandle = 0;
  IsMember = 0;
  v4 = CoImpersonateClient();
  if ( v4 >= 0 )
  {
    CurrentThread = GetCurrentThread();
    v6 = OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle);
    CoRevertToSelf();
    if ( !v6 )
      InternalError_Win32(L"com\\complus\\src\\events\\tier2\\security.cpp", 0x14u, 0x11u, L"OpenThreadToken");
    v4 = 0;
  }
  if ( !TokenHandle )
  {
    v14 = 0;
    if ( v4 != -2147417833 )
      v14 = v4;
    if ( v14 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier2\\security.cpp", 0x49u, 0x11u, v14);
    goto LABEL_9;
  }
  if ( v4 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier2\\security.cpp", 0x4Eu, 0x11u, v4);
  if ( (a1 & 6) == 0 )
  {
LABEL_9:
    IsMember = 1;
    goto LABEL_31;
  }
  IsMember = 0;
  if ( CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) )
  {
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
    v8 = LastError < 0;
    if ( LastError <= 0 )
      goto LABEL_13;
    LastError = (unsigned __int16)LastError | 0x80070000;
  }
  v8 = LastError < 0;
LABEL_13:
  if ( v8 )
    InternalError_HR(L"com\\complus\\src\\events\\tier2\\security.cpp", 0x58u, 0x11u, LastError);
  if ( !IsMember && a2 )
  {
    TokenSID = GetTokenSID(TokenHandle);
    if ( !TokenSID )
      InternalError(L"com\\complus\\src\\events\\tier2\\security.cpp", 0x5Eu, 0x80001203, 0x11u);
    v10 = TokenSID;
    v11 = (char *)(a2 - (char *)TokenSID);
    do
    {
      v12 = *(unsigned __int16 *)&v11[(_QWORD)v10];
      v13 = *v10 - v12;
      if ( v13 )
        break;
      ++v10;
    }
    while ( v12 );
    if ( !v13 )
      IsMember = 1;
    LocalFree(TokenSID);
  }
LABEL_31:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return IsMember != 0;
}

```

## disassembly

```asm
0x180012bcc  mov     rax, rsp
0x180012bcf  mov     [rax+8], rbx
0x180012bd3  mov     [rax+10h], rsi
0x180012bd7  push    r14
0x180012bd9  sub     rsp, 20h
0x180012bdd  mov     rsi, rdx
0x180012be0  mov     r14d, ecx
0x180012be3  mov     qword ptr [rax+20h], 0
0x180012beb  mov     dword ptr [rax+18h], 0
0x180012bf2  call    cs:__imp_CoImpersonateClient
0x180012bf8  test    eax, eax
0x180012bfa  js      short loc_180012C2B
0x180012bfc  call    cs:__imp_GetCurrentThread
0x180012c02  mov     rcx, rax; ThreadHandle
0x180012c05  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180012c0a  mov     edx, 8; DesiredAccess
0x180012c0f  lea     r8d, [rdx-7]; OpenAsSelf
0x180012c13  call    cs:__imp_OpenThreadToken
0x180012c19  mov     ebx, eax
0x180012c1b  call    cs:__imp_CoRevertToSelf
0x180012c21  test    ebx, ebx
0x180012c23  jz      loc_180012D0F
0x180012c29  xor     eax, eax
0x180012c2b  cmp     [rsp+28h+TokenHandle], 0
0x180012c31  jz      loc_180012CE0
0x180012c37  test    eax, eax
0x180012c39  js      loc_180012D31
0x180012c3f  test    r14b, 6
0x180012c43  jnz     short loc_180012C52
0x180012c45  mov     [rsp+28h+IsMember], 1
0x180012c4d  jmp     loc_180012DA8
0x180012c52  mov     [rsp+28h+IsMember], 0
0x180012c5a  lea     r8, [rsp+28h+IsMember]; IsMember
0x180012c5f  mov     rdx, cs:SidToCheck; SidToCheck
0x180012c66  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x180012c6b  call    cs:__imp_CheckTokenMembership
0x180012c71  test    eax, eax
0x180012c73  jz      loc_180012D6D
0x180012c79  xor     eax, eax
0x180012c7b  test    eax, eax
0x180012c7d  js      loc_180012D4F
0x180012c83  cmp     [rsp+28h+IsMember], 0
0x180012c88  jnz     loc_180012DA8
0x180012c8e  test    rsi, rsi
0x180012c91  jz      loc_180012DA8
0x180012c97  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x180012c9c  call    ?GetTokenSID@@YAPEAGPEAX@Z; GetTokenSID(void *)
0x180012ca1  mov     rbx, rax
0x180012ca4  test    rax, rax
0x180012ca7  jz      loc_180012D88
0x180012cad  mov     rcx, rbx
0x180012cb0  sub     rsi, rbx
0x180012cb3  movzx   eax, word ptr [rcx]
0x180012cb6  movzx   edx, word ptr [rcx+rsi]
0x180012cba  sub     eax, edx
0x180012cbc  jnz     short loc_180012CC6
0x180012cbe  add     rcx, 2
0x180012cc2  test    edx, edx
0x180012cc4  jnz     short loc_180012CB3
0x180012cc6  test    eax, eax
0x180012cc8  jnz     short loc_180012CD2
0x180012cca  mov     [rsp+28h+IsMember], 1
0x180012cd2  mov     rcx, rbx; hMem
0x180012cd5  call    cs:__imp_LocalFree
0x180012cdb  jmp     loc_180012DA8
0x180012ce0  xor     r9d, r9d
0x180012ce3  cmp     eax, 80010117h
0x180012ce8  cmovnz  r9d, eax; int
0x180012cec  test    r9d, r9d
0x180012cef  jns     loc_180012C45
0x180012cf5  mov     edx, 49h ; 'I'; unsigned int
0x180012cfa  lea     r8d, [rdx-38h]; unsigned __int16
0x180012cfe  lea     rcx, aComComplusSrcE_20; "com\\complus\\src\\events\\tier2\\secur"...
0x180012d05  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180012d0a  jmp     loc_180012C45
0x180012d0f  mov     r8d, 11h; unsigned __int16
0x180012d15  lea     r9, aOpenthreadtoke; "OpenThreadToken"
0x180012d1c  lea     edx, [r8+3]; unsigned int
0x180012d20  lea     rcx, aComComplusSrcE_20; "com\\complus\\src\\events\\tier2\\secur"...
0x180012d27  call    ?InternalError_Win32@@YA_NPEBGKG0@Z; InternalError_Win32(ushort const *,ulong,ushort,ushort const *)
0x180012d2c  jmp     loc_180012C29
0x180012d31  mov     r8d, 11h; unsigned __int16
0x180012d37  mov     r9d, eax; int
0x180012d3a  lea     edx, [r8+3Dh]; unsigned int
0x180012d3e  lea     rcx, aComComplusSrcE_20; "com\\complus\\src\\events\\tier2\\secur"...
0x180012d45  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180012d4a  jmp     loc_180012C3F
0x180012d4f  mov     r8d, 11h; unsigned __int16
0x180012d55  mov     r9d, eax; int
0x180012d58  lea     edx, [r8+47h]; unsigned int
0x180012d5c  lea     rcx, aComComplusSrcE_20; "com\\complus\\src\\events\\tier2\\secur"...
0x180012d63  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180012d68  jmp     loc_180012C83
0x180012d6d  call    cs:__imp_GetLastError
0x180012d73  test    eax, eax
0x180012d75  jle     loc_180012C7D
0x180012d7b  movzx   eax, ax
0x180012d7e  or      eax, 80070000h
0x180012d83  jmp     loc_180012C7B
0x180012d88  mov     edx, 5Eh ; '^'; unsigned int
0x180012d8d  lea     r9d, [rdx-4Dh]; unsigned __int16
0x180012d91  mov     r8d, 80001203h; unsigned int
0x180012d97  lea     rcx, aComComplusSrcE_20; "com\\complus\\src\\events\\tier2\\secur"...
0x180012d9e  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180012da3  jmp     loc_180012CAD
0x180012da8  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180012dad  test    rcx, rcx
0x180012db0  jz      short loc_180012DB8
0x180012db2  call    cs:__imp_CloseHandle
0x180012db8  cmp     [rsp+28h+IsMember], 0
0x180012dbd  setnz   al
0x180012dc0  mov     rbx, [rsp+28h+arg_0]
0x180012dc5  mov     rsi, [rsp+28h+arg_8]
0x180012dca  add     rsp, 20h
0x180012dce  pop     r14
0x180012dd0  retn
0x18004424c  push    rbp
0x18004424e  sub     rsp, 20h
0x180044252  mov     rbp, rdx
0x180044255  mov     rcx, [rbp+48h]; hObject
0x180044259  test    rcx, rcx
0x18004425c  jz      short loc_180044265
0x18004425e  call    cs:__imp_CloseHandle
0x180044264  nop
0x180044265  add     rsp, 20h
0x180044269  pop     rbp
0x18004426a  retn
```
