# IsProcessAllowed(ulong,ushort const *)

- ea: `0x18004d7a4`
- end: `0x18004dab5`
- name: `?IsProcessAllowed@@YAHKPEBG@Z`
- size: `785`
- prototype: `__int64 __fastcall(DWORD dwProcessId, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006068c`

## callees

- `0x1800128bc`
- `0x18004d7a4`
- `0x1800cf8c0`
- `0x1800e5ab0`
- `0x1800e81e4`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18004d827`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18004d827`
- `RPCRT4!RpcImpersonateClient` at `0x18004d804`
- `RPCRT4!RpcImpersonateClient` at `0x18004d804`
- `RPCRT4!RpcRevertToSelf` at `0x18004d944`
- `RPCRT4!RpcRevertToSelf` at `0x18004d944`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004d92f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004d939`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004d92f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004d939`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall IsProcessAllowed(DWORD dwProcessId, const unsigned __int16 *a2)
{
  unsigned int v4; // esi
  RPC_STATUS v5; // eax
  signed int v6; // ebx
  int v7; // r14d
  int v8; // edi
  unsigned int v9; // eax
  DWORD pSessionId; // [rsp+30h] [rbp-49h] BYREF
  __int64 v12; // [rsp+38h] [rbp-41h] BYREF
  __int64 v13; // [rsp+40h] [rbp-39h] BYREF
  __int64 v14; // [rsp+48h] [rbp-31h] BYREF
  __int64 v15; // [rsp+50h] [rbp-29h] BYREF
  PROPVARIANT pvar[2]; // [rsp+58h] [rbp-21h] BYREF
  __int64 v17; // [rsp+68h] [rbp-11h]
  PROPVARIANT v18[2]; // [rsp+70h] [rbp-9h] BYREF
  __int64 v19; // [rsp+80h] [rbp+7h]
  DEVPROPGUID fmtid; // [rsp+88h] [rbp+Fh] BYREF
  int v21; // [rsp+98h] [rbp+1Fh]

  v4 = 0;
  v15 = 0;
  v14 = 0;
  v13 = 0;
  v12 = 0;
  pSessionId = 0;
  *(_OWORD *)pvar = 0;
  v17 = 0;
  *(_OWORD *)v18 = 0;
  v19 = 0;
  v5 = RpcImpersonateClient(0);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    if ( v6 < 0 )
    {
      v7 = 0;
      AudSrvTraceLoggingErrorHelper("IsProcessAllowed", 0x24Au, v6);
      goto LABEL_16;
    }
  }
  v7 = 1;
  if ( !ProcessIdToSessionId(dwProcessId, &pSessionId) )
    pSessionId = 0;
  v6 = ((__int64 (__fastcall *)(struct IMMDeviceEnumerator *, const unsigned __int16 *, __int64 *))g_DeviceEnumerator->lpVtbl->GetDevice)(
         g_DeviceEnumerator,
         a2,
         &v15);
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v15 + 32LL))(v15, 0, &v14);
    if ( v6 >= 0 )
    {
      v8 = 0;
      if ( !(*(unsigned int (__fastcall **)(__int64, void *, PROPVARIANT *))(*(_QWORD *)v14 + 40LL))(
              v14,
              &PKEY_Endpoint_Devnode,
              pvar)
        && LOWORD(pvar[0]) == 31 )
      {
        v6 = ((__int64 (__fastcall *)(struct IMMDeviceEnumerator *, PROPVARIANT, __int64 *))g_DeviceEnumerator->lpVtbl->GetDevice)(
               g_DeviceEnumerator,
               pvar[1],
               &v12);
        if ( v6 < 0 )
          goto LABEL_16;
        v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v12 + 32LL))(v12, 0, &v13);
        if ( v6 < 0 )
          goto LABEL_16;
        fmtid = DEVPKEY_Device_SessionId.fmtid;
        v21 = 6;
        if ( (*(int (__fastcall **)(__int64, DEVPROPGUID *, PROPVARIANT *))(*(_QWORD *)v13 + 40LL))(v13, &fmtid, v18) >= 0
          && LOWORD(v18[0]) == 19 )
        {
          v8 = (int)v18[1];
        }
      }
      if ( pSessionId && v8 && pSessionId != v8 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_90bf5887897f36b945cd238057b2fdf5_Traceguids);
        }
        v4 = 0;
      }
      else
      {
        v4 = 1;
      }
    }
  }
