# IkeLookupDestinationTunnelChecksConfig

- ea: `0x1800565bc`
- end: `0x1800569b8`
- name: `IkeLookupDestinationTunnelChecksConfig`
- size: `1020`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, service_task`

## callers

- `0x180055d2c`
- `0x18005fac0`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x1800037c4`
- `0x180003cf0`
- `0x1800061ec`
- `0x180008388`
- `0x180025d88`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x18004d308`
- `0x180050850`
- `0x1800510ee`
- `0x180054b54`
- `0x1800565bc`
- `0x180056c60`
- `0x180111f24`
- `0x1801120e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180056716`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800567be`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180056716`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800567be`

## string_xrefs

- `0x1800565e8`: `IkeLookupDestinationTunnelChecksConfig`
- `0x18005695a`: `IkeLookupDestinationTunnelChecksConfig`
- `0x180056966`: `IkeLookupDestinationTunnelChecksConfig`
- `0x180056914`: `IkeLookupDestinationTunnelChecksConfig failed`
- `0x18005662b`: `SYSTEM\CurrentControlSet\Services\IKEEXT\Parameters\IPSecTunnelConfig\AuthIP\Kerberos`

## pseudocode

```c
__int64 __fastcall IkeLookupDestinationTunnelChecksConfig(__int64 a1, _DWORD *a2, _DWORD *a3)
{
  _DWORD *v3; // rbx
  __int64 v5; // rcx
  __int64 v6; // r8
  WCHAR *v7; // rsi
  HKEY v8; // rcx
  __int64 *v9; // r14
  DWORD v10; // r15d
  unsigned int v11; // r13d
  WCHAR *v12; // r8
  unsigned int v13; // eax
  __int64 v14; // rcx
  DWORD v15; // ebx
  __int64 v16; // rdi
  __int64 v17; // rax
  int i; // r8d
  DWORD v19; // edx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  int TlsMmLuid; // eax
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // r8
  __int64 v34; // r9
  int v36; // [rsp+40h] [rbp-79h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-71h] BYREF
  unsigned int v38; // [rsp+50h] [rbp-69h] BYREF
  DWORD cchValueName; // [rsp+54h] [rbp-65h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-61h] BYREF
  DWORD Type; // [rsp+5Ch] [rbp-5Dh] BYREF
  LPWSTR lpValueName; // [rsp+60h] [rbp-59h] BYREF
  __int64 v43; // [rsp+68h] [rbp-51h] BYREF
  _BYTE v44[32]; // [rsp+70h] [rbp-49h] BYREF
  __int64 *v45; // [rsp+90h] [rbp-29h]
  __int64 v46; // [rsp+98h] [rbp-21h]
  _BYTE v47[16]; // [rsp+A0h] [rbp-19h] BYREF
  const char *v48; // [rsp+B0h] [rbp-9h]
  __int64 v49; // [rsp+B8h] [rbp-1h]
  LPWSTR *p_lpValueName; // [rsp+C0h] [rbp+7h]
  __int64 v51; // [rsp+C8h] [rbp+Fh]

  v3 = a3;
  hKey = 0;
  v43 = (__int64)a3;
  v36 = 0;
  v38 = 0;
  cchValueName = 0;
  cbData = 0;
  Type = 0;
  lpValueName = 0;
  TraceLogHelper("IkeLookupDestinationTunnelChecksConfig", 1);
  *v3 = 0;
  v7 = (WCHAR *)WfpRegOpenKey(
                  v5,
                  L"SYSTEM\\CurrentControlSet\\Services\\IKEEXT\\Parameters\\IPSecTunnelConfig\\AuthIP\\Kerberos",
                  v6,
                  &hKey,
                  &v36);
  if ( v7 )
    goto LABEL_29;
  if ( v36 )
  {
    v8 = hKey;
    *v3 = 1;
    v7 = (WCHAR *)WfpRegQueryNumValues(v8, &v38);
    if ( v7 )
      goto LABEL_29;
    if ( v38 )
    {
      if ( v38 > 0x400 )
        v38 = 1024;
      v7 = (WCHAR *)WfpMemAlloc(0x8000u, 8u);
      if ( !v7 )
      {
        v9 = (__int64 *)(a2 + 2);
        v7 = (WCHAR *)WfpMemAlloc(160LL * v38, 8u);
        if ( !v7 )
        {
          v10 = 0;
          *a2 = 0;
          v11 = 0;
          v7 = 0;
          if ( v38 )
          {
            while ( 1 )
            {
              cbData = 0;
              cchValueName = 0x4000;
              v12 = lpValueName;
              *lpValueName = 0;
              v13 = RegEnumValueW(hKey, v10, v12, &cchValueName, 0, &Type, 0, &cbData);
              if ( v13 )
                break;
              if ( Type == 7 && cbData >= 2 && (cbData & 1) == 0 )
              {
                v15 = (cbData >> 1) + 2;
                if ( v15 <= 0x4000 )
                {
                  v16 = 160LL * v11;
                  v7 = (WCHAR *)WfpMemAlloc(2LL * v15, 8u);
                  if ( v7 )
                    goto LABEL_25;
                  v17 = *v9;
                  ++*a2;
                  ++cchValueName;
                  v13 = RegEnumValueW(
                          hKey,
                          v10,
                          lpValueName,
                          &cchValueName,
                          0,
                          &Type,
                          *(LPBYTE *)(v16 + v17 + 64),
                          &cbData);
                  if ( v13 )
                    break;
                  for ( i = 0; i < 2; ++i )
                  {
                    v19 = v15 - i;
                    *(_WORD *)(*(_QWORD *)(*v9 + v16 + 64) + 2LL * (v19 - 1)) = 0;
                  }
                  *(_DWORD *)(v16 + *v9 + 60) = 2 * v15;
                  if ( (unsigned int)IkePopulateDestinationTunnelChecksConfigEntry(v16 + *v9) )
                  {
                    ++v11;
                  }
                  else
                  {
                    WfpMemFree(v16 + *v9 + 64);
                    memset_0((void *)(v16 + *v9), 0, 0xA0u);
                    --*a2;
                  }
                }
              }
              if ( ++v10 >= v38 )
                goto LABEL_25;
            }
            v7 = (WCHAR *)WfpReportSysErrorAsWinError(v14, "RegEnumValueW", v13, 1);
LABEL_25:
            v3 = (_DWORD *)v43;
          }
        }
      }
      if ( lpValueName )
        WfpMemFree(&lpValueName);
      if ( v7 )
      {
LABEL_29:
        IkeFreeDestinationTunnelChecksConfig(a2);
        *v3 = 0;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v24 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          TlsPeerAddr = IkeGetTlsPeerAddr(v21);
          TlsMmLuid = IkeGetTlsMmLuid(v27, v26, v28, v29);
          WPP_SF_iSq(
            v24,
            28,
            (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids,
            TlsMmLuid,
            TlsPeerAddr,
            (__int64)v7);
        }
        if ( (unsigned int)dword_180173278 > 4 )
        {
          v43 = IkeGetTlsMmLuid(v21, v20, v22, v23);
          v45 = &v43;
          v46 = 8;
          v32 = IkeGetTlsPeerAddr(v31);
          tlgCreate1Sz_wchar_t(v47, v32);
          v49 = 46;
          p_lpValueName = &lpValueName;
          v48 = "IkeLookupDestinationTunnelChecksConfig failed";
          lpValueName = v7;
          v51 = 8;
          tlgWriteTransfer_EtwEventWriteTransfer(
            (__int64)&dword_180173278,
            (unsigned __int8 *)byte_18014F1F1,
            v33,
            v34,
            6,
            (__int64)v44);
        }
      }
    }
  }
  WfpRegCloseKey(hKey);
  TraceLogHelper("IkeLookupDestinationTunnelChecksConfig", 0);
  return IkeReturnError(0, "IkeLookupDestinationTunnelChecksConfig");
}

```

