# PushButtonReset::Directory::CopySecurity(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x18004b674`
- end: `0x18004b8b3`
- name: `?CopySecurity@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z`
- size: `575`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18004aabc`

## callees

- `0x180003c68`
- `0x180005c00`
- `0x18000d6f0`
- `0x180037344`
- `0x18004b674`
- `0x18006f010`

## import_xrefs

- `ADVAPI32!SetFileSecurityW` at `0x18004b834`
- `ADVAPI32!SetFileSecurityW` at `0x18004b834`
- `ADVAPI32!GetFileSecurityW` at `0x18004b6ac`
- `ADVAPI32!GetFileSecurityW` at `0x18004b798`
- `ADVAPI32!GetFileSecurityW` at `0x18004b6ac`
- `ADVAPI32!GetFileSecurityW` at `0x18004b798`
- `KERNEL32!GetLastError` at `0x18004b6b6`
- `KERNEL32!GetLastError` at `0x18004b6c4`
- `KERNEL32!GetLastError` at `0x18004b7a8`
- `KERNEL32!GetLastError` at `0x18004b7f3`
- `KERNEL32!GetLastError` at `0x18004b844`
- `KERNEL32!GetLastError` at `0x18004b6b6`
- `KERNEL32!GetLastError` at `0x18004b6c4`
- `KERNEL32!GetLastError` at `0x18004b7a8`
- `KERNEL32!GetLastError` at `0x18004b7f3`
- `KERNEL32!GetLastError` at `0x18004b844`

## string_xrefs

- `0x18004b6f6`: `PushButtonReset::Directory::CopySecurity`
- `0x18004b74d`: `PushButtonReset::Directory::CopySecurity`
- `0x18004b7e0`: `PushButtonReset::Directory::CopySecurity`
- `0x18004b87b`: `PushButtonReset::Directory::CopySecurity`
- `0x18004b7c5`: `Found but failed to read %u-byte security desciptor for [%s]`
- `0x18004b860`: `Failed to write [%s] security to [%s]`
- `0x18004b6db`: `Failed to read size of security descriptor for [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PushButtonReset::Directory::CopySecurity(LPCWSTR *a1, LPCWSTR *a2)
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
        "PushButtonReset::Directory::CopySecurity",
        "base\\reset\\util\\src\\filesystem.cpp",
        2743,
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
            "PushButtonReset::Directory::CopySecurity",
            "base\\reset\\util\\src\\filesystem.cpp",
            2758,
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
        "PushButtonReset::Directory::CopySecurity",
        "base\\reset\\util\\src\\filesystem.cpp",
        2750,
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
    "PushButtonReset::Directory::CopySecurity",
    "base\\reset\\util\\src\\filesystem.cpp",
    2765,
    L"Failed to read size of security descriptor for [%s]",
    v4);
  return 0;
}

