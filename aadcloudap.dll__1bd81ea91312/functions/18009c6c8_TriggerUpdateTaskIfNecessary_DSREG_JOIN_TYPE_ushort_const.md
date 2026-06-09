# TriggerUpdateTaskIfNecessary(_DSREG_JOIN_TYPE,ushort const *)

- ea: `0x18009c6c8`
- end: `0x18009ca14`
- name: `?TriggerUpdateTaskIfNecessary@@YAJW4_DSREG_JOIN_TYPE@@PEBG@Z`
- size: `844`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x18000caa0`

## callees

- `0x180003c20`
- `0x1800793e8`
- `0x1800793f8`
- `0x180084f3c`
- `0x180085628`
- `0x18008aa28`
- `0x18008aa64`
- `0x18008aa9c`
- `0x18008ac1c`
- `0x18008ac90`
- `0x180095210`
- `0x180095e90`
- `0x1800986fc`
- `0x18009c6c8`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x18009c96a`
- `ntdll!RtlPublishWnfStateData` at `0x18009c96a`

## string_xrefs

- `0x18009c99f`: `%s: No join info returned. Nothing to update. Join type = %d, Tenant ID = %s.`
- `0x18009c907`: `%s: Less then 24 hours since last sync attempt for device ID "%s".`
- `0x18009c6f4`: `TriggerUpdateTaskIfNecessary`
- `0x18009c887`: `TriggerUpdateTaskIfNecessary`
- `0x18009c8b2`: `TriggerUpdateTaskIfNecessary`
- `0x18009c8cc`: `TriggerUpdateTaskIfNecessary`
- `0x18009c8e4`: `TriggerUpdateTaskIfNecessary`
- `0x18009c900`: `TriggerUpdateTaskIfNecessary`
- `0x18009c9c6`: `TriggerUpdateTaskIfNecessary`
- `0x18009c94a`: `%s: Device attribute value change detected. Sending notification to task...`
- `0x18009c88e`: `%s: Cannot check attribute %d (%s) for device ID "%s". DeviceUpdateController::IsAttributeUpdateNeeded failed with error code: 0x%08x.`
- `0x18009c8d6`: `%s: Attribute %d (%s) for device ID "%s" needs to be updated.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 TriggerUpdateTaskIfNecessary()
{
  unsigned int v0; // edi
  int v1; // r15d
  int v2; // r13d
  int JoinInfo; // eax
  int IsAttributeUpdateNeeded; // r14d
  time_t v5; // r12
  unsigned int v6; // esi
  __int64 v7; // rbx
  unsigned int i; // ebx
  __int64 AttributeName; // r9
  int v10; // ebx
  int v11; // eax
  __int64 v13; // [rsp+28h] [rbp-E0h]
  __int64 v14; // [rsp+30h] [rbp-D8h]
  void *Block; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v17; // [rsp+48h] [rbp-C0h]
  __int64 v18; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v19; // [rsp+58h] [rbp-B0h]
  void **v20; // [rsp+68h] [rbp-A0h] BYREF
  __int16 v21; // [rsp+70h] [rbp-98h]
  __int128 v22; // [rsp+D8h] [rbp-30h]
  __int128 v23; // [rsp+E8h] [rbp-20h]
  __int128 v24; // [rsp+F8h] [rbp-10h]

  Logger::TraceVerbose(L"%s started", L"TriggerUpdateTaskIfNecessary");
  v0 = 0;
  v1 = 0;
  v2 = 0;
  LODWORD(v16) = 0;
  v18 = 1;
  v19 = 0;
  Block = 0;
  v20 = &DeviceInfo::`vftable';
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v21 = 0;
  JoinInfo = DsrGetJoinInfoEx(2, &v18, &Block);
  IsAttributeUpdateNeeded = JoinInfo;
  if ( JoinInfo >= 0 )
  {
    if ( Block && *((_QWORD *)Block + 1) && *((_DWORD *)Block + 4) )
    {
      v5 = time(0);
      if ( v5 < 0 )
        Logger::TraceError(L"%s: Cannot get system time. time() returned -1.", L"TriggerUpdateTaskIfNecessary");
      v6 = 0;
      while ( !v2 )
      {
        if ( v6 >= *((_DWORD *)Block + 4) )
          goto LABEL_23;
        if ( v5 > 0 )
        {
          v7 = 336LL * v6;
          if ( difftime(v5, *(_QWORD *)(*((_QWORD *)Block + 1) + v7 + 280)) < 86400.0 )
          {
            Logger::TraceVerbose(
              L"%s: Less then 24 hours since last sync attempt for device ID \"%s\".",
              L"TriggerUpdateTaskIfNecessary",
              *(_QWORD *)(*((_QWORD *)Block + 1) + v7 + 16));
            goto LABEL_23;
          }
        }
        for ( i = 1; (int)i <= 3; ++i )
        {
          v17 = 336LL * v6;
          IsAttributeUpdateNeeded = DeviceInfo::IsAttributeUpdateNeeded(&v20, i, v17 + *((_QWORD *)Block + 1), &v16);
          AttributeName = GetAttributeName(i);
          v2 = v16;
          if ( IsAttributeUpdateNeeded >= 0 )
          {
            v13 = *(_QWORD *)(*((_QWORD *)Block + 1) + v17 + 16);
            if ( (_DWORD)v16 )
            {
              Logger::TraceInformation(
                L"%s: Attribute %d (%s) for device ID \"%s\" needs to be updated.",
                L"TriggerUpdateTaskIfNecessary",
                i,
                AttributeName,
                v13);
              break;
            }
            Logger::TraceVerbose(
              L"%s: Attribute %d (%s) for device ID \"%s\" is up to date.",
              L"TriggerUpdateTaskIfNecessary",
              i,
              AttributeName,
              v13);
          }
          else
          {
            LODWORD(v14) = IsAttributeUpdateNeeded;
            Logger::TraceError(
              L"%s: Cannot check attribute %d (%s) for device ID \"%s\". DeviceUpdateController::IsAttributeUpdateNeeded f"
               "ailed with error code: 0x%08x.",
              L"TriggerUpdateTaskIfNecessary",
              i,
              AttributeName,
              *(_QWORD *)(*((_QWORD *)Block + 1) + v17 + 16),
              v14);
            v0 = IsAttributeUpdateNeeded;
          }
        }
        ++v6;
      }
      v0 = 0;
      IsAttributeUpdateNeeded = 0;
      Logger::TraceVerbose(
        L"%s: Device attribute value change detected. Sending notification to task...",
        L"TriggerUpdateTaskIfNecessary");
      v11 = RtlPublishWnfStateData(WNF_AAD_DEVICE_ATTRIBUTES_UPDATE, 0, 0, 0, 0);
      v1 = v11;
      if ( v11 < 0 )
        Logger::TraceError(
          L"%s: %s failed with NTSTATUS: 0x%08x.",
          L"TriggerUpdateTaskIfNecessary",
          L"RtlPublishWnfStateData",
          (unsigned int)v11);
    }
    else
    {
      Logger::TraceVerbose(
        L"%s: No join info returned. Nothing to update. Join type = %d, Tenant ID = %s.",
        L"TriggerUpdateTaskIfNecessary",
        1,
        L"<NULL>");
    }
  }
  else
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"TriggerUpdateTaskIfNecessary",
      L"DsrGetJoinInfoEx",
      (unsigned int)JoinInfo);
  }
