# CallerIdentity::GetProcessAppId(void *,ushort * *)

- ea: `0x18005cdb8`
- end: `0x18005cf3d`
- name: `?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z`
- size: `389`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, void *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005cbbc`

## callees

- `0x18001e798`
- `0x18002ad4c`
- `0x18002ae5c`
- `0x18002afb4`
- `0x180053cdc`
- `0x18005caf4`
- `0x18005cdb8`
- `0x18005cf70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ce9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ced6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005cf1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ce9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ced6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005cf1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ce1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ce1c`

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
  ARI::ProcessToken::SysAppId *v19[2]; // [rsp+30h] [rbp-10h] BYREF
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
0x18005cdb8  mov     [rsp-18h+arg_0], rbx
0x18005cdbd  push    rbp
0x18005cdbe  push    rsi
0x18005cdbf  push    rdi
0x18005cdc0  mov     rbp, rsp
0x18005cdc3  sub     rsp, 40h
0x18005cdc7  mov     rbx, rcx
0x18005cdca  mov     qword ptr [rdx], 0
0x18005cdd1  xorps   xmm0, xmm0
0x18005cdd4  lea     rcx, [rbp+var_10]; this
0x18005cdd8  movdqu  xmmword ptr [rbp+var_10], xmm0
0x18005cddd  mov     rsi, rdx
0x18005cde0  call    ?Close@AutoSysAppId@ProcessToken@ARI@@QEAAJXZ; ARI::ProcessToken::AutoSysAppId::Close(void)
0x18005cde5  lea     rdx, [rbp+hObject]; TokenHandle
0x18005cde9  mov     [rbp+hObject], 0
0x18005cdf1  mov     rcx, rbx; ProcessHandle
0x18005cdf4  call    ?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z; ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)
0x18005cdf9  mov     edi, eax
0x18005cdfb  test    eax, eax
0x18005cdfd  jnz     short loc_18005CE22
0x18005cdff  mov     rcx, [rbp+hObject]; TokenHandle
0x18005ce03  lea     r8, [rbp+var_10+8]; struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **
0x18005ce07  lea     rdx, [rbp+var_10]; void *
0x18005ce0b  call    ?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z; ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)
0x18005ce10  mov     rcx, [rbp+hObject]; hObject
0x18005ce14  mov     edi, eax
0x18005ce16  cmp     rcx, 0FFFFFFFFFFFFFFFCh
0x18005ce1a  jz      short loc_18005CE22
0x18005ce1c  call    cs:__imp_CloseHandle
0x18005ce22  test    edi, edi
0x18005ce24  jle     short loc_18005CE2F
0x18005ce26  movzx   edi, di
0x18005ce29  or      edi, 80070000h
0x18005ce2f  cmp     edi, 80070490h
0x18005ce35  jz      loc_18005CF25
0x18005ce3b  cmp     edi, 80070005h
0x18005ce41  jz      loc_18005CF25
0x18005ce47  test    edi, edi
0x18005ce49  jns     short loc_18005CE52
0x18005ce4b  mov     edx, 0A5h
0x18005ce50  jmp     short loc_18005CE7A
0x18005ce52  mov     rcx, [rbp+var_10+8]; this
0x18005ce56  lea     r8, [rbp+hObject]; unsigned int
0x18005ce5a  xor     r9d, r9d; unsigned int *
0x18005ce5d  mov     dword ptr [rbp+hObject], 0
0x18005ce64  xor     edx, edx; struct _TOKEN_SECURITY_ATTRIBUTE_V1 *
0x18005ce66  call    ?GetAppUserModelId@SysAppId@ProcessToken@ARI@@YAJPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@IPEAIPEAG@Z; ARI::ProcessToken::SysAppId::GetAppUserModelId(_TOKEN_SECURITY_ATTRIBUTE_V1 const *,uint,uint *,ushort *)
0x18005ce6b  cmp     eax, 7Ah ; 'z'
0x18005ce6e  jz      short loc_18005CE92
0x18005ce70  mov     edi, 8000FFFFh
0x18005ce75  mov     edx, 0A8h; void *
0x18005ce7a  mov     rcx, [rbp+18h]; this
0x18005ce7e  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x18005ce85  mov     r9d, edi; char *
0x18005ce88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ce8d  jmp     loc_18005CF25
0x18005ce92  xor     ecx, ecx; pv
0x18005ce94  mov     [rbp+pv], 0
0x18005ce9c  call    cs:__imp_CoTaskMemFree
0x18005cea2  mov     r9d, dword ptr [rbp+hObject]
0x18005cea6  lea     rax, [rbp+pv]
0x18005ceaa  mov     [rsp+40h+var_18], rax
0x18005ceaf  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18005ceb4  mov     edi, eax
0x18005ceb6  test    eax, eax
0x18005ceb8  jns     short loc_18005CEDE
0x18005ceba  mov     rcx, [rbp+18h]; this
0x18005cebe  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x18005cec5  mov     r9d, eax; char *
0x18005cec8  mov     edx, 0ABh; void *
0x18005cecd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ced2  mov     rcx, [rbp+pv]; pv
0x18005ced6  call    cs:__imp_CoTaskMemFree
0x18005cedc  jmp     short loc_18005CF25
0x18005cede  mov     rbx, [rbp+pv]
0x18005cee2  lea     r8, [rbp+hObject]; unsigned int
0x18005cee6  mov     edx, dword ptr [rbp+hObject]; struct _TOKEN_SECURITY_ATTRIBUTE_V1 *
0x18005cee9  mov     r9, rbx; unsigned int *
0x18005ceec  mov     rcx, [rbp+var_10+8]; this
0x18005cef0  call    ?GetAppUserModelId@SysAppId@ProcessToken@ARI@@YAJPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@IPEAIPEAG@Z; ARI::ProcessToken::SysAppId::GetAppUserModelId(_TOKEN_SECURITY_ATTRIBUTE_V1 const *,uint,uint *,ushort *)
0x18005cef5  test    eax, eax
0x18005cef7  jz      short loc_18005CF18
0x18005cef9  mov     rcx, [rbp+18h]; this
0x18005cefd  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x18005cf04  mov     r9d, eax; char *
0x18005cf07  mov     edx, 0ACh; void *
0x18005cf0c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005cf11  mov     edi, eax
0x18005cf13  mov     rcx, rbx
0x18005cf16  jmp     short loc_18005CED6
0x18005cf18  xor     ecx, ecx; pv
0x18005cf1a  mov     [rsi], rbx
0x18005cf1d  call    cs:__imp_CoTaskMemFree
0x18005cf23  xor     edi, edi
0x18005cf25  lea     rcx, [rbp+var_10]; this
0x18005cf29  call    ?Close@AutoSysAppId@ProcessToken@ARI@@QEAAJXZ; ARI::ProcessToken::AutoSysAppId::Close(void)
0x18005cf2e  mov     rbx, [rsp+40h+arg_0]
0x18005cf33  mov     eax, edi
0x18005cf35  add     rsp, 40h
0x18005cf39  pop     rdi
0x18005cf3a  pop     rsi
0x18005cf3b  pop     rbp
0x18005cf3c  retn
```
