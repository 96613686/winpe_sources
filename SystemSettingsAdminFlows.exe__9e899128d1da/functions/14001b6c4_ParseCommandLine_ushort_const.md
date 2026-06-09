# ParseCommandLine(ushort const *)

- ea: `0x14001b6c4`
- end: `0x14001bbe0`
- name: `?ParseCommandLine@@YAJPEBG@Z`
- size: `1308`
- prototype: `__int64 __fastcall(LPCWSTR lpCmdLine)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14002e0c0`

## callees

- `0x140005f30`
- `0x140005f84`
- `0x14000d5b8`
- `0x14000e624`
- `0x14000eb50`
- `0x14000ebf8`
- `0x14000ec54`
- `0x14000f110`
- `0x14000f544`
- `0x1400197a0`
- `0x14001b6c4`
- `0x14001fc88`
- `0x140025b30`
- `0x140025ce0`
- `0x140026058`
- `0x14002996c`
- `0x14002b464`
- `0x14002bc58`
- `0x14002c200`
- `0x14002ce90`
- `0x14002ddcc`
- `0x14002de74`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x14001b829`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x14001b829`
- `KERNEL32!LocalFree` at `0x14001bba4`
- `KERNEL32!LocalFree` at `0x14001bba4`
- `KERNEL32!TlsGetValue` at `0x14001b6fa`
- `KERNEL32!TlsGetValue` at `0x14001b6fa`
- `KERNEL32!TlsSetValue` at `0x14001b72c`
- `KERNEL32!TlsSetValue` at `0x14001b72c`
- `SHELL32!CommandLineToArgvW` at `0x14001b7a3`
- `SHELL32!CommandLineToArgvW` at `0x14001b7a3`

## string_xrefs

- `0x14001bb13`: `pcshell\shell\systemsettings\adminflows\common\main.cpp`

## pseudocode

