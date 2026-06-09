# RemoteAppIntegrationClient::SetCompositionInfo(tagMsgRoutingInfo,uint,uint,int,int,MsgString *)

- ea: `0x180033e30`
- end: `0x180033fc9`
- name: `?SetCompositionInfo@RemoteAppIntegrationClient@@UEAAJUtagMsgRoutingInfo@@IIHHPEAUMsgString@@@Z`
- size: `409`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180006a14`
- `0x180033e30`
- `0x180034ba8`
- `0x180034d6c`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180033ed4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180033ed4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RemoteAppIntegrationClient::SetCompositionInfo(
        __int64 a1,
        __int64 a2,
        int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        const WCHAR *a7)
{
  const WCHAR *v11; // rcx
  UINT32 v12; // edx
  unsigned int v13; // eax
  HRESULT v14; // eax
  unsigned int v15; // ebx
  char IsEnabled; // al
  __int64 v17; // r9
  __int64 v18; // rbx
  unsigned int v19; // edi
  int v20; // [rsp+20h] [rbp-68h]
  __int64 v21; // [rsp+40h] [rbp-48h] BYREF
  HSTRING string; // [rsp+48h] [rbp-40h] BYREF
  unsigned __int64 v23; // [rsp+50h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v21 = 0;
  if ( !(unsigned __int8)RemoteAppIntegrationClient::TryAcquireOwner(a1, &v21) )
  {
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    return 0;
  }
  v23 = __PAIR64__(a6, a5);
  string = 0;
  v11 = a7;
  if ( a7 )
  {
    v12 = *(_DWORD *)a7 & 0x1FFFFFFF;
    v13 = *(_DWORD *)a7 & 0xE0000000;
    if ( v13 == 0x40000000 )
    {
      v11 = a7 + 4;
    }
    else
    {
      if ( v13 != 0x80000000 )
        __debugbreak();
      v11 = (const WCHAR *)*((_QWORD *)a7 + 1);
    }
  }
  else
  {
    v12 = 0;
  }
  v14 = WindowsCreateString(v11, v12, &string);
  v15 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34C,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remoteappintegrationclient.cpp",
      (const char *)(unsigned int)v14,
      v20);
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    return v15;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608>::GetImpl'::`2'::impl);
  v17 = *(unsigned int *)(a1 + 60);
  if ( !IsEnabled )
  {
    v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, int, unsigned __int64, HSTRING))(**(_QWORD **)(a1 + 40) + 96LL))(
            *(_QWORD *)(a1 + 40),
            *(unsigned int *)(a1 + 56),
            a4,
            v17,
            a3,
            v23,
            string);
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    return v15;
  }
  v18 = v21;
  v19 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, int, unsigned __int64, HSTRING))(*(_QWORD *)v21 + 96LL))(
          v21,
          *(unsigned int *)(a1 + 56),
          a4,
          v17,
          a3,
          v23,
          string);
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  return v19;
}

