# FwOpenPorts::Add(INetFwOpenPort *)

- ea: `0x1800453d0`
- end: `0x18004553a`
- name: `?Add@FwOpenPorts@@UEAAJPEAUINetFwOpenPort@@@Z`
- size: `362`
- prototype: `int(FwOpenPorts *__hidden this, struct INetFwOpenPort *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001e58`
- `0x1800277b0`
- `0x18002a2e0`
- `0x18002e954`
- `0x1800453d0`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800454b1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800454b1`
- `fwbase!FwReportReturnError` at `0x18004540e`
- `fwbase!FwReportReturnError` at `0x180045441`
- `fwbase!FwReportReturnError` at `0x180045450`
- `fwbase!FwReportReturnError` at `0x1800454f1`
- `fwbase!FwReportReturnError` at `0x180045509`
- `fwbase!FwReportReturnError` at `0x18004540e`
- `fwbase!FwReportReturnError` at `0x180045441`
- `fwbase!FwReportReturnError` at `0x180045450`
- `fwbase!FwReportReturnError` at `0x1800454f1`
- `fwbase!FwReportReturnError` at `0x180045509`

## string_xrefs

- `0x18004543a`: `FwOpenPort::Narrow`
- `0x180045449`: `FwOpenPort::Narrow`
- `0x180045407`: `FwOpenPorts::Add`
- `0x1800454ea`: `FwOpenPorts::Add`
- `0x180045502`: `FwOpenPorts::Add`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FwOpenPorts::Add(FwOpenPorts *this, struct INetFwOpenPort *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int v6; // eax
  int v7; // ebx
  int v8; // eax
  HRESULT Instance; // eax
  __int64 v11; // [rsp+30h] [rbp-20h] BYREF
  struct INetFwOpenPort *ppv; // [rsp+38h] [rbp-18h] BYREF

  v11 = 0;
  if ( !a2 )
  {
    v4 = -2147467261;
    v5 = 2147500035LL;
LABEL_3:
    FwReportReturnError("FwOpenPorts::Add", v5);
    return (unsigned int)FwReportReturnError("FwOpenPorts::Add", v4);
  }
  v6 = ((__int64 (__fastcall *)(struct INetFwOpenPort *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_3b5a770c_910f_4628_8ae4_da3fdd060f52,
         &v11);
  v7 = v6;
  if ( v6 >= 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  else
  {
    FwReportReturnError("FwOpenPort::Narrow", (unsigned int)v6);
    v7 = FwReportReturnError("FwOpenPort::Narrow", (unsigned int)v7);
  }
  if ( v7 < 0 )
  {
    ppv = 0;
    Instance = CoCreateInstance(
                 &GUID_0ca545c6_37ad_4a6c_bf92_9f7610067ef5,
                 0,
                 1u,
                 &GUID_e0483ba0_47ff_4d9c_a6d6_7741d0b195f7,
                 (LPVOID *)&ppv);
    v4 = Instance;
    if ( Instance >= 0 )
    {
      Instance = CopyINetFwOpenPort(a2, ppv);
      v4 = Instance;
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(FwOpenPorts *, struct INetFwOpenPort *))(*(_QWORD *)this + 64LL))(
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
    FwReportReturnError("FwOpenPorts::Add", (unsigned int)Instance);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
    return (unsigned int)FwReportReturnError("FwOpenPorts::Add", v4);
  }
  v8 = FwOpenPort::Add(v11, *((_DWORD *)this + 6));
  v4 = v8;
  if ( v8 < 0 )
  {
    v5 = (unsigned int)v8;
    goto LABEL_3;
  }
  return v4;
}

```

## disassembly

