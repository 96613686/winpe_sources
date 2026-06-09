# FwService::put_RemoteAddresses(ushort *)

- ea: `0x18004a900`
- end: `0x18004a9cf`
- name: `?put_RemoteAddresses@FwService@@UEAAJPEAG@Z`
- size: `207`
- prototype: `__int64 __fastcall(FwService *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x1800294b0`
- `0x18002a1f4`
- `0x18004a0e8`
- `0x18004a258`
- `0x18004a900`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x18004a976`
- `fwbase!FwReportReturnError` at `0x18004a9a0`
- `fwbase!FwReportReturnError` at `0x18004a976`
- `fwbase!FwReportReturnError` at `0x18004a9a0`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x18004a93a`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x18004a93a`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18004a987`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18004a987`

## string_xrefs

- `0x18004a96f`: `FwService::put_RemoteAddresses`
- `0x18004a999`: `FwService::put_RemoteAddresses`

## pseudocode

```c
__int64 __fastcall FwService::put_RemoteAddresses(FwService *this, unsigned __int16 *a2)
{
  int v4; // eax
  int v5; // ebx
  _BYTE v7[80]; // [rsp+20h] [rbp-68h] BYREF

  memset_0(v7, 0, 0x48u);
  v4 = StringToOpenPortOrAuthAppAddress(a2, v7);
  v5 = v4;
  if ( v4 < 0
    || (v4 = FwService::PerformLazyInitialization(this), v5 = v4, v4 < 0)
    || (v4 = FwService::SetRemoteAddrs(this, (struct _tag_FW_ADDRESSES *const)v7), v5 = v4, v4 < 0) )
  {
    FwReportReturnError("FwService::put_RemoteAddresses", (unsigned int)v4);
  }
  FwPolioEmptyWFAddresses(v7);
  if ( v5 < 0 )
    return (unsigned int)FwReportReturnError("FwService::put_RemoteAddresses", (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004a900  mov     [rsp+arg_10], rbx
0x18004a905  push    rdi
0x18004a906  sub     rsp, 80h
0x18004a90d  mov     rax, cs:__security_cookie
0x18004a914  xor     rax, rsp
0x18004a917  mov     [rsp+88h+var_18], rax
0x18004a91c  mov     rbx, rdx
0x18004a91f  mov     rdi, rcx
0x18004a922  xor     edx, edx; Val
0x18004a924  lea     rcx, [rsp+88h+var_68]; void *
0x18004a929  lea     r8d, [rdx+48h]; Size
0x18004a92d  call    memset_0
0x18004a932  lea     rdx, [rsp+88h+var_68]
0x18004a937  mov     rcx, rbx
0x18004a93a  call    cs:__imp_StringToOpenPortOrAuthAppAddress
0x18004a941  nop     dword ptr [rax+rax+00h]
0x18004a946  mov     ebx, eax
0x18004a948  test    eax, eax
0x18004a94a  js      short loc_18004A96D
0x18004a94c  mov     rcx, rdi; this
0x18004a94f  call    ?PerformLazyInitialization@FwService@@AEAAJXZ; FwService::PerformLazyInitialization(void)
0x18004a954  mov     ebx, eax
0x18004a956  test    eax, eax
0x18004a958  js      short loc_18004A96D
0x18004a95a  lea     rdx, [rsp+88h+var_68]; struct _tag_FW_ADDRESSES *
0x18004a95f  mov     rcx, rdi; this
0x18004a962  call    ?SetRemoteAddrs@FwService@@AEAAJQEAU_tag_FW_ADDRESSES@@@Z; FwService::SetRemoteAddrs(_tag_FW_ADDRESSES * const)
0x18004a967  mov     ebx, eax
0x18004a969  test    eax, eax
0x18004a96b  jns     short loc_18004A982
0x18004a96d  mov     edx, eax
0x18004a96f  lea     rcx, aFwservicePutRe; "FwService::put_RemoteAddresses"
0x18004a976  call    cs:__imp_FwReportReturnError
0x18004a97d  nop     dword ptr [rax+rax+00h]
0x18004a982  lea     rcx, [rsp+88h+var_68]
0x18004a987  call    cs:__imp_FwPolioEmptyWFAddresses
0x18004a98e  nop     dword ptr [rax+rax+00h]
0x18004a993  test    ebx, ebx
0x18004a995  jns     short loc_18004A9AE
0x18004a997  mov     edx, ebx
0x18004a999  lea     rcx, aFwservicePutRe; "FwService::put_RemoteAddresses"
0x18004a9a0  call    cs:__imp_FwReportReturnError
0x18004a9a7  nop     dword ptr [rax+rax+00h]
0x18004a9ac  mov     ebx, eax
0x18004a9ae  mov     eax, ebx
0x18004a9b0  mov     rcx, [rsp+88h+var_18]
0x18004a9b5  xor     rcx, rsp; StackCookie
0x18004a9b8  call    __security_check_cookie
0x18004a9bd  mov     rbx, [rsp+88h+arg_10]
0x18004a9c5  add     rsp, 80h
0x18004a9cc  pop     rdi
0x18004a9cd  retn
```
