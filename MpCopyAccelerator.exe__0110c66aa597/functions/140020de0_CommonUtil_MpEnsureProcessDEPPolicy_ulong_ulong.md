# CommonUtil::MpEnsureProcessDEPPolicy(ulong &,ulong &)

- ea: `0x140020de0`
- end: `0x140020f36`
- name: `?MpEnsureProcessDEPPolicy@CommonUtil@@YAJAEAK0@Z`
- size: `342`
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
- `0x140020de0`
- `0x140021c14`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x140020e0a`
- `KERNEL32!GetCurrentProcess` at `0x140020e0a`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpEnsureProcessDEPPolicy(CommonUtil *this, unsigned int *a2, unsigned int *a3)
{
  CommonUtil *CurrentProcess; // rax
  int ProcessMitigationPolicy; // edi
  __int64 v7; // r8
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  enum _PROCESS_MITIGATION_POLICY v11[2]; // [rsp+30h] [rbp-28h] BYREF

  *(_QWORD *)v11 = 0;
  CurrentProcess = (CommonUtil *)GetCurrentProcess();
  ProcessMitigationPolicy = CommonUtil::UtilGetProcessMitigationPolicy(CurrentProcess, 0, (__int64)v11, (void *)8);
  if ( ProcessMitigationPolicy >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v7, v11[0] & 1, ((unsigned int)v11[0] >> 1) & 1);
    ++*a2;
    if ( (v11[0] & 3) != 3 )
    {
      v11[0] |= 3u;
      ProcessMitigationPolicy = CommonUtil::UtilSetProcessMitigationPolicy(0, (__int64)v11, (void *)8);
      if ( ProcessMitigationPolicy < 0 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          return (unsigned int)ProcessMitigationPolicy;
        v9 = 13;
        goto LABEL_17;
      }
      ++*(_DWORD *)this;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids);
    }
    return 0;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    return (unsigned int)ProcessMitigationPolicy;
  v9 = 10;
LABEL_17:
  WPP_SF_d(v8[2], v9, &WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids, (unsigned int)ProcessMitigationPolicy);
  return (unsigned int)ProcessMitigationPolicy;
}

```

## disassembly

```asm
0x140020de0  mov     [rsp+arg_10], rbx
0x140020de5  push    rbp
0x140020de6  push    rsi
0x140020de7  push    rdi
0x140020de8  sub     rsp, 40h
0x140020dec  mov     rax, cs:__security_cookie
0x140020df3  xor     rax, rsp
0x140020df6  mov     [rsp+58h+var_20], rax
0x140020dfb  mov     rbp, rdx
0x140020dfe  mov     rsi, rcx
0x140020e01  mov     qword ptr [rsp+58h+var_28], 0
0x140020e0a  call    cs:__imp_GetCurrentProcess
0x140020e10  mov     rcx, rax; this
0x140020e13  mov     r9d, 8; void *
0x140020e19  lea     r8, [rsp+58h+var_28]; enum _PROCESS_MITIGATION_POLICY
0x140020e1e  xor     edx, edx; void *
0x140020e20  call    ?UtilGetProcessMitigationPolicy@CommonUtil@@YAJPEAXW4_PROCESS_MITIGATION_POLICY@@0_K@Z; CommonUtil::UtilGetProcessMitigationPolicy(void *,_PROCESS_MITIGATION_POLICY,void *,unsigned __int64)
0x140020e25  mov     edi, eax
0x140020e27  test    eax, eax
0x140020e29  jns     short loc_140020E56
0x140020e2b  lea     rbx, WPP_GLOBAL_Control
0x140020e32  mov     rcx, cs:WPP_GLOBAL_Control
0x140020e39  cmp     rcx, rbx
0x140020e3c  jz      loc_140020F1A
0x140020e42  test    byte ptr [rcx+1Ch], 1
0x140020e46  jz      loc_140020F1A
0x140020e4c  mov     edx, 0Ah
0x140020e51  jmp     loc_140020F07
0x140020e56  lea     rbx, WPP_GLOBAL_Control
0x140020e5d  mov     rcx, cs:WPP_GLOBAL_Control
0x140020e64  cmp     rcx, rbx
0x140020e67  jz      short loc_140020E92
0x140020e69  test    byte ptr [rcx+1Ch], 4
0x140020e6d  jz      short loc_140020E92
0x140020e6f  mov     r9d, [rsp+58h+var_28]
0x140020e74  mov     eax, r9d
0x140020e77  shr     eax, 1
0x140020e79  and     eax, 1
0x140020e7c  and     r9d, 1
0x140020e80  mov     edx, 0Bh
0x140020e85  mov     [rsp+58h+var_38], eax
0x140020e89  mov     rcx, [rcx+10h]
0x140020e8d  call    WPP_SF_DD
0x140020e92  inc     dword ptr [rbp+0]
0x140020e95  mov     ecx, [rsp+58h+var_28]
0x140020e99  mov     eax, ecx
0x140020e9b  and     eax, 3
0x140020e9e  cmp     al, 3
0x140020ea0  jnz     short loc_140020EA6
0x140020ea2  xor     eax, eax
0x140020ea4  jmp     short loc_140020F1C
0x140020ea6  or      ecx, 3
0x140020ea9  mov     [rsp+58h+var_28], ecx
0x140020ead  mov     r8d, 8; void *
0x140020eb3  lea     rdx, [rsp+58h+var_28]; enum _PROCESS_MITIGATION_POLICY
0x140020eb8  xor     ecx, ecx; this
0x140020eba  call    ?UtilSetProcessMitigationPolicy@CommonUtil@@YAJW4_PROCESS_MITIGATION_POLICY@@PEAX_K@Z; CommonUtil::UtilSetProcessMitigationPolicy(_PROCESS_MITIGATION_POLICY,void *,unsigned __int64)
0x140020ebf  mov     edi, eax
0x140020ec1  test    eax, eax
0x140020ec3  js      short loc_140020EF0
0x140020ec5  inc     dword ptr [rsi]
0x140020ec7  mov     rcx, cs:WPP_GLOBAL_Control
0x140020ece  cmp     rcx, rbx
0x140020ed1  jz      short loc_140020EA2
0x140020ed3  test    byte ptr [rcx+1Ch], 4
0x140020ed7  jz      short loc_140020EA2
0x140020ed9  mov     edx, 0Ch
0x140020ede  lea     r8, WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids
0x140020ee5  mov     rcx, [rcx+10h]
0x140020ee9  call    WPP_SF_
0x140020eee  jmp     short loc_140020EA2
0x140020ef0  mov     rcx, cs:WPP_GLOBAL_Control
0x140020ef7  cmp     rcx, rbx
0x140020efa  jz      short loc_140020F1A
0x140020efc  test    byte ptr [rcx+1Ch], 2
0x140020f00  jz      short loc_140020F1A
0x140020f02  mov     edx, 0Dh
0x140020f07  mov     r9d, edi
0x140020f0a  lea     r8, WPP_d1ba5309cc45319bcbd4e2e17652be78_Traceguids
0x140020f11  mov     rcx, [rcx+10h]
0x140020f15  call    WPP_SF_d
0x140020f1a  mov     eax, edi
0x140020f1c  mov     rcx, [rsp+58h+var_20]
0x140020f21  xor     rcx, rsp; StackCookie
0x140020f24  call    __security_check_cookie
0x140020f29  mov     rbx, [rsp+58h+arg_10]
0x140020f2e  add     rsp, 40h
0x140020f32  pop     rdi
0x140020f33  pop     rsi
0x140020f34  pop     rbp
0x140020f35  retn
```