```asm
0x1800453d0  mov     [rsp-18h+arg_10], rbx
0x1800453d5  push    rbp
0x1800453d6  push    rsi
0x1800453d7  push    rdi
0x1800453d8  mov     rbp, rsp
0x1800453db  sub     rsp, 50h
0x1800453df  mov     rax, cs:__security_cookie
0x1800453e6  xor     rax, rsp
0x1800453e9  mov     [rbp+var_10], rax
0x1800453ed  mov     rdi, rdx
0x1800453f0  mov     rsi, rcx
0x1800453f3  mov     [rbp+var_20], 0
0x1800453fb  test    rdx, rdx
0x1800453fe  jnz     short loc_180045419
0x180045400  mov     ebx, 80004003h
0x180045405  mov     edx, ebx
0x180045407  lea     rcx, aFwopenportsAdd; "FwOpenPorts::Add"
0x18004540e  call    cs:__imp_FwReportReturnError
0x180045414  jmp     loc_180045500
0x180045419  mov     rax, [rdx]
0x18004541c  lea     r8, [rbp+var_20]
0x180045420  lea     rdx, _GUID_3b5a770c_910f_4628_8ae4_da3fdd060f52
0x180045427  mov     rcx, rdi
0x18004542a  mov     rax, [rax]
0x18004542d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045432  mov     ebx, eax
0x180045434  test    eax, eax
0x180045436  jns     short loc_18004545A
0x180045438  mov     edx, eax
0x18004543a  lea     rcx, aFwopenportNarr; "FwOpenPort::Narrow"
0x180045441  call    cs:__imp_FwReportReturnError
0x180045447  mov     edx, ebx
0x180045449  lea     rcx, aFwopenportNarr; "FwOpenPort::Narrow"
0x180045450  call    cs:__imp_FwReportReturnError
0x180045456  mov     ebx, eax
0x180045458  jmp     short loc_18004546B
0x18004545a  mov     rcx, [rbp+var_20]
0x18004545e  mov     rax, [rcx]
0x180045461  mov     rax, [rax+10h]
0x180045465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004546a  nop
0x18004546b  test    ebx, ebx
0x18004546d  js      short loc_18004548C
0x18004546f  mov     edx, [rsi+18h]
0x180045472  mov     rcx, [rbp+var_20]
0x180045476  call    ?Add@FwOpenPort@@QEAAJW4_tag_FW_PROFILE_TYPE@@@Z; FwOpenPort::Add(_tag_FW_PROFILE_TYPE)
0x18004547b  mov     ebx, eax
0x18004547d  test    eax, eax
0x18004547f  jns     loc_18004551C
0x180045485  mov     edx, eax
0x180045487  jmp     loc_180045407
0x18004548c  mov     [rbp+var_18], 0
0x180045494  lea     rax, [rbp+var_18]
0x180045498  mov     [rsp+50h+ppv], rax; ppv
0x18004549d  lea     r9, _GUID_e0483ba0_47ff_4d9c_a6d6_7741d0b195f7; riid
0x1800454a4  xor     edx, edx; pUnkOuter
0x1800454a6  lea     r8d, [rdx+1]; dwClsContext
0x1800454aa  lea     rcx, _GUID_0ca545c6_37ad_4a6c_bf92_9f7610067ef5; rclsid
0x1800454b1  call    cs:__imp_CoCreateInstance
0x1800454b7  mov     ebx, eax
0x1800454b9  test    eax, eax
0x1800454bb  js      short loc_1800454E8
0x1800454bd  mov     rdx, [rbp+var_18]; struct INetFwOpenPort *
0x1800454c1  mov     rcx, rdi; struct INetFwOpenPort *
0x1800454c4  call    ?CopyINetFwOpenPort@@YAJPEAUINetFwOpenPort@@0@Z; CopyINetFwOpenPort(INetFwOpenPort *,INetFwOpenPort *)
0x1800454c9  mov     ebx, eax
0x1800454cb  test    eax, eax
0x1800454cd  js      short loc_1800454E8
0x1800454cf  mov     rax, [rsi]
0x1800454d2  mov     rdx, [rbp+var_18]
0x1800454d6  mov     rcx, rsi
0x1800454d9  mov     rax, [rax+40h]
0x1800454dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800454e2  mov     ebx, eax
0x1800454e4  test    eax, eax
0x1800454e6  jns     short loc_180045513
0x1800454e8  mov     edx, eax
0x1800454ea  lea     rcx, aFwopenportsAdd; "FwOpenPorts::Add"
0x1800454f1  call    cs:__imp_FwReportReturnError
0x1800454f7  lea     rcx, [rbp+var_18]
0x1800454fb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180045500  mov     edx, ebx
0x180045502  lea     rcx, aFwopenportsAdd; "FwOpenPorts::Add"
0x180045509  call    cs:__imp_FwReportReturnError
0x18004550f  mov     ebx, eax
0x180045511  jmp     short loc_18004551C
0x180045513  lea     rcx, [rbp+var_18]
0x180045517  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004551c  mov     eax, ebx
0x18004551e  mov     rcx, [rbp+var_10]
0x180045522  xor     rcx, rsp; StackCookie
0x180045525  call    __security_check_cookie
0x18004552a  mov     rbx, [rsp+50h+arg_10]
0x180045532  add     rsp, 50h
0x180045536  pop     rdi
0x180045537  pop     rsi
0x180045538  pop     rbp
0x180045539  retn
```
