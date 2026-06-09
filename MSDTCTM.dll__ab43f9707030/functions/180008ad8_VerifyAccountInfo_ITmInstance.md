# VerifyAccountInfo(ITmInstance *)

- ea: `0x180008ad8`
- end: `0x180008e0a`
- name: `?VerifyAccountInfo@@YAJPEAUITmInstance@@@Z`
- size: `818`
- prototype: `__int64 __fastcall(struct ITmInstance *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180006750`

## callees

- `0x180007d08`
- `0x180008ad8`
- `0x180014b94`
- `0x180015230`
- `0x180016f3c`
- `0x18001f34c`
- `0x1800240b0`
- `0x1800240f0`
- `0x1800240fc`
- `0x180085f64`
- `0x1800b83ee`
- `0x1800b8420`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c0b`
- `msvcrt!_wcsicmp` at `0x180008d27`
- `msvcrt!_wcsicmp` at `0x180008d27`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180008c01`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180008c01`

## string_xrefs

- `0x180008d7f`: `com\complus\dtc\shared\util\security.cpp`
- `0x180008b72`: `com\complus\dtc\shared\util\scm.cpp`
- `0x180008c4f`: `com\complus\dtc\shared\util\scm.cpp`
- `0x180008b79`: `CService::InternalInit call failed`
- `0x180008c56`: `QueryServiceConfigW call failed`
- `0x180008d70`: `msdtc_trace : File: %s, Line: %d, VerifyAccountInfo: CService::Create failed, hr=0x%x\n`
- `0x180008d69`: `VerifyAccountInfo: CService::Create failed`
- `0x180008cb1`: `msdtc_trace : File: %s, Line: %d, VerifyAccountInfo: pDTCService->GetAccount failed, hr=0x%x\n`
- `0x180008caa`: `VerifyAccountInfo: pDTCService->GetAccount failed`
- `0x180008d0a`: `msdtc_trace : File: %s, Line: %d, VerifyAccountInfo : ReadRegKeyValue32W(ACCOUNT_NAME) failed, hr=0x%x\n`
- `0x180008cfd`: `VerifyAccountInfo : ReadRegKeyValue32W(ACCOUNT_NAME) failed`

## pseudocode

```c
__int64 __fastcall VerifyAccountInfo(struct ITmInstance *a1)
{
  SC_HANDLE *v2; // r14
  volatile signed __int32 *v3; // rax
  unsigned __int16 *v4; // rdx
  struct CServiceControlManager *v5; // r8
  unsigned int v6; // r9d
  volatile signed __int32 *v7; // rdi
  int v8; // eax
  signed int v9; // ebx
  struct _QUERY_SERVICE_CONFIGW *v10; // rdi
  int i; // esi
  struct _QUERY_SERVICE_CONFIGW *v12; // rax
  signed int LastError; // eax
  const unsigned __int16 *lpServiceStartName; // r8
  __int64 v15; // r11
  unsigned int v16; // r13d
  char *v17; // r15
  const char *v18; // r8
  __int64 v19; // rax
  int v20; // eax
  unsigned int v21; // edi
  int v22; // esi
  unsigned __int16 *v24; // [rsp+20h] [rbp-E0h]
  int v25; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v26; // [rsp+40h] [rbp-C0h] BYREF
  size_t Size; // [rsp+48h] [rbp-B8h] BYREF
  char v28; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v29[783]; // [rsp+51h] [rbp-AFh] BYREF
  wchar_t String2[256]; // [rsp+360h] [rbp+260h] BYREF
  wchar_t String1[256]; // [rsp+560h] [rbp+460h] BYREF

  LODWORD(v26) = 0;
  v28 = 0;
  v2 = 0;
  memset_0(v29, 0, 0x303u);
  v3 = (volatile signed __int32 *)operator new(0x18u);
  Size = (size_t)v3;
  v7 = v3;
  if ( !v3 )
  {
    v9 = -2147024882;
LABEL_38:
    v16 = 819;
    v17 = "VerifyAccountInfo: CService::Create failed";
    v18 = "msdtc_trace : File: %s, Line: %d, VerifyAccountInfo: CService::Create failed, hr=0x%x\n";
    goto LABEL_39;
  }
  *v3 = 1;
  *((_QWORD *)v3 + 1) = 0;
  *((_QWORD *)v3 + 2) = 0;
  v8 = CService::InternalInit((CService *)v3, v4, v5, v6, v24);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v2 = (SC_HANDLE *)v7;
    _InterlockedAdd(v7, 1u);
  }
  else
  {
    TraceFile(v8, "CService::InternalInit call failed", "com\\complus\\dtc\\shared\\util\\scm.cpp", 0x13Cu);
  }
  CService::Release((CService *)v7);
  if ( v9 < 0 )
    goto LABEL_38;
  LODWORD(v26) = 256;
  v9 = 0;
  LODWORD(Size) = 64;
  v10 = 0;
  for ( i = 2; i; --i )
  {
    if ( v10 )
      operator delete(v10);
    v12 = (struct _QUERY_SERVICE_CONFIGW *)operator new[]((unsigned int)Size);
    v10 = v12;
    if ( !v12 )
    {
      v9 = -2147024882;
LABEL_22:
      TraceFile(v9, "QueryServiceConfigW call failed", "com\\complus\\dtc\\shared\\util\\scm.cpp", 0x1E8u);
      goto LABEL_28;
    }
    memset_0(v12, 0, (unsigned int)Size);
    if ( QueryServiceConfigW(v2[2], v10, Size, (LPDWORD)&Size) )
    {
      v9 = 0;
      goto LABEL_18;
    }
    LastError = GetLastError();
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    else
      v9 = LastError;
    if ( LastError != 122 )
      break;
  }
  if ( v9 < 0 )
    goto LABEL_22;
