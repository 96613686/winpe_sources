# DeleteFilterFromIndex

- ea: `0x180033f90`
- end: `0x180034236`
- name: `DeleteFilterFromIndex`
- size: `678`
- prototype: ``
- caller_count: `4`
- callee_count: `15`
- tags: ``

## callers

- `0x180033f30`
- `0x18007ff60`
- `0x18008023c`
- `0x180080650`

## callees

- `0x1800135ac`
- `0x1800150b0`
- `0x1800177d0`
- `0x1800197d0`
- `0x180020960`
- `0x18002d470`
- `0x1800330a0`
- `0x180033f90`
- `0x180036258`
- `0x180036c10`
- `0x18005614c`
- `0x18007b290`
- `0x18007b79c`
- `0x18007b848`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800341b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800341b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800341d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800341d6`

## string_xrefs

- `0x180034012`: `DeleteFilterFromIndex`
- `0x180034112`: `DeleteFilterFromIndex`
- `0x180034214`: `DeleteFilterFromIndex`

## pseudocode

```c
__int64 __fastcall DeleteFilterFromIndex(__int64 a1, unsigned int a2, unsigned __int64 a3, int a4, __int64 a5)
{
  __int64 v6; // rbp
  unsigned __int16 v8; // r14
  int LayerStringFromLayerId; // eax
  __int64 v10; // r10
  int v11; // edx
  int v12; // r8d
  __int64 v13; // rbx
  __int64 IntFilter; // rax
  __int64 v15; // rdi
  int v16; // edx
  int v17; // ebx
  int v18; // r8d
  _QWORD *v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rsi
  const char *v22; // rdx
  int IsEnabledDeviceUsageNoInline; // eax
  _QWORD v25[9]; // [rsp+50h] [rbp-48h] BYREF

  v6 = a2;
  v8 = a1;
  v25[0] = 0;
  a5 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    LayerStringFromLayerId = WfpGetLayerStringFromLayerId((unsigned __int16)a1);
    WPP_SF_sddI(*(_QWORD *)(v10 + 16), v11, v12, LayerStringFromLayerId, v8, v6, v12);
  }
  if ( a4 && (_DWORD)v6 )
  {
    v13 = WfpReportSysErrorAsNtStatus(a1, "DeleteFilterFromIndex", 3221225485LL);
    goto LABEL_37;
  }
  IntFilter = FindIntFilter(v8, a3, &a5);
  v15 = a5;
  v13 = IntFilter;
  if ( IntFilter )
    goto LABEL_35;
  v17 = WfpGetLayerStringFromLayerId(v8);
  if ( *(__int64 *)(v15 + 16) <= 2 )
    goto LABEL_14;
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_19;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_sddIqd(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, v18, v17, v8, v6, a3, v15, *(_DWORD *)(v15 + 16));
LABEL_14:
    v19 = WPP_GLOBAL_Control;
  }
  if ( v19 != &WPP_GLOBAL_Control && *((_BYTE *)v19 + 25) >= 5u && (*((_BYTE *)v19 + 28) & 8) != 0 )
    WPP_SF_sddIq(v19[2], v16, v18, v17, v8, v6, a3, v15);
LABEL_19:
  v13 = GetLayerFromIdRead(v8, v25);
  if ( !v13 )
  {
    v21 = v25[0];
    if ( a4 || !*(_QWORD *)(v25[0] + 96LL) || (_DWORD)v6 )
    {
      if ( (unsigned int)IsValidIndex(v25[0], (unsigned int)v6) )
      {
        v13 = (*((__int64 (__fastcall **)(_QWORD, __int64))gWfpGlobal
               + 7 * *(int *)(*(_QWORD *)(v21 + 144) + 16 * v6 + 8)
               + 20))(
                *(_QWORD *)(*(_QWORD *)(v21 + 144) + 16 * v6),
                v15);
        if ( !v13 )
        {
          if ( (Feature_Netsec_BugFixes_25C_Loopback_Checksum_Injection__private_featureState & 0x10) != 0 )
            IsEnabledDeviceUsageNoInline = Feature_Netsec_BugFixes_25C_Loopback_Checksum_Injection__private_featureState
                                         & 1;
          else
            IsEnabledDeviceUsageNoInline = Feature_Netsec_BugFixes_25C_Loopback_Checksum_Injection__private_IsEnabledDeviceUsageNoInline();
          if ( IsEnabledDeviceUsageNoInline )
            *((_BYTE *)gWfpGlobal + 1076) = AreAllIpv4InLayersEmpty();
          EnterCriticalSection(&gLayerStatsLock);
          *(_QWORD *)(v21 + 136) -= *(_QWORD *)(v15 + 80);
          _InterlockedDecrement((volatile signed __int32 *)(v21 + 152));
          LeaveCriticalSection(&gLayerStatsLock);
          v13 = RemoveFilterFromFilterHashtable(v8, a3);
          if ( !v13 )
            HandleFilterDeref(v15, 0);
        }
        goto LABEL_35;
      }
      v22 = "IsValidIndex";
    }
    else
    {
      v22 = "DeleteFilterFromIndex";
    }
    v13 = WfpReportSysErrorAsNtStatus(v20, v22, 3221225485LL);
  }
