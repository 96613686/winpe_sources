# CallerIdentity::GetProcessAppId(void *,ushort * *)

- ea: `0x1801af740`
- end: `0x1801af8c8`
- name: `?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z`
- size: `392`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, void *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800f93b0`

## callees

- `0x1800620a0`
- `0x180098cb8`
- `0x1800c8458`
- `0x1800ff298`
- `0x1801af4dc`
- `0x1801af53c`
- `0x1801af740`
- `0x1801af8d0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801af7a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801af7a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801af824`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801af861`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801af8a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801af824`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801af861`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801af8a8`

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
  int v11; // eax
  void *v12; // rcx
  LPVOID v13; // rbx
  unsigned int AppUserModelId; // eax
  unsigned __int16 *v16; // [rsp+20h] [rbp-20h]
  unsigned __int16 *v17; // [rsp+20h] [rbp-20h]
  unsigned int v18; // [rsp+20h] [rbp-20h]
  struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *v19[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  HANDLE hObject; // [rsp+68h] [rbp+28h] BYREF
  LPVOID pv; // [rsp+70h] [rbp+30h] BYREF

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
        (int)v16);
      goto LABEL_19;
    }
    LODWORD(hObject) = 0;
    if ( (unsigned int)ARI::ProcessToken::SysAppId::GetAppUserModelId(v19[1], 0, (unsigned int)&hObject, 0, v16) != 122 )
    {
      v6 = -2147418113;
      v8 = 168;
      goto LABEL_12;
    }
    pv = 0;
    CoTaskMemFree(0);
    v11 = _AllocStringWorker<CTCoAllocPolicy>(v10, v9, 0, (unsigned int)hObject, (__int64)v16, &pv);
    v6 = v11;
    if ( v11 >= 0 )
    {
      v13 = pv;
      AppUserModelId = ARI::ProcessToken::SysAppId::GetAppUserModelId(
                         v19[1],
                         (const struct _TOKEN_SECURITY_ATTRIBUTE_V1 *)(unsigned int)hObject,
                         (unsigned int)&hObject,
                         (unsigned int *)pv,
                         v17);
      if ( !AppUserModelId )
      {
        *a2 = v13;
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
      v12 = v13;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAB,
        (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
        (const char *)(unsigned int)v11,
        (int)v17);
      v12 = pv;
    }
    CoTaskMemFree(v12);
  }
LABEL_19:
  ARI::ProcessToken::AutoSysAppId::Close((ARI::ProcessToken::AutoSysAppId *)v19);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801af740  mov     [rsp-18h+arg_0], rbx
0x1801af745  push    rbp
0x1801af746  push    rsi
0x1801af747  push    rdi
0x1801af748  mov     rbp, rsp
0x1801af74b  sub     rsp, 40h
0x1801af74f  mov     rbx, rcx
0x1801af752  mov     qword ptr [rdx], 0
0x1801af759  xorps   xmm0, xmm0
0x1801af75c  lea     rcx, [rbp+var_10]; this
0x1801af760  movdqu  xmmword ptr [rbp+var_10], xmm0
0x1801af765  mov     rsi, rdx
0x1801af768  call    ?Close@AutoSysAppId@ProcessToken@ARI@@QEAAJXZ; ARI::ProcessToken::AutoSysAppId::Close(void)
0x1801af76d  lea     rdx, [rbp+hObject]; TokenHandle
0x1801af771  mov     [rbp+hObject], 0
0x1801af779  mov     rcx, rbx; ProcessHandle
0x1801af77c  call    ?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z; ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)
0x1801af781  mov     edi, eax
0x1801af783  test    eax, eax
0x1801af785  jnz     short loc_1801AF7AA
0x1801af787  mov     rcx, [rbp+hObject]; TokenHandle
0x1801af78b  lea     r8, [rbp+var_10+8]; struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **
0x1801af78f  lea     rdx, [rbp+var_10]; void *
0x1801af793  call    ?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z; ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)
0x1801af798  mov     rcx, [rbp+hObject]; hObject
0x1801af79c  mov     edi, eax
0x1801af79e  cmp     rcx, 0FFFFFFFFFFFFFFFCh
0x1801af7a2  jz      short loc_1801AF7AA
0x1801af7a4  call    cs:__imp_CloseHandle
0x1801af7aa  test    edi, edi
0x1801af7ac  jle     short loc_1801AF7B7
0x1801af7ae  movzx   edi, di
0x1801af7b1  or      edi, 80070000h
0x1801af7b7  cmp     edi, 80070490h
0x1801af7bd  jz      loc_1801AF8B0
0x1801af7c3  cmp     edi, 80070005h
0x1801af7c9  jz      loc_1801AF8B0
0x1801af7cf  test    edi, edi
0x1801af7d1  jns     short loc_1801AF7DA
0x1801af7d3  mov     edx, 0A5h
0x1801af7d8  jmp     short loc_1801AF802
0x1801af7da  mov     rcx, [rbp+var_10+8]; this
0x1801af7de  lea     r8, [rbp+hObject]; unsigned int
0x1801af7e2  xor     r9d, r9d; unsigned int *
0x1801af7e5  mov     dword ptr [rbp+hObject], 0
0x1801af7ec  xor     edx, edx; struct _TOKEN_SECURITY_ATTRIBUTE_V1 *
0x1801af7ee  call    ?GetAppUserModelId@SysAppId@ProcessToken@ARI@@YAJPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@IPEAIPEAG@Z; ARI::ProcessToken::SysAppId::GetAppUserModelId(_TOKEN_SECURITY_ATTRIBUTE_V1 const *,uint,uint *,ushort *)
0x1801af7f3  cmp     eax, 7Ah ; 'z'
0x1801af7f6  jz      short loc_1801AF81A
0x1801af7f8  mov     edi, 8000FFFFh
0x1801af7fd  mov     edx, 0A8h; void *
0x1801af802  mov     rcx, [rbp+18h]; this
0x1801af806  lea     r8, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x1801af80d  mov     r9d, edi; char *
0x1801af810  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801af815  jmp     loc_1801AF8B0
0x1801af81a  xor     ecx, ecx; pv
0x1801af81c  mov     [rbp+pv], 0
0x1801af824  call    cs:__imp_CoTaskMemFree
0x1801af82a  mov     r9d, dword ptr [rbp+hObject]
0x1801af82e  lea     rax, [rbp+pv]
0x1801af832  xor     r8d, r8d
0x1801af835  mov     [rsp+40h+var_18], rax
0x1801af83a  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1801af83f  mov     edi, eax
0x1801af841  test    eax, eax
0x1801af843  jns     short loc_1801AF869
0x1801af845  mov     rcx, [rbp+18h]; this
0x1801af849  lea     r8, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x1801af850  mov     r9d, eax; char *
0x1801af853  mov     edx, 0ABh; void *
0x1801af858  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801af85d  mov     rcx, [rbp+pv]; pv
0x1801af861  call    cs:__imp_CoTaskMemFree
0x1801af867  jmp     short loc_1801AF8B0
0x1801af869  mov     rbx, [rbp+pv]
0x1801af86d  lea     r8, [rbp+hObject]; unsigned int
0x1801af871  mov     edx, dword ptr [rbp+hObject]; struct _TOKEN_SECURITY_ATTRIBUTE_V1 *
0x1801af874  mov     r9, rbx; unsigned int *
0x1801af877  mov     rcx, [rbp+var_10+8]; this
0x1801af87b  call    ?GetAppUserModelId@SysAppId@ProcessToken@ARI@@YAJPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@IPEAIPEAG@Z; ARI::ProcessToken::SysAppId::GetAppUserModelId(_TOKEN_SECURITY_ATTRIBUTE_V1 const *,uint,uint *,ushort *)
0x1801af880  test    eax, eax
0x1801af882  jz      short loc_1801AF8A3
0x1801af884  mov     rcx, [rbp+18h]; this
0x1801af888  lea     r8, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x1801af88f  mov     r9d, eax; char *
0x1801af892  mov     edx, 0ACh; void *
0x1801af897  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801af89c  mov     edi, eax
0x1801af89e  mov     rcx, rbx
0x1801af8a1  jmp     short loc_1801AF861
0x1801af8a3  xor     ecx, ecx; pv
0x1801af8a5  mov     [rsi], rbx
0x1801af8a8  call    cs:__imp_CoTaskMemFree
0x1801af8ae  xor     edi, edi
0x1801af8b0  lea     rcx, [rbp+var_10]; this
0x1801af8b4  call    ?Close@AutoSysAppId@ProcessToken@ARI@@QEAAJXZ; ARI::ProcessToken::AutoSysAppId::Close(void)
0x1801af8b9  mov     rbx, [rsp+40h+arg_0]
0x1801af8be  mov     eax, edi
0x1801af8c0  add     rsp, 40h
0x1801af8c4  pop     rdi
0x1801af8c5  pop     rsi
0x1801af8c6  pop     rbp
0x1801af8c7  retn
```
