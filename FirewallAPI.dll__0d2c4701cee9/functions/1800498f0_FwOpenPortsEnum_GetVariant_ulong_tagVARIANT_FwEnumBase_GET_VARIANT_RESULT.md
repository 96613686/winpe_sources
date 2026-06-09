# FwOpenPortsEnum::GetVariant(ulong,tagVARIANT *,FwEnumBase::GET_VARIANT_RESULT *)

- ea: `0x1800498f0`
- end: `0x180049acf`
- name: `?GetVariant@FwOpenPortsEnum@@EEAAJKPEAUtagVARIANT@@PEAW4GET_VARIANT_RESULT@FwEnumBase@@@Z`
- size: `479`
- prototype: `__int64 __fastcall(FwOpenPortsEnum *__hidden this, unsigned int, struct tagVARIANT *, enum FwEnumBase::GET_VARIANT_RESULT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800294b0`
- `0x18003bb48`
- `0x1800498f0`

## import_xrefs

- `fwbase!FwIsBuiltInPort` at `0x1800499f2`
- `fwbase!FwIsBuiltInPort` at `0x1800499f2`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x180049981`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x180049981`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x18004996e`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x18004996e`
- `fwbase!FwReportReturnError` at `0x180049a50`
- `fwbase!FwReportReturnError` at `0x180049a99`
- `fwbase!FwReportReturnError` at `0x180049a50`
- `fwbase!FwReportReturnError` at `0x180049a99`
- `FWPolicyIOMgr!FwWfProtocolToICFProtocol` at `0x1800499dd`
- `FWPolicyIOMgr!FwWfProtocolToICFProtocol` at `0x1800499dd`

## string_xrefs

- `0x180049a49`: `FwOpenPortsEnum::GetVariant`
- `0x180049a92`: `FwOpenPortsEnum::GetVariant`

## pseudocode

```c
__int64 __fastcall FwOpenPortsEnum::GetVariant(
        FwOpenPortsEnum *this,
        int a2,
        struct tagVARIANT *a3,
        enum FwEnumBase::GET_VARIANT_RESULT *a4)
{
  unsigned int v4; // edi
  int v5; // ebx
  _QWORD **v8; // rsi
  int *v9; // r12
  int *v10; // r14
  int v11; // r13d
  int v12; // ecx
  __int64 v13; // r8
  _QWORD *v14; // rcx
  int v15; // eax
  struct tagVARIANT *v16; // rcx
  LONGLONG v17; // rax
  unsigned int v19; // [rsp+30h] [rbp-78h]
  __int64 v20; // [rsp+38h] [rbp-70h]
  LONGLONG v22; // [rsp+48h] [rbp-60h] BYREF
  struct tagVARIANT *v23; // [rsp+50h] [rbp-58h]
  unsigned int v24; // [rsp+58h] [rbp-50h] BYREF

  v23 = a3;
  v4 = 0;
  HIWORD(v19) = 0;
  v5 = 0;
  v24 = 6;
  v22 = 0;
  v20 = 0;
  v8 = (_QWORD **)((char *)this + 104);
  v9 = (int *)((char *)this + 116);
  v10 = (int *)((char *)this + 112);
  if ( !a2 )
  {
    *v8 = (_QWORD *)*((_QWORD *)this + 11);
    *v10 = 0;
    *v9 = 0;
  }
  v11 = *v10;
  if ( (unsigned int)*v10 >= *((_DWORD *)this + 24) )
  {
LABEL_20:
    *(_DWORD *)a4 = 2;
    goto LABEL_21;
  }
  while ( 1 )
  {
    if ( (unsigned int)IsRuleOpenPortOrAuthApp(*v8)
      && (unsigned int)IsRuleOldGlobalOpenPort(*v8)
      && (v12 = *v9, ++*v9, a2 == v12) )
    {
      v13 = (__int64)*v8;
      v5 = 1;
      v20 = (__int64)*v8;
    }
    else
    {
      v13 = v20;
    }
    v14 = (_QWORD *)**v8;
    ++*v10;
    *v8 = v14;
    if ( v5 != 1 )
      goto LABEL_12;
    LOWORD(v19) = **(_WORD **)(v13 + 72);
    v4 = FwWfProtocolToICFProtocol(*(unsigned __int16 *)(v13 + 48), &v24);
    if ( !(unsigned int)FwIsBuiltInPort(v24, (unsigned __int16)v19) )
      break;
    v5 = 0;
LABEL_12:
    if ( (unsigned int)++v11 >= *((_DWORD *)this + 24) )
      goto LABEL_20;
  }
  v15 = FwOpenPort::CreateInstance(*((unsigned int *)this + 18), v19, v24, 0, &v22);
  v4 = v15;
  if ( v15 == -2147024883 || v15 == -2147024894 )
  {
    *(_DWORD *)a4 = 1;
    v4 = 0;
  }
  else
  {
    if ( v15 < 0 )
    {
      FwReportReturnError("FwOpenPortsEnum::GetVariant", (unsigned int)v15);
      return (unsigned int)FwReportReturnError("FwOpenPortsEnum::GetVariant", v4);
    }
    v16 = v23;
    v17 = v22;
    v23->vt = 9;
    v16->llVal = v17;
    *(_DWORD *)a4 = 0;
  }
LABEL_21:
  if ( (v4 & 0x80000000) != 0 )
    return (unsigned int)FwReportReturnError("FwOpenPortsEnum::GetVariant", v4);
  return v4;
}

```

