# WinReOpenLogInstance

- ea: `0x18002c280`
- end: `0x18002c4df`
- name: `WinReOpenLogInstance`
- size: `607`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task`

## callees

- `0x1800055c8`
- `0x180005694`
- `0x1800059fc`
- `0x18000fe58`
- `0x18000ffcc`
- `0x180011974`
- `0x18001c598`
- `0x18002b6f0`
- `0x18002c280`
- `0x18003f2c0`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002c4b2`
- `KERNEL32!SetLastError` at `0x18002c4b2`
- `ole32!CoTaskMemFree` at `0x18002c47c`
- `ole32!CoTaskMemFree` at `0x18002c48a`
- `ole32!CoTaskMemFree` at `0x18002c47c`
- `ole32!CoTaskMemFree` at `0x18002c48a`

## string_xrefs

- `0x18002c37c`: `failed to allocate path`
- `0x18002c321`: `base\diagnosis\srt\reagent2\reagent\logfile.cpp`
- `0x18002c365`: `base\diagnosis\srt\reagent2\reagent\logfile.cpp`
- `0x18002c3cd`: `base\diagnosis\srt\reagent2\reagent\logfile.cpp`
- `0x18002c2f1`: `Enter WinReOpenLogInstance`
- `0x18002c338`: `failed to create log directory`
- `0x18002c341`: `WinReOpenLogInstance %s (0x%x) in file %S line %d`
- `0x18002c385`: `WinReOpenLogInstance %s (0x%x) in file %S line %d`
- `0x18002c3d7`: `WinReOpenLogInstance %s (0x%x) in file %S line %d`
- `0x18002c3c6`: `failed to add reload file to directory path`
- `0x18002c40f`: `failed to init agent reload`
- `0x18002c492`: `Exit WinReOpenLogInstance returns %d with last error: 0x%x`
- `0x18002c3a2`: `Reload.xml`

## pseudocode

```c
_BOOL8 __fastcall WinReOpenLogInstance(__int64 a1)
{
  unsigned __int16 *v1; // rsi
  void *v3; // r14
  DWORD v4; // edi
  const wchar_t *v5; // r8
  __int64 v6; // rbx
  int v8; // [rsp+28h] [rbp-61h]
  LPVOID pv; // [rsp+30h] [rbp-59h] BYREF
  unsigned __int16 *v10; // [rsp+38h] [rbp-51h] BYREF
  _QWORD v11[3]; // [rsp+40h] [rbp-49h] BYREF
  int v12; // [rsp+58h] [rbp-31h]
  int v13; // [rsp+5Ch] [rbp-2Dh]
  __int128 v14; // [rsp+60h] [rbp-29h]
  __int128 v15; // [rsp+70h] [rbp-19h]
  __int64 v16; // [rsp+80h] [rbp-9h]
  int v17; // [rsp+88h] [rbp-1h]
  __int64 v18; // [rsp+90h] [rbp+7h]

  v1 = 0;
  v10 = 0;
  v11[1] = 0;
  v11[2] = 0;
  v12 = 0;
  v3 = 0;
  v13 = 2;
  pv = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v11[0] = &ReAgentReload::`vftable';
  v18 = 0;
  UnattendInitializeLogEx2(0);
  UnattendLogW(0, L"Enter WinReOpenLogInstance");
  if ( a1 && *(_QWORD *)a1 == 72 )
  {
    v4 = winreCreateOrOpenLogDir((unsigned __int16 **)&pv);
    if ( v4 )
    {
      UnattendLogW(
        2,
        L"WinReOpenLogInstance %s (0x%x) in file %S line %d",
        L"failed to create log directory",
        v4,
        "base\\diagnosis\\srt\\reagent2\\reagent\\logfile.cpp",
        531);
      v3 = pv;
      goto LABEL_14;
    }
    v4 = winreAllocPath(&v10);
    if ( v4 )
    {
      UnattendLogW(
        2,
        L"WinReOpenLogInstance %s (0x%x) in file %S line %d",
        L"failed to allocate path",
        v4,
        "base\\diagnosis\\srt\\reagent2\\reagent\\logfile.cpp",
        537);
      v3 = pv;
      v1 = v10;
      goto LABEL_14;
    }
    v1 = v10;
    v3 = pv;
    v4 = winreAddFileToDirPath((unsigned __int16 *)pv, L"Reload.xml", v10);
    if ( v4 )
    {
      v8 = 541;
      v5 = L"failed to add reload file to directory path";
LABEL_9:
      UnattendLogW(
        2,
        L"WinReOpenLogInstance %s (0x%x) in file %S line %d",
        v5,
        v4,
        "base\\diagnosis\\srt\\reagent2\\reagent\\logfile.cpp",
        v8);
      goto LABEL_14;
    }
    v4 = ReAgentReload::Init((ReAgentReload *)v11, v1, 1);
    if ( v4 )
    {
      v8 = 544;
      v5 = L"failed to init agent reload";
      goto LABEL_9;
    }
    v6 = v18;
    *(_DWORD *)(a1 + 8) = *((_DWORD *)ReAgentXMLParser::GetConfigInfo((ReAgentXMLParser *)v11) + 1403);
    *(_DWORD *)(a1 + 12) = *(_DWORD *)(v6 + 12);
    *(_DWORD *)(a1 + 16) = *(_DWORD *)(v6 + 16);
    *(_DWORD *)(a1 + 20) = *(_DWORD *)(v6 + 20);
    *(_DWORD *)(a1 + 24) = *(_DWORD *)(v6 + 24);
    *(_DWORD *)(a1 + 28) = *(_DWORD *)(v6 + 28);
    *(_DWORD *)(a1 + 32) = *(_DWORD *)(v6 + 32);
    *(_OWORD *)(a1 + 52) = *(_OWORD *)(v6 + 52);
    *(_OWORD *)(a1 + 36) = *(_OWORD *)(v6 + 36);
  }
  else
  {
    v4 = 87;
  }
