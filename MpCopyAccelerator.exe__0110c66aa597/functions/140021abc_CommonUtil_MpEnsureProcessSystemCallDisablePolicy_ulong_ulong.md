# CommonUtil::MpEnsureProcessSystemCallDisablePolicy(ulong &,ulong &)

- ea: `0x140021abc`
- end: `0x140021c14`
- name: `?MpEnsureProcessSystemCallDisablePolicy@CommonUtil@@YAJAEAK0@Z`
- size: `344`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140021424`

## callees

- `0x14000496c`
- `0x1400049e4`
- `0x140005c20`
- `0x14001da4c`
- `0x14001da70`
- `0x140021abc`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x140021aeb`
- `KERNEL32!GetCurrentProcess` at `0x140021aeb`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpEnsureProcessSystemCallDisablePolicy(
        CommonUtil *this,
        unsigned int *a2,
        unsigned int *a3)
{
  CommonUtil *CurrentProcess; // rax
  int ProcessMitigationPolicy; // edi
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  enum _PROCESS_MITIGATION_POLICY v10; // [rsp+20h] [rbp-28h] BYREF

  v10 = ProcessDEPPolicy;
  CurrentProcess = (CommonUtil *)GetCurrentProcess();
  ProcessMitigationPolicy = CommonUtil::UtilGetProcessMitigationPolicy(
                              CurrentProcess,
                              (void *)4,
                              (__int64)&v10,
                              (void *)4);
  if ( ProcessMitigationPolicy >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids, v10 & 1);
    ++*a2;
    if ( (v10 & 1) == 0 )
    {
      v10 |= 1u;
      ProcessMitigationPolicy = CommonUtil::UtilSetProcessMitigationPolicy((CommonUtil *)4, (__int64)&v10, (void *)4);
      if ( ProcessMitigationPolicy < 0 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          return (unsigned int)ProcessMitigationPolicy;
        v8 = 29;
        goto LABEL_17;
      }
      ++*(_DWORD *)this;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids);
    }
    return 0;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    return (unsigned int)ProcessMitigationPolicy;
  v8 = 26;
LABEL_17:
  WPP_SF_d(v7[2], v8, &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids, (unsigned int)ProcessMitigationPolicy);
  return (unsigned int)ProcessMitigationPolicy;
}

```

## disassembly

```asm
0x140021abc  mov     [rsp+arg_10], rbx
0x140021ac1  mov     [rsp+arg_18], rbp
0x140021ac6  push    rsi
0x140021ac7  push    rdi
0x140021ac8  push    r14
0x140021aca  sub     rsp, 30h
0x140021ace  mov     rax, cs:__security_cookie
0x140021ad5  xor     rax, rsp
0x140021ad8  mov     [rsp+48h+var_20], rax
0x140021add  mov     rbp, rdx
0x140021ae0  mov     rsi, rcx
0x140021ae3  mov     [rsp+48h+var_28], 0; unsigned __int64
0x140021aeb  call    cs:__imp_GetCurrentProcess
0x140021af1  mov     rcx, rax; this
0x140021af4  mov     r14d, 4
0x140021afa  mov     r9d, r14d; void *
0x140021afd  lea     r8, [rsp+48h+var_28]; enum _PROCESS_MITIGATION_POLICY
0x140021b02  mov     edx, r14d; void *
0x140021b05  call    ?UtilGetProcessMitigationPolicy@CommonUtil@@YAJPEAXW4_PROCESS_MITIGATION_POLICY@@0_K@Z; CommonUtil::UtilGetProcessMitigationPolicy(void *,_PROCESS_MITIGATION_POLICY,void *,unsigned __int64)
0x140021b0a  mov     edi, eax
0x140021b0c  test    eax, eax
0x140021b0e  jns     short loc_140021B3A
0x140021b10  lea     rbx, WPP_GLOBAL_Control
0x140021b17  mov     rcx, cs:WPP_GLOBAL_Control
0x140021b1e  cmp     rcx, rbx
0x140021b21  jz      loc_140021BF2
0x140021b27  test    byte ptr [rcx+1Ch], 1
0x140021b2b  jz      loc_140021BF2
0x140021b31  lea     edx, [r14+16h]
0x140021b35  jmp     loc_140021BDF
0x140021b3a  lea     rbx, WPP_GLOBAL_Control
0x140021b41  mov     rcx, cs:WPP_GLOBAL_Control
0x140021b48  cmp     rcx, rbx
0x140021b4b  jz      short loc_140021B71
0x140021b4d  test    [rcx+1Ch], r14b
0x140021b51  jz      short loc_140021B71
0x140021b53  mov     r9d, [rsp+48h+var_28]
0x140021b58  and     r9d, 1
0x140021b5c  mov     edx, 1Bh
0x140021b61  lea     r8, WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids
0x140021b68  mov     rcx, [rcx+10h]
0x140021b6c  call    WPP_SF_d
0x140021b71  inc     dword ptr [rbp+0]
0x140021b74  mov     eax, [rsp+48h+var_28]
0x140021b78  test    al, 1
0x140021b7a  jz      short loc_140021B80
0x140021b7c  xor     eax, eax
0x140021b7e  jmp     short loc_140021BF4
0x140021b80  or      eax, 1
0x140021b83  mov     [rsp+48h+var_28], eax
0x140021b87  mov     r8, r14; void *
0x140021b8a  lea     rdx, [rsp+48h+var_28]; enum _PROCESS_MITIGATION_POLICY
0x140021b8f  mov     ecx, r14d; this
0x140021b92  call    ?UtilSetProcessMitigationPolicy@CommonUtil@@YAJW4_PROCESS_MITIGATION_POLICY@@PEAX_K@Z; CommonUtil::UtilSetProcessMitigationPolicy(_PROCESS_MITIGATION_POLICY,void *,unsigned __int64)
0x140021b97  mov     edi, eax
0x140021b99  test    eax, eax
0x140021b9b  js      short loc_140021BC8
0x140021b9d  inc     dword ptr [rsi]
0x140021b9f  mov     rcx, cs:WPP_GLOBAL_Control
0x140021ba6  cmp     rcx, rbx
0x140021ba9  jz      short loc_140021B7C
0x140021bab  test    [rcx+1Ch], r14b
0x140021baf  jz      short loc_140021B7C
0x140021bb1  mov     edx, 1Ch
0x140021bb6  lea     r8, WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids
0x140021bbd  mov     rcx, [rcx+10h]
0x140021bc1  call    WPP_SF_
0x140021bc6  jmp     short loc_140021B7C
0x140021bc8  mov     rcx, cs:WPP_GLOBAL_Control
0x140021bcf  cmp     rcx, rbx
0x140021bd2  jz      short loc_140021BF2
0x140021bd4  test    byte ptr [rcx+1Ch], 2
0x140021bd8  jz      short loc_140021BF2
0x140021bda  mov     edx, 1Dh
0x140021bdf  mov     r9d, edi
0x140021be2  lea     r8, WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids
0x140021be9  mov     rcx, [rcx+10h]
0x140021bed  call    WPP_SF_d
0x140021bf2  mov     eax, edi
0x140021bf4  mov     rcx, [rsp+48h+var_20]
0x140021bf9  xor     rcx, rsp; StackCookie
0x140021bfc  call    __security_check_cookie
0x140021c01  mov     rbx, [rsp+48h+arg_10]
0x140021c06  mov     rbp, [rsp+48h+arg_18]
0x140021c0b  add     rsp, 30h
0x140021c0f  pop     r14
0x140021c11  pop     rdi
0x140021c12  pop     rsi
0x140021c13  retn
```
