# FileOperationBroker::CreateProgressFile(ushort const *,ushort * *,ushort const *)

- ea: `0x180027ad0`
- end: `0x180027c37`
- name: `?CreateProgressFile@FileOperationBroker@@UEAAJPEBGPEAPEAG0@Z`
- size: `359`
- prototype: `__int64 __fastcall(FileOperationBroker *this, unsigned __int16 *, LPCWSTR *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, reparse_path, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000e428`
- `0x18002762c`
- `0x180027684`
- `0x180027ad0`
- `0x180029920`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027c15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027c15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027b93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027b93`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180027b3a`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180027bd3`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180027b3a`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180027bd3`
- `ext-ms-win-security-efswrt-l1-1-1!ProtectFileToEnterpriseIdentity` at `0x180027b89`
- `ext-ms-win-security-efswrt-l1-1-1!ProtectFileToEnterpriseIdentity` at `0x180027b89`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x180027bb3`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x180027bb3`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall FileOperationBroker::CreateProgressFile(
        FileOperationBroker *this,
        unsigned __int16 *a2,
        LPCWSTR *a3,
        const unsigned __int16 *a4)
{
  int PIC; // ebx
  __int64 v8; // rsi
  signed int LastError; // eax
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rbp
  void **v14; // [rsp+30h] [rbp-38h] BYREF
  __int64 File2; // [rsp+38h] [rbp-30h]
  unsigned int v16; // [rsp+80h] [rbp+18h] BYREF

  *a3 = 0;
  v16 = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(1, &v16);
  if ( PIC >= 0 )
  {
    PIC = anonymous_namespace_::ConvertFinalPathToProgressPath(a2);
    if ( PIC < 0 )
      goto LABEL_18;
    v8 = -1;
    File2 = CreateFile2(*a3, 917504, 0, 1, 0);
    v14 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable';
    if ( File2 == -1 )
    {
      LastError = GetLastError();
      PIC = LastError;
      if ( LastError > 0 )
        PIC = (unsigned __int16)LastError | 0x80070000;
      if ( PIC == -2147024891 && PathIsNetworkPathW(*a3) )
      {
        v10 = CreateFile2(*a3, 0x20000, 0, 1, 0);
        v11 = File2;
        v12 = v10;
        if ( v10 != File2 )
        {
          Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::Close(&v14);
          v11 = v12;
          File2 = v12;
        }
        if ( v11 != -1 )
          PIC = 0;
      }
    }
    else if ( a4 )
    {
      do
        ++v8;
      while ( a4[v8] );
      if ( v8 && !(unsigned __int8)EdpIsExcludedExtension(a2) )
        PIC = ProtectFileToEnterpriseIdentity(*a3);
    }
    v14 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::Close(&v14);
    if ( PIC < 0 )
    {
LABEL_18:
      CoTaskMemFree((LPVOID)*a3);
      *a3 = 0;
    }
  }
  return (unsigned int)PIC;
}

```

## disassembly

