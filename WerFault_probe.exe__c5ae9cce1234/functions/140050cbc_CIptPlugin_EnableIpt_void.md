# CIptPlugin::EnableIpt(void)

- ea: `0x140050cbc`
- end: `0x140050ee8`
- name: `?EnableIpt@CIptPlugin@@AEAAJXZ`
- size: `556`
- prototype: `__int64 __fastcall(CIptPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1400513f0`

## callees

- `0x14001444c`
- `0x140014474`
- `0x140050cbc`
- `0x140051524`
- `0x1400554e4`
- `0x1400558fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050d11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050d7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050dbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050de4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050d11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050d7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050dbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050de4`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140050ce2`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140050ce2`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x140050dab`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x140050dab`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140050e0c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140050e15`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140050e0c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140050e15`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140050d4b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140050d4b`
- `ntdll!RtlInitUnicodeString` at `0x140050e74`
- `ntdll!RtlInitUnicodeString` at `0x140050e8b`
- `ntdll!RtlInitUnicodeString` at `0x140050e74`
- `ntdll!RtlInitUnicodeString` at `0x140050e8b`

## pseudocode

```c
int __fastcall CIptPlugin::EnableIpt(PCWSTR *this)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // r14
  CUserModeHangReport *v4; // rcx
  DWORD LastError; // eax
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rbp
  BOOL started; // esi
  DWORD v9; // eax
  DWORD v10; // eax
  const WCHAR *v12; // rdx
  struct _UNICODE_STRING *p_DestinationString; // rdi
  int v14; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  struct _UNICODE_STRING v16; // [rsp+40h] [rbp-38h] BYREF

  v16 = 0;
  DestinationString = 0;
  v2 = OpenSCManagerW(0, 0, 1u);
  v3 = v2;
  if ( !v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control )
      return -2147467259;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
LABEL_18:
      if ( v4 != (CUserModeHangReport *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)v4 + 2), 23, &WPP_3229bad3034f32dffa4581e190add958_Traceguids);
      return -2147467259;
    }
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 171, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids, LastError);
LABEL_17:
    v4 = WPP_GLOBAL_Control;
    goto LABEL_18;
  }
  v6 = OpenServiceW(v2, L"Ipt", 0x10u);
  v7 = v6;
  if ( v6 )
  {
    started = StartServiceW(v6, 0, 0);
    if ( !started )
    {
      if ( GetLastError() == 1056 )
      {
        started = 1;
      }
      else if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v10 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 173, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids, v10);
      }
    }
    CloseServiceHandle(v7);
  }
  else
  {
    started = 0;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v9 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 172, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids, v9);
    }
  }
  CloseServiceHandle(v3);
  if ( !started )
    goto LABEL_17;
  CIptPlugin::PrepareIptSettings((CIptPlugin *)this);
  if ( *((_BYTE *)this + 2880) )
  {
    v14 = StartCoreIptTracing(this[358], *((unsigned int *)this + 718), (unsigned int)(86400 * *((_DWORD *)this + 719)));
  }
  else
  {
    v12 = this[357];
    LODWORD(p_DestinationString) = 0;
    if ( v12 )
    {
      RtlInitUnicodeString(&DestinationString, v12);
      p_DestinationString = &DestinationString;
    }
    RtlInitUnicodeString(&v16, this[356]);
    v14 = RegisterExtendedImageForIptTracing(
            (unsigned int)&v16,
            (_DWORD)p_DestinationString,
            (unsigned int)this[358],
            *((_DWORD *)this + 718),
            86400 * *((_DWORD *)this + 719));
  }
  return v14 | 0x10000000;
}

