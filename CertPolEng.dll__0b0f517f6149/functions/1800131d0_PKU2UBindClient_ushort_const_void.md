# PKU2UBindClient(ushort const *,void * *)

- ea: `0x1800131d0`
- end: `0x1800133fc`
- name: `?PKU2UBindClient@@YAKPEBGPEAPEAX@Z`
- size: `556`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180013404`

## callees

- `0x180009190`
- `0x18000c344`
- `0x1800131d0`
- `0x18001a380`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013327`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013327`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18001338b`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18001338b`
- `RPCRT4!RpcStringBindingComposeW` at `0x180013274`
- `RPCRT4!RpcStringBindingComposeW` at `0x180013274`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800132a5`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800132a5`
- `RPCRT4!RpcStringFreeW` at `0x1800133cf`
- `RPCRT4!RpcStringFreeW` at `0x18001aa3c`
- `RPCRT4!RpcStringFreeW` at `0x1800133cf`
- `RPCRT4!RpcStringFreeW` at `0x18001aa3c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800132da`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800132da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800133bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001aa2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800133bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001aa2a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001331d`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001331d`

## string_xrefs

- `0x180013291`: `RpcStringBindingCompose`
- `0x18001333c`: `CreateWellKnownSid`

## pseudocode

```c
__int64 __fastcall PKU2UBindClient(const unsigned __int16 *a1, void **a2)
{
  void *v3; // rdi
  unsigned int v4; // ebx
  DWORD LastError; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  const char *v8; // r8
  HLOCAL v9; // rax
  __int64 v10; // r9
  RPC_WSTR String; // [rsp+48h] [rbp-270h] BYREF
  DWORD cbSid; // [rsp+50h] [rbp-268h] BYREF
  HLOCAL v14; // [rsp+58h] [rbp-260h]
  RPC_SECURITY_QOS SecurityQOS; // [rsp+60h] [rbp-258h] BYREF
  __int128 v16; // [rsp+70h] [rbp-248h]
  void *v17; // [rsp+80h] [rbp-238h]
  unsigned __int16 Endpoint[264]; // [rsp+90h] [rbp-228h] BYREF

  String = 0;
  v3 = 0;
  v14 = 0;
  SecurityQOS = 0;
  v16 = 0;
  v17 = 0;
  cbSid = 0;
  if ( (int)StringCchPrintfW(Endpoint, 0x104u, L"%s", a1) < 0 )
  {
    v4 = 122;
    goto LABEL_20;
  }
  LastError = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, Endpoint, 0, &String);
  v4 = LastError;
  if ( LastError )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) == 0 )
      goto LABEL_20;
    v8 = "RpcStringBindingCompose";
    goto LABEL_18;
  }
  LastError = RpcBindingFromStringBindingW(String, a2);
  v4 = LastError;
  if ( LastError )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) == 0 )
      goto LABEL_20;
    v8 = "RpcBindingFromStringBinding";
    goto LABEL_18;
  }
  cbSid = 68;
  v9 = LocalAlloc(0x40u, 0x44u);
  v3 = v9;
  v14 = v9;
  if ( !v9 )
  {
    v4 = 8;
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) == 0 )
      goto LABEL_20;
    v10 = 8;
    v8 = "LocalAlloc";
    goto LABEL_19;
  }
  if ( !CreateWellKnownSid(WinLocalSystemSid, 0, v9, &cbSid) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) == 0 )
      goto LABEL_20;
    v8 = "CreateWellKnownSid";
    goto LABEL_18;
  }
  SecurityQOS.Version = 3;
  *(_QWORD *)&SecurityQOS.Capabilities = 17;
  SecurityQOS.ImpersonationType = 3;
  v17 = v3;
  LastError = RpcBindingSetAuthInfoExW(*a2, 0, 6u, 0xAu, 0, 0, &SecurityQOS);
  v4 = LastError;
  if ( LastError && (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
  {
    v8 = "RpcBindingSetAuthInfoEx";
LABEL_18:
    v10 = LastError;
LABEL_19:
    McTemplateU0sq_EtwEventWriteTransfer(v7, v6, v8, v10);
  }
LABEL_20:
  if ( v3 )
    LocalFree(v3);
  if ( String )
    RpcStringFreeW(&String);
  return v4;
}

```

## disassembly

```asm
0x1800131d0  mov     r11, rsp
0x1800131d3  mov     [r11+18h], rbx
0x1800131d7  mov     [r11+20h], rsi
0x1800131db  push    rdi
0x1800131dc  sub     rsp, 2B0h
0x1800131e3  mov     rax, cs:__security_cookie
0x1800131ea  xor     rax, rsp
0x1800131ed  mov     [rsp+2B8h+var_18], rax
0x1800131f5  mov     rsi, rdx
0x1800131f8  mov     [rsp+2B8h+String], 0
0x180013201  xor     edi, edi
0x180013203  mov     [rsp+2B8h+var_260], rdi
0x180013208  xorps   xmm0, xmm0
0x18001320b  xor     eax, eax
0x18001320d  movups  xmmword ptr [rsp+2B8h+var_258.Version], xmm0
0x180013212  movups  [rsp+2B8h+var_248], xmm0
0x180013217  mov     [r11-238h], rax
0x18001321e  mov     [rsp+2B8h+cbSid], eax
0x180013222  mov     r9, rcx
0x180013225  lea     r8, aS; "%s"
0x18001322c  mov     edx, 104h; unsigned __int64
0x180013231  lea     rcx, [r11-228h]; unsigned __int16 *
0x180013238  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001323d  test    eax, eax
0x18001323f  jns     short loc_18001324D
0x180013241  lea     ebx, [rdi+7Ah]
0x180013244  mov     [rsp+2B8h+var_278], ebx
0x180013248  jmp     loc_1800133B4
0x18001324d  lea     rax, [rsp+2B8h+String]
0x180013252  mov     [rsp+2B8h+StringBinding], rax; StringBinding
0x180013257  mov     [rsp+2B8h+Options], 0; Options
0x180013260  lea     r9, [rsp+2B8h+Endpoint]; Endpoint
0x180013268  xor     r8d, r8d; NetworkAddr
0x18001326b  lea     rdx, ProtSeq; "ncalrpc"
0x180013272  xor     ecx, ecx; ObjUuid
0x180013274  call    cs:__imp_RpcStringBindingComposeW
0x18001327a  mov     ebx, eax
0x18001327c  mov     [rsp+2B8h+var_278], eax
0x180013280  test    eax, eax
0x180013282  jz      short loc_18001329D
0x180013284  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x18001328b  jz      loc_1800133B4
0x180013291  lea     r8, aRpcstringbindi; "RpcStringBindingCompose"
0x180013298  jmp     loc_1800133AB
0x18001329d  mov     rdx, rsi; Binding
0x1800132a0  mov     rcx, [rsp+2B8h+String]; StringBinding
0x1800132a5  call    cs:__imp_RpcBindingFromStringBindingW
0x1800132ab  mov     ebx, eax
0x1800132ad  mov     [rsp+2B8h+var_278], eax
0x1800132b1  test    eax, eax
0x1800132b3  jz      short loc_1800132CE
0x1800132b5  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x1800132bc  jz      loc_1800133B4
0x1800132c2  lea     r8, aRpcbindingfrom; "RpcBindingFromStringBinding"
0x1800132c9  jmp     loc_1800133AB
0x1800132ce  mov     edx, 44h ; 'D'; uBytes
0x1800132d3  mov     [rsp+2B8h+cbSid], edx
0x1800132d7  lea     ecx, [rdx-4]; uFlags
0x1800132da  call    cs:__imp_LocalAlloc
0x1800132e0  mov     rdi, rax
0x1800132e3  mov     [rsp+2B8h+var_260], rax
0x1800132e8  test    rax, rax
0x1800132eb  jnz     short loc_180013310
0x1800132ed  lea     ebx, [rax+8]
0x1800132f0  mov     [rsp+2B8h+var_278], ebx
0x1800132f4  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x1800132fb  jz      loc_1800133B4
0x180013301  mov     r9d, ebx
0x180013304  lea     r8, aLocalalloc; "LocalAlloc"
0x18001330b  jmp     loc_1800133AE
0x180013310  lea     r9, [rsp+2B8h+cbSid]; cbSid
0x180013315  mov     r8, rdi; pSid
0x180013318  xor     edx, edx; DomainSid
0x18001331a  lea     ecx, [rdx+16h]; WellKnownSidType
0x18001331d  call    cs:__imp_CreateWellKnownSid
0x180013323  test    eax, eax
0x180013325  jnz     short loc_180013345
0x180013327  call    cs:__imp_GetLastError
0x18001332d  mov     ebx, eax
0x18001332f  mov     [rsp+2B8h+var_278], eax
0x180013333  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x18001333a  jz      short loc_1800133B4
0x18001333c  lea     r8, aCreatewellknow; "CreateWellKnownSid"
0x180013343  jmp     short loc_1800133AB
0x180013345  mov     eax, 3
0x18001334a  mov     [rsp+2B8h+var_258.Version], eax
0x18001334e  mov     qword ptr [rsp+2B8h+var_258.Capabilities], 11h
0x180013357  mov     [rsp+2B8h+var_258.ImpersonationType], eax
0x18001335b  mov     [rsp+2B8h+var_238], rdi
0x180013363  lea     rax, [rsp+2B8h+var_258]
0x180013368  mov     [rsp+2B8h+SecurityQOS], rax; SecurityQOS
0x18001336d  mov     dword ptr [rsp+2B8h+StringBinding], 0; AuthzSvc
0x180013375  mov     [rsp+2B8h+Options], 0; AuthIdentity
0x18001337e  xor     edx, edx; ServerPrincName
0x180013380  lea     r9d, [rdx+0Ah]; AuthnSvc
0x180013384  lea     r8d, [rdx+6]; AuthnLevel
0x180013388  mov     rcx, [rsi]; Binding
0x18001338b  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180013391  mov     ebx, eax
0x180013393  mov     [rsp+2B8h+var_278], eax
0x180013397  test    eax, eax
0x180013399  jz      short loc_1800133B4
0x18001339b  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x1800133a2  jz      short loc_1800133B4
0x1800133a4  lea     r8, aRpcbindingseta; "RpcBindingSetAuthInfoEx"
0x1800133ab  mov     r9d, eax
0x1800133ae  call    McTemplateU0sq_EtwEventWriteTransfer
0x1800133b3  nop
0x1800133b4  test    rdi, rdi
0x1800133b7  jz      short loc_1800133C2
0x1800133b9  mov     rcx, rdi; hMem
0x1800133bc  call    cs:__imp_LocalFree
0x1800133c2  cmp     [rsp+2B8h+String], 0
0x1800133c8  jz      short loc_1800133D5
0x1800133ca  lea     rcx, [rsp+2B8h+String]; String
0x1800133cf  call    cs:__imp_RpcStringFreeW
0x1800133d5  mov     eax, ebx
0x1800133d7  mov     rcx, [rsp+2B8h+var_18]
0x1800133df  xor     rcx, rsp; StackCookie
0x1800133e2  call    __security_check_cookie
0x1800133e7  lea     r11, [rsp+2B8h+var_8]
0x1800133ef  mov     rbx, [r11+20h]
0x1800133f3  mov     rsi, [r11+28h]
0x1800133f7  mov     rsp, r11
0x1800133fa  pop     rdi
0x1800133fb  retn
0x18001aa18  push    rbp
0x18001aa1a  sub     rsp, 40h
0x18001aa1e  mov     rbp, rdx
0x18001aa21  mov     rcx, [rbp+58h]; hMem
0x18001aa25  test    rcx, rcx
0x18001aa28  jz      short loc_18001AA31
0x18001aa2a  call    cs:__imp_LocalFree
0x18001aa30  nop
0x18001aa31  cmp     qword ptr [rbp+48h], 0
0x18001aa36  jz      short loc_18001AA43
0x18001aa38  lea     rcx, [rbp+48h]; String
0x18001aa3c  call    cs:__imp_RpcStringFreeW
0x18001aa42  nop
0x18001aa43  add     rsp, 40h
0x18001aa47  pop     rbp
0x18001aa48  retn
```
