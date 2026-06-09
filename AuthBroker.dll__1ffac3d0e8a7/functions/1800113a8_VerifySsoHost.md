# _VerifySsoHost

- ea: `0x1800113a8`
- end: `0x18001146e`
- name: `_VerifySsoHost`
- size: `198`
- prototype: `HRESULT __fastcall(const wchar_t *host, void *clientTokenHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000f568`

## callees

- `0x1800045c0`
- `0x180004f00`
- `0x18000737c`
- `0x1800113a8`
- `0x180011c0c`

## import_xrefs

- `ntdll!_wcsicmp` at `0x180011411`
- `ntdll!_wcsicmp` at `0x180011411`

## pseudocode

```c
__int64 __fastcall VerifySsoHost(const wchar_t *host, void *clientTokenHandle)
{
  signed int AuthBrokerClientAppContainerStringInfo; // eax
  unsigned int v4; // ebx
  const _GUID *v5; // r8
  wchar_t *clientSid; // [rsp+50h] [rbp+18h] BYREF

  clientSid = 0;
  AuthBrokerClientAppContainerStringInfo = GetAuthBrokerClientAppContainerStringInfo(0, clientTokenHandle, &clientSid);
  v4 = AuthBrokerClientAppContainerStringInfo;
  if ( AuthBrokerClientAppContainerStringInfo >= 0 )
  {
    if ( _wcsicmp(clientSid, host) )
    {
      v4 = -2147024809;
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
        && WPP_GLOBAL_Control[1].Control.Level >= 2u )
      {
        WPP_SF_SS(WPP_GLOBAL_Control[1].Control.Logger, (unsigned __int16)&WPP_GLOBAL_Control, v5, host, clientSid);
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
         && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
         && WPP_GLOBAL_Control[1].Control.Level >= 2u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control[1].Control.Logger,
      0x23u,
      WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids,
      AuthBrokerClientAppContainerStringInfo);
  }
  FreeAuthBrokerClientAppContainerString(ClientAppContainerHostSidInfo, clientSid);
  return v4;
}

```

## disassembly

```asm
0x1800113a8  mov     [rsp+arg_0], rbx
0x1800113ad  push    rdi
0x1800113ae  sub     rsp, 30h
0x1800113b2  mov     rdi, host
0x1800113b5  mov     [rsp+38h+clientSid], 0
0x1800113be  xor     ecx, ecx; infoType
0x1800113c0  lea     r8, [rsp+38h+clientSid]; string
0x1800113c5  call    ?GetAuthBrokerClientAppContainerStringInfo@@YAJW4ClientAppContainerStringInfoType@@PEAXPEAPEAG@Z; GetAuthBrokerClientAppContainerStringInfo(ClientAppContainerStringInfoType,void *,ushort * *)
0x1800113ca  mov     ebx, eax
0x1800113cc  test    eax, eax
0x1800113ce  jns     short loc_180011409
0x1800113d0  mov     host, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800113d7  lea     clientTokenHandle, WPP_GLOBAL_Control
0x1800113de  cmp     host, clientTokenHandle
0x1800113e1  jz      short $Exit_13
0x1800113e3  test    byte ptr [host+44h], 8
0x1800113e7  jz      short $Exit_13
0x1800113e9  cmp     byte ptr [host+41h], 2
0x1800113ed  jb      short $Exit_13
0x1800113ef  mov     host, [host+38h]; Logger
0x1800113f3  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x1800113fa  mov     edx, 23h ; '#'; id
0x1800113ff  mov     r9d, eax; _a1
0x180011402  call    WPP_SF_d
0x180011407  jmp     short $Exit_13
0x180011409  mov     host, [rsp+38h+clientSid]; String1
0x18001140e  mov     clientTokenHandle, rdi; String2
0x180011411  call    cs:__imp__wcsicmp
0x180011417  test    eax, eax
0x180011419  jz      short $Exit_13
0x18001141b  mov     ebx, 80070057h
0x180011420  mov     host, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180011427  lea     clientTokenHandle, WPP_GLOBAL_Control; _a1
0x18001142e  cmp     host, clientTokenHandle
0x180011431  jz      short $Exit_13
0x180011433  test    byte ptr [host+44h], 8
0x180011437  jz      short $Exit_13
0x180011439  cmp     byte ptr [host+41h], 2
0x18001143d  jb      short $Exit_13
0x18001143f  mov     rax, [rsp+38h+clientSid]
0x180011444  mov     r9, rdi; Logger
0x180011447  mov     host, [host+38h]; Logger
0x18001144b  mov     [rsp+38h+id], rax; id
0x180011450  call    WPP_SF_SS
0x180011455  mov     clientTokenHandle, [rsp+38h+clientSid]; string
0x18001145a  xor     ecx, ecx; infoType
0x18001145c  call    ?FreeAuthBrokerClientAppContainerString@@YAXW4ClientAppContainerStringInfoType@@PEAG@Z; FreeAuthBrokerClientAppContainerString(ClientAppContainerStringInfoType,ushort *)
0x180011461  mov     eax, ebx
0x180011463  mov     rbx, [rsp+38h+arg_0]
0x180011468  add     rsp, 30h
0x18001146c  pop     rdi
0x18001146d  retn
```
