# DeployDtc

- ea: `0x180012e50`
- end: `0x1800130ba`
- name: `DeployDtc`
- size: `618`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180006214`
- `0x18001156c`
- `0x180012e50`
- `0x18001d178`
- `0x18001d184`
- `0x1800508b4`
- `0x180051b40`
- `0x180074200`
- `0x180081dd0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ee4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ee4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f5c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180012ed8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180012f52`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180012ed8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180012f52`
- `msvcrt!_wcsicmp` at `0x180012f8a`
- `msvcrt!_wcsicmp` at `0x180012f8a`

## string_xrefs

- `0x180012e7b`: `com\complus\dtc\dtc\adme\deployment.cpp`
- `0x180013007`: `com\complus\dtc\dtc\adme\deployment.cpp`
- `0x18001304c`: `com\complus\dtc\dtc\adme\deployment.cpp`
- `0x180013082`: `com\complus\dtc\dtc\adme\deployment.cpp`
- `0x180012e90`: `%INSTALLER_SHADOWED_COMPONENT_VERSION%`
- `0x180012f96`: `DeployDtc: Environment variable INSTALLER_SHADOWED_COMPONENT_VERSION is set, indicating Uninstall - do nothing.`
- `0x180012fb7`: `DeployDtc: CreateLocalTmInstance failed`
- `0x180012fd8`: `DeployDtc: InstallContacts failed`
- `0x180012ff2`: `DeployDtc: InstallDtcAsAnOleTxTm failed`

## pseudocode

