# FwOpenPorts::Add(INetFwOpenPort *)

- ea: `0x180048a20`
- end: `0x180048baf`
- name: `?Add@FwOpenPorts@@UEAAJPEAUINetFwOpenPort@@@Z`
- size: `399`
- prototype: `int(FwOpenPorts *__hidden this, struct INetFwOpenPort *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001edc`
- `0x1800294b0`
- `0x18002c02c`
- `0x18003097c`
- `0x180048a20`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180048b13`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180048b13`
- `fwbase!FwReportReturnError` at `0x180048a5e`
- `fwbase!FwReportReturnError` at `0x180048a97`
- `fwbase!FwReportReturnError` at `0x180048aac`
- `fwbase!FwReportReturnError` at `0x180048b59`
- `fwbase!FwReportReturnError` at `0x180048b77`
- `fwbase!FwReportReturnError` at `0x180048a5e`
- `fwbase!FwReportReturnError` at `0x180048a97`
- `fwbase!FwReportReturnError` at `0x180048aac`
- `fwbase!FwReportReturnError` at `0x180048b59`
- `fwbase!FwReportReturnError` at `0x180048b77`

## string_xrefs

- `0x180048a90`: `FwOpenPort::Narrow`
- `0x180048aa5`: `FwOpenPort::Narrow`
- `0x180048a57`: `FwOpenPorts::Add`
- `0x180048b52`: `FwOpenPorts::Add`
- `0x180048b70`: `FwOpenPorts::Add`

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
0x180048a20  mov     [rsp-18h+arg_10], rbx
0x180048a25  push    rbp
0x180048a26  push    rsi
0x180048a27  push    rdi
0x180048a28  mov     rbp, rsp
0x180048a2b  sub     rsp, 50h
0x180048a2f  mov     rax, cs:__security_cookie
0x180048a36  xor     rax, rsp
0x180048a39  mov     [rbp+var_10], rax
0x180048a3d  mov     rdi, rdx
0x180048a40  mov     rsi, rcx
0x180048a43  mov     [rbp+var_20], 0
0x180048a4b  test    rdx, rdx
0x180048a4e  jnz     short loc_180048A6F
0x180048a50  mov     ebx, 80004003h
0x180048a55  mov     edx, ebx
0x180048a57  lea     rcx, aFwopenportsAdd; "FwOpenPorts::Add"
0x180048a5e  call    cs:__imp_FwReportReturnError
0x180048a65  nop     dword ptr [rax+rax+00h]
0x180048a6a  jmp     loc_180048B6E
0x180048a6f  mov     rax, [rdx]
0x180048a72  lea     r8, [rbp+var_20]
0x180048a76  lea     rdx, _GUID_3b5a770c_910f_4628_8ae4_da3fdd060f52
0x180048a7d  mov     rcx, rdi
0x180048a80  mov     rax, [rax]
0x180048a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a88  mov     ebx, eax
0x180048a8a  test    eax, eax
0x180048a8c  jns     short loc_180048ABC
0x180048a8e  mov     edx, eax
0x180048a90  lea     rcx, aFwopenportNarr; "FwOpenPort::Narrow"
0x180048a97  call    cs:__imp_FwReportReturnError
0x180048a9e  nop     dword ptr [rax+rax+00h]
0x180048aa3  mov     edx, ebx
0x180048aa5  lea     rcx, aFwopenportNarr; "FwOpenPort::Narrow"
0x180048aac  call    cs:__imp_FwReportReturnError
0x180048ab3  nop     dword ptr [rax+rax+00h]
0x180048ab8  mov     ebx, eax
0x180048aba  jmp     short loc_180048ACD
0x180048abc  mov     rcx, [rbp+var_20]
0x180048ac0  mov     rax, [rcx]
0x180048ac3  mov     rax, [rax+10h]
0x180048ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048acc  nop
0x180048acd  test    ebx, ebx
0x180048acf  js      short loc_180048AEE
0x180048ad1  mov     edx, [rsi+18h]
0x180048ad4  mov     rcx, [rbp+var_20]
0x180048ad8  call    ?Add@FwOpenPort@@QEAAJW4_tag_FW_PROFILE_TYPE@@@Z; FwOpenPort::Add(_tag_FW_PROFILE_TYPE)
0x180048add  mov     ebx, eax
0x180048adf  test    eax, eax
0x180048ae1  jns     loc_180048B90
0x180048ae7  mov     edx, eax
0x180048ae9  jmp     loc_180048A57
0x180048aee  mov     [rbp+var_18], 0
0x180048af6  lea     rax, [rbp+var_18]
0x180048afa  mov     [rsp+50h+ppv], rax; ppv
0x180048aff  lea     r9, _GUID_e0483ba0_47ff_4d9c_a6d6_7741d0b195f7; riid
0x180048b06  xor     edx, edx; pUnkOuter
0x180048b08  lea     r8d, [rdx+1]; dwClsContext
0x180048b0c  lea     rcx, _GUID_0ca545c6_37ad_4a6c_bf92_9f7610067ef5; rclsid
0x180048b13  call    cs:__imp_CoCreateInstance
0x180048b1a  nop     dword ptr [rax+rax+00h]
0x180048b1f  mov     ebx, eax
0x180048b21  test    eax, eax
0x180048b23  js      short loc_180048B50
0x180048b25  mov     rdx, [rbp+var_18]; struct INetFwOpenPort *
0x180048b29  mov     rcx, rdi; struct INetFwOpenPort *
0x180048b2c  call    ?CopyINetFwOpenPort@@YAJPEAUINetFwOpenPort@@0@Z; CopyINetFwOpenPort(INetFwOpenPort *,INetFwOpenPort *)
0x180048b31  mov     ebx, eax
0x180048b33  test    eax, eax
0x180048b35  js      short loc_180048B50
0x180048b37  mov     rax, [rsi]
0x180048b3a  mov     rdx, [rbp+var_18]
0x180048b3e  mov     rcx, rsi
0x180048b41  mov     rax, [rax+40h]
0x180048b45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048b4a  mov     ebx, eax
0x180048b4c  test    eax, eax
0x180048b4e  jns     short loc_180048B87
0x180048b50  mov     edx, eax
0x180048b52  lea     rcx, aFwopenportsAdd; "FwOpenPorts::Add"
0x180048b59  call    cs:__imp_FwReportReturnError
0x180048b60  nop     dword ptr [rax+rax+00h]
0x180048b65  lea     rcx, [rbp+var_18]
0x180048b69  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180048b6e  mov     edx, ebx
0x180048b70  lea     rcx, aFwopenportsAdd; "FwOpenPorts::Add"
0x180048b77  call    cs:__imp_FwReportReturnError
0x180048b7e  nop     dword ptr [rax+rax+00h]
0x180048b83  mov     ebx, eax
0x180048b85  jmp     short loc_180048B90
0x180048b87  lea     rcx, [rbp+var_18]
0x180048b8b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180048b90  mov     eax, ebx
0x180048b92  mov     rcx, [rbp+var_10]
0x180048b96  xor     rcx, rsp; StackCookie
0x180048b99  call    __security_check_cookie
0x180048b9e  mov     rbx, [rsp+50h+arg_10]
0x180048ba6  add     rsp, 50h
0x180048baa  pop     rdi
0x180048bab  pop     rsi
0x180048bac  pop     rbp
0x180048bad  retn
```
