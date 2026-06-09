# RemoteAppIntegrationServer::RemoveTih(uint)

- ea: `0x18002b938`
- end: `0x18002bc06`
- name: `?RemoveTih@RemoteAppIntegrationServer@@QEAAJI@Z`
- size: `718`
- prototype: `__int64 __fastcall(RemoteAppIntegrationServer *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180025910`

## callees

- `0x180006a14`
- `0x18000c454`
- `0x180010540`
- `0x18002b938`
- `0x18002ca04`
- `0x180034ff8`
- `0x180058010`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18002bbc3`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18002bbc3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bb20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bbb2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bbd4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bb20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bbb2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bbd4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002b970`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002b970`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall RemoteAppIntegrationServer::RemoveTih(RTL_SRWLOCK *this, unsigned int a2)
{
  RTL_SRWLOCK *v4; // r14
  char *Ptr; // rdi
  char *v6; // rcx
  char v7; // dl
  char **v8; // rax
  RemoteAppIntegrationHost *v9; // rsi
  __int128 v10; // xmm6
  __int128 v11; // xmm7
  __int64 v12; // xmm8_8
  unsigned int v13; // r8d
  int v14; // eax
  wil::details *v15; // rcx
  unsigned int v16; // edi
  unsigned int v18; // r8d
  int v19; // [rsp+20h] [rbp-148h]
  int v20; // [rsp+40h] [rbp-128h] BYREF
  __int16 v21; // [rsp+44h] [rbp-124h]
  __int64 v22; // [rsp+48h] [rbp-120h] BYREF
  unsigned int v23; // [rsp+50h] [rbp-118h] BYREF
  PSRWLOCK SRWLock[3]; // [rsp+58h] [rbp-110h] BYREF
  _OWORD v25[2]; // [rsp+70h] [rbp-F8h] BYREF
  __int64 v26; // [rsp+90h] [rbp-D8h]
  RemoteAppIntegrationHost *v27; // [rsp+A0h] [rbp-C8h]
  __int128 v28; // [rsp+A8h] [rbp-C0h]
  __int128 v29; // [rsp+B8h] [rbp-B0h]
  __int64 v30; // [rsp+C8h] [rbp-A0h]
  __int128 v31; // [rsp+D0h] [rbp-98h]
  __int128 v32; // [rsp+E0h] [rbp-88h]
  __int64 v33; // [rsp+F0h] [rbp-78h]
  __int128 v34; // [rsp+F8h] [rbp-70h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v23 = a2;
  v4 = this + 13;
  SRWLock[0] = this + 13;
  AcquireSRWLockExclusive(this + 13);
  SRWLock[1] = v4;
  Ptr = (char *)this[10].Ptr;
  v6 = (char *)*((_QWORD *)Ptr + 1);
  HIDWORD(v25[0]) = 0;
  while ( !v6[25] )
  {
    if ( *((_DWORD *)v6 + 8) >= a2 )
    {
      v7 = 0;
      Ptr = v6;
    }
    else
    {
      v7 = 1;
    }
    v8 = (char **)(v6 + 16);
    if ( !v7 )
      v8 = (char **)v6;
    v6 = *v8;
  }
  if ( Ptr[25] || a2 < *((_DWORD *)Ptr + 8) )
  {
    std::_Xout_of_range("invalid map<K, T> key");
    if ( SRWLock[0] )
      ReleaseSRWLockExclusive(SRWLock[0]);
    return 2147942487LL;
  }
  else
  {
    v9 = (RemoteAppIntegrationHost *)*((_QWORD *)Ptr + 5);
    v27 = v9;
    if ( v9 )
      (*(void (__fastcall **)(RemoteAppIntegrationHost *))(*(_QWORD *)v9 + 8LL))(v9);
    v28 = *((_OWORD *)Ptr + 3);
    v29 = *((_OWORD *)Ptr + 4);
    v30 = *((_QWORD *)Ptr + 10);
    v10 = *(_OWORD *)(Ptr + 88);
    v31 = v10;
    v11 = *(_OWORD *)(Ptr + 104);
    v32 = v11;
    v12 = *((_QWORD *)Ptr + 15);
    v33 = v12;
    v34 = *((_OWORD *)Ptr + 8);
    v13 = *(_DWORD *)Feature_TextVirtPostNiBugFix__descriptor;
    if ( (*(_DWORD *)Feature_TextVirtPostNiBugFix__descriptor & 4) == 0 )
    {
      v22 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_TextVirtPostNiBugFix>::GetCachedFeatureEnabledState(
               (wil::details *)v6,
               &v22);
      v13 = v22;
    }
    v20 = 0;
    v21 = 3;
    wil::details::ReportUsageToService(
      (__int64)&unk_1800827F8,
      0x28F2738u,
      (v13 >> 10) & 1,
      (v13 >> 11) & 1,
      (__int64)&v20,
      1u,
      3);
    RemoteAppIntegrationHost::Dispose(v9);
    if ( v9 )
      (*(void (__fastcall **)(RemoteAppIntegrationHost *))(*(_QWORD *)v9 + 16LL))(v9);
    v25[0] = v10;
    v25[1] = v11;
    v26 = v12;
    v14 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *, _OWORD *))this->Ptr + 5))(this, v25);
    v16 = v14;
    if ( v14 >= 0 )
    {
      v18 = *(_DWORD *)Feature_TextVirtPostNiBugFix__descriptor;
      if ( (*(_DWORD *)Feature_TextVirtPostNiBugFix__descriptor & 4) == 0 )
      {
        v22 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_TextVirtPostNiBugFix>::GetCachedFeatureEnabledState(
                 v15,
                 SRWLock);
        v18 = v22;
      }
      v20 = 0;
      v21 = 3;
      wil::details::ReportUsageToService(
        (__int64)&unk_1800827F8,
        0x28F2738u,
        (v18 >> 10) & 1,
        (v18 >> 11) & 1,
        (__int64)&v20,
        1u,
        3);
      std::_Tree<std::_Tmap_traits<unsigned int,std::tuple<MessageObjectID,tagMsgRoutingInfo,tagMsgRoutingInfo,Microsoft::WRL::ComPtr<RemoteAppIntegrationHost>>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::tuple<MessageObjectID,tagMsgRoutingInfo,tagMsgRoutingInfo,Microsoft::WRL::ComPtr<RemoteAppIntegrationHost>>>>,0>>::erase(
        &this[10],
        &v23);
      if ( v4 )
        ReleaseSRWLockExclusive(v4);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x95,
        (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remoteappintegrationserver.cpp",
        (const char *)(unsigned int)v14,
        v19);
      if ( v4 )
        ReleaseSRWLockExclusive(v4);
      return v16;
    }
  }
}

```

