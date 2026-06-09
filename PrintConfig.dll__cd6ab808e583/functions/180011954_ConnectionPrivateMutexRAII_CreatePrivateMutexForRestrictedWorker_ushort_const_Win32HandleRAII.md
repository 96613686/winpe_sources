# ConnectionPrivateMutexRAII::CreatePrivateMutexForRestrictedWorker(ushort const *,Win32HandleRAII &)

- ea: `0x180011954`
- end: `0x180011b9b`
- name: `?CreatePrivateMutexForRestrictedWorker@ConnectionPrivateMutexRAII@@CAXPEBGAEAVWin32HandleRAII@@@Z`
- size: `583`
- prototype: `void __fastcall(LPCWSTR lpName, struct Win32HandleRAII *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180013150`

## callees

- `0x1800032e0`
- `0x180004424`
- `0x18000e4a0`
- `0x18000efdc`
- `0x18000f380`
- `0x180011954`
- `0x180012164`
- `0x180018bbc`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180011ab0`
- `KERNEL32!FreeLibrary` at `0x180011ab0`
- `KERNEL32!GetLastError` at `0x180011ad6`
- `KERNEL32!GetLastError` at `0x180011b39`
- `KERNEL32!GetLastError` at `0x180011ad6`
- `KERNEL32!GetLastError` at `0x180011b39`
- `ADVAPI32!InitializeSid` at `0x1800119bb`
- `ADVAPI32!InitializeSid` at `0x1800119bb`
- `ADVAPI32!GetSidSubAuthority` at `0x1800119ce`
- `ADVAPI32!GetSidSubAuthority` at `0x1800119e2`
- `ADVAPI32!GetSidSubAuthority` at `0x1800119f6`
- `ADVAPI32!GetSidSubAuthority` at `0x180011a0a`
- `ADVAPI32!GetSidSubAuthority` at `0x180011a1e`
- `ADVAPI32!GetSidSubAuthority` at `0x180011a32`
- `ADVAPI32!GetSidSubAuthority` at `0x1800119ce`
- `ADVAPI32!GetSidSubAuthority` at `0x1800119e2`
- `ADVAPI32!GetSidSubAuthority` at `0x1800119f6`
- `ADVAPI32!GetSidSubAuthority` at `0x180011a0a`
- `ADVAPI32!GetSidSubAuthority` at `0x180011a1e`
- `ADVAPI32!GetSidSubAuthority` at `0x180011a32`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ConnectionPrivateMutexRAII::CreatePrivateMutexForRestrictedWorker(LPCWSTR lpName, HANDLE *a2)
{
  signed int v4; // eax
  unsigned int v5; // ebx
  signed int LastError; // eax
  unsigned int v7; // ebx
  __int64 v8; // [rsp+28h] [rbp-49h] BYREF
  void *v9[2]; // [rsp+30h] [rbp-41h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+40h] [rbp-31h] BYREF
  _BYTE v11[48]; // [rsp+68h] [rbp-9h] BYREF
  void **v12; // [rsp+98h] [rbp+27h]
  HMODULE hLibModule; // [rsp+A0h] [rbp+2Fh]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A8h] [rbp+37h] BYREF

  v9[1] = (void *)-2LL;
  Kernel32RAII::Kernel32RAII((Kernel32RAII *)v11);
  if ( !`ConnectionPrivateMutexRAII::CreatePrivateMutexForRestrictedWorker'::`2'::fInitializedSID )
  {
    *(_DWORD *)pIdentifierAuthority.Value = 0;
    *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
    if ( !InitializeSid(
            `ConnectionPrivateMutexRAII::CreatePrivateMutexForRestrictedWorker'::`2'::RestricedSpoolerWorkerSID,
            &pIdentifierAuthority,
            6u) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 24, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, v7);
      }
      hr_error::hr_error((hr_error *)pExceptionObject, v7);
      throw (hr_error *)pExceptionObject;
    }
    *GetSidSubAuthority(
       `ConnectionPrivateMutexRAII::CreatePrivateMutexForRestrictedWorker'::`2'::RestricedSpoolerWorkerSID,
       0) = 99;
    *GetSidSubAuthority(
       `ConnectionPrivateMutexRAII::CreatePrivateMutexForRestrictedWorker'::`2'::RestricedSpoolerWorkerSID,
       1u) = 216390572;
    *GetSidSubAuthority(
       `ConnectionPrivateMutexRAII::CreatePrivateMutexForRestrictedWorker'::`2'::RestricedSpoolerWorkerSID,
       2u) = 1995538116;
    *GetSidSubAuthority(
       `ConnectionPrivateMutexRAII::CreatePrivateMutexForRestrictedWorker'::`2'::RestricedSpoolerWorkerSID,
       3u) = -437055781;
    *GetSidSubAuthority(
       `ConnectionPrivateMutexRAII::CreatePrivateMutexForRestrictedWorker'::`2'::RestricedSpoolerWorkerSID,
       4u) = -1890008784;
    *GetSidSubAuthority(
       `ConnectionPrivateMutexRAII::CreatePrivateMutexForRestrictedWorker'::`2'::RestricedSpoolerWorkerSID,
       5u) = -1671080067;
    `ConnectionPrivateMutexRAII::CreatePrivateMutexForRestrictedWorker'::`2'::fInitializedSID = 1;
  }
  BoundaryDescriptorRAII::BoundaryDescriptorRAII(
    (BoundaryDescriptorRAII *)&v8,
    L"RestrictedSpoolerWorker",
    (struct Kernel32RAII *)v11);
  if ( !(*(unsigned int (__fastcall **)(void **, __int64 *))(v8 + 40))(
          v9,
          `ConnectionPrivateMutexRAII::CreatePrivateMutexForRestrictedWorker'::`2'::RestricedSpoolerWorkerSID) )
  {
    v4 = GetLastError();
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, v5);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v5);
    throw (hr_error *)pExceptionObject;
  }
  ConnectionPrivateMutexRAII::CreatePrivateMutexInternal(
    lpName,
    v9[0],
    `ConnectionPrivateMutexRAII::CreatePrivateMutexForRestrictedWorker'::`2'::RestricedSpoolerWorkerSID,
    a2);
  if ( v9[0] )
    (*(void (**)(void))(v8 + 32))();
  v12 = &ModuleRAII::`vftable';
  if ( hLibModule )
    FreeLibrary(hLibModule);
}

```

