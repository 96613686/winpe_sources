# UalCollectData

- ea: `0x140086898`
- end: `0x140086adb`
- name: `UalCollectData`
- size: `579`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400173d0`

## callees

- `0x140002c73`
- `0x140085e10`
- `0x140086118`
- `0x1400865ac`
- `0x1400866bc`
- `0x140086898`
- `0x140086ec0`
- `0x14008b010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400869a1`
- `KERNEL32!GetLastError` at `0x1400869a1`
- `RPCRT4!RpcRevertToSelfEx` at `0x14008693a`
- `RPCRT4!RpcRevertToSelfEx` at `0x140086aad`
- `RPCRT4!RpcRevertToSelfEx` at `0x14008693a`
- `RPCRT4!RpcRevertToSelfEx` at `0x140086aad`
- `RPCRT4!RpcImpersonateClient` at `0x1400868f1`
- `RPCRT4!RpcImpersonateClient` at `0x1400868f1`
- `ntdll!RtlIpv4StringToAddressExW` at `0x140086a2e`
- `ntdll!RtlIpv4StringToAddressExW` at `0x140086a2e`
- `ntdll!RtlIpv6StringToAddressExW` at `0x1400869fa`
- `ntdll!RtlIpv6StringToAddressExW` at `0x1400869fa`
- `Secur32!GetUserNameExW` at `0x140086991`
- `Secur32!GetUserNameExW` at `0x140086991`

## pseudocode

```c
__int64 __fastcall UalCollectData(void *a1)
{
  void *v3; // rdi
  char v4; // si
  RPC_STATUS v5; // eax
  bool v6; // sf
  unsigned int v7; // r8d
  signed int LastError; // eax
  int IpAddressFromRpc; // ebx
  int v10; // eax
  int v11; // eax
  ULONG nSize[4]; // [rsp+20h] [rbp-E0h] BYREF
  int v13; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v14; // [rsp+34h] [rbp-CCh]
  _BYTE v15[20]; // [rsp+44h] [rbp-BCh] BYREF
  __int16 v16; // [rsp+58h] [rbp-A8h]
  USHORT Port; // [rsp+5Ah] [rbp-A6h] BYREF
  in_addr v18; // [rsp+5Ch] [rbp-A4h] BYREF
  in6_addr Address; // [rsp+60h] [rbp-A0h] BYREF
  ULONG ScopeId[26]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR NameBuffer[260]; // [rsp+D8h] [rbp-28h] BYREF
  WCHAR AddressString[72]; // [rsp+2E0h] [rbp+1E0h] BYREF

  if ( !fnUalInstrument )
    return 2147500037LL;
  v3 = 0;
  v4 = 0;
  if ( !a1 )
    goto LABEL_13;
  if ( !NtCurrentTeb()->IsImpersonating )
  {
    v5 = RpcImpersonateClient(a1);
    v6 = v5 < 0;
    if ( v5 > 0 )
      v6 = 1;
    if ( !v6 )
    {
      v3 = a1;
      v4 = 1;
    }
  }
  if ( IsLocalCall(a1) )
  {
    UalPrintTelemetry::WriteDbgTraceInfo("UalCollectData", L"Local client, no UAL collection");
    if ( v4 )
      RpcRevertToSelfEx(v3);
    return 1;
  }
  else
  {
LABEL_13:
    memset_0(v15, 0, 0x29Cu);
    v13 = 688;
    nSize[0] = 260;
    v14 = SumGuid_FAX;
    if ( !GetUserNameExW(NameSamCompatible, NameBuffer, nSize) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      UalPrintTelemetry::WriteDbgTraceError(
        "UalCollectData",
        L"Failed to collect username: hr: 0x%x",
        (unsigned int)LastError);
    }
    IpAddressFromRpc = GetIpAddressFromRpc(a1, AddressString, v7);
    if ( IpAddressFromRpc >= 0 )
    {
      v10 = RtlIpv6StringToAddressExW(AddressString, &Address, ScopeId, &Port) | 0x10000000;
      if ( v10 < 0 )
      {
        v10 = RtlIpv4StringToAddressExW(AddressString, 0, &v18, &Port) | 0x10000000;
        if ( v10 >= 0 )
          v16 = 2;
      }
      else
      {
        v16 = 23;
      }
      IpAddressFromRpc = 0;
      if ( v10 < 0 )
        IpAddressFromRpc = v10;
      if ( IpAddressFromRpc >= 0 )
        goto LABEL_26;
    }
    UalPrintTelemetry::WriteDbgTraceInfo(
      "UalCollectData",
      L"Failed to collect IP address: hr: 0x%x",
      (unsigned int)IpAddressFromRpc);
    v16 = 2;
    v18 = 0;
    if ( NameBuffer[0] )
    {
LABEL_26:
      v11 = ((__int64 (__fastcall *)(int *))fnUalInstrument)(&v13);
      IpAddressFromRpc = v11;
      if ( v11 < 0 )
        UalPrintTelemetry::WriteDbgTraceError("UalCollectData", L"Failed to log UAL data: hr: 0x%x", (unsigned int)v11);
    }
    if ( v4 )
      RpcRevertToSelfEx(v3);
    return (unsigned int)IpAddressFromRpc;
  }
}