```

## disassembly

```asm
0x140050cbc  push    rbx
0x140050cbe  push    rbp
0x140050cbf  push    rsi
0x140050cc0  push    rdi
0x140050cc1  push    r14
0x140050cc3  sub     rsp, 50h
0x140050cc7  xor     edx, edx; lpDatabaseName
0x140050cc9  mov     rbx, rcx
0x140050ccc  xorps   xmm0, xmm0
0x140050ccf  xorps   xmm1, xmm1
0x140050cd2  xor     ecx, ecx; lpMachineName
0x140050cd4  movups  xmmword ptr [rsp+78h+var_38.Length], xmm0
0x140050cd9  lea     r8d, [rdx+1]; dwDesiredAccess
0x140050cdd  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm1
0x140050ce2  call    cs:__imp_OpenSCManagerW
0x140050ce8  mov     r14, rax
0x140050ceb  test    rax, rax
0x140050cee  jnz     short loc_140050D3B
0x140050cf0  mov     rcx, cs:WPP_GLOBAL_Control
0x140050cf7  lea     rdi, WPP_GLOBAL_Control
0x140050cfe  cmp     rcx, rdi
0x140050d01  jz      loc_140050E46
0x140050d07  test    byte ptr [rcx+1Ch], 1
0x140050d0b  jz      loc_140050E26
0x140050d11  call    cs:__imp_GetLastError
0x140050d17  mov     rcx, cs:WPP_GLOBAL_Control
0x140050d1e  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x140050d25  mov     edx, 0ABh
0x140050d2a  mov     r9d, eax
0x140050d2d  mov     rcx, [rcx+10h]
0x140050d31  call    WPP_SF_d
0x140050d36  jmp     loc_140050E1F
0x140050d3b  mov     r8d, 10h; dwDesiredAccess
0x140050d41  lea     rdx, ServiceName; "Ipt"
0x140050d48  mov     rcx, r14; hSCManager
0x140050d4b  call    cs:__imp_OpenServiceW
0x140050d51  mov     rbp, rax
0x140050d54  test    rax, rax
0x140050d57  jnz     short loc_140050DA3
0x140050d59  xor     esi, esi
0x140050d5b  mov     rax, cs:WPP_GLOBAL_Control
0x140050d62  lea     rdi, WPP_GLOBAL_Control
0x140050d69  cmp     rax, rdi
0x140050d6c  jz      loc_140050E12
0x140050d72  test    byte ptr [rax+1Ch], 4
0x140050d76  jz      loc_140050E12
0x140050d7c  call    cs:__imp_GetLastError
0x140050d82  mov     rcx, cs:WPP_GLOBAL_Control
0x140050d89  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x140050d90  mov     edx, 0ACh
0x140050d95  mov     r9d, eax
0x140050d98  mov     rcx, [rcx+10h]
0x140050d9c  call    WPP_SF_d
0x140050da1  jmp     short loc_140050E12
0x140050da3  xor     r8d, r8d; lpServiceArgVectors
0x140050da6  xor     edx, edx; dwNumServiceArgs
0x140050da8  mov     rcx, rbp; hService
0x140050dab  call    cs:__imp_StartServiceW
0x140050db1  lea     rdi, WPP_GLOBAL_Control
0x140050db8  mov     esi, eax
0x140050dba  test    eax, eax
0x140050dbc  jnz     short loc_140050E09
0x140050dbe  call    cs:__imp_GetLastError
0x140050dc4  cmp     eax, 420h
0x140050dc9  jnz     short loc_140050DD2
0x140050dcb  mov     esi, 1
0x140050dd0  jmp     short loc_140050E09
0x140050dd2  mov     rax, cs:WPP_GLOBAL_Control
0x140050dd9  cmp     rax, rdi
0x140050ddc  jz      short loc_140050E09
0x140050dde  test    byte ptr [rax+1Ch], 4
0x140050de2  jz      short loc_140050E09
0x140050de4  call    cs:__imp_GetLastError
0x140050dea  mov     rcx, cs:WPP_GLOBAL_Control
0x140050df1  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x140050df8  mov     edx, 0ADh
0x140050dfd  mov     r9d, eax
0x140050e00  mov     rcx, [rcx+10h]
0x140050e04  call    WPP_SF_d
0x140050e09  mov     rcx, rbp; hSCObject
0x140050e0c  call    cs:__imp_CloseServiceHandle
0x140050e12  mov     rcx, r14; hSCObject
0x140050e15  call    cs:__imp_CloseServiceHandle
0x140050e1b  test    esi, esi
0x140050e1d  jnz     short loc_140050E50
0x140050e1f  mov     rcx, cs:WPP_GLOBAL_Control
0x140050e26  cmp     rcx, rdi
0x140050e29  jz      short loc_140050E46
0x140050e2b  test    byte ptr [rcx+1Ch], 1
0x140050e2f  jz      short loc_140050E46
0x140050e31  mov     rcx, [rcx+10h]
0x140050e35  lea     r8, WPP_3229bad3034f32dffa4581e190add958_Traceguids
0x140050e3c  mov     edx, 17h
0x140050e41  call    WPP_SF_
0x140050e46  mov     eax, 80004005h
0x140050e4b  jmp     loc_140050EDD
0x140050e50  mov     rcx, rbx; this
0x140050e53  call    ?PrepareIptSettings@CIptPlugin@@AEAAXXZ; CIptPlugin::PrepareIptSettings(void)
0x140050e58  cmp     byte ptr [rbx+0B40h], 0
0x140050e5f  jnz     short loc_140050EBC
0x140050e61  mov     rdx, [rbx+0B28h]; SourceString
0x140050e68  xor     edi, edi
0x140050e6a  test    rdx, rdx
0x140050e6d  jz      short loc_140050E7F
0x140050e6f  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x140050e74  call    cs:__imp_RtlInitUnicodeString
0x140050e7a  lea     rdi, [rsp+78h+DestinationString]
0x140050e7f  mov     rdx, [rbx+0B20h]; SourceString
0x140050e86  lea     rcx, [rsp+78h+var_38]; DestinationString
0x140050e8b  call    cs:__imp_RtlInitUnicodeString
0x140050e91  imul    eax, [rbx+0B3Ch], 15180h
0x140050e9b  lea     rcx, [rsp+78h+var_38]
0x140050ea0  mov     r9d, [rbx+0B38h]
0x140050ea7  mov     rdx, rdi
0x140050eaa  mov     r8, [rbx+0B30h]
0x140050eb1  mov     [rsp+78h+var_58], eax
0x140050eb5  call    RegisterExtendedImageForIptTracing
0x140050eba  jmp     short loc_140050ED9
0x140050ebc  imul    r8d, [rbx+0B3Ch], 15180h
0x140050ec7  mov     edx, [rbx+0B38h]
0x140050ecd  mov     rcx, [rbx+0B30h]
0x140050ed4  call    StartCoreIptTracing
0x140050ed9  bts     eax, 1Ch
0x140050edd  add     rsp, 50h
0x140050ee1  pop     r14
0x140050ee3  pop     rdi
0x140050ee4  pop     rsi
0x140050ee5  pop     rbp
0x140050ee6  pop     rbx
0x140050ee7  retn
```
