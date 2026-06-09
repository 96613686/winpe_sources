# RadioManager::_RemoveInstance(wchar_t const *)

- ea: `0x180021f9c`
- end: `0x180022144`
- name: `?_RemoveInstance@RadioManager@@AEAAXPEB_W@Z`
- size: `424`
- prototype: `void __fastcall(RadioManager *__hidden this, const wchar_t *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18001d4b4`
- `0x18001f090`

## callees

- `0x180001c7c`
- `0x1800085e4`
- `0x18000879c`
- `0x18000a43c`
- `0x18000c2a4`
- `0x18000d2a0`
- `0x18001b4ec`
- `0x18002195c`
- `0x180021f9c`
- `0x1800232b8`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021fce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021fce`

## string_xrefs

- `0x180022075`: `Removed radio instances maching given instance ID`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RadioManager::_RemoveInstance(struct _RTL_CRITICAL_SECTION *this, const wchar_t *a2)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  HANDLE LockSemaphore; // rcx
  ULONG_PTR SpinCount; // rsi
  __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // r14
  ULONG_PTR v9; // r15
  __int64 v10; // rax
  unsigned int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // [rsp+20h] [rbp-50h]
  int v16; // [rsp+28h] [rbp-48h]
  unsigned int v17; // [rsp+40h] [rbp-30h] BYREF
  const char *v18; // [rsp+48h] [rbp-28h] BYREF
  const wchar_t *v19; // [rsp+50h] [rbp-20h] BYREF
  struct _RTL_CRITICAL_SECTION *v20; // [rsp+58h] [rbp-18h] BYREF
  const wchar_t *v21; // [rsp+60h] [rbp-10h] BYREF

  v21 = a2;
  v3 = this + 6;
  EnterCriticalSection(this + 6);
  v20 = v3;
  LockSemaphore = this[7].LockSemaphore;
  SpinCount = this[7].SpinCount;
  v6 = (__int64)(SpinCount - (_QWORD)LockSemaphore) >> 3;
  v8 = std::remove_if_std::unique_ptr_RADIO_INSTANCE_std::default_delete_RADIO_INSTANCE_______RadioManager::_RemoveInstance_::_2_::_lambda_1___(
         LockSemaphore,
         SpinCount,
         &v21);
  if ( v8 != SpinCount )
  {
    v9 = this[7].SpinCount;
    while ( SpinCount != v9 )
    {
      std::unique_ptr<RADIO_INSTANCE>::operator=<std::default_delete<RADIO_INSTANCE>,0>(v8, SpinCount);
      v8 += 8;
      SpinCount += 8LL;
    }
    std::_Destroy_range<std::allocator<std::unique_ptr<RADIO_INSTANCE>>>(v8, this[7].SpinCount);
    this[7].SpinCount = v8;
  }
  v10 = (__int64)(this[7].SpinCount - (unsigned __int64)this[7].LockSemaphore) >> 3;
  if ( (unsigned int)v10 >= (unsigned int)v6 )
  {
    if ( (unsigned int)dword_180037050 > 4 )
    {
      v19 = v21;
      v18 = "Radio instance does not exist for given instance ID";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
        v7,
        &word_18002F1D6);
    }
  }
  else
  {
    v11 = v6 - v10;
    ProtectedSystemState::DecrementRadioInstances((ProtectedSystemState *)&this[1].LockCount, v11);
    if ( (unsigned int)dword_180037050 > 4 )
    {
      v18 = (const char *)v21;
      v17 = v11;
      v19 = (const wchar_t *)"Removed radio instances maching given instance ID";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v12,
        (unsigned __int8 *)&dword_18002F21C,
        v13,
        v14,
        &v19,
        (__int64)&v17,
        (__int64 **)&v18);
    }
    LOBYTE(v16) = 1;
    LOBYTE(v15) = 1;
    (*(void (__fastcall **)(ULONG_PTR *, __int64, _QWORD, const wchar_t *, int, int, _DWORD))(this->SpinCount + 32))(
      &this->SpinCount,
      1,
      0,
      v21,
      v15,
      v16,
      0);
    RadioManager::_NotifySysRadioChanged((RadioManager *)this);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v20);
}

```

## disassembly

