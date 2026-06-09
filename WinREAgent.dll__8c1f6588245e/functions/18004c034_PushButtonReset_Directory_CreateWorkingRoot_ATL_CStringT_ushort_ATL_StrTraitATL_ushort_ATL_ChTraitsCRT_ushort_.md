# PushButtonReset::Directory::CreateWorkingRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x18004c034`
- end: `0x18004c2aa`
- name: `?CreateWorkingRoot@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `630`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001eecc`

## callees

- `0x1800049a4`
- `0x180005cc0`
- `0x18000d92c`
- `0x180037344`
- `0x18004bb04`
- `0x18004c034`
- `0x18004c2b0`
- `0x18004d1fc`
- `0x18004fa50`
- `0x18004fa80`
- `0x18004fe94`
- `0x180065100`
- `0x18006f010`

## import_xrefs

- `ADVAPI32!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18004c119`
- `ADVAPI32!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18004c119`
- `KERNEL32!GetLastError` at `0x18004c075`
- `KERNEL32!GetLastError` at `0x18004c0b7`
- `KERNEL32!GetLastError` at `0x18004c123`
- `KERNEL32!GetLastError` at `0x18004c165`
- `KERNEL32!GetLastError` at `0x18004c075`
- `KERNEL32!GetLastError` at `0x18004c0b7`
- `KERNEL32!GetLastError` at `0x18004c123`
- `KERNEL32!GetLastError` at `0x18004c165`

## string_xrefs

- `0x18004c089`: `Failed to create working directory security descriptor`
- `0x18004c0a4`: `PushButtonReset::Directory::CreateWorkingRoot`
- `0x18004c152`: `PushButtonReset::Directory::CreateWorkingRoot`
- `0x18004c1bc`: `PushButtonReset::Directory::CreateWorkingRoot`
- `0x18004c262`: `PushButtonReset::Directory::CreateWorkingRoot`
- `0x18004c137`: `ConvertSecurityDescriptorToStringSecurityDescriptor failed`
- `0x18004c1a1`: `Failed to delete existing directory [%s]`
- `0x18004c21b`: `Failed to create directory [%s]`
- `0x18004c247`: `Failed to hide root working directory at [%s]`

## pseudocode

