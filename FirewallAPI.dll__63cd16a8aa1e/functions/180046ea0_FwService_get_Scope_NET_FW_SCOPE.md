# FwService::get_Scope(NET_FW_SCOPE_ *)

- ea: `0x180046ea0`
- end: `0x180046f68`
- name: `?get_Scope@FwService@@UEAAJPEAW4NET_FW_SCOPE_@@@Z`
- size: `200`
- prototype: `__int64 __fastcall(FwService *__hidden this, enum NET_FW_SCOPE_ *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x1800277b0`
- `0x1800284c4`
- `0x180046744`
- `0x1800468f8`
- `0x180046ea0`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x180046eea`
- `fwbase!FwReportReturnError` at `0x180046f3c`
- `fwbase!FwReportReturnError` at `0x180046eea`
- `fwbase!FwReportReturnError` at `0x180046f3c`
- `FWPolicyIOMgr!GetOpenPortOrAuthAppAddrScope` at `0x180046f1c`
- `FWPolicyIOMgr!GetOpenPortOrAuthAppAddrScope` at `0x180046f1c`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180046f29`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180046f29`

## string_xrefs

- `0x180046ee3`: `FwService::get_Scope`
- `0x180046f35`: `FwService::get_Scope`

## pseudocode

```c
__int64 __fastcall FwService::get_Scope(FwService *this, enum NET_FW_SCOPE_ *a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  int RemoteAddrs; // eax
  _BYTE v8[80]; // [rsp+20h] [rbp-68h] BYREF

  memset_0(v8, 0, 0x48u);
  if ( !a2 )
  {
    v4 = -2147467261;
    v5 = 2147500035LL;
LABEL_3:
    FwReportReturnError("FwService::get_Scope", v5);
    goto LABEL_8;
  }
  RemoteAddrs = FwService::PerformLazyInitialization(this);
  v4 = RemoteAddrs;
  if ( RemoteAddrs < 0
    || (RemoteAddrs = FwService::GetRemoteAddrs(this, (struct _tag_FW_ADDRESSES *)v8), v4 = RemoteAddrs, RemoteAddrs < 0) )
  {
    v5 = (unsigned int)RemoteAddrs;
    goto LABEL_3;
  }
  *a2 = GetOpenPortOrAuthAppAddrScope(v8);
LABEL_8:
  FwPolioEmptyWFAddresses(v8);
  if ( v4 < 0 )
    return (unsigned int)FwReportReturnError("FwService::get_Scope", (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180046ea0  mov     [rsp+arg_10], rbx
0x180046ea5  mov     [rsp+arg_18], rsi
0x180046eaa  push    rdi
0x180046eab  sub     rsp, 80h
0x180046eb2  mov     rax, cs:__security_cookie
0x180046eb9  xor     rax, rsp
0x180046ebc  mov     [rsp+88h+var_18], rax
0x180046ec1  mov     rsi, rdx
0x180046ec4  mov     rdi, rcx
0x180046ec7  xor     edx, edx; Val
0x180046ec9  lea     rcx, [rsp+88h+var_68]; void *
0x180046ece  lea     r8d, [rdx+48h]; Size
0x180046ed2  call    memset_0
0x180046ed7  test    rsi, rsi
0x180046eda  jnz     short loc_180046EF2
0x180046edc  mov     ebx, 80004003h
0x180046ee1  mov     edx, ebx
0x180046ee3  lea     rcx, aFwserviceGetSc; "FwService::get_Scope"
0x180046eea  call    cs:__imp_FwReportReturnError
0x180046ef0  jmp     short loc_180046F24
0x180046ef2  mov     rcx, rdi; this
0x180046ef5  call    ?PerformLazyInitialization@FwService@@AEAAJXZ; FwService::PerformLazyInitialization(void)
0x180046efa  mov     ebx, eax
0x180046efc  test    eax, eax
0x180046efe  jns     short loc_180046F04
0x180046f00  mov     edx, eax
0x180046f02  jmp     short loc_180046EE3
0x180046f04  lea     rdx, [rsp+88h+var_68]; struct _tag_FW_ADDRESSES *
0x180046f09  mov     rcx, rdi; this
0x180046f0c  call    ?GetRemoteAddrs@FwService@@AEAAJPEAU_tag_FW_ADDRESSES@@@Z; FwService::GetRemoteAddrs(_tag_FW_ADDRESSES *)
0x180046f11  mov     ebx, eax
0x180046f13  test    eax, eax
0x180046f15  js      short loc_180046F00
0x180046f17  lea     rcx, [rsp+88h+var_68]
0x180046f1c  call    cs:__imp_GetOpenPortOrAuthAppAddrScope
0x180046f22  mov     [rsi], eax
0x180046f24  lea     rcx, [rsp+88h+var_68]
0x180046f29  call    cs:__imp_FwPolioEmptyWFAddresses
0x180046f2f  test    ebx, ebx
0x180046f31  jns     short loc_180046F44
0x180046f33  mov     edx, ebx
0x180046f35  lea     rcx, aFwserviceGetSc; "FwService::get_Scope"
0x180046f3c  call    cs:__imp_FwReportReturnError
0x180046f42  mov     ebx, eax
0x180046f44  mov     eax, ebx
0x180046f46  mov     rcx, [rsp+88h+var_18]
0x180046f4b  xor     rcx, rsp; StackCookie
0x180046f4e  call    __security_check_cookie
0x180046f53  lea     r11, [rsp+88h+var_8]
0x180046f5b  mov     rbx, [r11+20h]
0x180046f5f  mov     rsi, [r11+28h]
0x180046f63  mov     rsp, r11
0x180046f66  pop     rdi
0x180046f67  retn
```
