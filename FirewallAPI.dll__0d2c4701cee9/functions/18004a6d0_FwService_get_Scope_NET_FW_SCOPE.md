# FwService::get_Scope(NET_FW_SCOPE_ *)

- ea: `0x18004a6d0`
- end: `0x18004a7b1`
- name: `?get_Scope@FwService@@UEAAJPEAW4NET_FW_SCOPE_@@@Z`
- size: `225`
- prototype: `__int64 __fastcall(FwService *__hidden this, enum NET_FW_SCOPE_ *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x1800294b0`
- `0x18002a1f4`
- `0x180049e84`
- `0x18004a0e8`
- `0x18004a6d0`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x18004a71a`
- `fwbase!FwReportReturnError` at `0x18004a77e`
- `fwbase!FwReportReturnError` at `0x18004a71a`
- `fwbase!FwReportReturnError` at `0x18004a77e`
- `FWPolicyIOMgr!GetOpenPortOrAuthAppAddrScope` at `0x18004a752`
- `FWPolicyIOMgr!GetOpenPortOrAuthAppAddrScope` at `0x18004a752`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18004a765`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18004a765`

## string_xrefs

- `0x18004a713`: `FwService::get_Scope`
- `0x18004a777`: `FwService::get_Scope`

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
0x18004a6d0  mov     [rsp+arg_10], rbx
0x18004a6d5  mov     [rsp+arg_18], rsi
0x18004a6da  push    rdi
0x18004a6db  sub     rsp, 80h
0x18004a6e2  mov     rax, cs:__security_cookie
0x18004a6e9  xor     rax, rsp
0x18004a6ec  mov     [rsp+88h+var_18], rax
0x18004a6f1  mov     rsi, rdx
0x18004a6f4  mov     rdi, rcx
0x18004a6f7  xor     edx, edx; Val
0x18004a6f9  lea     rcx, [rsp+88h+var_68]; void *
0x18004a6fe  lea     r8d, [rdx+48h]; Size
0x18004a702  call    memset_0
0x18004a707  test    rsi, rsi
0x18004a70a  jnz     short loc_18004A728
0x18004a70c  mov     ebx, 80004003h
0x18004a711  mov     edx, ebx
0x18004a713  lea     rcx, aFwserviceGetSc; "FwService::get_Scope"
0x18004a71a  call    cs:__imp_FwReportReturnError
0x18004a721  nop     dword ptr [rax+rax+00h]
0x18004a726  jmp     short loc_18004A760
0x18004a728  mov     rcx, rdi; this
0x18004a72b  call    ?PerformLazyInitialization@FwService@@AEAAJXZ; FwService::PerformLazyInitialization(void)
0x18004a730  mov     ebx, eax
0x18004a732  test    eax, eax
0x18004a734  jns     short loc_18004A73A
0x18004a736  mov     edx, eax
0x18004a738  jmp     short loc_18004A713
0x18004a73a  lea     rdx, [rsp+88h+var_68]; struct _tag_FW_ADDRESSES *
0x18004a73f  mov     rcx, rdi; this
0x18004a742  call    ?GetRemoteAddrs@FwService@@AEAAJPEAU_tag_FW_ADDRESSES@@@Z; FwService::GetRemoteAddrs(_tag_FW_ADDRESSES *)
0x18004a747  mov     ebx, eax
0x18004a749  test    eax, eax
0x18004a74b  js      short loc_18004A736
0x18004a74d  lea     rcx, [rsp+88h+var_68]
0x18004a752  call    cs:__imp_GetOpenPortOrAuthAppAddrScope
0x18004a759  nop     dword ptr [rax+rax+00h]
0x18004a75e  mov     [rsi], eax
0x18004a760  lea     rcx, [rsp+88h+var_68]
0x18004a765  call    cs:__imp_FwPolioEmptyWFAddresses
0x18004a76c  nop     dword ptr [rax+rax+00h]
0x18004a771  test    ebx, ebx
0x18004a773  jns     short loc_18004A78C
0x18004a775  mov     edx, ebx
0x18004a777  lea     rcx, aFwserviceGetSc; "FwService::get_Scope"
0x18004a77e  call    cs:__imp_FwReportReturnError
0x18004a785  nop     dword ptr [rax+rax+00h]
0x18004a78a  mov     ebx, eax
0x18004a78c  mov     eax, ebx
0x18004a78e  mov     rcx, [rsp+88h+var_18]
0x18004a793  xor     rcx, rsp; StackCookie
0x18004a796  call    __security_check_cookie
0x18004a79b  lea     r11, [rsp+88h+var_8]
0x18004a7a3  mov     rbx, [r11+20h]
0x18004a7a7  mov     rsi, [r11+28h]
0x18004a7ab  mov     rsp, r11
0x18004a7ae  pop     rdi
0x18004a7af  retn
```