## disassembly

```asm
0x180011954  mov     rax, rsp
0x180011957  push    rbp
0x180011958  push    rdi
0x180011959  push    r14
0x18001195b  lea     rbp, [rax-5Fh]
0x18001195f  sub     rsp, 0B0h
0x180011966  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFEh
0x18001196e  mov     [rax+18h], rbx
0x180011972  mov     rax, cs:__security_cookie
0x180011979  xor     rax, rsp
0x18001197c  mov     [rbp+57h+var_18], rax
0x180011980  mov     rdi, rdx
0x180011983  mov     rbx, rcx
0x180011986  lea     rcx, [rbp+57h+var_60]; this
0x18001198a  call    ??0Kernel32RAII@@QEAA@XZ; Kernel32RAII::Kernel32RAII(void)
0x18001198f  nop
0x180011990  lea     r14, ?RestricedSpoolerWorkerSID@?1??CreatePrivateMutexForRestrictedWorker@ConnectionPrivateMutexRAII@@CAXPEBGAEAVWin32HandleRAII@@@Z@4PAEA; uchar near * `ConnectionPrivateMutexRAII::CreatePrivateMutexForRestrictedWorker(ushort const *,Win32HandleRAII &)'::`2'::RestricedSpoolerWorkerSID
0x180011997  cmp     cs:?fInitializedSID@?1??CreatePrivateMutexForRestrictedWorker@ConnectionPrivateMutexRAII@@CAXPEBGAEAVWin32HandleRAII@@@Z@4_NA, 0; bool `ConnectionPrivateMutexRAII::CreatePrivateMutexForRestrictedWorker(ushort const *,Win32HandleRAII &)'::`2'::fInitializedSID
0x18001199e  jnz     loc_180011A45
0x1800119a4  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], 0
0x1800119ab  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800119b1  mov     r8b, 6; nSubAuthorityCount
0x1800119b4  lea     rdx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800119b8  mov     rcx, r14; Sid
0x1800119bb  call    cs:__imp_InitializeSid
0x1800119c1  test    eax, eax
0x1800119c3  jz      loc_180011B39
0x1800119c9  xor     edx, edx; nSubAuthority
0x1800119cb  mov     rcx, r14; pSid
0x1800119ce  call    cs:__imp_GetSidSubAuthority
0x1800119d4  mov     dword ptr [rax], 63h ; 'c'
0x1800119da  mov     edx, 1; nSubAuthority
0x1800119df  mov     rcx, r14; pSid
0x1800119e2  call    cs:__imp_GetSidSubAuthority
0x1800119e8  mov     dword ptr [rax], 0CE5DBACh
0x1800119ee  mov     edx, 2; nSubAuthority
0x1800119f3  mov     rcx, r14; pSid
0x1800119f6  call    cs:__imp_GetSidSubAuthority
0x1800119fc  mov     dword ptr [rax], 76F17EC4h
0x180011a02  mov     edx, 3; nSubAuthority
0x180011a07  mov     rcx, r14; pSid
0x180011a0a  call    cs:__imp_GetSidSubAuthority
0x180011a10  mov     dword ptr [rax], 0E5F30EDBh
0x180011a16  mov     edx, 4; nSubAuthority
0x180011a1b  mov     rcx, r14; pSid
0x180011a1e  call    cs:__imp_GetSidSubAuthority
0x180011a24  mov     dword ptr [rax], 8F58C130h
0x180011a2a  mov     edx, 5; nSubAuthority
0x180011a2f  mov     rcx, r14; pSid
0x180011a32  call    cs:__imp_GetSidSubAuthority
0x180011a38  mov     dword ptr [rax], 9C65577Dh
0x180011a3e  mov     cs:?fInitializedSID@?1??CreatePrivateMutexForRestrictedWorker@ConnectionPrivateMutexRAII@@CAXPEBGAEAVWin32HandleRAII@@@Z@4_NA, 1; bool `ConnectionPrivateMutexRAII::CreatePrivateMutexForRestrictedWorker(ushort const *,Win32HandleRAII &)'::`2'::fInitializedSID
0x180011a45  lea     r8, [rbp+57h+var_60]; struct Kernel32RAII *
0x180011a49  lea     rdx, aRestrictedspoo; "RestrictedSpoolerWorker"
0x180011a50  lea     rcx, [rbp+57h+var_A0]; this
0x180011a54  call    ??0BoundaryDescriptorRAII@@QEAA@PEBGAEAVKernel32RAII@@@Z; BoundaryDescriptorRAII::BoundaryDescriptorRAII(ushort const *,Kernel32RAII &)
0x180011a59  nop
0x180011a5a  mov     rax, [rbp+57h+var_A0]
0x180011a5e  mov     rdx, r14
0x180011a61  lea     rcx, [rbp+57h+var_98]
0x180011a65  mov     rax, [rax+28h]
0x180011a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a6e  test    eax, eax
0x180011a70  jz      short loc_180011AD6
0x180011a72  mov     r9, rdi; struct Win32HandleRAII *
0x180011a75  mov     r8, r14; void *
0x180011a78  mov     rdx, [rbp+57h+var_98]; void *
0x180011a7c  mov     rcx, rbx; lpName
0x180011a7f  call    ?CreatePrivateMutexInternal@ConnectionPrivateMutexRAII@@CAXPEBGPEAX1AEAVWin32HandleRAII@@@Z; ConnectionPrivateMutexRAII::CreatePrivateMutexInternal(ushort const *,void *,void *,Win32HandleRAII &)
0x180011a84  nop
0x180011a85  mov     rcx, [rbp+57h+var_98]
0x180011a89  test    rcx, rcx
0x180011a8c  jz      short loc_180011A9C
0x180011a8e  mov     rax, [rbp+57h+var_A0]
0x180011a92  mov     rax, [rax+20h]
0x180011a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a9b  nop
0x180011a9c  lea     rax, ??_7ModuleRAII@@6B@; const ModuleRAII::`vftable'
0x180011aa3  mov     [rbp+57h+var_30], rax
0x180011aa7  mov     rcx, [rbp+57h+hLibModule]; hLibModule
0x180011aab  test    rcx, rcx
0x180011aae  jz      short loc_180011AB6
0x180011ab0  call    cs:__imp_FreeLibrary
0x180011ab6  mov     rcx, [rbp+57h+var_18]
0x180011aba  xor     rcx, rsp; StackCookie
0x180011abd  call    __security_check_cookie
0x180011ac2  mov     rbx, [rsp+0C0h+arg_10]
0x180011aca  add     rsp, 0B0h
0x180011ad1  pop     r14
0x180011ad3  pop     rdi
0x180011ad4  pop     rbp
0x180011ad5  retn
0x180011ad6  call    cs:__imp_GetLastError
0x180011adc  nop
0x180011add  mov     ebx, eax
0x180011adf  test    eax, eax
0x180011ae1  jle     short loc_180011AEC
0x180011ae3  movzx   ebx, ax
0x180011ae6  or      ebx, 80070000h
0x180011aec  lea     rax, WPP_GLOBAL_Control
0x180011af3  mov     rcx, cs:WPP_GLOBAL_Control
0x180011afa  cmp     rcx, rax
0x180011afd  jz      short loc_180011B1D
0x180011aff  test    byte ptr [rcx+44h], 1
0x180011b03  jz      short loc_180011B1D
0x180011b05  mov     edx, 0Bh
0x180011b0a  mov     r9d, ebx
0x180011b0d  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x180011b14  mov     rcx, [rcx+38h]
0x180011b18  call    WPP_SF_d
0x180011b1d  mov     edx, ebx; int
0x180011b1f  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180011b23  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180011b28  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180011b2f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180011b33  call    _CxxThrowException_0
0x180011b39  call    cs:__imp_GetLastError
0x180011b3f  mov     ebx, eax
0x180011b41  test    eax, eax
0x180011b43  jle     short loc_180011B4E
0x180011b45  movzx   ebx, ax
0x180011b48  or      ebx, 80070000h
0x180011b4e  lea     rax, WPP_GLOBAL_Control
0x180011b55  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b5c  cmp     rcx, rax
0x180011b5f  jz      short loc_180011B7F
0x180011b61  test    byte ptr [rcx+44h], 1
0x180011b65  jz      short loc_180011B7F
0x180011b67  mov     edx, 18h
0x180011b6c  mov     r9d, ebx
0x180011b6f  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x180011b76  mov     rcx, [rcx+38h]
0x180011b7a  call    WPP_SF_d
0x180011b7f  mov     edx, ebx; int
0x180011b81  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180011b85  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180011b8a  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180011b91  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180011b95  call    _CxxThrowException_0
```