```asm
0x180021f9c  mov     [rsp-28h+arg_10], rbx
0x180021fa1  push    rbp
0x180021fa2  push    rsi
0x180021fa3  push    rdi
0x180021fa4  push    r14
0x180021fa6  push    r15
0x180021fa8  mov     rbp, rsp
0x180021fab  sub     rsp, 70h
0x180021faf  mov     rax, cs:__security_cookie
0x180021fb6  xor     rax, rsp
0x180021fb9  mov     [rbp+var_8], rax
0x180021fbd  mov     rdi, rcx
0x180021fc0  mov     [rbp+var_10], rdx
0x180021fc4  lea     rbx, [rcx+0F0h]
0x180021fcb  mov     rcx, rbx; lpCriticalSection
0x180021fce  call    cs:__imp_EnterCriticalSection
0x180021fd4  mov     [rbp+var_18], rbx
0x180021fd8  mov     rcx, [rdi+130h]
0x180021fdf  mov     rsi, [rdi+138h]
0x180021fe6  mov     rbx, rsi
0x180021fe9  sub     rbx, rcx
0x180021fec  sar     rbx, 3
0x180021ff0  lea     r8, [rbp+var_10]
0x180021ff4  mov     rdx, rsi
0x180021ff7  call    std__remove_if_std__unique_ptr_RADIO_INSTANCE_std__default_delete_RADIO_INSTANCE_______RadioManager___RemoveInstance____2____lambda_1___
0x180021ffc  mov     r14, rax
0x180021fff  cmp     rax, rsi
0x180022002  jz      short loc_180022038
0x180022004  mov     r15, [rdi+138h]
0x18002200b  jmp     short loc_18002201D
0x18002200d  mov     rdx, rsi
0x180022010  call    ??$?4U?$default_delete@URADIO_INSTANCE@@@std@@$0A@@?$unique_ptr@URADIO_INSTANCE@@U?$default_delete@URADIO_INSTANCE@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<RADIO_INSTANCE>::operator=<std::default_delete<RADIO_INSTANCE>,0>(std::unique_ptr<RADIO_INSTANCE> &&)
0x180022015  add     r14, 8
0x180022019  add     rsi, 8
0x18002201d  mov     rcx, r14
0x180022020  cmp     rsi, r15
0x180022023  jnz     short loc_18002200D
0x180022025  mov     rdx, [rdi+138h]
0x18002202c  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@URADIO_INSTANCE@@U?$default_delete@URADIO_INSTANCE@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@URADIO_INSTANCE@@U?$default_delete@URADIO_INSTANCE@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@URADIO_INSTANCE@@U?$default_delete@URADIO_INSTANCE@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<RADIO_INSTANCE>>>(std::unique_ptr<RADIO_INSTANCE> *,std::unique_ptr<RADIO_INSTANCE> * const,std::allocator<std::unique_ptr<RADIO_INSTANCE>> &)
0x180022031  mov     [rdi+138h], r14
0x180022038  mov     rax, [rdi+138h]
0x18002203f  sub     rax, [rdi+130h]
0x180022046  sar     rax, 3
0x18002204a  cmp     eax, ebx
0x18002204c  jnb     loc_1800220DE
0x180022052  sub     ebx, eax
0x180022054  lea     rcx, [rdi+30h]; this
0x180022058  mov     edx, ebx; unsigned int
0x18002205a  call    ?DecrementRadioInstances@ProtectedSystemState@@QEAAXK@Z; ProtectedSystemState::DecrementRadioInstances(ulong)
0x18002205f  mov     eax, cs:dword_180037050
0x180022065  cmp     eax, 4
0x180022068  jbe     short loc_1800220A7
0x18002206a  mov     rax, [rbp+var_10]
0x18002206e  mov     [rbp+var_28], rax
0x180022072  mov     [rbp+var_30], ebx
0x180022075  lea     rax, aRemovedRadioIn; "Removed radio instances maching given i"...
0x18002207c  mov     [rbp+var_20], rax
0x180022080  lea     rax, [rbp+var_28]
0x180022084  mov     [rsp+70h+var_40], rax
0x180022089  lea     rax, [rbp+var_30]
0x18002208d  mov     [rsp+70h+var_48], rax
0x180022092  lea     rax, [rbp+var_20]
0x180022096  mov     [rsp+70h+var_50], rax
0x18002209b  lea     rdx, dword_18002F21C
0x1800220a2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x1800220a7  lea     rcx, [rdi+20h]
0x1800220ab  mov     rax, [rcx]
0x1800220ae  mov     dword ptr [rsp+70h+var_40], 0
0x1800220b6  mov     byte ptr [rsp+70h+var_48], 1
0x1800220bb  mov     byte ptr [rsp+70h+var_50], 1
0x1800220c0  mov     r9, [rbp+var_10]
0x1800220c4  xor     r8d, r8d
0x1800220c7  lea     edx, [r8+1]
0x1800220cb  mov     rax, [rax+20h]
0x1800220cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220d4  mov     rcx, rdi; this
0x1800220d7  call    ?_NotifySysRadioChanged@RadioManager@@AEAAXXZ; RadioManager::_NotifySysRadioChanged(void)
0x1800220dc  jmp     short loc_18002211B
0x1800220de  mov     eax, cs:dword_180037050
0x1800220e4  cmp     eax, 4
0x1800220e7  jbe     short loc_18002211B
0x1800220e9  mov     rax, [rbp+var_10]
0x1800220ed  mov     [rbp+var_20], rax
0x1800220f1  lea     rax, aRadioInstanceD; "Radio instance does not exist for given"...
0x1800220f8  mov     [rbp+var_28], rax
0x1800220fc  lea     rax, [rbp+var_20]
0x180022100  mov     [rsp+70h+var_48], rax
0x180022105  lea     rax, [rbp+var_28]
0x180022109  mov     [rsp+70h+var_50], rax
0x18002210e  lea     rdx, word_18002F1D6
0x180022115  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x18002211a  nop
0x18002211b  lea     rcx, [rbp+var_18]
0x18002211f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180022124  mov     rcx, [rbp+var_8]
0x180022128  xor     rcx, rsp; StackCookie
0x18002212b  call    __security_check_cookie
0x180022130  mov     rbx, [rsp+70h+arg_10]
0x180022138  add     rsp, 70h
0x18002213c  pop     r15
0x18002213e  pop     r14
0x180022140  pop     rdi
0x180022141  pop     rsi
0x180022142  pop     rbp
0x180022143  retn
```
