# MosHostOpen(HMOSHOST__ * *)

- ea: `0x18000a810`
- end: `0x18000a911`
- name: `?MosHostOpen@@YAJPEAPEAUHMOSHOST__@@@Z`
- size: `257`
- prototype: `__int64 __fastcall(struct HMOSHOST__ **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x180002550`
- `0x180006214`
- `0x1800080cc`
- `0x180009304`
- `0x18000a810`
- `0x18000b1cc`
- `0x18000b400`
- `0x18000b8e8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000a8a8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000a8a8`

## pseudocode

```c
__int64 __fastcall MosHostOpen(struct HMOSHOST__ **a1)
{
  unsigned int v2; // edi
  __int64 v3; // rdx
  __int64 v4; // r8
  int v5; // eax
  unsigned int v6; // ebx
  int v8[2]; // [rsp+20h] [rbp-188h] BYREF
  __int64 (__fastcall *v9)(); // [rsp+28h] [rbp-180h]
  __int64 (__fastcall *v10)(); // [rsp+30h] [rbp-178h]
  _BYTE v11[336]; // [rsp+40h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  *(_QWORD *)v8 = &qword_180013F90;
  v9 = MosHostCreateContext;
  v10 = MosHostCloseContext;
  v2 = 4;
  OfflineMapsTelemetry::ClientOpenConnectionActivity::Start<>((OfflineMapsTelemetry::ClientOpenConnectionActivity *)v11);
  while ( 1 )
  {
    v5 = ServiceInterface<void *,HMOSHOST__ *>::TryOpenService(v8, v3, v4, a1);
    v6 = v5;
    if ( v5 != -2147023179 && v5 != -2147023641 && v5 != -2147023143 )
      break;
    if ( !--v2 )
      break;
    OfflineMapsTelemetry::ClientOpenConnectionActivity::ServiceNotReady(
      (OfflineMapsTelemetry::ClientOpenConnectionActivity *)v11,
      v5,
      v2);
    Sleep(0x1F4u);
  }
  if ( v5 >= 0 )
  {
    wil::ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v11);
    v6 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\ClientHelpers.h",
      (const char *)(unsigned int)v5,
      v8[0]);
  }
  OfflineMapsTelemetry::ClientOpenConnectionActivity::~ClientOpenConnectionActivity((OfflineMapsTelemetry::ClientOpenConnectionActivity *)v11);
  return v6;
}

```

## disassembly

```asm
0x18000a810  mov     [rsp+arg_8], rbx
0x18000a815  mov     [rsp+arg_10], rsi
0x18000a81a  push    rdi
0x18000a81b  sub     rsp, 1A0h
0x18000a822  mov     rax, cs:__security_cookie
0x18000a829  xor     rax, rsp
0x18000a82c  mov     [rsp+1A8h+var_18], rax
0x18000a834  mov     rsi, rcx
0x18000a837  lea     rax, qword_180013F90
0x18000a83e  mov     qword ptr [rsp+1A8h+var_188], rax; int
0x18000a843  lea     rax, MosHostCreateContext
0x18000a84a  mov     [rsp+1A8h+var_180], rax
0x18000a84f  lea     rax, MosHostCloseContext
0x18000a856  mov     [rsp+1A8h+var_178], rax
0x18000a85b  mov     edi, 4
0x18000a860  lea     rcx, [rsp+1A8h+var_168]; this
0x18000a865  call    ??$Start@$$V@ClientOpenConnectionActivity@OfflineMapsTelemetry@@SA?AV01@XZ; OfflineMapsTelemetry::ClientOpenConnectionActivity::Start<>(void)
0x18000a86a  nop
0x18000a86b  mov     r9, rsi
0x18000a86e  lea     rcx, [rsp+1A8h+var_188]
0x18000a873  call    ?TryOpenService@?$ServiceInterface@PEAXPEAUHMOSHOST__@@@@AEAAJPEBGW4__MIDL___MIDL_itf_moshostapi_0000_0000_0001@@PEAPEAUHMOSHOST__@@@Z; ServiceInterface<void *,HMOSHOST__ *>::TryOpenService(ushort const *,__MIDL___MIDL_itf_moshostapi_0000_0000_0001,HMOSHOST__ * *)
0x18000a878  mov     ebx, eax
0x18000a87a  cmp     eax, 800706B5h
0x18000a87f  jz      short loc_18000A88F
0x18000a881  cmp     eax, 800704E7h
0x18000a886  jz      short loc_18000A88F
0x18000a888  cmp     eax, 800706D9h
0x18000a88d  jnz     short loc_18000A8B0
0x18000a88f  add     edi, 0FFFFFFFFh
0x18000a892  jz      short loc_18000A8B0
0x18000a894  mov     r8d, edi; unsigned int
0x18000a897  mov     edx, eax; int
0x18000a899  lea     rcx, [rsp+1A8h+var_168]; this
0x18000a89e  call    ?ServiceNotReady@ClientOpenConnectionActivity@OfflineMapsTelemetry@@QEAAXJK@Z; OfflineMapsTelemetry::ClientOpenConnectionActivity::ServiceNotReady(long,ulong)
0x18000a8a3  mov     ecx, 1F4h; dwMilliseconds
0x18000a8a8  call    cs:__imp_Sleep
0x18000a8ae  jmp     short loc_18000A86B
0x18000a8b0  test    eax, eax
0x18000a8b2  jns     short loc_18000A8D3
0x18000a8b4  mov     rcx, [rsp+1A8h]; this
0x18000a8bc  mov     r9d, eax; char *
0x18000a8bf  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x18000a8c6  mov     edx, 51h ; 'Q'; void *
0x18000a8cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a8d0  nop
0x18000a8d1  jmp     short loc_18000A8E0
0x18000a8d3  lea     rcx, [rsp+1A8h+var_168]
0x18000a8d8  call    ?Stop@?$ActivityBase@VOfflineMapsTraceLogging@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000a8dd  nop
0x18000a8de  xor     ebx, ebx
0x18000a8e0  lea     rcx, [rsp+1A8h+var_168]; this
0x18000a8e5  call    ??1ClientOpenConnectionActivity@OfflineMapsTelemetry@@QEAA@XZ; OfflineMapsTelemetry::ClientOpenConnectionActivity::~ClientOpenConnectionActivity(void)
0x18000a8ea  mov     eax, ebx
0x18000a8ec  mov     rcx, [rsp+1A8h+var_18]
0x18000a8f4  xor     rcx, rsp; StackCookie
0x18000a8f7  call    __security_check_cookie
0x18000a8fc  lea     r11, [rsp+1A8h+var_8]
0x18000a904  mov     rbx, [r11+18h]
0x18000a908  mov     rsi, [r11+20h]
0x18000a90c  mov     rsp, r11
0x18000a90f  pop     rdi
0x18000a910  retn
```