LABEL_14:
  if ( v3 )
    CoTaskMemFree(v3);
  if ( v1 )
    CoTaskMemFree(v1);
  UnattendLogW(0, L"Exit WinReOpenLogInstance returns %d with last error: 0x%x", v4 == 0, v4);
  UnattendFinalizeLog();
  SetLastError(v4);
  ReAgentReload::~ReAgentReload((ReAgentReload *)v11);
  return v4 == 0;
}

```

## disassembly

```asm
0x18002c280  push    rbp
0x18002c282  push    rbx
0x18002c283  push    rsi
0x18002c284  push    rdi
0x18002c285  push    r14
0x18002c287  push    r15
0x18002c289  lea     rbp, [rsp-2Fh]
0x18002c28e  sub     rsp, 0B8h
0x18002c295  mov     rax, cs:__security_cookie
0x18002c29c  xor     rax, rsp
0x18002c29f  mov     [rbp+57h+var_40], rax
0x18002c2a3  xor     esi, esi
0x18002c2a5  lea     rax, ??_7ReAgentReload@@6B@; const ReAgentReload::`vftable'
0x18002c2ac  mov     r15, rcx
0x18002c2af  mov     [rbp+57h+var_A8], rsi
0x18002c2b3  xorps   xmm0, xmm0
0x18002c2b6  mov     [rbp+57h+var_98], rsi
0x18002c2ba  xorps   xmm1, xmm1
0x18002c2bd  mov     [rbp+57h+var_90], rsi
0x18002c2c1  lea     ebx, [rsi+2]
0x18002c2c4  mov     [rbp+57h+var_88], esi
0x18002c2c7  xor     r14d, r14d
0x18002c2ca  mov     [rbp+57h+var_84], ebx
0x18002c2cd  xor     ecx, ecx
0x18002c2cf  mov     [rbp+57h+pv], r14
0x18002c2d3  movdqa  [rbp+57h+var_80], xmm0
0x18002c2d8  movdqa  [rbp+57h+var_70], xmm1
0x18002c2dd  mov     [rbp+57h+var_60], rsi
0x18002c2e1  mov     [rbp+57h+var_58], esi
0x18002c2e4  mov     [rbp+57h+var_A0], rax
0x18002c2e8  mov     [rbp+57h+var_50], rsi
0x18002c2ec  call    UnattendInitializeLogEx2
0x18002c2f1  lea     rdx, aEnterWinreopen; "Enter WinReOpenLogInstance"
0x18002c2f8  xor     ecx, ecx
0x18002c2fa  call    UnattendLogW
0x18002c2ff  test    r15, r15
0x18002c302  jz      loc_18002C46F
0x18002c308  cmp     qword ptr [r15], 48h ; 'H'
0x18002c30c  jnz     loc_18002C46F
0x18002c312  lea     rcx, [rbp+57h+pv]; unsigned __int16 **
0x18002c316  call    ?winreCreateOrOpenLogDir@@YAKPEAPEAG@Z; winreCreateOrOpenLogDir(ushort * *)
0x18002c31b  mov     edi, eax
0x18002c31d  test    eax, eax
0x18002c31f  jz      short loc_18002C356
0x18002c321  lea     rax, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002c328  mov     [rsp+0E0h+var_B8], 213h
0x18002c330  mov     r9d, edi
0x18002c333  mov     [rsp+0E0h+var_C0], rax
0x18002c338  lea     r8, aFailedToCreate_25; "failed to create log directory"
0x18002c33f  mov     ecx, ebx
0x18002c341  lea     rdx, aWinreopenlogin_0; "WinReOpenLogInstance %s (0x%x) in file "...
0x18002c348  call    UnattendLogW
0x18002c34d  mov     r14, [rbp+57h+pv]
0x18002c351  jmp     loc_18002C474
0x18002c356  lea     rcx, [rbp+57h+var_A8]
0x18002c35a  call    winreAllocPath
0x18002c35f  mov     edi, eax
0x18002c361  test    eax, eax
0x18002c363  jz      short loc_18002C39E
0x18002c365  lea     rax, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002c36c  mov     [rsp+0E0h+var_B8], 219h
0x18002c374  mov     r9d, edi
0x18002c377  mov     [rsp+0E0h+var_C0], rax
0x18002c37c  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x18002c383  mov     ecx, ebx
0x18002c385  lea     rdx, aWinreopenlogin_0; "WinReOpenLogInstance %s (0x%x) in file "...
0x18002c38c  call    UnattendLogW
0x18002c391  mov     r14, [rbp+57h+pv]
0x18002c395  mov     rsi, [rbp+57h+var_A8]
0x18002c399  jmp     loc_18002C474
0x18002c39e  mov     rsi, [rbp+57h+var_A8]
0x18002c3a2  lea     rdx, aReloadXml; "Reload.xml"
0x18002c3a9  mov     r14, [rbp+57h+pv]
0x18002c3ad  mov     r8, rsi; unsigned __int16 *
0x18002c3b0  mov     rcx, r14; unsigned __int16 *
0x18002c3b3  call    winreAddFileToDirPath
0x18002c3b8  mov     edi, eax
0x18002c3ba  test    eax, eax
0x18002c3bc  jz      short loc_18002C3EF
0x18002c3be  mov     [rsp+0E0h+var_B8], 21Dh
0x18002c3c6  lea     r8, aFailedToAddRel; "failed to add reload file to directory "...
0x18002c3cd  lea     rax, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002c3d4  mov     r9d, edi
0x18002c3d7  lea     rdx, aWinreopenlogin_0; "WinReOpenLogInstance %s (0x%x) in file "...
0x18002c3de  mov     [rsp+0E0h+var_C0], rax
0x18002c3e3  mov     ecx, ebx
0x18002c3e5  call    UnattendLogW
0x18002c3ea  jmp     loc_18002C474
0x18002c3ef  mov     r8d, 1; int
0x18002c3f5  lea     rcx, [rbp+57h+var_A0]; this
0x18002c3f9  mov     rdx, rsi; unsigned __int16 *
0x18002c3fc  call    ?Init@ReAgentReload@@UEAAKPEAGH@Z; ReAgentReload::Init(ushort *,int)
0x18002c401  mov     edi, eax
0x18002c403  test    eax, eax
0x18002c405  jz      short loc_18002C418
0x18002c407  mov     [rsp+0E0h+var_B8], 220h
0x18002c40f  lea     r8, aFailedToInitAg_1; "failed to init agent reload"
0x18002c416  jmp     short loc_18002C3CD
0x18002c418  mov     rbx, [rbp+57h+var_50]
0x18002c41c  lea     rcx, [rbp+57h+var_A0]; this
0x18002c420  call    ?GetConfigInfo@ReAgentXMLParser@@QEAAPEAUReAgentConfigInfo@@XZ; ReAgentXMLParser::GetConfigInfo(void)
0x18002c425  mov     ecx, [rax+15ECh]
0x18002c42b  mov     [r15+8], ecx
0x18002c42f  mov     eax, [rbx+0Ch]
0x18002c432  mov     [r15+0Ch], eax
0x18002c436  mov     eax, [rbx+10h]
0x18002c439  mov     [r15+10h], eax
0x18002c43d  mov     eax, [rbx+14h]
0x18002c440  mov     [r15+14h], eax
0x18002c444  mov     eax, [rbx+18h]
0x18002c447  mov     [r15+18h], eax
0x18002c44b  mov     eax, [rbx+1Ch]
0x18002c44e  mov     [r15+1Ch], eax
0x18002c452  mov     eax, [rbx+20h]
0x18002c455  mov     [r15+20h], eax
0x18002c459  movups  xmm0, xmmword ptr [rbx+34h]
0x18002c45d  movdqu  xmmword ptr [r15+34h], xmm0
0x18002c463  movups  xmm1, xmmword ptr [rbx+24h]
0x18002c467  movdqu  xmmword ptr [r15+24h], xmm1
0x18002c46d  jmp     short loc_18002C474
0x18002c46f  mov     edi, 57h ; 'W'
0x18002c474  test    r14, r14
0x18002c477  jz      short loc_18002C482
0x18002c479  mov     rcx, r14; pv
0x18002c47c  call    cs:__imp_CoTaskMemFree
0x18002c482  test    rsi, rsi
0x18002c485  jz      short loc_18002C490
0x18002c487  mov     rcx, rsi; pv
0x18002c48a  call    cs:__imp_CoTaskMemFree
0x18002c490  xor     ebx, ebx
0x18002c492  lea     rdx, aExitWinreopenl; "Exit WinReOpenLogInstance returns %d wi"...
0x18002c499  test    edi, edi
0x18002c49b  mov     r9d, edi
0x18002c49e  setz    bl
0x18002c4a1  xor     ecx, ecx
0x18002c4a3  mov     r8d, ebx
0x18002c4a6  call    UnattendLogW
0x18002c4ab  call    UnattendFinalizeLog
0x18002c4b0  mov     ecx, edi; dwErrCode
0x18002c4b2  call    cs:__imp_SetLastError
0x18002c4b8  lea     rcx, [rbp+57h+var_A0]; this
0x18002c4bc  call    ??1ReAgentReload@@UEAA@XZ; ReAgentReload::~ReAgentReload(void)
0x18002c4c1  mov     eax, ebx
0x18002c4c3  mov     rcx, [rbp+57h+var_40]
0x18002c4c7  xor     rcx, rsp; StackCookie
0x18002c4ca  call    __security_check_cookie
0x18002c4cf  add     rsp, 0B8h
0x18002c4d6  pop     r15
0x18002c4d8  pop     r14
0x18002c4da  pop     rdi
0x18002c4db  pop     rsi
0x18002c4dc  pop     rbx
0x18002c4dd  pop     rbp
0x18002c4de  retn
```
