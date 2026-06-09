# CNetworkExplorerFolderViewCB::_OnDelayWindowCreate(ulong,HWND__ *)

- ea: `0x18000c984`
- end: `0x18000caa2`
- name: `?_OnDelayWindowCreate@CNetworkExplorerFolderViewCB@@AEAAJKPEAUHWND__@@@Z`
- size: `286`
- prototype: `__int64 __fastcall(CNetworkExplorerFolderViewCB *__hidden this, unsigned int, HWND)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800069c0`

## callees

- `0x180003778`
- `0x180008d50`
- `0x18000b8c4`
- `0x18000baa4`
- `0x18000c984`
- `0x18000cc44`
- `0x18000f076`
- `0x18000f0a0`

## string_xrefs

- `0x18000c9c1`: `NetworkExplorerOpen`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CNetworkExplorerFolderViewCB::_OnDelayWindowCreate(struct IUnknown **this, __int64 a2, HWND a3)
{
  void **v5; // [rsp+20h] [rbp-E0h] BYREF
  int v6; // [rsp+28h] [rbp-D8h] BYREF
  char v7; // [rsp+2Ch] [rbp-D4h]
  int v8; // [rsp+50h] [rbp-B0h] BYREF
  const char *v9; // [rsp+58h] [rbp-A8h]
  __int64 v10; // [rsp+60h] [rbp-A0h]
  char v11; // [rsp+68h] [rbp-98h]
  int v12; // [rsp+70h] [rbp-90h]
  _BYTE v13[152]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v14; // [rsp+110h] [rbp+10h]
  int v15; // [rsp+120h] [rbp+20h]
  __int64 v16; // [rsp+128h] [rbp+28h]
  int *v17; // [rsp+130h] [rbp+30h]
  __int64 v18; // [rsp+138h] [rbp+38h]
  __int64 v19; // [rsp+140h] [rbp+40h]
  void ***v20; // [rsp+148h] [rbp+48h]
  __int64 v21; // [rsp+150h] [rbp+50h]
  int v22; // [rsp+158h] [rbp+58h]
  int *v23; // [rsp+160h] [rbp+60h]
  char v24; // [rsp+168h] [rbp+68h]

  v6 = 0;
  v7 = 0;
  v11 = 0;
  v8 = 0;
  v9 = "NetworkExplorerOpen";
  v10 = 0;
  v12 = 0;
  v14 = 0;
  memset_0(v13, 0, sizeof(v13));
  v15 = 1;
  v16 = 0;
  v17 = &v6;
  v18 = 0;
  v19 = 0;
  v20 = &v5;
  v21 = 0;
  v22 = 0;
  v23 = &v8;
  v24 = 0;
  v5 = &NetworkLegacyUxTelemetry::NetworkExplorerOpen::`vftable';
  NetworkLegacyUxTelemetry::NetworkExplorerOpen::StartActivity((NetworkLegacyUxTelemetry::NetworkExplorerOpen *)&v5);
  if ( !(unsigned int)IsEnumerationBlocked(this[7]) )
    CNetworkExplorerFolderViewCB::_StartProgressBar((CNetworkExplorerFolderViewCB *)this);
  wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v5);
  NetworkLegacyUxTelemetry::NetworkExplorerOpen::~NetworkExplorerOpen((NetworkLegacyUxTelemetry::NetworkExplorerOpen *)&v5);
  return 0;
}

```

## disassembly

```asm
0x18000c984  mov     [rsp-8+arg_8], rbx
0x18000c989  push    rbp
0x18000c98a  lea     rbp, [rsp-80h]
0x18000c98f  sub     rsp, 180h
0x18000c996  mov     rax, cs:__security_cookie
0x18000c99d  xor     rax, rsp
0x18000c9a0  mov     [rbp+80h+var_10], rax
0x18000c9a4  mov     rbx, rcx
0x18000c9a7  mov     [rsp+180h+var_158], 0
0x18000c9af  mov     [rsp+180h+var_154], 0
0x18000c9b4  mov     [rsp+180h+var_118], 0
0x18000c9b9  mov     [rsp+180h+var_130], 0
0x18000c9c1  lea     rax, aNetworkexplore_1; "NetworkExplorerOpen"
0x18000c9c8  mov     [rsp+180h+var_128], rax
0x18000c9cd  mov     [rsp+180h+var_120], 0
0x18000c9d6  mov     [rsp+180h+var_110], 0
0x18000c9de  xorps   xmm0, xmm0
0x18000c9e1  movdqa  [rbp+80h+var_70], xmm0
0x18000c9e6  xor     edx, edx; Val
0x18000c9e8  mov     r8d, 98h; Size
0x18000c9ee  lea     rcx, [rsp+180h+var_108]; void *
0x18000c9f3  call    memset_0
0x18000c9f8  mov     [rbp+80h+var_60], 1
0x18000c9ff  xor     eax, eax
0x18000ca01  mov     [rbp+80h+var_58], rax
0x18000ca05  lea     rax, [rsp+180h+var_158]
0x18000ca0a  mov     [rbp+80h+var_50], rax
0x18000ca0e  mov     [rbp+80h+var_48], 0
0x18000ca16  mov     [rbp+80h+var_40], 0
0x18000ca1e  lea     rax, [rsp+180h+var_160]
0x18000ca23  mov     [rbp+80h+var_38], rax
0x18000ca27  mov     [rbp+80h+var_30], 0
0x18000ca2f  mov     [rbp+80h+var_28], 0
0x18000ca36  lea     rax, [rsp+180h+var_130]
0x18000ca3b  mov     [rbp+80h+var_20], rax
0x18000ca3f  mov     [rbp+80h+var_18], 0
0x18000ca43  lea     rax, ??_7NetworkExplorerOpen@NetworkLegacyUxTelemetry@@6B@; const NetworkLegacyUxTelemetry::NetworkExplorerOpen::`vftable'
0x18000ca4a  mov     [rsp+180h+var_160], rax
0x18000ca4f  lea     rcx, [rsp+180h+var_160]; this
0x18000ca54  call    ?StartActivity@NetworkExplorerOpen@NetworkLegacyUxTelemetry@@QEAAXXZ; NetworkLegacyUxTelemetry::NetworkExplorerOpen::StartActivity(void)
0x18000ca59  mov     rcx, [rbx+38h]; struct IUnknown *
0x18000ca5d  call    ?IsEnumerationBlocked@@YAHPEAUIUnknown@@@Z; IsEnumerationBlocked(IUnknown *)
0x18000ca62  test    eax, eax
0x18000ca64  jnz     short loc_18000CA6E
0x18000ca66  mov     rcx, rbx; this
0x18000ca69  call    ?_StartProgressBar@CNetworkExplorerFolderViewCB@@AEAAJXZ; CNetworkExplorerFolderViewCB::_StartProgressBar(void)
0x18000ca6e  lea     rcx, [rsp+180h+var_160]
0x18000ca73  call    ?Stop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000ca78  nop
0x18000ca79  lea     rcx, [rsp+180h+var_160]; this
0x18000ca7e  call    ??1NetworkExplorerOpen@NetworkLegacyUxTelemetry@@QEAA@XZ; NetworkLegacyUxTelemetry::NetworkExplorerOpen::~NetworkExplorerOpen(void)
0x18000ca83  xor     eax, eax
0x18000ca85  mov     rcx, [rbp+80h+var_10]
0x18000ca89  xor     rcx, rsp; StackCookie
0x18000ca8c  call    __security_check_cookie
0x18000ca91  mov     rbx, [rsp+180h+arg_8]
0x18000ca99  add     rsp, 180h
0x18000caa0  pop     rbp
0x18000caa1  retn
```
