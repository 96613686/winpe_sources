# FwService::put_RemoteAddresses(ushort *)

- ea: `0x180047090`
- end: `0x180047146`
- name: `?put_RemoteAddresses@FwService@@UEAAJPEAG@Z`
- size: `182`
- prototype: `__int64 __fastcall(FwService *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x1800277b0`
- `0x1800284c4`
- `0x1800468f8`
- `0x180046a58`
- `0x180047090`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x180047100`
- `fwbase!FwReportReturnError` at `0x18004711e`
- `fwbase!FwReportReturnError` at `0x180047100`
- `fwbase!FwReportReturnError` at `0x18004711e`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x1800470ca`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x1800470ca`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18004710b`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18004710b`

## string_xrefs

- `0x1800470f9`: `FwService::put_RemoteAddresses`
- `0x180047117`: `FwService::put_RemoteAddresses`

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
0x180047090  mov     [rsp+arg_10], rbx
0x180047095  push    rdi
0x180047096  sub     rsp, 80h
0x18004709d  mov     rax, cs:__security_cookie
0x1800470a4  xor     rax, rsp
0x1800470a7  mov     [rsp+88h+var_18], rax
0x1800470ac  mov     rbx, rdx
0x1800470af  mov     rdi, rcx
0x1800470b2  xor     edx, edx; Val
0x1800470b4  lea     rcx, [rsp+88h+var_68]; void *
0x1800470b9  lea     r8d, [rdx+48h]; Size
0x1800470bd  call    memset_0
0x1800470c2  lea     rdx, [rsp+88h+var_68]
0x1800470c7  mov     rcx, rbx
0x1800470ca  call    cs:__imp_StringToOpenPortOrAuthAppAddress
0x1800470d0  mov     ebx, eax
0x1800470d2  test    eax, eax
0x1800470d4  js      short loc_1800470F7
0x1800470d6  mov     rcx, rdi; this
0x1800470d9  call    ?PerformLazyInitialization@FwService@@AEAAJXZ; FwService::PerformLazyInitialization(void)
0x1800470de  mov     ebx, eax
0x1800470e0  test    eax, eax
0x1800470e2  js      short loc_1800470F7
0x1800470e4  lea     rdx, [rsp+88h+var_68]; struct _tag_FW_ADDRESSES *
0x1800470e9  mov     rcx, rdi; this
0x1800470ec  call    ?SetRemoteAddrs@FwService@@AEAAJQEAU_tag_FW_ADDRESSES@@@Z; FwService::SetRemoteAddrs(_tag_FW_ADDRESSES * const)
0x1800470f1  mov     ebx, eax
0x1800470f3  test    eax, eax
0x1800470f5  jns     short loc_180047106
0x1800470f7  mov     edx, eax
0x1800470f9  lea     rcx, aFwservicePutRe; "FwService::put_RemoteAddresses"
0x180047100  call    cs:__imp_FwReportReturnError
0x180047106  lea     rcx, [rsp+88h+var_68]
0x18004710b  call    cs:__imp_FwPolioEmptyWFAddresses
0x180047111  test    ebx, ebx
0x180047113  jns     short loc_180047126
0x180047115  mov     edx, ebx
0x180047117  lea     rcx, aFwservicePutRe; "FwService::put_RemoteAddresses"
0x18004711e  call    cs:__imp_FwReportReturnError
0x180047124  mov     ebx, eax
0x180047126  mov     eax, ebx
0x180047128  mov     rcx, [rsp+88h+var_18]
0x18004712d  xor     rcx, rsp; StackCookie
0x180047130  call    __security_check_cookie
0x180047135  mov     rbx, [rsp+88h+arg_10]
0x18004713d  add     rsp, 80h
0x180047144  pop     rdi
0x180047145  retn
```
