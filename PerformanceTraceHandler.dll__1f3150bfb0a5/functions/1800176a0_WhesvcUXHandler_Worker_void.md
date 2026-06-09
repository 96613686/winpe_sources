# WhesvcUXHandler::Worker(void)

- ea: `0x1800176a0`
- end: `0x18001782e`
- name: `?Worker@WhesvcUXHandler@@EEAAJXZ`
- size: `398`
- prototype: `__int64 __fastcall(WhesvcUXHandler *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callees

- `0x180007f3c`
- `0x180013da8`
- `0x18001642c`
- `0x1800166a0`
- `0x180016868`
- `0x1800176a0`
- `0x180017ca8`
- `0x18001857c`

## string_xrefs

- `0x1800177bf`: `pcshell\shell\performancetracehandler\dll\whesvcuxhandler.cpp`

## pseudocode

```c
__int64 __fastcall WhesvcUXHandler::Worker(WhesvcUXHandler *this)
{
  char IsEnabled; // al
  WhesvcUXHandler *v2; // rcx
  unsigned int v3; // ebx
  const char *v4; // rax
  WhesvcUXHandler *v6; // rcx
  __int64 v7; // rdx
  int v8; // [rsp+20h] [rbp-20h]
  unsigned __int64 *v9; // [rsp+28h] [rbp-18h]
  struct wil::WNF_CHANGE_STAMP_STRUCT *v10; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int64 v11; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  _WNF_STATE_NAME v13; // [rsp+58h] [rbp+18h] BYREF
  int v14; // [rsp+60h] [rbp+20h] BYREF
  __int64 v15; // [rsp+68h] [rbp+28h] BYREF

  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes3D>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixes3D>::GetImpl'::`2'::impl);
  LOBYTE(v13.Data[0]) = 0;
  if ( IsEnabled )
  {
    LODWORD(v15) = 0;
    v11 = 0;
    v14 = wil::wnf_query_nothrow(
            (wil *)&WNF_WHE_TASK_TOAST,
            &v13,
            (bool *)&v15,
            (void *)4,
            (unsigned __int64)&v11,
            v9,
            (struct wil::WNF_CHANGE_STAMP_STRUCT *)"None");
    v3 = v14;
    if ( v14 >= 0 )
    {
      if ( LOBYTE(v13.Data[0]) )
      {
        if ( v11 == 4 )
        {
          switch ( (_DWORD)v15 )
          {
            case 1:
              WhesvcUXHandler::HotkeyTraceStartedState(v2);
              goto LABEL_17;
            case 2:
              WhesvcUXHandler::HotkeyTraceEndedState(v2);
              goto LABEL_17;
            case 3:
              WhesvcUXHandler::HotkeyTraceErrorState(v2);
              goto LABEL_17;
          }
          v3 = -2147023728;
          v4 = "UnknownState";
        }
        else
        {
          v3 = -2147418113;
          v4 = "WnfPayloadSize";
        }
      }
      else
      {
        v3 = -2147418113;
        v4 = "WnfNotPublished";
      }
      v14 = v3;
    }
    else
    {
      v4 = "WnfQuery";
    }
    v10 = (struct wil::WNF_CHANGE_STAMP_STRUCT *)v4;
LABEL_17:
    WhesvcTelemetryProvider::HotkeyUXHandlerActivated<unsigned long &,long &,char const * &>(&v15, &v14, &v10);
    return v3;
  }
  v14 = 0;
  v15 = 0;
  v3 = wil::wnf_query_nothrow(
         (wil *)&WNF_WHE_TASK_TOAST,
         &v13,
         (bool *)&v14,
         (void *)4,
         (unsigned __int64)&v15,
         v9,
         v10);
  if ( (v3 & 0x80000000) != 0 )
  {
    v7 = 131;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\whesvcuxhandler.cpp",
      (const char *)v3,
      v8);
    return v3;
  }
  if ( !LOBYTE(v13.Data[0]) )
    return 1;
  if ( v15 != 4 )
  {
    v3 = -2147418113;
    v7 = 142;
    goto LABEL_21;
  }
  switch ( v14 )
  {
    case 1:
      WhesvcUXHandler::HotkeyTraceStartedState(v6);
      break;
    case 2:
      WhesvcUXHandler::HotkeyTraceEndedState(v6);
      break;
    case 3:
      WhesvcUXHandler::HotkeyTraceErrorState(v6);
      break;
    default:
      v3 = -2147023728;
      v7 = 161;
      goto LABEL_21;
  }
  return 0;
}

