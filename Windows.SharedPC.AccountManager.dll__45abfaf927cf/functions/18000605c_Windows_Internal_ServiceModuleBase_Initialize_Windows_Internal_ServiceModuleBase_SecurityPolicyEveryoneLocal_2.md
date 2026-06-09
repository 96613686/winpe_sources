# Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>(uchar,uchar,uchar,uchar,void *,ulong)

- ea: `0x18000605c`
- end: `0x1800061d2`
- name: `??$Initialize@USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@34@@ServiceModuleBase@Internal@Windows@@QEAAJEEEEPEAXK@Z`
- size: `374`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180008920`

## callees

- `0x180005120`
- `0x180005e90`
- `0x18000605c`
- `0x180008a38`
- `0x180009114`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006134`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006134`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180006089`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180006089`

## string_xrefs

- `0x1800060a0`: `onecore\internal\com\inc\comservicehelper.h`
- `0x1800060df`: `onecore\internal\com\inc\comservicehelper.h`
- `0x180006148`: `onecore\internal\com\inc\comservicehelper.h`
- `0x1800061a7`: `onecore\internal\com\inc\comservicehelper.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>(
        _DWORD *a1)
{
  Windows::Internal::ServiceModuleBase *v2; // rbx
  int v3; // eax
  unsigned int v4; // esi
  int v6; // eax
  HRESULT Instance; // eax
  int v8; // eax
  unsigned int v9; // edi
  int ppv; // [rsp+20h] [rbp-58h]
  int ppva; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  __int64 v13; // [rsp+80h] [rbp+8h] BYREF

  v2 = (Windows::Internal::ServiceModuleBase *)*wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                                  &v13,
                                                  (__int64)a1);
  v3 = RoInitialize(1);
  v4 = v3;
  a1[4] = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
      (const char *)(unsigned int)v3,
      ppv);
    Windows::Internal::ServiceModuleBase::Uninitialize(v2);
    return v4;
  }
  v6 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)a1 + 32LL))(a1);
  v4 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7B,
      (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
      (const char *)(unsigned int)v6,
      ppv);
    Windows::Internal::ServiceModuleBase::Uninitialize(v2);
    return v4;
  }
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)a1 + 16LL))(a1);
  *((_BYTE *)a1 + 20) = 1;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 6);
  Instance = CoCreateInstance(
               &CLSID_ContextSwitcher,
               0,
               1u,
               &GUID_000001da_0000_0000_c000_000000000046,
               (LPVOID *)a1 + 3);
  v4 = Instance;
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
      (const char *)(unsigned int)Instance,
      ppva);
    Windows::Internal::ServiceModuleBase::Uninitialize(v2);
    return v4;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall *)(struct tagComCallData *), _DWORD *, GUID *))(**((_QWORD **)a1 + 3) + 24LL))(
         *((_QWORD *)a1 + 3),
         Windows::Internal::ServiceModuleBase::ConnectCallbackThunk,
         a1,
         &IID_IContextCallback);
  v9 = v8;
  if ( v8 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x90,
    (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
    (const char *)(unsigned int)v8,
    5);
  Windows::Internal::ServiceModuleBase::Uninitialize(v2);
  return v9;
}

