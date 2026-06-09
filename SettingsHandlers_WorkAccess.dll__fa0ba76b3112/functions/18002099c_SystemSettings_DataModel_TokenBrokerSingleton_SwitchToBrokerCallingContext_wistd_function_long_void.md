# SystemSettings::DataModel::TokenBrokerSingleton::_SwitchToBrokerCallingContext(wistd::function<long (void)>)

- ea: `0x18002099c`
- end: `0x180020a7b`
- name: `?_SwitchToBrokerCallingContext@TokenBrokerSingleton@DataModel@SystemSettings@@CAJV?$function@$$A6AJXZ@wistd@@@Z`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020698`

## callees

- `0x1800045ec`
- `0x1800054b8`
- `0x1800096ec`
- `0x1800196ac`
- `0x18001a95c`
- `0x18002099c`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800209bd`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800209bd`

## string_xrefs

- `0x1800209d7`: `ShellCommon\private\Shell\inc\tokenbrokersingleton.h`
- `0x180020a31`: `ShellCommon\private\Shell\inc\tokenbrokersingleton.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::DataModel::TokenBrokerSingleton::_SwitchToBrokerCallingContext(__int64 a1)
{
  HRESULT v2; // eax
  unsigned int v3; // edi
  _lambda_d499bb7c7bb9030fdb66f37c3eece255_ *v4; // rax
  __int64 v5; // rcx
  int v6; // eax
  int v8[6]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  struct SystemSettings::DataModel::TokenBrokerSingleton *v10; // [rsp+48h] [rbp+10h] BYREF
  char v11; // [rsp+50h] [rbp+18h] BYREF

  v10 = 0;
  v2 = CoSwitchCallContext(0, (IUnknown **)&v10);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x180,
      (unsigned int)"ShellCommon\\private\\Shell\\inc\\tokenbrokersingleton.h",
      (const char *)(unsigned int)v2,
      v8[0]);
LABEL_7:
    wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::~function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>(a1);
    return v3;
  }
  v4 = _lambda_d499bb7c7bb9030fdb66f37c3eece255_::_lambda_d499bb7c7bb9030fdb66f37c3eece255_(
         (_lambda_d499bb7c7bb9030fdb66f37c3eece255_ *)&v11,
         &v10);
  wil::ScopeExit<_lambda_838e7888268f113a0424cd4af7690a39_>(v8, v4);
  v5 = *(_QWORD *)(a1 + 112);
  if ( !v5 )
    __fastfail(7u);
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 32LL))(v5);
  v3 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x188,
      (unsigned int)"ShellCommon\\private\\Shell\\inc\\tokenbrokersingleton.h",
      (const char *)(unsigned int)v6,
      v8[0]);
    wil::details::ScopeExitFn<_lambda_838e7888268f113a0424cd4af7690a39_>::~ScopeExitFn<_lambda_838e7888268f113a0424cd4af7690a39_>(v8);
    goto LABEL_7;
  }
  wil::details::ScopeExitFn<_lambda_838e7888268f113a0424cd4af7690a39_>::~ScopeExitFn<_lambda_838e7888268f113a0424cd4af7690a39_>(v8);
  wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::~function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>(a1);
  return 0;
}

