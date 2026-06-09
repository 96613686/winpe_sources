# CRemoveDeviceContextHandler::Invoke(IShellItemArray *,IBindCtx *)

- ea: `0x1800085b0`
- end: `0x180008748`
- name: `?Invoke@CRemoveDeviceContextHandler@@UEAAJPEAUIShellItemArray@@PEAUIBindCtx@@@Z`
- size: `408`
- prototype: `__int64 __fastcall(CRemoveDeviceContextHandler *__hidden this, struct IShellItemArray *, struct IBindCtx *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x180005d1c`
- `0x1800085b0`
- `0x1800088f0`
- `0x18000ac94`
- `0x18000b5dc`
- `0x18000b968`
- `0x18000bdec`
- `0x18000be1c`
- `0x18000c966`
- `0x18000c990`

## string_xrefs

- `0x1800085ff`: `RemoveDeviceActivity`

## pseudocode

```c
__int64 __fastcall CRemoveDeviceContextHandler::Invoke(
        CRemoveDeviceContextHandler *this,
        struct IShellItemArray *a2,
        struct IBindCtx *a3)
{
  __int64 v4; // rcx
  unsigned int v5; // r8d
  int v6; // eax
  __int64 v7; // r8
  unsigned int v8; // ebx
  int v10[2]; // [rsp+20h] [rbp-E0h] BYREF
  int v11; // [rsp+28h] [rbp-D8h] BYREF
  char v12; // [rsp+2Ch] [rbp-D4h]
  int v13; // [rsp+50h] [rbp-B0h] BYREF
  const char *v14; // [rsp+58h] [rbp-A8h]
  __int64 v15; // [rsp+60h] [rbp-A0h]
  char v16; // [rsp+68h] [rbp-98h]
  int v17; // [rsp+70h] [rbp-90h]
  _BYTE v18[152]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v19; // [rsp+110h] [rbp+10h]
  int v20; // [rsp+120h] [rbp+20h]
  __int64 v21; // [rsp+128h] [rbp+28h]
  int *v22; // [rsp+130h] [rbp+30h]
  __int64 v23; // [rsp+138h] [rbp+38h]
  __int64 v24; // [rsp+140h] [rbp+40h]
  int *v25; // [rsp+148h] [rbp+48h]
  __int64 v26; // [rsp+150h] [rbp+50h]
  int v27; // [rsp+158h] [rbp+58h]
  int *v28; // [rsp+160h] [rbp+60h]
  char v29; // [rsp+168h] [rbp+68h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16);
  v11 = 0;
  v14 = "RemoveDeviceActivity";
  v19 = 0;
  v12 = 0;
  v16 = 0;
  v13 = 0;
  v15 = 0;
  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  v20 = 1;
  v21 = 0;
  v23 = 0;
  v22 = &v11;
  v25 = v10;
  v28 = &v13;
  *(_QWORD *)v10 = &DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::`vftable';
  v24 = 0;
  v26 = 0;
  v27 = 0;
  v29 = 0;
  DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::StartActivity((DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity *)v10);
  if ( a2 )
  {
    v6 = CRemoveDeviceContextHandler::_ExecuteRemoveDevice(v4, (__int64 *)a2, (__int64)v10);
    v8 = v6;
    if ( v6 < 0 )
      wil::details::in1diag3::_Log_Hr(retaddr, (void *)0xFD, v7, (const char *)(unsigned int)v6);
  }
  else
  {
    v8 = -2147024809;
    wil::details::in1diag3::Log_Hr(retaddr, (void *)0x101, v5, (const char *)0x80070057LL, v10[0]);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, v7, v8);
  DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::~RemoveDeviceActivity((DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity *)v10);
  return v8;
}

