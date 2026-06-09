# ApplicationInstanceBroker::GetActivatedEventArgs(IInspectable * *)

- ea: `0x180014390`
- end: `0x180014540`
- name: `?GetActivatedEventArgs@ApplicationInstanceBroker@@UEAAJPEAPEAUIInspectable@@@Z`
- size: `432`
- prototype: `__int64 __fastcall(ApplicationInstanceBroker *__hidden this, struct IInspectable **)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800142f8`
- `0x180014390`
- `0x180015ba0`
- `0x180015f14`
- `0x18001baa4`
- `0x18001e3c4`
- `0x18001e5ac`
- `0x180027ce8`
- `0x180056208`
- `0x18005ae90`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001449d`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001449d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800144f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800144f3`

## string_xrefs

- `0x1800143da`: `GetActivatedEventArgsBroker`
- `0x1800143cb`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\applicationinstancebroker.cpp`
- `0x1800144c8`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\applicationinstancebroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall ApplicationInstanceBroker::GetActivatedEventArgs(
        ApplicationInstanceBroker *this,
        struct IInspectable **a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, unsigned __int64, _QWORD, struct IInspectable **); // rbx
  DWORD ProcessId; // eax
  int v7; // eax
  int v9; // [rsp+20h] [rbp-1C8h]
  int v10; // [rsp+20h] [rbp-1C8h]
  bool v11; // [rsp+40h] [rbp-1A8h] BYREF
  bool v12; // [rsp+41h] [rbp-1A7h] BYREF
  HANDLE Process; // [rsp+48h] [rbp-1A0h] BYREF
  unsigned __int64 v14; // [rsp+50h] [rbp-198h] BYREF
  HANDLE *p_Process; // [rsp+58h] [rbp-190h]
  void *v16; // [rsp+60h] [rbp-188h] BYREF
  char v17; // [rsp+68h] [rbp-180h]
  _QWORD v18[42]; // [rsp+70h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  if ( !a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancebroker.cpp",
      (const char *)0x80070057LL,
      v9);
  wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v18,
    "GetActivatedEventArgsBroker");
  v18[0] = &AAMTraceProvider::GetActivatedEventArgsBroker::`vftable';
  AAMTraceProvider::GetActivatedEventArgsBroker::StartActivity((AAMTraceProvider::GetActivatedEventArgsBroker *)v18);
  Process = 0;
  v14 = -1;
  v11 = 0;
  v12 = 0;
  p_Process = &Process;
  v16 = 0;
  v17 = 1;
  ApplicationInstanceBroker::GetCallerData(&v16, 0, &v14, &v11, &v12, 0, 0);
  if ( v17 )
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      p_Process,
      v16);
  if ( v11 || !v12 )
  {
    v4 = *((_QWORD *)this + 2);
    v5 = *(__int64 (__fastcall **)(__int64, unsigned __int64, _QWORD, struct IInspectable **))(*(_QWORD *)v4 + 56LL);
    ProcessId = GetProcessId(Process);
    v7 = v5(v4, v14, ProcessId, a2);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x58,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancebroker.cpp",
        (const char *)(unsigned int)v7,
        v10);
  }
  wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v18);
  if ( (char *)Process - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(Process);
  v18[0] = &AAMTraceProvider::GetActivatedEventArgsBroker::`vftable';
  wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v18);
  wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v18);
  return 0;
}

```

## disassembly

```asm
0x180014390  mov     [rsp+arg_10], rbx
0x180014395  push    rsi
0x180014396  push    rdi
0x180014397  push    r15
0x180014399  sub     rsp, 1D0h
0x1800143a0  mov     rax, cs:__security_cookie
0x1800143a7  xor     rax, rsp
0x1800143aa  mov     [rsp+1E8h+var_28], rax
0x1800143b2  mov     rsi, rdx
0x1800143b5  mov     rdi, rcx
0x1800143b8  mov     rcx, [rsp+1E8h]; this
0x1800143c0  test    rdx, rdx
0x1800143c3  jnz     short loc_1800143DA
0x1800143c5  mov     r9d, 80070057h; char *
0x1800143cb  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800143d2  lea     edx, [rsi+4Bh]; void *
0x1800143d5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800143da  lea     rdx, aGetactivatedev_0; "GetActivatedEventArgsBroker"
0x1800143e1  lea     rcx, [rsp+1E8h+var_178]
0x1800143e6  call    ??0?$ActivityBase@VAAMTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800143eb  lea     r15, ??_7GetActivatedEventArgsBroker@AAMTraceProvider@@6B@; const AAMTraceProvider::GetActivatedEventArgsBroker::`vftable'
0x1800143f2  mov     [rsp+1E8h+var_178], r15
0x1800143f7  lea     rcx, [rsp+1E8h+var_178]; this
0x1800143fc  call    ?StartActivity@GetActivatedEventArgsBroker@AAMTraceProvider@@QEAAXXZ; AAMTraceProvider::GetActivatedEventArgsBroker::StartActivity(void)
0x180014401  nop
0x180014402  mov     [rsp+1E8h+Process], 0
0x18001440b  mov     [rsp+1E8h+var_198], 0FFFFFFFFFFFFFFFFh
0x180014414  mov     [rsp+1E8h+var_1A8], 0
0x180014419  mov     [rsp+1E8h+var_1A7], 0
0x18001441e  lea     rax, [rsp+1E8h+Process]
0x180014423  mov     [rsp+1E8h+var_190], rax
0x180014428  mov     [rsp+1E8h+var_188], 0
0x180014431  mov     [rsp+1E8h+var_180], 1
0x180014436  mov     [rsp+1E8h+var_1B8], 0; unsigned __int16 *
0x18001443f  mov     [rsp+1E8h+var_1C0], 0; unsigned int *
0x180014448  lea     rax, [rsp+1E8h+var_1A7]
0x18001444d  mov     [rsp+1E8h+var_1C8], rax; int
0x180014452  lea     r9, [rsp+1E8h+var_1A8]; bool *
0x180014457  lea     r8, [rsp+1E8h+var_198]; unsigned __int64 *
0x18001445c  xor     edx, edx; unsigned __int64 *
0x18001445e  lea     rcx, [rsp+1E8h+var_188]; void **
0x180014463  call    ?GetCallerData@ApplicationInstanceBroker@@CAXPEAPEAXPEA_K1AEA_N2PEAIPEAG@Z; ApplicationInstanceBroker::GetCallerData(void * *,unsigned __int64 *,unsigned __int64 *,bool &,bool &,uint *,ushort *)
0x180014468  nop
0x180014469  cmp     [rsp+1E8h+var_180], 0
0x18001446e  jz      short loc_18001447F
0x180014470  mov     rdx, [rsp+1E8h+var_188]
0x180014475  mov     rcx, [rsp+1E8h+var_190]
0x18001447a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001447f  cmp     [rsp+1E8h+var_1A8], 0
0x180014484  jnz     short loc_18001448D
0x180014486  cmp     [rsp+1E8h+var_1A7], 0
0x18001448b  jnz     short loc_1800144D9
0x18001448d  mov     rdi, [rdi+10h]
0x180014491  mov     rax, [rdi]
0x180014494  mov     rbx, [rax+38h]
0x180014498  mov     rcx, [rsp+1E8h+Process]; Process
0x18001449d  call    cs:__imp_GetProcessId
0x1800144a3  mov     r9, rsi
0x1800144a6  mov     r8d, eax
0x1800144a9  mov     rdx, [rsp+1E8h+var_198]
0x1800144ae  mov     rcx, rdi
0x1800144b1  mov     rax, rbx
0x1800144b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144b9  mov     rcx, [rsp+1E8h]; this
0x1800144c1  test    eax, eax
0x1800144c3  jns     short loc_1800144D9
0x1800144c5  mov     r9d, eax; char *
0x1800144c8  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800144cf  mov     edx, 58h ; 'X'; void *
0x1800144d4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800144d9  lea     rcx, [rsp+1E8h+var_178]
0x1800144de  call    ?Stop@?$ActivityBase@VAAMTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800144e3  nop
0x1800144e4  mov     rcx, [rsp+1E8h+Process]; hObject
0x1800144e9  lea     rax, [rcx-1]
0x1800144ed  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800144f1  ja      short loc_1800144FA
0x1800144f3  call    cs:__imp_CloseHandle
0x1800144f9  nop
0x1800144fa  mov     [rsp+1E8h+var_178], r15
0x1800144ff  lea     rcx, [rsp+1E8h+var_178]
0x180014504  call    ?Destroy@?$ActivityBase@VAAMTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180014509  lea     rcx, [rsp+1E8h+var_178]
0x18001450e  call    ??1?$ActivityBase@VAAMTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180014513  xor     eax, eax
0x180014515  jmp     short loc_18001451B
0x180014517  mov     eax, dword ptr [rsp+1E8h+Process]
0x18001451b  mov     rcx, [rsp+1E8h+var_28]
0x180014523  xor     rcx, rsp; StackCookie
0x180014526  call    __security_check_cookie
0x18001452b  mov     rbx, [rsp+1E8h+arg_10]
0x180014533  add     rsp, 1D0h
0x18001453a  pop     r15
0x18001453c  pop     rdi
0x18001453d  pop     rsi
0x18001453e  retn
```
