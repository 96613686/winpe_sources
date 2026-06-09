# FileOperationBroker::PerformFileCopy(ushort *,ushort *,tagEdgeBrokerActionAfterCopy,_GUID,ushort const *)

- ea: `0x180028d60`
- end: `0x180028ee0`
- name: `?PerformFileCopy@FileOperationBroker@@UEAAJPEAG0W4tagEdgeBrokerActionAfterCopy@@U_GUID@@PEBG@Z`
- size: `384`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, const WCHAR *, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000e428`
- `0x18002762c`
- `0x180028d60`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180028e44`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180028e56`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180028e44`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180028e56`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180028de7`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180028e12`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180028de7`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180028e12`
- `api-ms-win-core-file-l2-1-0!CopyFile2` at `0x180028dc1`
- `api-ms-win-core-file-l2-1-0!CopyFile2` at `0x180028dc1`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientDecryptFile` at `0x180028eb4`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientDecryptFile` at `0x180028eb4`
- `ext-ms-win-security-efswrt-l1-1-1!ProtectFileToEnterpriseIdentity` at `0x180028ea0`
- `ext-ms-win-security-efswrt-l1-1-1!ProtectFileToEnterpriseIdentity` at `0x180028ea0`

## pseudocode

```c
__int64 __fastcall FileOperationBroker::PerformFileCopy(
        __int64 a1,
        const WCHAR *a2,
        const WCHAR *a3,
        int a4,
        __int64 a5,
        __int64 a6)
{
  int PIC; // ebx
  void *File2; // rax
  int v11; // eax
  union _LARGE_INTEGER v13; // [rsp+30h] [rbp-50h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+38h] [rbp-48h] BYREF
  void **v15; // [rsp+40h] [rbp-40h] BYREF
  HANDLE hFile; // [rsp+48h] [rbp-38h]
  _QWORD v17[2]; // [rsp+50h] [rbp-30h] BYREF
  COPYFILE2_EXTENDED_PARAMETERS pExtendedParameters; // [rsp+60h] [rbp-20h] BYREF

  v13.LowPart = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(1, (unsigned int *)&v13);
  if ( PIC >= 0 )
  {
    pExtendedParameters.dwSize = 32;
    pExtendedParameters.dwCopyFlags = 8;
    memset(&pExtendedParameters.pfCancel, 0, 24);
    PIC = CopyFile2(a2, a3, &pExtendedParameters);
    if ( PIC >= 0 )
      goto LABEL_10;
    hFile = (HANDLE)CreateFile2(a2, 0, 1, 3, 0);
    v15 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable';
    File2 = (void *)CreateFile2(a3, 0, 1, 3, 0);
    v17[0] = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable';
    v17[1] = File2;
    if ( File2 != (void *)-1LL && hFile != (HANDLE)-1LL )
    {
      FileSize.QuadPart = 0;
      v13.QuadPart = 0;
      if ( GetFileSizeEx(File2, &FileSize) )
      {
        if ( GetFileSizeEx(hFile, &v13) && FileSize.QuadPart == v13.QuadPart )
          PIC = 0;
      }
    }
    v17[0] = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::Close(v17);
    v15 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::Close(&v15);
    if ( PIC >= 0 )
    {
LABEL_10:
      if ( a4 )
      {
        if ( a4 == 2 )
        {
          if ( a6 )
            return (unsigned int)ProtectFileToEnterpriseIdentity(a3);
          return (unsigned int)-2147024809;
        }
        if ( a4 != 1 )
          return (unsigned int)-2147024809;
        v11 = EfsClientDecryptFile(a3, 0);
        PIC = v11;
        if ( v11 > 0 )
          return (unsigned __int16)v11 | 0x80070000;
      }
    }
  }
  return (unsigned int)PIC;
}