LABEL_16:
  PropVariantClear(pvar);
  PropVariantClear(v18);
  if ( v7 )
  {
    v9 = RpcRevertToSelf();
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_90bf5887897f36b945cd238057b2fdf5_Traceguids, v9);
      }
    }
  }
  if ( v6 < 0 )
    AudSrvTraceLoggingErrorHelper("IsProcessAllowed", 0x29Cu, v6);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  return v4;
}

```

## disassembly

```asm
0x18004d7a4  mov     [rsp-8+arg_10], rbx
0x18004d7a9  mov     [rsp-8+arg_18], rsi
0x18004d7ae  push    rbp
0x18004d7af  push    rdi
0x18004d7b0  push    r13
0x18004d7b2  push    r14
0x18004d7b4  push    r15
0x18004d7b6  lea     rbp, [rsp-37h]
0x18004d7bb  sub     rsp, 0B0h
0x18004d7c2  mov     rax, cs:__security_cookie
0x18004d7c9  xor     rax, rsp
0x18004d7cc  mov     [rbp+57h+var_30], rax
0x18004d7d0  mov     r15, rdx
0x18004d7d3  mov     edi, ecx
0x18004d7d5  xor     esi, esi
0x18004d7d7  mov     [rbp+57h+var_80], rsi
0x18004d7db  mov     [rbp+57h+var_88], rsi
0x18004d7df  mov     [rbp+57h+var_90], rsi
0x18004d7e3  mov     [rbp+57h+var_98], rsi
0x18004d7e7  mov     [rbp+57h+pSessionId], esi
0x18004d7ea  xorps   xmm0, xmm0
0x18004d7ed  xor     eax, eax
0x18004d7ef  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18004d7f3  mov     [rbp+57h+var_68], rax
0x18004d7f7  xorps   xmm1, xmm1
0x18004d7fa  movups  xmmword ptr [rbp+57h+var_60], xmm1
0x18004d7fe  mov     [rbp+57h+var_50], rax
0x18004d802  xor     ecx, ecx; BindingHandle
0x18004d804  call    cs:__imp_RpcImpersonateClient
0x18004d80a  mov     ebx, eax
0x18004d80c  lea     r13, WPP_GLOBAL_Control
0x18004d813  test    eax, eax
0x18004d815  jnz     loc_18004D9DC
0x18004d81b  mov     r14d, 1
0x18004d821  lea     rdx, [rbp+57h+pSessionId]; pSessionId
0x18004d825  mov     ecx, edi; dwProcessId
0x18004d827  call    cs:__imp_ProcessIdToSessionId
0x18004d82d  test    eax, eax
0x18004d82f  jnz     short loc_18004D834
0x18004d831  mov     [rbp+57h+pSessionId], eax
0x18004d834  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18004d83b  mov     rax, [rcx]
0x18004d83e  lea     r8, [rbp+57h+var_80]
0x18004d842  mov     rdx, r15
0x18004d845  mov     rax, [rax+28h]
0x18004d849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d84e  mov     ebx, eax
0x18004d850  test    eax, eax
0x18004d852  js      loc_18004D92B
0x18004d858  mov     rcx, [rbp+57h+var_80]
0x18004d85c  mov     rax, [rcx]
0x18004d85f  lea     r8, [rbp+57h+var_88]
0x18004d863  xor     edx, edx
0x18004d865  mov     rax, [rax+20h]
0x18004d869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d86e  mov     ebx, eax
0x18004d870  test    eax, eax
0x18004d872  js      loc_18004D92B
0x18004d878  xor     edi, edi
0x18004d87a  mov     rcx, [rbp+57h+var_88]
0x18004d87e  mov     rax, [rcx]
0x18004d881  lea     r8, [rbp+57h+pvar]
0x18004d885  lea     rdx, PKEY_Endpoint_Devnode
0x18004d88c  mov     rax, [rax+28h]
0x18004d890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d895  test    eax, eax
0x18004d897  jnz     short loc_18004D917
0x18004d899  cmp     word ptr [rbp+57h+pvar], 1Fh
0x18004d89e  jnz     short loc_18004D917
0x18004d8a0  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18004d8a7  mov     rax, [rcx]
0x18004d8aa  lea     r8, [rbp+57h+var_98]
0x18004d8ae  mov     rdx, [rbp+57h+pvar+8]
0x18004d8b2  mov     rax, [rax+28h]
0x18004d8b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d8bb  mov     ebx, eax
0x18004d8bd  test    eax, eax
0x18004d8bf  js      short loc_18004D92B
0x18004d8c1  mov     rcx, [rbp+57h+var_98]
0x18004d8c5  mov     rax, [rcx]
0x18004d8c8  lea     r8, [rbp+57h+var_90]
0x18004d8cc  xor     edx, edx
0x18004d8ce  mov     rax, [rax+20h]
0x18004d8d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d8d7  mov     ebx, eax
0x18004d8d9  test    eax, eax
0x18004d8db  js      short loc_18004D92B
0x18004d8dd  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_SessionId.fmtid.Data1
0x18004d8e4  movdqu  [rbp+57h+var_48], xmm0
0x18004d8e9  mov     [rbp+57h+var_38], 6
0x18004d8f0  mov     rcx, [rbp+57h+var_90]
0x18004d8f4  mov     rax, [rcx]
0x18004d8f7  lea     r8, [rbp+57h+var_60]
0x18004d8fb  lea     rdx, [rbp+57h+var_48]
0x18004d8ff  mov     rax, [rax+28h]
0x18004d903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d908  test    eax, eax
0x18004d90a  js      short loc_18004D917
0x18004d90c  cmp     word ptr [rbp+57h+var_60], 13h
0x18004d911  jz      loc_18004DA0B
0x18004d917  mov     r9d, [rbp+57h+pSessionId]
0x18004d91b  test    r9d, r9d
0x18004d91e  jz      short loc_18004D928
0x18004d920  test    edi, edi
0x18004d922  jnz     loc_18004DA13
0x18004d928  mov     esi, r14d
0x18004d92b  lea     rcx, [rbp+57h+pvar]; pvar
0x18004d92f  call    cs:__imp_PropVariantClear
0x18004d935  lea     rcx, [rbp+57h+var_60]; pvar
0x18004d939  call    cs:__imp_PropVariantClear
0x18004d93f  test    r14d, r14d
0x18004d942  jz      short loc_18004D952
0x18004d944  call    cs:__imp_RpcRevertToSelf
0x18004d94a  test    eax, eax
0x18004d94c  jnz     loc_18004DA57
0x18004d952  test    ebx, ebx
0x18004d954  js      loc_18004DA9B
0x18004d95a  mov     rcx, [rbp+57h+var_98]
0x18004d95e  test    rcx, rcx
0x18004d961  jz      short loc_18004D970
0x18004d963  mov     rax, [rcx]
0x18004d966  mov     rax, [rax+10h]
0x18004d96a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d96f  nop
0x18004d970  mov     rcx, [rbp+57h+var_90]
0x18004d974  test    rcx, rcx
0x18004d977  jz      short loc_18004D986
0x18004d979  mov     rax, [rcx]
0x18004d97c  mov     rax, [rax+10h]
0x18004d980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d985  nop
0x18004d986  mov     rcx, [rbp+57h+var_88]
0x18004d98a  test    rcx, rcx
0x18004d98d  jz      short loc_18004D99C
0x18004d98f  mov     rax, [rcx]
0x18004d992  mov     rax, [rax+10h]
0x18004d996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d99b  nop
0x18004d99c  mov     rcx, [rbp+57h+var_80]
0x18004d9a0  test    rcx, rcx
0x18004d9a3  jz      short loc_18004D9B2
0x18004d9a5  mov     rdx, [rcx]
0x18004d9a8  mov     rax, [rdx+10h]
0x18004d9ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d9b1  nop
0x18004d9b2  mov     eax, esi
0x18004d9b4  mov     rcx, [rbp+57h+var_30]
0x18004d9b8  xor     rcx, rsp; StackCookie
0x18004d9bb  call    __security_check_cookie
0x18004d9c0  lea     r11, [rsp+0D0h+var_20]
0x18004d9c8  mov     rbx, [r11+40h]
0x18004d9cc  mov     rsi, [r11+48h]
0x18004d9d0  mov     rsp, r11
0x18004d9d3  pop     r15
0x18004d9d5  pop     r14
0x18004d9d7  pop     r13
0x18004d9d9  pop     rdi
0x18004d9da  pop     rbp
0x18004d9db  retn
0x18004d9dc  jle     short loc_18004D9E7
0x18004d9de  movzx   ebx, ax
0x18004d9e1  or      ebx, 80070000h
0x18004d9e7  test    ebx, ebx
0x18004d9e9  jns     loc_18004D81B
0x18004d9ef  xor     r14d, r14d
0x18004d9f2  mov     r8d, ebx; int
0x18004d9f5  mov     edx, 24Ah; unsigned int
0x18004d9fa  lea     rcx, aIsprocessallow; "IsProcessAllowed"
0x18004da01  call    ?AudSrvTraceLoggingErrorHelper@@YAXPEBDIJ@Z; AudSrvTraceLoggingErrorHelper(char const *,uint,long)
0x18004da06  jmp     loc_18004D92B
0x18004da0b  mov     edi, dword ptr [rbp+57h+var_60+8]
0x18004da0e  jmp     loc_18004D917
0x18004da13  cmp     r9d, edi
0x18004da16  jz      loc_18004D928
0x18004da1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004da23  cmp     rcx, r13
0x18004da26  jz      short loc_18004DA50
0x18004da28  test    dword ptr [rcx+1Ch], 100h
0x18004da2f  jz      short loc_18004DA50
0x18004da31  cmp     byte ptr [rcx+19h], 2
0x18004da35  jb      short loc_18004DA50
0x18004da37  mov     edx, 0Ah
0x18004da3c  mov     [rsp+0D0h+var_B0], edi
0x18004da40  lea     r8, WPP_90bf5887897f36b945cd238057b2fdf5_Traceguids
0x18004da47  mov     rcx, [rcx+10h]
0x18004da4b  call    WPP_SF_dd
0x18004da50  xor     esi, esi
0x18004da52  jmp     loc_18004D92B
0x18004da57  mov     rcx, cs:WPP_GLOBAL_Control
0x18004da5e  cmp     rcx, r13
0x18004da61  jz      loc_18004D952
0x18004da67  test    dword ptr [rcx+1Ch], 100h
0x18004da6e  jz      loc_18004D952
0x18004da74  cmp     byte ptr [rcx+19h], 2
0x18004da78  jb      loc_18004D952
0x18004da7e  mov     edx, 0Bh
0x18004da83  mov     r9d, eax
0x18004da86  lea     r8, WPP_90bf5887897f36b945cd238057b2fdf5_Traceguids
0x18004da8d  mov     rcx, [rcx+10h]
0x18004da91  call    WPP_SF_d
0x18004da96  jmp     loc_18004D952
0x18004da9b  mov     r8d, ebx; int
0x18004da9e  mov     edx, 29Ch; unsigned int
0x18004daa3  lea     rcx, aIsprocessallow; "IsProcessAllowed"
0x18004daaa  call    ?AudSrvTraceLoggingErrorHelper@@YAXPEBDIJ@Z; AudSrvTraceLoggingErrorHelper(char const *,uint,long)
0x18004daaf  jmp     loc_18004D95A
```