LABEL_18:
  lpServiceStartName = v10->lpServiceStartName;
  if ( lpServiceStartName )
  {
    v15 = -1;
    do
      ++v15;
    while ( lpServiceStartName[v15] );
    if ( (int)v15 + 1 <= (unsigned int)v26 )
      StringCchCopyW(String1, (unsigned int)v26, lpServiceStartName);
    LODWORD(v26) = v15;
  }
  else
  {
    LODWORD(v26) = 0;
  }
LABEL_28:
  if ( v10 )
    operator delete(v10);
  if ( v9 < 0 )
  {
    v16 = 828;
    v17 = "VerifyAccountInfo: pDTCService->GetAccount failed";
    v18 = "msdtc_trace : File: %s, Line: %d, VerifyAccountInfo: pDTCService->GetAccount failed, hr=0x%x\n";
LABEL_39:
    v22 = v9;
    v21 = v9;
    goto LABEL_40;
  }
  v19 = *(_QWORD *)a1;
  LODWORD(v26) = 256;
  v20 = (*(__int64 (__fastcall **)(struct ITmInstance *, const wchar_t *, wchar_t *, unsigned __int64 *))(v19 + 240))(
          a1,
          L"AccountName",
          String2,
          &v26);
  v21 = v20;
  if ( v20 >= 0 )
  {
    if ( !_wcsicmp(String1, String2) )
      goto LABEL_41;
    goto LABEL_36;
  }
  if ( v20 == -2147024891 )
  {
LABEL_36:
    DtcWriteToEventLoggerA(1u, 8u, 0xC0001155, 0, 0, &v28, v25);
    v21 = 0;
    goto LABEL_41;
  }
  v22 = v20;
  v17 = "VerifyAccountInfo : ReadRegKeyValue32W(ACCOUNT_NAME) failed";
  v16 = 838;
  v18 = "msdtc_trace : File: %s, Line: %d, VerifyAccountInfo : ReadRegKeyValue32W(ACCOUNT_NAME) failed, hr=0x%x\n";
LABEL_40:
  StringCchPrintfA(&v28, 0x304u, v18);
  TraceFile(v22, v17, "com\\complus\\dtc\\shared\\util\\security.cpp", v16);
  DtcWriteToEventLoggerA(1u, 8u, 0xC0001157, 0, 0, &v28, v25);
LABEL_41:
  if ( v2 )
    CService::Release((CService *)v2);
  return v21;
}

