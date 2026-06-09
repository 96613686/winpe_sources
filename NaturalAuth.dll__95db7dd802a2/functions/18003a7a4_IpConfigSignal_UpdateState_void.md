# IpConfigSignal::UpdateState(void)

- ea: `0x18003a7a4`
- end: `0x18003a9a2`
- name: `?UpdateState@IpConfigSignal@@AEAAXXZ`
- size: `510`
- prototype: `void __fastcall(IpConfigSignal *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180039608`
- `0x180039810`

## callees

- `0x180005140`
- `0x18000a7f8`
- `0x18002d62c`
- `0x180038938`
- `0x180038be4`
- `0x180038e80`
- `0x180038f88`
- `0x180039130`
- `0x18003981c`
- `0x18003a7a4`
- `0x18003a9dc`

## import_xrefs

- `IPHLPAPI!GetAdaptersAddresses` at `0x18003a869`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18003a869`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall IpConfigSignal::UpdateState(IpConfigSignal *this)
{
  IP_ADAPTER_ADDRESSES_LH *v2; // rbx
  _lambda_e0961d09be37bcacb226eb1c325cdc72_ *v3; // rax
  ULONG AdaptersAddresses; // eax
  PIP_ADAPTER_ADDRESSES v5; // rdi
  IP_ADAPTER_ADDRESSES_LH *v6; // rax
  size_t v7; // rbx
  __int64 v8; // rax
  unsigned int matched; // [rsp+30h] [rbp-98h] BYREF
  unsigned int v10; // [rsp+34h] [rbp-94h] BYREF
  PIP_ADAPTER_ADDRESSES AdapterAddresses[2]; // [rsp+38h] [rbp-90h] BYREF
  __int64 v12; // [rsp+48h] [rbp-80h]
  std::exception *v13; // [rsp+50h] [rbp-78h] BYREF
  _BYTE v14[48]; // [rsp+58h] [rbp-70h] BYREF
  _BYTE v15[64]; // [rsp+88h] [rbp-40h] BYREF
  bool v16; // [rsp+D8h] [rbp+10h] BYREF
  ULONG SizePointer; // [rsp+E0h] [rbp+18h] BYREF
  unsigned int v18; // [rsp+E8h] [rbp+20h] BYREF

  matched = 2;
  v16 = 1;
  v10 = 0;
  SizePointer = 4096;
  *(_OWORD *)AdapterAddresses = 0;
  v12 = 0;
  std::vector<unsigned char>::_Construct_n<>(AdapterAddresses);
  v2 = AdapterAddresses[0];
  v18 = 0;
  v3 = _lambda_e0961d09be37bcacb226eb1c325cdc72_::_lambda_e0961d09be37bcacb226eb1c325cdc72_(
         (_lambda_e0961d09be37bcacb226eb1c325cdc72_ *)v15,
         &v16,
         &v10,
         (enum NA_RULE_STATE *)&matched,
         &SizePointer,
         &v18);
  wil::ScopeExit<_lambda_e0961d09be37bcacb226eb1c325cdc72_>(v14, v3);
  try
  {
    while ( 1 )
    {
      AdaptersAddresses = GetAdaptersAddresses(0, 0x186u, 0, v2, &SizePointer);
      v10 = AdaptersAddresses;
      if ( AdaptersAddresses != 111 )
        break;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_d1cee8b2867932f5b010f98517c4d23a_Traceguids, SizePointer);
      v5 = AdapterAddresses[1];
      if ( (PIP_ADAPTER_ADDRESSES)SizePointer < (PIP_ADAPTER_ADDRESSES)((char *)AdapterAddresses[1]
                                                                      - (char *)AdapterAddresses[0]) )
      {
        v6 = (PIP_ADAPTER_ADDRESSES)((char *)AdapterAddresses[0] + SizePointer);
LABEL_12:
        AdapterAddresses[1] = v6;
        goto LABEL_13;
      }
      if ( (PIP_ADAPTER_ADDRESSES)SizePointer > (PIP_ADAPTER_ADDRESSES)((char *)AdapterAddresses[1]
                                                                      - (char *)AdapterAddresses[0]) )
      {
        if ( SizePointer <= v12 - (unsigned __int64)AdapterAddresses[0] )
        {
          v7 = SizePointer - (unsigned __int64)((char *)AdapterAddresses[1] - (char *)AdapterAddresses[0]);
          memset_0(AdapterAddresses[1], 0, v7);
          v6 = (PIP_ADAPTER_ADDRESSES)((char *)v5 + v7);
          goto LABEL_12;
        }
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(AdapterAddresses, SizePointer);
      }
LABEL_13:
      v2 = AdapterAddresses[0];
      if ( ++v18 >= 0xA )
        goto LABEL_20;
    }
    if ( AdaptersAddresses )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_d1cee8b2867932f5b010f98517c4d23a_Traceguids,
          AdaptersAddresses);
    }
    else
    {
      matched = IpConfigSignal::MatchProperties(this, v2);
    }
LABEL_20:
    GenericPlugin::DefaultSignal::SetState(this, matched);
    v16 = 0;
  }
  catch ( std::bad_alloc )
  {
  }
  catch ( std::exception *v13 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = (*(__int64 (__fastcall **)(std::exception *))(*(_QWORD *)v13 + 8LL))(v13);
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_d1cee8b2867932f5b010f98517c4d23a_Traceguids, v8);
    }
  }
  wil::details::ScopeExitFn<_lambda_e0961d09be37bcacb226eb1c325cdc72_>::~ScopeExitFn<_lambda_e0961d09be37bcacb226eb1c325cdc72_>(v14);
  std::vector<unsigned char>::_Tidy(AdapterAddresses);
}

```

