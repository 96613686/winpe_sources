# PKU2URenewCertificate(ushort *,ushort const *)

- ea: `0x180013404`
- end: `0x180013554`
- name: `?PKU2URenewCertificate@@YAKPEAGPEBG@Z`
- size: `336`
- prototype: `__int64 __fastcall(unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800167c8`

## callees

- `0x180007c90`
- `0x1800131d0`
- `0x180013404`
- `0x18001355c`
- `0x18001a342`
- `0x18001a380`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180013484`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180013484`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013494`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013494`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001350c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001350c`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180013466`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180013466`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800134c0`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800134c0`
- `RPCRT4!RpcBindingFree` at `0x180013528`
- `RPCRT4!RpcBindingFree` at `0x180013528`

## pseudocode

```c
__int64 __fastcall PKU2URenewCertificate(unsigned __int16 *a1, const unsigned __int16 *a2)
{
  int v4; // edi
  unsigned int v5; // edx
  __int64 v6; // rcx
  unsigned int LastError; // ebx
  RPC_BINDING_HANDLE Binding; // [rsp+38h] [rbp-A0h] BYREF
  _RPC_ASYNC_STATE pAsync; // [rsp+40h] [rbp-98h] BYREF

  Binding = 0;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v4 = 0;
  LastError = PKU2UBindClient(a1, &Binding);
  if ( LastError )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0z_EtwEventWriteTransfer(v6, FailedToConnectToLRPC, a1);
  }
  else
  {
    LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
    if ( !LastError )
    {
      pAsync.NotificationType = RpcNotificationTypeEvent;
      pAsync.u.APC.NotificationRoutine = (PFN_RPCNOTIFICATION_ROUTINE)CreateEventW(0, 0, 0, 0);
      if ( !pAsync.u.APC.NotificationRoutine )
        LastError = GetLastError();
    }
    if ( !LastError )
    {
      Ndr64AsyncClientCall(
        (MIDL_STUBLESS_PROXY_INFO *)&OnlineProviderCertInterface_ProxyInfo,
        0,
        0,
        &pAsync,
        Binding,
        a2,
        0);
      v4 = 1;
    }
  }
  if ( v4 )
    LastError = PKU2UcpAsyncFinishCall(&pAsync, v5, LastError);
  if ( pAsync.u.APC.NotificationRoutine )
  {
    CloseHandle(pAsync.u.APC.NotificationRoutine);
    pAsync.u.APC.NotificationRoutine = 0;
  }
  if ( Binding )
    RpcBindingFree(&Binding);
  return LastError;
}

```

## disassembly

```asm
0x180013404  mov     [rsp+arg_10], rbx
0x180013409  push    rsi
0x18001340a  push    rdi
0x18001340b  push    r14
0x18001340d  sub     rsp, 0C0h
0x180013414  mov     rax, cs:__security_cookie
0x18001341b  xor     rax, rsp
0x18001341e  mov     [rsp+0D8h+var_28], rax
0x180013426  mov     r14, rdx
0x180013429  mov     rsi, rcx
0x18001342c  mov     [rsp+0D8h+Binding], 0
0x180013435  xor     edx, edx; Val
0x180013437  lea     r8d, [rdx+70h]; Size
0x18001343b  lea     rcx, [rsp+0D8h+pAsync]; void *
0x180013440  call    memset_0
0x180013445  xor     edi, edi
0x180013447  mov     [rsp+0D8h+var_A8], edi
0x18001344b  lea     rdx, [rsp+0D8h+Binding]; void **
0x180013450  mov     rcx, rsi; unsigned __int16 *
0x180013453  call    ?PKU2UBindClient@@YAKPEBGPEAPEAX@Z; PKU2UBindClient(ushort const *,void * *)
0x180013458  mov     ebx, eax
0x18001345a  test    eax, eax
0x18001345c  jnz     short loc_1800134D7
0x18001345e  lea     edx, [rdi+70h]; Size
0x180013461  lea     rcx, [rsp+0D8h+pAsync]; pAsync
0x180013466  call    cs:__imp_RpcAsyncInitializeHandle
0x18001346c  mov     ebx, eax
0x18001346e  test    eax, eax
0x180013470  jnz     short loc_18001349C
0x180013472  mov     [rsp+0D8h+pAsync.NotificationType], 1
0x18001347a  xor     r9d, r9d; lpName
0x18001347d  xor     r8d, r8d; bInitialState
0x180013480  xor     edx, edx; bManualReset
0x180013482  xor     ecx, ecx; lpEventAttributes
0x180013484  call    cs:__imp_CreateEventW
0x18001348a  mov     qword ptr [rsp+0D8h+pAsync.u], rax
0x18001348f  test    rax, rax
0x180013492  jnz     short loc_18001349C
0x180013494  call    cs:__imp_GetLastError
0x18001349a  mov     ebx, eax
0x18001349c  test    ebx, ebx
0x18001349e  jnz     short loc_1800134EF
0x1800134a0  mov     [rsp+0D8h+var_B0], r14
0x1800134a5  mov     rax, [rsp+0D8h+Binding]
0x1800134aa  mov     [rsp+0D8h+var_B8], rax
0x1800134af  lea     r9, [rsp+0D8h+pAsync]
0x1800134b4  xor     r8d, r8d; pReturnValue
0x1800134b7  xor     edx, edx; nProcNum
0x1800134b9  lea     rcx, ?OnlineProviderCertInterface_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800134c0  call    cs:__imp_Ndr64AsyncClientCall
0x1800134c6  lea     edi, [rbx+1]
0x1800134c9  mov     [rsp+0D8h+var_A8], edi
0x1800134cd  jmp     short loc_1800134EF
0x1800134cf  mov     ebx, eax
0x1800134d1  mov     edi, [rsp+0D8h+var_A8]
0x1800134d5  jmp     short loc_1800134EF
0x1800134d7  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x1800134de  jz      short loc_1800134EF
0x1800134e0  mov     r8, rsi
0x1800134e3  lea     rdx, FailedToConnectToLRPC
0x1800134ea  call    McTemplateU0z_EtwEventWriteTransfer
0x1800134ef  test    edi, edi
0x1800134f1  jz      short loc_180013502
0x1800134f3  mov     r8d, ebx; unsigned int
0x1800134f6  lea     rcx, [rsp+0D8h+pAsync]; pAsync
0x1800134fb  call    ?PKU2UcpAsyncFinishCall@@YAKPEAU_RPC_ASYNC_STATE@@KK@Z; PKU2UcpAsyncFinishCall(_RPC_ASYNC_STATE *,ulong,ulong)
0x180013500  mov     ebx, eax
0x180013502  mov     rcx, qword ptr [rsp+0D8h+pAsync.u]; hObject
0x180013507  test    rcx, rcx
0x18001350a  jz      short loc_18001351B
0x18001350c  call    cs:__imp_CloseHandle
0x180013512  mov     qword ptr [rsp+0D8h+pAsync.u], 0
0x18001351b  cmp     [rsp+0D8h+Binding], 0
0x180013521  jz      short loc_18001352E
0x180013523  lea     rcx, [rsp+0D8h+Binding]; Binding
0x180013528  call    cs:__imp_RpcBindingFree
0x18001352e  mov     eax, ebx
0x180013530  mov     rcx, [rsp+0D8h+var_28]
0x180013538  xor     rcx, rsp; StackCookie
0x18001353b  call    __security_check_cookie
0x180013540  mov     rbx, [rsp+0D8h+arg_10]
0x180013548  add     rsp, 0C0h
0x18001354f  pop     r14
0x180013551  pop     rdi
0x180013552  pop     rsi
0x180013553  retn
```