```

## disassembly

```asm
0x140086898  push    rbp
0x14008689a  push    rbx
0x14008689b  push    rsi
0x14008689c  push    rdi
0x14008689d  push    r12
0x14008689f  push    r14
0x1400868a1  lea     rbp, [rsp-288h]
0x1400868a9  sub     rsp, 388h
0x1400868b0  mov     rax, cs:__security_cookie
0x1400868b7  xor     rax, rsp
0x1400868ba  mov     [rbp+2B0h+var_40], rax
0x1400868c1  xor     r14d, r14d
0x1400868c4  mov     rbx, rcx
0x1400868c7  cmp     cs:?fnUalInstrument@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, r14; long (*fnUalInstrument)(tagUAL_DATA_BLOB *)
0x1400868ce  jnz     short loc_1400868DA
0x1400868d0  mov     eax, 80004005h
0x1400868d5  jmp     loc_140086ABB
0x1400868da  mov     rdi, r14
0x1400868dd  mov     sil, r14b
0x1400868e0  test    rbx, rbx
0x1400868e3  jz      short loc_140086950
0x1400868e5  mov     eax, gs:179Ch
0x1400868ed  test    eax, eax
0x1400868ef  jnz     short loc_140086913
0x1400868f1  call    cs:__imp_RpcImpersonateClient
0x1400868f8  nop     dword ptr [rax+rax+00h]
0x1400868fd  test    eax, eax
0x1400868ff  jle     short loc_14008690B
0x140086901  movzx   eax, ax
0x140086904  or      eax, 80070000h
0x140086909  test    eax, eax
0x14008690b  js      short loc_140086913
0x14008690d  mov     rdi, rbx
0x140086910  mov     sil, 1
0x140086913  mov     rcx, rbx; void *
0x140086916  call    ?IsLocalCall@@YA_NPEAX@Z; IsLocalCall(void *)
0x14008691b  test    al, al
0x14008691d  jz      short loc_140086950
0x14008691f  lea     rdx, aLocalClientNoU; "Local client, no UAL collection"
0x140086926  lea     rcx, aUalcollectdata; "UalCollectData"
0x14008692d  call    ?WriteDbgTraceInfo@UalPrintTelemetry@@SAXPEADPEAGZZ; UalPrintTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140086932  test    sil, sil
0x140086935  jz      short loc_140086946
0x140086937  mov     rcx, rdi; BindingHandle
0x14008693a  call    cs:__imp_RpcRevertToSelfEx
0x140086941  nop     dword ptr [rax+rax+00h]
0x140086946  mov     eax, 1
0x14008694b  jmp     loc_140086ABB
0x140086950  xor     edx, edx; Val
0x140086952  lea     rcx, [rsp+3B0h+var_36C]; void *
0x140086957  mov     r8d, 29Ch; Size
0x14008695d  call    memset_0
0x140086962  movups  xmm0, cs:SumGuid_FAX
0x140086969  mov     r12d, 2
0x14008696f  mov     [rsp+3B0h+var_380], 2B0h
0x140086977  lea     r8, [rsp+3B0h+nSize]; nSize
0x14008697c  mov     [rsp+3B0h+nSize], 104h
0x140086984  lea     rdx, [rbp+2B0h+NameBuffer]; lpNameBuffer
0x140086988  mov     ecx, r12d; NameFormat
0x14008698b  movdqu  [rsp+3B0h+var_37C], xmm0
0x140086991  call    cs:__imp_GetUserNameExW
0x140086998  nop     dword ptr [rax+rax+00h]
0x14008699d  test    al, al
0x14008699f  jnz     short loc_1400869CF
0x1400869a1  call    cs:__imp_GetLastError
0x1400869a8  nop     dword ptr [rax+rax+00h]
0x1400869ad  test    eax, eax
0x1400869af  jle     short loc_1400869B9
0x1400869b1  movzx   eax, ax
0x1400869b4  or      eax, 80070000h
0x1400869b9  mov     r8d, eax
0x1400869bc  lea     rdx, aFailedToCollec_0; "Failed to collect username: hr: 0x%x"
0x1400869c3  lea     rcx, aUalcollectdata; "UalCollectData"
0x1400869ca  call    ?WriteDbgTraceError@UalPrintTelemetry@@SAXPEADPEAGZZ; UalPrintTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400869cf  lea     rdx, [rbp+2B0h+AddressString]; unsigned __int16 *
0x1400869d6  mov     rcx, rbx; void *
0x1400869d9  call    ?GetIpAddressFromRpc@@YAJPEAXPEAGK@Z; GetIpAddressFromRpc(void *,ushort *,ulong)
0x1400869de  mov     ebx, eax
0x1400869e0  test    eax, eax
0x1400869e2  js      short loc_140086A50
0x1400869e4  lea     r9, [rsp+3B0h+Port]; Port
0x1400869e9  lea     r8, [rsp+3B0h+ScopeId]; ScopeId
0x1400869ee  lea     rdx, [rsp+3B0h+Address]; Address
0x1400869f3  lea     rcx, [rbp+2B0h+AddressString]; AddressString
0x1400869fa  call    cs:__imp_RtlIpv6StringToAddressExW
0x140086a01  nop     dword ptr [rax+rax+00h]
0x140086a06  mov     ebx, 10000000h
0x140086a0b  or      eax, ebx
0x140086a0d  jl      short loc_140086A1B
0x140086a0f  mov     ecx, 17h
0x140086a14  mov     [rsp+3B0h+var_358], cx
0x140086a19  jmp     short loc_140086A44
0x140086a1b  lea     r9, [rsp+3B0h+Port]; Port
0x140086a20  xor     edx, edx; Strict
0x140086a22  lea     r8, [rsp+3B0h+var_354]; Address
0x140086a27  lea     rcx, [rbp+2B0h+AddressString]; AddressString
0x140086a2e  call    cs:__imp_RtlIpv4StringToAddressExW
0x140086a35  nop     dword ptr [rax+rax+00h]
0x140086a3a  or      eax, ebx
0x140086a3c  jl      short loc_140086A44
0x140086a3e  mov     [rsp+3B0h+var_358], r12w
0x140086a44  test    eax, eax
0x140086a46  mov     ebx, r14d
0x140086a49  cmovs   ebx, eax
0x140086a4c  test    ebx, ebx
0x140086a4e  jns     short loc_140086A78
0x140086a50  mov     r8d, ebx
0x140086a53  lea     rdx, aFailedToCollec; "Failed to collect IP address: hr: 0x%x"
0x140086a5a  lea     rcx, aUalcollectdata; "UalCollectData"
0x140086a61  call    ?WriteDbgTraceInfo@UalPrintTelemetry@@SAXPEADPEAGZZ; UalPrintTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140086a66  mov     [rsp+3B0h+var_358], r12w
0x140086a6c  mov     dword ptr [rsp+3B0h+var_354.S_un], r14d
0x140086a71  cmp     [rbp+2B0h+NameBuffer], r14w
0x140086a76  jz      short loc_140086AA5
0x140086a78  mov     rax, cs:?fnUalInstrument@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA; long (*fnUalInstrument)(tagUAL_DATA_BLOB *)
0x140086a7f  lea     rcx, [rsp+3B0h+var_380]
0x140086a84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140086a89  mov     ebx, eax
0x140086a8b  test    eax, eax
0x140086a8d  jns     short loc_140086AA5
0x140086a8f  mov     r8d, eax
0x140086a92  lea     rdx, aFailedToLogUal; "Failed to log UAL data: hr: 0x%x"
0x140086a99  lea     rcx, aUalcollectdata; "UalCollectData"
0x140086aa0  call    ?WriteDbgTraceError@UalPrintTelemetry@@SAXPEADPEAGZZ; UalPrintTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140086aa5  test    sil, sil
0x140086aa8  jz      short loc_140086AB9
0x140086aaa  mov     rcx, rdi; BindingHandle
0x140086aad  call    cs:__imp_RpcRevertToSelfEx
0x140086ab4  nop     dword ptr [rax+rax+00h]
0x140086ab9  mov     eax, ebx
0x140086abb  mov     rcx, [rbp+2B0h+var_40]
0x140086ac2  xor     rcx, rsp; StackCookie
0x140086ac5  call    __security_check_cookie
0x140086aca  add     rsp, 388h
0x140086ad1  pop     r14
0x140086ad3  pop     r12
0x140086ad5  pop     rdi
0x140086ad6  pop     rsi
0x140086ad7  pop     rbx
0x140086ad8  pop     rbp
0x140086ad9  retn
```
