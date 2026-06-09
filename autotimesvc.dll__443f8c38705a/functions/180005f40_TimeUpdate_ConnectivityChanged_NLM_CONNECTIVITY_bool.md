# TimeUpdate::ConnectivityChanged(NLM_CONNECTIVITY,bool)

- ea: `0x180005f40`
- end: `0x18000600b`
- name: `?ConnectivityChanged@TimeUpdate@@AEAAXW4NLM_CONNECTIVITY@@_N@Z`
- size: `203`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, enum NLM_CONNECTIVITY, char)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180006020`
- `0x1800081ac`
- `0x180009bb8`

## callees

- `0x180001218`
- `0x1800012f0`
- `0x180005840`
- `0x180005f40`
- `0x18000b668`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005f5e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005f5e`

## pseudocode

```c
void __fastcall TimeUpdate::ConnectivityChanged(struct _RTL_CRITICAL_SECTION *this, enum NLM_CONNECTIVITY a2, char a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  _BYTE *v7; // rax
  struct _RTL_CRITICAL_SECTION *v8; // [rsp+50h] [rbp+8h] BYREF
  enum NLM_CONNECTIVITY v9; // [rsp+60h] [rbp+18h]

  v3 = this + 15;
  EnterCriticalSection(this + 15);
  v8 = v3;
  v7 = (char *)&this[14].SpinCount + 4;
  if ( !a3 || !*v7 )
  {
    *v7 = 1;
    if ( LODWORD(this[14].SpinCount) != a2 )
    {
      LODWORD(this[14].SpinCount) = a2;
      if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 0x400000000200LL) )
      {
        v9 = a2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_18001C010,
          (__int64)&dword_180016454,
          0,
          0);
      }
      WNFNotificationDispatcher::Enqueue(&this[1].LockSemaphore, (this[14].SpinCount & 0x660) != 0 ? 16 : 1);
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v8);
}

```

## disassembly

```asm
0x180005f40  mov     [rsp+arg_8], rbx
0x180005f45  push    rbp
0x180005f46  push    rsi
0x180005f47  push    rdi
0x180005f48  sub     rsp, 30h
0x180005f4c  lea     rbx, [rcx+258h]
0x180005f53  mov     rsi, rcx
0x180005f56  mov     rcx, rbx; lpCriticalSection
0x180005f59  mov     dil, r8b
0x180005f5c  mov     ebp, edx
0x180005f5e  call    cs:__imp_EnterCriticalSection
0x180005f64  mov     [rsp+48h+arg_0], rbx
0x180005f69  lea     rax, [rsi+254h]
0x180005f70  test    dil, dil
0x180005f73  jz      short loc_180005F7A
0x180005f75  cmp     byte ptr [rax], 0
0x180005f78  jnz     short loc_180005FF4
0x180005f7a  mov     byte ptr [rax], 1
0x180005f7d  cmp     [rsi+250h], ebp
0x180005f83  jz      short loc_180005FF4
0x180005f85  mov     [rsi+250h], ebp
0x180005f8b  mov     eax, cs:dword_18001C010
0x180005f91  cmp     eax, 4
0x180005f94  jbe     short loc_180005FD7
0x180005f96  mov     rdx, 400000000200h
0x180005fa0  lea     rcx, dword_18001C010
0x180005fa7  call    _tlgKeywordOn
0x180005fac  test    al, al
0x180005fae  jz      short loc_180005FD7
0x180005fb0  lea     rax, [rsp+48h+arg_10]
0x180005fb5  mov     [rsp+48h+arg_10], ebp
0x180005fb9  xor     r9d, r9d
0x180005fbc  mov     [rsp+48h+var_28], rax
0x180005fc1  xor     r8d, r8d
0x180005fc4  lea     rdx, dword_180016454
0x180005fcb  lea     rcx, dword_18001C010
0x180005fd2  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180005fd7  mov     eax, [rsi+250h]
0x180005fdd  lea     rcx, [rsi+40h]
0x180005fe1  and     eax, 660h
0x180005fe6  neg     eax
0x180005fe8  sbb     edx, edx
0x180005fea  and     edx, 0Fh
0x180005fed  inc     edx
0x180005fef  call    ?Enqueue@WNFNotificationDispatcher@@QEAA_NW4ActionType@@@Z; WNFNotificationDispatcher::Enqueue(ActionType)
0x180005ff4  lea     rcx, [rsp+48h+arg_0]
0x180005ff9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180005ffe  mov     rbx, [rsp+48h+arg_8]
0x180006003  add     rsp, 30h
0x180006007  pop     rdi
0x180006008  pop     rsi
0x180006009  pop     rbp
0x18000600a  retn
```