LABEL_23:
  v10 = v1 | 0x10000000;
  if ( v1 >= 0 )
    v10 = IsAttributeUpdateNeeded;
  if ( v10 < 0 )
  {
    v0 = v10;
    goto LABEL_34;
  }
  if ( (v0 & 0x80000000) != 0 )
  {
LABEL_34:
    Logger::WriteDeviceUpdateTaskTriggerFailureEvent(v0);
    goto LABEL_35;
  }
  if ( v2 )
    Logger::WriteDeviceUpdateTaskTriggerSuccessEvent();
  v0 = v10;
LABEL_35:
  DsrFreeJoinInfoEx(Block);
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"TriggerUpdateTaskIfNecessary", v0);
  v20 = &DeviceInfo::`vftable';
  DeviceInfo::Cleanup((DeviceInfo *)&v20);
  return v0;
}

```

## disassembly

```asm
0x18009c6c8  mov     rax, rsp
0x18009c6cb  push    rbp
0x18009c6cc  push    rbx
0x18009c6cd  push    rsi
0x18009c6ce  push    rdi
0x18009c6cf  push    r12
0x18009c6d1  push    r13
0x18009c6d3  push    r14
0x18009c6d5  push    r15
0x18009c6d7  lea     rbp, [rax-68h]
0x18009c6db  sub     rsp, 128h
0x18009c6e2  movaps  xmmword ptr [rax-58h], xmm6
0x18009c6e6  mov     rax, cs:__security_cookie
0x18009c6ed  xor     rax, rsp
0x18009c6f0  mov     [rbp+60h+var_60], rax
0x18009c6f4  lea     rbx, aTriggerupdatet; "TriggerUpdateTaskIfNecessary"
0x18009c6fb  mov     rdx, rbx
0x18009c6fe  lea     rcx, aSStarted; "%s started"
0x18009c705  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18009c70a  xor     edi, edi
0x18009c70c  xor     r15d, r15d
0x18009c70f  xor     r13d, r13d
0x18009c712  mov     dword ptr [rsp+160h+var_128], r13d
0x18009c717  lea     esi, [rdi+1]
0x18009c71a  mov     qword ptr [rsp+160h+var_118], rsi
0x18009c71f  xorps   xmm0, xmm0
0x18009c722  movdqu  [rsp+160h+var_118+8], xmm0
0x18009c728  mov     [rsp+160h+Block], rdi
0x18009c72d  lea     r12, ??_7DeviceInfo@@6B@; const DeviceInfo::`vftable'
0x18009c734  mov     [rsp+160h+var_100], r12
0x18009c739  movdqa  [rbp+60h+var_90], xmm0
0x18009c73e  xorps   xmm1, xmm1
0x18009c741  movdqa  [rbp+60h+var_80], xmm1
0x18009c746  movdqa  [rbp+60h+var_70], xmm0
0x18009c74b  xor     eax, eax
0x18009c74d  mov     [rsp+160h+var_F8], ax
0x18009c752  lea     r8, [rsp+160h+Block]
0x18009c757  lea     rdx, [rsp+160h+var_118]
0x18009c75c  lea     ecx, [rdi+2]
0x18009c75f  call    DsrGetJoinInfoEx
0x18009c764  mov     r14d, eax
0x18009c767  test    eax, eax
0x18009c769  jns     short loc_18009C789
0x18009c76b  mov     r9d, eax
0x18009c76e  lea     r8, aDsrgetjoininfo; "DsrGetJoinInfoEx"
0x18009c775  mov     rdx, rbx
0x18009c778  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18009c77f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009c784  jmp     loc_18009C91A
0x18009c789  mov     rax, [rsp+160h+Block]
0x18009c78e  test    rax, rax
0x18009c791  jz      loc_18009C992
0x18009c797  cmp     qword ptr [rax+8], 0
0x18009c79c  jz      loc_18009C992
0x18009c7a2  cmp     dword ptr [rax+10h], 0
0x18009c7a6  jz      loc_18009C992
0x18009c7ac  xor     ecx, ecx; Time
0x18009c7ae  call    time
0x18009c7b3  mov     r12, rax
0x18009c7b6  test    rax, rax
0x18009c7b9  jns     short loc_18009C7CA
0x18009c7bb  mov     rdx, rbx
0x18009c7be  lea     rcx, aSCannotGetSyst; "%s: Cannot get system time. time() retu"...
0x18009c7c5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009c7ca  xor     esi, esi
0x18009c7cc  movsd   xmm6, cs:__real@40f5180000000000
0x18009c7d4  test    r13d, r13d
0x18009c7d7  jnz     loc_18009C942
0x18009c7dd  mov     rdx, [rsp+160h+Block]
0x18009c7e2  cmp     esi, [rdx+10h]
0x18009c7e5  jnb     loc_18009C913
0x18009c7eb  test    r12, r12
0x18009c7ee  jle     short loc_18009C817
0x18009c7f0  mov     eax, esi
0x18009c7f2  imul    rbx, rax, 150h
0x18009c7f9  mov     rdx, [rdx+8]
0x18009c7fd  mov     rdx, [rdx+rbx+118h]; Time2
0x18009c805  mov     rcx, r12; Time1
0x18009c808  call    difftime
0x18009c80d  comisd  xmm6, xmm0
0x18009c811  ja      loc_18009C8F2
0x18009c817  mov     ebx, 1
0x18009c81c  cmp     ebx, 3
0x18009c81f  jg      loc_18009C8E4
0x18009c825  mov     eax, esi
0x18009c827  imul    rdx, rax, 150h
0x18009c82e  mov     [rsp+160h+var_120], rdx
0x18009c833  mov     rax, [rsp+160h+Block]
0x18009c838  mov     r8, [rax+8]
0x18009c83c  add     r8, rdx
0x18009c83f  lea     r9, [rsp+160h+var_128]
0x18009c844  mov     edx, ebx
0x18009c846  lea     rcx, [rsp+160h+var_100]
0x18009c84b  call    ?IsAttributeUpdateNeeded@DeviceInfo@@QEAAJW4_DSREG_DEVICE_ATTRIBUTES@@PEAU_DSREG_ACCOUNT_INFO_2@@PEAH@Z; DeviceInfo::IsAttributeUpdateNeeded(_DSREG_DEVICE_ATTRIBUTES,_DSREG_ACCOUNT_INFO_2 *,int *)
0x18009c850  mov     r14d, eax
0x18009c853  mov     ecx, ebx
0x18009c855  call    GetAttributeName
0x18009c85a  mov     r9, rax
0x18009c85d  mov     r13d, dword ptr [rsp+160h+var_128]
0x18009c862  mov     rax, [rsp+160h+Block]
0x18009c867  mov     rdx, [rsp+160h+var_120]
0x18009c86c  mov     r8d, ebx
0x18009c86f  test    r14d, r14d
0x18009c872  jns     short loc_18009C89F
0x18009c874  mov     rax, [rax+8]
0x18009c878  mov     dword ptr [rsp+160h+var_138], r14d
0x18009c87d  mov     rax, [rax+rdx+10h]
0x18009c882  mov     [rsp+160h+var_140], rax
0x18009c887  lea     rdx, aTriggerupdatet; "TriggerUpdateTaskIfNecessary"
0x18009c88e  lea     rcx, aSCannotCheckAt; "%s: Cannot check attribute %d (%s) for "...
0x18009c895  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009c89a  mov     edi, r14d
0x18009c89d  jmp     short loc_18009C8C5
0x18009c89f  mov     rcx, [rax+8]
0x18009c8a3  mov     rax, [rcx+rdx+10h]
0x18009c8a8  mov     [rsp+160h+var_140], rax
0x18009c8ad  test    r13d, r13d
0x18009c8b0  jnz     short loc_18009C8CC
0x18009c8b2  lea     rdx, aTriggerupdatet; "TriggerUpdateTaskIfNecessary"
0x18009c8b9  lea     rcx, aSAttributeDSFo; "%s: Attribute %d (%s) for device ID \"%"...
0x18009c8c0  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18009c8c5  inc     ebx
0x18009c8c7  jmp     loc_18009C81C
0x18009c8cc  lea     rbx, aTriggerupdatet; "TriggerUpdateTaskIfNecessary"
0x18009c8d3  mov     rdx, rbx
0x18009c8d6  lea     rcx, aSAttributeDSFo_0; "%s: Attribute %d (%s) for device ID \"%"...
0x18009c8dd  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18009c8e2  jmp     short loc_18009C8EB
0x18009c8e4  lea     rbx, aTriggerupdatet; "TriggerUpdateTaskIfNecessary"
0x18009c8eb  inc     esi
0x18009c8ed  jmp     loc_18009C7D4
0x18009c8f2  mov     rax, [rsp+160h+Block]
0x18009c8f7  mov     r8, [rax+8]
0x18009c8fb  mov     r8, [r8+rbx+10h]
0x18009c900  lea     rdx, aTriggerupdatet; "TriggerUpdateTaskIfNecessary"
0x18009c907  lea     rcx, aSLessThen24Hou; "%s: Less then 24 hours since last sync "...
0x18009c90e  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18009c913  lea     r12, ??_7DeviceInfo@@6B@; const DeviceInfo::`vftable'
0x18009c91a  mov     ebx, r15d
0x18009c91d  bts     ebx, 1Ch
0x18009c921  test    r15d, r15d
0x18009c924  cmovns  ebx, r14d
0x18009c928  test    ebx, ebx
0x18009c92a  js      loc_18009C9B0
0x18009c930  test    edi, edi
0x18009c932  js      short loc_18009C9B2
0x18009c934  test    r13d, r13d
0x18009c937  jz      short loc_18009C93E
0x18009c939  call    ?WriteDeviceUpdateTaskTriggerSuccessEvent@Logger@@SAJW4_DSREG_JOIN_TYPE@@PEBG@Z; Logger::WriteDeviceUpdateTaskTriggerSuccessEvent(_DSREG_JOIN_TYPE,ushort const *)
0x18009c93e  mov     edi, ebx
0x18009c940  jmp     short loc_18009C9B9
0x18009c942  xor     edi, edi
0x18009c944  xor     r14d, r14d
0x18009c947  mov     rdx, rbx
0x18009c94a  lea     rcx, aSDeviceAttribu; "%s: Device attribute value change detec"...
0x18009c951  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18009c956  mov     [rsp+160h+var_140], rdi
0x18009c95b  xor     r9d, r9d
0x18009c95e  xor     r8d, r8d
0x18009c961  xor     edx, edx
0x18009c963  mov     rcx, cs:WNF_AAD_DEVICE_ATTRIBUTES_UPDATE
0x18009c96a  call    cs:__imp_RtlPublishWnfStateData
0x18009c970  mov     r15d, eax
0x18009c973  test    eax, eax
0x18009c975  jns     short loc_18009C913
0x18009c977  mov     r9d, eax
0x18009c97a  lea     r8, aRtlpublishwnfs; "RtlPublishWnfStateData"
0x18009c981  mov     rdx, rbx
0x18009c984  lea     rcx, aSSFailedWithNt; "%s: %s failed with NTSTATUS: 0x%08x."
0x18009c98b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009c990  jmp     short loc_18009C913
0x18009c992  lea     r9, aNull_2; "<NULL>"
0x18009c999  mov     r8d, esi
0x18009c99c  mov     rdx, rbx
0x18009c99f  lea     rcx, aSNoJoinInfoRet; "%s: No join info returned. Nothing to u"...
0x18009c9a6  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18009c9ab  jmp     loc_18009C91A
0x18009c9b0  mov     edi, ebx
0x18009c9b2  mov     ecx, edi
0x18009c9b4  call    ?WriteDeviceUpdateTaskTriggerFailureEvent@Logger@@SAJJW4_DSREG_JOIN_TYPE@@PEBG@Z; Logger::WriteDeviceUpdateTaskTriggerFailureEvent(long,_DSREG_JOIN_TYPE,ushort const *)
0x18009c9b9  mov     rcx, [rsp+160h+Block]; Block
0x18009c9be  call    DsrFreeJoinInfoEx
0x18009c9c3  mov     r8d, edi
0x18009c9c6  lea     rdx, aTriggerupdatet; "TriggerUpdateTaskIfNecessary"
0x18009c9cd  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18009c9d4  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18009c9d9  nop
0x18009c9da  mov     [rsp+160h+var_100], r12
0x18009c9df  lea     rcx, [rsp+160h+var_100]; this
0x18009c9e4  call    ?Cleanup@DeviceInfo@@UEAAXXZ; DeviceInfo::Cleanup(void)
0x18009c9e9  nop
0x18009c9ea  mov     eax, edi
0x18009c9ec  mov     rcx, [rbp+60h+var_60]
0x18009c9f0  xor     rcx, rsp; StackCookie
0x18009c9f3  call    __security_check_cookie
0x18009c9f8  movaps  xmm6, [rsp+160h+var_58+8]
0x18009ca00  add     rsp, 128h
0x18009ca07  pop     r15
0x18009ca09  pop     r14
0x18009ca0b  pop     r13
0x18009ca0d  pop     r12
0x18009ca0f  pop     rdi
0x18009ca10  pop     rsi
0x18009ca11  pop     rbx
0x18009ca12  pop     rbp
0x18009ca13  retn
```
