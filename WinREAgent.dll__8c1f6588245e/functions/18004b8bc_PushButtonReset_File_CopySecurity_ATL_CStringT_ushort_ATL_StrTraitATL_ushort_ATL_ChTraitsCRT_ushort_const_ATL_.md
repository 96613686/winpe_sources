# PushButtonReset::File::CopySecurity(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x18004b8bc`
- end: `0x18004bafb`
- name: `?CopySecurity@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z`
- size: `575`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18004b35c`

## callees

- `0x180003c68`
- `0x180005c00`
- `0x18000d6f0`
- `0x180037344`
- `0x18004b8bc`
- `0x18006f010`

## import_xrefs

- `ADVAPI32!SetFileSecurityW` at `0x18004ba7c`
- `ADVAPI32!SetFileSecurityW` at `0x18004ba7c`
- `ADVAPI32!GetFileSecurityW` at `0x18004b8f4`
- `ADVAPI32!GetFileSecurityW` at `0x18004b9e0`
- `ADVAPI32!GetFileSecurityW` at `0x18004b8f4`
- `ADVAPI32!GetFileSecurityW` at `0x18004b9e0`
- `KERNEL32!GetLastError` at `0x18004b8fe`
- `KERNEL32!GetLastError` at `0x18004b90c`
- `KERNEL32!GetLastError` at `0x18004b9f0`
- `KERNEL32!GetLastError` at `0x18004ba3b`
- `KERNEL32!GetLastError` at `0x18004ba8c`
- `KERNEL32!GetLastError` at `0x18004b8fe`
- `KERNEL32!GetLastError` at `0x18004b90c`
- `KERNEL32!GetLastError` at `0x18004b9f0`
- `KERNEL32!GetLastError` at `0x18004ba3b`
- `KERNEL32!GetLastError` at `0x18004ba8c`

## string_xrefs

- `0x18004ba0d`: `Found but failed to read %u-byte security desciptor for [%s]`
- `0x18004baa8`: `Failed to write [%s] security to [%s]`
- `0x18004b923`: `Failed to read size of security descriptor for [%s]`
- `0x18004b93e`: `PushButtonReset::File::CopySecurity`
- `0x18004b995`: `PushButtonReset::File::CopySecurity`
- `0x18004ba28`: `PushButtonReset::File::CopySecurity`
- `0x18004bac3`: `PushButtonReset::File::CopySecurity`

## pseudocode

```c
__int64 __fastcall PushButtonReset::File::CopySecurity(LPCWSTR *a1, LPCWSTR *a2)
{
  LPCWSTR v4; // rbx
  signed int v5; // eax
  unsigned int v6; // ebx
  DWORD v7; // ebx
  void *v8; // rax
  LPCWSTR v9; // rbx
  DWORD v10; // esi
  signed int v11; // eax
  signed int v12; // eax
  void *v14; // rax
  LPCWSTR v15; // rbx
  LPCWSTR v16; // rsi
  signed int LastError; // eax
  DWORD v18; // [rsp+30h] [rbp-20h]
  __int64 v19[2]; // [rsp+40h] [rbp-10h] BYREF
  DWORD nLengthNeeded; // [rsp+70h] [rbp+20h] BYREF

  nLengthNeeded = 0;
  if ( GetFileSecurityW(*a1, 7u, 0, 0, &nLengthNeeded) || GetLastError() == 122 )
  {
    v19[1] = (__int64)PbrHeapAlloc<void>(nLengthNeeded);
    v19[0] = (__int64)&RAII::CAutoPbrHeapFree<void *>::`vftable';
    if ( (unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(v19) )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        2147942414LL,
        "PushButtonReset::File::CopySecurity",
        "base\\reset\\util\\src\\filesystem.cpp",
        3317,
        L"Failed to allocate desc");
      v6 = -2147024882;
    }
    else
    {
      v7 = nLengthNeeded;
      v8 = (void *)(*(__int64 (__fastcall **)(__int64 *))(v19[0] + 32))(v19);
      if ( GetFileSecurityW(*a1, 7u, v8, v7, &nLengthNeeded) )
      {
        v14 = (void *)(*(__int64 (__fastcall **)(__int64 *))(v19[0] + 32))(v19);
        if ( !SetFileSecurityW(*a2, 7u, v14) )
        {
          v15 = *a2;
          v16 = *a1;
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          PushButtonReset::Logging::TraceErr(
            1,
            (unsigned int)LastError,
            "PushButtonReset::File::CopySecurity",
            "base\\reset\\util\\src\\filesystem.cpp",
            3332,
            L"Failed to write [%s] security to [%s]",
            v16,
            v15);
        }
        v19[0] = (__int64)&RAII::CAutoPbrHeapFree<void *>::`vftable';
        RAII::CAutoPbrHeapFree<unsigned short *>::Release(v19);
        return 0;
      }
      v9 = *a1;
      v10 = nLengthNeeded;
      v11 = GetLastError();
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      v18 = v10;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v11,
        "PushButtonReset::File::CopySecurity",
        "base\\reset\\util\\src\\filesystem.cpp",
        3324,
        L"Found but failed to read %u-byte security desciptor for [%s]",
        v18,
        v9);
      v12 = GetLastError();
      v6 = v12;
      if ( v12 > 0 )
        v6 = (unsigned __int16)v12 | 0x80070000;
    }
    v19[0] = (__int64)&RAII::CAutoPbrHeapFree<void *>::`vftable';
    RAII::CAutoPbrHeapFree<unsigned short *>::Release(v19);
    return v6;
  }
  v4 = *a1;
  v5 = GetLastError();
  if ( v5 > 0 )
    v5 = (unsigned __int16)v5 | 0x80070000;
  PushButtonReset::Logging::TraceErr(
    1,
    (unsigned int)v5,
    "PushButtonReset::File::CopySecurity",
    "base\\reset\\util\\src\\filesystem.cpp",
    3339,
    L"Failed to read size of security descriptor for [%s]",
    v4);
  return 0;
}

```