```c
__int64 __fastcall ParseCommandLine(LPCWSTR lpCmdLine)
{
  __int64 *Value; // rsi
  unsigned int v3; // ecx
  __int64 v4; // rcx
  int FlowInfo; // edi
  unsigned __int16 **v6; // rax
  unsigned __int16 **v7; // r13
  struct FLOWINFO *v8; // r12
  int v9; // r14d
  int v10; // ebx
  __int64 v11; // rcx
  int v12; // eax
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rbx
  int v15; // r15d
  const unsigned __int16 *v16; // r14
  __int64 v17; // rax
  bool v18; // zf
  char v19; // al
  const unsigned __int16 *v20; // r8
  bool v21; // sf
  unsigned int v22; // ebx
  int v23; // ebx
  int v24; // ebx
  _QWORD *v25; // rax
  int v26; // eax
  void (__stdcall *v27)(PTP_CALLBACK_INSTANCE, PVOID, PTP_WORK); // rcx
  unsigned int v28; // edx
  __int64 v29; // r14
  int v31; // [rsp+20h] [rbp-E0h]
  int pNumArgs; // [rsp+30h] [rbp-D0h] BYREF
  struct FLOWINFO *v33; // [rsp+38h] [rbp-C8h] BYREF
  DWORD v34; // [rsp+40h] [rbp-C0h] BYREF
  __int64 TlsValue; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v36[16]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v37; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD pv[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v39; // [rsp+70h] [rbp-90h]
  __int128 v40; // [rsp+80h] [rbp-80h]
  _QWORD v41[42]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  Value = (__int64 *)TlsGetValue(__g_tracingTlsSlot);
  v34 = -1;
  TlsValue = 0;
  if ( !Value )
  {
    Value = &TlsValue;
    v34 = __g_tracingTlsSlot;
    TlsSetValue(__g_tracingTlsSlot, &TlsValue);
  }
  ++*(_DWORD *)Value;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v3 = 5 * *(_DWORD *)Value;
    if ( v3 > 0x1E1 )
      v4 = 0;
    else
      v4 = 479LL - v3;
    WPP_SF_sS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      106,
      (unsigned int)&WPP_efafaf3e289e3856a10987a4bac777a3_Traceguids,
      (unsigned int)&asc_1400849C0[v4],
      (__int64)lpCmdLine);
  }
  FlowInfo = 0;
  pNumArgs = 0;
  v6 = CommandLineToArgvW(lpCmdLine, &pNumArgs);
  v7 = v6;
  if ( v6 )
  {
    if ( pNumArgs >= 1 )
    {
      v33 = 0;
      FlowInfo = GetFlowInfo(*v6, &v33);
      if ( FlowInfo >= 0 )
      {
        v8 = v33;
        pv[0] = *((_DWORD *)v33 + 2);
        pv[1] = 0;
        v39 = 0;
        v40 = 0;
        v9 = 1;
        if ( *((_BYTE *)v33 + 12) )
        {
          v10 = 0;
LABEL_14:
          if ( FlowInfo < 0 )
            goto LABEL_25;
          while ( 1 )
          {
            if ( v9 >= pNumArgs )
            {
              FlowInfo = -2147467259;
              goto LABEL_28;
            }
            FlowInfo = 0;
            v11 = v9++;
            v12 = _o__wtoi(v7[v11]);
            if ( v10 )
            {
              switch ( v10 )
              {
                case 1:
                  *((float *)&v39 + 3) = (float)v12;
                  break;
                case 2:
                  *(float *)&v40 = (float)v12;
                  break;
                case 3:
                  *((float *)&v40 + 1) = (float)v12;
                  goto LABEL_25;
                default:
LABEL_28:
                  if ( ++v10 >= 4 )
                    goto LABEL_25;
                  goto LABEL_14;
              }
            }
            else
            {
              *((float *)&v39 + 2) = (float)v12;
            }
            ++v10;
          }
        }
LABEL_25:
        v13 = (unsigned __int16 *)operator new[](0x10002u, (const struct std::nothrow_t *)std::nothrow);
        v14 = v13;
        v37 = v13;
        if ( !v13 )
        {
          FlowInfo = -2147024882;
          goto LABEL_59;
        }
        if ( FlowInfo >= 0 && *((_BYTE *)v8 + 13) )
        {
          *v13 = 0;
          while ( 1 )
          {
            if ( v9 >= pNumArgs )
            {
              *(_QWORD *)&v39 = v14;
              goto LABEL_59;
            }
            v15 = v9 + 1;
            if ( (*((_BYTE *)v8 + 20) & 1) == 0 || v15 != pNumArgs )
              break;
            v16 = v7[v9];
            FlowInfo = StringCchCatW(v14, 0x8001u, L"\"");
            if ( FlowInfo >= 0 )
              FlowInfo = StringCchCatW(v14, 0x8001u, v16);
            if ( (*((_BYTE *)v8 + 20) & 2) != 0 )
            {
              v17 = -1;
              do
                ++v17;
              while ( v16[v17] );
              if ( !v17 || (v18 = v16[v17 - 1] == 92, v19 = 1, !v18) )
                v19 = 0;
              if ( FlowInfo < 0 )
                goto LABEL_52;
              v20 = L"\\\"";
              if ( !v19 )
                v20 = L"\"";
              goto LABEL_51;
            }
            if ( FlowInfo >= 0 )
            {
              v20 = L"\"";
LABEL_51:
              FlowInfo = StringCchCatW(v14, 0x8001u, v20);
            }
LABEL_52:
            v9 = v15;
            v21 = FlowInfo < 0;
            if ( FlowInfo >= 0 )
            {
              if ( v15 < pNumArgs )
                FlowInfo = StringCchCatW(v14, 0x8001u, L" ");
              v21 = FlowInfo < 0;
            }
            if ( v21 )
              goto LABEL_59;
          }
          v20 = v7[v9];
          goto LABEL_51;
        }
LABEL_59:
        DWORD2(v40) = 0;
        if ( FlowInfo < 0 )
          goto LABEL_77;
        v22 = *((_DWORD *)v8 + 2);
        wil::ActivityBase<SettingsAdminFlowLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SettingsAdminFlowLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v41);
        v41[0] = &SettingsAdminFlowLogging::RunTaskFlow::`vftable';
        SettingsAdminFlowLogging::RunTaskFlow::StartActivity(
          (SettingsAdminFlowLogging::RunTaskFlow *)v41,
          v22,
          *(const unsigned __int16 **)v8);
        v33 = 0;
        v23 = *((_DWORD *)v8 + 2);
        *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_AdminFlowsAllowedFlowTypeTest,_tip_AdminFlowsAllowedFlowTypeTest>>::operator->(
                                 &v33,
                                 v36)
                  + 272LL) = v23;
        tip2::test_data_control<tip2::details::merged_data<_tip_AdminFlowsAllowedFlowTypeTest,_tip_AdminFlowsAllowedFlowTypeTest>>::~test_data_control<tip2::details::merged_data<_tip_AdminFlowsAllowedFlowTypeTest,_tip_AdminFlowsAllowedFlowTypeTest>>(v36);
        v24 = *((_DWORD *)v8 + 4);
        *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_AdminFlowsAllowedFlowTypeTest,_tip_AdminFlowsAllowedFlowTypeTest>>::operator->(
                                 &v33,
                                 v36)
                  + 276LL) = v24;
        tip2::test_data_control<tip2::details::merged_data<_tip_AdminFlowsAllowedFlowTypeTest,_tip_AdminFlowsAllowedFlowTypeTest>>::~test_data_control<tip2::details::merged_data<_tip_AdminFlowsAllowedFlowTypeTest,_tip_AdminFlowsAllowedFlowTypeTest>>(v36);
        if ( v33 && (unsigned __int8)tip2::details::shared_data<0,0,0>::has_ever_started((char *)v33 + 8) )
          wil::com_ptr_t<tip2::details::merged_data<_tip_AdminFlowsAllowedFlowTypeTest,_tip_AdminFlowsAllowedFlowTypeTest>,wil::err_returncode_policy>::reset(&v33);
        v25 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_AdminFlowsAllowedFlowTypeTest,_tip_AdminFlowsAllowedFlowTypeTest>>::ensure_data(&v33);
        tip2::details::shared_data<0,0,0>::start(*v25 + 8LL, v36);
        wil::com_ptr_t<tip2::details::merged_data<_tip_AdminFlowsAllowedFlowTypeTest,_tip_AdminFlowsAllowedFlowTypeTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_AdminFlowsAllowedFlowTypeTest,_tip_AdminFlowsAllowedFlowTypeTest>,wil::err_returncode_policy>(&v33);
        v26 = *((_DWORD *)v8 + 4);
        if ( v26 )
        {
          switch ( v26 )
          {
            case 1:
              v27 = (void (__stdcall *)(PTP_CALLBACK_INSTANCE, PVOID, PTP_WORK))RunXAMLFlowWork;
              break;
            case 2:
              v27 = (void (__stdcall *)(PTP_CALLBACK_INSTANCE, PVOID, PTP_WORK))RunSilentFlowWork;
              break;
            case 3:
              if ( *((_DWORD *)v8 + 2) != 117 && *((_DWORD *)v8 + 2) != 102 )
              {
                FlowInfo = -2147024809;
LABEL_75:
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x1202,
                  (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\common\\main.cpp",
                  (const char *)(unsigned int)FlowInfo,
                  v31);
                goto LABEL_76;
              }
              v27 = (void (__stdcall *)(PTP_CALLBACK_INSTANCE, PVOID, PTP_WORK))RunComServerFlowWork;
              break;
            default:
              goto LABEL_76;
          }
        }
        else
        {
          v27 = (void (__stdcall *)(PTP_CALLBACK_INSTANCE, PVOID, PTP_WORK))RunDUIFlowWork;
        }
        FlowInfo = RunFlowThread(v27, pv);
        if ( FlowInfo < 0 )
          goto LABEL_75;
