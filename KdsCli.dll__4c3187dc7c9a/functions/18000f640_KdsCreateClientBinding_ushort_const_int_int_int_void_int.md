# KdsCreateClientBinding(ushort const *,int,int,int,void * *,int *)

- ea: `0x18000f640`
- end: `0x18000f9e7`
- name: `?KdsCreateClientBinding@@YAJPEBGHHHPEAPEAXPEAH@Z`
- size: `935`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, int, int, void **, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000edb8`
- `0x18000ef64`

## callees

- `0x180001630`
- `0x18000f1a8`
- `0x18000f47c`
- `0x18000f640`
- `0x180010708`
- `0x180010950`
- `0x18001a450`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f9b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f9b8`
- `ntdll!NtSetInformationThread` at `0x18000f708`
- `ntdll!NtSetInformationThread` at `0x18000f7b9`
- `ntdll!NtSetInformationThread` at `0x18000f93b`
- `ntdll!NtSetInformationThread` at `0x18000f708`
- `ntdll!NtSetInformationThread` at `0x18000f7b9`
- `ntdll!NtSetInformationThread` at `0x18000f93b`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000f8e7`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000f8e7`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000f81f`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000f81f`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000f84d`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000f84d`
- `RPCRT4!RpcEpResolveBinding` at `0x18000f879`
- `RPCRT4!RpcEpResolveBinding` at `0x18000f879`
- `RPCRT4!RpcStringFreeW` at `0x18000f98b`
- `RPCRT4!RpcStringFreeW` at `0x18000f98b`
- `RPCRT4!RpcBindingFree` at `0x18000f9a9`
- `RPCRT4!RpcBindingFree` at `0x18000f9a9`

## string_xrefs

