# _lambda_15df47ab0cabbe53c99a4a7d317bb960_::operator()

- ea: `0x18001efb0`
- end: `0x18001f076`
- name: `_lambda_15df47ab0cabbe53c99a4a7d317bb960_::operator()`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18001e1f4`

## callees

- `0x1800089e8`
- `0x18001ea6c`
- `0x18001eadc`
- `0x18001efb0`
- `0x18001f07c`
- `0x1800212d0`
- `0x18005e010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18001f006`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18001f006`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_BOOL8 __fastcall lambda_15df47ab0cabbe53c99a4a7d317bb960_::operator()(__int64 a1)
{
  BOOL v1; // ebx
  _QWORD v3[2]; // [rsp+20h] [rbp-20h] BYREF
  _QWORD *v4; // [rsp+30h] [rbp-10h] BYREF
  __int16 v5; // [rsp+38h] [rbp-8h]
  __int64 v6; // [rsp+50h] [rbp+10h] BYREF
  HRESULT CanUnloadNow; // [rsp+58h] [rbp+18h] BYREF
  int v8; // [rsp+60h] [rbp+20h] BYREF

  v6 = a1;
  errorlib::scoped_error<hresult_error::tag>::scoped_error<hresult_error::tag>(&v8);
  v1 = 1;
  LOBYTE(v6) = 1;
  v3[0] = &v6;
  v3[1] = &v8;
  lambda_1985c226740a74586a5400633cb5e065_::operator()(v3);
  LOBYTE(v6) = 0;
  v4 = v3;
  v5 = 258;
  CanUnloadNow = NdrDllCanUnloadNow(&gPFactory);
  errorlib::scoped_error<hresult_error::tag>::receiveAndThrow<long>(&v8, &CanUnloadNow);
  if ( v8 != 1 )
  {
    CanUnloadNow = (*(__int64 (__fastcall **)(void *))(module + 24LL))(&module) != 0;
    errorlib::scoped_error<hresult_error::tag>::receiveAndThrow<long>(&v8, &CanUnloadNow);
    v1 = v8 == 1;
  }
  wil::details::ScopeExitFnGuard_std::tr1::reference_wrapper__lambda_1985c226740a74586a5400633cb5e065_____::operator()(&v4);
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v8);
  return v1;
}

```

## disassembly

```asm
0x18001efb0  mov     [rsp-8+arg_18], rbx
0x18001efb5  mov     [rsp-8+arg_0], rcx
0x18001efba  push    rbp
0x18001efbb  mov     rbp, rsp
0x18001efbe  sub     rsp, 40h
0x18001efc2  lea     rcx, [rbp+arg_10]
0x18001efc6  call    ??0?$scoped_error@Utag@hresult_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<hresult_error::tag>::scoped_error<hresult_error::tag>(void)
0x18001efcb  nop
0x18001efcc  mov     ebx, 1
0x18001efd1  mov     byte ptr [rbp+arg_0], bl
0x18001efd4  lea     rax, [rbp+arg_0]
0x18001efd8  mov     [rbp+var_20], rax
0x18001efdc  lea     rax, [rbp+arg_10]
0x18001efe0  mov     [rbp+var_18], rax
0x18001efe4  lea     rcx, [rbp+var_20]
0x18001efe8  call    _lambda_1985c226740a74586a5400633cb5e065___operator__
0x18001efed  mov     byte ptr [rbp+arg_0], 0
0x18001eff1  lea     rax, [rbp+var_20]
0x18001eff5  mov     [rbp+var_10], rax
0x18001eff9  mov     [rbp+var_8], 102h
0x18001efff  lea     rcx, gPFactory; pPSFactoryBuffer
0x18001f006  call    cs:__imp_NdrDllCanUnloadNow
0x18001f00c  mov     [rbp+arg_8], eax
0x18001f00f  lea     rdx, [rbp+arg_8]
0x18001f013  lea     rcx, [rbp+arg_10]
0x18001f017  call    ??$receiveAndThrow@J@?$scoped_error@Utag@hresult_error@@@errorlib@@QEAAX$$QEAJ@Z; errorlib::scoped_error<hresult_error::tag>::receiveAndThrow<long>(long &&)
0x18001f01c  cmp     [rbp+arg_10], ebx
0x18001f01f  jz      short loc_18001F056
0x18001f021  mov     rax, cs:?module@@3VGidsSimulatorManagerModule@@A; GidsSimulatorManagerModule module
0x18001f028  lea     rcx, ?module@@3VGidsSimulatorManagerModule@@A; GidsSimulatorManagerModule module
0x18001f02f  mov     rax, [rax+18h]
0x18001f033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f038  xor     ecx, ecx
0x18001f03a  test    eax, eax
0x18001f03c  setnz   cl
0x18001f03f  mov     [rbp+arg_8], ecx
0x18001f042  lea     rdx, [rbp+arg_8]
0x18001f046  lea     rcx, [rbp+arg_10]
0x18001f04a  call    ??$receiveAndThrow@J@?$scoped_error@Utag@hresult_error@@@errorlib@@QEAAX$$QEAJ@Z; errorlib::scoped_error<hresult_error::tag>::receiveAndThrow<long>(long &&)
0x18001f04f  cmp     [rbp+arg_10], ebx
0x18001f052  jz      short loc_18001F056
0x18001f054  xor     ebx, ebx
0x18001f056  lea     rcx, [rbp+var_10]
0x18001f05a  call    wil__details__ScopeExitFnGuard_std__tr1__reference_wrapper__lambda_1985c226740a74586a5400633cb5e065_______operator__
0x18001f05f  nop
0x18001f060  lea     rcx, [rbp+arg_10]
0x18001f064  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x18001f069  mov     eax, ebx
0x18001f06b  mov     rbx, [rsp+40h+arg_18]
0x18001f070  add     rsp, 40h
0x18001f074  pop     rbp
0x18001f075  retn
```
