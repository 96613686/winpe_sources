# CNetworkHandler::_GetNetworkMask(ulong)

- ea: `0x18000d4e4`
- end: `0x18000d6cf`
- name: `?_GetNetworkMask@CNetworkHandler@@AEAA_KK@Z`
- size: `491`
- prototype: `__int64 __fastcall(CNetworkHandler *this, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000dc80`

## callees

- `0x18000a644`
- `0x18000a778`
- `0x18000d4e4`
- `0x18000e1b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d551`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d551`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d6b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d6b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d5bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d5bf`
- `WS2_32!__imp_inet_addr` at `0x18000d614`
- `WS2_32!__imp_inet_addr` at `0x18000d614`
- `IPHLPAPI!GetAdaptersInfo` at `0x18000d539`
- `IPHLPAPI!GetAdaptersInfo` at `0x18000d59b`
- `IPHLPAPI!GetAdaptersInfo` at `0x18000d539`
- `IPHLPAPI!GetAdaptersInfo` at `0x18000d59b`

## pseudocode

```c
__int64 __fastcall CNetworkHandler::_GetNetworkMask(CNetworkHandler *this, int a2)
{
  __int64 v3; // r14
  __int64 v4; // rsi
  struct _IP_ADAPTER_INFO *v5; // rdi
  struct _IP_ADAPTER_INFO *v6; // rax
  _QWORD *v7; // rcx
  struct _IP_ADAPTER_INFO *v8; // rbx
  unsigned int v9; // eax
  __int64 v10; // r8
  unsigned int v11; // ebp
  int v12; // eax
  __int64 v13; // rdx
  CNetworkHandler *SizePointer; // [rsp+70h] [rbp+8h] BYREF

  SizePointer = this;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 124, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
  v3 = 0;
  LODWORD(SizePointer) = 0;
  v4 = 33;
  GetAdaptersInfo(0, (PULONG)&SizePointer);
  if ( (unsigned int)SizePointer > 0x7FFFFFFFuLL )
  {
    v5 = 0;
LABEL_7:
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_32;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_29;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
    goto LABEL_28;
  }
  v6 = (struct _IP_ADAPTER_INFO *)CoTaskMemAlloc((unsigned int)SizePointer);
  v5 = v6;
  if ( !v6 )
    goto LABEL_7;
  if ( GetAdaptersInfo(v6, (PULONG)&SizePointer) )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_32;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_29;
    GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 126, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
    goto LABEL_28;
  }
  v8 = v5;
  while ( v8->Index != a2 )
  {
    v8 = v8->Next;
    if ( !v8 )
      goto LABEL_28;
  }
  v9 = inet_addr(v8->IpAddressList.IpMask.String);
  v11 = v9;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 127, v10, v8->Index, v9);
    v7 = WPP_GLOBAL_Control;
  }
  v12 = 1;
  v13 = 32;
  do
  {
    v4 = v3 + 1;
    if ( (v12 & v11) == 0 )
      v4 = v3;
    v12 *= 2;
    v3 = v4;
    --v13;
  }
  while ( v13 );
  if ( v7 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v7 + 28) & 8) == 0 )
    {
LABEL_29:
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x20) != 0 )
        WPP_SF_(v7[2], 129, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
      goto LABEL_32;
    }
    WPP_SF_DD(v7[2], 128, v10, v8->Index, v4);
LABEL_28:
    v7 = WPP_GLOBAL_Control;
    goto LABEL_29;
  }
LABEL_32:
  CoTaskMemFree(v5);
  return v4;
}

```

## disassembly

