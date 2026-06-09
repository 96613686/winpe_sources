# OfflineKey::OpenSubkey(ushort const *,PushButtonReset::RegKey * *)

- ea: `0x180057b20`
- end: `0x180057cd2`
- name: `?OpenSubkey@OfflineKey@@UEAAJPEBGPEAPEAVRegKey@PushButtonReset@@@Z`
- size: `434`
- prototype: `int(OfflineKey *__hidden this, const unsigned __int16 *, struct PushButtonReset::RegKey **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x180005c00`
- `0x180005cc0`
- `0x18000d5c0`
- `0x180037344`
- `0x180053c30`
- `0x180053c58`
- `0x180056d64`
- `0x180057b20`

## import_xrefs

- `ADVAPI32!RegDeleteKeyExW` at `0x180057c03`
- `ADVAPI32!RegDeleteKeyExW` at `0x180057c03`
- `ADVAPI32!RegCreateKeyExW` at `0x180057b93`
- `ADVAPI32!RegCreateKeyExW` at `0x180057b93`

## string_xrefs

- `0x180057bb1`: `Failed to open [%s]`
- `0x180057bcc`: `OfflineKey::OpenSubkey`
- `0x180057c5f`: `OfflineKey::OpenSubkey`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OfflineKey::OpenSubkey(HKEY *this, const unsigned __int16 *a2, struct PushButtonReset::RegKey **a3)
{
  HKEY *phkResult; // rax
  LSTATUS v7; // eax
  unsigned int v8; // ebx
  struct PushButtonReset::RegKey *v9; // rax
  void **v11; // [rsp+50h] [rbp-20h] BYREF
  __int64 v12; // [rsp+58h] [rbp-18h]
  void **v13; // [rsp+60h] [rbp-10h] BYREF
  __int64 v14; // [rsp+68h] [rbp-8h] BYREF
  char v15; // [rsp+A0h] [rbp+30h] BYREF
  DWORD dwDisposition; // [rsp+B8h] [rbp+48h] BYREF

  v13 = &RAII::CAutoCleanup<HKEY__ *>::`vftable';
  v14 = 0;
  dwDisposition = 0;
  phkResult = (HKEY *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v13);
  v7 = RegCreateKeyExW(this[2], a2, 0, 0, 4u, 0xF003Fu, 0, phkResult, &dwDisposition);
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  if ( (v8 & 0x80000000) == 0 )
  {
    if ( dwDisposition == 1 )
    {
      RAII::CAutoCleanup<HKEY__ *>::Release(&v13);
      RegDeleteKeyExW(this[2], a2, 0xF003Fu, 0);
      v8 = -2147024893;
    }
    else
    {
      v15 = 0;
      v12 = PbrNew<OfflineKey,OfflineHive * &,RAII::CAutoCleanup<HKEY__ *> &,bool>(this + 1, &v13, &v15);
      v11 = &RAII::CAutoPbrDelete<OfflineKey *>::`vftable';
      if ( (unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!((__int64 *)&v11) )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          2147942414LL,
          "OfflineKey::OpenSubkey",
          "base\\reset\\util\\src\\regoffline.cpp",
          400,
          L"Failed to allocate key");
        v11 = &RAII::CAutoPbrDelete<OfflineKey *>::`vftable';
        RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(&v11);
        v8 = -2147024882;
      }
      else
      {
        v14 = 0;
        v9 = (struct PushButtonReset::RegKey *)v12;
        v12 = 0;
        *a3 = v9;
        v11 = &RAII::CAutoPbrDelete<OfflineKey *>::`vftable';
        RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(&v11);
      }
    }
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      v8,
      "OfflineKey::OpenSubkey",
      "base\\reset\\util\\src\\regoffline.cpp",
      389,
      L"Failed to open [%s]",
      a2);
  }
  v13 = &RAII::CAutoCleanup<HKEY__ *>::`vftable';
  RAII::CleanupInfo<HKEY__ *>::Release(&v14);
  return v8;
}

```

## disassembly

