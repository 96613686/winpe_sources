# CallerIdentity::GetProcessAppId(void *,ushort * *)

- ea: `0x180043788`
- end: `0x180043904`
- name: `?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z`
- size: `380`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, void *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800434ac`

## callees

- `0x18000ddac`
- `0x1800432dc`
- `0x180043398`
- `0x1800433f8`
- `0x180043788`
- `0x180043938`
- `0x180043a94`
- `0x180043b14`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004386c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800438a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800438e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004386c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800438a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800438e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800437ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800437ec`

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
  void *v15; // rdx
  unsigned int v16; // r8d
  unsigned __int16 *v18; // [rsp+20h] [rbp-20h]
  unsigned int v19; // [rsp+20h] [rbp-20h]
  ARI::ProcessToken::SysAppId *v20[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  HANDLE hObject; // [rsp+68h] [rbp+28h] BYREF
  LPVOID pv; // [rsp+70h] [rbp+30h]

  *a2 = 0;
  *(_OWORD *)v20 = 0;
  ARI::ProcessToken::AutoSysAppId::Close((ARI::ProcessToken::AutoSysAppId *)v20);
  hObject = 0;
  v6 = ARI::ProcessToken::SysAppId::OpenTokenForProcess(ProcessHandle, &hObject, v5);
  if ( !v6 )
  {
    v6 = ARI::ProcessToken::SysAppId::Open(hObject, v20, (const UNICODE_STRING **)&v20[1], v7);
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
        (int)v18);
      goto LABEL_19;
    }
    LODWORD(hObject) = 0;
    if ( (unsigned int)ARI::ProcessToken::SysAppId::GetAppUserModelId(v20[1], 0, (unsigned int)&hObject, 0, v18) != 122 )
    {
      v6 = -2147418113;
      v8 = 168;
      goto LABEL_12;
    }
    pv = 0;
    CoTaskMemFree(0);
    v11 = _AllocStringWorker<CTCoAllocPolicy>(v10, v9, 0, (unsigned int)hObject);
    v6 = v11;
    if ( v11 >= 0 )
    {
      v13 = pv;
      AppUserModelId = ARI::ProcessToken::SysAppId::GetAppUserModelId(
                         v20[1],
                         (const struct _TOKEN_SECURITY_ATTRIBUTE_V1 *)(unsigned int)hObject,
                         (unsigned int)&hObject,
                         (unsigned int *)pv,
                         v18);
      if ( !AppUserModelId )
      {
        *a2 = v13;
        CoTaskMemFree(0);
        v6 = 0;
        goto LABEL_19;
      }
      v6 = wil::details::in1diag3::Return_Win32(retaddr, v15, v16, (const char *)AppUserModelId, v19);
      v12 = v13;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAB,
        (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
        (const char *)(unsigned int)v11,
        (int)v18);
      v12 = pv;
    }
    CoTaskMemFree(v12);
  }
LABEL_19:
  ARI::ProcessToken::AutoSysAppId::Close((ARI::ProcessToken::AutoSysAppId *)v20);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180043788  mov     [rsp-18h+arg_0], rbx
