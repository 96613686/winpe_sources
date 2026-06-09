# BipGetSignedInUserSidForHoloLens

- ea: `0x1800789b8`
- end: `0x180078b40`
- name: `BipGetSignedInUserSidForHoloLens`
- size: `392`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005df20`

## callees

- `0x1800789b8`
- `0x180094662`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180078b23`
- `ntdll!RtlFreeHeap` at `0x180078b23`
- `ntdll!RtlAllocateHeap` at `0x180078a98`
- `ntdll!RtlAllocateHeap` at `0x180078a98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078a69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078a74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078a69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078a74`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180078ad3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180078ad3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180078a5f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180078ac6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180078a5f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180078ac6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180078b0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180078b0c`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x1800789f6`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x1800789f6`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x180078a20`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x180078a20`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x180078afc`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x180078afc`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180078a38`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180078a38`

## pseudocode

```c
__int64 __fastcall BipGetSignedInUserSidForHoloLens(void *a1)
{
  PSID *Heap; // rdi
  signed int v3; // ebx
  int v4; // eax
  signed int LastError; // eax
  DWORD LengthSid; // eax
  _QWORD *v8; // [rsp+30h] [rbp-10h] BYREF
  DWORD TokenInformationLength; // [rsp+68h] [rbp+28h] BYREF
  unsigned int v10; // [rsp+70h] [rbp+30h] BYREF
  HANDLE TokenHandle; // [rsp+78h] [rbp+38h] BYREF

  v8 = 0;
  TokenInformationLength = 0;
  v10 = 0;
  TokenHandle = (HANDLE)-1LL;
  Heap = 0;
  v3 = UMgrEnumerateSessionUsers(&v10, &v8);
  if ( v3 < 0 )
    goto LABEL_19;
  if ( v10 > 1 )
  {
    v3 = -2147418113;
    goto LABEL_19;
  }
  if ( !v10 )
  {
    v4 = UMgrQueryDefaultAccountToken(&TokenHandle);
    goto LABEL_8;
  }
  if ( v10 == 1 )
  {
    v4 = UMgrQueryUserToken(*v8, &TokenHandle);
LABEL_8:
    v3 = v4;
    if ( v4 < 0 )
      goto LABEL_19;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) && GetLastError() != 122 )
    goto LABEL_11;
  Heap = (PSID *)RtlAllocateHeap(BipHeap, 0, TokenInformationLength);
  if ( !Heap )
  {
    v3 = -2147024882;
    goto LABEL_19;
  }
  if ( GetTokenInformation(TokenHandle, TokenUser, Heap, TokenInformationLength, &TokenInformationLength) )
  {
    LengthSid = GetLengthSid(*Heap);
    if ( LengthSid <= 0x44 )
      memcpy_0(a1, *Heap, LengthSid);
    else
      v3 = -2147024774;
  }
  else
  {
LABEL_11:
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_19:
  if ( v8 )
    UMgrFreeSessionUsers();
  if ( TokenHandle != (HANDLE)-1LL )
    CloseHandle(TokenHandle);
  if ( Heap )
    RtlFreeHeap(BipHeap, 0, Heap);
  return v3 & 0xAFFFFFFF | 0x40000000;
}

