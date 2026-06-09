# PushButtonReset::WindowsRE::OpenConfig(PushButtonReset::WindowsRE::Config * *)

- ea: `0x180053afc`
- end: `0x180053c2a`
- name: `?OpenConfig@WindowsRE@PushButtonReset@@SAJPEAPEAVConfig@12@@Z`
- size: `302`
- prototype: `__int64 __fastcall(struct PushButtonReset::WindowsRE::Config **)`
- caller_count: `6`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180015f00`
- `0x1800168a0`
- `0x1800173a0`
- `0x18001b268`
- `0x18001e51c`
- `0x180053830`

## callees

- `0x180005c00`
- `0x18000d6f0`
- `0x180037344`
- `0x1800535fc`
- `0x180053afc`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180053ba4`
- `KERNEL32!GetLastError` at `0x180053be4`
- `KERNEL32!GetLastError` at `0x180053ba4`
- `KERNEL32!GetLastError` at `0x180053be4`
- `ReAgent!WinReGetConfig` at `0x180053b9a`
- `ReAgent!WinReGetConfig` at `0x180053b9a`

## string_xrefs

- `0x180053b48`: `PushButtonReset::WindowsRE::OpenConfig`
- `0x180053bd1`: `PushButtonReset::WindowsRE::OpenConfig`
- `0x180053bb6`: `Failed to load system WinRE config`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PushButtonReset::WindowsRE::OpenConfig(struct PushButtonReset::WindowsRE::Config **a1)
{
  unsigned int v2; // ebx
  __int64 v3; // rax
  signed int LastError; // eax
  signed int v5; // eax
  struct PushButtonReset::WindowsRE::Config *v6; // rax
  void **v8; // [rsp+30h] [rbp-18h] BYREF
  __int64 v9; // [rsp+38h] [rbp-10h]

  v9 = PbrNew<PushButtonReset::WindowsRE::Config,>();
  v8 = &RAII::CAutoPbrDelete<PushButtonReset::WindowsRE::Config *>::`vftable';
  if ( (unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(&v8) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942414LL,
      "PushButtonReset::WindowsRE::OpenConfig",
      "base\\reset\\util\\src\\windowsre.cpp",
      275,
      L"Failed to allocate result");
    v2 = -2147024882;
  }
  else
  {
    *(_QWORD *)((__int64 (__fastcall *)(void ***))v8[3])(&v8) = 3744;
    v3 = ((__int64 (__fastcall *)(void ***))v8[3])(&v8);
    if ( (unsigned int)WinReGetConfig(0, v3) )
    {
      v6 = (struct PushButtonReset::WindowsRE::Config *)v9;
      v9 = 0;
      *a1 = v6;
      v2 = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)LastError,
        "PushButtonReset::WindowsRE::OpenConfig",
        "base\\reset\\util\\src\\windowsre.cpp",
        282,
        L"Failed to load system WinRE config");
      v5 = GetLastError();
      v2 = v5;
      if ( v5 > 0 )
        v2 = (unsigned __int16)v5 | 0x80070000;
    }
  }
  v8 = &RAII::CAutoPbrDelete<PushButtonReset::WindowsRE::Config *>::`vftable';
  RAII::CAutoPbrHeapFree<unsigned short *>::Release(&v8);
  return v2;
}

```

## disassembly

```asm
0x180053afc  mov     [rsp+arg_0], rbx
0x180053b01  push    rsi
0x180053b02  sub     rsp, 40h
0x180053b06  mov     rbx, rcx
0x180053b09  call    ??$PbrNew@VConfig@WindowsRE@PushButtonReset@@$$V@@YAPEAVConfig@WindowsRE@PushButtonReset@@XZ; PbrNew<PushButtonReset::WindowsRE::Config,>(void)
0x180053b0e  mov     [rsp+48h+var_10], rax
0x180053b13  lea     rsi, ??_7?$CAutoPbrDelete@PEAVConfig@WindowsRE@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::WindowsRE::Config *>::`vftable'
0x180053b1a  mov     [rsp+48h+var_18], rsi
0x180053b1f  lea     rcx, [rsp+48h+var_18]
0x180053b24  call    ??7?$CAutoCleanupBase@PEAUISetupOneSettings@@@RAII@@UEBA_NXZ; RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(void)
0x180053b29  test    al, al
0x180053b2b  jz      short loc_180053B68
0x180053b2d  lea     rax, aFailedToAlloca_43; "Failed to allocate result"
0x180053b34  mov     [rsp+48h+var_20], rax
0x180053b39  mov     [rsp+48h+var_28], 113h
0x180053b41  lea     r9, aBaseResetUtilS_11; "base\\reset\\util\\src\\windowsre.cpp"
0x180053b48  lea     r8, aPushbuttonrese_0; "PushButtonReset::WindowsRE::OpenConfig"
0x180053b4f  mov     edx, 8007000Eh
0x180053b54  mov     ecx, 2
0x180053b59  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180053b5e  mov     ebx, 8007000Eh
0x180053b63  jmp     loc_180053C0E
0x180053b68  mov     rax, [rsp+48h+var_18]
0x180053b6d  lea     rcx, [rsp+48h+var_18]
0x180053b72  mov     rax, [rax+18h]
0x180053b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b7b  mov     qword ptr [rax], 0EA0h
0x180053b82  mov     rax, [rsp+48h+var_18]
0x180053b87  lea     rcx, [rsp+48h+var_18]
0x180053b8c  mov     rax, [rax+18h]
0x180053b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b95  mov     rdx, rax
0x180053b98  xor     ecx, ecx
0x180053b9a  call    cs:__imp_WinReGetConfig
0x180053ba0  test    eax, eax
0x180053ba2  jnz     short loc_180053BFB
0x180053ba4  call    cs:__imp_GetLastError
0x180053baa  test    eax, eax
0x180053bac  jle     short loc_180053BB6
0x180053bae  movzx   eax, ax
0x180053bb1  or      eax, 80070000h
0x180053bb6  lea     rcx, aFailedToLoadSy; "Failed to load system WinRE config"
0x180053bbd  mov     [rsp+48h+var_20], rcx
0x180053bc2  mov     [rsp+48h+var_28], 11Ah
0x180053bca  lea     r9, aBaseResetUtilS_11; "base\\reset\\util\\src\\windowsre.cpp"
0x180053bd1  lea     r8, aPushbuttonrese_0; "PushButtonReset::WindowsRE::OpenConfig"
0x180053bd8  mov     edx, eax
0x180053bda  mov     ecx, 2
0x180053bdf  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180053be4  call    cs:__imp_GetLastError
0x180053bea  mov     ebx, eax
0x180053bec  test    eax, eax
0x180053bee  jle     short loc_180053C0E
0x180053bf0  movzx   ebx, ax
0x180053bf3  or      ebx, 80070000h
0x180053bf9  jmp     short loc_180053C0E
0x180053bfb  mov     rax, [rsp+48h+var_10]
0x180053c00  mov     [rsp+48h+var_10], 0
0x180053c09  mov     [rbx], rax
0x180053c0c  xor     ebx, ebx
0x180053c0e  mov     [rsp+48h+var_18], rsi
0x180053c13  lea     rcx, [rsp+48h+var_18]
0x180053c18  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x180053c1d  mov     eax, ebx
0x180053c1f  mov     rbx, [rsp+48h+arg_0]
0x180053c24  add     rsp, 40h
0x180053c28  pop     rsi
0x180053c29  retn
```
