# DoesUserHavePrivilege(ushort const *)

- ea: `0x180005eec`
- end: `0x180005ffd`
- name: `?DoesUserHavePrivilege@@YAHPEBG@Z`
- size: `273`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180007888`
- `0x180007aa0`

## callees

- `0x180005eec`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x180005f12`
- `KERNEL32!GetCurrentProcess` at `0x180005f12`
- `KERNEL32!GetLastError` at `0x180005f58`
- `KERNEL32!GetLastError` at `0x180005f58`
- `KERNEL32!CloseHandle` at `0x180005fed`
- `KERNEL32!CloseHandle` at `0x180005fed`
- `KERNEL32!LocalFree` at `0x180005fe3`
- `KERNEL32!LocalFree` at `0x180005fe3`
- `KERNEL32!LocalAlloc` at `0x180005f6d`
- `KERNEL32!LocalAlloc` at `0x180005f6d`
- `ADVAPI32!LookupPrivilegeValueW` at `0x180005fa9`
- `ADVAPI32!LookupPrivilegeValueW` at `0x180005fa9`
- `ADVAPI32!OpenProcessToken` at `0x180005f24`
- `ADVAPI32!OpenProcessToken` at `0x180005f24`
- `ADVAPI32!GetTokenInformation` at `0x180005f4a`
- `ADVAPI32!GetTokenInformation` at `0x180005f92`
- `ADVAPI32!GetTokenInformation` at `0x180005f4a`
- `ADVAPI32!GetTokenInformation` at `0x180005f92`

## string_xrefs

- `0x180005fa2`: `SeLoadDriverPrivilege`

## pseudocode

```c
BOOL __fastcall DoesUserHavePrivilege(const unsigned __int16 *a1)
{
  HANDLE CurrentProcess; // rax
  BOOL result; // eax
  int v3; // edi
  _DWORD *v4; // rbx
  __int64 v5; // rdx
  DWORD TokenInformationLength; // [rsp+50h] [rbp+20h] BYREF
  int v7; // [rsp+54h] [rbp+24h]
  void *TokenHandle; // [rsp+58h] [rbp+28h] BYREF
  _LUID Luid; // [rsp+60h] [rbp+30h] BYREF

  v7 = HIDWORD(a1);
  TokenHandle = 0;
  TokenInformationLength = 0;
  Luid = 0;
  CurrentProcess = GetCurrentProcess();
  result = OpenProcessToken(CurrentProcess, 8u, &TokenHandle);
  if ( result )
  {
    v3 = 0;
    if ( !GetTokenInformation(TokenHandle, TokenPrivileges, 0, 0, &TokenInformationLength) && GetLastError() == 122 )
    {
      v4 = LocalAlloc(0x40u, TokenInformationLength);
      if ( v4 )
      {
        if ( GetTokenInformation(TokenHandle, TokenPrivileges, v4, TokenInformationLength, &TokenInformationLength) )
        {
          if ( LookupPrivilegeValueW(0, L"SeLoadDriverPrivilege", &Luid) )
          {
            v5 = 0;
            if ( *v4 )
            {
              while ( Luid.LowPart != v4[3 * v5 + 1] || Luid.HighPart != v4[3 * v5 + 2] )
              {
                v5 = (unsigned int)(v5 + 1);
                if ( (unsigned int)v5 >= *v4 )
                  goto LABEL_13;
              }
              v3 = 1;
            }
          }
        }
LABEL_13:
        LocalFree(v4);
      }
    }
    CloseHandle(TokenHandle);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x180005eec  mov     qword ptr [rsp-18h+TokenInformationLength], rcx
0x180005ef1  push    rbp
0x180005ef2  push    rbx
0x180005ef3  push    rdi
0x180005ef4  mov     rbp, rsp
0x180005ef7  sub     rsp, 30h
0x180005efb  mov     [rbp+TokenHandle], 0
0x180005f03  mov     [rbp+TokenInformationLength], 0
0x180005f0a  mov     qword ptr [rbp+Luid.LowPart], 0
0x180005f12  call    cs:__imp_GetCurrentProcess
0x180005f18  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180005f1c  mov     edx, 8; DesiredAccess
0x180005f21  mov     rcx, rax; ProcessHandle
0x180005f24  call    cs:__imp_OpenProcessToken
0x180005f2a  test    eax, eax
0x180005f2c  jz      loc_180005FF5
0x180005f32  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180005f36  lea     rax, [rbp+TokenInformationLength]
0x180005f3a  xor     edi, edi
0x180005f3c  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180005f41  xor     r9d, r9d; TokenInformationLength
0x180005f44  xor     r8d, r8d; TokenInformation
0x180005f47  lea     edx, [rdi+3]; TokenInformationClass
0x180005f4a  call    cs:__imp_GetTokenInformation
0x180005f50  test    eax, eax
0x180005f52  jnz     loc_180005FE9
0x180005f58  call    cs:__imp_GetLastError
0x180005f5e  cmp     eax, 7Ah ; 'z'
0x180005f61  jnz     loc_180005FE9
0x180005f67  mov     edx, [rbp+TokenInformationLength]; uBytes
0x180005f6a  lea     ecx, [rdi+40h]; uFlags
0x180005f6d  call    cs:__imp_LocalAlloc
0x180005f73  mov     rbx, rax
0x180005f76  test    rax, rax
0x180005f79  jz      short loc_180005FE9
0x180005f7b  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180005f7f  lea     rax, [rbp+TokenInformationLength]
0x180005f83  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180005f87  lea     edx, [rdi+3]; TokenInformationClass
0x180005f8a  mov     r8, rbx; TokenInformation
0x180005f8d  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180005f92  call    cs:__imp_GetTokenInformation
0x180005f98  test    eax, eax
0x180005f9a  jz      short loc_180005FE0
0x180005f9c  lea     r8, [rbp+Luid]; lpLuid
0x180005fa0  xor     ecx, ecx; lpSystemName
0x180005fa2  lea     rdx, aSeloaddriverpr; "SeLoadDriverPrivilege"
0x180005fa9  call    cs:__imp_LookupPrivilegeValueW
0x180005faf  test    eax, eax
0x180005fb1  jz      short loc_180005FE0
0x180005fb3  xor     edx, edx
0x180005fb5  cmp     [rbx], edx
0x180005fb7  jbe     short loc_180005FE0
0x180005fb9  mov     rax, qword ptr [rbp+Luid.LowPart]
0x180005fbd  mov     r9d, [rbp+Luid.HighPart]
0x180005fc1  lea     r8, [rdx+rdx*2]
0x180005fc5  cmp     eax, [rbx+r8*4+4]
0x180005fca  jnz     short loc_180005FD3
0x180005fcc  cmp     r9d, [rbx+r8*4+8]
0x180005fd1  jz      short loc_180005FDB
0x180005fd3  inc     edx
0x180005fd5  cmp     edx, [rbx]
0x180005fd7  jb      short loc_180005FC1
0x180005fd9  jmp     short loc_180005FE0
0x180005fdb  mov     edi, 1
0x180005fe0  mov     rcx, rbx; hMem
0x180005fe3  call    cs:__imp_LocalFree
0x180005fe9  mov     rcx, [rbp+TokenHandle]; hObject
0x180005fed  call    cs:__imp_CloseHandle
0x180005ff3  mov     eax, edi
0x180005ff5  add     rsp, 30h
0x180005ff9  pop     rdi
0x180005ffa  pop     rbx
0x180005ffb  pop     rbp
0x180005ffc  retn
```
