# CommonUtil::MpEnsureProcessFontDisablePolicy(ulong &,ulong &)

- ea: `0x1400211ec`
- end: `0x1400212c0`
- name: `?MpEnsureProcessFontDisablePolicy@CommonUtil@@YAJAEAK0@Z`
- size: `212`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140021424`

## callees

- `0x14000496c`
- `0x140005c20`
- `0x14001da70`
- `0x1400211ec`
- `0x140021c14`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x140021210`
- `KERNEL32!GetCurrentProcess` at `0x140021210`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpEnsureProcessFontDisablePolicy(CommonUtil *this, unsigned int *a2, unsigned int *a3)
{
  CommonUtil *CurrentProcess; // rax
  int ProcessMitigationPolicy; // eax
  __int64 v6; // r8
  unsigned int v7; // ebx
  enum _PROCESS_MITIGATION_POLICY v9; // [rsp+30h] [rbp-18h] BYREF

  v9 = ProcessDEPPolicy;
  CurrentProcess = (CommonUtil *)GetCurrentProcess();
  ProcessMitigationPolicy = CommonUtil::UtilGetProcessMitigationPolicy(
                              CurrentProcess,
                              (void *)9,
                              (__int64)&v9,
                              (void *)4);
  v7 = ProcessMitigationPolicy;
  if ( ProcessMitigationPolicy >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, v6, v9 & 1, ((unsigned int)v9 >> 1) & 1);
    ++*a2;
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        44,
        &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids,
        (unsigned int)ProcessMitigationPolicy);
    return v7;
  }
}

```

## disassembly

```asm
0x1400211ec  mov     [rsp+arg_0], rbx
0x1400211f1  push    rdi
0x1400211f2  sub     rsp, 40h
0x1400211f6  mov     rax, cs:__security_cookie
0x1400211fd  xor     rax, rsp
0x140021200  mov     [rsp+48h+var_10], rax
0x140021205  mov     rdi, rdx
0x140021208  mov     [rsp+48h+var_18], 0
0x140021210  call    cs:__imp_GetCurrentProcess
0x140021216  mov     rcx, rax; this
0x140021219  mov     r9d, 4; void *
0x14002121f  lea     r8, [rsp+48h+var_18]; enum _PROCESS_MITIGATION_POLICY
0x140021224  lea     edx, [r9+5]; void *
0x140021228  call    ?UtilGetProcessMitigationPolicy@CommonUtil@@YAJPEAXW4_PROCESS_MITIGATION_POLICY@@0_K@Z; CommonUtil::UtilGetProcessMitigationPolicy(void *,_PROCESS_MITIGATION_POLICY,void *,unsigned __int64)
0x14002122d  mov     ebx, eax
0x14002122f  test    eax, eax
0x140021231  jns     short loc_140021268
0x140021233  lea     rdx, WPP_GLOBAL_Control
0x14002123a  mov     rcx, cs:WPP_GLOBAL_Control
0x140021241  cmp     rcx, rdx
0x140021244  jz      short loc_140021264
0x140021246  test    byte ptr [rcx+1Ch], 1
0x14002124a  jz      short loc_140021264
0x14002124c  mov     edx, 2Ch ; ','
0x140021251  mov     r9d, eax
0x140021254  lea     r8, WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids
0x14002125b  mov     rcx, [rcx+10h]
0x14002125f  call    WPP_SF_d
0x140021264  mov     eax, ebx
0x140021266  jmp     short loc_1400212A8
0x140021268  lea     rdx, WPP_GLOBAL_Control
0x14002126f  mov     rcx, cs:WPP_GLOBAL_Control
0x140021276  cmp     rcx, rdx
0x140021279  jz      short loc_1400212A4
0x14002127b  test    byte ptr [rcx+1Ch], 4
0x14002127f  jz      short loc_1400212A4
0x140021281  mov     r9d, [rsp+48h+var_18]
0x140021286  mov     eax, r9d
0x140021289  shr     eax, 1
0x14002128b  and     eax, 1
0x14002128e  and     r9d, 1
0x140021292  mov     edx, 2Dh ; '-'
0x140021297  mov     [rsp+48h+var_28], eax
0x14002129b  mov     rcx, [rcx+10h]
0x14002129f  call    WPP_SF_DD
0x1400212a4  inc     dword ptr [rdi]
0x1400212a6  xor     eax, eax
0x1400212a8  mov     rcx, [rsp+48h+var_10]
0x1400212ad  xor     rcx, rsp; StackCookie
0x1400212b0  call    __security_check_cookie
0x1400212b5  mov     rbx, [rsp+48h+arg_0]
0x1400212ba  add     rsp, 40h
0x1400212be  pop     rdi
0x1400212bf  retn
```
