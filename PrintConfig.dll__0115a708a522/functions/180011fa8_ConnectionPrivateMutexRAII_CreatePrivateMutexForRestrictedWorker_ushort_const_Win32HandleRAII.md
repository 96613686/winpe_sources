# ConnectionPrivateMutexRAII::CreatePrivateMutexForRestrictedWorker(ushort const *,Win32HandleRAII &)

- ea: `0x180011fa8`
- end: `0x18001222c`
- name: `?CreatePrivateMutexForRestrictedWorker@ConnectionPrivateMutexRAII@@CAXPEBGAEAVWin32HandleRAII@@@Z`
- size: `644`
- prototype: `void __fastcall(LPCWSTR lpName, struct Win32HandleRAII *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180013918`

## callees

- `0x180003400`
- `0x180004564`
- `0x18000e8ac`
- `0x18000f45c`
- `0x18000f830`
- `0x180011fa8`
- `0x180012870`
- `0x1800197b4`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18001212e`
- `KERNEL32!FreeLibrary` at `0x18001212e`
- `KERNEL32!GetLastError` at `0x18001215b`
- `KERNEL32!GetLastError` at `0x1800121c4`
- `KERNEL32!GetLastError` at `0x18001215b`
- `KERNEL32!GetLastError` at `0x1800121c4`
- `ADVAPI32!InitializeSid` at `0x18001200f`
- `ADVAPI32!InitializeSid` at `0x18001200f`
- `ADVAPI32!GetSidSubAuthority` at `0x180012028`
- `ADVAPI32!GetSidSubAuthority` at `0x180012042`
- `ADVAPI32!GetSidSubAuthority` at `0x18001205c`
- `ADVAPI32!GetSidSubAuthority` at `0x180012076`
- `ADVAPI32!GetSidSubAuthority` at `0x180012090`
- `ADVAPI32!GetSidSubAuthority` at `0x1800120aa`
- `ADVAPI32!GetSidSubAuthority` at `0x180012028`
- `ADVAPI32!GetSidSubAuthority` at `0x180012042`
- `ADVAPI32!GetSidSubAuthority` at `0x18001205c`
- `ADVAPI32!GetSidSubAuthority` at `0x180012076`
- `ADVAPI32!GetSidSubAuthority` at `0x180012090`
- `ADVAPI32!GetSidSubAuthority` at `0x1800120aa`

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
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          0x18u,
          (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
          v7);
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
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0xBu,
        (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
        v5);
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
0x180011fa8  mov     rax, rsp
0x180011fab  push    rbp
0x180011fac  push    rdi
0x180011fad  push    r14
0x180011faf  lea     rbp, [rax-5Fh]
0x180011fb3  sub     rsp, 0B0h
0x180011fba  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFEh
0x180011fc2  mov     [rax+18h], rbx
0x180011fc6  mov     rax, cs:__security_cookie
0x180011fcd  xor     rax, rsp
0x180011fd0  mov     [rbp+57h+var_18], rax
0x180011fd4  mov     rdi, rdx
0x180011fd7  mov     rbx, rcx
0x180011fda  lea     rcx, [rbp+57h+var_60]; this
0x180011fde  call    ??0Kernel32RAII@@QEAA@XZ; Kernel32RAII::Kernel32RAII(void)
0x180011fe3  nop
0x180011fe4  lea     r14, ?RestricedSpoolerWorkerSID@?1??CreatePrivateMutexForRestrictedWorker@ConnectionPrivateMutexRAII@@CAXPEBGAEAVWin32HandleRAII@@@Z@4PAEA; uchar near * `ConnectionPrivateMutexRAII::CreatePrivateMutexForRestrictedWorker(ushort const *,Win32HandleRAII &)'::`2'::RestricedSpoolerWorkerSID
0x180011feb  cmp     cs:?fInitializedSID@?1??CreatePrivateMutexForRestrictedWorker@ConnectionPrivateMutexRAII@@CAXPEBGAEAVWin32HandleRAII@@@Z@4_NA, 0; bool `ConnectionPrivateMutexRAII::CreatePrivateMutexForRestrictedWorker(ushort const *,Win32HandleRAII &)'::`2'::fInitializedSID
0x180011ff2  jnz     loc_1800120C3
0x180011ff8  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], 0
0x180011fff  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180012005  mov     r8b, 6; nSubAuthorityCount
0x180012008  lea     rdx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18001200c  mov     rcx, r14; Sid
0x18001200f  call    cs:__imp_InitializeSid
0x180012016  nop     dword ptr [rax+rax+00h]
0x18001201b  test    eax, eax
0x18001201d  jz      loc_1800121C4
0x180012023  xor     edx, edx; nSubAuthority
0x180012025  mov     rcx, r14; pSid
0x180012028  call    cs:__imp_GetSidSubAuthority
0x18001202f  nop     dword ptr [rax+rax+00h]
0x180012034  mov     dword ptr [rax], 63h ; 'c'
0x18001203a  mov     edx, 1; nSubAuthority
0x18001203f  mov     rcx, r14; pSid
0x180012042  call    cs:__imp_GetSidSubAuthority
0x180012049  nop     dword ptr [rax+rax+00h]
0x18001204e  mov     dword ptr [rax], 0CE5DBACh
0x180012054  mov     edx, 2; nSubAuthority
0x180012059  mov     rcx, r14; pSid
0x18001205c  call    cs:__imp_GetSidSubAuthority
0x180012063  nop     dword ptr [rax+rax+00h]
0x180012068  mov     dword ptr [rax], 76F17EC4h
0x18001206e  mov     edx, 3; nSubAuthority
0x180012073  mov     rcx, r14; pSid
0x180012076  call    cs:__imp_GetSidSubAuthority
0x18001207d  nop     dword ptr [rax+rax+00h]
0x180012082  mov     dword ptr [rax], 0E5F30EDBh
0x180012088  mov     edx, 4; nSubAuthority
0x18001208d  mov     rcx, r14; pSid
0x180012090  call    cs:__imp_GetSidSubAuthority
0x180012097  nop     dword ptr [rax+rax+00h]
0x18001209c  mov     dword ptr [rax], 8F58C130h
0x1800120a2  mov     edx, 5; nSubAuthority
0x1800120a7  mov     rcx, r14; pSid
0x1800120aa  call    cs:__imp_GetSidSubAuthority
0x1800120b1  nop     dword ptr [rax+rax+00h]
0x1800120b6  mov     dword ptr [rax], 9C65577Dh
0x1800120bc  mov     cs:?fInitializedSID@?1??CreatePrivateMutexForRestrictedWorker@ConnectionPrivateMutexRAII@@CAXPEBGAEAVWin32HandleRAII@@@Z@4_NA, 1; bool `ConnectionPrivateMutexRAII::CreatePrivateMutexForRestrictedWorker(ushort const *,Win32HandleRAII &)'::`2'::fInitializedSID
0x1800120c3  lea     r8, [rbp+57h+var_60]; struct Kernel32RAII *
0x1800120c7  lea     rdx, aRestrictedspoo; "RestrictedSpoolerWorker"
0x1800120ce  lea     rcx, [rbp+57h+var_A0]; this
0x1800120d2  call    ??0BoundaryDescriptorRAII@@QEAA@PEBGAEAVKernel32RAII@@@Z; BoundaryDescriptorRAII::BoundaryDescriptorRAII(ushort const *,Kernel32RAII &)
0x1800120d7  nop
0x1800120d8  mov     rax, [rbp+57h+var_A0]
0x1800120dc  mov     rdx, r14
0x1800120df  lea     rcx, [rbp+57h+var_98]
0x1800120e3  mov     rax, [rax+28h]
0x1800120e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120ec  test    eax, eax
0x1800120ee  jz      short loc_18001215B
0x1800120f0  mov     r9, rdi; struct Win32HandleRAII *
0x1800120f3  mov     r8, r14; void *
0x1800120f6  mov     rdx, [rbp+57h+var_98]; void *
0x1800120fa  mov     rcx, rbx; lpName
0x1800120fd  call    ?CreatePrivateMutexInternal@ConnectionPrivateMutexRAII@@CAXPEBGPEAX1AEAVWin32HandleRAII@@@Z; ConnectionPrivateMutexRAII::CreatePrivateMutexInternal(ushort const *,void *,void *,Win32HandleRAII &)
0x180012102  nop
0x180012103  mov     rcx, [rbp+57h+var_98]
0x180012107  test    rcx, rcx
0x18001210a  jz      short loc_18001211A
0x18001210c  mov     rax, [rbp+57h+var_A0]
0x180012110  mov     rax, [rax+20h]
0x180012114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012119  nop
0x18001211a  lea     rax, ??_7ModuleRAII@@6B@; const ModuleRAII::`vftable'
0x180012121  mov     [rbp+57h+var_30], rax
0x180012125  mov     rcx, [rbp+57h+hLibModule]; hLibModule
0x180012129  test    rcx, rcx
0x18001212c  jz      short loc_18001213A
0x18001212e  call    cs:__imp_FreeLibrary
0x180012135  nop     dword ptr [rax+rax+00h]
0x18001213a  mov     rcx, [rbp+57h+var_18]
0x18001213e  xor     rcx, rsp; StackCookie
0x180012141  call    __security_check_cookie
0x180012146  mov     rbx, [rsp+0C0h+arg_10]
0x18001214e  add     rsp, 0B0h
0x180012155  pop     r14
0x180012157  pop     rdi
0x180012158  pop     rbp
0x180012159  retn
0x18001215b  call    cs:__imp_GetLastError
0x180012162  nop     dword ptr [rax+rax+00h]
0x180012167  nop
0x180012168  mov     ebx, eax
0x18001216a  test    eax, eax
0x18001216c  jle     short loc_180012177
0x18001216e  movzx   ebx, ax
0x180012171  or      ebx, 80070000h
0x180012177  lea     rax, WPP_GLOBAL_Control
0x18001217e  mov     rcx, cs:WPP_GLOBAL_Control
0x180012185  cmp     rcx, rax
0x180012188  jz      short loc_1800121A8
0x18001218a  test    byte ptr [rcx+44h], 1
0x18001218e  jz      short loc_1800121A8
0x180012190  mov     edx, 0Bh
0x180012195  mov     r9d, ebx
0x180012198  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x18001219f  mov     rcx, [rcx+38h]
0x1800121a3  call    WPP_SF_d
0x1800121a8  mov     edx, ebx; int
0x1800121aa  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800121ae  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800121b3  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800121ba  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800121be  call    _CxxThrowException_0
0x1800121c4  call    cs:__imp_GetLastError
0x1800121cb  nop     dword ptr [rax+rax+00h]
0x1800121d0  mov     ebx, eax
0x1800121d2  test    eax, eax
0x1800121d4  jle     short loc_1800121DF
0x1800121d6  movzx   ebx, ax
0x1800121d9  or      ebx, 80070000h
0x1800121df  lea     rax, WPP_GLOBAL_Control
0x1800121e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800121ed  cmp     rcx, rax
0x1800121f0  jz      short loc_180012210
0x1800121f2  test    byte ptr [rcx+44h], 1
0x1800121f6  jz      short loc_180012210
0x1800121f8  mov     edx, 18h
0x1800121fd  mov     r9d, ebx
0x180012200  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x180012207  mov     rcx, [rcx+38h]
0x18001220b  call    WPP_SF_d
0x180012210  mov     edx, ebx; int
0x180012212  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180012216  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18001221b  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180012222  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180012226  call    _CxxThrowException_0
```
