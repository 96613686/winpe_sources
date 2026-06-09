# RdpIdQueueInitialize

- ea: `0x180011e08`
- end: `0x18001210e`
- name: `RdpIdQueueInitialize`
- size: `774`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000f31c`

## callees

- `0x180007b38`
- `0x18000dbd8`
- `0x1800106b8`
- `0x180011e08`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011e6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800120c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011e6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800120c0`

## string_xrefs

- `0x180011f91`: `Failed to configure default queue for read`
- `0x180011fd5`: `Failed to configure default queue for write`

## pseudocode

```c
_UNKNOWN **__fastcall RdpIdQueueInitialize(__int64 a1)
{
  char v2; // di
  bool v3; // bl
  bool v4; // si
  char CurrentThreadId; // al
  int v6; // r8d
  int v7; // edx
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  __int64 v11; // rbx
  unsigned int v12; // eax
  _UNKNOWN **result; // rax
  bool v14; // bl
  char v15; // al
  int v16; // r8d
  int v17; // edx
  int v18; // [rsp+20h] [rbp-A9h]
  int v19; // [rsp+20h] [rbp-A9h]
  const char *v20; // [rsp+28h] [rbp-A1h]
  const char *v21; // [rsp+28h] [rbp-A1h]
  const char *v22; // [rsp+28h] [rbp-A1h]
  const char *v23; // [rsp+28h] [rbp-A1h]
  int v24; // [rsp+28h] [rbp-A1h]
  int v25; // [rsp+50h] [rbp-79h] BYREF
  __int64 v26; // [rsp+54h] [rbp-75h]
  _BYTE v27[12]; // [rsp+5Ch] [rbp-6Dh] BYREF
  void *v28; // [rsp+68h] [rbp-61h]
  void *v29; // [rsp+70h] [rbp-59h]
  int v30; // [rsp+A0h] [rbp-29h]
  __int64 v31; // [rsp+A8h] [rbp-21h]
  __int128 v32; // [rsp+B0h] [rbp-19h] BYREF
  __int64 v33; // [rsp+C0h] [rbp-9h]
  __int64 v34; // [rsp+C8h] [rbp-1h]
  __int128 v35; // [rsp+D0h] [rbp+7h]
  __int64 v36; // [rsp+E0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]
  __int64 v38; // [rsp+138h] [rbp+6Fh] BYREF

  v2 = 1;
  v3 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v4 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v6) = v4;
    LOBYTE(v7) = v3;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      v6,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v18,
      (int)v20,
      10,
      &WPP_2e15f101429739f78915c2e5bbc8982e_Traceguids,
      CurrentThreadId);
  }
  v38 = 0;
  v33 = 0;
  v36 = 0;
  v32 = 0;
  LODWORD(v32) = 56;
  v35 = 0;
  v34 = 0x300000001LL;
  memset_0(&v25, 0, 0x60u);
  v28 = &RdpIdEvtIoRead;
  v25 = 96;
  v29 = &RdpIdEvtIoWrite;
  v30 = -1;
  v26 = 2;
  v31 = *(_QWORD *)WdfDriverGlobals;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64, int *, __int128 *, __int64 *))(WdfFunctions_02025 + 680))(
         WdfDriverGlobals,
         a1,
         &v25,
         &v32,
         &v38);
  wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
    retaddr,
    (void *)0x5B,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\queue.cpp",
    (const char *)v8,
    (int)"Failed to initialize default queue",
    v20);
  v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(WdfFunctions_02025 + 320))(
         WdfDriverGlobals,
         a1,
         v38,
         3);
  wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
    retaddr,
    (void *)0x62,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\queue.cpp",
    (const char *)v9,
    (int)"Failed to configure default queue for read",
    v21);
  v10 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(WdfFunctions_02025 + 320))(
          WdfDriverGlobals,
          a1,
          v38,
          4);
  wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
    retaddr,
    (void *)0x69,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\queue.cpp",
    (const char *)v10,
    (int)"Failed to configure default queue for write",
    v22);
  v11 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(WdfFunctions_02025 + 984))(
          WdfDriverGlobals,
          a1,
          off_180057078);
  memset_0(v27, 0, 0x54u);
  v25 = 96;
  v26 = 0x200000003LL;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64, int *, _QWORD, __int64))(WdfFunctions_02025 + 680))(
          WdfDriverGlobals,
          a1,
          &v25,
          0,
          v11 + 16);
  wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
    retaddr,
    (void *)0x7C,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\queue.cpp",
    (const char *)v12,
    (int)"Failed to initialize pending Ioctl queue",
    v23);
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    v2 = 0;
  }
  result = &WPP_RECORDER_INITIALIZED;
  v14 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v15 = GetCurrentThreadId();
    LOBYTE(v16) = v14;
    LOBYTE(v17) = v2;
    return (_UNKNOWN **)WPP_RECORDER_AND_TRACE_SF_D(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          v17,
                          v16,
                          *((_QWORD *)WPP_GLOBAL_Control + 5),
                          v19,
                          v24,
                          11,
                          &WPP_2e15f101429739f78915c2e5bbc8982e_Traceguids,
                          v15);
  }
  return result;
}

```

