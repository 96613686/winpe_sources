# FwRules::Add(INetFwRule *)

- ea: `0x180013020`
- end: `0x180013199`
- name: `?Add@FwRules@@UEAAJPEAUINetFwRule@@@Z`
- size: `377`
- prototype: `int(FwRules *__hidden this, struct INetFwRule *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012f58`
- `0x180013020`
- `0x1800135e4`
- `0x1800294b0`
- `0x18002c02c`
- `0x180030c08`
- `0x18003336c`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013110`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013110`
- `fwbase!FwReportReturnError` at `0x1800130d8`
- `fwbase!FwReportReturnError` at `0x180013167`
- `fwbase!FwReportReturnError` at `0x180013186`
- `fwbase!FwReportReturnError` at `0x1800130d8`
- `fwbase!FwReportReturnError` at `0x180013167`
- `fwbase!FwReportReturnError` at `0x180013186`

## pseudocode

```c
__int64 __fastcall FwRules::Add(FwRules *this, struct INetFwRule *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v7; // rdx
  HRESULT Instance; // eax
  struct FwRule *v9; // [rsp+30h] [rbp-28h] BYREF
  struct INetFwRule *ppv; // [rsp+38h] [rbp-20h] BYREF

  v9 = 0;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_4cf7a87c86333f9f8c34ccce893540da_Traceguids);
  if ( !a2 )
  {
    v5 = -2147467261;
    v7 = 2147500035LL;
LABEL_10:
    FwReportReturnError("FwRules::Add", v7);
    return (unsigned int)FwReportReturnError("FwRules::Add", v5);
  }
  if ( (int)FwRule::Narrow(a2, &v9) < 0 )
  {
    ppv = 0;
    Instance = CoCreateInstance(
                 &GUID_2c5bc43e_3369_4c33_ab0c_be9469677af4,
                 0,
                 1u,
                 &GUID_af230d27_baba_4e42_aced_f524f22cfce2,
                 (LPVOID *)&ppv);
    v5 = Instance;
    if ( Instance >= 0 )
    {
      Instance = CopyINetFwRule(a2, ppv);
      v5 = Instance;
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(FwRules *, struct INetFwRule *))(*(_QWORD *)this + 64LL))(this, ppv);
        v5 = Instance;
        if ( Instance >= 0 )
        {
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
          return v5;
        }
      }
    }
    FwReportReturnError("FwRules::Add", (unsigned int)Instance);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
    return (unsigned int)FwReportReturnError("FwRules::Add", v5);
  }
  v4 = FwRule::Add(v9, *((unsigned int *)this + 6));
  v5 = v4;
  if ( v4 < 0 )
  {
    v7 = (unsigned int)v4;
    goto LABEL_10;
  }
  return v5;
}

```

## disassembly