```c
__int64 DeployDtc()
{
  DWORD v0; // eax
  wchar_t *v1; // rdi
  signed int v2; // eax
  int v3; // ebx
  unsigned __int16 *v4; // rdx
  unsigned int v5; // r9d
  DWORD v6; // ebx
  WCHAR *v7; // rax
  signed int LastError; // eax
  struct ITmInstance *v10; // [rsp+20h] [rbp-19h] BYREF
  WCHAR Src[40]; // [rsp+30h] [rbp-9h] BYREF

  TraceFileW(0, L"Entering DeployDtc", L"com\\complus\\dtc\\dtc\\adme\\deployment.cpp", 0x3Bu);
  wcscpy(Src, L"%INSTALLER_SHADOWED_COMPONENT_ERSION%");
  v10 = 0;
  v0 = ExpandEnvironmentStringsW(Src, 0, 0);
  if ( v0 )
  {
    v6 = v0 + 2;
    v7 = (WCHAR *)operator new[](saturated_mul(v0 + 2, 2u));
    v1 = v7;
    if ( v7 )
    {
      if ( ExpandEnvironmentStringsW(Src, v7, v6) )
      {
        if ( _wcsicmp(v1, Src) )
        {
          v3 = 0;
          v4 = L"DeployDtc: Environment variable INSTALLER_SHADOWED_COMPONENT_VERSION is set, indicating Uninstall - do nothing.";
          v5 = 99;
        }
        else
        {
          v3 = CreateLocalTmInstance(0, &v10);
          if ( v3 >= 0 )
          {
            v3 = InstallContacts(v10);
            if ( v3 >= 0 )
            {
              v3 = InstallDtcAsAnOleTxTm();
              if ( v3 )
              {
                v4 = L"DeployDtc: InstallDtcAsAnOleTxTm failed";
                v5 = 123;
              }
              else
              {
                TraceFileW(
                  0,
                  L"DeployDtc: Calling SetSddlOnResources",
                  L"com\\complus\\dtc\\dtc\\adme\\deployment.cpp",
                  0x7Fu);
                v3 = SetSddlOnResources(v10, 0, 0);
                if ( v3 >= 0 )
                {
                  v4 = L"DeployDtc: SetSddlOnResources finished";
                  v5 = 136;
                }
                else
                {
                  v4 = L"DeployDtc: SetSddlOnResources failed";
                  v5 = 133;
                }
              }
            }
            else
            {
              v4 = L"DeployDtc: InstallContacts failed";
              v5 = 115;
            }
          }
          else
          {
            v4 = L"DeployDtc: CreateLocalTmInstance failed";
            v5 = 108;
          }
        }
      }
      else
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        v4 = L"DeployDtc: ExpandEnvironmentStringsW failed";
        v5 = 89;
      }
    }
    else
    {
      v3 = -2147024882;
      v4 = L"DeployDtc: Unable to allocate memory for expanded environment variable string.";
      v5 = 81;
    }
  }
  else
  {
    v1 = 0;
    v2 = GetLastError();
    v3 = v2;
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    v4 = L"DeployDtc: ExpandEnvironmentStringsW failed";
    v5 = 73;
  }
  TraceFileW(v3, v4, L"com\\complus\\dtc\\dtc\\adme\\deployment.cpp", v5);
  if ( v10 )
    (*(void (__fastcall **)(struct ITmInstance *))(*(_QWORD *)v10 + 16LL))(v10);
  if ( v1 )
    operator delete(v1);
  TraceFileW(v3, L"Exiting DeployDtc", L"com\\complus\\dtc\\dtc\\adme\\deployment.cpp", 0x8Fu);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180012e50  mov     [rsp-8+arg_0], rbx
0x180012e55  mov     [rsp-8+arg_8], rdi
0x180012e5a  push    rbp
0x180012e5b  lea     rbp, [rsp-57h]
0x180012e60  sub     rsp, 90h
0x180012e67  mov     rax, cs:__security_cookie
0x180012e6e  xor     rax, rsp
0x180012e71  mov     [rbp+57h+var_10], rax
0x180012e75  mov     r9d, 3Bh ; ';'; unsigned int
0x180012e7b  lea     r8, aComComplusDtcD_8; "com\\complus\\dtc\\dtc\\adme\\deploymen"...
0x180012e82  lea     rdx, aEnteringDeploy; "Entering DeployDtc"
0x180012e89  xor     ecx, ecx; int
0x180012e8b  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x180012e90  movaps  xmm0, xmmword ptr cs:aInstallerShado; "%INSTALLER_SHADOWED_COMPONENT_VERSION%"
0x180012e97  lea     rcx, [rbp+57h+Src]; lpSrc
0x180012e9b  movaps  xmm1, xmmword ptr cs:aInstallerShado+10h; "ER_SHADOWED_COMPONENT_VERSION%"
0x180012ea2  xor     r8d, r8d; nSize
0x180012ea5  movaps  xmmword ptr [rbp+57h+Src], xmm0
0x180012ea9  xor     edx, edx; lpDst
0x180012eab  movaps  xmm0, xmmword ptr cs:aInstallerShado+20h; "WED_COMPONENT_VERSION%"
0x180012eb2  movaps  [rbp+57h+var_40], xmm0
0x180012eb6  movups  xmm0, xmmword ptr cs:aInstallerShado+3Eh; "ERSION%"
0x180012ebd  mov     [rbp+57h+var_70], 0
0x180012ec5  movaps  [rbp+57h+var_50], xmm1
0x180012ec9  movaps  xmm1, xmmword ptr cs:aInstallerShado+30h; "ONENT_VERSION%"
0x180012ed0  movaps  [rbp+57h+var_30], xmm1
0x180012ed4  movups  [rbp+57h+var_30+0Eh], xmm0
0x180012ed8  call    cs:__imp_ExpandEnvironmentStringsW
0x180012ede  test    eax, eax
0x180012ee0  jnz     short loc_180012F0B
0x180012ee2  xor     edi, edi
0x180012ee4  call    cs:__imp_GetLastError
0x180012eea  mov     ebx, eax
0x180012eec  test    eax, eax
0x180012eee  jle     short loc_180012EF9
0x180012ef0  movzx   ebx, ax
0x180012ef3  or      ebx, 80070000h
0x180012ef9  lea     rdx, aDeploydtcExpan; "DeployDtc: ExpandEnvironmentStringsW fa"...
0x180012f00  mov     r9d, 49h ; 'I'
0x180012f06  jmp     loc_18001304C
0x180012f0b  lea     ebx, [rax+2]
0x180012f0e  mov     eax, 2
0x180012f13  mov     ecx, ebx
0x180012f15  mul     rcx
0x180012f18  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180012f1f  cmovb   rax, rcx
0x180012f23  mov     rcx, rax; unsigned __int64
0x180012f26  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180012f2b  mov     rdi, rax
0x180012f2e  test    rax, rax
0x180012f31  jnz     short loc_180012F48
0x180012f33  mov     ebx, 8007000Eh
0x180012f38  lea     rdx, aDeploydtcUnabl; "DeployDtc: Unable to allocate memory fo"...
0x180012f3f  lea     r9d, [rax+51h]
0x180012f43  jmp     loc_18001304C
0x180012f48  mov     r8d, ebx; nSize
0x180012f4b  lea     rcx, [rbp+57h+Src]; lpSrc
0x180012f4f  mov     rdx, rdi; lpDst
0x180012f52  call    cs:__imp_ExpandEnvironmentStringsW
0x180012f58  test    eax, eax
0x180012f5a  jnz     short loc_180012F83
0x180012f5c  call    cs:__imp_GetLastError
0x180012f62  mov     ebx, eax
0x180012f64  test    eax, eax
0x180012f66  jle     short loc_180012F71
0x180012f68  movzx   ebx, ax
0x180012f6b  or      ebx, 80070000h
0x180012f71  lea     rdx, aDeploydtcExpan; "DeployDtc: ExpandEnvironmentStringsW fa"...
0x180012f78  mov     r9d, 59h ; 'Y'
0x180012f7e  jmp     loc_18001304C
0x180012f83  lea     rdx, [rbp+57h+Src]; String2
0x180012f87  mov     rcx, rdi; String1
0x180012f8a  call    cs:__imp__wcsicmp
0x180012f90  test    eax, eax
0x180012f92  jz      short loc_180012FA6
0x180012f94  xor     ebx, ebx
0x180012f96  lea     rdx, aDeploydtcEnvir; "DeployDtc: Environment variable INSTALL"...
0x180012f9d  lea     r9d, [rbx+63h]
0x180012fa1  jmp     loc_18001304C
0x180012fa6  lea     rdx, [rbp+57h+var_70]; struct ITmInstance **
0x180012faa  xor     ecx, ecx; unsigned __int16 *
0x180012fac  call    ?CreateLocalTmInstance@@YAJPEBGPEAPEAUITmInstance@@@Z; CreateLocalTmInstance(ushort const *,ITmInstance * *)
0x180012fb1  mov     ebx, eax
0x180012fb3  test    eax, eax
0x180012fb5  jns     short loc_180012FC9
0x180012fb7  lea     rdx, aDeploydtcCreat; "DeployDtc: CreateLocalTmInstance failed"
0x180012fbe  mov     r9d, 6Ch ; 'l'
0x180012fc4  jmp     loc_18001304C
0x180012fc9  mov     rcx, [rbp+57h+var_70]; struct ITmInstance *
0x180012fcd  call    InstallContacts
0x180012fd2  mov     ebx, eax
0x180012fd4  test    eax, eax
0x180012fd6  jns     short loc_180012FE7
0x180012fd8  lea     rdx, aDeploydtcInsta_0; "DeployDtc: InstallContacts failed"
0x180012fdf  mov     r9d, 73h ; 's'
0x180012fe5  jmp     short loc_18001304C
0x180012fe7  call    InstallDtcAsAnOleTxTm
0x180012fec  mov     ebx, eax
0x180012fee  test    eax, eax
0x180012ff0  jz      short loc_180013001
0x180012ff2  lea     rdx, aDeploydtcInsta; "DeployDtc: InstallDtcAsAnOleTxTm failed"
0x180012ff9  mov     r9d, 7Bh ; '{'
0x180012fff  jmp     short loc_18001304C
0x180013001  mov     r9d, 7Fh; unsigned int
0x180013007  lea     r8, aComComplusDtcD_8; "com\\complus\\dtc\\dtc\\adme\\deploymen"...
0x18001300e  lea     rdx, aDeploydtcCalli; "DeployDtc: Calling SetSddlOnResources"
0x180013015  xor     ecx, ecx; int
0x180013017  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x18001301c  mov     rcx, [rbp+57h+var_70]; struct ITmInstance *
0x180013020  xor     r8d, r8d; int
0x180013023  xor     edx, edx; unsigned __int16 *
0x180013025  call    ?SetSddlOnResources@@YAJPEAUITmInstance@@PEAGH@Z; SetSddlOnResources(ITmInstance *,ushort *,int)
0x18001302a  mov     ebx, eax
0x18001302c  test    eax, eax
0x18001302e  jns     short loc_18001303F
0x180013030  lea     rdx, aDeploydtcSetsd_0; "DeployDtc: SetSddlOnResources failed"
0x180013037  mov     r9d, 85h
0x18001303d  jmp     short loc_18001304C
0x18001303f  lea     rdx, aDeploydtcSetsd; "DeployDtc: SetSddlOnResources finished"
0x180013046  mov     r9d, 88h; unsigned int
0x18001304c  lea     r8, aComComplusDtcD_8; "com\\complus\\dtc\\dtc\\adme\\deploymen"...
0x180013053  mov     ecx, ebx; int
0x180013055  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x18001305a  mov     rcx, [rbp+57h+var_70]
0x18001305e  test    rcx, rcx
0x180013061  jz      short loc_18001306F
0x180013063  mov     rax, [rcx]
0x180013066  mov     rax, [rax+10h]
0x18001306a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001306f  test    rdi, rdi
0x180013072  jz      short loc_18001307C
0x180013074  mov     rcx, rdi; Block
0x180013077  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001307c  mov     r9d, 8Fh; unsigned int
0x180013082  lea     r8, aComComplusDtcD_8; "com\\complus\\dtc\\dtc\\adme\\deploymen"...
0x180013089  lea     rdx, aExitingDeployd; "Exiting DeployDtc"
0x180013090  mov     ecx, ebx; int
0x180013092  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x180013097  mov     eax, ebx
0x180013099  mov     rcx, [rbp+57h+var_10]
0x18001309d  xor     rcx, rsp; StackCookie
0x1800130a0  call    __security_check_cookie
0x1800130a5  lea     r11, [rsp+90h+var_s0]
0x1800130ad  mov     rbx, [r11+10h]
0x1800130b1  mov     rdi, [r11+18h]
0x1800130b5  mov     rsp, r11
0x1800130b8  pop     rbp
0x1800130b9  retn
```
