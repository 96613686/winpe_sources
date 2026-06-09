# CommonUtil::MpEnsureProcessSignaturePolicy(ulong &,ulong &)

- ea: `0x140021788`
- end: `0x140021963`
- name: `?MpEnsureProcessSignaturePolicy@CommonUtil@@YAJAEAK0@Z`
- size: `475`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140021424`

## callees

- `0x14000496c`
- `0x1400049e4`
- `0x140004adc`
- `0x140005c20`
- `0x14001da4c`
- `0x14001da70`
- `0x140021788`
- `0x140021c7c`
- `0x140024c40`

## import_xrefs

- `MpClient!MpClientUtilExportFunctions` at `0x1400217bc`
- `MpClient!MpClientUtilExportFunctions` at `0x1400217bc`
- `KERNEL32!GetCurrentProcess` at `0x14002181b`
- `KERNEL32!GetCurrentProcess` at `0x14002181b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CommonUtil::MpEnsureProcessSignaturePolicy(CommonUtil *this, unsigned int *a2, unsigned int *a3)
{
  int IsWindowsBlueOrGreater; // ebx
  __int64 v6; // rax
  int v7; // ebp
  CommonUtil *CurrentProcess; // rax
  int ProcessMitigationPolicy; // ebx
  unsigned __int64 v10; // r9
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  unsigned __int64 v16; // [rsp+20h] [rbp-48h]
  enum _PROCESS_MITIGATION_POLICY v17; // [rsp+30h] [rbp-38h] BYREF
  int v18; // [rsp+34h] [rbp-34h] BYREF

  IsWindowsBlueOrGreater = MpIsWindowsBlueOrGreater(this, a2, a3);
  v18 = 0;
  v6 = MpClientUtilExportFunctions();
  v7 = 0;
  if ( (*(int (__fastcall **)(int *))(v6 + 152))(&v18) >= 0 )
    v7 = v18;
  if ( IsWindowsBlueOrGreater
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids);
  }
  v17 = ProcessDEPPolicy;
  CurrentProcess = (CommonUtil *)GetCurrentProcess();
  ProcessMitigationPolicy = CommonUtil::UtilGetProcessMitigationPolicy(
                              CurrentProcess,
                              (void *)8,
                              (enum _PROCESS_MITIGATION_POLICY)&v17,
                              (void *)4,
                              v16);
  if ( ProcessMitigationPolicy >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_DDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        ((unsigned int)v17 >> 2) & 1,
        v17 & 1,
        ((unsigned int)v17 >> 1) & 1,
        ((unsigned int)v17 >> 2) & 1);
    ++*a2;
    if ( v7 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        return 0;
      v14 = 41;
    }
    else
    {
      if ( (v17 & 1) != 0 )
        return 0;
      v17 |= 1u;
      ProcessMitigationPolicy = CommonUtil::UtilSetProcessMitigationPolicy(
                                  (CommonUtil *)8,
                                  (enum _PROCESS_MITIGATION_POLICY)&v17,
                                  (void *)4,
                                  v10);
      if ( ProcessMitigationPolicy < 0 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          return (unsigned int)ProcessMitigationPolicy;
        v12 = 43;
        goto LABEL_28;
      }
      ++*(_DWORD *)this;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        return 0;
      v14 = 42;
    }
    WPP_SF_(v13[2], v14, &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids);
    return 0;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    return (unsigned int)ProcessMitigationPolicy;
  v12 = 39;
LABEL_28:
  WPP_SF_d(v11[2], v12, &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids, (unsigned int)ProcessMitigationPolicy);
  return (unsigned int)ProcessMitigationPolicy;
}

