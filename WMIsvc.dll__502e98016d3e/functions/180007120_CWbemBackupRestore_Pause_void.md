# CWbemBackupRestore::Pause(void)

- ea: `0x180007120`
- end: `0x1800076d8`
- name: `?Pause@CWbemBackupRestore@@UEAAJXZ`
- size: `1464`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180001d30`
- `0x180007120`
- `0x1800076e0`
- `0x180014cdc`
- `0x180014d24`
- `0x180014e4c`
- `0x180014ea0`
- `0x180014fd4`
- `0x18001d3a0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007164`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007164`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007630`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007665`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000768f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007630`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007665`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000768f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x180007184`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x180007184`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180007622`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180007622`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180007315`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180007315`
- `wbemcomn!EnableAllPrivileges` at `0x1800071aa`
- `wbemcomn!EnableAllPrivileges` at `0x1800071aa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800074ce`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800075af`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800074ce`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800075af`
- `wbemcomn!GetMemLogObject` at `0x1800074be`
- `wbemcomn!GetMemLogObject` at `0x18000759f`
- `wbemcomn!GetMemLogObject` at `0x1800074be`
- `wbemcomn!GetMemLogObject` at `0x18000759f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007272`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800073d5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007272`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800073d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWbemBackupRestore::Pause(PVOID Parameter)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  HRESULT DefaultRepDriverClsId; // edi
  __int64 v5; // r8
  LPVOID v6; // rsi
  __int64 v7; // r15
  LPVOID v8; // r14
  __int64 v9; // r8
  _QWORD *v10; // rcx
  __int64 result; // rax
  CMemoryLog *v12; // rax
  __int64 v13; // r8
  CMemoryLog *MemLogObject; // rax
  __int64 v15; // r8
  __int64 v16; // rcx
  DWORD LastError; // eax
  __int64 v18; // r8
  __int64 v19; // rdx
  void *v20; // rax
  DWORD v21; // eax
  volatile signed __int32 *v22; // rbx
  CMemoryLog *v23; // rax
  __int64 v24; // r8
  DWORD Period; // [rsp+28h] [rbp-C0h]
  LPVOID v26; // [rsp+48h] [rbp-A0h] BYREF
  void *phNewTimer; // [rsp+50h] [rbp-98h] BYREF
  ULONG BackTraceHash; // [rsp+58h] [rbp-90h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-88h] BYREF
  __int64 v30; // [rsp+68h] [rbp-80h] BYREF
  LPVOID v31; // [rsp+70h] [rbp-78h]
  __int64 v32; // [rsp+78h] [rbp-70h]
  LPVOID v33; // [rsp+80h] [rbp-68h]
  volatile signed __int32 *v34; // [rsp+88h] [rbp-60h]
  IID rclsid; // [rsp+90h] [rbp-58h] BYREF

  v34 = (volatile signed __int32 *)Parameter;
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)Parameter + 16, 1, 0) )
  {
    *((_DWORD *)Parameter + 22) |= 4u;
    *((_DWORD *)Parameter + 23) = GetCurrentThreadId();
    BackTraceHash = 0;
    RtlCaptureStackBackTrace(0, 8u, (PVOID *)Parameter + 12, &BackTraceHash);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), v2, v3, Parameter);
    }
    try
    {
      DefaultRepDriverClsId = 0;
      EnableAllPrivileges(1u);
      if ( !(unsigned int)CheckSecurity(17, 0) )
        DefaultRepDriverClsId = -2147217405;
      rclsid = 0;
      if ( DefaultRepDriverClsId >= 0 )
        DefaultRepDriverClsId = CWbemBackupRestore::GetDefaultRepDriverClsId(
                                  (CWbemBackupRestore *)0x80041003LL,
                                  &rclsid);
      v6 = 0;
      ppv = 0;
      if ( DefaultRepDriverClsId >= 0 )
      {
        DefaultRepDriverClsId = CoCreateInstance(&CLSID_IWmiCoreServices, 0, 1u, &IID__IWmiCoreServices, &ppv);
        v6 = ppv;
      }
      v33 = v6;
      v7 = 0;
      v30 = 0;
      if ( DefaultRepDriverClsId >= 0 )
      {
        DefaultRepDriverClsId = (*(__int64 (__fastcall **)(LPVOID, const OLECHAR *, _QWORD, _QWORD, _DWORD, GUID *, __int64 *))(*(_QWORD *)ppv + 32LL))(
                                  ppv,
                                  L"root",
                                  0,
                                  0,
                                  0,
                                  &IID_IWbemServices,
                                  &v30);
        v7 = v30;
      }
      v32 = v7;
      v8 = 0;
      v26 = 0;
      if ( DefaultRepDriverClsId >= 0 )
      {
        DefaultRepDriverClsId = CoCreateInstance(&rclsid, 0, 1u, &IID_IWmiDbController, &v26);
        v8 = v26;
      }
      v31 = v8;
      if ( DefaultRepDriverClsId < 0 )
        goto LABEL_70;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, v5, Parameter, v26);
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v26 + 8LL))(v26);
      _InterlockedExchange64((volatile __int64 *)Parameter + 7, (__int64)v26);
      if ( !*((_QWORD *)Parameter + 7) )
      {
        _InterlockedCompareExchange((volatile signed __int32 *)Parameter + 16, 0, 1);
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v26 + 16LL))(v26);
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, -2147217386);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v15, Parameter, -2147217386);
        }
        if ( v8 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
        v31 = 0;
        if ( v7 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        v32 = 0;
        if ( v6 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
        v33 = 0;
        return 2147749910LL;
      }
      DefaultRepDriverClsId = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v26 + 104LL))(v26);
      if ( DefaultRepDriverClsId < 0 )
      {
        v16 = *((_QWORD *)Parameter + 7);
        if ( v16 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        _InterlockedExchange64((volatile __int64 *)Parameter + 7, 0);
        goto LABEL_30;
      }
      phNewTimer = 0;
      if ( CreateTimerQueueTimer(
             &phNewTimer,
             0,
             CWbemBackupRestore::TimeOutCallback,
             Parameter,
             *((_DWORD *)Parameter + 12),
             0x7530u,
             0x20u) )
      {
        if ( v26 == *((LPVOID *)Parameter + 7) )
        {
          (*(void (__fastcall **)(PVOID))(*(_QWORD *)Parameter + 8LL))(Parameter);
          _InterlockedExchange64((volatile __int64 *)Parameter + 5, (__int64)phNewTimer);
LABEL_30:
          v10 = WPP_GLOBAL_Control;
          goto LABEL_31;
        }
        if ( DeleteTimerQueueTimer(0, phNewTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL) || GetLastError() == 997 )
          goto LABEL_30;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_20;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
        {
LABEL_31:
          if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 5u )
            WPP_SF_qqqD(
              v10[2],
              *((_QWORD *)Parameter + 7),
              v9,
              Parameter,
              *((_QWORD *)Parameter + 7),
              *((_QWORD *)Parameter + 5),
              DefaultRepDriverClsId);
LABEL_20:
          if ( DefaultRepDriverClsId >= 0 )
          {
LABEL_21:
            if ( v8 )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
            v31 = 0;
            if ( v7 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
            v32 = 0;
            if ( v6 )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
            v33 = 0;
            return (unsigned int)DefaultRepDriverClsId;
          }
LABEL_70:
          _InterlockedCompareExchange((volatile signed __int32 *)Parameter + 16, 0, 1);
          goto LABEL_21;
        }
        LastError = GetLastError();
        v19 = 27;
        Period = LastError;
        v20 = phNewTimer;
      }
      else
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_20;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
          goto LABEL_31;
        v21 = GetLastError();
        v19 = 28;
        Period = v21;
        v20 = (void *)*((_QWORD *)Parameter + 5);
      }
      WPP_SF_qqD(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, v18, Parameter, v20, Period);
      goto LABEL_30;
    }
    catch ( CX_MemoryException )
    {
      v22 = v34;
      _InterlockedCompareExchange(v34 + 16, 0, 1);
      v23 = GetMemLogObject();
      CMemoryLog::Write(v23, -2147217402);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, v24, v22, -2147217402);
      }
      return 2147749894LL;
    }
    return result;
  }
  v12 = GetMemLogObject();
  CMemoryLog::Write(v12, -2147217386);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v13, Parameter, -2147217386);
  }
  return 2147749910LL;
}