## disassembly

```asm
0x18002b938  mov     rax, rsp
0x18002b93b  mov     [rax+18h], rbx
0x18002b93f  push    rsi
0x18002b940  push    rdi
0x18002b941  push    r12
0x18002b943  push    r14
0x18002b945  push    r15
0x18002b947  sub     rsp, 140h
0x18002b94e  movaps  xmmword ptr [rax-38h], xmm6
0x18002b952  movaps  xmmword ptr [rax-48h], xmm7
0x18002b956  movaps  xmmword ptr [rax-58h], xmm8
0x18002b95b  mov     esi, edx
0x18002b95d  mov     r15, rcx
0x18002b960  mov     [rsp+168h+var_118], edx
0x18002b964  lea     r14, [rcx+68h]
0x18002b968  mov     [rsp+168h+SRWLock], r14
0x18002b96d  mov     rcx, r14; SRWLock
0x18002b970  call    cs:__imp_AcquireSRWLockExclusive
0x18002b976  mov     [rsp+168h+var_108], r14
0x18002b97b  mov     rdi, [r15+50h]
0x18002b97f  mov     rcx, [rdi+8]
0x18002b983  xor     eax, eax
0x18002b985  mov     dword ptr [rsp+168h+var_F8+0Ch], eax
0x18002b989  xor     ebx, ebx
0x18002b98b  jmp     short loc_18002B9A8
0x18002b98d  cmp     [rcx+20h], esi
0x18002b990  jnb     short loc_18002B996
0x18002b992  mov     dl, 1
0x18002b994  jmp     short loc_18002B99B
0x18002b996  mov     dl, bl
0x18002b998  mov     rdi, rcx
0x18002b99b  lea     rax, [rcx+10h]
0x18002b99f  test    dl, dl
0x18002b9a1  cmovz   rax, rcx
0x18002b9a5  mov     rcx, [rax]
0x18002b9a8  cmp     [rcx+19h], bl
0x18002b9ab  jz      short loc_18002B98D
0x18002b9ad  cmp     [rdi+19h], bl
0x18002b9b0  jnz     loc_18002BBBC
0x18002b9b6  cmp     esi, [rdi+20h]
0x18002b9b9  jb      loc_18002BBBC
0x18002b9bf  mov     rsi, [rdi+28h]
0x18002b9c3  mov     [rsp+168h+var_C8], rsi
0x18002b9cb  test    rsi, rsi
0x18002b9ce  jz      short loc_18002B9E0
0x18002b9d0  mov     rax, [rsi]
0x18002b9d3  mov     rcx, rsi
0x18002b9d6  mov     rax, [rax+8]
0x18002b9da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9df  nop
0x18002b9e0  movups  xmm0, xmmword ptr [rdi+30h]
0x18002b9e4  movups  [rsp+168h+var_C0], xmm0
0x18002b9ec  movups  xmm1, xmmword ptr [rdi+40h]
0x18002b9f0  movups  [rsp+168h+var_B0], xmm1
0x18002b9f8  movsd   xmm0, qword ptr [rdi+50h]
0x18002b9fd  movsd   [rsp+168h+var_A0], xmm0
0x18002ba06  movups  xmm6, xmmword ptr [rdi+58h]
0x18002ba0a  movaps  [rsp+168h+var_98], xmm6
0x18002ba12  movups  xmm7, xmmword ptr [rdi+68h]
0x18002ba16  movaps  [rsp+168h+var_88], xmm7
0x18002ba1e  movsd   xmm8, qword ptr [rdi+78h]
0x18002ba24  movsd   [rsp+168h+var_78], xmm8
0x18002ba2e  movups  xmm0, xmmword ptr [rdi+80h]
0x18002ba35  movdqu  [rsp+168h+var_70], xmm0
0x18002ba3e  mov     rax, cs:Feature_TextVirtPostNiBugFix__descriptor
0x18002ba45  mov     r8d, [rax]
0x18002ba48  test    r8b, 4
0x18002ba4c  jnz     short loc_18002BA63
0x18002ba4e  lea     rdx, [rsp+168h+var_120]
0x18002ba53  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TextVirtPostNiBugFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TextVirtPostNiBugFix>::GetCachedFeatureEnabledState(void)
0x18002ba58  mov     rax, [rax]
0x18002ba5b  mov     [rsp+168h+var_120], rax
0x18002ba60  mov     r8d, eax
0x18002ba63  mov     [rsp+168h+var_128], ebx
0x18002ba67  mov     [rsp+168h+var_124], 3
0x18002ba6e  mov     r9d, r8d
0x18002ba71  shr     r9d, 0Bh
0x18002ba75  and     r9d, 1
0x18002ba79  shr     r8d, 0Ah
0x18002ba7d  and     r8d, 1
0x18002ba81  mov     [rsp+168h+var_138], 3
0x18002ba89  mov     [rsp+168h+var_140], 1
0x18002ba91  lea     rax, [rsp+168h+var_128]
0x18002ba96  mov     qword ptr [rsp+168h+var_148], rax; int
0x18002ba9b  mov     edx, 28F2738h
0x18002baa0  lea     rcx, unk_1800827F8
0x18002baa7  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18002baac  mov     rcx, rsi; this
0x18002baaf  call    ?Dispose@RemoteAppIntegrationHost@@QEAAJXZ; RemoteAppIntegrationHost::Dispose(void)
0x18002bab4  nop
0x18002bab5  test    rsi, rsi
0x18002bab8  jz      short loc_18002BACA
0x18002baba  mov     rax, [rsi]
0x18002babd  mov     rcx, rsi
0x18002bac0  mov     rax, [rax+10h]
0x18002bac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bac9  nop
0x18002baca  movaps  [rsp+168h+var_F8], xmm6
0x18002bacf  movaps  [rsp+168h+var_E8], xmm7
0x18002bad7  movsd   [rsp+168h+var_D8], xmm8
0x18002bae1  mov     rax, [r15]
0x18002bae4  lea     rdx, [rsp+168h+var_F8]
0x18002bae9  mov     rcx, r15
0x18002baec  mov     rax, [rax+28h]
0x18002baf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002baf5  mov     edi, eax
0x18002baf7  test    eax, eax
0x18002baf9  jns     short loc_18002BB2D
0x18002bafb  mov     rcx, [rsp+168h]; this
0x18002bb03  mov     r9d, eax; char *
0x18002bb06  lea     r8, aMincoreTextinp_0; "mincore\\textinput\\dev\\virtualization"...
0x18002bb0d  mov     edx, 95h; void *
0x18002bb12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bb17  nop
0x18002bb18  test    r14, r14
0x18002bb1b  jz      short loc_18002BB26
0x18002bb1d  mov     rcx, r14; SRWLock
0x18002bb20  call    cs:__imp_ReleaseSRWLockExclusive
0x18002bb26  mov     eax, edi
0x18002bb28  jmp     loc_18002BBDF
0x18002bb2d  mov     rax, cs:Feature_TextVirtPostNiBugFix__descriptor
0x18002bb34  mov     r8d, [rax]
0x18002bb37  test    r8b, 4
0x18002bb3b  jnz     short loc_18002BB52
0x18002bb3d  lea     rdx, [rsp+168h+SRWLock]
0x18002bb42  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TextVirtPostNiBugFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TextVirtPostNiBugFix>::GetCachedFeatureEnabledState(void)
0x18002bb47  mov     rcx, [rax]
0x18002bb4a  mov     [rsp+168h+var_120], rcx
0x18002bb4f  mov     r8d, ecx
0x18002bb52  mov     [rsp+168h+var_128], ebx
0x18002bb56  mov     [rsp+168h+var_124], 3
0x18002bb5d  mov     r9d, r8d
0x18002bb60  shr     r9d, 0Bh
0x18002bb64  and     r9d, 1
0x18002bb68  shr     r8d, 0Ah
0x18002bb6c  and     r8d, 1
0x18002bb70  mov     [rsp+168h+var_138], 3
0x18002bb78  mov     [rsp+168h+var_140], 1
0x18002bb80  lea     rax, [rsp+168h+var_128]
0x18002bb85  mov     qword ptr [rsp+168h+var_148], rax
0x18002bb8a  mov     edx, 28F2738h
0x18002bb8f  lea     rcx, unk_1800827F8
0x18002bb96  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18002bb9b  lea     rdx, [rsp+168h+var_118]
0x18002bba0  lea     rcx, [r15+50h]
0x18002bba4  call    ?erase@?$_Tree@V?$_Tmap_traits@IV?$tuple@UMessageObjectID@@UtagMsgRoutingInfo@@U2@V?$ComPtr@VRemoteAppIntegrationHost@@@WRL@Microsoft@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$tuple@UMessageObjectID@@UtagMsgRoutingInfo@@U2@V?$ComPtr@VRemoteAppIntegrationHost@@@WRL@Microsoft@@@std@@@std@@@2@$0A@@std@@@std@@QEAA_KAEBI@Z; std::_Tree<std::_Tmap_traits<uint,std::tuple<MessageObjectID,tagMsgRoutingInfo,tagMsgRoutingInfo,Microsoft::WRL::ComPtr<RemoteAppIntegrationHost>>,std::less<uint>,std::allocator<std::pair<uint const,std::tuple<MessageObjectID,tagMsgRoutingInfo,tagMsgRoutingInfo,Microsoft::WRL::ComPtr<RemoteAppIntegrationHost>>>>,0>>::erase(uint const &)
0x18002bba9  nop
0x18002bbaa  test    r14, r14
0x18002bbad  jz      short loc_18002BBB8
0x18002bbaf  mov     rcx, r14; SRWLock
0x18002bbb2  call    cs:__imp_ReleaseSRWLockExclusive
0x18002bbb8  xor     eax, eax
0x18002bbba  jmp     short loc_18002BBDF
0x18002bbbc  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x18002bbc3  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18002bbc9  nop
0x18002bbca  mov     rcx, [rsp+168h+SRWLock]; SRWLock
0x18002bbcf  test    rcx, rcx
0x18002bbd2  jz      short loc_18002BBDA
0x18002bbd4  call    cs:__imp_ReleaseSRWLockExclusive
0x18002bbda  mov     eax, 80070057h
0x18002bbdf  lea     r11, [rsp+168h+var_28]
0x18002bbe7  mov     rbx, [r11+40h]
0x18002bbeb  movaps  xmm6, xmmword ptr [r11-10h]
0x18002bbf0  movaps  xmm7, xmmword ptr [r11-20h]
0x18002bbf5  movaps  xmm8, xmmword ptr [r11-30h]
0x18002bbfa  mov     rsp, r11
0x18002bbfd  pop     r15
0x18002bbff  pop     r14
0x18002bc01  pop     r12
0x18002bc03  pop     rdi
0x18002bc04  pop     rsi
0x18002bc05  retn
```
