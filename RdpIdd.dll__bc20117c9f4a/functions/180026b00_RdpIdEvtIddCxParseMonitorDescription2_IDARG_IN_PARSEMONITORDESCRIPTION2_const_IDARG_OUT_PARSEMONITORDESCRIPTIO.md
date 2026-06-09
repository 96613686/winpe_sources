# RdpIdEvtIddCxParseMonitorDescription2(IDARG_IN_PARSEMONITORDESCRIPTION2 const *,IDARG_OUT_PARSEMONITORDESCRIPTION *)

- ea: `0x180026b00`
- end: `0x180026ed7`
- name: `?RdpIdEvtIddCxParseMonitorDescription2@@YAJPEBUIDARG_IN_PARSEMONITORDESCRIPTION2@@PEAUIDARG_OUT_PARSEMONITORDESCRIPTION@@@Z`
- size: `983`
- prototype: `__int64 __fastcall(const struct IDARG_IN_PARSEMONITORDESCRIPTION2 *, struct IDARG_OUT_PARSEMONITORDESCRIPTION *)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180006f60`
- `0x18000875c`
- `0x18000dbd8`
- `0x18000e978`
- `0x1800106b8`
- `0x180011584`
- `0x18001dd70`
- `0x180023174`
- `0x180026b00`
- `0x180036fcc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026b8e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026e04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026b8e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026e04`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180026e44`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180026e44`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RdpIdEvtIddCxParseMonitorDescription2(
        const struct IDARG_IN_PARSEMONITORDESCRIPTION2 *a1,
        struct IDARG_OUT_PARSEMONITORDESCRIPTION *a2)
{
  char v4; // bl
  bool v5; // si
  bool v6; // r14
  char CurrentThreadId; // al
  int v8; // r8d
  int v9; // edx
  __int64 v10; // rcx
  __int64 v11; // rax
  unsigned int v12; // eax
  unsigned int v13; // esi
  __int64 v14; // r14
  unsigned int MonitorModes; // eax
  __int64 v16; // r9
  __int64 v17; // r8
  __int64 v18; // rdx
  bool v19; // di
  char v20; // al
  int v21; // r8d
  int v22; // edx
  const char *v23; // r9
  __int64 result; // rax
  int v25; // [rsp+20h] [rbp-98h]
  int v26; // [rsp+20h] [rbp-98h]
  int v27; // [rsp+28h] [rbp-90h]
  const char *v28; // [rsp+28h] [rbp-90h]
  char *v29; // [rsp+30h] [rbp-88h]
  unsigned int v30; // [rsp+50h] [rbp-68h] BYREF
  char v31[4]; // [rsp+54h] [rbp-64h] BYREF
  __int128 v32; // [rsp+58h] [rbp-60h] BYREF
  __int64 v33; // [rsp+68h] [rbp-50h]
  GUID ActivityId; // [rsp+70h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  CAutoSetThreadActivityId::CAutoSetThreadActivityId(
    &ActivityId,
    &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId);
  v4 = 1;
  v5 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v6 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v8) = v6;
    LOBYTE(v9) = v5;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      v8,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v25,
      v27,
      14,
      &WPP_21c286969d51392f6eed59d913c079a0_Traceguids,
      CurrentThreadId);
  }
  v30 = 0;
  *(_DWORD *)v31 = 0;
  try
  {
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x782,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
      (const char *)0x8000FFFFLL,
      *((_DWORD *)a1 + 1) == 2,
      (bool)"DisplayId is not supported",
      v29);
    v11 = *((unsigned int *)a1 + 6);
    if ( (_DWORD)v11 )
    {
      v32 = 0;
      v33 = 0;
      v30 = v11;
      std::vector<_VideoModeDescriptor>::_Resize_reallocate<std::_Value_init_tag>(&v32, v11);
      v14 = *((_QWORD *)a1 + 4);
      MonitorModes = EDID_V1_GetMonitorModes(v31, *((unsigned int *)a1 + 2), *((_QWORD *)a1 + 2), &v30, v32);
      wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
        retaddr,
        (void *)0x7AD,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
        (const char *)MonitorModes,
        (int)"Failed to extract monitor modes from EDID",
        v31);
      v13 = v30;
      if ( *((_DWORD *)a1 + 6) < v30 )
        wil::details::in1diag3::Throw_NtStatusMsg(
          retaddr,
          (void *)0x7B1,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
          (const char *)0x80000005LL,
          (int)"Invalid number of video modes returned from EDID",
          v28);
      v16 = 0;
      if ( v30 )
      {
        do
        {
          v17 = 9 * v16;
          *(_DWORD *)(v14 + 8 * v17) = 72;
          *(_DWORD *)(v14 + 8 * v17 + 4) = 1;
          *(_DWORD *)(v14 + 8 * v17 + 56) = 6;
          v18 = 56LL * (unsigned int)v16;
          *(_DWORD *)(v14 + 8 * v17 + 32) = *(unsigned __int16 *)(v18 + v32 + 20);
          *(_DWORD *)(v14 + 8 * v17 + 36) = *(unsigned __int16 *)(v18 + v32 + 22);
          *(_QWORD *)(v14 + 8 * v17 + 40) = *(_QWORD *)(v14 + 72 * v16 + 32);
          *(_DWORD *)(v14 + 8 * v17 + 24) = *(_DWORD *)(v18 + v32 + 4);
          *(_DWORD *)(v14 + 8 * v17 + 28) = *(_DWORD *)(v18 + v32 + 8);
          *(_DWORD *)(v14 + 8 * v17 + 16) = *(_DWORD *)(v18 + v32 + 12);
          *(_DWORD *)(v14 + 8 * v17 + 20) = *(_DWORD *)(v18 + v32 + 16);
          *(_QWORD *)(v14 + 8 * v17 + 8) = *(unsigned int *)(v18 + v32);
          *(_DWORD *)(v14 + 8 * v17 + 48) = 1;
          *(_DWORD *)(v14 + 8 * v17 + 52) = 1;
          v16 = (unsigned int)(v16 + 1);
        }
        while ( (unsigned int)v16 < v13 );
      }
      if ( (_QWORD)v32 )
        std::_Deallocate<16>(v32, 8 * ((v33 - (__int64)v32) >> 3));
    }
    else
    {
      v28 = v31;
      v12 = EDID_V1_GetMonitorModes(v10, *((unsigned int *)a1 + 2), *((_QWORD *)a1 + 2), &v30, 0);
      if ( v12 != -1073741789 && v12 != -2147483643 || (v13 = v30) == 0 )
        wil::details::in1diag3::Throw_NtStatusMsg(
          retaddr,
          (void *)0x793,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
          (const char *)v12,
          (int)"Failed to parse EDID",
          v31);
    }
    *(_DWORD *)a2 = v13;
    *((_DWORD *)a2 + 1) = *(_DWORD *)v31;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v4 = 0;
    }
    v19 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v20 = GetCurrentThreadId();
      LOBYTE(v21) = v19;
      LOBYTE(v22) = v4;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v22,
        v21,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v26,
        (int)v28,
        15,
        &WPP_21c286969d51392f6eed59d913c079a0_Traceguids,
        v20);
    }
    EventActivityIdControl(2u, &ActivityId);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Nt_Return_CaughtException(
                           retaddr,
                           (void *)0x7D3,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitor.cpp",
                           v23);
  }
  return result;
}

