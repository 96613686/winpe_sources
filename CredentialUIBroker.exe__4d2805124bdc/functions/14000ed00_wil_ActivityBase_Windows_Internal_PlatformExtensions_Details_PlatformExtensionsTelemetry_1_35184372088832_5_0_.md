# wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)

- ea: `0x14000ed00`
- end: `0x14000ed81`
- name: `?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ`
- size: `129`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `15`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14000b584`
- `0x14000b658`
- `0x14000b6f4`
- `0x14000b7c8`
- `0x14000f750`
- `0x14000faa0`
- `0x14000fdf0`
- `0x140010140`
- `0x140014578`
- `0x1400147dc`
- `0x14001492c`
- `0x140014ac8`
- `0x140017060`
- `0x14001c0fc`
- `0x14001c16c`

## callees

- `0x140009158`
- `0x14000ed00`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000ed28`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000ed28`

## pseudocode

```c
RTL_SRWLOCK **__fastcall wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        __int64 a1,
        RTL_SRWLOCK **a2)
{
  RTL_SRWLOCK *v2; // rbx
  RTL_SRWLOCK *v4; // rbx
  RTL_SRWLOCK **v5; // rax
  int v6; // ecx
  int v7; // esi
  RTL_SRWLOCK *v9; // [rsp+30h] [rbp+8h] BYREF
  RTL_SRWLOCK *v10; // [rsp+38h] [rbp+10h] BYREF

  v2 = *(RTL_SRWLOCK **)(a1 + 280);
  if ( v2 )
  {
    v4 = v2 + 33;
    AcquireSRWLockExclusive(v4);
    v5 = &v10;
    v6 = 0;
    v7 = 1;
  }
  else
  {
    v4 = 0;
    v5 = &v9;
    v7 = 0;
    v6 = 2;
  }
  *a2 = v4;
  *v5 = 0;
  if ( v6 )
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  if ( v7 )
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  return a2;
}

```

## disassembly

```asm
0x14000ed00  mov     [rsp+arg_10], rbx
0x14000ed05  mov     [rsp+arg_18], rsi
0x14000ed0a  push    rdi
0x14000ed0b  sub     rsp, 20h
0x14000ed0f  mov     rbx, [rcx+118h]
0x14000ed16  mov     rdi, rdx
0x14000ed19  test    rbx, rbx
0x14000ed1c  jz      short loc_14000ED3C
0x14000ed1e  add     rbx, 108h
0x14000ed25  mov     rcx, rbx; SRWLock
0x14000ed28  call    cs:__imp_AcquireSRWLockExclusive
0x14000ed2e  lea     rax, [rsp+28h+arg_8]
0x14000ed33  xor     ecx, ecx
0x14000ed35  mov     esi, 1
0x14000ed3a  jmp     short loc_14000ED48
0x14000ed3c  xor     ebx, ebx
0x14000ed3e  lea     rax, [rsp+28h+arg_0]
0x14000ed43  xor     esi, esi
0x14000ed45  lea     ecx, [rbx+2]
0x14000ed48  mov     [rdi], rbx
0x14000ed4b  mov     qword ptr [rax], 0
0x14000ed52  test    ecx, ecx
0x14000ed54  jz      short loc_14000ED60
0x14000ed56  lea     rcx, [rsp+28h+arg_0]
0x14000ed5b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000ed60  test    esi, esi
0x14000ed62  jz      short loc_14000ED6E
0x14000ed64  lea     rcx, [rsp+28h+arg_8]
0x14000ed69  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000ed6e  mov     rbx, [rsp+28h+arg_10]
0x14000ed73  mov     rax, rdi
0x14000ed76  mov     rsi, [rsp+28h+arg_18]
0x14000ed7b  add     rsp, 20h
0x14000ed7f  pop     rdi
0x14000ed80  retn
```