```asm
0x18000d4e4  mov     [rsp+SizePointer], rcx
0x18000d4e9  push    rbx
0x18000d4ea  push    rbp
0x18000d4eb  push    rsi
0x18000d4ec  push    rdi
0x18000d4ed  push    r14
0x18000d4ef  push    r15
0x18000d4f1  sub     rsp, 38h
0x18000d4f5  mov     ebp, edx
0x18000d4f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4fe  lea     r15, WPP_GLOBAL_Control
0x18000d505  cmp     rcx, r15
0x18000d508  jz      short loc_18000D525
0x18000d50a  test    byte ptr [rcx+1Ch], 20h
0x18000d50e  jz      short loc_18000D525
0x18000d510  mov     rcx, [rcx+10h]
0x18000d514  lea     r8, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000d51b  mov     edx, 7Ch ; '|'
0x18000d520  call    WPP_SF_
0x18000d525  xor     r14d, r14d
0x18000d528  lea     rdx, [rsp+68h+SizePointer]; SizePointer
0x18000d52d  xor     ecx, ecx; AdapterInfo
0x18000d52f  mov     dword ptr [rsp+68h+SizePointer], r14d
0x18000d534  mov     esi, 21h ; '!'
0x18000d539  call    cs:__imp_GetAdaptersInfo
0x18000d53f  mov     ecx, dword ptr [rsp+68h+SizePointer]; cb
0x18000d543  cmp     rcx, 7FFFFFFFh
0x18000d54a  jbe     short loc_18000D551
0x18000d54c  mov     edi, r14d
0x18000d54f  jmp     short loc_18000D55F
0x18000d551  call    cs:__imp_CoTaskMemAlloc
0x18000d557  mov     rdi, rax
0x18000d55a  test    rax, rax
0x18000d55d  jnz     short loc_18000D593
0x18000d55f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d566  cmp     rcx, r15
0x18000d569  jz      loc_18000D6B6
0x18000d56f  test    byte ptr [rcx+1Ch], 2
0x18000d573  jz      loc_18000D696
0x18000d579  mov     rcx, [rcx+10h]
0x18000d57d  lea     r8, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000d584  mov     edx, 7Dh ; '}'
0x18000d589  call    WPP_SF_
0x18000d58e  jmp     loc_18000D68F
0x18000d593  lea     rdx, [rsp+68h+SizePointer]; SizePointer
0x18000d598  mov     rcx, rdi; AdapterInfo
0x18000d59b  call    cs:__imp_GetAdaptersInfo
0x18000d5a1  test    eax, eax
0x18000d5a3  jz      short loc_18000D5F5
0x18000d5a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d5ac  cmp     rcx, r15
0x18000d5af  jz      loc_18000D6B6
0x18000d5b5  test    byte ptr [rcx+1Ch], 2
0x18000d5b9  jz      loc_18000D696
0x18000d5bf  call    cs:__imp_GetLastError
0x18000d5c5  test    eax, eax
0x18000d5c7  jle     short loc_18000D5D1
0x18000d5c9  movzx   eax, ax
0x18000d5cc  or      eax, 80070000h
0x18000d5d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d5d8  lea     r8, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000d5df  mov     edx, 7Eh ; '~'
0x18000d5e4  mov     r9d, eax
0x18000d5e7  mov     rcx, [rcx+10h]
0x18000d5eb  call    WPP_SF_d
0x18000d5f0  jmp     loc_18000D68F
0x18000d5f5  mov     rbx, rdi
0x18000d5f8  cmp     [rbx+1A0h], ebp
0x18000d5fe  jz      short loc_18000D60D
0x18000d600  mov     rbx, [rbx]
0x18000d603  test    rbx, rbx
0x18000d606  jnz     short loc_18000D5F8
0x18000d608  jmp     loc_18000D68F
0x18000d60d  lea     rcx, [rbx+1D0h]; cp
0x18000d614  call    cs:__imp_inet_addr
0x18000d61a  mov     ebp, eax
0x18000d61c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d623  cmp     rcx, r15
0x18000d626  jz      short loc_18000D64E
0x18000d628  test    byte ptr [rcx+1Ch], 8
0x18000d62c  jz      short loc_18000D64E
0x18000d62e  mov     r9d, [rbx+1A0h]
0x18000d635  mov     edx, 7Fh
0x18000d63a  mov     rcx, [rcx+10h]
0x18000d63e  mov     [rsp+68h+var_48], eax
0x18000d642  call    WPP_SF_DD
0x18000d647  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d64e  mov     eax, 1
0x18000d653  lea     edx, [rax+1Fh]
0x18000d656  test    ebp, eax
0x18000d658  lea     rsi, [r14+1]
0x18000d65c  cmovz   rsi, r14
0x18000d660  add     eax, eax
0x18000d662  mov     r14, rsi
0x18000d665  sub     rdx, 1
0x18000d669  jnz     short loc_18000D656
0x18000d66b  cmp     rcx, r15
0x18000d66e  jz      short loc_18000D6B6
0x18000d670  test    byte ptr [rcx+1Ch], 8
0x18000d674  jz      short loc_18000D696
0x18000d676  mov     r9d, [rbx+1A0h]
0x18000d67d  mov     edx, 80h
0x18000d682  mov     rcx, [rcx+10h]
0x18000d686  mov     [rsp+68h+var_48], esi
0x18000d68a  call    WPP_SF_DD
0x18000d68f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d696  cmp     rcx, r15
0x18000d699  jz      short loc_18000D6B6
0x18000d69b  test    byte ptr [rcx+1Ch], 20h
0x18000d69f  jz      short loc_18000D6B6
0x18000d6a1  mov     rcx, [rcx+10h]
0x18000d6a5  lea     r8, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000d6ac  mov     edx, 81h
0x18000d6b1  call    WPP_SF_
0x18000d6b6  mov     rcx, rdi; pv
0x18000d6b9  call    cs:__imp_CoTaskMemFree
0x18000d6bf  mov     rax, rsi
0x18000d6c2  add     rsp, 38h
0x18000d6c6  pop     r15
0x18000d6c8  pop     r14
0x18000d6ca  pop     rdi
0x18000d6cb  pop     rsi
0x18000d6cc  pop     rbp
0x18000d6cd  pop     rbx
0x18000d6ce  retn
```