```

## disassembly

```asm
0x1800176a0  mov     [rsp-8+arg_0], rbx
0x1800176a5  push    rbp
0x1800176a6  mov     rbp, rsp
0x1800176a9  sub     rsp, 40h
0x1800176ad  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFixes3D@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes3D@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes3D> `wil::Feature<__WilFeatureTraits_Feature_BugFixes3D>::GetImpl(void)'::`2'::impl
0x1800176b4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes3D@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes3D>::__private_IsEnabled(void)
0x1800176b9  mov     byte ptr [rbp+arg_8.Data], 0
0x1800176bd  mov     r9d, 4; void *
0x1800176c3  lea     rdx, [rbp+arg_8]; struct _WNF_STATE_NAME *
0x1800176c7  lea     rcx, WNF_WHE_TASK_TOAST; this
0x1800176ce  test    al, al
0x1800176d0  jz      loc_18001778F
0x1800176d6  lea     rax, aNone; "None"
0x1800176dd  mov     dword ptr [rbp+arg_18], 0
0x1800176e4  mov     [rbp+var_10], rax
0x1800176e8  lea     r8, [rbp+arg_18]; bool *
0x1800176ec  lea     rax, [rbp+var_8]
0x1800176f0  mov     [rbp+var_8], 0
0x1800176f8  mov     [rsp+40h+var_20], rax; unsigned __int64
0x1800176fd  call    ?wnf_query_nothrow@wil@@YAJAEBU_WNF_STATE_NAME@@PEA_NPEAX_KPEA_KPEAUWNF_CHANGE_STAMP_STRUCT@1@@Z; wil::wnf_query_nothrow(_WNF_STATE_NAME const &,bool *,void *,unsigned __int64,unsigned __int64 *,wil::WNF_CHANGE_STAMP_STRUCT *)
0x180017702  mov     [rbp+arg_10], eax
0x180017705  mov     ebx, eax
0x180017707  test    eax, eax
0x180017709  jns     short loc_180017714
0x18001770b  lea     rax, aWnfquery; "WnfQuery"
0x180017712  jmp     short loc_18001775E
0x180017714  cmp     byte ptr [rbp+arg_8.Data], 0
0x180017718  jnz     short loc_180017728
0x18001771a  mov     ebx, 8000FFFFh
0x18001771f  lea     rax, aWnfnotpublishe; "WnfNotPublished"
0x180017726  jmp     short loc_18001775B
0x180017728  cmp     [rbp+var_8], 4
0x18001772d  jz      short loc_18001773D
0x18001772f  mov     ebx, 8000FFFFh
0x180017734  lea     rax, aWnfpayloadsize; "WnfPayloadSize"
0x18001773b  jmp     short loc_18001775B
0x18001773d  mov     eax, dword ptr [rbp+arg_18]
0x180017740  sub     eax, 1
0x180017743  jz      short loc_180017772
0x180017745  sub     eax, 1
0x180017748  jz      short loc_18001776B
0x18001774a  cmp     eax, 1
0x18001774d  jz      short loc_180017764
0x18001774f  mov     ebx, 80070490h
0x180017754  lea     rax, aUnknownstate; "UnknownState"
0x18001775b  mov     [rbp+arg_10], ebx
0x18001775e  mov     [rbp+var_10], rax
0x180017762  jmp     short loc_180017777
0x180017764  call    ?HotkeyTraceErrorState@WhesvcUXHandler@@AEAAJXZ; WhesvcUXHandler::HotkeyTraceErrorState(void)
0x180017769  jmp     short loc_180017777
0x18001776b  call    ?HotkeyTraceEndedState@WhesvcUXHandler@@AEAAJXZ; WhesvcUXHandler::HotkeyTraceEndedState(void)
0x180017770  jmp     short loc_180017777
0x180017772  call    ?HotkeyTraceStartedState@WhesvcUXHandler@@AEAAJXZ; WhesvcUXHandler::HotkeyTraceStartedState(void)
0x180017777  lea     r8, [rbp+var_10]
0x18001777b  lea     rdx, [rbp+arg_10]
0x18001777f  lea     rcx, [rbp+arg_18]
0x180017783  call    ??$HotkeyUXHandlerActivated@AEAKAEAJAEAPEBD@WhesvcTelemetryProvider@@SAXAEAKAEAJAEAPEBD@Z; WhesvcTelemetryProvider::HotkeyUXHandlerActivated<ulong &,long &,char const * &>(ulong &,long &,char const * &)
0x180017788  mov     eax, ebx
0x18001778a  jmp     loc_180017823
0x18001778f  lea     rax, [rbp+arg_18]
0x180017793  mov     [rbp+arg_10], 0
0x18001779a  lea     r8, [rbp+arg_10]; bool *
0x18001779e  mov     [rsp+40h+var_20], rax; int
0x1800177a3  mov     [rbp+arg_18], 0
0x1800177ab  call    ?wnf_query_nothrow@wil@@YAJAEBU_WNF_STATE_NAME@@PEA_NPEAX_KPEA_KPEAUWNF_CHANGE_STAMP_STRUCT@1@@Z; wil::wnf_query_nothrow(_WNF_STATE_NAME const &,bool *,void *,unsigned __int64,unsigned __int64 *,wil::WNF_CHANGE_STAMP_STRUCT *)
0x1800177b0  mov     ebx, eax
0x1800177b2  test    eax, eax
0x1800177b4  jns     short loc_1800177D0
0x1800177b6  mov     edx, 83h; void *
0x1800177bb  mov     rcx, [rbp+8]; this
0x1800177bf  lea     r8, aPcshellShellPe; "pcshell\\shell\\performancetracehandler"...
0x1800177c6  mov     r9d, ebx; char *
0x1800177c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800177ce  jmp     short loc_180017788
0x1800177d0  cmp     byte ptr [rbp+arg_8.Data], 0
0x1800177d4  jnz     short loc_1800177DD
0x1800177d6  mov     eax, 1
0x1800177db  jmp     short loc_180017823
0x1800177dd  cmp     [rbp+arg_18], 4
0x1800177e2  jz      short loc_1800177F0
0x1800177e4  mov     ebx, 8000FFFFh
0x1800177e9  mov     edx, 8Eh
0x1800177ee  jmp     short loc_1800177BB
0x1800177f0  mov     eax, [rbp+arg_10]
0x1800177f3  sub     eax, 1
0x1800177f6  jz      short loc_18001781C
0x1800177f8  sub     eax, 1
0x1800177fb  jz      short loc_180017815
0x1800177fd  cmp     eax, 1
0x180017800  jz      short loc_18001780E
0x180017802  mov     ebx, 80070490h
0x180017807  mov     edx, 0A1h
0x18001780c  jmp     short loc_1800177BB
0x18001780e  call    ?HotkeyTraceErrorState@WhesvcUXHandler@@AEAAJXZ; WhesvcUXHandler::HotkeyTraceErrorState(void)
0x180017813  jmp     short loc_180017821
0x180017815  call    ?HotkeyTraceEndedState@WhesvcUXHandler@@AEAAJXZ; WhesvcUXHandler::HotkeyTraceEndedState(void)
0x18001781a  jmp     short loc_180017821
0x18001781c  call    ?HotkeyTraceStartedState@WhesvcUXHandler@@AEAAJXZ; WhesvcUXHandler::HotkeyTraceStartedState(void)
0x180017821  xor     eax, eax
0x180017823  mov     rbx, [rsp+40h+arg_0]
0x180017828  add     rsp, 40h
0x18001782c  pop     rbp
0x18001782d  retn
```
