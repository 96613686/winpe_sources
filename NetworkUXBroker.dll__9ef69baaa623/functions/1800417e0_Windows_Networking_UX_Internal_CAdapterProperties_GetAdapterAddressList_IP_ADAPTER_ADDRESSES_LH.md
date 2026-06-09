# Windows::Networking::UX::Internal::CAdapterProperties::GetAdapterAddressList(_IP_ADAPTER_ADDRESSES_LH * *)

- ea: `0x1800417e0`
- end: `0x180041971`
- name: `?GetAdapterAddressList@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAJPEAPEAU_IP_ADAPTER_ADDRESSES_LH@@@Z`
- size: `401`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::CAdapterProperties *__hidden this, struct _IP_ADAPTER_ADDRESSES_LH **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180041e58`

## callees

- `0x18000a6e4`
- `0x180037c4c`
- `0x1800417e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004185a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004185a`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180041845`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18004187d`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180041845`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18004187d`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::CAdapterProperties::GetAdapterAddressList(
        Windows::Networking::UX::Internal::CAdapterProperties *this,
        struct _IP_ADAPTER_ADDRESSES_LH **a2)
{
  signed int AdaptersAddresses; // eax
  signed int v4; // ebx
  struct _IP_ADAPTER_ADDRESSES_LH *v5; // rdi
  signed int v6; // eax
  PVOID *v7; // rcx
  __int64 v8; // r9
  __int64 v9; // rdx
  Windows::Networking::UX::Internal::CAdapterProperties *SizePointer; // [rsp+60h] [rbp+8h] BYREF

  SizePointer = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_07bd92578572370284dbe53730fdfa75_Traceguids);
  *a2 = 0;
  LODWORD(SizePointer) = 0;
  AdaptersAddresses = GetAdaptersAddresses(0, 0xA6u, 0, 0, (PULONG)&SizePointer);
  v4 = AdaptersAddresses;
  if ( AdaptersAddresses == 111 )
  {
    v5 = (struct _IP_ADAPTER_ADDRESSES_LH *)CoTaskMemAlloc((unsigned int)SizePointer);
    if ( !v5 )
    {
      v4 = 14;
LABEL_25:
      v7 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_26;
    }
    v6 = GetAdaptersAddresses(0, 0xA6u, 0, v5, (PULONG)&SizePointer);
    v4 = v6;
    if ( !v6 )
    {
      *a2 = v5;
      v7 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_28;
    }
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      if ( v6 > 0 )
        v8 = (unsigned __int16)v6 | 0x80070000;
      else
        v8 = (unsigned int)v6;
      v9 = 22;
LABEL_24:
      WPP_SF_d(v7[2], v9, WPP_07bd92578572370284dbe53730fdfa75_Traceguids, v8);
      goto LABEL_25;
    }
  }
  else
  {
    if ( AdaptersAddresses > 0 )
      AdaptersAddresses = (unsigned __int16)AdaptersAddresses | 0x80070000;
    if ( AdaptersAddresses >= 0 )
      goto LABEL_25;
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      if ( v4 > 0 )
        v8 = (unsigned __int16)v4 | 0x80070000;
      else
        v8 = (unsigned int)v4;
      v9 = 23;
      goto LABEL_24;
    }
  }
LABEL_26:
  if ( v4 > 0 )
    v4 = (unsigned __int16)v4 | 0x80070000;
LABEL_28:
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x40) != 0 )
    WPP_SF_d(v7[2], 24, WPP_07bd92578572370284dbe53730fdfa75_Traceguids, (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800417e0  mov     [rsp+arg_0], rcx
0x1800417e5  push    rbx
0x1800417e6  push    rsi
0x1800417e7  push    rdi
0x1800417e8  push    r14
0x1800417ea  sub     rsp, 38h
0x1800417ee  mov     rsi, rdx
0x1800417f1  lea     r14, WPP_GLOBAL_Control
0x1800417f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800417ff  cmp     rcx, r14
0x180041802  jz      short loc_18004181F
0x180041804  test    byte ptr [rcx+1Ch], 40h
0x180041808  jz      short loc_18004181F
0x18004180a  mov     edx, 15h
0x18004180f  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x180041816  mov     rcx, [rcx+10h]
0x18004181a  call    WPP_SF_
0x18004181f  mov     qword ptr [rsi], 0
0x180041826  mov     dword ptr [rsp+58h+arg_0], 0
0x18004182e  lea     rax, [rsp+58h+arg_0]
0x180041833  mov     [rsp+58h+SizePointer], rax; SizePointer
0x180041838  xor     r9d, r9d; AdapterAddresses
0x18004183b  xor     r8d, r8d; Reserved
0x18004183e  mov     edx, 0A6h; Flags
0x180041843  xor     ecx, ecx; Family
0x180041845  call    cs:__imp_GetAdaptersAddresses
0x18004184b  mov     ebx, eax
0x18004184d  cmp     eax, 6Fh ; 'o'
0x180041850  jnz     loc_1800418DC
0x180041856  mov     ecx, dword ptr [rsp+58h+arg_0]; cb
0x18004185a  call    cs:__imp_CoTaskMemAlloc
0x180041860  mov     rdi, rax
0x180041863  test    rax, rax
0x180041866  jz      short loc_1800418D5
0x180041868  lea     rax, [rsp+58h+arg_0]
0x18004186d  mov     [rsp+58h+SizePointer], rax; SizePointer
0x180041872  mov     r9, rdi; AdapterAddresses
0x180041875  xor     r8d, r8d; Reserved
0x180041878  lea     edx, [rbx+37h]; Flags
0x18004187b  xor     ecx, ecx; Family
0x18004187d  call    cs:__imp_GetAdaptersAddresses
0x180041883  mov     ebx, eax
0x180041885  test    eax, eax
0x180041887  jnz     short loc_180041898
0x180041889  mov     [rsi], rdi
0x18004188c  mov     rcx, cs:WPP_GLOBAL_Control
0x180041893  jmp     loc_18004193B
0x180041898  movzx   r9d, bx
0x18004189c  test    ebx, ebx
0x18004189e  jle     short loc_1800418A8
0x1800418a0  mov     eax, r9d
0x1800418a3  or      eax, 80070000h
0x1800418a8  test    eax, eax
0x1800418aa  jns     short loc_180041927
0x1800418ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800418b3  cmp     rcx, r14
0x1800418b6  jz      short loc_18004192E
0x1800418b8  test    byte ptr [rcx+1Ch], 2
0x1800418bc  jz      short loc_18004192E
0x1800418be  test    ebx, ebx
0x1800418c0  jg      short loc_1800418C7
0x1800418c2  mov     r9d, ebx
0x1800418c5  jmp     short loc_1800418CE
0x1800418c7  or      r9d, 80070000h
0x1800418ce  mov     edx, 16h
0x1800418d3  jmp     short loc_180041917
0x1800418d5  mov     ebx, 0Eh
0x1800418da  jmp     short loc_180041927
0x1800418dc  movzx   r9d, bx
0x1800418e0  test    ebx, ebx
0x1800418e2  jle     short loc_1800418EC
0x1800418e4  mov     eax, r9d
0x1800418e7  or      eax, 80070000h
0x1800418ec  test    eax, eax
0x1800418ee  jns     short loc_180041927
0x1800418f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800418f7  cmp     rcx, r14
0x1800418fa  jz      short loc_18004192E
0x1800418fc  test    byte ptr [rcx+1Ch], 2
0x180041900  jz      short loc_18004192E
0x180041902  test    ebx, ebx
0x180041904  jg      short loc_18004190B
0x180041906  mov     r9d, ebx
0x180041909  jmp     short loc_180041912
0x18004190b  or      r9d, 80070000h
0x180041912  mov     edx, 17h
0x180041917  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x18004191e  mov     rcx, [rcx+10h]
0x180041922  call    WPP_SF_d
0x180041927  mov     rcx, cs:WPP_GLOBAL_Control
0x18004192e  test    ebx, ebx
0x180041930  jle     short loc_18004193B
0x180041932  movzx   ebx, bx
0x180041935  or      ebx, 80070000h
0x18004193b  cmp     rcx, r14
0x18004193e  jz      short loc_18004195E
0x180041940  test    byte ptr [rcx+1Ch], 40h
0x180041944  jz      short loc_18004195E
0x180041946  mov     edx, 18h
0x18004194b  mov     r9d, ebx
0x18004194e  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x180041955  mov     rcx, [rcx+10h]
0x180041959  call    WPP_SF_d
0x18004195e  mov     eax, ebx
0x180041960  jmp     short loc_180041966
0x180041962  mov     eax, dword ptr [rsp+58h+arg_0]
0x180041966  add     rsp, 38h
0x18004196a  pop     r14
0x18004196c  pop     rdi
0x18004196d  pop     rsi
0x18004196e  pop     rbx
0x18004196f  retn
```
