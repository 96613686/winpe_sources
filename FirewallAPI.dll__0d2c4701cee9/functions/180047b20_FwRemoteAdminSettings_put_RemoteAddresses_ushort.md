# FwRemoteAdminSettings::put_RemoteAddresses(ushort *)

- ea: `0x180047b20`
- end: `0x180047bef`
- name: `?put_RemoteAddresses@FwRemoteAdminSettings@@UEAAJPEAG@Z`
- size: `207`
- prototype: `__int64 __fastcall(FwRemoteAdminSettings *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1800294b0`
- `0x18002a1f4`
- `0x1800474c8`
- `0x180047618`
- `0x180047b20`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x180047b96`
- `fwbase!FwReportReturnError` at `0x180047bc0`
- `fwbase!FwReportReturnError` at `0x180047b96`
- `fwbase!FwReportReturnError` at `0x180047bc0`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x180047b5a`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x180047b5a`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180047ba7`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180047ba7`

## pseudocode

```c
__int64 __fastcall FwRemoteAdminSettings::put_RemoteAddresses(FwRemoteAdminSettings *this, unsigned __int16 *a2)
{
  int v4; // eax
  int v5; // ebx
  _BYTE v7[80]; // [rsp+20h] [rbp-68h] BYREF

  memset_0(v7, 0, 0x48u);
  v4 = StringToOpenPortOrAuthAppAddress(a2, v7);
  v5 = v4;
  if ( v4 < 0
    || (v4 = FwRemoteAdminSettings::PerformLazyInitialization(this), v5 = v4, v4 < 0)
    || (v4 = FwRemoteAdminSettings::SetRemoteAddrs(this, (struct _tag_FW_ADDRESSES *const)v7), v5 = v4, v4 < 0) )
  {
    FwReportReturnError("FwRemoteAdminSettings::put_RemoteAddresses", (unsigned int)v4);
  }
  FwPolioEmptyWFAddresses(v7);
  if ( v5 < 0 )
    return (unsigned int)FwReportReturnError("FwRemoteAdminSettings::put_RemoteAddresses", (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180047b20  mov     [rsp+arg_10], rbx
0x180047b25  push    rdi
0x180047b26  sub     rsp, 80h
0x180047b2d  mov     rax, cs:__security_cookie
0x180047b34  xor     rax, rsp
0x180047b37  mov     [rsp+88h+var_18], rax
0x180047b3c  mov     rbx, rdx
0x180047b3f  mov     rdi, rcx
0x180047b42  xor     edx, edx; Val
0x180047b44  lea     rcx, [rsp+88h+var_68]; void *
0x180047b49  lea     r8d, [rdx+48h]; Size
0x180047b4d  call    memset_0
0x180047b52  lea     rdx, [rsp+88h+var_68]
0x180047b57  mov     rcx, rbx
0x180047b5a  call    cs:__imp_StringToOpenPortOrAuthAppAddress
0x180047b61  nop     dword ptr [rax+rax+00h]
0x180047b66  mov     ebx, eax
0x180047b68  test    eax, eax
0x180047b6a  js      short loc_180047B8D
0x180047b6c  mov     rcx, rdi; this
0x180047b6f  call    ?PerformLazyInitialization@FwRemoteAdminSettings@@AEAAJXZ; FwRemoteAdminSettings::PerformLazyInitialization(void)
0x180047b74  mov     ebx, eax
0x180047b76  test    eax, eax
0x180047b78  js      short loc_180047B8D
0x180047b7a  lea     rdx, [rsp+88h+var_68]; struct _tag_FW_ADDRESSES *
0x180047b7f  mov     rcx, rdi; this
0x180047b82  call    ?SetRemoteAddrs@FwRemoteAdminSettings@@AEAAJQEAU_tag_FW_ADDRESSES@@@Z; FwRemoteAdminSettings::SetRemoteAddrs(_tag_FW_ADDRESSES * const)
0x180047b87  mov     ebx, eax
0x180047b89  test    eax, eax
0x180047b8b  jns     short loc_180047BA2
0x180047b8d  mov     edx, eax
0x180047b8f  lea     rcx, aFwremoteadmins_7; "FwRemoteAdminSettings::put_RemoteAddres"...
0x180047b96  call    cs:__imp_FwReportReturnError
0x180047b9d  nop     dword ptr [rax+rax+00h]
0x180047ba2  lea     rcx, [rsp+88h+var_68]
0x180047ba7  call    cs:__imp_FwPolioEmptyWFAddresses
0x180047bae  nop     dword ptr [rax+rax+00h]
0x180047bb3  test    ebx, ebx
0x180047bb5  jns     short loc_180047BCE
0x180047bb7  mov     edx, ebx
0x180047bb9  lea     rcx, aFwremoteadmins_7; "FwRemoteAdminSettings::put_RemoteAddres"...
0x180047bc0  call    cs:__imp_FwReportReturnError
0x180047bc7  nop     dword ptr [rax+rax+00h]
0x180047bcc  mov     ebx, eax
0x180047bce  mov     eax, ebx
0x180047bd0  mov     rcx, [rsp+88h+var_18]
0x180047bd5  xor     rcx, rsp; StackCookie
0x180047bd8  call    __security_check_cookie
0x180047bdd  mov     rbx, [rsp+88h+arg_10]
0x180047be5  add     rsp, 80h
0x180047bec  pop     rdi
0x180047bed  retn
```
