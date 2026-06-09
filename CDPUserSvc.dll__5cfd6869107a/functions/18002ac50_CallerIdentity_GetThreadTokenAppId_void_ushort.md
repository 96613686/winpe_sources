# CallerIdentity::GetThreadTokenAppId(void *,ushort * *)

- ea: `0x18002ac50`
- end: `0x18002ad44`
- name: `?GetThreadTokenAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z`
- size: `244`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180051830`

## callees

- `0x18002ac50`
- `0x18002ad4c`
- `0x18002ae5c`
- `0x18002afb4`
- `0x18005caf4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002acd3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ad26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002acd3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ad26`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetThreadTokenAppId(HANDLE TokenHandle, _QWORD *a2, unsigned __int16 **a3)
{
  const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **v5; // r9
  signed int v6; // eax
  signed int v7; // edi
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  int v11; // eax
  void *v12; // rbx
  int AppUserModelId; // eax
  void *v14; // rax
  unsigned __int16 *v16; // [rsp+20h] [rbp-20h]
  unsigned __int16 *v17; // [rsp+20h] [rbp-20h]
  ARI::ProcessToken::SysAppId *v18[2]; // [rsp+30h] [rbp-10h] BYREF
  struct _TOKEN_SECURITY_ATTRIBUTE_V1 *v19; // [rsp+68h] [rbp+28h] BYREF
  LPVOID pv; // [rsp+70h] [rbp+30h]

  *a2 = 0;
  *(_OWORD *)v18 = 0;
  ARI::ProcessToken::AutoSysAppId::Close((ARI::ProcessToken::AutoSysAppId *)v18);
  v6 = ARI::ProcessToken::SysAppId::Open(TokenHandle, v18, &v18[1], v5);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 >= 0 )
  {
    LODWORD(v19) = 0;
    if ( (unsigned int)ARI::ProcessToken::SysAppId::GetAppUserModelId(v18[1], 0, (unsigned int)&v19, 0, v16) == 122 )
    {
      pv = 0;
      CoTaskMemFree(0);
      v11 = _AllocStringWorker<CTCoAllocPolicy>(v9, v8, v10, (unsigned int)v19);
      v12 = pv;
      v7 = v11;
      if ( v11 >= 0 )
      {
        AppUserModelId = ARI::ProcessToken::SysAppId::GetAppUserModelId(
                           v18[1],
                           (const struct _TOKEN_SECURITY_ATTRIBUTE_V1 *)(unsigned int)v19,
                           (unsigned int)&v19,
                           (unsigned int *)pv,
                           v17);
        v7 = AppUserModelId;
        if ( AppUserModelId > 0 )
          v7 = (unsigned __int16)AppUserModelId | 0x80070000;
        if ( v7 >= 0 )
        {
          v14 = v12;
          v12 = 0;
          *a2 = v14;
        }
      }
      CoTaskMemFree(v12);
    }
    else
    {
      v7 = -2147418113;
    }
  }
  ARI::ProcessToken::AutoSysAppId::Close((ARI::ProcessToken::AutoSysAppId *)v18);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002ac50  mov     [rsp-18h+arg_0], rbx
0x18002ac55  push    rbp
0x18002ac56  push    rsi
0x18002ac57  push    rdi
0x18002ac58  mov     rbp, rsp
0x18002ac5b  sub     rsp, 40h
0x18002ac5f  mov     rbx, rcx
0x18002ac62  mov     qword ptr [rdx], 0
0x18002ac69  xorps   xmm0, xmm0
0x18002ac6c  lea     rcx, [rbp+var_10]; this
0x18002ac70  movdqu  xmmword ptr [rbp+var_10], xmm0
0x18002ac75  mov     rsi, rdx
0x18002ac78  call    ?Close@AutoSysAppId@ProcessToken@ARI@@QEAAJXZ; ARI::ProcessToken::AutoSysAppId::Close(void)
0x18002ac7d  lea     r8, [rbp+var_10+8]; struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **
0x18002ac81  mov     rcx, rbx; TokenHandle
0x18002ac84  lea     rdx, [rbp+var_10]; void *
0x18002ac88  call    ?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z; ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)
0x18002ac8d  mov     edi, eax
0x18002ac8f  test    eax, eax
0x18002ac91  jle     short loc_18002AC9C
0x18002ac93  movzx   edi, ax
0x18002ac96  or      edi, 80070000h
0x18002ac9c  test    edi, edi
0x18002ac9e  js      loc_18002AD2C
0x18002aca4  mov     rcx, [rbp+var_10+8]; this
0x18002aca8  lea     r8, [rbp+arg_8]; unsigned int
0x18002acac  xor     r9d, r9d; unsigned int *
0x18002acaf  mov     dword ptr [rbp+arg_8], 0
0x18002acb6  xor     edx, edx; struct _TOKEN_SECURITY_ATTRIBUTE_V1 *
0x18002acb8  call    ?GetAppUserModelId@SysAppId@ProcessToken@ARI@@YAJPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@IPEAIPEAG@Z; ARI::ProcessToken::SysAppId::GetAppUserModelId(_TOKEN_SECURITY_ATTRIBUTE_V1 const *,uint,uint *,ushort *)
0x18002acbd  cmp     eax, 7Ah ; 'z'
0x18002acc0  jz      short loc_18002ACC9
0x18002acc2  mov     edi, 8000FFFFh
0x18002acc7  jmp     short loc_18002AD2C
0x18002acc9  xor     ecx, ecx; pv
0x18002accb  mov     [rbp+pv], 0
0x18002acd3  call    cs:__imp_CoTaskMemFree
0x18002acd9  mov     r9d, dword ptr [rbp+arg_8]
0x18002acdd  lea     rax, [rbp+pv]
0x18002ace1  mov     [rsp+40h+var_18], rax
0x18002ace6  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18002aceb  mov     rbx, [rbp+pv]
0x18002acef  mov     edi, eax
0x18002acf1  test    eax, eax
0x18002acf3  js      short loc_18002AD23
0x18002acf5  mov     edx, dword ptr [rbp+arg_8]; struct _TOKEN_SECURITY_ATTRIBUTE_V1 *
0x18002acf8  lea     r8, [rbp+arg_8]; unsigned int
0x18002acfc  mov     rcx, [rbp+var_10+8]; this
0x18002ad00  mov     r9, rbx; unsigned int *
0x18002ad03  call    ?GetAppUserModelId@SysAppId@ProcessToken@ARI@@YAJPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@IPEAIPEAG@Z; ARI::ProcessToken::SysAppId::GetAppUserModelId(_TOKEN_SECURITY_ATTRIBUTE_V1 const *,uint,uint *,ushort *)
0x18002ad08  mov     edi, eax
0x18002ad0a  test    eax, eax
0x18002ad0c  jle     short loc_18002AD17
0x18002ad0e  movzx   edi, ax
0x18002ad11  or      edi, 80070000h
0x18002ad17  test    edi, edi
0x18002ad19  js      short loc_18002AD23
0x18002ad1b  mov     rax, rbx
0x18002ad1e  xor     ebx, ebx
0x18002ad20  mov     [rsi], rax
0x18002ad23  mov     rcx, rbx; pv
0x18002ad26  call    cs:__imp_CoTaskMemFree
0x18002ad2c  lea     rcx, [rbp+var_10]; this
0x18002ad30  call    ?Close@AutoSysAppId@ProcessToken@ARI@@QEAAJXZ; ARI::ProcessToken::AutoSysAppId::Close(void)
0x18002ad35  mov     rbx, [rsp+40h+arg_0]
0x18002ad3a  mov     eax, edi
0x18002ad3c  add     rsp, 40h
0x18002ad40  pop     rdi
0x18002ad41  pop     rsi
0x18002ad42  pop     rbp
0x18002ad43  retn
```
