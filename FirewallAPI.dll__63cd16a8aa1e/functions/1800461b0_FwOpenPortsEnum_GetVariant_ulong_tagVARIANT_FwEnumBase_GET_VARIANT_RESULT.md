# FwOpenPortsEnum::GetVariant(ulong,tagVARIANT *,FwEnumBase::GET_VARIANT_RESULT *)

- ea: `0x1800461b0`
- end: `0x18004636a`
- name: `?GetVariant@FwOpenPortsEnum@@EEAAJKPEAUtagVARIANT@@PEAW4GET_VARIANT_RESULT@FwEnumBase@@@Z`
- size: `442`
- prototype: `__int64 __fastcall(FwOpenPortsEnum *__hidden this, unsigned int, struct tagVARIANT *, enum FwEnumBase::GET_VARIANT_RESULT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800277b0`
- `0x1800390a0`
- `0x1800461b0`

## import_xrefs

- `fwbase!FwIsBuiltInPort` at `0x1800462a0`
- `fwbase!FwIsBuiltInPort` at `0x1800462a0`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x18004623b`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x18004623b`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x18004622e`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x18004622e`
- `fwbase!FwReportReturnError` at `0x1800462f8`
- `fwbase!FwReportReturnError` at `0x18004633b`
- `fwbase!FwReportReturnError` at `0x1800462f8`
- `fwbase!FwReportReturnError` at `0x18004633b`
- `FWPolicyIOMgr!FwWfProtocolToICFProtocol` at `0x180046291`
- `FWPolicyIOMgr!FwWfProtocolToICFProtocol` at `0x180046291`

## string_xrefs

