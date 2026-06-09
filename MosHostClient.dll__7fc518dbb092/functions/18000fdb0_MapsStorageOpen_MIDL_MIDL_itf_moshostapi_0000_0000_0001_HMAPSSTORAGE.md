# MapsStorageOpen(__MIDL___MIDL_itf_moshostapi_0000_0000_0001,HMAPSSTORAGE__ * *)

- ea: `0x18000fdb0`
- end: `0x18000feb1`
- name: `?MapsStorageOpen@@YAJW4__MIDL___MIDL_itf_moshostapi_0000_0000_0001@@PEAPEAUHMAPSSTORAGE__@@@Z`
- size: `257`
- prototype: `__int64 __fastcall(unsigned int, __int64)`
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
- `0x18000fdb0`
- `0x180010038`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000fe4a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000fe4a`

## pseudocode

```c
__int64 __fastcall MapsStorageOpen(unsigned int a1, __int64 a2)
{
  unsigned int v4; // edi
  __int64 v5; // rdx
  int v6; // eax
  unsigned int v7; // ebx
  int v9[2]; // [rsp+20h] [rbp-198h] BYREF
  __int64 (__fastcall *v10)(); // [rsp+28h] [rbp-190h]
  __int64 (__fastcall *v11)(); // [rsp+30h] [rbp-188h]
  _BYTE v12[336]; // [rsp+40h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  *(_QWORD *)v9 = &qword_180014250;
  v10 = MapsStorageSvcOpen;
  v11 = MapsStorageSvcClose;
  v4 = 4;
  OfflineMapsTelemetry::ClientOpenConnectionActivity::Start<>((OfflineMapsTelemetry::ClientOpenConnectionActivity *)v12);
  while ( 1 )
  {
    v6 = ServiceInterface<void *,HMAPSSTORAGE__ *>::TryOpenService(v9, v5, a1, a2);
    v7 = v6;
    if ( v6 != -2147023179 && v6 != -2147023641 && v6 != -2147023143 )
      break;
    if ( !--v4 )
      break;
    OfflineMapsTelemetry::ClientOpenConnectionActivity::ServiceNotReady(
      (OfflineMapsTelemetry::ClientOpenConnectionActivity *)v12,
      v6,
      v4);
    Sleep(0x1F4u);
  }
  if ( v6 >= 0 )
  {
    wil::ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v12);
    v7 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\ClientHelpers.h",
      (const char *)(unsigned int)v6,
      v9[0]);
  }
  OfflineMapsTelemetry::ClientOpenConnectionActivity::~ClientOpenConnectionActivity((OfflineMapsTelemetry::ClientOpenConnectionActivity *)v12);
  return v7;
}

```

## disassembly

```asm
0x18000fdb0  mov     [rsp+arg_10], rbx
0x18000fdb5  push    rbp
0x18000fdb6  push    rsi
0x18000fdb7  push    rdi
0x18000fdb8  sub     rsp, 1A0h
0x18000fdbf  mov     rax, cs:__security_cookie
0x18000fdc6  xor     rax, rsp
0x18000fdc9  mov     [rsp+1B8h+var_28], rax
0x18000fdd1  mov     rbp, rdx
0x18000fdd4  mov     esi, ecx
0x18000fdd6  lea     rax, qword_180014250
0x18000fddd  mov     qword ptr [rsp+1B8h+var_198], rax; int
0x18000fde2  lea     rax, MapsStorageSvcOpen
0x18000fde9  mov     [rsp+1B8h+var_190], rax
0x18000fdee  lea     rax, MapsStorageSvcClose
0x18000fdf5  mov     [rsp+1B8h+var_188], rax
0x18000fdfa  mov     edi, 4
0x18000fdff  lea     rcx, [rsp+1B8h+var_178]; this
0x18000fe04  call    ??$Start@$$V@ClientOpenConnectionActivity@OfflineMapsTelemetry@@SA?AV01@XZ; OfflineMapsTelemetry::ClientOpenConnectionActivity::Start<>(void)
0x18000fe09  nop
0x18000fe0a  mov     r9, rbp
0x18000fe0d  mov     r8d, esi
0x18000fe10  lea     rcx, [rsp+1B8h+var_198]
0x18000fe15  call    ?TryOpenService@?$ServiceInterface@PEAXPEAUHMAPSSTORAGE__@@@@AEAAJPEBGW4__MIDL___MIDL_itf_moshostapi_0000_0000_0001@@PEAPEAUHMAPSSTORAGE__@@@Z; ServiceInterface<void *,HMAPSSTORAGE__ *>::TryOpenService(ushort const *,__MIDL___MIDL_itf_moshostapi_0000_0000_0001,HMAPSSTORAGE__ * *)
0x18000fe1a  mov     ebx, eax
0x18000fe1c  cmp     eax, 800706B5h
0x18000fe21  jz      short loc_18000FE31
0x18000fe23  cmp     eax, 800704E7h
0x18000fe28  jz      short loc_18000FE31
0x18000fe2a  cmp     eax, 800706D9h
0x18000fe2f  jnz     short loc_18000FE52
0x18000fe31  add     edi, 0FFFFFFFFh
0x18000fe34  jz      short loc_18000FE52
0x18000fe36  mov     r8d, edi; unsigned int
0x18000fe39  mov     edx, eax; int
0x18000fe3b  lea     rcx, [rsp+1B8h+var_178]; this
0x18000fe40  call    ?ServiceNotReady@ClientOpenConnectionActivity@OfflineMapsTelemetry@@QEAAXJK@Z; OfflineMapsTelemetry::ClientOpenConnectionActivity::ServiceNotReady(long,ulong)
0x18000fe45  mov     ecx, 1F4h; dwMilliseconds
0x18000fe4a  call    cs:__imp_Sleep
0x18000fe50  jmp     short loc_18000FE0A
0x18000fe52  test    eax, eax
0x18000fe54  jns     short loc_18000FE75
0x18000fe56  mov     rcx, [rsp+1B8h]; this
0x18000fe5e  mov     r9d, eax; char *
0x18000fe61  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x18000fe68  mov     edx, 51h ; 'Q'; void *
0x18000fe6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fe72  nop
0x18000fe73  jmp     short loc_18000FE82
0x18000fe75  lea     rcx, [rsp+1B8h+var_178]
0x18000fe7a  call    ?Stop@?$ActivityBase@VOfflineMapsTraceLogging@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000fe7f  nop
0x18000fe80  xor     ebx, ebx
0x18000fe82  lea     rcx, [rsp+1B8h+var_178]; this
0x18000fe87  call    ??1ClientOpenConnectionActivity@OfflineMapsTelemetry@@QEAA@XZ; OfflineMapsTelemetry::ClientOpenConnectionActivity::~ClientOpenConnectionActivity(void)
0x18000fe8c  mov     eax, ebx
0x18000fe8e  mov     rcx, [rsp+1B8h+var_28]
0x18000fe96  xor     rcx, rsp; StackCookie
0x18000fe99  call    __security_check_cookie
0x18000fe9e  mov     rbx, [rsp+1B8h+arg_10]
0x18000fea6  add     rsp, 1A0h
0x18000fead  pop     rdi
0x18000feae  pop     rsi
0x18000feaf  pop     rbp
0x18000feb0  retn
```
