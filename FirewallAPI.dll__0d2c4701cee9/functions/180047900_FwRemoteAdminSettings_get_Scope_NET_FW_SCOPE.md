# FwRemoteAdminSettings::get_Scope(NET_FW_SCOPE_ *)

- ea: `0x180047900`
- end: `0x1800479e1`
- name: `?get_Scope@FwRemoteAdminSettings@@UEAAJPEAW4NET_FW_SCOPE_@@@Z`
- size: `225`
- prototype: `__int64 __fastcall(FwRemoteAdminSettings *__hidden this, enum NET_FW_SCOPE_ *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1800294b0`
- `0x18002a1f4`
- `0x180047304`
- `0x1800474c8`
- `0x180047900`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x18004794a`
- `fwbase!FwReportReturnError` at `0x1800479ae`
- `fwbase!FwReportReturnError` at `0x18004794a`
- `fwbase!FwReportReturnError` at `0x1800479ae`
- `FWPolicyIOMgr!GetOpenPortOrAuthAppAddrScope` at `0x180047982`
- `FWPolicyIOMgr!GetOpenPortOrAuthAppAddrScope` at `0x180047982`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180047995`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180047995`

## pseudocode

```c
__int64 __fastcall FwRemoteAdminSettings::get_Scope(FwRemoteAdminSettings *this, enum NET_FW_SCOPE_ *a2)
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
    FwReportReturnError("FwRemoteAdminSettings::get_Scope", v5);
    goto LABEL_8;
  }
  RemoteAddrs = FwRemoteAdminSettings::PerformLazyInitialization(this);
  v4 = RemoteAddrs;
  if ( RemoteAddrs < 0
    || (RemoteAddrs = FwRemoteAdminSettings::GetRemoteAddrs(this, (struct _tag_FW_ADDRESSES *)v8),
        v4 = RemoteAddrs,
        RemoteAddrs < 0) )
  {
    v5 = (unsigned int)RemoteAddrs;
    goto LABEL_3;
  }
  *a2 = GetOpenPortOrAuthAppAddrScope(v8);
LABEL_8:
  FwPolioEmptyWFAddresses(v8);
  if ( v4 < 0 )
    return (unsigned int)FwReportReturnError("FwRemoteAdminSettings::get_Scope", (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180047900  mov     [rsp+arg_10], rbx
0x180047905  mov     [rsp+arg_18], rsi
0x18004790a  push    rdi
0x18004790b  sub     rsp, 80h
0x180047912  mov     rax, cs:__security_cookie
0x180047919  xor     rax, rsp
0x18004791c  mov     [rsp+88h+var_18], rax
0x180047921  mov     rsi, rdx
0x180047924  mov     rdi, rcx
0x180047927  xor     edx, edx; Val
0x180047929  lea     rcx, [rsp+88h+var_68]; void *
0x18004792e  lea     r8d, [rdx+48h]; Size
0x180047932  call    memset_0
0x180047937  test    rsi, rsi
0x18004793a  jnz     short loc_180047958
0x18004793c  mov     ebx, 80004003h
0x180047941  mov     edx, ebx
0x180047943  lea     rcx, aFwremoteadmins_9; "FwRemoteAdminSettings::get_Scope"
0x18004794a  call    cs:__imp_FwReportReturnError
0x180047951  nop     dword ptr [rax+rax+00h]
0x180047956  jmp     short loc_180047990
0x180047958  mov     rcx, rdi; this
0x18004795b  call    ?PerformLazyInitialization@FwRemoteAdminSettings@@AEAAJXZ; FwRemoteAdminSettings::PerformLazyInitialization(void)
0x180047960  mov     ebx, eax
0x180047962  test    eax, eax
0x180047964  jns     short loc_18004796A
0x180047966  mov     edx, eax
0x180047968  jmp     short loc_180047943
0x18004796a  lea     rdx, [rsp+88h+var_68]; struct _tag_FW_ADDRESSES *
0x18004796f  mov     rcx, rdi; this
0x180047972  call    ?GetRemoteAddrs@FwRemoteAdminSettings@@AEAAJPEAU_tag_FW_ADDRESSES@@@Z; FwRemoteAdminSettings::GetRemoteAddrs(_tag_FW_ADDRESSES *)
0x180047977  mov     ebx, eax
0x180047979  test    eax, eax
0x18004797b  js      short loc_180047966
0x18004797d  lea     rcx, [rsp+88h+var_68]
0x180047982  call    cs:__imp_GetOpenPortOrAuthAppAddrScope
0x180047989  nop     dword ptr [rax+rax+00h]
0x18004798e  mov     [rsi], eax
0x180047990  lea     rcx, [rsp+88h+var_68]
0x180047995  call    cs:__imp_FwPolioEmptyWFAddresses
0x18004799c  nop     dword ptr [rax+rax+00h]
0x1800479a1  test    ebx, ebx
0x1800479a3  jns     short loc_1800479BC
0x1800479a5  mov     edx, ebx
0x1800479a7  lea     rcx, aFwremoteadmins_9; "FwRemoteAdminSettings::get_Scope"
0x1800479ae  call    cs:__imp_FwReportReturnError
0x1800479b5  nop     dword ptr [rax+rax+00h]
0x1800479ba  mov     ebx, eax
0x1800479bc  mov     eax, ebx
0x1800479be  mov     rcx, [rsp+88h+var_18]
0x1800479c3  xor     rcx, rsp; StackCookie
0x1800479c6  call    __security_check_cookie
0x1800479cb  lea     r11, [rsp+88h+var_8]
0x1800479d3  mov     rbx, [r11+20h]
0x1800479d7  mov     rsi, [r11+28h]
0x1800479db  mov     rsp, r11
0x1800479de  pop     rdi
0x1800479df  retn
```
