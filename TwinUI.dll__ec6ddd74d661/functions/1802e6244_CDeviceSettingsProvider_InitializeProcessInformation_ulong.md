# CDeviceSettingsProvider::InitializeProcessInformation(ulong)

- ea: `0x1802e6244`
- end: `0x1802e6447`
- name: `?InitializeProcessInformation@CDeviceSettingsProvider@@AEAAJK@Z`
- size: `515`
- prototype: `int(CDeviceSettingsProvider *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1802e618c`

## callees

- `0x18010e138`
- `0x18018e5b4`
- `0x1802e6244`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802e62e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802e62f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802e6367`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802e63ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802e62e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802e62f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802e6367`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802e63ce`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1802e6297`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1802e6297`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802e638b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802e639f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802e638b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802e639f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802e6419`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802e642d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802e6419`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802e642d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1802e6323`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1802e6323`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802e62d1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802e6357`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802e62d1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802e6357`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1802e6264`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1802e6264`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1802e63be`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1802e63be`

## pseudocode

```c
__int64 __fastcall CDeviceSettingsProvider::InitializeProcessInformation(CDeviceSettingsProvider *this, DWORD a2)
{
  signed int Error; // ebx
  HANDLE v4; // rsi
  PSID *v5; // rdi
  signed int LastError; // eax
  signed int v7; // eax
  signed int v8; // eax
  LPWSTR v9; // rax
  void *TokenHandle; // [rsp+60h] [rbp+30h] BYREF
  DWORD TokenInformationLength; // [rsp+68h] [rbp+38h] BYREF
  LPWSTR StringSid; // [rsp+70h] [rbp+40h] BYREF

  *((_DWORD *)this + 8) = a2;
  Error = 0;
  v4 = OpenProcess(0x400u, 0, a2);
  if ( !v4 )
    Error = ResultFromLastError();
  TokenHandle = 0;
  if ( Error >= 0 && !OpenProcessToken(v4, 8u, &TokenHandle) )
    Error = ResultFromLastError();
  v5 = 0;
  if ( Error >= 0 )
  {
    TokenInformationLength = 0;
    if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, 0, 0, &TokenInformationLength) || GetLastError() == 122 )
      goto LABEL_12;
    LastError = GetLastError();
    Error = LastError;
    if ( LastError > 0 )
      Error = (unsigned __int16)LastError | 0x80070000;
    if ( Error >= 0 )
    {
LABEL_12:
      if ( TokenInformationLength > 8 )
      {
        v5 = (PSID *)LocalAlloc(0, TokenInformationLength);
        if ( v5 )
        {
          if ( !GetTokenInformation(
                  TokenHandle,
                  TokenAppContainerSid,
                  v5,
                  TokenInformationLength,
                  &TokenInformationLength) )
          {
            v7 = GetLastError();
            Error = v7;
            if ( v7 > 0 )
              Error = (unsigned __int16)v7 | 0x80070000;
          }
        }
        else
        {
          Error = -2147024882;
        }
      }
      else
      {
        Error = -2147024809;
      }
    }
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v4 )
    CloseHandle(v4);
  StringSid = 0;
  if ( Error >= 0 )
  {
    if ( ConvertSidToStringSidW(*v5, &StringSid) )
      goto LABEL_29;
    v8 = GetLastError();
    Error = v8;
    if ( v8 > 0 )
      Error = (unsigned __int16)v8 | 0x80070000;
    if ( Error >= 0 )
    {
LABEL_29:
      v9 = StringSid;
      if ( !StringSid )
      {
        Error = -2147467261;
LABEL_32:
        if ( v9 )
          LocalFree(v9);
        goto LABEL_34;
      }
      Error = Windows::Internal::String::_InitializeHelper((HSTRING *)this + 3, StringSid);
    }
    v9 = StringSid;
    goto LABEL_32;
  }
LABEL_34:
  if ( v5 )
    LocalFree(v5);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1802e6244  push    rbp
