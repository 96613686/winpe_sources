# PolicyEngineController::CreateAndAddPolicyEngine<DiskPolicyEngine>(void)

- ea: `0x18001ac78`
- end: `0x18001ad23`
- name: `??$CreateAndAddPolicyEngine@VDiskPolicyEngine@@@PolicyEngineController@@AEAAXXZ`
- size: `171`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c4f4`

## callees

- `0x180005120`
- `0x18000ccd4`
- `0x18001ac78`
- `0x18001b164`
- `0x18001b898`
- `0x18001b8c4`
- `0x180026010`

## string_xrefs

- `0x18001acbc`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\policyEngineController.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PolicyEngineController::CreateAndAddPolicyEngine<DiskPolicyEngine>(__int64 *a1)
{
  int v2; // eax
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *v6; // [rsp+30h] [rbp+8h] BYREF
  __int64 v7; // [rsp+38h] [rbp+10h]

  v6 = 0;
  v7 = a1[10];
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v6);
  v2 = Microsoft::WRL::Details::MakeAndInitialize<DiskPolicyEngine,IPolicyEngine,IUserAccountStore *,enum DeletionPolicy &>(&v6);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\policyEngineController.h",
      (const char *)(unsigned int)v2,
      v4);
  if ( (*(unsigned __int8 (__fastcall **)(void *))(*(_QWORD *)v6 + 24LL))(v6) )
  {
    if ( a1[8] == a1[9] )
    {
      std::vector<Microsoft::WRL::ComPtr<IPolicyEngine>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<IPolicyEngine> const &>(
        a1 + 7,
        a1[8],
        (__int64 *)&v6);
    }
    else
    {
      std::_Construct_in_place<Microsoft::WRL::ComPtr<IPolicyEngine>,Microsoft::WRL::ComPtr<IPolicyEngine> const &>(
        (__int64 *)a1[8],
        (__int64 *)&v6);
      a1[8] += 8;
    }
  }
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v6);
}

```

## disassembly

```asm
0x18001ac78  push    rbx; int
0x18001ac7a  sub     rsp, 20h
0x18001ac7e  mov     rbx, rcx
0x18001ac81  mov     [rsp+28h+arg_0], 0
0x18001ac8a  mov     rax, [rcx+50h]
0x18001ac8e  mov     [rsp+28h+arg_8], rax
0x18001ac93  lea     rcx, [rsp+28h+arg_0]
0x18001ac98  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ac9d  lea     r8, [rbx+30h]
0x18001aca1  lea     rdx, [rsp+28h+arg_8]
0x18001aca6  lea     rcx, [rsp+28h+arg_0]; void **
0x18001acab  call    ??$MakeAndInitialize@VDiskPolicyEngine@@UIPolicyEngine@@PEAUIUserAccountStore@@AEAW4DeletionPolicy@@@Details@WRL@Microsoft@@YAJPEAPEAUIPolicyEngine@@$$QEAPEAUIUserAccountStore@@AEAW4DeletionPolicy@@@Z; Microsoft::WRL::Details::MakeAndInitialize<DiskPolicyEngine,IPolicyEngine,IUserAccountStore *,DeletionPolicy &>(IPolicyEngine * *,IUserAccountStore * &&,DeletionPolicy &)
0x18001acb0  mov     rcx, [rsp+28h]; this
0x18001acb5  test    eax, eax
0x18001acb7  jns     short loc_18001ACCE
0x18001acb9  mov     r9d, eax; char *
0x18001acbc  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001acc3  mov     edx, 24h ; '$'; void *
0x18001acc8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001acce  mov     rcx, [rsp+28h+arg_0]
0x18001acd3  mov     rax, [rcx]
0x18001acd6  mov     rax, [rax+18h]
0x18001acda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acdf  test    al, al
0x18001ace1  jz      short loc_18001AD13
0x18001ace3  mov     rax, [rbx+40h]
0x18001ace7  cmp     rax, [rbx+48h]
0x18001aceb  jz      short loc_18001AD01
0x18001aced  lea     rdx, [rsp+28h+arg_0]
0x18001acf2  mov     rcx, rax
0x18001acf5  call    ??$_Construct_in_place@V?$ComPtr@UIPolicyEngine@@@WRL@Microsoft@@AEBV123@@std@@YAXAEAV?$ComPtr@UIPolicyEngine@@@WRL@Microsoft@@AEBV123@@Z; std::_Construct_in_place<Microsoft::WRL::ComPtr<IPolicyEngine>,Microsoft::WRL::ComPtr<IPolicyEngine> const &>(Microsoft::WRL::ComPtr<IPolicyEngine> &,Microsoft::WRL::ComPtr<IPolicyEngine> const &)
0x18001acfa  add     qword ptr [rbx+40h], 8
0x18001acff  jmp     short loc_18001AD13
0x18001ad01  lea     r8, [rsp+28h+arg_0]
0x18001ad06  mov     rdx, rax
0x18001ad09  lea     rcx, [rbx+38h]
0x18001ad0d  call    ??$_Emplace_reallocate@AEBV?$ComPtr@UIPolicyEngine@@@WRL@Microsoft@@@?$vector@V?$ComPtr@UIPolicyEngine@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIPolicyEngine@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@UIPolicyEngine@@@WRL@Microsoft@@QEAV234@AEBV234@@Z; std::vector<Microsoft::WRL::ComPtr<IPolicyEngine>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<IPolicyEngine> const &>(Microsoft::WRL::ComPtr<IPolicyEngine> * const,Microsoft::WRL::ComPtr<IPolicyEngine> const &)
0x18001ad12  nop
0x18001ad13  lea     rcx, [rsp+28h+arg_0]
0x18001ad18  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ad1d  add     rsp, 20h
0x18001ad21  pop     rbx
0x18001ad22  retn
```
