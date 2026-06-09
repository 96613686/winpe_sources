# QueuePolicyEngine::RunPolicyEvaluation(EvaluationTrigger,std::vector<Microsoft::WRL::ComPtr<IUserAccount>,std::allocator<Microsoft::WRL::ComPtr<IUserAccount>>> &,_GUID const &)

- ea: `0x180020070`
- end: `0x18002023e`
- name: `?RunPolicyEvaluation@QueuePolicyEngine@@UEAAJW4EvaluationTrigger@@AEAV?$vector@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@std@@@std@@AEBU_GUID@@@Z`
- size: `462`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003530`
- `0x180005120`
- `0x18000f454`
- `0x1800113d8`
- `0x180012294`
- `0x180017244`
- `0x18001d110`
- `0x18001d900`
- `0x18001e9c0`
- `0x18001eb50`
- `0x18001f37c`
- `0x18001fcc8`
- `0x18001fcf4`
- `0x180020070`
- `0x1800202f0`
- `0x1800205f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002014a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002014a`

## pseudocode

```c
__int64 __fastcall QueuePolicyEngine::RunPolicyEvaluation(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  _QWORD *SortedCandidateAccounts; // rax
  unsigned int v9; // esi
  unsigned __int64 v10; // r8
  __int64 v11; // rbx
  char v12; // al
  unsigned int v13; // ecx
  DWORD pcbData[2]; // [rsp+40h] [rbp-1B8h] BYREF
  int pvData; // [rsp+48h] [rbp-1B0h] BYREF
  __int64 v17; // [rsp+50h] [rbp-1A8h] BYREF
  __int64 v18; // [rsp+58h] [rbp-1A0h]
  _QWORD v19[3]; // [rsp+68h] [rbp-190h] BYREF
  _QWORD v20[42]; // [rsp+80h] [rbp-178h] BYREF

  wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v20,
    "QueuePolicyEvaluation");
  v20[0] = &PolicyTelemetry::QueuePolicyEvaluation::`vftable';
  wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
    v20,
    a4);
  PolicyTelemetry::QueuePolicyEvaluation::StartActivity((PolicyTelemetry::QueuePolicyEvaluation *)v20);
  BasePolicyEngine::DeleteTemporaryLocalAccounts(a1, a3, a2, v20[34] + 8LL);
  if ( !*(_BYTE *)(a1 + 72) )
  {
    *(_BYTE *)(a1 + 72) = 1;
    pvData = 0;
    pcbData[0] = 4;
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\SharedPC",
            L"Queuesize",
            0x18u,
            0,
            &pvData,
            pcbData) )
      *(_DWORD *)(a1 + 76) = pvData;
  }
  std::vector<SessionUserInfo>::vector<SessionUserInfo>(&v17);
  SortedCandidateAccounts = GetSortedCandidateAccounts(v19);
  std::vector<Microsoft::WRL::ComPtr<IUserAccount>>::operator=(&v17, SortedCandidateAccounts);
  std::vector<Microsoft::WRL::ComPtr<IUserAccount>>::_Tidy(v19);
  v9 = 0;
  while ( 1 )
  {
    v10 = *(unsigned int *)(a1 + 76);
    if ( (v18 - v17) >> 3 <= v10 )
      break;
    *(_QWORD *)pcbData = *(_QWORD *)(v18 - 8);
    v11 = *(_QWORD *)pcbData;
    Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>::InternalAddRef(pcbData);
    v12 = BasePolicyEngine::DeleteUserAccount((_QWORD **)a1, v11, a2);
    v13 = v9 + 1;
    if ( !v12 )
      v13 = v9;
    v9 = v13;
    std::vector<Microsoft::WRL::ComPtr<IUserAccount>>::pop_back(&v17);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(pcbData);
  }
  PolicyTelemetry::QueuePolicyEvaluation::Stop((PolicyTelemetry::QueuePolicyEvaluation *)v20, v9, v10);
  std::vector<Microsoft::WRL::ComPtr<IUserAccount>>::_Tidy(&v17);
  PolicyTelemetry::QueuePolicyEvaluation::~QueuePolicyEvaluation((PolicyTelemetry::QueuePolicyEvaluation *)v20);
  return 0;
}

```

