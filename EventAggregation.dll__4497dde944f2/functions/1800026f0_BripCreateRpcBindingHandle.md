# BripCreateRpcBindingHandle

- ea: `0x1800026f0`
- end: `0x1800028fd`
- name: `BripCreateRpcBindingHandle`
- size: `525`
- prototype: `__int64 __fastcall(void *Source1)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002130`
- `0x1800022b0`
- `0x180008d98`

## callees

- `0x1800026f0`
- `0x180002910`
- `0x180003070`
- `0x180004480`
- `0x1800072e0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800028e5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800028e5`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000272c`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000272c`
- `ntdll!RtlReleaseSRWLockShared` at `0x180002873`
- `ntdll!RtlReleaseSRWLockShared` at `0x180002873`
- `RPCRT4!RpcBindingFree` at `0x180002859`
- `RPCRT4!RpcBindingFree` at `0x180002859`
- `RPCRT4!RpcBindingBind` at `0x18000283d`
- `RPCRT4!RpcBindingBind` at `0x18000283d`
- `RPCRT4!RpcBindingCreateW` at `0x1800027fc`
- `RPCRT4!RpcBindingCreateW` at `0x1800027fc`
- `RPCRT4!UuidEqual` at `0x18000281c`
- `RPCRT4!UuidEqual` at `0x18000281c`

## pseudocode

```c
__int64 __fastcall BripCreateRpcBindingHandle(UCHAR *Source1, RPC_BINDING_HANDLE *a2)
{
  char v4; // si
  __int64 BindingContextByBrokerId; // rbx
  __int64 v6; // rax
  UUID v7; // xmm0
  unsigned int v8; // ebx
  int v9; // eax
  __int64 *v10; // r8
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-89h] BYREF
  RPC_STATUS Status; // [rsp+28h] [rbp-81h] BYREF
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+30h] [rbp-79h] BYREF
  _DWORD v15[4]; // [rsp+58h] [rbp-51h] BYREF
  __int128 v16; // [rsp+68h] [rbp-41h]
  __int64 v17; // [rsp+78h] [rbp-31h]
  __int64 v18; // [rsp+80h] [rbp-29h]
  __int64 v19; // [rsp+88h] [rbp-21h]
  RPC_BINDING_HANDLE_OPTIONS_V1 Options; // [rsp+90h] [rbp-19h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+A0h] [rbp-9h] BYREF

  *a2 = 0;
  v4 = 0;
  RtlAcquireSRWLockShared(&BrokerBindingTableLock);
  BindingContextByBrokerId = BripFindBindingContextByBrokerId(Source1);
  if ( !BindingContextByBrokerId )
  {
    if ( !(unsigned __int8)EaLibConvertLockSharedToExclusive() )
      BindingContextByBrokerId = BripFindBindingContextByBrokerId(Source1);
    v4 = 1;
    if ( !BindingContextByBrokerId )
    {
      BindingContextByBrokerId = BripCreateBindingContext((const GUID *)Source1);
      if ( !BindingContextByBrokerId )
      {
        v8 = 1710;
LABEL_16:
        dword_180012198 = 0;
        RtlReleaseSRWLockExclusive(&BrokerBindingTableLock);
        return v8;
      }
    }
  }
  v17 = *(_QWORD *)(BindingContextByBrokerId + 40);
  v6 = *(_QWORD *)(BindingContextByBrokerId + 48);
  memset(&Template.ProtocolSequence + 1, 0, 32);
  v19 = v6;
  v16 = 0;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v15;
  v7 = *(UUID *)Source1;
  Binding = 0;
  *(_QWORD *)&Options.ComTimeout = 5;
  v18 = 0;
  *(_QWORD *)(&Security.Version + 1) = 0;
  HIDWORD(Security.ServerPrincName) = 0;
  Security.AuthIdentity = 0;
  Template.Version = 1;
  Template.ProtocolSequence = 3;
  Template.Flags = 1;
  Template.ObjectUuid = v7;
  Options.Version = 1;
  Options.Flags = 1;
  v15[0] = 5;
  v15[1] = 1;
  v15[2] = 1;
  v15[3] = 2;
  Security.Version = 1;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 20;
  v8 = RpcBindingCreateW(&Template, &Security, &Options, &Binding);
  if ( v8 )
    goto LABEL_6;
  Status = 0;
  v9 = UuidEqual((UUID *)Source1, (UUID *)&g_SmsRouterBrokerId, &Status);
  v10 = qword_18000D000;
  if ( !v9 )
    v10 = qword_18000D060;
  v8 = RpcBindingBind(0, Binding, v10);
  if ( v8 )
  {
LABEL_6:
    if ( Binding )
      RpcBindingFree(&Binding);
  }
  else
  {
    *a2 = Binding;
    v8 = 0;
  }
  if ( v4 )
    goto LABEL_16;
  RtlReleaseSRWLockShared(&BrokerBindingTableLock);
  return v8;
}

```

