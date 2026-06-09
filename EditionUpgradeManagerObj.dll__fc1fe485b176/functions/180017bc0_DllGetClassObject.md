# DllGetClassObject

- ea: `0x180017bc0`
- end: `0x180017c6f`
- name: `DllGetClassObject`
- size: `175`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x18001356c`
- `0x180017bc0`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180017c26`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180017c26`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  int v5; // ebx
  int v6; // ecx
  _QWORD *v7; // rdi
  __int64 (__fastcall *v8)(const IID *const, LPVOID *); // rax
  int v9; // eax
  int v11; // [rsp+40h] [rbp+18h] BYREF

  v11 = 0;
  if ( !ppv )
  {
    v5 = -2147467261;
LABEL_3:
    v6 = v5;
    goto LABEL_8;
  }
  v7 = CComMainDllModuleT<CSrvDllModuleT<CEmptyType>,CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>::g_pGlobalState;
  if ( !CSortedArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::Find(
          (__int64)CComMainDllModuleT<CSrvDllModuleT<CEmptyType>,CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>::g_pGlobalState
        + 24,
          rclsid,
          &v11) )
  {
    *ppv = 0;
    v5 = -2147221231;
    goto LABEL_3;
  }
  v8 = (__int64 (__fastcall *)(const IID *const, LPVOID *))DecodePointer(*(PVOID *)(*(_QWORD *)(v7[4] + 8LL * v11) + 24LL));
  v9 = v8(riid, ppv);
  v5 = v9;
  if ( v9 >= 0 )
    goto LABEL_9;
  v6 = v9;
LABEL_8:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
LABEL_9:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( v5 < 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  return v5;
}

```

## disassembly

```asm
0x180017bc0  mov     [rsp+arg_0], rbx
0x180017bc5  mov     [rsp+arg_8], rsi
0x180017bca  push    rdi
0x180017bcb  sub     rsp, 20h
0x180017bcf  mov     [rsp+28h+arg_10], 0
0x180017bd7  mov     rsi, rdx
0x180017bda  mov     rdx, rcx
0x180017bdd  mov     rbx, r8
0x180017be0  test    r8, r8
0x180017be3  jnz     short loc_180017BEE
0x180017be5  mov     ebx, 80004003h
0x180017bea  mov     ecx, ebx
0x180017bec  jmp     short loc_180017C3F
0x180017bee  mov     rdi, cs:?g_pGlobalState@?$CComMainDllModuleT@V?$CSrvDllModuleT@VCEmptyType@@@@V?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@@@0PEAV?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@EA; CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>> * CComMainDllModuleT<CSrvDllModuleT<CEmptyType>,CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>>::g_pGlobalState
0x180017bf5  lea     r8, [rsp+28h+arg_10]
0x180017bfa  lea     rcx, [rdi+18h]
0x180017bfe  call    ?Find@?$CSortedArray@PEAU?$CComObjectActivationT@VCEmptyType@@@@U_GUID@@VCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NAEBU_GUID@@PEAH@Z; CSortedArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::Find(_GUID const &,int *)
0x180017c03  test    al, al
0x180017c05  jnz     short loc_180017C15
0x180017c07  mov     qword ptr [rbx], 0
0x180017c0e  mov     ebx, 80040111h
0x180017c13  jmp     short loc_180017BEA
0x180017c15  mov     rcx, [rdi+20h]
0x180017c19  movsxd  rax, [rsp+28h+arg_10]
0x180017c1e  mov     rcx, [rcx+rax*8]
0x180017c22  mov     rcx, [rcx+18h]; Ptr
0x180017c26  call    cs:__imp_DecodePointer
0x180017c2c  mov     rdx, rbx
0x180017c2f  mov     rcx, rsi
0x180017c32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c37  mov     ebx, eax
0x180017c39  test    eax, eax
0x180017c3b  jns     short loc_180017C44
0x180017c3d  mov     ecx, eax
0x180017c3f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180017c44  mov     ecx, ebx
0x180017c46  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180017c4b  test    ebx, ebx
0x180017c4d  jns     short loc_180017C56
0x180017c4f  mov     ecx, ebx
0x180017c51  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180017c56  mov     ecx, ebx
0x180017c58  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180017c5d  mov     rsi, [rsp+28h+arg_8]
0x180017c62  mov     eax, ebx
0x180017c64  mov     rbx, [rsp+28h+arg_0]
0x180017c69  add     rsp, 20h
0x180017c6d  pop     rdi
0x180017c6e  retn
```