```

## disassembly

```asm
0x1800085b0  mov     [rsp-8+arg_0], rbx
0x1800085b5  mov     [rsp-8+arg_10], rsi
0x1800085ba  push    rbp
0x1800085bb  lea     rbp, [rsp-80h]
0x1800085c0  sub     rsp, 180h
0x1800085c7  mov     rax, cs:__security_cookie
0x1800085ce  xor     rax, rsp
0x1800085d1  mov     [rbp+80h+var_10], rax
0x1800085d5  mov     rbx, rdx
0x1800085d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800085df  lea     rsi, WPP_GLOBAL_Control
0x1800085e6  cmp     rcx, rsi
0x1800085e9  jz      short loc_1800085FF
0x1800085eb  test    byte ptr [rcx+1Ch], 20h
0x1800085ef  jz      short loc_1800085FF
0x1800085f1  mov     rcx, [rcx+10h]
0x1800085f5  mov     edx, 10h
0x1800085fa  call    WPP_SF_
0x1800085ff  lea     rax, aRemovedeviceac; "RemoveDeviceActivity"
0x180008606  mov     [rsp+180h+var_158], 0
0x18000860e  xorps   xmm0, xmm0
0x180008611  mov     [rsp+180h+var_128], rax
0x180008616  xor     edx, edx; Val
0x180008618  movdqa  [rbp+80h+var_70], xmm0
0x18000861d  mov     r8d, 98h; Size
0x180008623  mov     [rsp+180h+var_154], 0
0x180008628  lea     rcx, [rsp+180h+var_108]; void *
0x18000862d  mov     [rsp+180h+var_118], 0
0x180008632  mov     [rsp+180h+var_130], 0
0x18000863a  mov     [rsp+180h+var_120], 0
0x180008643  mov     [rsp+180h+var_110], 0
0x18000864b  call    memset_0
0x180008650  xor     eax, eax
0x180008652  mov     [rbp+80h+var_60], 1
0x180008659  mov     [rbp+80h+var_58], rax
0x18000865d  lea     rcx, [rsp+180h+var_160]; this
0x180008662  lea     rax, [rsp+180h+var_158]
0x180008667  mov     [rbp+80h+var_48], 0
0x18000866f  mov     [rbp+80h+var_50], rax
0x180008673  lea     rax, [rsp+180h+var_160]
0x180008678  mov     [rbp+80h+var_38], rax
0x18000867c  lea     rax, [rsp+180h+var_130]
0x180008681  mov     [rbp+80h+var_20], rax
0x180008685  lea     rax, ??_7RemoveDeviceActivity@DeviceCenterContextHandlersTelemetry@@6B@; const DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::`vftable'
0x18000868c  mov     qword ptr [rsp+180h+var_160], rax; int
0x180008691  mov     [rbp+80h+var_40], 0
0x180008699  mov     [rbp+80h+var_30], 0
0x1800086a1  mov     [rbp+80h+var_28], 0
0x1800086a8  mov     [rbp+80h+var_18], 0
0x1800086ac  call    ?StartActivity@RemoveDeviceActivity@DeviceCenterContextHandlersTelemetry@@QEAAXXZ; DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::StartActivity(void)
0x1800086b1  test    rbx, rbx
0x1800086b4  jz      short loc_1800086DF
0x1800086b6  lea     r8, [rsp+180h+var_160]
0x1800086bb  mov     rdx, rbx
0x1800086be  call    ?_ExecuteRemoveDevice@CRemoveDeviceContextHandler@@AEAAJPEAUIShellItemArray@@$$QEAVRemoveDeviceActivity@DeviceCenterContextHandlersTelemetry@@@Z; CRemoveDeviceContextHandler::_ExecuteRemoveDevice(IShellItemArray *,DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity &&)
0x1800086c3  mov     ebx, eax
0x1800086c5  test    eax, eax
0x1800086c7  jns     short loc_1800086F8
0x1800086c9  mov     rcx, [rbp+88h]; this
0x1800086d0  mov     r9d, eax; char *
0x1800086d3  mov     edx, 0FDh; void *
0x1800086d8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800086dd  jmp     short loc_1800086F8
0x1800086df  mov     rcx, [rbp+88h]; this
0x1800086e6  mov     ebx, 80070057h
0x1800086eb  mov     r9d, ebx; char *
0x1800086ee  mov     edx, 101h; void *
0x1800086f3  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800086f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086ff  cmp     rcx, rsi
0x180008702  jz      short loc_18000871B
0x180008704  test    byte ptr [rcx+1Ch], 20h
0x180008708  jz      short loc_18000871B
0x18000870a  mov     rcx, [rcx+10h]
0x18000870e  mov     edx, 11h
0x180008713  mov     r9d, ebx
0x180008716  call    WPP_SF_d
0x18000871b  lea     rcx, [rsp+180h+var_160]; this
0x180008720  call    ??1RemoveDeviceActivity@DeviceCenterContextHandlersTelemetry@@QEAA@XZ; DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::~RemoveDeviceActivity(void)
0x180008725  mov     eax, ebx
0x180008727  mov     rcx, [rbp+80h+var_10]
0x18000872b  xor     rcx, rsp; StackCookie
0x18000872e  call    __security_check_cookie
0x180008733  lea     r11, [rsp+180h+var_s0]
0x18000873b  mov     rbx, [r11+10h]
0x18000873f  mov     rsi, [r11+20h]
0x180008743  mov     rsp, r11
0x180008746  pop     rbp
0x180008747  retn
```
