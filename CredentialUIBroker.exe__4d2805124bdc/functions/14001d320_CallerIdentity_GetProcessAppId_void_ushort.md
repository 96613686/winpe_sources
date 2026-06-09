# CallerIdentity::GetProcessAppId(void *,ushort * *)

- ea: `0x14001d320`
- end: `0x14001d4a8`
- name: `?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z`
- size: `392`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, _QWORD *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14001d730`
- `0x14001dadc`

## callees

- `0x140007218`
- `0x1400136fc`
- `0x140013720`
- `0x14001d07c`
- `0x14001d0dc`
- `0x14001d320`
- `0x14001d568`
- `0x14001d6c0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001d384`
- `KERNEL32!CloseHandle` at `0x14001d384`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001d404`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001d441`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001d488`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001d404`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001d441`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001d488`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetProcessAppId(HANDLE ProcessHandle, _QWORD *a2, unsigned __int16 **a3)
{
  void **v5; // r8
  void *v6; // rdx
  signed int v7; // edi
  const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // eax
  void *v13; // rcx
  LPVOID v14; // rbx
  unsigned int AppUserModelId; // eax
  bool *v17; // [rsp+20h] [rbp-20h]
  struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *v18[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  HANDLE hObject; // [rsp+68h] [rbp+28h] BYREF
  LPVOID pv; // [rsp+70h] [rbp+30h]

  *a2 = 0;
  *(_OWORD *)v18 = 0;
  ARI::ProcessToken::AutoSysAppId::Close((ARI::ProcessToken::AutoSysAppId *)v18, a2);
  hObject = 0;
  v7 = ARI::ProcessToken::SysAppId::OpenTokenForProcess(ProcessHandle, &hObject, v5);
  if ( !v7 )
  {
    v7 = ARI::ProcessToken::SysAppId::Open(hObject, v18, &v18[1], v8, v17);
    if ( hObject != (HANDLE)-4LL )
      CloseHandle(hObject);
  }
  if ( v7 > 0 )
    v7 = (unsigned __int16)v7 | 0x80070000;
  if ( v7 != -2147023728 && v7 != -2147024891 )
  {
    if ( v7 < 0 )
    {
      v9 = 165;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
        (const char *)(unsigned int)v7,
        (int)v17);
      goto LABEL_19;
    }
    LODWORD(hObject) = 0;
    if ( ARI::ProcessToken::SysAppId::GetAppUserModelId(v18[1], 0, &hObject, 0) != 122 )
    {
      v7 = -2147418113;
      v9 = 168;
      goto LABEL_12;
    }
    pv = 0;
    CoTaskMemFree(0);
    v12 = _AllocStringWorker<CTCoAllocPolicy>(v11, v10, 0);
    v7 = v12;
    if ( v12 >= 0 )
    {
      v14 = pv;
      AppUserModelId = ARI::ProcessToken::SysAppId::GetAppUserModelId(
                         v18[1],
                         (const struct _TOKEN_SECURITY_ATTRIBUTE_V1 *)(unsigned int)hObject,
                         &hObject,
                         (unsigned int *)pv);
      if ( !AppUserModelId )
      {
        *a2 = v14;
        CoTaskMemFree(0);
        v7 = 0;
        goto LABEL_19;
      }
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xAC,
             (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
             (const char *)AppUserModelId,
             (unsigned int)v17);
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
  ARI::ProcessToken::AutoSysAppId::Close((ARI::ProcessToken::AutoSysAppId *)v18, v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14001d320  mov     [rsp-18h+arg_0], rbx
0x14001d325  push    rbp
0x14001d326  push    rsi
0x14001d327  push    rdi
0x14001d328  mov     rbp, rsp
0x14001d32b  sub     rsp, 40h
0x14001d32f  mov     rbx, rcx
0x14001d332  mov     qword ptr [rdx], 0
0x14001d339  xorps   xmm0, xmm0
0x14001d33c  lea     rcx, [rbp+var_10]; this
0x14001d340  movdqu  xmmword ptr [rbp+var_10], xmm0
0x14001d345  mov     rsi, rdx
0x14001d348  call    ?Close@AutoSysAppId@ProcessToken@ARI@@QEAAJXZ; ARI::ProcessToken::AutoSysAppId::Close(void)
0x14001d34d  lea     rdx, [rbp+hObject]; TokenHandle
0x14001d351  mov     [rbp+hObject], 0
0x14001d359  mov     rcx, rbx; ProcessHandle
0x14001d35c  call    ?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z; ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)
0x14001d361  mov     edi, eax
0x14001d363  test    eax, eax
0x14001d365  jnz     short loc_14001D38A
0x14001d367  mov     rcx, [rbp+hObject]; TokenHandle
0x14001d36b  lea     r8, [rbp+var_10+8]; struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **
0x14001d36f  lea     rdx, [rbp+var_10]; void *
0x14001d373  call    ?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z; ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)
0x14001d378  mov     rcx, [rbp+hObject]; hObject
0x14001d37c  mov     edi, eax
0x14001d37e  cmp     rcx, 0FFFFFFFFFFFFFFFCh
0x14001d382  jz      short loc_14001D38A
0x14001d384  call    cs:__imp_CloseHandle
0x14001d38a  test    edi, edi
0x14001d38c  jle     short loc_14001D397
0x14001d38e  movzx   edi, di
0x14001d391  or      edi, 80070000h
0x14001d397  cmp     edi, 80070490h
0x14001d39d  jz      loc_14001D490
0x14001d3a3  cmp     edi, 80070005h
0x14001d3a9  jz      loc_14001D490
0x14001d3af  test    edi, edi
0x14001d3b1  jns     short loc_14001D3BA
0x14001d3b3  mov     edx, 0A5h
0x14001d3b8  jmp     short loc_14001D3E2
0x14001d3ba  mov     rcx, [rbp+var_10+8]; this
0x14001d3be  lea     r8, [rbp+hObject]; unsigned int
0x14001d3c2  xor     r9d, r9d; unsigned int *
0x14001d3c5  mov     dword ptr [rbp+hObject], 0
0x14001d3cc  xor     edx, edx; struct _TOKEN_SECURITY_ATTRIBUTE_V1 *
0x14001d3ce  call    ?GetAppUserModelId@SysAppId@ProcessToken@ARI@@YAJPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@IPEAIPEAG@Z; ARI::ProcessToken::SysAppId::GetAppUserModelId(_TOKEN_SECURITY_ATTRIBUTE_V1 const *,uint,uint *,ushort *)
0x14001d3d3  cmp     eax, 7Ah ; 'z'
0x14001d3d6  jz      short loc_14001D3FA
0x14001d3d8  mov     edi, 8000FFFFh
0x14001d3dd  mov     edx, 0A8h; void *
0x14001d3e2  mov     rcx, [rbp+18h]; this
0x14001d3e6  lea     r8, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x14001d3ed  mov     r9d, edi; char *
0x14001d3f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001d3f5  jmp     loc_14001D490
0x14001d3fa  xor     ecx, ecx; pv
0x14001d3fc  mov     [rbp+pv], 0
0x14001d404  call    cs:__imp_CoTaskMemFree
0x14001d40a  mov     r9d, dword ptr [rbp+hObject]
0x14001d40e  lea     rax, [rbp+pv]
0x14001d412  xor     r8d, r8d
0x14001d415  mov     [rsp+40h+var_18], rax
0x14001d41a  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x14001d41f  mov     edi, eax
0x14001d421  test    eax, eax
0x14001d423  jns     short loc_14001D449
0x14001d425  mov     rcx, [rbp+18h]; this
0x14001d429  lea     r8, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x14001d430  mov     r9d, eax; char *
0x14001d433  mov     edx, 0ABh; void *
0x14001d438  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001d43d  mov     rcx, [rbp+pv]; pv
0x14001d441  call    cs:__imp_CoTaskMemFree
0x14001d447  jmp     short loc_14001D490
0x14001d449  mov     rbx, [rbp+pv]
0x14001d44d  lea     r8, [rbp+hObject]; unsigned int
0x14001d451  mov     edx, dword ptr [rbp+hObject]; struct _TOKEN_SECURITY_ATTRIBUTE_V1 *
0x14001d454  mov     r9, rbx; unsigned int *
0x14001d457  mov     rcx, [rbp+var_10+8]; this
0x14001d45b  call    ?GetAppUserModelId@SysAppId@ProcessToken@ARI@@YAJPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@IPEAIPEAG@Z; ARI::ProcessToken::SysAppId::GetAppUserModelId(_TOKEN_SECURITY_ATTRIBUTE_V1 const *,uint,uint *,ushort *)
0x14001d460  test    eax, eax
0x14001d462  jz      short loc_14001D483
0x14001d464  mov     rcx, [rbp+18h]; this
0x14001d468  lea     r8, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x14001d46f  mov     r9d, eax; char *
0x14001d472  mov     edx, 0ACh; void *
0x14001d477  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14001d47c  mov     edi, eax
0x14001d47e  mov     rcx, rbx
0x14001d481  jmp     short loc_14001D441
0x14001d483  xor     ecx, ecx; pv
0x14001d485  mov     [rsi], rbx
0x14001d488  call    cs:__imp_CoTaskMemFree
0x14001d48e  xor     edi, edi
0x14001d490  lea     rcx, [rbp+var_10]; this
0x14001d494  call    ?Close@AutoSysAppId@ProcessToken@ARI@@QEAAJXZ; ARI::ProcessToken::AutoSysAppId::Close(void)
0x14001d499  mov     rbx, [rsp+40h+arg_0]
0x14001d49e  mov     eax, edi
0x14001d4a0  add     rsp, 40h
0x14001d4a4  pop     rdi
0x14001d4a5  pop     rsi
0x14001d4a6  pop     rbp
0x14001d4a7  retn
```