## disassembly

```asm
0x1800498f0  mov     [rsp+arg_8], rbx
0x1800498f5  push    rbp
0x1800498f6  push    rsi
0x1800498f7  push    rdi
0x1800498f8  push    r12
0x1800498fa  push    r13
0x1800498fc  push    r14
0x1800498fe  push    r15
0x180049900  sub     rsp, 70h
0x180049904  mov     rax, cs:__security_cookie
0x18004990b  xor     rax, rsp
0x18004990e  mov     [rsp+0A8h+var_48], rax
0x180049913  mov     eax, edx
0x180049915  mov     [rsp+0A8h+var_68], edx
0x180049919  xor     edx, edx
0x18004991b  mov     [rsp+0A8h+var_58], r8
0x180049920  xor     edi, edi
0x180049922  mov     [rsp+0A8h+var_78], edx
0x180049926  xor     ebx, ebx
0x180049928  mov     [rsp+0A8h+var_50], 6
0x180049930  mov     [rsp+0A8h+var_60], rdx
0x180049935  mov     r15, r9
0x180049938  mov     [rsp+0A8h+var_70], rdx
0x18004993d  mov     rbp, rcx
0x180049940  lea     rsi, [rcx+68h]
0x180049944  lea     r12, [rcx+74h]
0x180049948  lea     r14, [rcx+70h]
0x18004994c  test    eax, eax
0x18004994e  jnz     short loc_18004995E
0x180049950  mov     rax, [rcx+58h]
0x180049954  mov     [rsi], rax
0x180049957  mov     [r14], edx
0x18004995a  mov     [r12], edx
0x18004995e  mov     r13d, [r14]
0x180049961  cmp     r13d, [rcx+60h]
0x180049965  jnb     loc_180049A85
0x18004996b  mov     rcx, [rsi]
0x18004996e  call    cs:__imp_IsRuleOpenPortOrAuthApp
0x180049975  nop     dword ptr [rax+rax+00h]
0x18004997a  test    eax, eax
0x18004997c  jz      short loc_1800499B1
0x18004997e  mov     rcx, [rsi]
0x180049981  call    cs:__imp_IsRuleOldGlobalOpenPort
0x180049988  nop     dword ptr [rax+rax+00h]
0x18004998d  test    eax, eax
0x18004998f  jz      short loc_1800499B1
0x180049991  mov     ecx, [r12]
0x180049995  lea     eax, [rcx+1]
0x180049998  mov     [r12], eax
0x18004999c  cmp     [rsp+0A8h+var_68], ecx
0x1800499a0  jnz     short loc_1800499B1
0x1800499a2  mov     r8, [rsi]
0x1800499a5  mov     ebx, 1
0x1800499aa  mov     [rsp+0A8h+var_70], r8
0x1800499af  jmp     short loc_1800499B6
0x1800499b1  mov     r8, [rsp+0A8h+var_70]
0x1800499b6  mov     rax, [rsi]
0x1800499b9  mov     rcx, [rax]
0x1800499bc  inc     dword ptr [r14]
0x1800499bf  mov     [rsi], rcx
0x1800499c2  cmp     ebx, 1
0x1800499c5  jnz     short loc_180049A04
0x1800499c7  mov     rax, [r8+48h]
0x1800499cb  lea     rdx, [rsp+0A8h+var_50]
0x1800499d0  movzx   ecx, word ptr [r8+30h]
0x1800499d5  movzx   ebx, word ptr [rax]
0x1800499d8  mov     word ptr [rsp+0A8h+var_78], bx
0x1800499dd  call    cs:__imp_FwWfProtocolToICFProtocol
0x1800499e4  nop     dword ptr [rax+rax+00h]
0x1800499e9  mov     ecx, [rsp+0A8h+var_50]
0x1800499ed  movzx   edx, bx
0x1800499f0  mov     edi, eax
0x1800499f2  call    cs:__imp_FwIsBuiltInPort
0x1800499f9  nop     dword ptr [rax+rax+00h]
0x1800499fe  test    eax, eax
0x180049a00  jz      short loc_180049A15
0x180049a02  xor     ebx, ebx
0x180049a04  inc     r13d
0x180049a07  cmp     r13d, [rbp+60h]
0x180049a0b  jb      loc_18004996B
0x180049a11  test    ebx, ebx
0x180049a13  jz      short loc_180049A85
0x180049a15  mov     r8d, [rsp+0A8h+var_50]
0x180049a1a  lea     rax, [rsp+0A8h+var_60]
0x180049a1f  mov     edx, [rsp+0A8h+var_78]
0x180049a23  xor     r9d, r9d
0x180049a26  mov     ecx, [rbp+48h]
0x180049a29  mov     [rsp+0A8h+var_88], rax
0x180049a2e  call    ?CreateInstance@FwOpenPort@@SAJW4_tag_FW_PROFILE_TYPE@@GW4NET_FW_IP_PROTOCOL_@@QEAU_tag_FW_RULE@@PEAPEAV1@@Z; FwOpenPort::CreateInstance(_tag_FW_PROFILE_TYPE,ushort,NET_FW_IP_PROTOCOL_,_tag_FW_RULE * const,FwOpenPort * *)
0x180049a33  mov     edi, eax
0x180049a35  cmp     eax, 8007000Dh
0x180049a3a  jz      short loc_180049A7A
0x180049a3c  cmp     eax, 80070002h
0x180049a41  jz      short loc_180049A7A
0x180049a43  test    eax, eax
0x180049a45  jns     short loc_180049A5E
0x180049a47  mov     edx, eax
0x180049a49  lea     rcx, aFwopenportsenu; "FwOpenPortsEnum::GetVariant"
0x180049a50  call    cs:__imp_FwReportReturnError
0x180049a57  nop     dword ptr [rax+rax+00h]
0x180049a5c  jmp     short loc_180049A90
0x180049a5e  mov     rcx, [rsp+0A8h+var_58]
0x180049a63  mov     rax, [rsp+0A8h+var_60]
0x180049a68  mov     word ptr [rcx], 9
0x180049a6d  mov     [rcx+8], rax
0x180049a71  mov     dword ptr [r15], 0
0x180049a78  jmp     short loc_180049A8C
0x180049a7a  mov     dword ptr [r15], 1
0x180049a81  xor     edi, edi
0x180049a83  jmp     short loc_180049A8C
0x180049a85  mov     dword ptr [r15], 2
0x180049a8c  test    edi, edi
0x180049a8e  jns     short loc_180049AA7
0x180049a90  mov     edx, edi
0x180049a92  lea     rcx, aFwopenportsenu; "FwOpenPortsEnum::GetVariant"
0x180049a99  call    cs:__imp_FwReportReturnError
0x180049aa0  nop     dword ptr [rax+rax+00h]
0x180049aa5  mov     edi, eax
0x180049aa7  mov     eax, edi
0x180049aa9  mov     rcx, [rsp+0A8h+var_48]
0x180049aae  xor     rcx, rsp; StackCookie
0x180049ab1  call    __security_check_cookie
0x180049ab6  mov     rbx, [rsp+0A8h+arg_8]
0x180049abe  add     rsp, 70h
0x180049ac2  pop     r15
0x180049ac4  pop     r14
0x180049ac6  pop     r13
0x180049ac8  pop     r12
0x180049aca  pop     rdi
0x180049acb  pop     rsi
0x180049acc  pop     rbp
0x180049acd  retn
```