```

## disassembly

```asm
0x140021788  mov     [rsp+arg_10], rbx
0x14002178d  push    rbp
0x14002178e  push    rsi
0x14002178f  push    rdi
0x140021790  push    r14
0x140021792  push    r15
0x140021794  sub     rsp, 40h
0x140021798  mov     rax, cs:__security_cookie
0x14002179f  xor     rax, rsp
0x1400217a2  mov     [rsp+68h+var_30], rax
0x1400217a7  mov     rsi, rdx
0x1400217aa  mov     rdi, rcx
0x1400217ad  call    MpIsWindowsBlueOrGreater
0x1400217b2  mov     ebx, eax
0x1400217b4  mov     [rsp+68h+var_34], 0
0x1400217bc  call    cs:__imp_MpClientUtilExportFunctions
0x1400217c2  lea     rcx, [rsp+68h+var_34]
0x1400217c7  mov     rax, [rax+98h]
0x1400217ce  call    cs:__guard_dispatch_icall_fptr
0x1400217d4  nop
0x1400217d5  xor     ebp, ebp
0x1400217d7  test    eax, eax
0x1400217d9  cmovns  ebp, [rsp+68h+var_34]
0x1400217de  lea     r15, WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids
0x1400217e5  lea     r14, WPP_GLOBAL_Control
0x1400217ec  test    ebx, ebx
0x1400217ee  jz      short loc_140021813
0x1400217f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400217f7  cmp     rcx, r14
0x1400217fa  jz      short loc_140021813
0x1400217fc  test    byte ptr [rcx+1Ch], 4
0x140021800  jz      short loc_140021813
0x140021802  mov     edx, 26h ; '&'
0x140021807  mov     r8, r15
0x14002180a  mov     rcx, [rcx+10h]
0x14002180e  call    WPP_SF_
0x140021813  mov     [rsp+68h+var_38], 0
0x14002181b  call    cs:__imp_GetCurrentProcess
0x140021821  mov     rcx, rax; this
0x140021824  mov     r9d, 4; void *
0x14002182a  lea     r8, [rsp+68h+var_38]; enum _PROCESS_MITIGATION_POLICY
0x14002182f  lea     edx, [r9+4]; void *
0x140021833  call    ?UtilGetProcessMitigationPolicy@CommonUtil@@YAJPEAXW4_PROCESS_MITIGATION_POLICY@@0_K@Z; CommonUtil::UtilGetProcessMitigationPolicy(void *,_PROCESS_MITIGATION_POLICY,void *,unsigned __int64)
0x140021838  mov     ebx, eax
0x14002183a  test    eax, eax
0x14002183c  jns     short loc_140021862
0x14002183e  mov     rcx, cs:WPP_GLOBAL_Control
0x140021845  cmp     rcx, r14
0x140021848  jz      loc_140021940
0x14002184e  test    byte ptr [rcx+1Ch], 1
0x140021852  jz      loc_140021940
0x140021858  mov     edx, 27h ; '''
0x14002185d  jmp     loc_140021931
0x140021862  mov     rcx, cs:WPP_GLOBAL_Control
0x140021869  cmp     rcx, r14
0x14002186c  jz      short loc_1400218A7
0x14002186e  test    byte ptr [rcx+1Ch], 4
0x140021872  jz      short loc_1400218A7
0x140021874  mov     r9d, [rsp+68h+var_38]
0x140021879  mov     r8d, r9d
0x14002187c  shr     r8d, 2
0x140021880  and     r8d, 1
0x140021884  mov     eax, r9d
0x140021887  shr     eax, 1
0x140021889  and     eax, 1
0x14002188c  and     r9d, 1
0x140021890  mov     edx, 28h ; '('
0x140021895  mov     [rsp+68h+var_40], r8d
0x14002189a  mov     dword ptr [rsp+68h+var_48], eax
0x14002189e  mov     rcx, [rcx+10h]
0x1400218a2  call    WPP_SF_DDD
0x1400218a7  inc     dword ptr [rsi]
0x1400218a9  test    ebp, ebp
0x1400218ab  jz      short loc_1400218D2
0x1400218ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400218b4  cmp     rcx, r14
0x1400218b7  jz      short loc_1400218DA
0x1400218b9  test    byte ptr [rcx+1Ch], 2
0x1400218bd  jz      short loc_1400218DA
0x1400218bf  mov     edx, 29h ; ')'
0x1400218c4  mov     r8, r15
0x1400218c7  mov     rcx, [rcx+10h]
0x1400218cb  call    WPP_SF_
0x1400218d0  jmp     short loc_1400218DA
0x1400218d2  mov     eax, [rsp+68h+var_38]
0x1400218d6  test    al, 1
0x1400218d8  jz      short loc_1400218DE
0x1400218da  xor     eax, eax
0x1400218dc  jmp     short loc_140021942
0x1400218de  or      eax, 1
0x1400218e1  mov     [rsp+68h+var_38], eax
0x1400218e5  mov     r8d, 4; void *
0x1400218eb  lea     rdx, [rsp+68h+var_38]; enum _PROCESS_MITIGATION_POLICY
0x1400218f0  lea     ecx, [r8+4]; this
0x1400218f4  call    ?UtilSetProcessMitigationPolicy@CommonUtil@@YAJW4_PROCESS_MITIGATION_POLICY@@PEAX_K@Z; CommonUtil::UtilSetProcessMitigationPolicy(_PROCESS_MITIGATION_POLICY,void *,unsigned __int64)
0x1400218f9  mov     ebx, eax
0x1400218fb  test    eax, eax
0x1400218fd  js      short loc_14002191A
0x1400218ff  inc     dword ptr [rdi]
0x140021901  mov     rcx, cs:WPP_GLOBAL_Control
0x140021908  cmp     rcx, r14
0x14002190b  jz      short loc_1400218DA
0x14002190d  test    byte ptr [rcx+1Ch], 2
0x140021911  jz      short loc_1400218DA
0x140021913  mov     edx, 2Ah ; '*'
0x140021918  jmp     short loc_1400218C4
0x14002191a  mov     rcx, cs:WPP_GLOBAL_Control
0x140021921  cmp     rcx, r14
0x140021924  jz      short loc_140021940
0x140021926  test    byte ptr [rcx+1Ch], 2
0x14002192a  jz      short loc_140021940
0x14002192c  mov     edx, 2Bh ; '+'
0x140021931  mov     r9d, ebx
0x140021934  mov     r8, r15
0x140021937  mov     rcx, [rcx+10h]
0x14002193b  call    WPP_SF_d
0x140021940  mov     eax, ebx
0x140021942  mov     rcx, [rsp+68h+var_30]
0x140021947  xor     rcx, rsp; StackCookie
0x14002194a  call    __security_check_cookie
0x14002194f  mov     rbx, [rsp+68h+arg_10]
0x140021957  add     rsp, 40h
0x14002195b  pop     r15
0x14002195d  pop     r14
0x14002195f  pop     rdi
0x140021960  pop     rsi
0x140021961  pop     rbp
0x140021962  retn
```