```c
__int64 __fastcall PushButtonReset::Directory::CreateWorkingRoot(__int64 *a1)
{
  __int64 v2; // rax
  signed int v3; // eax
  signed int v4; // eax
  int v5; // ebx
  LPWSTR *v6; // rbx
  void *v7; // rax
  signed int LastError; // eax
  signed int v9; // eax
  const WCHAR *v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rdx
  _QWORD v14[2]; // [rsp+40h] [rbp-20h] BYREF
  _QWORD v15[2]; // [rsp+50h] [rbp-10h] BYREF
  __int64 v16; // [rsp+88h] [rbp+28h] BYREF

  v15[1] = 0;
  v15[0] = &RAII::CAutoWdsLibFree<void *>::`vftable';
  v2 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(v15);
  if ( (unsigned int)CreateWorkingDirectorySecurityDescriptor(v2) )
  {
    v14[1] = 0;
    v14[0] = &RAII::CAutoLocalFree<unsigned short *>::`vftable';
    v6 = (LPWSTR *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(v14);
    v7 = (void *)(*(__int64 (__fastcall **)(_QWORD *))(v15[0] + 32LL))(v15);
    if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(v7, 1u, 0xFu, v6, 0) )
    {
      if ( (unsigned __int8)PushButtonReset::Directory::Exists(a1)
        && (v5 = PushButtonReset::Directory::Delete(a1, v10), v5 < 0) )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v5,
          "PushButtonReset::Directory::CreateWorkingRoot",
          "base\\reset\\util\\src\\filesystem.cpp",
          2321,
          L"Failed to delete existing directory [%s]",
          *a1);
      }
      else
      {
        v11 = (*(__int64 (__fastcall **)(_QWORD *))(v14[0] + 32LL))(v14);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v16,
          v11);
        LOBYTE(v12) = 1;
        v5 = PushButtonReset::Directory::Create(a1, v12, &v16);
        ATL::CStringData::Release((ATL::CStringData *)(v16 - 24));
        if ( v5 >= 0 )
        {
          v5 = PushButtonReset::Path::SetHidden(a1);
          if ( v5 < 0 )
          {
            PushButtonReset::Logging::TraceErr(
              1,
              (unsigned int)v5,
              "PushButtonReset::Directory::CreateWorkingRoot",
              "base\\reset\\util\\src\\filesystem.cpp",
              2335,
              L"Failed to hide root working directory at [%s]",
              *a1);
            v5 = 0;
          }
        }
        else
        {
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)v5,
            "PushButtonReset::Directory::CreateWorkingRoot",
            "base\\reset\\util\\src\\filesystem.cpp",
            2327,
            L"Failed to create directory [%s]",
            *a1);
        }
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)LastError,
        "PushButtonReset::Directory::CreateWorkingRoot",
        "base\\reset\\util\\src\\filesystem.cpp",
        2314,
        L"ConvertSecurityDescriptorToStringSecurityDescriptor failed");
      v9 = GetLastError();
      v5 = v9;
      if ( v9 > 0 )
        v5 = (unsigned __int16)v9 | 0x80070000;
    }
    v14[0] = &RAII::CAutoLocalFree<unsigned short *>::`vftable';
    RAII::CAutoLocalFree<unsigned short *>::Release(v14);
  }
  else
  {
    v3 = GetLastError();
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v3,
      "PushButtonReset::Directory::CreateWorkingRoot",
      "base\\reset\\util\\src\\filesystem.cpp",
      2306,
      L"Failed to create working directory security descriptor");
    v4 = GetLastError();
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
  }
  v15[0] = &RAII::CAutoWdsLibFree<void *>::`vftable';
  RAII::CAutoWdsLibFree<void *>::Release(v15);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004c034  mov     [rsp-18h+arg_0], rbx
0x18004c039  mov     [rsp-18h+arg_10], rdi
0x18004c03e  push    rbp
0x18004c03f  push    r14
0x18004c041  push    r15
0x18004c043  mov     rbp, rsp
0x18004c046  sub     rsp, 60h
0x18004c04a  mov     rdi, rcx
0x18004c04d  mov     [rbp+var_8], 0
0x18004c055  lea     r15, ??_7?$CAutoWdsLibFree@PEAX@RAII@@6B@; const RAII::CAutoWdsLibFree<void *>::`vftable'
0x18004c05c  mov     [rbp+var_10], r15
0x18004c060  lea     rcx, [rbp+var_10]
0x18004c064  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18004c069  mov     rcx, rax
0x18004c06c  call    CreateWorkingDirectorySecurityDescriptor
0x18004c071  test    eax, eax
0x18004c073  jnz     short loc_18004C0D1
0x18004c075  call    cs:__imp_GetLastError
0x18004c07b  mov     edi, 80070000h
0x18004c080  test    eax, eax
0x18004c082  jle     short loc_18004C089
0x18004c084  movzx   eax, ax
0x18004c087  or      eax, edi
0x18004c089  lea     rcx, aFailedToCreate_7; "Failed to create working directory secu"...
0x18004c090  mov     [rsp+60h+var_38], rcx
0x18004c095  mov     dword ptr [rsp+60h+StringSecurityDescriptorLen], 902h
0x18004c09d  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004c0a4  lea     r8, aPushbuttonrese_82; "PushButtonReset::Directory::CreateWorki"...
0x18004c0ab  mov     edx, eax
0x18004c0ad  mov     ecx, 2
0x18004c0b2  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004c0b7  call    cs:__imp_GetLastError
0x18004c0bd  mov     ebx, eax
0x18004c0bf  test    eax, eax
0x18004c0c1  jle     loc_18004C285
0x18004c0c7  movzx   ebx, ax
0x18004c0ca  or      ebx, edi
0x18004c0cc  jmp     loc_18004C285
0x18004c0d1  mov     [rbp+var_18], 0
0x18004c0d9  lea     r14, ??_7?$CAutoLocalFree@PEAG@RAII@@6B@; const RAII::CAutoLocalFree<ushort *>::`vftable'
0x18004c0e0  mov     [rbp+var_20], r14
0x18004c0e4  lea     rcx, [rbp+var_20]
0x18004c0e8  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18004c0ed  mov     rbx, rax
0x18004c0f0  mov     rcx, [rbp+var_10]
0x18004c0f4  mov     rax, [rcx+20h]
0x18004c0f8  lea     rcx, [rbp+var_10]
0x18004c0fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c101  mov     [rsp+60h+StringSecurityDescriptorLen], 0; StringSecurityDescriptorLen
0x18004c10a  mov     r9, rbx; StringSecurityDescriptor
0x18004c10d  mov     edx, 1; RequestedStringSDRevision
0x18004c112  lea     r8d, [rdx+0Eh]; SecurityInformation
0x18004c116  mov     rcx, rax; SecurityDescriptor
0x18004c119  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x18004c11f  test    eax, eax
0x18004c121  jnz     short loc_18004C17F
0x18004c123  call    cs:__imp_GetLastError
0x18004c129  mov     edi, 80070000h
0x18004c12e  test    eax, eax
0x18004c130  jle     short loc_18004C137
0x18004c132  movzx   eax, ax
0x18004c135  or      eax, edi
0x18004c137  lea     rcx, aConvertsecurit; "ConvertSecurityDescriptorToStringSecuri"...
0x18004c13e  mov     [rsp+60h+var_38], rcx
0x18004c143  mov     dword ptr [rsp+60h+StringSecurityDescriptorLen], 90Ah
0x18004c14b  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004c152  lea     r8, aPushbuttonrese_82; "PushButtonReset::Directory::CreateWorki"...
0x18004c159  mov     edx, eax
0x18004c15b  mov     ecx, 2
0x18004c160  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004c165  call    cs:__imp_GetLastError
0x18004c16b  mov     ebx, eax
0x18004c16d  test    eax, eax
0x18004c16f  jle     loc_18004C277
0x18004c175  movzx   ebx, ax
0x18004c178  or      ebx, edi
0x18004c17a  jmp     loc_18004C277
0x18004c17f  mov     rcx, rdi
0x18004c182  call    ?Exists@Directory@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::Directory::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18004c187  test    al, al
0x18004c189  jz      short loc_18004C1D4
0x18004c18b  mov     rcx, rdi
0x18004c18e  call    ?Delete@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAUProgressCallback@2@@Z; PushButtonReset::Directory::Delete(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::ProgressCallback *)
0x18004c193  mov     ebx, eax
0x18004c195  test    eax, eax
0x18004c197  jns     short loc_18004C1D4
0x18004c199  mov     rcx, [rdi]
0x18004c19c  mov     [rsp+60h+var_30], rcx
0x18004c1a1  lea     rax, aFailedToDelete_18; "Failed to delete existing directory [%s"...
0x18004c1a8  mov     [rsp+60h+var_38], rax
0x18004c1ad  mov     dword ptr [rsp+60h+StringSecurityDescriptorLen], 911h
0x18004c1b5  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004c1bc  lea     r8, aPushbuttonrese_82; "PushButtonReset::Directory::CreateWorki"...
0x18004c1c3  mov     edx, ebx
0x18004c1c5  mov     ecx, 2
0x18004c1ca  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004c1cf  jmp     loc_18004C277
0x18004c1d4  mov     rax, [rbp+var_20]
0x18004c1d8  lea     rcx, [rbp+var_20]
0x18004c1dc  mov     rax, [rax+20h]
0x18004c1e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c1e5  mov     rdx, rax
0x18004c1e8  lea     rcx, [rbp+arg_8]
0x18004c1ec  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18004c1f1  nop
0x18004c1f2  lea     r8, [rbp+arg_8]
0x18004c1f6  mov     dl, 1
0x18004c1f8  mov     rcx, rdi
0x18004c1fb  call    ?Create@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N0@Z; PushButtonReset::Directory::Create(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18004c200  mov     ebx, eax
0x18004c202  mov     rcx, [rbp+arg_8]
0x18004c206  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004c20a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004c20f  test    ebx, ebx
0x18004c211  jns     short loc_18004C231
0x18004c213  mov     rcx, [rdi]
0x18004c216  mov     [rsp+60h+var_30], rcx
0x18004c21b  lea     rax, aFailedToCreate_43; "Failed to create directory [%s]"
0x18004c222  mov     [rsp+60h+var_38], rax
0x18004c227  mov     dword ptr [rsp+60h+StringSecurityDescriptorLen], 917h
0x18004c22f  jmp     short loc_18004C1B5
0x18004c231  mov     rcx, rdi
0x18004c234  call    ?SetHidden@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N@Z; PushButtonReset::Path::SetHidden(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool)
0x18004c239  mov     ebx, eax
0x18004c23b  test    eax, eax
0x18004c23d  jns     short loc_18004C277
0x18004c23f  mov     rdx, [rdi]
0x18004c242  mov     [rsp+60h+var_30], rdx
0x18004c247  lea     rax, aFailedToHideRo; "Failed to hide root working directory a"...
0x18004c24e  mov     [rsp+60h+var_38], rax
0x18004c253  mov     dword ptr [rsp+60h+StringSecurityDescriptorLen], 91Fh
0x18004c25b  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004c262  lea     r8, aPushbuttonrese_82; "PushButtonReset::Directory::CreateWorki"...
0x18004c269  mov     edx, ebx
0x18004c26b  mov     ecx, 1
0x18004c270  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004c275  xor     ebx, ebx
0x18004c277  mov     [rbp+var_20], r14
0x18004c27b  lea     rcx, [rbp+var_20]
0x18004c27f  call    ?Release@?$CAutoLocalFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoLocalFree<ushort *>::Release(void)
0x18004c284  nop
0x18004c285  mov     [rbp+var_10], r15
0x18004c289  lea     rcx, [rbp+var_10]
0x18004c28d  call    ?Release@?$CAutoWdsLibFree@PEAX@RAII@@UEAAXXZ; RAII::CAutoWdsLibFree<void *>::Release(void)
0x18004c292  mov     eax, ebx
0x18004c294  lea     r11, [rsp+60h+var_s0]
0x18004c299  mov     rbx, [r11+20h]
0x18004c29d  mov     rdi, [r11+30h]
0x18004c2a1  mov     rsp, r11
0x18004c2a4  pop     r15
0x18004c2a6  pop     r14
0x18004c2a8  pop     rbp
0x18004c2a9  retn
```