## disassembly

```asm
0x18003a7a4  mov     rax, rsp
0x18003a7a7  mov     [rax+8], rbx
0x18003a7ab  push    rsi
0x18003a7ac  push    rdi
0x18003a7ad  push    r15
0x18003a7af  sub     rsp, 0B0h
0x18003a7b6  mov     rsi, rcx
0x18003a7b9  mov     [rsp+0C8h+var_98], 2
0x18003a7c1  mov     byte ptr [rax+10h], 1
0x18003a7c5  mov     [rsp+0C8h+var_94], 0
0x18003a7cd  mov     edx, 1000h
0x18003a7d2  mov     [rax+18h], edx
0x18003a7d5  xorps   xmm0, xmm0
0x18003a7d8  movdqu  xmmword ptr [rsp+0C8h+AdapterAddresses], xmm0
0x18003a7de  mov     qword ptr [rax-80h], 0
0x18003a7e6  lea     rcx, [rsp+0C8h+AdapterAddresses]
0x18003a7eb  call    ??$_Construct_n@$$V@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Construct_n<>(unsigned __int64)
0x18003a7f0  nop
0x18003a7f1  mov     rbx, [rsp+0C8h+AdapterAddresses]
0x18003a7f6  mov     [rsp+0C8h+arg_18], 0
0x18003a801  lea     rax, [rsp+0C8h+arg_18]
0x18003a809  mov     [rsp+0C8h+var_A0], rax; unsigned int *
0x18003a80e  lea     rax, [rsp+0C8h+arg_10]
0x18003a816  mov     [rsp+0C8h+SizePointer], rax; unsigned int *
0x18003a81b  lea     r9, [rsp+0C8h+var_98]; enum NA_RULE_STATE *
0x18003a820  lea     r8, [rsp+0C8h+var_94]; unsigned int *
0x18003a825  lea     rdx, [rsp+0C8h+arg_8]; bool *
0x18003a82d  lea     rcx, [rsp+0C8h+var_40]; this
0x18003a835  call    ??0_lambda_e0961d09be37bcacb226eb1c325cdc72_@@QEAA@AEA_NAEAKAEAW4NA_RULE_STATE@@11@Z; _lambda_e0961d09be37bcacb226eb1c325cdc72_::_lambda_e0961d09be37bcacb226eb1c325cdc72_(bool &,ulong &,NA_RULE_STATE &,ulong &,ulong &)
0x18003a83a  mov     rdx, rax
0x18003a83d  lea     rcx, [rsp+0C8h+var_70]
0x18003a842  call    ??$ScopeExit@V_lambda_e0961d09be37bcacb226eb1c325cdc72_@@@wil@@YA?AV?$ScopeExitFn@V_lambda_e0961d09be37bcacb226eb1c325cdc72_@@@details@0@$$QEAV_lambda_e0961d09be37bcacb226eb1c325cdc72_@@@Z; wil::ScopeExit<_lambda_e0961d09be37bcacb226eb1c325cdc72_>(_lambda_e0961d09be37bcacb226eb1c325cdc72_ &&)
0x18003a847  nop
0x18003a848  lea     r15, WPP_GLOBAL_Control
0x18003a84f  lea     rax, [rsp+0C8h+arg_10]
0x18003a857  mov     [rsp+0C8h+SizePointer], rax; SizePointer
0x18003a85c  mov     r9, rbx; AdapterAddresses
0x18003a85f  xor     r8d, r8d; Reserved
0x18003a862  mov     edx, 186h; Flags
0x18003a867  xor     ecx, ecx; Family
0x18003a869  call    cs:__imp_GetAdaptersAddresses
0x18003a86f  mov     [rsp+0C8h+var_94], eax
0x18003a873  cmp     eax, 6Fh ; 'o'
0x18003a876  jnz     loc_18003A922
0x18003a87c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a883  cmp     rcx, r15
0x18003a886  jz      short loc_18003A8A9
0x18003a888  test    byte ptr [rcx+1Ch], 4
0x18003a88c  jz      short loc_18003A8A9
0x18003a88e  lea     edx, [rax-63h]
0x18003a891  mov     r9d, [rsp+0C8h+arg_10]
0x18003a899  lea     r8, WPP_d1cee8b2867932f5b010f98517c4d23a_Traceguids
0x18003a8a0  mov     rcx, [rcx+10h]
0x18003a8a4  call    WPP_SF_d
0x18003a8a9  mov     ebx, [rsp+0C8h+arg_10]
0x18003a8b0  mov     rdx, [rsp+0C8h+AdapterAddresses]
0x18003a8b5  mov     rdi, [rsp+0C8h+AdapterAddresses+8]
0x18003a8ba  mov     rcx, rdi
0x18003a8bd  sub     rcx, rdx
0x18003a8c0  cmp     rbx, rcx
0x18003a8c3  jnb     short loc_18003A8CB
0x18003a8c5  lea     rax, [rbx+rdx]
0x18003a8c9  jmp     short loc_18003A8FD
0x18003a8cb  jbe     short loc_18003A902
0x18003a8cd  mov     rax, [rsp+0C8h+var_80]
0x18003a8d2  sub     rax, rdx
0x18003a8d5  cmp     rbx, rax
0x18003a8d8  jbe     short loc_18003A8E9
0x18003a8da  mov     rdx, rbx
0x18003a8dd  lea     rcx, [rsp+0C8h+AdapterAddresses]
0x18003a8e2  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18003a8e7  jmp     short loc_18003A902
0x18003a8e9  sub     rbx, rcx
0x18003a8ec  mov     r8, rbx; Size
0x18003a8ef  xor     edx, edx; Val
0x18003a8f1  mov     rcx, rdi; void *
0x18003a8f4  call    memset_0
0x18003a8f9  lea     rax, [rbx+rdi]
0x18003a8fd  mov     [rsp+0C8h+AdapterAddresses+8], rax
0x18003a902  mov     rbx, [rsp+0C8h+AdapterAddresses]
0x18003a907  mov     eax, [rsp+0C8h+arg_18]
0x18003a90e  inc     eax
0x18003a910  mov     [rsp+0C8h+arg_18], eax
0x18003a917  cmp     eax, 0Ah
0x18003a91a  jb      loc_18003A84F
0x18003a920  jmp     short loc_18003A961
0x18003a922  test    eax, eax
0x18003a924  jz      short loc_18003A952
0x18003a926  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a92d  cmp     rcx, r15
0x18003a930  jz      short loc_18003A961
0x18003a932  test    byte ptr [rcx+1Ch], 4
0x18003a936  jz      short loc_18003A961
0x18003a938  mov     edx, 0Dh
0x18003a93d  mov     r9d, eax
0x18003a940  lea     r8, WPP_d1cee8b2867932f5b010f98517c4d23a_Traceguids
0x18003a947  mov     rcx, [rcx+10h]
0x18003a94b  call    WPP_SF_d
0x18003a950  jmp     short loc_18003A961
0x18003a952  mov     rdx, rbx
0x18003a955  mov     rcx, rsi
0x18003a958  call    ?MatchProperties@IpConfigSignal@@AEAA?AW4NA_RULE_STATE@@PEBU_IP_ADAPTER_ADDRESSES_LH@@@Z; IpConfigSignal::MatchProperties(_IP_ADAPTER_ADDRESSES_LH const *)
0x18003a95d  mov     [rsp+0C8h+var_98], eax
0x18003a961  mov     edx, [rsp+0C8h+var_98]
0x18003a965  mov     rcx, rsi
0x18003a968  call    ?SetState@DefaultSignal@GenericPlugin@@QEAAXW4NA_RULE_STATE@@@Z; GenericPlugin::DefaultSignal::SetState(NA_RULE_STATE)
0x18003a96d  mov     [rsp+0C8h+arg_8], 0
0x18003a975  jmp     short loc_18003A979
0x18003a977  jmp     short $+2
0x18003a979  lea     rcx, [rsp+0C8h+var_70]
0x18003a97e  call    ??1?$ScopeExitFn@V_lambda_e0961d09be37bcacb226eb1c325cdc72_@@@details@wil@@QEAA@XZ; wil::details::ScopeExitFn<_lambda_e0961d09be37bcacb226eb1c325cdc72_>::~ScopeExitFn<_lambda_e0961d09be37bcacb226eb1c325cdc72_>(void)
0x18003a983  nop
0x18003a984  lea     rcx, [rsp+0C8h+AdapterAddresses]
0x18003a989  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18003a98e  mov     rbx, [rsp+0C8h+arg_0]
0x18003a996  add     rsp, 0B0h
0x18003a99d  pop     r15
0x18003a99f  pop     rdi
0x18003a9a0  pop     rsi
0x18003a9a1  retn
```
