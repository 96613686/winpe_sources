# ComTraceMessageWorker

- ea: `0x14000eb14`
- end: `0x14000ef04`
- name: `ComTraceMessageWorker`
- size: `1008`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int, unsigned __int16 *, char *)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x14000d63c`

## callees

- `0x140008c80`
- `0x14000dc4c`
- `0x14000dc6c`
- `0x14000dd14`
- `0x14000df04`
- `0x14000df40`
- `0x14000e530`
- `0x14000e7cc`
- `0x14000e8e4`
- `0x14000e98c`
- `0x14000eb14`
- `0x14000ef0c`
- `0x14000efa4`
- `0x14000f05c`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000eb55`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000eb55`

## pseudocode

```c
void __fastcall ComTraceMessageWorker(
        int a1,
        __int64 a2,
        __int64 a3,
        int a4,
        unsigned int a5,
        unsigned __int16 *a6,
        char *a7)
{
  unsigned __int64 v11; // rsi
  void *v12; // rsp
  unsigned __int16 *v13; // rbx
  _DWORD *v14; // rax
  unsigned __int16 *v15; // r10
  unsigned __int64 v16; // rdx
  __int64 v17; // r8
  unsigned __int8 v18; // cl
  __int64 v19; // rcx
  ComTrace *v20; // rcx
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  ComTrace *v24; // rcx
  __int64 v25; // rcx
  ComTrace *v26; // rcx
  __int64 v27; // [rsp-20h] [rbp-860h] BYREF
  __int64 v28; // [rsp+20h] [rbp-820h]
  int v29; // [rsp+30h] [rbp-810h]
  _BYTE v30[1976]; // [rsp+38h] [rbp-808h] BYREF
  unsigned __int16 *v31; // [rsp+840h] [rbp+0h] BYREF
  DiagnosticsInfo v32; // [rsp+848h] [rbp+8h] BYREF
  __int64 v33; // [rsp+850h] [rbp+10h]
  __int64 v34; // [rsp+858h] [rbp+18h]
  __int16 v35; // [rsp+860h] [rbp+20h]
  unsigned __int64 v36; // [rsp+868h] [rbp+28h] BYREF

  if ( g_hrToDebug && a1 == g_hrToDebug && (IsDebuggerPresent() || MEMORY[0x7FFE02D4]) )
    BreakIntoDebugger();
  if ( gfEnableTracing || a5 <= 1 || a5 == 7 )
  {
    v11 = 1024;
    v36 = 1024;
    if ( (unsigned __int64)g_ulMaxStackAllocSize >= 0x800 && (unsigned __int64)(g_ulAdditionalProbeSize + 2056) >= 0x800 )
    {
      if ( (unsigned int)VerifyStackAvailable() )
      {
        v12 = alloca(2064);
        if ( &v27 != (__int64 *)-80LL )
        {
          v29 = 1801679955;
          v13 = (unsigned __int16 *)v30;
          if ( v30 )
            goto LABEL_16;
        }
      }
    }
    v14 = (_DWORD *)((__int64 (__fastcall *)(__int64))g_pfnAllocate)(2056);
    if ( v14 )
    {
      *v14 = 1885431112;
      v13 = (unsigned __int16 *)(v14 + 2);
      if ( v14 != (_DWORD *)-8LL )
      {
LABEL_16:
        v31 = v13;
        if ( (unsigned __int8)IsWppLevelEnabled(a5) )
        {
          LODWORD(v28) = a4;
          StringCchPrintfExW(v13, 0x400u, &v31, &v36, 0, L"(%S):(%S):(%d) ", a2, a3, v28);
          v15 = v31;
          v11 = v36;
        }
        FormatTraceMessage(v15, v11, a6, a7);
        if ( a5 )
        {
          switch ( a5 )
          {
            case 1u:
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v17, v13);
              }
              goto LABEL_30;
            case 2u:
              v21 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
              {
                goto LABEL_59;
              }
              v22 = 12;
              break;
            case 3u:
              v21 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
              {
                goto LABEL_59;
              }
              v22 = 13;
              break;
            case 4u:
              v21 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
              {
                goto LABEL_59;
              }
              v22 = 14;
              break;
            case 5u:
              v21 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 )
              {
                goto LABEL_59;
              }
              v22 = 15;
              break;
            default:
              v18 = a5 - 6;
              if ( a5 != 6 )
              {
                if ( a5 != 7 )
                  goto LABEL_29;
                goto LABEL_26;
              }
              v21 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
              {
                goto LABEL_59;
              }
              v22 = 16;
              break;
          }
          WPP_SF_S(v21[2], v22, v17, v13);
          goto LABEL_59;
        }
LABEL_26:
        v18 = (unsigned __int8)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v17, v13);
