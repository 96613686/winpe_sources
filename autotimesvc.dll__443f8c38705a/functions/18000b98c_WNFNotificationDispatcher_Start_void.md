# WNFNotificationDispatcher::Start(void)

- ea: `0x18000b98c`
- end: `0x18000b9e7`
- name: `?Start@WNFNotificationDispatcher@@QEAAXXZ`
- size: `91`
- prototype: `void __fastcall(WNFNotificationDispatcher *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180007534`
- `0x1800098d4`

## callees

- `0x180005840`
- `0x18000b98c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b9a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b9a0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000b9c8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000b9c8`

## pseudocode

```c
void __fastcall WNFNotificationDispatcher::Start(WNFNotificationDispatcher *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  struct _TP_WORK *v3; // rcx
  struct _RTL_CRITICAL_SECTION *v4; // [rsp+30h] [rbp+8h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v4 = v1;
  if ( !*((_BYTE *)this + 56) )
  {
    v3 = (struct _TP_WORK *)*((_QWORD *)this + 8);
    if ( v3 )
    {
      *((_BYTE *)this + 56) = 1;
      if ( *(_DWORD *)this )
      {
        if ( !*((_BYTE *)this + 57) )
        {
          SubmitThreadpoolWork(v3);
          *((_BYTE *)this + 57) = 1;
        }
      }
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v4);
}

```

## disassembly

```asm
0x18000b98c  mov     [rsp+arg_8], rbx
0x18000b991  push    rdi
0x18000b992  sub     rsp, 20h
0x18000b996  lea     rbx, [rcx+10h]
0x18000b99a  mov     rdi, rcx
0x18000b99d  mov     rcx, rbx; lpCriticalSection
0x18000b9a0  call    cs:__imp_EnterCriticalSection
0x18000b9a6  xor     eax, eax
0x18000b9a8  mov     [rsp+28h+arg_0], rbx
0x18000b9ad  cmp     [rdi+38h], al
0x18000b9b0  jnz     short loc_18000B9D2
0x18000b9b2  mov     rcx, [rdi+40h]; pwk
0x18000b9b6  test    rcx, rcx
0x18000b9b9  jz      short loc_18000B9D2
0x18000b9bb  mov     byte ptr [rdi+38h], 1
0x18000b9bf  cmp     [rdi], eax
0x18000b9c1  jz      short loc_18000B9D2
0x18000b9c3  cmp     [rdi+39h], al
0x18000b9c6  jnz     short loc_18000B9D2
0x18000b9c8  call    cs:__imp_SubmitThreadpoolWork
0x18000b9ce  mov     byte ptr [rdi+39h], 1
0x18000b9d2  lea     rcx, [rsp+28h+arg_0]
0x18000b9d7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000b9dc  mov     rbx, [rsp+28h+arg_8]
0x18000b9e1  add     rsp, 20h
0x18000b9e5  pop     rdi
0x18000b9e6  retn
```