LABEL_76:
        wil::ActivityBase<SettingsAdminFlowLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
          v41,
          (unsigned int)FlowInfo);
        SettingsAdminFlowLogging::RunTaskFlow::~RunTaskFlow((SettingsAdminFlowLogging::RunTaskFlow *)v41);
LABEL_77:
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v37);
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v28 = 5 * *(_DWORD *)Value;
    if ( v28 > 0x1E1 )
      v29 = 0;
    else
      v29 = 479LL - v28;
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      107,
      (unsigned int)&WPP_efafaf3e289e3856a10987a4bac777a3_Traceguids,
      (unsigned int)&asc_1400849C0[v29],
      FlowInfo);
  }
  if ( v7 )
    LocalFree(v7);
  if ( Value )
    --*(_DWORD *)Value;
  TracingInternal::AutoTlsPtr<TracingInternal::TracingContext>::~AutoTlsPtr<TracingInternal::TracingContext>(&v34);
  return (unsigned int)FlowInfo;
}

```

## disassembly

```asm
0x14001b6c4  push    rbp
0x14001b6c6  push    rbx
0x14001b6c7  push    rsi
0x14001b6c8  push    rdi
0x14001b6c9  push    r12
0x14001b6cb  push    r13
0x14001b6cd  push    r14
0x14001b6cf  push    r15
0x14001b6d1  lea     rbp, [rsp-0F8h]
0x14001b6d9  sub     rsp, 1F8h
0x14001b6e0  mov     rax, cs:__security_cookie
0x14001b6e7  xor     rax, rsp
0x14001b6ea  mov     [rbp+130h+var_50], rax
0x14001b6f1  mov     rbx, rcx
0x14001b6f4  mov     ecx, cs:?__g_tracingTlsSlot@@3KA; dwTlsIndex
0x14001b6fa  call    cs:__imp_TlsGetValue
0x14001b700  mov     rsi, rax
0x14001b703  mov     [rsp+230h+var_1F0], 0FFFFFFFFh
0x14001b70b  xor     r15d, r15d
0x14001b70e  mov     [rsp+230h+TlsValue], r15
0x14001b713  test    rax, rax
0x14001b716  jnz     short loc_14001B732
0x14001b718  lea     rsi, [rsp+230h+TlsValue]
0x14001b71d  mov     ecx, cs:?__g_tracingTlsSlot@@3KA; dwTlsIndex
0x14001b723  mov     [rsp+230h+var_1F0], ecx
0x14001b727  lea     rdx, [rsp+230h+TlsValue]; lpTlsValue
0x14001b72c  call    cs:__imp_TlsSetValue
0x14001b732  inc     dword ptr [rsi]
0x14001b734  lea     rax, WPP_GLOBAL_Control
0x14001b73b  mov     r14d, 1DFh
0x14001b741  lea     r12, asc_1400849C0; "                                       "...
0x14001b748  mov     r10, cs:WPP_GLOBAL_Control
0x14001b74f  cmp     r10, rax
0x14001b752  jz      short loc_14001B793
0x14001b754  test    byte ptr [r10+1Ch], 80h
0x14001b759  jz      short loc_14001B793
0x14001b75b  mov     eax, [rsi]
0x14001b75d  lea     ecx, [rax+rax*4]
0x14001b760  cmp     ecx, 1E1h
0x14001b766  ja      short loc_14001B772
0x14001b768  mov     eax, ecx
0x14001b76a  mov     ecx, r14d
0x14001b76d  sub     rcx, rax
0x14001b770  jmp     short loc_14001B775
0x14001b772  mov     rcx, r15
0x14001b775  lea     r9, [rcx+r12]
0x14001b779  mov     edx, 6Ah ; 'j'
0x14001b77e  mov     qword ptr [rsp+230h+var_210], rbx; int
0x14001b783  lea     r8, WPP_efafaf3e289e3856a10987a4bac777a3_Traceguids
0x14001b78a  mov     rcx, [r10+10h]
0x14001b78e  call    WPP_SF_sS
0x14001b793  mov     edi, r15d
0x14001b796  mov     [rsp+230h+pNumArgs], r15d
0x14001b79b  lea     rdx, [rsp+230h+pNumArgs]; pNumArgs
0x14001b7a0  mov     rcx, rbx; lpCmdLine
0x14001b7a3  call    cs:__imp_CommandLineToArgvW
0x14001b7a9  mov     r13, rax
0x14001b7ac  test    rax, rax
0x14001b7af  jz      loc_14001BB4F
0x14001b7b5  cmp     [rsp+230h+pNumArgs], 1
0x14001b7ba  jl      loc_14001BB4F
0x14001b7c0  mov     [rsp+230h+var_1F8], r15
0x14001b7c5  lea     rdx, [rsp+230h+var_1F8]; struct FLOWINFO **
0x14001b7ca  mov     rcx, [rax]; unsigned __int16 *
0x14001b7cd  call    ?GetFlowInfo@@YAJPEAGPEAPEBUFLOWINFO@@@Z; GetFlowInfo(ushort *,FLOWINFO const * *)
0x14001b7d2  mov     edi, eax
0x14001b7d4  test    eax, eax
0x14001b7d6  js      loc_14001BB4F
0x14001b7dc  mov     r12, [rsp+230h+var_1F8]
0x14001b7e1  mov     ecx, [r12+8]
0x14001b7e6  mov     [rsp+230h+pv], ecx
0x14001b7ea  xor     eax, eax
0x14001b7ec  mov     [rsp+230h+var_1C4], eax
0x14001b7f0  xorps   xmm0, xmm0
0x14001b7f3  movups  [rsp+230h+var_1C0], xmm0
0x14001b7f8  movups  [rbp+130h+var_1B0], xmm0
0x14001b7fc  lea     r14d, [rax+1]
0x14001b800  cmp     [r12+0Ch], r15b
0x14001b805  jz      short loc_14001B883
0x14001b807  mov     ebx, r15d
0x14001b80a  test    edi, edi
0x14001b80c  js      short loc_14001B883
0x14001b80e  mov     r15d, ebx
0x14001b811  cmp     r14d, [rsp+230h+pNumArgs]
0x14001b816  jge     loc_14001B8AB
0x14001b81c  xor     edi, edi
0x14001b81e  movsxd  rcx, r14d
0x14001b821  inc     r14d
0x14001b824  mov     rcx, [r13+rcx*8+0]
0x14001b829  call    cs:__imp__o__wtoi
0x14001b82f  mov     edx, ebx
0x14001b831  test    ebx, ebx
0x14001b833  jz      short loc_14001B85C
0x14001b835  sub     edx, 1
0x14001b838  jz      short loc_14001B84D
0x14001b83a  sub     edx, 1
0x14001b83d  jnz     short loc_14001B86F
0x14001b83f  movd    xmm0, eax
0x14001b843  cvtdq2ps xmm0, xmm0
0x14001b846  movss   dword ptr [rbp+130h+var_1B0], xmm0
0x14001b84b  jmp     short loc_14001B869
0x14001b84d  movd    xmm0, eax
0x14001b851  cvtdq2ps xmm0, xmm0
0x14001b854  movss   dword ptr [rsp+230h+var_1C0+0Ch], xmm0
0x14001b85a  jmp     short loc_14001B869
0x14001b85c  movd    xmm0, eax
0x14001b860  cvtdq2ps xmm0, xmm0
0x14001b863  movss   dword ptr [rsp+230h+var_1C0+8], xmm0
0x14001b869  lea     ebx, [r15+1]
0x14001b86d  jmp     short loc_14001B80E
0x14001b86f  cmp     edx, 1
0x14001b872  jnz     short loc_14001B8B0
0x14001b874  movd    xmm0, eax
0x14001b878  cvtdq2ps xmm0, xmm0
0x14001b87b  movss   dword ptr [rbp+130h+var_1B0+4], xmm0
0x14001b880  xor     r15d, r15d
0x14001b883  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001b88a  mov     ecx, 10002h; unsigned __int64
0x14001b88f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14001b894  mov     rbx, rax
0x14001b897  mov     [rsp+230h+var_1D0], rax
0x14001b89c  test    rax, rax
0x14001b89f  jnz     short loc_14001B8BF
0x14001b8a1  mov     edi, 8007000Eh
0x14001b8a6  jmp     loc_14001B9DA
0x14001b8ab  mov     edi, 80004005h
0x14001b8b0  inc     ebx
0x14001b8b2  xor     r15d, r15d
0x14001b8b5  cmp     ebx, 4
0x14001b8b8  jge     short loc_14001B883
0x14001b8ba  jmp     loc_14001B80A
0x14001b8bf  test    edi, edi
0x14001b8c1  js      loc_14001B9DA
0x14001b8c7  cmp     [r12+0Dh], r15b
0x14001b8cc  jz      loc_14001B9DA
0x14001b8d2  mov     [rax], r15w
0x14001b8d6  lea     rcx, asc_14008859C; "\""
0x14001b8dd  cmp     r14d, [rsp+230h+pNumArgs]
0x14001b8e2  jge     loc_14001B9D5
0x14001b8e8  lea     r15d, [r14+1]
0x14001b8ec  test    byte ptr [r12+14h], 1
0x14001b8f2  jz      loc_14001B986
0x14001b8f8  cmp     r15d, [rsp+230h+pNumArgs]
0x14001b8fd  jnz     loc_14001B986
0x14001b903  movsxd  rax, r14d
0x14001b906  mov     r14, [r13+rax*8+0]
0x14001b90b  mov     r8, rcx; unsigned __int16 *
0x14001b90e  mov     edx, 8001h; unsigned __int64
0x14001b913  mov     rcx, rbx; unsigned __int16 *
0x14001b916  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14001b91b  mov     edi, eax
0x14001b91d  xor     ecx, ecx
0x14001b91f  test    eax, eax
0x14001b921  js      short loc_14001B937
0x14001b923  mov     r8, r14; unsigned __int16 *
0x14001b926  mov     edx, 8001h; unsigned __int64
0x14001b92b  mov     rcx, rbx; unsigned __int16 *
0x14001b92e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14001b933  mov     edi, eax
0x14001b935  xor     ecx, ecx
0x14001b937  test    byte ptr [r12+14h], 2
0x14001b93d  jz      short loc_14001B979
0x14001b93f  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001b943  inc     rax
0x14001b946  cmp     [r14+rax*2], cx
0x14001b94b  jnz     short loc_14001B943
0x14001b94d  test    rax, rax
0x14001b950  jz      short loc_14001B95D
0x14001b952  cmp     word ptr [r14+rax*2-2], 5Ch ; '\'
0x14001b959  mov     al, 1
0x14001b95b  jz      short loc_14001B95F
0x14001b95d  mov     al, cl
0x14001b95f  test    edi, edi
0x14001b961  js      short loc_14001B99D
0x14001b963  lea     r8, asc_1400885A0; "\\\""
0x14001b96a  test    al, al
0x14001b96c  lea     rax, asc_14008859C; "\""
0x14001b973  cmovz   r8, rax
0x14001b977  jmp     short loc_14001B98E
0x14001b979  test    edi, edi
0x14001b97b  js      short loc_14001B99D
0x14001b97d  lea     r8, asc_14008859C; "\""
0x14001b984  jmp     short loc_14001B98E
0x14001b986  movsxd  r8, r14d
0x14001b989  mov     r8, [r13+r8*8+0]; unsigned __int16 *
0x14001b98e  mov     edx, 8001h; unsigned __int64
0x14001b993  mov     rcx, rbx; unsigned __int16 *
0x14001b996  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14001b99b  mov     edi, eax
0x14001b99d  mov     r14d, r15d
0x14001b9a0  xor     r15d, r15d
0x14001b9a3  test    edi, edi
0x14001b9a5  js      short loc_14001B9C6
0x14001b9a7  cmp     r14d, [rsp+230h+pNumArgs]
0x14001b9ac  jge     short loc_14001B9C4
0x14001b9ae  lea     r8, Delimiter; " "
0x14001b9b5  mov     edx, 8001h; unsigned __int64
0x14001b9ba  mov     rcx, rbx; unsigned __int16 *
0x14001b9bd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14001b9c2  mov     edi, eax
0x14001b9c4  test    edi, edi
0x14001b9c6  lea     rcx, asc_14008859C; "\""
0x14001b9cd  jns     loc_14001B8DD
0x14001b9d3  jmp     short loc_14001B9DA
0x14001b9d5  mov     qword ptr [rsp+230h+var_1C0], rbx
0x14001b9da  mov     dword ptr [rbp+130h+var_1B0+8], r15d
0x14001b9de  test    edi, edi
0x14001b9e0  js      loc_14001BB38
0x14001b9e6  mov     ebx, [r12+8]
0x14001b9eb  lea     rcx, [rbp+130h+var_1A0]; struct wil::details::IFailureCallback *
0x14001b9ef  call    ??0?$ActivityBase@VSettingsAdminFlowLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SettingsAdminFlowLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SettingsAdminFlowLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14001b9f4  lea     rax, ??_7RunTaskFlow@SettingsAdminFlowLogging@@6B@; const SettingsAdminFlowLogging::RunTaskFlow::`vftable'
0x14001b9fb  mov     [rbp+130h+var_1A0], rax
0x14001b9ff  mov     r8, [r12]; unsigned __int16 *
0x14001ba03  mov     edx, ebx; unsigned int
0x14001ba05  lea     rcx, [rbp+130h+var_1A0]; this
0x14001ba09  call    ?StartActivity@RunTaskFlow@SettingsAdminFlowLogging@@QEAAXIPEBG@Z; SettingsAdminFlowLogging::RunTaskFlow::StartActivity(uint,ushort const *)
0x14001ba0e  nop
0x14001ba0f  mov     [rsp+230h+var_1F8], r15
0x14001ba14  mov     ebx, [r12+8]
0x14001ba19  lea     rdx, [rsp+230h+var_1E0]
0x14001ba1e  lea     rcx, [rsp+230h+var_1F8]
0x14001ba23  call    ??C?$tip_test@V?$merged_data@U_tip_AdminFlowsAllowedFlowTypeTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_AdminFlowsAllowedFlowTypeTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AdminFlowsAllowedFlowTypeTest,_tip_AdminFlowsAllowedFlowTypeTest>>::operator->(void)
0x14001ba28  mov     rcx, [rax]
0x14001ba2b  mov     [rcx+110h], ebx
0x14001ba31  lea     rcx, [rsp+230h+var_1E0]
0x14001ba36  call    ??1?$test_data_control@V?$merged_data@U_tip_AdminFlowsAllowedFlowTypeTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AdminFlowsAllowedFlowTypeTest,_tip_AdminFlowsAllowedFlowTypeTest>>::~test_data_control<tip2::details::merged_data<_tip_AdminFlowsAllowedFlowTypeTest,_tip_AdminFlowsAllowedFlowTypeTest>>(void)
0x14001ba3b  mov     ebx, [r12+10h]
0x14001ba40  lea     rdx, [rsp+230h+var_1E0]
0x14001ba45  lea     rcx, [rsp+230h+var_1F8]
0x14001ba4a  call    ??C?$tip_test@V?$merged_data@U_tip_AdminFlowsAllowedFlowTypeTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_AdminFlowsAllowedFlowTypeTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AdminFlowsAllowedFlowTypeTest,_tip_AdminFlowsAllowedFlowTypeTest>>::operator->(void)
0x14001ba4f  mov     rcx, [rax]
0x14001ba52  mov     [rcx+114h], ebx
0x14001ba58  lea     rcx, [rsp+230h+var_1E0]
0x14001ba5d  call    ??1?$test_data_control@V?$merged_data@U_tip_AdminFlowsAllowedFlowTypeTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AdminFlowsAllowedFlowTypeTest,_tip_AdminFlowsAllowedFlowTypeTest>>::~test_data_control<tip2::details::merged_data<_tip_AdminFlowsAllowedFlowTypeTest,_tip_AdminFlowsAllowedFlowTypeTest>>(void)
0x14001ba62  mov     rcx, [rsp+230h+var_1F8]
0x14001ba67  test    rcx, rcx
0x14001ba6a  jz      short loc_14001BA83
0x14001ba6c  add     rcx, 8
0x14001ba70  call    ?has_ever_started@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::has_ever_started(void)
0x14001ba75  test    al, al
0x14001ba77  jz      short loc_14001BA83
0x14001ba79  lea     rcx, [rsp+230h+var_1F8]
0x14001ba7e  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_AdminFlowsAllowedFlowTypeTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_AdminFlowsAllowedFlowTypeTest,_tip_AdminFlowsAllowedFlowTypeTest>,wil::err_returncode_policy>::reset(void)
0x14001ba83  lea     rcx, [rsp+230h+var_1F8]
0x14001ba88  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_AdminFlowsAllowedFlowTypeTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_AdminFlowsAllowedFlowTypeTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AdminFlowsAllowedFlowTypeTest,_tip_AdminFlowsAllowedFlowTypeTest>>::ensure_data(void)
0x14001ba8d  mov     rcx, [rax]
0x14001ba90  add     rcx, 8
0x14001ba94  lea     rdx, [rsp+230h+var_1E0]
0x14001ba99  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x14001ba9e  lea     rcx, [rsp+230h+var_1F8]
0x14001baa3  call    ??1?$com_ptr_t@V?$merged_data@U_tip_AdminFlowsAllowedFlowTypeTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_AdminFlowsAllowedFlowTypeTest,_tip_AdminFlowsAllowedFlowTypeTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_AdminFlowsAllowedFlowTypeTest,_tip_AdminFlowsAllowedFlowTypeTest>,wil::err_returncode_policy>(void)
0x14001baa8  mov     eax, [r12+10h]
0x14001baad  test    eax, eax
0x14001baaf  jnz     short loc_14001BABA
0x14001bab1  lea     rcx, ?RunDUIFlowWork@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; RunDUIFlowWork(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)
0x14001bab8  jmp     short loc_14001BAF9
0x14001baba  cmp     eax, 1
0x14001babd  jnz     short loc_14001BAC8
0x14001babf  lea     rcx, ?RunXAMLFlowWork@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; RunXAMLFlowWork(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)
0x14001bac6  jmp     short loc_14001BAF9
0x14001bac8  cmp     eax, 2
0x14001bacb  jnz     short loc_14001BAD6
0x14001bacd  lea     rcx, ?RunSilentFlowWork@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; RunSilentFlowWork(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)
0x14001bad4  jmp     short loc_14001BAF9
0x14001bad6  cmp     eax, 3
0x14001bad9  jnz     short loc_14001BB24
0x14001badb  cmp     dword ptr [r12+8], 75h ; 'u'
0x14001bae1  jz      short loc_14001BAF2
0x14001bae3  cmp     dword ptr [r12+8], 66h ; 'f'
0x14001bae9  jz      short loc_14001BAF2
0x14001baeb  mov     edi, 80070057h
0x14001baf0  jmp     short loc_14001BB09
0x14001baf2  lea     rcx, ?RunComServerFlowWork@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x14001baf9  lea     rdx, [rsp+230h+pv]; pv
0x14001bafe  call    ?RunFlowThread@@YAJP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@ZPEAUTHREAD_CONTEXT@@@Z; RunFlowThread(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),THREAD_CONTEXT *)
0x14001bb03  mov     edi, eax
0x14001bb05  test    eax, eax
0x14001bb07  jns     short loc_14001BB24
0x14001bb09  mov     rcx, [rbp+138h]; this
0x14001bb10  mov     r9d, edi; char *
0x14001bb13  lea     r8, aPcshellShellSy_29; "pcshell\\shell\\systemsettings\\adminfl"...
0x14001bb1a  mov     edx, 1202h; void *
0x14001bb1f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14001bb24  mov     edx, edi
0x14001bb26  lea     rcx, [rbp+130h+var_1A0]
0x14001bb2a  call    ?Stop@?$ActivityBase@VSettingsAdminFlowLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SettingsAdminFlowLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14001bb2f  lea     rcx, [rbp+130h+var_1A0]; this
0x14001bb33  call    ??1RunTaskFlow@SettingsAdminFlowLogging@@QEAA@XZ; SettingsAdminFlowLogging::RunTaskFlow::~RunTaskFlow(void)
0x14001bb38  lea     rcx, [rsp+230h+var_1D0]
0x14001bb3d  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x14001bb42  mov     r14d, 1DFh
0x14001bb48  lea     r12, asc_1400849C0; "                                       "...
0x14001bb4f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bb56  lea     rax, WPP_GLOBAL_Control
0x14001bb5d  cmp     rcx, rax
0x14001bb60  jz      short loc_14001BB9C
0x14001bb62  test    byte ptr [rcx+1Ch], 80h
0x14001bb66  jz      short loc_14001BB9C
0x14001bb68  mov     eax, [rsi]
  ... truncated ...
```
