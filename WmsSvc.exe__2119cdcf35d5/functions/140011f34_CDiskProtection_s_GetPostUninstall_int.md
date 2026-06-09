# CDiskProtection::s_GetPostUninstall(int *)

- ea: `0x140011f34`
- end: `0x14001214f`
- name: `?s_GetPostUninstall@CDiskProtection@@SAJPEAH@Z`
- size: `539`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x140007fd0`

## callees

- `0x140011f34`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140012133`
- `ADVAPI32!RegCloseKey` at `0x140012133`
- `ADVAPI32!RegCreateKeyExW` at `0x140011fa6`
- `ADVAPI32!RegCreateKeyExW` at `0x140011fa6`
- `ADVAPI32!RegQueryValueExW` at `0x140012084`
- `ADVAPI32!RegQueryValueExW` at `0x140012084`
- `KERNEL32!IsDebuggerPresent` at `0x140011ff9`
- `KERNEL32!IsDebuggerPresent` at `0x140012104`
- `KERNEL32!IsDebuggerPresent` at `0x140011ff9`
- `KERNEL32!IsDebuggerPresent` at `0x140012104`

## string_xrefs

- `0x140011fcc`: `CDiskProtection::s_GetPostUninstall`
- `0x1400120d3`: `CDiskProtection::s_GetPostUninstall`
- `0x140012078`: `PostUninstall`
- `0x140011f59`: `System\CurrentControlSet\Services\WMS\Parameters\`

## pseudocode

```c
__int64 __fastcall CDiskProtection::s_GetPostUninstall(int *a1)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  const unsigned __int16 *v4; // r13
  __int64 v5; // r9
  __int64 v6; // r8
  LSTATUS v7; // eax
  __int64 v9; // [rsp+30h] [rbp-30h]
  __int64 v10; // [rsp+38h] [rbp-28h]
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  DWORD Type; // [rsp+98h] [rbp+38h] BYREF
  int Data; // [rsp+A0h] [rbp+40h] BYREF
  DWORD cbData; // [rsp+A8h] [rbp+48h] BYREF

  hKey = 0;
  Data = 0;
  Type = 0;
  cbData = 4;
  v2 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\WMS\\Parameters\\",
         0,
         0,
         0,
         1u,
         0,
         &hKey,
         0);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    v4 = L"err == 0L";
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      0x74Au,
      L"CDiskProtection::s_GetPostUninstall",
      L"CBRAEx",
      L"err == 0L",
      v3);
    if ( IsDebuggerPresent() )
    {
      v5 = 1866;
LABEL_6:
      LODWORD(v10) = v3;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        v5,
        L"CDiskProtection::s_GetPostUninstall",
        L"CBRAEx",
        v4,
        v10);
      goto LABEL_23;
    }
    v6 = 1866;
LABEL_8:
    LODWORD(v9) = v3;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      v6,
      L"CDiskProtection::s_GetPostUninstall",
      L"CBRAEx",
      v4,
      v9);
    goto LABEL_23;
  }
  v7 = RegQueryValueExW(hKey, L"PostUninstall", 0, &Type, (LPBYTE)&Data, &cbData);
  v3 = v7;
  if ( v7 == 2 )
  {
    v3 = 0;
  }
  else if ( v7 )
  {
    if ( v7 > 0 )
      v3 = (unsigned __int16)v7 | 0x80070000;
  }
  else if ( Type == 4 )
  {
    v3 = 0;
    if ( Data )
    {
      if ( Data != 1 )
      {
        v3 = -2147418113;
        v4 = L"0";
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
          0x761u,
          L"CDiskProtection::s_GetPostUninstall",
          L"CBRAEx",
          L"0",
          -2147418113);
        if ( IsDebuggerPresent() )
        {
          v5 = 1889;
          goto LABEL_6;
        }
        v6 = 1889;
        goto LABEL_8;
      }
      *a1 = 1;
    }
    else
    {
      *a1 = 0;
    }
  }
  else
  {
    v3 = -2147467259;
  }