```

## disassembly

```asm
0x18002099c  mov     rax, rsp
0x18002099f  mov     [rax+20h], rbx
0x1800209a3  mov     [rax+8], rcx
0x1800209a7  push    rdi
0x1800209a8  sub     rsp, 30h
0x1800209ac  mov     rbx, rcx
0x1800209af  mov     qword ptr [rax+10h], 0
0x1800209b7  lea     rdx, [rax+10h]; ppOldObject
0x1800209bb  xor     ecx, ecx; pNewObject
0x1800209bd  call    cs:__imp_CoSwitchCallContext
0x1800209c4  nop     dword ptr [rax+rax+00h]
0x1800209c9  mov     edi, eax
0x1800209cb  test    eax, eax
0x1800209cd  jns     short loc_1800209EA
0x1800209cf  mov     rcx, [rsp+38h]; this
0x1800209d4  mov     r9d, eax; char *
0x1800209d7  lea     r8, aShellcommonPri; "ShellCommon\\private\\Shell\\inc\\token"...
0x1800209de  mov     edx, 180h; void *
0x1800209e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800209e8  jmp     short loc_180020A4E
0x1800209ea  lea     rdx, [rsp+38h+arg_8]; struct SystemSettings::DataModel::TokenBrokerSingleton **
0x1800209ef  lea     rcx, [rsp+38h+arg_10]; this
0x1800209f4  call    ??0_lambda_d499bb7c7bb9030fdb66f37c3eece255_@@QEAA@AEBQEAVTokenBrokerSingleton@DataModel@SystemSettings@@@Z; _lambda_d499bb7c7bb9030fdb66f37c3eece255_::_lambda_d499bb7c7bb9030fdb66f37c3eece255_(SystemSettings::DataModel::TokenBrokerSingleton * const &)
0x1800209f9  mov     rdx, rax
0x1800209fc  lea     rcx, [rsp+38h+var_18]
0x180020a01  call    ??$ScopeExit@V_lambda_838e7888268f113a0424cd4af7690a39_@@@wil@@YA?AV?$ScopeExitFn@V_lambda_838e7888268f113a0424cd4af7690a39_@@@details@0@$$QEAV_lambda_838e7888268f113a0424cd4af7690a39_@@@Z; wil::ScopeExit<_lambda_838e7888268f113a0424cd4af7690a39_>(_lambda_838e7888268f113a0424cd4af7690a39_ &&)
0x180020a06  nop
0x180020a07  mov     rcx, [rbx+70h]
0x180020a0b  test    rcx, rcx
0x180020a0e  jnz     short loc_180020A17
0x180020a10  mov     ecx, 7
0x180020a15  int     29h; Win8: RtlFailFast(ecx)
0x180020a17  mov     rax, [rcx]
0x180020a1a  mov     rax, [rax+20h]
0x180020a1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a23  mov     edi, eax
0x180020a25  test    eax, eax
0x180020a27  jns     short loc_180020A5A
0x180020a29  mov     rcx, [rsp+38h]; this
0x180020a2e  mov     r9d, eax; char *
0x180020a31  lea     r8, aShellcommonPri; "ShellCommon\\private\\Shell\\inc\\token"...
0x180020a38  mov     edx, 188h; void *
0x180020a3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020a42  nop
0x180020a43  lea     rcx, [rsp+38h+var_18]
0x180020a48  call    ??1?$ScopeExitFn@V_lambda_838e7888268f113a0424cd4af7690a39_@@@details@wil@@QEAA@XZ; wil::details::ScopeExitFn<_lambda_838e7888268f113a0424cd4af7690a39_>::~ScopeExitFn<_lambda_838e7888268f113a0424cd4af7690a39_>(void)
0x180020a4d  nop
0x180020a4e  mov     rcx, rbx
0x180020a51  call    ??1?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEAA@XZ; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::~function<long (ushort *,unsigned __int64,unsigned __int64 *)>(void)
0x180020a56  mov     eax, edi
0x180020a58  jmp     short loc_180020A6F
0x180020a5a  lea     rcx, [rsp+38h+var_18]
0x180020a5f  call    ??1?$ScopeExitFn@V_lambda_838e7888268f113a0424cd4af7690a39_@@@details@wil@@QEAA@XZ; wil::details::ScopeExitFn<_lambda_838e7888268f113a0424cd4af7690a39_>::~ScopeExitFn<_lambda_838e7888268f113a0424cd4af7690a39_>(void)
0x180020a64  nop
0x180020a65  mov     rcx, rbx
0x180020a68  call    ??1?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEAA@XZ; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::~function<long (ushort *,unsigned __int64,unsigned __int64 *)>(void)
0x180020a6d  xor     eax, eax
0x180020a6f  mov     rbx, [rsp+38h+arg_18]
0x180020a74  add     rsp, 30h
0x180020a78  pop     rdi
0x180020a79  retn
```