```

## disassembly

```asm
0x1800789b8  mov     [rsp-18h+arg_0], rbx
0x1800789bd  mov     [rsp-18h+TokenInformationLength], edx
0x1800789c1  push    rbp
0x1800789c2  push    rsi
0x1800789c3  push    rdi
0x1800789c4  mov     rbp, rsp
0x1800789c7  sub     rsp, 40h
0x1800789cb  mov     rsi, rcx
0x1800789ce  mov     [rbp+var_10], 0
0x1800789d6  lea     rcx, [rbp+arg_10]
0x1800789da  mov     [rbp+TokenInformationLength], 0
0x1800789e1  lea     rdx, [rbp+var_10]
0x1800789e5  mov     [rbp+arg_10], 0
0x1800789ec  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1800789f4  xor     edi, edi
0x1800789f6  call    cs:__imp_UMgrEnumerateSessionUsers
0x1800789fc  mov     ebx, eax
0x1800789fe  test    eax, eax
0x180078a00  js      loc_180078AF3
0x180078a06  mov     eax, [rbp+arg_10]
0x180078a09  cmp     eax, 1
0x180078a0c  jbe     short loc_180078A18
0x180078a0e  mov     ebx, 8000FFFFh
0x180078a13  jmp     loc_180078AF3
0x180078a18  test    eax, eax
0x180078a1a  jnz     short loc_180078A28
0x180078a1c  lea     rcx, [rbp+TokenHandle]
0x180078a20  call    cs:__imp_UMgrQueryDefaultAccountToken
0x180078a26  jmp     short loc_180078A3E
0x180078a28  cmp     eax, 1
0x180078a2b  jnz     short loc_180078A48
0x180078a2d  mov     rcx, [rbp+var_10]
0x180078a31  lea     rdx, [rbp+TokenHandle]
0x180078a35  mov     rcx, [rcx]
0x180078a38  call    cs:__imp_UMgrQueryUserToken
0x180078a3e  mov     ebx, eax
0x180078a40  test    eax, eax
0x180078a42  js      loc_180078AF3
0x180078a48  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180078a4c  lea     rax, [rbp+TokenInformationLength]
0x180078a50  xor     r9d, r9d; TokenInformationLength
0x180078a53  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180078a58  xor     r8d, r8d; TokenInformation
0x180078a5b  lea     edx, [r9+1]; TokenInformationClass
0x180078a5f  call    cs:__imp_GetTokenInformation
0x180078a65  test    eax, eax
0x180078a67  jnz     short loc_180078A8B
0x180078a69  call    cs:__imp_GetLastError
0x180078a6f  cmp     eax, 7Ah ; 'z'
0x180078a72  jz      short loc_180078A8B
0x180078a74  call    cs:__imp_GetLastError
0x180078a7a  mov     ebx, eax
0x180078a7c  test    eax, eax
0x180078a7e  jle     short loc_180078AF3
0x180078a80  movzx   ebx, ax
0x180078a83  or      ebx, 80070000h
0x180078a89  jmp     short loc_180078AF3
0x180078a8b  mov     r8d, [rbp+TokenInformationLength]; Size
0x180078a8f  xor     edx, edx; Flags
0x180078a91  mov     rcx, cs:BipHeap; HeapHandle
0x180078a98  call    cs:__imp_RtlAllocateHeap
0x180078a9e  mov     rdi, rax
0x180078aa1  test    rax, rax
0x180078aa4  jnz     short loc_180078AAD
0x180078aa6  mov     ebx, 8007000Eh
0x180078aab  jmp     short loc_180078AF3
0x180078aad  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180078ab1  lea     rax, [rbp+TokenInformationLength]
0x180078ab5  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180078ab9  mov     r8, rdi; TokenInformation
0x180078abc  mov     edx, 1; TokenInformationClass
0x180078ac1  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180078ac6  call    cs:__imp_GetTokenInformation
0x180078acc  test    eax, eax
0x180078ace  jz      short loc_180078A74
0x180078ad0  mov     rcx, [rdi]; pSid
0x180078ad3  call    cs:__imp_GetLengthSid
0x180078ad9  cmp     eax, 44h ; 'D'
0x180078adc  jbe     short loc_180078AE5
0x180078ade  mov     ebx, 8007007Ah
0x180078ae3  jmp     short loc_180078AF3
0x180078ae5  mov     rdx, [rdi]; Src
0x180078ae8  mov     rcx, rsi; void *
0x180078aeb  mov     r8d, eax; Size
0x180078aee  call    memcpy_0
0x180078af3  mov     rcx, [rbp+var_10]
0x180078af7  test    rcx, rcx
0x180078afa  jz      short loc_180078B02
0x180078afc  call    cs:__imp_UMgrFreeSessionUsers
0x180078b02  mov     rcx, [rbp+TokenHandle]; hObject
0x180078b06  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180078b0a  jz      short loc_180078B12
0x180078b0c  call    cs:__imp_CloseHandle
0x180078b12  test    rdi, rdi
0x180078b15  jz      short loc_180078B29
0x180078b17  mov     rcx, cs:BipHeap; HeapHandle
0x180078b1e  mov     r8, rdi; P
0x180078b21  xor     edx, edx; Flags
0x180078b23  call    cs:__imp_RtlFreeHeap
0x180078b29  btr     ebx, 1Ch
0x180078b2d  bts     ebx, 1Eh
0x180078b31  mov     eax, ebx
0x180078b33  mov     rbx, [rsp+40h+arg_0]
0x180078b38  add     rsp, 40h
0x180078b3c  pop     rdi
0x180078b3d  pop     rsi
0x180078b3e  pop     rbp
0x180078b3f  retn
```
