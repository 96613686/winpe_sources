# FwRemoteAdminSettings::put_RemoteAddresses(ushort *)

- ea: `0x180044590`
- end: `0x180044646`
- name: `?put_RemoteAddresses@FwRemoteAdminSettings@@UEAAJPEAG@Z`
- size: `182`
- prototype: `__int64 __fastcall(FwRemoteAdminSettings *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1800277b0`
- `0x1800284c4`
- `0x180043fc8`
- `0x180044108`
- `0x180044590`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x180044600`
- `fwbase!FwReportReturnError` at `0x18004461e`
- `fwbase!FwReportReturnError` at `0x180044600`
- `fwbase!FwReportReturnError` at `0x18004461e`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x1800445ca`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x1800445ca`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18004460b`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18004460b`

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
0x180044590  mov     [rsp+arg_10], rbx
0x180044595  push    rdi
0x180044596  sub     rsp, 80h
0x18004459d  mov     rax, cs:__security_cookie
0x1800445a4  xor     rax, rsp
0x1800445a7  mov     [rsp+88h+var_18], rax
0x1800445ac  mov     rbx, rdx
0x1800445af  mov     rdi, rcx
0x1800445b2  xor     edx, edx; Val
0x1800445b4  lea     rcx, [rsp+88h+var_68]; void *
0x1800445b9  lea     r8d, [rdx+48h]; Size
0x1800445bd  call    memset_0
0x1800445c2  lea     rdx, [rsp+88h+var_68]
0x1800445c7  mov     rcx, rbx
0x1800445ca  call    cs:__imp_StringToOpenPortOrAuthAppAddress
0x1800445d0  mov     ebx, eax
0x1800445d2  test    eax, eax
0x1800445d4  js      short loc_1800445F7
0x1800445d6  mov     rcx, rdi; this
0x1800445d9  call    ?PerformLazyInitialization@FwRemoteAdminSettings@@AEAAJXZ; FwRemoteAdminSettings::PerformLazyInitialization(void)
0x1800445de  mov     ebx, eax
0x1800445e0  test    eax, eax
0x1800445e2  js      short loc_1800445F7
0x1800445e4  lea     rdx, [rsp+88h+var_68]; struct _tag_FW_ADDRESSES *
0x1800445e9  mov     rcx, rdi; this
0x1800445ec  call    ?SetRemoteAddrs@FwRemoteAdminSettings@@AEAAJQEAU_tag_FW_ADDRESSES@@@Z; FwRemoteAdminSettings::SetRemoteAddrs(_tag_FW_ADDRESSES * const)
0x1800445f1  mov     ebx, eax
0x1800445f3  test    eax, eax
0x1800445f5  jns     short loc_180044606
0x1800445f7  mov     edx, eax
0x1800445f9  lea     rcx, aFwremoteadmins_7; "FwRemoteAdminSettings::put_RemoteAddres"...
0x180044600  call    cs:__imp_FwReportReturnError
0x180044606  lea     rcx, [rsp+88h+var_68]
0x18004460b  call    cs:__imp_FwPolioEmptyWFAddresses
0x180044611  test    ebx, ebx
0x180044613  jns     short loc_180044626
0x180044615  mov     edx, ebx
0x180044617  lea     rcx, aFwremoteadmins_7; "FwRemoteAdminSettings::put_RemoteAddres"...
0x18004461e  call    cs:__imp_FwReportReturnError
0x180044624  mov     ebx, eax
0x180044626  mov     eax, ebx
0x180044628  mov     rcx, [rsp+88h+var_18]
0x18004462d  xor     rcx, rsp; StackCookie
0x180044630  call    __security_check_cookie
0x180044635  mov     rbx, [rsp+88h+arg_10]
0x18004463d  add     rsp, 80h
0x180044644  pop     rdi
0x180044645  retn
```
