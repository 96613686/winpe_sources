# CSoftwareUpdates::GetAutomaticMaintenanceSettings(ulong *,int *)

- ea: `0x14002fad4`
- end: `0x14002feac`
- name: `?GetAutomaticMaintenanceSettings@CSoftwareUpdates@@AEAAJPEAKPEAH@Z`
- size: `984`
- prototype: `__int64 __fastcall(CSoftwareUpdates *__hidden this, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140030474`

## callees

- `0x14002fad4`
- `0x1400307e4`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14006296c`
- `0x14007e010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14002fe90`
- `ADVAPI32!RegCloseKey` at `0x14002fe90`
- `ADVAPI32!RegCreateKeyExW` at `0x14002fcf8`
- `ADVAPI32!RegCreateKeyExW` at `0x14002fcf8`
- `ADVAPI32!RegSetValueExW` at `0x14002fd4c`
- `ADVAPI32!RegSetValueExW` at `0x14002fd4c`
- `KERNEL32!IsDebuggerPresent` at `0x14002fdec`
- `KERNEL32!IsDebuggerPresent` at `0x14002fdec`
- `ole32!CoCreateInstance` at `0x14002fb54`
- `ole32!CoCreateInstance` at `0x14002fb54`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fe80`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fe80`
- `OLEAUT32!__imp_VariantInit` at `0x14002fb2f`
- `OLEAUT32!__imp_VariantInit` at `0x14002fb2f`

## string_xrefs

- `0x14002fdcf`: `termsrv\wms\src\devices\wmssvc\softwareupdates.cpp`
- `0x14002fdc4`: `CSoftwareUpdates::GetAutomaticMaintenanceSettings`
- `0x14002fcb9`: `System\CurrentControlSet\Services\WMS\Parameters\`

## pseudocode

```c
__int64 __fastcall CSoftwareUpdates::GetAutomaticMaintenanceSettings(CSoftwareUpdates *this, unsigned int *a2, int *a3)
{
  int v6; // ebx
  unsigned int v7; // r13d
  __int64 v8; // rax
  __int64 (__fastcall *v9)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *); // rax
  BSTR v10; // rax
  __int64 v11; // rcx
  LSTATUS v12; // eax
  const unsigned __int16 *v13; // r14
  const unsigned __int16 *v14; // r15
  LSTATUS v15; // eax
  const unsigned __int16 *v16; // r9
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-D0h]
  PHKEY phkResult; // [rsp+38h] [rbp-C8h]
  BYTE Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v21; // [rsp+54h] [rbp-ACh] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v23; // [rsp+60h] [rbp-A0h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-88h] BYREF
  __int128 v27; // [rsp+90h] [rbp-70h] BYREF
  IRecordInfo *pRecInfo; // [rsp+A0h] [rbp-60h]
  VARIANTARG v29; // [rsp+B0h] [rbp-50h] BYREF
  VARIANTARG v30; // [rsp+D0h] [rbp-30h] BYREF
  VARIANTARG v31; // [rsp+F0h] [rbp-10h] BYREF
  __int16 v32; // [rsp+178h] [rbp+78h] BYREF

  ppv = 0;
  v23 = 0;
  hKey = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v32 = 0;
  bstrString = 0;
  v21 = 0;
  *(_DWORD *)Data = 0;
  VariantInit(&pvarg);
  v6 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &ppv);
  if ( v6 < 0 )
  {
    v7 = 564;
LABEL_29:
    v13 = L"hr";
    v14 = L"CHRA";
LABEL_30:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
      v7,
      L"CSoftwareUpdates::GetAutomaticMaintenanceSettings",
      v14,
      v13,
      v6);
    if ( IsDebuggerPresent() )
    {
      LODWORD(phkResult) = v6;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
        v7,
        L"CSoftwareUpdates::GetAutomaticMaintenanceSettings",
        v14,
        v13,
        phkResult);
    }
    else
    {
      LODWORD(lpSecurityAttributes) = v6;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
        v7,
        L"CSoftwareUpdates::GetAutomaticMaintenanceSettings",
        v14,
        v13,
        lpSecurityAttributes);
    }
    goto LABEL_33;
  }
  v27 = *(_OWORD *)&pvarg.vt;
  v8 = *(_QWORD *)ppv;
  pRecInfo = pvarg.pRecInfo;
  v29 = pvarg;
  v9 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *))(v8 + 80);
  v30 = pvarg;
  v31 = pvarg;
  v6 = v9(ppv, &v31, &v30, &v29, &v27);
  if ( v6 < 0 )
  {
    v7 = 567;
    goto LABEL_29;
  }
  v6 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
         ppv,
         &GUID_77148e19_0c14_4138_8fb4_e0f456f53e1d,
         &v23);
  if ( v6 < 0 )
  {
    v7 = 570;
    goto LABEL_29;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v23 + 64LL))(v23, &bstrString);
  if ( v6 < 0 )
  {
    v7 = 577;
    goto LABEL_29;
  }
  if ( !bstrString )
  {
    v6 = -2147024809;
LABEL_28:
    v7 = 580;
    goto LABEL_29;
  }
  v10 = bstrString;
  v11 = 0x7FFFFFFF;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v11;
  }
  while ( v11 );
  v6 = v11 == 0 ? 0x80070057 : 0;
  if ( !v11 )
    goto LABEL_28;
  v6 = CSoftwareUpdates::ParseDateTime(this, bstrString, (0x7FFFFFFF - v11) & -(__int64)(v11 != 0), &v21);
  if ( v6 < 0 )
    goto LABEL_33;
  v6 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v23 + 80LL))(v23, &v32);
  if ( v6 < 0 )
  {
    v7 = 590;
    goto LABEL_29;
  }
  *(_DWORD *)Data = v32 == -1;
  v12 = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\WMS\\Parameters\\",
          0,
          0,
          0,
          2u,
          0,
          &hKey,
          0);
  v6 = v12;
  if ( v12 )
  {
    if ( v12 > 0 )
      v6 = (unsigned __int16)v12 | 0x80070000;
    v13 = L"err == 0L";
    v7 = 607;
    v14 = L"CBRAEx";
    goto LABEL_30;
  }
  v15 = RegSetValueExW(hKey, L"AmOriginalWakeupSystem", 0, 4u, Data, 4u);
  v6 = v15;
  if ( v15 )
  {
    if ( v15 > 0 )
      v6 = (unsigned __int16)v15 | 0x80070000;
    v13 = L"err == 0L";
    v7 = 610;
    v14 = L"CBRAEx";
    goto LABEL_30;
  }
  v6 = RegUtil::SetStringValue((RegUtil *)hKey, (HKEY)&stru_1400BB078, bstrString, v16);
  if ( v6 >= 0 )
  {
    *a2 = v21;
    *a3 = *(_DWORD *)Data;
  }