LABEL_29:
        if ( a5 > 1 )
        {
LABEL_31:
          switch ( a5 )
          {
            case 0u:
              v32 = 0;
              v33 = a2;
              v34 = a3;
              v35 = a4;
              if ( ComTrace::IsEnabled(v18, v16) )
              {
                wil::details::static_lazy<ComTrace>::get(
                  v25,
                  _lambda_f8a79a44bba2ee3470b25df359f31864_::_lambda_invoker_cdecl_);
                ComTrace::Error_(v26, a1, v13, &v32);
              }
              break;
            case 1u:
              v32 = 0;
              v33 = a2;
              v34 = a3;
              v35 = a4;
              if ( ComTrace::IsEnabled(v18, v16) )
              {
                wil::details::static_lazy<ComTrace>::get(
                  v23,
                  _lambda_f8a79a44bba2ee3470b25df359f31864_::_lambda_invoker_cdecl_);
                ComTrace::Warning_(v24, a1, v13, &v32);
              }
              break;
            case 7u:
              goto LABEL_34;
          }
LABEL_59:
          if ( v13 )
          {
            if ( *((_DWORD *)v13 - 2) == 1885431112 )
              ((void (*)(void))g_pfnFree)();
          }
          return;
        }
LABEL_30:
        if ( !TraceAllowedByRateLimiter() )
        {
LABEL_34:
          v32 = 0;
          v33 = a2;
          v34 = a3;
          v35 = a4;
          if ( ComTrace::IsEnabled(v18, v16) )
          {
            wil::details::static_lazy<ComTrace>::get(
              v19,
              _lambda_f8a79a44bba2ee3470b25df359f31864_::_lambda_invoker_cdecl_);
            ComTrace::NoisyError_(v20, a1, v13, &v32);
          }
          goto LABEL_59;
        }
        goto LABEL_31;
      }
    }
  }
}

