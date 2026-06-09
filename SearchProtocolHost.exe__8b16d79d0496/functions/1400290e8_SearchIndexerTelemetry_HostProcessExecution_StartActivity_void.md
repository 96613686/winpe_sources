# SearchIndexerTelemetry::HostProcessExecution::StartActivity(void)

- ea: `0x1400290e8`
- end: `0x140029256`
- name: `?StartActivity@HostProcessExecution@SearchIndexerTelemetry@@QEAAXXZ`
- size: `366`
- prototype: `void __fastcall(SearchIndexerTelemetry::HostProcessExecution *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14003a8e8`

## callees

- `0x1400023dc`
- `0x140002408`
- `0x140005240`
- `0x14000f30c`
- `0x14001fb34`
- `0x1400290e8`
- `0x1400292c4`
- `0x1400361a4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140029154`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140029154`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400291a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400291a0`

## pseudocode

```c
void __fastcall SearchIndexerTelemetry::HostProcessExecution::StartActivity(
        SearchIndexerTelemetry::HostProcessExecution *this)
{
  __int64 v2; // rbx
  _DWORD *v3; // rcx
  __int64 v4; // rdx
  _DWORD *v5; // rbx
  __int64 v6; // r8
  const GUID *v7; // r9
  DWORD CurrentThreadId; // [rsp+38h] [rbp-19h] BYREF
  _QWORD v9[3]; // [rsp+40h] [rbp-11h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+58h] [rbp+7h] BYREF
  _QWORD *v11; // [rsp+78h] [rbp+27h]
  __int64 v12; // [rsp+80h] [rbp+2Fh]
  DWORD *p_CurrentThreadId; // [rsp+88h] [rbp+37h]
  __int64 v14; // [rsp+90h] [rbp+3Fh]

  v9[1] = -2;
  wil::ActivityBase<SearchIndexerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &CurrentThreadId);
  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD **)(wil::details::static_lazy<SearchIndexerLogging>::get() + 8);
  if ( *v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL) )
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  else
    *(_OWORD *)(v2 + 8) = 0;
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&CurrentThreadId);
  v5 = *(_DWORD **)(wil::details::static_lazy<SearchIndexerLogging>::get() + 8);
  if ( *v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v9[0] = 0;
    v6 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v6 + 4)
      || (v7 = (const GUID *)(v6 + 24), !*(_DWORD *)(v6 + 24))
      && !*(_DWORD *)(v6 + 28)
      && !*(_DWORD *)(v6 + 32)
      && !*(_DWORD *)(v6 + 36) )
    {
      v7 = 0;
    }
    p_CurrentThreadId = &CurrentThreadId;
    v14 = 4;
    v11 = v9;
    v12 = 8;
    tlgWriteTransfer_EventWriteTransfer(
      (__int64)v5,
      (unsigned __int8 *)byte_14008420B,
      (const GUID *)(v6 + 8),
      v7,
      4u,
      &v10);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (SearchIndexerTelemetry::HostProcessExecution *)((char *)this + 288),
      v4);
}

```

## disassembly

