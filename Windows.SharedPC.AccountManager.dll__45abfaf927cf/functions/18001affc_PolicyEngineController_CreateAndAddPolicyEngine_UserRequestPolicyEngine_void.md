# PolicyEngineController::CreateAndAddPolicyEngine<UserRequestPolicyEngine>(void)

- ea: `0x18001affc`
- end: `0x18001b0a7`
- name: `??$CreateAndAddPolicyEngine@VUserRequestPolicyEngine@@@PolicyEngineController@@AEAAXXZ`
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
- `0x18001affc`
- `0x18001b774`
- `0x18001b898`
- `0x18001b8c4`
- `0x180026010`

## string_xrefs

- `0x18001b040`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\policyEngineController.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PolicyEngineController::CreateAndAddPolicyEngine<UserRequestPolicyEngine>(__int64 *a1)
{
  int v2; // eax
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *v6; // [rsp+30h] [rbp+8h] BYREF
  __int64 v7; // [rsp+38h] [rbp+10h]

  v6 = 0;
  v7 = a1[10];
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v6);
  v2 = Microsoft::WRL::Details::MakeAndInitialize<UserRequestPolicyEngine,IPolicyEngine,IUserAccountStore *,enum DeletionPolicy &>(&v6);
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
0x18001affc  push    rbx; int
0x18001affe  sub     rsp, 20h
0x18001b002  mov     rbx, rcx
0x18001b005  mov     [rsp+28h+arg_0], 0
0x18001b00e  mov     rax, [rcx+50h]
0x18001b012  mov     [rsp+28h+arg_8], rax
0x18001b017  lea     rcx, [rsp+28h+arg_0]
0x18001b01c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b021  lea     r8, [rbx+30h]
0x18001b025  lea     rdx, [rsp+28h+arg_8]
0x18001b02a  lea     rcx, [rsp+28h+arg_0]; void **
0x18001b02f  call    ??$MakeAndInitialize@VUserRequestPolicyEngine@@UIPolicyEngine@@PEAUIUserAccountStore@@AEAW4DeletionPolicy@@@Details@WRL@Microsoft@@YAJPEAPEAUIPolicyEngine@@$$QEAPEAUIUserAccountStore@@AEAW4DeletionPolicy@@@Z; Microsoft::WRL::Details::MakeAndInitialize<UserRequestPolicyEngine,IPolicyEngine,IUserAccountStore *,DeletionPolicy &>(IPolicyEngine * *,IUserAccountStore * &&,DeletionPolicy &)
0x18001b034  mov     rcx, [rsp+28h]; this
0x18001b039  test    eax, eax
0x18001b03b  jns     short loc_18001B052
0x18001b03d  mov     r9d, eax; char *
0x18001b040  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001b047  mov     edx, 24h ; '$'; void *
0x18001b04c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001b052  mov     rcx, [rsp+28h+arg_0]
0x18001b057  mov     rax, [rcx]
0x18001b05a  mov     rax, [rax+18h]
0x18001b05e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b063  test    al, al
0x18001b065  jz      short loc_18001B097
0x18001b067  mov     rax, [rbx+40h]
0x18001b06b  cmp     rax, [rbx+48h]
0x18001b06f  jz      short loc_18001B085
0x18001b071  lea     rdx, [rsp+28h+arg_0]
0x18001b076  mov     rcx, rax
0x18001b079  call    ??$_Construct_in_place@V?$ComPtr@UIPolicyEngine@@@WRL@Microsoft@@AEBV123@@std@@YAXAEAV?$ComPtr@UIPolicyEngine@@@WRL@Microsoft@@AEBV123@@Z; std::_Construct_in_place<Microsoft::WRL::ComPtr<IPolicyEngine>,Microsoft::WRL::ComPtr<IPolicyEngine> const &>(Microsoft::WRL::ComPtr<IPolicyEngine> &,Microsoft::WRL::ComPtr<IPolicyEngine> const &)
0x18001b07e  add     qword ptr [rbx+40h], 8
0x18001b083  jmp     short loc_18001B097
0x18001b085  lea     r8, [rsp+28h+arg_0]
0x18001b08a  mov     rdx, rax
0x18001b08d  lea     rcx, [rbx+38h]
0x18001b091  call    ??$_Emplace_reallocate@AEBV?$ComPtr@UIPolicyEngine@@@WRL@Microsoft@@@?$vector@V?$ComPtr@UIPolicyEngine@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIPolicyEngine@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@UIPolicyEngine@@@WRL@Microsoft@@QEAV234@AEBV234@@Z; std::vector<Microsoft::WRL::ComPtr<IPolicyEngine>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<IPolicyEngine> const &>(Microsoft::WRL::ComPtr<IPolicyEngine> * const,Microsoft::WRL::ComPtr<IPolicyEngine> const &)
0x18001b096  nop
0x18001b097  lea     rcx, [rsp+28h+arg_0]
0x18001b09c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b0a1  add     rsp, 20h
0x18001b0a5  pop     rbx
0x18001b0a6  retn
```
