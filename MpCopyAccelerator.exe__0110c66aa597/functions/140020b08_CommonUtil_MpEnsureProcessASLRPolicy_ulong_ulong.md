# CommonUtil::MpEnsureProcessASLRPolicy(ulong &,ulong &)

- ea: `0x140020b08`
- end: `0x140020c7b`
- name: `?MpEnsureProcessASLRPolicy@CommonUtil@@YAJAEAK0@Z`
- size: `371`
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
- `0x140020b08`
- `0x140021cf0`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x140020b31`
- `KERNEL32!GetCurrentProcess` at `0x140020b31`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpEnsureProcessASLRPolicy(CommonUtil *this, unsigned int *a2, unsigned int *a3)
{
  CommonUtil *CurrentProcess; // rax
  int ProcessMitigationPolicy; // edi
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  _PROCESS_MITIGATION_POLICY v10; // [rsp+40h] [rbp-28h] BYREF

  v10 = ProcessDEPPolicy;
  CurrentProcess = (CommonUtil *)GetCurrentProcess();
  ProcessMitigationPolicy = CommonUtil::UtilGetProcessMitigationPolicy(
                              CurrentProcess,
                              (void *)1,
                              (__int64)&v10,
                              (void *)4);
  if ( ProcessMitigationPolicy >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_DDDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        ((unsigned int)v10 >> 2) & 1,
        ((unsigned int)v10 >> 3) & 1,
        v10 & 1,
        ((unsigned int)v10 >> 1) & 1,
        ((unsigned int)v10 >> 2) & 1,
        ((unsigned int)v10 >> 3) & 1);
    ++*a2;
    if ( (v10 & 1) == 0 || (v10 & 4) == 0 )
    {
      v10 |= 5u;
      ProcessMitigationPolicy = CommonUtil::UtilSetProcessMitigationPolicy((CommonUtil *)1, (__int64)&v10, (void *)4);
      if ( ProcessMitigationPolicy < 0 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          return (unsigned int)ProcessMitigationPolicy;
        v8 = 17;
        goto LABEL_18;
      }
      ++*(_DWORD *)this;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids);
    }
    return 0;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    return (unsigned int)ProcessMitigationPolicy;
  v8 = 14;
LABEL_18:
  WPP_SF_d(v7[2], v8, &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids, (unsigned int)ProcessMitigationPolicy);
  return (unsigned int)ProcessMitigationPolicy;
}

```

## disassembly