```asm
0x1400290e8  mov     rax, rsp
0x1400290eb  push    rbp
0x1400290ec  lea     rbp, [rax-5Fh]
0x1400290f0  sub     rsp, 0A0h
0x1400290f7  mov     [rbp+57h+var_60], 0FFFFFFFFFFFFFFFEh
0x1400290ff  mov     [rax+10h], rbx
0x140029103  mov     [rax+18h], rdi
0x140029107  mov     rax, cs:__security_cookie
0x14002910e  xor     rax, rsp
0x140029111  mov     [rbp+57h+var_10], rax
0x140029115  mov     rdi, rcx
0x140029118  lea     rdx, [rbp+57h+var_70]
0x14002911c  call    ?LockExclusive@?$ActivityBase@VSearchIndexerLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SearchIndexerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140029121  mov     rbx, [rdi+110h]
0x140029128  call    ?get@?$static_lazy@VSearchIndexerLogging@@@details@wil@@QEAAPEAVSearchIndexerLogging@@P6AXXZ@Z; wil::details::static_lazy<SearchIndexerLogging>::get(void (*)(void))
0x14002912d  mov     rcx, [rax+8]
0x140029131  mov     eax, [rcx]
0x140029133  cmp     eax, 5
0x140029136  jbe     short loc_14002915C
0x140029138  mov     rdx, 400000000000h
0x140029142  call    _tlgKeywordOn
0x140029147  test    al, al
0x140029149  jz      short loc_14002915C
0x14002914b  lea     rdx, [rbx+8]; ActivityId
0x14002914f  mov     ecx, 3; ControlCode
0x140029154  call    cs:__imp_EventActivityIdControl
0x14002915a  jmp     short loc_140029163
0x14002915c  xorps   xmm0, xmm0
0x14002915f  movups  xmmword ptr [rbx+8], xmm0
0x140029163  mov     dword ptr [rbx], 1
0x140029169  lea     rcx, [rbp+57h+var_70]
0x14002916d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140029172  call    ?get@?$static_lazy@VSearchIndexerLogging@@@details@wil@@QEAAPEAVSearchIndexerLogging@@P6AXXZ@Z; wil::details::static_lazy<SearchIndexerLogging>::get(void (*)(void))
0x140029177  mov     rbx, [rax+8]
0x14002917b  mov     eax, [rbx]
0x14002917d  cmp     eax, 5
0x140029180  jbe     loc_140029222
0x140029186  mov     rdx, 400000000000h
0x140029190  mov     rcx, rbx
0x140029193  call    _tlgKeywordOn
0x140029198  test    al, al
0x14002919a  jz      loc_140029222
0x1400291a0  call    cs:__imp_GetCurrentThreadId
0x1400291a6  mov     [rbp+57h+var_70], eax
0x1400291a9  mov     [rbp+57h+var_68], 0
0x1400291b1  mov     r8, [rdi+110h]
0x1400291b8  cmp     byte ptr [r8+4], 0
0x1400291bd  jz      short loc_1400291DE
0x1400291bf  lea     r9, [r8+18h]
0x1400291c3  cmp     dword ptr [r9], 0
0x1400291c7  jnz     short loc_1400291E1
0x1400291c9  cmp     dword ptr [r9+4], 0
0x1400291ce  jnz     short loc_1400291E1
0x1400291d0  cmp     dword ptr [r9+8], 0
0x1400291d5  jnz     short loc_1400291E1
0x1400291d7  cmp     dword ptr [r9+0Ch], 0
0x1400291dc  jnz     short loc_1400291E1
0x1400291de  xor     r9d, r9d
0x1400291e1  lea     rax, [rbp+57h+var_70]
0x1400291e5  mov     [rbp+57h+var_20], rax
0x1400291e9  mov     ecx, 4
0x1400291ee  mov     [rbp+57h+var_18], rcx
0x1400291f2  lea     rax, [rbp+57h+var_68]
0x1400291f6  mov     [rbp+57h+var_30], rax
0x1400291fa  mov     [rbp+57h+var_28], 8
0x140029202  add     r8, 8
0x140029206  lea     rax, [rbp+57h+var_50]
0x14002920a  mov     [rsp+0A0h+var_78], rax
0x14002920f  mov     dword ptr [rsp+0A0h+var_80], ecx
0x140029213  lea     rdx, byte_14008420B
0x14002921a  mov     rcx, rbx
0x14002921d  call    _tlgWriteTransfer_EventWriteTransfer
0x140029222  lea     rcx, [rdi+120h]; this
0x140029229  cmp     dword ptr [rcx+18h], 0
0x14002922d  jnz     short loc_140029235
0x14002922f  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x140029234  nop
0x140029235  mov     rcx, [rbp+57h+var_10]
0x140029239  xor     rcx, rsp; StackCookie
0x14002923c  call    __security_check_cookie
0x140029241  lea     r11, [rsp+0A0h+var_s0]
0x140029249  mov     rbx, [r11+18h]
0x14002924d  mov     rdi, [r11+20h]
0x140029251  mov     rsp, r11
0x140029254  pop     rbp
0x140029255  retn
```
