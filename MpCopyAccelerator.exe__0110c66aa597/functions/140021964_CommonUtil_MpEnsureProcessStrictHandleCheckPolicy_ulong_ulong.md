# CommonUtil::MpEnsureProcessStrictHandleCheckPolicy(ulong &,ulong &)

- ea: `0x140021964`
- end: `0x140021abc`
- name: `?MpEnsureProcessStrictHandleCheckPolicy@CommonUtil@@YAJAEAK0@Z`
- size: `344`
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
- `0x140021964`
- `0x140021c14`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x14002198d`
- `KERNEL32!GetCurrentProcess` at `0x14002198d`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpEnsureProcessStrictHandleCheckPolicy(
        CommonUtil *this,
        unsigned int *a2,
        unsigned int *a3)
{
  CommonUtil *CurrentProcess; // rax
  int ProcessMitigationPolicy; // edi
  __int64 v7; // r8
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  enum _PROCESS_MITIGATION_POLICY v11; // [rsp+30h] [rbp-28h] BYREF

  v11 = ProcessDEPPolicy;
  CurrentProcess = (CommonUtil *)GetCurrentProcess();
  ProcessMitigationPolicy = CommonUtil::UtilGetProcessMitigationPolicy(
                              CurrentProcess,
                              (void *)3,
                              (__int64)&v11,
                              (void *)4);
  if ( ProcessMitigationPolicy >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v7, v11 & 1, ((unsigned int)v11 >> 1) & 1);
    ++*a2;
    if ( (v11 & 1) == 0 || (v11 & 2) == 0 )
    {
      v11 |= 3u;
      ProcessMitigationPolicy = CommonUtil::UtilSetProcessMitigationPolicy((CommonUtil *)3, (__int64)&v11, (void *)4);
      if ( ProcessMitigationPolicy < 0 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          return (unsigned int)ProcessMitigationPolicy;
        v9 = 25;
        goto LABEL_18;
      }
      ++*(_DWORD *)this;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids);
    }
    return 0;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    return (unsigned int)ProcessMitigationPolicy;
  v9 = 22;
LABEL_18:
  WPP_SF_d(v8[2], v9, &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids, (unsigned int)ProcessMitigationPolicy);
  return (unsigned int)ProcessMitigationPolicy;
}

```

## disassembly

```asm
0x140021964  mov     [rsp+arg_10], rbx
0x140021969  push    rbp
0x14002196a  push    rsi
0x14002196b  push    rdi
0x14002196c  sub     rsp, 40h
0x140021970  mov     rax, cs:__security_cookie
0x140021977  xor     rax, rsp
0x14002197a  mov     [rsp+58h+var_20], rax
0x14002197f  mov     rbp, rdx
0x140021982  mov     rsi, rcx
0x140021985  mov     [rsp+58h+var_28], 0
0x14002198d  call    cs:__imp_GetCurrentProcess
0x140021993  mov     rcx, rax; this
0x140021996  mov     r9d, 4; void *
0x14002199c  lea     r8, [rsp+58h+var_28]; enum _PROCESS_MITIGATION_POLICY
0x1400219a1  lea     edx, [r9-1]; void *
0x1400219a5  call    ?UtilGetProcessMitigationPolicy@CommonUtil@@YAJPEAXW4_PROCESS_MITIGATION_POLICY@@0_K@Z; CommonUtil::UtilGetProcessMitigationPolicy(void *,_PROCESS_MITIGATION_POLICY,void *,unsigned __int64)
0x1400219aa  mov     edi, eax
0x1400219ac  test    eax, eax
0x1400219ae  jns     short loc_1400219DB
0x1400219b0  lea     rbx, WPP_GLOBAL_Control
0x1400219b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400219be  cmp     rcx, rbx
0x1400219c1  jz      loc_140021AA0
0x1400219c7  test    byte ptr [rcx+1Ch], 1
0x1400219cb  jz      loc_140021AA0
0x1400219d1  mov     edx, 16h
0x1400219d6  jmp     loc_140021A8D
0x1400219db  lea     rbx, WPP_GLOBAL_Control
0x1400219e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400219e9  cmp     rcx, rbx
0x1400219ec  jz      short loc_140021A17
0x1400219ee  test    byte ptr [rcx+1Ch], 4
0x1400219f2  jz      short loc_140021A17
0x1400219f4  mov     r9d, [rsp+58h+var_28]
0x1400219f9  mov     eax, r9d
0x1400219fc  shr     eax, 1
0x1400219fe  and     eax, 1
0x140021a01  and     r9d, 1
0x140021a05  mov     edx, 17h
0x140021a0a  mov     [rsp+58h+var_38], eax
0x140021a0e  mov     rcx, [rcx+10h]
0x140021a12  call    WPP_SF_DD
0x140021a17  inc     dword ptr [rbp+0]
0x140021a1a  mov     eax, [rsp+58h+var_28]
0x140021a1e  test    al, 1
0x140021a20  jz      short loc_140021A2A
0x140021a22  test    al, 2
0x140021a24  jz      short loc_140021A2A
0x140021a26  xor     eax, eax
0x140021a28  jmp     short loc_140021AA2
0x140021a2a  or      eax, 3
0x140021a2d  mov     [rsp+58h+var_28], eax
0x140021a31  mov     r8d, 4; void *
0x140021a37  lea     rdx, [rsp+58h+var_28]; enum _PROCESS_MITIGATION_POLICY
0x140021a3c  lea     ecx, [r8-1]; this
0x140021a40  call    ?UtilSetProcessMitigationPolicy@CommonUtil@@YAJW4_PROCESS_MITIGATION_POLICY@@PEAX_K@Z; CommonUtil::UtilSetProcessMitigationPolicy(_PROCESS_MITIGATION_POLICY,void *,unsigned __int64)
0x140021a45  mov     edi, eax
0x140021a47  test    eax, eax
0x140021a49  js      short loc_140021A76
0x140021a4b  inc     dword ptr [rsi]
0x140021a4d  mov     rcx, cs:WPP_GLOBAL_Control
0x140021a54  cmp     rcx, rbx
0x140021a57  jz      short loc_140021A26
0x140021a59  test    byte ptr [rcx+1Ch], 4
0x140021a5d  jz      short loc_140021A26
0x140021a5f  mov     edx, 18h
0x140021a64  lea     r8, WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids
0x140021a6b  mov     rcx, [rcx+10h]
0x140021a6f  call    WPP_SF_
0x140021a74  jmp     short loc_140021A26
0x140021a76  mov     rcx, cs:WPP_GLOBAL_Control
0x140021a7d  cmp     rcx, rbx
0x140021a80  jz      short loc_140021AA0
0x140021a82  test    byte ptr [rcx+1Ch], 2
0x140021a86  jz      short loc_140021AA0
0x140021a88  mov     edx, 19h
0x140021a8d  mov     r9d, edi
0x140021a90  lea     r8, WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids
0x140021a97  mov     rcx, [rcx+10h]
0x140021a9b  call    WPP_SF_d
0x140021aa0  mov     eax, edi
0x140021aa2  mov     rcx, [rsp+58h+var_20]
0x140021aa7  xor     rcx, rsp; StackCookie
0x140021aaa  call    __security_check_cookie
0x140021aaf  mov     rbx, [rsp+58h+arg_10]
0x140021ab4  add     rsp, 40h
0x140021ab8  pop     rdi
0x140021ab9  pop     rsi
0x140021aba  pop     rbp
0x140021abb  retn
```
