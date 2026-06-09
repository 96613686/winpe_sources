# TimeUpdate::InactivityCallback(void)

- ea: `0x18000743c`
- end: `0x18000752d`
- name: `?InactivityCallback@TimeUpdate@@AEAAXXZ`
- size: `241`
- prototype: `void __fastcall(TimeUpdate *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x180003bd0`

## callees

- `0x180001054`
- `0x1800012f0`
- `0x180002a70`
- `0x1800037ec`
- `0x180005840`
- `0x18000743c`
- `0x180007a5c`
- `0x18000b86c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007465`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007465`

## pseudocode

```c
void __fastcall TimeUpdate::InactivityCallback(TimeUpdate *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  bool IsQueueEmpty; // bl
  bool v4; // si
  struct _RTL_CRITICAL_SECTION *v5; // rdx
  bool v6; // [rsp+30h] [rbp-29h] BYREF
  bool v7; // [rsp+31h] [rbp-28h] BYREF
  struct _RTL_CRITICAL_SECTION *v8[9]; // [rsp+38h] [rbp-21h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v8[0] = v1;
  IsQueueEmpty = WNFNotificationDispatcher::IsQueueEmpty((TimeUpdate *)((char *)this + 64));
  v4 = WNFNotificationDispatcher::IsQueueEmpty((TimeUpdate *)((char *)this + 144));
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v8);
  if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 1) )
  {
    v8[8] = v5;
    v8[7] = (struct _RTL_CRITICAL_SECTION *)&v6;
    v8[6] = v5;
    v8[5] = (struct _RTL_CRITICAL_SECTION *)&v7;
    v6 = v4;
    v7 = IsQueueEmpty;
    tlgWriteTransfer_EventWriteTransfer(&dword_18001C010, &word_18001685E, 0, 0);
  }
  if ( TimeUpdate::IsRunning(this) && v4 && IsQueueEmpty )
    InitiateStop();
}

```

## disassembly

```asm
0x18000743c  push    rbp
0x18000743e  push    rbx
0x18000743f  push    rsi
0x180007440  push    rdi
0x180007441  lea     rbp, [rsp-3Fh]
0x180007446  sub     rsp, 98h
0x18000744d  mov     rax, cs:__security_cookie
0x180007454  xor     rax, rsp
0x180007457  mov     [rbp+57h+var_30], rax
0x18000745b  lea     rbx, [rcx+10h]
0x18000745f  mov     rdi, rcx
0x180007462  mov     rcx, rbx; lpCriticalSection
0x180007465  call    cs:__imp_EnterCriticalSection
0x18000746b  lea     rcx, [rdi+40h]; this
0x18000746f  mov     [rbp+57h+var_78], rbx
0x180007473  call    ?IsQueueEmpty@WNFNotificationDispatcher@@QEBA_NXZ; WNFNotificationDispatcher::IsQueueEmpty(void)
0x180007478  lea     rcx, [rdi+90h]; this
0x18000747f  mov     bl, al
0x180007481  call    ?IsQueueEmpty@WNFNotificationDispatcher@@QEBA_NXZ; WNFNotificationDispatcher::IsQueueEmpty(void)
0x180007486  lea     rcx, [rbp+57h+var_78]
0x18000748a  mov     sil, al
0x18000748d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180007492  mov     ecx, cs:dword_18001C010
0x180007498  cmp     ecx, 4
0x18000749b  jbe     short loc_1800074FB
0x18000749d  mov     edx, 1
0x1800074a2  lea     rcx, dword_18001C010
0x1800074a9  call    _tlgKeywordOn
0x1800074ae  test    al, al
0x1800074b0  jz      short loc_1800074FB
0x1800074b2  lea     rax, [rbp+57h+var_80]
0x1800074b6  mov     [rbp+57h+var_38], rdx
0x1800074ba  mov     [rbp+57h+var_40], rax
0x1800074be  lea     rcx, dword_18001C010
0x1800074c5  lea     rax, [rbp+57h+var_7F]
0x1800074c9  mov     [rbp+57h+var_48], rdx
0x1800074cd  mov     [rbp+57h+var_50], rax
0x1800074d1  lea     rdx, word_18001685E
0x1800074d8  lea     rax, [rbp+57h+var_70]
0x1800074dc  mov     [rbp+57h+var_80], sil
0x1800074e0  mov     [rsp+0B0h+var_88], rax
0x1800074e5  xor     r9d, r9d
0x1800074e8  xor     r8d, r8d
0x1800074eb  mov     [rsp+0B0h+var_90], 4
0x1800074f3  mov     [rbp+57h+var_7F], bl
0x1800074f6  call    _tlgWriteTransfer_EventWriteTransfer
0x1800074fb  mov     rcx, rdi; this
0x1800074fe  call    ?IsRunning@TimeUpdate@@AEBA_NXZ; TimeUpdate::IsRunning(void)
0x180007503  test    al, al
0x180007505  jz      short loc_180007515
0x180007507  test    sil, sil
0x18000750a  jz      short loc_180007515
0x18000750c  test    bl, bl
0x18000750e  jz      short loc_180007515
0x180007510  call    ?InitiateStop@@YAXXZ; InitiateStop(void)
0x180007515  mov     rcx, [rbp+57h+var_30]
0x180007519  xor     rcx, rsp; StackCookie
0x18000751c  call    __security_check_cookie
0x180007521  add     rsp, 98h
0x180007528  pop     rdi
0x180007529  pop     rsi
0x18000752a  pop     rbx
0x18000752b  pop     rbp
0x18000752c  retn
```
