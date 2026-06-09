# CommonUtil::MpEnsureProcessImageLoadPolicy(ulong &,ulong &)

- ea: `0x1400212c0`
- end: `0x140021424`
- name: `?MpEnsureProcessImageLoadPolicy@CommonUtil@@YAJAEAK0@Z`
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
- `0x1400212c0`
- `0x140021c7c`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x1400212e9`
- `KERNEL32!GetCurrentProcess` at `0x1400212e9`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpEnsureProcessImageLoadPolicy(CommonUtil *this, unsigned int *a2, unsigned int *a3)
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
                              (void *)0xA,
                              (__int64)&v10,
                              (void *)4);
  if ( ProcessMitigationPolicy >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_DDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        47,
        ((unsigned int)v10 >> 2) & 1,
        v10 & 1,
        ((unsigned int)v10 >> 1) & 1,
        ((unsigned int)v10 >> 2) & 1);
    ++*a2;
    if ( (v10 & 1) == 0 )
    {
      v10 |= 1u;
      ProcessMitigationPolicy = CommonUtil::UtilSetProcessMitigationPolicy((CommonUtil *)0xA, (__int64)&v10, (void *)4);
      if ( ProcessMitigationPolicy < 0 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          return (unsigned int)ProcessMitigationPolicy;
        v8 = 49;
        goto LABEL_17;
      }
      ++*(_DWORD *)this;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids);
    }
    return 0;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    return (unsigned int)ProcessMitigationPolicy;
  v8 = 46;
LABEL_17:
  WPP_SF_d(v7[2], v8, &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids, (unsigned int)ProcessMitigationPolicy);
  return (unsigned int)ProcessMitigationPolicy;
}

```

## disassembly

```asm
0x1400212c0  mov     [rsp+arg_10], rbx
0x1400212c5  push    rbp
0x1400212c6  push    rsi
0x1400212c7  push    rdi
0x1400212c8  sub     rsp, 40h
0x1400212cc  mov     rax, cs:__security_cookie
0x1400212d3  xor     rax, rsp
0x1400212d6  mov     [rsp+58h+var_20], rax
0x1400212db  mov     rbp, rdx
0x1400212de  mov     rsi, rcx
0x1400212e1  mov     [rsp+58h+var_28], 0
0x1400212e9  call    cs:__imp_GetCurrentProcess
0x1400212ef  mov     rcx, rax; this
0x1400212f2  mov     r9d, 4; void *
0x1400212f8  lea     r8, [rsp+58h+var_28]; enum _PROCESS_MITIGATION_POLICY
0x1400212fd  lea     edx, [r9+6]; void *
0x140021301  call    ?UtilGetProcessMitigationPolicy@CommonUtil@@YAJPEAXW4_PROCESS_MITIGATION_POLICY@@0_K@Z; CommonUtil::UtilGetProcessMitigationPolicy(void *,_PROCESS_MITIGATION_POLICY,void *,unsigned __int64)
0x140021306  mov     edi, eax
0x140021308  test    eax, eax
0x14002130a  jns     short loc_140021337
0x14002130c  lea     rbx, WPP_GLOBAL_Control
0x140021313  mov     rcx, cs:WPP_GLOBAL_Control
0x14002131a  cmp     rcx, rbx
0x14002131d  jz      loc_140021408
0x140021323  test    byte ptr [rcx+1Ch], 1
0x140021327  jz      loc_140021408
0x14002132d  mov     edx, 2Eh ; '.'
0x140021332  jmp     loc_1400213F5
0x140021337  lea     rbx, WPP_GLOBAL_Control
0x14002133e  mov     rcx, cs:WPP_GLOBAL_Control
0x140021345  cmp     rcx, rbx
0x140021348  jz      short loc_140021383
0x14002134a  test    byte ptr [rcx+1Ch], 4
0x14002134e  jz      short loc_140021383
0x140021350  mov     r9d, [rsp+58h+var_28]
0x140021355  mov     r8d, r9d
0x140021358  shr     r8d, 2
0x14002135c  and     r8d, 1
0x140021360  mov     eax, r9d
0x140021363  shr     eax, 1
0x140021365  and     eax, 1
0x140021368  and     r9d, 1
0x14002136c  mov     edx, 2Fh ; '/'
0x140021371  mov     [rsp+58h+var_30], r8d
0x140021376  mov     [rsp+58h+var_38], eax
0x14002137a  mov     rcx, [rcx+10h]
0x14002137e  call    WPP_SF_DDD
0x140021383  inc     dword ptr [rbp+0]
0x140021386  mov     eax, [rsp+58h+var_28]
0x14002138a  test    al, 1
0x14002138c  jz      short loc_140021392
0x14002138e  xor     eax, eax
0x140021390  jmp     short loc_14002140A
0x140021392  or      eax, 1
0x140021395  mov     [rsp+58h+var_28], eax
0x140021399  mov     r8d, 4; void *
0x14002139f  lea     rdx, [rsp+58h+var_28]; enum _PROCESS_MITIGATION_POLICY
0x1400213a4  lea     ecx, [r8+6]; this
0x1400213a8  call    ?UtilSetProcessMitigationPolicy@CommonUtil@@YAJW4_PROCESS_MITIGATION_POLICY@@PEAX_K@Z; CommonUtil::UtilSetProcessMitigationPolicy(_PROCESS_MITIGATION_POLICY,void *,unsigned __int64)
0x1400213ad  mov     edi, eax
0x1400213af  test    eax, eax
0x1400213b1  js      short loc_1400213DE
0x1400213b3  inc     dword ptr [rsi]
0x1400213b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400213bc  cmp     rcx, rbx
0x1400213bf  jz      short loc_14002138E
0x1400213c1  test    byte ptr [rcx+1Ch], 4
0x1400213c5  jz      short loc_14002138E
0x1400213c7  mov     edx, 30h ; '0'
0x1400213cc  lea     r8, WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids
0x1400213d3  mov     rcx, [rcx+10h]
0x1400213d7  call    WPP_SF_
0x1400213dc  jmp     short loc_14002138E
0x1400213de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400213e5  cmp     rcx, rbx
0x1400213e8  jz      short loc_140021408
0x1400213ea  test    byte ptr [rcx+1Ch], 2
0x1400213ee  jz      short loc_140021408
0x1400213f0  mov     edx, 31h ; '1'
0x1400213f5  mov     r9d, edi
0x1400213f8  lea     r8, WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids
0x1400213ff  mov     rcx, [rcx+10h]
0x140021403  call    WPP_SF_d
0x140021408  mov     eax, edi
0x14002140a  mov     rcx, [rsp+58h+var_20]
0x14002140f  xor     rcx, rsp; StackCookie
0x140021412  call    __security_check_cookie
0x140021417  mov     rbx, [rsp+58h+arg_10]
0x14002141c  add     rsp, 40h
0x140021420  pop     rdi
0x140021421  pop     rsi
0x140021422  pop     rbp
0x140021423  retn
```
