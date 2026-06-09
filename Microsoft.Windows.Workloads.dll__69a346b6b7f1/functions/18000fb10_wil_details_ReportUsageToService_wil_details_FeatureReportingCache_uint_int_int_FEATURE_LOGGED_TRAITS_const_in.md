# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18000fb10`
- end: `0x18000fd18`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `520`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000e370`
- `0x18002a390`

## callees

- `0x18000f2c0`
- `0x18000f8f0`
- `0x18000fb10`
- `0x18003bed0`

## pseudocode

```c
void __fastcall wil::details::ReportUsageToService(
        volatile signed __int32 *a1,
        DWORD a2,
        int a3,
        int a4,
        __int64 a5,
        unsigned int a6,
        int a7)
{
  unsigned int v11; // ebx
  int v12; // eax
  unsigned __int8 v13; // bp
  __int64 v14; // rax
  __int64 v15; // xmm0_8
  __int64 v16; // r8
  void (__fastcall *v17)(_QWORD, __int64, _QWORD, _QWORD); // rax
  __int64 v18; // rdx
  __int128 v19; // [rsp+50h] [rbp-68h] BYREF
  __int64 v20; // [rsp+60h] [rbp-58h]
  _BYTE v21[24]; // [rsp+68h] [rbp-50h] BYREF

  if ( a7 )
  {
    switch ( a7 )
    {
      case 0:
        goto LABEL_25;
      case 1:
        v11 = 4;
        if ( a6 )
          v11 = 0;
        break;
      case 2:
        v11 = 5;
        if ( a6 )
          v11 = 1;
        break;
      case 3:
        v11 = 6;
        if ( a6 )
          v11 = 2;
        break;
      case 4:
        v11 = 7;
        if ( a6 )
          v11 = 3;
        break;
      case 5:
        v11 = 10;
        if ( a6 )
          v11 = 8;
        break;
      case 6:
        v11 = 11;
        if ( a6 )
          v11 = 9;
        break;
      default:
        if ( (unsigned __int8)(a7 - 100) > 0x31u )
        {
LABEL_25:
          v11 = 255;
        }
        else
        {
          v12 = 100;
          if ( !a6 )
            v12 = 150;
          v11 = v12 + (unsigned __int8)(a7 - 100);
        }
        break;
    }
    v13 = *(_BYTE *)(a5 + 4);
    v14 = wil_details_FeatureReporting_RecordUsageInCache((__int64)v21, a1, v11);
    v15 = *(_QWORD *)(v14 + 16);
    v19 = *(_OWORD *)v14;
    v20 = v15;
    wil::details::RecordFeatureUsageCallback(a2, v11, v16, (__int64)a1, &v19);
    if ( a3 )
    {
      v17 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
      v18 = v11;
      LODWORD(v18) = v11 | 0x80000000;
      if ( !a4 )
        v18 = v11;
      if ( g_wil_details_internalRecordFeatureUsage
        || (v17 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
      {
        v17(a2, v18, 0, 0);
      }
    }
    if ( !(_DWORD)v20 )
    {
      if ( g_wil_details_realtimeFeatureUsageHook )
        g_wil_details_realtimeFeatureUsageHook(a2, v11, v13);
      if ( g_wil_details_pfnFeatureLoggingHook )
        g_wil_details_pfnFeatureLoggingHook(a2, a5, 0, a6, &a7, 0, 0, 1);
    }
  }
}

```

## disassembly

```asm
0x18000fb10  mov     rax, rsp
0x18000fb13  push    rsi
0x18000fb14  push    r12
0x18000fb16  push    r13
0x18000fb18  push    r14
0x18000fb1a  push    r15
0x18000fb1c  sub     rsp, 90h
0x18000fb23  mov     r13, [rsp+0B8h+arg_20]
0x18000fb2b  mov     esi, edx
0x18000fb2d  movsxd  rdx, dword ptr [rax+38h]
0x18000fb31  mov     r14d, r9d
0x18000fb34  mov     r12d, r8d
0x18000fb37  mov     r15, rcx
0x18000fb3a  test    edx, edx
0x18000fb3c  jz      loc_18000FCE9
0x18000fb42  mov     [rax+18h], rbx
0x18000fb46  xor     r9d, r9d
0x18000fb49  mov     [rax-30h], rbp
0x18000fb4d  mov     r10d, 1
0x18000fb53  mov     [rax-38h], rdi
0x18000fb57  mov     edi, [rsp+0B8h+arg_28]
0x18000fb5e  cmp     edx, 6; switch 7 cases
0x18000fb61  ja      short def_18000FB75; jumptable 000000018000FB75 default case
0x18000fb63  lea     r8, cs:180000000h
0x18000fb6a  mov     ecx, ds:(jpt_18000FB75 - 180000000h)[r8+rdx*4]
0x18000fb72  add     rcx, r8
0x18000fb75  jmp     rcx; switch jump
0x18000fb77  test    edi, edi; jumptable 000000018000FB75 case 1
0x18000fb79  mov     ebx, 4
0x18000fb7e  cmovnz  ebx, r9d
0x18000fb82  jmp     short loc_18000FBFA
0x18000fb84  test    edi, edi; jumptable 000000018000FB75 case 2
0x18000fb86  mov     ebx, 5
0x18000fb8b  cmovnz  ebx, r10d
0x18000fb8f  jmp     short loc_18000FBFA
0x18000fb91  test    edi, edi; jumptable 000000018000FB75 case 3
0x18000fb93  mov     ebx, 6
0x18000fb98  mov     eax, 2
0x18000fb9d  cmovnz  ebx, eax
0x18000fba0  jmp     short loc_18000FBFA
0x18000fba2  test    edi, edi; jumptable 000000018000FB75 case 4
0x18000fba4  mov     ebx, 7
0x18000fba9  mov     eax, 3
0x18000fbae  cmovnz  ebx, eax
0x18000fbb1  jmp     short loc_18000FBFA
0x18000fbb3  test    edi, edi; jumptable 000000018000FB75 case 5
0x18000fbb5  mov     ebx, 0Ah
0x18000fbba  mov     eax, 8
0x18000fbbf  cmovnz  ebx, eax
0x18000fbc2  jmp     short loc_18000FBFA
0x18000fbc4  test    edi, edi; jumptable 000000018000FB75 case 6
0x18000fbc6  mov     ebx, 0Bh
0x18000fbcb  mov     eax, 9
0x18000fbd0  cmovnz  ebx, eax
0x18000fbd3  jmp     short loc_18000FBFA
0x18000fbd5  lea     eax, [rdx-64h]; jumptable 000000018000FB75 default case
0x18000fbd8  cmp     al, 31h ; '1'
0x18000fbda  ja      short loc_18000FBF5; jumptable 000000018000FB75 case 0
0x18000fbdc  sub     dl, 64h ; 'd'
0x18000fbdf  mov     eax, 64h ; 'd'
0x18000fbe4  test    edi, edi
0x18000fbe6  movzx   ebx, dl
0x18000fbe9  mov     ecx, 96h
0x18000fbee  cmovz   eax, ecx
0x18000fbf1  add     ebx, eax
0x18000fbf3  jmp     short loc_18000FBFA
0x18000fbf5  mov     ebx, 0FFh; jumptable 000000018000FB75 case 0
0x18000fbfa  movzx   ebp, byte ptr [r13+4]
0x18000fbff  lea     rcx, [rsp+0B8h+var_50]
0x18000fc04  mov     r8d, ebx
0x18000fc07  mov     rdx, r15
0x18000fc0a  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000fc0f  mov     r9, r15
0x18000fc12  mov     edx, ebx
0x18000fc14  mov     ecx, esi
0x18000fc16  movups  xmm1, xmmword ptr [rax]
0x18000fc19  movsd   xmm0, qword ptr [rax+10h]
0x18000fc1e  lea     rax, [rsp+0B8h+var_68]
0x18000fc23  movups  [rsp+0B8h+var_68], xmm1
0x18000fc28  mov     [rsp+0B8h+var_98], rax
0x18000fc2d  movsd   [rsp+0B8h+var_58], xmm0
0x18000fc33  call    ?RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z; wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)
0x18000fc38  test    r12d, r12d
0x18000fc3b  jz      short loc_18000FC6F
0x18000fc3d  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000fc44  mov     edx, ebx
0x18000fc46  bts     edx, 1Fh
0x18000fc4a  test    r14d, r14d
0x18000fc4d  cmovz   edx, ebx
0x18000fc50  test    rax, rax
0x18000fc53  jnz     short loc_18000FC61
0x18000fc55  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000fc5c  test    rax, rax
0x18000fc5f  jz      short loc_18000FC6F
0x18000fc61  xor     r9d, r9d
0x18000fc64  xor     r8d, r8d
0x18000fc67  mov     ecx, esi
0x18000fc69  call    cs:__guard_dispatch_icall_fptr
0x18000fc6f  cmp     dword ptr [rsp+0B8h+var_58], 0
0x18000fc74  jnz     short loc_18000FCD1
0x18000fc76  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000fc7d  test    rax, rax
0x18000fc80  jz      short loc_18000FC90
0x18000fc82  movzx   r8d, bpl
0x18000fc86  mov     edx, ebx
0x18000fc88  mov     ecx, esi
0x18000fc8a  call    cs:__guard_dispatch_icall_fptr
0x18000fc90  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000fc97  test    rax, rax
0x18000fc9a  jz      short loc_18000FCD1
0x18000fc9c  mov     [rsp+0B8h+var_80], 1
0x18000fca5  lea     rcx, [rsp+0B8h+arg_30]
0x18000fcad  mov     [rsp+0B8h+var_88], 0
0x18000fcb2  mov     r9d, edi
0x18000fcb5  mov     [rsp+0B8h+var_90], 0
0x18000fcbe  xor     r8d, r8d
0x18000fcc1  mov     [rsp+0B8h+var_98], rcx
0x18000fcc6  mov     rdx, r13
0x18000fcc9  mov     ecx, esi
0x18000fccb  call    cs:__guard_dispatch_icall_fptr
0x18000fcd1  mov     rbp, [rsp+0B8h+var_30]
0x18000fcd9  mov     rbx, [rsp+0B8h+arg_10]
0x18000fce1  mov     rdi, [rsp+0B8h+var_38]
0x18000fce9  add     rsp, 90h
0x18000fcf0  pop     r15
0x18000fcf2  pop     r14
0x18000fcf4  pop     r13
0x18000fcf6  pop     r12
0x18000fcf8  pop     rsi
0x18000fcf9  retn
```