0x18004378d  push    rbp
0x18004378e  push    rsi
0x18004378f  push    rdi
0x180043790  mov     rbp, rsp
0x180043793  sub     rsp, 40h
0x180043797  mov     rbx, rcx
0x18004379a  mov     qword ptr [rdx], 0
0x1800437a1  xorps   xmm0, xmm0
0x1800437a4  lea     rcx, [rbp+var_10]; this
0x1800437a8  movdqu  xmmword ptr [rbp+var_10], xmm0
0x1800437ad  mov     rsi, rdx
0x1800437b0  call    ?Close@AutoSysAppId@ProcessToken@ARI@@QEAAJXZ; ARI::ProcessToken::AutoSysAppId::Close(void)
0x1800437b5  lea     rdx, [rbp+hObject]; TokenHandle
0x1800437b9  mov     [rbp+hObject], 0
0x1800437c1  mov     rcx, rbx; ProcessHandle
0x1800437c4  call    ?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z; ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)
0x1800437c9  mov     edi, eax
0x1800437cb  test    eax, eax
0x1800437cd  jnz     short loc_1800437F2
0x1800437cf  mov     rcx, [rbp+hObject]; TokenHandle
0x1800437d3  lea     r8, [rbp+var_10+8]; struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **
0x1800437d7  lea     rdx, [rbp+var_10]; void *
0x1800437db  call    ?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z; ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)
0x1800437e0  mov     rcx, [rbp+hObject]; hObject
0x1800437e4  mov     edi, eax
0x1800437e6  cmp     rcx, 0FFFFFFFFFFFFFFFCh
0x1800437ea  jz      short loc_1800437F2
0x1800437ec  call    cs:__imp_CloseHandle
0x1800437f2  test    edi, edi
0x1800437f4  jle     short loc_1800437FF
0x1800437f6  movzx   edi, di
0x1800437f9  or      edi, 80070000h
0x1800437ff  cmp     edi, 80070490h
0x180043805  jz      loc_1800438EC
0x18004380b  cmp     edi, 80070005h
0x180043811  jz      loc_1800438EC
0x180043817  test    edi, edi
0x180043819  jns     short loc_180043822
0x18004381b  mov     edx, 0A5h
0x180043820  jmp     short loc_18004384A
0x180043822  mov     rcx, [rbp+var_10+8]; this
0x180043826  lea     r8, [rbp+hObject]; unsigned int
0x18004382a  xor     r9d, r9d; unsigned int *
0x18004382d  mov     dword ptr [rbp+hObject], 0
0x180043834  xor     edx, edx; struct _TOKEN_SECURITY_ATTRIBUTE_V1 *
0x180043836  call    ?GetAppUserModelId@SysAppId@ProcessToken@ARI@@YAJPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@IPEAIPEAG@Z; ARI::ProcessToken::SysAppId::GetAppUserModelId(_TOKEN_SECURITY_ATTRIBUTE_V1 const *,uint,uint *,ushort *)
0x18004383b  cmp     eax, 7Ah ; 'z'
0x18004383e  jz      short loc_180043862
0x180043840  mov     edi, 8000FFFFh
0x180043845  mov     edx, 0A8h; void *
0x18004384a  mov     rcx, [rbp+18h]; this
0x18004384e  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180043855  mov     r9d, edi; char *
0x180043858  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004385d  jmp     loc_1800438EC
0x180043862  xor     ecx, ecx; pv
0x180043864  mov     [rbp+pv], 0
0x18004386c  call    cs:__imp_CoTaskMemFree
0x180043872  mov     r9d, dword ptr [rbp+hObject]
0x180043876  lea     rax, [rbp+pv]
0x18004387a  xor     r8d, r8d
0x18004387d  mov     [rsp+40h+var_18], rax
0x180043882  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180043887  mov     edi, eax
0x180043889  test    eax, eax
0x18004388b  jns     short loc_1800438B1
0x18004388d  mov     rcx, [rbp+18h]; this
0x180043891  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180043898  mov     r9d, eax; char *
0x18004389b  mov     edx, 0ABh; void *
0x1800438a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800438a5  mov     rcx, [rbp+pv]; pv
0x1800438a9  call    cs:__imp_CoTaskMemFree
0x1800438af  jmp     short loc_1800438EC
0x1800438b1  mov     rbx, [rbp+pv]
0x1800438b5  lea     r8, [rbp+hObject]; unsigned int
0x1800438b9  mov     edx, dword ptr [rbp+hObject]; struct _TOKEN_SECURITY_ATTRIBUTE_V1 *
0x1800438bc  mov     r9, rbx; unsigned int *
0x1800438bf  mov     rcx, [rbp+var_10+8]; this
0x1800438c3  call    ?GetAppUserModelId@SysAppId@ProcessToken@ARI@@YAJPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@IPEAIPEAG@Z; ARI::ProcessToken::SysAppId::GetAppUserModelId(_TOKEN_SECURITY_ATTRIBUTE_V1 const *,uint,uint *,ushort *)
0x1800438c8  test    eax, eax
0x1800438ca  jz      short loc_1800438DF
0x1800438cc  mov     rcx, [rbp+18h]; this
0x1800438d0  mov     r9d, eax; char *
0x1800438d3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800438d8  mov     edi, eax
0x1800438da  mov     rcx, rbx
0x1800438dd  jmp     short loc_1800438A9
0x1800438df  xor     ecx, ecx; pv
0x1800438e1  mov     [rsi], rbx
0x1800438e4  call    cs:__imp_CoTaskMemFree
0x1800438ea  xor     edi, edi
0x1800438ec  lea     rcx, [rbp+var_10]; this
0x1800438f0  call    ?Close@AutoSysAppId@ProcessToken@ARI@@QEAAJXZ; ARI::ProcessToken::AutoSysAppId::Close(void)
0x1800438f5  mov     rbx, [rsp+40h+arg_0]
0x1800438fa  mov     eax, edi
0x1800438fc  add     rsp, 40h
0x180043900  pop     rdi
0x180043901  pop     rsi
0x180043902  pop     rbp
0x180043903  retn
```
