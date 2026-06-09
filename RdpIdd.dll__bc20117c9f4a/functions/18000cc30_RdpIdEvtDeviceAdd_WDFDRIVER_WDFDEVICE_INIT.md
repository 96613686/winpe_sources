# RdpIdEvtDeviceAdd(WDFDRIVER__ *,WDFDEVICE_INIT *)

- ea: `0x18000cc30`
- end: `0x18000ce77`
- name: `?RdpIdEvtDeviceAdd@@YAJPEAUWDFDRIVER__@@PEAUWDFDEVICE_INIT@@@Z`
- size: `583`
- prototype: `__int64 __fastcall(struct WDFDRIVER__ *, struct WDFDEVICE_INIT *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180007b38`
- `0x18000cc30`
- `0x18000dbd8`
- `0x18000f31c`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cc9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ce19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cc9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ce19`

## pseudocode

```c
__int64 __fastcall RdpIdEvtDeviceAdd(struct WDFDRIVER__ *a1, struct WDFDEVICE_INIT *a2)
{
  char v3; // bl
  bool v4; // di
  bool v5; // r14
  char CurrentThreadId; // al
  int v7; // r8d
  int v8; // edx
  const char *v9; // r9
  bool v10; // di
  char v11; // al
  int v12; // r8d
  int v13; // edx
  __int64 result; // rax
  int v15; // [rsp+20h] [rbp-148h]
  int v16; // [rsp+28h] [rbp-140h]
  _QWORD v17[4]; // [rsp+50h] [rbp-118h] BYREF
  int v18; // [rsp+70h] [rbp-F8h]
  int v19; // [rsp+74h] [rbp-F4h]
  __int128 v20; // [rsp+78h] [rbp-F0h] BYREF
  __int64 v21; // [rsp+88h] [rbp-E0h]
  __int64 v22; // [rsp+90h] [rbp-D8h]
  __int128 v23; // [rsp+98h] [rbp-D0h]
  __int64 *v24; // [rsp+A8h] [rbp-C0h]
  int v25[10]; // [rsp+B0h] [rbp-B8h] BYREF
  __int64 (__fastcall *v26)(struct WDFDEVICE__ *, struct WDFCMRESLIST__ *, struct WDFCMRESLIST__ *); // [rsp+D8h] [rbp-90h]
  __int64 (__fastcall *v27)(struct WDFDEVICE__ *, struct WDFCMRESLIST__ *); // [rsp+E0h] [rbp-88h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v3 = 1;
  v4 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v5 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v7) = v5;
    LOBYTE(v8) = v4;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      v7,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v15,
      v16,
      12,
      &WPP_70c27897107932ddeed0a391b27b7ece_Traceguids,
      CurrentThreadId);
  }
  if ( byte_180057E4A )
    __debugbreak();
  memset_0(v25, 0, 0x90u);
  v25[0] = 144;
  v26 = RdpIdEvtDevicePrepareHardware;
  v27 = RdpIdEvtDeviceReleaseHardware;
  try
  {
    (*(void (**)(void))(WdfFunctions_02025 + 152))();
    v17[0] = 40;
    v17[1] = RdpIdEvtFileCreate;
    v17[2] = RdpIdEvtFileClose;
    v17[3] = 0;
    v19 = 4;
    v18 = 2;
    v20 = 0;
    v21 = 0;
    v23 = 0;
    LODWORD(v20) = 56;
    v22 = 0x200000001LL;
    v24 = off_180057020;
    (*(void (__fastcall **)(__int64, struct WDFDEVICE_INIT *, _QWORD *, __int128 *))(WdfFunctions_02025 + 184))(
      WdfDriverGlobals,
      a2,
      v17,
      &v20);
    RdpIdCreateDevice(a2);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v3 = 0;
    }
    v10 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v11 = GetCurrentThreadId();
      LOBYTE(v12) = v10;
      LOBYTE(v13) = v3;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        v12,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v15,
        v16,
        13,
        &WPP_70c27897107932ddeed0a391b27b7ece_Traceguids,
        v11);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Nt_Return_CaughtException(
                           retaddr,
                           (void *)0xBD,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\driver.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x18000cc30  mov     [rsp+arg_0], rbx
0x18000cc35  mov     [rsp+arg_8], rsi
0x18000cc3a  push    rdi
0x18000cc3b  push    r12
0x18000cc3d  push    r13
0x18000cc3f  push    r14
0x18000cc41  push    r15
0x18000cc43  sub     rsp, 140h
0x18000cc4a  mov     r15, rdx
0x18000cc4d  lea     r12, WPP_GLOBAL_Control
0x18000cc54  mov     rax, cs:WPP_GLOBAL_Control
0x18000cc5b  mov     ebx, 1
0x18000cc60  cmp     rax, r12
0x18000cc63  jz      short loc_18000CC75
0x18000cc65  test    [rax+1Ch], bl
0x18000cc68  jz      short loc_18000CC75
0x18000cc6a  cmp     byte ptr [rax+19h], 4
0x18000cc6e  jb      short loc_18000CC75
0x18000cc70  mov     dil, bl
0x18000cc73  jmp     short loc_18000CC78
0x18000cc75  xor     dil, dil
0x18000cc78  lea     r13, WPP_RECORDER_INITIALIZED
0x18000cc7f  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000cc86  setnz   r14b
0x18000cc8a  test    dil, dil
0x18000cc8d  jnz     short loc_18000CC9D
0x18000cc8f  test    r14b, r14b
0x18000cc92  jnz     short loc_18000CC9D
0x18000cc94  lea     rsi, WPP_70c27897107932ddeed0a391b27b7ece_Traceguids
0x18000cc9b  jmp     short loc_18000CCDA
0x18000cc9d  call    cs:__imp_GetCurrentThreadId
0x18000cca4  nop     dword ptr [rax+rax+00h]
0x18000cca9  mov     dword ptr [rsp+168h+var_128], eax; char
0x18000ccad  lea     rsi, WPP_70c27897107932ddeed0a391b27b7ece_Traceguids
0x18000ccb4  mov     [rsp+168h+MessageGuid], rsi; MessageGuid
0x18000ccb9  mov     [rsp+168h+var_138], 0Ch; __int16
0x18000ccc0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ccc7  mov     r9, [rcx+28h]; int
0x18000cccb  mov     r8b, r14b; int
0x18000ccce  mov     dl, dil; int
0x18000ccd1  mov     rcx, [rcx+10h]; int
0x18000ccd5  call    WPP_RECORDER_AND_TRACE_SF_D
0x18000ccda  cmp     cs:byte_180057E4A, 0
0x18000cce1  jz      short loc_18000CCE4
0x18000cce3  int     3; Trap to Debugger
0x18000cce4  mov     edi, 90h
0x18000cce9  mov     r8d, edi; Size
0x18000ccec  xor     edx, edx; Val
0x18000ccee  lea     rcx, [rsp+168h+var_B8]; void *
0x18000ccf6  call    memset_0
0x18000ccfb  mov     [rsp+168h+var_B8], edi
0x18000cd02  lea     rax, ?RdpIdEvtDevicePrepareHardware@@YAJPEAUWDFDEVICE__@@PEAUWDFCMRESLIST__@@1@Z; RdpIdEvtDevicePrepareHardware(WDFDEVICE__ *,WDFCMRESLIST__ *,WDFCMRESLIST__ *)
0x18000cd09  mov     [rsp+168h+var_90], rax
0x18000cd11  lea     rax, ?RdpIdEvtDeviceReleaseHardware@@YAJPEAUWDFDEVICE__@@PEAUWDFCMRESLIST__@@@Z; RdpIdEvtDeviceReleaseHardware(WDFDEVICE__ *,WDFCMRESLIST__ *)
0x18000cd18  mov     [rsp+168h+var_88], rax
0x18000cd20  mov     rax, cs:WdfFunctions_02025
0x18000cd27  lea     r8, [rsp+168h+var_B8]
0x18000cd2f  mov     rdx, r15
0x18000cd32  mov     rcx, cs:WdfDriverGlobals
0x18000cd39  mov     rax, [rax+98h]
0x18000cd40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd45  mov     [rsp+168h+var_118], 28h ; '('
0x18000cd4e  lea     rax, ?RdpIdEvtFileCreate@@YAXPEAUWDFDEVICE__@@PEAUWDFREQUEST__@@PEAUWDFFILEOBJECT__@@@Z; RdpIdEvtFileCreate(WDFDEVICE__ *,WDFREQUEST__ *,WDFFILEOBJECT__ *)
0x18000cd55  mov     [rsp+168h+var_110], rax
0x18000cd5a  lea     rax, ?RdpIdEvtFileClose@@YAXPEAUWDFFILEOBJECT__@@@Z; RdpIdEvtFileClose(WDFFILEOBJECT__ *)
0x18000cd61  mov     [rsp+168h+var_108], rax
0x18000cd66  mov     [rsp+168h+var_100], 0
0x18000cd6f  mov     [rsp+168h+var_F4], 4
0x18000cd77  mov     ecx, 2
0x18000cd7c  mov     [rsp+168h+var_F8], ecx
0x18000cd80  xorps   xmm0, xmm0
0x18000cd83  movups  [rsp+168h+var_F0], xmm0
0x18000cd88  movups  [rsp+168h+var_E0], xmm0
0x18000cd90  movups  [rsp+168h+var_D0], xmm0
0x18000cd98  mov     dword ptr [rsp+168h+var_F0], 38h ; '8'
0x18000cda0  mov     dword ptr [rsp+168h+var_E0+8], ebx
0x18000cda7  mov     rax, cs:off_180057020
0x18000cdae  mov     [rsp+168h+var_C0], rax
0x18000cdb6  mov     dword ptr [rsp+168h+var_E0+0Ch], ecx
0x18000cdbd  mov     rax, cs:WdfFunctions_02025
0x18000cdc4  lea     r9, [rsp+168h+var_F0]
0x18000cdc9  lea     r8, [rsp+168h+var_118]
0x18000cdce  mov     rdx, r15
0x18000cdd1  mov     rcx, cs:WdfDriverGlobals
0x18000cdd8  mov     rax, [rax+0B8h]
0x18000cddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cde4  mov     rcx, r15; struct WDFDEVICE_INIT *
0x18000cde7  call    ?RdpIdCreateDevice@@YAXPEAUWDFDEVICE_INIT@@@Z; RdpIdCreateDevice(WDFDEVICE_INIT *)
0x18000cdec  mov     rax, cs:WPP_GLOBAL_Control
0x18000cdf3  cmp     rax, r12
0x18000cdf6  jz      short loc_18000CE03
0x18000cdf8  test    [rax+1Ch], bl
0x18000cdfb  jz      short loc_18000CE03
0x18000cdfd  cmp     byte ptr [rax+19h], 4
0x18000ce01  jnb     short loc_18000CE05
0x18000ce03  xor     bl, bl
0x18000ce05  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000ce0c  setnz   dil
0x18000ce10  test    bl, bl
0x18000ce12  jnz     short loc_18000CE19
0x18000ce14  test    dil, dil
0x18000ce17  jz      short loc_18000CE4E
0x18000ce19  call    cs:__imp_GetCurrentThreadId
0x18000ce20  nop     dword ptr [rax+rax+00h]
0x18000ce25  mov     dword ptr [rsp+168h+var_128], eax; char
0x18000ce29  mov     [rsp+168h+MessageGuid], rsi; MessageGuid
0x18000ce2e  mov     [rsp+168h+var_138], 0Dh; __int16
0x18000ce35  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce3c  mov     r9, [rcx+28h]; int
0x18000ce40  mov     r8b, dil; int
0x18000ce43  mov     dl, bl; int
0x18000ce45  mov     rcx, [rcx+10h]; int
0x18000ce49  call    WPP_RECORDER_AND_TRACE_SF_D
0x18000ce4e  xor     eax, eax
0x18000ce50  jmp     short loc_18000CE59
0x18000ce52  mov     eax, [rsp+168h+arg_10]
0x18000ce59  lea     r11, [rsp+168h+var_28]
0x18000ce61  mov     rbx, [r11+30h]
0x18000ce65  mov     rsi, [r11+38h]
0x18000ce69  mov     rsp, r11
0x18000ce6c  pop     r15
0x18000ce6e  pop     r14
0x18000ce70  pop     r13
0x18000ce72  pop     r12
0x18000ce74  pop     rdi
0x18000ce75  retn
```