```asm
0x140020b08  mov     [rsp+arg_10], rbx
0x140020b0d  push    rbp
0x140020b0e  push    rsi
0x140020b0f  push    rdi
0x140020b10  sub     rsp, 50h
0x140020b14  mov     rax, cs:__security_cookie
0x140020b1b  xor     rax, rsp
0x140020b1e  mov     [rsp+68h+var_20], rax
0x140020b23  mov     rbp, rdx
0x140020b26  mov     rsi, rcx
0x140020b29  mov     [rsp+68h+var_28], 0
0x140020b31  call    cs:__imp_GetCurrentProcess
0x140020b37  mov     rcx, rax; this
0x140020b3a  mov     r9d, 4; void *
0x140020b40  lea     r8, [rsp+68h+var_28]; enum _PROCESS_MITIGATION_POLICY
0x140020b45  lea     edx, [r9-3]; void *
0x140020b49  call    ?UtilGetProcessMitigationPolicy@CommonUtil@@YAJPEAXW4_PROCESS_MITIGATION_POLICY@@0_K@Z; CommonUtil::UtilGetProcessMitigationPolicy(void *,_PROCESS_MITIGATION_POLICY,void *,unsigned __int64)
0x140020b4e  mov     edi, eax
0x140020b50  test    eax, eax
0x140020b52  jns     short loc_140020B7F
0x140020b54  lea     rbx, WPP_GLOBAL_Control
0x140020b5b  mov     rcx, cs:WPP_GLOBAL_Control
0x140020b62  cmp     rcx, rbx
0x140020b65  jz      loc_140020C5C
0x140020b6b  test    byte ptr [rcx+1Ch], 1
0x140020b6f  jz      loc_140020C5C
0x140020b75  mov     edx, 0Eh
0x140020b7a  jmp     loc_140020C49
0x140020b7f  lea     rbx, WPP_GLOBAL_Control
0x140020b86  mov     rcx, cs:WPP_GLOBAL_Control
0x140020b8d  cmp     rcx, rbx
0x140020b90  jz      short loc_140020BD3
0x140020b92  test    byte ptr [rcx+1Ch], 4
0x140020b96  jz      short loc_140020BD3
0x140020b98  mov     r9d, [rsp+68h+var_28]
0x140020b9d  mov     r8d, r9d
0x140020ba0  shr     r8d, 3
0x140020ba4  and     r8d, 1
0x140020ba8  mov     edx, r9d
0x140020bab  shr     edx, 2
0x140020bae  and     edx, 1
0x140020bb1  mov     eax, r9d
0x140020bb4  shr     eax, 1
0x140020bb6  and     eax, 1
0x140020bb9  and     r9d, 1
0x140020bbd  mov     [rsp+68h+var_38], r8d
0x140020bc2  mov     [rsp+68h+var_40], edx
0x140020bc6  mov     [rsp+68h+var_48], eax
0x140020bca  mov     rcx, [rcx+10h]
0x140020bce  call    WPP_SF_DDDD
0x140020bd3  inc     dword ptr [rbp+0]
0x140020bd6  mov     eax, [rsp+68h+var_28]
0x140020bda  test    al, 1
0x140020bdc  jz      short loc_140020BE6
0x140020bde  test    al, 4
0x140020be0  jz      short loc_140020BE6
0x140020be2  xor     eax, eax
0x140020be4  jmp     short loc_140020C5E
0x140020be6  or      eax, 5
0x140020be9  mov     [rsp+68h+var_28], eax
0x140020bed  mov     r8d, 4; void *
0x140020bf3  lea     rdx, [rsp+68h+var_28]; enum _PROCESS_MITIGATION_POLICY
0x140020bf8  lea     ecx, [r8-3]; this
0x140020bfc  call    ?UtilSetProcessMitigationPolicy@CommonUtil@@YAJW4_PROCESS_MITIGATION_POLICY@@PEAX_K@Z; CommonUtil::UtilSetProcessMitigationPolicy(_PROCESS_MITIGATION_POLICY,void *,unsigned __int64)
0x140020c01  mov     edi, eax
0x140020c03  test    eax, eax
0x140020c05  js      short loc_140020C32
0x140020c07  inc     dword ptr [rsi]
0x140020c09  mov     rcx, cs:WPP_GLOBAL_Control
0x140020c10  cmp     rcx, rbx
0x140020c13  jz      short loc_140020BE2
0x140020c15  test    byte ptr [rcx+1Ch], 4
0x140020c19  jz      short loc_140020BE2
0x140020c1b  mov     edx, 10h
0x140020c20  lea     r8, WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids
0x140020c27  mov     rcx, [rcx+10h]
0x140020c2b  call    WPP_SF_
0x140020c30  jmp     short loc_140020BE2
0x140020c32  mov     rcx, cs:WPP_GLOBAL_Control
0x140020c39  cmp     rcx, rbx
0x140020c3c  jz      short loc_140020C5C
0x140020c3e  test    byte ptr [rcx+1Ch], 2
0x140020c42  jz      short loc_140020C5C
0x140020c44  mov     edx, 11h
0x140020c49  mov     r9d, edi
0x140020c4c  lea     r8, WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids
0x140020c53  mov     rcx, [rcx+10h]
0x140020c57  call    WPP_SF_d
0x140020c5c  mov     eax, edi
0x140020c5e  mov     rcx, [rsp+68h+var_20]
0x140020c63  xor     rcx, rsp; StackCookie
0x140020c66  call    __security_check_cookie
0x140020c6b  mov     rbx, [rsp+68h+arg_10]
0x140020c73  add     rsp, 50h
0x140020c77  pop     rdi
0x140020c78  pop     rsi
0x140020c79  pop     rbp
0x140020c7a  retn
```