## disassembly

```asm
0x180020070  mov     [rsp+arg_8], rbx
0x180020075  push    rsi
0x180020076  push    rdi
0x180020077  push    r14
0x180020079  sub     rsp, 1E0h
0x180020080  mov     rax, cs:__security_cookie
0x180020087  xor     rax, rsp
0x18002008a  mov     [rsp+1F8h+var_28], rax
0x180020092  mov     rsi, r9
0x180020095  mov     rbx, r8
0x180020098  mov     r14d, edx
0x18002009b  mov     rdi, rcx
0x18002009e  lea     rdx, aQueuepolicyeva; "QueuePolicyEvaluation"
0x1800200a5  lea     rcx, [rsp+1F8h+var_178]
0x1800200ad  call    ??0?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800200b2  lea     rax, ??_7QueuePolicyEvaluation@PolicyTelemetry@@6B@; const PolicyTelemetry::QueuePolicyEvaluation::`vftable'
0x1800200b9  mov     [rsp+1F8h+var_178], rax
0x1800200c1  mov     rdx, rsi
0x1800200c4  lea     rcx, [rsp+1F8h+var_178]
0x1800200cc  call    ?SetRelatedActivityId@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x1800200d1  lea     rcx, [rsp+1F8h+var_178]; this
0x1800200d9  call    ?StartActivity@QueuePolicyEvaluation@PolicyTelemetry@@QEAAXXZ; PolicyTelemetry::QueuePolicyEvaluation::StartActivity(void)
0x1800200de  mov     r9, [rsp+1F8h+var_68]
0x1800200e6  add     r9, 8
0x1800200ea  mov     r8d, r14d
0x1800200ed  mov     rdx, rbx
0x1800200f0  mov     rcx, rdi
0x1800200f3  call    ?DeleteTemporaryLocalAccounts@BasePolicyEngine@@IEAAXAEBV?$vector@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@std@@@std@@W4EvaluationTrigger@@AEBU_GUID@@@Z; BasePolicyEngine::DeleteTemporaryLocalAccounts(std::vector<Microsoft::WRL::ComPtr<IUserAccount>> const &,EvaluationTrigger,_GUID const &)
0x1800200f8  cmp     byte ptr [rdi+48h], 0
0x1800200fc  jnz     short loc_18002015B
0x1800200fe  mov     byte ptr [rdi+48h], 1
0x180020102  mov     [rsp+1F8h+var_1B0], 0
0x18002010a  mov     [rsp+1F8h+var_1B8], 4
0x180020112  lea     rax, [rsp+1F8h+var_1B8]
0x180020117  mov     [rsp+1F8h+pcbData], rax; pcbData
0x18002011c  lea     rax, [rsp+1F8h+var_1B0]
0x180020121  mov     [rsp+1F8h+pvData], rax; pvData
0x180020126  mov     [rsp+1F8h+pdwType], 0; pdwType
0x18002012f  mov     r9d, 18h; dwFlags
0x180020135  lea     r8, aQueuesize; "Queuesize"
0x18002013c  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180020143  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002014a  call    cs:__imp_RegGetValueW
0x180020150  test    eax, eax
0x180020152  jnz     short loc_18002015B
0x180020154  mov     eax, [rsp+1F8h+var_1B0]
0x180020158  mov     [rdi+4Ch], eax
0x18002015b  lea     rcx, [rsp+1F8h+var_1A8]
0x180020160  call    ??0?$vector@USessionUserInfo@@V?$allocator@USessionUserInfo@@@std@@@std@@QEAA@XZ; std::vector<SessionUserInfo>::vector<SessionUserInfo>(void)
0x180020165  nop
0x180020166  mov     rdx, rbx
0x180020169  lea     rcx, [rsp+1F8h+var_190]
0x18002016e  call    ?GetSortedCandidateAccounts@@YA?AV?$vector@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@std@@@std@@AEAV12@@Z; GetSortedCandidateAccounts(std::vector<Microsoft::WRL::ComPtr<IUserAccount>> &)
0x180020173  mov     rdx, rax
0x180020176  lea     rcx, [rsp+1F8h+var_1A8]
0x18002017b  call    ??4?$vector@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<Microsoft::WRL::ComPtr<IUserAccount>>::operator=(std::vector<Microsoft::WRL::ComPtr<IUserAccount>> &&)
0x180020180  lea     rcx, [rsp+1F8h+var_190]
0x180020185  call    ?_Tidy@?$vector@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@std@@@std@@AEAAXXZ; std::vector<Microsoft::WRL::ComPtr<IUserAccount>>::_Tidy(void)
0x18002018a  xor     esi, esi
0x18002018c  mov     r8d, [rdi+4Ch]; unsigned int
0x180020190  mov     rbx, [rsp+1F8h+var_1A0]
0x180020195  mov     rax, rbx
0x180020198  sub     rax, [rsp+1F8h+var_1A8]
0x18002019d  sar     rax, 3
0x1800201a1  cmp     rax, r8
0x1800201a4  jbe     short loc_1800201E9
0x1800201a6  mov     rbx, [rbx-8]
0x1800201aa  mov     qword ptr [rsp+1F8h+var_1B8], rbx
0x1800201af  lea     rcx, [rsp+1F8h+var_1B8]
0x1800201b4  call    ?InternalAddRef@?$ComPtr@UIUserProfile@Internal@System@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>::InternalAddRef(void)
0x1800201b9  nop
0x1800201ba  mov     r8d, r14d
0x1800201bd  mov     rdx, rbx
0x1800201c0  mov     rcx, rdi
0x1800201c3  call    ?DeleteUserAccount@BasePolicyEngine@@IEAA_NPEAUIUserAccount@@W4EvaluationTrigger@@@Z; BasePolicyEngine::DeleteUserAccount(IUserAccount *,EvaluationTrigger)
0x1800201c8  lea     ecx, [rsi+1]
0x1800201cb  test    al, al
0x1800201cd  cmovz   ecx, esi
0x1800201d0  mov     esi, ecx
0x1800201d2  lea     rcx, [rsp+1F8h+var_1A8]
0x1800201d7  call    ?pop_back@?$vector@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@std@@@std@@QEAAXXZ; std::vector<Microsoft::WRL::ComPtr<IUserAccount>>::pop_back(void)
0x1800201dc  nop
0x1800201dd  lea     rcx, [rsp+1F8h+var_1B8]
0x1800201e2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800201e7  jmp     short loc_18002018C
0x1800201e9  mov     edx, esi; unsigned int
0x1800201eb  lea     rcx, [rsp+1F8h+var_178]; this
0x1800201f3  call    ?Stop@QueuePolicyEvaluation@PolicyTelemetry@@QEAAXII@Z; PolicyTelemetry::QueuePolicyEvaluation::Stop(uint,uint)
0x1800201f8  nop
0x1800201f9  lea     rcx, [rsp+1F8h+var_1A8]
0x1800201fe  call    ?_Tidy@?$vector@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@std@@@std@@AEAAXXZ; std::vector<Microsoft::WRL::ComPtr<IUserAccount>>::_Tidy(void)
0x180020203  nop
0x180020204  lea     rcx, [rsp+1F8h+var_178]; this
0x18002020c  call    ??1QueuePolicyEvaluation@PolicyTelemetry@@QEAA@XZ; PolicyTelemetry::QueuePolicyEvaluation::~QueuePolicyEvaluation(void)
0x180020211  xor     eax, eax
0x180020213  jmp     short loc_180020219
0x180020215  mov     eax, [rsp+1F8h+var_1B8]
0x180020219  mov     rcx, [rsp+1F8h+var_28]
0x180020221  xor     rcx, rsp; StackCookie
0x180020224  call    __security_check_cookie
0x180020229  mov     rbx, [rsp+1F8h+arg_8]
0x180020231  add     rsp, 1E0h
0x180020238  pop     r14
0x18002023a  pop     rdi
0x18002023b  pop     rsi
0x18002023c  retn
```