0x1802e6246  push    rbx
0x1802e6247  push    rsi
0x1802e6248  push    rdi
0x1802e6249  push    r14
0x1802e624b  mov     rbp, rsp
0x1802e624e  sub     rsp, 30h
0x1802e6252  mov     [rcx+20h], edx
0x1802e6255  mov     r14, rcx
0x1802e6258  mov     r8d, edx; dwProcessId
0x1802e625b  mov     ecx, 400h; dwDesiredAccess
0x1802e6260  xor     edx, edx; bInheritHandle
0x1802e6262  xor     ebx, ebx
0x1802e6264  call    cs:__imp_OpenProcess
0x1802e626b  nop     dword ptr [rax+rax+00h]
0x1802e6270  mov     rsi, rax
0x1802e6273  test    rax, rax
0x1802e6276  jnz     short loc_1802E627F
0x1802e6278  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1802e627d  mov     ebx, eax
0x1802e627f  mov     [rbp+TokenHandle], 0
0x1802e6287  test    ebx, ebx
0x1802e6289  js      short loc_1802E62AE
0x1802e628b  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1802e628f  mov     edx, 8; DesiredAccess
0x1802e6294  mov     rcx, rsi; ProcessHandle
0x1802e6297  call    cs:__imp_OpenProcessToken
0x1802e629e  nop     dword ptr [rax+rax+00h]
0x1802e62a3  test    eax, eax
0x1802e62a5  jnz     short loc_1802E62AE
0x1802e62a7  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1802e62ac  mov     ebx, eax
0x1802e62ae  xor     edi, edi
0x1802e62b0  test    ebx, ebx
0x1802e62b2  js      loc_1802E6382
0x1802e62b8  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1802e62bc  lea     rax, [rbp+TokenInformationLength]
0x1802e62c0  xor     r9d, r9d; TokenInformationLength
0x1802e62c3  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1802e62c8  xor     r8d, r8d; TokenInformation
0x1802e62cb  mov     [rbp+TokenInformationLength], edi
0x1802e62ce  lea     edx, [rdi+1Fh]; TokenInformationClass
0x1802e62d1  call    cs:__imp_GetTokenInformation
0x1802e62d8  nop     dword ptr [rax+rax+00h]
0x1802e62dd  test    eax, eax
0x1802e62df  jnz     short loc_1802E6311
0x1802e62e1  call    cs:__imp_GetLastError
0x1802e62e8  nop     dword ptr [rax+rax+00h]
0x1802e62ed  cmp     eax, 7Ah ; 'z'
0x1802e62f0  jz      short loc_1802E6311
0x1802e62f2  call    cs:__imp_GetLastError
0x1802e62f9  nop     dword ptr [rax+rax+00h]
0x1802e62fe  mov     ebx, eax
0x1802e6300  test    eax, eax
0x1802e6302  jle     short loc_1802E630D
0x1802e6304  movzx   ebx, ax
0x1802e6307  or      ebx, 80070000h
0x1802e630d  test    ebx, ebx
0x1802e630f  js      short loc_1802E6382
0x1802e6311  cmp     [rbp+TokenInformationLength], 8
0x1802e6315  ja      short loc_1802E631E
0x1802e6317  mov     ebx, 80070057h
0x1802e631c  jmp     short loc_1802E6382
0x1802e631e  mov     edx, [rbp+TokenInformationLength]; uBytes
0x1802e6321  xor     ecx, ecx; uFlags
0x1802e6323  call    cs:__imp_LocalAlloc
0x1802e632a  nop     dword ptr [rax+rax+00h]
0x1802e632f  mov     rdi, rax
0x1802e6332  test    rax, rax
0x1802e6335  jnz     short loc_1802E633E
0x1802e6337  mov     ebx, 8007000Eh
0x1802e633c  jmp     short loc_1802E6382
0x1802e633e  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1802e6342  lea     rax, [rbp+TokenInformationLength]
0x1802e6346  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1802e634a  mov     r8, rdi; TokenInformation
0x1802e634d  mov     edx, 1Fh; TokenInformationClass
0x1802e6352  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1802e6357  call    cs:__imp_GetTokenInformation
0x1802e635e  nop     dword ptr [rax+rax+00h]
0x1802e6363  test    eax, eax
0x1802e6365  jnz     short loc_1802E6382
0x1802e6367  call    cs:__imp_GetLastError
0x1802e636e  nop     dword ptr [rax+rax+00h]
0x1802e6373  mov     ebx, eax
0x1802e6375  test    eax, eax
0x1802e6377  jle     short loc_1802E6382
0x1802e6379  movzx   ebx, ax
0x1802e637c  or      ebx, 80070000h
0x1802e6382  mov     rcx, [rbp+TokenHandle]; hObject
0x1802e6386  test    rcx, rcx
0x1802e6389  jz      short loc_1802E6397
0x1802e638b  call    cs:__imp_CloseHandle
0x1802e6392  nop     dword ptr [rax+rax+00h]
0x1802e6397  test    rsi, rsi
0x1802e639a  jz      short loc_1802E63AB
0x1802e639c  mov     rcx, rsi; hObject
0x1802e639f  call    cs:__imp_CloseHandle
0x1802e63a6  nop     dword ptr [rax+rax+00h]
0x1802e63ab  mov     [rbp+StringSid], 0
0x1802e63b3  test    ebx, ebx
0x1802e63b5  js      short loc_1802E6425
0x1802e63b7  mov     rcx, [rdi]; Sid
0x1802e63ba  lea     rdx, [rbp+StringSid]; StringSid
0x1802e63be  call    cs:__imp_ConvertSidToStringSidW
0x1802e63c5  nop     dword ptr [rax+rax+00h]
0x1802e63ca  test    eax, eax
0x1802e63cc  jnz     short loc_1802E63F3
0x1802e63ce  call    cs:__imp_GetLastError
0x1802e63d5  nop     dword ptr [rax+rax+00h]
0x1802e63da  mov     ebx, eax
0x1802e63dc  test    eax, eax
0x1802e63de  jle     short loc_1802E63E9
0x1802e63e0  movzx   ebx, ax
0x1802e63e3  or      ebx, 80070000h
0x1802e63e9  test    ebx, ebx
0x1802e63eb  jns     short loc_1802E63F3
0x1802e63ed  mov     rax, [rbp+StringSid]
0x1802e63f1  jmp     short loc_1802E6411
0x1802e63f3  mov     rax, [rbp+StringSid]
0x1802e63f7  test    rax, rax
0x1802e63fa  jz      short loc_1802E640C
0x1802e63fc  lea     rcx, [r14+18h]; this
0x1802e6400  mov     rdx, rax; unsigned __int16 *
0x1802e6403  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x1802e6408  mov     ebx, eax
0x1802e640a  jmp     short loc_1802E63ED
0x1802e640c  mov     ebx, 80004003h
0x1802e6411  test    rax, rax
0x1802e6414  jz      short loc_1802E6425
0x1802e6416  mov     rcx, rax; hMem
0x1802e6419  call    cs:__imp_LocalFree
0x1802e6420  nop     dword ptr [rax+rax+00h]
0x1802e6425  test    rdi, rdi
0x1802e6428  jz      short loc_1802E6439
0x1802e642a  mov     rcx, rdi; hMem
0x1802e642d  call    cs:__imp_LocalFree
0x1802e6434  nop     dword ptr [rax+rax+00h]
0x1802e6439  mov     eax, ebx
0x1802e643b  add     rsp, 30h
0x1802e643f  pop     r14
0x1802e6441  pop     rdi
0x1802e6442  pop     rsi
0x1802e6443  pop     rbx
0x1802e6444  pop     rbp
0x1802e6445  retn
```
