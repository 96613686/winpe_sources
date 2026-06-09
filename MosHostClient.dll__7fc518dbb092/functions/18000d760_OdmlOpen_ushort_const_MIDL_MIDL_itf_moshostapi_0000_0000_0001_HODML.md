# OdmlOpen(ushort const *,__MIDL___MIDL_itf_moshostapi_0000_0000_0001,HODML__ * *)

- ea: `0x18000d760`
- end: `0x18000d861`
- name: `?OdmlOpen@@YAJPEBGW4__MIDL___MIDL_itf_moshostapi_0000_0000_0001@@PEAPEAUHODML__@@@Z`
- size: `257`
- prototype: `__int64 __fastcall(__int64, int, _QWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x180002550`
- `0x180006214`
- `0x1800080cc`
- `0x180009304`
- `0x18000b1cc`
- `0x18000b400`
- `0x18000d760`
- `0x18000dad8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000d7ff`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000d7ff`

## pseudocode

```c
__int64 __fastcall OdmlOpen(__int64 a1, int a2, _QWORD *a3)
{
  unsigned int v6; // edi
  int v7; // eax
  unsigned int v8; // ebx
  int v10[2]; // [rsp+20h] [rbp-1A8h] BYREF
  __int64 (__fastcall *v11)(); // [rsp+28h] [rbp-1A0h]
  __int64 (__fastcall *v12)(); // [rsp+30h] [rbp-198h]
  _BYTE v13[336]; // [rsp+40h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  *(_QWORD *)v10 = &qword_180013D60;
  v11 = OdmlSvcOpen;
  v12 = OdmlSvcClose;
  v6 = 4;
  OfflineMapsTelemetry::ClientOpenConnectionActivity::Start<>((OfflineMapsTelemetry::ClientOpenConnectionActivity *)v13);
  while ( 1 )
  {
    v7 = ServiceInterface<void *,HODML__ *>::TryOpenService((RPC_IF_HANDLE *)v10, a1, a2, a3);
    v8 = v7;
    if ( v7 != -2147023179 && v7 != -2147023641 && v7 != -2147023143 )
      break;
    if ( !--v6 )
      break;
    OfflineMapsTelemetry::ClientOpenConnectionActivity::ServiceNotReady(
      (OfflineMapsTelemetry::ClientOpenConnectionActivity *)v13,
      v7,
      v6);
    Sleep(0x1F4u);
  }
  if ( v7 >= 0 )
  {
    wil::ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v13);
    v8 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\ClientHelpers.h",
      (const char *)(unsigned int)v7,
      v10[0]);
  }
  OfflineMapsTelemetry::ClientOpenConnectionActivity::~ClientOpenConnectionActivity((OfflineMapsTelemetry::ClientOpenConnectionActivity *)v13);
  return v8;
}

```

## disassembly

```asm
0x18000d760  push    rbx
0x18000d762  push    rbp
0x18000d763  push    rsi
0x18000d764  push    rdi
0x18000d765  push    r14
0x18000d767  sub     rsp, 1A0h
0x18000d76e  mov     rax, cs:__security_cookie
0x18000d775  xor     rax, rsp
0x18000d778  mov     [rsp+1C8h+var_38], rax
0x18000d780  mov     r14, r8
0x18000d783  mov     ebp, edx
0x18000d785  mov     rsi, rcx
0x18000d788  lea     rax, qword_180013D60
0x18000d78f  mov     qword ptr [rsp+1C8h+var_1A8], rax; int
0x18000d794  lea     rax, OdmlSvcOpen
0x18000d79b  mov     [rsp+1C8h+var_1A0], rax
0x18000d7a0  lea     rax, OdmlSvcClose
0x18000d7a7  mov     [rsp+1C8h+var_198], rax
0x18000d7ac  mov     edi, 4
0x18000d7b1  lea     rcx, [rsp+1C8h+var_188]; this
0x18000d7b6  call    ??$Start@$$V@ClientOpenConnectionActivity@OfflineMapsTelemetry@@SA?AV01@XZ; OfflineMapsTelemetry::ClientOpenConnectionActivity::Start<>(void)
0x18000d7bb  nop
0x18000d7bc  mov     r9, r14
0x18000d7bf  mov     r8d, ebp
0x18000d7c2  mov     rdx, rsi
0x18000d7c5  lea     rcx, [rsp+1C8h+var_1A8]
0x18000d7ca  call    ?TryOpenService@?$ServiceInterface@PEAXPEAUHODML__@@@@AEAAJPEBGW4__MIDL___MIDL_itf_moshostapi_0000_0000_0001@@PEAPEAUHODML__@@@Z; ServiceInterface<void *,HODML__ *>::TryOpenService(ushort const *,__MIDL___MIDL_itf_moshostapi_0000_0000_0001,HODML__ * *)
0x18000d7cf  mov     ebx, eax
0x18000d7d1  cmp     eax, 800706B5h
0x18000d7d6  jz      short loc_18000D7E6
0x18000d7d8  cmp     eax, 800704E7h
0x18000d7dd  jz      short loc_18000D7E6
0x18000d7df  cmp     eax, 800706D9h
0x18000d7e4  jnz     short loc_18000D807
0x18000d7e6  add     edi, 0FFFFFFFFh
0x18000d7e9  jz      short loc_18000D807
0x18000d7eb  mov     r8d, edi; unsigned int
0x18000d7ee  mov     edx, eax; int
0x18000d7f0  lea     rcx, [rsp+1C8h+var_188]; this
0x18000d7f5  call    ?ServiceNotReady@ClientOpenConnectionActivity@OfflineMapsTelemetry@@QEAAXJK@Z; OfflineMapsTelemetry::ClientOpenConnectionActivity::ServiceNotReady(long,ulong)
0x18000d7fa  mov     ecx, 1F4h; dwMilliseconds
0x18000d7ff  call    cs:__imp_Sleep
0x18000d805  jmp     short loc_18000D7BC
0x18000d807  test    eax, eax
0x18000d809  jns     short loc_18000D82A
0x18000d80b  mov     rcx, [rsp+1C8h]; this
0x18000d813  mov     r9d, eax; char *
0x18000d816  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x18000d81d  mov     edx, 51h ; 'Q'; void *
0x18000d822  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d827  nop
0x18000d828  jmp     short loc_18000D837
0x18000d82a  lea     rcx, [rsp+1C8h+var_188]
0x18000d82f  call    ?Stop@?$ActivityBase@VOfflineMapsTraceLogging@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000d834  nop
0x18000d835  xor     ebx, ebx
0x18000d837  lea     rcx, [rsp+1C8h+var_188]; this
0x18000d83c  call    ??1ClientOpenConnectionActivity@OfflineMapsTelemetry@@QEAA@XZ; OfflineMapsTelemetry::ClientOpenConnectionActivity::~ClientOpenConnectionActivity(void)
0x18000d841  mov     eax, ebx
0x18000d843  mov     rcx, [rsp+1C8h+var_38]
0x18000d84b  xor     rcx, rsp; StackCookie
0x18000d84e  call    __security_check_cookie
0x18000d853  add     rsp, 1A0h
0x18000d85a  pop     r14
0x18000d85c  pop     rdi
0x18000d85d  pop     rsi
0x18000d85e  pop     rbp
0x18000d85f  pop     rbx
0x18000d860  retn
```
