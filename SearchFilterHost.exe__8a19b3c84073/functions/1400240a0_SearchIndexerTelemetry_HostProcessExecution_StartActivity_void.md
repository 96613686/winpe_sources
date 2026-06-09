# SearchIndexerTelemetry::HostProcessExecution::StartActivity(void)

- ea: `0x1400240a0`
- end: `0x14002420c`
- name: `?StartActivity@HostProcessExecution@SearchIndexerTelemetry@@QEAAXXZ`
- size: `364`
- prototype: `void __fastcall(SearchIndexerTelemetry::HostProcessExecution *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14002753c`

## callees

- `0x14000185c`
- `0x140001888`
- `0x1400030a0`
- `0x1400067e4`
- `0x1400152b4`
- `0x140021b14`
- `0x140022688`
- `0x1400240a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140024156`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140024156`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14002410b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14002410b`

## pseudocode

```c
void __fastcall SearchIndexerTelemetry::HostProcessExecution::StartActivity(
        SearchIndexerTelemetry::HostProcessExecution *this)
{
  __int64 v2; // rbx
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  __int64 v5; // r9
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rbx
  __int64 v11; // r8
  const GUID *v12; // r9
  RTL_SRWLOCK *v13; // [rsp+38h] [rbp-19h] BYREF
  _QWORD v14[3]; // [rsp+40h] [rbp-11h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+58h] [rbp+7h] BYREF
  _QWORD *v16; // [rsp+78h] [rbp+27h]
  __int64 v17; // [rsp+80h] [rbp+2Fh]
  RTL_SRWLOCK **v18; // [rsp+88h] [rbp+37h]
  __int64 v19; // [rsp+90h] [rbp+3Fh]

  v14[1] = -2;
  wil::ActivityBase<SearchIndexerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &v13);
  v2 = *((_QWORD *)this + 34);
  v3 = SearchIndexerLogging::Provider();
  if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL, v4, v5) )
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  else
    *(_OWORD *)(v2 + 8) = 0;
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
  v6 = SearchIndexerLogging::Provider();
  v10 = (__int64)v6;
  if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL, v8, v9) )
  {
    LODWORD(v13) = GetCurrentThreadId();
    v14[0] = 0;
    v11 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v11 + 4)
      || (v12 = (const GUID *)(v11 + 24), !*(_DWORD *)(v11 + 24))
      && !*(_DWORD *)(v11 + 28)
      && !*(_DWORD *)(v11 + 32)
      && !*(_DWORD *)(v11 + 36) )
    {
      v12 = 0;
    }
    v18 = &v13;
    v19 = 4;
    v16 = v14;
    v17 = 8;
    tlgWriteTransfer_EventWriteTransfer(v10, (unsigned __int8 *)word_14005CF92, (const GUID *)(v11 + 8), v12, 4u, &v15);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (SearchIndexerTelemetry::HostProcessExecution *)((char *)this + 288),
      v7);
}

```

## disassembly

