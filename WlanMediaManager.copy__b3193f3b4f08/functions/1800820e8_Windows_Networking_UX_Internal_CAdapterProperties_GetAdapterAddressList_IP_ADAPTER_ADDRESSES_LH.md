# Windows::Networking::UX::Internal::CAdapterProperties::GetAdapterAddressList(_IP_ADAPTER_ADDRESSES_LH * *)

- ea: `0x1800820e8`
- end: `0x180082279`
- name: `?GetAdapterAddressList@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAJPEAPEAU_IP_ADAPTER_ADDRESSES_LH@@@Z`
- size: `401`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::CAdapterProperties *__hidden this, struct _IP_ADAPTER_ADDRESSES_LH **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180082b60`

## callees

- `0x18000de4c`
- `0x18001d4d4`
- `0x1800820e8`

## import_xrefs

- `IPHLPAPI!GetAdaptersAddresses` at `0x18008214d`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180082185`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18008214d`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180082185`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180082162`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180082162`

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
0x1800820e8  mov     [rsp+arg_0], rcx
0x1800820ed  push    rbx
0x1800820ee  push    rsi
0x1800820ef  push    rdi
0x1800820f0  push    r14
0x1800820f2  sub     rsp, 38h
0x1800820f6  mov     rsi, rdx
0x1800820f9  lea     r14, WPP_GLOBAL_Control
0x180082100  mov     rcx, cs:WPP_GLOBAL_Control
0x180082107  cmp     rcx, r14
0x18008210a  jz      short loc_180082127
0x18008210c  test    byte ptr [rcx+1Ch], 40h
0x180082110  jz      short loc_180082127
0x180082112  mov     edx, 15h
0x180082117  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x18008211e  mov     rcx, [rcx+10h]
0x180082122  call    WPP_SF_
0x180082127  mov     qword ptr [rsi], 0
0x18008212e  mov     dword ptr [rsp+58h+arg_0], 0
0x180082136  lea     rax, [rsp+58h+arg_0]
0x18008213b  mov     [rsp+58h+SizePointer], rax; SizePointer
0x180082140  xor     r9d, r9d; AdapterAddresses
0x180082143  xor     r8d, r8d; Reserved
0x180082146  mov     edx, 0A6h; Flags
0x18008214b  xor     ecx, ecx; Family
0x18008214d  call    cs:__imp_GetAdaptersAddresses
0x180082153  mov     ebx, eax
0x180082155  cmp     eax, 6Fh ; 'o'
0x180082158  jnz     loc_1800821E4
0x18008215e  mov     ecx, dword ptr [rsp+58h+arg_0]; cb
0x180082162  call    cs:__imp_CoTaskMemAlloc
0x180082168  mov     rdi, rax
0x18008216b  test    rax, rax
0x18008216e  jz      short loc_1800821DD
0x180082170  lea     rax, [rsp+58h+arg_0]
0x180082175  mov     [rsp+58h+SizePointer], rax; SizePointer
0x18008217a  mov     r9, rdi; AdapterAddresses
0x18008217d  xor     r8d, r8d; Reserved
0x180082180  lea     edx, [rbx+37h]; Flags
0x180082183  xor     ecx, ecx; Family
0x180082185  call    cs:__imp_GetAdaptersAddresses
0x18008218b  mov     ebx, eax
0x18008218d  test    eax, eax
0x18008218f  jnz     short loc_1800821A0
0x180082191  mov     [rsi], rdi
0x180082194  mov     rcx, cs:WPP_GLOBAL_Control
0x18008219b  jmp     loc_180082243
0x1800821a0  movzx   r9d, bx
0x1800821a4  test    ebx, ebx
0x1800821a6  jle     short loc_1800821B0
0x1800821a8  mov     eax, r9d
0x1800821ab  or      eax, 80070000h
0x1800821b0  test    eax, eax
0x1800821b2  jns     short loc_18008222F
0x1800821b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800821bb  cmp     rcx, r14
0x1800821be  jz      short loc_180082236
0x1800821c0  test    byte ptr [rcx+1Ch], 2
0x1800821c4  jz      short loc_180082236
0x1800821c6  test    ebx, ebx
0x1800821c8  jg      short loc_1800821CF
0x1800821ca  mov     r9d, ebx
0x1800821cd  jmp     short loc_1800821D6
0x1800821cf  or      r9d, 80070000h
0x1800821d6  mov     edx, 16h
0x1800821db  jmp     short loc_18008221F
0x1800821dd  mov     ebx, 0Eh
0x1800821e2  jmp     short loc_18008222F
0x1800821e4  movzx   r9d, bx
0x1800821e8  test    ebx, ebx
0x1800821ea  jle     short loc_1800821F4
0x1800821ec  mov     eax, r9d
0x1800821ef  or      eax, 80070000h
0x1800821f4  test    eax, eax
0x1800821f6  jns     short loc_18008222F
0x1800821f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800821ff  cmp     rcx, r14
0x180082202  jz      short loc_180082236
0x180082204  test    byte ptr [rcx+1Ch], 2
0x180082208  jz      short loc_180082236
0x18008220a  test    ebx, ebx
0x18008220c  jg      short loc_180082213
0x18008220e  mov     r9d, ebx
0x180082211  jmp     short loc_18008221A
0x180082213  or      r9d, 80070000h
0x18008221a  mov     edx, 17h
0x18008221f  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x180082226  mov     rcx, [rcx+10h]
0x18008222a  call    WPP_SF_d
0x18008222f  mov     rcx, cs:WPP_GLOBAL_Control
0x180082236  test    ebx, ebx
0x180082238  jle     short loc_180082243
0x18008223a  movzx   ebx, bx
0x18008223d  or      ebx, 80070000h
0x180082243  cmp     rcx, r14
0x180082246  jz      short loc_180082266
0x180082248  test    byte ptr [rcx+1Ch], 40h
0x18008224c  jz      short loc_180082266
0x18008224e  mov     edx, 18h
0x180082253  mov     r9d, ebx
0x180082256  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x18008225d  mov     rcx, [rcx+10h]
0x180082261  call    WPP_SF_d
0x180082266  mov     eax, ebx
0x180082268  jmp     short loc_18008226E
0x18008226a  mov     eax, dword ptr [rsp+58h+arg_0]
0x18008226e  add     rsp, 38h
0x180082272  pop     r14
0x180082274  pop     rdi
0x180082275  pop     rsi
0x180082276  pop     rbx
0x180082277  retn
```
