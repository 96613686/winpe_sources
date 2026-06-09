# SWDSingleton::Initialize(void)

- ea: `0x18000c118`
- end: `0x18000c40a`
- name: `?Initialize@SWDSingleton@@AEAAJXZ`
- size: `754`
- prototype: `__int64 __fastcall(SWDSingleton *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000c01c`

## callees

- `0x1800016c0`
- `0x180002b70`
- `0x1800079e0`
- `0x180009260`
- `0x18000c118`
- `0x18000c410`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c267`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c267`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c277`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c299`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c299`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000c344`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000c344`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000c255`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000c255`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c282`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c398`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c282`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c398`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18000c2e6`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18000c2e6`

## string_xrefs

- `0x18000c3c7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000c3e6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall SWDSingleton::Initialize(SWDSingleton *this)
{
  void *v2; // rdx
  HANDLE Event; // rsi
  unsigned int v4; // r8d
  const char *v5; // r9
  HANDLE v6; // rbx
  DWORD LastError; // edi
  const char *v8; // r9
  unsigned int v9; // eax
  unsigned int v10; // ebx
  DWORD v11; // eax
  __int64 v12; // r8
  const char *v13; // r9
  const char *v14; // r9
  int v16; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v17; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-B0h]
  _QWORD v19[7]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v20; // [rsp+98h] [rbp-68h]
  DEVPROPKEY v21; // [rsp+B0h] [rbp-50h] BYREF
  int v22; // [rsp+C4h] [rbp-3Ch]
  __int64 v23; // [rsp+C8h] [rbp-38h]
  int v24; // [rsp+D0h] [rbp-30h]
  int v25; // [rsp+D4h] [rbp-2Ch]
  int *v26; // [rsp+D8h] [rbp-28h]
  DEVPROPKEY v27; // [rsp+E0h] [rbp-20h]
  int v28; // [rsp+F4h] [rbp-Ch]
  __int64 v29; // [rsp+F8h] [rbp-8h]
  int v30; // [rsp+100h] [rbp+0h]
  int v31; // [rsp+104h] [rbp+4h]
  char *v32; // [rsp+108h] [rbp+8h]
  DEVPROPKEY v33; // [rsp+110h] [rbp+10h]
  int v34; // [rsp+124h] [rbp+24h]
  __int64 v35; // [rsp+128h] [rbp+28h]
  int v36; // [rsp+130h] [rbp+30h]
  int v37; // [rsp+134h] [rbp+34h]
  char *v38; // [rsp+138h] [rbp+38h]
  DEVPROPKEY v39; // [rsp+140h] [rbp+40h]
  int v40; // [rsp+154h] [rbp+54h]
  __int64 v41; // [rsp+158h] [rbp+58h]
  int v42; // [rsp+160h] [rbp+60h]
  int v43; // [rsp+164h] [rbp+64h]
  char *v44; // [rsp+168h] [rbp+68h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v19[0] = 72;
  v19[1] = L"XboxgipSynthetic_000";
  v19[2] = L"SWD\\XBOXGIP_SYNTHETIC";
  v19[3] = 0;
  v19[4] = 0;
  v19[5] = 5;
  v19[6] = L"Xbox Virtual Game Controller";
  v20 = 0;
  v16 = -65281;
  v21 = DEVPKEY_Device_GenericDriverInstalled;
  v22 = 0;
  v23 = 0;
  v24 = 17;
  v25 = 1;
  v26 = &v16;
  v27 = DEVPKEY_DeviceContainer_IsDeviceUniquelyIdentifiable;
  v28 = 0;
  v29 = 0;
  v30 = 17;
  v31 = 1;
  v32 = (char *)&v16 + 1;
  v33 = DEVPKEY_Device_NoConnectSound;
  v34 = 0;
  v35 = 0;
  v36 = 17;
  v37 = 1;
  v38 = (char *)&v16 + 2;
  v39 = DEVPKEY_DeviceClass_SilentInstall;
  v40 = 0;
  v41 = 0;
  v42 = 17;
  v43 = 1;
  v44 = (char *)&v16 + 3;
  hObject = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v2, v4, v5);
  GetLastError();
  v6 = hObject;
  if ( hObject )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v8);
    SetLastError(LastError);
  }
  hObject = Event;
  v17 = 0;
  v9 = SwDeviceCreate(
         L"XboxgipSynthetic",
         L"HTREE\\ROOT\\0",
         v19,
         4,
         &v21,
         _lambda_19a98c5a81a3f7f216e793bf8327e4a2_::_lambda_invoker_cdecl_,
         &v17,
         this);
  v10 = v9;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_0dff6f38adfd39e199de348a1fa5a8cf_Traceguids, v9);
  }
  if ( (int)(v10 + 0x80000000) < 0 || v10 == -2147024713 )
  {
    v11 = WaitForSingleObjectEx(hObject, 0xFFFFFFFF, 0);
    if ( v11 != 258 && v11 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, 2831, v12, v13);
    v10 = v17;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_0dff6f38adfd39e199de348a1fa5a8cf_Traceguids, v17);
    }
  }
  if ( hObject && !CloseHandle(hObject) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v14);
  return v10;
}

