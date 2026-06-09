# FwAuthApps::Add(INetFwAuthorizedApplication *)

- ea: `0x180020fb0`
- end: `0x1800210dc`
- name: `?Add@FwAuthApps@@UEAAJPEAUINetFwAuthorizedApplication@@@Z`
- size: `300`
- prototype: `int(FwAuthApps *__hidden this, struct INetFwAuthorizedApplication *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180020fb0`
- `0x180023c6c`
- `0x180025014`
- `0x1800277b0`
- `0x18002a2e0`
- `0x18002e714`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002104e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002104e`
- `fwbase!FwReportReturnError` at `0x180020ff0`
- `fwbase!FwReportReturnError` at `0x180021090`
- `fwbase!FwReportReturnError` at `0x1800210a9`
- `fwbase!FwReportReturnError` at `0x180020ff0`
- `fwbase!FwReportReturnError` at `0x180021090`
- `fwbase!FwReportReturnError` at `0x1800210a9`

## pseudocode

```c
__int64 __fastcall FwAuthApps::Add(FwAuthApps *this, struct INetFwAuthorizedApplication *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int v6; // eax
  HRESULT Instance; // eax
  struct FwAuthApp *v9; // [rsp+30h] [rbp-28h] BYREF
  struct INetFwAuthorizedApplication *ppv; // [rsp+38h] [rbp-20h] BYREF

  v9 = 0;
  if ( !a2 )
  {
    v4 = -2147467261;
    v5 = 2147500035LL;
LABEL_3:
    FwReportReturnError("FwAuthApps::Add", v5);
    return (unsigned int)FwReportReturnError("FwAuthApps::Add", v4);
  }
  if ( (int)FwAuthApp::Narrow(a2, &v9) < 0 )
  {
    ppv = 0;
    Instance = CoCreateInstance(
                 &GUID_ec9846b3_2762_4a6b_a214_6acb603462d2,
                 0,
                 1u,
                 &GUID_b5e64ffa_c2c5_444e_a301_fb5e00018050,
                 (LPVOID *)&ppv);
    v4 = Instance;
    if ( Instance >= 0 )
    {
      Instance = CopyINetFwAuthorizedApplication(a2, ppv);
      v4 = Instance;
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(FwAuthApps *, struct INetFwAuthorizedApplication *))(*(_QWORD *)this + 64LL))(
                     this,
                     ppv);
        v4 = Instance;
        if ( Instance >= 0 )
        {
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
          return v4;
        }
      }
    }
    FwReportReturnError("FwAuthApps::Add", (unsigned int)Instance);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
    return (unsigned int)FwReportReturnError("FwAuthApps::Add", v4);
  }
  v6 = FwAuthApp::Add(v9, *((unsigned int *)this + 6));
  v4 = v6;
  if ( v6 < 0 )
  {
    v5 = (unsigned int)v6;
    goto LABEL_3;
  }
  return v4;
}