```

## disassembly

```asm
0x180007120  push    rbx
0x180007122  push    rsi
0x180007123  push    rdi
0x180007124  push    r13
0x180007126  push    r14
0x180007128  push    r15
0x18000712a  sub     rsp, 0B8h
0x180007131  mov     rax, cs:__security_cookie
0x180007138  xor     rax, rsp
0x18000713b  mov     [rsp+0E8h+var_48], rax
0x180007143  mov     rbx, rcx
0x180007146  mov     [rsp+0E8h+var_60], rcx
0x18000714e  xor     eax, eax
0x180007150  lea     r14d, [rax+1]
0x180007154  lock cmpxchg [rcx+40h], r14d
0x18000715a  jnz     loc_1800074BE
0x180007160  or      dword ptr [rcx+58h], 4
0x180007164  call    cs:__imp_GetCurrentThreadId
0x18000716a  mov     [rbx+5Ch], eax
0x18000716d  mov     [rsp+0E8h+BackTraceHash], 0
0x180007175  lea     r8, [rbx+60h]; BackTrace
0x180007179  lea     r9, [rsp+0E8h+BackTraceHash]; BackTraceHash
0x18000717e  lea     edx, [r14+7]; FramesToCapture
0x180007182  xor     ecx, ecx; FramesToSkip
0x180007184  call    cs:__imp_RtlCaptureStackBackTrace
0x18000718a  lea     r13, WPP_GLOBAL_Control
0x180007191  mov     rcx, cs:WPP_GLOBAL_Control
0x180007198  cmp     rcx, r13
0x18000719b  jnz     loc_180007513
0x1800071a1  xor     edi, edi
0x1800071a3  mov     [rsp+0E8h+var_A8], edi
0x1800071a7  mov     ecx, r14d
0x1800071aa  call    cs:__imp_?EnableAllPrivileges@@YAJK@Z; EnableAllPrivileges(ulong)
0x1800071b0  xor     edx, edx; void **
0x1800071b2  lea     ecx, [rdi+11h]; int
0x1800071b5  call    ?CheckSecurity@@YAHJPEAPEAX@Z; CheckSecurity(long,void * *)
0x1800071ba  mov     ecx, 80041003h; this
0x1800071bf  test    eax, eax
0x1800071c1  cmovz   edi, ecx
0x1800071c4  mov     [rsp+0E8h+var_A8], edi
0x1800071c8  xorps   xmm0, xmm0
0x1800071cb  movups  xmmword ptr [rsp+0E8h+rclsid.Data1], xmm0
0x1800071d3  test    edi, edi
0x1800071d5  jns     loc_180007538
0x1800071db  xor     esi, esi
0x1800071dd  mov     [rsp+0E8h+var_88], rsi
0x1800071e2  test    edi, edi
0x1800071e4  jns     loc_1800073B8
0x1800071ea  mov     [rsp+0E8h+var_68], rsi
0x1800071f2  xor     r15d, r15d
0x1800071f5  mov     [rsp+0E8h+var_80], r15
0x1800071fa  test    edi, edi
0x1800071fc  js      short loc_180007242
0x1800071fe  mov     rcx, [rsp+0E8h+var_88]
0x180007203  mov     rax, [rcx]
0x180007206  lea     rdx, [rsp+0E8h+var_80]
0x18000720b  mov     qword ptr [rsp+0E8h+Flags], rdx
0x180007210  lea     rdx, IID_IWbemServices
0x180007217  mov     qword ptr [rsp+0E8h+Period], rdx
0x18000721c  mov     dword ptr [rsp+0E8h+ppv], r15d
0x180007221  xor     r9d, r9d
0x180007224  xor     r8d, r8d
0x180007227  lea     rdx, psz; "root"
0x18000722e  mov     rax, [rax+20h]
0x180007232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007237  mov     edi, eax
0x180007239  mov     [rsp+0E8h+var_A8], eax
0x18000723d  mov     r15, [rsp+0E8h+var_80]
0x180007242  mov     [rsp+0E8h+var_70], r15
0x180007247  xor     r14d, r14d
0x18000724a  mov     [rsp+0E8h+var_A0], r14
0x18000724f  test    edi, edi
0x180007251  js      short loc_180007283
0x180007253  lea     rax, [rsp+0E8h+var_A0]
0x180007258  mov     [rsp+0E8h+ppv], rax; ppv
0x18000725d  lea     r9, IID_IWmiDbController; riid
0x180007264  xor     edx, edx; pUnkOuter
0x180007266  lea     r8d, [r14+1]; dwClsContext
0x18000726a  lea     rcx, [rsp+0E8h+rclsid]; rclsid
0x180007272  call    cs:__imp_CoCreateInstance
0x180007278  mov     edi, eax
0x18000727a  mov     [rsp+0E8h+var_A8], eax
0x18000727e  mov     r14, [rsp+0E8h+var_A0]
0x180007283  mov     [rsp+0E8h+var_78], r14
0x180007288  test    edi, edi
0x18000728a  js      loc_1800076BF
0x180007290  mov     rcx, cs:WPP_GLOBAL_Control
0x180007297  cmp     rcx, r13
0x18000729a  jnz     loc_180007550
0x1800072a0  mov     rcx, [rsp+0E8h+var_A0]
0x1800072a5  mov     rax, [rcx]
0x1800072a8  mov     rax, [rax+8]
0x1800072ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072b1  mov     rax, [rsp+0E8h+var_A0]
0x1800072b6  xchg    rax, [rbx+38h]
0x1800072ba  cmp     qword ptr [rbx+38h], 0
0x1800072bf  jz      loc_180007584
0x1800072c5  mov     rcx, [rsp+0E8h+var_A0]
0x1800072ca  mov     rax, [rcx]
0x1800072cd  mov     rax, [rax+68h]
0x1800072d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072d6  mov     edi, eax
0x1800072d8  mov     [rsp+0E8h+var_A8], eax
0x1800072dc  test    eax, eax
0x1800072de  js      loc_1800075F7
0x1800072e4  mov     [rsp+0E8h+phNewTimer], 0
0x1800072ed  mov     [rsp+0E8h+Flags], 20h ; ' '; Flags
0x1800072f5  mov     [rsp+0E8h+Period], 7530h; Period
0x1800072fd  mov     eax, [rbx+30h]
0x180007300  mov     dword ptr [rsp+0E8h+ppv], eax; DueTime
0x180007304  mov     r9, rbx; Parameter
0x180007307  lea     r8, ?TimeOutCallback@CWbemBackupRestore@@SAXPEAXE@Z; Callback
0x18000730e  xor     edx, edx; TimerQueue
0x180007310  lea     rcx, [rsp+0E8h+phNewTimer]; phNewTimer
0x180007315  call    cs:__imp_CreateTimerQueueTimer
0x18000731b  test    eax, eax
0x18000731d  jnz     loc_1800073EB
0x180007323  mov     rcx, cs:WPP_GLOBAL_Control
0x18000732a  cmp     rcx, r13
0x18000732d  jnz     loc_18000767B
0x180007333  test    edi, edi
0x180007335  js      loc_1800076BF
0x18000733b  test    r14, r14
0x18000733e  jz      short loc_18000734F
0x180007340  mov     rax, [r14]
0x180007343  mov     rcx, r14
0x180007346  mov     rax, [rax+10h]
0x18000734a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000734f  mov     [rsp+0E8h+var_78], 0
0x180007358  test    r15, r15
0x18000735b  jz      short loc_18000736C
0x18000735d  mov     rax, [r15]
0x180007360  mov     rcx, r15
0x180007363  mov     rax, [rax+10h]
0x180007367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000736c  mov     [rsp+0E8h+var_70], 0
0x180007375  test    rsi, rsi
0x180007378  jz      short loc_180007389
0x18000737a  mov     rax, [rsi]
0x18000737d  mov     rcx, rsi
0x180007380  mov     rax, [rax+10h]
0x180007384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007389  mov     [rsp+0E8h+var_68], 0
0x180007395  mov     eax, edi
0x180007397  mov     rcx, [rsp+0E8h+var_48]
0x18000739f  xor     rcx, rsp; StackCookie
0x1800073a2  call    __security_check_cookie
0x1800073a7  add     rsp, 0B8h
0x1800073ae  pop     r15
0x1800073b0  pop     r14
0x1800073b2  pop     r13
0x1800073b4  pop     rdi
0x1800073b5  pop     rsi
0x1800073b6  pop     rbx
0x1800073b7  retn
0x1800073b8  lea     rax, [rsp+0E8h+var_88]
0x1800073bd  mov     [rsp+0E8h+ppv], rax; ppv
0x1800073c2  lea     r9, IID__IWmiCoreServices; riid
0x1800073c9  mov     r8d, r14d; dwClsContext
0x1800073cc  xor     edx, edx; pUnkOuter
0x1800073ce  lea     rcx, CLSID_IWmiCoreServices; rclsid
0x1800073d5  call    cs:__imp_CoCreateInstance
0x1800073db  mov     edi, eax
0x1800073dd  mov     [rsp+0E8h+var_A8], eax
0x1800073e1  mov     rsi, [rsp+0E8h+var_88]
0x1800073e6  jmp     loc_1800071EA
0x1800073eb  mov     rax, [rbx+38h]
0x1800073ef  cmp     [rsp+0E8h+var_A0], rax
0x1800073f4  jnz     loc_180007617
0x1800073fa  mov     rax, [rbx]
0x1800073fd  mov     rcx, rbx
0x180007400  mov     rax, [rax+8]
0x180007404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007409  mov     rax, [rsp+0E8h+phNewTimer]
0x18000740e  xchg    rax, [rbx+28h]
0x180007412  mov     rcx, cs:WPP_GLOBAL_Control
0x180007419  cmp     rcx, r13
0x18000741c  jz      loc_180007333
0x180007422  test    byte ptr [rcx+1Ch], 1
0x180007426  jz      loc_180007333
0x18000742c  cmp     byte ptr [rcx+19h], 5
0x180007430  jb      loc_180007333
0x180007436  mov     [rsp+0E8h+Flags], edi
0x18000743a  mov     rdx, [rbx+28h]
0x18000743e  mov     qword ptr [rsp+0E8h+Period], rdx
0x180007443  mov     rdx, [rbx+38h]
0x180007447  mov     [rsp+0E8h+ppv], rdx
0x18000744c  mov     r9, rbx
0x18000744f  mov     rcx, [rcx+10h]
0x180007453  call    WPP_SF_qqqD
0x180007458  jmp     loc_180007333
0x18000745d  test    r14, r14
0x180007460  jz      short loc_180007471
0x180007462  mov     rax, [r14]
0x180007465  mov     rcx, r14
0x180007468  mov     rax, [rax+10h]
0x18000746c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007471  mov     [rsp+0E8h+var_78], 0
0x18000747a  test    r15, r15
0x18000747d  jz      short loc_18000748E
0x18000747f  mov     rax, [r15]
0x180007482  mov     rcx, r15
0x180007485  mov     rax, [rax+10h]
0x180007489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000748e  mov     [rsp+0E8h+var_70], 0
0x180007497  test    rsi, rsi
0x18000749a  jz      short loc_1800074AB
0x18000749c  mov     rax, [rsi]
0x18000749f  mov     rcx, rsi
0x1800074a2  mov     rax, [rax+10h]
0x1800074a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074ab  mov     [rsp+0E8h+var_68], 0
0x1800074b7  mov     eax, edi
0x1800074b9  jmp     loc_180007397
0x1800074be  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800074c4  mov     edi, 80041016h
0x1800074c9  mov     edx, edi
0x1800074cb  mov     rcx, rax
0x1800074ce  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800074d4  lea     r13, WPP_GLOBAL_Control
0x1800074db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800074e2  cmp     rcx, r13
0x1800074e5  jz      short loc_18000750C
0x1800074e7  test    [rcx+1Ch], r14b
0x1800074eb  jz      short loc_18000750C
0x1800074ed  cmp     byte ptr [rcx+19h], 2
0x1800074f1  jb      short loc_18000750C
0x1800074f3  mov     edx, 17h
0x1800074f8  mov     dword ptr [rsp+0E8h+ppv], 80041016h
0x180007500  mov     r9, rbx
0x180007503  mov     rcx, [rcx+10h]
0x180007507  call    WPP_SF_qD
0x18000750c  mov     eax, edi
0x18000750e  jmp     loc_180007397
0x180007513  test    [rcx+1Ch], r14b
0x180007517  jz      loc_1800071A1
0x18000751d  cmp     byte ptr [rcx+19h], 5
0x180007521  jb      loc_1800071A1
0x180007527  mov     r9, rbx
0x18000752a  mov     rcx, [rcx+10h]
0x18000752e  call    WPP_SF_q
0x180007533  jmp     loc_1800071A1
0x180007538  lea     rdx, [rsp+0E8h+rclsid]; struct _GUID *
0x180007540  call    ?GetDefaultRepDriverClsId@CWbemBackupRestore@@QEAAJAEAU_GUID@@@Z; CWbemBackupRestore::GetDefaultRepDriverClsId(_GUID &)
0x180007545  mov     edi, eax
0x180007547  mov     [rsp+0E8h+var_A8], eax
0x18000754b  jmp     loc_1800071DB
0x180007550  test    byte ptr [rcx+1Ch], 1
0x180007554  jz      loc_1800072A0
0x18000755a  cmp     byte ptr [rcx+19h], 5
0x18000755e  jb      loc_1800072A0
0x180007564  mov     edx, 19h
0x180007569  mov     rax, [rsp+0E8h+var_A0]
0x18000756e  mov     [rsp+0E8h+ppv], rax
0x180007573  mov     r9, rbx
0x180007576  mov     rcx, [rcx+10h]
0x18000757a  call    WPP_SF_qq
0x18000757f  jmp     loc_1800072A0
0x180007584  xor     ecx, ecx
0x180007586  lea     eax, [rcx+1]
0x180007589  lock cmpxchg [rbx+40h], ecx
0x18000758e  mov     rcx, [rsp+0E8h+var_A0]
0x180007593  mov     rax, [rcx]
0x180007596  mov     rax, [rax+10h]
0x18000759a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000759f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800075a5  mov     edi, 80041016h
0x1800075aa  mov     edx, edi
0x1800075ac  mov     rcx, rax
0x1800075af  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800075b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800075bc  cmp     rcx, r13
0x1800075bf  jz      loc_18000745D
0x1800075c5  test    byte ptr [rcx+1Ch], 1
0x1800075c9  jz      loc_18000745D
0x1800075cf  cmp     byte ptr [rcx+19h], 2
0x1800075d3  jb      loc_18000745D
0x1800075d9  mov     edx, 1Ah
0x1800075de  mov     dword ptr [rsp+0E8h+ppv], 80041016h
0x1800075e6  mov     r9, rbx
0x1800075e9  mov     rcx, [rcx+10h]
0x1800075ed  call    WPP_SF_qD
0x1800075f2  jmp     loc_18000745D
0x1800075f7  mov     rcx, [rbx+38h]
0x1800075fb  test    rcx, rcx
0x1800075fe  jz      short loc_18000760C
0x180007600  mov     rax, [rcx]
0x180007603  mov     rax, [rax+10h]
0x180007607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000760c  xor     eax, eax
0x18000760e  xchg    rax, [rbx+38h]
0x180007612  jmp     loc_180007412
0x180007617  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18000761b  mov     rdx, [rsp+0E8h+phNewTimer]; Timer
0x180007620  xor     ecx, ecx; TimerQueue
0x180007622  call    cs:__imp_DeleteTimerQueueTimer
0x180007628  test    eax, eax
0x18000762a  jnz     loc_180007412
0x180007630  call    cs:__imp_GetLastError
0x180007636  cmp     eax, 3E5h
  ... truncated ...
```
