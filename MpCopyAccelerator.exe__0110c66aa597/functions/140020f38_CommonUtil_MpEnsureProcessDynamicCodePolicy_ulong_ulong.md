# CommonUtil::MpEnsureProcessDynamicCodePolicy(ulong &,ulong &)

- ea: `0x140020f38`
- end: `0x14002109c`
- name: `?MpEnsureProcessDynamicCodePolicy@CommonUtil@@YAJAEAK0@Z`
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
- `0x140020f38`
- `0x140021c7c`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x140020f61`
- `KERNEL32!GetCurrentProcess` at `0x140020f61`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpEnsureProcessDynamicCodePolicy(CommonUtil *this, unsigned int *a2, unsigned int *a3)
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
                              (void *)2,
                              (__int64)&v10,
                              (void *)4);
  if ( ProcessMitigationPolicy >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_DDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        ((unsigned int)v10 >> 2) & 1,
        v10 & 1,
        ((unsigned int)v10 >> 1) & 1,
        ((unsigned int)v10 >> 2) & 1);
    ++*a2;
    if ( (v10 & 1) == 0 )
    {
      v10 |= 1u;
      ProcessMitigationPolicy = CommonUtil::UtilSetProcessMitigationPolicy((CommonUtil *)2, (__int64)&v10, (void *)4);
      if ( ProcessMitigationPolicy < 0 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          return (unsigned int)ProcessMitigationPolicy;
        v8 = 21;
        goto LABEL_17;
      }
      ++*(_DWORD *)this;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids);
    }
    return 0;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    return (unsigned int)ProcessMitigationPolicy;
  v8 = 18;
LABEL_17:
  WPP_SF_d(v7[2], v8, &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids, (unsigned int)ProcessMitigationPolicy);
  return (unsigned int)ProcessMitigationPolicy;
}

```

## disassembly

```asm
0x140020f38  mov     [rsp+arg_10], rbx
0x140020f3d  push    rbp
0x140020f3e  push    rsi
0x140020f3f  push    rdi
0x140020f40  sub     rsp, 40h
0x140020f44  mov     rax, cs:__security_cookie
0x140020f4b  xor     rax, rsp
0x140020f4e  mov     [rsp+58h+var_20], rax
0x140020f53  mov     rbp, rdx
0x140020f56  mov     rsi, rcx
0x140020f59  mov     [rsp+58h+var_28], 0
0x140020f61  call    cs:__imp_GetCurrentProcess
0x140020f67  mov     rcx, rax; this
0x140020f6a  mov     r9d, 4; void *
0x140020f70  lea     r8, [rsp+58h+var_28]; enum _PROCESS_MITIGATION_POLICY
0x140020f75  lea     edx, [r9-2]; void *
0x140020f79  call    ?UtilGetProcessMitigationPolicy@CommonUtil@@YAJPEAXW4_PROCESS_MITIGATION_POLICY@@0_K@Z; CommonUtil::UtilGetProcessMitigationPolicy(void *,_PROCESS_MITIGATION_POLICY,void *,unsigned __int64)
0x140020f7e  mov     edi, eax
0x140020f80  test    eax, eax
0x140020f82  jns     short loc_140020FAF
0x140020f84  lea     rbx, WPP_GLOBAL_Control
0x140020f8b  mov     rcx, cs:WPP_GLOBAL_Control
0x140020f92  cmp     rcx, rbx
0x140020f95  jz      loc_140021080
0x140020f9b  test    byte ptr [rcx+1Ch], 1
0x140020f9f  jz      loc_140021080
0x140020fa5  mov     edx, 12h
0x140020faa  jmp     loc_14002106D
0x140020faf  lea     rbx, WPP_GLOBAL_Control
0x140020fb6  mov     rcx, cs:WPP_GLOBAL_Control
0x140020fbd  cmp     rcx, rbx
0x140020fc0  jz      short loc_140020FFB
0x140020fc2  test    byte ptr [rcx+1Ch], 4
0x140020fc6  jz      short loc_140020FFB
0x140020fc8  mov     r9d, [rsp+58h+var_28]
0x140020fcd  mov     r8d, r9d
0x140020fd0  shr     r8d, 2
0x140020fd4  and     r8d, 1
0x140020fd8  mov     eax, r9d
0x140020fdb  shr     eax, 1
0x140020fdd  and     eax, 1
0x140020fe0  and     r9d, 1
0x140020fe4  mov     edx, 13h
0x140020fe9  mov     [rsp+58h+var_30], r8d
0x140020fee  mov     [rsp+58h+var_38], eax
0x140020ff2  mov     rcx, [rcx+10h]
0x140020ff6  call    WPP_SF_DDD
0x140020ffb  inc     dword ptr [rbp+0]
0x140020ffe  mov     eax, [rsp+58h+var_28]
0x140021002  test    al, 1
0x140021004  jz      short loc_14002100A
0x140021006  xor     eax, eax
0x140021008  jmp     short loc_140021082
0x14002100a  or      eax, 1
0x14002100d  mov     [rsp+58h+var_28], eax
0x140021011  mov     r8d, 4; void *
0x140021017  lea     rdx, [rsp+58h+var_28]; enum _PROCESS_MITIGATION_POLICY
0x14002101c  lea     ecx, [r8-2]; this
0x140021020  call    ?UtilSetProcessMitigationPolicy@CommonUtil@@YAJW4_PROCESS_MITIGATION_POLICY@@PEAX_K@Z; CommonUtil::UtilSetProcessMitigationPolicy(_PROCESS_MITIGATION_POLICY,void *,unsigned __int64)
0x140021025  mov     edi, eax
0x140021027  test    eax, eax
0x140021029  js      short loc_140021056
0x14002102b  inc     dword ptr [rsi]
0x14002102d  mov     rcx, cs:WPP_GLOBAL_Control
0x140021034  cmp     rcx, rbx
0x140021037  jz      short loc_140021006
0x140021039  test    byte ptr [rcx+1Ch], 4
0x14002103d  jz      short loc_140021006
0x14002103f  mov     edx, 14h
0x140021044  lea     r8, WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids
0x14002104b  mov     rcx, [rcx+10h]
0x14002104f  call    WPP_SF_
0x140021054  jmp     short loc_140021006
0x140021056  mov     rcx, cs:WPP_GLOBAL_Control
0x14002105d  cmp     rcx, rbx
0x140021060  jz      short loc_140021080
0x140021062  test    byte ptr [rcx+1Ch], 2
0x140021066  jz      short loc_140021080
0x140021068  mov     edx, 15h
0x14002106d  mov     r9d, edi
0x140021070  lea     r8, WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids
0x140021077  mov     rcx, [rcx+10h]
0x14002107b  call    WPP_SF_d
0x140021080  mov     eax, edi
0x140021082  mov     rcx, [rsp+58h+var_20]
0x140021087  xor     rcx, rsp; StackCookie
0x14002108a  call    __security_check_cookie
0x14002108f  mov     rbx, [rsp+58h+arg_10]
0x140021094  add     rsp, 40h
0x140021098  pop     rdi
0x140021099  pop     rsi
0x14002109a  pop     rbp
0x14002109b  retn
```
