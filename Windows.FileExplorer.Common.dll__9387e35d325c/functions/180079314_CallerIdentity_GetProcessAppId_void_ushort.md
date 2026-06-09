# CallerIdentity::GetProcessAppId(void *,ushort * *)

- ea: `0x180079314`
- end: `0x18007949c`
- name: `?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z`
- size: `392`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, void *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800790fc`

## callees

- `0x1800077c8`
- `0x18000ba10`
- `0x18002edcc`
- `0x180078f8c`
- `0x180078fec`
- `0x180079314`
- `0x1800794d0`
- `0x180079628`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180079378`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180079378`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800793f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079435`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007947c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800793f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079435`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007947c`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetProcessAppId(HANDLE ProcessHandle, _QWORD *a2, unsigned __int16 **a3)
{
  void **v5; // r8
  signed int v6; // edi
  const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **v7; // r9
  __int64 v8; // rdx
  int v9; // edx
  int v10; // ecx
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
    v11 = _AllocStringWorker<CTCoAllocPolicy>(v10, v9, 0, (_DWORD)hObject, (_DWORD)v16, (__int64)&pv);
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
0x180079314  mov     [rsp-18h+arg_0], rbx
0x180079319  push    rbp
0x18007931a  push    rsi
0x18007931b  push    rdi
0x18007931c  mov     rbp, rsp
0x18007931f  sub     rsp, 40h
0x180079323  mov     rbx, rcx
0x180079326  mov     qword ptr [rdx], 0
0x18007932d  xorps   xmm0, xmm0
0x180079330  lea     rcx, [rbp+var_10]; this
0x180079334  movdqu  xmmword ptr [rbp+var_10], xmm0
0x180079339  mov     rsi, rdx
0x18007933c  call    ?Close@AutoSysAppId@ProcessToken@ARI@@QEAAJXZ; ARI::ProcessToken::AutoSysAppId::Close(void)
0x180079341  lea     rdx, [rbp+hObject]; TokenHandle
0x180079345  mov     [rbp+hObject], 0
0x18007934d  mov     rcx, rbx; ProcessHandle
0x180079350  call    ?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z; ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)
0x180079355  mov     edi, eax
0x180079357  test    eax, eax
0x180079359  jnz     short loc_18007937E
0x18007935b  mov     rcx, [rbp+hObject]; TokenHandle
0x18007935f  lea     r8, [rbp+var_10+8]; struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **
0x180079363  lea     rdx, [rbp+var_10]; void *
0x180079367  call    ?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z; ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)
0x18007936c  mov     rcx, [rbp+hObject]; hObject
0x180079370  mov     edi, eax
0x180079372  cmp     rcx, 0FFFFFFFFFFFFFFFCh
0x180079376  jz      short loc_18007937E
0x180079378  call    cs:__imp_CloseHandle
0x18007937e  test    edi, edi
0x180079380  jle     short loc_18007938B
0x180079382  movzx   edi, di
0x180079385  or      edi, 80070000h
0x18007938b  cmp     edi, 80070490h
0x180079391  jz      loc_180079484
0x180079397  cmp     edi, 80070005h
0x18007939d  jz      loc_180079484
0x1800793a3  test    edi, edi
0x1800793a5  jns     short loc_1800793AE
0x1800793a7  mov     edx, 0A5h
0x1800793ac  jmp     short loc_1800793D6
0x1800793ae  mov     rcx, [rbp+var_10+8]; this
0x1800793b2  lea     r8, [rbp+hObject]; unsigned int
0x1800793b6  xor     r9d, r9d; unsigned int *
0x1800793b9  mov     dword ptr [rbp+hObject], 0
0x1800793c0  xor     edx, edx; struct _TOKEN_SECURITY_ATTRIBUTE_V1 *
0x1800793c2  call    ?GetAppUserModelId@SysAppId@ProcessToken@ARI@@YAJPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@IPEAIPEAG@Z; ARI::ProcessToken::SysAppId::GetAppUserModelId(_TOKEN_SECURITY_ATTRIBUTE_V1 const *,uint,uint *,ushort *)
0x1800793c7  cmp     eax, 7Ah ; 'z'
0x1800793ca  jz      short loc_1800793EE
0x1800793cc  mov     edi, 8000FFFFh
0x1800793d1  mov     edx, 0A8h; void *
0x1800793d6  mov     rcx, [rbp+18h]; this
0x1800793da  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x1800793e1  mov     r9d, edi; char *
0x1800793e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800793e9  jmp     loc_180079484
0x1800793ee  xor     ecx, ecx; pv
0x1800793f0  mov     [rbp+pv], 0
0x1800793f8  call    cs:__imp_CoTaskMemFree
0x1800793fe  mov     r9d, dword ptr [rbp+hObject]
0x180079402  lea     rax, [rbp+pv]
0x180079406  xor     r8d, r8d
0x180079409  mov     [rsp+40h+var_18], rax
0x18007940e  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180079413  mov     edi, eax
0x180079415  test    eax, eax
0x180079417  jns     short loc_18007943D
0x180079419  mov     rcx, [rbp+18h]; this
0x18007941d  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180079424  mov     r9d, eax; char *
0x180079427  mov     edx, 0ABh; void *
0x18007942c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079431  mov     rcx, [rbp+pv]; pv
0x180079435  call    cs:__imp_CoTaskMemFree
0x18007943b  jmp     short loc_180079484
0x18007943d  mov     rbx, [rbp+pv]
0x180079441  lea     r8, [rbp+hObject]; unsigned int
0x180079445  mov     edx, dword ptr [rbp+hObject]; struct _TOKEN_SECURITY_ATTRIBUTE_V1 *
0x180079448  mov     r9, rbx; unsigned int *
0x18007944b  mov     rcx, [rbp+var_10+8]; this
0x18007944f  call    ?GetAppUserModelId@SysAppId@ProcessToken@ARI@@YAJPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@IPEAIPEAG@Z; ARI::ProcessToken::SysAppId::GetAppUserModelId(_TOKEN_SECURITY_ATTRIBUTE_V1 const *,uint,uint *,ushort *)
0x180079454  test    eax, eax
0x180079456  jz      short loc_180079477
0x180079458  mov     rcx, [rbp+18h]; this
0x18007945c  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180079463  mov     r9d, eax; char *
0x180079466  mov     edx, 0ACh; void *
0x18007946b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180079470  mov     edi, eax
0x180079472  mov     rcx, rbx
0x180079475  jmp     short loc_180079435
0x180079477  xor     ecx, ecx; pv
0x180079479  mov     [rsi], rbx
0x18007947c  call    cs:__imp_CoTaskMemFree
0x180079482  xor     edi, edi
0x180079484  lea     rcx, [rbp+var_10]; this
0x180079488  call    ?Close@AutoSysAppId@ProcessToken@ARI@@QEAAJXZ; ARI::ProcessToken::AutoSysAppId::Close(void)
0x18007948d  mov     rbx, [rsp+40h+arg_0]
0x180079492  mov     eax, edi
0x180079494  add     rsp, 40h
0x180079498  pop     rdi
0x180079499  pop     rsi
0x18007949a  pop     rbp
0x18007949b  retn
```