LABEL_35:
  if ( v15 )
    HandleFilterDeref(v15, 0);
LABEL_37:
  if ( v13 )
    WfpReportError(v13, "DeleteFilterFromIndex");
  return v13;
}

```

## disassembly

```asm
0x180033f90  mov     rax, rsp
0x180033f93  push    rbx
0x180033f94  push    rbp
0x180033f95  push    rsi
0x180033f96  push    rdi
0x180033f97  push    r12
0x180033f99  push    r14
0x180033f9b  push    r15
0x180033f9d  sub     rsp, 60h
0x180033fa1  mov     r12d, r9d
0x180033fa4  mov     ebp, edx
0x180033fa6  mov     r15, r8
0x180033fa9  movzx   r14d, cx
0x180033fad  mov     qword ptr [rax-48h], 0
0x180033fb5  mov     qword ptr [rax+28h], 0
0x180033fbd  mov     r10, cs:WPP_GLOBAL_Control
0x180033fc4  lea     rax, WPP_GLOBAL_Control
0x180033fcb  mov     sil, 8
0x180033fce  cmp     r10, rax
0x180033fd1  jz      short loc_180034003
0x180033fd3  cmp     byte ptr [r10+19h], 5
0x180033fd8  jb      short loc_180034003
0x180033fda  test    [r10+1Ch], sil
0x180033fde  jz      short loc_180034003
0x180033fe0  movzx   ecx, r14w
0x180033fe4  call    WfpGetLayerStringFromLayerId
0x180033fe9  mov     rcx, [r10+10h]
0x180033fed  mov     r9, rax
0x180033ff0  mov     [rsp+98h+var_68], r8
0x180033ff5  mov     [rsp+98h+var_70], ebp
0x180033ff9  mov     [rsp+98h+var_78], r14d
0x180033ffe  call    WPP_SF_sddI
0x180034003  test    r12d, r12d
0x180034006  jz      short loc_180034026
0x180034008  test    ebp, ebp
0x18003400a  jz      short loc_180034026
0x18003400c  mov     r8d, 0C000000Dh
0x180034012  lea     rdx, aDeletefilterfr; "DeleteFilterFromIndex"
0x180034019  call    WfpReportSysErrorAsNtStatus
0x18003401e  mov     rbx, rax
0x180034021  jmp     loc_18003420F
0x180034026  lea     r8, [rsp+98h+arg_20]
0x18003402e  mov     rdx, r15
0x180034031  movzx   ecx, r14w
0x180034035  call    FindIntFilter
0x18003403a  mov     rdi, [rsp+98h+arg_20]
0x180034042  mov     rbx, rax
0x180034045  test    rax, rax
0x180034048  jnz     loc_180034200
0x18003404e  movzx   ecx, r14w
0x180034052  call    WfpGetLayerStringFromLayerId
0x180034057  cmp     qword ptr [rdi+10h], 2
0x18003405c  mov     rbx, rax
0x18003405f  jle     short loc_1800340A6
0x180034061  mov     rcx, cs:WPP_GLOBAL_Control
0x180034068  lea     rax, WPP_GLOBAL_Control
0x18003406f  cmp     rcx, rax
0x180034072  jz      short loc_1800340E4
0x180034074  cmp     byte ptr [rcx+19h], 3
0x180034078  jb      short loc_1800340B4
0x18003407a  test    [rcx+1Ch], sil
0x18003407e  jz      short loc_1800340B4
0x180034080  mov     eax, [rdi+10h]
0x180034083  mov     r9, rbx
0x180034086  mov     rcx, [rcx+10h]
0x18003408a  mov     [rsp+98h+var_58], eax
0x18003408e  mov     [rsp+98h+var_60], rdi
0x180034093  mov     [rsp+98h+var_68], r15
0x180034098  mov     [rsp+98h+var_70], ebp
0x18003409c  mov     [rsp+98h+var_78], r14d
0x1800340a1  call    WPP_SF_sddIqd
0x1800340a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800340ad  lea     rax, WPP_GLOBAL_Control
0x1800340b4  cmp     rcx, rax
0x1800340b7  jz      short loc_1800340E4
0x1800340b9  cmp     byte ptr [rcx+19h], 5
0x1800340bd  jb      short loc_1800340E4
0x1800340bf  test    [rcx+1Ch], sil
0x1800340c3  jz      short loc_1800340E4
0x1800340c5  mov     rcx, [rcx+10h]
0x1800340c9  mov     r9, rbx
0x1800340cc  mov     [rsp+98h+var_60], rdi
0x1800340d1  mov     [rsp+98h+var_68], r15
0x1800340d6  mov     [rsp+98h+var_70], ebp
0x1800340da  mov     [rsp+98h+var_78], r14d
0x1800340df  call    WPP_SF_sddIq
0x1800340e4  lea     rdx, [rsp+98h+var_48]
0x1800340e9  movzx   ecx, r14w
0x1800340ed  call    GetLayerFromIdRead
0x1800340f2  mov     rbx, rax
0x1800340f5  test    rax, rax
0x1800340f8  jnz     loc_180034200
0x1800340fe  mov     rsi, [rsp+98h+var_48]
0x180034103  test    r12d, r12d
0x180034106  jnz     short loc_18003412C
0x180034108  cmp     [rsi+60h], rax
0x18003410c  jz      short loc_18003412C
0x18003410e  test    ebp, ebp
0x180034110  jnz     short loc_18003412C
0x180034112  lea     rdx, aDeletefilterfr; "DeleteFilterFromIndex"
0x180034119  mov     r8d, 0C000000Dh
0x18003411f  call    WfpReportSysErrorAsNtStatus
0x180034124  mov     rbx, rax
0x180034127  jmp     loc_180034200
0x18003412c  mov     edx, ebp
0x18003412e  mov     rcx, rsi
0x180034131  call    IsValidIndex
0x180034136  test    eax, eax
0x180034138  jnz     short loc_180034143
0x18003413a  lea     rdx, aIsvalidindex; "IsValidIndex"
0x180034141  jmp     short loc_180034119
0x180034143  mov     r8, [rsi+90h]
0x18003414a  mov     r9, rbp
0x18003414d  add     r9, r9
0x180034150  mov     rdx, rdi
0x180034153  movsxd  rax, dword ptr [r8+r9*8+8]
0x180034158  imul    rcx, rax, 38h ; '8'
0x18003415c  mov     rax, cs:gWfpGlobal
0x180034163  mov     rax, [rcx+rax+0A0h]
0x18003416b  mov     rcx, [r8+r9*8]
0x18003416f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034174  mov     rbx, rax
0x180034177  test    rax, rax
0x18003417a  jnz     loc_180034200
0x180034180  mov     eax, cs:Feature_Netsec_BugFixes_25C_Loopback_Checksum_Injection__private_featureState
0x180034186  test    al, 10h
0x180034188  jz      short loc_18003418F
0x18003418a  and     eax, 1
0x18003418d  jmp     short loc_180034194
0x18003418f  call    Feature_Netsec_BugFixes_25C_Loopback_Checksum_Injection__private_IsEnabledDeviceUsageNoInline
0x180034194  test    eax, eax
0x180034196  jz      short loc_1800341AA
0x180034198  call    AreAllIpv4InLayersEmpty
0x18003419d  mov     rcx, cs:gWfpGlobal
0x1800341a4  mov     [rcx+434h], al
0x1800341aa  lea     rcx, gLayerStatsLock; lpCriticalSection
0x1800341b1  call    cs:__imp_EnterCriticalSection
0x1800341b8  nop     dword ptr [rax+rax+00h]
0x1800341bd  mov     rax, [rdi+50h]
0x1800341c1  lea     rcx, gLayerStatsLock; lpCriticalSection
0x1800341c8  sub     [rsi+88h], rax
0x1800341cf  lock dec dword ptr [rsi+98h]
0x1800341d6  call    cs:__imp_LeaveCriticalSection
0x1800341dd  nop     dword ptr [rax+rax+00h]
0x1800341e2  mov     rdx, r15
0x1800341e5  movzx   ecx, r14w
0x1800341e9  call    RemoveFilterFromFilterHashtable
0x1800341ee  mov     rbx, rax
0x1800341f1  test    rax, rax
0x1800341f4  jnz     short loc_180034200
0x1800341f6  xor     edx, edx
0x1800341f8  mov     rcx, rdi
0x1800341fb  call    HandleFilterDeref
0x180034200  test    rdi, rdi
0x180034203  jz      short loc_18003420F
0x180034205  xor     edx, edx
0x180034207  mov     rcx, rdi
0x18003420a  call    HandleFilterDeref
0x18003420f  test    rbx, rbx
0x180034212  jz      short loc_180034223
0x180034214  lea     rdx, aDeletefilterfr; "DeleteFilterFromIndex"
0x18003421b  mov     rcx, rbx
0x18003421e  call    WfpReportError
0x180034223  mov     rax, rbx
0x180034226  add     rsp, 60h
0x18003422a  pop     r15
0x18003422c  pop     r14
0x18003422e  pop     r12
0x180034230  pop     rdi
0x180034231  pop     rsi
0x180034232  pop     rbp
0x180034233  pop     rbx
0x180034234  retn
```