```asm
0x180027ad0  mov     rax, rsp
0x180027ad3  mov     [rax+8], rbx
0x180027ad7  mov     [rax+10h], rbp
0x180027adb  push    rsi
0x180027adc  push    rdi
0x180027add  push    r13
0x180027adf  push    r14
0x180027ae1  push    r15
0x180027ae3  sub     rsp, 40h
0x180027ae7  xor     r15d, r15d
0x180027aea  mov     r14, rdx
0x180027aed  lea     rdx, [rax+18h]; unsigned int *
0x180027af1  mov     [r8], r15
0x180027af4  mov     rbp, r9
0x180027af7  mov     [rax+18h], r15d
0x180027afb  mov     rdi, r8
0x180027afe  lea     ecx, [r15+1]; unsigned int
0x180027b02  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x180027b07  mov     ebx, eax
0x180027b09  test    eax, eax
0x180027b0b  js      loc_180027C1E
0x180027b11  mov     rdx, rdi
0x180027b14  mov     rcx, r14; unsigned __int16 *
0x180027b17  call    _anonymous_namespace___ConvertFinalPathToProgressPath
0x180027b1c  mov     ebx, eax
0x180027b1e  test    eax, eax
0x180027b20  js      loc_180027C12
0x180027b26  mov     rcx, [rdi]
0x180027b29  lea     r9d, [r15+1]
0x180027b2d  xor     r8d, r8d
0x180027b30  mov     [rsp+68h+var_48], r15
0x180027b35  mov     edx, 0E0000h
0x180027b3a  call    cs:__imp_CreateFile2
0x180027b40  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180027b44  lea     r13, ??_7?$HandleT@UFileHandleTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable'
0x180027b4b  mov     [rsp+68h+var_30], rax
0x180027b50  mov     [rsp+68h+var_38], r13
0x180027b55  cmp     rax, rsi
0x180027b58  jz      short loc_180027B93
0x180027b5a  test    rbp, rbp
0x180027b5d  jz      loc_180027BFF
0x180027b63  inc     rsi
0x180027b66  cmp     [rbp+rsi*2+0], r15w
0x180027b6c  jnz     short loc_180027B63
0x180027b6e  test    rsi, rsi
0x180027b71  jz      loc_180027BFF
0x180027b77  mov     rcx, r14
0x180027b7a  call    _EdpIsExcludedExtension
0x180027b7f  test    al, al
0x180027b81  jnz     short loc_180027BFF
0x180027b83  mov     rcx, [rdi]
0x180027b86  mov     rdx, rbp
0x180027b89  call    cs:__imp_ProtectFileToEnterpriseIdentity
0x180027b8f  mov     ebx, eax
0x180027b91  jmp     short loc_180027BFF
0x180027b93  call    cs:__imp_GetLastError
0x180027b99  mov     ebx, eax
0x180027b9b  test    eax, eax
0x180027b9d  jle     short loc_180027BA8
0x180027b9f  movzx   ebx, ax
0x180027ba2  or      ebx, 80070000h
0x180027ba8  cmp     ebx, 80070005h
0x180027bae  jnz     short loc_180027BFF
0x180027bb0  mov     rcx, [rdi]; pszPath
0x180027bb3  call    cs:__imp_PathIsNetworkPathW
0x180027bb9  test    eax, eax
0x180027bbb  jz      short loc_180027BFF
0x180027bbd  mov     rcx, [rdi]
0x180027bc0  mov     r9d, 1
0x180027bc6  xor     r8d, r8d
0x180027bc9  mov     [rsp+68h+var_48], r15
0x180027bce  mov     edx, 20000h
0x180027bd3  call    cs:__imp_CreateFile2
0x180027bd9  mov     rcx, [rsp+68h+var_30]
0x180027bde  mov     rbp, rax
0x180027be1  cmp     rax, rcx
0x180027be4  jz      short loc_180027BF8
0x180027be6  lea     rcx, [rsp+68h+var_38]
0x180027beb  call    ?Close@?$HandleT@UFileHandleTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::Close(void)
0x180027bf0  mov     rcx, rbp
0x180027bf3  mov     [rsp+68h+var_30], rcx
0x180027bf8  cmp     rcx, rsi
0x180027bfb  cmovnz  ebx, r15d
0x180027bff  lea     rcx, [rsp+68h+var_38]
0x180027c04  mov     [rsp+68h+var_38], r13
0x180027c09  call    ?Close@?$HandleT@UFileHandleTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::Close(void)
0x180027c0e  test    ebx, ebx
0x180027c10  jns     short loc_180027C1E
0x180027c12  mov     rcx, [rdi]; pv
0x180027c15  call    cs:__imp_CoTaskMemFree
0x180027c1b  mov     [rdi], r15
0x180027c1e  mov     rbp, [rsp+68h+arg_8]
0x180027c23  mov     eax, ebx
0x180027c25  mov     rbx, [rsp+68h+arg_0]
0x180027c2a  add     rsp, 40h
0x180027c2e  pop     r15
0x180027c30  pop     r14
0x180027c32  pop     r13
0x180027c34  pop     rdi
0x180027c35  pop     rsi
0x180027c36  retn
```