```

## disassembly

```asm
0x180028d60  push    rbp
0x180028d62  push    rbx
0x180028d63  push    rsi
0x180028d64  push    rdi
0x180028d65  push    r14
0x180028d67  mov     rbp, rsp
0x180028d6a  sub     rsp, 80h
0x180028d71  mov     r14, rdx
0x180028d74  mov     dword ptr [rbp+var_50], 0
0x180028d7b  lea     rdx, [rbp+var_50]; unsigned int *
0x180028d7f  mov     ecx, 1; unsigned int
0x180028d84  mov     edi, r9d
0x180028d87  mov     rsi, r8
0x180028d8a  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x180028d8f  mov     ebx, eax
0x180028d91  test    eax, eax
0x180028d93  js      loc_180028ED0
0x180028d99  xorps   xmm0, xmm0
0x180028d9c  mov     [rbp+pExtendedParameters.pvCallbackContext], 0
0x180028da4  lea     r8, [rbp+pExtendedParameters]; pExtendedParameters
0x180028da8  mov     [rbp+pExtendedParameters.dwSize], 20h ; ' '
0x180028daf  mov     rdx, rsi; pwszNewFileName
0x180028db2  mov     [rbp+pExtendedParameters.dwCopyFlags], 8
0x180028db9  mov     rcx, r14; pwszExistingFileName
0x180028dbc  movdqu  xmmword ptr [rbp+pExtendedParameters.pfCancel], xmm0
0x180028dc1  call    cs:__imp_CopyFile2
0x180028dc7  mov     ebx, eax
0x180028dc9  test    eax, eax
0x180028dcb  jns     loc_180028E8B
0x180028dd1  xor     edx, edx
0x180028dd3  mov     [rsp+80h+var_60], 0
0x180028ddc  mov     rcx, r14
0x180028ddf  lea     r9d, [rdx+3]
0x180028de3  lea     r8d, [rdx+1]
0x180028de7  call    cs:__imp_CreateFile2
0x180028ded  xor     edx, edx
0x180028def  mov     [rsp+80h+var_60], 0
0x180028df8  lea     r14, ??_7?$HandleT@UFileHandleTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable'
0x180028dff  mov     [rbp+hFile], rax
0x180028e03  mov     rcx, rsi
0x180028e06  mov     [rbp+var_40], r14
0x180028e0a  lea     r9d, [rdx+3]
0x180028e0e  lea     r8d, [rdx+1]
0x180028e12  call    cs:__imp_CreateFile2
0x180028e18  mov     [rbp+var_30], r14
0x180028e1c  mov     [rbp+var_28], rax
0x180028e20  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180028e24  jz      short loc_180028E6D
0x180028e26  cmp     [rbp+hFile], 0FFFFFFFFFFFFFFFFh
0x180028e2b  jz      short loc_180028E6D
0x180028e2d  lea     rdx, [rbp+FileSize]; lpFileSize
0x180028e31  mov     qword ptr [rbp+FileSize], 0
0x180028e39  mov     rcx, rax; hFile
0x180028e3c  mov     qword ptr [rbp+var_50], 0
0x180028e44  call    cs:__imp_GetFileSizeEx
0x180028e4a  test    eax, eax
0x180028e4c  jz      short loc_180028E6D
0x180028e4e  mov     rcx, [rbp+hFile]; hFile
0x180028e52  lea     rdx, [rbp+var_50]; lpFileSize
0x180028e56  call    cs:__imp_GetFileSizeEx
0x180028e5c  test    eax, eax
0x180028e5e  jz      short loc_180028E6D
0x180028e60  mov     rax, qword ptr [rbp+var_50]
0x180028e64  xor     ecx, ecx
0x180028e66  cmp     qword ptr [rbp+FileSize], rax
0x180028e6a  cmovz   ebx, ecx
0x180028e6d  lea     rcx, [rbp+var_30]
0x180028e71  mov     [rbp+var_30], r14
0x180028e75  call    ?Close@?$HandleT@UFileHandleTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::Close(void)
0x180028e7a  lea     rcx, [rbp+var_40]
0x180028e7e  mov     [rbp+var_40], r14
0x180028e82  call    ?Close@?$HandleT@UFileHandleTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::Close(void)
0x180028e87  test    ebx, ebx
0x180028e89  js      short loc_180028ED0
0x180028e8b  test    edi, edi
0x180028e8d  jz      short loc_180028ED0
0x180028e8f  cmp     edi, 2
0x180028e92  jnz     short loc_180028EAA
0x180028e94  mov     rdx, [rbp+arg_28]
0x180028e98  test    rdx, rdx
0x180028e9b  jz      short loc_180028ECB
0x180028e9d  mov     rcx, rsi
0x180028ea0  call    cs:__imp_ProtectFileToEnterpriseIdentity
0x180028ea6  mov     ebx, eax
0x180028ea8  jmp     short loc_180028ED0
0x180028eaa  cmp     edi, 1
0x180028ead  jnz     short loc_180028ECB
0x180028eaf  xor     edx, edx
0x180028eb1  mov     rcx, rsi
0x180028eb4  call    cs:__imp_EfsClientDecryptFile
0x180028eba  mov     ebx, eax
0x180028ebc  test    eax, eax
0x180028ebe  jle     short loc_180028ED0
0x180028ec0  movzx   ebx, ax
0x180028ec3  or      ebx, 80070000h
0x180028ec9  jmp     short loc_180028ED0
0x180028ecb  mov     ebx, 80070057h
0x180028ed0  mov     eax, ebx
0x180028ed2  add     rsp, 80h
0x180028ed9  pop     r14
0x180028edb  pop     rdi
0x180028edc  pop     rsi
0x180028edd  pop     rbx
0x180028ede  pop     rbp
0x180028edf  retn
```
