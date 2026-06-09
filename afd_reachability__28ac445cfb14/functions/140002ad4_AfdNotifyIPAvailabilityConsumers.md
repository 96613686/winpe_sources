# AfdNotifyIPAvailabilityConsumers

- ea: `0x140002ad4`
- end: `0x140002c86`
- name: `AfdNotifyIPAvailabilityConsumers`
- size: `434`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140003164`
- `0x140003338`

## callees

- `0x140002ad4`
- `0x140002f44`
- `0x1400726a0`
- `0x1400932cc`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x140002ba3`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140002ba3`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140002c1a`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140002c1a`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140002b83`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140002b83`
- `ntoskrnl!EtwWrite` at `0x140002c06`
- `ntoskrnl!EtwWrite` at `0x140002c06`
- `NETIO!GetDefaultCompartmentId` at `0x140002b0d`
- `NETIO!GetDefaultCompartmentId` at `0x140002b0d`

## pseudocode

```c
void __fastcall AfdNotifyIPAvailabilityConsumers(char a1, int a2)
{
  int v3; // eax
  int updated; // eax
  struct _EX_RUNDOWN_REF *Current; // rsi
  __int64 *v6; // rcx
  const EVENT_DESCRIPTOR *v7; // rdx
  NTSTATUS v8; // eax
  __int64 v9; // [rsp+40h] [rbp-28h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-20h] BYREF

  v9 = 0;
  UserData = 0;
  if ( a2 == 1 || a2 == GetDefaultCompartmentId() )
  {
    v3 = v9 | 1;
    HIDWORD(v9) = -1;
    LODWORD(v9) = v9 | 1;
    if ( a1 )
      LODWORD(v9) = v3 | 2;
    updated = ZwUpdateWnfStateData(&WNF_SEB_IP_ADDRESS_AVAILABLE, &v9, 8);
    if ( updated < 0 && (BYTE2(xmmword_1400875E0) & 2) != 0 )
      WPP_SF_d(1041, 32, WPP_8fbd4859c37b31fb3b8ef6913c458dec_Traceguids, (unsigned int)updated);
    Current = (struct _EX_RUNDOWN_REF *)AfdPodGetCurrent();
    if ( ExAcquireRundownProtection(Current + 2) )
    {
      *(_QWORD *)&UserData.Size = 16;
      v6 = AfdNetworkMgrFirstAddressArrivalGuid;
      if ( !a1 )
        v6 = AfdNetworkMgrLastAddressRemovalGuid;
      v7 = (const EVENT_DESCRIPTOR *)Symbol_FirstAddressArrivalEvent;
      UserData.Ptr = (ULONGLONG)v6;
      if ( !a1 )
        v7 = &Symbol_LastAddressRemovalEvent;
      v8 = EtwWrite(Current[19].Count, v7, 0, 1u, &UserData);
      if ( v8 < 0 && (BYTE2(xmmword_1400875E0) & 2) != 0 )
        WPP_SF_d(1041, 33, WPP_8fbd4859c37b31fb3b8ef6913c458dec_Traceguids, (unsigned int)v8);
      ExReleaseRundownProtection(Current + 2);
    }
  }
}