```

## disassembly

```asm
0x18000605c  mov     rax, rsp
0x18000605f  push    rbx
0x180006060  push    rsi
0x180006061  push    rdi
0x180006062  push    r14
0x180006064  sub     rsp, 58h
0x180006068  mov     rdi, rcx
0x18000606b  mov     rdx, rcx
0x18000606e  lea     rcx, [rax+8]
0x180006072  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180006077  mov     rbx, [rax]
0x18000607a  mov     [rsp+78h+var_38], rbx
0x18000607f  mov     [rsp+78h+var_30], 1
0x180006084  mov     ecx, 1
0x180006089  call    cs:__imp_RoInitialize
0x18000608f  mov     esi, eax
0x180006091  mov     [rdi+10h], eax
0x180006094  test    eax, eax
0x180006096  jns     short loc_1800060C2
0x180006098  mov     rcx, [rsp+78h]; this
0x18000609d  mov     r9d, eax; char *
0x1800060a0  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x1800060a7  mov     edx, 63h ; 'c'; void *
0x1800060ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800060b1  nop
0x1800060b2  mov     rcx, rbx; this
0x1800060b5  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x1800060ba  nop
0x1800060bb  mov     eax, esi
0x1800060bd  jmp     loc_1800061C8
0x1800060c2  mov     rax, [rdi]
0x1800060c5  mov     rcx, rdi
0x1800060c8  mov     rax, [rax+20h]
0x1800060cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060d1  mov     esi, eax
0x1800060d3  test    eax, eax
0x1800060d5  jns     short loc_1800060FC
0x1800060d7  mov     rcx, [rsp+78h]; this
0x1800060dc  mov     r9d, eax; char *
0x1800060df  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x1800060e6  mov     edx, 7Bh ; '{'; void *
0x1800060eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800060f0  nop
0x1800060f1  mov     rcx, rbx; this
0x1800060f4  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x1800060f9  nop
0x1800060fa  jmp     short loc_1800060BB
0x1800060fc  mov     rax, [rdi]
0x1800060ff  mov     rcx, rdi
0x180006102  mov     rax, [rax+10h]
0x180006106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000610b  mov     byte ptr [rdi+14h], 1
0x18000610f  lea     r14, [rdi+18h]
0x180006113  mov     rcx, r14
0x180006116  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000611b  mov     [rsp+78h+ppv], r14; int
0x180006120  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x180006127  xor     edx, edx; pUnkOuter
0x180006129  lea     r8d, [rdx+1]; dwClsContext
0x18000612d  lea     rcx, CLSID_ContextSwitcher; rclsid
0x180006134  call    cs:__imp_CoCreateInstance
0x18000613a  mov     esi, eax
0x18000613c  test    eax, eax
0x18000613e  jns     short loc_180006168
0x180006140  mov     rcx, [rsp+78h]; this
0x180006145  mov     r9d, eax; char *
0x180006148  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x18000614f  mov     edx, 8Dh; void *
0x180006154  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006159  nop
0x18000615a  mov     rcx, rbx; this
0x18000615d  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x180006162  nop
0x180006163  jmp     loc_1800060BB
0x180006168  mov     rcx, [r14]
0x18000616b  mov     rax, [rcx]
0x18000616e  mov     [rsp+78h+var_50], 0
0x180006177  mov     dword ptr [rsp+78h+ppv], 5; int
0x18000617f  lea     r9, IID_IContextCallback
0x180006186  mov     r8, rdi
0x180006189  lea     rdx, ?ConnectCallbackThunk@ServiceModuleBase@Internal@Windows@@SAJPEAUtagComCallData@@@Z; Windows::Internal::ServiceModuleBase::ConnectCallbackThunk(tagComCallData *)
0x180006190  mov     rax, [rax+18h]
0x180006194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006199  mov     edi, eax
0x18000619b  test    eax, eax
0x18000619d  jns     short loc_1800061C6
0x18000619f  mov     rcx, [rsp+78h]; this
0x1800061a4  mov     r9d, eax; char *
0x1800061a7  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x1800061ae  mov     edx, 90h; void *
0x1800061b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800061b8  nop
0x1800061b9  mov     rcx, rbx; this
0x1800061bc  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x1800061c1  nop
0x1800061c2  mov     eax, edi
0x1800061c4  jmp     short loc_1800061C8
0x1800061c6  xor     eax, eax
0x1800061c8  add     rsp, 58h
0x1800061cc  pop     r14
0x1800061ce  pop     rdi
0x1800061cf  pop     rsi
0x1800061d0  pop     rbx
0x1800061d1  retn
```