## disassembly

```asm
0x180011e08  push    rbp
0x180011e0a  push    rbx
0x180011e0b  push    rsi
0x180011e0c  push    rdi
0x180011e0d  push    r14
0x180011e0f  push    r15
0x180011e11  lea     rbp, [rsp-2Fh]
0x180011e16  sub     rsp, 0F8h
0x180011e1d  mov     r14, rcx
0x180011e20  mov     rax, cs:WPP_GLOBAL_Control
0x180011e27  lea     rcx, WPP_GLOBAL_Control
0x180011e2e  mov     edi, 1
0x180011e33  cmp     rax, rcx
0x180011e36  jz      short loc_180011E49
0x180011e38  test    [rax+1Ch], dil
0x180011e3c  jz      short loc_180011E49
0x180011e3e  cmp     byte ptr [rax+19h], 4
0x180011e42  jb      short loc_180011E49
0x180011e44  mov     bl, dil
0x180011e47  jmp     short loc_180011E4B
0x180011e49  xor     bl, bl
0x180011e4b  lea     rax, WPP_RECORDER_INITIALIZED
0x180011e52  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180011e59  lea     r15, WPP_2e15f101429739f78915c2e5bbc8982e_Traceguids
0x180011e60  setnz   sil
0x180011e64  test    bl, bl
0x180011e66  jnz     short loc_180011E6D
0x180011e68  test    sil, sil
0x180011e6b  jz      short loc_180011EA2
0x180011e6d  call    cs:__imp_GetCurrentThreadId
0x180011e74  nop     dword ptr [rax+rax+00h]
0x180011e79  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e80  mov     r8b, sil; int
0x180011e83  mov     dword ptr [rsp+120h+var_E0], eax; char
0x180011e87  mov     dl, bl; int
0x180011e89  mov     [rsp+120h+MessageGuid], r15; MessageGuid
0x180011e8e  mov     [rsp+120h+var_F0], 0Ah; __int16
0x180011e95  mov     r9, [rcx+28h]; int
0x180011e99  mov     rcx, [rcx+10h]; int
0x180011e9d  call    WPP_RECORDER_AND_TRACE_SF_D
0x180011ea2  xorps   xmm0, xmm0
0x180011ea5  mov     [rbp+57h+arg_8], 0
0x180011ead  xor     eax, eax
0x180011eaf  lea     rcx, [rbp+57h+var_D0]; void *
0x180011eb3  movups  [rbp+57h+var_60], xmm0
0x180011eb7  xor     edx, edx; Val
0x180011eb9  mov     [rbp+57h+var_40], rax
0x180011ebd  movups  [rbp+57h+var_70], xmm0
0x180011ec1  lea     r8d, [rax+60h]; Size
0x180011ec5  mov     dword ptr [rbp+57h+var_70], 38h ; '8'
0x180011ecc  movups  [rbp+57h+var_50], xmm0
0x180011ed0  mov     dword ptr [rbp+57h+var_60+8], edi
0x180011ed3  mov     dword ptr [rbp+57h+var_60+0Ch], 3
0x180011eda  call    memset_0
0x180011edf  mov     rcx, cs:WdfDriverGlobals
0x180011ee6  lea     rax, RdpIdEvtIoRead
0x180011eed  mov     [rbp+57h+var_B8], rax
0x180011ef1  lea     rdx, [rbp+57h+arg_8]
0x180011ef5  mov     [rbp+57h+var_D0], 60h ; '`'
0x180011efc  lea     rax, RdpIdEvtIoWrite
0x180011f03  mov     [rbp+57h+var_B0], rax
0x180011f07  lea     r9, [rbp+57h+var_70]
0x180011f0b  mov     [rbp+57h+var_80], 0FFFFFFFFh
0x180011f12  lea     r8, [rbp+57h+var_D0]
0x180011f16  mov     qword ptr [rsp+120h+var_100], rdx
0x180011f1b  mov     r15d, 2
0x180011f21  mov     [rbp+57h+var_CC], r15
0x180011f25  mov     rdx, r14
0x180011f28  mov     rax, [rcx]
0x180011f2b  mov     [rbp+57h+var_78], rax
0x180011f2f  mov     rax, cs:WdfFunctions_02025
0x180011f36  mov     rax, [rax+2A8h]
0x180011f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f42  mov     rcx, [rbp+5Fh]; this
0x180011f46  lea     rdx, aFailedToInitia_1; "Failed to initialize default queue"
0x180011f4d  mov     qword ptr [rsp+120h+var_100], rdx; int
0x180011f52  lea     rsi, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180011f59  lea     edx, [r15+59h]; void *
0x180011f5d  mov     r9d, eax; char *
0x180011f60  mov     r8, rsi; unsigned int
0x180011f63  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x180011f68  mov     rax, cs:WdfFunctions_02025
0x180011f6f  lea     r9d, [r15+1]
0x180011f73  mov     r8, [rbp+57h+arg_8]
0x180011f77  mov     rdx, r14
0x180011f7a  mov     rcx, cs:WdfDriverGlobals
0x180011f81  mov     rax, [rax+140h]
0x180011f88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f8d  mov     rcx, [rbp+5Fh]; this
0x180011f91  lea     rdx, aFailedToConfig; "Failed to configure default queue for r"...
0x180011f98  mov     qword ptr [rsp+120h+var_100], rdx; int
0x180011f9d  mov     r9d, eax; char *
0x180011fa0  lea     edx, [r15+60h]; void *
0x180011fa4  mov     r8, rsi; unsigned int
0x180011fa7  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x180011fac  mov     rax, cs:WdfFunctions_02025
0x180011fb3  lea     r9d, [r15+2]
0x180011fb7  mov     r8, [rbp+57h+arg_8]
0x180011fbb  mov     rdx, r14
0x180011fbe  mov     rcx, cs:WdfDriverGlobals
0x180011fc5  mov     rax, [rax+140h]
0x180011fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fd1  mov     rcx, [rbp+5Fh]; this
0x180011fd5  lea     rdx, aFailedToConfig_0; "Failed to configure default queue for w"...
0x180011fdc  mov     qword ptr [rsp+120h+var_100], rdx; int
0x180011fe1  mov     r9d, eax; char *
0x180011fe4  lea     edx, [r15+67h]; void *
0x180011fe8  mov     r8, rsi; unsigned int
0x180011feb  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x180011ff0  mov     rax, cs:WdfFunctions_02025
0x180011ff7  mov     rdx, r14
0x180011ffa  mov     r8, cs:off_180057078
0x180012001  mov     rcx, cs:WdfDriverGlobals
0x180012008  mov     rax, [rax+3D8h]
0x18001200f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012014  xor     edx, edx; Val
0x180012016  lea     r8d, [r15+52h]; Size
0x18001201a  lea     rcx, [rbp+57h+var_C4]; void *
0x18001201e  mov     rbx, rax
0x180012021  call    memset_0
0x180012026  mov     [rbp+57h+var_D0], 60h ; '`'
0x18001202d  mov     rax, cs:WdfFunctions_02025
0x180012034  lea     rcx, [rbx+10h]
0x180012038  mov     dword ptr [rbp+57h+var_CC+4], r15d
0x18001203c  lea     r8, [rbp+57h+var_D0]
0x180012040  mov     dword ptr [rbp+57h+var_CC], 3
0x180012047  xor     r9d, r9d
0x18001204a  mov     qword ptr [rsp+120h+var_100], rcx
0x18001204f  mov     rdx, r14
0x180012052  mov     rax, [rax+2A8h]
0x180012059  mov     rcx, cs:WdfDriverGlobals
0x180012060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012065  mov     rcx, [rbp+5Fh]; this
0x180012069  lea     rdx, aFailedToInitia_2; "Failed to initialize pending Ioctl queu"...
0x180012070  mov     qword ptr [rsp+120h+var_100], rdx; int
0x180012075  mov     r9d, eax; char *
0x180012078  lea     edx, [r15+7Ah]; void *
0x18001207c  mov     r8, rsi; unsigned int
0x18001207f  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x180012084  mov     rax, cs:WPP_GLOBAL_Control
0x18001208b  lea     rcx, WPP_GLOBAL_Control
0x180012092  cmp     rax, rcx
0x180012095  jz      short loc_1800120A3
0x180012097  test    [rax+1Ch], dil
0x18001209b  jz      short loc_1800120A3
0x18001209d  cmp     byte ptr [rax+19h], 4
0x1800120a1  jnb     short loc_1800120A6
0x1800120a3  xor     dil, dil
0x1800120a6  lea     rax, WPP_RECORDER_INITIALIZED
0x1800120ad  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800120b4  setnz   bl
0x1800120b7  test    dil, dil
0x1800120ba  jnz     short loc_1800120C0
0x1800120bc  test    bl, bl
0x1800120be  jz      short loc_1800120FD
0x1800120c0  call    cs:__imp_GetCurrentThreadId
0x1800120c7  nop     dword ptr [rax+rax+00h]
0x1800120cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800120d3  mov     r8b, bl; int
0x1800120d6  mov     dword ptr [rsp+120h+var_E0], eax; char
0x1800120da  mov     dl, dil; int
0x1800120dd  lea     rax, WPP_2e15f101429739f78915c2e5bbc8982e_Traceguids
0x1800120e4  mov     [rsp+120h+MessageGuid], rax; MessageGuid
0x1800120e9  mov     r9, [rcx+28h]; int
0x1800120ed  mov     rcx, [rcx+10h]; int
0x1800120f1  mov     [rsp+120h+var_F0], 0Bh; __int16
0x1800120f8  call    WPP_RECORDER_AND_TRACE_SF_D
0x1800120fd  add     rsp, 0F8h
0x180012104  pop     r15
0x180012106  pop     r14
0x180012108  pop     rdi
0x180012109  pop     rsi
0x18001210a  pop     rbx
0x18001210b  pop     rbp
0x18001210c  retn
```
