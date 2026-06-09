# FwSvcPorts::CreateInstance(_tag_FW_PROFILE_TYPE,_tag_FW_RULE * * const,ulong,FwSvcPorts * *)

- ea: `0x180047958`
- end: `0x180047a60`
- name: `?CreateInstance@FwSvcPorts@@SAJW4_tag_FW_PROFILE_TYPE@@QEAPEAU_tag_FW_RULE@@KPEAPEAV1@@Z`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180046c60`

## callees

- `0x1800478ac`
- `0x180047958`
- `0x18005e010`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x1800479f0`
- `fwbase!FwReportReturnError` at `0x1800479ff`
- `fwbase!FwReportReturnError` at `0x180047a14`
- `fwbase!FwReportReturnError` at `0x180047a37`
- `fwbase!FwReportReturnError` at `0x1800479f0`
- `fwbase!FwReportReturnError` at `0x1800479ff`
- `fwbase!FwReportReturnError` at `0x180047a14`
- `fwbase!FwReportReturnError` at `0x180047a37`
- `FWPolicyIOMgr!FwCopyRule` at `0x1800479cb`
- `FWPolicyIOMgr!FwCopyRule` at `0x1800479cb`

## string_xrefs

- `0x180047a0d`: `FwSvcPorts::CreateInstance`
- `0x180047a30`: `FwSvcPorts::CreateInstance`

## pseudocode

```c
__int64 __fastcall FwSvcPorts::CreateInstance(int a1, __int64 a2, unsigned int a3, _QWORD *a4)
{
  int v8; // eax
  _DWORD *v9; // rdi
  unsigned int v10; // ebx
  __int64 v11; // rsi
  _QWORD *v12; // r14
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rdx
  _DWORD *v17; // [rsp+68h] [rbp+20h] BYREF

  v17 = 0;
  *a4 = 0;
  v8 = ATL::CComObject<FwSvcPorts>::CreateInstance(&v17);
  v9 = v17;
  v10 = v8;
  if ( v8 < 0 )
  {
LABEL_10:
    FwReportReturnError("FwSvcPorts::CreateInstance", (unsigned int)v8);
    if ( v9 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 16LL))(v9);
    return (unsigned int)FwReportReturnError("FwSvcPorts::CreateInstance", v10);
  }
  else
  {
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v17 + 8LL))(v17);
    v10 = 0;
    v9[6] = a1;
    v11 = 0;
    v12 = v9 + 8;
    while ( 1 )
    {
      if ( (unsigned int)v11 >= a3 )
      {
        v9[10] = a3;
        goto LABEL_14;
      }
      v13 = *(_QWORD *)(a2 + 8 * v11);
      if ( !v13 )
        break;
      v14 = FwCopyRule(v13, v12);
      v10 = v14;
      if ( v14 < 0 )
      {
        v15 = (unsigned int)v14;
        goto LABEL_9;
      }
      v12 = (_QWORD *)*v12;
      v11 = (unsigned int)(v11 + 1);
    }
    v10 = -2147418113;
    v15 = 2147549183LL;
LABEL_9:
    FwReportReturnError("FwSvcPorts::Initialize", v15);
    v8 = FwReportReturnError("FwSvcPorts::Initialize", v10);
    v10 = v8;
    if ( v8 < 0 )
      goto LABEL_10;
LABEL_14:
    *a4 = v9;
  }
  return v10;
}

```

## disassembly

```asm
0x180047958  mov     rax, rsp
0x18004795b  mov     [rax+8], rbx
0x18004795f  mov     [rax+10h], rbp
0x180047963  push    rsi
0x180047964  push    rdi
0x180047965  push    r12
0x180047967  push    r14
0x180047969  push    r15
0x18004796b  sub     rsp, 20h
0x18004796f  mov     esi, ecx
0x180047971  mov     qword ptr [rax+20h], 0
0x180047979  lea     rcx, [rax+20h]
0x18004797d  mov     qword ptr [r9], 0
0x180047984  mov     r15, r9
0x180047987  mov     ebp, r8d
0x18004798a  mov     r12, rdx
0x18004798d  call    ?CreateInstance@?$CComObject@VFwSvcPorts@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<FwSvcPorts>::CreateInstance(ATL::CComObject<FwSvcPorts> * *)
0x180047992  mov     rdi, [rsp+48h+arg_18]
0x180047997  mov     ebx, eax
0x180047999  test    eax, eax
0x18004799b  js      short loc_180047A0B
0x18004799d  mov     rax, [rdi]
0x1800479a0  mov     rcx, rdi
0x1800479a3  mov     rax, [rax+8]
0x1800479a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800479ac  xor     ebx, ebx
0x1800479ae  mov     [rdi+18h], esi
0x1800479b1  xor     esi, esi
0x1800479b3  lea     r14, [rdi+20h]
0x1800479b7  cmp     esi, ebp
0x1800479b9  jnb     loc_180047A41
0x1800479bf  mov     rcx, [r12+rsi*8]
0x1800479c3  test    rcx, rcx
0x1800479c6  jz      short loc_1800479E2
0x1800479c8  mov     rdx, r14
0x1800479cb  call    cs:__imp_FwCopyRule
0x1800479d1  mov     ebx, eax
0x1800479d3  test    eax, eax
0x1800479d5  js      short loc_1800479DE
0x1800479d7  mov     r14, [r14]
0x1800479da  inc     esi
0x1800479dc  jmp     short loc_1800479B7
0x1800479de  mov     edx, eax
0x1800479e0  jmp     short loc_1800479E9
0x1800479e2  mov     ebx, 8000FFFFh
0x1800479e7  mov     edx, ebx
0x1800479e9  lea     rcx, aFwsvcportsInit; "FwSvcPorts::Initialize"
0x1800479f0  call    cs:__imp_FwReportReturnError
0x1800479f6  mov     edx, ebx
0x1800479f8  lea     rcx, aFwsvcportsInit; "FwSvcPorts::Initialize"
0x1800479ff  call    cs:__imp_FwReportReturnError
0x180047a05  mov     ebx, eax
0x180047a07  test    eax, eax
0x180047a09  jns     short loc_180047A44
0x180047a0b  mov     edx, eax
0x180047a0d  lea     rcx, aFwsvcportsCrea; "FwSvcPorts::CreateInstance"
0x180047a14  call    cs:__imp_FwReportReturnError
0x180047a1a  test    rdi, rdi
0x180047a1d  jz      short loc_180047A2E
0x180047a1f  mov     rax, [rdi]
0x180047a22  mov     rcx, rdi
0x180047a25  mov     rax, [rax+10h]
0x180047a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047a2e  mov     edx, ebx
0x180047a30  lea     rcx, aFwsvcportsCrea; "FwSvcPorts::CreateInstance"
0x180047a37  call    cs:__imp_FwReportReturnError
0x180047a3d  mov     ebx, eax
0x180047a3f  jmp     short loc_180047A47
0x180047a41  mov     [rdi+28h], ebp
0x180047a44  mov     [r15], rdi
0x180047a47  mov     rbp, [rsp+48h+arg_8]
0x180047a4c  mov     eax, ebx
0x180047a4e  mov     rbx, [rsp+48h+arg_0]
0x180047a53  add     rsp, 20h
0x180047a57  pop     r15
0x180047a59  pop     r14
0x180047a5b  pop     r12
0x180047a5d  pop     rdi
0x180047a5e  pop     rsi
0x180047a5f  retn
```
