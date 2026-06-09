# Windows::Networking::UX::Internal::CAdapterProperties::GetAdapterAddressList(_IP_ADAPTER_ADDRESSES_LH * *)

- ea: `0x180003b70`
- end: `0x180003d01`
- name: `?GetAdapterAddressList@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAJPEAPEAU_IP_ADAPTER_ADDRESSES_LH@@@Z`
- size: `401`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::CAdapterProperties *__hidden this, struct _IP_ADAPTER_ADDRESSES_LH **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003108`

## callees

- `0x180003b70`
- `0x180005be0`
- `0x180005c80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003bea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003bea`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180003bd5`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180003c0d`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180003bd5`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180003c0d`

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
0x180003b70  mov     [rsp+arg_0], rcx
0x180003b75  push    rbx
0x180003b76  push    rsi
0x180003b77  push    rdi
0x180003b78  push    r14
0x180003b7a  sub     rsp, 38h
0x180003b7e  mov     rsi, rdx
0x180003b81  lea     r14, WPP_GLOBAL_Control
0x180003b88  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b8f  cmp     rcx, r14
0x180003b92  jz      short loc_180003BAF
0x180003b94  test    byte ptr [rcx+1Ch], 40h
0x180003b98  jz      short loc_180003BAF
0x180003b9a  mov     edx, 15h
0x180003b9f  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x180003ba6  mov     rcx, [rcx+10h]
0x180003baa  call    WPP_SF_
0x180003baf  mov     qword ptr [rsi], 0
0x180003bb6  mov     dword ptr [rsp+58h+arg_0], 0
0x180003bbe  lea     rax, [rsp+58h+arg_0]
0x180003bc3  mov     [rsp+58h+SizePointer], rax; SizePointer
0x180003bc8  xor     r9d, r9d; AdapterAddresses
0x180003bcb  xor     r8d, r8d; Reserved
0x180003bce  mov     edx, 0A6h; Flags
0x180003bd3  xor     ecx, ecx; Family
0x180003bd5  call    cs:__imp_GetAdaptersAddresses
0x180003bdb  mov     ebx, eax
0x180003bdd  cmp     eax, 6Fh ; 'o'
0x180003be0  jnz     loc_180003C6C
0x180003be6  mov     ecx, dword ptr [rsp+58h+arg_0]; cb
0x180003bea  call    cs:__imp_CoTaskMemAlloc
0x180003bf0  mov     rdi, rax
0x180003bf3  test    rax, rax
0x180003bf6  jz      short loc_180003C65
0x180003bf8  lea     rax, [rsp+58h+arg_0]
0x180003bfd  mov     [rsp+58h+SizePointer], rax; SizePointer
0x180003c02  mov     r9, rdi; AdapterAddresses
0x180003c05  xor     r8d, r8d; Reserved
0x180003c08  lea     edx, [rbx+37h]; Flags
0x180003c0b  xor     ecx, ecx; Family
0x180003c0d  call    cs:__imp_GetAdaptersAddresses
0x180003c13  mov     ebx, eax
0x180003c15  test    eax, eax
0x180003c17  jnz     short loc_180003C28
0x180003c19  mov     [rsi], rdi
0x180003c1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c23  jmp     loc_180003CCB
0x180003c28  movzx   r9d, bx
0x180003c2c  test    ebx, ebx
0x180003c2e  jle     short loc_180003C38
0x180003c30  mov     eax, r9d
0x180003c33  or      eax, 80070000h
0x180003c38  test    eax, eax
0x180003c3a  jns     short loc_180003CB7
0x180003c3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c43  cmp     rcx, r14
0x180003c46  jz      short loc_180003CBE
0x180003c48  test    byte ptr [rcx+1Ch], 2
0x180003c4c  jz      short loc_180003CBE
0x180003c4e  test    ebx, ebx
0x180003c50  jg      short loc_180003C57
0x180003c52  mov     r9d, ebx
0x180003c55  jmp     short loc_180003C5E
0x180003c57  or      r9d, 80070000h
0x180003c5e  mov     edx, 16h
0x180003c63  jmp     short loc_180003CA7
0x180003c65  mov     ebx, 0Eh
0x180003c6a  jmp     short loc_180003CB7
0x180003c6c  movzx   r9d, bx
0x180003c70  test    ebx, ebx
0x180003c72  jle     short loc_180003C7C
0x180003c74  mov     eax, r9d
0x180003c77  or      eax, 80070000h
0x180003c7c  test    eax, eax
0x180003c7e  jns     short loc_180003CB7
0x180003c80  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c87  cmp     rcx, r14
0x180003c8a  jz      short loc_180003CBE
0x180003c8c  test    byte ptr [rcx+1Ch], 2
0x180003c90  jz      short loc_180003CBE
0x180003c92  test    ebx, ebx
0x180003c94  jg      short loc_180003C9B
0x180003c96  mov     r9d, ebx
0x180003c99  jmp     short loc_180003CA2
0x180003c9b  or      r9d, 80070000h
0x180003ca2  mov     edx, 17h
0x180003ca7  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x180003cae  mov     rcx, [rcx+10h]
0x180003cb2  call    WPP_SF_d
0x180003cb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180003cbe  test    ebx, ebx
0x180003cc0  jle     short loc_180003CCB
0x180003cc2  movzx   ebx, bx
0x180003cc5  or      ebx, 80070000h
0x180003ccb  cmp     rcx, r14
0x180003cce  jz      short loc_180003CEE
0x180003cd0  test    byte ptr [rcx+1Ch], 40h
0x180003cd4  jz      short loc_180003CEE
0x180003cd6  mov     edx, 18h
0x180003cdb  mov     r9d, ebx
0x180003cde  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x180003ce5  mov     rcx, [rcx+10h]
0x180003ce9  call    WPP_SF_d
0x180003cee  mov     eax, ebx
0x180003cf0  jmp     short loc_180003CF6
0x180003cf2  mov     eax, dword ptr [rsp+58h+arg_0]
0x180003cf6  add     rsp, 38h
0x180003cfa  pop     r14
0x180003cfc  pop     rdi
0x180003cfd  pop     rsi
0x180003cfe  pop     rbx
0x180003cff  retn
```
