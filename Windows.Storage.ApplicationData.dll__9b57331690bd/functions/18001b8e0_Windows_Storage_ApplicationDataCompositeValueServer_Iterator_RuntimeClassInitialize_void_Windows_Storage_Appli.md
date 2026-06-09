# Windows::Storage::ApplicationDataCompositeValueServer::Iterator::RuntimeClassInitialize(void *,Windows::Storage::ApplicationDataCompositeValueServer *)

- ea: `0x18001b8e0`
- end: `0x18001b9ff`
- name: `?RuntimeClassInitialize@Iterator@ApplicationDataCompositeValueServer@Storage@Windows@@MEAAJPEAXPEAV234@@Z`
- size: `287`
- prototype: `HRESULT __fastcall(Windows::Storage::ApplicationDataCompositeValueServer::Iterator *this, void *atomHandle, Windows::Storage::ApplicationDataCompositeValueServer *compositeServerInstance)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005ee0`
- `0x180009778`
- `0x18000d4bc`
- `0x18001b8e0`
- `0x180021efc`
- `0x180021fc4`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001b9cd`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001b9cd`

## string_xrefs

- `0x18001b9a0`: `onecoreuap\base\appmodel\statemanager\winrt\lib\windows.storage.applicationdatacompositevalue.server.cpp`
- `0x18001b9e9`: `onecoreuap\base\appmodel\statemanager\winrt\lib\windows.storage.applicationdatacompositevalue.server.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Storage::ApplicationDataCompositeValueServer::Iterator::RuntimeClassInitialize(
        Windows::Storage::ApplicationDataCompositeValueServer::Iterator *this,
        void *atomHandle,
        Windows::Storage::ApplicationDataCompositeValueServer *compositeServerInstance)
{
  tag_STATE_ENUM_ITEM **p_compositeEnumerationResult; // rsi
  Windows::Storage::ApplicationDataCompositeValueServer *ptr; // rcx
  unsigned int v8; // edi
  unsigned int v10; // edx
  void *retaddr; // [rsp+58h] [rbp+0h]

  p_compositeEnumerationResult = &this->compositeEnumerationResult;
  if ( this->compositeEnumerationResult )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( !atomHandle )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
    RoOriginateError(2147942487LL, 0);
    v10 = 728;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v10,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacompositevalue.server.cpp",
      -2147024809);
    return 2147942487LL;
  }
  if ( !compositeServerInstance )
  {
    v10 = 731;
    goto LABEL_14;
  }
  if ( this->compositeServer.ptr_ != compositeServerInstance )
  {
    compositeServerInstance->AddRef(compositeServerInstance);
    ptr = this->compositeServer.ptr_;
    this->compositeServer.ptr_ = compositeServerInstance;
    if ( ptr )
      ptr->Release(ptr);
  }
  v8 = Windows::Storage::StateABIHelpers::EnumerateApiSetItems(
         atomHandle,
         Windows::Storage::StateABIHelpers::ApiSetEnumerateAtom,
         ENUMERATE_ITEM_SETTINGS,
         p_compositeEnumerationResult);
  if ( (int)(v8 + 0x80000000) < 0 || v8 == -2147024637 )
  {
    this->compositeEnumerationResultCurrent = *p_compositeEnumerationResult;
    return 0;
  }
  else
  {
    Windows::Storage::StateABIHelpers::ReportError(v8, 7u);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x2EBu,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacompositevalue.server.cpp",
      v8,
      "EnumerateApiSetItems");
    return v8;
  }
}

```

## disassembly