LABEL_23:
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x140011f34  mov     r11, rsp
0x140011f37  mov     [r11+8], rbx
0x140011f3b  push    rbp
0x140011f3c  push    rsi
0x140011f3d  push    rdi
0x140011f3e  push    r13
0x140011f40  push    r14
0x140011f42  mov     rbp, rsp
0x140011f45  sub     rsp, 60h
0x140011f49  mov     qword ptr [r11-48h], 0
0x140011f51  lea     rax, [rbp+hKey]
0x140011f55  mov     [r11-50h], rax
0x140011f59  lea     rdx, ?s_szServiceParametersKey@CDiskProtection@@1QBGB; "System\\CurrentControlSet\\Services\\WM"...
0x140011f60  mov     qword ptr [r11-58h], 0
0x140011f68  mov     rdi, rcx
0x140011f6b  mov     esi, 1
0x140011f70  mov     [rbp+hKey], 0
0x140011f78  mov     [rsp+60h+samDesired], esi; samDesired
0x140011f7c  xor     r9d, r9d; lpClass
0x140011f7f  xor     r8d, r8d; Reserved
0x140011f82  mov     [rsp+60h+dwOptions], 0; dwOptions
0x140011f8a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140011f91  mov     [rbp+Data], 0
0x140011f98  mov     [rbp+Type], 0
0x140011f9f  mov     [rbp+cbData], 4
0x140011fa6  call    cs:__imp_RegCreateKeyExW
0x140011fac  mov     ebx, eax
0x140011fae  test    eax, eax
0x140011fb0  jz      loc_140012060
0x140011fb6  jle     short loc_140011FC1
0x140011fb8  movzx   ebx, ax
0x140011fbb  or      ebx, 80070000h
0x140011fc1  lea     r14, aCbraex; "CBRAEx"
0x140011fc8  mov     [rsp+60h+samDesired], ebx; int
0x140011fcc  lea     rsi, aCdiskprotectio_178; "CDiskProtection::s_GetPostUninstall"
0x140011fd3  mov     r9, r14; unsigned __int16 *
0x140011fd6  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140011fdd  mov     r8, rsi; unsigned __int16 *
0x140011fe0  lea     r13, aErr0l; "err == 0L"
0x140011fe7  mov     rcx, rdi; unsigned __int16 *
0x140011fea  mov     edx, 74Ah; unsigned int
0x140011fef  mov     qword ptr [rsp+60h+dwOptions], r13; unsigned __int16 *
0x140011ff4  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140011ff9  call    cs:__imp_IsDebuggerPresent
0x140011fff  test    eax, eax
0x140012001  jz      short loc_140012035
0x140012003  mov     r9d, 74Ah
0x140012009  mov     dword ptr [rsp+60h+var_28], ebx
0x14001200d  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140012014  mov     [rsp+60h+var_30], r13
0x140012019  mov     r8, rdi
0x14001201c  mov     qword ptr [rsp+60h+samDesired], r14
0x140012021  mov     ecx, 2; unsigned __int8
0x140012026  mov     qword ptr [rsp+60h+dwOptions], rsi
0x14001202b  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140012030  jmp     loc_14001212A
0x140012035  mov     r8d, 74Ah
0x14001203b  mov     dword ptr [rsp+60h+var_30], ebx
0x14001203f  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140012046  mov     qword ptr [rsp+60h+samDesired], r13
0x14001204b  mov     r9, rsi
0x14001204e  mov     rdx, rdi
0x140012051  mov     qword ptr [rsp+60h+dwOptions], r14
0x140012056  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14001205b  jmp     loc_14001212A
0x140012060  mov     rcx, [rbp+hKey]; hKey
0x140012064  lea     rax, [rbp+cbData]
0x140012068  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x14001206d  lea     r9, [rbp+Type]; lpType
0x140012071  lea     rax, [rbp+Data]
0x140012075  xor     r8d, r8d; lpReserved
0x140012078  lea     rdx, ?s_szPostUninstallRegValueName@CDiskProtection@@1QBGB; "PostUninstall"
0x14001207f  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x140012084  call    cs:__imp_RegQueryValueExW
0x14001208a  mov     ebx, eax
0x14001208c  cmp     eax, 2
0x14001208f  jnz     short loc_140012098
0x140012091  xor     ebx, ebx
0x140012093  jmp     loc_14001212A
0x140012098  test    eax, eax
0x14001209a  jz      short loc_1400120AD
0x14001209c  jle     loc_14001212A
0x1400120a2  movzx   ebx, ax
0x1400120a5  or      ebx, 80070000h
0x1400120ab  jmp     short loc_14001212A
0x1400120ad  cmp     [rbp+Type], 4
0x1400120b1  jz      short loc_1400120BA
0x1400120b3  mov     ebx, 80004005h
0x1400120b8  jmp     short loc_14001212A
0x1400120ba  mov     eax, [rbp+Data]
0x1400120bd  xor     ebx, ebx
0x1400120bf  test    eax, eax
0x1400120c1  jz      short loc_140012128
0x1400120c3  cmp     eax, esi
0x1400120c5  jz      short loc_140012124
0x1400120c7  mov     ebx, 8000FFFFh
0x1400120cc  lea     r14, aCbraex; "CBRAEx"
0x1400120d3  lea     rsi, aCdiskprotectio_178; "CDiskProtection::s_GetPostUninstall"
0x1400120da  mov     [rsp+60h+samDesired], ebx; int
0x1400120de  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x1400120e5  mov     r9, r14; unsigned __int16 *
0x1400120e8  lea     r13, a0; "0"
0x1400120ef  mov     r8, rsi; unsigned __int16 *
0x1400120f2  mov     rcx, rdi; unsigned __int16 *
0x1400120f5  mov     qword ptr [rsp+60h+dwOptions], r13; unsigned __int16 *
0x1400120fa  mov     edx, 761h; unsigned int
0x1400120ff  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140012104  call    cs:__imp_IsDebuggerPresent
0x14001210a  test    eax, eax
0x14001210c  jz      short loc_140012119
0x14001210e  mov     r9d, 761h
0x140012114  jmp     loc_140012009
0x140012119  mov     r8d, 761h
0x14001211f  jmp     loc_14001203B
0x140012124  mov     [rdi], esi
0x140012126  jmp     short loc_14001212A
0x140012128  mov     [rdi], ebx
0x14001212a  mov     rcx, [rbp+hKey]; hKey
0x14001212e  test    rcx, rcx
0x140012131  jz      short loc_140012139
0x140012133  call    cs:__imp_RegCloseKey
0x140012139  mov     eax, ebx
0x14001213b  mov     rbx, [rsp+60h+arg_0]
0x140012143  add     rsp, 60h
0x140012147  pop     r14
0x140012149  pop     r13
0x14001214b  pop     rdi
0x14001214c  pop     rsi
0x14001214d  pop     rbp
0x14001214e  retn
```