```

## disassembly

```asm
0x180033e30  push    rbx
0x180033e32  push    rbp
0x180033e33  push    rsi
0x180033e34  push    rdi
0x180033e35  sub     rsp, 68h
0x180033e39  mov     esi, r9d
0x180033e3c  mov     ebp, r8d
0x180033e3f  mov     rdi, rcx
0x180033e42  mov     [rsp+88h+var_48], 0
0x180033e4b  lea     rdx, [rsp+88h+var_48]
0x180033e50  call    ?TryAcquireOwner@RemoteAppIntegrationClient@@AEAA_NAEAV?$ComPtr@UIRemoteAppIntegrationOwner@@@WRL@Microsoft@@@Z; RemoteAppIntegrationClient::TryAcquireOwner(Microsoft::WRL::ComPtr<IRemoteAppIntegrationOwner> &)
0x180033e55  test    al, al
0x180033e57  jnz     short loc_180033E77
0x180033e59  mov     rcx, [rsp+88h+var_48]
0x180033e5e  test    rcx, rcx
0x180033e61  jz      short loc_180033E70
0x180033e63  mov     rax, [rcx]
0x180033e66  mov     rax, [rax+10h]
0x180033e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e6f  nop
0x180033e70  xor     eax, eax
0x180033e72  jmp     loc_180033FC0
0x180033e77  mov     eax, [rsp+88h+arg_20]
0x180033e7e  mov     dword ptr [rsp+88h+var_38], eax
0x180033e82  mov     eax, [rsp+88h+arg_28]
0x180033e89  mov     dword ptr [rsp+88h+var_38+4], eax
0x180033e8d  mov     [rsp+88h+string], 0
0x180033e96  mov     rcx, [rsp+88h+arg_30]
0x180033e9e  test    rcx, rcx
0x180033ea1  jnz     short loc_180033EA7
0x180033ea3  xor     edx, edx
0x180033ea5  jmp     short loc_180033ECF
0x180033ea7  mov     eax, [rcx]
0x180033ea9  mov     edx, eax
0x180033eab  and     edx, 1FFFFFFFh; length
0x180033eb1  and     eax, 0E0000000h
0x180033eb6  cmp     eax, 40000000h
0x180033ebb  jz      short loc_180033ECB
0x180033ebd  cmp     eax, 80000000h
0x180033ec2  jz      short loc_180033EC5
0x180033ec4  int     3; Trap to Debugger
0x180033ec5  mov     rcx, [rcx+8]
0x180033ec9  jmp     short loc_180033ECF
0x180033ecb  add     rcx, 8; sourceString
0x180033ecf  lea     r8, [rsp+88h+string]; string
0x180033ed4  call    cs:__imp_WindowsCreateString
0x180033eda  mov     ebx, eax
0x180033edc  test    eax, eax
0x180033ede  jns     short loc_180033F19
0x180033ee0  mov     rcx, [rsp+88h]; this
0x180033ee8  mov     r9d, eax; char *
0x180033eeb  lea     r8, aMincoreTextinp_19; "mincore\\textinput\\dev\\virtualization"...
0x180033ef2  mov     edx, 34Ch; void *
0x180033ef7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033efc  nop
0x180033efd  mov     rcx, [rsp+88h+var_48]
0x180033f02  test    rcx, rcx
0x180033f05  jz      short loc_180033F14
0x180033f07  mov     rax, [rcx]
0x180033f0a  mov     rax, [rax+10h]
0x180033f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f13  nop
0x180033f14  jmp     loc_180033FBE
0x180033f19  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608> `wil::Feature<__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608>::GetImpl(void)'::`2'::impl
0x180033f20  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608>::__private_IsEnabled(void)
0x180033f25  mov     r9d, [rdi+3Ch]
0x180033f29  mov     r8d, esi
0x180033f2c  test    al, al
0x180033f2e  jz      short loc_180033F7A
0x180033f30  mov     rbx, [rsp+88h+var_48]
0x180033f35  mov     rcx, [rsp+88h+string]
0x180033f3a  mov     rax, [rbx]
0x180033f3d  mov     [rsp+88h+var_58], rcx
0x180033f42  mov     rcx, [rsp+88h+var_38]
0x180033f47  mov     [rsp+88h+var_60], rcx
0x180033f4c  mov     [rsp+88h+var_68], ebp
0x180033f50  mov     edx, [rdi+38h]
0x180033f53  mov     rcx, rbx
0x180033f56  mov     rax, [rax+60h]
0x180033f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f5f  mov     edi, eax
0x180033f61  test    rbx, rbx
0x180033f64  jz      short loc_180033F76
0x180033f66  mov     rdx, [rbx]
0x180033f69  mov     rcx, rbx
0x180033f6c  mov     rax, [rdx+10h]
0x180033f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f75  nop
0x180033f76  mov     eax, edi
0x180033f78  jmp     short loc_180033FC0
0x180033f7a  mov     rcx, [rdi+28h]
0x180033f7e  mov     rdx, [rsp+88h+string]
0x180033f83  mov     rax, [rcx]
0x180033f86  mov     [rsp+88h+var_58], rdx
0x180033f8b  mov     rdx, [rsp+88h+var_38]
0x180033f90  mov     [rsp+88h+var_60], rdx
0x180033f95  mov     [rsp+88h+var_68], ebp
0x180033f99  mov     edx, [rdi+38h]
0x180033f9c  mov     rax, [rax+60h]
0x180033fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033fa5  mov     ebx, eax
0x180033fa7  mov     rcx, [rsp+88h+var_48]
0x180033fac  test    rcx, rcx
0x180033faf  jz      short loc_180033FBE
0x180033fb1  mov     rdx, [rcx]
0x180033fb4  mov     rax, [rdx+10h]
0x180033fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033fbd  nop
0x180033fbe  mov     eax, ebx
0x180033fc0  add     rsp, 68h
0x180033fc4  pop     rdi
0x180033fc5  pop     rsi
0x180033fc6  pop     rbp
0x180033fc7  pop     rbx
0x180033fc8  retn
```
