# Windows::Storage::StateABIImplementation::ClearOperation::EnumerateAndDeleteContainerItems(void *,tag_ENUMERATE_ITEM_TYPE)

- ea: `0x1800238d8`
- end: `0x180023aa8`
- name: `?EnumerateAndDeleteContainerItems@ClearOperation@StateABIImplementation@Storage@Windows@@AEAAJPEAXW4tag_ENUMERATE_ITEM_TYPE@@@Z`
- size: `464`
- prototype: `HRESULT __fastcall(Windows::Storage::StateABIImplementation::ClearOperation *this, void *rootContainer, tag_ENUMERATE_ITEM_TYPE enumItemType)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180023748`

## callees

- `0x180009778`
- `0x18000d4bc`
- `0x180017120`
- `0x180018fb8`
- `0x1800238d8`
- `0x180025004`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800239ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800239ce`
- `ext-ms-win-appmodel-state-ext-l1-2-0!DeleteStateContainer` at `0x1800239bc`
- `ext-ms-win-appmodel-state-ext-l1-2-0!DeleteStateContainer` at `0x1800239bc`
- `ext-ms-win-appmodel-state-ext-l1-2-0!DeleteStateContainerValue` at `0x1800239c4`
- `ext-ms-win-appmodel-state-ext-l1-2-0!DeleteStateContainerValue` at `0x1800239c4`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIImplementation::ClearOperation::EnumerateAndDeleteContainerItems(
        Windows::Storage::StateABIImplementation::ClearOperation *this,
        void *rootContainer,
        tag_ENUMERATE_ITEM_TYPE enumItemType)
{
  HRESULT v6; // ebx
  tag_STATE_ENUM_ITEM *v7; // rcx
  tag_STATE_ENUM_ITEM *v8; // rcx
  tag_STATE_ENUM_ITEM *value; // rbx
  HRESULT v11; // esi
  wchar_t *Name; // rdx
  int v13; // eax
  signed int LastError; // eax
  HRESULT v15; // edi
  volatile Microsoft::WRL::Details::AsyncStatusInternal currentStatus; // ecx
  tag_STATE_ENUM_ITEM *v17; // rcx
  wistd::unique_ptr<tag_STATE_ENUM_ITEM,wistd::default_delete<tag_STATE_ENUM_ITEM> > apisetContainerEnumerationResult; // [rsp+30h] [rbp-20h] BYREF
  wil::details::out_param_t<wistd::unique_ptr<tag_STATE_ENUM_ITEM,wistd::default_delete<tag_STATE_ENUM_ITEM> > > v19; // [rsp+38h] [rbp-18h] BYREF
  void *retaddr; // [rsp+78h] [rbp+28h]
  signed __int32 v21; // [rsp+98h] [rbp+48h] BYREF

  apisetContainerEnumerationResult.__ptr_.__value_ = 0;
  v19.pRaw = 0;
  v19.replace = 1;
  v19.wrapper = &apisetContainerEnumerationResult;
  v6 = Windows::Storage::StateABIHelpers::EnumerateApiSetItems(
         rootContainer,
         Windows::Storage::StateABIHelpers::ApiSetEnumerateContainer,
         enumItemType,
         &v19.pRaw);
  wil::details::out_param_t<wistd::unique_ptr<tag_STATE_ENUM_ITEM,wistd::default_delete<tag_STATE_ENUM_ITEM>>>::~out_param_t<wistd::unique_ptr<tag_STATE_ENUM_ITEM,wistd::default_delete<tag_STATE_ENUM_ITEM>>>(&v19);
  if ( v6 >= 0 )
  {
    value = apisetContainerEnumerationResult.__ptr_.__value_;
    v11 = 0;
    if ( apisetContainerEnumerationResult.__ptr_.__value_ )
    {
      do
      {
        Name = value->Name;
        if ( enumItemType == ENUMERATE_ITEM_SUBCONTAINER )
          v13 = DeleteStateContainer(rootContainer, Name);
        else
          v13 = DeleteStateContainerValue(rootContainer, Name);
        if ( !v13 )
        {
          LastError = GetLastError();
          v15 = LastError;
          if ( LastError != 4312 )
          {
            if ( LastError > 0 )
              v15 = (unsigned __int16)LastError | 0x80070000;
            if ( v15 < 0 )
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                0x218u,
                "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.clearoperation.cpp",
                v15);
              if ( v11 >= 0 )
                v11 = v15;
            }
          }
        }
        currentStatus = this->currentStatus_;
        v21 = -2;
        _InterlockedCompareExchange(&v21, currentStatus, -2);
        if ( v21 )
          break;
        value = (tag_STATE_ENUM_ITEM *)value->pNext;
      }
      while ( value );
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x229u,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.clearoperation.cpp",
          v11,
          "Type %u",
          enumItemType);
        v17 = apisetContainerEnumerationResult.__ptr_.__value_;
        apisetContainerEnumerationResult.__ptr_.__value_ = 0;
        if ( v17 )
          operator delete(v17);
        return (unsigned int)v11;
      }
      value = apisetContainerEnumerationResult.__ptr_.__value_;
    }
    apisetContainerEnumerationResult.__ptr_.__value_ = 0;
    if ( value )
    {
      v7 = value;
LABEL_28:
      operator delete(v7);
    }
    return 0;
  }
  if ( v6 == -2147024637 )
  {
    v7 = apisetContainerEnumerationResult.__ptr_.__value_;
    apisetContainerEnumerationResult.__ptr_.__value_ = 0;
    if ( v7 )
      goto LABEL_28;
    return 0;
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    0x1F7u,
    "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.clearoperation.cpp",
    v6,
    "EnumerateApiSetItems %u",
    enumItemType);
  v8 = apisetContainerEnumerationResult.__ptr_.__value_;
  apisetContainerEnumerationResult.__ptr_.__value_ = 0;
  if ( v8 )
    operator delete(v8);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800238d8  mov     [rsp-28h+arg_0], rbx
0x1800238dd  mov     [rsp-28h+arg_8], rsi
0x1800238e2  push    rbp
0x1800238e3  push    rdi
0x1800238e4  push    r13
0x1800238e6  push    r14
0x1800238e8  push    r15
0x1800238ea  mov     rbp, rsp
0x1800238ed  sub     rsp, 50h
0x1800238f1  mov     r15, rootContainer
0x1800238f4  mov     [rbp+apisetContainerEnumerationResult.__ptr_.__value_], 0
0x1800238fc  mov     r13, this
0x1800238ff  mov     [rbp+var_18.pRaw], 0
0x180023907  lea     rax, [rbp+apisetContainerEnumerationResult]
0x18002390b  mov     [rbp+var_18.replace], 1
0x18002390f  mov     this, r15; stateHandle
0x180023912  mov     [rbp+var_18.wrapper], rax
0x180023916  lea     r9, [rbp+var_18.pRaw]; apisetEnumerationResult
0x18002391a  mov     r14d, enumItemType
0x18002391d  lea     rootContainer, ?ApiSetEnumerateContainer@StateABIHelpers@Storage@Windows@@YAJPEAXW4tag_ENUMERATE_ITEM_TYPE@@PEAUtag_STATE_ENUM_ITEM@@PEAI@Z; fnEnumerator
0x180023924  call    ?EnumerateApiSetItems@StateABIHelpers@Storage@Windows@@YAJPEAXP6AJ0W4tag_ENUMERATE_ITEM_TYPE@@PEAUtag_STATE_ENUM_ITEM@@PEAI@Z1PEAPEAU5@@Z; Windows::Storage::StateABIHelpers::EnumerateApiSetItems(void *,long (*)(void *,tag_ENUMERATE_ITEM_TYPE,tag_STATE_ENUM_ITEM *,uint *),tag_ENUMERATE_ITEM_TYPE,tag_STATE_ENUM_ITEM * *)
0x180023929  lea     this, [rbp+var_18]; this
0x18002392d  mov     ebx, eax
0x18002392f  call    ??1?$out_param_t@V?$unique_ptr@Utag_STATE_ENUM_ITEM@@U?$default_delete@Utag_STATE_ENUM_ITEM@@@wistd@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<tag_STATE_ENUM_ITEM,wistd::default_delete<tag_STATE_ENUM_ITEM>>>::~out_param_t<wistd::unique_ptr<tag_STATE_ENUM_ITEM,wistd::default_delete<tag_STATE_ENUM_ITEM>>>(void)
0x180023934  test    ebx, ebx
0x180023936  jns     short loc_1800239A0
0x180023938  cmp     ebx, 80070103h
0x18002393e  jnz     short loc_18002395A
0x180023940  mov     this, [rbp+apisetContainerEnumerationResult.__ptr_.__value_]
0x180023944  mov     [rbp+apisetContainerEnumerationResult.__ptr_.__value_], 0
0x18002394c  test    this, this
0x18002394f  jz      loc_180023A8D
0x180023955  jmp     loc_180023A88
0x18002395a  mov     this, [rbp+28h]; callerReturnAddress
0x18002395e  lea     rax, aEnumerateapise; "EnumerateApiSetItems %u"
0x180023965  mov     [rsp+50h+var_28], r14d
0x18002396a  lea     r8, aOnecoreuapBase_23; "onecoreuap\\base\\appmodel\\statemanage"...
0x180023971  mov     r9d, ebx; hr
0x180023974  mov     [rsp+50h+formatString], rax; formatString
0x180023979  mov     edx, 1F7h; lineNumber
0x18002397e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180023983  mov     this, [rbp+apisetContainerEnumerationResult.__ptr_.__value_]; p
0x180023987  mov     [rbp+apisetContainerEnumerationResult.__ptr_.__value_], 0
0x18002398f  test    this, this
0x180023992  jz      short loc_180023999
0x180023994  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023999  mov     eax, ebx
0x18002399b  jmp     loc_180023A8F
0x1800239a0  mov     rbx, [rbp+apisetContainerEnumerationResult.__ptr_.__value_]
0x1800239a4  xor     esi, esi
0x1800239a6  test    rbx, rbx
0x1800239a9  jz      loc_180023A78
0x1800239af  mov     rootContainer, [rbx+8]
0x1800239b3  mov     this, r15
0x1800239b6  cmp     r14d, 1
0x1800239ba  jnz     short loc_1800239C4
0x1800239bc  call    cs:__imp_DeleteStateContainer
0x1800239c2  jmp     short loc_1800239CA
0x1800239c4  call    cs:__imp_DeleteStateContainerValue
0x1800239ca  test    eax, eax
0x1800239cc  jnz     short loc_180023A0B
0x1800239ce  call    cs:__imp_GetLastError
0x1800239d4  mov     edi, eax
0x1800239d6  cmp     eax, 10D8h
0x1800239db  jz      short loc_180023A0B
0x1800239dd  test    eax, eax
0x1800239df  jle     short loc_1800239EA
0x1800239e1  movzx   edi, ax
0x1800239e4  or      edi, 80070000h
0x1800239ea  test    edi, edi
0x1800239ec  jns     short loc_180023A0B
0x1800239ee  mov     this, [rbp+28h]; callerReturnAddress
0x1800239f2  lea     r8, aOnecoreuapBase_23; "onecoreuap\\base\\appmodel\\statemanage"...
0x1800239f9  mov     r9d, edi; hr
0x1800239fc  mov     edx, 218h; lineNumber
0x180023a01  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180023a06  test    esi, esi
0x180023a08  cmovns  esi, edi
0x180023a0b  mov     ecx, [r13+48h]
0x180023a0f  mov     [rbp+arg_18], 0FFFFFFFEh
0x180023a16  mov     eax, [rbp+arg_18]
0x180023a19  lock cmpxchg [rbp+arg_18], ecx
0x180023a1e  cmp     [rbp+arg_18], 0
0x180023a22  jnz     short loc_180023A2D
0x180023a24  mov     rbx, [rbx+10h]
0x180023a28  test    rbx, rbx
0x180023a2b  jnz     short loc_1800239AF
0x180023a2d  test    esi, esi
0x180023a2f  jns     short loc_180023A74
0x180023a31  mov     this, [rbp+28h]; callerReturnAddress
0x180023a35  lea     rax, aTypeU; "Type %u"
0x180023a3c  mov     [rsp+50h+var_28], r14d
0x180023a41  lea     r8, aOnecoreuapBase_23; "onecoreuap\\base\\appmodel\\statemanage"...
0x180023a48  mov     r9d, esi; hr
0x180023a4b  mov     [rsp+50h+formatString], rax; formatString
0x180023a50  mov     edx, 229h; lineNumber
0x180023a55  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180023a5a  mov     this, [rbp+apisetContainerEnumerationResult.__ptr_.__value_]; p
0x180023a5e  mov     [rbp+apisetContainerEnumerationResult.__ptr_.__value_], 0
0x180023a66  test    this, this
0x180023a69  jz      short loc_180023A70
0x180023a6b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023a70  mov     eax, esi
0x180023a72  jmp     short loc_180023A8F
0x180023a74  mov     rbx, [rbp+apisetContainerEnumerationResult.__ptr_.__value_]
0x180023a78  mov     [rbp+apisetContainerEnumerationResult.__ptr_.__value_], 0
0x180023a80  test    rbx, rbx
0x180023a83  jz      short loc_180023A8D
0x180023a85  mov     this, rbx; p
0x180023a88  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023a8d  xor     eax, eax
0x180023a8f  lea     r11, [rsp+50h+var_s0]
0x180023a94  mov     rbx, [r11+30h]
0x180023a98  mov     rsi, [r11+38h]
0x180023a9c  mov     rsp, r11
0x180023a9f  pop     r15
0x180023aa1  pop     r14
0x180023aa3  pop     r13
0x180023aa5  pop     rdi
0x180023aa6  pop     rbp
0x180023aa7  retn
```