```

## disassembly

```asm
0x140002ad4  mov     [rsp+arg_0], rbx
0x140002ad9  mov     [rsp+arg_8], rsi
0x140002ade  push    rdi
0x140002adf  sub     rsp, 60h
0x140002ae3  mov     rax, cs:__security_cookie
0x140002aea  xor     rax, rsp
0x140002aed  mov     [rsp+68h+var_10], rax
0x140002af2  mov     [rsp+68h+var_28], 0
0x140002afb  xorps   xmm0, xmm0
0x140002afe  mov     ebx, edx
0x140002b00  mov     dil, cl
0x140002b03  movups  xmmword ptr [rsp+68h+var_20.Ptr], xmm0
0x140002b08  cmp     edx, 1
0x140002b0b  jz      short loc_140002B3B
0x140002b0d  call    cs:__imp_GetDefaultCompartmentId
0x140002b14  nop     dword ptr [rax+rax+00h]
0x140002b19  cmp     ebx, eax
0x140002b1b  jz      short loc_140002B3B
0x140002b1d  mov     rcx, [rsp+68h+var_10]
0x140002b22  xor     rcx, rsp; StackCookie
0x140002b25  call    __security_check_cookie
0x140002b2a  mov     rbx, [rsp+68h+arg_0]
0x140002b2f  mov     rsi, [rsp+68h+arg_8]
0x140002b34  add     rsp, 60h
0x140002b38  pop     rdi
0x140002b39  retn
0x140002b3b  mov     eax, dword ptr [rsp+68h+var_28]
0x140002b3f  or      eax, 1
0x140002b42  mov     dword ptr [rsp+68h+var_28+4], 0FFFFFFFFh
0x140002b4a  mov     dword ptr [rsp+68h+var_28], eax
0x140002b4e  test    dil, dil
0x140002b51  jnz     loc_140002C2B
0x140002b57  xor     r9d, r9d
0x140002b5a  mov     [rsp+68h+var_38], 0
0x140002b62  mov     [rsp+68h+var_40], 0
0x140002b6a  lea     rdx, [rsp+68h+var_28]
0x140002b6f  lea     rcx, WNF_SEB_IP_ADDRESS_AVAILABLE
0x140002b76  mov     [rsp+68h+UserData], 0
0x140002b7f  lea     r8d, [r9+8]
0x140002b83  call    cs:__imp_ZwUpdateWnfStateData
0x140002b8a  nop     dword ptr [rax+rax+00h]
0x140002b8f  test    eax, eax
0x140002b91  js      loc_140002C37
0x140002b97  call    AfdPodGetCurrent
0x140002b9c  mov     rsi, rax
0x140002b9f  lea     rcx, [rax+10h]; RunRef
0x140002ba3  call    cs:__imp_ExAcquireRundownProtection
0x140002baa  nop     dword ptr [rax+rax+00h]
0x140002baf  test    al, al
0x140002bb1  jz      loc_140002B1D
0x140002bb7  test    dil, dil
0x140002bba  mov     qword ptr [rsp+68h+var_20.Size], 10h
0x140002bc3  lea     rax, AfdNetworkMgrLastAddressRemovalGuid
0x140002bca  mov     r9d, 1; UserDataCount
0x140002bd0  lea     rcx, AfdNetworkMgrFirstAddressArrivalGuid
0x140002bd7  cmovz   rcx, rax
0x140002bdb  lea     rdx, Symbol_FirstAddressArrivalEvent
0x140002be2  lea     rax, Symbol_LastAddressRemovalEvent
0x140002be9  mov     [rsp+68h+var_20.Ptr], rcx
0x140002bee  mov     rcx, [rsi+98h]; RegHandle
0x140002bf5  cmovz   rdx, rax; EventDescriptor
0x140002bf9  lea     rax, [rsp+68h+var_20]
0x140002bfe  xor     r8d, r8d; ActivityId
0x140002c01  mov     [rsp+68h+UserData], rax; UserData
0x140002c06  call    cs:__imp_EtwWrite
0x140002c0d  nop     dword ptr [rax+rax+00h]
0x140002c12  test    eax, eax
0x140002c14  js      short loc_140002C62
0x140002c16  lea     rcx, [rsi+10h]; RunRef
0x140002c1a  call    cs:__imp_ExReleaseRundownProtection
0x140002c21  nop     dword ptr [rax+rax+00h]
0x140002c26  jmp     loc_140002B1D
0x140002c2b  or      eax, 2
0x140002c2e  mov     dword ptr [rsp+68h+var_28], eax
0x140002c32  jmp     loc_140002B57
0x140002c37  test    byte ptr cs:xmmword_1400875E0+2, 2
0x140002c3e  jz      loc_140002B97
0x140002c44  mov     edx, 20h ; ' '
0x140002c49  lea     r8, WPP_8fbd4859c37b31fb3b8ef6913c458dec_Traceguids
0x140002c50  mov     ecx, 411h
0x140002c55  mov     r9d, eax
0x140002c58  call    WPP_SF_d
0x140002c5d  jmp     loc_140002B97
0x140002c62  test    byte ptr cs:xmmword_1400875E0+2, 2
0x140002c69  jz      short loc_140002C16
0x140002c6b  mov     edx, 21h ; '!'
0x140002c70  lea     r8, WPP_8fbd4859c37b31fb3b8ef6913c458dec_Traceguids
0x140002c77  mov     ecx, 411h
0x140002c7c  mov     r9d, eax
0x140002c7f  call    WPP_SF_d
0x140002c84  jmp     short loc_140002C16
```