```

## disassembly

```asm
0x180026b00  mov     [rsp+arg_10], rbx
0x180026b05  push    rsi
0x180026b06  push    rdi
0x180026b07  push    r12
0x180026b09  push    r14
0x180026b0b  push    r15
0x180026b0d  sub     rsp, 90h
0x180026b14  mov     rax, cs:__security_cookie
0x180026b1b  xor     rax, rsp
0x180026b1e  mov     [rsp+0B8h+var_38], rax
0x180026b26  mov     r12, rdx
0x180026b29  mov     rdi, rcx
0x180026b2c  lea     rdx, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; struct _GUID *
0x180026b33  lea     rcx, [rsp+0B8h+ActivityId]; ActivityId
0x180026b38  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x180026b3d  nop
0x180026b3e  lea     rcx, WPP_GLOBAL_Control
0x180026b45  mov     rax, cs:WPP_GLOBAL_Control
0x180026b4c  mov     ebx, 1
0x180026b51  cmp     rax, rcx
0x180026b54  jz      short loc_180026B66
0x180026b56  test    [rax+1Ch], bl
0x180026b59  jz      short loc_180026B66
0x180026b5b  cmp     byte ptr [rax+19h], 4
0x180026b5f  jb      short loc_180026B66
0x180026b61  mov     sil, bl
0x180026b64  jmp     short loc_180026B69
0x180026b66  xor     sil, sil
0x180026b69  lea     rax, WPP_RECORDER_INITIALIZED
0x180026b70  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180026b77  setnz   r14b
0x180026b7b  test    sil, sil
0x180026b7e  jnz     short loc_180026B8E
0x180026b80  test    r14b, r14b
0x180026b83  jnz     short loc_180026B8E
0x180026b85  lea     r15, WPP_21c286969d51392f6eed59d913c079a0_Traceguids
0x180026b8c  jmp     short loc_180026BCB
0x180026b8e  call    cs:__imp_GetCurrentThreadId
0x180026b95  nop     dword ptr [rax+rax+00h]
0x180026b9a  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x180026b9e  lea     r15, WPP_21c286969d51392f6eed59d913c079a0_Traceguids
0x180026ba5  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x180026baa  mov     word ptr [rsp+0B8h+var_88], 0Eh; char *
0x180026bb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180026bb8  mov     r9, [rcx+28h]; int
0x180026bbc  mov     r8b, r14b; int
0x180026bbf  mov     dl, sil; int
0x180026bc2  mov     rcx, [rcx+10h]; int
0x180026bc6  call    WPP_RECORDER_AND_TRACE_SF_D
0x180026bcb  mov     [rsp+0B8h+var_68], 0
0x180026bd3  mov     dword ptr [rsp+0B8h+var_64], 0
0x180026bdb  cmp     dword ptr [rdi+4], 2
0x180026bdf  setz    al
0x180026be2  mov     rcx, [rsp+0B8h]; this
0x180026bea  lea     rdx, aDisplayidIsNot; "DisplayId is not supported"
0x180026bf1  mov     [rsp+0B8h+var_90], rdx; bool
0x180026bf6  mov     [rsp+0B8h+var_98], al; char
0x180026bfa  mov     r9d, 8000FFFFh; char *
0x180026c00  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180026c07  mov     edx, 782h; void *
0x180026c0c  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180026c11  mov     eax, [rdi+18h]
0x180026c14  test    eax, eax
0x180026c16  jnz     short loc_180026C5F
0x180026c18  lea     rax, [rsp+0B8h+var_64]
0x180026c1d  mov     [rsp+0B8h+var_90], rax; char *
0x180026c22  mov     qword ptr [rsp+0B8h+var_98], 0
0x180026c2b  lea     r9, [rsp+0B8h+var_68]
0x180026c30  mov     r8, [rdi+10h]
0x180026c34  mov     edx, [rdi+8]
0x180026c37  call    ?EDID_V1_GetMonitorModes@@YAJW4__WMI_MONITOR_CAPABILITY_ORIGIN_TYPE@@KPEBEPEAKPEAU_VideoModeDescriptor@@2@Z; EDID_V1_GetMonitorModes(__WMI_MONITOR_CAPABILITY_ORIGIN_TYPE,ulong,uchar const *,ulong *,_VideoModeDescriptor *,ulong *)
0x180026c3c  cmp     eax, 0C0000023h
0x180026c41  jz      short loc_180026C4E
0x180026c43  cmp     eax, 80000005h
0x180026c48  jnz     loc_180026E81
0x180026c4e  mov     esi, [rsp+0B8h+var_68]
0x180026c52  test    esi, esi
0x180026c54  jz      loc_180026E81
0x180026c5a  jmp     loc_180026DBC
0x180026c5f  xorps   xmm0, xmm0
0x180026c62  movdqu  [rsp+0B8h+var_60], xmm0
0x180026c68  mov     [rsp+0B8h+var_50], 0
0x180026c71  mov     [rsp+0B8h+var_68], eax
0x180026c75  mov     rdx, rax
0x180026c78  lea     rcx, [rsp+0B8h+var_60]
0x180026c7d  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@U_VideoModeDescriptor@@V?$allocator@U_VideoModeDescriptor@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<_VideoModeDescriptor>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180026c82  mov     r14, [rdi+20h]
0x180026c86  mov     rax, qword ptr [rsp+0B8h+var_60]
0x180026c8b  lea     rcx, [rsp+0B8h+var_64]
0x180026c90  mov     [rsp+0B8h+var_90], rcx; char *
0x180026c95  mov     qword ptr [rsp+0B8h+var_98], rax
0x180026c9a  lea     r9, [rsp+0B8h+var_68]
0x180026c9f  mov     r8, [rdi+10h]
0x180026ca3  mov     edx, [rdi+8]
0x180026ca6  call    ?EDID_V1_GetMonitorModes@@YAJW4__WMI_MONITOR_CAPABILITY_ORIGIN_TYPE@@KPEBEPEAKPEAU_VideoModeDescriptor@@2@Z; EDID_V1_GetMonitorModes(__WMI_MONITOR_CAPABILITY_ORIGIN_TYPE,ulong,uchar const *,ulong *,_VideoModeDescriptor *,ulong *)
0x180026cab  mov     rcx, [rsp+0B8h]; this
0x180026cb3  lea     rdx, aFailedToExtrac; "Failed to extract monitor modes from ED"...
0x180026cba  mov     qword ptr [rsp+0B8h+var_98], rdx; int
0x180026cbf  mov     r9d, eax; char *
0x180026cc2  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180026cc9  mov     edx, 7ADh; void *
0x180026cce  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x180026cd3  mov     esi, [rsp+0B8h+var_68]
0x180026cd7  cmp     [rdi+18h], esi
0x180026cda  jb      loc_180026EAA
0x180026ce0  xor     r9d, r9d
0x180026ce3  test    esi, esi
0x180026ce5  jz      loc_180026D8F
0x180026ceb  mov     eax, r9d
0x180026cee  lea     r8, [r9+r9*8]
0x180026cf2  mov     dword ptr [r14+r8*8], 48h ; 'H'
0x180026cfa  mov     [r14+r8*8+4], ebx
0x180026cff  mov     dword ptr [r14+r8*8+38h], 6
0x180026d08  imul    rdx, rax, 38h ; '8'
0x180026d0c  mov     rax, qword ptr [rsp+0B8h+var_60]
0x180026d11  movzx   ecx, word ptr [rdx+rax+14h]
0x180026d16  mov     [r14+r8*8+20h], ecx
0x180026d1b  mov     rax, qword ptr [rsp+0B8h+var_60]
0x180026d20  movzx   ecx, word ptr [rdx+rax+16h]
0x180026d25  mov     [r14+r8*8+24h], ecx
0x180026d2a  mov     rax, [r14+r8*8+20h]
0x180026d2f  mov     [r14+r8*8+28h], rax
0x180026d34  mov     rax, qword ptr [rsp+0B8h+var_60]
0x180026d39  mov     ecx, [rdx+rax+4]
0x180026d3d  mov     [r14+r8*8+18h], ecx
0x180026d42  mov     rax, qword ptr [rsp+0B8h+var_60]
0x180026d47  mov     ecx, [rdx+rax+8]
0x180026d4b  mov     [r14+r8*8+1Ch], ecx
0x180026d50  mov     rax, qword ptr [rsp+0B8h+var_60]
0x180026d55  mov     ecx, [rdx+rax+0Ch]
0x180026d59  mov     [r14+r8*8+10h], ecx
0x180026d5e  mov     rax, qword ptr [rsp+0B8h+var_60]
0x180026d63  mov     ecx, [rdx+rax+10h]
0x180026d67  mov     [r14+r8*8+14h], ecx
0x180026d6c  mov     rax, qword ptr [rsp+0B8h+var_60]
0x180026d71  mov     ecx, [rdx+rax]
0x180026d74  mov     [r14+r8*8+8], rcx
0x180026d79  mov     [r14+r8*8+30h], ebx
0x180026d7e  mov     [r14+r8*8+34h], ebx
0x180026d83  add     r9d, ebx
0x180026d86  cmp     r9d, esi
0x180026d89  jb      loc_180026CEB
0x180026d8f  mov     rcx, qword ptr [rsp+0B8h+var_60]
0x180026d94  test    rcx, rcx
0x180026d97  jz      short loc_180026DBC
0x180026d99  mov     rax, [rsp+0B8h+var_50]
0x180026d9e  sub     rax, rcx
0x180026da1  sar     rax, 3
0x180026da5  mov     rdx, 6DB6DB6DB6DB6DB7h
0x180026daf  imul    rax, rdx
0x180026db3  imul    rdx, rax, 38h ; '8'
0x180026db7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180026dbc  mov     [r12], esi
0x180026dc0  mov     eax, dword ptr [rsp+0B8h+var_64]
0x180026dc4  mov     [r12+4], eax
0x180026dc9  mov     rax, cs:WPP_GLOBAL_Control
0x180026dd0  lea     rcx, WPP_GLOBAL_Control
0x180026dd7  cmp     rax, rcx
0x180026dda  jz      short loc_180026DE7
0x180026ddc  test    [rax+1Ch], bl
0x180026ddf  jz      short loc_180026DE7
0x180026de1  cmp     byte ptr [rax+19h], 4
0x180026de5  jnb     short loc_180026DE9
0x180026de7  xor     bl, bl
0x180026de9  lea     rax, WPP_RECORDER_INITIALIZED
0x180026df0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180026df7  setnz   dil
0x180026dfb  test    bl, bl
0x180026dfd  jnz     short loc_180026E04
0x180026dff  test    dil, dil
0x180026e02  jz      short loc_180026E3A
0x180026e04  call    cs:__imp_GetCurrentThreadId
0x180026e0b  nop     dword ptr [rax+rax+00h]
0x180026e10  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x180026e14  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x180026e19  mov     word ptr [rsp+0B8h+var_88], 0Fh; __int16
0x180026e20  mov     rcx, cs:WPP_GLOBAL_Control
0x180026e27  mov     r9, [rcx+28h]; int
0x180026e2b  mov     r8b, dil; int
0x180026e2e  mov     dl, bl; int
0x180026e30  mov     rcx, [rcx+10h]; int
0x180026e34  call    WPP_RECORDER_AND_TRACE_SF_D
0x180026e39  nop
0x180026e3a  lea     rdx, [rsp+0B8h+ActivityId]; ActivityId
0x180026e3f  mov     ecx, 2; ControlCode
0x180026e44  call    cs:__imp_EventActivityIdControl
0x180026e4b  nop     dword ptr [rax+rax+00h]
0x180026e50  xor     eax, eax
0x180026e52  jmp     short loc_180026E58
0x180026e54  mov     eax, dword ptr [rsp+0B8h+var_64]
0x180026e58  mov     rcx, [rsp+0B8h+var_38]
0x180026e60  xor     rcx, rsp; StackCookie
0x180026e63  call    __security_check_cookie
0x180026e68  mov     rbx, [rsp+0B8h+arg_10]
0x180026e70  add     rsp, 90h
0x180026e77  pop     r15
0x180026e79  pop     r14
0x180026e7b  pop     r12
0x180026e7d  pop     rdi
0x180026e7e  pop     rsi
0x180026e7f  retn
0x180026e81  mov     rcx, [rsp+0B8h]; this
0x180026e89  lea     rdx, aFailedToParseE; "Failed to parse EDID"
0x180026e90  mov     qword ptr [rsp+0B8h+var_98], rdx; int
0x180026e95  mov     r9d, eax; char *
0x180026e98  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180026e9f  mov     edx, 793h; void *
0x180026ea4  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x180026eaa  mov     rcx, [rsp+0B8h]; this
0x180026eb2  lea     rax, aInvalidNumberO_1; "Invalid number of video modes returned "...
0x180026eb9  mov     qword ptr [rsp+0B8h+var_98], rax; int
0x180026ebe  mov     r9d, 80000005h; char *
0x180026ec4  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180026ecb  mov     edx, 7B1h; void *
0x180026ed0  call    ?Throw_NtStatusMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_NtStatusMsg(void *,uint,char const *,long,char const *,...)
```