- `0x18000f6d9`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyrpccommon.cxx`
- `0x18000f71a`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyrpccommon.cxx`
- `0x18000f77d`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyrpccommon.cxx`

## pseudocode

```c
__int64 __fastcall KdsCreateClientBinding(const unsigned __int16 *a1, int a2, int a3, int a4, void **a5, int *a6)
{
  int v9; // esi
  signed int v10; // eax
  unsigned int v11; // ebx
  NTSTATUS v12; // eax
  NTSTATUS v13; // ebx
  int DomainControllerInfo; // eax
  unsigned __int16 *v15; // r15
  void *v16; // r12
  unsigned int v17; // r9d
  unsigned int v18; // ecx
  NTSTATUS v19; // eax
  NTSTATUS v20; // ebx
  RPC_STATUS v21; // eax
  RPC_STATUS v22; // eax
  RPC_STATUS v23; // eax
  int v24; // r14d
  RPC_STATUS v25; // eax
  NTSTATUS v26; // eax
  NTSTATUS v27; // esi
  RPC_BINDING_HANDLE Binding; // [rsp+40h] [rbp-59h] BYREF
  int v30; // [rsp+48h] [rbp-51h] BYREF
  RPC_WSTR String; // [rsp+50h] [rbp-49h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-41h] BYREF
  RPC_WSTR ServerPrincName; // [rsp+60h] [rbp-39h] BYREF
  RPC_WSTR NetworkAddr; // [rsp+68h] [rbp-31h] BYREF
  void *lpMem; // [rsp+70h] [rbp-29h] BYREF
  __int64 ThreadInformation; // [rsp+78h] [rbp-21h] BYREF
  unsigned __int64 v37; // [rsp+80h] [rbp-19h] BYREF
  unsigned __int64 v38; // [rsp+88h] [rbp-11h] BYREF
  int *v39; // [rsp+90h] [rbp-9h]
  RPC_SECURITY_QOS SecurityQOS; // [rsp+98h] [rbp-1h] BYREF

  v39 = a6;
  Binding = 0;
  NetworkAddr = 0;
  *a5 = 0;
  v9 = 0;
  *a6 = 0;
  lpMem = 0;
  v38 = 0;
  v37 = 0;
  v30 = 0;
  String = 0;
  ServerPrincName = 0;
  ThreadInformation = 0;
  hObject = 0;
  SecurityQOS = 0;
  if ( a2 )
  {
    v10 = OpenCallerToken(0xEu, &hObject);
    v11 = v10;
    if ( v10 < 0 )
    {
      SidKeyDebugTraceError(v10, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyrpccommon.cxx", 0x205u);
      goto LABEL_46;
    }
    v12 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
    v13 = v12;
    if ( v12 < 0 )
    {
      SidKeyDebugTraceError(
        v12,
        "status",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyrpccommon.cxx",
        0x213u);
      v11 = v13 | 0x10000000;
      goto LABEL_46;
    }
    v9 = 1;
  }
  DomainControllerInfo = GetDomainControllerInfo(
                           a3,
                           a4,
                           a1,
                           &NetworkAddr,
                           &v38,
                           (unsigned __int16 **)&lpMem,
                           &v37,
                           &v30);
  v15 = NetworkAddr;
  v11 = DomainControllerInfo;
  v16 = lpMem;
  if ( DomainControllerInfo < 0 )
  {
    v17 = 550;
LABEL_9:
    v18 = DomainControllerInfo;
LABEL_10:
    SidKeyDebugTraceError(v18, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyrpccommon.cxx", v17);
    goto LABEL_38;
  }
  if ( v9 )
  {
    v9 = 0;
    v19 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &hObject, 8u);
    v20 = v19;
    if ( v19 < 0 )
    {
      SidKeyDebugTraceError(
        v19,
        "status",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyrpccommon.cxx",
        0x236u);
      goto LABEL_41;
    }
  }
  DomainControllerInfo = GetSPN(v15, v16, &ServerPrincName);
  v11 = DomainControllerInfo;
  if ( DomainControllerInfo < 0 )
  {
    v17 = 579;
    goto LABEL_9;
  }
  v21 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_ip_tcp", v15, 0, 0, &String);
  if ( v21 )
  {
    if ( v21 > 0 )
      v11 = (unsigned __int16)v21 | 0x80070000;
    else
      v11 = v21;
    v17 = 593;
LABEL_21:
    v18 = v11;
    goto LABEL_10;
  }
  v22 = RpcBindingFromStringBindingW(String, &Binding);
  if ( v22 )
  {
    if ( v22 > 0 )
      v11 = (unsigned __int16)v22 | 0x80070000;
    else
      v11 = v22;
    v17 = 604;
    goto LABEL_21;
  }
  v23 = RpcEpResolveBinding(Binding, qword_18001C2F0);
  if ( v23 )
  {
    if ( v23 > 0 )
      v11 = (unsigned __int16)v23 | 0x80070000;
    else
      v11 = v23;
    v17 = 614;
    goto LABEL_21;
  }
  v24 = v30;
  SecurityQOS.Version = 1;
  SecurityQOS.Capabilities = 1;
  SecurityQOS.IdentityTracking = 1;
  SecurityQOS.ImpersonationType = (v30 != 0) + 2;
  v25 = RpcBindingSetAuthInfoExW(Binding, ServerPrincName, 6u, 9u, 0, 0, &SecurityQOS);
  if ( v25 )
  {
    if ( v25 > 0 )
      v11 = (unsigned __int16)v25 | 0x80070000;
    else
      v11 = v25;
    v17 = 635;
    goto LABEL_21;
  }
  *a5 = Binding;
  Binding = 0;
  *v39 = v24;
LABEL_38:
  if ( !v9 )
    goto LABEL_42;
  v26 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &hObject, 8u);
  v27 = v26;
  if ( v26 >= 0 )
    goto LABEL_42;
  SidKeyDebugTraceError(v26, "status", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyrpccommon.cxx", 0x290u);
  v20 = v27;
LABEL_41:
  v11 = v20 | 0x10000000;
LABEL_42:
  if ( v15 )
    SIDKeyProvFree(v15);
  if ( v16 )
    SIDKeyProvFree(v16);
LABEL_46:
  if ( String )
    RpcStringFreeW(&String);
  if ( ServerPrincName )
    SIDKeyProvFree(ServerPrincName);
  if ( Binding )
    RpcBindingFree(&Binding);
  if ( hObject )
    CloseHandle(hObject);
  return v11;
}

```

## disassembly

```asm
0x18000f640  mov     [rsp-8+arg_8], rbx
0x18000f645  push    rbp
0x18000f646  push    rsi
0x18000f647  push    rdi
0x18000f648  push    r12
0x18000f64a  push    r13
0x18000f64c  push    r14
0x18000f64e  push    r15
0x18000f650  lea     rbp, [rsp-17h]
0x18000f655  sub     rsp, 0B0h
0x18000f65c  mov     rax, cs:__security_cookie
0x18000f663  xor     rax, rsp
0x18000f666  mov     [rbp+47h+var_38], rax
0x18000f66a  mov     rax, [rbp+47h+arg_28]
0x18000f66e  xor     r12d, r12d
0x18000f671  mov     r13, [rbp+47h+arg_20]
0x18000f675  xorps   xmm0, xmm0
0x18000f678  mov     [rbp+47h+var_50], rax
0x18000f67c  mov     r15d, r9d
0x18000f67f  mov     [rbp+47h+Binding], r12
0x18000f683  mov     r14d, r8d
0x18000f686  mov     [rbp+47h+NetworkAddr], r12
0x18000f68a  mov     rdi, rcx
0x18000f68d  mov     [r13+0], r12
0x18000f691  mov     esi, r12d
0x18000f694  mov     [rax], r12d
0x18000f697  mov     [rbp+47h+lpMem], r12
0x18000f69b  mov     [rbp+47h+var_58], r12
0x18000f69f  mov     [rbp+47h+var_60], r12
0x18000f6a3  mov     [rbp+47h+var_98], r12d
0x18000f6a7  mov     [rbp+47h+String], r12
0x18000f6ab  mov     [rbp+47h+ServerPrincName], r12
0x18000f6af  mov     [rbp+47h+ThreadInformation], r12
0x18000f6b3  mov     [rbp+47h+hObject], r12
0x18000f6b7  movups  xmmword ptr [rbp+47h+var_48.Version], xmm0
0x18000f6bb  test    edx, edx
0x18000f6bd  jz      short loc_18000F73D
0x18000f6bf  lea     rdx, [rbp+47h+hObject]; void **
0x18000f6c3  lea     ecx, [r12+0Eh]; DesiredAccess
0x18000f6c8  call    ?OpenCallerToken@@YAJKPEAPEAX@Z; OpenCallerToken(ulong,void * *)
0x18000f6cd  mov     ebx, eax
0x18000f6cf  test    eax, eax
0x18000f6d1  jns     short loc_18000F6F3
0x18000f6d3  mov     r9d, 205h; unsigned int
0x18000f6d9  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000f6e0  lea     rdx, aHr; "hr"
0x18000f6e7  mov     ecx, eax; unsigned int
0x18000f6e9  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000f6ee  jmp     loc_18000F981
0x18000f6f3  mov     r9d, 8; ThreadInformationLength
0x18000f6f9  lea     r8, [rbp+47h+ThreadInformation]; ThreadInformation
0x18000f6fd  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000f704  lea     edx, [r9-3]; ThreadInformationClass
0x18000f708  call    cs:__imp_NtSetInformationThread
0x18000f70e  mov     ebx, eax
0x18000f710  test    eax, eax
0x18000f712  jns     short loc_18000F738
0x18000f714  mov     r9d, 213h; unsigned int
0x18000f71a  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000f721  lea     rdx, aStatus; "status"
0x18000f728  mov     ecx, eax; unsigned int
0x18000f72a  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000f72f  bts     ebx, 1Ch
0x18000f733  jmp     loc_18000F981
0x18000f738  mov     esi, 1
0x18000f73d  lea     rax, [rbp+47h+var_98]
0x18000f741  mov     r8, rdi; unsigned __int16 *
0x18000f744  mov     [rsp+0E0h+var_A8], rax; int *
0x18000f749  lea     r9, [rbp+47h+NetworkAddr]; unsigned __int16 **
0x18000f74d  lea     rax, [rbp+47h+var_60]
0x18000f751  mov     edx, r15d; int
0x18000f754  mov     [rsp+0E0h+SecurityQOS], rax; unsigned __int64 *
0x18000f759  mov     ecx, r14d; int
0x18000f75c  lea     rax, [rbp+47h+lpMem]
0x18000f760  mov     [rsp+0E0h+StringBinding], rax; unsigned __int16 **
0x18000f765  lea     rax, [rbp+47h+var_58]
0x18000f769  mov     [rsp+0E0h+Options], rax; unsigned __int64 *
0x18000f76e  call    ?GetDomainControllerInfo@@YAJHHPEBGPEAPEAGPEA_K12PEAH@Z; GetDomainControllerInfo(int,int,ushort const *,ushort * *,unsigned __int64 *,ushort * *,unsigned __int64 *,int *)
0x18000f773  mov     r15, [rbp+47h+NetworkAddr]
0x18000f777  mov     ebx, eax
0x18000f779  mov     r12, [rbp+47h+lpMem]
0x18000f77d  lea     rdi, aOnecoreDsSecur_0; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000f784  test    eax, eax
0x18000f786  jns     short loc_18000F7A4
0x18000f788  mov     r9d, 226h; unsigned int
0x18000f78e  mov     ecx, eax; unsigned int
0x18000f790  lea     rdx, aHr; "hr"
0x18000f797  mov     r8, rdi; char *
0x18000f79a  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000f79f  jmp     loc_18000F922
0x18000f7a4  test    esi, esi
0x18000f7a6  jz      short loc_18000F7E1
0x18000f7a8  xor     esi, esi
0x18000f7aa  lea     r8, [rbp+47h+hObject]; ThreadInformation
0x18000f7ae  lea     r9d, [rsi+8]; ThreadInformationLength
0x18000f7b2  lea     edx, [rsi+5]; ThreadInformationClass
0x18000f7b5  lea     rcx, [rsi-2]; ThreadHandle
0x18000f7b9  call    cs:__imp_NtSetInformationThread
0x18000f7bf  mov     ebx, eax
0x18000f7c1  test    eax, eax
0x18000f7c3  jns     short loc_18000F7E1
0x18000f7c5  mov     r9d, 236h; unsigned int
0x18000f7cb  lea     rdx, aStatus; "status"
0x18000f7d2  mov     r8, rdi; char *
0x18000f7d5  mov     ecx, eax; unsigned int
0x18000f7d7  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000f7dc  jmp     loc_18000F960
0x18000f7e1  lea     r8, [rbp+47h+ServerPrincName]
0x18000f7e5  mov     rdx, r12
0x18000f7e8  mov     rcx, r15
0x18000f7eb  call    GetSPN
0x18000f7f0  mov     ebx, eax
0x18000f7f2  test    eax, eax
0x18000f7f4  jns     short loc_18000F7FE
0x18000f7f6  mov     r9d, 243h
0x18000f7fc  jmp     short loc_18000F78E
0x18000f7fe  lea     rax, [rbp+47h+String]
0x18000f802  xor     r9d, r9d; Endpoint
0x18000f805  mov     [rsp+0E0h+StringBinding], rax; StringBinding
0x18000f80a  lea     rdx, ProtSeq; "ncacn_ip_tcp"
0x18000f811  mov     r8, r15; NetworkAddr
0x18000f814  mov     [rsp+0E0h+Options], 0; Options
0x18000f81d  xor     ecx, ecx; ObjUuid
0x18000f81f  call    cs:__imp_RpcStringBindingComposeW
0x18000f825  test    eax, eax
0x18000f827  jz      short loc_18000F845
0x18000f829  jg      short loc_18000F82F
0x18000f82b  mov     ebx, eax
0x18000f82d  jmp     short loc_18000F838
0x18000f82f  movzx   ebx, ax
0x18000f832  or      ebx, 80070000h
0x18000f838  mov     r9d, 251h
0x18000f83e  mov     ecx, ebx
0x18000f840  jmp     loc_18000F790
0x18000f845  mov     rcx, [rbp+47h+String]; StringBinding
0x18000f849  lea     rdx, [rbp+47h+Binding]; Binding
0x18000f84d  call    cs:__imp_RpcBindingFromStringBindingW
0x18000f853  test    eax, eax
0x18000f855  jz      short loc_18000F86E
0x18000f857  jg      short loc_18000F85D
0x18000f859  mov     ebx, eax
0x18000f85b  jmp     short loc_18000F866
0x18000f85d  movzx   ebx, ax
0x18000f860  or      ebx, 80070000h
0x18000f866  mov     r9d, 25Ch
0x18000f86c  jmp     short loc_18000F83E
0x18000f86e  mov     rcx, [rbp+47h+Binding]; Binding
0x18000f872  lea     rdx, qword_18001C2F0; IfSpec
0x18000f879  call    cs:__imp_RpcEpResolveBinding
0x18000f87f  test    eax, eax
0x18000f881  jz      short loc_18000F89A
0x18000f883  jg      short loc_18000F889
0x18000f885  mov     ebx, eax
0x18000f887  jmp     short loc_18000F892
0x18000f889  movzx   ebx, ax
0x18000f88c  or      ebx, 80070000h
0x18000f892  mov     r9d, 266h
0x18000f898  jmp     short loc_18000F83E
0x18000f89a  mov     r14d, [rbp+47h+var_98]
0x18000f89e  mov     eax, 1
0x18000f8a3  mov     rdx, [rbp+47h+ServerPrincName]; ServerPrincName
0x18000f8a7  mov     r9d, 9; AuthnSvc
0x18000f8ad  mov     [rbp+47h+var_48.Version], eax
0x18000f8b0  mov     [rbp+47h+var_48.Capabilities], eax
0x18000f8b3  mov     [rbp+47h+var_48.IdentityTracking], eax
0x18000f8b6  mov     eax, r14d
0x18000f8b9  neg     eax
0x18000f8bb  lea     r8d, [r9-3]; AuthnLevel
0x18000f8bf  lea     rax, [rbp+47h+var_48]
0x18000f8c3  sbb     ecx, ecx
0x18000f8c5  mov     [rsp+0E0h+SecurityQOS], rax; SecurityQOS
0x18000f8ca  neg     ecx
0x18000f8cc  mov     dword ptr [rsp+0E0h+StringBinding], 0; AuthzSvc
0x18000f8d4  add     ecx, 2
0x18000f8d7  mov     [rsp+0E0h+Options], 0; AuthIdentity
0x18000f8e0  mov     [rbp+47h+var_48.ImpersonationType], ecx
0x18000f8e3  mov     rcx, [rbp+47h+Binding]; Binding
0x18000f8e7  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18000f8ed  test    eax, eax
0x18000f8ef  jz      short loc_18000F90B
0x18000f8f1  jg      short loc_18000F8F7
0x18000f8f3  mov     ebx, eax
0x18000f8f5  jmp     short loc_18000F900
0x18000f8f7  movzx   ebx, ax
0x18000f8fa  or      ebx, 80070000h
0x18000f900  mov     r9d, 27Bh
0x18000f906  jmp     loc_18000F83E
0x18000f90b  mov     rax, [rbp+47h+Binding]
0x18000f90f  mov     [r13+0], rax
0x18000f913  mov     rax, [rbp+47h+var_50]
0x18000f917  mov     [rbp+47h+Binding], 0
0x18000f91f  mov     [rax], r14d
0x18000f922  test    esi, esi
0x18000f924  jz      short loc_18000F964
0x18000f926  mov     r9d, 8; ThreadInformationLength
0x18000f92c  lea     r8, [rbp+47h+hObject]; ThreadInformation
0x18000f930  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000f937  lea     edx, [r9-3]; ThreadInformationClass
0x18000f93b  call    cs:__imp_NtSetInformationThread
0x18000f941  mov     esi, eax
0x18000f943  test    eax, eax
0x18000f945  jns     short loc_18000F964
0x18000f947  mov     r9d, 290h; unsigned int
0x18000f94d  lea     rdx, aStatus; "status"
0x18000f954  mov     r8, rdi; char *
0x18000f957  mov     ecx, eax; unsigned int
0x18000f959  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000f95e  mov     ebx, esi
0x18000f960  bts     ebx, 1Ch
0x18000f964  test    r15, r15
0x18000f967  jz      short loc_18000F971
0x18000f969  mov     rcx, r15; lpMem
0x18000f96c  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000f971  test    r12, r12
0x18000f974  jz      short loc_18000F97E
0x18000f976  mov     rcx, r12; lpMem
0x18000f979  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000f97e  xor     r12d, r12d
0x18000f981  cmp     [rbp+47h+String], r12
0x18000f985  jz      short loc_18000F991
0x18000f987  lea     rcx, [rbp+47h+String]; String
0x18000f98b  call    cs:__imp_RpcStringFreeW
0x18000f991  mov     rcx, [rbp+47h+ServerPrincName]; lpMem
0x18000f995  test    rcx, rcx
0x18000f998  jz      short loc_18000F99F
0x18000f99a  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000f99f  cmp     [rbp+47h+Binding], r12
0x18000f9a3  jz      short loc_18000F9AF
0x18000f9a5  lea     rcx, [rbp+47h+Binding]; Binding
0x18000f9a9  call    cs:__imp_RpcBindingFree
0x18000f9af  mov     rcx, [rbp+47h+hObject]; hObject
0x18000f9b3  test    rcx, rcx
0x18000f9b6  jz      short loc_18000F9BE
0x18000f9b8  call    cs:__imp_CloseHandle
0x18000f9be  mov     eax, ebx
0x18000f9c0  mov     rcx, [rbp+47h+var_38]
0x18000f9c4  xor     rcx, rsp; StackCookie
0x18000f9c7  call    __security_check_cookie
0x18000f9cc  mov     rbx, [rsp+0E0h+arg_8]
0x18000f9d4  add     rsp, 0B0h
0x18000f9db  pop     r15
0x18000f9dd  pop     r14
0x18000f9df  pop     r13
0x18000f9e1  pop     r12
0x18000f9e3  pop     rdi
0x18000f9e4  pop     rsi
0x18000f9e5  pop     rbp
0x18000f9e6  retn
```
