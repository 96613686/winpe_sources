# Rdp::Avenc::Yuv::CYuvProcessor::ProcessIoctl(bool,unsigned __int64,void *,unsigned __int64,void *,uint *)

- ea: `0x18005bae0`
- end: `0x18005bd3a`
- name: `?ProcessIoctl@CYuvProcessor@Yuv@Avenc@Rdp@@UEAAJ_N_KPEAX12PEAI@Z`
- size: `602`
- prototype: `__int64 __fastcall(Rdp::Avenc::Yuv::CYuvProcessor *this, __int64, unsigned __int64, _DWORD *, unsigned __int64, _DWORD *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x18001143c`
- `0x1800146bc`
- `0x180014710`
- `0x180015480`
- `0x18005bae0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005bb4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005bca7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005bb4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005bca7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005bc5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005bc5c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Rdp::Avenc::Yuv::CYuvProcessor::ProcessIoctl(
        Rdp::Avenc::Yuv::CYuvProcessor *this,
        __int64 a2,
        unsigned __int64 a3,
        _DWORD *a4,
        unsigned __int64 a5,
        _DWORD *a6,
        unsigned int *a7)
{
  char v10; // di
  bool v11; // bl
  bool v12; // si
  char CurrentThreadId; // al
  int v14; // r8d
  int v15; // edx
  const char *v16; // r9
  bool v17; // bl
  char v18; // al
  int v19; // r8d
  int v20; // edx
  __int64 result; // rax
  int v22; // [rsp+20h] [rbp-58h]
  int v23; // [rsp+20h] [rbp-58h]
  int v24; // [rsp+20h] [rbp-58h]
  int v25; // [rsp+28h] [rbp-50h]
  char *v26; // [rsp+28h] [rbp-50h]
  int v27; // [rsp+28h] [rbp-50h]
  char *v28; // [rsp+30h] [rbp-48h]
  char *v29; // [rsp+30h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v10 = 1;
  v11 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v12 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v14) = v12;
    LOBYTE(v15) = v11;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v15,
      v14,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v22,
      v25,
      18,
      &WPP_ad6665f7b8be3bbcc1289583115d6a25_Traceguids,
      CurrentThreadId);
  }
  try
  {
    LOBYTE(v22) = *((_BYTE *)this + 168) == 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0xE9,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvprocessor.cpp",
      (const char *)0x8000FFFFLL,
      v22,
      (bool)"Processor is not started",
      v28);
    v26 = "BytesWritten can't be null";
    v23 = (int)a7;
    wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
      retaddr,
      234,
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvprocessor.cpp",
      2147500035LL);
    if ( a3 < 0xC )
      wil::details::in1diag3::Throw_NtStatusMsg(
        retaddr,
        (void *)0xF0,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvprocessor.cpp",
        (const char *)0xC0000023LL,
        (int)"Input buffer size is too small to cast to RDPCTRL_HEADER",
        "BytesWritten can't be null");
    *a7 = 0;
    if ( a4[2] )
    {
      LODWORD(v26) = a4[2];
      wil::details::in1diag3::Throw_NtStatusMsg(
        retaddr,
        (void *)0x10A,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvprocessor.cpp",
        (const char *)0xC00000BBLL,
        (int)"Unknown CmdId 0x%lx",
        v26);
    }
    LOBYTE(v23) = a5 < 0x18;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0xFE,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvprocessor.cpp",
      (const char *)0x8007007ALL,
      v23,
      (bool)"Buffer size is too small to cast to RDPCTRL_SRC_BIND",
      v29);
    a6[2] = 0;
    *a6 = 24;
    a6[3] = 1;
    a6[4] = 1;
    a6[5] = GetCurrentProcessId();
    *a7 = 24;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v10 = 0;
    }
    v17 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v18 = GetCurrentThreadId();
      LOBYTE(v19) = v17;
      LOBYTE(v20) = v10;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v20,
        v19,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v24,
        v27,
        19,
        &WPP_ad6665f7b8be3bbcc1289583115d6a25_Traceguids,
        v18);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x113,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvprocessor.cpp",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x18005bae0  mov     [rsp+arg_8], rbx
0x18005bae5  mov     [rsp+arg_10], rsi
0x18005baea  push    rdi
0x18005baeb  push    r12
0x18005baed  push    r13
0x18005baef  push    r14
0x18005baf1  push    r15
0x18005baf3  sub     rsp, 50h
0x18005baf7  mov     r13, r9
0x18005bafa  mov     r15, r8
0x18005bafd  mov     r12, rcx
0x18005bb00  lea     rcx, WPP_GLOBAL_Control
0x18005bb07  mov     rax, cs:WPP_GLOBAL_Control
0x18005bb0e  mov     edi, 1
0x18005bb13  cmp     rax, rcx
0x18005bb16  jz      short loc_18005BB29
0x18005bb18  test    [rax+1Ch], dil
0x18005bb1c  jz      short loc_18005BB29
0x18005bb1e  cmp     byte ptr [rax+19h], 4
0x18005bb22  jb      short loc_18005BB29
0x18005bb24  mov     bl, dil
0x18005bb27  jmp     short loc_18005BB2B
0x18005bb29  xor     bl, bl
0x18005bb2b  lea     rax, WPP_RECORDER_INITIALIZED
0x18005bb32  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005bb39  setnz   sil
0x18005bb3d  test    bl, bl
0x18005bb3f  jnz     short loc_18005BB4F
0x18005bb41  test    sil, sil
0x18005bb44  jnz     short loc_18005BB4F
0x18005bb46  lea     r14, WPP_ad6665f7b8be3bbcc1289583115d6a25_Traceguids
0x18005bb4d  jmp     short loc_18005BB85
0x18005bb4f  call    cs:__imp_GetCurrentThreadId
0x18005bb55  mov     dword ptr [rsp+78h+var_38], eax; char
0x18005bb59  lea     r14, WPP_ad6665f7b8be3bbcc1289583115d6a25_Traceguids
0x18005bb60  mov     [rsp+78h+MessageGuid], r14; MessageGuid
0x18005bb65  mov     word ptr [rsp+78h+var_48], 12h; char *
0x18005bb6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bb73  mov     r9, [rcx+28h]; int
0x18005bb77  mov     r8b, sil; int
0x18005bb7a  mov     dl, bl; int
0x18005bb7c  mov     rcx, [rcx+10h]; int
0x18005bb80  call    WPP_RECORDER_AND_TRACE_SF_D
0x18005bb85  cmp     byte ptr [r12+0A8h], 0
0x18005bb8e  setz    al
0x18005bb91  mov     rcx, [rsp+78h]; this
0x18005bb96  lea     rdx, aProcessorIsNot; "Processor is not started"
0x18005bb9d  mov     [rsp+78h+var_50], rdx; bool
0x18005bba2  mov     byte ptr [rsp+78h+var_58], al; int
0x18005bba6  mov     r9d, 8000FFFFh; char *
0x18005bbac  lea     rbx, aOnecoreuapTerm_33; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18005bbb3  mov     r8, rbx; unsigned int
0x18005bbb6  mov     edx, 0E9h; void *
0x18005bbbb  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18005bbc0  mov     rcx, [rsp+78h]
0x18005bbc5  lea     rax, aByteswrittenCa; "BytesWritten can't be null"
0x18005bbcc  mov     [rsp+78h+var_50], rax; char *
0x18005bbd1  mov     rsi, [rsp+78h+arg_30]
0x18005bbd9  mov     qword ptr [rsp+78h+var_58], rsi
0x18005bbde  mov     r9d, 80004003h
0x18005bbe4  mov     r8, rbx
0x18005bbe7  mov     edx, 0EAh
0x18005bbec  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x18005bbf1  mov     rcx, [rsp+78h]; this
0x18005bbf6  mov     r8, rbx; unsigned int
0x18005bbf9  cmp     r15, 0Ch
0x18005bbfd  jb      loc_18005BCFC
0x18005bc03  mov     dword ptr [rsi], 0
0x18005bc09  mov     eax, [r13+8]
0x18005bc0d  test    eax, eax
0x18005bc0f  jnz     loc_18005BD18
0x18005bc15  cmp     [rsp+78h+arg_20], 18h
0x18005bc1e  setb    al
0x18005bc21  lea     rdx, aBufferSizeIsTo_5; "Buffer size is too small to cast to RDP"...
0x18005bc28  mov     [rsp+78h+var_50], rdx; int
0x18005bc2d  mov     byte ptr [rsp+78h+var_58], al; int
0x18005bc31  mov     r9d, 8007007Ah; char *
0x18005bc37  mov     edx, 0FEh; void *
0x18005bc3c  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18005bc41  mov     rbx, [rsp+78h+arg_28]
0x18005bc49  mov     dword ptr [rbx+8], 0
0x18005bc50  mov     dword ptr [rbx], 18h
0x18005bc56  mov     [rbx+0Ch], edi
0x18005bc59  mov     [rbx+10h], edi
0x18005bc5c  call    cs:__imp_GetCurrentProcessId
0x18005bc62  mov     [rbx+14h], eax
0x18005bc65  mov     dword ptr [rsi], 18h
0x18005bc6b  mov     rax, cs:WPP_GLOBAL_Control
0x18005bc72  lea     rcx, WPP_GLOBAL_Control
0x18005bc79  cmp     rax, rcx
0x18005bc7c  jz      short loc_18005BC8A
0x18005bc7e  test    [rax+1Ch], dil
0x18005bc82  jz      short loc_18005BC8A
0x18005bc84  cmp     byte ptr [rax+19h], 4
0x18005bc88  jnb     short loc_18005BC8D
0x18005bc8a  xor     dil, dil
0x18005bc8d  lea     rax, WPP_RECORDER_INITIALIZED
0x18005bc94  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005bc9b  setnz   bl
0x18005bc9e  test    dil, dil
0x18005bca1  jnz     short loc_18005BCA7
0x18005bca3  test    bl, bl
0x18005bca5  jz      short loc_18005BCD7
0x18005bca7  call    cs:__imp_GetCurrentThreadId
0x18005bcad  mov     dword ptr [rsp+78h+var_38], eax; char
0x18005bcb1  mov     [rsp+78h+MessageGuid], r14; MessageGuid
0x18005bcb6  mov     word ptr [rsp+78h+var_48], 13h; __int16
0x18005bcbd  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bcc4  mov     r9, [rcx+28h]; int
0x18005bcc8  mov     r8b, bl; int
0x18005bccb  mov     dl, dil; int
0x18005bcce  mov     rcx, [rcx+10h]; int
0x18005bcd2  call    WPP_RECORDER_AND_TRACE_SF_D
0x18005bcd7  xor     eax, eax
0x18005bcd9  jmp     short loc_18005BCE2
0x18005bcdb  mov     eax, [rsp+78h+arg_0]
0x18005bce2  lea     r11, [rsp+78h+var_28]
0x18005bce7  mov     rbx, [r11+38h]
0x18005bceb  mov     rsi, [r11+40h]
0x18005bcef  mov     rsp, r11
0x18005bcf2  pop     r15
0x18005bcf4  pop     r14
0x18005bcf6  pop     r13
0x18005bcf8  pop     r12
0x18005bcfa  pop     rdi
0x18005bcfb  retn
0x18005bcfc  lea     rax, aInputBufferSiz_8; "Input buffer size is too small to cast "...
0x18005bd03  mov     qword ptr [rsp+78h+var_58], rax; int
0x18005bd08  mov     r9d, 0C0000023h; char *
0x18005bd0e  mov     edx, 0F0h; void *
0x18005bd13  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x18005bd18  mov     dword ptr [rsp+78h+var_50], eax; char *
0x18005bd1c  lea     rax, aUnknownCmdid0x; "Unknown CmdId 0x%lx"
0x18005bd23  mov     qword ptr [rsp+78h+var_58], rax; int
0x18005bd28  mov     r9d, 0C00000BBh; char *
0x18005bd2e  mov     edx, 10Ah; void *
0x18005bd33  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
```
