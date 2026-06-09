# IsProcessAllowed(ulong,ushort const *)

- ea: `0x18004d314`
- end: `0x18004d625`
- name: `?IsProcessAllowed@@YAHKPEBG@Z`
- size: `785`
- prototype: `__int64 __fastcall(DWORD dwProcessId, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800601fc`

## callees

- `0x180012a0c`
- `0x18004d314`
- `0x1800cd8d0`
- `0x1800e5330`
- `0x1800e7a64`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18004d397`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18004d397`
- `RPCRT4!RpcImpersonateClient` at `0x18004d374`
- `RPCRT4!RpcImpersonateClient` at `0x18004d374`
- `RPCRT4!RpcRevertToSelf` at `0x18004d4b4`
- `RPCRT4!RpcRevertToSelf` at `0x18004d4b4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004d49f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004d4a9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004d49f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004d4a9`

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
      if ( !(*(unsigned int (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v14 + 40LL))(
              v14,
              PKEY_Endpoint_Devnode,
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
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            10,
            WPP_90bf5887897f36b945cd238057b2fdf5_Traceguids,
            pSessionId,
            v8);
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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_90bf5887897f36b945cd238057b2fdf5_Traceguids, v9);
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
0x18004d314  mov     [rsp-8+arg_10], rbx
0x18004d319  mov     [rsp-8+arg_18], rsi
0x18004d31e  push    rbp
0x18004d31f  push    rdi
0x18004d320  push    r13
0x18004d322  push    r14
0x18004d324  push    r15
0x18004d326  lea     rbp, [rsp-37h]
0x18004d32b  sub     rsp, 0B0h
0x18004d332  mov     rax, cs:__security_cookie
0x18004d339  xor     rax, rsp
0x18004d33c  mov     [rbp+57h+var_30], rax
0x18004d340  mov     r15, rdx
0x18004d343  mov     edi, ecx
0x18004d345  xor     esi, esi
0x18004d347  mov     [rbp+57h+var_80], rsi
0x18004d34b  mov     [rbp+57h+var_88], rsi
0x18004d34f  mov     [rbp+57h+var_90], rsi
0x18004d353  mov     [rbp+57h+var_98], rsi
0x18004d357  mov     [rbp+57h+pSessionId], esi
0x18004d35a  xorps   xmm0, xmm0
0x18004d35d  xor     eax, eax
0x18004d35f  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18004d363  mov     [rbp+57h+var_68], rax
0x18004d367  xorps   xmm1, xmm1
0x18004d36a  movups  xmmword ptr [rbp+57h+var_60], xmm1
0x18004d36e  mov     [rbp+57h+var_50], rax
0x18004d372  xor     ecx, ecx; BindingHandle
0x18004d374  call    cs:__imp_RpcImpersonateClient
0x18004d37a  mov     ebx, eax
0x18004d37c  lea     r13, WPP_GLOBAL_Control
0x18004d383  test    eax, eax
0x18004d385  jnz     loc_18004D54C
0x18004d38b  mov     r14d, 1
0x18004d391  lea     rdx, [rbp+57h+pSessionId]; pSessionId
0x18004d395  mov     ecx, edi; dwProcessId
0x18004d397  call    cs:__imp_ProcessIdToSessionId
0x18004d39d  test    eax, eax
0x18004d39f  jnz     short loc_18004D3A4
0x18004d3a1  mov     [rbp+57h+pSessionId], eax
0x18004d3a4  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18004d3ab  mov     rax, [rcx]
0x18004d3ae  lea     r8, [rbp+57h+var_80]
0x18004d3b2  mov     rdx, r15
0x18004d3b5  mov     rax, [rax+28h]
0x18004d3b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d3be  mov     ebx, eax
0x18004d3c0  test    eax, eax
0x18004d3c2  js      loc_18004D49B
0x18004d3c8  mov     rcx, [rbp+57h+var_80]
0x18004d3cc  mov     rax, [rcx]
0x18004d3cf  lea     r8, [rbp+57h+var_88]
0x18004d3d3  xor     edx, edx
0x18004d3d5  mov     rax, [rax+20h]
0x18004d3d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d3de  mov     ebx, eax
0x18004d3e0  test    eax, eax
0x18004d3e2  js      loc_18004D49B
0x18004d3e8  xor     edi, edi
0x18004d3ea  mov     rcx, [rbp+57h+var_88]
0x18004d3ee  mov     rax, [rcx]
0x18004d3f1  lea     r8, [rbp+57h+pvar]
0x18004d3f5  lea     rdx, PKEY_Endpoint_Devnode
0x18004d3fc  mov     rax, [rax+28h]
0x18004d400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d405  test    eax, eax
0x18004d407  jnz     short loc_18004D487
0x18004d409  cmp     word ptr [rbp+57h+pvar], 1Fh
0x18004d40e  jnz     short loc_18004D487
0x18004d410  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18004d417  mov     rax, [rcx]
0x18004d41a  lea     r8, [rbp+57h+var_98]
0x18004d41e  mov     rdx, [rbp+57h+pvar+8]
0x18004d422  mov     rax, [rax+28h]
0x18004d426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d42b  mov     ebx, eax
0x18004d42d  test    eax, eax
0x18004d42f  js      short loc_18004D49B
0x18004d431  mov     rcx, [rbp+57h+var_98]
0x18004d435  mov     rax, [rcx]
0x18004d438  lea     r8, [rbp+57h+var_90]
0x18004d43c  xor     edx, edx
0x18004d43e  mov     rax, [rax+20h]
0x18004d442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d447  mov     ebx, eax
0x18004d449  test    eax, eax
0x18004d44b  js      short loc_18004D49B
0x18004d44d  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_SessionId.fmtid.Data1
0x18004d454  movdqu  [rbp+57h+var_48], xmm0
0x18004d459  mov     [rbp+57h+var_38], 6
0x18004d460  mov     rcx, [rbp+57h+var_90]
0x18004d464  mov     rax, [rcx]
0x18004d467  lea     r8, [rbp+57h+var_60]
0x18004d46b  lea     rdx, [rbp+57h+var_48]
0x18004d46f  mov     rax, [rax+28h]
0x18004d473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d478  test    eax, eax
0x18004d47a  js      short loc_18004D487
0x18004d47c  cmp     word ptr [rbp+57h+var_60], 13h
0x18004d481  jz      loc_18004D57B
0x18004d487  mov     r9d, [rbp+57h+pSessionId]
0x18004d48b  test    r9d, r9d
0x18004d48e  jz      short loc_18004D498
0x18004d490  test    edi, edi
0x18004d492  jnz     loc_18004D583
0x18004d498  mov     esi, r14d
0x18004d49b  lea     rcx, [rbp+57h+pvar]; pvar
0x18004d49f  call    cs:__imp_PropVariantClear
0x18004d4a5  lea     rcx, [rbp+57h+var_60]; pvar
0x18004d4a9  call    cs:__imp_PropVariantClear
0x18004d4af  test    r14d, r14d
0x18004d4b2  jz      short loc_18004D4C2
0x18004d4b4  call    cs:__imp_RpcRevertToSelf
0x18004d4ba  test    eax, eax
0x18004d4bc  jnz     loc_18004D5C7
0x18004d4c2  test    ebx, ebx
0x18004d4c4  js      loc_18004D60B
0x18004d4ca  mov     rcx, [rbp+57h+var_98]
0x18004d4ce  test    rcx, rcx
0x18004d4d1  jz      short loc_18004D4E0
0x18004d4d3  mov     rax, [rcx]
0x18004d4d6  mov     rax, [rax+10h]
0x18004d4da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d4df  nop
0x18004d4e0  mov     rcx, [rbp+57h+var_90]
0x18004d4e4  test    rcx, rcx
0x18004d4e7  jz      short loc_18004D4F6
0x18004d4e9  mov     rax, [rcx]
0x18004d4ec  mov     rax, [rax+10h]
0x18004d4f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d4f5  nop
0x18004d4f6  mov     rcx, [rbp+57h+var_88]
0x18004d4fa  test    rcx, rcx
0x18004d4fd  jz      short loc_18004D50C
0x18004d4ff  mov     rax, [rcx]
0x18004d502  mov     rax, [rax+10h]
0x18004d506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d50b  nop
0x18004d50c  mov     rcx, [rbp+57h+var_80]
0x18004d510  test    rcx, rcx
0x18004d513  jz      short loc_18004D522
0x18004d515  mov     rdx, [rcx]
0x18004d518  mov     rax, [rdx+10h]
0x18004d51c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d521  nop
0x18004d522  mov     eax, esi
0x18004d524  mov     rcx, [rbp+57h+var_30]
0x18004d528  xor     rcx, rsp; StackCookie
0x18004d52b  call    __security_check_cookie
0x18004d530  lea     r11, [rsp+0D0h+var_20]
0x18004d538  mov     rbx, [r11+40h]
0x18004d53c  mov     rsi, [r11+48h]
0x18004d540  mov     rsp, r11
0x18004d543  pop     r15
0x18004d545  pop     r14
0x18004d547  pop     r13
0x18004d549  pop     rdi
0x18004d54a  pop     rbp
0x18004d54b  retn
0x18004d54c  jle     short loc_18004D557
0x18004d54e  movzx   ebx, ax
0x18004d551  or      ebx, 80070000h
0x18004d557  test    ebx, ebx
0x18004d559  jns     loc_18004D38B
0x18004d55f  xor     r14d, r14d
0x18004d562  mov     r8d, ebx; int
0x18004d565  mov     edx, 24Ah; unsigned int
0x18004d56a  lea     rcx, aIsprocessallow; "IsProcessAllowed"
0x18004d571  call    ?AudSrvTraceLoggingErrorHelper@@YAXPEBDIJ@Z; AudSrvTraceLoggingErrorHelper(char const *,uint,long)
0x18004d576  jmp     loc_18004D49B
0x18004d57b  mov     edi, dword ptr [rbp+57h+var_60+8]
0x18004d57e  jmp     loc_18004D487
0x18004d583  cmp     r9d, edi
0x18004d586  jz      loc_18004D498
0x18004d58c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d593  cmp     rcx, r13
0x18004d596  jz      short loc_18004D5C0
0x18004d598  test    dword ptr [rcx+1Ch], 100h
0x18004d59f  jz      short loc_18004D5C0
0x18004d5a1  cmp     byte ptr [rcx+19h], 2
0x18004d5a5  jb      short loc_18004D5C0
0x18004d5a7  mov     edx, 0Ah
0x18004d5ac  mov     [rsp+0D0h+var_B0], edi
0x18004d5b0  lea     r8, WPP_90bf5887897f36b945cd238057b2fdf5_Traceguids
0x18004d5b7  mov     rcx, [rcx+10h]
0x18004d5bb  call    WPP_SF_dd
0x18004d5c0  xor     esi, esi
0x18004d5c2  jmp     loc_18004D49B
0x18004d5c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d5ce  cmp     rcx, r13
0x18004d5d1  jz      loc_18004D4C2
0x18004d5d7  test    dword ptr [rcx+1Ch], 100h
0x18004d5de  jz      loc_18004D4C2
0x18004d5e4  cmp     byte ptr [rcx+19h], 2
0x18004d5e8  jb      loc_18004D4C2
0x18004d5ee  mov     edx, 0Bh
0x18004d5f3  mov     r9d, eax
0x18004d5f6  lea     r8, WPP_90bf5887897f36b945cd238057b2fdf5_Traceguids
0x18004d5fd  mov     rcx, [rcx+10h]
0x18004d601  call    WPP_SF_d
0x18004d606  jmp     loc_18004D4C2
0x18004d60b  mov     r8d, ebx; int
0x18004d60e  mov     edx, 29Ch; unsigned int
0x18004d613  lea     rcx, aIsprocessallow; "IsProcessAllowed"
0x18004d61a  call    ?AudSrvTraceLoggingErrorHelper@@YAXPEBDIJ@Z; AudSrvTraceLoggingErrorHelper(char const *,uint,long)
0x18004d61f  jmp     loc_18004D4CA
```
