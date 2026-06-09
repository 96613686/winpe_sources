# MapsPackageOpen(ushort const *,__MIDL___MIDL_itf_moshostapi_0000_0000_0001,HMAPSPACKAGE__ * *)

- ea: `0x18000f0c0`
- end: `0x18000f1c1`
- name: `?MapsPackageOpen@@YAJPEBGW4__MIDL___MIDL_itf_moshostapi_0000_0000_0001@@PEAPEAUHMAPSPACKAGE__@@@Z`
- size: `257`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
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
- `0x18000f0c0`
- `0x18000f1e4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000f15f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000f15f`

## pseudocode

```c
__int64 __fastcall MapsPackageOpen(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int v6; // edi
  int v7; // eax
  unsigned int v8; // ebx
  int v10[2]; // [rsp+20h] [rbp-1A8h] BYREF
  __int64 (__fastcall *v11)(); // [rsp+28h] [rbp-1A0h]
  __int64 (__fastcall *v12)(); // [rsp+30h] [rbp-198h]
  _BYTE v13[336]; // [rsp+40h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  *(_QWORD *)v10 = &qword_180013E00;
  v11 = MapsPackageSvcOpen;
  v12 = MapsPackageSvcClose;
  v6 = 4;
  OfflineMapsTelemetry::ClientOpenConnectionActivity::Start<>((OfflineMapsTelemetry::ClientOpenConnectionActivity *)v13);
  while ( 1 )
  {
    v7 = ServiceInterface<void *,HMAPSPACKAGE__ *>::TryOpenService(v10, a1, a2, a3);
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
0x18000f0c0  push    rbx
0x18000f0c2  push    rbp
0x18000f0c3  push    rsi
0x18000f0c4  push    rdi
0x18000f0c5  push    r14
0x18000f0c7  sub     rsp, 1A0h
0x18000f0ce  mov     rax, cs:__security_cookie
0x18000f0d5  xor     rax, rsp
0x18000f0d8  mov     [rsp+1C8h+var_38], rax
0x18000f0e0  mov     r14, r8
0x18000f0e3  mov     ebp, edx
0x18000f0e5  mov     rsi, rcx
0x18000f0e8  lea     rax, qword_180013E00
0x18000f0ef  mov     qword ptr [rsp+1C8h+var_1A8], rax; int
0x18000f0f4  lea     rax, MapsPackageSvcOpen
0x18000f0fb  mov     [rsp+1C8h+var_1A0], rax
0x18000f100  lea     rax, MapsPackageSvcClose
0x18000f107  mov     [rsp+1C8h+var_198], rax
0x18000f10c  mov     edi, 4
0x18000f111  lea     rcx, [rsp+1C8h+var_188]; this
0x18000f116  call    ??$Start@$$V@ClientOpenConnectionActivity@OfflineMapsTelemetry@@SA?AV01@XZ; OfflineMapsTelemetry::ClientOpenConnectionActivity::Start<>(void)
0x18000f11b  nop
0x18000f11c  mov     r9, r14
0x18000f11f  mov     r8d, ebp
0x18000f122  mov     rdx, rsi
0x18000f125  lea     rcx, [rsp+1C8h+var_1A8]
0x18000f12a  call    ?TryOpenService@?$ServiceInterface@PEAXPEAUHMAPSPACKAGE__@@@@AEAAJPEBGW4__MIDL___MIDL_itf_moshostapi_0000_0000_0001@@PEAPEAUHMAPSPACKAGE__@@@Z; ServiceInterface<void *,HMAPSPACKAGE__ *>::TryOpenService(ushort const *,__MIDL___MIDL_itf_moshostapi_0000_0000_0001,HMAPSPACKAGE__ * *)
0x18000f12f  mov     ebx, eax
0x18000f131  cmp     eax, 800706B5h
0x18000f136  jz      short loc_18000F146
0x18000f138  cmp     eax, 800704E7h
0x18000f13d  jz      short loc_18000F146
0x18000f13f  cmp     eax, 800706D9h
0x18000f144  jnz     short loc_18000F167
0x18000f146  add     edi, 0FFFFFFFFh
0x18000f149  jz      short loc_18000F167
0x18000f14b  mov     r8d, edi; unsigned int
0x18000f14e  mov     edx, eax; int
0x18000f150  lea     rcx, [rsp+1C8h+var_188]; this
0x18000f155  call    ?ServiceNotReady@ClientOpenConnectionActivity@OfflineMapsTelemetry@@QEAAXJK@Z; OfflineMapsTelemetry::ClientOpenConnectionActivity::ServiceNotReady(long,ulong)
0x18000f15a  mov     ecx, 1F4h; dwMilliseconds
0x18000f15f  call    cs:__imp_Sleep
0x18000f165  jmp     short loc_18000F11C
0x18000f167  test    eax, eax
0x18000f169  jns     short loc_18000F18A
0x18000f16b  mov     rcx, [rsp+1C8h]; this
0x18000f173  mov     r9d, eax; char *
0x18000f176  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x18000f17d  mov     edx, 51h ; 'Q'; void *
0x18000f182  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f187  nop
0x18000f188  jmp     short loc_18000F197
0x18000f18a  lea     rcx, [rsp+1C8h+var_188]
0x18000f18f  call    ?Stop@?$ActivityBase@VOfflineMapsTraceLogging@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000f194  nop
0x18000f195  xor     ebx, ebx
0x18000f197  lea     rcx, [rsp+1C8h+var_188]; this
0x18000f19c  call    ??1ClientOpenConnectionActivity@OfflineMapsTelemetry@@QEAA@XZ; OfflineMapsTelemetry::ClientOpenConnectionActivity::~ClientOpenConnectionActivity(void)
0x18000f1a1  mov     eax, ebx
0x18000f1a3  mov     rcx, [rsp+1C8h+var_38]
0x18000f1ab  xor     rcx, rsp; StackCookie
0x18000f1ae  call    __security_check_cookie
0x18000f1b3  add     rsp, 1A0h
0x18000f1ba  pop     r14
0x18000f1bc  pop     rdi
0x18000f1bd  pop     rsi
0x18000f1be  pop     rbp
0x18000f1bf  pop     rbx
0x18000f1c0  retn
```