## disassembly

```asm
0x1800565bc  mov     [rsp-8+arg_0], rbx
0x1800565c1  push    rbp
0x1800565c2  push    rsi
0x1800565c3  push    rdi
0x1800565c4  push    r12
0x1800565c6  push    r13
0x1800565c8  push    r14
0x1800565ca  push    r15
0x1800565cc  lea     rbp, [rsp-27h]
0x1800565d1  sub     rsp, 0E0h
0x1800565d8  mov     rax, cs:__security_cookie
0x1800565df  xor     rax, rsp
0x1800565e2  mov     [rbp+57h+var_40], rax
0x1800565e6  xor     edi, edi
0x1800565e8  lea     rcx, aIkelookupdesti; "IkeLookupDestinationTunnelChecksConfig"
0x1800565ef  mov     rbx, r8
0x1800565f2  mov     [rbp+57h+hKey], rdi
0x1800565f6  mov     r12, rdx
0x1800565f9  mov     [rbp+57h+var_A8], rbx
0x1800565fd  mov     [rbp+57h+var_D0], edi
0x180056600  lea     r14d, [rdi+1]
0x180056604  mov     [rbp+57h+var_C0], edi
0x180056607  mov     edx, r14d
0x18005660a  mov     [rbp+57h+cchValueName], edi
0x18005660d  mov     [rbp+57h+cbData], edi
0x180056610  mov     [rbp+57h+Type], edi
0x180056613  mov     [rbp+57h+lpValueName], rdi
0x180056617  call    TraceLogHelper
0x18005661c  lea     rax, [rbp+57h+var_D0]
0x180056620  mov     [rbx], edi
0x180056622  lea     r9, [rbp+57h+hKey]
0x180056626  mov     [rsp+110h+lpReserved], rax
0x18005662b  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\IK"...
0x180056632  call    WfpRegOpenKey
0x180056637  mov     rsi, rax
0x18005663a  test    rax, rax
0x18005663d  jnz     loc_180056874
0x180056643  cmp     [rbp+57h+var_D0], edi
0x180056646  jz      loc_18005694F
0x18005664c  mov     rcx, [rbp+57h+hKey]
0x180056650  lea     rdx, [rbp+57h+var_C0]
0x180056654  mov     [rbx], r14d
0x180056657  call    WfpRegQueryNumValues
0x18005665c  mov     rsi, rax
0x18005665f  test    rax, rax
0x180056662  jnz     loc_180056874
0x180056668  mov     eax, [rbp+57h+var_C0]
0x18005666b  test    eax, eax
0x18005666d  jz      loc_18005694F
0x180056673  mov     ecx, 400h
0x180056678  cmp     eax, ecx
0x18005667a  jbe     short loc_18005667F
0x18005667c  mov     [rbp+57h+var_C0], ecx
0x18005667f  lea     r8, [rbp+57h+lpValueName]
0x180056683  mov     edx, 8; dwFlags
0x180056688  mov     ecx, 8000h; dwBytes
0x18005668d  call    WfpMemAlloc
0x180056692  mov     rsi, rax
0x180056695  test    rax, rax
0x180056698  jnz     loc_18005685C
0x18005669e  mov     eax, [rbp+57h+var_C0]
0x1800566a1  lea     r14, [r12+8]
0x1800566a6  mov     r8, r14
0x1800566a9  lea     edx, [rsi+8]; dwFlags
0x1800566ac  lea     rcx, [rax+rax*4]
0x1800566b0  shl     rcx, 5; dwBytes
0x1800566b4  call    WfpMemAlloc
0x1800566b9  mov     rsi, rax
0x1800566bc  test    rax, rax
0x1800566bf  jnz     loc_18005685C
0x1800566c5  mov     r15d, edi
0x1800566c8  mov     [r12], edi
0x1800566cc  mov     r13d, edi
0x1800566cf  mov     rsi, rdi
0x1800566d2  cmp     [rbp+57h+var_C0], edi
0x1800566d5  jbe     loc_18005685C
0x1800566db  mov     rcx, [rbp+57h+lpValueName]
0x1800566df  lea     rax, [rbp+57h+cbData]
0x1800566e3  mov     [rsp+110h+lpcbData], rax; lpcbData
0x1800566e8  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x1800566ec  mov     [rbp+57h+cbData], edi
0x1800566ef  lea     rax, [rbp+57h+Type]
0x1800566f3  mov     [rbp+57h+cchValueName], 4000h
0x1800566fa  mov     r8, rcx; lpValueName
0x1800566fd  mov     [rcx], di
0x180056700  mov     edx, r15d; dwIndex
0x180056703  mov     rcx, [rbp+57h+hKey]; hKey
0x180056707  mov     [rsp+110h+lpData], rdi; lpData
0x18005670c  mov     [rsp+110h+lpType], rax; lpType
0x180056711  mov     [rsp+110h+lpReserved], rdi; lpReserved
0x180056716  call    cs:__imp_RegEnumValueW
0x18005671c  test    eax, eax
0x18005671e  jnz     loc_18005699B
0x180056724  cmp     [rbp+57h+Type], 7
0x180056728  jnz     loc_18005682F
0x18005672e  mov     ebx, [rbp+57h+cbData]
0x180056731  cmp     ebx, 2
0x180056734  jb      loc_18005682F
0x18005673a  test    bl, 1
0x18005673d  jnz     loc_18005682F
0x180056743  shr     ebx, 1
0x180056745  add     ebx, 2
0x180056748  cmp     ebx, 4000h
0x18005674e  ja      loc_18005682F
0x180056754  mov     r8, [r14]
0x180056757  mov     edx, 8; dwFlags
0x18005675c  mov     eax, r13d
0x18005675f  add     r8, 40h ; '@'
0x180056763  mov     ecx, ebx
0x180056765  add     rcx, rcx; dwBytes
0x180056768  lea     rdi, [rax+rax*4]
0x18005676c  shl     rdi, 5
0x180056770  add     r8, rdi
0x180056773  call    WfpMemAlloc
0x180056778  mov     rsi, rax
0x18005677b  test    rax, rax
0x18005677e  jnz     loc_180056856
0x180056784  mov     rax, [r14]
0x180056787  lea     rcx, [rbp+57h+cbData]
0x18005678b  inc     dword ptr [r12]
0x18005678f  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x180056793  inc     [rbp+57h+cchValueName]
0x180056796  mov     edx, r15d; dwIndex
0x180056799  mov     r8, [rbp+57h+lpValueName]; lpValueName
0x18005679d  mov     rax, [rdi+rax+40h]
0x1800567a2  mov     [rsp+110h+lpcbData], rcx; lpcbData
0x1800567a7  mov     rcx, [rbp+57h+hKey]; hKey
0x1800567ab  mov     [rsp+110h+lpData], rax; lpData
0x1800567b0  lea     rax, [rbp+57h+Type]
0x1800567b4  mov     [rsp+110h+lpType], rax; lpType
0x1800567b9  mov     [rsp+110h+lpReserved], rsi; lpReserved
0x1800567be  call    cs:__imp_RegEnumValueW
0x1800567c4  test    eax, eax
0x1800567c6  jnz     short loc_18005683E
0x1800567c8  xor     r8d, r8d
0x1800567cb  mov     rax, [r14]
0x1800567ce  mov     edx, ebx
0x1800567d0  sub     edx, r8d
0x1800567d3  inc     r8d
0x1800567d6  dec     edx
0x1800567d8  mov     rcx, [rax+rdi+40h]
0x1800567dd  xor     eax, eax
0x1800567df  mov     [rcx+rdx*2], ax
0x1800567e3  cmp     r8d, 2
0x1800567e7  jl      short loc_1800567CB
0x1800567e9  mov     rax, [r14]
0x1800567ec  lea     ecx, [rbx+rbx]
0x1800567ef  mov     [rdi+rax+3Ch], ecx
0x1800567f3  mov     rcx, [r14]
0x1800567f6  add     rcx, rdi
0x1800567f9  call    IkePopulateDestinationTunnelChecksConfigEntry
0x1800567fe  test    eax, eax
0x180056800  jz      short loc_180056807
0x180056802  inc     r13d
0x180056805  jmp     short loc_18005682D
0x180056807  mov     rcx, [r14]
0x18005680a  add     rcx, 40h ; '@'
0x18005680e  add     rcx, rdi
0x180056811  call    WfpMemFree
0x180056816  mov     rcx, [r14]
0x180056819  xor     edx, edx; Val
0x18005681b  add     rcx, rdi; void *
0x18005681e  mov     r8d, 0A0h; Size
0x180056824  call    memset_0
0x180056829  dec     dword ptr [r12]
0x18005682d  xor     edi, edi
0x18005682f  inc     r15d
0x180056832  cmp     r15d, [rbp+57h+var_C0]
0x180056836  jb      loc_1800566DB
0x18005683c  jmp     short loc_180056858
0x18005683e  mov     r9d, 1
0x180056844  lea     rdx, aRegenumvaluew; "RegEnumValueW"
0x18005684b  mov     r8d, eax
0x18005684e  call    WfpReportSysErrorAsWinError
0x180056853  mov     rsi, rax
0x180056856  xor     edi, edi
0x180056858  mov     rbx, [rbp+57h+var_A8]
0x18005685c  cmp     [rbp+57h+lpValueName], rdi
0x180056860  jz      short loc_18005686B
0x180056862  lea     rcx, [rbp+57h+lpValueName]
0x180056866  call    WfpMemFree
0x18005686b  test    rsi, rsi
0x18005686e  jz      loc_18005694F
0x180056874  mov     rcx, r12
0x180056877  call    IkeFreeDestinationTunnelChecksConfig
0x18005687c  mov     [rbx], edi
0x18005687e  mov     rdi, cs:WPP_GLOBAL_Control
0x180056885  lea     rax, WPP_GLOBAL_Control
0x18005688c  cmp     rdi, rax
0x18005688f  jz      short loc_1800568CF
0x180056891  cmp     byte ptr [rdi+19h], 4
0x180056895  jb      short loc_1800568CF
0x180056897  test    byte ptr [rdi+1Ch], 10h
0x18005689b  jz      short loc_1800568CF
0x18005689d  mov     rdi, [rdi+10h]
0x1800568a1  call    IkeGetTlsPeerAddr
0x1800568a6  mov     rbx, rax
0x1800568a9  call    IkeGetTlsMmLuid
0x1800568ae  mov     r9, rax
0x1800568b1  mov     [rsp+110h+lpType], rsi
0x1800568b6  mov     edx, 1Ch
0x1800568bb  mov     [rsp+110h+lpReserved], rbx
0x1800568c0  lea     r8, WPP_c3da8f174801358a223b58501d21a257_Traceguids
0x1800568c7  mov     rcx, rdi
0x1800568ca  call    WPP_SF_iSq
0x1800568cf  mov     eax, cs:dword_180173278
0x1800568d5  cmp     eax, 4
0x1800568d8  jbe     short loc_18005694F
0x1800568da  call    IkeGetTlsMmLuid
0x1800568df  mov     [rbp+57h+var_A8], rax
0x1800568e3  lea     rax, [rbp+57h+var_A8]
0x1800568e7  mov     [rbp+57h+var_80], rax
0x1800568eb  mov     [rbp+57h+var_78], 8
0x1800568f3  call    IkeGetTlsPeerAddr
0x1800568f8  mov     rdx, rax
0x1800568fb  lea     rcx, [rbp+57h+var_70]
0x1800568ff  call    _tlgCreate1Sz_wchar_t
0x180056904  lea     rax, [rbp+57h+lpValueName]
0x180056908  mov     [rbp+57h+var_58], 2Eh ; '.'
0x180056910  mov     [rbp+57h+var_50], rax
0x180056914  lea     rcx, aIkelookupdesti_0; "IkeLookupDestinationTunnelChecksConfig "...
0x18005691b  lea     rax, [rbp+57h+var_A0]
0x18005691f  mov     [rbp+57h+var_60], rcx
0x180056923  mov     [rsp+110h+lpType], rax
0x180056928  lea     rdx, byte_18014F1F1
0x18005692f  lea     rcx, dword_180173278
0x180056936  mov     dword ptr [rsp+110h+lpReserved], 6
0x18005693e  mov     [rbp+57h+lpValueName], rsi
0x180056942  mov     [rbp+57h+var_48], 8
0x18005694a  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18005694f  mov     rcx, [rbp+57h+hKey]
0x180056953  call    WfpRegCloseKey
0x180056958  xor     edx, edx
0x18005695a  lea     rcx, aIkelookupdesti; "IkeLookupDestinationTunnelChecksConfig"
0x180056961  call    TraceLogHelper
0x180056966  lea     rdx, aIkelookupdesti; "IkeLookupDestinationTunnelChecksConfig"
0x18005696d  xor     ecx, ecx
0x18005696f  call    IkeReturnError
0x180056974  mov     rcx, [rbp+57h+var_40]
0x180056978  xor     rcx, rsp; StackCookie
0x18005697b  call    __security_check_cookie
0x180056980  mov     rbx, [rsp+110h+arg_0]
0x180056988  add     rsp, 0E0h
0x18005698f  pop     r15
0x180056991  pop     r14
0x180056993  pop     r13
0x180056995  pop     r12
0x180056997  pop     rdi
0x180056998  pop     rsi
0x180056999  pop     rbp
0x18005699a  retn
0x18005699b  mov     r9d, 1
0x1800569a1  lea     rdx, aRegenumvaluew; "RegEnumValueW"
0x1800569a8  mov     r8d, eax
0x1800569ab  call    WfpReportSysErrorAsWinError
0x1800569b0  mov     rsi, rax
0x1800569b3  jmp     loc_180056858
```