```

## disassembly

```asm
0x180020fb0  mov     [rsp+arg_10], rbx
0x180020fb5  mov     [rsp+arg_18], rsi
0x180020fba  push    rdi
0x180020fbb  sub     rsp, 50h
0x180020fbf  mov     rax, cs:__security_cookie
0x180020fc6  xor     rax, rsp
0x180020fc9  mov     [rsp+58h+var_18], rax
0x180020fce  mov     [rsp+58h+var_28], 0
0x180020fd7  mov     rdi, rdx
0x180020fda  mov     rsi, rcx
0x180020fdd  test    rdx, rdx
0x180020fe0  jnz     short loc_180020FFB
0x180020fe2  mov     ebx, 80004003h
0x180020fe7  mov     edx, ebx
0x180020fe9  lea     rcx, aFwauthappsAdd; "FwAuthApps::Add"
0x180020ff0  call    cs:__imp_FwReportReturnError
0x180020ff6  jmp     loc_1800210A0
0x180020ffb  lea     rdx, [rsp+58h+var_28]; struct FwAuthApp **
0x180021000  mov     rcx, rdi; struct INetFwAuthorizedApplication *
0x180021003  call    ?Narrow@FwAuthApp@@SAJPEAUINetFwAuthorizedApplication@@PEAPEAV1@@Z; FwAuthApp::Narrow(INetFwAuthorizedApplication *,FwAuthApp * *)
0x180021008  test    eax, eax
0x18002100a  js      short loc_180021027
0x18002100c  mov     edx, [rsi+18h]
0x18002100f  mov     rcx, [rsp+58h+var_28]
0x180021014  call    ?Add@FwAuthApp@@QEAAJW4_tag_FW_PROFILE_TYPE@@@Z; FwAuthApp::Add(_tag_FW_PROFILE_TYPE)
0x180021019  mov     ebx, eax
0x18002101b  test    eax, eax
0x18002101d  jns     loc_1800210BD
0x180021023  mov     edx, eax
0x180021025  jmp     short loc_180020FE9
0x180021027  xor     edx, edx; pUnkOuter
0x180021029  mov     [rsp+58h+var_20], 0
0x180021032  lea     rax, [rsp+58h+var_20]
0x180021037  lea     r9, _GUID_b5e64ffa_c2c5_444e_a301_fb5e00018050; riid
0x18002103e  mov     [rsp+58h+ppv], rax; ppv
0x180021043  lea     rcx, _GUID_ec9846b3_2762_4a6b_a214_6acb603462d2; rclsid
0x18002104a  lea     r8d, [rdx+1]; dwClsContext
0x18002104e  call    cs:__imp_CoCreateInstance
0x180021054  mov     ebx, eax
0x180021056  test    eax, eax
0x180021058  js      short loc_180021087
0x18002105a  mov     rdx, [rsp+58h+var_20]; struct INetFwAuthorizedApplication *
0x18002105f  mov     rcx, rdi; struct INetFwAuthorizedApplication *
0x180021062  call    ?CopyINetFwAuthorizedApplication@@YAJPEAUINetFwAuthorizedApplication@@0@Z; CopyINetFwAuthorizedApplication(INetFwAuthorizedApplication *,INetFwAuthorizedApplication *)
0x180021067  mov     ebx, eax
0x180021069  test    eax, eax
0x18002106b  js      short loc_180021087
0x18002106d  mov     rax, [rsi]
0x180021070  mov     rcx, rsi
0x180021073  mov     rdx, [rsp+58h+var_20]
0x180021078  mov     rax, [rax+40h]
0x18002107c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021081  mov     ebx, eax
0x180021083  test    eax, eax
0x180021085  jns     short loc_1800210B3
0x180021087  mov     edx, eax
0x180021089  lea     rcx, aFwauthappsAdd; "FwAuthApps::Add"
0x180021090  call    cs:__imp_FwReportReturnError
0x180021096  lea     rcx, [rsp+58h+var_20]
0x18002109b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800210a0  mov     edx, ebx
0x1800210a2  lea     rcx, aFwauthappsAdd; "FwAuthApps::Add"
0x1800210a9  call    cs:__imp_FwReportReturnError
0x1800210af  mov     ebx, eax
0x1800210b1  jmp     short loc_1800210BD
0x1800210b3  lea     rcx, [rsp+58h+var_20]
0x1800210b8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800210bd  mov     eax, ebx
0x1800210bf  mov     rcx, [rsp+58h+var_18]
0x1800210c4  xor     rcx, rsp; StackCookie
0x1800210c7  call    __security_check_cookie
0x1800210cc  mov     rbx, [rsp+58h+arg_10]
0x1800210d1  mov     rsi, [rsp+58h+arg_18]
0x1800210d6  add     rsp, 50h
0x1800210da  pop     rdi
0x1800210db  retn
```
