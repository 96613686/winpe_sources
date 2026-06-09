# CallerIdentity::GetProcessAppId(void *,ushort * *)

- ea: `0x180056464`
- end: `0x1800565e9`
- name: `?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z`
- size: `389`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, void *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180055dd0`

## callees

- `0x180015f40`
- `0x180049dd4`
- `0x180055f4c`
- `0x180055fd8`
- `0x180056038`
- `0x180056190`
- `0x180056300`
- `0x180056464`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056548`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056582`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800565c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056548`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056582`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800565c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800564c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800564c8`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetProcessAppId(HANDLE ProcessHandle, _QWORD *a2, unsigned __int16 **a3)
{
  void **v5; // r8
  signed int v6; // edi
  const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  int v12; // eax
  void *v13; // rcx
  LPVOID v14; // rbx
  unsigned int AppUserModelId; // eax
  unsigned __int16 *v17; // [rsp+20h] [rbp-20h]
  unsigned int v18; // [rsp+20h] [rbp-20h]
  struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *v19[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  HANDLE hObject; // [rsp+68h] [rbp+28h] BYREF
  LPVOID pv; // [rsp+70h] [rbp+30h]

  *a2 = 0;
  *(_OWORD *)v19 = 0;
  ARI::ProcessToken::AutoSysAppId::Close((ARI::ProcessToken::AutoSysAppId *)v19);
  hObject = 0;
  v6 = ARI::ProcessToken::SysAppId::OpenTokenForProcess(ProcessHandle, &hObject, v5);
  if ( !v6 )
  {
    v6 = ARI::ProcessToken::SysAppId::Open(hObject, v19, &v19[1], v7);
    if ( hObject != (HANDLE)-4LL )
      CloseHandle(hObject);
  }
  if ( v6 > 0 )
    v6 = (unsigned __int16)v6 | 0x80070000;
  if ( v6 != -2147023728 && v6 != -2147024891 )
  {
    if ( v6 < 0 )
    {
      v8 = 165;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
        (const char *)(unsigned int)v6,
        (int)v17);
      goto LABEL_19;
    }
    LODWORD(hObject) = 0;
    if ( (unsigned int)ARI::ProcessToken::SysAppId::GetAppUserModelId(v19[1], 0, (unsigned int)&hObject, 0, v17) != 122 )
    {
      v6 = -2147418113;
      v8 = 168;
      goto LABEL_12;
    }
    pv = 0;
    CoTaskMemFree(0);
    v12 = _AllocStringWorker<CTCoAllocPolicy>(v10, v9, v11, (unsigned int)hObject);
    v6 = v12;
    if ( v12 >= 0 )
    {
      v14 = pv;
      AppUserModelId = ARI::ProcessToken::SysAppId::GetAppUserModelId(
                         v19[1],
                         (const struct _TOKEN_SECURITY_ATTRIBUTE_V1 *)(unsigned int)hObject,
                         (unsigned int)&hObject,
                         (unsigned int *)pv,
                         v17);
      if ( !AppUserModelId )
      {
        *a2 = v14;
        CoTaskMemFree(0);
        v6 = 0;
        goto LABEL_19;
      }
      v6 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xAC,
             (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
             (const char *)AppUserModelId,
             v18);
      v13 = v14;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAB,
        (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
        (const char *)(unsigned int)v12,
        (int)v17);
      v13 = pv;
    }
    CoTaskMemFree(v13);
  }
LABEL_19:
  ARI::ProcessToken::AutoSysAppId::Close((ARI::ProcessToken::AutoSysAppId *)v19);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180056464  mov     [rsp-18h+arg_0], rbx
0x180056469  push    rbp
0x18005646a  push    rsi
0x18005646b  push    rdi
0x18005646c  mov     rbp, rsp
0x18005646f  sub     rsp, 40h
0x180056473  mov     rbx, rcx
0x180056476  mov     qword ptr [rdx], 0
0x18005647d  xorps   xmm0, xmm0
0x180056480  lea     rcx, [rbp+var_10]; this
0x180056484  movdqu  xmmword ptr [rbp+var_10], xmm0
0x180056489  mov     rsi, rdx
0x18005648c  call    ?Close@AutoSysAppId@ProcessToken@ARI@@QEAAJXZ; ARI::ProcessToken::AutoSysAppId::Close(void)
0x180056491  lea     rdx, [rbp+hObject]; TokenHandle
0x180056495  mov     [rbp+hObject], 0
0x18005649d  mov     rcx, rbx; ProcessHandle
0x1800564a0  call    ?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z; ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)
0x1800564a5  mov     edi, eax
0x1800564a7  test    eax, eax
0x1800564a9  jnz     short loc_1800564CE
0x1800564ab  mov     rcx, [rbp+hObject]; TokenHandle
0x1800564af  lea     r8, [rbp+var_10+8]; struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **
0x1800564b3  lea     rdx, [rbp+var_10]; void *
0x1800564b7  call    ?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z; ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)
0x1800564bc  mov     rcx, [rbp+hObject]; hObject
0x1800564c0  mov     edi, eax
0x1800564c2  cmp     rcx, 0FFFFFFFFFFFFFFFCh
0x1800564c6  jz      short loc_1800564CE
0x1800564c8  call    cs:__imp_CloseHandle
0x1800564ce  test    edi, edi
0x1800564d0  jle     short loc_1800564DB
0x1800564d2  movzx   edi, di
0x1800564d5  or      edi, 80070000h
0x1800564db  cmp     edi, 80070490h
0x1800564e1  jz      loc_1800565D1
0x1800564e7  cmp     edi, 80070005h
0x1800564ed  jz      loc_1800565D1
0x1800564f3  test    edi, edi
0x1800564f5  jns     short loc_1800564FE
0x1800564f7  mov     edx, 0A5h
0x1800564fc  jmp     short loc_180056526
0x1800564fe  mov     rcx, [rbp+var_10+8]; this
0x180056502  lea     r8, [rbp+hObject]; unsigned int
0x180056506  xor     r9d, r9d; unsigned int *
0x180056509  mov     dword ptr [rbp+hObject], 0
0x180056510  xor     edx, edx; struct _TOKEN_SECURITY_ATTRIBUTE_V1 *
0x180056512  call    ?GetAppUserModelId@SysAppId@ProcessToken@ARI@@YAJPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@IPEAIPEAG@Z; ARI::ProcessToken::SysAppId::GetAppUserModelId(_TOKEN_SECURITY_ATTRIBUTE_V1 const *,uint,uint *,ushort *)
0x180056517  cmp     eax, 7Ah ; 'z'
0x18005651a  jz      short loc_18005653E
0x18005651c  mov     edi, 8000FFFFh
0x180056521  mov     edx, 0A8h; void *
0x180056526  mov     rcx, [rbp+18h]; this
0x18005652a  lea     r8, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180056531  mov     r9d, edi; char *
0x180056534  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180056539  jmp     loc_1800565D1
0x18005653e  xor     ecx, ecx; pv
0x180056540  mov     [rbp+pv], 0
0x180056548  call    cs:__imp_CoTaskMemFree
0x18005654e  mov     r9d, dword ptr [rbp+hObject]
0x180056552  lea     rax, [rbp+pv]
0x180056556  mov     [rsp+40h+var_18], rax
0x18005655b  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180056560  mov     edi, eax
0x180056562  test    eax, eax
0x180056564  jns     short loc_18005658A
0x180056566  mov     rcx, [rbp+18h]; this
0x18005656a  lea     r8, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180056571  mov     r9d, eax; char *
0x180056574  mov     edx, 0ABh; void *
0x180056579  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005657e  mov     rcx, [rbp+pv]; pv
0x180056582  call    cs:__imp_CoTaskMemFree
0x180056588  jmp     short loc_1800565D1
0x18005658a  mov     rbx, [rbp+pv]
0x18005658e  lea     r8, [rbp+hObject]; unsigned int
0x180056592  mov     edx, dword ptr [rbp+hObject]; struct _TOKEN_SECURITY_ATTRIBUTE_V1 *
0x180056595  mov     r9, rbx; unsigned int *
0x180056598  mov     rcx, [rbp+var_10+8]; this
0x18005659c  call    ?GetAppUserModelId@SysAppId@ProcessToken@ARI@@YAJPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@IPEAIPEAG@Z; ARI::ProcessToken::SysAppId::GetAppUserModelId(_TOKEN_SECURITY_ATTRIBUTE_V1 const *,uint,uint *,ushort *)
0x1800565a1  test    eax, eax
0x1800565a3  jz      short loc_1800565C4
0x1800565a5  mov     rcx, [rbp+18h]; this
0x1800565a9  lea     r8, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x1800565b0  mov     r9d, eax; char *
0x1800565b3  mov     edx, 0ACh; void *
0x1800565b8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800565bd  mov     edi, eax
0x1800565bf  mov     rcx, rbx
0x1800565c2  jmp     short loc_180056582
0x1800565c4  xor     ecx, ecx; pv
0x1800565c6  mov     [rsi], rbx
0x1800565c9  call    cs:__imp_CoTaskMemFree
0x1800565cf  xor     edi, edi
0x1800565d1  lea     rcx, [rbp+var_10]; this
0x1800565d5  call    ?Close@AutoSysAppId@ProcessToken@ARI@@QEAAJXZ; ARI::ProcessToken::AutoSysAppId::Close(void)
0x1800565da  mov     rbx, [rsp+40h+arg_0]
0x1800565df  mov     eax, edi
0x1800565e1  add     rsp, 40h
0x1800565e5  pop     rdi
0x1800565e6  pop     rsi
0x1800565e7  pop     rbp
0x1800565e8  retn
```