```

## disassembly

```asm
0x14000eb14  push    rbp
0x14000eb16  push    rbx
0x14000eb17  push    rsi
0x14000eb18  push    rdi
0x14000eb19  push    r12
0x14000eb1b  push    r13
0x14000eb1d  push    r14
0x14000eb1f  push    r15
0x14000eb21  sub     rsp, 98h
0x14000eb28  lea     rbp, [rsp+50h]
0x14000eb2d  mov     rax, cs:__security_cookie
0x14000eb34  xor     rax, rbp
0x14000eb37  mov     [rbp+80h+var_50], rax
0x14000eb3b  mov     eax, cs:?g_hrToDebug@@3JA; long g_hrToDebug
0x14000eb41  mov     r15d, r9d
0x14000eb44  mov     r12, r8
0x14000eb47  mov     r13, rdx
0x14000eb4a  mov     r14d, ecx
0x14000eb4d  test    eax, eax
0x14000eb4f  jz      short loc_14000EB6D
0x14000eb51  cmp     ecx, eax
0x14000eb53  jnz     short loc_14000EB6D
0x14000eb55  call    cs:__imp_IsDebuggerPresent
0x14000eb5b  test    eax, eax
0x14000eb5d  jnz     short loc_14000EB68
0x14000eb5f  cmp     ds:7FFE02D4h, al
0x14000eb66  jz      short loc_14000EB6D
0x14000eb68  call    ?BreakIntoDebugger@@YAXXZ; BreakIntoDebugger(void)
0x14000eb6d  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x14000eb74  mov     edi, [rbp+80h+arg_20]
0x14000eb7a  jnz     short loc_14000EB8A
0x14000eb7c  cmp     edi, 1
0x14000eb7f  jbe     short loc_14000EB8A
0x14000eb81  cmp     edi, 7
0x14000eb84  jnz     loc_14000EEE7
0x14000eb8a  mov     edx, 800h
0x14000eb8f  mov     esi, 400h
0x14000eb94  cmp     cs:g_ulMaxStackAllocSize, rdx
0x14000eb9b  mov     [rbp+80h+var_58], rsi
0x14000eb9f  jb      short loc_14000EBE0
0x14000eba1  mov     rcx, cs:g_ulAdditionalProbeSize
0x14000eba8  add     rcx, 808h
0x14000ebaf  cmp     rcx, rdx
0x14000ebb2  jb      short loc_14000EBE0
0x14000ebb4  call    VerifyStackAvailable
0x14000ebb9  test    eax, eax
0x14000ebbb  jz      short loc_14000EBE0
0x14000ebbd  mov     eax, [rsp+0D0h+var_D0]
0x14000ebc0  mov     eax, 810h
0x14000ebc5  sub     rsp, rax
0x14000ebc8  lea     rbx, [rsp+8E0h+var_890]
0x14000ebcd  mov     eax, [rbx]
0x14000ebcf  test    rbx, rbx
0x14000ebd2  jz      short loc_14000EBE0
0x14000ebd4  mov     dword ptr [rbx], 6B637453h
0x14000ebda  add     rbx, 8
0x14000ebde  jnz     short loc_14000EC0D
0x14000ebe0  mov     rax, cs:g_pfnAllocate
0x14000ebe7  mov     ecx, 808h
0x14000ebec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ebf1  mov     rbx, rax
0x14000ebf4  test    rax, rax
0x14000ebf7  jz      loc_14000EEE7
0x14000ebfd  mov     dword ptr [rax], 70616548h
0x14000ec03  add     rbx, 8
0x14000ec07  jz      loc_14000EEE7
0x14000ec0d  mov     ecx, edi
0x14000ec0f  mov     [rbp+80h+var_80], rbx
0x14000ec13  mov     r10, rbx
0x14000ec16  call    IsWppLevelEnabled
0x14000ec1b  test    al, al
0x14000ec1d  jz      short loc_14000EC5E
0x14000ec1f  mov     dword ptr [rsp+8E0h+var_8A0], r15d
0x14000ec24  lea     rax, aSSD; "(%S):(%S):(%d) "
0x14000ec2b  mov     [rsp+8E0h+var_8A8], r12
0x14000ec30  lea     r9, [rbp+80h+var_58]; unsigned __int64 *
0x14000ec34  mov     [rsp+8E0h+var_8B0], r13
0x14000ec39  lea     r8, [rbp+80h+var_80]; unsigned __int16 **
0x14000ec3d  mov     [rsp+8E0h+var_8B8], rax; unsigned __int16 *
0x14000ec42  mov     rdx, rsi; unsigned __int64
0x14000ec45  mov     rcx, rbx; pszDest
0x14000ec48  mov     qword ptr [rsp+8E0h+var_8C0], 0; unsigned int
0x14000ec51  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x14000ec56  mov     r10, [rbp+80h+var_80]
0x14000ec5a  mov     rsi, [rbp+80h+var_58]
0x14000ec5e  mov     r9, [rbp+80h+arg_30]; char *
0x14000ec65  mov     rdx, rsi; unsigned __int64
0x14000ec68  mov     r8, [rbp+80h+arg_28]; unsigned __int16 *
0x14000ec6f  mov     rcx, r10; unsigned __int16 *
0x14000ec72  call    ?FormatTraceMessage@@YAXPEAG_KPEBGPEAD@Z; FormatTraceMessage(ushort *,unsigned __int64,ushort const *,char *)
0x14000ec77  xor     esi, esi
0x14000ec79  mov     ecx, edi
0x14000ec7b  test    edi, edi
0x14000ec7d  jz      short loc_14000ECBA
0x14000ec7f  sub     ecx, 1
0x14000ec82  jz      loc_14000EE27
0x14000ec88  sub     ecx, 1
0x14000ec8b  jz      loc_14000EDFC
0x14000ec91  sub     ecx, 1
0x14000ec94  jz      loc_14000EDD1
0x14000ec9a  sub     ecx, 1
0x14000ec9d  jz      loc_14000EDA9
0x14000eca3  sub     ecx, 1
0x14000eca6  jz      loc_14000ED81
0x14000ecac  sub     ecx, 1
0x14000ecaf  jz      loc_14000ED4A
0x14000ecb5  cmp     ecx, 1
0x14000ecb8  jnz     short loc_14000ECE4
0x14000ecba  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ecc1  lea     rax, WPP_GLOBAL_Control
0x14000ecc8  cmp     rcx, rax
0x14000eccb  jz      short loc_14000ECE4
0x14000eccd  test    byte ptr [rcx+1Ch], 1
0x14000ecd1  jz      short loc_14000ECE4
0x14000ecd3  mov     rcx, [rcx+10h]
0x14000ecd7  mov     edx, 0Ah
0x14000ecdc  mov     r9, rbx
0x14000ecdf  call    WPP_SF_S
0x14000ece4  cmp     edi, 1
0x14000ece7  ja      short loc_14000ECF2
0x14000ece9  call    ?TraceAllowedByRateLimiter@@YA_NXZ; TraceAllowedByRateLimiter(void)
0x14000ecee  test    al, al
0x14000ecf0  jz      short loc_14000ED0C
0x14000ecf2  test    edi, edi
0x14000ecf4  jz      loc_14000EE95
0x14000ecfa  sub     edi, 1
0x14000ecfd  jz      loc_14000EE5E
0x14000ed03  cmp     edi, 6
0x14000ed06  jnz     loc_14000EECA
0x14000ed0c  mov     qword ptr [rbp+80h+var_78.cost], rsi
0x14000ed10  mov     [rbp+80h+var_70], r13
0x14000ed14  mov     [rbp+80h+var_68], r12
0x14000ed18  mov     [rbp+80h+var_60], r15w
0x14000ed1d  call    ?IsEnabled@ComTrace@@SA_NE_K@Z; ComTrace::IsEnabled(uchar,unsigned __int64)
0x14000ed22  test    al, al
0x14000ed24  jz      loc_14000EECA
0x14000ed2a  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f8a79a44bba2ee3470b25df359f31864_@@CA@XZ; _lambda_f8a79a44bba2ee3470b25df359f31864_::_lambda_invoker_cdecl_(void)
0x14000ed31  call    ?get@?$static_lazy@VComTrace@@@details@wil@@QEAAPEAVComTrace@@P6AXXZ@Z; wil::details::static_lazy<ComTrace>::get(void (*)(void))
0x14000ed36  lea     r9, [rbp+80h+var_78]; struct DiagnosticsInfo *
0x14000ed3a  mov     r8, rbx; unsigned __int16 *
0x14000ed3d  mov     edx, r14d; int
0x14000ed40  call    ?NoisyError_@ComTrace@@QEAAXJPEBGAEBUDiagnosticsInfo@wil@@@Z; ComTrace::NoisyError_(long,ushort const *,wil::DiagnosticsInfo const &)
0x14000ed45  jmp     loc_14000EECA
0x14000ed4a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ed51  lea     rax, WPP_GLOBAL_Control
0x14000ed58  cmp     rcx, rax
0x14000ed5b  jz      loc_14000EECA
0x14000ed61  test    byte ptr [rcx+1Ch], 40h
0x14000ed65  jz      loc_14000EECA
0x14000ed6b  mov     edx, 10h
0x14000ed70  mov     rcx, [rcx+10h]
0x14000ed74  mov     r9, rbx
0x14000ed77  call    WPP_SF_S
0x14000ed7c  jmp     loc_14000EECA
0x14000ed81  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ed88  lea     rax, WPP_GLOBAL_Control
0x14000ed8f  cmp     rcx, rax
0x14000ed92  jz      loc_14000EECA
0x14000ed98  test    byte ptr [rcx+1Ch], 20h
0x14000ed9c  jz      loc_14000EECA
0x14000eda2  mov     edx, 0Fh
0x14000eda7  jmp     short loc_14000ED70
0x14000eda9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000edb0  lea     rax, WPP_GLOBAL_Control
0x14000edb7  cmp     rcx, rax
0x14000edba  jz      loc_14000EECA
0x14000edc0  test    byte ptr [rcx+1Ch], 10h
0x14000edc4  jz      loc_14000EECA
0x14000edca  mov     edx, 0Eh
0x14000edcf  jmp     short loc_14000ED70
0x14000edd1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000edd8  lea     rax, WPP_GLOBAL_Control
0x14000eddf  cmp     rcx, rax
0x14000ede2  jz      loc_14000EECA
0x14000ede8  test    byte ptr [rcx+1Ch], 8
0x14000edec  jz      loc_14000EECA
0x14000edf2  mov     edx, 0Dh
0x14000edf7  jmp     loc_14000ED70
0x14000edfc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ee03  lea     rax, WPP_GLOBAL_Control
0x14000ee0a  cmp     rcx, rax
0x14000ee0d  jz      loc_14000EECA
0x14000ee13  test    byte ptr [rcx+1Ch], 4
0x14000ee17  jz      loc_14000EECA
0x14000ee1d  mov     edx, 0Ch
0x14000ee22  jmp     loc_14000ED70
0x14000ee27  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ee2e  lea     rax, WPP_GLOBAL_Control
0x14000ee35  cmp     rcx, rax
0x14000ee38  jz      loc_14000ECE9
0x14000ee3e  test    byte ptr [rcx+1Ch], 2
0x14000ee42  jz      loc_14000ECE9
0x14000ee48  mov     rcx, [rcx+10h]
0x14000ee4c  mov     edx, 0Bh
0x14000ee51  mov     r9, rbx
0x14000ee54  call    WPP_SF_S
0x14000ee59  jmp     loc_14000ECE9
0x14000ee5e  mov     qword ptr [rbp+80h+var_78.cost], rsi
0x14000ee62  mov     [rbp+80h+var_70], r13
0x14000ee66  mov     [rbp+80h+var_68], r12
0x14000ee6a  mov     [rbp+80h+var_60], r15w
0x14000ee6f  call    ?IsEnabled@ComTrace@@SA_NE_K@Z; ComTrace::IsEnabled(uchar,unsigned __int64)
0x14000ee74  test    al, al
0x14000ee76  jz      short loc_14000EECA
0x14000ee78  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f8a79a44bba2ee3470b25df359f31864_@@CA@XZ; _lambda_f8a79a44bba2ee3470b25df359f31864_::_lambda_invoker_cdecl_(void)
0x14000ee7f  call    ?get@?$static_lazy@VComTrace@@@details@wil@@QEAAPEAVComTrace@@P6AXXZ@Z; wil::details::static_lazy<ComTrace>::get(void (*)(void))
0x14000ee84  lea     r9, [rbp+80h+var_78]; struct DiagnosticsInfo *
0x14000ee88  mov     r8, rbx; unsigned __int16 *
0x14000ee8b  mov     edx, r14d; int
0x14000ee8e  call    ?Warning_@ComTrace@@QEAAXJPEBGAEBUDiagnosticsInfo@wil@@@Z; ComTrace::Warning_(long,ushort const *,wil::DiagnosticsInfo const &)
0x14000ee93  jmp     short loc_14000EECA
0x14000ee95  mov     qword ptr [rbp+80h+var_78.cost], rsi
0x14000ee99  mov     [rbp+80h+var_70], r13
0x14000ee9d  mov     [rbp+80h+var_68], r12
0x14000eea1  mov     [rbp+80h+var_60], r15w
0x14000eea6  call    ?IsEnabled@ComTrace@@SA_NE_K@Z; ComTrace::IsEnabled(uchar,unsigned __int64)
0x14000eeab  test    al, al
0x14000eead  jz      short loc_14000EECA
0x14000eeaf  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f8a79a44bba2ee3470b25df359f31864_@@CA@XZ; _lambda_f8a79a44bba2ee3470b25df359f31864_::_lambda_invoker_cdecl_(void)
0x14000eeb6  call    ?get@?$static_lazy@VComTrace@@@details@wil@@QEAAPEAVComTrace@@P6AXXZ@Z; wil::details::static_lazy<ComTrace>::get(void (*)(void))
0x14000eebb  lea     r9, [rbp+80h+var_78]; struct DiagnosticsInfo *
0x14000eebf  mov     r8, rbx; unsigned __int16 *
0x14000eec2  mov     edx, r14d; int
0x14000eec5  call    ?Error_@ComTrace@@QEAAXJPEBGAEBUDiagnosticsInfo@wil@@@Z; ComTrace::Error_(long,ushort const *,wil::DiagnosticsInfo const &)
0x14000eeca  test    rbx, rbx
0x14000eecd  jz      short loc_14000EEE7
0x14000eecf  lea     rcx, [rbx-8]
0x14000eed3  cmp     dword ptr [rcx], 70616548h
0x14000eed9  jnz     short loc_14000EEE7
0x14000eedb  mov     rax, cs:g_pfnFree
0x14000eee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eee7  mov     rcx, [rbp+80h+var_50]
0x14000eeeb  xor     rcx, rbp; StackCookie
0x14000eeee  call    __security_check_cookie
0x14000eef3  lea     rsp, [rbp+48h]
0x14000eef7  pop     r15
0x14000eef9  pop     r14
0x14000eefb  pop     r13
0x14000eefd  pop     r12
0x14000eeff  pop     rdi
0x14000ef00  pop     rsi
0x14000ef01  pop     rbx
0x14000ef02  pop     rbp
0x14000ef03  retn
```