```

## disassembly

```asm
0x18000c118  push    rbp
0x18000c11a  push    rbx
0x18000c11b  push    rsi
0x18000c11c  push    rdi
0x18000c11d  push    r14
0x18000c11f  push    r15
0x18000c121  lea     rbp, [rsp-88h]
0x18000c129  sub     rsp, 188h
0x18000c130  mov     rax, cs:__security_cookie
0x18000c137  xor     rax, rsp
0x18000c13a  mov     [rbp+0B0h+var_40], rax
0x18000c13e  mov     r14, rcx
0x18000c141  mov     [rsp+1B0h+var_150], 48h ; 'H'
0x18000c14a  lea     rax, aXboxgipsynthet; "XboxgipSynthetic_000"
0x18000c151  mov     [rsp+1B0h+var_148], rax
0x18000c156  lea     rax, aSwdXboxgipSynt; "SWD\\XBOXGIP_SYNTHETIC"
0x18000c15d  mov     [rsp+1B0h+var_140], rax
0x18000c162  xor     r15d, r15d
0x18000c165  mov     [rsp+1B0h+var_138], r15
0x18000c16a  mov     [rbp+0B0h+var_130], r15
0x18000c16e  mov     [rbp+0B0h+var_128], 5
0x18000c176  lea     rax, aXboxVirtualGam; "Xbox Virtual Game Controller"
0x18000c17d  mov     [rbp+0B0h+var_120], rax
0x18000c181  xorps   xmm0, xmm0
0x18000c184  movups  [rbp+0B0h+var_118], xmm0
0x18000c188  mov     [rsp+1B0h+var_170], 0FFFF00FFh
0x18000c190  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_GenericDriverInstalled.fmtid.Data1
0x18000c197  movaps  [rbp+0B0h+var_100], xmm0
0x18000c19b  mov     eax, cs:DEVPKEY_Device_GenericDriverInstalled.pid
0x18000c1a1  mov     [rbp+0B0h+var_F0], eax
0x18000c1a4  mov     [rbp+0B0h+var_EC], r15d
0x18000c1a8  mov     [rbp+0B0h+var_E8], r15
0x18000c1ac  lea     edx, [r15+11h]
0x18000c1b0  mov     [rbp+0B0h+var_E0], edx
0x18000c1b3  lea     ecx, [rdx-10h]
0x18000c1b6  mov     [rbp+0B0h+var_DC], ecx
0x18000c1b9  lea     rax, [rsp+1B0h+var_170]
0x18000c1be  mov     [rbp+0B0h+var_D8], rax
0x18000c1c2  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceContainer_IsDeviceUniquelyIdentifiable.fmtid.Data1
0x18000c1c9  movaps  [rbp+0B0h+var_D0], xmm0
0x18000c1cd  mov     eax, cs:DEVPKEY_DeviceContainer_IsDeviceUniquelyIdentifiable.pid
0x18000c1d3  mov     [rbp+0B0h+var_C0], eax
0x18000c1d6  mov     [rbp+0B0h+var_BC], r15d
0x18000c1da  mov     [rbp+0B0h+var_B8], r15
0x18000c1de  mov     [rbp+0B0h+var_B0], edx
0x18000c1e1  mov     [rbp+0B0h+var_AC], ecx
0x18000c1e4  lea     rax, [rsp+1B0h+var_170+1]
0x18000c1e9  mov     [rbp+0B0h+var_A8], rax
0x18000c1ed  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_NoConnectSound.fmtid.Data1
0x18000c1f4  movaps  [rbp+0B0h+var_A0], xmm0
0x18000c1f8  mov     eax, cs:DEVPKEY_Device_NoConnectSound.pid
0x18000c1fe  mov     [rbp+0B0h+var_90], eax
0x18000c201  mov     [rbp+0B0h+var_8C], r15d
0x18000c205  mov     [rbp+0B0h+var_88], r15
0x18000c209  mov     [rbp+0B0h+var_80], edx
0x18000c20c  mov     [rbp+0B0h+var_7C], ecx
0x18000c20f  lea     rax, [rsp+1B0h+var_170+2]
0x18000c214  mov     [rbp+0B0h+var_78], rax
0x18000c218  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceClass_SilentInstall.fmtid.Data1
0x18000c21f  movaps  [rbp+0B0h+var_70], xmm0
0x18000c223  mov     eax, cs:DEVPKEY_DeviceClass_SilentInstall.pid
0x18000c229  mov     [rbp+0B0h+var_60], eax
0x18000c22c  mov     [rbp+0B0h+var_5C], r15d
0x18000c230  mov     [rbp+0B0h+var_58], r15
0x18000c234  mov     [rbp+0B0h+var_50], edx
0x18000c237  mov     [rbp+0B0h+var_4C], ecx
0x18000c23a  lea     rax, [rsp+1B0h+var_170+3]
0x18000c23f  mov     [rbp+0B0h+var_48], rax
0x18000c243  mov     [rsp+1B0h+hObject], r15
0x18000c248  mov     r9d, 1F0003h; dwDesiredAccess
0x18000c24e  xor     r8d, r8d; dwFlags
0x18000c251  xor     edx, edx; lpName
0x18000c253  xor     ecx, ecx; lpEventAttributes
0x18000c255  call    cs:__imp_CreateEventExW
0x18000c25b  mov     rsi, rax
0x18000c25e  test    rax, rax
0x18000c261  jz      loc_18000C3D9
0x18000c267  call    cs:__imp_GetLastError
0x18000c26d  mov     rbx, [rsp+1B0h+hObject]
0x18000c272  test    rbx, rbx
0x18000c275  jz      short loc_18000C29F
0x18000c277  call    cs:__imp_GetLastError
0x18000c27d  mov     edi, eax
0x18000c27f  mov     rcx, rbx; hObject
0x18000c282  call    cs:__imp_CloseHandle
0x18000c288  mov     rcx, [rbp+0B8h]; this
0x18000c28f  test    eax, eax
0x18000c291  jz      loc_18000C3E6
0x18000c297  mov     ecx, edi; dwErrCode
0x18000c299  call    cs:__imp_SetLastError
0x18000c29f  mov     [rsp+1B0h+hObject], rsi
0x18000c2a4  mov     [rsp+1B0h+var_168], r15d
0x18000c2a9  mov     [rsp+1B0h+var_178], r14
0x18000c2ae  lea     rax, [rsp+1B0h+var_168]
0x18000c2b3  mov     [rsp+1B0h+var_180], rax
0x18000c2b8  lea     rax, ?_lambda_invoker_cdecl_@_lambda_19a98c5a81a3f7f216e793bf8327e4a2_@@CAXPEAUHSWDEVICE__@@JPEAXPEBG@Z; _lambda_19a98c5a81a3f7f216e793bf8327e4a2_::_lambda_invoker_cdecl_(HSWDEVICE__ *,long,void *,ushort const *)
0x18000c2bf  mov     [rsp+1B0h+var_188], rax
0x18000c2c4  lea     rax, [rbp+0B0h+var_100]
0x18000c2c8  mov     [rsp+1B0h+var_190], rax
0x18000c2cd  mov     r9d, 4
0x18000c2d3  lea     r8, [rsp+1B0h+var_150]
0x18000c2d8  lea     rdx, aHtreeRoot0; "HTREE\\ROOT\\0"
0x18000c2df  lea     rcx, aXboxgipsynthet_0; "XboxgipSynthetic"
0x18000c2e6  call    cs:__imp_SwDeviceCreate
0x18000c2ec  mov     ebx, eax
0x18000c2ee  lea     rdi, WPP_GLOBAL_Control
0x18000c2f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c2fc  cmp     rcx, rdi
0x18000c2ff  jz      short loc_18000C325
0x18000c301  test    byte ptr [rcx+1Ch], 8
0x18000c305  jz      short loc_18000C325
0x18000c307  cmp     byte ptr [rcx+19h], 4
0x18000c30b  jb      short loc_18000C325
0x18000c30d  mov     edx, 0Bh
0x18000c312  mov     r9d, eax
0x18000c315  lea     r8, WPP_0dff6f38adfd39e199de348a1fa5a8cf_Traceguids
0x18000c31c  mov     rcx, [rcx+10h]
0x18000c320  call    WPP_SF_D
0x18000c325  mov     ecx, 80000000h
0x18000c32a  lea     eax, [rbx+rcx]
0x18000c32d  test    ecx, eax
0x18000c32f  jnz     short loc_18000C339
0x18000c331  cmp     ebx, 800700B7h
0x18000c337  jnz     short loc_18000C38E
0x18000c339  xor     r8d, r8d; bAlertable
0x18000c33c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000c33f  mov     rcx, [rsp+1B0h+hObject]; hHandle
0x18000c344  call    cs:__imp_WaitForSingleObjectEx
0x18000c34a  cmp     eax, 102h
0x18000c34f  jz      short loc_18000C359
0x18000c351  test    eax, eax
0x18000c353  jnz     loc_18000C3F8
0x18000c359  mov     ebx, [rsp+1B0h+var_168]
0x18000c35d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c364  cmp     rcx, rdi
0x18000c367  jz      short loc_18000C38E
0x18000c369  test    byte ptr [rcx+1Ch], 8
0x18000c36d  jz      short loc_18000C38E
0x18000c36f  cmp     byte ptr [rcx+19h], 4
0x18000c373  jb      short loc_18000C38E
0x18000c375  mov     edx, 0Ch
0x18000c37a  mov     r9d, ebx
0x18000c37d  lea     r8, WPP_0dff6f38adfd39e199de348a1fa5a8cf_Traceguids
0x18000c384  mov     rcx, [rcx+10h]
0x18000c388  call    WPP_SF_D
0x18000c38d  nop
0x18000c38e  mov     rcx, [rsp+1B0h+hObject]; hObject
0x18000c393  test    rcx, rcx
0x18000c396  jz      short loc_18000C3A2
0x18000c398  call    cs:__imp_CloseHandle
0x18000c39e  test    eax, eax
0x18000c3a0  jz      short loc_18000C3C0
0x18000c3a2  mov     eax, ebx
0x18000c3a4  mov     rcx, [rbp+0B0h+var_40]
0x18000c3a8  xor     rcx, rsp; StackCookie
0x18000c3ab  call    __security_check_cookie
0x18000c3b0  add     rsp, 188h
0x18000c3b7  pop     r15
0x18000c3b9  pop     r14
0x18000c3bb  pop     rdi
0x18000c3bc  pop     rsi
0x18000c3bd  pop     rbx
0x18000c3be  pop     rbp
0x18000c3bf  retn
0x18000c3c0  mov     rcx, [rbp+0B8h]; this
0x18000c3c7  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c3ce  mov     edx, 0A0Bh; void *
0x18000c3d3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c3d9  mov     rcx, [rbp+0B8h]; this
0x18000c3e0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18000c3e6  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c3ed  mov     edx, 0A0Bh; void *
0x18000c3f2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c3f8  mov     rcx, [rbp+0B8h]; this
0x18000c3ff  mov     edx, 0B0Fh; void *
0x18000c404  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
