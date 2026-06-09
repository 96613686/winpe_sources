# FindServicingStackDirectory

- ea: `0x14000c3e0`
- end: `0x14000c6dd`
- name: `FindServicingStackDirectory`
- size: `765`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x140009650`

## callees

- `0x1400023e0`
- `0x140002674`
- `0x140002de4`
- `0x14000c3e0`
- `0x14000c6e4`
- `0x140016948`
- `0x140017658`
- `0x140019d84`
- `0x14001f134`
- `0x14001f880`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000c6a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000c6a9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000c47b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000c47b`

## string_xrefs

- `0x14000c439`: `No servicing stack directory result specified`
- `0x14000c471`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Component Based Servicing\Version`
- `0x14000c49a`: `Get fallback servicing stack directory failed.`
- `0x14000c611`: `Get fallback servicing stack directory failed.`
- `0x14000c4b4`: `Failed to open servicing stack version registry key.`
- `0x14000c659`: `Failed to expand path to servicing stack directory: %S`

## pseudocode

```c
__int64 __fastcall FindServicingStackDirectory(_QWORD *a1)
{
  __int64 v1; // rdi
  unsigned int v3; // ebx
  const char *v4; // r9
  LSTATUS v5; // eax
  int FallbackServicingStackDirectory; // eax
  DWORD v7; // r15d
  unsigned int v8; // r12d
  unsigned int v9; // r13d
  unsigned int v10; // r9d
  unsigned __int64 v11; // rdx
  int v12; // eax
  unsigned __int64 v13; // rdx
  wchar_t *v14; // rdi
  unsigned int v15; // r15d
  int v16; // eax
  unsigned int v17; // r9d
  int v18; // eax
  DWORD v20; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v21; // [rsp+34h] [rbp-CCh] BYREF
  wchar_t *v22; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t v25[264]; // [rsp+60h] [rbp-A0h] BYREF

  v1 = 0;
  hKey = 0;
  v22 = 0;
  v23 = 0;
  if ( !a1 )
  {
    v3 = -2147467261;
    v4 = "No servicing stack directory result specified";
LABEL_3:
    CBSWdsLogLight(0x4000000, v3, 1, v4);
    goto LABEL_36;
  }
  *a1 = 0;
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\Version",
         0,
         0x20019u,
         &hKey);
  v3 = v5;
  if ( v5 == 2 )
  {
    FallbackServicingStackDirectory = GetFallbackServicingStackDirectory(a1);
    v3 = FallbackServicingStackDirectory;
    if ( FallbackServicingStackDirectory < 0 )
      CBSWdsLogLight(
        0x4000000,
        (unsigned int)FallbackServicingStackDirectory,
        1,
        "Get fallback servicing stack directory failed.");
    goto LABEL_36;
  }
  if ( v5 )
  {
    if ( v5 > 0 )
      v3 = (unsigned __int16)v5 | 0x80070000;
    v4 = "Failed to open servicing stack version registry key.";
    goto LABEL_3;
  }
  v7 = 0;
  v20 = 0;
  v8 = 0;
  v9 = 0;
  memset_0(v25, 0, 0x208u);
  v21 = 0;
  v3 = CbsRegEnumStringValue(hKey, 0, v25, v10, &v22);
  if ( v3 != -2147024637 )
  {
    while ( (v3 & 0x80000000) == 0 )
    {
      v12 = FileVersionFromString(v25, (char *)&v21 + 4, &v21);
      v14 = v22;
      if ( v12 )
      {
        if ( v12 != -2147024809 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
      }
      else
      {
        v15 = HIDWORD(v21);
        if ( __PAIR64__(v8, v9) < v21 )
        {
          v16 = FileExpandPath(v22, &v23);
          v3 = v16;
          if ( v16 < 0 )
          {
            CBSWdsLogLight(
              0x4000000,
              (unsigned int)v16,
              1,
              "Failed to expand path to servicing stack directory: %S",
              v14);
            goto LABEL_26;
          }
          v9 = v21;
          v8 = v15;
        }
        v7 = v20;
      }
      if ( v14 )
      {
        operator delete(v14 - 4, v13);
        v22 = 0;
      }
      v20 = ++v7;
      memset_0(v25, 0, 0x208u);
      v21 = 0;
      v3 = CbsRegEnumStringValue(hKey, v7, v25, v17, &v22);
      if ( v3 == -2147024637 )
      {
        v1 = v23;
        goto LABEL_22;
      }
    }
    CBSWdsLogLight(0x4000000, v3, 1, "Failed to enumerate all servicing stack versions.");
    goto LABEL_25;
  }
LABEL_22:
  v3 = 0;
  if ( !v1 )
  {
    CBSWdsLogLight(0x4000000, 2147942402LL, 1, "Unable to find servicing stack from store.");
    v18 = GetFallbackServicingStackDirectory(&v23);
    v3 = v18;
    if ( v18 < 0 )
    {
      CBSWdsLogLight(0x4000000, (unsigned int)v18, 1, "Get fallback servicing stack directory failed.");
LABEL_25:
      v14 = v22;
LABEL_26:
      if ( v23 )
        operator delete((void *)(v23 - 8), v11);
      goto LABEL_34;
    }
    v1 = v23;
  }
  *a1 = v1;
  v14 = v22;
LABEL_34:
  if ( v14 )
    operator delete(v14 - 4, v11);
LABEL_36:
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x14000c3e0  mov     [rsp-8+arg_8], rbx
0x14000c3e5  mov     [rsp-8+arg_10], rdi
0x14000c3ea  push    rbp
0x14000c3eb  push    r12
0x14000c3ed  push    r13
0x14000c3ef  push    r14
0x14000c3f1  push    r15
0x14000c3f3  lea     rbp, [rsp-180h]
0x14000c3fb  sub     rsp, 280h
0x14000c402  mov     rax, cs:__security_cookie
0x14000c409  xor     rax, rsp
0x14000c40c  mov     [rbp+1A0h+var_30], rax
0x14000c413  xor     edi, edi
0x14000c415  mov     [rsp+2A0h+hKey], 0
0x14000c41e  mov     [rsp+2A0h+var_260], 0
0x14000c427  mov     r14, rcx
0x14000c42a  mov     [rsp+2A0h+var_258], rdi
0x14000c42f  test    rcx, rcx
0x14000c432  jnz     short loc_14000C457
0x14000c434  mov     ebx, 80004003h
0x14000c439  lea     r9, aNoServicingSta; "No servicing stack directory result spe"...
0x14000c440  mov     edx, ebx
0x14000c442  mov     r8d, 1
0x14000c448  mov     ecx, 4000000h
0x14000c44d  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000c452  jmp     loc_14000C69F
0x14000c457  mov     [rcx], rdi
0x14000c45a  lea     rax, [rsp+2A0h+hKey]
0x14000c45f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000c466  mov     [rsp+2A0h+phkResult], rax; phkResult
0x14000c46b  mov     r9d, 20019h; samDesired
0x14000c471  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14000c478  xor     r8d, r8d; ulOptions
0x14000c47b  call    cs:__imp_RegOpenKeyExW
0x14000c481  mov     ebx, eax
0x14000c483  cmp     eax, 2
0x14000c486  jnz     short loc_14000C4A5
0x14000c488  mov     rcx, r14
0x14000c48b  call    GetFallbackServicingStackDirectory
0x14000c490  mov     ebx, eax
0x14000c492  test    eax, eax
0x14000c494  jns     loc_14000C69F
0x14000c49a  lea     r9, aGetFallbackSer; "Get fallback servicing stack directory "...
0x14000c4a1  mov     edx, eax
0x14000c4a3  jmp     short loc_14000C442
0x14000c4a5  test    eax, eax
0x14000c4a7  jz      short loc_14000C4BD
0x14000c4a9  jle     short loc_14000C4B4
0x14000c4ab  movzx   ebx, ax
0x14000c4ae  or      ebx, 80070000h
0x14000c4b4  lea     r9, aFailedToOpenSe; "Failed to open servicing stack version "...
0x14000c4bb  jmp     short loc_14000C440
0x14000c4bd  xor     r15d, r15d
0x14000c4c0  lea     rcx, [rsp+2A0h+var_240]; void *
0x14000c4c5  xor     edx, edx; Val
0x14000c4c7  mov     [rsp+2A0h+var_270], r15d
0x14000c4cc  mov     r8d, 208h; Size
0x14000c4d2  xor     r12d, r12d
0x14000c4d5  xor     r13d, r13d
0x14000c4d8  call    memset_0
0x14000c4dd  mov     rcx, [rsp+2A0h+hKey]; hKey
0x14000c4e2  lea     rax, [rsp+2A0h+var_260]
0x14000c4e7  lea     r8, [rsp+2A0h+var_240]; wchar_t *
0x14000c4ec  mov     [rsp+2A0h+phkResult], rax; wchar_t **
0x14000c4f1  xor     edx, edx; dwIndex
0x14000c4f3  mov     dword ptr [rsp+2A0h+var_26C+4], edi
0x14000c4f7  mov     dword ptr [rsp+2A0h+var_26C], edi
0x14000c4fb  call    ?CbsRegEnumStringValue@@YAJPEAUHKEY__@@KPEA_WKPEAPEA_W@Z; CbsRegEnumStringValue(HKEY__ *,ulong,wchar_t *,ulong,wchar_t * *)
0x14000c500  mov     ebx, eax
0x14000c502  cmp     eax, 80070103h
0x14000c507  jz      loc_14000C5DC
0x14000c50d  test    ebx, ebx
0x14000c50f  js      loc_14000C679
0x14000c515  lea     r8, [rsp+2A0h+var_26C]
0x14000c51a  lea     rdx, [rsp+2A0h+var_26C+4]
0x14000c51f  lea     rcx, [rsp+2A0h+var_240]
0x14000c524  call    FileVersionFromString
0x14000c529  mov     rdi, [rsp+2A0h+var_260]
0x14000c52e  test    eax, eax
0x14000c530  jnz     loc_14000C644
0x14000c536  mov     r15d, dword ptr [rsp+2A0h+var_26C+4]
0x14000c53b  cmp     r12d, r15d
0x14000c53e  jb      short loc_14000C549
0x14000c540  jnz     short loc_14000C568
0x14000c542  cmp     r13d, dword ptr [rsp+2A0h+var_26C]
0x14000c547  jnb     short loc_14000C568
0x14000c549  lea     rdx, [rsp+2A0h+var_258]
0x14000c54e  mov     rcx, rdi
0x14000c551  call    FileExpandPath
0x14000c556  mov     ebx, eax
0x14000c558  test    eax, eax
0x14000c55a  js      loc_14000C659
0x14000c560  mov     r13d, dword ptr [rsp+2A0h+var_26C]
0x14000c565  mov     r12d, r15d
0x14000c568  mov     r15d, [rsp+2A0h+var_270]
0x14000c56d  test    rdi, rdi
0x14000c570  jz      short loc_14000C584
0x14000c572  lea     rcx, [rdi-8]; void *
0x14000c576  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000c57b  mov     [rsp+2A0h+var_260], 0
0x14000c584  inc     r15d
0x14000c587  lea     rcx, [rsp+2A0h+var_240]; void *
0x14000c58c  xor     edx, edx; Val
0x14000c58e  mov     [rsp+2A0h+var_270], r15d
0x14000c593  mov     r8d, 208h; Size
0x14000c599  call    memset_0
0x14000c59e  mov     rcx, [rsp+2A0h+hKey]; hKey
0x14000c5a3  lea     rax, [rsp+2A0h+var_260]
0x14000c5a8  lea     r8, [rsp+2A0h+var_240]; wchar_t *
0x14000c5ad  mov     [rsp+2A0h+phkResult], rax; wchar_t **
0x14000c5b2  mov     edx, r15d; dwIndex
0x14000c5b5  mov     dword ptr [rsp+2A0h+var_26C+4], 0
0x14000c5bd  mov     dword ptr [rsp+2A0h+var_26C], 0
0x14000c5c5  call    ?CbsRegEnumStringValue@@YAJPEAUHKEY__@@KPEA_WKPEAPEA_W@Z; CbsRegEnumStringValue(HKEY__ *,ulong,wchar_t *,ulong,wchar_t * *)
0x14000c5ca  mov     ebx, eax
0x14000c5cc  cmp     eax, 80070103h
0x14000c5d1  jnz     loc_14000C50D
0x14000c5d7  mov     rdi, [rsp+2A0h+var_258]
0x14000c5dc  xor     ebx, ebx
0x14000c5de  test    rdi, rdi
0x14000c5e1  jnz     loc_14000C689
0x14000c5e7  lea     r9, aUnableToFindSe; "Unable to find servicing stack from sto"...
0x14000c5ee  mov     edx, 80070002h
0x14000c5f3  mov     ecx, 4000000h
0x14000c5f8  lea     r8d, [rbx+1]
0x14000c5fc  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000c601  lea     rcx, [rsp+2A0h+var_258]
0x14000c606  call    GetFallbackServicingStackDirectory
0x14000c60b  mov     ebx, eax
0x14000c60d  test    eax, eax
0x14000c60f  jns     short loc_14000C684
0x14000c611  lea     r9, aGetFallbackSer; "Get fallback servicing stack directory "...
0x14000c618  mov     edx, eax
0x14000c61a  mov     r8d, 1
0x14000c620  mov     ecx, 4000000h
0x14000c625  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000c62a  mov     rdi, [rsp+2A0h+var_260]
0x14000c62f  mov     rcx, [rsp+2A0h+var_258]
0x14000c634  test    rcx, rcx
0x14000c637  jz      short loc_14000C691
0x14000c639  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x14000c63d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000c642  jmp     short loc_14000C691
0x14000c644  cmp     eax, 80070057h
0x14000c649  jz      loc_14000C56D
0x14000c64f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14000c654  jmp     loc_14000C56D
0x14000c659  lea     r9, aFailedToExpand; "Failed to expand path to servicing stac"...
0x14000c660  mov     [rsp+2A0h+phkResult], rdi
0x14000c665  mov     r8d, 1
0x14000c66b  mov     edx, eax
0x14000c66d  mov     ecx, 4000000h
0x14000c672  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000c677  jmp     short loc_14000C62F
0x14000c679  lea     r9, aFailedToEnumer_0; "Failed to enumerate all servicing stack"...
0x14000c680  mov     edx, ebx
0x14000c682  jmp     short loc_14000C61A
0x14000c684  mov     rdi, [rsp+2A0h+var_258]
0x14000c689  mov     [r14], rdi
0x14000c68c  mov     rdi, [rsp+2A0h+var_260]
0x14000c691  test    rdi, rdi
0x14000c694  jz      short loc_14000C69F
0x14000c696  lea     rcx, [rdi-8]; void *
0x14000c69a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000c69f  mov     rcx, [rsp+2A0h+hKey]; hKey
0x14000c6a4  test    rcx, rcx
0x14000c6a7  jz      short loc_14000C6AF
0x14000c6a9  call    cs:__imp_RegCloseKey
0x14000c6af  mov     eax, ebx
0x14000c6b1  mov     rcx, [rbp+1A0h+var_30]
0x14000c6b8  xor     rcx, rsp; StackCookie
0x14000c6bb  call    __security_check_cookie
0x14000c6c0  lea     r11, [rsp+2A0h+var_20]
0x14000c6c8  mov     rbx, [r11+38h]
0x14000c6cc  mov     rdi, [r11+40h]
0x14000c6d0  mov     rsp, r11
0x14000c6d3  pop     r15
0x14000c6d5  pop     r14
0x14000c6d7  pop     r13
0x14000c6d9  pop     r12
0x14000c6db  pop     rbp
0x14000c6dc  retn
```
