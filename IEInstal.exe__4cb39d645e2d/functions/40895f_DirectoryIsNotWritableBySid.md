# DirectoryIsNotWritableBySid

- ea: `0x40895f`
- end: `0x408a29`
- name: `DirectoryIsNotWritableBySid`
- size: `202`
- prototype: `int __thiscall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x408a2f`

## callees

- `0x40865e`
- `0x408841`
- `0x40895f`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x408a1c`
- `KERNEL32!CloseHandle` at `0x408a1c`
- `KERNEL32!LocalFree` at `0x408a15`
- `KERNEL32!LocalFree` at `0x408a15`
- `KERNEL32!CreateFileW` at `0x408981`
- `KERNEL32!CreateFileW` at `0x408981`
- `AUTHZ!AuthzFreeContext` at `0x4089fd`
- `AUTHZ!AuthzFreeContext` at `0x4089fd`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x4089e3`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x4089e3`
- `AUTHZ!AuthzInitializeResourceManager` at `0x4089b9`
- `AUTHZ!AuthzInitializeResourceManager` at `0x4089b9`
- `AUTHZ!AuthzFreeResourceManager` at `0x408a0e`
- `AUTHZ!AuthzFreeResourceManager` at `0x408a0e`

## pseudocode

```c
int __thiscall DirectoryIsNotWritableBySid(LPCWSTR lpFileName)
{
  HANDLE FileW; // eax
  void *v2; // esi

  FileW = CreateFileW(lpFileName, 0x20000u, 0, 0, 3u, 0x2000000u, 0);
  v2 = FileW;
  if ( FileW != (HANDLE)-1 )
  {
    GetSecurityDescriptor(FileW);
    CloseHandle(v2);
  }
  return 0;
}

```

## disassembly

```asm
0x40895f  mov     edi, edi
0x408961  push    ebp
0x408962  mov     ebp, esp
0x408964  sub     esp, 1Ch
0x408967  push    ebx
0x408968  push    esi
0x408969  push    edi
0x40896a  xor     edi, edi
0x40896c  mov     [ebp+UserSid], edx
0x40896f  push    edi; hTemplateFile
0x408970  push    2000000h; dwFlagsAndAttributes
0x408975  push    3; dwCreationDisposition
0x408977  push    edi; lpSecurityAttributes
0x408978  push    edi; dwShareMode
0x408979  push    20000h; dwDesiredAccess
0x40897e  push    ecx; lpFileName
0x40897f  mov     ebx, edi
0x408981  call    ds:__imp__CreateFileW@28; CreateFileW(x,x,x,x,x,x,x)
0x408987  mov     esi, eax
0x408989  mov     [ebp+var_10], esi
0x40898c  cmp     esi, 0FFFFFFFFh
0x40898f  jz      loc_408A22
0x408995  lea     edx, [ebp+phAuthzClientContext]
0x408998  mov     [ebp+phAuthzClientContext], edi
0x40899b  mov     ecx, esi; Handle
0x40899d  call    GetSecurityDescriptor
0x4089a2  test    eax, eax
0x4089a4  js      short loc_408A1B
0x4089a6  mov     edi, [ebp+phAuthzClientContext]
0x4089a9  test    edi, edi
0x4089ab  jz      short loc_408A1B
0x4089ad  lea     eax, [ebp+phAuthzResourceManager]
0x4089b0  push    eax; phAuthzResourceManager
0x4089b1  xor     eax, eax
0x4089b3  push    eax; szResourceManagerName
0x4089b4  push    eax; pfnFreeDynamicGroups
0x4089b5  push    eax; pfnComputeDynamicGroups
0x4089b6  push    eax; pfnDynamicAccessCheck
0x4089b7  push    1; Flags
0x4089b9  call    ds:__imp__AuthzInitializeResourceManager@24; AuthzInitializeResourceManager(x,x,x,x,x,x)
0x4089bf  test    eax, eax
0x4089c1  jz      short loc_408A14
0x4089c3  xor     ecx, ecx
0x4089c5  lea     eax, [ebp+phAuthzClientContext]
0x4089c8  push    eax; phAuthzClientContext
0x4089c9  push    ecx; DynamicGroupArgs
0x4089ca  xorps   xmm0, xmm0
0x4089cd  mov     [ebp+phAuthzClientContext], ecx
0x4089d0  movlpd  qword ptr [ebp+Identifier.LowPart], xmm0
0x4089d5  push    [ebp+Identifier.HighPart]
0x4089d8  push    [ebp+Identifier.LowPart]; Identifier
0x4089db  push    ecx; pExpirationTime
0x4089dc  push    [ebp+phAuthzResourceManager]; hAuthzResourceManager
0x4089df  push    [ebp+UserSid]; UserSid
0x4089e2  push    ecx; Flags
0x4089e3  call    ds:__imp__AuthzInitializeContextFromSid@32; AuthzInitializeContextFromSid(x,x,x,x,x,x,x,x)
0x4089e9  test    eax, eax
0x4089eb  jz      short loc_408A0B
0x4089ed  push    ecx; int
0x4089ee  mov     ecx, [ebp+phAuthzClientContext]; hAuthzClientContext
0x4089f1  mov     edx, edi; pSecurityDescriptor
0x4089f3  call    PrincipalHasWriteAccess
0x4089f8  push    [ebp+phAuthzClientContext]; hAuthzClientContext
0x4089fb  mov     esi, eax
0x4089fd  call    ds:__imp__AuthzFreeContext@4; AuthzFreeContext(x)
0x408a03  test    esi, esi
0x408a05  mov     esi, [ebp+var_10]
0x408a08  setz    bl
0x408a0b  push    [ebp+phAuthzResourceManager]; hAuthzResourceManager
0x408a0e  call    ds:__imp__AuthzFreeResourceManager@4; AuthzFreeResourceManager(x)
0x408a14  push    edi; hMem
0x408a15  call    ds:__imp__LocalFree@4; LocalFree(x)
0x408a1b  push    esi; hObject
0x408a1c  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x408a22  pop     edi
0x408a23  pop     esi
0x408a24  mov     eax, ebx
0x408a26  pop     ebx
0x408a27  leave
0x408a28  retn
```
