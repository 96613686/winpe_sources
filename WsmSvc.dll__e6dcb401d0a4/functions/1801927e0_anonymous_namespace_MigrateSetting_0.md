# _anonymous_namespace_::MigrateSetting_0

- ea: `0x1801927e0`
- end: `0x180192dda`
- name: `_anonymous_namespace_::MigrateSetting_0`
- size: `1530`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180191878`
- `0x1801926c4`

## callees

- `0x180005d10`
- `0x180008920`
- `0x180013760`
- `0x180034f60`
- `0x18003e680`
- `0x1800621e0`
- `0x1800bac30`
- `0x1800d5e90`
- `0x1800e8a50`
- `0x1800ed980`
- `0x180105188`
- `0x180190f30`
- `0x1801910a8`
- `0x1801927e0`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `msvcrt!_itow_s` at `0x18019297f`
- `msvcrt!_itow_s` at `0x18019297f`
- `msvcrt!_wtoi` at `0x180192c03`
- `msvcrt!_wtoi` at `0x180192d7d`
- `msvcrt!_wtoi` at `0x180192c03`
- `msvcrt!_wtoi` at `0x180192d7d`
- `msvcrt!_wcsicmp` at `0x180192d65`
- `msvcrt!_wcsicmp` at `0x180192d65`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180192a1a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180192bba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180192a1a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180192bba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180192a09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180192a09`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180192b6b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180192b6b`

## string_xrefs

- `0x180192b2b`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WSMAN\Service`
- `0x180192b43`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WSMAN\Service`
- `0x18019283f`: `onecore\admin\wmi\wmx\config\wsmanconfigmigration.cpp`
- `0x18019286b`: `onecore\admin\wmi\wmx\config\wsmanconfigmigration.cpp`
- `0x180192ba3`: `RegOpenKeyEx`
- `0x180192b80`: `Migration ERROR in MigrateSetting: RegOpenKeyEx returned %lu for %ls `
- `0x180192d2d`: `Migration ERROR in MigrateSetting: GetSDDLWithReadToIU failed - Error: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall anonymous_namespace_::MigrateSetting_0(
        __int64 *a1,
        struct IRequestContext *a2,
        __int64 a3,
        __int64 a4,
        const WCHAR *a5,
        unsigned int *a6,
        __int64 a7,
        int a8,
        int a9,
        _DWORD *a10,
        __int64 a11)
{
  __int64 v15; // rax
  const unsigned __int16 *v16; // r8
  __int64 v17; // rdx
  int v19; // eax
  int v20; // edx
  unsigned int v21; // edi
  __int64 v22; // r14
  wchar_t *v23; // rax
  wchar_t *v24; // rbx
  __int64 v25; // r8
  char v26; // r12
  unsigned int v27; // r14d
  const WCHAR *v28; // r12
  unsigned int v29; // eax
  DWORD v30; // r14d
  const wchar_t *v31; // r8
  wchar_t *v32; // rcx
  __int64 v33; // rax
  _DWORD *v34; // r14
  const wchar_t *v35; // rcx
  unsigned int v36; // eax
  unsigned int v37; // ebx
  BYTE phkResult; // [rsp+20h] [rbp-A1h]
  PHKEY phkResulta; // [rsp+20h] [rbp-A1h]
  BYTE Data[4]; // [rsp+30h] [rbp-91h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-89h] BYREF
  wchar_t *String2; // [rsp+40h] [rbp-81h] BYREF
  __int64 v43; // [rsp+48h] [rbp-79h]
  const WCHAR *v44; // [rsp+50h] [rbp-71h] BYREF
  LPCWSTR lpValueName; // [rsp+58h] [rbp-69h]
  _DWORD *v46; // [rsp+60h] [rbp-61h]
  wchar_t Buffer[8]; // [rsp+70h] [rbp-51h] BYREF
  __int128 v48; // [rsp+80h] [rbp-41h]
  const wchar_t *v49; // [rsp+90h] [rbp-31h]
  const wchar_t *v50; // [rsp+98h] [rbp-29h]
  const wchar_t *v51; // [rsp+A0h] [rbp-21h]
  const wchar_t *v52; // [rsp+A8h] [rbp-19h]

  lpValueName = a5;
  v15 = a7;
  v43 = a7;
  v46 = a10;
  if ( !a2 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\wsmanconfigmigration.cpp", 668, L"668", 0x54Fu, 0);
    v15 = v43;
  }
  if ( !a5 )
  {
    v16 = L"669";
    v17 = 669;
LABEL_5:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\wsmanconfigmigration.cpp", v17, v16, 0x54Fu, a2);
    return 0;
  }
  if ( !a6 )
  {
    v16 = L"670";
    v17 = 670;
    goto LABEL_5;
  }
  if ( !v15 )
  {
    v16 = L"671";
    v17 = 671;
    goto LABEL_5;
  }
  v19 = *a6;
  if ( *a6 - 2000 > 0x17 || (v20 = 8585217, !_bittest(&v20, *a6 - 2000)) )
  {
    if ( v19 != 1002 && v19 != 3011 )
    {
      v21 = 1;
      if ( !a11 )
      {
        if ( a6[4] == 2 )
        {
          v22 = a3;
        }
        else
        {
          if ( a6[4] != 1 )
          {
            v16 = L"696";
            v17 = 696;
            goto LABEL_5;
          }
          v22 = a4;
        }
        if ( !v22 )
        {
          anonymous_namespace_::LogMigrationMessage(a1, 0, L"Migration for %ls not needed.", *((_QWORD *)a6 + 1));
          return v21;
        }
      }
      if ( a8 && v19 == 2021 || a9 && v19 == 2022 )
      {
        *(_OWORD *)Buffer = 0;
        v48 = 0;
        _itow_s(a6[8], Buffer, 0x10u, 10);
        return ConfigUpdate::AddChange(v43, a2, *a6, Buffer, 0);
      }
      v23 = (wchar_t *)WSManMemory::Alloc(20480, 0, 0);
      v24 = v23;
      String2 = v23;
      if ( !v23 )
      {
        (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
        AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&String2);
        return 0;
      }
      if ( !(unsigned int)anonymous_namespace_::GetSetting(a2, phkResult, v23) )
      {
        if ( GetLastError() == 2 )
        {
          SetLastError(0);
LABEL_79:
          AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&String2);
          return v21;
        }
LABEL_78:
        v21 = 0;
        goto LABEL_79;
      }
      v26 = 0;
      switch ( *a6 )
      {
        case 0x7D1u:
          v27 = 1500;
          break;
        case 0x7D6u:
          v27 = 500;
          break;
        case 0x7D7u:
          v27 = 300;
          break;
        case 0xBC1u:
          v27 = 7200000;
          v26 = 1;
          break;
        default:
          if ( *a6 != 3010 )
          {
            if ( *a6 != 3012 && *a6 - 3013 > 1 )
              goto LABEL_53;
            v26 = 1;
          }
          v27 = 0x7FFFFFFF;
          break;
      }
      *(_DWORD *)Data = 0;
      if ( !(unsigned int)StringToDword(v24, (unsigned int *)Data) )
      {
        anonymous_namespace_::LogMigrationMessage(
          a1,
          0,
          L"Migration for %ls failed can not convert the value %ls to int.",
          *((_QWORD *)a6 + 1),
          v24);
        (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, 1359);
        goto LABEL_78;
      }
      if ( *(_DWORD *)Data <= v27 && (*(_DWORD *)Data || !v26) )
      {
        LODWORD(phkResulta) = *(_DWORD *)Data;
        anonymous_namespace_::LogMigrationMessage(
          a1,
          0,
          L"Migration for %ls current value %d is less than Win8 default. Skip Migration",
          *((_QWORD *)a6 + 1),
          phkResulta);
        goto LABEL_79;
      }
LABEL_53:
      if ( *a6 == 2024 )
      {
        hKey = 0;
        if ( a1 )
          v28 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64 *, const WCHAR *))(*a1 + 16))(
                                 a1,
                                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WSMAN\\Service");
        else
          v28 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WSMAN\\Service";
        v44 = v28;
        v29 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v28, 0, 0xF003Fu, &hKey);
        v30 = v29;
        if ( v29 )
        {
          anonymous_namespace_::LogMigrationMessage(
            a1,
            2u,
            L"Migration ERROR in MigrateSetting: RegOpenKeyEx returned %lu for %ls ",
            v29,
            v28);
          if ( a2 )
            (*(void (__fastcall **)(struct IRequestContext *, __int64, const wchar_t *, _QWORD))(*(_QWORD *)a2 + 88LL))(
              a2,
              1077134180,
              L"RegOpenKeyEx",
              v30);
          SetLastError(v30);
LABEL_61:
          AutoCleanup<AutoBstr,unsigned short *>::ReleasePtr(&v44);
          AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&hKey);
          goto LABEL_78;
        }
        *(_DWORD *)Data = anonymous_namespace_::GetInt(a2, hKey, lpValueName, Data) == 0;
        if ( _wtoi(v24) != 1 || (v31 = L"1", *(_DWORD *)Data != 1) )
          v31 = L"0";
        *(_DWORD *)&Buffer[4] = 0;
        *(_QWORD *)Buffer = &CErrorContext::`vftable';
        *(_QWORD *)&v48 = 0xFFFFFFFF00000000uLL;
        v49 = &Class;
        v50 = &Class;
        v51 = &Class;
        v52 = &Class;
        BYTE8(v48) = 1;
        _InterlockedAdd((volatile signed __int32 *)&Buffer[4], 1u);
        v32 = Buffer;
        if ( a2 )
          v32 = (wchar_t *)a2;
        v33 = CopyString(v32, 191, v31);
        AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(&String2, v33);
        v24 = String2;
        if ( !String2 )
        {
          anonymous_namespace_::LogMigrationMessage(
            a1,
            2u,
            L"Migration ERROR in MigrateSetting: allocation failed - out of memory");
          if ( a2 )
            (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
          *(_QWORD *)Buffer = &ILifeTimeMgmt::`vftable';
          goto LABEL_61;
        }
        *(_QWORD *)Buffer = &ILifeTimeMgmt::`vftable';
        AutoCleanup<AutoBstr,unsigned short *>::ReleasePtr(&v44);
        AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&hKey);
      }
      else if ( *a6 == 2005 && !GetSDDLWithReadToIU(a2, v24, v25, v24) )
      {
        v36 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2);
        anonymous_namespace_::LogMigrationMessage(
          a1,
          2u,
          L"Migration ERROR in MigrateSetting: GetSDDLWithReadToIU failed - Error: %d",
          v36);
        goto LABEL_78;
      }
      v34 = v46;
      if ( !v46 )
        goto LABEL_87;
      if ( *a6 == 3003 )
      {
        v35 = &Class;
      }
      else
      {
        if ( *a6 != 3005 )
        {
          if ( *a6 != 3004 || _wtoi(v24) == 1 )
            goto LABEL_87;
LABEL_86:
          *v34 = 1;
LABEL_87:
          v37 = ConfigUpdate::AddChange(v43, a2, *a6, v24, 0);
          AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&String2);
          return v37;
        }
        v35 = L"wsman";
      }
      if ( !_wcsicmp(v35, v24) )
        goto LABEL_87;
      goto LABEL_86;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1801927e0  push    rbp
0x1801927e2  push    rbx
0x1801927e3  push    rsi
0x1801927e4  push    rdi
0x1801927e5  push    r12
0x1801927e7  push    r13
0x1801927e9  push    r14
0x1801927eb  push    r15
0x1801927ed  lea     rbp, [rsp-7]
0x1801927f2  sub     rsp, 0C8h
0x1801927f9  mov     rax, cs:__security_cookie
0x180192800  xor     rax, rsp
0x180192803  mov     [rbp+3Fh+var_50], rax
0x180192807  mov     r12, r9
0x18019280a  mov     rbx, r8
0x18019280d  mov     rsi, rdx
0x180192810  mov     r13, rcx
0x180192813  mov     r15, [rbp+3Fh+arg_28]
0x180192817  mov     rdi, [rbp+3Fh+arg_20]
0x18019281b  mov     [rbp+3Fh+lpValueName], rdi
0x18019281f  mov     rax, [rbp+3Fh+arg_30]
0x180192823  mov     [rbp+3Fh+var_B8], rax
0x180192827  mov     rcx, [rbp+3Fh+arg_48]
0x18019282e  mov     [rbp+3Fh+var_A0], rcx
0x180192832  mov     r14, [rbp+3Fh+arg_50]
0x180192839  mov     r8d, 54Fh
0x18019283f  lea     r10, aOnecoreAdminWm_134; "onecore\\admin\\wmi\\wmx\\config\\wsman"...
0x180192846  test    rdx, rdx
0x180192849  jnz     short loc_180192878
0x18019284b  mov     [rsp+100h+phkResult], rdx; Data
0x180192850  mov     r9d, r8d; unsigned int
0x180192853  lea     r8, a668; "668"
0x18019285a  mov     edx, 29Ch; unsigned int
0x18019285f  mov     rcx, r10; String1
0x180192862  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180192867  mov     rax, [rbp+3Fh+var_B8]
0x18019286b  lea     r10, aOnecoreAdminWm_134; "onecore\\admin\\wmi\\wmx\\config\\wsman"...
0x180192872  mov     r8d, 54Fh
0x180192878  test    rdi, rdi
0x18019287b  jnz     short loc_1801928A0
0x18019287d  mov     r9d, r8d; unsigned int
0x180192880  lea     r8, a669; "669"
0x180192887  mov     edx, 29Dh; unsigned int
0x18019288c  mov     [rsp+100h+phkResult], rsi; struct IRequestContext *
0x180192891  mov     rcx, r10; String1
0x180192894  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180192899  xor     eax, eax
0x18019289b  jmp     loc_180192DBA
0x1801928a0  test    r15, r15
0x1801928a3  jnz     short loc_1801928B6
0x1801928a5  mov     r9d, r8d
0x1801928a8  lea     r8, a670; "670"
0x1801928af  mov     edx, 29Eh
0x1801928b4  jmp     short loc_18019288C
0x1801928b6  test    rax, rax
0x1801928b9  jnz     short loc_1801928CC
0x1801928bb  mov     r9d, r8d
0x1801928be  lea     r8, a671; "671"
0x1801928c5  mov     edx, 29Fh
0x1801928ca  jmp     short loc_18019288C
0x1801928cc  mov     eax, [r15]
0x1801928cf  lea     ecx, [rax-7D0h]
0x1801928d5  cmp     ecx, 17h
0x1801928d8  ja      short loc_1801928E8
0x1801928da  mov     edx, 830001h
0x1801928df  bt      edx, ecx
0x1801928e2  jb      loc_180192DB5
0x1801928e8  cmp     eax, 3EAh
0x1801928ed  jz      loc_180192DB5
0x1801928f3  cmp     eax, 0BC3h
0x1801928f8  jz      loc_180192DB5
0x1801928fe  mov     edi, 1
0x180192903  test    r14, r14
0x180192906  jnz     short loc_180192952
0x180192908  cmp     dword ptr [r15+10h], 2
0x18019290d  jnz     short loc_180192914
0x18019290f  mov     r14, rbx
0x180192912  jmp     short loc_18019291D
0x180192914  cmp     [r15+10h], edi
0x180192918  jnz     short loc_18019293E
0x18019291a  mov     r14, r12
0x18019291d  test    r14, r14
0x180192920  jnz     short loc_180192952
0x180192922  mov     r9, [r15+8]
0x180192926  lea     r8, aMigrationForLs; "Migration for %ls not needed."
0x18019292d  xor     edx, edx
0x18019292f  mov     rcx, r13
0x180192932  call    _anonymous_namespace___LogMigrationMessage
0x180192937  mov     eax, edi
0x180192939  jmp     loc_180192DBA
0x18019293e  mov     r9d, r8d
0x180192941  lea     r8, a696; "696"
0x180192948  mov     edx, 2B8h
0x18019294d  jmp     loc_18019288C
0x180192952  cmp     [rbp+3Fh+arg_38], 0
0x180192959  jz      short loc_1801929A6
0x18019295b  cmp     eax, 7E5h
0x180192960  jnz     short loc_1801929A6
0x180192962  xorps   xmm0, xmm0
0x180192965  movups  xmmword ptr [rbp+3Fh+Buffer], xmm0
0x180192969  movups  [rbp+3Fh+var_80], xmm0
0x18019296d  mov     r9d, 0Ah; Radix
0x180192973  lea     r8d, [r9+6]; BufferCount
0x180192977  lea     rdx, [rbp+3Fh+Buffer]; Buffer
0x18019297b  mov     ecx, [r15+20h]; Value
0x18019297f  call    cs:__imp__itow_s
0x180192985  mov     [rsp+100h+phkResult], 0
0x18019298e  lea     r9, [rbp+3Fh+Buffer]
0x180192992  mov     r8d, [r15]
0x180192995  mov     rdx, rsi
0x180192998  mov     rcx, [rbp+3Fh+var_B8]
0x18019299c  call    ?AddChange@ConfigUpdate@@QEAAHPEAVIRequestContext@@W4ConfigSetting@@PEBG2@Z; ConfigUpdate::AddChange(IRequestContext *,ConfigSetting,ushort const *,ushort const *)
0x1801929a1  jmp     loc_180192DBA
0x1801929a6  cmp     [rbp+3Fh+arg_40], 0
0x1801929ad  jz      short loc_1801929B6
0x1801929af  cmp     eax, 7E6h
0x1801929b4  jz      short loc_180192962
0x1801929b6  xor     r8d, r8d
0x1801929b9  xor     edx, edx
0x1801929bb  mov     ecx, 5000h
0x1801929c0  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x1801929c5  mov     rbx, rax
0x1801929c8  mov     [rsp+100h+String2], rax
0x1801929cd  mov     rcx, rsi; struct IRequestContext *
0x1801929d0  test    rax, rax
0x1801929d3  jnz     short loc_1801929F1
0x1801929d5  mov     rax, [rsi]
0x1801929d8  mov     rax, [rax+18h]
0x1801929dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801929e1  nop
0x1801929e2  lea     rcx, [rsp+100h+String2]
0x1801929e7  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x1801929ec  jmp     loc_180192899
0x1801929f1  mov     [rsp+100h+var_D8], rbx; unsigned __int16 *
0x1801929f6  mov     r9, r15
0x1801929f9  mov     r8, [rbp+3Fh+lpValueName]
0x1801929fd  mov     rdx, r14
0x180192a00  call    _anonymous_namespace___GetSetting
0x180192a05  test    eax, eax
0x180192a07  jnz     short loc_180192A25
0x180192a09  call    cs:__imp_GetLastError
0x180192a0f  cmp     eax, 2
0x180192a12  jnz     loc_180192D41
0x180192a18  xor     ecx, ecx; dwErrCode
0x180192a1a  call    cs:__imp_SetLastError
0x180192a20  jmp     loc_180192D43
0x180192a25  xor     r12b, r12b
0x180192a28  mov     ecx, [r15]
0x180192a2b  sub     ecx, 7D1h
0x180192a31  jz      short loc_180192A83
0x180192a33  sub     ecx, 5
0x180192a36  jz      short loc_180192A7B
0x180192a38  sub     ecx, 1
0x180192a3b  jz      short loc_180192A73
0x180192a3d  sub     ecx, 3EAh
0x180192a43  jz      short loc_180192A68
0x180192a45  sub     ecx, 1
0x180192a48  jz      short loc_180192A60
0x180192a4a  sub     ecx, 2
0x180192a4d  jz      short loc_180192A5D
0x180192a4f  sub     ecx, 1
0x180192a52  jz      short loc_180192A5D
0x180192a54  cmp     ecx, 1
0x180192a57  jnz     loc_180192B05
0x180192a5d  mov     r12b, dil
0x180192a60  mov     r14d, 7FFFFFFFh
0x180192a66  jmp     short loc_180192A89
0x180192a68  mov     r14d, 6DDD00h
0x180192a6e  mov     r12b, dil
0x180192a71  jmp     short loc_180192A89
0x180192a73  mov     r14d, 12Ch
0x180192a79  jmp     short loc_180192A89
0x180192a7b  mov     r14d, 1F4h
0x180192a81  jmp     short loc_180192A89
0x180192a83  mov     r14d, 5DCh
0x180192a89  mov     dword ptr [rsp+100h+Data], 0
0x180192a91  lea     rdx, [rsp+100h+Data]; unsigned int *
0x180192a96  mov     rcx, rbx; String
0x180192a99  call    ?StringToDword@@YAHPEBGPEAK@Z; StringToDword(ushort const *,ulong *)
0x180192a9e  test    eax, eax
0x180192aa0  jnz     short loc_180192AD5
0x180192aa2  mov     [rsp+100h+phkResult], rbx
0x180192aa7  mov     r9, [r15+8]
0x180192aab  lea     r8, aMigrationForLs_1; "Migration for %ls failed can not conver"...
0x180192ab2  xor     edx, edx
0x180192ab4  mov     rcx, r13
0x180192ab7  call    _anonymous_namespace___LogMigrationMessage
0x180192abc  mov     rax, [rsi]
0x180192abf  mov     edx, 54Fh
0x180192ac4  mov     rcx, rsi
0x180192ac7  mov     rax, [rax+48h]
0x180192acb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192ad0  jmp     loc_180192D41
0x180192ad5  mov     eax, dword ptr [rsp+100h+Data]
0x180192ad9  cmp     eax, r14d
0x180192adc  ja      short loc_180192B05
0x180192ade  test    eax, eax
0x180192ae0  jnz     short loc_180192AE7
0x180192ae2  test    r12b, r12b
0x180192ae5  jnz     short loc_180192B05
0x180192ae7  mov     dword ptr [rsp+100h+phkResult], eax
0x180192aeb  mov     r9, [r15+8]
0x180192aef  lea     r8, aMigrationForLs_0; "Migration for %ls current value %d is l"...
0x180192af6  xor     edx, edx
0x180192af8  mov     rcx, r13
0x180192afb  call    _anonymous_namespace___LogMigrationMessage
0x180192b00  jmp     loc_180192D43
0x180192b05  lea     r12, Class
0x180192b0c  cmp     dword ptr [r15], 7E8h
0x180192b13  jnz     loc_180192CFD
0x180192b19  mov     [rsp+100h+hKey], 0
0x180192b22  test    r13, r13
0x180192b25  jz      short loc_180192B43
0x180192b27  mov     rax, [r13+0]
0x180192b2b  lea     rdx, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180192b32  mov     rcx, r13
0x180192b35  mov     rax, [rax+10h]
0x180192b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192b3e  mov     r12, rax
0x180192b41  jmp     short loc_180192B4A
0x180192b43  lea     r12, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180192b4a  mov     [rbp+3Fh+var_B0], r12
0x180192b4e  lea     rax, [rsp+100h+hKey]
0x180192b53  mov     [rsp+100h+phkResult], rax; phkResult
0x180192b58  mov     r9d, 0F003Fh; samDesired
0x180192b5e  xor     r8d, r8d; ulOptions
0x180192b61  mov     rdx, r12; lpSubKey
0x180192b64  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180192b6b  call    cs:__imp_RegOpenKeyExW
0x180192b71  mov     r14d, eax
0x180192b74  test    eax, eax
0x180192b76  jz      short loc_180192BDA
0x180192b78  mov     [rsp+100h+phkResult], r12
0x180192b7d  mov     r9d, eax
0x180192b80  lea     r8, aMigrationError_2; "Migration ERROR in MigrateSetting: RegO"...
0x180192b87  mov     edx, 2
0x180192b8c  mov     rcx, r13
0x180192b8f  call    _anonymous_namespace___LogMigrationMessage
0x180192b94  test    rsi, rsi
0x180192b97  jz      short loc_180192BB7
0x180192b99  mov     rcx, [rsi]
0x180192b9c  mov     rax, [rcx+58h]
0x180192ba0  mov     r9d, r14d
0x180192ba3  lea     r8, aRegopenkeyex; "RegOpenKeyEx"
0x180192baa  mov     edx, 4033C364h
0x180192baf  mov     rcx, rsi
0x180192bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180192bb7  mov     ecx, r14d; dwErrCode
0x180192bba  call    cs:__imp_SetLastError
0x180192bc0  nop
0x180192bc1  lea     rcx, [rbp+3Fh+var_B0]
0x180192bc5  call    ?ReleasePtr@?$AutoCleanup@VAutoBstr@@PEAG@@AEAAXXZ; AutoCleanup<AutoBstr,ushort *>::ReleasePtr(void)
0x180192bca  nop
0x180192bcb  lea     rcx, [rsp+100h+hKey]
0x180192bd0  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x180192bd5  jmp     loc_180192D41
0x180192bda  mov     dword ptr [rsp+100h+Data], 0
0x180192be2  lea     r9, [rsp+100h+Data]; lpData
0x180192be7  mov     r8, [rbp+3Fh+lpValueName]; lpValueName
0x180192beb  mov     rdx, [rsp+100h+hKey]; hKey
0x180192bf0  mov     rcx, rsi; struct IRequestContext *
0x180192bf3  call    _anonymous_namespace___GetInt
0x180192bf8  test    eax, eax
0x180192bfa  jnz     short loc_180192C00
0x180192bfc  mov     dword ptr [rsp+100h+Data], edi
0x180192c00  mov     rcx, rbx; String
0x180192c03  call    cs:__imp__wtoi
0x180192c09  cmp     eax, edi
0x180192c0b  jnz     short loc_180192C1A
0x180192c0d  cmp     dword ptr [rsp+100h+Data], edi
0x180192c11  lea     r8, a1; "1"
0x180192c18  jz      short loc_180192C21
0x180192c1a  lea     r8, a0_1; "0"
0x180192c21  mov     dword ptr [rbp+3Fh+Buffer+8], 0
0x180192c28  lea     rax, ??_7CErrorContext@@6B@; const CErrorContext::`vftable'
0x180192c2f  mov     qword ptr [rbp+3Fh+Buffer], rax
0x180192c33  mov     dword ptr [rbp+3Fh+var_80], 0
0x180192c3a  mov     dword ptr [rbp+3Fh+var_80+4], 0FFFFFFFFh
0x180192c41  lea     r12, Class
0x180192c48  mov     [rbp+3Fh+var_70], r12
0x180192c4c  mov     [rbp+3Fh+var_68], r12
0x180192c50  mov     [rbp+3Fh+var_60], r12
0x180192c54  mov     [rbp+3Fh+var_58], r12
0x180192c58  mov     byte ptr [rbp+3Fh+var_80+8], dil
0x180192c5c  lock add dword ptr [rbp+3Fh+Buffer+8], edi
0x180192c60  lea     rcx, [rbp+3Fh+Buffer]
0x180192c64  test    rsi, rsi
0x180192c67  cmovnz  rcx, rsi
0x180192c6b  mov     edx, 0BFh
0x180192c70  call    ?CopyString@@YAPEAGPEAVIRequestContext@@W4CallSiteId@@PEBG@Z; CopyString(IRequestContext *,CallSiteId,ushort const *)
0x180192c75  mov     rdx, rax
0x180192c78  lea     rcx, [rsp+100h+String2]
0x180192c7d  call    ??4?$AutoDeleteVector@U_WINRS_RUN_COMMAND_ARG@@@@QEAAAEAV0@PEAU_WINRS_RUN_COMMAND_ARG@@@Z; AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(_WINRS_RUN_COMMAND_ARG *)
0x180192c82  mov     rbx, [rsp+100h+String2]
0x180192c87  test    rbx, rbx
0x180192c8a  jnz     short loc_180192CC3
0x180192c8c  lea     r8, aMigrationError_0; "Migration ERROR in MigrateSetting: allo"...
0x180192c93  lea     edx, [rbx+2]
0x180192c96  mov     rcx, r13
0x180192c99  call    _anonymous_namespace___LogMigrationMessage
  ... truncated ...
```