LABEL_33:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
  SysFreeString(bstrString);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14002fad4  push    rbp
0x14002fad6  push    rbx
0x14002fad7  push    rsi
0x14002fad8  push    rdi
0x14002fad9  push    r12
0x14002fadb  push    r13
0x14002fadd  push    r14
0x14002fadf  push    r15
0x14002fae1  lea     rbp, [rsp-18h]
0x14002fae6  sub     rsp, 118h
0x14002faed  xor     r12d, r12d
0x14002faf0  mov     rdi, rcx
0x14002faf3  xorps   xmm0, xmm0
0x14002faf6  mov     [rsp+150h+var_F8], r12
0x14002fafb  xor     eax, eax
0x14002fafd  mov     [rsp+150h+var_F0], r12
0x14002fb02  lea     rcx, [rsp+150h+pvarg]; pvarg
0x14002fb07  mov     [rsp+150h+hKey], r12
0x14002fb0c  movups  xmmword ptr [rsp+150h+pvarg], xmm0
0x14002fb11  mov     qword ptr [rbp+50h+pvarg+10h], rax
0x14002fb15  mov     rsi, r8
0x14002fb18  mov     [rbp+50h+arg_18], r12w
0x14002fb1d  mov     r14, rdx
0x14002fb20  mov     [rsp+150h+bstrString], r12
0x14002fb25  mov     [rsp+150h+var_FC], r12d
0x14002fb2a  mov     dword ptr [rsp+150h+Data], r12d
0x14002fb2f  call    cs:__imp_VariantInit
0x14002fb35  lea     rax, [rsp+150h+var_F8]
0x14002fb3a  xor     edx, edx; pUnkOuter
0x14002fb3c  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x14002fb43  mov     [rsp+150h+ppv], rax; ppv
0x14002fb48  lea     r8d, [r12+1]; dwClsContext
0x14002fb4d  lea     rcx, CLSID_TaskScheduler; rclsid
0x14002fb54  call    cs:__imp_CoCreateInstance
0x14002fb5a  mov     ebx, eax
0x14002fb5c  test    eax, eax
0x14002fb5e  jns     short loc_14002FB6B
0x14002fb60  mov     r13d, 234h
0x14002fb66  jmp     loc_14002FDB6
0x14002fb6b  movups  xmm1, xmmword ptr [rsp+150h+pvarg]
0x14002fb70  lea     rdx, [rbp+50h+var_C0]
0x14002fb74  mov     rcx, [rsp+150h+var_F8]
0x14002fb79  movsd   xmm0, qword ptr [rbp+50h+pvarg+10h]
0x14002fb7e  lea     r9, [rbp+50h+var_A0]
0x14002fb82  mov     [rsp+150h+ppv], rdx
0x14002fb87  lea     r8, [rbp+50h+var_80]
0x14002fb8b  lea     rdx, [rbp+50h+var_60]
0x14002fb8f  movaps  [rbp+50h+var_C0], xmm1
0x14002fb93  mov     rax, [rcx]
0x14002fb96  movsd   [rbp+50h+var_B0], xmm0
0x14002fb9b  movaps  [rbp+50h+var_A0], xmm1
0x14002fb9f  movsd   [rbp+50h+var_90], xmm0
0x14002fba4  mov     rax, [rax+50h]
0x14002fba8  movaps  [rbp+50h+var_80], xmm1
0x14002fbac  movsd   [rbp+50h+var_70], xmm0
0x14002fbb1  movaps  [rbp+50h+var_60], xmm1
0x14002fbb5  movsd   [rbp+50h+var_50], xmm0
0x14002fbba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002fbbf  mov     ebx, eax
0x14002fbc1  test    eax, eax
0x14002fbc3  jns     short loc_14002FBD0
0x14002fbc5  mov     r13d, 237h
0x14002fbcb  jmp     loc_14002FDB6
0x14002fbd0  mov     rcx, [rsp+150h+var_F8]
0x14002fbd5  lea     r8, [rsp+150h+var_F0]
0x14002fbda  lea     rdx, _GUID_77148e19_0c14_4138_8fb4_e0f456f53e1d
0x14002fbe1  mov     rax, [rcx]
0x14002fbe4  mov     rax, [rax]
0x14002fbe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002fbec  mov     ebx, eax
0x14002fbee  test    eax, eax
0x14002fbf0  jns     short loc_14002FBFD
0x14002fbf2  mov     r13d, 23Ah
0x14002fbf8  jmp     loc_14002FDB6
0x14002fbfd  mov     rcx, [rsp+150h+var_F0]
0x14002fc02  lea     rdx, [rsp+150h+bstrString]
0x14002fc07  mov     rax, [rcx]
0x14002fc0a  mov     rax, [rax+40h]
0x14002fc0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002fc13  mov     ebx, eax
0x14002fc15  test    eax, eax
0x14002fc17  jns     short loc_14002FC24
0x14002fc19  mov     r13d, 241h
0x14002fc1f  jmp     loc_14002FDB6
0x14002fc24  mov     r10, [rsp+150h+bstrString]
0x14002fc29  test    r10, r10
0x14002fc2c  jz      loc_14002FDAB
0x14002fc32  mov     edx, 7FFFFFFFh
0x14002fc37  mov     rax, r10
0x14002fc3a  mov     ecx, edx
0x14002fc3c  cmp     [rax], r12w
0x14002fc40  jz      short loc_14002FC4C
0x14002fc42  add     rax, 2
0x14002fc46  sub     rcx, 1
0x14002fc4a  jnz     short loc_14002FC3C
0x14002fc4c  mov     rax, rcx
0x14002fc4f  neg     rax
0x14002fc52  mov     rax, rcx
0x14002fc55  sbb     ebx, ebx
0x14002fc57  sub     rdx, rcx
0x14002fc5a  not     ebx
0x14002fc5c  and     ebx, 80070057h
0x14002fc62  neg     rax
0x14002fc65  sbb     r8, r8
0x14002fc68  and     r8, rdx; unsigned __int64
0x14002fc6b  test    rcx, rcx
0x14002fc6e  jz      loc_14002FDB0
0x14002fc74  lea     r9, [rsp+150h+var_FC]; unsigned int *
0x14002fc79  mov     rdx, r10; unsigned __int16 *
0x14002fc7c  mov     rcx, rdi; this
0x14002fc7f  call    ?ParseDateTime@CSoftwareUpdates@@AEAAJPEBG_KPEAI@Z; CSoftwareUpdates::ParseDateTime(ushort const *,unsigned __int64,uint *)
0x14002fc84  mov     ebx, eax
0x14002fc86  test    eax, eax
0x14002fc88  js      loc_14002FE45
0x14002fc8e  mov     rcx, [rsp+150h+var_F0]
0x14002fc93  lea     rdx, [rbp+50h+arg_18]
0x14002fc97  mov     rax, [rcx]
0x14002fc9a  mov     rax, [rax+50h]
0x14002fc9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002fca3  mov     ebx, eax
0x14002fca5  test    eax, eax
0x14002fca7  jns     short loc_14002FCB4
0x14002fca9  mov     r13d, 24Eh
0x14002fcaf  jmp     loc_14002FDB6
0x14002fcb4  cmp     [rbp+50h+arg_18], 0FFFFh
0x14002fcb9  lea     rdx, ?s_szRegKey@CSoftwareUpdates@@0QBGB; "System\\CurrentControlSet\\Services\\WM"...
0x14002fcc0  mov     [rsp+150h+lpdwDisposition], r12; lpdwDisposition
0x14002fcc5  mov     eax, r12d
0x14002fcc8  setz    al
0x14002fccb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14002fcd2  mov     dword ptr [rsp+150h+Data], eax
0x14002fcd6  xor     r9d, r9d; lpClass
0x14002fcd9  lea     rax, [rsp+150h+hKey]
0x14002fcde  xor     r8d, r8d; Reserved
0x14002fce1  mov     [rsp+150h+phkResult], rax; phkResult
0x14002fce6  mov     [rsp+150h+lpSecurityAttributes], r12; lpSecurityAttributes
0x14002fceb  mov     [rsp+150h+samDesired], 2; samDesired
0x14002fcf3  mov     dword ptr [rsp+150h+ppv], r12d; dwOptions
0x14002fcf8  call    cs:__imp_RegCreateKeyExW
0x14002fcfe  mov     ebx, eax
0x14002fd00  test    eax, eax
0x14002fd02  jz      short loc_14002FD28
0x14002fd04  jle     short loc_14002FD0F
0x14002fd06  movzx   ebx, ax
0x14002fd09  or      ebx, 80070000h
0x14002fd0f  lea     r14, aErr0l; "err == 0L"
0x14002fd16  mov     r13d, 25Fh
0x14002fd1c  lea     r15, aCbraex; "CBRAEx"
0x14002fd23  jmp     loc_14002FDC4
0x14002fd28  mov     rcx, [rsp+150h+hKey]; hKey
0x14002fd2d  lea     rax, [rsp+150h+Data]
0x14002fd32  mov     r9d, 4; dwType
0x14002fd38  lea     rdx, aAmoriginalwake; "AmOriginalWakeupSystem"
0x14002fd3f  mov     [rsp+150h+samDesired], r9d; cbData
0x14002fd44  xor     r8d, r8d; Reserved
0x14002fd47  mov     [rsp+150h+ppv], rax; lpData
0x14002fd4c  call    cs:__imp_RegSetValueExW
0x14002fd52  mov     ebx, eax
0x14002fd54  test    eax, eax
0x14002fd56  jz      short loc_14002FD79
0x14002fd58  jle     short loc_14002FD63
0x14002fd5a  movzx   ebx, ax
0x14002fd5d  or      ebx, 80070000h
0x14002fd63  lea     r14, aErr0l; "err == 0L"
0x14002fd6a  mov     r13d, 262h
0x14002fd70  lea     r15, aCbraex; "CBRAEx"
0x14002fd77  jmp     short loc_14002FDC4
0x14002fd79  mov     r8, [rsp+150h+bstrString]; unsigned __int16 *
0x14002fd7e  lea     rdx, stru_1400BB078; HKEY
0x14002fd85  mov     rcx, [rsp+150h+hKey]; this
0x14002fd8a  call    ?SetStringValue@RegUtil@@YAJPEAUHKEY__@@PEBG1@Z; RegUtil::SetStringValue(HKEY__ *,ushort const *,ushort const *)
0x14002fd8f  mov     ebx, eax
0x14002fd91  test    eax, eax
0x14002fd93  js      loc_14002FE45
0x14002fd99  mov     eax, [rsp+150h+var_FC]
0x14002fd9d  mov     [r14], eax
0x14002fda0  mov     eax, dword ptr [rsp+150h+Data]
0x14002fda4  mov     [rsi], eax
0x14002fda6  jmp     loc_14002FE45
0x14002fdab  mov     ebx, 80070057h
0x14002fdb0  mov     r13d, 244h
0x14002fdb6  lea     r14, aHr; "hr"
0x14002fdbd  lea     r15, aChra; "CHRA"
0x14002fdc4  lea     rsi, aCsoftwareupdat_6; "CSoftwareUpdates::GetAutomaticMaintenan"...
0x14002fdcb  mov     [rsp+150h+samDesired], ebx; int
0x14002fdcf  lea     rdi, aTermsrvWmsSrcD_18; "termsrv\\wms\\src\\devices\\wmssvc\\sof"...
0x14002fdd6  mov     [rsp+150h+ppv], r14; unsigned __int16 *
0x14002fddb  mov     r8, rsi; unsigned __int16 *
0x14002fdde  mov     rcx, rdi; unsigned __int16 *
0x14002fde1  mov     r9, r15; unsigned __int16 *
0x14002fde4  mov     edx, r13d; unsigned int
0x14002fde7  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002fdec  call    cs:__imp_IsDebuggerPresent
0x14002fdf2  test    eax, eax
0x14002fdf4  jz      short loc_14002FE22
0x14002fdf6  mov     dword ptr [rsp+150h+phkResult], ebx
0x14002fdfa  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14002fe01  mov     [rsp+150h+lpSecurityAttributes], r14
0x14002fe06  mov     r9d, r13d
0x14002fe09  mov     qword ptr [rsp+150h+samDesired], r15
0x14002fe0e  mov     r8, rdi
0x14002fe11  mov     ecx, 2; unsigned __int8
0x14002fe16  mov     [rsp+150h+ppv], rsi
0x14002fe1b  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002fe20  jmp     short loc_14002FE45
0x14002fe22  mov     dword ptr [rsp+150h+lpSecurityAttributes], ebx
0x14002fe26  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14002fe2d  mov     qword ptr [rsp+150h+samDesired], r14
0x14002fe32  mov     r9, rsi
0x14002fe35  mov     r8d, r13d
0x14002fe38  mov     [rsp+150h+ppv], r15
0x14002fe3d  mov     rdx, rdi
0x14002fe40  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14002fe45  mov     rcx, [rsp+150h+var_F8]
0x14002fe4a  test    rcx, rcx
0x14002fe4d  jz      short loc_14002FE60
0x14002fe4f  mov     rax, [rcx]
0x14002fe52  mov     rax, [rax+10h]
0x14002fe56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002fe5b  mov     [rsp+150h+var_F8], r12
0x14002fe60  mov     rcx, [rsp+150h+var_F0]
0x14002fe65  test    rcx, rcx
0x14002fe68  jz      short loc_14002FE7B
0x14002fe6a  mov     rax, [rcx]
0x14002fe6d  mov     rax, [rax+10h]
0x14002fe71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002fe76  mov     [rsp+150h+var_F0], r12
0x14002fe7b  mov     rcx, [rsp+150h+bstrString]; bstrString
0x14002fe80  call    cs:__imp_SysFreeString
0x14002fe86  mov     rcx, [rsp+150h+hKey]; hKey
0x14002fe8b  test    rcx, rcx
0x14002fe8e  jz      short loc_14002FE96
0x14002fe90  call    cs:__imp_RegCloseKey
0x14002fe96  mov     eax, ebx
0x14002fe98  add     rsp, 118h
0x14002fe9f  pop     r15
0x14002fea1  pop     r14
0x14002fea3  pop     r13
0x14002fea5  pop     r12
0x14002fea7  pop     rdi
0x14002fea8  pop     rsi
0x14002fea9  pop     rbx
0x14002feaa  pop     rbp
0x14002feab  retn
```