```

## disassembly

```asm
0x18004b674  mov     [rsp-18h+arg_8], rbx
0x18004b679  mov     [rsp-18h+arg_10], rsi
0x18004b67e  push    rbp
0x18004b67f  push    rdi
0x18004b680  push    r14
0x18004b682  mov     rbp, rsp
0x18004b685  sub     rsp, 50h
0x18004b689  mov     rsi, rdx
0x18004b68c  mov     rdi, rcx
0x18004b68f  mov     [rbp+nLengthNeeded], 0
0x18004b696  lea     rax, [rbp+nLengthNeeded]
0x18004b69a  mov     [rsp+50h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18004b69f  xor     r9d, r9d; nLength
0x18004b6a2  xor     r8d, r8d; pSecurityDescriptor
0x18004b6a5  lea     edx, [r9+7]; RequestedInformation
0x18004b6a9  mov     rcx, [rcx]; lpFileName
0x18004b6ac  call    cs:__imp_GetFileSecurityW
0x18004b6b2  test    eax, eax
0x18004b6b4  jnz     short loc_18004B70E
0x18004b6b6  call    cs:__imp_GetLastError
0x18004b6bc  cmp     eax, 7Ah ; 'z'
0x18004b6bf  jz      short loc_18004B70E
0x18004b6c1  mov     rbx, [rdi]
0x18004b6c4  call    cs:__imp_GetLastError
0x18004b6ca  test    eax, eax
0x18004b6cc  jle     short loc_18004B6D6
0x18004b6ce  movzx   eax, ax
0x18004b6d1  or      eax, 80070000h
0x18004b6d6  mov     [rsp+50h+var_20], rbx
0x18004b6db  lea     rcx, aFailedToReadSi; "Failed to read size of security descrip"...
0x18004b6e2  mov     [rsp+50h+var_28], rcx
0x18004b6e7  mov     dword ptr [rsp+50h+lpnLengthNeeded], 0ACDh
0x18004b6ef  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004b6f6  lea     r8, aPushbuttonrese_4; "PushButtonReset::Directory::CopySecurit"...
0x18004b6fd  mov     edx, eax
0x18004b6ff  mov     ecx, 1
0x18004b704  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004b709  jmp     loc_18004B89C
0x18004b70e  mov     ecx, [rbp+nLengthNeeded]
0x18004b711  call    ??$PbrHeapAlloc@X@@YAPEAX_K@Z; PbrHeapAlloc<void>(unsigned __int64)
0x18004b716  mov     [rbp+var_8], rax
0x18004b71a  lea     r14, ??_7?$CAutoPbrHeapFree@PEAX@RAII@@6B@; const RAII::CAutoPbrHeapFree<void *>::`vftable'
0x18004b721  mov     [rbp+var_10], r14
0x18004b725  lea     rcx, [rbp+var_10]
0x18004b729  call    ??7?$CAutoCleanupBase@PEAUISetupOneSettings@@@RAII@@UEBA_NXZ; RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(void)
0x18004b72e  test    al, al
0x18004b730  jz      short loc_18004B76D
0x18004b732  lea     rax, aFailedToAlloca_29; "Failed to allocate desc"
0x18004b739  mov     [rsp+50h+var_28], rax
0x18004b73e  mov     dword ptr [rsp+50h+lpnLengthNeeded], 0AB7h
0x18004b746  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004b74d  lea     r8, aPushbuttonrese_4; "PushButtonReset::Directory::CopySecurit"...
0x18004b754  mov     edx, 8007000Eh
0x18004b759  mov     ecx, 2
0x18004b75e  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004b763  mov     ebx, 8007000Eh
0x18004b768  jmp     loc_18004B804
0x18004b76d  mov     ebx, [rbp+nLengthNeeded]
0x18004b770  mov     rax, [rbp+var_10]
0x18004b774  lea     rcx, [rbp+var_10]
0x18004b778  mov     rax, [rax+20h]
0x18004b77c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b781  lea     rcx, [rbp+nLengthNeeded]
0x18004b785  mov     [rsp+50h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x18004b78a  mov     r9d, ebx; nLength
0x18004b78d  mov     r8, rax; pSecurityDescriptor
0x18004b790  mov     edx, 7; RequestedInformation
0x18004b795  mov     rcx, [rdi]; lpFileName
0x18004b798  call    cs:__imp_GetFileSecurityW
0x18004b79e  test    eax, eax
0x18004b7a0  jnz     short loc_18004B818
0x18004b7a2  mov     rbx, [rdi]
0x18004b7a5  mov     esi, [rbp+nLengthNeeded]
0x18004b7a8  call    cs:__imp_GetLastError
0x18004b7ae  mov     edi, 80070000h
0x18004b7b3  test    eax, eax
0x18004b7b5  jle     short loc_18004B7BC
0x18004b7b7  movzx   eax, ax
0x18004b7ba  or      eax, edi
0x18004b7bc  mov     [rsp+50h+var_18], rbx
0x18004b7c1  mov     dword ptr [rsp+50h+var_20], esi
0x18004b7c5  lea     rcx, aFoundButFailed; "Found but failed to read %u-byte securi"...
0x18004b7cc  mov     [rsp+50h+var_28], rcx
0x18004b7d1  mov     dword ptr [rsp+50h+lpnLengthNeeded], 0ABEh
0x18004b7d9  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004b7e0  lea     r8, aPushbuttonrese_4; "PushButtonReset::Directory::CopySecurit"...
0x18004b7e7  mov     edx, eax
0x18004b7e9  mov     ecx, 2
0x18004b7ee  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004b7f3  call    cs:__imp_GetLastError
0x18004b7f9  mov     ebx, eax
0x18004b7fb  test    eax, eax
0x18004b7fd  jle     short loc_18004B804
0x18004b7ff  movzx   ebx, ax
0x18004b802  or      ebx, edi
0x18004b804  mov     [rbp+var_10], r14
0x18004b808  lea     rcx, [rbp+var_10]
0x18004b80c  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x18004b811  mov     eax, ebx
0x18004b813  jmp     loc_18004B89E
0x18004b818  mov     rax, [rbp+var_10]
0x18004b81c  lea     rcx, [rbp+var_10]
0x18004b820  mov     rax, [rax+20h]
0x18004b824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b829  mov     r8, rax; pSecurityDescriptor
0x18004b82c  mov     edx, 7; SecurityInformation
0x18004b831  mov     rcx, [rsi]; lpFileName
0x18004b834  call    cs:__imp_SetFileSecurityW
0x18004b83a  test    eax, eax
0x18004b83c  jnz     short loc_18004B88F
0x18004b83e  mov     rbx, [rsi]
0x18004b841  mov     rsi, [rdi]
0x18004b844  call    cs:__imp_GetLastError
0x18004b84a  test    eax, eax
0x18004b84c  jle     short loc_18004B856
0x18004b84e  movzx   eax, ax
0x18004b851  or      eax, 80070000h
0x18004b856  mov     [rsp+50h+var_18], rbx
0x18004b85b  mov     [rsp+50h+var_20], rsi
0x18004b860  lea     rcx, aFailedToWriteS_1; "Failed to write [%s] security to [%s]"
0x18004b867  mov     [rsp+50h+var_28], rcx
0x18004b86c  mov     dword ptr [rsp+50h+lpnLengthNeeded], 0AC6h
0x18004b874  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004b87b  lea     r8, aPushbuttonrese_4; "PushButtonReset::Directory::CopySecurit"...
0x18004b882  mov     edx, eax
0x18004b884  mov     ecx, 1
0x18004b889  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004b88e  nop
0x18004b88f  mov     [rbp+var_10], r14
0x18004b893  lea     rcx, [rbp+var_10]
0x18004b897  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x18004b89c  xor     eax, eax
0x18004b89e  lea     r11, [rsp+50h+var_s0]
0x18004b8a3  mov     rbx, [r11+28h]
0x18004b8a7  mov     rsi, [r11+30h]
0x18004b8ab  mov     rsp, r11
0x18004b8ae  pop     r14
0x18004b8b0  pop     rdi
0x18004b8b1  pop     rbp
0x18004b8b2  retn
```