```asm
0x18001b8e0  push    rbx
0x18001b8e2  push    rbp
0x18001b8e3  push    rsi
0x18001b8e4  push    rdi
0x18001b8e5  sub     rsp, 38h
0x18001b8e9  lea     rsi, [this+30h]
0x18001b8ed  mov     rdi, compositeServerInstance
0x18001b8f0  cmp     qword ptr [rsi], 0
0x18001b8f4  mov     rbp, atomHandle
0x18001b8f7  mov     rbx, this
0x18001b8fa  jnz     loc_18001B9B5
0x18001b900  test    rbp, rbp
0x18001b903  jz      loc_18001B9BF
0x18001b909  test    rdi, rdi
0x18001b90c  jz      loc_18001B9DA
0x18001b912  cmp     [rbx+20h], rdi
0x18001b916  jz      short loc_18001B940
0x18001b918  mov     rax, [rdi]
0x18001b91b  mov     this, rdi
0x18001b91e  mov     rax, [rax+8]
0x18001b922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b927  mov     this, [rbx+20h]
0x18001b92b  mov     [rbx+20h], rdi
0x18001b92f  test    this, this
0x18001b932  jz      short loc_18001B940
0x18001b934  mov     rax, [this]
0x18001b937  mov     rax, [rax+10h]
0x18001b93b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b940  mov     r9, rsi; apisetEnumerationResult
0x18001b943  lea     atomHandle, ?ApiSetEnumerateAtom@StateABIHelpers@Storage@Windows@@YAJPEAXW4tag_ENUMERATE_ITEM_TYPE@@PEAUtag_STATE_ENUM_ITEM@@PEAI@Z; fnEnumerator
0x18001b94a  mov     r8d, 2; enumerationType
0x18001b950  mov     this, rbp; stateHandle
0x18001b953  call    ?EnumerateApiSetItems@StateABIHelpers@Storage@Windows@@YAJPEAXP6AJ0W4tag_ENUMERATE_ITEM_TYPE@@PEAUtag_STATE_ENUM_ITEM@@PEAI@Z1PEAPEAU5@@Z; Windows::Storage::StateABIHelpers::EnumerateApiSetItems(void *,long (*)(void *,tag_ENUMERATE_ITEM_TYPE,tag_STATE_ENUM_ITEM *,uint *),tag_ENUMERATE_ITEM_TYPE,tag_STATE_ENUM_ITEM * *)
0x18001b958  mov     edi, eax
0x18001b95a  mov     eax, 80000000h
0x18001b95f  lea     ecx, [rdi+rax]
0x18001b962  test    eax, ecx
0x18001b964  jz      short loc_18001B978
0x18001b966  mov     rax, [rsi]
0x18001b969  mov     [rbx+38h], rax
0x18001b96d  xor     eax, eax
0x18001b96f  add     rsp, 38h
0x18001b973  pop     rdi
0x18001b974  pop     rsi
0x18001b975  pop     rbp
0x18001b976  pop     rbx
0x18001b977  retn
0x18001b978  cmp     edi, 80070103h
0x18001b97e  jz      short loc_18001B966
0x18001b980  mov     edx, 7; idsValue
0x18001b985  mov     ecx, edi; hr
0x18001b987  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x18001b98c  mov     this, [rsp+58h]; callerReturnAddress
0x18001b991  lea     rax, aEnumerateapise_0; "EnumerateApiSetItems"
0x18001b998  mov     r9d, edi; hr
0x18001b99b  mov     [rsp+58h+formatString], rax; formatString
0x18001b9a0  lea     compositeServerInstance, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\statemanage"...
0x18001b9a7  mov     edx, 2EBh; lineNumber
0x18001b9ac  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001b9b1  mov     eax, edi
0x18001b9b3  jmp     short loc_18001B96F
0x18001b9b5  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "this->compositeEnumerationResult == nullptr")
0x18001b9ba  jmp     loc_18001B900
0x18001b9bf  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "FALSE")
0x18001b9c4  mov     ebx, 80070057h
0x18001b9c9  xor     edx, edx
0x18001b9cb  mov     ecx, ebx
0x18001b9cd  call    cs:__imp_RoOriginateError
0x18001b9d3  mov     edx, 2D8h
0x18001b9d8  jmp     short loc_18001B9E4
0x18001b9da  mov     ebx, 80070057h
0x18001b9df  mov     edx, 2DBh; lineNumber
0x18001b9e4  mov     this, [rsp+58h]; callerReturnAddress
0x18001b9e9  lea     compositeServerInstance, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\statemanage"...
0x18001b9f0  mov     r9d, ebx; hr
0x18001b9f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b9f8  mov     eax, ebx
0x18001b9fa  jmp     loc_18001B96F
```
