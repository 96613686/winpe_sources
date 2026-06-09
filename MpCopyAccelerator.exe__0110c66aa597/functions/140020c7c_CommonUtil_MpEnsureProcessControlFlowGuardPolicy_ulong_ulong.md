# CommonUtil::MpEnsureProcessControlFlowGuardPolicy(ulong &,ulong &)

- ea: `0x140020c7c`
- end: `0x140020de0`
- name: `?MpEnsureProcessControlFlowGuardPolicy@CommonUtil@@YAJAEAK0@Z`
- size: `356`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140021424`

## callees

- `0x14000496c`
- `0x1400049e4`
- `0x140005c20`
- `0x14001da4c`
- `0x14001da70`
- `0x140020c7c`
- `0x140021c7c`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x140020ca5`
- `KERNEL32!GetCurrentProcess` at `0x140020ca5`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpEnsureProcessControlFlowGuardPolicy(
        CommonUtil *this,
        unsigned int *a2,
        unsigned int *a3)
{
  CommonUtil *CurrentProcess; // rax
  int ProcessMitigationPolicy; // edi
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  enum _PROCESS_MITIGATION_POLICY v10; // [rsp+30h] [rbp-28h] BYREF

  v10 = ProcessDEPPolicy;
  CurrentProcess = (CommonUtil *)GetCurrentProcess();
  ProcessMitigationPolicy = CommonUtil::UtilGetProcessMitigationPolicy(
                              CurrentProcess,
                              (void *)7,
                              (__int64)&v10,
                              (void *)4);
  if ( ProcessMitigationPolicy >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_DDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        ((unsigned int)v10 >> 2) & 1,
        v10 & 1,
        ((unsigned int)v10 >> 1) & 1,
        ((unsigned int)v10 >> 2) & 1);
    ++*a2;
    if ( (v10 & 1) == 0 )
    {
      v10 |= 1u;
      ProcessMitigationPolicy = CommonUtil::UtilSetProcessMitigationPolicy((CommonUtil *)7, (__int64)&v10, (void *)4);
      if ( ProcessMitigationPolicy < 0 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          return (unsigned int)ProcessMitigationPolicy;
        v8 = 37;
        goto LABEL_17;
      }
      ++*(_DWORD *)this;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids);
    }
    return 0;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    return (unsigned int)ProcessMitigationPolicy;
  v8 = 34;
LABEL_17:
  WPP_SF_d(v7[2], v8, &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids, (unsigned int)ProcessMitigationPolicy);
  return (unsigned int)ProcessMitigationPolicy;
}