## disassembly

```asm
0x1800026f0  mov     [rsp-8+arg_10], rbx
0x1800026f5  push    rbp
0x1800026f6  push    rsi
0x1800026f7  push    rdi
0x1800026f8  push    r14
0x1800026fa  push    r15
0x1800026fc  lea     rbp, [rsp-37h]
0x180002701  sub     rsp, 0E0h
0x180002708  mov     rax, cs:__security_cookie
0x18000270f  xor     rax, rsp
0x180002712  mov     [rbp+57h+var_28], rax
0x180002716  mov     rdi, rcx
0x180002719  xor     r15d, r15d
0x18000271c  lea     rcx, BrokerBindingTableLock
0x180002723  mov     [rdx], r15
0x180002726  mov     r14, rdx
0x180002729  xor     sil, sil
0x18000272c  call    cs:__imp_RtlAcquireSRWLockShared
0x180002732  mov     rcx, rdi; Source1
0x180002735  call    BripFindBindingContextByBrokerId
0x18000273a  mov     rbx, rax
0x18000273d  test    rax, rax
0x180002740  jz      loc_18000289E
0x180002746  mov     rax, [rbx+28h]
0x18000274a  lea     r9, [rsp+100h+Binding]; Binding
0x18000274f  xorps   xmm0, xmm0
0x180002752  mov     [rbp+57h+var_88], rax
0x180002756  mov     rax, [rbx+30h]
0x18000275a  lea     r8, [rbp+57h+Options]; Options
0x18000275e  movdqu  xmmword ptr [rbp+57h+Template+0Ch], xmm0
0x180002763  mov     [rbp+57h+var_78], rax
0x180002767  lea     rax, [rbp+57h+var_A8]
0x18000276b  movdqu  [rbp+57h+var_98], xmm0
0x180002770  lea     rdx, [rbp+57h+Security]; Security
0x180002774  mov     [rbp+57h+Security.SecurityQos], rax
0x180002778  movups  xmm0, xmmword ptr [rdi]
0x18000277b  mov     [rsp+100h+Binding], r15
0x180002780  lea     rcx, [rbp+57h+Template]; Template
0x180002784  xorps   xmm1, xmm1
0x180002787  mov     qword ptr [rbp+57h+Options.ComTimeout], 5
0x18000278f  movdqu  xmmword ptr [rbp+57h+Template.StringEndpoint+4], xmm1
0x180002794  mov     [rbp+57h+var_80], r15
0x180002798  mov     qword ptr [rbp+57h+Security+4], r15
0x18000279c  mov     dword ptr [rbp+57h+Security.ServerPrincName+4], r15d
0x1800027a0  mov     [rbp+57h+Security.AuthIdentity], r15
0x1800027a4  mov     [rbp+57h+Template.Version], 1
0x1800027ab  mov     [rbp+57h+Template.ProtocolSequence], 3
0x1800027b2  mov     [rbp+57h+Template.Flags], 1
0x1800027b9  movups  xmmword ptr [rbp+57h+Template.ObjectUuid.Data1], xmm0
0x1800027bd  mov     [rbp+57h+Options.Version], 1
0x1800027c4  mov     [rbp+57h+Options.Flags], 1
0x1800027cb  mov     [rbp+57h+var_A8], 5
0x1800027d2  mov     [rbp+57h+var_A4], 1
0x1800027d9  mov     [rbp+57h+var_A0], 1
0x1800027e0  mov     [rbp+57h+var_9C], 2
0x1800027e7  mov     [rbp+57h+Security.Version], 1
0x1800027ee  mov     [rbp+57h+Security.AuthnLevel], 6
0x1800027f5  mov     [rbp+57h+Security.AuthnSvc], 14h
0x1800027fc  call    cs:__imp_RpcBindingCreateW
0x180002802  mov     ebx, eax
0x180002804  test    eax, eax
0x180002806  jnz     short loc_18000284D
0x180002808  lea     r8, [rsp+100h+Status]; Status
0x18000280d  mov     [rsp+100h+Status], r15d
0x180002812  lea     rdx, g_SmsRouterBrokerId; Uuid2
0x180002819  mov     rcx, rdi; Uuid1
0x18000281c  call    cs:__imp_UuidEqual
0x180002822  mov     rdx, [rsp+100h+Binding]; Binding
0x180002827  lea     rcx, qword_18000D060
0x18000282e  test    eax, eax
0x180002830  lea     r8, qword_18000D000
0x180002837  cmovz   r8, rcx; IfSpec
0x18000283b  xor     ecx, ecx; pAsync
0x18000283d  call    cs:__imp_RpcBindingBind
0x180002843  mov     ebx, eax
0x180002845  test    eax, eax
0x180002847  jz      loc_1800028ED
0x18000284d  cmp     [rsp+100h+Binding], r15
0x180002852  jz      short loc_180002867
0x180002854  lea     rcx, [rsp+100h+Binding]; Binding
0x180002859  call    cs:__imp_RpcBindingFree
0x18000285f  test    ebx, ebx
0x180002861  jz      loc_1800028F5
0x180002867  test    sil, sil
0x18000286a  jnz     short loc_1800028D7
0x18000286c  lea     rcx, BrokerBindingTableLock
0x180002873  call    cs:__imp_RtlReleaseSRWLockShared
0x180002879  mov     eax, ebx
0x18000287b  mov     rcx, [rbp+57h+var_28]
0x18000287f  xor     rcx, rsp; StackCookie
0x180002882  call    __security_check_cookie
0x180002887  mov     rbx, [rsp+100h+arg_10]
0x18000288f  add     rsp, 0E0h
0x180002896  pop     r15
0x180002898  pop     r14
0x18000289a  pop     rdi
0x18000289b  pop     rsi
0x18000289c  pop     rbp
0x18000289d  retn
0x18000289e  call    EaLibConvertLockSharedToExclusive
0x1800028a3  test    al, al
0x1800028a5  jnz     short loc_1800028B2
0x1800028a7  mov     rcx, rdi; Source1
0x1800028aa  call    BripFindBindingContextByBrokerId
0x1800028af  mov     rbx, rax
0x1800028b2  mov     sil, 1
0x1800028b5  test    rbx, rbx
0x1800028b8  jnz     loc_180002746
0x1800028be  mov     rcx, rdi
0x1800028c1  call    BripCreateBindingContext
0x1800028c6  mov     rbx, rax
0x1800028c9  test    rax, rax
0x1800028cc  jnz     loc_180002746
0x1800028d2  mov     ebx, 6AEh
0x1800028d7  lea     rcx, BrokerBindingTableLock
0x1800028de  mov     cs:dword_180012198, r15d
0x1800028e5  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800028eb  jmp     short loc_180002879
0x1800028ed  mov     rax, [rsp+100h+Binding]
0x1800028f2  mov     [r14], rax
0x1800028f5  mov     ebx, r15d
0x1800028f8  jmp     loc_180002867
```
