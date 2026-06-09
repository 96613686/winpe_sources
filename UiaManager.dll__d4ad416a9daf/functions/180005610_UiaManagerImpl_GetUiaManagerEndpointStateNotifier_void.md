# UiaManagerImpl::GetUiaManagerEndpointStateNotifier(void)

- ea: `0x180005610`
- end: `0x180005702`
- name: `?GetUiaManagerEndpointStateNotifier@UiaManagerImpl@@AEAA?AV?$ComPtr@UIUiaManagerEndpointStateNotifierSink@@@WRL@Microsoft@@XZ`
- size: `242`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000ba00`
- `0x1800139a0`
- `0x18006fde0`
- `0x180070000`
- `0x180070120`

## callees

- `0x1800054f8`
- `0x180005610`
- `0x180018868`
- `0x180031540`
- `0x18006d474`
- `0x180091010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18000569b`
- `msvcp_win!_Mtx_unlock` at `0x18000569b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005666`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005666`

## string_xrefs

- `0x1800056f0`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *__fastcall UiaManagerImpl::GetUiaManagerEndpointStateNotifier(__int64 a1, __int64 *a2)
{
  __int64 *v4; // rbx
  HRESULT v5; // eax
  LPVOID v6; // rcx
  __int64 v7; // rcx
  int ppv; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPVOID v11; // [rsp+50h] [rbp+8h] BYREF

  v4 = (__int64 *)(a1 + 848);
  if ( !*(_QWORD *)(a1 + 848) )
  {
    v11 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
    v5 = CoCreateInstance(
           &CLSID_UiaManagerEndpointStateNotifier,
           0,
           4u,
           &GUID_12127662_a088_41c6_afc7_4cbf014a4c7e,
           &v11);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x212,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
        (const char *)(unsigned int)v5,
        ppv);
    std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 856));
    if ( !*v4 )
      Microsoft::WRL::ComPtr<IUiaManagerEndpointStateNotifierSink>::operator=(v4, &v11);
    _Mtx_unlock((_Mtx_t)(a1 + 856));
    v6 = v11;
    if ( v11 )
    {
      v11 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  v7 = *v4;
  *a2 = *v4;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  return a2;
}

```

## disassembly

```asm
0x180005610  mov     rax, rsp
0x180005613  mov     [rax+10h], rbx
0x180005617  mov     [rax+18h], rsi
0x18000561b  push    rdi
0x18000561c  sub     rsp, 40h
0x180005620  mov     rdi, rdx
0x180005623  mov     rsi, rcx
0x180005626  lea     rbx, [rcx+350h]
0x18000562d  cmp     qword ptr [rbx], 0
0x180005631  jnz     loc_1800056C2
0x180005637  mov     qword ptr [rax+8], 0
0x18000563f  lea     rcx, [rax+8]
0x180005643  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180005648  lea     rax, [rsp+48h+arg_0]
0x18000564d  mov     qword ptr [rsp+48h+ppv], rax; int
0x180005652  lea     r9, _GUID_12127662_a088_41c6_afc7_4cbf014a4c7e; riid
0x180005659  xor     edx, edx; pUnkOuter
0x18000565b  lea     r8d, [rdx+4]; dwClsContext
0x18000565f  lea     rcx, CLSID_UiaManagerEndpointStateNotifier; rclsid
0x180005666  call    cs:__imp_CoCreateInstance
0x18000566c  mov     rcx, [rsp+48h]; this
0x180005671  test    eax, eax
0x180005673  js      short loc_1800056ED
0x180005675  lea     rcx, [rsi+358h]; this
0x18000567c  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180005681  cmp     qword ptr [rbx], 0
0x180005685  jnz     short loc_180005694
0x180005687  lea     rdx, [rsp+48h+arg_0]
0x18000568c  mov     rcx, rbx
0x18000568f  call    ??4?$ComPtr@UIUiaManagerEndpointStateNotifierSink@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IUiaManagerEndpointStateNotifierSink>::operator=(Microsoft::WRL::ComPtr<IUiaManagerEndpointStateNotifierSink> &&)
0x180005694  lea     rcx, [rsi+358h]; _Mtx_t
0x18000569b  call    cs:__imp__Mtx_unlock
0x1800056a1  nop
0x1800056a2  mov     rcx, [rsp+48h+arg_0]
0x1800056a7  test    rcx, rcx
0x1800056aa  jz      short loc_1800056C2
0x1800056ac  mov     [rsp+48h+arg_0], 0
0x1800056b5  mov     rax, [rcx]
0x1800056b8  mov     rax, [rax+10h]
0x1800056bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056c1  nop
0x1800056c2  mov     rcx, [rbx]
0x1800056c5  mov     [rdi], rcx
0x1800056c8  test    rcx, rcx
0x1800056cb  jz      short loc_1800056DA
0x1800056cd  mov     rax, [rcx]
0x1800056d0  mov     rax, [rax+8]
0x1800056d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056d9  nop
0x1800056da  mov     rax, rdi
0x1800056dd  mov     rbx, [rsp+48h+arg_8]
0x1800056e2  mov     rsi, [rsp+48h+arg_10]
0x1800056e7  add     rsp, 40h
0x1800056eb  pop     rdi
0x1800056ec  retn
0x1800056ed  mov     r9d, eax; char *
0x1800056f0  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x1800056f7  mov     edx, 212h; void *
0x1800056fc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
