# CallerIdentity::GetProcessAppId(void *,ushort * *)

- ea: `0x1800d8494`
- end: `0x1800d861c`
- name: `?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z`
- size: `392`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, void *, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003ef78`
- `0x1800754ec`
- `0x1800bae1c`
- `0x1800d81b4`

## callees

- `0x180019bd0`
- `0x180030640`
- `0x180034c6c`
- `0x180034db4`
- `0x18004db70`
- `0x1800d8020`
- `0x1800d8494`
- `0x1800d8624`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d84f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d84f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d8578`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d85b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d85fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d8578`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d85b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d85fc`

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
    v11 = _AllocStringWorker<CTCoAllocPolicy>(v10, v9, 0, (unsigned int)hObject, (int)v16, &pv);
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
0x1800d8494  mov     [rsp-18h+arg_0], rbx
0x1800d8499  push    rbp
0x1800d849a  push    rsi
0x1800d849b  push    rdi
0x1800d849c  mov     rbp, rsp
0x1800d849f  sub     rsp, 40h
0x1800d84a3  mov     rbx, rcx
0x1800d84a6  mov     qword ptr [rdx], 0
0x1800d84ad  xorps   xmm0, xmm0
0x1800d84b0  lea     rcx, [rbp+var_10]; this
0x1800d84b4  movdqu  xmmword ptr [rbp+var_10], xmm0
0x1800d84b9  mov     rsi, rdx
0x1800d84bc  call    ?Close@AutoSysAppId@ProcessToken@ARI@@QEAAJXZ; ARI::ProcessToken::AutoSysAppId::Close(void)
0x1800d84c1  lea     rdx, [rbp+hObject]; TokenHandle
0x1800d84c5  mov     [rbp+hObject], 0
0x1800d84cd  mov     rcx, rbx; ProcessHandle
0x1800d84d0  call    ?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z; ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)
0x1800d84d5  mov     edi, eax
0x1800d84d7  test    eax, eax
0x1800d84d9  jnz     short loc_1800D84FE
0x1800d84db  mov     rcx, [rbp+hObject]; TokenHandle
0x1800d84df  lea     r8, [rbp+var_10+8]; struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **
0x1800d84e3  lea     rdx, [rbp+var_10]; void *
0x1800d84e7  call    ?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z; ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)
0x1800d84ec  mov     rcx, [rbp+hObject]; hObject
0x1800d84f0  mov     edi, eax
0x1800d84f2  cmp     rcx, 0FFFFFFFFFFFFFFFCh
0x1800d84f6  jz      short loc_1800D84FE
0x1800d84f8  call    cs:__imp_CloseHandle
0x1800d84fe  test    edi, edi
0x1800d8500  jle     short loc_1800D850B
0x1800d8502  movzx   edi, di
0x1800d8505  or      edi, 80070000h
0x1800d850b  cmp     edi, 80070490h
0x1800d8511  jz      loc_1800D8604
0x1800d8517  cmp     edi, 80070005h
0x1800d851d  jz      loc_1800D8604
0x1800d8523  test    edi, edi
0x1800d8525  jns     short loc_1800D852E
0x1800d8527  mov     edx, 0A5h
0x1800d852c  jmp     short loc_1800D8556
0x1800d852e  mov     rcx, [rbp+var_10+8]; this
0x1800d8532  lea     r8, [rbp+hObject]; unsigned int
0x1800d8536  xor     r9d, r9d; unsigned int *
0x1800d8539  mov     dword ptr [rbp+hObject], 0
0x1800d8540  xor     edx, edx; struct _TOKEN_SECURITY_ATTRIBUTE_V1 *
0x1800d8542  call    ?GetAppUserModelId@SysAppId@ProcessToken@ARI@@YAJPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@IPEAIPEAG@Z; ARI::ProcessToken::SysAppId::GetAppUserModelId(_TOKEN_SECURITY_ATTRIBUTE_V1 const *,uint,uint *,ushort *)
0x1800d8547  cmp     eax, 7Ah ; 'z'
0x1800d854a  jz      short loc_1800D856E
0x1800d854c  mov     edi, 8000FFFFh
0x1800d8551  mov     edx, 0A8h; void *
0x1800d8556  mov     rcx, [rbp+18h]; this
0x1800d855a  lea     r8, aOnecoreShellLi_2; "onecore\\shell\\lib\\calleridentity\\ca"...
0x1800d8561  mov     r9d, edi; char *
0x1800d8564  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d8569  jmp     loc_1800D8604
0x1800d856e  xor     ecx, ecx; pv
0x1800d8570  mov     [rbp+pv], 0
0x1800d8578  call    cs:__imp_CoTaskMemFree
0x1800d857e  mov     r9d, dword ptr [rbp+hObject]
0x1800d8582  lea     rax, [rbp+pv]
0x1800d8586  xor     r8d, r8d
0x1800d8589  mov     [rsp+40h+var_18], rax
0x1800d858e  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1800d8593  mov     edi, eax
0x1800d8595  test    eax, eax
0x1800d8597  jns     short loc_1800D85BD
0x1800d8599  mov     rcx, [rbp+18h]; this
0x1800d859d  lea     r8, aOnecoreShellLi_2; "onecore\\shell\\lib\\calleridentity\\ca"...
0x1800d85a4  mov     r9d, eax; char *
0x1800d85a7  mov     edx, 0ABh; void *
0x1800d85ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d85b1  mov     rcx, [rbp+pv]; pv
0x1800d85b5  call    cs:__imp_CoTaskMemFree
0x1800d85bb  jmp     short loc_1800D8604
0x1800d85bd  mov     rbx, [rbp+pv]
0x1800d85c1  lea     r8, [rbp+hObject]; unsigned int
0x1800d85c5  mov     edx, dword ptr [rbp+hObject]; struct _TOKEN_SECURITY_ATTRIBUTE_V1 *
0x1800d85c8  mov     r9, rbx; unsigned int *
0x1800d85cb  mov     rcx, [rbp+var_10+8]; this
0x1800d85cf  call    ?GetAppUserModelId@SysAppId@ProcessToken@ARI@@YAJPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@IPEAIPEAG@Z; ARI::ProcessToken::SysAppId::GetAppUserModelId(_TOKEN_SECURITY_ATTRIBUTE_V1 const *,uint,uint *,ushort *)
0x1800d85d4  test    eax, eax
0x1800d85d6  jz      short loc_1800D85F7
0x1800d85d8  mov     rcx, [rbp+18h]; this
0x1800d85dc  lea     r8, aOnecoreShellLi_2; "onecore\\shell\\lib\\calleridentity\\ca"...
0x1800d85e3  mov     r9d, eax; char *
0x1800d85e6  mov     edx, 0ACh; void *
0x1800d85eb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800d85f0  mov     edi, eax
0x1800d85f2  mov     rcx, rbx
0x1800d85f5  jmp     short loc_1800D85B5
0x1800d85f7  xor     ecx, ecx; pv
0x1800d85f9  mov     [rsi], rbx
0x1800d85fc  call    cs:__imp_CoTaskMemFree
0x1800d8602  xor     edi, edi
0x1800d8604  lea     rcx, [rbp+var_10]; this
0x1800d8608  call    ?Close@AutoSysAppId@ProcessToken@ARI@@QEAAJXZ; ARI::ProcessToken::AutoSysAppId::Close(void)
0x1800d860d  mov     rbx, [rsp+40h+arg_0]
0x1800d8612  mov     eax, edi
0x1800d8614  add     rsp, 40h
0x1800d8618  pop     rdi
0x1800d8619  pop     rsi
0x1800d861a  pop     rbp
0x1800d861b  retn
```
