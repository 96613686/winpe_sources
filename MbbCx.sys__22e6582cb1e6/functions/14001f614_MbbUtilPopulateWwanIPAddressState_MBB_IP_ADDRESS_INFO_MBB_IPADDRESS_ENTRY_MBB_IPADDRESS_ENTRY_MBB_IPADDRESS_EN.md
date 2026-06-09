# MbbUtilPopulateWwanIPAddressState(_MBB_IP_ADDRESS_INFO *,_MBB_IPADDRESS_ENTRY *,_MBB_IPADDRESS_ENTRY *,_MBB_IPADDRESS_ENTRY *,ulong,ulong,ulong,_WWAN_IP_ADDRESS_STATE *)

- ea: `0x14001f614`
- end: `0x14001f82b`
- name: `?MbbUtilPopulateWwanIPAddressState@@YAHPEAU_MBB_IP_ADDRESS_INFO@@PEAU_MBB_IPADDRESS_ENTRY@@11KKKPEAU_WWAN_IP_ADDRESS_STATE@@@Z`
- size: `535`
- prototype: `__int64 __fastcall(WWAN_IP_CONFIGURATION_FLAGS *, struct _MBB_IPADDRESS_ENTRY *, struct _MBB_IPADDRESS_ENTRY *, struct _MBB_IPADDRESS_ENTRY *, ULONG, ULONG, ULONG, struct _WWAN_IP_ADDRESS_STATE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140006d90`

## callees

- `0x140001cf8`
- `0x14001f614`
- `0x140048040`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001f6d3`
- `ntoskrnl!ExAllocatePool2` at `0x14001f753`
- `ntoskrnl!ExAllocatePool2` at `0x14001f7d2`
- `ntoskrnl!ExAllocatePool2` at `0x14001f6d3`
- `ntoskrnl!ExAllocatePool2` at `0x14001f753`
- `ntoskrnl!ExAllocatePool2` at `0x14001f7d2`

## pseudocode

```c
__int64 __fastcall MbbUtilPopulateWwanIPAddressState(
        WWAN_IP_CONFIGURATION_FLAGS *a1,
        struct _MBB_IPADDRESS_ENTRY *a2,
        struct _MBB_IPADDRESS_ENTRY *a3,
        struct _MBB_IPADDRESS_ENTRY *a4,
        ULONG a5,
        ULONG a6,
        ULONG a7,
        struct _WWAN_IP_ADDRESS_STATE *a8)
{
  struct _MBB_IPADDRESS_ENTRY *v10; // r15
  unsigned int v11; // edi
  int v12; // r9d
  struct _WWAN_IPADDRESS_ENTRY *Pool2; // rax
  int v14; // edx
  struct _WWAN_IPADDRESS_ENTRY *v15; // rax
  int v16; // edx
  struct _WWAN_IPADDRESS_ENTRY *v17; // rax