## disassembly

```asm
0x18004b8bc  mov     [rsp-18h+arg_8], rbx
0x18004b8c1  mov     [rsp-18h+arg_10], rsi
0x18004b8c6  push    rbp
0x18004b8c7  push    rdi
0x18004b8c8  push    r14
0x18004b8ca  mov     rbp, rsp
0x18004b8cd  sub     rsp, 50h
0x18004b8d1  mov     rsi, rdx
0x18004b8d4  mov     rdi, rcx
0x18004b8d7  mov     [rbp+nLengthNeeded], 0
0x18004b8de  lea     rax, [rbp+nLengthNeeded]
0x18004b8e2  mov     [rsp+50h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18004b8e7  xor     r9d, r9d; nLength
0x18004b8ea  xor     r8d, r8d; pSecurityDescriptor
0x18004b8ed  lea     edx, [r9+7]; RequestedInformation
0x18004b8f1  mov     rcx, [rcx]; lpFileName
0x18004b8f4  call    cs:__imp_GetFileSecurityW
0x18004b8fa  test    eax, eax
0x18004b8fc  jnz     short loc_18004B956
0x18004b8fe  call    cs:__imp_GetLastError
0x18004b904  cmp     eax, 7Ah ; 'z'
0x18004b907  jz      short loc_18004B956
0x18004b909  mov     rbx, [rdi]
0x18004b90c  call    cs:__imp_GetLastError
0x18004b912  test    eax, eax
0x18004b914  jle     short loc_18004B91E
0x18004b916  movzx   eax, ax
0x18004b919  or      eax, 80070000h
0x18004b91e  mov     [rsp+50h+var_20], rbx
0x18004b923  lea     rcx, aFailedToReadSi; "Failed to read size of security descrip"...
0x18004b92a  mov     [rsp+50h+var_28], rcx
0x18004b92f  mov     dword ptr [rsp+50h+lpnLengthNeeded], 0D0Bh
0x18004b937  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004b93e  lea     r8, aPushbuttonrese_122; "PushButtonReset::File::CopySecurity"
0x18004b945  mov     edx, eax
0x18004b947  mov     ecx, 1
0x18004b94c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004b951  jmp     loc_18004BAE4
0x18004b956  mov     ecx, [rbp+nLengthNeeded]
0x18004b959  call    ??$PbrHeapAlloc@X@@YAPEAX_K@Z; PbrHeapAlloc<void>(unsigned __int64)
0x18004b95e  mov     [rbp+var_8], rax
0x18004b962  lea     r14, ??_7?$CAutoPbrHeapFree@PEAX@RAII@@6B@; const RAII::CAutoPbrHeapFree<void *>::`vftable'
0x18004b969  mov     [rbp+var_10], r14
0x18004b96d  lea     rcx, [rbp+var_10]
0x18004b971  call    ??7?$CAutoCleanupBase@PEAUISetupOneSettings@@@RAII@@UEBA_NXZ; RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(void)
0x18004b976  test    al, al
0x18004b978  jz      short loc_18004B9B5
0x18004b97a  lea     rax, aFailedToAlloca_29; "Failed to allocate desc"
0x18004b981  mov     [rsp+50h+var_28], rax
0x18004b986  mov     dword ptr [rsp+50h+lpnLengthNeeded], 0CF5h
0x18004b98e  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004b995  lea     r8, aPushbuttonrese_122; "PushButtonReset::File::CopySecurity"
0x18004b99c  mov     edx, 8007000Eh
0x18004b9a1  mov     ecx, 2
0x18004b9a6  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004b9ab  mov     ebx, 8007000Eh
0x18004b9b0  jmp     loc_18004BA4C
0x18004b9b5  mov     ebx, [rbp+nLengthNeeded]
0x18004b9b8  mov     rax, [rbp+var_10]
0x18004b9bc  lea     rcx, [rbp+var_10]
0x18004b9c0  mov     rax, [rax+20h]
0x18004b9c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b9c9  lea     rcx, [rbp+nLengthNeeded]
0x18004b9cd  mov     [rsp+50h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x18004b9d2  mov     r9d, ebx; nLength
0x18004b9d5  mov     r8, rax; pSecurityDescriptor
0x18004b9d8  mov     edx, 7; RequestedInformation
0x18004b9dd  mov     rcx, [rdi]; lpFileName
0x18004b9e0  call    cs:__imp_GetFileSecurityW
0x18004b9e6  test    eax, eax
0x18004b9e8  jnz     short loc_18004BA60
0x18004b9ea  mov     rbx, [rdi]
0x18004b9ed  mov     esi, [rbp+nLengthNeeded]
0x18004b9f0  call    cs:__imp_GetLastError
0x18004b9f6  mov     edi, 80070000h
0x18004b9fb  test    eax, eax
0x18004b9fd  jle     short loc_18004BA04
0x18004b9ff  movzx   eax, ax
0x18004ba02  or      eax, edi
0x18004ba04  mov     [rsp+50h+var_18], rbx
0x18004ba09  mov     dword ptr [rsp+50h+var_20], esi
0x18004ba0d  lea     rcx, aFoundButFailed; "Found but failed to read %u-byte securi"...
0x18004ba14  mov     [rsp+50h+var_28], rcx
0x18004ba19  mov     dword ptr [rsp+50h+lpnLengthNeeded], 0CFCh
0x18004ba21  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004ba28  lea     r8, aPushbuttonrese_122; "PushButtonReset::File::CopySecurity"
0x18004ba2f  mov     edx, eax
0x18004ba31  mov     ecx, 2
0x18004ba36  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004ba3b  call    cs:__imp_GetLastError
0x18004ba41  mov     ebx, eax
0x18004ba43  test    eax, eax
0x18004ba45  jle     short loc_18004BA4C
0x18004ba47  movzx   ebx, ax
0x18004ba4a  or      ebx, edi
0x18004ba4c  mov     [rbp+var_10], r14
0x18004ba50  lea     rcx, [rbp+var_10]
0x18004ba54  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x18004ba59  mov     eax, ebx
0x18004ba5b  jmp     loc_18004BAE6
0x18004ba60  mov     rax, [rbp+var_10]
0x18004ba64  lea     rcx, [rbp+var_10]
0x18004ba68  mov     rax, [rax+20h]
0x18004ba6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ba71  mov     r8, rax; pSecurityDescriptor
0x18004ba74  mov     edx, 7; SecurityInformation
0x18004ba79  mov     rcx, [rsi]; lpFileName
0x18004ba7c  call    cs:__imp_SetFileSecurityW
0x18004ba82  test    eax, eax
0x18004ba84  jnz     short loc_18004BAD7
0x18004ba86  mov     rbx, [rsi]
0x18004ba89  mov     rsi, [rdi]
0x18004ba8c  call    cs:__imp_GetLastError
0x18004ba92  test    eax, eax
0x18004ba94  jle     short loc_18004BA9E
0x18004ba96  movzx   eax, ax
0x18004ba99  or      eax, 80070000h
0x18004ba9e  mov     [rsp+50h+var_18], rbx
0x18004baa3  mov     [rsp+50h+var_20], rsi
0x18004baa8  lea     rcx, aFailedToWriteS_1; "Failed to write [%s] security to [%s]"
0x18004baaf  mov     [rsp+50h+var_28], rcx
0x18004bab4  mov     dword ptr [rsp+50h+lpnLengthNeeded], 0D04h
0x18004babc  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004bac3  lea     r8, aPushbuttonrese_122; "PushButtonReset::File::CopySecurity"
0x18004baca  mov     edx, eax
0x18004bacc  mov     ecx, 1
0x18004bad1  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004bad6  nop
0x18004bad7  mov     [rbp+var_10], r14
0x18004badb  lea     rcx, [rbp+var_10]
0x18004badf  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x18004bae4  xor     eax, eax
0x18004bae6  lea     r11, [rsp+50h+var_s0]
0x18004baeb  mov     rbx, [r11+28h]
0x18004baef  mov     rsi, [r11+30h]
0x18004baf3  mov     rsp, r11
0x18004baf6  pop     r14
0x18004baf8  pop     rdi
0x18004baf9  pop     rbp
0x18004bafa  retn
```
