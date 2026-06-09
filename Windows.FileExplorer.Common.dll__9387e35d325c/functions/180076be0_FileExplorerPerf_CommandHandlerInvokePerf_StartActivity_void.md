# FileExplorerPerf::CommandHandlerInvokePerf::StartActivity(void)

- ea: `0x180076be0`
- end: `0x180076cbb`
- name: `?StartActivity@CommandHandlerInvokePerf@FileExplorerPerf@@QEAAXXZ`
- size: `219`
- prototype: `void __fastcall(FileExplorerPerf::CommandHandlerInvokePerf *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800723b0`

## callees

- `0x180001e3c`
- `0x18000e774`
- `0x18001d848`
- `0x18002d4e4`
- `0x180044020`
- `0x180076280`
- `0x180076be0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180076c15`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180076c15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180076c43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180076c43`

## pseudocode

```c
void __fastcall FileExplorerPerf::CommandHandlerInvokePerf::StartActivity(
        FileExplorerPerf::CommandHandlerInvokePerf *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // rdx
  int v5; // edi
  __int64 v6; // r8
  int v7; // ecx
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<FileExplorerPerf,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &CurrentThreadId);
  v2 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)FileExplorerPerf::Provider() <= 5u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  *(_DWORD *)v2 = 1;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&CurrentThreadId);
  v3 = FileExplorerPerf::Provider();
  v5 = (int)v3;
  if ( *(_DWORD *)v3 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v9 = 0;
    v6 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v6 + 4) || _tlgGuidIsZero((const struct _GUID *)(v6 + 24)) )
      v7 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)&byte_18009B8F7,
      v6 + 8,
      v7,
      (__int64)&v9,
      (__int64)&CurrentThreadId);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (FileExplorerPerf::CommandHandlerInvokePerf *)((char *)this + 288),
      v4);
}

```

## disassembly

```asm
0x180076be0  mov     [rsp+arg_10], rbx
0x180076be5  push    rdi
0x180076be6  sub     rsp, 30h
0x180076bea  mov     rbx, rcx
0x180076bed  lea     rdx, [rsp+38h+arg_0]
0x180076bf2  call    ?LockExclusive@?$ActivityBase@VFileExplorerPerf@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<FileExplorerPerf,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180076bf7  mov     rdi, [rbx+110h]
0x180076bfe  call    ?Provider@FileExplorerPerf@@SAPEBU_tlgProvider_t@@XZ; FileExplorerPerf::Provider(void)
0x180076c03  mov     r8d, [rax]
0x180076c06  cmp     r8d, 5
0x180076c0a  jbe     short loc_180076C1D
0x180076c0c  lea     rdx, [rdi+8]; ActivityId
0x180076c10  mov     ecx, 3; ControlCode
0x180076c15  call    cs:__imp_EventActivityIdControl
0x180076c1b  jmp     short loc_180076C24
0x180076c1d  xorps   xmm0, xmm0
0x180076c20  movups  xmmword ptr [rdi+8], xmm0
0x180076c24  mov     dword ptr [rdi], 1
0x180076c2a  lea     rcx, [rsp+38h+arg_0]
0x180076c2f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180076c34  call    ?Provider@FileExplorerPerf@@SAPEBU_tlgProvider_t@@XZ; FileExplorerPerf::Provider(void)
0x180076c39  mov     rdi, rax
0x180076c3c  mov     ecx, [rax]
0x180076c3e  cmp     ecx, 5
0x180076c41  jbe     short loc_180076C9D
0x180076c43  call    cs:__imp_GetCurrentThreadId
0x180076c49  mov     [rsp+38h+arg_0], eax
0x180076c4d  mov     [rsp+38h+arg_8], 0
0x180076c56  mov     r8, [rbx+110h]
0x180076c5d  cmp     byte ptr [r8+4], 0
0x180076c62  jz      short loc_180076C71
0x180076c64  lea     rcx, [r8+18h]; struct _GUID *
0x180076c68  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180076c6d  test    al, al
0x180076c6f  jz      short loc_180076C73
0x180076c71  xor     ecx, ecx
0x180076c73  add     r8, 8
0x180076c77  lea     rax, [rsp+38h+arg_0]
0x180076c7c  mov     [rsp+38h+var_10], rax
0x180076c81  lea     rax, [rsp+38h+arg_8]
0x180076c86  mov     [rsp+38h+var_18], rax
0x180076c8b  mov     r9, rcx
0x180076c8e  lea     rdx, byte_18009B8F7
0x180076c95  mov     rcx, rdi
0x180076c98  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180076c9d  lea     rcx, [rbx+120h]; this
0x180076ca4  cmp     dword ptr [rcx+18h], 0
0x180076ca8  jnz     short loc_180076CB0
0x180076caa  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180076caf  nop
0x180076cb0  mov     rbx, [rsp+38h+arg_10]
0x180076cb5  add     rsp, 30h
0x180076cb9  pop     rdi
0x180076cba  retn
```