```

## disassembly

```asm
0x180008ad8  push    rbp
0x180008ada  push    rbx
0x180008adb  push    rsi
0x180008adc  push    rdi
0x180008add  push    r12
0x180008adf  push    r13
0x180008ae1  push    r14
0x180008ae3  push    r15
0x180008ae5  lea     rbp, [rsp-678h]
0x180008aed  sub     rsp, 778h
0x180008af4  mov     rax, cs:__security_cookie
0x180008afb  xor     rax, rsp
0x180008afe  mov     [rbp+6B0h+var_50], rax
0x180008b05  xor     r12d, r12d
0x180008b08  mov     r15, rcx
0x180008b0b  lea     rcx, [rsp+7B0h+var_75F]; void *
0x180008b10  mov     dword ptr [rsp+7B0h+var_770], r12d
0x180008b15  xor     edx, edx; Val
0x180008b17  mov     [rsp+7B0h+var_760], r12b
0x180008b1c  mov     r8d, 303h; Size
0x180008b22  mov     r14d, r12d
0x180008b25  call    memset_0
0x180008b2a  lea     ecx, [r12+18h]; Size
0x180008b2f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008b34  mov     [rsp+7B0h+Size], rax
0x180008b39  mov     rdi, rax
0x180008b3c  lea     r13d, [r12+1]
0x180008b41  test    rax, rax
0x180008b44  jz      loc_180008D5E
0x180008b4a  mov     [rax], r13d
0x180008b4d  mov     [rax+8], r12
0x180008b51  mov     [rax+10h], r12
0x180008b55  test    rax, rax
0x180008b58  jz      loc_180008D5E
0x180008b5e  mov     rcx, rax; this
0x180008b61  call    ?InternalInit@CService@@IEAAJPEAGPEAVCServiceControlManager@@K0@Z; CService::InternalInit(ushort *,CServiceControlManager *,ulong,ushort *)
0x180008b66  mov     ebx, eax
0x180008b68  test    eax, eax
0x180008b6a  jns     short loc_180008B89
0x180008b6c  mov     r9d, 13Ch; unsigned int
0x180008b72  lea     r8, aComComplusDtcS_1; "com\\complus\\dtc\\shared\\util\\scm.cp"...
0x180008b79  lea     rdx, aCserviceIntern; "CService::InternalInit call failed"
0x180008b80  mov     ecx, eax; int
0x180008b82  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180008b87  jmp     short loc_180008B90
0x180008b89  mov     r14, rdi
0x180008b8c  lock add [rdi], r13d
0x180008b90  mov     rcx, rdi; this
0x180008b93  call    ?Release@CService@@QEAAKXZ; CService::Release(void)
0x180008b98  test    ebx, ebx
0x180008b9a  js      loc_180008D63
0x180008ba0  mov     dword ptr [rsp+7B0h+var_770], 100h
0x180008ba8  mov     ebx, r12d
0x180008bab  mov     dword ptr [rsp+7B0h+Size], 40h ; '@'
0x180008bb3  mov     rdi, r12
0x180008bb6  mov     esi, 2
0x180008bbb  test    esi, esi
0x180008bbd  jz      loc_180008C45
0x180008bc3  test    rdi, rdi
0x180008bc6  jz      short loc_180008BD0
0x180008bc8  mov     rcx, rdi; Block
0x180008bcb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008bd0  mov     ecx, dword ptr [rsp+7B0h+Size]; unsigned __int64
0x180008bd4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180008bd9  mov     rdi, rax
0x180008bdc  test    rax, rax
0x180008bdf  jz      short loc_180008C3E
0x180008be1  mov     r8d, dword ptr [rsp+7B0h+Size]; Size
0x180008be6  xor     edx, edx; Val
0x180008be8  mov     rcx, rax; void *
0x180008beb  call    memset_0
0x180008bf0  mov     r8d, dword ptr [rsp+7B0h+Size]; cbBufSize
0x180008bf5  lea     r9, [rsp+7B0h+Size]; pcbBytesNeeded
0x180008bfa  mov     rcx, [r14+10h]; hService
0x180008bfe  mov     rdx, rdi; lpServiceConfig
0x180008c01  call    cs:__imp_QueryServiceConfigW
0x180008c07  test    eax, eax
0x180008c09  jnz     short loc_180008C2B
0x180008c0b  call    cs:__imp_GetLastError
0x180008c11  test    eax, eax
0x180008c13  jg      short loc_180008C19
0x180008c15  mov     ebx, eax
0x180008c17  jmp     short loc_180008C22
0x180008c19  movzx   ebx, ax
0x180008c1c  or      ebx, 80070000h
0x180008c22  cmp     eax, 7Ah ; 'z'
0x180008c25  jnz     short loc_180008C45
0x180008c27  dec     esi
0x180008c29  jmp     short loc_180008BBB
0x180008c2b  mov     ebx, r12d
0x180008c2e  mov     r8, [rdi+30h]; unsigned __int16 *
0x180008c32  test    r8, r8
0x180008c35  jnz     short loc_180008C66
0x180008c37  mov     dword ptr [rsp+7B0h+var_770], r12d
0x180008c3c  jmp     short loc_180008C93
0x180008c3e  mov     ebx, 8007000Eh
0x180008c43  jmp     short loc_180008C49
0x180008c45  test    ebx, ebx
0x180008c47  jns     short loc_180008C2E
0x180008c49  mov     r9d, 1E8h; unsigned int
0x180008c4f  lea     r8, aComComplusDtcS_1; "com\\complus\\dtc\\shared\\util\\scm.cp"...
0x180008c56  lea     rdx, aQueryserviceco; "QueryServiceConfigW call failed"
0x180008c5d  mov     ecx, ebx; int
0x180008c5f  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180008c64  jmp     short loc_180008C93
0x180008c66  or      r11, 0FFFFFFFFFFFFFFFFh
0x180008c6a  inc     r11
0x180008c6d  cmp     [r8+r11*2], r12w
0x180008c72  jnz     short loc_180008C6A
0x180008c74  lea     eax, [r11+1]
0x180008c78  cmp     eax, dword ptr [rsp+7B0h+var_770]
0x180008c7c  ja      short loc_180008C8E
0x180008c7e  mov     edx, dword ptr [rsp+7B0h+var_770]; unsigned __int64
0x180008c82  lea     rcx, [rbp+6B0h+String1]; unsigned __int16 *
0x180008c89  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008c8e  mov     dword ptr [rsp+7B0h+var_770], r11d
0x180008c93  test    rdi, rdi
0x180008c96  jz      short loc_180008CA0
0x180008c98  mov     rcx, rdi; Block
0x180008c9b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008ca0  test    ebx, ebx
0x180008ca2  jns     short loc_180008CC1
0x180008ca4  mov     r13d, 33Ch
0x180008caa  lea     r15, aVerifyaccounti_0; "VerifyAccountInfo: pDTCService->GetAcco"...
0x180008cb1  lea     r8, aMsdtcTraceFile_0; "msdtc_trace : File: %s, Line: %d, Verif"...
0x180008cb8  lea     eax, [r13-1]
0x180008cbc  jmp     loc_180008D7B
0x180008cc1  mov     rax, [r15]
0x180008cc4  lea     r9, [rsp+7B0h+var_770]
0x180008cc9  lea     r8, [rbp+6B0h+String2]
0x180008cd0  mov     dword ptr [rsp+7B0h+var_770], 100h
0x180008cd8  lea     rdx, aAccountname; "AccountName"
0x180008cdf  mov     rcx, r15
0x180008ce2  mov     rax, [rax+0F0h]
0x180008ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cee  mov     edi, eax
0x180008cf0  test    eax, eax
0x180008cf2  jns     short loc_180008D19
0x180008cf4  cmp     eax, 80070005h
0x180008cf9  jz      short loc_180008D35
0x180008cfb  mov     esi, eax
0x180008cfd  lea     r15, aVerifyaccounti_1; "VerifyAccountInfo : ReadRegKeyValue32W("...
0x180008d04  mov     r13d, 346h
0x180008d0a  lea     r8, aMsdtcTraceFile_1; "msdtc_trace : File: %s, Line: %d, Verif"...
0x180008d11  mov     ebx, esi
0x180008d13  lea     eax, [r13-1]
0x180008d17  jmp     short loc_180008D7F
0x180008d19  lea     rdx, [rbp+6B0h+String2]; String2
0x180008d20  lea     rcx, [rbp+6B0h+String1]; String1
0x180008d27  call    cs:__imp__wcsicmp
0x180008d2d  test    eax, eax
0x180008d2f  jz      loc_180008DD8
0x180008d35  xor     r9d, r9d; unsigned int
0x180008d38  lea     rax, [rsp+7B0h+var_760]
0x180008d3d  mov     [rsp+7B0h+var_788], rax; char *
0x180008d42  mov     r8d, 0C0001155h; unsigned int
0x180008d48  mov     ecx, r13d; unsigned int
0x180008d4b  mov     [rsp+7B0h+var_790], r12; void *
0x180008d50  lea     edx, [r9+8]; unsigned int
0x180008d54  call    ?DtcWriteToEventLoggerA@@YAJKKKKPEAXPEADH@Z; DtcWriteToEventLoggerA(ulong,ulong,ulong,ulong,void *,char *,int)
0x180008d59  mov     edi, r12d
0x180008d5c  jmp     short loc_180008DD8
0x180008d5e  mov     ebx, 8007000Eh
0x180008d63  mov     r13d, 333h
0x180008d69  lea     r15, aVerifyaccounti; "VerifyAccountInfo: CService::Create fai"...
0x180008d70  lea     r8, aMsdtcTraceFile; "msdtc_trace : File: %s, Line: %d, Verif"...
0x180008d77  lea     eax, [r13-1]
0x180008d7b  mov     esi, ebx
0x180008d7d  mov     edi, ebx
0x180008d7f  lea     r9, aComComplusDtcS_7; "com\\complus\\dtc\\shared\\util\\securi"...
0x180008d86  mov     dword ptr [rsp+7B0h+var_788], ebx
0x180008d8a  lea     rcx, [rsp+7B0h+var_760]; char *
0x180008d8f  mov     dword ptr [rsp+7B0h+var_790], eax
0x180008d93  mov     edx, 304h; unsigned __int64
0x180008d98  mov     r12, r9
0x180008d9b  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180008da0  mov     r9d, r13d; unsigned int
0x180008da3  mov     r8, r12; char *
0x180008da6  mov     rdx, r15; char *
0x180008da9  mov     ecx, esi; int
0x180008dab  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180008db0  xor     r12d, r12d
0x180008db3  lea     rax, [rsp+7B0h+var_760]
0x180008db8  mov     [rsp+7B0h+var_788], rax; char *
0x180008dbd  xor     r9d, r9d; unsigned int
0x180008dc0  mov     r8d, 0C0001157h; unsigned int
0x180008dc6  mov     [rsp+7B0h+var_790], r12; void *
0x180008dcb  lea     edx, [r12+8]; unsigned int
0x180008dd0  lea     ecx, [rdx-7]; unsigned int
0x180008dd3  call    ?DtcWriteToEventLoggerA@@YAJKKKKPEAXPEADH@Z; DtcWriteToEventLoggerA(ulong,ulong,ulong,ulong,void *,char *,int)
0x180008dd8  test    r14, r14
0x180008ddb  jz      short loc_180008DE5
0x180008ddd  mov     rcx, r14; this
0x180008de0  call    ?Release@CService@@QEAAKXZ; CService::Release(void)
0x180008de5  mov     eax, edi
0x180008de7  mov     rcx, [rbp+6B0h+var_50]
0x180008dee  xor     rcx, rsp; StackCookie
0x180008df1  call    __security_check_cookie
0x180008df6  add     rsp, 778h
0x180008dfd  pop     r15
0x180008dff  pop     r14
0x180008e01  pop     r13
0x180008e03  pop     r12
0x180008e05  pop     rdi
0x180008e06  pop     rsi
0x180008e07  pop     rbx
0x180008e08  pop     rbp
0x180008e09  retn
```