```

## disassembly

```asm
0x140020c7c  mov     [rsp+arg_10], rbx
0x140020c81  push    rbp
0x140020c82  push    rsi
0x140020c83  push    rdi
0x140020c84  sub     rsp, 40h
0x140020c88  mov     rax, cs:__security_cookie
0x140020c8f  xor     rax, rsp
0x140020c92  mov     [rsp+58h+var_20], rax
0x140020c97  mov     rbp, rdx
0x140020c9a  mov     rsi, rcx
0x140020c9d  mov     [rsp+58h+var_28], 0
0x140020ca5  call    cs:__imp_GetCurrentProcess
0x140020cab  mov     rcx, rax; this
0x140020cae  mov     r9d, 4; void *
0x140020cb4  lea     r8, [rsp+58h+var_28]; enum _PROCESS_MITIGATION_POLICY
0x140020cb9  lea     edx, [r9+3]; void *
0x140020cbd  call    ?UtilGetProcessMitigationPolicy@CommonUtil@@YAJPEAXW4_PROCESS_MITIGATION_POLICY@@0_K@Z; CommonUtil::UtilGetProcessMitigationPolicy(void *,_PROCESS_MITIGATION_POLICY,void *,unsigned __int64)
0x140020cc2  mov     edi, eax
0x140020cc4  test    eax, eax
0x140020cc6  jns     short loc_140020CF3
0x140020cc8  lea     rbx, WPP_GLOBAL_Control
0x140020ccf  mov     rcx, cs:WPP_GLOBAL_Control
0x140020cd6  cmp     rcx, rbx
0x140020cd9  jz      loc_140020DC4
0x140020cdf  test    byte ptr [rcx+1Ch], 1
0x140020ce3  jz      loc_140020DC4
0x140020ce9  mov     edx, 22h ; '"'
0x140020cee  jmp     loc_140020DB1
0x140020cf3  lea     rbx, WPP_GLOBAL_Control
0x140020cfa  mov     rcx, cs:WPP_GLOBAL_Control
0x140020d01  cmp     rcx, rbx
0x140020d04  jz      short loc_140020D3F
0x140020d06  test    byte ptr [rcx+1Ch], 4
0x140020d0a  jz      short loc_140020D3F
0x140020d0c  mov     r9d, [rsp+58h+var_28]
0x140020d11  mov     r8d, r9d
0x140020d14  shr     r8d, 2
0x140020d18  and     r8d, 1
0x140020d1c  mov     eax, r9d
0x140020d1f  shr     eax, 1
0x140020d21  and     eax, 1
0x140020d24  and     r9d, 1
0x140020d28  mov     edx, 23h ; '#'
0x140020d2d  mov     [rsp+58h+var_30], r8d
0x140020d32  mov     [rsp+58h+var_38], eax
0x140020d36  mov     rcx, [rcx+10h]
0x140020d3a  call    WPP_SF_DDD
0x140020d3f  inc     dword ptr [rbp+0]
0x140020d42  mov     eax, [rsp+58h+var_28]
0x140020d46  test    al, 1
0x140020d48  jz      short loc_140020D4E
0x140020d4a  xor     eax, eax
0x140020d4c  jmp     short loc_140020DC6
0x140020d4e  or      eax, 1
0x140020d51  mov     [rsp+58h+var_28], eax
0x140020d55  mov     r8d, 4; void *
0x140020d5b  lea     rdx, [rsp+58h+var_28]; enum _PROCESS_MITIGATION_POLICY
0x140020d60  lea     ecx, [r8+3]; this
0x140020d64  call    ?UtilSetProcessMitigationPolicy@CommonUtil@@YAJW4_PROCESS_MITIGATION_POLICY@@PEAX_K@Z; CommonUtil::UtilSetProcessMitigationPolicy(_PROCESS_MITIGATION_POLICY,void *,unsigned __int64)
0x140020d69  mov     edi, eax
0x140020d6b  test    eax, eax
0x140020d6d  js      short loc_140020D9A
0x140020d6f  inc     dword ptr [rsi]
0x140020d71  mov     rcx, cs:WPP_GLOBAL_Control
0x140020d78  cmp     rcx, rbx
0x140020d7b  jz      short loc_140020D4A
0x140020d7d  test    byte ptr [rcx+1Ch], 4
0x140020d81  jz      short loc_140020D4A
0x140020d83  mov     edx, 24h ; '$'
0x140020d88  lea     r8, WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids
0x140020d8f  mov     rcx, [rcx+10h]
0x140020d93  call    WPP_SF_
0x140020d98  jmp     short loc_140020D4A
0x140020d9a  mov     rcx, cs:WPP_GLOBAL_Control
0x140020da1  cmp     rcx, rbx
0x140020da4  jz      short loc_140020DC4
0x140020da6  test    byte ptr [rcx+1Ch], 2
0x140020daa  jz      short loc_140020DC4
0x140020dac  mov     edx, 25h ; '%'
0x140020db1  mov     r9d, edi
0x140020db4  lea     r8, WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids
0x140020dbb  mov     rcx, [rcx+10h]
0x140020dbf  call    WPP_SF_d
0x140020dc4  mov     eax, edi
0x140020dc6  mov     rcx, [rsp+58h+var_20]
0x140020dcb  xor     rcx, rsp; StackCookie
0x140020dce  call    __security_check_cookie
0x140020dd3  mov     rbx, [rsp+58h+arg_10]
0x140020dd8  add     rsp, 40h
0x140020ddc  pop     rdi
0x140020ddd  pop     rsi
0x140020dde  pop     rbp
0x140020ddf  retn
```