```asm
0x1400240a0  mov     rax, rsp
0x1400240a3  push    rbp
0x1400240a4  lea     rbp, [rax-5Fh]
0x1400240a8  sub     rsp, 0A0h
0x1400240af  mov     [rbp+57h+var_60], 0FFFFFFFFFFFFFFFEh
0x1400240b7  mov     [rax+10h], rbx
0x1400240bb  mov     [rax+18h], rdi
0x1400240bf  mov     rax, cs:__security_cookie
0x1400240c6  xor     rax, rsp
0x1400240c9  mov     [rbp+57h+var_10], rax
0x1400240cd  mov     rdi, rcx
0x1400240d0  lea     rdx, [rbp+57h+var_70]
0x1400240d4  call    ?LockExclusive@?$ActivityBase@VSearchIndexerLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SearchIndexerLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400240d9  mov     rbx, [rdi+110h]
0x1400240e0  call    ?Provider@SearchIndexerLogging@@SAPEBU_tlgProvider_t@@XZ; SearchIndexerLogging::Provider(void)
0x1400240e5  mov     edx, [rax]
0x1400240e7  cmp     edx, 5
0x1400240ea  jbe     short loc_140024113
0x1400240ec  mov     rdx, 400000000000h
0x1400240f6  mov     rcx, rax
0x1400240f9  call    _tlgKeywordOn
0x1400240fe  test    al, al
0x140024100  jz      short loc_140024113
0x140024102  lea     rdx, [rbx+8]; ActivityId
0x140024106  mov     ecx, 3; ControlCode
0x14002410b  call    cs:__imp_EventActivityIdControl
0x140024111  jmp     short loc_14002411A
0x140024113  xorps   xmm0, xmm0
0x140024116  movups  xmmword ptr [rbx+8], xmm0
0x14002411a  mov     dword ptr [rbx], 1
0x140024120  lea     rcx, [rbp+57h+var_70]
0x140024124  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140024129  call    ?Provider@SearchIndexerLogging@@SAPEBU_tlgProvider_t@@XZ; SearchIndexerLogging::Provider(void)
0x14002412e  mov     rbx, rax
0x140024131  mov     ecx, [rax]
0x140024133  cmp     ecx, 5
0x140024136  jbe     loc_1400241D8
0x14002413c  mov     rdx, 400000000000h
0x140024146  mov     rcx, rax
0x140024149  call    _tlgKeywordOn
0x14002414e  test    al, al
0x140024150  jz      loc_1400241D8
0x140024156  call    cs:__imp_GetCurrentThreadId
0x14002415c  mov     dword ptr [rbp+57h+var_70], eax
0x14002415f  mov     [rbp+57h+var_68], 0
0x140024167  mov     r8, [rdi+110h]
0x14002416e  cmp     byte ptr [r8+4], 0
0x140024173  jz      short loc_140024194
0x140024175  lea     r9, [r8+18h]
0x140024179  cmp     dword ptr [r9], 0
0x14002417d  jnz     short loc_140024197
0x14002417f  cmp     dword ptr [r9+4], 0
0x140024184  jnz     short loc_140024197
0x140024186  cmp     dword ptr [r9+8], 0
0x14002418b  jnz     short loc_140024197
0x14002418d  cmp     dword ptr [r9+0Ch], 0
0x140024192  jnz     short loc_140024197
0x140024194  xor     r9d, r9d
0x140024197  lea     rax, [rbp+57h+var_70]
0x14002419b  mov     [rbp+57h+var_20], rax
0x14002419f  mov     ecx, 4
0x1400241a4  mov     [rbp+57h+var_18], rcx
0x1400241a8  lea     rax, [rbp+57h+var_68]
0x1400241ac  mov     [rbp+57h+var_30], rax
0x1400241b0  mov     [rbp+57h+var_28], 8
0x1400241b8  add     r8, 8
0x1400241bc  lea     rax, [rbp+57h+var_50]
0x1400241c0  mov     [rsp+0A0h+var_78], rax
0x1400241c5  mov     dword ptr [rsp+0A0h+var_80], ecx
0x1400241c9  lea     rdx, word_14005CF92
0x1400241d0  mov     rcx, rbx
0x1400241d3  call    _tlgWriteTransfer_EventWriteTransfer
0x1400241d8  lea     rcx, [rdi+120h]; this
0x1400241df  cmp     dword ptr [rcx+18h], 0
0x1400241e3  jnz     short loc_1400241EB
0x1400241e5  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1400241ea  nop
0x1400241eb  mov     rcx, [rbp+57h+var_10]
0x1400241ef  xor     rcx, rsp; StackCookie
0x1400241f2  call    __security_check_cookie
0x1400241f7  lea     r11, [rsp+0A0h+var_s0]
0x1400241ff  mov     rbx, [r11+18h]
0x140024203  mov     rdi, [r11+20h]
0x140024207  mov     rsp, r11
0x14002420a  pop     rbp
0x14002420b  retn
```
