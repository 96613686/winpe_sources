# FwService::get_RemoteAddresses(ushort * *)

- ea: `0x180046dc0`
- end: `0x180046e8e`
- name: `?get_RemoteAddresses@FwService@@UEAAJPEAPEAG@Z`
- size: `206`
- prototype: `__int64 __fastcall(FwService *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x1800277b0`
- `0x1800284c4`
- `0x180046744`
- `0x1800468f8`
- `0x180046dc0`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x180046e4a`
- `fwbase!FwReportReturnError` at `0x180046e64`
- `fwbase!FwReportReturnError` at `0x180046e4a`
- `fwbase!FwReportReturnError` at `0x180046e64`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAsBSTR` at `0x180046e39`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAsBSTR` at `0x180046e39`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180046e55`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180046e55`

## string_xrefs

- `0x180046df4`: `FwService::get_RemoteAddresses`

## pseudocode

```c
__int64 __fastcall FwService::get_RemoteAddresses(FwService *this, unsigned __int16 **a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  int RemoteAddrs; // eax
  _BYTE v8[80]; // [rsp+20h] [rbp-78h] BYREF

  memset_0(v8, 0, 0x48u);
  if ( !a2 )
  {
    v4 = -2147467261;
    v5 = 2147500035LL;
LABEL_7:
    FwReportReturnError("FwService::get_RemoteAddresses", v5);
    goto LABEL_8;
  }
  *a2 = 0;
  RemoteAddrs = FwService::PerformLazyInitialization(this);
  v4 = RemoteAddrs;
  if ( RemoteAddrs < 0
    || (RemoteAddrs = FwService::GetRemoteAddrs(this, (struct _tag_FW_ADDRESSES *)v8), v4 = RemoteAddrs, RemoteAddrs < 0)
    || (RemoteAddrs = GetOpenPortorAuthAppAsBSTR(v8, a2), v4 = RemoteAddrs, RemoteAddrs < 0) )
  {
    v5 = (unsigned int)RemoteAddrs;
    goto LABEL_7;
  }
LABEL_8:
  FwPolioEmptyWFAddresses(v8);
  if ( v4 < 0 )
    return (unsigned int)FwReportReturnError("FwService::get_RemoteAddresses", (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180046dc0  mov     [rsp+arg_10], rbx
0x180046dc5  push    rbp
0x180046dc6  push    rsi
0x180046dc7  push    rdi
0x180046dc8  sub     rsp, 80h
0x180046dcf  mov     rax, cs:__security_cookie
0x180046dd6  xor     rax, rsp
0x180046dd9  mov     [rsp+98h+var_28], rax
0x180046dde  mov     rdi, rdx
0x180046de1  mov     rsi, rcx
0x180046de4  xor     edx, edx; Val
0x180046de6  lea     rcx, [rsp+98h+var_78]; void *
0x180046deb  lea     r8d, [rdx+48h]; Size
0x180046def  call    memset_0
0x180046df4  lea     rbp, aFwserviceGetRe; "FwService::get_RemoteAddresses"
0x180046dfb  test    rdi, rdi
0x180046dfe  jnz     short loc_180046E09
0x180046e00  mov     ebx, 80004003h
0x180046e05  mov     edx, ebx
0x180046e07  jmp     short loc_180046E47
0x180046e09  mov     rcx, rsi; this
0x180046e0c  mov     qword ptr [rdi], 0
0x180046e13  call    ?PerformLazyInitialization@FwService@@AEAAJXZ; FwService::PerformLazyInitialization(void)
0x180046e18  mov     ebx, eax
0x180046e1a  test    eax, eax
0x180046e1c  js      short loc_180046E45
0x180046e1e  lea     rdx, [rsp+98h+var_78]; struct _tag_FW_ADDRESSES *
0x180046e23  mov     rcx, rsi; this
0x180046e26  call    ?GetRemoteAddrs@FwService@@AEAAJPEAU_tag_FW_ADDRESSES@@@Z; FwService::GetRemoteAddrs(_tag_FW_ADDRESSES *)
0x180046e2b  mov     ebx, eax
0x180046e2d  test    eax, eax
0x180046e2f  js      short loc_180046E45
0x180046e31  mov     rdx, rdi
0x180046e34  lea     rcx, [rsp+98h+var_78]
0x180046e39  call    cs:__imp_GetOpenPortorAuthAppAsBSTR
0x180046e3f  mov     ebx, eax
0x180046e41  test    eax, eax
0x180046e43  jns     short loc_180046E50
0x180046e45  mov     edx, eax
0x180046e47  mov     rcx, rbp
0x180046e4a  call    cs:__imp_FwReportReturnError
0x180046e50  lea     rcx, [rsp+98h+var_78]
0x180046e55  call    cs:__imp_FwPolioEmptyWFAddresses
0x180046e5b  test    ebx, ebx
0x180046e5d  jns     short loc_180046E6C
0x180046e5f  mov     edx, ebx
0x180046e61  mov     rcx, rbp
0x180046e64  call    cs:__imp_FwReportReturnError
0x180046e6a  mov     ebx, eax
0x180046e6c  mov     eax, ebx
0x180046e6e  mov     rcx, [rsp+98h+var_28]
0x180046e73  xor     rcx, rsp; StackCookie
0x180046e76  call    __security_check_cookie
0x180046e7b  mov     rbx, [rsp+98h+arg_10]
0x180046e83  add     rsp, 80h
0x180046e8a  pop     rdi
0x180046e8b  pop     rsi
0x180046e8c  pop     rbp
0x180046e8d  retn
```
