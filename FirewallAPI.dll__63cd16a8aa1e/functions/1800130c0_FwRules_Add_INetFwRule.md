# FwRules::Add(INetFwRule *)

- ea: `0x1800130c0`
- end: `0x180013220`
- name: `?Add@FwRules@@UEAAJPEAUINetFwRule@@@Z`
- size: `352`
- prototype: `__int64 __fastcall(FwRules *this, struct INetFwRule *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180013004`
- `0x1800130c0`
- `0x180013638`
- `0x1800277b0`
- `0x18002a2e0`
- `0x18002ebc8`
- `0x18003104c`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800131a9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800131a9`
- `fwbase!FwReportReturnError` at `0x180013177`
- `fwbase!FwReportReturnError` at `0x1800131fa`
- `fwbase!FwReportReturnError` at `0x180013213`
- `fwbase!FwReportReturnError` at `0x180013177`
- `fwbase!FwReportReturnError` at `0x1800131fa`
- `fwbase!FwReportReturnError` at `0x180013213`

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
0x1800130c0  mov     [rsp+arg_10], rbx
0x1800130c5  mov     [rsp+arg_18], rsi
0x1800130ca  push    rdi
0x1800130cb  sub     rsp, 50h
0x1800130cf  mov     rax, cs:__security_cookie
0x1800130d6  xor     rax, rsp
0x1800130d9  mov     [rsp+58h+var_18], rax
0x1800130de  mov     rdi, rdx
0x1800130e1  mov     [rsp+58h+var_28], 0
0x1800130ea  mov     rsi, rcx
0x1800130ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800130f4  lea     rax, WPP_GLOBAL_Control
0x1800130fb  cmp     rcx, rax
0x1800130fe  jz      short loc_180013106
0x180013100  test    byte ptr [rcx+1Ch], 8
0x180013104  jnz     short loc_18001314E
0x180013106  test    rdi, rdi
0x180013109  jz      short loc_180013165
0x18001310b  lea     rdx, [rsp+58h+var_28]; struct FwRule **
0x180013110  mov     rcx, rdi; struct INetFwRule *
0x180013113  call    ?Narrow@FwRule@@SAJPEAUINetFwRule@@PEAPEAV1@@Z; FwRule::Narrow(INetFwRule *,FwRule * *)
0x180013118  test    eax, eax
0x18001311a  js      short loc_180013182
0x18001311c  mov     edx, [rsi+18h]
0x18001311f  mov     rcx, [rsp+58h+var_28]
0x180013124  call    ?Add@FwRule@@QEAAJW4FwPolicyViewFlags@@@Z; FwRule::Add(FwPolicyViewFlags)
0x180013129  mov     ebx, eax
0x18001312b  test    eax, eax
0x18001312d  js      short loc_18001316E
0x18001312f  mov     eax, ebx
0x180013131  mov     rcx, [rsp+58h+var_18]
0x180013136  xor     rcx, rsp; StackCookie
0x180013139  call    __security_check_cookie
0x18001313e  mov     rbx, [rsp+58h+arg_10]
0x180013143  mov     rsi, [rsp+58h+arg_18]
0x180013148  add     rsp, 50h
0x18001314c  pop     rdi
0x18001314d  retn
0x18001314e  mov     rcx, [rcx+10h]
0x180013152  lea     r8, WPP_4cf7a87c86333f9f8c34ccce893540da_Traceguids
0x180013159  mov     edx, 0Bh
0x18001315e  call    WPP_SF_
0x180013163  jmp     short loc_180013106
0x180013165  mov     ebx, 80004003h
0x18001316a  mov     edx, ebx
0x18001316c  jmp     short loc_180013170
0x18001316e  mov     edx, eax
0x180013170  lea     rcx, aFwrulesAdd; "FwRules::Add"
0x180013177  call    cs:__imp_FwReportReturnError
0x18001317d  jmp     loc_18001320A
0x180013182  xor     edx, edx; pUnkOuter
0x180013184  mov     [rsp+58h+var_20], 0
0x18001318d  lea     rax, [rsp+58h+var_20]
0x180013192  lea     r9, _GUID_af230d27_baba_4e42_aced_f524f22cfce2; riid
0x180013199  mov     [rsp+58h+ppv], rax; ppv
0x18001319e  lea     rcx, _GUID_2c5bc43e_3369_4c33_ab0c_be9469677af4; rclsid
0x1800131a5  lea     r8d, [rdx+1]; dwClsContext
0x1800131a9  call    cs:__imp_CoCreateInstance
0x1800131af  mov     ebx, eax
0x1800131b1  test    eax, eax
0x1800131b3  js      short loc_1800131F1
0x1800131b5  mov     rdx, [rsp+58h+var_20]; struct INetFwRule *
0x1800131ba  mov     rcx, rdi; struct INetFwRule *
0x1800131bd  call    ?CopyINetFwRule@@YAJPEAUINetFwRule@@0@Z; CopyINetFwRule(INetFwRule *,INetFwRule *)
0x1800131c2  mov     ebx, eax
0x1800131c4  test    eax, eax
0x1800131c6  js      short loc_1800131F1
0x1800131c8  mov     rax, [rsi]
0x1800131cb  mov     rcx, rsi
0x1800131ce  mov     rdx, [rsp+58h+var_20]
0x1800131d3  mov     rax, [rax+40h]
0x1800131d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131dc  mov     ebx, eax
0x1800131de  test    eax, eax
0x1800131e0  js      short loc_1800131F1
0x1800131e2  lea     rcx, [rsp+58h+var_20]
0x1800131e7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800131ec  jmp     loc_18001312F
0x1800131f1  mov     edx, eax
0x1800131f3  lea     rcx, aFwrulesAdd; "FwRules::Add"
0x1800131fa  call    cs:__imp_FwReportReturnError
0x180013200  lea     rcx, [rsp+58h+var_20]
0x180013205  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001320a  mov     edx, ebx
0x18001320c  lea     rcx, aFwrulesAdd; "FwRules::Add"
0x180013213  call    cs:__imp_FwReportReturnError
0x180013219  mov     ebx, eax
0x18001321b  jmp     loc_18001312F
```