- `0x1800462f1`: `FwOpenPortsEnum::GetVariant`
- `0x180046334`: `FwOpenPortsEnum::GetVariant`

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
0x1800461b0  mov     [rsp+arg_8], rbx
0x1800461b5  push    rbp
0x1800461b6  push    rsi
0x1800461b7  push    rdi
0x1800461b8  push    r12
0x1800461ba  push    r13
0x1800461bc  push    r14
0x1800461be  push    r15
0x1800461c0  sub     rsp, 70h
0x1800461c4  mov     rax, cs:__security_cookie
0x1800461cb  xor     rax, rsp
0x1800461ce  mov     [rsp+0A8h+var_48], rax
0x1800461d3  mov     eax, edx
0x1800461d5  mov     [rsp+0A8h+var_68], edx
0x1800461d9  xor     edx, edx
0x1800461db  mov     [rsp+0A8h+var_58], r8
0x1800461e0  xor     edi, edi
0x1800461e2  mov     [rsp+0A8h+var_78], edx
0x1800461e6  xor     ebx, ebx
0x1800461e8  mov     [rsp+0A8h+var_50], 6
0x1800461f0  mov     [rsp+0A8h+var_60], rdx
0x1800461f5  mov     r15, r9
0x1800461f8  mov     [rsp+0A8h+var_70], rdx
0x1800461fd  mov     rbp, rcx
0x180046200  lea     rsi, [rcx+68h]
0x180046204  lea     r12, [rcx+74h]
0x180046208  lea     r14, [rcx+70h]
0x18004620c  test    eax, eax
0x18004620e  jnz     short loc_18004621E
0x180046210  mov     rax, [rcx+58h]
0x180046214  mov     [rsi], rax
0x180046217  mov     [r14], edx
0x18004621a  mov     [r12], edx
0x18004621e  mov     r13d, [r14]
0x180046221  cmp     r13d, [rcx+60h]
0x180046225  jnb     loc_180046327
0x18004622b  mov     rcx, [rsi]
0x18004622e  call    cs:__imp_IsRuleOpenPortOrAuthApp
0x180046234  test    eax, eax
0x180046236  jz      short loc_180046265
0x180046238  mov     rcx, [rsi]
0x18004623b  call    cs:__imp_IsRuleOldGlobalOpenPort
0x180046241  test    eax, eax
0x180046243  jz      short loc_180046265
0x180046245  mov     ecx, [r12]
0x180046249  lea     eax, [rcx+1]
0x18004624c  mov     [r12], eax
0x180046250  cmp     [rsp+0A8h+var_68], ecx
0x180046254  jnz     short loc_180046265
0x180046256  mov     r8, [rsi]
0x180046259  mov     ebx, 1
0x18004625e  mov     [rsp+0A8h+var_70], r8
0x180046263  jmp     short loc_18004626A
0x180046265  mov     r8, [rsp+0A8h+var_70]
0x18004626a  mov     rax, [rsi]
0x18004626d  mov     rcx, [rax]
0x180046270  inc     dword ptr [r14]
0x180046273  mov     [rsi], rcx
0x180046276  cmp     ebx, 1
0x180046279  jnz     short loc_1800462AC
0x18004627b  mov     rax, [r8+48h]
0x18004627f  lea     rdx, [rsp+0A8h+var_50]
0x180046284  movzx   ecx, word ptr [r8+30h]
0x180046289  movzx   ebx, word ptr [rax]
0x18004628c  mov     word ptr [rsp+0A8h+var_78], bx
0x180046291  call    cs:__imp_FwWfProtocolToICFProtocol
0x180046297  mov     ecx, [rsp+0A8h+var_50]
0x18004629b  movzx   edx, bx
0x18004629e  mov     edi, eax
0x1800462a0  call    cs:__imp_FwIsBuiltInPort
0x1800462a6  test    eax, eax
0x1800462a8  jz      short loc_1800462BD
0x1800462aa  xor     ebx, ebx
0x1800462ac  inc     r13d
0x1800462af  cmp     r13d, [rbp+60h]
0x1800462b3  jb      loc_18004622B
0x1800462b9  test    ebx, ebx
0x1800462bb  jz      short loc_180046327
0x1800462bd  mov     r8d, [rsp+0A8h+var_50]
0x1800462c2  lea     rax, [rsp+0A8h+var_60]
0x1800462c7  mov     edx, [rsp+0A8h+var_78]
0x1800462cb  xor     r9d, r9d
0x1800462ce  mov     ecx, [rbp+48h]
0x1800462d1  mov     [rsp+0A8h+var_88], rax
0x1800462d6  call    ?CreateInstance@FwOpenPort@@SAJW4_tag_FW_PROFILE_TYPE@@GW4NET_FW_IP_PROTOCOL_@@QEAU_tag_FW_RULE@@PEAPEAV1@@Z; FwOpenPort::CreateInstance(_tag_FW_PROFILE_TYPE,ushort,NET_FW_IP_PROTOCOL_,_tag_FW_RULE * const,FwOpenPort * *)
0x1800462db  mov     edi, eax
0x1800462dd  cmp     eax, 8007000Dh
0x1800462e2  jz      short loc_18004631C
0x1800462e4  cmp     eax, 80070002h
0x1800462e9  jz      short loc_18004631C
0x1800462eb  test    eax, eax
0x1800462ed  jns     short loc_180046300
0x1800462ef  mov     edx, eax
0x1800462f1  lea     rcx, aFwopenportsenu; "FwOpenPortsEnum::GetVariant"
0x1800462f8  call    cs:__imp_FwReportReturnError
0x1800462fe  jmp     short loc_180046332
0x180046300  mov     rcx, [rsp+0A8h+var_58]
0x180046305  mov     rax, [rsp+0A8h+var_60]
0x18004630a  mov     word ptr [rcx], 9
0x18004630f  mov     [rcx+8], rax
0x180046313  mov     dword ptr [r15], 0
0x18004631a  jmp     short loc_18004632E
0x18004631c  mov     dword ptr [r15], 1
0x180046323  xor     edi, edi
0x180046325  jmp     short loc_18004632E
0x180046327  mov     dword ptr [r15], 2
0x18004632e  test    edi, edi
0x180046330  jns     short loc_180046343
0x180046332  mov     edx, edi
0x180046334  lea     rcx, aFwopenportsenu; "FwOpenPortsEnum::GetVariant"
0x18004633b  call    cs:__imp_FwReportReturnError
0x180046341  mov     edi, eax
0x180046343  mov     eax, edi
0x180046345  mov     rcx, [rsp+0A8h+var_48]
0x18004634a  xor     rcx, rsp; StackCookie
0x18004634d  call    __security_check_cookie
0x180046352  mov     rbx, [rsp+0A8h+arg_8]
0x18004635a  add     rsp, 70h
0x18004635e  pop     r15
0x180046360  pop     r14
0x180046362  pop     r13
0x180046364  pop     r12
0x180046366  pop     rdi
0x180046367  pop     rsi
0x180046368  pop     rbp
0x180046369  retn
```