```asm
0x180013020  mov     [rsp+arg_10], rbx
0x180013025  mov     [rsp+arg_18], rsi
0x18001302a  push    rdi
0x18001302b  sub     rsp, 50h
0x18001302f  mov     rax, cs:__security_cookie
0x180013036  xor     rax, rsp
0x180013039  mov     [rsp+58h+var_18], rax
0x18001303e  mov     rdi, rdx
0x180013041  mov     [rsp+58h+var_28], 0
0x18001304a  mov     rsi, rcx
0x18001304d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013054  lea     rax, WPP_GLOBAL_Control
0x18001305b  cmp     rcx, rax
0x18001305e  jz      short loc_180013066
0x180013060  test    byte ptr [rcx+1Ch], 8
0x180013064  jnz     short loc_1800130AF
0x180013066  test    rdi, rdi
0x180013069  jz      short loc_1800130C6
0x18001306b  lea     rdx, [rsp+58h+var_28]; struct FwRule **
0x180013070  mov     rcx, rdi; struct INetFwRule *
0x180013073  call    ?Narrow@FwRule@@SAJPEAUINetFwRule@@PEAPEAV1@@Z; FwRule::Narrow(INetFwRule *,FwRule * *)
0x180013078  test    eax, eax
0x18001307a  js      short loc_1800130E9
0x18001307c  mov     edx, [rsi+18h]
0x18001307f  mov     rcx, [rsp+58h+var_28]
0x180013084  call    ?Add@FwRule@@QEAAJW4FwPolicyViewFlags@@@Z; FwRule::Add(FwPolicyViewFlags)
0x180013089  mov     ebx, eax
0x18001308b  test    eax, eax
0x18001308d  js      short loc_1800130CF
0x18001308f  mov     eax, ebx
0x180013091  mov     rcx, [rsp+58h+var_18]
0x180013096  xor     rcx, rsp; StackCookie
0x180013099  call    __security_check_cookie
0x18001309e  mov     rbx, [rsp+58h+arg_10]
0x1800130a3  mov     rsi, [rsp+58h+arg_18]
0x1800130a8  add     rsp, 50h
0x1800130ac  pop     rdi
0x1800130ad  retn
0x1800130af  mov     rcx, [rcx+10h]
0x1800130b3  lea     r8, WPP_4cf7a87c86333f9f8c34ccce893540da_Traceguids
0x1800130ba  mov     edx, 0Bh
0x1800130bf  call    WPP_SF_
0x1800130c4  jmp     short loc_180013066
0x1800130c6  mov     ebx, 80004003h
0x1800130cb  mov     edx, ebx
0x1800130cd  jmp     short loc_1800130D1
0x1800130cf  mov     edx, eax
0x1800130d1  lea     rcx, aFwrulesAdd; "FwRules::Add"
0x1800130d8  call    cs:__imp_FwReportReturnError
0x1800130df  nop     dword ptr [rax+rax+00h]
0x1800130e4  jmp     loc_18001317D
0x1800130e9  xor     edx, edx; pUnkOuter
0x1800130eb  mov     [rsp+58h+var_20], 0
0x1800130f4  lea     rax, [rsp+58h+var_20]
0x1800130f9  lea     r9, _GUID_af230d27_baba_4e42_aced_f524f22cfce2; riid
0x180013100  mov     [rsp+58h+ppv], rax; ppv
0x180013105  lea     rcx, _GUID_2c5bc43e_3369_4c33_ab0c_be9469677af4; rclsid
0x18001310c  lea     r8d, [rdx+1]; dwClsContext
0x180013110  call    cs:__imp_CoCreateInstance
0x180013117  nop     dword ptr [rax+rax+00h]
0x18001311c  mov     ebx, eax
0x18001311e  test    eax, eax
0x180013120  js      short loc_18001315E
0x180013122  mov     rdx, [rsp+58h+var_20]; struct INetFwRule *
0x180013127  mov     rcx, rdi; struct INetFwRule *
0x18001312a  call    ?CopyINetFwRule@@YAJPEAUINetFwRule@@0@Z; CopyINetFwRule(INetFwRule *,INetFwRule *)
0x18001312f  mov     ebx, eax
0x180013131  test    eax, eax
0x180013133  js      short loc_18001315E
0x180013135  mov     rax, [rsi]
0x180013138  mov     rcx, rsi
0x18001313b  mov     rdx, [rsp+58h+var_20]
0x180013140  mov     rax, [rax+40h]
0x180013144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013149  mov     ebx, eax
0x18001314b  test    eax, eax
0x18001314d  js      short loc_18001315E
0x18001314f  lea     rcx, [rsp+58h+var_20]
0x180013154  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180013159  jmp     loc_18001308F
0x18001315e  mov     edx, eax
0x180013160  lea     rcx, aFwrulesAdd; "FwRules::Add"
0x180013167  call    cs:__imp_FwReportReturnError
0x18001316e  nop     dword ptr [rax+rax+00h]
0x180013173  lea     rcx, [rsp+58h+var_20]
0x180013178  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001317d  mov     edx, ebx
0x18001317f  lea     rcx, aFwrulesAdd; "FwRules::Add"
0x180013186  call    cs:__imp_FwReportReturnError
0x18001318d  nop     dword ptr [rax+rax+00h]
0x180013192  mov     ebx, eax
0x180013194  jmp     loc_18001308F
```
