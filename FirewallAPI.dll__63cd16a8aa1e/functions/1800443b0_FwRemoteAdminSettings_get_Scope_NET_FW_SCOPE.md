# FwRemoteAdminSettings::get_Scope(NET_FW_SCOPE_ *)

- ea: `0x1800443b0`
- end: `0x180044478`
- name: `?get_Scope@FwRemoteAdminSettings@@UEAAJPEAW4NET_FW_SCOPE_@@@Z`
- size: `200`
- prototype: `__int64 __fastcall(FwRemoteAdminSettings *__hidden this, enum NET_FW_SCOPE_ *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1800277b0`
- `0x1800284c4`
- `0x180043e24`
- `0x180043fc8`
- `0x1800443b0`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x1800443fa`
- `fwbase!FwReportReturnError` at `0x18004444c`
- `fwbase!FwReportReturnError` at `0x1800443fa`
- `fwbase!FwReportReturnError` at `0x18004444c`
- `FWPolicyIOMgr!GetOpenPortOrAuthAppAddrScope` at `0x18004442c`
- `FWPolicyIOMgr!GetOpenPortOrAuthAppAddrScope` at `0x18004442c`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180044439`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180044439`

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
0x1800443b0  mov     [rsp+arg_10], rbx
0x1800443b5  mov     [rsp+arg_18], rsi
0x1800443ba  push    rdi
0x1800443bb  sub     rsp, 80h
0x1800443c2  mov     rax, cs:__security_cookie
0x1800443c9  xor     rax, rsp
0x1800443cc  mov     [rsp+88h+var_18], rax
0x1800443d1  mov     rsi, rdx
0x1800443d4  mov     rdi, rcx
0x1800443d7  xor     edx, edx; Val
0x1800443d9  lea     rcx, [rsp+88h+var_68]; void *
0x1800443de  lea     r8d, [rdx+48h]; Size
0x1800443e2  call    memset_0
0x1800443e7  test    rsi, rsi
0x1800443ea  jnz     short loc_180044402
0x1800443ec  mov     ebx, 80004003h
0x1800443f1  mov     edx, ebx
0x1800443f3  lea     rcx, aFwremoteadmins_9; "FwRemoteAdminSettings::get_Scope"
0x1800443fa  call    cs:__imp_FwReportReturnError
0x180044400  jmp     short loc_180044434
0x180044402  mov     rcx, rdi; this
0x180044405  call    ?PerformLazyInitialization@FwRemoteAdminSettings@@AEAAJXZ; FwRemoteAdminSettings::PerformLazyInitialization(void)
0x18004440a  mov     ebx, eax
0x18004440c  test    eax, eax
0x18004440e  jns     short loc_180044414
0x180044410  mov     edx, eax
0x180044412  jmp     short loc_1800443F3
0x180044414  lea     rdx, [rsp+88h+var_68]; struct _tag_FW_ADDRESSES *
0x180044419  mov     rcx, rdi; this
0x18004441c  call    ?GetRemoteAddrs@FwRemoteAdminSettings@@AEAAJPEAU_tag_FW_ADDRESSES@@@Z; FwRemoteAdminSettings::GetRemoteAddrs(_tag_FW_ADDRESSES *)
0x180044421  mov     ebx, eax
0x180044423  test    eax, eax
0x180044425  js      short loc_180044410
0x180044427  lea     rcx, [rsp+88h+var_68]
0x18004442c  call    cs:__imp_GetOpenPortOrAuthAppAddrScope
0x180044432  mov     [rsi], eax
0x180044434  lea     rcx, [rsp+88h+var_68]
0x180044439  call    cs:__imp_FwPolioEmptyWFAddresses
0x18004443f  test    ebx, ebx
0x180044441  jns     short loc_180044454
0x180044443  mov     edx, ebx
0x180044445  lea     rcx, aFwremoteadmins_9; "FwRemoteAdminSettings::get_Scope"
0x18004444c  call    cs:__imp_FwReportReturnError
0x180044452  mov     ebx, eax
0x180044454  mov     eax, ebx
0x180044456  mov     rcx, [rsp+88h+var_18]
0x18004445b  xor     rcx, rsp; StackCookie
0x18004445e  call    __security_check_cookie
0x180044463  lea     r11, [rsp+88h+var_8]
0x18004446b  mov     rbx, [r11+20h]
0x18004446f  mov     rsi, [r11+28h]
0x180044473  mov     rsp, r11
0x180044476  pop     rdi
0x180044477  retn
```
