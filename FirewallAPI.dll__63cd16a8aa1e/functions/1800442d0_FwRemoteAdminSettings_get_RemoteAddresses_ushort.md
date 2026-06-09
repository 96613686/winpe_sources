# FwRemoteAdminSettings::get_RemoteAddresses(ushort * *)

- ea: `0x1800442d0`
- end: `0x18004439e`
- name: `?get_RemoteAddresses@FwRemoteAdminSettings@@UEAAJPEAPEAG@Z`
- size: `206`
- prototype: `__int64 __fastcall(FwRemoteAdminSettings *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1800277b0`
- `0x1800284c4`
- `0x180043e24`
- `0x180043fc8`
- `0x1800442d0`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x18004435a`
- `fwbase!FwReportReturnError` at `0x180044374`
- `fwbase!FwReportReturnError` at `0x18004435a`
- `fwbase!FwReportReturnError` at `0x180044374`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAsBSTR` at `0x180044349`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAsBSTR` at `0x180044349`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180044365`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180044365`

## pseudocode

```c
__int64 __fastcall FwRemoteAdminSettings::get_RemoteAddresses(FwRemoteAdminSettings *this, unsigned __int16 **a2)
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
    FwReportReturnError("FwRemoteAdminSettings::get_RemoteAddresses", v5);
    goto LABEL_8;
  }
  *a2 = 0;
  RemoteAddrs = FwRemoteAdminSettings::PerformLazyInitialization(this);
  v4 = RemoteAddrs;
  if ( RemoteAddrs < 0
    || (RemoteAddrs = FwRemoteAdminSettings::GetRemoteAddrs(this, (struct _tag_FW_ADDRESSES *)v8),
        v4 = RemoteAddrs,
        RemoteAddrs < 0)
    || (RemoteAddrs = GetOpenPortorAuthAppAsBSTR(v8, a2), v4 = RemoteAddrs, RemoteAddrs < 0) )
  {
    v5 = (unsigned int)RemoteAddrs;
    goto LABEL_7;
  }
LABEL_8:
  FwPolioEmptyWFAddresses(v8);
  if ( v4 < 0 )
    return (unsigned int)FwReportReturnError("FwRemoteAdminSettings::get_RemoteAddresses", (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800442d0  mov     [rsp+arg_10], rbx
0x1800442d5  push    rbp
0x1800442d6  push    rsi
0x1800442d7  push    rdi
0x1800442d8  sub     rsp, 80h
0x1800442df  mov     rax, cs:__security_cookie
0x1800442e6  xor     rax, rsp
0x1800442e9  mov     [rsp+98h+var_28], rax
0x1800442ee  mov     rdi, rdx
0x1800442f1  mov     rsi, rcx
0x1800442f4  xor     edx, edx; Val
0x1800442f6  lea     rcx, [rsp+98h+var_78]; void *
0x1800442fb  lea     r8d, [rdx+48h]; Size
0x1800442ff  call    memset_0
0x180044304  lea     rbp, aFwremoteadmins; "FwRemoteAdminSettings::get_RemoteAddres"...
0x18004430b  test    rdi, rdi
0x18004430e  jnz     short loc_180044319
0x180044310  mov     ebx, 80004003h
0x180044315  mov     edx, ebx
0x180044317  jmp     short loc_180044357
0x180044319  mov     rcx, rsi; this
0x18004431c  mov     qword ptr [rdi], 0
0x180044323  call    ?PerformLazyInitialization@FwRemoteAdminSettings@@AEAAJXZ; FwRemoteAdminSettings::PerformLazyInitialization(void)
0x180044328  mov     ebx, eax
0x18004432a  test    eax, eax
0x18004432c  js      short loc_180044355
0x18004432e  lea     rdx, [rsp+98h+var_78]; struct _tag_FW_ADDRESSES *
0x180044333  mov     rcx, rsi; this
0x180044336  call    ?GetRemoteAddrs@FwRemoteAdminSettings@@AEAAJPEAU_tag_FW_ADDRESSES@@@Z; FwRemoteAdminSettings::GetRemoteAddrs(_tag_FW_ADDRESSES *)
0x18004433b  mov     ebx, eax
0x18004433d  test    eax, eax
0x18004433f  js      short loc_180044355
0x180044341  mov     rdx, rdi
0x180044344  lea     rcx, [rsp+98h+var_78]
0x180044349  call    cs:__imp_GetOpenPortorAuthAppAsBSTR
0x18004434f  mov     ebx, eax
0x180044351  test    eax, eax
0x180044353  jns     short loc_180044360
0x180044355  mov     edx, eax
0x180044357  mov     rcx, rbp
0x18004435a  call    cs:__imp_FwReportReturnError
0x180044360  lea     rcx, [rsp+98h+var_78]
0x180044365  call    cs:__imp_FwPolioEmptyWFAddresses
0x18004436b  test    ebx, ebx
0x18004436d  jns     short loc_18004437C
0x18004436f  mov     edx, ebx
0x180044371  mov     rcx, rbp
0x180044374  call    cs:__imp_FwReportReturnError
0x18004437a  mov     ebx, eax
0x18004437c  mov     eax, ebx
0x18004437e  mov     rcx, [rsp+98h+var_28]
0x180044383  xor     rcx, rsp; StackCookie
0x180044386  call    __security_check_cookie
0x18004438b  mov     rbx, [rsp+98h+arg_10]
0x180044393  add     rsp, 80h
0x18004439a  pop     rdi
0x18004439b  pop     rsi
0x18004439c  pop     rbp
0x18004439d  retn
```
