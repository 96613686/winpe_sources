# CommonUtil::MpEnsureProcessExtensionPointDisablePolicy(ulong &,ulong &)

- ea: `0x14002109c`
- end: `0x1400211eb`
- name: `?MpEnsureProcessExtensionPointDisablePolicy@CommonUtil@@YAJAEAK0@Z`
- size: `335`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140021424`

## callees

- `0x14000496c`
- `0x1400049e4`
- `0x140005c20`
- `0x14001da4c`
- `0x14001da70`
- `0x14002109c`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x1400210c5`
- `KERNEL32!GetCurrentProcess` at `0x1400210c5`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpEnsureProcessExtensionPointDisablePolicy(
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
                              (void *)6,
                              (__int64)&v10,
                              (void *)4);
  if ( ProcessMitigationPolicy >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids, v10 & 1);
    ++*a2;
    if ( (v10 & 1) == 0 )
    {
      v10 |= 1u;
      ProcessMitigationPolicy = CommonUtil::UtilSetProcessMitigationPolicy((CommonUtil *)6, (__int64)&v10, (void *)4);
      if ( ProcessMitigationPolicy < 0 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          return (unsigned int)ProcessMitigationPolicy;
        v8 = 33;
        goto LABEL_17;
      }
      ++*(_DWORD *)this;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids);
    }
    return 0;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    return (unsigned int)ProcessMitigationPolicy;
  v8 = 30;
LABEL_17:
  WPP_SF_d(v7[2], v8, &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids, (unsigned int)ProcessMitigationPolicy);
  return (unsigned int)ProcessMitigationPolicy;
}

```

## disassembly

```asm
0x14002109c  mov     [rsp+arg_10], rbx
0x1400210a1  push    rbp
0x1400210a2  push    rsi
0x1400210a3  push    rdi
0x1400210a4  sub     rsp, 30h
0x1400210a8  mov     rax, cs:__security_cookie
0x1400210af  xor     rax, rsp
0x1400210b2  mov     [rsp+48h+var_20], rax
0x1400210b7  mov     rbp, rdx
0x1400210ba  mov     rsi, rcx
0x1400210bd  mov     [rsp+48h+var_28], 0; unsigned __int64
0x1400210c5  call    cs:__imp_GetCurrentProcess
0x1400210cb  mov     rcx, rax; this
0x1400210ce  mov     r9d, 4; void *
0x1400210d4  lea     r8, [rsp+48h+var_28]; enum _PROCESS_MITIGATION_POLICY
0x1400210d9  lea     edx, [r9+2]; void *
0x1400210dd  call    ?UtilGetProcessMitigationPolicy@CommonUtil@@YAJPEAXW4_PROCESS_MITIGATION_POLICY@@0_K@Z; CommonUtil::UtilGetProcessMitigationPolicy(void *,_PROCESS_MITIGATION_POLICY,void *,unsigned __int64)
0x1400210e2  mov     edi, eax
0x1400210e4  test    eax, eax
0x1400210e6  jns     short loc_140021113
0x1400210e8  lea     rbx, WPP_GLOBAL_Control
0x1400210ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400210f6  cmp     rcx, rbx
0x1400210f9  jz      loc_1400211CF
0x1400210ff  test    byte ptr [rcx+1Ch], 1
0x140021103  jz      loc_1400211CF
0x140021109  mov     edx, 1Eh
0x14002110e  jmp     loc_1400211BC
0x140021113  lea     rbx, WPP_GLOBAL_Control
0x14002111a  mov     rcx, cs:WPP_GLOBAL_Control
0x140021121  cmp     rcx, rbx
0x140021124  jz      short loc_14002114A
0x140021126  test    byte ptr [rcx+1Ch], 4
0x14002112a  jz      short loc_14002114A
0x14002112c  mov     r9d, [rsp+48h+var_28]
0x140021131  and     r9d, 1
0x140021135  mov     edx, 1Fh
0x14002113a  lea     r8, WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids
0x140021141  mov     rcx, [rcx+10h]
0x140021145  call    WPP_SF_d
0x14002114a  inc     dword ptr [rbp+0]
0x14002114d  mov     eax, [rsp+48h+var_28]
0x140021151  test    al, 1
0x140021153  jz      short loc_140021159
0x140021155  xor     eax, eax
0x140021157  jmp     short loc_1400211D1
0x140021159  or      eax, 1
0x14002115c  mov     [rsp+48h+var_28], eax
0x140021160  mov     r8d, 4; void *
0x140021166  lea     rdx, [rsp+48h+var_28]; enum _PROCESS_MITIGATION_POLICY
0x14002116b  lea     ecx, [r8+2]; this
0x14002116f  call    ?UtilSetProcessMitigationPolicy@CommonUtil@@YAJW4_PROCESS_MITIGATION_POLICY@@PEAX_K@Z; CommonUtil::UtilSetProcessMitigationPolicy(_PROCESS_MITIGATION_POLICY,void *,unsigned __int64)
0x140021174  mov     edi, eax
0x140021176  test    eax, eax
0x140021178  js      short loc_1400211A5
0x14002117a  inc     dword ptr [rsi]
0x14002117c  mov     rcx, cs:WPP_GLOBAL_Control
0x140021183  cmp     rcx, rbx
0x140021186  jz      short loc_140021155
0x140021188  test    byte ptr [rcx+1Ch], 4
0x14002118c  jz      short loc_140021155
0x14002118e  mov     edx, 20h ; ' '
0x140021193  lea     r8, WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids
0x14002119a  mov     rcx, [rcx+10h]
0x14002119e  call    WPP_SF_
0x1400211a3  jmp     short loc_140021155
0x1400211a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400211ac  cmp     rcx, rbx
0x1400211af  jz      short loc_1400211CF
0x1400211b1  test    byte ptr [rcx+1Ch], 2
0x1400211b5  jz      short loc_1400211CF
0x1400211b7  mov     edx, 21h ; '!'
0x1400211bc  mov     r9d, edi
0x1400211bf  lea     r8, WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids
0x1400211c6  mov     rcx, [rcx+10h]
0x1400211ca  call    WPP_SF_d
0x1400211cf  mov     eax, edi
0x1400211d1  mov     rcx, [rsp+48h+var_20]
0x1400211d6  xor     rcx, rsp; StackCookie
0x1400211d9  call    __security_check_cookie
0x1400211de  mov     rbx, [rsp+48h+arg_10]
0x1400211e3  add     rsp, 30h
0x1400211e7  pop     rdi
0x1400211e8  pop     rsi
0x1400211e9  pop     rbp
0x1400211ea  retn
```