```asm
0x180057b20  mov     [rsp-28h+arg_8], rbx
0x180057b25  push    rbp
0x180057b26  push    rsi
0x180057b27  push    rdi
0x180057b28  push    r12
0x180057b2a  push    r14
0x180057b2c  mov     rbp, rsp
0x180057b2f  sub     rsp, 70h
0x180057b33  mov     r14, r8
0x180057b36  mov     rdi, rdx
0x180057b39  mov     rsi, rcx
0x180057b3c  lea     r12, ??_7?$CAutoCleanup@PEAUHKEY__@@@RAII@@6B@; const RAII::CAutoCleanup<HKEY__ *>::`vftable'
0x180057b43  mov     [rbp+var_10], r12
0x180057b47  mov     [rbp+var_8], 0
0x180057b4f  mov     [rbp+dwDisposition], 0
0x180057b56  lea     rcx, [rbp+var_10]
0x180057b5a  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180057b5f  lea     rcx, [rbp+dwDisposition]
0x180057b63  mov     [rsp+70h+lpdwDisposition], rcx; lpdwDisposition
0x180057b68  mov     [rsp+70h+phkResult], rax; phkResult
0x180057b6d  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180057b76  mov     [rsp+70h+samDesired], 0F003Fh; samDesired
0x180057b7e  mov     [rsp+70h+dwOptions], 4; dwOptions
0x180057b86  xor     r9d, r9d; lpClass
0x180057b89  xor     r8d, r8d; Reserved
0x180057b8c  mov     rdx, rdi; lpSubKey
0x180057b8f  mov     rcx, [rsi+10h]; hKey
0x180057b93  call    cs:__imp_RegCreateKeyExW
0x180057b99  mov     ebx, eax
0x180057b9b  test    eax, eax
0x180057b9d  jle     short loc_180057BA8
0x180057b9f  movzx   ebx, ax
0x180057ba2  or      ebx, 80070000h
0x180057ba8  test    ebx, ebx
0x180057baa  jns     short loc_180057BE4
0x180057bac  mov     [rsp+70h+lpSecurityAttributes], rdi
0x180057bb1  lea     rax, aFailedToOpenS; "Failed to open [%s]"
0x180057bb8  mov     qword ptr [rsp+70h+samDesired], rax
0x180057bbd  mov     [rsp+70h+dwOptions], 185h
0x180057bc5  lea     r9, aBaseResetUtilS_3; "base\\reset\\util\\src\\regoffline.cpp"
0x180057bcc  lea     r8, aOfflinekeyOpen; "OfflineKey::OpenSubkey"
0x180057bd3  mov     edx, ebx
0x180057bd5  mov     ecx, 2
0x180057bda  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180057bdf  jmp     loc_180057CAF
0x180057be4  cmp     [rbp+dwDisposition], 1
0x180057be8  jnz     short loc_180057C13
0x180057bea  lea     rcx, [rbp+var_10]
0x180057bee  call    ?Release@?$CAutoCleanup@PEAUHKEY__@@@RAII@@UEAAXXZ; RAII::CAutoCleanup<HKEY__ *>::Release(void)
0x180057bf3  xor     r9d, r9d; Reserved
0x180057bf6  mov     r8d, 0F003Fh; samDesired
0x180057bfc  mov     rdx, rdi; lpSubKey
0x180057bff  mov     rcx, [rsi+10h]; hKey
0x180057c03  call    cs:__imp_RegDeleteKeyExW
0x180057c09  mov     ebx, 80070003h
0x180057c0e  jmp     loc_180057CAF
0x180057c13  mov     [rbp+arg_0], 0
0x180057c17  lea     rcx, [rsi+8]
0x180057c1b  lea     r8, [rbp+arg_0]
0x180057c1f  lea     rdx, [rbp+var_10]
0x180057c23  call    ??$PbrNew@VOfflineKey@@AEAPEAVOfflineHive@@AEAV?$CAutoCleanup@PEAUHKEY__@@@RAII@@_N@@YAPEAVOfflineKey@@AEAPEAVOfflineHive@@AEAV?$CAutoCleanup@PEAUHKEY__@@@RAII@@$$QEA_N@Z; PbrNew<OfflineKey,OfflineHive * &,RAII::CAutoCleanup<HKEY__ *> &,bool>(OfflineHive * &,RAII::CAutoCleanup<HKEY__ *> &,bool &&)
0x180057c28  mov     [rbp+var_18], rax
0x180057c2c  lea     rdi, ??_7?$CAutoPbrDelete@PEAVOfflineKey@@@RAII@@6B@; const RAII::CAutoPbrDelete<OfflineKey *>::`vftable'
0x180057c33  mov     [rbp+var_20], rdi
0x180057c37  lea     rcx, [rbp+var_20]
0x180057c3b  call    ??7?$CAutoCleanupBase@PEAUISetupOneSettings@@@RAII@@UEBA_NXZ; RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(void)
0x180057c40  test    al, al
0x180057c42  jz      short loc_180057C8A
0x180057c44  lea     rax, aFailedToAlloca_31; "Failed to allocate key"
0x180057c4b  mov     qword ptr [rsp+70h+samDesired], rax
0x180057c50  mov     [rsp+70h+dwOptions], 190h
0x180057c58  lea     r9, aBaseResetUtilS_3; "base\\reset\\util\\src\\regoffline.cpp"
0x180057c5f  lea     r8, aOfflinekeyOpen; "OfflineKey::OpenSubkey"
0x180057c66  mov     edx, 8007000Eh
0x180057c6b  mov     ecx, 2
0x180057c70  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180057c75  nop
0x180057c76  mov     [rbp+var_20], rdi
0x180057c7a  lea     rcx, [rbp+var_20]
0x180057c7e  call    ?Release@?$CAutoPbrDelete@PEAVPrepareWinRE@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(void)
0x180057c83  mov     ebx, 8007000Eh
0x180057c88  jmp     short loc_180057CAF
0x180057c8a  mov     [rbp+var_8], 0
0x180057c92  mov     rax, [rbp+var_18]
0x180057c96  mov     [rbp+var_18], 0
0x180057c9e  mov     [r14], rax
0x180057ca1  mov     [rbp+var_20], rdi
0x180057ca5  lea     rcx, [rbp+var_20]
0x180057ca9  call    ?Release@?$CAutoPbrDelete@PEAVPrepareWinRE@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(void)
0x180057cae  nop
0x180057caf  mov     [rbp+var_10], r12
0x180057cb3  lea     rcx, [rbp+var_8]
0x180057cb7  call    ?Release@?$CleanupInfo@PEAUHKEY__@@@RAII@@SAXAEAPEAUHKEY__@@@Z; RAII::CleanupInfo<HKEY__ *>::Release(HKEY__ * &)
0x180057cbc  mov     eax, ebx
0x180057cbe  mov     rbx, [rsp+70h+arg_8]
0x180057cc6  add     rsp, 70h
0x180057cca  pop     r14
0x180057ccc  pop     r12
0x180057cce  pop     rdi
0x180057ccf  pop     rsi
0x180057cd0  pop     rbp
0x180057cd1  retn
```