  v10 = a2;
  if ( a1 )
  {
    v11 = 0;
    a8->IPv4Flags = a1[1];
    a8->IPv6Flags = a1[2];
    a8->IPv4MTU = a1[13].Value;
    a8->IPv6MTU = a1[14].Value;
    if ( a2 )
    {
      Pool2 = (struct _WWAN_IPADDRESS_ENTRY *)ExAllocatePool2(64, 24LL * a5, 1683505741);
      a8->IpTable = Pool2;
      if ( Pool2 )
      {
        memmove(Pool2, v10, 24LL * a5);
        a8->IpCount = a5;
      }
      else
      {
        v11 = -1073741670;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v14) = 2;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v14,
            9,
            75,
            (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids);
        }
      }
    }
    if ( a3 )
    {
      v15 = (struct _WWAN_IPADDRESS_ENTRY *)ExAllocatePool2(64, 24LL * a6, 1683505741);
      a8->GatewayTable = v15;
      if ( v15 )
      {
        memmove(v15, a3, 24LL * a6);
        a8->GatewayCount = a6;
      }
      else
      {
        v11 = -1073741670;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v16) = 2;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v16,
            9,
            76,
            (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids);
        }
      }
    }
    if ( a4 )
    {
      v17 = (struct _WWAN_IPADDRESS_ENTRY *)ExAllocatePool2(64, 24LL * a7, 1683505741);
      a8->DnsTable = v17;
      if ( v17 )
      {
        memmove(v17, a4, 24LL * a7);
        a8->DnsCount = a7;
        return v11;
      }
      v11 = -1073741670;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v12 = 77;
        goto LABEL_4;
      }
    }
  }
  else
  {
    v11 = -1073741823;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v12 = 74;
LABEL_4:
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        9,
        v12,
        (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x14001f614  mov     [rsp+arg_8], rbx
0x14001f619  mov     [rsp+arg_10], rsi
0x14001f61e  push    rdi
0x14001f61f  push    r12
0x14001f621  push    r13
0x14001f623  push    r14
0x14001f625  push    r15
0x14001f627  sub     rsp, 30h
0x14001f62b  mov     r13, r9
0x14001f62e  mov     r12, r8
0x14001f631  mov     r15, rdx
0x14001f634  test    rcx, rcx
0x14001f637  jnz     short loc_14001F67F
0x14001f639  mov     edi, 0C0000001h
0x14001f63e  lea     rbx, WPP_RECORDER_INITIALIZED
0x14001f645  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14001f64c  jz      loc_14001F810
0x14001f652  lea     r9d, [rcx+4Ah]
0x14001f656  lea     r14, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x14001f65d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f664  mov     r8d, 9
0x14001f66a  mov     dl, 2
0x14001f66c  mov     [rsp+58h+var_38], r14
0x14001f671  mov     rcx, [rcx+40h]
0x14001f675  call    WPP_RECORDER_SF_
0x14001f67a  jmp     loc_14001F810
0x14001f67f  mov     eax, [rcx+4]
0x14001f682  lea     rbx, WPP_RECORDER_INITIALIZED
0x14001f689  mov     rsi, [rsp+58h+arg_38]
0x14001f691  lea     r14, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x14001f698  xor     edi, edi
0x14001f69a  mov     [rsi], eax
0x14001f69c  mov     eax, [rcx+8]
0x14001f69f  mov     [rsi+4], eax
0x14001f6a2  mov     eax, [rcx+34h]
0x14001f6a5  mov     [rsi+8], eax
0x14001f6a8  mov     eax, [rcx+38h]
0x14001f6ab  mov     [rsi+0Ch], eax
0x14001f6ae  test    r15, r15
0x14001f6b1  jz      short loc_14001F731
0x14001f6b3  mov     eax, [rsp+58h+arg_20]
0x14001f6ba  lea     ecx, [rdi+40h]
0x14001f6bd  mov     r8d, 6458424Dh
0x14001f6c3  lea     rax, [rax+rax*2]
0x14001f6c7  shl     rax, 3
0x14001f6cb  mov     rdx, rax
0x14001f6ce  mov     [rsp+58h+Size], rax
0x14001f6d3  call    cs:__imp_ExAllocatePool2
0x14001f6da  nop     dword ptr [rax+rax+00h]
0x14001f6df  mov     [rsi+10h], rax
0x14001f6e3  test    rax, rax
0x14001f6e6  jnz     short loc_14001F717
0x14001f6e8  mov     edi, 0C000009Ah
0x14001f6ed  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14001f6f4  jz      short loc_14001F731
0x14001f6f6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f6fd  lea     r9d, [rax+4Bh]
0x14001f701  lea     r8d, [rax+9]
0x14001f705  mov     [rsp+58h+var_38], r14
0x14001f70a  mov     dl, 2
0x14001f70c  mov     rcx, [rcx+40h]
0x14001f710  call    WPP_RECORDER_SF_
0x14001f715  jmp     short loc_14001F731
0x14001f717  mov     r8, [rsp+58h+Size]; Size
0x14001f71c  mov     rdx, r15; Src
0x14001f71f  mov     rcx, rax; void *
0x14001f722  call    memmove
0x14001f727  mov     eax, [rsp+58h+arg_20]
0x14001f72e  mov     [rsi+18h], eax
0x14001f731  test    r12, r12
0x14001f734  jz      short loc_14001F7AF
0x14001f736  mov     eax, [rsp+58h+arg_28]
0x14001f73d  mov     r8d, 6458424Dh
0x14001f743  mov     ecx, 40h ; '@'
0x14001f748  lea     r15, [rax+rax*2]
0x14001f74c  shl     r15, 3
0x14001f750  mov     rdx, r15
0x14001f753  call    cs:__imp_ExAllocatePool2
0x14001f75a  nop     dword ptr [rax+rax+00h]
0x14001f75f  mov     [rsi+20h], rax
0x14001f763  test    rax, rax
0x14001f766  jnz     short loc_14001F797
0x14001f768  mov     edi, 0C000009Ah
0x14001f76d  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14001f774  jz      short loc_14001F7AF
0x14001f776  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f77d  lea     r9d, [rax+4Ch]
0x14001f781  lea     r8d, [rax+9]
0x14001f785  mov     [rsp+58h+var_38], r14
0x14001f78a  mov     dl, 2
0x14001f78c  mov     rcx, [rcx+40h]
0x14001f790  call    WPP_RECORDER_SF_
0x14001f795  jmp     short loc_14001F7AF
0x14001f797  mov     r8, r15; Size
0x14001f79a  mov     rdx, r12; Src
0x14001f79d  mov     rcx, rax; void *
0x14001f7a0  call    memmove
0x14001f7a5  mov     eax, [rsp+58h+arg_28]
0x14001f7ac  mov     [rsi+28h], eax
0x14001f7af  test    r13, r13
0x14001f7b2  jz      short loc_14001F810
0x14001f7b4  mov     r12d, [rsp+58h+arg_30]
0x14001f7bc  mov     r8d, 6458424Dh
0x14001f7c2  mov     ecx, 40h ; '@'
0x14001f7c7  lea     r15, [r12+r12*2]
0x14001f7cb  shl     r15, 3
0x14001f7cf  mov     rdx, r15
0x14001f7d2  call    cs:__imp_ExAllocatePool2
0x14001f7d9  nop     dword ptr [rax+rax+00h]
0x14001f7de  mov     [rsi+30h], rax
0x14001f7e2  test    rax, rax
0x14001f7e5  jnz     short loc_14001F7FE
0x14001f7e7  mov     edi, 0C000009Ah
0x14001f7ec  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14001f7f3  jz      short loc_14001F810
0x14001f7f5  lea     r9d, [rax+4Dh]
0x14001f7f9  jmp     loc_14001F65D
0x14001f7fe  mov     r8, r15; Size
0x14001f801  mov     rdx, r13; Src
0x14001f804  mov     rcx, rax; void *
0x14001f807  call    memmove
0x14001f80c  mov     [rsi+38h], r12d
0x14001f810  mov     rbx, [rsp+58h+arg_8]
0x14001f815  mov     eax, edi
0x14001f817  mov     rsi, [rsp+58h+arg_10]
0x14001f81c  add     rsp, 30h
0x14001f820  pop     r15
0x14001f822  pop     r14
0x14001f824  pop     r13
0x14001f826  pop     r12
0x14001f828  pop     rdi
0x14001f829  retn
```
